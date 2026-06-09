# CVaultNonTransacted::FileOperationsDeleteAllFiles(ushort const *)

- ea: `0x1800402b0`
- end: `0x1800404dd`
- name: `?FileOperationsDeleteAllFiles@CVaultNonTransacted@@UEAAKPEBG@Z`
- size: `557`
- prototype: `__int64 __fastcall(CVaultNonTransacted *this, wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180003140`
- `0x18001b5a0`
- `0x18003a580`
- `0x18003af10`
- `0x1800402b0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004043d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004043d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800403a7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800403a7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180040329`

## pseudocode

```c
__int64 __fastcall CVaultNonTransacted::FileOperationsDeleteAllFiles(CVaultNonTransacted *this, wchar_t *a2)
{
  unsigned int v4; // ebx
  HANDLE FirstFile; // rdi
  BOOL (__stdcall *v7)(HANDLE); // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v8; // [rsp+38h] [rbp-C8h]
  int v9; // [rsp+40h] [rbp-C0h]
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  int v15; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v11 = 0;
  v12 = 0;
  v10 = 0;
  lpFileName = 0;
  v15 = 0;
  v13 = 0;
  v7 = FindClose;
  v8 = 0;
  v9 = 0;
  v4 = PathCombine(a2, (wchar_t *)L"*", (unsigned __int16 **)&lpFileName);
  if ( v4 )
  {
LABEL_2:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
    return v4;
  }
  else
  {
    FirstFile = FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
    v8 = FirstFile;
    if ( FirstFile == (HANDLE)-1LL )
    {
      v8 = 0;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
    }
    else
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v4 = PathCombine(a2, FindFileData.cFileName, &v11);
          if ( v4 )
            goto LABEL_2;
          v4 = (*(__int64 (__fastcall **)(CVaultNonTransacted *, unsigned __int16 *))(*(_QWORD *)this + 56LL))(
                 this,
                 v11);
          if ( v4 )
            goto LABEL_2;
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
        }
      }
      while ( FindNextFileW(FirstFile, &FindFileData) );
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800402b0  mov     [rsp-8+arg_10], rbx
0x1800402b5  mov     [rsp-8+arg_18], rsi
0x1800402ba  push    rbp
0x1800402bb  push    rdi
0x1800402bc  push    r14
0x1800402be  lea     rbp, [rsp-1E0h]
0x1800402c6  sub     rsp, 2E0h
0x1800402cd  mov     rax, cs:__security_cookie
0x1800402d4  xor     rax, rsp
0x1800402d7  mov     [rbp+1F0h+var_20], rax
0x1800402de  mov     r14, rdx
0x1800402e1  mov     rsi, rcx
0x1800402e4  xor     edx, edx; Val
0x1800402e6  mov     r8d, 250h; Size
0x1800402ec  lea     rcx, [rbp+1F0h+FindFileData]; void *
0x1800402f0  call    memset_0
0x1800402f5  mov     [rsp+2F0h+var_2A0], 0
0x1800402fe  mov     [rsp+2F0h+var_298], 0
0x180040306  mov     [rsp+2F0h+var_2A8], 0
0x18004030f  mov     [rsp+2F0h+lpFileName], 0
0x180040318  mov     [rsp+2F0h+var_280], 0
0x180040320  mov     [rsp+2F0h+var_290], 0
0x180040329  mov     rax, cs:__imp_FindClose
0x180040330  mov     [rsp+2F0h+var_2C0], rax
0x180040335  mov     [rsp+2F0h+var_2B8], 0
0x18004033e  mov     [rsp+2F0h+var_2B0], 0
0x180040346  lea     r8, [rsp+2F0h+lpFileName]; unsigned __int16 **
0x18004034b  lea     rdx, asc_180052C0C; "*"
0x180040352  mov     rcx, r14; Source
0x180040355  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x18004035a  mov     ebx, eax
0x18004035c  test    eax, eax
0x18004035e  jz      short loc_180040388
0x180040360  lea     rcx, [rsp+2F0h+var_2C0]
0x180040365  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004036a  nop
0x18004036b  lea     rcx, [rsp+2F0h+var_290]
0x180040370  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040375  nop
0x180040376  lea     rcx, [rsp+2F0h+var_2A8]
0x18004037b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040380  nop
0x180040381  mov     eax, ebx
0x180040383  jmp     loc_18004046A
0x180040388  mov     [rsp+2F0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180040390  mov     [rsp+2F0h+lpSearchFilter], 0; lpSearchFilter
0x180040399  xor     r9d, r9d; fSearchOp
0x18004039c  lea     r8, [rbp+1F0h+FindFileData]; lpFindFileData
0x1800403a0  xor     edx, edx; fInfoLevelId
0x1800403a2  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1800403a7  call    cs:__imp_FindFirstFileExW
0x1800403ad  mov     rdi, rax
0x1800403b0  lea     rcx, [rsp+2F0h+var_2C0]
0x1800403b5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800403ba  mov     [rsp+2F0h+var_2B8], rdi
0x1800403bf  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800403c3  jnz     short loc_1800403F1
0x1800403c5  mov     [rsp+2F0h+var_2B8], 0
0x1800403ce  lea     rcx, [rsp+2F0h+var_2C0]
0x1800403d3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800403d8  nop
0x1800403d9  lea     rcx, [rsp+2F0h+var_290]
0x1800403de  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800403e3  nop
0x1800403e4  lea     rcx, [rsp+2F0h+var_2A8]
0x1800403e9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800403ee  nop
0x1800403ef  jmp     short loc_180040468
0x1800403f1  test    [rbp+1F0h+FindFileData], 10h
0x1800403f5  jnz     short loc_180040436
0x1800403f7  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int16 **
0x1800403fc  lea     rdx, [rbp+1F0h+var_244]; wchar_t *
0x180040400  mov     rcx, r14; Source
0x180040403  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180040408  mov     ebx, eax
0x18004040a  test    eax, eax
0x18004040c  jnz     loc_1800404B7
0x180040412  mov     rax, [rsi]
0x180040415  mov     rdx, [rsp+2F0h+var_2A0]
0x18004041a  mov     rcx, rsi
0x18004041d  mov     rax, [rax+38h]
0x180040421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040426  mov     ebx, eax
0x180040428  test    eax, eax
0x18004042a  jnz     short loc_180040491
0x18004042c  lea     rcx, [rsp+2F0h+var_2A8]
0x180040431  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040436  lea     rdx, [rbp+1F0h+FindFileData]; lpFindFileData
0x18004043a  mov     rcx, rdi; hFindFile
0x18004043d  call    cs:__imp_FindNextFileW
0x180040443  test    eax, eax
0x180040445  jnz     short loc_1800403F1
0x180040447  lea     rcx, [rsp+2F0h+var_2C0]
0x18004044c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040451  nop
0x180040452  lea     rcx, [rsp+2F0h+var_290]
0x180040457  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004045c  nop
0x18004045d  lea     rcx, [rsp+2F0h+var_2A8]
0x180040462  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040467  nop
0x180040468  xor     eax, eax
0x18004046a  mov     rcx, [rbp+1F0h+var_20]
0x180040471  xor     rcx, rsp; StackCookie
0x180040474  call    __security_check_cookie
0x180040479  lea     r11, [rsp+2F0h+var_10]
0x180040481  mov     rbx, [r11+30h]
0x180040485  mov     rsi, [r11+38h]
0x180040489  mov     rsp, r11
0x18004048c  pop     r14
0x18004048e  pop     rdi
0x18004048f  pop     rbp
0x180040490  retn
0x180040491  lea     rcx, [rsp+2F0h+var_2C0]
0x180040496  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004049b  nop
0x18004049c  lea     rcx, [rsp+2F0h+var_290]
0x1800404a1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800404a6  nop
0x1800404a7  lea     rcx, [rsp+2F0h+var_2A8]
0x1800404ac  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800404b1  nop
0x1800404b2  jmp     loc_180040381
0x1800404b7  lea     rcx, [rsp+2F0h+var_2C0]
0x1800404bc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800404c1  nop
0x1800404c2  lea     rcx, [rsp+2F0h+var_290]
0x1800404c7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800404cc  nop
0x1800404cd  lea     rcx, [rsp+2F0h+var_2A8]
0x1800404d2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800404d7  nop
0x1800404d8  jmp     loc_180040381
```
