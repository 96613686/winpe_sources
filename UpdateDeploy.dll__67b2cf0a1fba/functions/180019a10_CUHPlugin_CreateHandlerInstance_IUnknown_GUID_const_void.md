# CUHPlugin::CreateHandlerInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180019a10`
- end: `0x180019c2f`
- name: `?CreateHandlerInstance@CUHPlugin@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `543`
- prototype: `__int64 __fastcall(CUHPlugin *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800174a0`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x180019a10`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019b4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019b87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019b4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019b87`

## string_xrefs

- `0x180019a50`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019b9b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019bce`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019b80`: `WUCreateUpdateHandler`

## pseudocode

```c
__int64 __fastcall CUHPlugin::CreateHandlerInstance(
        CUHPlugin *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rbx
  const char *v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD, int *, void **); // r15
  HMODULE v16; // rcx
  FARPROC v17; // rax
  FARPROC v18; // rax
  int v20; // [rsp+20h] [rbp-30h]
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  int v22; // [rsp+38h] [rbp-18h] BYREF
  void *lpMem; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a2 )
  {
    v7 = 1349;
LABEL_3:
    LastError = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)LastError,
      v20);
    return LastError;
  }
  if ( !a4 )
  {
    v7 = 1350;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    LastError = -2147483634;
    v7 = 1351;
    goto LABEL_4;
  }
  lpMem = 0;
  v22 = 0;
  v21 = 0;
  ProcAddress = GetProcAddress(g_hInstance, (LPCSTR)4);
  if ( ProcAddress )
  {
    v12 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v21);
    LastError = v12;
    if ( v12 >= 0 )
    {
      v14 = v21;
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, void **))(*(_QWORD *)v21 + 40LL);
      if ( lpMem )
      {
        SusFree(lpMem);
        lpMem = 0;
      }
      v12 = v15(v14, *((_QWORD *)this + 2), &v22, &lpMem);
      LastError = v12;
      if ( v12 >= 0 )
      {
        v16 = (HMODULE)*((_QWORD *)this + 7);
        if ( v22 )
        {
          v17 = GetProcAddress(v16, (LPCSTR)7);
          if ( !v17 )
          {
            v11 = 1373;
            goto LABEL_24;
          }
          v12 = ((__int64 (__fastcall *)(_QWORD, struct IUnknown *, GUID *, void **))v17)(
                  *((_QWORD *)this + 2),
                  a2,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  a4);
          LastError = v12;
          if ( v12 < 0 )
          {
            v13 = 1374;
            goto LABEL_27;
          }
        }
        else
        {
          v18 = GetProcAddress(v16, "WUCreateUpdateHandler");
          if ( !v18 )
          {
            v11 = 1381;
            goto LABEL_24;
          }
          v12 = ((__int64 (__fastcall *)(_QWORD, struct IUnknown *, GUID *, void **))v18)(
                  *((unsigned int *)this + 2),
                  a2,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  a4);
          LastError = v12;
          if ( v12 < 0 )
          {
            v13 = 1382;
            goto LABEL_27;
          }
        }
        LastError = 0;
        goto LABEL_29;
      }
      v13 = 1366;
    }
    else
    {
      v13 = 1362;
    }
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)v12,
      v20);
    goto LABEL_29;
  }
  v11 = 1360;
LABEL_24:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v11,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                v10);
LABEL_29:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( lpMem )
    SusFree(lpMem);
  return LastError;
}

```

## disassembly

```asm
0x180019a10  mov     [rsp-28h+arg_10], rbx
0x180019a15  push    rbp
0x180019a16  push    rsi
0x180019a17  push    rdi
0x180019a18  push    r14
0x180019a1a  push    r15
0x180019a1c  mov     rbp, rsp
0x180019a1f  sub     rsp, 50h
0x180019a23  mov     rax, cs:__security_cookie
0x180019a2a  xor     rax, rsp
0x180019a2d  mov     [rbp+var_8], rax
0x180019a31  mov     rsi, r9
0x180019a34  mov     r14, rdx
0x180019a37  mov     rdi, rcx
0x180019a3a  test    rdx, rdx
0x180019a3d  jnz     short loc_180019A61
0x180019a3f  mov     edx, 545h; void *
0x180019a44  mov     ebx, 80004003h
0x180019a49  mov     rcx, [rbp+28h]; this
0x180019a4d  mov     r9d, ebx; char *
0x180019a50  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a5c  jmp     loc_180019C0D
0x180019a61  test    rsi, rsi
0x180019a64  jnz     short loc_180019A6D
0x180019a66  mov     edx, 546h
0x180019a6b  jmp     short loc_180019A44
0x180019a6d  cmp     qword ptr [rcx+38h], 0
0x180019a72  jnz     short loc_180019A80
0x180019a74  mov     ebx, 8000000Eh
0x180019a79  mov     edx, 547h
0x180019a7e  jmp     short loc_180019A49
0x180019a80  mov     [rbp+lpMem], 0
0x180019a88  mov     [rbp+var_18], 0
0x180019a8f  mov     [rbp+var_20], 0
0x180019a97  mov     edx, 4; lpProcName
0x180019a9c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180019aa3  call    cs:__imp_GetProcAddress
0x180019aa9  mov     rbx, rax
0x180019aac  test    rax, rax
0x180019aaf  jnz     short loc_180019ABB
0x180019ab1  mov     edx, 550h
0x180019ab6  jmp     loc_180019B97
0x180019abb  mov     rcx, [rbp+var_20]
0x180019abf  test    rcx, rcx
0x180019ac2  jz      short loc_180019AD8
0x180019ac4  mov     rax, [rcx]
0x180019ac7  mov     rax, [rax+10h]
0x180019acb  call    _guard_dispatch_icall
0x180019ad0  mov     [rbp+var_20], 0
0x180019ad8  lea     rcx, [rbp+var_20]
0x180019adc  mov     rax, rbx
0x180019adf  call    _guard_dispatch_icall
0x180019ae4  mov     ebx, eax
0x180019ae6  test    eax, eax
0x180019ae8  jns     short loc_180019AF4
0x180019aea  mov     edx, 552h
0x180019aef  jmp     loc_180019BCB
0x180019af4  mov     rbx, [rbp+var_20]
0x180019af8  mov     rax, [rbx]
0x180019afb  mov     r15, [rax+28h]
0x180019aff  mov     rcx, [rbp+lpMem]; lpMem
0x180019b03  test    rcx, rcx
0x180019b06  jz      short loc_180019B15
0x180019b08  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180019b0d  mov     [rbp+lpMem], 0
0x180019b15  lea     r9, [rbp+lpMem]
0x180019b19  lea     r8, [rbp+var_18]
0x180019b1d  mov     rdx, [rdi+10h]
0x180019b21  mov     rcx, rbx
0x180019b24  mov     rax, r15
0x180019b27  call    _guard_dispatch_icall
0x180019b2c  mov     ebx, eax
0x180019b2e  test    eax, eax
0x180019b30  jns     short loc_180019B3C
0x180019b32  mov     edx, 556h
0x180019b37  jmp     loc_180019BCB
0x180019b3c  mov     rcx, [rdi+38h]; hModule
0x180019b40  cmp     [rbp+var_18], 0
0x180019b44  jz      short loc_180019B80
0x180019b46  mov     edx, 7; lpProcName
0x180019b4b  call    cs:__imp_GetProcAddress
0x180019b51  test    rax, rax
0x180019b54  jnz     short loc_180019B5D
0x180019b56  mov     edx, 55Dh
0x180019b5b  jmp     short loc_180019B97
0x180019b5d  mov     r9, rsi
0x180019b60  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180019b67  mov     rdx, r14
0x180019b6a  mov     rcx, [rdi+10h]
0x180019b6e  call    _guard_dispatch_icall
0x180019b73  mov     ebx, eax
0x180019b75  test    eax, eax
0x180019b77  jns     short loc_180019BE0
0x180019b79  mov     edx, 55Eh
0x180019b7e  jmp     short loc_180019BCB
0x180019b80  lea     rdx, aWucreateupdate; "WUCreateUpdateHandler"
0x180019b87  call    cs:__imp_GetProcAddress
0x180019b8d  test    rax, rax
0x180019b90  jnz     short loc_180019BAB
0x180019b92  mov     edx, 565h; void *
0x180019b97  mov     rcx, [rbp+28h]; this
0x180019b9b  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019ba2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019ba7  mov     ebx, eax
0x180019ba9  jmp     short loc_180019BE2
0x180019bab  mov     r9, rsi
0x180019bae  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180019bb5  mov     rdx, r14
0x180019bb8  mov     ecx, [rdi+8]
0x180019bbb  call    _guard_dispatch_icall
0x180019bc0  mov     ebx, eax
0x180019bc2  test    eax, eax
0x180019bc4  jns     short loc_180019BE0
0x180019bc6  mov     edx, 566h; void *
0x180019bcb  mov     r9d, eax; char *
0x180019bce  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019bd5  mov     rcx, [rbp+28h]; this
0x180019bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019bde  jmp     short loc_180019BE2
0x180019be0  xor     ebx, ebx
0x180019be2  mov     rcx, [rbp+var_20]
0x180019be6  test    rcx, rcx
0x180019be9  jz      short loc_180019BFF
0x180019beb  mov     rax, [rcx]
0x180019bee  mov     rax, [rax+10h]
0x180019bf2  call    _guard_dispatch_icall
0x180019bf7  mov     [rbp+var_20], 0
0x180019bff  mov     rcx, [rbp+lpMem]; lpMem
0x180019c03  test    rcx, rcx
0x180019c06  jz      short loc_180019C0D
0x180019c08  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180019c0d  mov     eax, ebx
0x180019c0f  mov     rcx, [rbp+var_8]
0x180019c13  xor     rcx, rsp; StackCookie
0x180019c16  call    __security_check_cookie
0x180019c1b  mov     rbx, [rsp+50h+arg_10]
0x180019c23  add     rsp, 50h
0x180019c27  pop     r15
0x180019c29  pop     r14
0x180019c2b  pop     rdi
0x180019c2c  pop     rsi
0x180019c2d  pop     rbp
0x180019c2e  retn
```
