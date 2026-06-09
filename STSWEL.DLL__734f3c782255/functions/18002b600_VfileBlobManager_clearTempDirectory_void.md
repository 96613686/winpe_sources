# VfileBlobManager::clearTempDirectory(void)

- ea: `0x18002b600`
- end: `0x18002b988`
- name: `?clearTempDirectory@VfileBlobManager@@KA?AVVHRESULT@@XZ`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027e80`

## callees

- `0x18002b600`
- `0x1801c1770`
- `0x1801c2da0`

## import_xrefs

- `KERNEL32!FindClose` at `0x18002b8c9`
- `KERNEL32!FindClose` at `0x18002b8c9`
- `KERNEL32!FindNextFileA` at `0x18002b889`
- `KERNEL32!FindNextFileA` at `0x18002b889`
- `KERNEL32!DeleteFileA` at `0x18002b81a`
- `KERNEL32!DeleteFileA` at `0x18002b81a`
- `KERNEL32!FindFirstFileA` at `0x18002b75f`
- `KERNEL32!FindFirstFileA` at `0x18002b75f`
- `KERNEL32!SystemTimeToFileTime` at `0x18002b6ba`
- `KERNEL32!SystemTimeToFileTime` at `0x18002b6ba`
- `KERNEL32!GetLastError` at `0x18002b6c4`
- `KERNEL32!GetLastError` at `0x18002b830`
- `KERNEL32!GetLastError` at `0x18002b6c4`
- `KERNEL32!GetLastError` at `0x18002b830`
- `KERNEL32!GetSystemTime` at `0x18002b6a4`
- `KERNEL32!GetSystemTime` at `0x18002b6a4`
- `onetutil!??4Vstring@@QEAAAEAV0@AEBV0@@Z` at `0x18002b71c`
- `onetutil!??4Vstring@@QEAAAEAV0@AEBV0@@Z` at `0x18002b7eb`
- `onetutil!??4Vstring@@QEAAAEAV0@AEBV0@@Z` at `0x18002b71c`
- `onetutil!??4Vstring@@QEAAAEAV0@AEBV0@@Z` at `0x18002b7eb`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b74e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b811`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b83d`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b74e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b811`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18002b83d`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x18002b91e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x18002b91e`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x18002b951`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x18002b951`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x18002b824`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x18002b8d4`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x18002b824`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x18002b8d4`
- `onetutil!??0Vpath@@QEAA@PEBD@Z` at `0x18002b658`
- `onetutil!??0Vpath@@QEAA@PEBD@Z` at `0x18002b658`
- `onetutil!?tempDir@Vpath@@SAPEAVVstatus@@PEAVVstring@@@Z` at `0x18002b6ea`
- `onetutil!?tempDir@Vpath@@SAPEAVVstatus@@PEAVVstring@@@Z` at `0x18002b6ea`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b70d`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b7c5`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b7dc`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b70d`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b7c5`
- `onetutil!??H@YA?AVVstring@@AEBV0@PEBD@Z` at `0x18002b7dc`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18002b737`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18002b737`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18002b8b7`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18002b8b7`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b664`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b670`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b67c`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b664`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b670`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x18002b67c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b728`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b7f7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b806`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b92a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b936`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b942`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b728`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b7f7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b806`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b92a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b936`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18002b942`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18002b72e`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18002b8ae`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18002b72e`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18002b8ae`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18002b688`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18002b688`

## string_xrefs

- `0x18002b84c`: `Cannot delete temp file: %s Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
VHRESULT *__fastcall VfileBlobManager::clearTempDirectory(VHRESULT *a1)
{
  VHRESULT *v1; // r13
  signed int LastError; // eax
  __int64 v3; // rdx
  _FILETIME v4; // rbx
  struct Vstatus *v5; // rdi
  __int64 v6; // rax
  VthreadContext *v7; // rax
  const CHAR *v8; // rax
  HANDLE FirstFileA; // r12
  __int64 v10; // rax
  __int64 v11; // rax
  const CHAR *v12; // rax
  struct VprocessGlobals *v13; // r14
  __int64 v14; // rsi
  DWORD v15; // edi
  const char *v16; // rax
  VthreadContext *v17; // rax
  struct VprocessGlobals *v18; // rax
  int v20; // [rsp+20h] [rbp-228h]
  __int64 v21; // [rsp+38h] [rbp-210h]
  _BYTE v22[8]; // [rsp+50h] [rbp-1F8h] BYREF
  _BYTE v23[8]; // [rsp+58h] [rbp-1F0h] BYREF
  int v24; // [rsp+60h] [rbp-1E8h]
  _BYTE v25[8]; // [rsp+68h] [rbp-1E0h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-1D0h]
  _FILETIME FileTime; // [rsp+80h] [rbp-1C8h] BYREF
  _BYTE v29[8]; // [rsp+88h] [rbp-1C0h] BYREF
  VHRESULT *v30; // [rsp+90h] [rbp-1B8h]
  __int64 v31; // [rsp+98h] [rbp-1B0h]
  _BYTE v32[24]; // [rsp+A0h] [rbp-1A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-190h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+D0h] [rbp-178h] BYREF

  v31 = -2;
  v1 = a1;
  v30 = a1;
  v24 = 0;
  Vpath::Vpath((Vpath *)v32, ".");
  Vstring::Vstring((Vstring *)v23);
  Vstring::Vstring((Vstring *)v25);
  Vstring::Vstring((Vstring *)v22);
  VHRESULT::VHRESULT(v1, 0);
  v24 = 1;
  v27 = -1;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v3 = (unsigned int)LastError;
    goto LABEL_19;
  }
  v4 = FileTime;
  v5 = Vpath::tempDir((struct Vstring *)v23);
  if ( v5 )
    goto LABEL_18;
  v6 = operator+(v26, v23, "\\*.*");
  Vstring::operator=(v25, v6);
  Vstring::~Vstring((Vstring *)v26);
  v7 = (VthreadContext *)VthreadContext::pCurrentContext();
  v5 = VthreadContext::suspendImpersonation(v7);
  if ( v5 )
    goto LABEL_18;
  try
  {
    v8 = Vstring::data((Vstring *)v25);
    FirstFileA = FindFirstFileA(v8, &FindFileData);
    v27 = (__int64)FirstFileA;
    if ( FirstFileA != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && *(_QWORD *)&FindFileData.ftLastWriteTime < *(unsigned __int64 *)&v4
          && *(_QWORD *)&v4 - *(_QWORD *)&FindFileData.ftLastWriteTime > 0xC92A69C000uLL )
        {
          v10 = operator+(v29, v23, "\\");
          v11 = operator+(v26, v10, FindFileData.cFileName);
          Vstring::operator=(v22, v11);
          Vstring::~Vstring((Vstring *)v26);
          Vstring::~Vstring((Vstring *)v29);
          v12 = Vstring::data((Vstring *)v22);
          if ( !DeleteFileA(v12) )
          {
            v13 = VgetProcessGlobals();
            v14 = *(_QWORD *)v13;
            v15 = GetLastError();
            v16 = Vstring::data((Vstring *)v22);
            LODWORD(v21) = v15;
            LOWORD(v20) = 1;
            (*(void (**)(struct VprocessGlobals *, __int64, __int64, _QWORD, int, const char *, ...))(v14 + 80))(
              v13,
              926051379,
              117141571,
              0,
              v20,
              "Cannot delete temp file: %s Error = %d",
              v16,
              v21);
          }
        }
      }
      while ( FindNextFileA(FirstFileA, &FindFileData) );
    }
  }
  catch ( ... )
  {
    FirstFileA = (HANDLE)v27;
    v1 = v30;
  }
  v17 = (VthreadContext *)VthreadContext::pCurrentContext();
  v5 = VthreadContext::resumeImpersonation(v17);
  if ( FirstFileA != (HANDLE)-1LL )
    FindClose(FirstFileA);
  if ( v5 )
  {
LABEL_18:
    v18 = VgetProcessGlobals();
    (*(void (__fastcall **)(struct VprocessGlobals *, __int64, __int64, _QWORD, struct Vstatus *))(*(_QWORD *)v18 + 32LL))(
      v18,
      926051380,
      117141571,
      0,
      v5);
    (**(void (__fastcall ***)(struct Vstatus *, __int64))v5)(v5, 1);
    v3 = 2147500037LL;
LABEL_19:
    VHRESULT::operator=(v1, v3);
  }
  Vstring::~Vstring((Vstring *)v22);
  Vstring::~Vstring((Vstring *)v25);
  Vstring::~Vstring((Vstring *)v23);
  Vpath::~Vpath((Vpath *)v32);
  return v1;
}

```

## disassembly

```asm
0x18002b600  mov     r11, rsp
0x18002b603  push    rdi
0x18002b604  push    r12
0x18002b606  push    r13
0x18002b608  push    r14
0x18002b60a  push    r15
0x18002b60c  sub     rsp, 220h
0x18002b613  mov     qword ptr [r11-1B0h], 0FFFFFFFFFFFFFFFEh
0x18002b61e  mov     [r11+10h], rbx
0x18002b622  mov     [r11+18h], rsi
0x18002b626  mov     rax, cs:__security_cookie
0x18002b62d  xor     rax, rsp
0x18002b630  mov     [rsp+248h+var_38], rax
0x18002b638  mov     r13, rcx
0x18002b63b  mov     [r11-1B8h], rcx
0x18002b642  xor     r15d, r15d
0x18002b645  mov     [rsp+248h+var_1E8], r15d
0x18002b64a  lea     rdx, asc_180217BF0; "."
0x18002b651  lea     rcx, [r11-1A8h]
0x18002b658  call    cs:??0Vpath@@QEAA@PEBD@Z; Vpath::Vpath(char const *)
0x18002b65e  nop
0x18002b65f  lea     rcx, [rsp+248h+var_1F0]
0x18002b664  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x18002b66a  nop
0x18002b66b  lea     rcx, [rsp+248h+var_1E0]
0x18002b670  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x18002b676  nop
0x18002b677  lea     rcx, [rsp+248h+var_1F8]
0x18002b67c  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x18002b682  nop
0x18002b683  xor     edx, edx
0x18002b685  mov     rcx, r13
0x18002b688  call    cs:??0VHRESULT@@QEAA@J@Z; VHRESULT::VHRESULT(long)
0x18002b68e  lea     esi, [r15+1]
0x18002b692  mov     [rsp+248h+var_1E8], esi
0x18002b696  or      [rsp+248h+var_1D0], 0FFFFFFFFFFFFFFFFh
0x18002b69c  lea     rcx, [rsp+248h+SystemTime]; lpSystemTime
0x18002b6a4  call    cs:GetSystemTime
0x18002b6aa  lea     rdx, [rsp+248h+FileTime]; lpFileTime
0x18002b6b2  lea     rcx, [rsp+248h+SystemTime]; lpSystemTime
0x18002b6ba  call    cs:SystemTimeToFileTime
0x18002b6c0  test    eax, eax
0x18002b6c2  jnz     short loc_18002B6DD
0x18002b6c4  call    cs:GetLastError
0x18002b6ca  movzx   edx, ax
0x18002b6cd  or      edx, 80070000h
0x18002b6d3  test    eax, eax
0x18002b6d5  cmovle  edx, eax
0x18002b6d8  jmp     loc_18002B91B
0x18002b6dd  mov     rbx, qword ptr [rsp+248h+FileTime.dwLowDateTime]
0x18002b6e5  lea     rcx, [rsp+248h+var_1F0]
0x18002b6ea  call    cs:?tempDir@Vpath@@SAPEAVVstatus@@PEAVVstring@@@Z; Vpath::tempDir(Vstring *)
0x18002b6f0  mov     rdi, rax
0x18002b6f3  test    rax, rax
0x18002b6f6  jnz     loc_18002B8D4
0x18002b6fc  lea     r8, asc_180217BB8; "\\*.*"
0x18002b703  lea     rdx, [rsp+248h+var_1F0]
0x18002b708  lea     rcx, [rsp+248h+var_1D8]
0x18002b70d  call    cs:??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x18002b713  nop
0x18002b714  mov     rdx, rax
0x18002b717  lea     rcx, [rsp+248h+var_1E0]
0x18002b71c  call    cs:??4Vstring@@QEAAAEAV0@AEBV0@@Z; Vstring::operator=(Vstring const &)
0x18002b722  nop
0x18002b723  lea     rcx, [rsp+248h+var_1D8]
0x18002b728  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b72e  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x18002b734  mov     rcx, rax
0x18002b737  call    cs:?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::suspendImpersonation(void)
0x18002b73d  mov     rdi, rax
0x18002b740  test    rax, rax
0x18002b743  jnz     loc_18002B8D4
0x18002b749  lea     rcx, [rsp+248h+var_1E0]
0x18002b74e  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x18002b754  mov     rcx, rax; lpFileName
0x18002b757  lea     rdx, [rsp+248h+FindFileData]; lpFindFileData
0x18002b75f  call    cs:FindFirstFileA
0x18002b765  mov     r12, rax
0x18002b768  mov     [rsp+248h+var_1D0], rax
0x18002b76d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b771  jz      loc_18002B89A
0x18002b777  test    byte ptr [rsp+248h+FindFileData.dwFileAttributes], 10h
0x18002b77f  jnz     loc_18002B87E
0x18002b785  cmp     qword ptr [rsp+248h+FindFileData.ftLastWriteTime.dwLowDateTime], rbx
0x18002b78d  jnb     loc_18002B87E
0x18002b793  mov     rax, rbx
0x18002b796  sub     rax, qword ptr [rsp+248h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18002b79e  mov     rcx, 0C92A69C000h
0x18002b7a8  cmp     rax, rcx
0x18002b7ab  jbe     loc_18002B87E
0x18002b7b1  lea     r8, asc_180217BC0; "\\"
0x18002b7b8  lea     rdx, [rsp+248h+var_1F0]
0x18002b7bd  lea     rcx, [rsp+248h+var_1C0]
0x18002b7c5  call    cs:??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x18002b7cb  nop
0x18002b7cc  lea     r8, [rsp+248h+FindFileData.cFileName]
0x18002b7d4  mov     rdx, rax
0x18002b7d7  lea     rcx, [rsp+248h+var_1D8]
0x18002b7dc  call    cs:??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x18002b7e2  nop
0x18002b7e3  mov     rdx, rax
0x18002b7e6  lea     rcx, [rsp+248h+var_1F8]
0x18002b7eb  call    cs:??4Vstring@@QEAAAEAV0@AEBV0@@Z; Vstring::operator=(Vstring const &)
0x18002b7f1  nop
0x18002b7f2  lea     rcx, [rsp+248h+var_1D8]
0x18002b7f7  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b7fd  nop
0x18002b7fe  lea     rcx, [rsp+248h+var_1C0]
0x18002b806  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b80c  lea     rcx, [rsp+248h+var_1F8]
0x18002b811  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x18002b817  mov     rcx, rax; lpFileName
0x18002b81a  call    cs:DeleteFileA
0x18002b820  test    eax, eax
0x18002b822  jnz     short loc_18002B87E
0x18002b824  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x18002b82a  mov     r14, rax
0x18002b82d  mov     rsi, [rax]
0x18002b830  call    cs:GetLastError
0x18002b836  mov     edi, eax
0x18002b838  lea     rcx, [rsp+248h+var_1F8]
0x18002b83d  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x18002b843  mov     dword ptr [rsp+248h+var_210], edi
0x18002b847  mov     [rsp+248h+var_218], rax
0x18002b84c  lea     rax, aCannotDeleteTe; "Cannot delete temp file: %s Error = %d"
0x18002b853  mov     [rsp+248h+var_220], rax
0x18002b858  mov     eax, 1
0x18002b85d  mov     word ptr [rsp+248h+var_228], ax
0x18002b862  movzx   r9d, r15w
0x18002b866  mov     edx, 37326C33h
0x18002b86b  mov     r8d, 6FB7043h
0x18002b871  mov     rcx, r14
0x18002b874  mov     rax, [rsi+50h]
0x18002b878  call    cs:__guard_dispatch_icall_fptr
0x18002b87e  lea     rdx, [rsp+248h+FindFileData]; lpFindFileData
0x18002b886  mov     rcx, r12; hFindFile
0x18002b889  call    cs:FindNextFileA
0x18002b88f  test    eax, eax
0x18002b891  jnz     loc_18002B777
0x18002b897  lea     esi, [rax+1]
0x18002b89a  jmp     short loc_18002B8AE
0x18002b89c  mov     esi, 1
0x18002b8a1  mov     r12, [rsp+248h+var_1D0]
0x18002b8a6  mov     r13, [rsp+248h+var_1B8]
0x18002b8ae  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x18002b8b4  mov     rcx, rax
0x18002b8b7  call    cs:?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::resumeImpersonation(void)
0x18002b8bd  mov     rdi, rax
0x18002b8c0  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18002b8c4  jz      short loc_18002B8CF
0x18002b8c6  mov     rcx, r12; hFindFile
0x18002b8c9  call    cs:FindClose
0x18002b8cf  test    rdi, rdi
0x18002b8d2  jz      short loc_18002B925
0x18002b8d4  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x18002b8da  mov     r10, rax
0x18002b8dd  mov     rcx, [rax]
0x18002b8e0  xor     r9d, r9d
0x18002b8e3  mov     rax, [rcx+20h]
0x18002b8e7  mov     [rsp+248h+var_228], rdi
0x18002b8ec  mov     edx, 37326C34h
0x18002b8f1  mov     r8d, 6FB7043h
0x18002b8f7  mov     rcx, r10
0x18002b8fa  call    cs:__guard_dispatch_icall_fptr
0x18002b900  test    rdi, rdi
0x18002b903  jz      short loc_18002B916
0x18002b905  mov     rax, [rdi]
0x18002b908  mov     edx, esi
0x18002b90a  mov     rcx, rdi
0x18002b90d  mov     rax, [rax]
0x18002b910  call    cs:__guard_dispatch_icall_fptr
0x18002b916  mov     edx, 80004005h
0x18002b91b  mov     rcx, r13
0x18002b91e  call    cs:??4VHRESULT@@QEAAAEAV0@J@Z; VHRESULT::operator=(long)
0x18002b924  nop
0x18002b925  lea     rcx, [rsp+248h+var_1F8]
0x18002b92a  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b930  nop
0x18002b931  lea     rcx, [rsp+248h+var_1E0]
0x18002b936  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b93c  nop
0x18002b93d  lea     rcx, [rsp+248h+var_1F0]
0x18002b942  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18002b948  nop
0x18002b949  lea     rcx, [rsp+248h+var_1A8]
0x18002b951  call    cs:??1Vpath@@QEAA@XZ; Vpath::~Vpath(void)
0x18002b957  mov     rax, r13
0x18002b95a  mov     rcx, [rsp+248h+var_38]
0x18002b962  xor     rcx, rsp
0x18002b965  call    sub_1801C1770
0x18002b96a  lea     r11, [rsp+248h+var_28]
0x18002b972  mov     rbx, [r11+38h]
0x18002b976  mov     rsi, [r11+40h]
0x18002b97a  mov     rsp, r11
0x18002b97d  pop     r15
0x18002b97f  pop     r14
0x18002b981  pop     r13
0x18002b983  pop     r12
0x18002b985  pop     rdi
0x18002b986  retn
```
