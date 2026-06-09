# CVaultTransacted::FileOperationsDeleteAllFiles(ushort const *)

- ea: `0x1800404f0`
- end: `0x180040725`
- name: `?FileOperationsDeleteAllFiles@CVaultTransacted@@UEAAKPEBG@Z`
- size: `565`
- prototype: `__int64 __fastcall(HANDLE *this, wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180003140`
- `0x18001b5a0`
- `0x18003a580`
- `0x18003af10`
- `0x1800404f0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040685`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180040685`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180040568`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x1800405ef`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x1800405ef`

## pseudocode

```c
__int64 __fastcall CVaultTransacted::FileOperationsDeleteAllFiles(HANDLE *this, wchar_t *a2)
{
  unsigned int v4; // ebx
  HANDLE FirstFileTransactedW; // rdi
  BOOL (__stdcall *v7)(HANDLE); // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v11; // [rsp+60h] [rbp-A0h] BYREF
  int v12; // [rsp+68h] [rbp-98h]
  __int64 v13; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h] BYREF
  int v15; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

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
    FirstFileTransactedW = FindFirstFileTransactedW(
                             lpFileName,
                             FindExInfoStandard,
                             &FindFileData,
                             FindExSearchNameMatch,
                             0,
                             0,
                             this[1]);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v7);
    v8 = FirstFileTransactedW;
    if ( FirstFileTransactedW == (HANDLE)-1LL )
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
          v4 = (*((__int64 (__fastcall **)(HANDLE *, unsigned __int16 *))*this + 7))(this, v11);
          if ( v4 )
            goto LABEL_2;
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v10);
        }
      }
      while ( FindNextFileW(FirstFileTransactedW, &FindFileData) );
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
0x1800404f0  mov     [rsp-8+arg_10], rbx
0x1800404f5  mov     [rsp-8+arg_18], rsi
0x1800404fa  push    rbp
0x1800404fb  push    rdi
0x1800404fc  push    r14
0x1800404fe  lea     rbp, [rsp-1F0h]
0x180040506  sub     rsp, 2F0h
0x18004050d  mov     rax, cs:__security_cookie
0x180040514  xor     rax, rsp
0x180040517  mov     [rbp+200h+var_20], rax
0x18004051e  mov     r14, rdx
0x180040521  mov     rsi, rcx
0x180040524  xor     edx, edx; Val
0x180040526  mov     r8d, 250h; Size
0x18004052c  lea     rcx, [rbp+200h+FindFileData]; void *
0x180040530  call    memset_0
0x180040535  mov     [rsp+300h+var_2A0], 0
0x18004053e  mov     [rsp+300h+var_298], 0
0x180040546  mov     [rsp+300h+var_2A8], 0
0x18004054f  mov     [rsp+300h+lpFileName], 0
0x180040558  mov     [rbp+200h+var_280], 0
0x18004055f  mov     [rsp+300h+var_290], 0
0x180040568  mov     rax, cs:__imp_FindClose
0x18004056f  mov     [rsp+300h+var_2C0], rax
0x180040574  mov     [rsp+300h+var_2B8], 0
0x18004057d  mov     [rsp+300h+var_2B0], 0
0x180040585  lea     r8, [rsp+300h+lpFileName]; unsigned __int16 **
0x18004058a  lea     rdx, asc_180052C0C; "*"
0x180040591  mov     rcx, r14; Source
0x180040594  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180040599  mov     ebx, eax
0x18004059b  test    eax, eax
0x18004059d  jz      short loc_1800405C7
0x18004059f  lea     rcx, [rsp+300h+var_2C0]
0x1800405a4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800405a9  nop
0x1800405aa  lea     rcx, [rsp+300h+var_290]
0x1800405af  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800405b4  nop
0x1800405b5  lea     rcx, [rsp+300h+var_2A8]
0x1800405ba  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800405bf  nop
0x1800405c0  mov     eax, ebx
0x1800405c2  jmp     loc_1800406B2
0x1800405c7  mov     rax, [rsi+8]
0x1800405cb  mov     [rsp+300h+hTransaction], rax; hTransaction
0x1800405d0  mov     [rsp+300h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1800405d8  mov     [rsp+300h+lpSearchFilter], 0; lpSearchFilter
0x1800405e1  xor     r9d, r9d; fSearchOp
0x1800405e4  lea     r8, [rbp+200h+FindFileData]; lpFindFileData
0x1800405e8  xor     edx, edx; fInfoLevelId
0x1800405ea  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x1800405ef  call    cs:__imp_FindFirstFileTransactedW
0x1800405f5  mov     rdi, rax
0x1800405f8  lea     rcx, [rsp+300h+var_2C0]
0x1800405fd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040602  mov     [rsp+300h+var_2B8], rdi
0x180040607  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004060b  jnz     short loc_180040639
0x18004060d  mov     [rsp+300h+var_2B8], 0
0x180040616  lea     rcx, [rsp+300h+var_2C0]
0x18004061b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040620  nop
0x180040621  lea     rcx, [rsp+300h+var_290]
0x180040626  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004062b  nop
0x18004062c  lea     rcx, [rsp+300h+var_2A8]
0x180040631  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040636  nop
0x180040637  jmp     short loc_1800406B0
0x180040639  test    [rbp+200h+FindFileData], 10h
0x18004063d  jnz     short loc_18004067E
0x18004063f  lea     r8, [rsp+300h+var_2A0]; unsigned __int16 **
0x180040644  lea     rdx, [rbp+200h+var_244]; wchar_t *
0x180040648  mov     rcx, r14; Source
0x18004064b  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180040650  mov     ebx, eax
0x180040652  test    eax, eax
0x180040654  jnz     loc_1800406FF
0x18004065a  mov     rax, [rsi]
0x18004065d  mov     rdx, [rsp+300h+var_2A0]
0x180040662  mov     rcx, rsi
0x180040665  mov     rax, [rax+38h]
0x180040669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004066e  mov     ebx, eax
0x180040670  test    eax, eax
0x180040672  jnz     short loc_1800406D9
0x180040674  lea     rcx, [rsp+300h+var_2A8]
0x180040679  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004067e  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x180040682  mov     rcx, rdi; hFindFile
0x180040685  call    cs:__imp_FindNextFileW
0x18004068b  test    eax, eax
0x18004068d  jnz     short loc_180040639
0x18004068f  lea     rcx, [rsp+300h+var_2C0]
0x180040694  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040699  nop
0x18004069a  lea     rcx, [rsp+300h+var_290]
0x18004069f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800406a4  nop
0x1800406a5  lea     rcx, [rsp+300h+var_2A8]
0x1800406aa  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800406af  nop
0x1800406b0  xor     eax, eax
0x1800406b2  mov     rcx, [rbp+200h+var_20]
0x1800406b9  xor     rcx, rsp; StackCookie
0x1800406bc  call    __security_check_cookie
0x1800406c1  lea     r11, [rsp+300h+var_10]
0x1800406c9  mov     rbx, [r11+30h]
0x1800406cd  mov     rsi, [r11+38h]
0x1800406d1  mov     rsp, r11
0x1800406d4  pop     r14
0x1800406d6  pop     rdi
0x1800406d7  pop     rbp
0x1800406d8  retn
0x1800406d9  lea     rcx, [rsp+300h+var_2C0]
0x1800406de  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800406e3  nop
0x1800406e4  lea     rcx, [rsp+300h+var_290]
0x1800406e9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800406ee  nop
0x1800406ef  lea     rcx, [rsp+300h+var_2A8]
0x1800406f4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800406f9  nop
0x1800406fa  jmp     loc_1800405C0
0x1800406ff  lea     rcx, [rsp+300h+var_2C0]
0x180040704  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040709  nop
0x18004070a  lea     rcx, [rsp+300h+var_290]
0x18004070f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040714  nop
0x180040715  lea     rcx, [rsp+300h+var_2A8]
0x18004071a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004071f  nop
0x180040720  jmp     loc_1800405C0
```
