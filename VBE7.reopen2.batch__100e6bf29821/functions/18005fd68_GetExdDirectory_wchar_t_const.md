# GetExdDirectory(wchar_t const *)

- ea: `0x18005fd68`
- end: `0x18005ffdc`
- name: `?GetExdDirectory@@YAPEA_WPEB_W@Z`
- size: `628`
- prototype: `wchar_t *__fastcall(const wchar_t *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180046e4c`
- `0x18005f644`
- `0x1800796b0`

## callees

- `0x18001b8b0`
- `0x18001ba34`
- `0x18001bf20`
- `0x18001bff0`
- `0x18001c1b0`
- `0x18001c844`
- `0x18005aa78`
- `0x18005ab18`
- `0x18005fd68`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x18005fdfd`
- `MSVCR100!strcpy_s` at `0x18005fdfd`
- `MSVCR100!strcat_s` at `0x18005fe2c`
- `MSVCR100!strcat_s` at `0x18005fe2c`
- `MSVCR100!_access_s` at `0x18005feeb`
- `MSVCR100!_access_s` at `0x18005ff54`
- `MSVCR100!_access_s` at `0x18005feeb`
- `MSVCR100!_access_s` at `0x18005ff54`
- `MSVCR100!_access` at `0x18005fde2`
- `MSVCR100!_access` at `0x18005fde2`
- `MSVCR100!_mkdir` at `0x18005fe5a`
- `MSVCR100!_mkdir` at `0x18005ff01`
- `MSVCR100!_mkdir` at `0x18005fe5a`
- `MSVCR100!_mkdir` at `0x18005ff01`
- `KERNEL32!GetTempPathA` at `0x18005fdc0`
- `KERNEL32!GetTempPathA` at `0x18005fdc0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005ffc2`
- `OLEAUT32!__imp_SysAllocString` at `0x18005ffc2`

## pseudocode

```c
BSTR __fastcall GetExdDirectory(const wchar_t *a1)
{
  DWORD TempPathA; // eax
  __int64 v3; // rdi
  __int64 v4; // rcx
  char *i; // rbx
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  const char *NonPrintDriveDir; // rax
  const char *PrintDriveDir; // rax
  int v14; // eax
  const char *v16; // rax
  const char *v17; // rbx
  const char *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  const OLECHAR *v23; // rax
  BSTR v24; // rbx
  wchar_t v25[16]; // [rsp+20h] [rbp+0h] BYREF
  char Destination[2048]; // [rsp+40h] [rbp+20h] BYREF
  CHAR Buffer[2048]; // [rsp+840h] [rbp+820h] BYREF

  CFileRep::CFileRep((CFileRep *)v25);
  TempPathA = GetTempPathA(0x800u, Buffer);
  if ( !TempPathA || TempPathA > 0x800 )
    goto LABEL_23;
  v3 = -1;
  if ( _access(Buffer, 0) )
  {
    strcpy_s(Destination, 0x800u, Buffer);
    v4 = -1;
    do
      ++v4;
    while ( Destination[v4] );
    if ( Destination[v4 - 1] != 92 )
      strcat_s(Destination, 0x800u, "\\");
    for ( i = Destination; *i; ++i )
    {
      do
      {
        if ( *i == 92 )
          break;
        ++i;
      }
      while ( *i );
      if ( *i )
      {
        *i = 0;
        _mkdir(Destination);
        *i = 92;
      }
    }
  }
  CFileRep::SetDirectory((CFileRep *)v25, Buffer);
  if ( ((unsigned __int64)a1 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = 2 * v6 + 1;
    v8 = v7 + 15;
    if ( v7 + 15 < v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    a1 = (const wchar_t *)strcpyAfromW((char *)v25, a1);
  }
  CFileRep::AddDirToDir((CFileRep *)v25, (const char *)a1);
  NonPrintDriveDir = CFileRep::GetNonPrintDriveDir((CFileRep *)v25);
  if ( _access_s(NonPrintDriveDir, 0) )
  {
    PrintDriveDir = CFileRep::GetPrintDriveDir((CFileRep *)v25);
    v14 = _mkdir(PrintDriveDir);
  }
  else
  {
    v16 = CFileRep::GetNonPrintDriveDir((CFileRep *)v25);
    v14 = _access_s(v16, 2);
  }
  if ( !v14 )
  {
    if ( ((unsigned __int64)CFileRep::GetNonPrintDriveDir((CFileRep *)v25) & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v17 = CFileRep::GetNonPrintDriveDir((CFileRep *)v25);
      v18 = CFileRep::GetNonPrintDriveDir((CFileRep *)v25);
      do
        ++v3;
      while ( v18[v3] );
      v19 = 2 * v3 + 17;
      if ( v19 <= 2 * v3 + 2 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      v23 = strcpyWfromA(v25, v17);
    }
    else
    {
      v23 = (const OLECHAR *)CFileRep::GetNonPrintDriveDir((CFileRep *)v25);
    }
    v24 = SysAllocString(v23);
    CFileRep::~CFileRep((CFileRep *)v25);
    return v24;
  }
  else
  {
LABEL_23:
    CFileRep::~CFileRep((CFileRep *)v25);
    return 0;
  }
}

```

## disassembly

```asm
0x18005fd68  push    rbp
0x18005fd6a  push    r14
0x18005fd6c  push    r15
0x18005fd6e  mov     eax, 1050h
0x18005fd73  call    _alloca_probe
0x18005fd78  sub     rsp, rax
0x18005fd7b  lea     rbp, [rsp+20h]
0x18005fd80  mov     [rbp+1040h+arg_8], rbx
0x18005fd87  mov     [rbp+1040h+arg_10], rsi
0x18005fd8e  mov     [rbp+1040h+arg_18], rdi
0x18005fd95  mov     rax, cs:__security_cookie
0x18005fd9c  xor     rax, rbp
0x18005fd9f  mov     [rbp+1040h+var_20], rax
0x18005fda6  mov     rsi, rcx
0x18005fda9  lea     rcx, [rbp+1040h+var_1040]; this
0x18005fdad  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x18005fdb2  mov     ebx, 800h
0x18005fdb7  lea     rdx, [rbp+1040h+Buffer]; lpBuffer
0x18005fdbe  mov     ecx, ebx; nBufferLength
0x18005fdc0  call    cs:__imp_GetTempPathA
0x18005fdc6  xor     r14d, r14d
0x18005fdc9  test    eax, eax
0x18005fdcb  jz      loc_18005FF0B
0x18005fdd1  cmp     eax, ebx
0x18005fdd3  ja      loc_18005FF0B
0x18005fdd9  lea     rcx, [rbp+1040h+Buffer]; FileName
0x18005fde0  xor     edx, edx; AccessMode
0x18005fde2  call    cs:__imp__access
0x18005fde8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005fdec  test    eax, eax
0x18005fdee  jz      short loc_18005FE6B
0x18005fdf0  lea     r8, [rbp+1040h+Buffer]; Source
0x18005fdf7  lea     rcx, [rbp+1040h+Destination]; Destination
0x18005fdfb  mov     edx, ebx; SizeInBytes
0x18005fdfd  call    cs:__imp_strcpy_s
0x18005fe03  lea     r11, [rbp+1040h+Destination]
0x18005fe07  mov     rcx, rdi
0x18005fe0a  inc     rcx
0x18005fe0d  cmp     [r11+rcx], r14b
0x18005fe11  jnz     short loc_18005FE0A
0x18005fe13  lea     rax, [rbp+1040h+Destination]
0x18005fe17  cmp     byte ptr [rcx+rax-1], 5Ch ; '\'
0x18005fe1c  jz      short loc_18005FE32
0x18005fe1e  lea     r8, asc_1803A109C; "\\"
0x18005fe25  lea     rcx, [rbp+1040h+Destination]; Destination
0x18005fe29  mov     rdx, rbx; SizeInBytes
0x18005fe2c  call    cs:__imp_strcat_s
0x18005fe32  lea     rbx, [rbp+1040h+Destination]
0x18005fe36  cmp     [rbp+1040h+Destination], r14b
0x18005fe3a  jz      short loc_18005FE6B
0x18005fe3c  cmp     [rbx], r14b
0x18005fe3f  jz      short loc_18005FE63
0x18005fe41  cmp     byte ptr [rbx], 5Ch ; '\'
0x18005fe44  jz      short loc_18005FE4E
0x18005fe46  inc     rbx
0x18005fe49  cmp     [rbx], r14b
0x18005fe4c  jnz     short loc_18005FE41
0x18005fe4e  cmp     [rbx], r14b
0x18005fe51  jz      short loc_18005FE63
0x18005fe53  lea     rcx, [rbp+1040h+Destination]; Path
0x18005fe57  mov     [rbx], r14b
0x18005fe5a  call    cs:__imp__mkdir
0x18005fe60  mov     byte ptr [rbx], 5Ch ; '\'
0x18005fe63  inc     rbx
0x18005fe66  cmp     [rbx], r14b
0x18005fe69  jnz     short loc_18005FE41
0x18005fe6b  lea     rdx, [rbp+1040h+Buffer]; char *
0x18005fe72  lea     rcx, [rbp+1040h+var_1040]; this
0x18005fe76  call    ?SetDirectory@CFileRep@@QEAAHPEBD@Z; CFileRep::SetDirectory(char const *)
0x18005fe7b  mov     rbx, 0FFFFFFFFFFFF0000h
0x18005fe82  mov     r15, 0FFFFFFFFFFFFFF0h
0x18005fe8c  test    rbx, rsi
0x18005fe8f  jz      short loc_18005FED1
0x18005fe91  mov     rax, rdi
0x18005fe94  inc     rax
0x18005fe97  cmp     [rsi+rax*2], r14w
0x18005fe9c  jnz     short loc_18005FE94
0x18005fe9e  lea     rax, ds:1[rax*2]
0x18005fea6  lea     rcx, [rax+0Fh]
0x18005feaa  cmp     rcx, rax
0x18005fead  ja      short loc_18005FEB2
0x18005feaf  mov     rcx, r15
0x18005feb2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005feb6  mov     rax, rcx
0x18005feb9  call    _alloca_probe
0x18005febe  sub     rsp, rcx
0x18005fec1  mov     rdx, rsi; wchar_t *
0x18005fec4  lea     rcx, [rsp+1060h+var_1040]; char *
0x18005fec9  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x18005fece  mov     rsi, rax
0x18005fed1  lea     rcx, [rbp+1040h+var_1040]; this
0x18005fed5  mov     rdx, rsi; char *
0x18005fed8  call    ?AddDirToDir@CFileRep@@QEAAHPEBD@Z; CFileRep::AddDirToDir(char const *)
0x18005fedd  lea     rcx, [rbp+1040h+var_1040]; this
0x18005fee1  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005fee6  xor     edx, edx; AccessMode
0x18005fee8  mov     rcx, rax; FileName
0x18005feeb  call    cs:__imp__access_s
0x18005fef1  lea     rcx, [rbp+1040h+var_1040]; this
0x18005fef5  test    eax, eax
0x18005fef7  jz      short loc_18005FF47
0x18005fef9  call    ?GetPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintDriveDir(void)
0x18005fefe  mov     rcx, rax; Path
0x18005ff01  call    cs:__imp__mkdir
0x18005ff07  test    eax, eax
0x18005ff09  jz      short loc_18005FF5C
0x18005ff0b  lea     rcx, [rbp+1040h+var_1040]; this
0x18005ff0f  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18005ff14  xor     eax, eax
0x18005ff16  mov     rcx, [rbp+1040h+var_20]
0x18005ff1d  xor     rcx, rbp; StackCookie
0x18005ff20  call    __security_check_cookie
0x18005ff25  mov     rbx, [rbp+1040h+arg_8]
0x18005ff2c  mov     rsi, [rbp+1040h+arg_10]
0x18005ff33  mov     rdi, [rbp+1040h+arg_18]
0x18005ff3a  lea     rsp, [rbp+1030h]
0x18005ff41  pop     r15
0x18005ff43  pop     r14
0x18005ff45  pop     rbp
0x18005ff46  retn
0x18005ff47  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005ff4c  mov     edx, 2; AccessMode
0x18005ff51  mov     rcx, rax; FileName
0x18005ff54  call    cs:__imp__access_s
0x18005ff5a  jmp     short loc_18005FF07
0x18005ff5c  lea     rcx, [rbp+1040h+var_1040]; this
0x18005ff60  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005ff65  lea     rcx, [rbp+1040h+var_1040]; this
0x18005ff69  test    rbx, rax
0x18005ff6c  jz      short loc_18005FFBA
0x18005ff6e  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005ff73  lea     rcx, [rbp+1040h+var_1040]; this
0x18005ff77  mov     rbx, rax
0x18005ff7a  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005ff7f  inc     rdi
0x18005ff82  cmp     [rax+rdi], r14b
0x18005ff86  jnz     short loc_18005FF7F
0x18005ff88  lea     rax, ds:2[rdi*2]
0x18005ff90  lea     rcx, [rax+0Fh]
0x18005ff94  cmp     rcx, rax
0x18005ff97  ja      short loc_18005FF9C
0x18005ff99  mov     rcx, r15
0x18005ff9c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005ffa0  mov     rax, rcx
0x18005ffa3  call    _alloca_probe
0x18005ffa8  sub     rsp, rcx
0x18005ffab  mov     rdx, rbx; char *
0x18005ffae  lea     rcx, [rsp+1060h+var_1040]; wchar_t *
0x18005ffb3  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18005ffb8  jmp     short loc_18005FFBF
0x18005ffba  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18005ffbf  mov     rcx, rax; psz
0x18005ffc2  call    cs:__imp_SysAllocString
0x18005ffc8  lea     rcx, [rbp+1040h+var_1040]; this
0x18005ffcc  mov     rbx, rax
0x18005ffcf  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18005ffd4  mov     rax, rbx
0x18005ffd7  jmp     loc_18005FF16
```
