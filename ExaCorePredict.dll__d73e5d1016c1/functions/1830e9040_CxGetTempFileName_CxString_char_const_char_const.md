# CxGetTempFileName(CxString &,char const *,char const *)

- ea: `0x1830e9040`
- end: `0x1830e9192`
- name: `?CxGetTempFileName@@YA_NAEAVCxString@@PEBD1@Z`
- size: `338`
- prototype: `bool __fastcall(struct CxString *this, const char *DirectoryName, const char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x182dcc6d0`
- `0x183052e40`
- `0x183053010`
- `0x183053170`
- `0x183055850`
- `0x183055940`
- `0x183055970`
- `0x1830e9040`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1830e909c`
- `KERNEL32!GetCurrentProcessId` at `0x1830e909c`
- `api-ms-win-crt-stdio-l1-1-0!tmpnam_s` at `0x1830e90e5`
- `api-ms-win-crt-stdio-l1-1-0!tmpnam_s` at `0x1830e90e5`
- `api-ms-win-crt-stdio-l1-1-0!_tempnam` at `0x1830e90cd`
- `api-ms-win-crt-stdio-l1-1-0!_tempnam` at `0x1830e90cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1830e913e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1830e913e`

## string_xrefs

- `0x1830e9150`: `Failed to get the name of a temp file.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CxGetTempFileName(struct CxString *this, const char *DirectoryName, const char *a3)
{
  int v6; // ebx
  DWORD CurrentProcessId; // eax
  const char *CharPointer; // rax
  char *v9; // rax
  char *v10; // rbx
  unsigned __int8 v11; // bl
  _BYTE v13[8]; // [rsp+30h] [rbp-158h] BYREF
  __int64 v14; // [rsp+38h] [rbp-150h]
  _QWORD v15[2]; // [rsp+40h] [rbp-148h] BYREF
  char Buffer[272]; // [rsp+50h] [rbp-138h] BYREF

  v14 = -2;
  v15[0] = 0;
  CxString::CxString((CxString *)v15, a3);
  v6 = dword_1836E8600++;
  CurrentProcessId = GetCurrentProcessId();
  CxString::Format((CxString *)v15, "%s%d%d", a3, CurrentProcessId, v6);
  CharPointer = CxString::GetCharPointer((CxString *)v15);
  v9 = _tempnam(DirectoryName, CharPointer);
  v10 = v9;
  if ( v9 )
  {
    CxString::CxString((CxString *)v13, v9);
    CxString::operator=(this, v13);
    CxString::~CxString((CxString *)v13);
    free(v10);
  }
  else
  {
    tmpnam_s(Buffer, 0x104u);
    CxString::CxString((CxString *)v13, Buffer);
    CxString::operator=(this, v13);
    CxString::~CxString((CxString *)v13);
  }
  if ( CxString::IsEmpty(this) )
  {
    CxReportError("Failed to get the name of a temp file.");
    v11 = 0;
  }
  else
  {
    v11 = 1;
  }
  CxString::~CxString((CxString *)v15);
  return v11;
}

```

## disassembly

```asm
0x1830e9040  push    rbp
0x1830e9042  push    rsi
0x1830e9043  push    rdi
0x1830e9044  sub     rsp, 170h
0x1830e904b  mov     [rsp+188h+var_150], 0FFFFFFFFFFFFFFFEh
0x1830e9054  mov     [rsp+188h+arg_18], rbx
0x1830e905c  mov     rax, cs:__security_cookie
0x1830e9063  xor     rax, rsp
0x1830e9066  mov     [rsp+188h+var_28], rax
0x1830e906e  mov     rdi, r8
0x1830e9071  mov     rsi, rdx
0x1830e9074  mov     rbp, rcx
0x1830e9077  xor     eax, eax
0x1830e9079  mov     [rsp+188h+var_148], rax
0x1830e907e  mov     rdx, r8; char *
0x1830e9081  lea     rcx, [rsp+188h+var_148]; this
0x1830e9086  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x1830e908b  nop
0x1830e908c  mov     eax, cs:dword_1836E8600
0x1830e9092  mov     ebx, eax
0x1830e9094  inc     eax
0x1830e9096  mov     cs:dword_1836E8600, eax
0x1830e909c  call    cs:__imp_GetCurrentProcessId
0x1830e90a2  mov     r9d, eax
0x1830e90a5  mov     [rsp+188h+var_168], ebx
0x1830e90a9  mov     r8, rdi
0x1830e90ac  lea     rdx, aSDD; "%s%d%d"
0x1830e90b3  lea     rcx, [rsp+188h+var_148]; this
0x1830e90b8  call    ?Format@CxString@@QEAAXPEBDZZ; CxString::Format(char const *,...)
0x1830e90bd  lea     rcx, [rsp+188h+var_148]; this
0x1830e90c2  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830e90c7  mov     rdx, rax; FilePrefix
0x1830e90ca  mov     rcx, rsi; DirectoryName
0x1830e90cd  call    cs:__imp__tempnam
0x1830e90d3  mov     rbx, rax
0x1830e90d6  test    rax, rax
0x1830e90d9  jnz     short loc_1830E9115
0x1830e90db  mov     edx, 104h; Size
0x1830e90e0  lea     rcx, [rsp+188h+Buffer]; Buffer
0x1830e90e5  call    cs:__imp_tmpnam_s
0x1830e90eb  lea     rdx, [rsp+188h+Buffer]; char *
0x1830e90f0  lea     rcx, [rsp+188h+var_158]; this
0x1830e90f5  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x1830e90fa  nop
0x1830e90fb  lea     rdx, [rsp+188h+var_158]
0x1830e9100  mov     rcx, rbp
0x1830e9103  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z; CxString::operator=(CxString const &)
0x1830e9108  nop
0x1830e9109  lea     rcx, [rsp+188h+var_158]; this
0x1830e910e  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830e9113  jmp     short loc_1830E9144
0x1830e9115  mov     rdx, rbx; char *
0x1830e9118  lea     rcx, [rsp+188h+var_158]; this
0x1830e911d  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x1830e9122  nop
0x1830e9123  lea     rdx, [rsp+188h+var_158]
0x1830e9128  mov     rcx, rbp
0x1830e912b  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z; CxString::operator=(CxString const &)
0x1830e9130  nop
0x1830e9131  lea     rcx, [rsp+188h+var_158]; this
0x1830e9136  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830e913b  mov     rcx, rbx; Block
0x1830e913e  call    cs:__imp_free
0x1830e9144  mov     rcx, rbp; this
0x1830e9147  call    ?IsEmpty@CxString@@QEBA_NXZ; CxString::IsEmpty(void)
0x1830e914c  test    al, al
0x1830e914e  jz      short loc_1830E9160
0x1830e9150  lea     rcx, aFailedToGetThe; "Failed to get the name of a temp file."
0x1830e9157  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830e915c  xor     bl, bl
0x1830e915e  jmp     short loc_1830E9162
0x1830e9160  mov     bl, 1
0x1830e9162  lea     rcx, [rsp+188h+var_148]; this
0x1830e9167  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830e916c  movzx   eax, bl
0x1830e916f  mov     rcx, [rsp+188h+var_28]
0x1830e9177  xor     rcx, rsp; StackCookie
0x1830e917a  call    __security_check_cookie
0x1830e917f  mov     rbx, [rsp+188h+arg_18]
0x1830e9187  add     rsp, 170h
0x1830e918e  pop     rdi
0x1830e918f  pop     rsi
0x1830e9190  pop     rbp
0x1830e9191  retn
```
