# CVaultFileStore::DeleteAllCredentials(IVaultFileSystem *)

- ea: `0x180040cc0`
- end: `0x180040f24`
- name: `?DeleteAllCredentials@CVaultFileStore@@AEAAKPEAUIVaultFileSystem@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(wchar_t **this, struct IVaultFileSystem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800398d0`

## callees

- `0x180003140`
- `0x18001b5a0`
- `0x18003a580`
- `0x18003af10`
- `0x180040cc0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040e84`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040e84`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180040dea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180040dea`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180040d0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVaultFileStore::DeleteAllCredentials(wchar_t **this, struct IVaultFileSystem *a2)
{
  unsigned int v5; // ebx
  HANDLE FirstFile; // rdi
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+40h] [rbp-C0h]
  BOOL (__stdcall *v10)(HANDLE); // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  int v15; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  lpFileName = 0;
  v15 = 0;
  v13 = 0;
  v10 = FindClose;
  v11 = 0;
  v12 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = 0;
  v9 = 0;
  v7 = 0;
  if ( a2 )
  {
    v5 = PathCombine(this[39], (wchar_t *)L"*.vcrd", (unsigned __int16 **)&lpFileName);
    if ( v5 )
    {
LABEL_4:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return v5;
    }
    else
    {
      FirstFile = FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
      v11 = FirstFile;
      if ( FirstFile == (HANDLE)-1LL )
      {
        v11 = 0;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      }
      else
      {
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          {
            v5 = PathCombine(this[39], FindFileData.cFileName, &v8);
            if ( v5 )
              goto LABEL_4;
            v5 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, unsigned __int16 *))(*(_QWORD *)a2 + 56LL))(
                   a2,
                   v8);
            if ( v5 )
              goto LABEL_4;
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
          }
        }
        while ( FindNextFileW(FirstFile, &FindFileData) );
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      }
      return 0;
    }
  }
  else
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
    return 87;
  }
}

```

## disassembly

```asm
0x180040cc0  mov     [rsp-8+arg_10], rbx
0x180040cc5  mov     [rsp-8+arg_18], rsi
0x180040cca  push    rbp
0x180040ccb  push    rdi
0x180040ccc  push    r14
0x180040cce  lea     rbp, [rsp-1E0h]
0x180040cd6  sub     rsp, 2E0h
0x180040cdd  mov     rax, cs:__security_cookie
0x180040ce4  xor     rax, rsp
0x180040ce7  mov     [rbp+1F0h+var_20], rax
0x180040cee  mov     r14, rdx
0x180040cf1  mov     rsi, rcx
0x180040cf4  mov     [rsp+2F0h+lpFileName], 0
0x180040cfd  mov     [rsp+2F0h+var_280], 0
0x180040d05  mov     [rsp+2F0h+var_290], 0
0x180040d0e  mov     rax, cs:__imp_FindClose
0x180040d15  mov     [rsp+2F0h+var_2A8], rax
0x180040d1a  mov     [rsp+2F0h+var_2A0], 0
0x180040d23  mov     [rsp+2F0h+var_298], 0
0x180040d2b  xor     edx, edx; Val
0x180040d2d  mov     r8d, 250h; Size
0x180040d33  lea     rcx, [rbp+1F0h+FindFileData]; void *
0x180040d37  call    memset_0
0x180040d3c  mov     [rsp+2F0h+var_2B8], 0
0x180040d45  mov     [rsp+2F0h+var_2B0], 0
0x180040d4d  mov     [rsp+2F0h+var_2C0], 0
0x180040d56  test    r14, r14
0x180040d59  jnz     short loc_180040D85
0x180040d5b  lea     rcx, [rsp+2F0h+var_2C0]
0x180040d60  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040d65  nop
0x180040d66  lea     rcx, [rsp+2F0h+var_2A8]
0x180040d6b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040d70  nop
0x180040d71  lea     rcx, [rsp+2F0h+var_290]
0x180040d76  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040d7b  nop
0x180040d7c  lea     eax, [r14+57h]
0x180040d80  jmp     loc_180040EB1
0x180040d85  lea     r8, [rsp+2F0h+lpFileName]; unsigned __int16 **
0x180040d8a  lea     rdx, aVcrd; "*.vcrd"
0x180040d91  mov     rcx, [rsi+138h]; Source
0x180040d98  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180040d9d  mov     ebx, eax
0x180040d9f  test    eax, eax
0x180040da1  jz      short loc_180040DCB
0x180040da3  lea     rcx, [rsp+2F0h+var_2C0]
0x180040da8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040dad  nop
0x180040dae  lea     rcx, [rsp+2F0h+var_2A8]
0x180040db3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040db8  nop
0x180040db9  lea     rcx, [rsp+2F0h+var_290]
0x180040dbe  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040dc3  nop
0x180040dc4  mov     eax, ebx
0x180040dc6  jmp     loc_180040EB1
0x180040dcb  mov     [rsp+2F0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180040dd3  mov     [rsp+2F0h+lpSearchFilter], 0; lpSearchFilter
0x180040ddc  xor     r9d, r9d; fSearchOp
0x180040ddf  lea     r8, [rbp+1F0h+FindFileData]; lpFindFileData
0x180040de3  xor     edx, edx; fInfoLevelId
0x180040de5  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x180040dea  call    cs:__imp_FindFirstFileExW
0x180040df0  mov     rdi, rax
0x180040df3  lea     rcx, [rsp+2F0h+var_2A8]
0x180040df8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040dfd  mov     [rsp+2F0h+var_2A0], rdi
0x180040e02  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180040e06  jnz     short loc_180040E34
0x180040e08  mov     [rsp+2F0h+var_2A0], 0
0x180040e11  lea     rcx, [rsp+2F0h+var_2C0]
0x180040e16  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040e1b  nop
0x180040e1c  lea     rcx, [rsp+2F0h+var_2A8]
0x180040e21  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040e26  nop
0x180040e27  lea     rcx, [rsp+2F0h+var_290]
0x180040e2c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040e31  nop
0x180040e32  jmp     short loc_180040EAF
0x180040e34  test    [rbp+1F0h+FindFileData], 10h
0x180040e38  jnz     short loc_180040E7D
0x180040e3a  lea     r8, [rsp+2F0h+var_2B8]; unsigned __int16 **
0x180040e3f  lea     rdx, [rbp+1F0h+var_244]; wchar_t *
0x180040e43  mov     rcx, [rsi+138h]; Source
0x180040e4a  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180040e4f  mov     ebx, eax
0x180040e51  test    eax, eax
0x180040e53  jnz     loc_180040EFE
0x180040e59  mov     rax, [r14]
0x180040e5c  mov     rdx, [rsp+2F0h+var_2B8]
0x180040e61  mov     rcx, r14
0x180040e64  mov     rax, [rax+38h]
0x180040e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e6d  mov     ebx, eax
0x180040e6f  test    eax, eax
0x180040e71  jnz     short loc_180040ED8
0x180040e73  lea     rcx, [rsp+2F0h+var_2C0]
0x180040e78  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040e7d  lea     rdx, [rbp+1F0h+FindFileData]; lpFindFileData
0x180040e81  mov     rcx, rdi; hFindFile
0x180040e84  call    cs:__imp_FindNextFileW
0x180040e8a  test    eax, eax
0x180040e8c  jnz     short loc_180040E34
0x180040e8e  lea     rcx, [rsp+2F0h+var_2C0]
0x180040e93  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040e98  nop
0x180040e99  lea     rcx, [rsp+2F0h+var_2A8]
0x180040e9e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040ea3  nop
0x180040ea4  lea     rcx, [rsp+2F0h+var_290]
0x180040ea9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040eae  nop
0x180040eaf  xor     eax, eax
0x180040eb1  mov     rcx, [rbp+1F0h+var_20]
0x180040eb8  xor     rcx, rsp; StackCookie
0x180040ebb  call    __security_check_cookie
0x180040ec0  lea     r11, [rsp+2F0h+var_10]
0x180040ec8  mov     rbx, [r11+30h]
0x180040ecc  mov     rsi, [r11+38h]
0x180040ed0  mov     rsp, r11
0x180040ed3  pop     r14
0x180040ed5  pop     rdi
0x180040ed6  pop     rbp
0x180040ed7  retn
0x180040ed8  lea     rcx, [rsp+2F0h+var_2C0]
0x180040edd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040ee2  nop
0x180040ee3  lea     rcx, [rsp+2F0h+var_2A8]
0x180040ee8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040eed  nop
0x180040eee  lea     rcx, [rsp+2F0h+var_290]
0x180040ef3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040ef8  nop
0x180040ef9  jmp     loc_180040DC4
0x180040efe  lea     rcx, [rsp+2F0h+var_2C0]
0x180040f03  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040f08  nop
0x180040f09  lea     rcx, [rsp+2F0h+var_2A8]
0x180040f0e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040f13  nop
0x180040f14  lea     rcx, [rsp+2F0h+var_290]
0x180040f19  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040f1e  nop
0x180040f1f  jmp     loc_180040DC4
```
