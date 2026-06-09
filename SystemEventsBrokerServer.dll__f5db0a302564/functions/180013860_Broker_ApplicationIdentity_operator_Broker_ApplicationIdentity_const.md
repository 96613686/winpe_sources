# Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)

- ea: `0x180013860`
- end: `0x180013911`
- name: `??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z`
- size: `177`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ae14`
- `0x18001bcdc`
- `0x18001be34`
- `0x180020220`

## callees

- `0x180013860`
- `0x180022434`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800138bb`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800138bb`

## pseudocode

```c
char __fastcall Broker::ApplicationIdentity::operator!=(__int64 a1, __int64 a2)
{
  const WCHAR *lpString2; // rax
  const WCHAR *v5; // r8
  size_t v6; // rax
  size_t v7; // r8
  int v8; // eax

  lpString2 = (const WCHAR *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 48) > 7u )
    lpString2 = *(const WCHAR **)lpString2;
  v5 = (const WCHAR *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 48) > 7u )
    v5 = *(const WCHAR **)v5;
  if ( CompareStringEx(&LocaleName, 1u, v5, *(_DWORD *)(a1 + 40), lpString2, *(_DWORD *)(a2 + 40), 0, 0, 0) != 2
    || (v6 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2, v7 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1, v7 < v6)
    || v7 > v6
    || (v8 = memcmp_0(*(const void **)a1, *(const void **)a2, v7)) != 0 )
  {
    LOBYTE(v8) = 1;
  }
  return v8;
}

```

## disassembly

```asm
0x180013860  mov     [rsp+arg_0], rbx
0x180013865  mov     [rsp+arg_8], rsi
0x18001386a  push    rdi
0x18001386b  sub     rsp, 50h
0x18001386f  cmp     qword ptr [rdx+30h], 7
0x180013874  lea     rax, [rdx+18h]
0x180013878  mov     rbx, rcx
0x18001387b  mov     rdi, rdx
0x18001387e  mov     ecx, [rdx+28h]
0x180013881  jbe     short loc_180013886
0x180013883  mov     rax, [rax]
0x180013886  cmp     qword ptr [rbx+30h], 7
0x18001388b  lea     r8, [rbx+18h]; lpString1
0x18001388f  ja      short loc_18001390C
0x180013891  mov     r9d, [rbx+28h]; cchCount1
0x180013895  xor     esi, esi
0x180013897  mov     [rsp+58h+lParam], rsi; lParam
0x18001389c  mov     edx, 1; dwCmpFlags
0x1800138a1  mov     [rsp+58h+lpReserved], rsi; lpReserved
0x1800138a6  mov     [rsp+58h+lpVersionInformation], rsi; lpVersionInformation
0x1800138ab  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x1800138af  lea     rcx, LocaleName; lpLocaleName
0x1800138b6  mov     [rsp+58h+lpString2], rax; lpString2
0x1800138bb  call    cs:__imp_CompareStringEx
0x1800138c1  cmp     eax, 2
0x1800138c4  jnz     short loc_1800138FA
0x1800138c6  mov     rdx, [rdi]; Buf2
0x1800138c9  mov     rax, [rdi+8]
0x1800138cd  mov     rcx, [rbx]; Buf1
0x1800138d0  sub     rax, rdx
0x1800138d3  mov     r8, [rbx+8]
0x1800138d7  sub     r8, rcx; Size
0x1800138da  cmp     r8, rax
0x1800138dd  jb      short loc_1800138FA
0x1800138df  ja      short loc_1800138FA
0x1800138e1  call    memcmp_0
0x1800138e6  test    eax, eax
0x1800138e8  jnz     short loc_1800138FA
0x1800138ea  mov     rbx, [rsp+58h+arg_0]
0x1800138ef  mov     rsi, [rsp+58h+arg_8]
0x1800138f4  add     rsp, 50h
0x1800138f8  pop     rdi
0x1800138f9  retn
0x1800138fa  mov     rbx, [rsp+58h+arg_0]
0x1800138ff  mov     al, 1
0x180013901  mov     rsi, [rsp+58h+arg_8]
0x180013906  add     rsp, 50h
0x18001390a  pop     rdi
0x18001390b  retn
0x18001390c  mov     r8, [r8]
0x18001390f  jmp     short loc_180013891
```
