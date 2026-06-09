# MsixPreRegisterUupProducts

- ea: `0x18008fcb0`
- end: `0x18008feb0`
- name: `MsixPreRegisterUupProducts`
- size: `512`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180008a1c`
- `0x1800140c8`
- `0x180014f94`
- `0x1800298b4`
- `0x180085fec`
- `0x18008fcb0`
- `0x1800a73c0`
- `0x1800ca4dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008fd63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008fd63`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fdea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fe8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fdea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008fe8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008fd9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008fd9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fdad`

## string_xrefs

- `0x18008fd56`: `ext-ms-onecore-appmodel-staterepository-internal-l1-1-7.dll`
- `0x18008fd94`: `SRAddOrUpdateUupProduct`

## pseudocode

```c
__int64 __fastcall MsixPreRegisterUupProducts(__int64 a1, char a2)
{
  int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // r9
  __int64 v7; // rdx
  HMODULE Library; // rax
  HMODULE v9; // rbx
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // edi
  __int64 v13; // rdx
  __int128 v15; // [rsp+20h] [rbp-40h] BYREF
  int v16; // [rsp+30h] [rbp-30h]
  _QWORD v17[4]; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+78h] [rbp+18h]
  __int64 v19; // [rsp+80h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+28h] BYREF
  FARPROC ProcAddress; // [rsp+90h] [rbp+30h] BYREF

  v16 = 0;
  v15 = 0;
  v2 = sub_1800CA4DC((__int64)L"UupProducts", a2, (__int64)&v15);
  v4 = v2;
  if ( v2 >= 0 )
  {
    v19 = 0;
    v5 = sub_1800A73C0(&v19, v3, *((_QWORD *)&v15 + 1), 131097);
    v4 = v5;
    if ( v5 < 0 )
    {
      v6 = (unsigned int)v5;
      v7 = 3461;
      goto LABEL_5;
    }
    if ( ((v19 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
LABEL_27:
      sub_180014F94(&v19);
      v4 = 0;
      goto LABEL_28;
    }
    Library = LoadLibraryExW(L"ext-ms-onecore-appmodel-staterepository-internal-l1-1-7.dll", 0, 0x800u);
    v9 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (v4 & 0x80000000) == 0 )
        goto LABEL_6;
      v6 = v4;
      v7 = 3479;
LABEL_5:
      sub_180008A1C(retaddr, v7, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v6);
LABEL_6:
      sub_180014F94(&v19);
      goto LABEL_28;
    }
    ProcAddress = GetProcAddress(Library, "SRAddOrUpdateUupProduct");
    if ( !ProcAddress )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 != 127 )
      {
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        if ( v12 < 0 )
          sub_180008A1C(
            retaddr,
            3486,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v12);
        goto LABEL_19;
      }
      goto LABEL_26;
    }
    phkResult = 0;
    v12 = sub_1800298B4(&phkResult, HKEY_LOCAL_MACHINE, L"Software", 0x2001Fu);
    if ( v12 >= 0 )
    {
      v17[0] = &v19;
      v17[1] = &phkResult;
      v17[2] = &ProcAddress;
      v12 = sub_180085FEC(&v19, v17);
      if ( v12 >= 0 )
      {
        sub_180014F94(&phkResult);
LABEL_26:
        FreeLibrary(v9);
        goto LABEL_27;
      }
      v13 = 3568;
    }
    else
    {
      v13 = 3491;
    }
    sub_180008A1C(retaddr, v13, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v12);
    sub_180014F94(&phkResult);
LABEL_19:
    FreeLibrary(v9);
    sub_180014F94(&v19);
    v4 = v12;
    goto LABEL_28;
  }
  sub_180008A1C(retaddr, 3458, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v2);
LABEL_28:
  Concurrency::details::TaskStack::~TaskStack((Concurrency::details::TaskStack *)&v15);
  return v4;
}

```

## disassembly

```asm
0x18008fcb0  push    rbp
0x18008fcb2  push    rbx
0x18008fcb3  push    rdi
0x18008fcb4  mov     rbp, rsp
0x18008fcb7  sub     rsp, 60h
0x18008fcbb  xor     eax, eax
0x18008fcbd  lea     r8, [rbp+var_40]
0x18008fcc1  xorps   xmm0, xmm0
0x18008fcc4  mov     [rbp+var_30], eax
0x18008fcc7  lea     rcx, aUupproducts; "UupProducts"
0x18008fcce  movups  [rbp+var_40], xmm0
0x18008fcd2  call    sub_1800CA4DC
0x18008fcd7  mov     ebx, eax
0x18008fcd9  test    eax, eax
0x18008fcdb  jns     short loc_18008FCFA
0x18008fcdd  mov     rcx, [rbp+18h]
0x18008fce1  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008fce8  mov     r9d, eax
0x18008fceb  mov     edx, 0D82h
0x18008fcf0  call    sub_180008A1C
0x18008fcf5  jmp     loc_18008FE9D
0x18008fcfa  mov     r8, qword ptr [rbp+var_40+8]
0x18008fcfe  lea     rcx, [rbp+arg_0]
0x18008fd02  mov     r9d, 20019h
0x18008fd08  mov     [rbp+arg_0], 0
0x18008fd10  call    sub_1800A73C0
0x18008fd15  mov     ebx, eax
0x18008fd17  test    eax, eax
0x18008fd19  jns     short loc_18008FD41
0x18008fd1b  mov     r9d, eax
0x18008fd1e  mov     edx, 0D85h
0x18008fd23  mov     rcx, [rbp+18h]
0x18008fd27  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008fd2e  call    sub_180008A1C
0x18008fd33  lea     rcx, [rbp+arg_0]
0x18008fd37  call    sub_180014F94
0x18008fd3c  jmp     loc_18008FE9D
0x18008fd41  mov     rax, [rbp+arg_0]
0x18008fd45  inc     rax
0x18008fd48  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008fd4e  jz      loc_18008FE92
0x18008fd54  xor     edx, edx; hFile
0x18008fd56  lea     rcx, aExtMsOnecoreAp_3; "ext-ms-onecore-appmodel-staterepository"...
0x18008fd5d  mov     r8d, 800h; dwFlags
0x18008fd63  call    cs:__imp_LoadLibraryExW
0x18008fd69  mov     rbx, rax
0x18008fd6c  test    rax, rax
0x18008fd6f  jnz     short loc_18008FD94
0x18008fd71  call    cs:GetLastError
0x18008fd77  mov     ebx, eax
0x18008fd79  test    eax, eax
0x18008fd7b  jle     short loc_18008FD86
0x18008fd7d  movzx   ebx, ax
0x18008fd80  or      ebx, 80070000h
0x18008fd86  test    ebx, ebx
0x18008fd88  jns     short loc_18008FD33
0x18008fd8a  mov     r9d, ebx
0x18008fd8d  mov     edx, 0D97h
0x18008fd92  jmp     short loc_18008FD23
0x18008fd94  lea     rdx, aSraddorupdateu; "SRAddOrUpdateUupProduct"
0x18008fd9b  mov     rcx, rbx; hModule
0x18008fd9e  call    cs:__imp_GetProcAddress
0x18008fda4  mov     [rbp+arg_10], rax
0x18008fda8  test    rax, rax
0x18008fdab  jnz     short loc_18008FE00
0x18008fdad  call    cs:GetLastError
0x18008fdb3  mov     edi, eax
0x18008fdb5  cmp     eax, 7Fh
0x18008fdb8  jz      loc_18008FE89
0x18008fdbe  test    eax, eax
0x18008fdc0  jle     short loc_18008FDCB
0x18008fdc2  movzx   edi, ax
0x18008fdc5  or      edi, 80070000h
0x18008fdcb  test    edi, edi
0x18008fdcd  jns     short loc_18008FDE7
0x18008fdcf  mov     rcx, [rbp+18h]
0x18008fdd3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008fdda  mov     r9d, edi
0x18008fddd  mov     edx, 0D9Eh
0x18008fde2  call    sub_180008A1C
0x18008fde7  mov     rcx, rbx; hLibModule
0x18008fdea  call    cs:__imp_FreeLibrary
0x18008fdf0  lea     rcx, [rbp+arg_0]
0x18008fdf4  call    sub_180014F94
0x18008fdf9  mov     ebx, edi
0x18008fdfb  jmp     loc_18008FE9D
0x18008fe00  mov     r9d, 2001Fh; samDesired
0x18008fe06  mov     [rbp+phkResult], 0
0x18008fe0e  lea     r8, SubKey; "Software"
0x18008fe15  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18008fe1c  lea     rcx, [rbp+phkResult]; phkResult
0x18008fe20  call    sub_1800298B4
0x18008fe25  mov     edi, eax
0x18008fe27  test    eax, eax
0x18008fe29  jns     short loc_18008FE4E
0x18008fe2b  mov     edx, 0DA3h
0x18008fe30  mov     rcx, [rbp+18h]
0x18008fe34  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008fe3b  mov     r9d, edi
0x18008fe3e  call    sub_180008A1C
0x18008fe43  lea     rcx, [rbp+phkResult]
0x18008fe47  call    sub_180014F94
0x18008fe4c  jmp     short loc_18008FDE7
0x18008fe4e  lea     rax, [rbp+arg_0]
0x18008fe52  mov     [rbp+var_20], rax
0x18008fe56  lea     rdx, [rbp+var_20]
0x18008fe5a  lea     rax, [rbp+phkResult]
0x18008fe5e  mov     [rbp+var_18], rax
0x18008fe62  lea     rcx, [rbp+arg_0]
0x18008fe66  lea     rax, [rbp+arg_10]
0x18008fe6a  mov     [rbp+var_10], rax
0x18008fe6e  call    sub_180085FEC
0x18008fe73  mov     edi, eax
0x18008fe75  test    eax, eax
0x18008fe77  jns     short loc_18008FE80
0x18008fe79  mov     edx, 0DF0h
0x18008fe7e  jmp     short loc_18008FE30
0x18008fe80  lea     rcx, [rbp+phkResult]
0x18008fe84  call    sub_180014F94
0x18008fe89  mov     rcx, rbx; hLibModule
0x18008fe8c  call    cs:__imp_FreeLibrary
0x18008fe92  lea     rcx, [rbp+arg_0]
0x18008fe96  call    sub_180014F94
0x18008fe9b  xor     ebx, ebx
0x18008fe9d  lea     rcx, [rbp+var_40]; this
0x18008fea1  call    ??1TaskStack@details@Concurrency@@QEAA@XZ; Concurrency::details::TaskStack::~TaskStack(void)
0x18008fea6  mov     eax, ebx
0x18008fea8  add     rsp, 60h
0x18008feac  pop     rdi
0x18008fead  pop     rbx
0x18008feae  pop     rbp
0x18008feaf  retn
```
