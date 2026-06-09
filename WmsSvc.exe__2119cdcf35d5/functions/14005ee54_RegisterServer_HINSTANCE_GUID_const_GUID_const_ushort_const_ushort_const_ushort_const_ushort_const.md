# RegisterServer(HINSTANCE__ *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x14005ee54`
- end: `0x14005f577`
- name: `?RegisterServer@@YAJPEAUHINSTANCE__@@PEBU_GUID@@1PEBG222@Z`
- size: `1827`
- prototype: `int(HINSTANCE, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140044ca0`

## callees

- `0x14002e718`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005ee54`
- `0x14005f580`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14005ef23`
- `KERNEL32!GetModuleFileNameW` at `0x14005ef23`
- `KERNEL32!GetLastError` at `0x14005ef34`
- `KERNEL32!GetLastError` at `0x14005ef34`
- `KERNEL32!IsDebuggerPresent` at `0x14005ef91`
- `KERNEL32!IsDebuggerPresent` at `0x14005f04f`
- `KERNEL32!IsDebuggerPresent` at `0x14005f0dc`
- `KERNEL32!IsDebuggerPresent` at `0x14005f1f5`
- `KERNEL32!IsDebuggerPresent` at `0x14005f41c`
- `KERNEL32!IsDebuggerPresent` at `0x14005ef91`
- `KERNEL32!IsDebuggerPresent` at `0x14005f04f`
- `KERNEL32!IsDebuggerPresent` at `0x14005f0dc`
- `KERNEL32!IsDebuggerPresent` at `0x14005f1f5`
- `KERNEL32!IsDebuggerPresent` at `0x14005f41c`
- `msvcrt!wcsrchr` at `0x14005effe`
- `msvcrt!wcsrchr` at `0x14005effe`
- `ole32!StringFromGUID2` at `0x14005f129`
- `ole32!StringFromGUID2` at `0x14005f146`
- `ole32!StringFromGUID2` at `0x14005f129`
- `ole32!StringFromGUID2` at `0x14005f146`

## string_xrefs

- `0x14005ef5f`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f028`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f0c1`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f1d4`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f3fb`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f02f`: `pszServiceExeName != 0`
- `0x14005f09c`: `pszServiceExeName[0] != 0`
- `0x14005f0e4`: `pszServiceExeName[0] != 0`
- `0x14005f15b`: `CLSID\`
- `0x14005f30e`: `CLSID`
- `0x14005f36b`: `CLSID`
- `0x14005f496`: `LocalService`

## pseudocode

```c
__int64 __fastcall RegisterServer(
        HINSTANCE a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const BYTE *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  signed int LastError; // eax
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r8
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r13
  unsigned int v16; // r13d
  __int64 v17; // rsi
  const wchar_t *v18; // rcx
  unsigned __int16 *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned __int16 *v22; // rcx
  unsigned int v23; // r12d
  const wchar_t *v24; // rdi
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  unsigned __int16 *v27; // r8
  __int64 v28; // rdx
  unsigned __int16 *v29; // rcx
  __int64 v30; // rdx
  unsigned __int16 *v31; // r8
  unsigned __int16 *v32; // rcx
  unsigned __int16 *v34; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v35; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v36; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v37; // [rsp+30h] [rbp-D0h]
  int v38; // [rsp+30h] [rbp-D0h]
  int v39; // [rsp+38h] [rbp-C8h]
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR v41[40]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v42[128]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v43[128]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v44[128]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR Filename[512]; // [rsp+3F0h] [rbp+2F0h] BYREF

  memset_0(Filename, 0, sizeof(Filename));
  memset_0(sz, 0, sizeof(sz));
  memset_0(v41, 0, sizeof(v41));
  memset_0(v42, 0, sizeof(v42));
  memset_0(v44, 0, sizeof(v44));
  memset_0(v43, 0, sizeof(v43));
  if ( !GetModuleFileNameW(0, Filename, 0x200u) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0x7Cu,
      L"RegisterServer",
      L"CBRAEx",
      L"dwResult != 0",
      v11);
    if ( IsDebuggerPresent() )
    {
      v39 = v11;
      v12 = 124;
      v37 = L"dwResult != 0";
      v35 = L"CBRAEx";
LABEL_8:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        v12,
        L"RegisterServer",
        v35,
        v37,
        v39);
      return (unsigned int)v11;
    }
    v38 = v11;
    v13 = 124;
    v36 = L"dwResult != 0";
    v34 = L"CBRAEx";
LABEL_11:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      v13,
      L"RegisterServer",
      v34,
      v36,
      v38);
    return (unsigned int)v11;
  }
  v14 = wcsrchr(Filename, 0x5Cu);
  if ( !v14 )
  {
    v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0x80u,
      L"RegisterServer",
      L"CBRA",
      L"pszServiceExeName != 0",
      -2147467259);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        128,
        L"RegisterServer",
        L"CBRA",
        L"pszServiceExeName != 0",
        -2147467259);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        128,
        L"RegisterServer",
        L"CBRA",
        L"pszServiceExeName != 0",
        -2147467259);
    return (unsigned int)v11;
  }
  v15 = v14 + 1;
  if ( !v14[1] )
  {
    v16 = 132;
    v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0x84u,
      L"RegisterServer",
      L"CBRA",
      L"pszServiceExeName[0] != 0",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v39 = -2147467259;
      v37 = L"pszServiceExeName[0] != 0";
      v35 = L"CBRA";
LABEL_20:
      v12 = v16;
      goto LABEL_8;
    }
    v38 = -2147467259;
    v36 = L"pszServiceExeName[0] != 0";
    v34 = L"CBRA";
    goto LABEL_22;
  }
  v11 = StringFromGUID2(a2, sz, 40);
  if ( v11 >= 0 )
  {
    v11 = StringFromGUID2(a3, v41, 40);
    if ( v11 >= 0 )
    {
      v17 = 2147483646;
      v18 = L"CLSID\\";
      v19 = v42;
      v20 = 2147483646;
      v21 = 128;
      do
      {
        if ( !v20 )
          break;
        if ( !*v18 )
          break;
        *v19++ = *v18++;
        --v20;
        --v21;
      }
      while ( v21 );
      v22 = v19 - 1;
      v11 = v21 == 0 ? 0x8007007A : 0;
      if ( v21 )
        v22 = v19;
      *v22 = 0;
      if ( !v21 )
      {
        v23 = 144;
        goto LABEL_33;
      }
      v11 = StringCchCatW(v42, 0x80u, sz);
      if ( v11 < 0 )
      {
        v23 = 146;
LABEL_33:
        LOGASSERTHR(L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp", v23, L"RegisterServer", L"CHRA", L"hr", v11);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            v23,
            L"RegisterServer",
            L"CHRA",
            L"hr",
            v11);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            v23,
            L"RegisterServer",
            L"CHRA",
            L"hr",
            v11);
        return (unsigned int)v11;
      }
      v11 = anonymous_namespace_::SetKeyAndValue(v42, 0, 0, a4);
      if ( v11 >= 0 )
      {
        v11 = anonymous_namespace_::SetKeyAndValue(v42, 0, L"AppID", (const BYTE *)v41);
        if ( v11 >= 0 )
        {
          v11 = anonymous_namespace_::SetKeyAndValue(v42, L"LocalServer32", 0, (const BYTE *)Filename);
          if ( v11 >= 0 )
          {
            v11 = anonymous_namespace_::SetKeyAndValue(v42, L"ProgID", 0, (const BYTE *)a6);
            if ( v11 >= 0 )
            {
              v11 = anonymous_namespace_::SetKeyAndValue(v42, L"VersionIndependentProgID", 0, (const BYTE *)a5);
              if ( v11 >= 0 )
              {
                v11 = anonymous_namespace_::SetKeyAndValue(a5, 0, 0, a4);
                if ( v11 >= 0 )
                {
                  v11 = anonymous_namespace_::SetKeyAndValue(a5, L"CLSID", 0, (const BYTE *)sz);
                  if ( v11 >= 0 )
                  {
                    v11 = anonymous_namespace_::SetKeyAndValue(a5, L"CurVer", 0, (const BYTE *)a6);
                    if ( v11 >= 0 )
                    {
                      v11 = anonymous_namespace_::SetKeyAndValue(a6, 0, 0, a4);
                      if ( v11 >= 0 )
                      {
                        v11 = anonymous_namespace_::SetKeyAndValue(a6, L"CLSID", 0, (const BYTE *)sz);
                        if ( v11 >= 0 )
                        {
                          v24 = L"AppID\\";
                          v25 = 2147483646;
                          v26 = L"AppID\\";
                          v27 = v43;
                          v28 = 128;
                          do
                          {
                            if ( !v25 )
                              break;
                            if ( !*v26 )
                              break;
                            *v27++ = *v26++;
                            --v25;
                            --v28;
                          }
                          while ( v28 );
                          v29 = v27 - 1;
                          v11 = v28 == 0 ? 0x8007007A : 0;
                          if ( v28 )
                            v29 = v27;
                          *v29 = 0;
                          if ( !v28 )
                          {
                            v16 = 188;
LABEL_56:
                            LOGASSERTHR(
                              L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                              v16,
                              L"RegisterServer",
                              L"CHRA",
                              L"hr",
                              v11);
                            if ( IsDebuggerPresent() )
                            {
                              v39 = v11;
                              v37 = L"hr";
                              v35 = L"CHRA";
                              goto LABEL_20;
                            }
                            v38 = v11;
                            v36 = L"hr";
                            v34 = L"CHRA";
LABEL_22:
                            v13 = v16;
                            goto LABEL_11;
                          }
                          v11 = StringCchCatW(v43, 0x80u, v41);
                          if ( v11 < 0 )
                          {
                            v16 = 190;
                            goto LABEL_56;
                          }
                          v11 = anonymous_namespace_::SetKeyAndValue(v43, 0, 0, (const BYTE *)a7);
                          if ( v11 >= 0 )
                          {
                            v11 = anonymous_namespace_::SetKeyAndValue(v43, 0, L"LocalService", (const BYTE *)a7);
                            if ( v11 >= 0 )
                            {
                              v30 = 128;
                              v31 = v44;
                              do
                              {
                                if ( !v17 )
                                  break;
                                if ( !*v24 )
                                  break;
                                *v31++ = *v24++;
                                --v17;
                                --v30;
                              }
                              while ( v30 );
                              v32 = v31 - 1;
                              v11 = v30 == 0 ? 0x8007007A : 0;
                              if ( v30 )
                                v32 = v31;
                              *v32 = 0;
                              if ( v30 )
                              {
                                v11 = StringCchCatW(v44, 0x80u, v15);
                                if ( v11 >= 0 )
                                  return (unsigned int)anonymous_namespace_::SetKeyAndValue(
                                                         v44,
                                                         0,
                                                         L"AppID",
                                                         (const BYTE *)v41);
                                v16 = 202;
                              }
                              else
                              {
                                v16 = 200;
                              }
                              goto LABEL_56;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14005ee54  mov     [rsp-8+arg_0], rbx
0x14005ee59  push    rbp
0x14005ee5a  push    rsi
0x14005ee5b  push    rdi
0x14005ee5c  push    r12
0x14005ee5e  push    r13
0x14005ee60  push    r14
0x14005ee62  push    r15
0x14005ee64  lea     rbp, [rsp-700h]
0x14005ee6c  sub     rsp, 800h
0x14005ee73  mov     rax, cs:__security_cookie
0x14005ee7a  xor     rax, rsp
0x14005ee7d  mov     [rbp+730h+var_40], rax
0x14005ee84  mov     rax, [rbp+730h+arg_30]
0x14005ee8b  lea     rcx, [rbp+730h+Filename]; void *
0x14005ee92  mov     rdi, [rbp+730h+arg_20]
0x14005ee99  mov     rsi, r8
0x14005ee9c  mov     r14, [rbp+730h+arg_28]
0x14005eea3  mov     rbx, rdx
0x14005eea6  xor     edx, edx; Val
0x14005eea8  mov     [rsp+830h+var_7F0], rax
0x14005eead  mov     r8d, 400h; Size
0x14005eeb3  mov     r12, r9
0x14005eeb6  call    memset_0
0x14005eebb  mov     r15d, 50h ; 'P'
0x14005eec1  lea     rcx, [rsp+830h+sz]; void *
0x14005eec6  mov     r8d, r15d; Size
0x14005eec9  xor     edx, edx; Val
0x14005eecb  call    memset_0
0x14005eed0  mov     r8d, r15d; Size
0x14005eed3  lea     rcx, [rbp+730h+var_790]; void *
0x14005eed7  xor     edx, edx; Val
0x14005eed9  call    memset_0
0x14005eede  mov     r15d, 100h
0x14005eee4  lea     rcx, [rbp+730h+var_740]; void *
0x14005eee8  mov     r8d, r15d; Size
0x14005eeeb  xor     edx, edx; Val
0x14005eeed  call    memset_0
0x14005eef2  mov     r8d, r15d; Size
0x14005eef5  lea     rcx, [rbp+730h+var_540]; void *
0x14005eefc  xor     edx, edx; Val
0x14005eefe  call    memset_0
0x14005ef03  mov     r8d, r15d; Size
0x14005ef06  lea     rcx, [rbp+730h+var_640]; void *
0x14005ef0d  xor     edx, edx; Val
0x14005ef0f  call    memset_0
0x14005ef14  mov     r8d, 200h; nSize
0x14005ef1a  lea     rdx, [rbp+730h+Filename]; lpFilename
0x14005ef21  xor     ecx, ecx; hModule
0x14005ef23  call    cs:__imp_GetModuleFileNameW
0x14005ef29  xor     r15d, r15d
0x14005ef2c  test    eax, eax
0x14005ef2e  jnz     loc_14005EFF2
0x14005ef34  call    cs:__imp_GetLastError
0x14005ef3a  mov     ebx, eax
0x14005ef3c  test    eax, eax
0x14005ef3e  jle     short loc_14005EF49
0x14005ef40  movzx   ebx, ax
0x14005ef43  or      ebx, 80070000h
0x14005ef49  mov     r14d, 80004005h
0x14005ef4f  lea     r13, aCbraex; "CBRAEx"
0x14005ef56  test    ebx, ebx
0x14005ef58  lea     rsi, aRegisterserver; "RegisterServer"
0x14005ef5f  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005ef66  mov     r9, r13; unsigned __int16 *
0x14005ef69  cmovns  ebx, r14d
0x14005ef6d  lea     r12, aDwresult0; "dwResult != 0"
0x14005ef74  mov     r14d, 7Ch ; '|'
0x14005ef7a  mov     [rsp+830h+var_808], ebx; int
0x14005ef7e  mov     edx, r14d; unsigned int
0x14005ef81  mov     [rsp+830h+var_810], r12; unsigned __int16 *
0x14005ef86  mov     r8, rsi; unsigned __int16 *
0x14005ef89  mov     rcx, rdi; unsigned __int16 *
0x14005ef8c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005ef91  call    cs:__imp_IsDebuggerPresent
0x14005ef97  test    eax, eax
0x14005ef99  jz      short loc_14005EFCA
0x14005ef9b  mov     [rsp+830h+var_7F8], ebx
0x14005ef9f  mov     r9d, r14d
0x14005efa2  mov     [rsp+830h+var_800], r12
0x14005efa7  mov     qword ptr [rsp+830h+var_808], r13
0x14005efac  mov     r8, rdi
0x14005efaf  mov     [rsp+830h+var_810], rsi
0x14005efb4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005efbb  mov     ecx, 2; unsigned __int8
0x14005efc0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005efc5  jmp     loc_14005F54B
0x14005efca  mov     dword ptr [rsp+830h+var_800], ebx
0x14005efce  mov     r8d, r14d
0x14005efd1  mov     qword ptr [rsp+830h+var_808], r12
0x14005efd6  mov     [rsp+830h+var_810], r13
0x14005efdb  mov     r9, rsi
0x14005efde  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005efe5  mov     rdx, rdi
0x14005efe8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005efed  jmp     loc_14005F54B
0x14005eff2  mov     edx, 5Ch ; '\'; Ch
0x14005eff7  lea     rcx, [rbp+730h+Filename]; Str
0x14005effe  call    cs:__imp_wcsrchr
0x14005f004  test    rax, rax
0x14005f007  jnz     short loc_14005F087
0x14005f009  mov     r14d, 80004005h
0x14005f00f  lea     r12, aCbra; "CBRA"
0x14005f016  lea     rsi, aRegisterserver; "RegisterServer"
0x14005f01d  mov     [rsp+830h+var_808], r14d; int
0x14005f022  mov     r15d, 80h
0x14005f028  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f02f  lea     r13, aPszserviceexen_0; "pszServiceExeName != 0"
0x14005f036  mov     r9, r12; unsigned __int16 *
0x14005f039  mov     r8, rsi; unsigned __int16 *
0x14005f03c  mov     [rsp+830h+var_810], r13; unsigned __int16 *
0x14005f041  mov     edx, r15d; unsigned int
0x14005f044  mov     rcx, rdi; unsigned __int16 *
0x14005f047  mov     ebx, r14d
0x14005f04a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f04f  call    cs:__imp_IsDebuggerPresent
0x14005f055  test    eax, eax
0x14005f057  jz      short loc_14005F070
0x14005f059  mov     [rsp+830h+var_7F8], r14d
0x14005f05e  mov     r9d, r15d
0x14005f061  mov     [rsp+830h+var_800], r13
0x14005f066  mov     qword ptr [rsp+830h+var_808], r12
0x14005f06b  jmp     loc_14005EFAC
0x14005f070  mov     dword ptr [rsp+830h+var_800], r14d
0x14005f075  mov     r8d, r15d
0x14005f078  mov     qword ptr [rsp+830h+var_808], r13
0x14005f07d  mov     [rsp+830h+var_810], r12
0x14005f082  jmp     loc_14005EFDB
0x14005f087  lea     r13, [rax+2]
0x14005f08b  cmp     [r13+0], r15w
0x14005f090  jnz     loc_14005F11B
0x14005f096  mov     r14d, 80004005h
0x14005f09c  lea     rax, aPszserviceexen; "pszServiceExeName[0] != 0"
0x14005f0a3  lea     r12, aCbra; "CBRA"
0x14005f0aa  mov     [rsp+830h+var_808], r14d; int
0x14005f0af  lea     rsi, aRegisterserver; "RegisterServer"
0x14005f0b6  mov     [rsp+830h+var_810], rax; unsigned __int16 *
0x14005f0bb  mov     r13d, 84h
0x14005f0c1  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f0c8  mov     r9, r12; unsigned __int16 *
0x14005f0cb  mov     r8, rsi; unsigned __int16 *
0x14005f0ce  mov     edx, r13d; unsigned int
0x14005f0d1  mov     rcx, rdi; unsigned __int16 *
0x14005f0d4  mov     ebx, r14d
0x14005f0d7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f0dc  call    cs:__imp_IsDebuggerPresent
0x14005f0e2  test    eax, eax
0x14005f0e4  lea     rax, aPszserviceexen; "pszServiceExeName[0] != 0"
0x14005f0eb  jz      short loc_14005F104
0x14005f0ed  mov     [rsp+830h+var_7F8], r14d
0x14005f0f2  mov     [rsp+830h+var_800], rax
0x14005f0f7  mov     qword ptr [rsp+830h+var_808], r12
0x14005f0fc  mov     r9d, r13d
0x14005f0ff  jmp     loc_14005EFAC
0x14005f104  mov     dword ptr [rsp+830h+var_800], r14d
0x14005f109  mov     qword ptr [rsp+830h+var_808], rax
0x14005f10e  mov     [rsp+830h+var_810], r12
0x14005f113  mov     r8d, r13d
0x14005f116  jmp     loc_14005EFDB
0x14005f11b  mov     r8d, 28h ; '('; cchMax
0x14005f121  lea     rdx, [rsp+830h+sz]; lpsz
0x14005f126  mov     rcx, rbx; rguid
0x14005f129  call    cs:__imp_StringFromGUID2
0x14005f12f  mov     ebx, eax
0x14005f131  test    eax, eax
0x14005f133  js      loc_14005F54B
0x14005f139  mov     r8d, 28h ; '('; cchMax
0x14005f13f  lea     rdx, [rbp+730h+var_790]; lpsz
0x14005f143  mov     rcx, rsi; rguid
0x14005f146  call    cs:__imp_StringFromGUID2
0x14005f14c  mov     ebx, eax
0x14005f14e  test    eax, eax
0x14005f150  js      loc_14005F54B
0x14005f156  mov     esi, 7FFFFFFEh
0x14005f15b  lea     rcx, aClsid; "CLSID\\"
0x14005f162  mov     r15d, 80h
0x14005f168  lea     r8, [rbp+730h+var_740]
0x14005f16c  mov     eax, esi
0x14005f16e  mov     edx, r15d
0x14005f171  xor     r10d, r10d
0x14005f174  test    rax, rax
0x14005f177  jz      short loc_14005F198
0x14005f179  movzx   r9d, word ptr [rcx]
0x14005f17d  test    r9w, r9w
0x14005f181  jz      short loc_14005F198
0x14005f183  mov     [r8], r9w
0x14005f187  add     rcx, 2
0x14005f18b  add     r8, 2
0x14005f18f  dec     rax
0x14005f192  sub     rdx, 1
0x14005f196  jnz     short loc_14005F174
0x14005f198  mov     rax, rdx
0x14005f19b  lea     rcx, [r8-2]
0x14005f19f  neg     rax
0x14005f1a2  sbb     ebx, ebx
0x14005f1a4  not     ebx
0x14005f1a6  and     ebx, 8007007Ah
0x14005f1ac  test    rdx, rdx
0x14005f1af  cmovnz  rcx, r8
0x14005f1b3  mov     [rcx], r10w
0x14005f1b7  jnz     short loc_14005F22B
0x14005f1b9  mov     r12d, 90h
0x14005f1bf  lea     r15, aChra; "CHRA"
0x14005f1c6  mov     [rsp+830h+var_808], ebx; int
0x14005f1ca  lea     rsi, aRegisterserver; "RegisterServer"
0x14005f1d1  mov     r9, r15; unsigned __int16 *
0x14005f1d4  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f1db  mov     r8, rsi; unsigned __int16 *
0x14005f1de  lea     r14, aHr; "hr"
0x14005f1e5  mov     rcx, rdi; unsigned __int16 *
0x14005f1e8  mov     edx, r12d; unsigned int
0x14005f1eb  mov     [rsp+830h+var_810], r14; unsigned __int16 *
0x14005f1f0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f1f5  call    cs:__imp_IsDebuggerPresent
0x14005f1fb  test    eax, eax
0x14005f1fd  jz      short loc_14005F215
0x14005f1ff  mov     [rsp+830h+var_7F8], ebx
0x14005f203  mov     r9d, r12d
0x14005f206  mov     [rsp+830h+var_800], r14
0x14005f20b  mov     qword ptr [rsp+830h+var_808], r15
0x14005f210  jmp     loc_14005EFAC
0x14005f215  mov     dword ptr [rsp+830h+var_800], ebx
0x14005f219  mov     r8d, r12d
0x14005f21c  mov     qword ptr [rsp+830h+var_808], r14
0x14005f221  mov     [rsp+830h+var_810], r15
0x14005f226  jmp     loc_14005EFDB
0x14005f22b  lea     r8, [rsp+830h+sz]; unsigned __int16 *
0x14005f230  mov     rdx, r15; unsigned __int64
0x14005f233  lea     rcx, [rbp+730h+var_740]; unsigned __int16 *
0x14005f237  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005f23c  mov     ebx, eax
0x14005f23e  test    eax, eax
0x14005f240  jns     short loc_14005F24D
0x14005f242  mov     r12d, 92h
0x14005f248  jmp     loc_14005F1BF
0x14005f24d  mov     r9, r12
0x14005f250  lea     rcx, [rbp+730h+var_740]
0x14005f254  xor     r8d, r8d
0x14005f257  xor     edx, edx
0x14005f259  call    _anonymous_namespace___SetKeyAndValue
0x14005f25e  mov     ebx, eax
0x14005f260  test    eax, eax
0x14005f262  js      loc_14005F54B
0x14005f268  lea     r9, [rbp+730h+var_790]
0x14005f26c  xor     edx, edx
0x14005f26e  lea     r8, aAppid_0; "AppID"
0x14005f275  lea     rcx, [rbp+730h+var_740]
0x14005f279  call    _anonymous_namespace___SetKeyAndValue
0x14005f27e  mov     ebx, eax
0x14005f280  test    eax, eax
0x14005f282  js      loc_14005F54B
0x14005f288  lea     r9, [rbp+730h+Filename]
0x14005f28f  xor     r8d, r8d
0x14005f292  lea     rdx, aLocalserver32; "LocalServer32"
0x14005f299  lea     rcx, [rbp+730h+var_740]
0x14005f29d  call    _anonymous_namespace___SetKeyAndValue
0x14005f2a2  mov     ebx, eax
0x14005f2a4  test    eax, eax
0x14005f2a6  js      loc_14005F54B
0x14005f2ac  mov     r9, r14
0x14005f2af  lea     rdx, aProgid; "ProgID"
0x14005f2b6  xor     r8d, r8d
0x14005f2b9  lea     rcx, [rbp+730h+var_740]
0x14005f2bd  call    _anonymous_namespace___SetKeyAndValue
0x14005f2c2  mov     ebx, eax
0x14005f2c4  test    eax, eax
0x14005f2c6  js      loc_14005F54B
0x14005f2cc  mov     r9, rdi
0x14005f2cf  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x14005f2d6  xor     r8d, r8d
0x14005f2d9  lea     rcx, [rbp+730h+var_740]
0x14005f2dd  call    _anonymous_namespace___SetKeyAndValue
0x14005f2e2  mov     ebx, eax
0x14005f2e4  test    eax, eax
0x14005f2e6  js      loc_14005F54B
0x14005f2ec  mov     r9, r12
0x14005f2ef  xor     r8d, r8d
0x14005f2f2  xor     edx, edx
0x14005f2f4  mov     rcx, rdi
0x14005f2f7  call    _anonymous_namespace___SetKeyAndValue
0x14005f2fc  mov     ebx, eax
0x14005f2fe  test    eax, eax
0x14005f300  js      loc_14005F54B
0x14005f306  lea     r9, [rsp+830h+sz]
0x14005f30b  xor     r8d, r8d
0x14005f30e  lea     rdx, aClsid_0; "CLSID"
0x14005f315  mov     rcx, rdi
0x14005f318  call    _anonymous_namespace___SetKeyAndValue
0x14005f31d  mov     ebx, eax
0x14005f31f  test    eax, eax
0x14005f321  js      loc_14005F54B
0x14005f327  mov     r9, r14
0x14005f32a  lea     rdx, aCurver; "CurVer"
0x14005f331  xor     r8d, r8d
0x14005f334  mov     rcx, rdi
0x14005f337  call    _anonymous_namespace___SetKeyAndValue
0x14005f33c  mov     ebx, eax
0x14005f33e  test    eax, eax
0x14005f340  js      loc_14005F54B
0x14005f346  mov     r9, r12
  ... truncated ...
```
