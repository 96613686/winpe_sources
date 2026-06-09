# StatePaths::IsPackageUnregisteredForRoaming(ushort const *,bool *)

- ea: `0x18006350c`
- end: `0x180063817`
- name: `?IsPackageUnregisteredForRoaming@StatePaths@@YAJPEBGPEA_N@Z`
- size: `779`
- prototype: `__int64 __fastcall(StatePaths *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012bb38`

## callees

- `0x18006350c`
- `0x180063820`
- `0x18007689c`
- `0x180076900`
- `0x180087238`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063777`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800635c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006364b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800637eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800635c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006364b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800637eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006358d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006358d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800635fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800635fa`

## string_xrefs

- `0x18006355e`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x180063621`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x1800636dd`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18006371c`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x1800637a1`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x180063604`: `RegOpenKeyEx %ws`
- `0x1800636ce`: `StringCchCopy`
- `0x180063597`: `RegOpenCurrentUser %ws`

## pseudocode

```c
__int64 __fastcall StatePaths::IsPackageUnregisteredForRoaming(StatePaths *this, unsigned __int16 *a2, bool *a3)
{
  unsigned int v5; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // r8
  __int64 v13; // rax
  WCHAR *v14; // rcx
  unsigned int ValueW; // eax
  const char *pvData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR SubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[268]; // [rsp+64h] [rbp-9Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  if ( !*(_WORD *)this )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x364,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)0x80070057LL,
      (int)"IsPackageUnregisteredForRoaming: bad packageFamilyName",
      pvData);
    return v5;
  }
  *(_BYTE *)a2 = 0;
  hKey = 0;
  phkResult = 0;
  v7 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x36A,
           (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
           (const char *)v7,
           (unsigned int)"RegOpenCurrentUser %ws",
           (const char *)this);
LABEL_8:
    v5 = v8;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v5;
  }
  hKey = 0;
  v9 = RegOpenKeyExW(phkResult, L"Software\\Classes\\Local Settings", 0, 0xF003Fu, &hKey);
  if ( v9 )
  {
    v8 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x36D,
           (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
           (const char *)v9,
           (unsigned int)"RegOpenKeyEx %ws",
           (const char *)this);
    goto LABEL_8;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  *(_DWORD *)SubKey = 0;
  memset_0(v22, 0, 0x100u);
  v10 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData\\";
  v11 = 130;
  v12 = SubKey;
  v13 = 2147483646;
  do
  {
    if ( !v13 )
      break;
    if ( !*v10 )
      break;
    *v12++ = *v10++;
    --v13;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  v5 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x371,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)v5,
      (int)"StringCchCopy",
      pvData);
    goto LABEL_25;
  }
  v5 = StringCchCatW(SubKey, 0x82u, (const unsigned __int16 *)this);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)v5,
      (int)"StringCchCat %ws",
      (const char *)this);
    goto LABEL_25;
  }
  v20 = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, SubKey, L"UnregisteredForProfileRoaming", 0x10u, 0, &v20, &pcbData);
  if ( ValueW == 1168 || ValueW - 2 <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    if ( ValueW )
    {
      v5 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x382,
             (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
             (const char *)ValueW,
             (unsigned int)"RegGetValueW %ws",
             (const char *)SubKey);
      goto LABEL_25;
    }
    *(_BYTE *)a2 = 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18006350c  mov     [rsp-8+arg_10], rbx
0x180063511  mov     [rsp-8+arg_18], rsi
0x180063516  push    rbp
0x180063517  push    rdi
0x180063518  push    r14
0x18006351a  lea     rbp, [rsp-80h]
0x18006351f  sub     rsp, 180h
0x180063526  mov     rax, cs:__security_cookie
0x18006352d  xor     rax, rsp
0x180063530  mov     [rbp+90h+var_20], rax
0x180063534  xor     r14d, r14d
0x180063537  mov     rsi, rdx
0x18006353a  mov     rdi, rcx
0x18006353d  cmp     [rcx], r14w
0x180063541  jnz     short loc_180063576
0x180063543  mov     rcx, [rbp+98h]; this
0x18006354a  lea     rax, aIspackageunreg; "IsPackageUnregisteredForRoaming: bad pa"...
0x180063551  mov     ebx, 80070057h
0x180063556  mov     [rsp+190h+var_170], rax; int
0x18006355b  mov     r9d, ebx; char *
0x18006355e  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x180063565  mov     edx, 364h; void *
0x18006356a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006356f  mov     eax, ebx
0x180063571  jmp     loc_1800637F3
0x180063576  mov     [rdx], r14b
0x180063579  mov     ecx, 0F003Fh; samDesired
0x18006357e  lea     rdx, [rsp+190h+phkResult]; phkResult
0x180063583  mov     [rsp+190h+hKey], r14
0x180063588  mov     [rsp+190h+phkResult], r14
0x18006358d  call    cs:__imp_RegOpenCurrentUser
0x180063593  test    eax, eax
0x180063595  jz      short loc_1800635AF
0x180063597  lea     rdx, aRegopencurrent; "RegOpenCurrentUser %ws"
0x18006359e  mov     [rsp+190h+pvData], rdi
0x1800635a3  mov     [rsp+190h+var_170], rdx
0x1800635a8  mov     edx, 36Ah
0x1800635ad  jmp     short loc_18006361A
0x1800635af  mov     rbx, [rsp+190h+hKey]
0x1800635b4  test    rbx, rbx
0x1800635b7  jz      short loc_1800635D6
0x1800635b9  lea     rcx, [rsp+190h+var_138]; this
0x1800635be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800635c3  mov     rcx, rbx; hKey
0x1800635c6  call    cs:__imp_RegCloseKey
0x1800635cc  lea     rcx, [rsp+190h+var_138]; this
0x1800635d1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800635d6  mov     rcx, [rsp+190h+phkResult]; hKey
0x1800635db  lea     rax, [rsp+190h+hKey]
0x1800635e0  mov     r9d, 0F003Fh; samDesired
0x1800635e6  mov     [rsp+190h+var_170], rax; phkResult
0x1800635eb  xor     r8d, r8d; ulOptions
0x1800635ee  mov     [rsp+190h+hKey], r14
0x1800635f3  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\Local Settings"
0x1800635fa  call    cs:__imp_RegOpenKeyExW
0x180063600  test    eax, eax
0x180063602  jz      short loc_180063641
0x180063604  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx %ws"
0x18006360b  mov     [rsp+190h+pvData], rdi; char *
0x180063610  mov     [rsp+190h+var_170], rdx; unsigned int
0x180063615  mov     edx, 36Dh; void *
0x18006361a  mov     rcx, [rbp+98h]; this
0x180063621  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x180063628  mov     r9d, eax; char *
0x18006362b  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180063630  lea     rcx, [rsp+190h+phkResult]
0x180063635  mov     ebx, eax
0x180063637  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006363c  jmp     loc_1800637C3
0x180063641  mov     rcx, [rsp+190h+phkResult]; hKey
0x180063646  test    rcx, rcx
0x180063649  jz      short loc_180063651
0x18006364b  call    cs:__imp_RegCloseKey
0x180063651  xor     edx, edx; Val
0x180063653  mov     dword ptr [rsp+190h+SubKey], r14d
0x180063658  mov     r8d, 100h; Size
0x18006365e  lea     rcx, [rsp+190h+var_12C]; void *
0x180063663  call    memset_0
0x180063668  mov     r10d, 82h
0x18006366e  lea     rcx, aSoftwareMicros_28; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180063675  mov     edx, r10d
0x180063678  lea     r8, [rsp+190h+SubKey]
0x18006367d  mov     eax, 7FFFFFFEh
0x180063682  test    rax, rax
0x180063685  jz      short loc_1800636A6
0x180063687  movzx   r9d, word ptr [rcx]
0x18006368b  test    r9w, r9w
0x18006368f  jz      short loc_1800636A6
0x180063691  mov     [r8], r9w
0x180063695  add     rcx, 2
0x180063699  add     r8, 2
0x18006369d  dec     rax
0x1800636a0  sub     rdx, 1
0x1800636a4  jnz     short loc_180063682
0x1800636a6  mov     rax, rdx
0x1800636a9  lea     rcx, [r8-2]
0x1800636ad  neg     rax
0x1800636b0  sbb     ebx, ebx
0x1800636b2  not     ebx
0x1800636b4  and     ebx, 8007007Ah
0x1800636ba  test    rdx, rdx
0x1800636bd  cmovnz  rcx, r8
0x1800636c1  mov     [rcx], r14w
0x1800636c5  jnz     short loc_1800636F3
0x1800636c7  mov     rcx, [rbp+98h]; this
0x1800636ce  lea     rax, aStringcchcopy; "StringCchCopy"
0x1800636d5  mov     r9d, ebx; char *
0x1800636d8  mov     [rsp+190h+var_170], rax; int
0x1800636dd  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x1800636e4  mov     edx, 371h; void *
0x1800636e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800636ee  jmp     loc_1800637C3
0x1800636f3  mov     r8, rdi; unsigned __int16 *
0x1800636f6  lea     rcx, [rsp+190h+SubKey]; unsigned __int16 *
0x1800636fb  mov     rdx, r10; unsigned __int64
0x1800636fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180063703  mov     ebx, eax
0x180063705  test    eax, eax
0x180063707  jns     short loc_18006373A
0x180063709  mov     rcx, [rbp+98h]; this
0x180063710  lea     rax, aStringcchcatWs; "StringCchCat %ws"
0x180063717  mov     [rsp+190h+pvData], rdi; char *
0x18006371c  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x180063723  mov     r9d, ebx; char *
0x180063726  mov     [rsp+190h+var_170], rax; int
0x18006372b  mov     edx, 373h; void *
0x180063730  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180063735  jmp     loc_1800637C3
0x18006373a  mov     rcx, [rsp+190h+hKey]; hkey
0x18006373f  lea     rax, [rsp+190h+var_140]
0x180063744  mov     [rsp+190h+pcbData], rax; pcbData
0x180063749  lea     r8, aUnregisteredfo; "UnregisteredForProfileRoaming"
0x180063750  lea     rax, [rsp+190h+var_13C]
0x180063755  mov     [rsp+190h+var_13C], r14d
0x18006375a  mov     [rsp+190h+pvData], rax; pvData
0x18006375f  lea     rdx, [rsp+190h+SubKey]; lpSubKey
0x180063764  mov     r9d, 10h; dwFlags
0x18006376a  mov     [rsp+190h+var_170], r14; pdwType
0x18006376f  mov     [rsp+190h+var_140], 4
0x180063777  call    cs:__imp_RegGetValueW
0x18006377d  cmp     eax, 490h
0x180063782  jz      short loc_1800637E1
0x180063784  lea     ecx, [rax-2]
0x180063787  cmp     ecx, 1
0x18006378a  jbe     short loc_1800637E1
0x18006378c  test    eax, eax
0x18006378e  jz      short loc_1800637D2
0x180063790  mov     rcx, [rbp+98h]; this
0x180063797  lea     rdx, [rsp+190h+SubKey]
0x18006379c  mov     [rsp+190h+pvData], rdx; char *
0x1800637a1  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x1800637a8  lea     rdx, aReggetvaluewWs; "RegGetValueW %ws"
0x1800637af  mov     r9d, eax; char *
0x1800637b2  mov     [rsp+190h+var_170], rdx; unsigned int
0x1800637b7  mov     edx, 382h; void *
0x1800637bc  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800637c1  mov     ebx, eax
0x1800637c3  lea     rcx, [rsp+190h+hKey]
0x1800637c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800637cd  jmp     loc_18006356F
0x1800637d2  lea     rcx, [rsp+190h+hKey]
0x1800637d7  mov     byte ptr [rsi], 1
0x1800637da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800637df  jmp     short loc_1800637F1
0x1800637e1  mov     rcx, [rsp+190h+hKey]; hKey
0x1800637e6  test    rcx, rcx
0x1800637e9  jz      short loc_1800637F1
0x1800637eb  call    cs:__imp_RegCloseKey
0x1800637f1  xor     eax, eax
0x1800637f3  mov     rcx, [rbp+90h+var_20]
0x1800637f7  xor     rcx, rsp; StackCookie
0x1800637fa  call    __security_check_cookie
0x1800637ff  lea     r11, [rsp+190h+var_10]
0x180063807  mov     rbx, [r11+30h]
0x18006380b  mov     rsi, [r11+38h]
0x18006380f  mov     rsp, r11
0x180063812  pop     r14
0x180063814  pop     rdi
0x180063815  pop     rbp
0x180063816  retn
```
