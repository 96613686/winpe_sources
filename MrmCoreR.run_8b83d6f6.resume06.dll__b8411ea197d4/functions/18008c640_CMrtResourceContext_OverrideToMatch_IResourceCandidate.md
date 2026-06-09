# CMrtResourceContext::OverrideToMatch(IResourceCandidate *)

- ea: `0x18008c640`
- end: `0x18008c76e`
- name: `?OverrideToMatch@CMrtResourceContext@@UEAAJPEAUIResourceCandidate@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CMrtResourceContext *__hidden this, struct IResourceCandidate *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002c8d0`
- `0x18008c640`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c71e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c71e`

## string_xrefs

- `0x18008c66e`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecontext.cpp`
- `0x18008c744`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecontext.cpp`

## pseudocode

```c
__int64 __fastcall CMrtResourceContext::OverrideToMatch(CMrtResourceContext *this, struct IResourceCandidate *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rax
  unsigned int v8; // ebx
  int v9; // esi
  __int64 v10; // rdx
  LPVOID pv[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+30h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v15; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 525;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecontext.cpp",
      (const char *)(unsigned int)v4,
      (int)pv[0]);
    return (unsigned int)v4;
  }
  v7 = *(_QWORD *)a2;
  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IResourceCandidate *, unsigned int *))(v7 + 48))(a2, &v15);
  if ( v4 < 0 )
  {
    v5 = 529;
    goto LABEL_3;
  }
  *(_OWORD *)pv = 0;
  v13 = 0;
  v8 = 0;
  v12 = 0;
  while ( v8 < v15 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IResourceCandidate *, _QWORD, LPVOID *))(*(_QWORD *)a2 + 56LL))(a2, v8, pv);
    if ( v9 < 0 )
    {
      v10 = 534;
      goto LABEL_17;
    }
    v9 = (*(__int64 (__fastcall **)(CMrtResourceContext *, LPVOID, LPVOID))(*(_QWORD *)this + 144LL))(
           this,
           pv[0],
           pv[1]);
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    if ( pv[1] )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
    }
    if ( v9 < 0 )
    {
      v10 = 547;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecontext.cpp",
        (const char *)(unsigned int)v9,
        (int)pv[0]);
      return (unsigned int)v9;
    }
    ++v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18008c640  mov     [rsp-18h+arg_0], rbx
0x18008c645  mov     [rsp-18h+arg_10], rsi
0x18008c64a  push    rbp
0x18008c64b  push    rdi
0x18008c64c  push    r14
0x18008c64e  mov     rbp, rsp
0x18008c651  sub     rsp, 50h
0x18008c655  mov     rdi, rdx
0x18008c658  mov     r14, rcx
0x18008c65b  test    rdx, rdx
0x18008c65e  jnz     short loc_18008C684
0x18008c660  mov     ebx, 80070057h
0x18008c665  mov     edx, 20Dh; void *
0x18008c66a  mov     rcx, [rbp+18h]; this
0x18008c66e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18008c675  mov     r9d, ebx; char *
0x18008c678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c67d  mov     eax, ebx
0x18008c67f  jmp     loc_18008C759
0x18008c684  mov     rax, [rdx]
0x18008c687  mov     rcx, rdi
0x18008c68a  lea     rdx, [rbp+arg_8]
0x18008c68e  mov     [rbp+arg_8], 0
0x18008c695  mov     rax, [rax+30h]
0x18008c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c69e  mov     ebx, eax
0x18008c6a0  test    eax, eax
0x18008c6a2  jns     short loc_18008C6AB
0x18008c6a4  mov     edx, 211h
0x18008c6a9  jmp     short loc_18008C66A
0x18008c6ab  xorps   xmm0, xmm0
0x18008c6ae  xor     eax, eax
0x18008c6b0  movups  xmmword ptr [rbp+pv], xmm0
0x18008c6b4  mov     [rbp+var_10], rax
0x18008c6b8  xor     ebx, ebx
0x18008c6ba  movups  [rbp+var_20], xmm0
0x18008c6be  cmp     ebx, [rbp+arg_8]
0x18008c6c1  jnb     loc_18008C757
0x18008c6c7  mov     rax, [rdi]
0x18008c6ca  lea     r8, [rbp+pv]
0x18008c6ce  mov     edx, ebx
0x18008c6d0  mov     rcx, rdi
0x18008c6d3  mov     rax, [rax+38h]
0x18008c6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c6dc  mov     esi, eax
0x18008c6de  test    eax, eax
0x18008c6e0  js      short loc_18008C73B
0x18008c6e2  mov     rax, [r14]
0x18008c6e5  mov     rcx, r14
0x18008c6e8  mov     r8, [rbp+pv+8]
0x18008c6ec  mov     rdx, [rbp+pv]
0x18008c6f0  mov     rax, [rax+90h]
0x18008c6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c6fc  mov     rcx, [rbp+pv]; pv
0x18008c700  mov     esi, eax
0x18008c702  test    rcx, rcx
0x18008c705  jz      short loc_18008C715
0x18008c707  call    cs:__imp_CoTaskMemFree
0x18008c70d  mov     [rbp+pv], 0
0x18008c715  mov     rcx, [rbp+pv+8]; pv
0x18008c719  test    rcx, rcx
0x18008c71c  jz      short loc_18008C72C
0x18008c71e  call    cs:__imp_CoTaskMemFree
0x18008c724  mov     [rbp+pv+8], 0
0x18008c72c  test    esi, esi
0x18008c72e  js      short loc_18008C734
0x18008c730  inc     ebx
0x18008c732  jmp     short loc_18008C6BE
0x18008c734  mov     edx, 223h
0x18008c739  jmp     short loc_18008C740
0x18008c73b  mov     edx, 216h; void *
0x18008c740  mov     rcx, [rbp+18h]; this
0x18008c744  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18008c74b  mov     r9d, esi; char *
0x18008c74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c753  mov     eax, esi
0x18008c755  jmp     short loc_18008C759
0x18008c757  xor     eax, eax
0x18008c759  lea     r11, [rsp+50h+var_s0]
0x18008c75e  mov     rbx, [r11+20h]
0x18008c762  mov     rsi, [r11+30h]
0x18008c766  mov     rsp, r11
0x18008c769  pop     r14
0x18008c76b  pop     rdi
0x18008c76c  pop     rbp
0x18008c76d  retn
```
