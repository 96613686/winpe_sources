# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18004b524`
- end: `0x18004b63f`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z`
- size: `283`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c87c`

## callees

- `0x180002740`
- `0x180010350`
- `0x180044ac6`
- `0x18004b524`
- `0x180060bd0`

## import_xrefs

- `msvcrt!realloc` at `0x18004b5ca`
- `msvcrt!realloc` at `0x18004b5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b61f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b61f`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rsi
  unsigned int v7; // ebx
  SIZE_T v8; // r15
  LPVOID v9; // rax
  void *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  int v13; // eax
  void *v14; // rax
  __int64 result; // rax

  v6 = (void **)WinMalloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v7 = 2 * ocslen(a3) + 2;
  v8 = 2 * (unsigned int)ocslen(a2) + 2;
  *v6 = CoTaskMemAlloc(v8);
  v9 = CoTaskMemAlloc(v7);
  v10 = *v6;
  v6[1] = v9;
  if ( !v10 || !v9 )
  {
    CoTaskMemFree(v10);
    CoTaskMemFree(v6[1]);
    WinFree(v6);
    return 2147942414LL;
  }
  memcpy_0(v10, a2, (unsigned int)v8);
  memcpy_0(v6[1], a3, v7);
  v11 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) != v11 )
  {
LABEL_8:
    result = 0;
    *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
    return result;
  }
  v12 = *(void **)this;
  v13 = 2 * v11;
  *((_DWORD *)this + 3) = v13;
  v14 = realloc(v12, 8LL * v13);
  if ( v14 )
  {
    *(_QWORD *)this = v14;
    goto LABEL_8;
  }
  CoTaskMemFree(*v6);
  CoTaskMemFree(v6[1]);
  WinFree(v6);
  *((int *)this + 3) /= 2;
  return 2147942414LL;
}

```

## disassembly

```asm
0x18004b524  push    rbx
0x18004b526  push    rbp
0x18004b527  push    rsi
0x18004b528  push    rdi
0x18004b529  push    r14
0x18004b52b  push    r15
0x18004b52d  sub     rsp, 28h
0x18004b531  mov     rdi, rcx
0x18004b534  mov     rbp, r8
0x18004b537  mov     ecx, 10h; unsigned __int64
0x18004b53c  mov     r14, rdx
0x18004b53f  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x18004b544  mov     rsi, rax
0x18004b547  test    rax, rax
0x18004b54a  jz      loc_18004B62D
0x18004b550  mov     rcx, rbp; unsigned __int16 *
0x18004b553  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18004b558  mov     rcx, r14; unsigned __int16 *
0x18004b55b  lea     ebx, ds:2[rax*2]
0x18004b562  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18004b567  lea     eax, ds:2[rax*2]
0x18004b56e  mov     ecx, eax; cb
0x18004b570  mov     r15d, eax
0x18004b573  call    cs:__imp_CoTaskMemAlloc
0x18004b579  mov     ecx, ebx; cb
0x18004b57b  mov     [rsi], rax
0x18004b57e  call    cs:__imp_CoTaskMemAlloc
0x18004b584  mov     rcx, [rsi]; pv
0x18004b587  mov     [rsi+8], rax
0x18004b58b  test    rcx, rcx
0x18004b58e  jz      loc_18004B615
0x18004b594  test    rax, rax
0x18004b597  jz      short loc_18004B615
0x18004b599  mov     r8d, r15d; Size
0x18004b59c  mov     rdx, r14; Src
0x18004b59f  call    memcpy_0
0x18004b5a4  mov     rcx, [rsi+8]; void *
0x18004b5a8  mov     r8d, ebx; Size
0x18004b5ab  mov     rdx, rbp; Src
0x18004b5ae  call    memcpy_0
0x18004b5b3  mov     eax, [rdi+0Ch]
0x18004b5b6  cmp     [rdi+8], eax
0x18004b5b9  jnz     short loc_18004B603
0x18004b5bb  mov     rcx, [rdi]; Block
0x18004b5be  add     eax, eax
0x18004b5c0  movsxd  rdx, eax
0x18004b5c3  shl     rdx, 3; Size
0x18004b5c7  mov     [rdi+0Ch], eax
0x18004b5ca  call    cs:__imp_realloc
0x18004b5d0  test    rax, rax
0x18004b5d3  jnz     short loc_18004B600
0x18004b5d5  mov     rcx, [rsi]; pv
0x18004b5d8  call    cs:__imp_CoTaskMemFree
0x18004b5de  mov     rcx, [rsi+8]; pv
0x18004b5e2  call    cs:__imp_CoTaskMemFree
0x18004b5e8  mov     rcx, rsi; void *
0x18004b5eb  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18004b5f0  mov     eax, [rdi+0Ch]
0x18004b5f3  mov     ecx, 2
0x18004b5f8  cdq
0x18004b5f9  idiv    ecx
0x18004b5fb  mov     [rdi+0Ch], eax
0x18004b5fe  jmp     short loc_18004B62D
0x18004b600  mov     [rdi], rax
0x18004b603  movsxd  rdx, dword ptr [rdi+8]
0x18004b607  xor     eax, eax
0x18004b609  mov     rcx, [rdi]
0x18004b60c  mov     [rcx+rdx*8], rsi
0x18004b610  inc     dword ptr [rdi+8]
0x18004b613  jmp     short loc_18004B632
0x18004b615  call    cs:__imp_CoTaskMemFree
0x18004b61b  mov     rcx, [rsi+8]; pv
0x18004b61f  call    cs:__imp_CoTaskMemFree
0x18004b625  mov     rcx, rsi; void *
0x18004b628  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18004b62d  mov     eax, 8007000Eh
0x18004b632  add     rsp, 28h
0x18004b636  pop     r15
0x18004b638  pop     r14
0x18004b63a  pop     rdi
0x18004b63b  pop     rsi
0x18004b63c  pop     rbp
0x18004b63d  pop     rbx
0x18004b63e  retn
```
