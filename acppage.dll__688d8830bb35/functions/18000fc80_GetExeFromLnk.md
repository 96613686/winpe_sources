# GetExeFromLnk

- ea: `0x18000fc80`
- end: `0x18000ffc6`
- name: `GetExeFromLnk`
- size: `838`
- prototype: `__int64 __fastcall(__int64, _WORD *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000fc80`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000ff98`
- `KERNEL32!LocalFree` at `0x18000ff98`
- `SHELL32!SHGetPathFromIDListW` at `0x18000fed3`
- `SHELL32!SHGetPathFromIDListW` at `0x18000fed3`
- `ole32!CoCreateInstance` at `0x18000fcf1`
- `ole32!CoCreateInstance` at `0x18000fcf1`
- `ole32!CoTaskMemFree` at `0x18000ff41`
- `ole32!CoTaskMemFree` at `0x18000ff41`
- `msi!__imp_MsiGetComponentPathW` at `0x18000fe0d`
- `msi!__imp_MsiGetComponentPathW` at `0x18000fe0d`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x18000fde2`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x18000fde2`

## pseudocode

```c
__int64 __fastcall GetExeFromLnk(__int64 a1, _WORD *a2, int a3)
{
  unsigned __int64 v3; // rdi
  _WORD *v4; // rbx
  unsigned int v6; // esi
  unsigned __int64 v7; // rdx
  __int64 v8; // rax
  WCHAR *v9; // rcx
  _WORD *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  WCHAR *v13; // rcx
  _WORD *v14; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchBuf[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szComponent[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szProduct[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v24[80]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR PathBuf[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v3 = a3;
  v4 = a2;
  *a2 = 0;
  ppv = 0;
  v20 = 0;
  v19 = 0;
  hMem = 0;
  v6 = 0;
  if ( CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv) >= 0
    && (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v20) >= 0
    && (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v20 + 40LL))(v20, a1, 0) >= 0 )
  {
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IShellLinkDataList, &v19) >= 0 )
    {
      if ( v19 )
      {
        v17 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 48LL))(v19, &v17);
        if ( (v17 & 0x1000) != 0 )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v19 + 32LL))(
                  v19,
                  2684354566LL,
                  &hMem) )
          {
            if ( hMem )
            {
              if ( !(unsigned int)MsiDecomposeDescriptorW((char *)hMem + 268, szProduct, v24, szComponent, 0) )
              {
                pcchBuf[0] = 260;
                MsiGetComponentPathW(szProduct, szComponent, PathBuf, pcchBuf);
                if ( PathBuf[0] )
                {
                  v7 = v3;
                  if ( (_DWORD)v3 )
                  {
                    if ( v3 > 0x7FFFFFFF )
                    {
                      *v4 = 0;
                    }
                    else
                    {
                      v8 = 2147483646;
                      v9 = PathBuf;
                      do
                      {
                        if ( !v8 )
                          break;
                        if ( !*v9 )
                          break;
                        *v4++ = *v9++;
                        --v8;
                        --v7;
                      }
                      while ( v7 );
                      v10 = v4 - 1;
                      if ( v7 )
                        v10 = v4;
                      *v10 = 0;
                    }
                  }
                }
              }
            }
          }
LABEL_36:
          v6 = 1;
          goto LABEL_37;
        }
      }
    }
    *(_QWORD *)pcchBuf = 0;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 152LL))(ppv, 0, 57) >= 0
      && (*(int (__fastcall **)(LPVOID, DWORD *))(*(_QWORD *)ppv + 32LL))(ppv, pcchBuf) >= 0 )
    {
      if ( SHGetPathFromIDListW(*(LPCITEMIDLIST *)pcchBuf, PathBuf) )
      {
        if ( PathBuf[0] )
        {
          v11 = v3;
          if ( (_DWORD)v3 )
          {
            if ( v3 > 0x7FFFFFFF )
            {
              *v4 = 0;
            }
            else
            {
              v12 = 2147483646;
              v13 = PathBuf;
              do
              {
                if ( !v12 )
                  break;
                if ( !*v13 )
                  break;
                *v4++ = *v13++;
                --v12;
                --v11;
              }
              while ( v11 );
              v14 = v4 - 1;
              if ( v11 )
                v14 = v4;
              *v14 = 0;
            }
          }
        }
      }
      CoTaskMemFree(*(LPVOID *)pcchBuf);
      goto LABEL_36;
    }
  }
LABEL_37:
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( hMem )
    LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x18000fc80  mov     [rsp-8+arg_10], rbx
0x18000fc85  push    rbp
0x18000fc86  push    rsi
0x18000fc87  push    rdi
0x18000fc88  push    r14
0x18000fc8a  push    r15
0x18000fc8c  lea     rbp, [rsp-2D0h]
0x18000fc94  sub     rsp, 3D0h
0x18000fc9b  mov     rax, cs:__security_cookie
0x18000fca2  xor     rax, rsp
0x18000fca5  mov     [rbp+2F0h+var_30], rax
0x18000fcac  xor     r15d, r15d
0x18000fcaf  movsxd  rdi, r8d
0x18000fcb2  mov     rbx, rdx
0x18000fcb5  mov     [rdx], r15w
0x18000fcb9  mov     r14, rcx
0x18000fcbc  mov     [rsp+3F0h+var_3C0], r15
0x18000fcc1  lea     rax, [rsp+3F0h+var_3C0]
0x18000fcc6  mov     [rsp+3F0h+var_3A0], r15
0x18000fccb  lea     r8d, [r15+1]; dwClsContext
0x18000fccf  mov     [rsp+3F0h+var_3A8], r15
0x18000fcd4  lea     r9, IID_IShellLinkW; riid
0x18000fcdb  mov     [rsp+3F0h+hMem], r15
0x18000fce0  xor     edx, edx; pUnkOuter
0x18000fce2  mov     [rsp+3F0h+ppv], rax; ppv
0x18000fce7  lea     rcx, CLSID_ShellLink; rclsid
0x18000fcee  mov     esi, r15d
0x18000fcf1  call    cs:__imp_CoCreateInstance
0x18000fcf7  test    eax, eax
0x18000fcf9  js      loc_18000FF4C
0x18000fcff  mov     rcx, [rsp+3F0h+var_3C0]
0x18000fd04  lea     r8, [rsp+3F0h+var_3A0]
0x18000fd09  lea     rdx, IID_IPersistFile
0x18000fd10  mov     rax, [rcx]
0x18000fd13  mov     rax, [rax]
0x18000fd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd1b  test    eax, eax
0x18000fd1d  js      loc_18000FF4C
0x18000fd23  mov     rcx, [rsp+3F0h+var_3A0]
0x18000fd28  xor     r8d, r8d
0x18000fd2b  mov     rdx, r14
0x18000fd2e  mov     rax, [rcx]
0x18000fd31  mov     rax, [rax+28h]
0x18000fd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd3a  test    eax, eax
0x18000fd3c  js      loc_18000FF4C
0x18000fd42  mov     rcx, [rsp+3F0h+var_3C0]
0x18000fd47  lea     r8, [rsp+3F0h+var_3A8]
0x18000fd4c  lea     rdx, IID_IShellLinkDataList
0x18000fd53  mov     rax, [rcx]
0x18000fd56  mov     rax, [rax]
0x18000fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd5e  test    eax, eax
0x18000fd60  js      loc_18000FE82
0x18000fd66  mov     rcx, [rsp+3F0h+var_3A8]
0x18000fd6b  test    rcx, rcx
0x18000fd6e  jz      loc_18000FE82
0x18000fd74  mov     [rsp+3F0h+var_3B8], r15d
0x18000fd79  lea     rdx, [rsp+3F0h+var_3B8]
0x18000fd7e  mov     rax, [rcx]
0x18000fd81  mov     rax, [rax+30h]
0x18000fd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8a  test    [rsp+3F0h+var_3B8], 1000h
0x18000fd92  jz      loc_18000FE82
0x18000fd98  mov     rcx, [rsp+3F0h+var_3A8]
0x18000fd9d  lea     r8, [rsp+3F0h+hMem]
0x18000fda2  mov     edx, 0A0000006h
0x18000fda7  mov     rax, [rcx]
0x18000fdaa  mov     rax, [rax+20h]
0x18000fdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb3  test    eax, eax
0x18000fdb5  jnz     loc_18000FF47
0x18000fdbb  mov     rcx, [rsp+3F0h+hMem]
0x18000fdc0  test    rcx, rcx
0x18000fdc3  jz      loc_18000FF47
0x18000fdc9  add     rcx, 10Ch
0x18000fdd0  mov     [rsp+3F0h+ppv], r15
0x18000fdd5  lea     r9, [rsp+3F0h+szComponent]
0x18000fdda  lea     r8, [rbp+2F0h+var_290]
0x18000fdde  lea     rdx, [rbp+2F0h+szProduct]
0x18000fde2  call    cs:__imp_MsiDecomposeDescriptorW
0x18000fde8  test    eax, eax
0x18000fdea  jnz     loc_18000FF47
0x18000fdf0  lea     r9, [rsp+3F0h+pcchBuf]; pcchBuf
0x18000fdf5  mov     [rsp+3F0h+pcchBuf], 104h
0x18000fdfd  lea     r8, [rbp+2F0h+PathBuf]; lpPathBuf
0x18000fe04  lea     rdx, [rsp+3F0h+szComponent]; szComponent
0x18000fe09  lea     rcx, [rbp+2F0h+szProduct]; szProduct
0x18000fe0d  call    cs:__imp_MsiGetComponentPathW
0x18000fe13  cmp     [rbp+2F0h+PathBuf], r15w
0x18000fe1b  jz      loc_18000FF47
0x18000fe21  mov     rdx, rdi
0x18000fe24  test    edi, edi
0x18000fe26  jz      loc_18000FF47
0x18000fe2c  cmp     rdx, 7FFFFFFFh
0x18000fe33  ja      short loc_18000FE79
0x18000fe35  mov     eax, 7FFFFFFEh
0x18000fe3a  lea     rcx, [rbp+2F0h+PathBuf]
0x18000fe41  test    rax, rax
0x18000fe44  jz      short loc_18000FE65
0x18000fe46  movzx   r8d, word ptr [rcx]
0x18000fe4a  test    r8w, r8w
0x18000fe4e  jz      short loc_18000FE65
0x18000fe50  mov     [rbx], r8w
0x18000fe54  add     rcx, 2
0x18000fe58  add     rbx, 2
0x18000fe5c  dec     rax
0x18000fe5f  sub     rdx, 1
0x18000fe63  jnz     short loc_18000FE41
0x18000fe65  test    rdx, rdx
0x18000fe68  lea     rcx, [rbx-2]
0x18000fe6c  cmovnz  rcx, rbx
0x18000fe70  mov     [rcx], r15w
0x18000fe74  jmp     loc_18000FF47
0x18000fe79  mov     [rbx], r15w
0x18000fe7d  jmp     loc_18000FF47
0x18000fe82  mov     rcx, [rsp+3F0h+var_3C0]
0x18000fe87  xor     edx, edx
0x18000fe89  mov     qword ptr [rsp+3F0h+pcchBuf], r15
0x18000fe8e  mov     rax, [rcx]
0x18000fe91  lea     r8d, [rdx+39h]
0x18000fe95  mov     rax, [rax+98h]
0x18000fe9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fea1  test    eax, eax
0x18000fea3  js      loc_18000FF4C
0x18000fea9  mov     rcx, [rsp+3F0h+var_3C0]
0x18000feae  lea     rdx, [rsp+3F0h+pcchBuf]
0x18000feb3  mov     rax, [rcx]
0x18000feb6  mov     rax, [rax+20h]
0x18000feba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febf  test    eax, eax
0x18000fec1  js      loc_18000FF4C
0x18000fec7  mov     rcx, qword ptr [rsp+3F0h+pcchBuf]; pidl
0x18000fecc  lea     rdx, [rbp+2F0h+PathBuf]; pszPath
0x18000fed3  call    cs:__imp_SHGetPathFromIDListW
0x18000fed9  test    eax, eax
0x18000fedb  jz      short loc_18000FF3C
0x18000fedd  cmp     [rbp+2F0h+PathBuf], r15w
0x18000fee5  jz      short loc_18000FF3C
0x18000fee7  mov     rdx, rdi
0x18000feea  test    edi, edi
0x18000feec  jz      short loc_18000FF3C
0x18000feee  cmp     rdx, 7FFFFFFFh
0x18000fef5  ja      short loc_18000FF38
0x18000fef7  mov     eax, 7FFFFFFEh
0x18000fefc  lea     rcx, [rbp+2F0h+PathBuf]
0x18000ff03  test    rax, rax
0x18000ff06  jz      short loc_18000FF27
0x18000ff08  movzx   r8d, word ptr [rcx]
0x18000ff0c  test    r8w, r8w
0x18000ff10  jz      short loc_18000FF27
0x18000ff12  mov     [rbx], r8w
0x18000ff16  add     rcx, 2
0x18000ff1a  add     rbx, 2
0x18000ff1e  dec     rax
0x18000ff21  sub     rdx, 1
0x18000ff25  jnz     short loc_18000FF03
0x18000ff27  test    rdx, rdx
0x18000ff2a  lea     rcx, [rbx-2]
0x18000ff2e  cmovnz  rcx, rbx
0x18000ff32  mov     [rcx], r15w
0x18000ff36  jmp     short loc_18000FF3C
0x18000ff38  mov     [rbx], r15w
0x18000ff3c  mov     rcx, qword ptr [rsp+3F0h+pcchBuf]; pv
0x18000ff41  call    cs:__imp_CoTaskMemFree
0x18000ff47  mov     esi, 1
0x18000ff4c  mov     rcx, [rsp+3F0h+var_3A0]
0x18000ff51  test    rcx, rcx
0x18000ff54  jz      short loc_18000FF62
0x18000ff56  mov     rax, [rcx]
0x18000ff59  mov     rax, [rax+10h]
0x18000ff5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff62  mov     rcx, [rsp+3F0h+var_3C0]
0x18000ff67  test    rcx, rcx
0x18000ff6a  jz      short loc_18000FF78
0x18000ff6c  mov     rax, [rcx]
0x18000ff6f  mov     rax, [rax+10h]
0x18000ff73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff78  mov     rcx, [rsp+3F0h+var_3A8]
0x18000ff7d  test    rcx, rcx
0x18000ff80  jz      short loc_18000FF8E
0x18000ff82  mov     rax, [rcx]
0x18000ff85  mov     rax, [rax+10h]
0x18000ff89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff8e  mov     rcx, [rsp+3F0h+hMem]; hMem
0x18000ff93  test    rcx, rcx
0x18000ff96  jz      short loc_18000FF9E
0x18000ff98  call    cs:__imp_LocalFree
0x18000ff9e  mov     eax, esi
0x18000ffa0  mov     rcx, [rbp+2F0h+var_30]
0x18000ffa7  xor     rcx, rsp; StackCookie
0x18000ffaa  call    __security_check_cookie
0x18000ffaf  mov     rbx, [rsp+3F0h+arg_10]
0x18000ffb7  add     rsp, 3D0h
0x18000ffbe  pop     r15
0x18000ffc0  pop     r14
0x18000ffc2  pop     rdi
0x18000ffc3  pop     rsi
0x18000ffc4  pop     rbp
0x18000ffc5  retn
```
