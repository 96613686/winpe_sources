# CEnumStreamMapBase::AddStreamMap(ulong,ushort const *,ulong,void *)

- ea: `0x1800279d0`
- end: `0x180027ac8`
- name: `?AddStreamMap@CEnumStreamMapBase@@QEAAJKPEBGKPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(CEnumStreamMapBase *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001e944`
- `0x1800277e8`

## callees

- `0x1800279d0`
- `0x180033dfd`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027a48`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027a48`
- `ole32!CoTaskMemFree` at `0x180027a37`
- `ole32!CoTaskMemFree` at `0x180027a8b`
- `ole32!CoTaskMemFree` at `0x180027a37`
- `ole32!CoTaskMemFree` at `0x180027a8b`
- `ole32!CoTaskMemAlloc` at `0x1800279ef`
- `ole32!CoTaskMemAlloc` at `0x180027a25`
- `ole32!CoTaskMemAlloc` at `0x180027a68`
- `ole32!CoTaskMemAlloc` at `0x1800279ef`
- `ole32!CoTaskMemAlloc` at `0x180027a25`
- `ole32!CoTaskMemAlloc` at `0x180027a68`

## pseudocode

```c
__int64 __fastcall CEnumStreamMapBase::AddStreamMap(
        CEnumStreamMapBase *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        void *Src)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  __int64 result; // rax
  __int64 v12; // rax
  __int64 v13; // r15
  LPVOID v14; // rax
  unsigned int v15; // edi
  void *v16; // rax
  _QWORD *v17; // rax

  v9 = CoTaskMemAlloc(0x30u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  *v9 = a2;
  v9[4] = a4;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = v12 + 1;
  v14 = CoTaskMemAlloc(2 * (v12 + 1));
  *((_QWORD *)v10 + 1) = v14;
  if ( !v14 )
  {
LABEL_6:
    CoTaskMemFree(v10);
    return 2147942414LL;
  }
  _o_wcscpy_s(v14, v13, a3);
  if ( Src )
  {
    v15 = a4 == 0 ? 8 : 0;
    v16 = CoTaskMemAlloc(v15);
    *((_QWORD *)v10 + 3) = v16;
    if ( !v16 )
    {
      CoTaskMemFree(*((LPVOID *)v10 + 1));
      goto LABEL_6;
    }
    memcpy_0(v16, Src, v15);
  }
  else
  {
    *((_QWORD *)v10 + 3) = 0;
  }
  v17 = (_QWORD *)*((_QWORD *)this + 5);
  *((_QWORD *)v10 + 5) = v17;
  *((_QWORD *)v10 + 4) = (char *)this + 32;
  *v17 = v10 + 8;
  ++*((_DWORD *)this + 14);
  ++*((_DWORD *)this + 15);
  result = 0;
  *((_QWORD *)this + 5) = v10 + 8;
  return result;
}

```

## disassembly

```asm
0x1800279d0  push    rbx
0x1800279d2  push    rbp
0x1800279d3  push    rsi
0x1800279d4  push    rdi
0x1800279d5  push    r12
0x1800279d7  push    r14
0x1800279d9  push    r15
0x1800279db  sub     rsp, 20h
0x1800279df  mov     rsi, rcx
0x1800279e2  mov     edi, r9d
0x1800279e5  mov     ecx, 30h ; '0'; cb
0x1800279ea  mov     r14, r8
0x1800279ed  mov     ebp, edx
0x1800279ef  call    cs:__imp_CoTaskMemAlloc
0x1800279f5  xor     r12d, r12d
0x1800279f8  mov     rbx, rax
0x1800279fb  test    rax, rax
0x1800279fe  jnz     short loc_180027A0A
0x180027a00  mov     eax, 8007000Eh
0x180027a05  jmp     loc_180027AB9
0x180027a0a  mov     [rax], ebp
0x180027a0c  mov     [rax+10h], edi
0x180027a0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027a13  inc     rax
0x180027a16  cmp     [r14+rax*2], r12w
0x180027a1b  jnz     short loc_180027A13
0x180027a1d  lea     r15, [rax+1]
0x180027a21  lea     rcx, [r15+r15]; cb
0x180027a25  call    cs:__imp_CoTaskMemAlloc
0x180027a2b  mov     [rbx+8], rax
0x180027a2f  test    rax, rax
0x180027a32  jnz     short loc_180027A3F
0x180027a34  mov     rcx, rbx; pv
0x180027a37  call    cs:__imp_CoTaskMemFree
0x180027a3d  jmp     short loc_180027A00
0x180027a3f  mov     r8, r14
0x180027a42  mov     rdx, r15
0x180027a45  mov     rcx, rax
0x180027a48  call    cs:__imp__o_wcscpy_s
0x180027a4e  mov     rbp, [rsp+58h+Src]
0x180027a56  test    rbp, rbp
0x180027a59  jz      short loc_180027A93
0x180027a5b  neg     edi
0x180027a5d  sbb     rdi, rdi
0x180027a60  not     rdi
0x180027a63  and     edi, 8
0x180027a66  mov     ecx, edi; cb
0x180027a68  call    cs:__imp_CoTaskMemAlloc
0x180027a6e  mov     [rbx+18h], rax
0x180027a72  test    rax, rax
0x180027a75  jz      short loc_180027A87
0x180027a77  mov     r8d, edi; Size
0x180027a7a  mov     rdx, rbp; Src
0x180027a7d  mov     rcx, rax; void *
0x180027a80  call    memcpy_0
0x180027a85  jmp     short loc_180027A97
0x180027a87  mov     rcx, [rbx+8]; pv
0x180027a8b  call    cs:__imp_CoTaskMemFree
0x180027a91  jmp     short loc_180027A34
0x180027a93  mov     [rbx+18h], r12
0x180027a97  lea     rdx, [rsi+20h]
0x180027a9b  mov     rax, [rdx+8]
0x180027a9f  lea     rcx, [rbx+20h]
0x180027aa3  mov     [rbx+28h], rax
0x180027aa7  mov     [rcx], rdx
0x180027aaa  mov     [rax], rcx
0x180027aad  inc     dword ptr [rsi+38h]
0x180027ab0  inc     dword ptr [rsi+3Ch]
0x180027ab3  xor     eax, eax
0x180027ab5  mov     [rdx+8], rcx
0x180027ab9  add     rsp, 20h
0x180027abd  pop     r15
0x180027abf  pop     r14
0x180027ac1  pop     r12
0x180027ac3  pop     rdi
0x180027ac4  pop     rsi
0x180027ac5  pop     rbp
0x180027ac6  pop     rbx
0x180027ac7  retn
```
