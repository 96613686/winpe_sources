# CError::PostError(long,ulong)

- ea: `0x18002d574`
- end: `0x18002d76a`
- name: `?PostError@CError@@QEAAXJK@Z`
- size: `502`
- prototype: `void(CError *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021680`
- `0x18002d770`

## callees

- `0x18000266c`
- `0x18002d4a4`
- `0x18002d574`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x18002d66f`
- `msvcrt!mbstowcs` at `0x18002d66f`
- `ole32!CoCreateInstance` at `0x18002d6d1`
- `ole32!CoCreateInstance` at `0x18002d6d1`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002d6aa`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002d6aa`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d72f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d72f`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002d5df`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002d5df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CError::PostError(CError *this, int a2, unsigned int a3, unsigned int a4)
{
  char *v7; // rsi
  const char *v8; // rdx
  __int64 v9; // rax
  size_t v10; // r8
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  void *v13; // rsp
  ICreateErrorInfo **p_pperrinfo; // rbx
  __int64 v15; // [rsp+0h] [rbp-40h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp+0h] BYREF
  IErrorInfo *perrinfo; // [rsp+48h] [rbp+8h] BYREF
  __int64 v18; // [rsp+50h] [rbp+10h] BYREF
  _DWORD v19[2]; // [rsp+58h] [rbp+18h] BYREF
  __int128 v20; // [rsp+60h] [rbp+20h]
  __int128 v21; // [rsp+70h] [rbp+30h] BYREF
  int v22; // [rsp+80h] [rbp+40h]

  pperrinfo = 0;
  perrinfo = 0;
  v18 = 0;
  if ( *((_DWORD *)this + 1033) )
    goto LABEL_16;
  *((_DWORD *)this + 1033) = 1;
  v7 = (char *)this + 32;
  CError::LoadDescription(this, a3, (unsigned __int16 *)this + 16, a4);
  if ( CreateErrorInfo(&pperrinfo) < 0 )
    goto LABEL_14;
  v20 = *((_OWORD *)this + 275);
  v22 = 0;
  v19[1] = a3;
  v19[0] = a2;
  v21 = *((_OWORD *)this + 1);
  ((void (__fastcall *)(ICreateErrorInfo *, __int128 *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &v21);
  v8 = (const char *)*((_QWORD *)this + 552);
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  v10 = (unsigned int)(v9 + 1);
  v11 = 2LL * (unsigned int)(v9 + 2);
  v12 = v11 + 15;
  if ( v11 + 15 < v11 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
  p_pperrinfo = &pperrinfo;
  if ( &v15 == (__int64 *)-64LL )
    p_pperrinfo = (ICreateErrorInfo **)&strIn;
  else
    mbstowcs((wchar_t *)&pperrinfo, v8, v10);
  ((void (__fastcall *)(ICreateErrorInfo *, ICreateErrorInfo **))pperrinfo->lpVtbl->SetSource)(pperrinfo, p_pperrinfo);
  ((void (__fastcall *)(ICreateErrorInfo *, char *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v7);
  if ( !GetErrorInfo(0, &perrinfo)
    || CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&perrinfo) >= 0 )
  {
    if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))perrinfo->lpVtbl->QueryInterface)(
           perrinfo,
           &IID_IErrorRecords,
           &v18) >= 0 )
      (*(void (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD, ICreateErrorInfo *, _DWORD))(*(_QWORD *)v18 + 24LL))(
        v18,
        v19,
        0,
        0,
        pperrinfo,
        0);
LABEL_14:
    if ( perrinfo )
      SetErrorInfo(0, perrinfo);
  }
LABEL_16:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v18);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
}

```

## disassembly

```asm
0x18002d574  push    rbp
0x18002d576  push    rbx
0x18002d577  push    rsi
0x18002d578  push    rdi
0x18002d579  push    r14
0x18002d57b  sub     rsp, 90h
0x18002d582  lea     rbp, [rsp+40h]
0x18002d587  mov     rax, cs:__security_cookie
0x18002d58e  xor     rax, rbp
0x18002d591  mov     [rbp+70h+var_28], rax
0x18002d595  mov     edi, r8d
0x18002d598  mov     r14d, edx
0x18002d59b  mov     rbx, rcx
0x18002d59e  mov     [rbp+70h+pperrinfo], 0
0x18002d5a6  mov     [rbp+70h+perrinfo], 0
0x18002d5ae  mov     [rbp+70h+var_60], 0
0x18002d5b6  cmp     dword ptr [rcx+1024h], 0
0x18002d5bd  jnz     loc_18002D736
0x18002d5c3  mov     dword ptr [rcx+1024h], 1
0x18002d5cd  lea     rsi, [rcx+20h]
0x18002d5d1  mov     r8, rsi; unsigned __int16 *
0x18002d5d4  mov     edx, edi; unsigned int
0x18002d5d6  call    ?LoadDescription@CError@@IEAAXKPEAGK@Z; CError::LoadDescription(ulong,ushort *,ulong)
0x18002d5db  lea     rcx, [rbp+70h+pperrinfo]; pperrinfo
0x18002d5df  call    cs:__imp_CreateErrorInfo
0x18002d5e5  test    eax, eax
0x18002d5e7  js      loc_18002D724
0x18002d5ed  movups  xmm0, xmmword ptr [rbx+1130h]
0x18002d5f4  movdqu  [rbp+70h+var_50], xmm0
0x18002d5f9  mov     [rbp+70h+var_30], 0
0x18002d600  mov     [rbp+70h+var_54], edi
0x18002d603  mov     [rbp+70h+var_58], r14d
0x18002d607  movups  xmm0, xmmword ptr [rbx+10h]
0x18002d60b  movdqu  [rbp+70h+var_40], xmm0
0x18002d610  mov     rcx, [rbp+70h+pperrinfo]
0x18002d614  mov     rax, [rcx]
0x18002d617  lea     rdx, [rbp+70h+var_40]
0x18002d61b  mov     rax, [rax+18h]
0x18002d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d624  mov     rdx, [rbx+1140h]
0x18002d62b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d62f  inc     rax
0x18002d632  cmp     byte ptr [rdx+rax], 0
0x18002d636  jnz     short loc_18002D62F
0x18002d638  lea     r8d, [rax+1]
0x18002d63c  lea     ecx, [r8+1]
0x18002d640  add     rcx, rcx
0x18002d643  lea     rax, [rcx+0Fh]
0x18002d647  cmp     rax, rcx
0x18002d64a  ja      short loc_18002D656
0x18002d64c  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002d656  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002d65a  call    _alloca_probe
0x18002d65f  sub     rsp, rax
0x18002d662  lea     rbx, [rsp+0B0h+pperrinfo]
0x18002d667  test    rbx, rbx
0x18002d66a  jz      short loc_18002D677
0x18002d66c  mov     rcx, rbx; Dest
0x18002d66f  call    cs:__imp_mbstowcs
0x18002d675  jmp     short loc_18002D67E
0x18002d677  lea     rbx, strIn
0x18002d67e  mov     rcx, [rbp+70h+pperrinfo]
0x18002d682  mov     rax, [rcx]
0x18002d685  mov     rdx, rbx
0x18002d688  mov     rax, [rax+20h]
0x18002d68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d691  mov     rcx, [rbp+70h+pperrinfo]
0x18002d695  mov     rax, [rcx]
0x18002d698  mov     rdx, rsi
0x18002d69b  mov     rax, [rax+28h]
0x18002d69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6a4  lea     rdx, [rbp+70h+perrinfo]; pperrinfo
0x18002d6a8  xor     ecx, ecx; dwReserved
0x18002d6aa  call    cs:__imp_GetErrorInfo
0x18002d6b0  test    eax, eax
0x18002d6b2  jz      short loc_18002D6DB
0x18002d6b4  lea     rax, [rbp+70h+perrinfo]
0x18002d6b8  mov     [rsp+0B0h+ppv], rax; ppv
0x18002d6bd  lea     r9, IID_IErrorInfo; riid
0x18002d6c4  xor     edx, edx; pUnkOuter
0x18002d6c6  lea     r8d, [rdx+1]; dwClsContext
0x18002d6ca  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x18002d6d1  call    cs:__imp_CoCreateInstance
0x18002d6d7  test    eax, eax
0x18002d6d9  js      short loc_18002D736
0x18002d6db  mov     rcx, [rbp+70h+perrinfo]
0x18002d6df  mov     rax, [rcx]
0x18002d6e2  lea     r8, [rbp+70h+var_60]
0x18002d6e6  lea     rdx, IID_IErrorRecords
0x18002d6ed  mov     rax, [rax]
0x18002d6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6f5  test    eax, eax
0x18002d6f7  js      short loc_18002D724
0x18002d6f9  mov     rcx, [rbp+70h+var_60]
0x18002d6fd  mov     rax, [rcx]
0x18002d700  mov     [rsp+0B0h+var_88], 0
0x18002d708  mov     rdx, [rbp+70h+pperrinfo]
0x18002d70c  mov     [rsp+0B0h+ppv], rdx
0x18002d711  xor     r9d, r9d
0x18002d714  xor     r8d, r8d
0x18002d717  lea     rdx, [rbp+70h+var_58]
0x18002d71b  mov     rax, [rax+18h]
0x18002d71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d724  mov     rdx, [rbp+70h+perrinfo]; perrinfo
0x18002d728  test    rdx, rdx
0x18002d72b  jz      short loc_18002D736
0x18002d72d  xor     ecx, ecx; dwReserved
0x18002d72f  call    cs:__imp_SetErrorInfo
0x18002d735  nop
0x18002d736  lea     rcx, [rbp+70h+var_60]
0x18002d73a  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002d73f  nop
0x18002d740  lea     rcx, [rbp+70h+perrinfo]
0x18002d744  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002d749  nop
0x18002d74a  lea     rcx, [rbp+70h+pperrinfo]
0x18002d74e  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002d753  mov     rcx, [rbp+70h+var_28]
0x18002d757  xor     rcx, rbp; StackCookie
0x18002d75a  call    __security_check_cookie
0x18002d75f  lea     rsp, [rbp+50h]
0x18002d763  pop     r14
0x18002d765  pop     rdi
0x18002d766  pop     rsi
0x18002d767  pop     rbx
0x18002d768  pop     rbp
0x18002d769  retn
```
