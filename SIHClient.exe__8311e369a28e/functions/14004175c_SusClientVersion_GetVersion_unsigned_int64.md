# SusClientVersion::GetVersion(unsigned __int64 *)

- ea: `0x14004175c`
- end: `0x140041ab7`
- name: `?GetVersion@SusClientVersion@@SAJPEA_K@Z`
- size: `859`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140038354`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x14000d7e4`
- `0x1400154b4`
- `0x14003a864`
- `0x140040ef8`
- `0x14004175c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14004181b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140041848`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140041879`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400418ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400418ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14004191b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14004181b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140041848`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140041879`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400418ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400418ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14004191b`

## string_xrefs

- `0x1400417dc`: `wuapicore.dll`
- `0x14004188c`: `wuapicore.dll`
- `0x140041a41`: `wuapicore.dll`
- `0x1400417ee`: `wuauengcore.dll`
- `0x1400418c8`: `wuauengcore.dll`
- `0x14004179b`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`
- `0x1400419a6`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`
- `0x140041a6c`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SusClientVersion::GetVersion(unsigned __int64 *a1)
{
  int FileVersion; // ebx
  int v2; // edi
  unsigned __int64 v3; // rax
  unsigned int v4; // r12d
  wchar_t **v5; // rsi
  const WCHAR *v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  const WCHAR *v11; // r8
  int v12; // eax
  const WCHAR *v13; // r8
  wchar_t *v14; // r14
  int v15; // eax
  unsigned __int64 v16; // rax
  int lpString2; // [rsp+20h] [rbp-60h]
  int lpString2a; // [rsp+20h] [rbp-60h]
  unsigned __int64 v21; // [rsp+68h] [rbp-18h] BYREF
  void *lpMem; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a1 )
  {
    FileVersion = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
      (const char *)0x80004003LL,
      lpString2);
    return (unsigned int)FileVersion;
  }
  v21 = 0;
  v2 = 0;
  lpMem = 0;
  v3 = SusClientVersion::m_CachedVersion;
  *a1 = SusClientVersion::m_CachedVersion;
  if ( v3 )
  {
LABEL_39:
    FileVersion = 0;
    goto LABEL_40;
  }
  v4 = 0;
  v5 = (wchar_t **)off_14006F4D0;
  do
  {
    v6 = *v5;
    if ( *v5 == L"wuapicore.dll" )
      goto LABEL_14;
    if ( v6 )
    {
      v7 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuapicore.dll", -1);
      v6 = *v5;
      if ( v7 == 2 )
        goto LABEL_14;
    }
    if ( v6 == L"wuauengcore.dll" )
      goto LABEL_14;
    if ( v6 )
    {
      v8 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuauengcore.dll", -1);
      v6 = *v5;
      if ( v8 == 2 )
        goto LABEL_14;
    }
    if ( v6 == L"wuaucltcore.exe" )
      goto LABEL_14;
    if ( !v6 )
      goto LABEL_26;
    v9 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuaucltcore.exe", -1);
    v6 = *v5;
    if ( v9 == 2 )
LABEL_14:
      v2 |= 9u;
    if ( v6 != L"wuapicore.dll" )
    {
      if ( !v6 )
        goto LABEL_26;
      v10 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuapicore.dll", -1);
      v11 = *v5;
      if ( v10 != 2 )
      {
        if ( v11 == L"wuauengcore.dll" )
          goto LABEL_25;
        if ( v11 )
        {
          v12 = CompareStringW(0x7Fu, 1u, v11, -1, L"wuauengcore.dll", -1);
          v13 = *v5;
          if ( v12 == 2 )
          {
LABEL_25:
            v14 = L"wu.core.wuaueng";
            goto LABEL_28;
          }
          if ( v13 == L"wuaucltcore.exe" || v13 && CompareStringW(0x7Fu, 1u, v13, -1, L"wuaucltcore.exe", -1) == 2 )
          {
            v14 = L"wu.wuaucltcore";
            goto LABEL_28;
          }
        }
LABEL_26:
        v14 = L"wu";
        goto LABEL_28;
      }
    }
    v14 = L"wu.core.wuapi";
LABEL_28:
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    v15 = UndockedModuleLoader::Load(v14, *v5, 0, 0, (__int64)&lpMem);
    FileVersion = v15;
    if ( v15 >= 0 )
    {
      FileVersion = GetFileVersion(lpMem, &v21);
      if ( FileVersion >= 0 )
      {
        WUTrace(0, 0, 32, 5, 0, L"   ClientVersion: %ws = %hu.%hu.%hu.%hu");
        if ( SusClientVersion::m_CachedVersion < v21 )
          SusClientVersion::m_CachedVersion = v21;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
        (const char *)(unsigned int)v15);
    }
    ++v4;
    ++v5;
  }
  while ( v4 < 3 );
  v16 = SusClientVersion::m_CachedVersion;
  *a1 = SusClientVersion::m_CachedVersion;
  if ( v16 )
    goto LABEL_39;
  if ( FileVersion < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
      (const char *)(unsigned int)FileVersion,
      lpString2a);
LABEL_40:
  if ( lpMem )
    SusFree(lpMem);
  return (unsigned int)FileVersion;
}

```

## disassembly

```asm
0x14004175c  mov     [rsp-28h+arg_8], rbx
0x140041761  mov     [rsp-28h+arg_10], rsi
0x140041766  push    rbp
0x140041767  push    rdi
0x140041768  push    r12
0x14004176a  push    r14
0x14004176c  push    r15
0x14004176e  mov     rbp, rsp
0x140041771  sub     rsp, 80h
0x140041778  mov     rax, cs:__security_cookie
0x14004177f  xor     rax, rsp
0x140041782  mov     [rbp+var_8], rax
0x140041786  mov     [rbp+var_20], rcx
0x14004178a  test    rcx, rcx
0x14004178d  jnz     short loc_1400417B1
0x14004178f  mov     rcx, [rbp+28h]; this
0x140041793  mov     ebx, 80004003h
0x140041798  mov     r9d, ebx; char *
0x14004179b  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400417a2  mov     edx, 20h ; ' '; void *
0x1400417a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400417ac  jmp     loc_140041A8D
0x1400417b1  mov     [rbp+var_18], 0
0x1400417b9  xor     edi, edi
0x1400417bb  mov     [rbp+lpMem], rdi
0x1400417bf  mov     rax, cs:?m_CachedVersion@SusClientVersion@@2_KA; unsigned __int64 SusClientVersion::m_CachedVersion
0x1400417c6  mov     [rcx], rax
0x1400417c9  test    rax, rax
0x1400417cc  jnz     loc_140041A7D
0x1400417d2  xor     r12d, r12d
0x1400417d5  lea     rsi, off_14006F4D0; "wuapicore.dll"
0x1400417dc  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x1400417e3  or      r14d, 0FFFFFFFFh
0x1400417e7  lea     r15, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x1400417ee  lea     rbx, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x1400417f5  mov     r8, [rsi]; lpString1
0x1400417f8  cmp     r8, rax
0x1400417fb  jz      loc_140041887
0x140041801  test    r8, r8
0x140041804  jz      short loc_140041829
0x140041806  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x14004180b  mov     [rsp+80h+lpString2], rax; lpString2
0x140041810  mov     r9d, r14d; cchCount1
0x140041813  mov     edx, 1; dwCmpFlags
0x140041818  lea     ecx, [rdx+7Eh]; Locale
0x14004181b  call    cs:__imp_CompareStringW
0x140041821  mov     r8, [rsi]; lpString1
0x140041824  cmp     eax, 2
0x140041827  jz      short loc_140041887
0x140041829  cmp     r8, rbx
0x14004182c  jz      short loc_140041887
0x14004182e  test    r8, r8
0x140041831  jz      short loc_140041856
0x140041833  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x140041838  mov     [rsp+80h+lpString2], rbx; lpString2
0x14004183d  mov     r9d, r14d; cchCount1
0x140041840  mov     edx, 1; dwCmpFlags
0x140041845  lea     ecx, [rdx+7Eh]; Locale
0x140041848  call    cs:__imp_CompareStringW
0x14004184e  mov     r8, [rsi]; lpString1
0x140041851  cmp     eax, 2
0x140041854  jz      short loc_140041887
0x140041856  cmp     r8, r15
0x140041859  jz      short loc_140041887
0x14004185b  test    r8, r8
0x14004185e  jz      loc_14004193A
0x140041864  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x140041869  mov     [rsp+80h+lpString2], r15; lpString2
0x14004186e  mov     r9d, r14d; cchCount1
0x140041871  mov     edx, 1; dwCmpFlags
0x140041876  lea     ecx, [rdx+7Eh]; Locale
0x140041879  call    cs:__imp_CompareStringW
0x14004187f  mov     r8, [rsi]; lpString1
0x140041882  cmp     eax, 2
0x140041885  jnz     short loc_14004188A
0x140041887  or      edi, 9
0x14004188a  mov     ebx, edi
0x14004188c  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x140041893  cmp     r8, rax
0x140041896  jz      loc_140041943
0x14004189c  test    r8, r8
0x14004189f  jz      loc_14004193A
0x1400418a5  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x1400418aa  mov     [rsp+80h+lpString2], rax; lpString2
0x1400418af  mov     r9d, r14d; cchCount1
0x1400418b2  mov     edx, 1; dwCmpFlags
0x1400418b7  lea     ecx, [rdx+7Eh]; Locale
0x1400418ba  call    cs:__imp_CompareStringW
0x1400418c0  mov     r8, [rsi]; lpString1
0x1400418c3  cmp     eax, 2
0x1400418c6  jz      short loc_140041943
0x1400418c8  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x1400418cf  cmp     r8, rax
0x1400418d2  jz      short loc_140041931
0x1400418d4  test    r8, r8
0x1400418d7  jz      short loc_14004193A
0x1400418d9  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x1400418de  mov     [rsp+80h+lpString2], rax; lpString2
0x1400418e3  mov     r9d, r14d; cchCount1
0x1400418e6  mov     edx, 1; dwCmpFlags
0x1400418eb  lea     ecx, [rdx+7Eh]; Locale
0x1400418ee  call    cs:__imp_CompareStringW
0x1400418f4  mov     r8, [rsi]; lpString1
0x1400418f7  cmp     eax, 2
0x1400418fa  jz      short loc_140041931
0x1400418fc  cmp     r8, r15
0x1400418ff  jz      short loc_140041926
0x140041901  test    r8, r8
0x140041904  jz      short loc_14004193A
0x140041906  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x14004190b  mov     [rsp+80h+lpString2], r15; lpString2
0x140041910  mov     r9d, r14d; cchCount1
0x140041913  mov     edx, 1; dwCmpFlags
0x140041918  lea     ecx, [rdx+7Eh]; Locale
0x14004191b  call    cs:__imp_CompareStringW
0x140041921  cmp     eax, 2
0x140041924  jnz     short loc_14004193A
0x140041926  lea     r14, aWuWuaucltcore; "wu.wuaucltcore"
0x14004192d  mov     edi, ebx
0x14004192f  jmp     short loc_14004194A
0x140041931  lea     r14, aWuCoreWuaueng; "wu.core.wuaueng"
0x140041938  jmp     short loc_14004194A
0x14004193a  lea     r14, aWu; "wu"
0x140041941  jmp     short loc_14004194A
0x140041943  lea     r14, aWuCoreWuapi; "wu.core.wuapi"
0x14004194a  mov     rcx, [rbp+lpMem]; lpMem
0x14004194e  test    rcx, rcx
0x140041951  jz      short loc_140041960
0x140041953  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140041958  mov     [rbp+lpMem], 0
0x140041960  mov     [rsp+80h+var_48], 0
0x140041969  lea     rax, [rbp+lpMem]
0x14004196d  mov     [rsp+80h+var_50], rax
0x140041972  mov     qword ptr [rsp+80h+cchCount2], 0
0x14004197b  mov     [rsp+80h+lpString2], 0; int
0x140041984  lea     r9, ?m_spUusSession@SusClientVersion@@0V?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@A; wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> SusClientVersion::m_spUusSession
0x14004198b  mov     r8d, edi
0x14004198e  mov     rdx, [rsi]
0x140041991  mov     rcx, r14
0x140041994  call    UndockedModuleLoader__Load
0x140041999  mov     ebx, eax
0x14004199b  mov     rcx, [rbp+28h]; this
0x14004199f  test    eax, eax
0x1400419a1  jns     short loc_1400419B9
0x1400419a3  mov     r9d, eax; char *
0x1400419a6  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400419ad  mov     edx, 58h ; 'X'; void *
0x1400419b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400419b7  jmp     short loc_140041A30
0x1400419b9  lea     rdx, [rbp+var_18]
0x1400419bd  mov     rcx, [rbp+lpMem]
0x1400419c1  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x1400419c6  mov     ebx, eax
0x1400419c8  test    eax, eax
0x1400419ca  js      short loc_140041A30
0x1400419cc  movzx   eax, word ptr [rbp+var_18]
0x1400419d0  movzx   ecx, word ptr [rbp+var_18+2]
0x1400419d4  movzx   edx, word ptr [rbp+var_18+4]
0x1400419d8  movzx   r8d, word ptr [rbp+var_18+6]
0x1400419dd  mov     [rsp+80h+var_30], eax
0x1400419e1  mov     [rsp+80h+var_38], ecx
0x1400419e5  mov     [rsp+80h+var_40], edx
0x1400419e9  mov     dword ptr [rsp+80h+var_48], r8d
0x1400419ee  mov     rax, [rsi]
0x1400419f1  mov     [rsp+80h+var_50], rax
0x1400419f6  lea     rax, aClientversionW; "   ClientVersion: %ws = %hu.%hu.%hu.%hu"
0x1400419fd  mov     qword ptr [rsp+80h+cchCount2], rax
0x140041a02  mov     [rsp+80h+lpString2], 0; int
0x140041a0b  xor     edx, edx
0x140041a0d  xor     ecx, ecx
0x140041a0f  lea     r9d, [rdx+5]
0x140041a13  lea     r8d, [rdx+20h]
0x140041a17  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140041a1c  mov     rax, [rbp+var_18]
0x140041a20  cmp     cs:?m_CachedVersion@SusClientVersion@@2_KA, rax; unsigned __int64 SusClientVersion::m_CachedVersion
0x140041a27  jnb     short loc_140041A30
0x140041a29  mov     cs:?m_CachedVersion@SusClientVersion@@2_KA, rax; unsigned __int64 SusClientVersion::m_CachedVersion
0x140041a30  inc     r12d
0x140041a33  add     rsi, 8
0x140041a37  cmp     r12d, 3
0x140041a3b  mov     r14d, 0FFFFFFFFh
0x140041a41  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x140041a48  jb      loc_1400417EE
0x140041a4e  mov     rax, cs:?m_CachedVersion@SusClientVersion@@2_KA; unsigned __int64 SusClientVersion::m_CachedVersion
0x140041a55  mov     r15, [rbp+var_20]
0x140041a59  mov     [r15], rax
0x140041a5c  test    rax, rax
0x140041a5f  jnz     short loc_140041A7D
0x140041a61  test    ebx, ebx
0x140041a63  jns     short loc_140041A7F
0x140041a65  mov     rcx, [rbp+28h]; this
0x140041a69  mov     r9d, ebx; char *
0x140041a6c  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140041a73  lea     edx, [rax+79h]; void *
0x140041a76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140041a7b  jmp     short loc_140041A7F
0x140041a7d  xor     ebx, ebx
0x140041a7f  mov     rcx, [rbp+lpMem]; lpMem
0x140041a83  test    rcx, rcx
0x140041a86  jz      short loc_140041A8D
0x140041a88  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140041a8d  mov     eax, ebx
0x140041a8f  mov     rcx, [rbp+var_8]
0x140041a93  xor     rcx, rsp; StackCookie
0x140041a96  call    __security_check_cookie
0x140041a9b  lea     r11, [rsp+80h+var_s0]
0x140041aa3  mov     rbx, [r11+38h]
0x140041aa7  mov     rsi, [r11+40h]
0x140041aab  mov     rsp, r11
0x140041aae  pop     r15
0x140041ab0  pop     r14
0x140041ab2  pop     r12
0x140041ab4  pop     rdi
0x140041ab5  pop     rbp
0x140041ab6  retn
```
