# Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)

- ea: `0x18000a0d0`
- end: `0x18000a183`
- name: `??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009bb0`
- `0x180009ee0`
- `0x1800187b8`
- `0x18001ab8c`

## callees

- `0x18000a0d0`
- `0x18001659e`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000a12b`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000a12b`

## pseudocode

```c
bool __fastcall Broker::ApplicationIdentity::operator!=(__int64 a1, __int64 a2)
{
  const WCHAR *lpString2; // rax
  const WCHAR *v5; // r8
  size_t v6; // rax
  size_t v7; // r8
  bool result; // al

  lpString2 = (const WCHAR *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 48) > 7u )
    lpString2 = *(const WCHAR **)lpString2;
  v5 = (const WCHAR *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 48) > 7u )
    v5 = *(const WCHAR **)v5;
  result = 1;
  if ( CompareStringEx(&LocaleName, 1u, v5, *(_DWORD *)(a1 + 40), lpString2, *(_DWORD *)(a2 + 40), 0, 0, 0) == 2 )
  {
    v6 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
    v7 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
    if ( v7 >= v6 && v7 <= v6 && !memcmp_0(*(const void **)a1, *(const void **)a2, v7) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a0d0  mov     [rsp+arg_0], rbx
0x18000a0d5  mov     [rsp+arg_8], rsi
0x18000a0da  push    rdi
0x18000a0db  sub     rsp, 50h
0x18000a0df  cmp     qword ptr [rdx+30h], 7
0x18000a0e4  lea     rax, [rdx+18h]
0x18000a0e8  mov     rbx, rcx
0x18000a0eb  mov     rdi, rdx
0x18000a0ee  mov     ecx, [rdx+28h]
0x18000a0f1  jbe     short loc_18000A0F6
0x18000a0f3  mov     rax, [rax]
0x18000a0f6  cmp     qword ptr [rbx+30h], 7
0x18000a0fb  lea     r8, [rbx+18h]; lpString1
0x18000a0ff  ja      short loc_18000A16C
0x18000a101  mov     r9d, [rbx+28h]; cchCount1
0x18000a105  xor     esi, esi
0x18000a107  mov     [rsp+58h+lParam], rsi; lParam
0x18000a10c  mov     edx, 1; dwCmpFlags
0x18000a111  mov     [rsp+58h+lpReserved], rsi; lpReserved
0x18000a116  mov     [rsp+58h+lpVersionInformation], rsi; lpVersionInformation
0x18000a11b  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x18000a11f  lea     rcx, LocaleName; lpLocaleName
0x18000a126  mov     [rsp+58h+lpString2], rax; lpString2
0x18000a12b  call    cs:__imp_CompareStringEx
0x18000a131  cmp     eax, 2
0x18000a134  jnz     short loc_18000A15A
0x18000a136  mov     rdx, [rdi]; Buf2
0x18000a139  mov     rax, [rdi+8]
0x18000a13d  mov     rcx, [rbx]; Buf1
0x18000a140  sub     rax, rdx
0x18000a143  mov     r8, [rbx+8]
0x18000a147  sub     r8, rcx; Size
0x18000a14a  cmp     r8, rax
0x18000a14d  jb      short loc_18000A15A
0x18000a14f  ja      short loc_18000A15A
0x18000a151  call    memcmp_0
0x18000a156  test    eax, eax
0x18000a158  jz      short loc_18000A171
0x18000a15a  mov     al, 1
0x18000a15c  mov     rbx, [rsp+58h+arg_0]
0x18000a161  mov     rsi, [rsp+58h+arg_8]
0x18000a166  add     rsp, 50h
0x18000a16a  pop     rdi
0x18000a16b  retn
0x18000a16c  mov     r8, [r8]
0x18000a16f  jmp     short loc_18000A101
0x18000a171  mov     rbx, [rsp+58h+arg_0]
0x18000a176  xor     al, al
0x18000a178  mov     rsi, [rsp+58h+arg_8]
0x18000a17d  add     rsp, 50h
0x18000a181  pop     rdi
0x18000a182  retn
```
