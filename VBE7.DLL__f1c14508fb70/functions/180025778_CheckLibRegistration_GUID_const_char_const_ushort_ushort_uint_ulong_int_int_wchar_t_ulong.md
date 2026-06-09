# _CheckLibRegistration(_GUID const &,char const *,ushort,ushort,uint,ulong,int,int,wchar_t * *,ulong)

- ea: `0x180025778`
- end: `0x180025a7d`
- name: `?_CheckLibRegistration@@YAIAEBU_GUID@@PEBDGGIKHHPEAPEA_WK@Z`
- size: `773`
- prototype: `unsigned int __fastcall(const struct _GUID *, const char *, unsigned __int16, unsigned __int16, unsigned int, unsigned int, int, int, wchar_t **, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180025008`

## callees

- `0x18001653c`
- `0x18001b8b0`
- `0x18001b8c8`
- `0x18001bf20`
- `0x18001bff0`
- `0x180025778`
- `0x180025a84`
- `0x180025cf0`
- `0x18005aa78`
- `0x18005b318`
- `0x18006b7e0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strtoul` at `0x180025880`
- `MSVCR100!strtoul` at `0x180025880`
- `MSVCR100!_access_s` at `0x1800258a0`
- `MSVCR100!_access_s` at `0x1800258a0`
- `KERNEL32!lstrlenA` at `0x1800259cf`
- `KERNEL32!lstrlenA` at `0x180025a39`
- `KERNEL32!lstrlenA` at `0x1800259cf`
- `KERNEL32!lstrlenA` at `0x180025a39`
- `KERNEL32!lstrcpyA` at `0x180025921`
- `KERNEL32!lstrcpyA` at `0x180025921`
- `KERNEL32!lstrcatA` at `0x1800259f9`
- `KERNEL32!lstrcatA` at `0x180025a06`
- `KERNEL32!lstrcatA` at `0x1800259f9`
- `KERNEL32!lstrcatA` at `0x180025a06`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002598d`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002598d`
- `KERNEL32!GetSystemDirectoryA` at `0x18002595b`
- `KERNEL32!GetSystemDirectoryA` at `0x18002595b`
- `USER32!CharPrevA` at `0x1800259e3`
- `USER32!CharPrevA` at `0x1800259e3`
- `USER32!wsprintfA` at `0x180025a2f`
- `USER32!wsprintfA` at `0x180025a2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180025905`
- `OLEAUT32!__imp_SysAllocString` at `0x180025905`

## pseudocode

```c
__int64 __fastcall _CheckLibRegistration(
        const struct _GUID *a1,
        const char *a2,
        unsigned __int16 a3,
        __int16 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        wchar_t **a9,
        unsigned int a10)
{
  unsigned int v13; // ebx
  __int64 v14; // r15
  char *v15; // rdi
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  const CHAR *PrintDriveDir; // rax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // eax
  char v27[2]; // [rsp+30h] [rbp+0h] BYREF
  char *FileName; // [rsp+38h] [rbp+8h] BYREF
  char *String; // [rsp+40h] [rbp+10h] BYREF
  char *EndPtr; // [rsp+48h] [rbp+18h] BYREF
  CHAR v31[32]; // [rsp+50h] [rbp+20h] BYREF
  CHAR String1[2064]; // [rsp+70h] [rbp+40h] BYREF
  OLECHAR psz[2048]; // [rsp+880h] [rbp+850h] BYREF

  *(_WORD *)v27 = a4;
  CFileRep::CFileRep((CFileRep *)v31);
  v13 = 0;
  v14 = -1;
  if ( a8 )
    goto LABEL_21;
  if ( QueryPathOfRegTypeLibAPI(a1, a3, *(unsigned __int16 *)v27, a6, (wchar_t **)&FileName) )
  {
LABEL_18:
    if ( a10 == 3 && (int)VbeSiteUtilsGetFilePath(0, 0, psz, 2048) >= 0 )
      *a9 = SysAllocString(psz);
LABEL_21:
    PrintDriveDir = CFileRep::GetPrintDriveDir((CFileRep *)&Dlg_filerepModuleDir);
    lstrcpyA(String1, PrintDriveDir);
    v23 = _LoadAndRegister(String1, a2, a3, *(unsigned __int16 *)v27, a5);
    if ( v23 == 50078 )
    {
      if ( !a7 )
        goto LABEL_26;
      GetSystemDirectoryA(String1, 0x800u);
      v23 = _LoadAndRegister(String1, a2, a3, *(unsigned __int16 *)v27, a5);
      if ( v23 == 50078 )
      {
        GetWindowsDirectoryA(String1, 0x800u);
        v23 = _LoadAndRegister(String1, a2, a3, *(unsigned __int16 *)v27, a5);
      }
    }
    if ( !v23 )
    {
      if ( a9 )
      {
        v24 = lstrlenA(String1);
        if ( *CharPrevA(String1, &String1[v24]) != 92 )
          lstrcatA(String1, "\\");
        lstrcatA(String1, a2);
        if ( a5 )
        {
          do
            ++v14;
          while ( String1[v14] );
          wsprintfA(&String1[v14], "\\%u", a5);
        }
        v25 = lstrlenA(String1);
        *a9 = AllocBstrLenWfromA(String1, v25);
      }
      goto LABEL_34;
    }
LABEL_26:
    ErrorRemember(v23, a2);
LABEL_34:
    v13 = v23;
    goto LABEL_35;
  }
  v15 = FileName;
  if ( ((unsigned __int64)FileName & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&FileName[2 * v16] );
    v17 = 2 * v16 + 1;
    v18 = v17 + 15;
    if ( v17 + 15 < v17 )
      v18 = 0xFFFFFFFFFFFFFF0LL;
    v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
    v20 = alloca(v19);
    v21 = alloca(v19);
    v15 = strcpyAfromW(v27, (const wchar_t *)FileName);
  }
  if ( a5 && (!(unsigned int)_SplitResID(v15, &String) || strtoul(String, &EndPtr, 10) != a5)
    || !(unsigned int)CFileRep::SetFullPath((CFileRep *)v31, v15)
    || _access_s(v15, 0) )
  {
    SysFreeStringAPI((wchar_t *)FileName);
    goto LABEL_18;
  }
  if ( a9 )
    *a9 = (wchar_t *)FileName;
  else
    SysFreeStringAPI((wchar_t *)FileName);
LABEL_35:
  CFileRep::~CFileRep((CFileRep *)v31);
  return v13;
}

```

## disassembly

```asm
0x180025778  push    rbp
0x18002577a  push    rbx
0x18002577b  push    rsi
0x18002577c  push    rdi
0x18002577d  push    r12
0x18002577f  push    r13
0x180025781  push    r14
0x180025783  push    r15
0x180025785  mov     eax, 1898h
0x18002578a  call    _alloca_probe
0x18002578f  sub     rsp, rax
0x180025792  lea     rbp, [rsp+30h]
0x180025797  mov     rax, cs:__security_cookie
0x18002579e  xor     rax, rbp
0x1800257a1  mov     [rbp+18A0h+var_50], rax
0x1800257a8  mov     rsi, [rbp+18A0h+arg_40]
0x1800257af  mov     rdi, rcx
0x1800257b2  lea     rcx, [rbp+18A0h+var_1880]; this
0x1800257b6  mov     word ptr [rbp+18A0h+var_18A0], r9w
0x1800257bb  movzx   r13d, r8w
0x1800257bf  mov     r12, rdx
0x1800257c2  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x1800257c7  mov     r14d, [rbp+18A0h+arg_20]
0x1800257ce  xor     ebx, ebx
0x1800257d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800257d4  cmp     [rbp+18A0h+arg_38], ebx
0x1800257da  jnz     loc_18002590E
0x1800257e0  mov     r9d, [rbp+18A0h+arg_28]
0x1800257e7  movzx   r8d, word ptr [rbp+18A0h+var_18A0]
0x1800257ec  lea     rax, [rbp+18A0h+FileName]
0x1800257f0  movzx   edx, r13w
0x1800257f4  mov     rcx, rdi
0x1800257f7  mov     qword ptr [rsp+18D0h+var_18B0], rax
0x1800257fc  call    cs:?QueryPathOfRegTypeLibAPI@@3P6AJAEBU_GUID@@GGKPEAPEA_W@ZEA; long (*QueryPathOfRegTypeLibAPI)(_GUID const &,ushort,ushort,ulong,wchar_t * *)
0x180025802  test    eax, eax
0x180025804  jnz     loc_1800258DB
0x18002580a  mov     rdi, [rbp+18A0h+FileName]
0x18002580e  test    rdi, 0FFFFFFFFFFFF0000h
0x180025815  jz      short loc_18002585D
0x180025817  mov     rax, r15
0x18002581a  inc     rax
0x18002581d  cmp     [rdi+rax*2], bx
0x180025821  jnz     short loc_18002581A
0x180025823  lea     rax, ds:1[rax*2]
0x18002582b  lea     rcx, [rax+0Fh]
0x18002582f  cmp     rcx, rax
0x180025832  ja      short loc_18002583E
0x180025834  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002583e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180025842  mov     rax, rcx
0x180025845  call    _alloca_probe
0x18002584a  sub     rsp, rcx
0x18002584d  mov     rdx, rdi; wchar_t *
0x180025850  lea     rcx, [rsp+18D0h+var_18A0]; char *
0x180025855  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x18002585a  mov     rdi, rax
0x18002585d  test    r14d, r14d
0x180025860  jz      short loc_18002588B
0x180025862  lea     rdx, [rbp+18A0h+String]; char **
0x180025866  mov     rcx, rdi; char *
0x180025869  call    ?_SplitResID@@YAHPEADPEAPEAD@Z; _SplitResID(char *,char * *)
0x18002586e  test    eax, eax
0x180025870  jz      short loc_1800258D1
0x180025872  mov     rcx, [rbp+18A0h+String]; String
0x180025876  lea     rdx, [rbp+18A0h+EndPtr]; EndPtr
0x18002587a  mov     r8d, 0Ah; Radix
0x180025880  call    cs:__imp_strtoul
0x180025886  cmp     eax, r14d
0x180025889  jnz     short loc_1800258D1
0x18002588b  lea     rcx, [rbp+18A0h+var_1880]; this
0x18002588f  mov     rdx, rdi; char *
0x180025892  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x180025897  test    eax, eax
0x180025899  jz      short loc_1800258D1
0x18002589b  xor     edx, edx; AccessMode
0x18002589d  mov     rcx, rdi; FileName
0x1800258a0  call    cs:__imp__access_s
0x1800258a6  mov     ecx, ebx
0x1800258a8  test    eax, eax
0x1800258aa  setz    cl
0x1800258ad  test    ecx, ecx
0x1800258af  jz      short loc_1800258D1
0x1800258b1  test    rsi, rsi
0x1800258b4  jz      short loc_1800258C2
0x1800258b6  mov     rax, [rbp+18A0h+FileName]
0x1800258ba  mov     [rsi], rax
0x1800258bd  jmp     loc_180025A4F
0x1800258c2  mov     rcx, [rbp+18A0h+FileName]
0x1800258c6  call    cs:?SysFreeStringAPI@@3P6AXPEA_W@ZEA; void (*SysFreeStringAPI)(wchar_t *)
0x1800258cc  jmp     loc_180025A4F
0x1800258d1  mov     rcx, [rbp+18A0h+FileName]
0x1800258d5  call    cs:?SysFreeStringAPI@@3P6AXPEA_W@ZEA; void (*SysFreeStringAPI)(wchar_t *)
0x1800258db  cmp     [rbp+18A0h+arg_48], 3
0x1800258e2  jnz     short loc_18002590E
0x1800258e4  lea     r8, [rbp+18A0h+psz]
0x1800258eb  mov     r9d, 800h
0x1800258f1  xor     edx, edx
0x1800258f3  xor     ecx, ecx
0x1800258f5  call    ?VbeSiteUtilsGetFilePath@@YAJW4MSIEntries@@KPEA_WH@Z; VbeSiteUtilsGetFilePath(MSIEntries,ulong,wchar_t *,int)
0x1800258fa  test    eax, eax
0x1800258fc  js      short loc_18002590E
0x1800258fe  lea     rcx, [rbp+18A0h+psz]; psz
0x180025905  call    cs:__imp_SysAllocString
0x18002590b  mov     [rsi], rax
0x18002590e  lea     rcx, ?Dlg_filerepModuleDir@@3VCFileRep@@A; this
0x180025915  call    ?GetPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintDriveDir(void)
0x18002591a  lea     rcx, [rbp+18A0h+String1]; lpString1
0x18002591e  mov     rdx, rax; lpString2
0x180025921  call    cs:__imp_lstrcpyA
0x180025927  movzx   r9d, word ptr [rbp+18A0h+var_18A0]; unsigned __int16
0x18002592c  lea     rcx, [rbp+18A0h+String1]; char *
0x180025930  movzx   r8d, r13w; unsigned __int16
0x180025934  mov     rdx, r12; char *
0x180025937  mov     [rsp+18D0h+var_18B0], r14d; unsigned int
0x18002593c  call    ?_LoadAndRegister@@YAIPEBD0GGI@Z; _LoadAndRegister(char const *,char const *,ushort,ushort,uint)
0x180025941  mov     edi, eax
0x180025943  cmp     eax, 0C39Eh
0x180025948  jnz     short loc_1800259AF
0x18002594a  cmp     [rbp+18A0h+arg_30], ebx
0x180025950  jz      short loc_1800259B3
0x180025952  lea     rcx, [rbp+18A0h+String1]; lpBuffer
0x180025956  mov     edx, 800h; uSize
0x18002595b  call    cs:__imp_GetSystemDirectoryA
0x180025961  movzx   r9d, word ptr [rbp+18A0h+var_18A0]; unsigned __int16
0x180025966  lea     rcx, [rbp+18A0h+String1]; char *
0x18002596a  movzx   r8d, r13w; unsigned __int16
0x18002596e  mov     rdx, r12; char *
0x180025971  mov     [rsp+18D0h+var_18B0], r14d; unsigned int
0x180025976  call    ?_LoadAndRegister@@YAIPEBD0GGI@Z; _LoadAndRegister(char const *,char const *,ushort,ushort,uint)
0x18002597b  mov     edi, eax
0x18002597d  cmp     eax, 0C39Eh
0x180025982  jnz     short loc_1800259AF
0x180025984  lea     rcx, [rbp+18A0h+String1]; lpBuffer
0x180025988  mov     edx, 800h; uSize
0x18002598d  call    cs:__imp_GetWindowsDirectoryA
0x180025993  movzx   r9d, word ptr [rbp+18A0h+var_18A0]; unsigned __int16
0x180025998  lea     rcx, [rbp+18A0h+String1]; char *
0x18002599c  movzx   r8d, r13w; unsigned __int16
0x1800259a0  mov     rdx, r12; char *
0x1800259a3  mov     [rsp+18D0h+var_18B0], r14d; unsigned int
0x1800259a8  call    ?_LoadAndRegister@@YAIPEBD0GGI@Z; _LoadAndRegister(char const *,char const *,ushort,ushort,uint)
0x1800259ad  mov     edi, eax
0x1800259af  test    edi, edi
0x1800259b1  jz      short loc_1800259C2
0x1800259b3  mov     rdx, r12; char *
0x1800259b6  mov     ecx, edi; unsigned int
0x1800259b8  call    ?ErrorRemember@@YAIIPEBD@Z; ErrorRemember(uint,char const *)
0x1800259bd  jmp     loc_180025A4D
0x1800259c2  test    rsi, rsi
0x1800259c5  jz      loc_180025A4D
0x1800259cb  lea     rcx, [rbp+18A0h+String1]; lpString
0x1800259cf  call    cs:__imp_lstrlenA
0x1800259d5  lea     rdx, [rbp+18A0h+String1]
0x1800259d9  movsxd  rcx, eax
0x1800259dc  add     rdx, rcx; lpszCurrent
0x1800259df  lea     rcx, [rbp+18A0h+String1]; lpszStart
0x1800259e3  call    cs:__imp_CharPrevA
0x1800259e9  cmp     byte ptr [rax], 5Ch ; '\'
0x1800259ec  jz      short loc_1800259FF
0x1800259ee  lea     rdx, asc_1803A109C; "\\"
0x1800259f5  lea     rcx, [rbp+18A0h+String1]; lpString1
0x1800259f9  call    cs:__imp_lstrcatA
0x1800259ff  lea     rcx, [rbp+18A0h+String1]; lpString1
0x180025a03  mov     rdx, r12; lpString2
0x180025a06  call    cs:__imp_lstrcatA
0x180025a0c  test    r14d, r14d
0x180025a0f  jz      short loc_180025A35
0x180025a11  lea     rax, [rbp+18A0h+String1]
0x180025a15  inc     r15
0x180025a18  cmp     [rax+r15], bl
0x180025a1c  jnz     short loc_180025A15
0x180025a1e  lea     rcx, [rbp+18A0h+String1]
0x180025a22  lea     rdx, aU_1; "\\%u"
0x180025a29  mov     r8d, r14d
0x180025a2c  add     rcx, r15; LPSTR
0x180025a2f  call    cs:__imp_wsprintfA
0x180025a35  lea     rcx, [rbp+18A0h+String1]; lpString
0x180025a39  call    cs:__imp_lstrlenA
0x180025a3f  lea     rcx, [rbp+18A0h+String1]; char *
0x180025a43  mov     edx, eax; unsigned int
0x180025a45  call    ?AllocBstrLenWfromA@@YAPEA_WPEBDI@Z; AllocBstrLenWfromA(char const *,uint)
0x180025a4a  mov     [rsi], rax
0x180025a4d  mov     ebx, edi
0x180025a4f  lea     rcx, [rbp+18A0h+var_1880]; this
0x180025a53  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x180025a58  mov     eax, ebx
0x180025a5a  mov     rcx, [rbp+18A0h+var_50]
0x180025a61  xor     rcx, rbp; StackCookie
0x180025a64  call    __security_check_cookie
0x180025a69  lea     rsp, [rbp+1868h]
0x180025a70  pop     r15
0x180025a72  pop     r14
0x180025a74  pop     r13
0x180025a76  pop     r12
0x180025a78  pop     rdi
0x180025a79  pop     rsi
0x180025a7a  pop     rbx
0x180025a7b  pop     rbp
0x180025a7c  retn
```
