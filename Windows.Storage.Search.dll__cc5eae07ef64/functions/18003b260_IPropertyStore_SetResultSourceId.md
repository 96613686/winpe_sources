# IPropertyStore_SetResultSourceId

- ea: `0x18003b260`
- end: `0x18003b462`
- name: `IPropertyStore_SetResultSourceId`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b4054`

## callees

- `0x18003b260`
- `0x180063a68`
- `0x180071dc0`
- `0x180072cdc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b3da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b3da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003b3ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003b3ce`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18003b2a0`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18003b2a0`

## pseudocode

```c
__int64 __fastcall IPropertyStore_SetResultSourceId(
        int (__fastcall ***a1)(__int64, GUID *, __int64 *),
        GUID *a2,
        __int64 a3,
        _WORD *a4)
{
  int v7; // ebp
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v11; // r15
  unsigned __int64 v12; // rcx
  char *v13; // r14
  size_t v14; // rdi
  int (__fastcall **v15)(__int64, GUID *, __int64 *); // rax
  int v17; // [rsp+20h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-C8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B0h]
  _WORD Src[40]; // [rsp+50h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v7 = SHStringFromGUIDW(a3, Src, 39);
  if ( v7 < 0 )
    goto LABEL_15;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  while ( a4[++v8] != 0 )
    ;
  v11 = v9 + v8;
  v18 = 0;
  v12 = v9 + v8 + 2;
  if ( !is_mul_ok(v12, 2u) )
  {
    v7 = -2147024362;
    goto LABEL_15;
  }
  v13 = (char *)CoTaskMemAlloc(2 * v12);
  if ( !v13 )
  {
    v7 = -2147024882;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v7,
      v17);
    return (unsigned int)v7;
  }
  v14 = 2 * v9;
  memcpy_0(v13, Src, v14);
  *(_WORD *)&v13[v14] = 46;
  memcpy_0(&v13[v14 + 2], a4, 2 * v8);
  v18 = 0;
  *(_WORD *)&v13[2 * v11 + 2] = 0;
  v20 = 0;
  *(_OWORD *)pvar = 0;
  LOWORD(pvar[0]) = 31;
  v15 = *a1;
  pvar[1] = v13;
  if ( (*v15)((__int64)a1, &GUID_388cec0d_4ef6_4015_a135_d96527fd84e2, &v18) < 0 )
  {
    v7 = (*a1)[6]((__int64)a1, a2, (__int64 *)pvar);
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, PROPVARIANT *, _QWORD))(*(_QWORD *)v18 + 64LL))(v18, a2, pvar, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  PropVariantClear(pvar);
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v7,
      v17);
  CoTaskMemFree(0);
  if ( v7 < 0 )
    goto LABEL_15;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003b260  push    rbx
0x18003b262  push    rbp
0x18003b263  push    rsi
0x18003b264  push    rdi
0x18003b265  push    r12
0x18003b267  push    r13
0x18003b269  push    r14
0x18003b26b  push    r15
0x18003b26d  sub     rsp, 0B8h
0x18003b274  mov     rax, cs:__security_cookie
0x18003b27b  xor     rax, rsp
0x18003b27e  mov     [rsp+0F8h+var_58], rax
0x18003b286  mov     rax, r8
0x18003b289  mov     r12, rdx
0x18003b28c  mov     r13, rcx
0x18003b28f  lea     rdx, [rsp+0F8h+Src]
0x18003b294  mov     rcx, rax
0x18003b297  mov     r8d, 27h ; '''
0x18003b29d  mov     rsi, r9
0x18003b2a0  call    cs:__imp_SHStringFromGUIDW
0x18003b2a6  mov     ebp, eax
0x18003b2a8  test    eax, eax
0x18003b2aa  js      loc_18003B40F
0x18003b2b0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18003b2b7  lea     rax, [rsp+0F8h+Src]
0x18003b2bc  mov     rdi, rbx
0x18003b2bf  nop
0x18003b2c0  inc     rdi
0x18003b2c3  cmp     word ptr [rax+rdi*2], 0
0x18003b2c8  jnz     short loc_18003B2C0
0x18003b2ca  nop     word ptr [rax+rax+00h]
0x18003b2d0  cmp     word ptr [rsi+rbx*2+2], 0
0x18003b2d6  lea     rbx, [rbx+1]
0x18003b2da  jnz     short loc_18003B2D0
0x18003b2dc  lea     r15, [rdi+rbx]
0x18003b2e0  mov     [rsp+0F8h+var_C8], 0
0x18003b2e9  lea     rcx, [r15+2]
0x18003b2ed  mov     eax, 2
0x18003b2f2  mul     rcx
0x18003b2f5  test    rdx, rdx
0x18003b2f8  jnz     loc_18003B40A
0x18003b2fe  mov     rcx, rax; cb
0x18003b301  call    cs:__imp_CoTaskMemAlloc
0x18003b307  mov     r14, rax
0x18003b30a  xor     ebp, ebp
0x18003b30c  test    r14, r14
0x18003b30f  mov     eax, 8007000Eh
0x18003b314  cmovz   ebp, eax
0x18003b317  jz      loc_18003B40F
0x18003b31d  add     rdi, rdi
0x18003b320  lea     rdx, [rsp+0F8h+Src]; Src
0x18003b325  mov     r8, rdi; Size
0x18003b328  mov     rcx, r14; void *
0x18003b32b  call    memcpy_0
0x18003b330  lea     rcx, [rdi+2]
0x18003b334  mov     word ptr [rdi+r14], 2Eh ; '.'
0x18003b33b  add     rcx, r14; void *
0x18003b33e  lea     r8, [rbx+rbx]; Size
0x18003b342  mov     rdx, rsi; Src
0x18003b345  call    memcpy_0
0x18003b34a  xor     eax, eax
0x18003b34c  mov     [rsp+0F8h+var_C8], 0
0x18003b355  mov     [r14+r15*2+2], ax
0x18003b35b  lea     r8, [rsp+0F8h+var_C8]
0x18003b360  mov     [rsp+0F8h+var_B0], rax
0x18003b365  lea     rdx, _GUID_388cec0d_4ef6_4015_a135_d96527fd84e2
0x18003b36c  xorps   xmm0, xmm0
0x18003b36f  mov     eax, 1Fh
0x18003b374  movups  xmmword ptr [rsp+0F8h+pvar], xmm0
0x18003b379  mov     word ptr [rsp+0F8h+pvar], ax
0x18003b37e  mov     rcx, r13
0x18003b381  mov     rax, [r13+0]
0x18003b385  mov     [rsp+0F8h+pvar+8], r14
0x18003b38a  mov     rax, [rax]
0x18003b38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b392  lea     r8, [rsp+0F8h+pvar]
0x18003b397  mov     rdx, r12
0x18003b39a  test    eax, eax
0x18003b39c  js      loc_18003B42D
0x18003b3a2  mov     rcx, [rsp+0F8h+var_C8]
0x18003b3a7  xor     r9d, r9d
0x18003b3aa  mov     rax, [rcx]
0x18003b3ad  mov     rax, [rax+40h]
0x18003b3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3b6  mov     rcx, [rsp+0F8h+var_C8]
0x18003b3bb  mov     ebp, eax
0x18003b3bd  mov     rax, [rcx]
0x18003b3c0  mov     rax, [rax+10h]
0x18003b3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3c9  lea     rcx, [rsp+0F8h+pvar]; pvar
0x18003b3ce  call    cs:__imp_PropVariantClear
0x18003b3d4  test    ebp, ebp
0x18003b3d6  js      short loc_18003B441
0x18003b3d8  xor     ecx, ecx; pv
0x18003b3da  call    cs:__imp_CoTaskMemFree
0x18003b3e0  test    ebp, ebp
0x18003b3e2  js      short loc_18003B40F
0x18003b3e4  mov     eax, ebp
0x18003b3e6  mov     rcx, [rsp+0F8h+var_58]
0x18003b3ee  xor     rcx, rsp; StackCookie
0x18003b3f1  call    __security_check_cookie
0x18003b3f6  add     rsp, 0B8h
0x18003b3fd  pop     r15
0x18003b3ff  pop     r14
0x18003b401  pop     r13
0x18003b403  pop     r12
0x18003b405  pop     rdi
0x18003b406  pop     rsi
0x18003b407  pop     rbp
0x18003b408  pop     rbx
0x18003b409  retn
0x18003b40a  mov     ebp, 80070216h
0x18003b40f  mov     rcx, [rsp+0F8h]; this
0x18003b417  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18003b41e  mov     r9d, ebp; char *
0x18003b421  mov     edx, 95h; void *
0x18003b426  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b42b  jmp     short loc_18003B3E4
0x18003b42d  mov     rax, [r13+0]
0x18003b431  mov     rcx, r13
0x18003b434  mov     rax, [rax+30h]
0x18003b438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b43d  mov     ebp, eax
0x18003b43f  jmp     short loc_18003B3C9
0x18003b441  mov     rcx, [rsp+0F8h]; this
0x18003b449  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18003b450  mov     r9d, ebp; char *
0x18003b453  mov     edx, 7Ah ; 'z'; void *
0x18003b458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b45d  jmp     loc_18003B3D8
```
