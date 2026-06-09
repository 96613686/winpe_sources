# SplashScreen::CSplashScreenConfiguration::LoadBackgroundColor(void)

- ea: `0x18000dad0`
- end: `0x18000dc36`
- name: `?LoadBackgroundColor@CSplashScreenConfiguration@SplashScreen@@MEAAXXZ`
- size: `358`
- prototype: `void __fastcall(SplashScreen::CSplashScreenConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004e8c`
- `0x18000da80`
- `0x18000dad0`
- `0x180041268`
- `0x180043c30`
- `0x180047034`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000db75`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000db75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000db48`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000db48`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000dc23`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000dc23`

## pseudocode

```c
void __fastcall SplashScreen::CSplashScreenConfiguration::LoadBackgroundColor(
        SplashScreen::CSplashScreenConfiguration *this)
{
  HKEY v2; // rcx
  LSTATUS ValueW; // eax
  bool v4; // sf
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rdx
  DWORD pcbData; // [rsp+40h] [rbp-58h] BYREF
  WCHAR String1[32]; // [rsp+48h] [rbp-50h] BYREF

  if ( (unsigned __int8)IsGetSysColorPresent() && (unsigned int)IsHighContrast() )
  {
    *((_BYTE *)this + 8) = 1;
    *((_DWORD *)this + 20) = GetSysColor(5) | 0xFF000000;
  }
  else
  {
    v2 = (HKEY)*((_QWORD *)this + 11);
    if ( v2 )
    {
      pcbData = 60;
      ValueW = RegGetValueW(v2, 0, L"BackgroundColor", 2u, 0, String1, &pcbData);
      v4 = ValueW < 0;
      if ( ValueW )
      {
        String1[0] = 0;
        if ( ValueW > 0 )
          v4 = 1;
      }
      if ( !v4 )
      {
        v5 = -1;
        if ( CompareStringOrdinal(String1, -1, L"Transparent", -1, 1) == 2 )
        {
          *((_BYTE *)this + 8) = (*(__int64 (__fastcall **)(SplashScreen::CSplashScreenConfiguration *))(*(_QWORD *)this + 32LL))(this);
          LOBYTE(v7) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl'::`2'::impl,
            v7);
        }
        if ( !*((_BYTE *)this + 8) )
        {
          do
            ++v5;
          while ( String1[v5] );
          v6 = s_ParseColorFormat(String1);
          *((_DWORD *)this + 20) |= 0xFF000000;
          *((_BYTE *)this + 8) = v6 >= 0;
        }
      }
    }
  }
  *((_BYTE *)this + 9) = 1;
}

```

## disassembly

```asm
0x18000dad0  mov     [rsp+arg_8], rbx
0x18000dad5  mov     [rsp+arg_10], rsi
0x18000dada  push    rdi
0x18000dadb  sub     rsp, 90h
0x18000dae2  mov     rax, cs:__security_cookie
0x18000dae9  xor     rax, rsp
0x18000daec  mov     [rsp+98h+var_10], rax
0x18000daf4  mov     rdi, rcx
0x18000daf7  call    IsGetSysColorPresent
0x18000dafc  xor     ebx, ebx
0x18000dafe  test    al, al
0x18000db00  jz      short loc_18000DB0F
0x18000db02  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x18000db07  test    eax, eax
0x18000db09  jnz     loc_18000DC1A
0x18000db0f  mov     rcx, [rdi+58h]; hkey
0x18000db13  test    rcx, rcx
0x18000db16  jz      short loc_18000DB85
0x18000db18  lea     rax, [rsp+98h+var_58]
0x18000db1d  mov     [rsp+98h+var_58], 3Ch ; '<'
0x18000db25  mov     [rsp+98h+pcbData], rax; pcbData
0x18000db2a  lea     r8, aBackgroundcolo; "BackgroundColor"
0x18000db31  lea     rax, [rsp+98h+String1]
0x18000db36  mov     r9d, 2; dwFlags
0x18000db3c  mov     [rsp+98h+pvData], rax; pvData
0x18000db41  xor     edx, edx; lpSubKey
0x18000db43  mov     [rsp+98h+pdwType], rbx; pdwType
0x18000db48  call    cs:__imp_RegGetValueW
0x18000db4e  test    eax, eax
0x18000db50  jnz     loc_18000DC00
0x18000db56  js      short loc_18000DB85
0x18000db58  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000db5c  mov     dword ptr [rsp+98h+pdwType], 1; bIgnoreCase
0x18000db64  mov     r9d, esi; cchCount2
0x18000db67  lea     r8, String2; "Transparent"
0x18000db6e  mov     edx, esi; cchCount1
0x18000db70  lea     rcx, [rsp+98h+String1]; lpString1
0x18000db75  call    cs:__imp_CompareStringOrdinal
0x18000db7b  cmp     eax, 2
0x18000db7e  jz      short loc_18000DBDE
0x18000db80  cmp     [rdi+8], bl
0x18000db83  jz      short loc_18000DBAE
0x18000db85  mov     byte ptr [rdi+9], 1
0x18000db89  mov     rcx, [rsp+98h+var_10]
0x18000db91  xor     rcx, rsp; StackCookie
0x18000db94  call    __security_check_cookie
0x18000db99  lea     r11, [rsp+98h+var_8]
0x18000dba1  mov     rbx, [r11+18h]
0x18000dba5  mov     rsi, [r11+20h]
0x18000dba9  mov     rsp, r11
0x18000dbac  pop     rdi
0x18000dbad  retn
0x18000dbae  lea     rax, [rsp+98h+String1]
0x18000dbb3  inc     rsi
0x18000dbb6  cmp     [rax+rsi*2], bx
0x18000dbba  jnz     short loc_18000DBB3
0x18000dbbc  lea     edx, [rsi+1]
0x18000dbbf  lea     r8, [rdi+50h]
0x18000dbc3  lea     rcx, [rsp+98h+String1]; lpString1
0x18000dbc8  call    s_ParseColorFormat
0x18000dbcd  shr     eax, 1Fh
0x18000dbd0  xor     al, 1
0x18000dbd2  or      dword ptr [rdi+50h], 0FF000000h
0x18000dbd9  mov     [rdi+8], al
0x18000dbdc  jmp     short loc_18000DB85
0x18000dbde  mov     rax, [rdi]
0x18000dbe1  mov     rcx, rdi
0x18000dbe4  mov     rax, [rax+20h]
0x18000dbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbed  mov     [rdi+8], al
0x18000dbf0  mov     dl, 1
0x18000dbf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens> `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl(void)'::`2'::impl
0x18000dbf9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000dbfe  jmp     short loc_18000DB80
0x18000dc00  mov     [rsp+98h+String1], bx
0x18000dc05  jle     loc_18000DB56
0x18000dc0b  movzx   eax, ax
0x18000dc0e  or      eax, 80070000h
0x18000dc13  test    eax, eax
0x18000dc15  jmp     loc_18000DB56
0x18000dc1a  mov     ecx, 5; nIndex
0x18000dc1f  mov     byte ptr [rdi+8], 1
0x18000dc23  call    cs:__imp_GetSysColor
0x18000dc29  or      eax, 0FF000000h
0x18000dc2e  mov     [rdi+50h], eax
0x18000dc31  jmp     loc_18000DB85
```
