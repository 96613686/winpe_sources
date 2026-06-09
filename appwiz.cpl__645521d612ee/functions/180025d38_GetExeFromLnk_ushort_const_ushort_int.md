# GetExeFromLnk(ushort const *,ushort *,int)

- ea: `0x180025d38`
- end: `0x180025fea`
- name: `?GetExeFromLnk@@YAHPEBGPEAGH@Z`
- size: `690`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002636c`

## callees

- `0x18000791c`
- `0x180025d38`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x180025f37`
- `SHELL32!SHGetPathFromIDListW` at `0x180025f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025fbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025fbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025da8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f64`
- `msi!__imp_MsiGetComponentPathW` at `0x180025ec4`
- `msi!__imp_MsiGetComponentPathW` at `0x180025ec4`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x180025e99`
- `msi!__imp_MsiDecomposeDescriptorW` at `0x180025e99`

## pseudocode

```c
__int64 __fastcall GetExeFromLnk(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  int v7; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchBuf[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szComponent[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szProduct[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v14[80]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR PathBuf[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  *a2 = 0;
  ppv = 0;
  v10 = 0;
  v9 = 0;
  hMem = 0;
  v4 = 0;
  if ( CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv) >= 0
    && (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v10) >= 0
    && (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, a1, 0) >= 0 )
  {
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IShellLinkDataList, &v9) >= 0 )
    {
      if ( v9 )
      {
        v7 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 48LL))(v9, &v7);
        if ( (v7 & 0x1000) != 0 )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v9 + 32LL))(
                  v9,
                  2684354566LL,
                  &hMem) )
          {
            if ( hMem )
            {
              if ( !(unsigned int)MsiDecomposeDescriptorW((char *)hMem + 268, szProduct, v14, szComponent, 0) )
              {
                pcchBuf[0] = 260;
                MsiGetComponentPathW(szProduct, szComponent, PathBuf, pcchBuf);
                if ( PathBuf[0] )
                  StringCchCopyW(a2, 0x104u, PathBuf);
              }
            }
          }
LABEL_18:
          v4 = 1;
          goto LABEL_19;
        }
      }
    }
    *(_QWORD *)pcchBuf = 0;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 152LL))(ppv, 0, 57) >= 0
      && (*(int (__fastcall **)(LPVOID, DWORD *))(*(_QWORD *)ppv + 32LL))(ppv, pcchBuf) >= 0 )
    {
      if ( SHGetPathFromIDListW(*(LPCITEMIDLIST *)pcchBuf, PathBuf) && PathBuf[0] )
        StringCchCopyW(a2, 0x104u, PathBuf);
      CoTaskMemFree(*(LPVOID *)pcchBuf);
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x180025d38  mov     [rsp-8+arg_10], rbx
0x180025d3d  mov     [rsp-8+arg_18], rsi
0x180025d42  push    rbp
0x180025d43  push    rdi
0x180025d44  push    r14
0x180025d46  lea     rbp, [rsp-2D0h]
0x180025d4e  sub     rsp, 3D0h
0x180025d55  mov     rax, cs:__security_cookie
0x180025d5c  xor     rax, rsp
0x180025d5f  mov     [rbp+2E0h+var_20], rax
0x180025d66  xor     r14d, r14d
0x180025d69  lea     rax, [rsp+3E0h+var_3B0]
0x180025d6e  mov     rdi, rdx
0x180025d71  mov     [rdx], r14w
0x180025d75  mov     rsi, rcx
0x180025d78  mov     [rsp+3E0h+var_3B0], r14
0x180025d7d  lea     r9, IID_IShellLinkW; riid
0x180025d84  mov     [rsp+3E0h+var_390], r14
0x180025d89  lea     r8d, [r14+1]; dwClsContext
0x180025d8d  mov     [rsp+3E0h+var_398], r14
0x180025d92  xor     edx, edx; pUnkOuter
0x180025d94  mov     [rsp+3E0h+hMem], r14
0x180025d99  lea     rcx, CLSID_ShellLink; rclsid
0x180025da0  mov     [rsp+3E0h+ppv], rax; ppv
0x180025da5  mov     ebx, r14d
0x180025da8  call    cs:__imp_CoCreateInstance
0x180025dae  test    eax, eax
0x180025db0  js      loc_180025F6F
0x180025db6  mov     rcx, [rsp+3E0h+var_3B0]
0x180025dbb  lea     r8, [rsp+3E0h+var_390]
0x180025dc0  lea     rdx, IID_IPersistFile
0x180025dc7  mov     rax, [rcx]
0x180025dca  mov     rax, [rax]
0x180025dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd2  test    eax, eax
0x180025dd4  js      loc_180025F6F
0x180025dda  mov     rcx, [rsp+3E0h+var_390]
0x180025ddf  xor     r8d, r8d
0x180025de2  mov     rdx, rsi
0x180025de5  mov     rax, [rcx]
0x180025de8  mov     rax, [rax+28h]
0x180025dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025df1  test    eax, eax
0x180025df3  js      loc_180025F6F
0x180025df9  mov     rcx, [rsp+3E0h+var_3B0]
0x180025dfe  lea     r8, [rsp+3E0h+var_398]
0x180025e03  lea     rdx, IID_IShellLinkDataList
0x180025e0a  mov     rax, [rcx]
0x180025e0d  mov     rax, [rax]
0x180025e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e15  test    eax, eax
0x180025e17  js      loc_180025EEE
0x180025e1d  mov     rcx, [rsp+3E0h+var_398]
0x180025e22  test    rcx, rcx
0x180025e25  jz      loc_180025EEE
0x180025e2b  mov     [rsp+3E0h+var_3A8], r14d
0x180025e30  lea     rdx, [rsp+3E0h+var_3A8]
0x180025e35  mov     rax, [rcx]
0x180025e38  mov     rax, [rax+30h]
0x180025e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e41  test    [rsp+3E0h+var_3A8], 1000h
0x180025e49  jz      loc_180025EEE
0x180025e4f  mov     rcx, [rsp+3E0h+var_398]
0x180025e54  lea     r8, [rsp+3E0h+hMem]
0x180025e59  mov     edx, 0A0000006h
0x180025e5e  mov     rax, [rcx]
0x180025e61  mov     rax, [rax+20h]
0x180025e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e6a  test    eax, eax
0x180025e6c  jnz     loc_180025F6A
0x180025e72  mov     rcx, [rsp+3E0h+hMem]
0x180025e77  test    rcx, rcx
0x180025e7a  jz      loc_180025F6A
0x180025e80  add     rcx, 10Ch
0x180025e87  mov     [rsp+3E0h+ppv], r14
0x180025e8c  lea     r9, [rsp+3E0h+szComponent]
0x180025e91  lea     r8, [rbp+2E0h+var_280]
0x180025e95  lea     rdx, [rbp+2E0h+szProduct]
0x180025e99  call    cs:__imp_MsiDecomposeDescriptorW
0x180025e9f  test    eax, eax
0x180025ea1  jnz     loc_180025F6A
0x180025ea7  lea     r9, [rsp+3E0h+pcchBuf]; pcchBuf
0x180025eac  mov     [rsp+3E0h+pcchBuf], 104h
0x180025eb4  lea     r8, [rbp+2E0h+PathBuf]; lpPathBuf
0x180025ebb  lea     rdx, [rsp+3E0h+szComponent]; szComponent
0x180025ec0  lea     rcx, [rbp+2E0h+szProduct]; szProduct
0x180025ec4  call    cs:__imp_MsiGetComponentPathW
0x180025eca  cmp     [rbp+2E0h+PathBuf], r14w
0x180025ed2  jz      loc_180025F6A
0x180025ed8  lea     r8, [rbp+2E0h+PathBuf]; unsigned __int16 *
0x180025edf  mov     edx, 104h; unsigned __int64
0x180025ee4  mov     rcx, rdi; unsigned __int16 *
0x180025ee7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025eec  jmp     short loc_180025F6A
0x180025eee  mov     rcx, [rsp+3E0h+var_3B0]
0x180025ef3  xor     edx, edx
0x180025ef5  mov     qword ptr [rsp+3E0h+pcchBuf], r14
0x180025efa  mov     rax, [rcx]
0x180025efd  lea     r8d, [rdx+39h]
0x180025f01  mov     rax, [rax+98h]
0x180025f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f0d  test    eax, eax
0x180025f0f  js      short loc_180025F6F
0x180025f11  mov     rcx, [rsp+3E0h+var_3B0]
0x180025f16  lea     rdx, [rsp+3E0h+pcchBuf]
0x180025f1b  mov     rax, [rcx]
0x180025f1e  mov     rax, [rax+20h]
0x180025f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f27  test    eax, eax
0x180025f29  js      short loc_180025F6F
0x180025f2b  mov     rcx, qword ptr [rsp+3E0h+pcchBuf]; pidl
0x180025f30  lea     rdx, [rbp+2E0h+PathBuf]; pszPath
0x180025f37  call    cs:__imp_SHGetPathFromIDListW
0x180025f3d  test    eax, eax
0x180025f3f  jz      short loc_180025F5F
0x180025f41  cmp     [rbp+2E0h+PathBuf], r14w
0x180025f49  jz      short loc_180025F5F
0x180025f4b  lea     r8, [rbp+2E0h+PathBuf]; unsigned __int16 *
0x180025f52  mov     edx, 104h; unsigned __int64
0x180025f57  mov     rcx, rdi; unsigned __int16 *
0x180025f5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025f5f  mov     rcx, qword ptr [rsp+3E0h+pcchBuf]; pv
0x180025f64  call    cs:__imp_CoTaskMemFree
0x180025f6a  mov     ebx, 1
0x180025f6f  mov     rcx, [rsp+3E0h+var_390]
0x180025f74  test    rcx, rcx
0x180025f77  jz      short loc_180025F85
0x180025f79  mov     rax, [rcx]
0x180025f7c  mov     rax, [rax+10h]
0x180025f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f85  mov     rcx, [rsp+3E0h+var_3B0]
0x180025f8a  test    rcx, rcx
0x180025f8d  jz      short loc_180025F9B
0x180025f8f  mov     rax, [rcx]
0x180025f92  mov     rax, [rax+10h]
0x180025f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f9b  mov     rcx, [rsp+3E0h+var_398]
0x180025fa0  test    rcx, rcx
0x180025fa3  jz      short loc_180025FB1
0x180025fa5  mov     rax, [rcx]
0x180025fa8  mov     rax, [rax+10h]
0x180025fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fb1  mov     rcx, [rsp+3E0h+hMem]; hMem
0x180025fb6  test    rcx, rcx
0x180025fb9  jz      short loc_180025FC1
0x180025fbb  call    cs:__imp_LocalFree
0x180025fc1  mov     eax, ebx
0x180025fc3  mov     rcx, [rbp+2E0h+var_20]
0x180025fca  xor     rcx, rsp; StackCookie
0x180025fcd  call    __security_check_cookie
0x180025fd2  lea     r11, [rsp+3E0h+var_10]
0x180025fda  mov     rbx, [r11+30h]
0x180025fde  mov     rsi, [r11+38h]
0x180025fe2  mov     rsp, r11
0x180025fe5  pop     r14
0x180025fe7  pop     rdi
0x180025fe8  pop     rbp
0x180025fe9  retn
```
