# ResolveLink(IUnknown *,ushort *,ulong *)

- ea: `0x18000dfe0`
- end: `0x18000e31c`
- name: `?ResolveLink@@YAHPEAUIUnknown@@PEAGPEAK@Z`
- size: `828`
- prototype: `__int64 __fastcall(IUnknown *punk, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e324`

## callees

- `0x18000dfe0`
- `0x18001623a`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000e2a7`
- `KERNEL32!LocalFree` at `0x18000e2a7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000e0a9`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000e0a9`
- `ole32!CoCreateInstance` at `0x18000e0ce`
- `ole32!CoCreateInstance` at `0x18000e0ce`
- `msi!__imp_MsiGetComponentPathW` at `0x18000e1cf`
- `msi!__imp_MsiGetComponentPathW` at `0x18000e1cf`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x18000e1b1`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x18000e1b1`

## pseudocode

```c
__int64 __fastcall ResolveLink(IUnknown *punk, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v6; // edi
  HRESULT v7; // eax
  HLOCAL v8; // rdx
  INSTALLSTATE ComponentPathW; // eax
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  WCHAR *v12; // rcx
  unsigned __int16 *v13; // rcx
  void *ppvOut; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchBuf; // [rsp+3Ch] [rbp-C4h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[80]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szComponent[64]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szProduct[64]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR PathBuf[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  ppvOut = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  hMem = 0;
  v6 = 0;
  memset_0(PathBuf, 0, 0x208u);
  memset_0(szProduct, 0, sizeof(szProduct));
  memset_0(v21, 0, sizeof(v21));
  memset_0(szComponent, 0, sizeof(szComponent));
  pcchBuf = 260;
  if ( punk )
  {
    v7 = IUnknown_QueryService(punk, &IID_IShellLinkW, &GUID_000214f9_0000_0000_c000_000000000046, &ppvOut);
  }
  else
  {
    if ( CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppvOut) < 0
      || (**(int (__fastcall ***)(void *, GUID *, __int64 *))ppvOut)(ppvOut, &IID_IPersistFile, &v20) < 0 )
    {
      goto LABEL_28;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v20 + 40LL))(v20, a2, 0);
  }
  if ( v7 < 0
    || (**(int (__fastcall ***)(void *, GUID *, __int64 *))ppvOut)(
         ppvOut,
         &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1,
         &v19) < 0 )
  {
LABEL_28:
    v8 = hMem;
    goto LABEL_29;
  }
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 48LL))(v19, &v16);
  if ( (v16 & 0x1000) == 0 )
  {
    if ( (*(int (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppvOut + 152LL))(ppvOut, 0, 105) >= 0
      && (*(int (__fastcall **)(void *, WCHAR *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           PathBuf,
           pcchBuf,
           0,
           0) >= 0 )
    {
      goto LABEL_17;
    }
    goto LABEL_28;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v19 + 32LL))(v19, 2684354566LL, &hMem) )
  {
    v8 = hMem;
    if ( !hMem )
      goto LABEL_18;
    if ( !(unsigned int)MsiDecomposeDescriptorW((char *)hMem + 268, szProduct, v21, szComponent, 0) )
    {
      ComponentPathW = MsiGetComponentPathW(szProduct, szComponent, PathBuf, &pcchBuf);
      if ( (unsigned int)(ComponentPathW + 2) > 1 && ComponentPathW != INSTALLSTATE_ABSENT )
      {
        v6 = 1;
        goto LABEL_17;
      }
      goto LABEL_28;
    }
  }
LABEL_17:
  v8 = hMem;
LABEL_18:
  v10 = *a3;
  if ( *a3 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      v11 = 2147483646;
      v12 = PathBuf;
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *a2++ = *v12++;
        --v11;
        --v10;
      }
      while ( v10 );
      v13 = a2 - 1;
      if ( v10 )
      {
        v13 = a2;
        v6 = 1;
      }
      *v13 = 0;
    }
    else
    {
      *a2 = 0;
    }
  }
LABEL_29:
  if ( v8 )
    LocalFree(v8);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( ppvOut )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  return v6;
}

```

## disassembly

```asm
0x18000dfe0  mov     [rsp-8+arg_10], rbx
0x18000dfe5  mov     [rsp-8+arg_18], rsi
0x18000dfea  push    rbp
0x18000dfeb  push    rdi
0x18000dfec  push    r12
0x18000dfee  push    r14
0x18000dff0  push    r15
0x18000dff2  lea     rbp, [rsp-2D0h]
0x18000dffa  sub     rsp, 3D0h
0x18000e001  mov     rax, cs:__security_cookie
0x18000e008  xor     rax, rsp
0x18000e00b  mov     [rbp+2F0h+var_30], rax
0x18000e012  xor     r12d, r12d
0x18000e015  mov     r14, r8
0x18000e018  mov     rbx, rdx
0x18000e01b  mov     [rsp+3F0h+ppvOut], r12
0x18000e020  mov     rsi, rcx
0x18000e023  mov     [rsp+3F0h+var_3A8], r12
0x18000e028  xor     edx, edx; Val
0x18000e02a  mov     [rsp+3F0h+var_3A0], r12
0x18000e02f  mov     r8d, 208h; Size
0x18000e035  mov     [rsp+3F0h+var_3B8], r12d
0x18000e03a  lea     rcx, [rbp+2F0h+PathBuf]; void *
0x18000e041  mov     [rsp+3F0h+hMem], r12
0x18000e046  mov     edi, r12d
0x18000e049  call    memset_0
0x18000e04e  mov     r15d, 80h
0x18000e054  lea     rcx, [rbp+2F0h+szProduct]; void *
0x18000e058  mov     r8d, r15d; Size
0x18000e05b  xor     edx, edx; Val
0x18000e05d  call    memset_0
0x18000e062  xor     edx, edx; Val
0x18000e064  lea     r8d, [r12+50h]; Size
0x18000e069  lea     rcx, [rsp+3F0h+var_390]; void *
0x18000e06e  call    memset_0
0x18000e073  mov     r8d, r15d; Size
0x18000e076  lea     rcx, [rbp+2F0h+szComponent]; void *
0x18000e07a  xor     edx, edx; Val
0x18000e07c  call    memset_0
0x18000e081  mov     [rsp+3F0h+pcchBuf], 104h
0x18000e089  lea     r15d, [r12+1]
0x18000e08e  test    rsi, rsi
0x18000e091  jz      short loc_18000E0B1
0x18000e093  lea     r9, [rsp+3F0h+ppvOut]; ppvOut
0x18000e098  mov     rcx, rsi; punk
0x18000e09b  lea     r8, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18000e0a2  lea     rdx, IID_IShellLinkW; guidService
0x18000e0a9  call    cs:__imp_IUnknown_QueryService
0x18000e0af  jmp     short loc_18000E117
0x18000e0b1  lea     rax, [rsp+3F0h+ppvOut]
0x18000e0b6  mov     r8d, r15d; dwClsContext
0x18000e0b9  lea     r9, IID_IShellLinkW; riid
0x18000e0c0  mov     [rsp+3F0h+ppv], rax; ppv
0x18000e0c5  xor     edx, edx; pUnkOuter
0x18000e0c7  lea     rcx, CLSID_ShellLink; rclsid
0x18000e0ce  call    cs:__imp_CoCreateInstance
0x18000e0d4  test    eax, eax
0x18000e0d6  js      loc_18000E29A
0x18000e0dc  mov     rcx, [rsp+3F0h+ppvOut]
0x18000e0e1  lea     r8, [rsp+3F0h+var_3A0]
0x18000e0e6  lea     rdx, IID_IPersistFile
0x18000e0ed  mov     rax, [rcx]
0x18000e0f0  mov     rax, [rax]
0x18000e0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f8  test    eax, eax
0x18000e0fa  js      loc_18000E29A
0x18000e100  mov     rcx, [rsp+3F0h+var_3A0]
0x18000e105  xor     r8d, r8d
0x18000e108  mov     rdx, rbx
0x18000e10b  mov     rax, [rcx]
0x18000e10e  mov     rax, [rax+28h]
0x18000e112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e117  test    eax, eax
0x18000e119  js      loc_18000E29A
0x18000e11f  mov     rcx, [rsp+3F0h+ppvOut]
0x18000e124  lea     r8, [rsp+3F0h+var_3A8]
0x18000e129  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18000e130  mov     rax, [rcx]
0x18000e133  mov     rax, [rax]
0x18000e136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e13b  test    eax, eax
0x18000e13d  js      loc_18000E29A
0x18000e143  mov     rcx, [rsp+3F0h+var_3A8]
0x18000e148  lea     rdx, [rsp+3F0h+var_3B8]
0x18000e14d  mov     rax, [rcx]
0x18000e150  mov     rax, [rax+30h]
0x18000e154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e159  test    [rsp+3F0h+var_3B8], 1000h
0x18000e161  jz      loc_18000E1EF
0x18000e167  mov     rcx, [rsp+3F0h+var_3A8]
0x18000e16c  lea     r8, [rsp+3F0h+hMem]
0x18000e171  mov     edx, 0A0000006h
0x18000e176  mov     rax, [rcx]
0x18000e179  mov     rax, [rax+20h]
0x18000e17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e182  test    eax, eax
0x18000e184  jnz     loc_18000E23A
0x18000e18a  mov     rdx, [rsp+3F0h+hMem]
0x18000e18f  test    rdx, rdx
0x18000e192  jz      loc_18000E23F
0x18000e198  lea     rcx, [rdx+10Ch]
0x18000e19f  mov     [rsp+3F0h+ppv], r12
0x18000e1a4  lea     rdx, [rbp+2F0h+szProduct]
0x18000e1a8  lea     r9, [rbp+2F0h+szComponent]
0x18000e1ac  lea     r8, [rsp+3F0h+var_390]
0x18000e1b1  call    cs:__imp_MsiDecomposeDescriptorW
0x18000e1b7  test    eax, eax
0x18000e1b9  jnz     short loc_18000E23A
0x18000e1bb  lea     r9, [rsp+3F0h+pcchBuf]; pcchBuf
0x18000e1c0  lea     r8, [rbp+2F0h+PathBuf]; lpPathBuf
0x18000e1c7  lea     rdx, [rbp+2F0h+szComponent]; szComponent
0x18000e1cb  lea     rcx, [rbp+2F0h+szProduct]; szProduct
0x18000e1cf  call    cs:__imp_MsiGetComponentPathW
0x18000e1d5  lea     ecx, [rax+2]
0x18000e1d8  cmp     ecx, r15d
0x18000e1db  jbe     loc_18000E29A
0x18000e1e1  cmp     eax, 2
0x18000e1e4  jz      loc_18000E29A
0x18000e1ea  mov     edi, r15d
0x18000e1ed  jmp     short loc_18000E23A
0x18000e1ef  mov     rcx, [rsp+3F0h+ppvOut]
0x18000e1f4  xor     edx, edx
0x18000e1f6  mov     rax, [rcx]
0x18000e1f9  lea     r8d, [rdx+69h]
0x18000e1fd  mov     rax, [rax+98h]
0x18000e204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e209  test    eax, eax
0x18000e20b  js      loc_18000E29A
0x18000e211  mov     rcx, [rsp+3F0h+ppvOut]
0x18000e216  lea     rdx, [rbp+2F0h+PathBuf]
0x18000e21d  mov     r8d, [rsp+3F0h+pcchBuf]
0x18000e222  xor     r9d, r9d
0x18000e225  mov     dword ptr [rsp+3F0h+ppv], r12d
0x18000e22a  mov     rax, [rcx]
0x18000e22d  mov     rax, [rax+18h]
0x18000e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e236  test    eax, eax
0x18000e238  js      short loc_18000E29A
0x18000e23a  mov     rdx, [rsp+3F0h+hMem]
0x18000e23f  mov     r8d, [r14]
0x18000e242  test    r8, r8
0x18000e245  jz      short loc_18000E29F
0x18000e247  cmp     r8, 7FFFFFFFh
0x18000e24e  jbe     short loc_18000E256
0x18000e250  mov     [rbx], r12w
0x18000e254  jmp     short loc_18000E29F
0x18000e256  mov     eax, 7FFFFFFEh
0x18000e25b  lea     rcx, [rbp+2F0h+PathBuf]
0x18000e262  test    rax, rax
0x18000e265  jz      short loc_18000E285
0x18000e267  movzx   r9d, word ptr [rcx]
0x18000e26b  test    r9w, r9w
0x18000e26f  jz      short loc_18000E285
0x18000e271  mov     [rbx], r9w
0x18000e275  add     rcx, 2
0x18000e279  add     rbx, 2
0x18000e27d  sub     rax, r15
0x18000e280  sub     r8, r15
0x18000e283  jnz     short loc_18000E262
0x18000e285  test    r8, r8
0x18000e288  lea     rcx, [rbx-2]
0x18000e28c  cmovnz  rcx, rbx
0x18000e290  cmovnz  edi, r15d
0x18000e294  mov     [rcx], r12w
0x18000e298  jmp     short loc_18000E29F
0x18000e29a  mov     rdx, [rsp+3F0h+hMem]
0x18000e29f  test    rdx, rdx
0x18000e2a2  jz      short loc_18000E2AD
0x18000e2a4  mov     rcx, rdx; hMem
0x18000e2a7  call    cs:__imp_LocalFree
0x18000e2ad  mov     rcx, [rsp+3F0h+var_3A0]
0x18000e2b2  test    rcx, rcx
0x18000e2b5  jz      short loc_18000E2C3
0x18000e2b7  mov     rax, [rcx]
0x18000e2ba  mov     rax, [rax+10h]
0x18000e2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2c3  mov     rcx, [rsp+3F0h+var_3A8]
0x18000e2c8  test    rcx, rcx
0x18000e2cb  jz      short loc_18000E2D9
0x18000e2cd  mov     rax, [rcx]
0x18000e2d0  mov     rax, [rax+10h]
0x18000e2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d9  mov     rcx, [rsp+3F0h+ppvOut]
0x18000e2de  test    rcx, rcx
0x18000e2e1  jz      short loc_18000E2EF
0x18000e2e3  mov     rdx, [rcx]
0x18000e2e6  mov     rax, [rdx+10h]
0x18000e2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ef  mov     eax, edi
0x18000e2f1  mov     rcx, [rbp+2F0h+var_30]
0x18000e2f8  xor     rcx, rsp; StackCookie
0x18000e2fb  call    __security_check_cookie
0x18000e300  lea     r11, [rsp+3F0h+var_20]
0x18000e308  mov     rbx, [r11+40h]
0x18000e30c  mov     rsi, [r11+48h]
0x18000e310  mov     rsp, r11
0x18000e313  pop     r15
0x18000e315  pop     r14
0x18000e317  pop     r12
0x18000e319  pop     rdi
0x18000e31a  pop     rbp
0x18000e31b  retn
```
