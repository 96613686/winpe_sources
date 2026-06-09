# CMsiPath::Remove(bool *)

- ea: `0x180125bf0`
- end: `0x180125f7f`
- name: `?Remove@CMsiPath@@UEAAPEAVIMsiRecord@@PEA_N@Z`
- size: `911`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x180083178`
- `0x1800833ec`
- `0x1800d6ff0`
- `0x1800e80a4`
- `0x180125bf0`
- `0x18014e4d4`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180125c97`
- `KERNEL32!GetLastError` at `0x180125d4a`
- `KERNEL32!GetLastError` at `0x180125c97`
- `KERNEL32!GetLastError` at `0x180125d4a`
- `KERNEL32!FindFirstFileW` at `0x180125e43`
- `KERNEL32!FindFirstFileW` at `0x180125e43`
- `KERNEL32!FindNextFileW` at `0x180125e9d`
- `KERNEL32!FindNextFileW` at `0x180125e9d`
- `KERNEL32!FindClose` at `0x180125eae`
- `KERNEL32!FindClose` at `0x180125eae`
- `KERNEL32!RemoveDirectoryW` at `0x180125c85`
- `KERNEL32!RemoveDirectoryW` at `0x180125d38`
- `KERNEL32!RemoveDirectoryW` at `0x180125c85`
- `KERNEL32!RemoveDirectoryW` at `0x180125d38`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::Remove(CMsiPath *this, bool *a2)
{
  int v4; // edi
  const WCHAR *v5; // rax
  BOOL v6; // r12d
  BOOL v7; // r15d
  bool v8; // cl
  DWORD LastError; // esi
  __int64 v10; // rax
  __int64 v11; // rsi
  const WCHAR *v13; // rax
  BOOL v14; // r12d
  bool v15; // cl
  __int64 v16; // r12
  MsiString *v17; // rax
  const WCHAR *v18; // rax
  HANDLE FirstFileW; // r14
  int v20; // edx
  int v21; // edx
  __int64 v22; // rbx
  const unsigned __int16 *v23; // rax
  struct IMsiRecord *v24; // rdi
  void (*v25)(void); // rax
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2 )
    *a2 = 0;
  v26 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
  v4 = 1;
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v26 + 192LL))(v26, 4, 1, &v26);
  if ( *((_DWORD *)this + 12) )
    StartImpersonating();
  v5 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
  v6 = RemoveDirectoryW(v5);
  v7 = v6;
  LastError = GetLastError();
  if ( *((_DWORD *)this + 12) )
    StopImpersonating(v8);
  if ( !v6 && LastError == 5 )
  {
    v10 = *(_QWORD *)this;
    LODWORD(v27) = 0;
    v11 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, __int64 *))(v10 + 384))(this, 0, &v27);
    if ( v11
      || (v11 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, _QWORD))(*(_QWORD *)this + 392LL))(this, 0, 0)) != 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      return (struct IMsiRecord *)v11;
    }
    if ( *((_DWORD *)this + 12) )
      StartImpersonating();
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
    v14 = RemoveDirectoryW(v13);
    v7 = v14;
    LastError = GetLastError();
    if ( *((_DWORD *)this + 12) )
      StopImpersonating(v15);
    if ( !v14 )
    {
      v16 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, _QWORD))(*(_QWORD *)this + 392LL))(
              this,
              0,
              (unsigned int)v27);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        return (struct IMsiRecord *)v16;
      }
    }
  }
  if ( v7 )
  {
    if ( a2 )
      *a2 = 1;
LABEL_40:
    v25 = *(void (**)(void))(*(_QWORD *)this + 576LL);
    goto LABEL_41;
  }
  if ( LastError == 145 || LastError - 2 <= 1 || LastError == 303 )
    goto LABEL_40;
  v27 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
  v17 = MsiString::MsiString((MsiString *)&v28, L"*.*");
  MsiString::operator+=(&v27, v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v18 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 80LL))(v27);
  FirstFileW = FindFirstFileW(v18, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v20 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v20 = FindFileData.cFileName[1];
      if ( v20 )
      {
        v21 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v21 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v21 = FindFileData.cFileName[2];
        }
        if ( v21 )
          break;
      }
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
        goto LABEL_37;
    }
    v4 = 0;
  }
LABEL_37:
  FindClose(FirstFileW);
  if ( v4 )
  {
    v22 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
    v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 80LL))(v22);
    v24 = PostError(2327, LastError, v23);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return v24;
  }
  v25 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
LABEL_41:
  v25();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x180125bf0  mov     [rsp-8+arg_10], rbx
0x180125bf5  mov     [rsp-8+arg_18], rsi
0x180125bfa  push    rbp
0x180125bfb  push    rdi
0x180125bfc  push    r12
0x180125bfe  push    r14
0x180125c00  push    r15
0x180125c02  lea     rbp, [rsp-1B0h]
0x180125c0a  sub     rsp, 2B0h
0x180125c11  mov     rax, cs:__security_cookie
0x180125c18  xor     rax, rsp
0x180125c1b  mov     [rbp+1D0h+var_30], rax
0x180125c22  mov     r14, rdx
0x180125c25  mov     rbx, rcx
0x180125c28  test    rdx, rdx
0x180125c2b  jz      short loc_180125C30
0x180125c2d  mov     byte ptr [rdx], 0
0x180125c30  mov     rax, [rcx]
0x180125c33  mov     rax, [rax+38h]
0x180125c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125c3c  mov     [rsp+2D0h+var_2A0], rax
0x180125c41  lea     r9, [rsp+2D0h+var_2A0]
0x180125c46  mov     edi, 1
0x180125c4b  mov     r8d, edi
0x180125c4e  mov     rcx, [rax]
0x180125c51  lea     edx, [rdi+3]
0x180125c54  mov     r10, [rcx+0C0h]
0x180125c5b  mov     rcx, rax
0x180125c5e  mov     rax, r10
0x180125c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125c66  cmp     dword ptr [rbx+30h], 0
0x180125c6a  jz      short loc_180125C71
0x180125c6c  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180125c71  mov     rcx, [rsp+2D0h+var_2A0]
0x180125c76  mov     rax, [rcx]
0x180125c79  mov     rax, [rax+50h]
0x180125c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125c82  mov     rcx, rax; lpPathName
0x180125c85  call    cs:__imp_RemoveDirectoryW
0x180125c8b  xor     r15d, r15d
0x180125c8e  mov     r12d, eax
0x180125c91  test    eax, eax
0x180125c93  setnz   r15b
0x180125c97  call    cs:__imp_GetLastError
0x180125c9d  cmp     dword ptr [rbx+30h], 0
0x180125ca1  mov     esi, eax
0x180125ca3  jz      short loc_180125CAA
0x180125ca5  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180125caa  test    r12d, r12d
0x180125cad  jnz     loc_180125D9C
0x180125cb3  cmp     esi, 5
0x180125cb6  jnz     loc_180125D9C
0x180125cbc  mov     rax, [rbx]
0x180125cbf  lea     r8, [rsp+2D0h+var_298]
0x180125cc4  xor     edx, edx
0x180125cc6  mov     dword ptr [rsp+2D0h+var_298], r12d
0x180125ccb  mov     rcx, rbx
0x180125cce  mov     rax, [rax+180h]
0x180125cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125cda  mov     rsi, rax
0x180125cdd  test    rax, rax
0x180125ce0  jz      short loc_180125CFB
0x180125ce2  mov     rcx, [rsp+2D0h+var_2A0]
0x180125ce7  mov     rdx, [rcx]
0x180125cea  mov     rax, [rdx+10h]
0x180125cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125cf3  mov     rax, rsi
0x180125cf6  jmp     loc_180125F54
0x180125cfb  mov     rax, [rbx]
0x180125cfe  xor     r8d, r8d
0x180125d01  xor     edx, edx
0x180125d03  mov     rcx, rbx
0x180125d06  mov     rax, [rax+188h]
0x180125d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d12  mov     rsi, rax
0x180125d15  test    rax, rax
0x180125d18  jnz     short loc_180125CE2
0x180125d1a  cmp     [rbx+30h], eax
0x180125d1d  jz      short loc_180125D24
0x180125d1f  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180125d24  mov     rcx, [rsp+2D0h+var_2A0]
0x180125d29  mov     rax, [rcx]
0x180125d2c  mov     rax, [rax+50h]
0x180125d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d35  mov     rcx, rax; lpPathName
0x180125d38  call    cs:__imp_RemoveDirectoryW
0x180125d3e  xor     r15d, r15d
0x180125d41  mov     r12d, eax
0x180125d44  test    eax, eax
0x180125d46  setnz   r15b
0x180125d4a  call    cs:__imp_GetLastError
0x180125d50  cmp     dword ptr [rbx+30h], 0
0x180125d54  mov     esi, eax
0x180125d56  jz      short loc_180125D5D
0x180125d58  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180125d5d  test    r12d, r12d
0x180125d60  jnz     short loc_180125D9C
0x180125d62  mov     rax, [rbx]
0x180125d65  xor     edx, edx
0x180125d67  mov     r8d, dword ptr [rsp+2D0h+var_298]
0x180125d6c  mov     rcx, rbx
0x180125d6f  mov     rax, [rax+188h]
0x180125d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d7b  mov     r12, rax
0x180125d7e  test    rax, rax
0x180125d81  jz      short loc_180125D9C
0x180125d83  mov     rcx, [rsp+2D0h+var_2A0]
0x180125d88  mov     rdx, [rcx]
0x180125d8b  mov     rax, [rdx+10h]
0x180125d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125d94  mov     rax, r12
0x180125d97  jmp     loc_180125F54
0x180125d9c  test    r15d, r15d
0x180125d9f  jz      short loc_180125DB2
0x180125da1  test    r14, r14
0x180125da4  jz      short loc_180125DA9
0x180125da6  mov     [r14], dil
0x180125da9  cmp     r15d, edi
0x180125dac  jz      loc_180125F2F
0x180125db2  cmp     esi, 91h
0x180125db8  jz      loc_180125F2F
0x180125dbe  lea     eax, [rsi-2]
0x180125dc1  cmp     eax, edi
0x180125dc3  jbe     loc_180125F2F
0x180125dc9  cmp     esi, 12Fh
0x180125dcf  jz      loc_180125F2F
0x180125dd5  mov     rax, [rbx]
0x180125dd8  mov     rcx, rbx
0x180125ddb  mov     rax, [rax+38h]
0x180125ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125de4  lea     rdx, asc_180286BA0; "*.*"
0x180125deb  mov     [rsp+2D0h+var_298], rax
0x180125df0  lea     rcx, [rsp+2D0h+var_290]; this
0x180125df5  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180125dfa  mov     rdx, rax
0x180125dfd  lea     rcx, [rsp+2D0h+var_298]
0x180125e02  call    ??YMsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator+=(MsiString const &)
0x180125e07  mov     rcx, [rsp+2D0h+var_290]
0x180125e0c  mov     rax, [rcx]
0x180125e0f  mov     rax, [rax+10h]
0x180125e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125e18  xor     edx, edx; Val
0x180125e1a  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180125e1f  mov     r8d, 250h; Size
0x180125e25  call    memset_0
0x180125e2a  mov     rcx, [rsp+2D0h+var_298]
0x180125e2f  mov     rax, [rcx]
0x180125e32  mov     rax, [rax+50h]
0x180125e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125e3b  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180125e40  mov     rcx, rax; lpFileName
0x180125e43  call    cs:__imp_FindFirstFileW
0x180125e49  mov     r14, rax
0x180125e4c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180125e50  jz      short loc_180125EAB
0x180125e52  mov     r15d, 2Eh ; '.'
0x180125e58  movzx   edx, [rsp+2D0h+FindFileData.cFileName]
0x180125e5d  sub     edx, r15d
0x180125e60  jnz     short loc_180125E6E
0x180125e62  movzx   edx, [rsp+2D0h+FindFileData.cFileName+2]
0x180125e67  xor     eax, eax
0x180125e69  movzx   ecx, ax
0x180125e6c  sub     edx, ecx
0x180125e6e  test    edx, edx
0x180125e70  jz      short loc_180125E95
0x180125e72  movzx   edx, [rsp+2D0h+FindFileData.cFileName]
0x180125e77  sub     edx, r15d
0x180125e7a  jnz     short loc_180125E91
0x180125e7c  movzx   edx, [rsp+2D0h+FindFileData.cFileName+2]
0x180125e81  sub     edx, r15d
0x180125e84  jnz     short loc_180125E91
0x180125e86  movzx   edx, [rbp+1D0h+FindFileData.cFileName+4]
0x180125e8a  xor     eax, eax
0x180125e8c  movzx   ecx, ax
0x180125e8f  sub     edx, ecx
0x180125e91  test    edx, edx
0x180125e93  jnz     short loc_180125EA9
0x180125e95  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180125e9a  mov     rcx, r14; hFindFile
0x180125e9d  call    cs:__imp_FindNextFileW
0x180125ea3  cmp     eax, edi
0x180125ea5  jz      short loc_180125E58
0x180125ea7  jmp     short loc_180125EAB
0x180125ea9  xor     edi, edi
0x180125eab  mov     rcx, r14; hFindFile
0x180125eae  call    cs:__imp_FindClose
0x180125eb4  test    edi, edi
0x180125eb6  jz      short loc_180125F21
0x180125eb8  mov     rax, [rbx]
0x180125ebb  mov     rcx, rbx
0x180125ebe  mov     rax, [rax+38h]
0x180125ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125ec7  mov     rbx, rax
0x180125eca  mov     rcx, [rax]
0x180125ecd  mov     rax, [rcx+50h]
0x180125ed1  mov     rcx, rbx
0x180125ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125ed9  mov     r8, rax; unsigned __int16 *
0x180125edc  mov     edx, esi; int
0x180125ede  mov     ecx, 917h; int
0x180125ee3  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180125ee8  mov     rcx, [rbx]
0x180125eeb  mov     rdi, rax
0x180125eee  mov     rax, [rcx+10h]
0x180125ef2  mov     rcx, rbx
0x180125ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125efa  mov     rcx, [rsp+2D0h+var_298]
0x180125eff  mov     rdx, [rcx]
0x180125f02  mov     rax, [rdx+10h]
0x180125f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125f0b  mov     rcx, [rsp+2D0h+var_2A0]
0x180125f10  mov     rax, [rcx]
0x180125f13  mov     rax, [rax+10h]
0x180125f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125f1c  mov     rax, rdi
0x180125f1f  jmp     short loc_180125F54
0x180125f21  mov     rcx, [rsp+2D0h+var_298]
0x180125f26  mov     rax, [rcx]
0x180125f29  mov     rax, [rax+10h]
0x180125f2d  jmp     short loc_180125F3C
0x180125f2f  mov     rax, [rbx]
0x180125f32  mov     rcx, rbx
0x180125f35  mov     rax, [rax+240h]
0x180125f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125f41  mov     rcx, [rsp+2D0h+var_2A0]
0x180125f46  mov     rax, [rcx]
0x180125f49  mov     rax, [rax+10h]
0x180125f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125f52  xor     eax, eax
0x180125f54  mov     rcx, [rbp+1D0h+var_30]
0x180125f5b  xor     rcx, rsp; StackCookie
0x180125f5e  call    __security_check_cookie
0x180125f63  lea     r11, [rsp+2D0h+var_20]
0x180125f6b  mov     rbx, [r11+40h]
0x180125f6f  mov     rsi, [r11+48h]
0x180125f73  mov     rsp, r11
0x180125f76  pop     r15
0x180125f78  pop     r14
0x180125f7a  pop     r12
0x180125f7c  pop     rdi
0x180125f7d  pop     rbp
0x180125f7e  retn
```
