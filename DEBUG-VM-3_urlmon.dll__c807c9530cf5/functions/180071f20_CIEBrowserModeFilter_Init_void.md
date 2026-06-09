# CIEBrowserModeFilter::Init(void)

- ea: `0x180071f20`
- end: `0x1800721fa`
- name: `?Init@CIEBrowserModeFilter@@EEAAJXZ`
- size: `730`
- prototype: `__int64 __fastcall(CIEBrowserModeFilter *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071c7c`

## callees

- `0x180071f20`
- `0x180072200`
- `0x18007225c`
- `0x180092154`
- `0x1800a5a88`
- `0x1800a5a94`
- `0x1800aad74`
- `0x1800ac5f4`
- `0x1800ada48`
- `0x1800adb2c`
- `0x1800adc18`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18007202c`
- `msvcrt!wcscat_s` at `0x180072046`
- `msvcrt!wcscat_s` at `0x18007202c`
- `msvcrt!wcscat_s` at `0x180072046`
- `msvcrt!wcscpy_s` at `0x18007200e`
- `msvcrt!wcscpy_s` at `0x18007200e`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18007209d`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18007209d`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180071fbc`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180071fbc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f57`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f64`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f73`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800720be`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800720cd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180072100`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007215a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180072169`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f57`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f64`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180071f73`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800720be`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800720cd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180072100`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007215a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180072169`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180072019`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180072019`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180071fc9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180072061`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180071fc9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180072061`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007219e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007219e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800721ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800721ae`

## pseudocode

```c
__int64 __fastcall CIEBrowserModeFilter::Init(CIEBrowserModeFilter *this)
{
  unsigned int NewVersionXML; // ebx
  char Bool; // bl
  bool v4; // si
  unsigned __int16 *v5; // rbx
  const wchar_t *String; // rax
  wchar_t *p_Destination; // r8
  bool v8; // si
  bool v9; // zf
  signed int LastError; // eax
  unsigned int v12[4]; // [rsp+20h] [rbp-258h] BYREF
  wchar_t Destination; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v14[558]; // [rsp+32h] [rbp-246h] BYREF

  NewVersionXML = 0;
  if ( *((_BYTE *)this + 32) )
    return NewVersionXML;
  Bool = IEConfiguration_GetBool(268435519);
  v4 = ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481))
    && !Bool;
  if ( *((_DWORD *)this + 14) )
    goto LABEL_12;
  if ( v4 )
  {
    v5 = (unsigned __int16 *)operator new[](0x230u);
    *v5 = 0;
    IsoPrefixUserQualifierToName(v5, 0x118u, **((const unsigned __int16 ***)this + 66));
    *((_QWORD *)this + 6) = CreateMutexW(0, 0, v5);
    operator delete[](v5);
    goto LABEL_14;
  }
  if ( !Bool )
  {
LABEL_12:
    p_Destination = (wchar_t *)**((_QWORD **)this + 66);
  }
  else
  {
    Destination = 0;
    memset_0(v14, 0, sizeof(v14));
    wcscpy_s(&Destination, 0x118u, L"Local\\");
    String = (const wchar_t *)IEConfiguration_GetString(268435499);
    wcscat_s(&Destination, 0x118u, String);
    wcscat_s(&Destination, 0x118u, **((const wchar_t ***)this + 66));
    p_Destination = &Destination;
  }
  *((_QWORD *)this + 6) = CreateMutexW(0, 0, p_Destination);
LABEL_14:
  if ( *((_QWORD *)this + 6) )
  {
    if ( v4 && !*((_DWORD *)this + 14) && GetLastError() != 183 )
      SetWindowsHandleAccess(*((void **)this + 6), 0x114Fu, 0x801F0003);
    v12[0] = CIEBrowserModeFilter::lock(this);
    NewVersionXML = v12[0];
    if ( v12[0] )
      goto LABEL_44;
    if ( (unsigned __int8)IEConfiguration_GetBool(536870925) && !(unsigned __int8)IEConfiguration_GetBool(268435500) )
      goto LABEL_40;
    v8 = CIEBrowserModeFilter::MustUpgradeCacheContainers(this) || !CIEBrowserModeFilter::isCacheVersionCurrent(this);
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) || v8 )
    {
      NewVersionXML = CIEBrowserModeFilter::initializeUrlCache(this);
      v12[0] = NewVersionXML;
    }
    if ( NewVersionXML )
      goto LABEL_43;
    if ( !IsValidContextToUpdateFilter() || !v8 )
      goto LABEL_40;
    if ( (unsigned __int8)CIEBrowserModeFilter::CallElevationBrokerIfAppropriate(this, v12, 6) )
    {
      NewVersionXML = v12[0];
    }
    else
    {
      NewVersionXML = CIEBrowserModeFilter::loadNewVersionXML(this);
      if ( NewVersionXML == -2147024894
        && (unsigned __int8)IEConfiguration_GetBool(268435519)
        && (unsigned __int8)IEConfiguration_GetBool(536870923) )
      {
        NewVersionXML = 0;
      }
    }
    v9 = NewVersionXML == 0;
    if ( (NewVersionXML & 0x80000000) == 0 )
    {
LABEL_40:
      NewVersionXML = CIEBrowserModeFilter::readCacheVersionFromRegistry(
                        this,
                        (unsigned int *)this + 9,
                        (unsigned int *)this + 10);
      v9 = NewVersionXML == 0;
    }
    if ( v9 )
      *((_BYTE *)this + 32) = 1;
LABEL_43:
    ReleaseMutex(*((HANDLE *)this + 6));
LABEL_44:
    if ( !*((_BYTE *)this + 32) )
    {
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = 0;
    }
    return NewVersionXML;
  }
  LastError = GetLastError();
  NewVersionXML = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return NewVersionXML;
}

```

## disassembly

```asm
0x180071f20  mov     [rsp+arg_8], rbx
0x180071f25  mov     [rsp+arg_10], rsi
0x180071f2a  push    rdi
0x180071f2b  sub     rsp, 270h
0x180071f32  mov     rax, cs:__security_cookie
0x180071f39  xor     rax, rsp
0x180071f3c  mov     [rsp+278h+var_18], rax
0x180071f44  xor     ebx, ebx
0x180071f46  mov     rdi, rcx
0x180071f49  cmp     [rcx+20h], bl
0x180071f4c  jnz     loc_1800721D3
0x180071f52  mov     ecx, 1000003Fh
0x180071f57  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180071f5d  mov     ecx, 1000001Ah
0x180071f62  mov     bl, al
0x180071f64  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180071f6a  test    al, al
0x180071f6c  jnz     short loc_180071F7D
0x180071f6e  mov     ecx, 10000019h
0x180071f73  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180071f79  test    al, al
0x180071f7b  jz      short loc_180071F86
0x180071f7d  test    bl, bl
0x180071f7f  jnz     short loc_180071F86
0x180071f81  mov     sil, 1
0x180071f84  jmp     short loc_180071F89
0x180071f86  xor     sil, sil
0x180071f89  cmp     dword ptr [rdi+38h], 0
0x180071f8d  jnz     loc_180072053
0x180071f93  test    sil, sil
0x180071f96  jz      short loc_180071FE0
0x180071f98  mov     ecx, 230h; unsigned __int64
0x180071f9d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180071fa2  mov     rbx, rax
0x180071fa5  mov     edx, 118h
0x180071faa  xor     eax, eax
0x180071fac  mov     rcx, rbx
0x180071faf  mov     [rbx], ax
0x180071fb2  mov     r8, [rdi+210h]
0x180071fb9  mov     r8, [r8]
0x180071fbc  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x180071fc2  mov     r8, rbx; lpName
0x180071fc5  xor     edx, edx; bInitialOwner
0x180071fc7  xor     ecx, ecx; lpMutexAttributes
0x180071fc9  call    cs:__imp_CreateMutexW
0x180071fcf  mov     rcx, rbx; void *
0x180071fd2  mov     [rdi+30h], rax
0x180071fd6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180071fdb  jmp     loc_18007206B
0x180071fe0  test    bl, bl
0x180071fe2  jz      short loc_180072053
0x180071fe4  xor     eax, eax
0x180071fe6  lea     rcx, [rsp+278h+var_246]; void *
0x180071feb  xor     edx, edx; Val
0x180071fed  mov     [rsp+278h+Destination], ax
0x180071ff2  mov     r8d, 22Eh; Size
0x180071ff8  call    memset_0
0x180071ffd  lea     r8, aLocal_0; "Local\\"
0x180072004  mov     edx, 118h; SizeInWords
0x180072009  lea     rcx, [rsp+278h+Destination]; Destination
0x18007200e  call    cs:__imp_wcscpy_s
0x180072014  mov     ecx, 1000002Bh
0x180072019  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18007201f  mov     edx, 118h; SizeInWords
0x180072024  lea     rcx, [rsp+278h+Destination]; Destination
0x180072029  mov     r8, rax; Source
0x18007202c  call    cs:__imp_wcscat_s
0x180072032  mov     r8, [rdi+210h]
0x180072039  lea     rcx, [rsp+278h+Destination]; Destination
0x18007203e  mov     edx, 118h; SizeInWords
0x180072043  mov     r8, [r8]; Source
0x180072046  call    cs:__imp_wcscat_s
0x18007204c  lea     r8, [rsp+278h+Destination]
0x180072051  jmp     short loc_18007205D
0x180072053  mov     r8, [rdi+210h]
0x18007205a  mov     r8, [r8]; lpName
0x18007205d  xor     edx, edx; bInitialOwner
0x18007205f  xor     ecx, ecx; lpMutexAttributes
0x180072061  call    cs:__imp_CreateMutexW
0x180072067  mov     [rdi+30h], rax
0x18007206b  cmp     qword ptr [rdi+30h], 0
0x180072070  jz      loc_1800721BE
0x180072076  test    sil, sil
0x180072079  jz      short loc_1800720A3
0x18007207b  cmp     dword ptr [rdi+38h], 0
0x18007207f  jnz     short loc_1800720A3
0x180072081  call    cs:__imp_GetLastError
0x180072087  cmp     eax, 0B7h
0x18007208c  jz      short loc_1800720A3
0x18007208e  mov     rcx, [rdi+30h]
0x180072092  mov     edx, 114Fh
0x180072097  mov     r8d, 801F0003h
0x18007209d  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x1800720a3  mov     rcx, rdi; this
0x1800720a6  call    ?lock@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::lock(void)
0x1800720ab  mov     [rsp+278h+var_258], eax
0x1800720af  mov     ebx, eax
0x1800720b1  test    eax, eax
0x1800720b3  jnz     loc_1800721A4
0x1800720b9  mov     ecx, 2000000Dh
0x1800720be  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800720c4  test    al, al
0x1800720c6  jz      short loc_1800720DB
0x1800720c8  mov     ecx, 1000002Ch
0x1800720cd  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800720d3  test    al, al
0x1800720d5  jz      loc_180072180
0x1800720db  mov     rcx, rdi; this
0x1800720de  call    ?MustUpgradeCacheContainers@CIEBrowserModeFilter@@AEAA_NXZ; CIEBrowserModeFilter::MustUpgradeCacheContainers(void)
0x1800720e3  test    al, al
0x1800720e5  jnz     short loc_1800720F8
0x1800720e7  mov     rcx, rdi; this
0x1800720ea  call    ?isCacheVersionCurrent@CIEBrowserModeFilter@@AEAA_NXZ; CIEBrowserModeFilter::isCacheVersionCurrent(void)
0x1800720ef  test    al, al
0x1800720f1  jz      short loc_1800720F8
0x1800720f3  xor     sil, sil
0x1800720f6  jmp     short loc_1800720FB
0x1800720f8  mov     sil, 1
0x1800720fb  mov     ecx, 20000001h
0x180072100  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180072106  test    al, al
0x180072108  jz      short loc_18007210F
0x18007210a  test    sil, sil
0x18007210d  jz      short loc_18007211D
0x18007210f  mov     rcx, rdi; this
0x180072112  call    ?initializeUrlCache@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::initializeUrlCache(void)
0x180072117  mov     ebx, eax
0x180072119  mov     [rsp+278h+var_258], eax
0x18007211d  test    ebx, ebx
0x18007211f  jnz     short loc_18007219A
0x180072121  call    ?IsValidContextToUpdateFilter@@YA_NXZ; IsValidContextToUpdateFilter(void)
0x180072126  test    al, al
0x180072128  jz      short loc_180072180
0x18007212a  test    sil, sil
0x18007212d  jz      short loc_180072180
0x18007212f  lea     r8d, [rbx+6]
0x180072133  mov     rcx, rdi
0x180072136  lea     rdx, [rsp+278h+var_258]
0x18007213b  call    ?CallElevationBrokerIfAppropriate@CIEBrowserModeFilter@@AEAA_NPEAJW4_BROWSERBROKER_CVLISTACTION@@@Z; CIEBrowserModeFilter::CallElevationBrokerIfAppropriate(long *,_BROWSERBROKER_CVLISTACTION)
0x180072140  test    al, al
0x180072142  jnz     short loc_180072178
0x180072144  mov     rcx, rdi; this
0x180072147  call    ?loadNewVersionXML@CIEBrowserModeFilter@@AEAAJXZ; CIEBrowserModeFilter::loadNewVersionXML(void)
0x18007214c  mov     ebx, eax
0x18007214e  cmp     eax, 80070002h
0x180072153  jnz     short loc_18007217C
0x180072155  mov     ecx, 1000003Fh
0x18007215a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180072160  test    al, al
0x180072162  jz      short loc_18007217C
0x180072164  mov     ecx, 2000000Bh
0x180072169  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007216f  xor     ecx, ecx
0x180072171  test    al, al
0x180072173  cmovnz  ebx, ecx
0x180072176  jmp     short loc_18007217C
0x180072178  mov     ebx, [rsp+278h+var_258]
0x18007217c  test    ebx, ebx
0x18007217e  js      short loc_180072194
0x180072180  lea     r8, [rdi+28h]; unsigned int *
0x180072184  mov     rcx, rdi; this
0x180072187  lea     rdx, [rdi+24h]; unsigned int *
0x18007218b  call    ?readCacheVersionFromRegistry@CIEBrowserModeFilter@@AEAAJPEAK0@Z; CIEBrowserModeFilter::readCacheVersionFromRegistry(ulong *,ulong *)
0x180072190  mov     ebx, eax
0x180072192  test    eax, eax
0x180072194  jnz     short loc_18007219A
0x180072196  mov     byte ptr [rdi+20h], 1
0x18007219a  mov     rcx, [rdi+30h]; hMutex
0x18007219e  call    cs:__imp_ReleaseMutex
0x1800721a4  cmp     byte ptr [rdi+20h], 0
0x1800721a8  jnz     short loc_1800721D3
0x1800721aa  mov     rcx, [rdi+30h]; hObject
0x1800721ae  call    cs:__imp_CloseHandle
0x1800721b4  mov     qword ptr [rdi+30h], 0
0x1800721bc  jmp     short loc_1800721D3
0x1800721be  call    cs:__imp_GetLastError
0x1800721c4  mov     ebx, eax
0x1800721c6  test    eax, eax
0x1800721c8  jle     short loc_1800721D3
0x1800721ca  movzx   ebx, ax
0x1800721cd  or      ebx, 80070000h
0x1800721d3  mov     eax, ebx
0x1800721d5  mov     rcx, [rsp+278h+var_18]
0x1800721dd  xor     rcx, rsp; StackCookie
0x1800721e0  call    __security_check_cookie
0x1800721e5  lea     r11, [rsp+278h+var_8]
0x1800721ed  mov     rbx, [r11+18h]
0x1800721f1  mov     rsi, [r11+20h]
0x1800721f5  mov     rsp, r11
0x1800721f8  pop     rdi
0x1800721f9  retn
```
