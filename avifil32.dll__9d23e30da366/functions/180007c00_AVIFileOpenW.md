# AVIFileOpenW

- ea: `0x180007c00`
- end: `0x180007dde`
- name: `AVIFileOpenW`
- size: `478`
- prototype: `HRESULT __stdcall(PAVIFILE *ppfile, LPCWSTR szFile, UINT uMode, LPCLSID lpHandler)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001fe0`
- `0x180007b70`
- `0x180008470`

## callees

- `0x180001460`
- `0x180006d80`
- `0x180007c00`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007c69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007c69`

## pseudocode

```c
HRESULT __stdcall AVIFileOpenW(PAVIFILE *ppfile, LPCWSTR szFile, UINT uMode, LPCLSID lpHandler)
{
  HRESULT result; // eax
  UINT v8; // r14d
  UINT v9; // edi
  int v10; // ebx
  int v11; // eax
  HRESULT v12; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  IID rclsid; // [rsp+48h] [rbp-20h] BYREF

  ppv = 0;
  *ppfile = 0;
  rclsid = 0;
  if ( lpHandler )
  {
    rclsid = *lpHandler;
  }
  else if ( !GetHandlerFromFile((LPWSTR)szFile, &rclsid) )
  {
    return -2147221164;
  }
  result = CoCreateInstance(&rclsid, 0, 3u, &IID_IUnknown, &ppv);
  if ( result < 0 )
    return result;
  v8 = uMode & 0x100;
  v9 = uMode & 0xFFFFFFFE;
  if ( (uMode & 2) == 0 )
    v9 = uMode;
  if ( (v9 & 0x1000) != 0 )
    v9 = v9 & 0xFFFFFFFC | 2;
  if ( (v9 & 1) != 0 )
    v9 = v9 & 0xFFFFFFFC | 2;
  v14 = 0;
  v15 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IAVIPersistFile, &v15) >= 0 )
  {
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v15)(v15, &IID_IPersistFile, &v14);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v10 >= 0 )
    {
      v11 = v9 | 0x100;
      if ( !v8 )
        v11 = v9;
      v9 = v11;
      goto LABEL_18;
    }
  }
  v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v14);
  if ( v12 >= 0 )
  {
LABEL_18:
    v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, PAVIFILE *))ppv)(ppv, &IID_IAVIFile, ppfile);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, _QWORD))(*(_QWORD *)v14 + 40LL))(v14, szFile, v9);
      if ( v12 < 0 )
      {
        ((void (__fastcall *)(PAVIFILE))(*ppfile)->lpVtbl->Release)(*ppfile);
        *ppfile = 0;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v12;
}

```

## disassembly

```asm
0x180007c00  push    rbp
0x180007c02  push    rbx
0x180007c03  push    rsi
0x180007c04  push    rdi
0x180007c05  push    r14
0x180007c07  push    r15
0x180007c09  mov     rbp, rsp
0x180007c0c  sub     rsp, 68h
0x180007c10  mov     rax, cs:__security_cookie
0x180007c17  xor     rax, rsp
0x180007c1a  mov     [rbp+var_10], rax
0x180007c1e  mov     [rbp+var_38], 0
0x180007c26  xorps   xmm0, xmm0
0x180007c29  mov     qword ptr [rcx], 0
0x180007c30  mov     ebx, r8d
0x180007c33  mov     r15, rdx
0x180007c36  mov     rsi, rcx
0x180007c39  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180007c3d  test    r9, r9
0x180007c40  jz      loc_180007D14
0x180007c46  movups  xmm0, xmmword ptr [r9]
0x180007c4a  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180007c4f  xor     edx, edx; pUnkOuter
0x180007c51  lea     rax, [rbp+var_38]
0x180007c55  lea     r9, IID_IUnknown; riid
0x180007c5c  mov     [rsp+68h+ppv], rax; ppv
0x180007c61  lea     rcx, [rbp+rclsid]; rclsid
0x180007c65  lea     r8d, [rdx+3]; dwClsContext
0x180007c69  call    cs:__imp_CoCreateInstance
0x180007c6f  test    eax, eax
0x180007c71  js      loc_180007DC5
0x180007c77  mov     r14d, ebx
0x180007c7a  mov     edi, ebx
0x180007c7c  and     r14d, 100h
0x180007c83  mov     ecx, 0FFFFFFFEh
0x180007c88  and     edi, ecx
0x180007c8a  test    bl, 2
0x180007c8d  cmovz   edi, ebx
0x180007c90  bt      edi, 0Ch
0x180007c94  jnb     short loc_180007C9B
0x180007c96  and     edi, ecx
0x180007c98  or      edi, 2
0x180007c9b  test    dil, 1
0x180007c9f  jz      short loc_180007CA6
0x180007ca1  and     edi, ecx
0x180007ca3  or      edi, 2
0x180007ca6  mov     rcx, [rbp+var_38]
0x180007caa  lea     r8, [rbp+var_28]
0x180007cae  mov     [rbp+var_30], 0
0x180007cb6  lea     rdx, IID_IAVIPersistFile
0x180007cbd  mov     [rbp+var_28], 0
0x180007cc5  mov     rax, [rcx]
0x180007cc8  mov     rax, [rax]
0x180007ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd0  test    eax, eax
0x180007cd2  js      short loc_180007D32
0x180007cd4  mov     rcx, [rbp+var_28]
0x180007cd8  lea     r8, [rbp+var_30]
0x180007cdc  lea     rdx, IID_IPersistFile
0x180007ce3  mov     rax, [rcx]
0x180007ce6  mov     rax, [rax]
0x180007ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cee  mov     rcx, [rbp+var_28]
0x180007cf2  mov     ebx, eax
0x180007cf4  mov     rdx, [rcx]
0x180007cf7  mov     rax, [rdx+10h]
0x180007cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d00  test    ebx, ebx
0x180007d02  js      short loc_180007D32
0x180007d04  mov     eax, edi
0x180007d06  bts     eax, 8
0x180007d0a  test    r14d, r14d
0x180007d0d  cmovz   eax, edi
0x180007d10  mov     edi, eax
0x180007d12  jmp     short loc_180007D52
0x180007d14  lea     rdx, [rbp+rclsid]; struct _GUID *
0x180007d18  mov     rcx, r15; pszFileName
0x180007d1b  call    ?GetHandlerFromFile@@YAHPEBGPEAU_GUID@@@Z; GetHandlerFromFile(ushort const *,_GUID *)
0x180007d20  test    eax, eax
0x180007d22  jnz     loc_180007C4F
0x180007d28  mov     eax, 80040154h
0x180007d2d  jmp     loc_180007DC5
0x180007d32  mov     rcx, [rbp+var_38]
0x180007d36  lea     r8, [rbp+var_30]
0x180007d3a  lea     rdx, IID_IPersistFile
0x180007d41  mov     rax, [rcx]
0x180007d44  mov     rax, [rax]
0x180007d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4c  mov     ebx, eax
0x180007d4e  test    eax, eax
0x180007d50  js      short loc_180007DB3
0x180007d52  mov     rcx, [rbp+var_38]
0x180007d56  lea     rdx, IID_IAVIFile
0x180007d5d  mov     r8, rsi
0x180007d60  mov     rax, [rcx]
0x180007d63  mov     rax, [rax]
0x180007d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d6b  mov     ebx, eax
0x180007d6d  test    eax, eax
0x180007d6f  js      short loc_180007DA3
0x180007d71  mov     rcx, [rbp+var_30]
0x180007d75  mov     r8d, edi
0x180007d78  mov     rdx, r15
0x180007d7b  mov     rax, [rcx]
0x180007d7e  mov     rax, [rax+28h]
0x180007d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d87  mov     ebx, eax
0x180007d89  test    eax, eax
0x180007d8b  jns     short loc_180007DA3
0x180007d8d  mov     rcx, [rsi]
0x180007d90  mov     rax, [rcx]
0x180007d93  mov     rax, [rax+10h]
0x180007d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9c  mov     qword ptr [rsi], 0
0x180007da3  mov     rcx, [rbp+var_30]
0x180007da7  mov     rax, [rcx]
0x180007daa  mov     rax, [rax+10h]
0x180007dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db3  mov     rcx, [rbp+var_38]
0x180007db7  mov     rax, [rcx]
0x180007dba  mov     rax, [rax+10h]
0x180007dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc3  mov     eax, ebx
0x180007dc5  mov     rcx, [rbp+var_10]
0x180007dc9  xor     rcx, rsp; StackCookie
0x180007dcc  call    __security_check_cookie
0x180007dd1  add     rsp, 68h
0x180007dd5  pop     r15
0x180007dd7  pop     r14
0x180007dd9  pop     rdi
0x180007dda  pop     rsi
0x180007ddb  pop     rbx
0x180007ddc  pop     rbp
0x180007ddd  retn
```
