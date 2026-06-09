# CClientUtils::DeleteRegistryEntry(ushort const *,ushort const *)

- ea: `0x1800816b0`
- end: `0x18008194f`
- name: `?DeleteRegistryEntry@CClientUtils@@UEAAHPEBG0@Z`
- size: `671`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ece0`
- `0x18003ce1c`
- `0x1800816b0`
- `0x1800824b4`
- `0x180084594`
- `0x180084634`
- `0x180087938`
- `0x180087b50`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800818d4`
- `ADVAPI32!RegCloseKey` at `0x180081921`
- `ADVAPI32!RegCloseKey` at `0x1800818d4`
- `ADVAPI32!RegCloseKey` at `0x180081921`
- `ADVAPI32!RegOpenKeyExW` at `0x18008179b`
- `ADVAPI32!RegOpenKeyExW` at `0x180081825`
- `ADVAPI32!RegOpenKeyExW` at `0x18008179b`
- `ADVAPI32!RegOpenKeyExW` at `0x180081825`
- `ADVAPI32!RegDeleteValueW` at `0x180081873`
- `ADVAPI32!RegDeleteValueW` at `0x180081873`

## string_xrefs

- `0x18008174c`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::DeleteRegistryEntry(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // esi
  int AppContainerRegistryLocation; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v8; // eax
  char v9; // di
  unsigned int v10; // eax
  int v11; // r8d
  int v12; // edx
  LSTATUS v13; // eax
  LSTATUS v14; // edi
  unsigned int v15; // eax
  __int64 v16; // r8
  int v18; // [rsp+28h] [rbp-D8h]
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[272]; // [rsp+40h] [rbp-C0h] BYREF

  phkResult = 0;
  v4 = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = AppContainerRegistryLocation;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v18,
          phkResult);
      }
      goto LABEL_28;
    }
    v8 = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 23;
      goto LABEL_12;
    }
  }
  else
  {
    v13 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &phkResult);
    v9 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 24;
LABEL_12:
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v11, v10, (__int64)SubKey, v9);
      goto LABEL_28;
    }
  }
  if ( RegDeleteValueW(phkResult, a3)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a2);
  }
  v4 = 1;
  v14 = RegCloseKey(phkResult);
  if ( v14
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, v15, v14);
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800816b0  mov     [rsp-8+arg_0], rbx
0x1800816b5  push    rbp
0x1800816b6  push    rsi
0x1800816b7  push    rdi
0x1800816b8  push    r14
0x1800816ba  push    r15
0x1800816bc  lea     rbp, [rsp-170h]
0x1800816c4  sub     rsp, 270h
0x1800816cb  mov     rax, cs:__security_cookie
0x1800816d2  xor     rax, rsp
0x1800816d5  mov     [rbp+190h+var_30], rax
0x1800816dc  mov     r14, r8
0x1800816df  mov     [rsp+290h+var_260], 0
0x1800816e8  xor     esi, esi
0x1800816ea  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1800816ef  mov     r8, rdx; unsigned __int16 *
0x1800816f2  mov     [rsp+290h+hKey], rsi
0x1800816f7  mov     r15, rdx
0x1800816fa  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1800816ff  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x180081704  test    eax, eax
0x180081706  jz      loc_180081806
0x18008170c  lea     rcx, [rsp+290h+hKey]; HKEY *
0x180081711  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x180081716  mov     edi, eax
0x180081718  test    eax, eax
0x18008171a  jns     short loc_18008177E
0x18008171c  mov     rcx, cs:WPP_GLOBAL_Control
0x180081723  lea     rbx, WPP_GLOBAL_Control
0x18008172a  cmp     rcx, rbx
0x18008172d  jz      loc_180081917
0x180081733  test    byte ptr [rcx+1Ch], 8
0x180081737  jz      loc_180081917
0x18008173d  cmp     byte ptr [rcx+19h], 2
0x180081741  jb      loc_180081917
0x180081747  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008174c  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180081753  mov     dword ptr [rsp+290h+var_268], edi
0x180081757  mov     [rsp+290h+phkResult], rcx
0x18008175c  lea     edx, [rsi+16h]
0x18008175f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081766  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x18008176d  mov     r9d, eax
0x180081770  mov     rcx, [rcx+10h]
0x180081774  call    WPP_SF_DsD
0x180081779  jmp     loc_180081917
0x18008177e  mov     rcx, [rsp+290h+hKey]; hKey
0x180081783  lea     rax, [rsp+290h+var_260]
0x180081788  mov     r9d, 20006h; samDesired
0x18008178e  mov     [rsp+290h+phkResult], rax; phkResult
0x180081793  xor     r8d, r8d; ulOptions
0x180081796  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18008179b  call    cs:__imp_RegOpenKeyExW
0x1800817a1  mov     edi, eax
0x1800817a3  test    eax, eax
0x1800817a5  jz      loc_18008186B
0x1800817ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800817b2  lea     rbx, WPP_GLOBAL_Control
0x1800817b9  cmp     rcx, rbx
0x1800817bc  jz      loc_180081917
0x1800817c2  test    byte ptr [rcx+1Ch], 1
0x1800817c6  jz      loc_180081917
0x1800817cc  cmp     byte ptr [rcx+19h], 4
0x1800817d0  jb      loc_180081917
0x1800817d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800817db  mov     edx, 17h
0x1800817e0  lea     rcx, [rsp+290h+SubKey]
0x1800817e5  mov     dword ptr [rsp+290h+var_268], edi
0x1800817e9  mov     [rsp+290h+phkResult], rcx
0x1800817ee  mov     r9d, eax
0x1800817f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800817f8  mov     rcx, [rcx+10h]
0x1800817fc  call    WPP_SF_DSl
0x180081801  jmp     loc_180081917
0x180081806  lea     rax, [rsp+290h+var_260]
0x18008180b  mov     r9d, 20006h; samDesired
0x180081811  xor     r8d, r8d; ulOptions
0x180081814  mov     [rsp+290h+phkResult], rax; phkResult
0x180081819  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18008181e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081825  call    cs:__imp_RegOpenKeyExW
0x18008182b  mov     edi, eax
0x18008182d  test    eax, eax
0x18008182f  jz      short loc_18008186B
0x180081831  mov     rcx, cs:WPP_GLOBAL_Control
0x180081838  lea     rbx, WPP_GLOBAL_Control
0x18008183f  cmp     rcx, rbx
0x180081842  jz      loc_180081917
0x180081848  test    byte ptr [rcx+1Ch], 1
0x18008184c  jz      loc_180081917
0x180081852  cmp     byte ptr [rcx+19h], 4
0x180081856  jb      loc_180081917
0x18008185c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081861  mov     edx, 18h
0x180081866  jmp     loc_1800817E0
0x18008186b  mov     rcx, [rsp+290h+var_260]; hKey
0x180081870  mov     rdx, r14; lpValueName
0x180081873  call    cs:__imp_RegDeleteValueW
0x180081879  lea     rbx, WPP_GLOBAL_Control
0x180081880  test    eax, eax
0x180081882  jz      short loc_1800818CA
0x180081884  mov     rax, cs:WPP_GLOBAL_Control
0x18008188b  cmp     rax, rbx
0x18008188e  jz      short loc_1800818CA
0x180081890  test    byte ptr [rax+1Ch], 1
0x180081894  jz      short loc_1800818CA
0x180081896  cmp     byte ptr [rax+19h], 4
0x18008189a  jb      short loc_1800818CA
0x18008189c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800818a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800818a8  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1800818af  mov     edx, 19h
0x1800818b4  mov     [rsp+290h+var_268], r15; __int64
0x1800818b9  mov     r9d, eax
0x1800818bc  mov     [rsp+290h+phkResult], r14; __int64
0x1800818c1  mov     rcx, [rcx+10h]; LoggerHandle
0x1800818c5  call    WPP_SF_DSS
0x1800818ca  mov     esi, 1
0x1800818cf  mov     rcx, [rsp+290h+var_260]; hKey
0x1800818d4  call    cs:__imp_RegCloseKey
0x1800818da  mov     edi, eax
0x1800818dc  test    eax, eax
0x1800818de  jz      short loc_180081917
0x1800818e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800818e7  cmp     rcx, rbx
0x1800818ea  jz      short loc_180081917
0x1800818ec  test    [rcx+1Ch], sil
0x1800818f0  jz      short loc_180081917
0x1800818f2  cmp     byte ptr [rcx+19h], 2
0x1800818f6  jb      short loc_180081917
0x1800818f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800818fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180081904  lea     edx, [rsi+19h]
0x180081907  mov     r9d, eax
0x18008190a  mov     dword ptr [rsp+290h+phkResult], edi
0x18008190e  mov     rcx, [rcx+10h]
0x180081912  call    WPP_SF_Dl
0x180081917  mov     rcx, [rsp+290h+hKey]; hKey
0x18008191c  test    rcx, rcx
0x18008191f  jz      short loc_180081927
0x180081921  call    cs:__imp_RegCloseKey
0x180081927  mov     eax, esi
0x180081929  mov     rcx, [rbp+190h+var_30]
0x180081930  xor     rcx, rsp; StackCookie
0x180081933  call    __security_check_cookie
0x180081938  mov     rbx, [rsp+290h+arg_0]
0x180081940  add     rsp, 270h
0x180081947  pop     r15
0x180081949  pop     r14
0x18008194b  pop     rdi
0x18008194c  pop     rsi
0x18008194d  pop     rbp
0x18008194e  retn
```
