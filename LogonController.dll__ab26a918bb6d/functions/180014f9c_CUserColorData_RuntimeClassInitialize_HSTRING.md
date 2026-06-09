# CUserColorData::RuntimeClassInitialize(HSTRING__ *)

- ea: `0x180014f9c`
- end: `0x180015398`
- name: `?RuntimeClassInitialize@CUserColorData@@QEAAJPEAUHSTRING__@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CUserColorData *this, HSTRING)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014798`
- `0x18007e230`

## callees

- `0x180004b70`
- `0x180014f9c`
- `0x18005d488`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180014ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180014ff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001500c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001500c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015136`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015195`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015257`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015335`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015136`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015195`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015257`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015335`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015061`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015061`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152c7`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001515d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001515d`
- `UxTheme!__imp_GetDefaultColorPreference` at `0x180015023`
- `UxTheme!__imp_GetDefaultColorPreference` at `0x180015023`

## string_xrefs

- `0x180015090`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserColorData::RuntimeClassInitialize(CUserColorData *this, HSTRING a2)
{
  HSTRING *v2; // rbx
  HRESULT v5; // eax
  unsigned int v6; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 *v8; // rbx
  PCWSTR v9; // rdi
  LSTATUS v10; // eax
  bool v11; // sf
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS ValueW; // eax
  bool v15; // sf
  LSTATUS v16; // eax
  bool v17; // sf
  unsigned int v18; // edi
  unsigned int i; // r14d
  LSTATUS v20; // eax
  bool v21; // sf
  LSTATUS v22; // eax
  bool v23; // sf
  __int64 v24; // rcx
  HKEY v25; // rcx
  HKEY v26; // rcx
  LSTATUS v28; // eax
  bool v29; // sf
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v2 = (HSTRING *)((char *)this + 168);
  if ( a2 && a2 == *v2 || (WindowsDeleteString(*v2), *v2 = 0, v5 = WindowsDuplicateString(a2, v2), v6 = v5, v5 >= 0) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*v2, 0);
    v8 = (__int64 *)((char *)this + 52);
    *((_BYTE *)this + 48) = 0;
    *(_QWORD *)((char *)this + 52) = 0;
    v9 = StringRawBuffer;
    GetDefaultColorPreference((char *)this + 52);
    *((_DWORD *)this + 41) = 0;
    *((_DWORD *)this + 15) = 0;
    *((_DWORD *)this + 28) = 0;
    hKey = 0;
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\DefaultColors\\HighContrast",
            0,
            0x20019u,
            &hKey);
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( !v11 )
    {
      hkey = 0;
      if ( (int)StringCchPrintfW(
                  SubKey,
                  0x104u,
                  L"%s\\%s\\%s\\%s",
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                  v9,
                  L"AnyoneRead",
                  L"Colors") >= 0 )
      {
        v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hkey);
        v13 = v12 < 0;
        if ( v12 > 0 )
          v13 = 1;
        if ( !v13 )
        {
          pvData = 0;
          pcbData = 4;
          ValueW = RegGetValueW(hkey, 0, L"HighContrastEnabled", 0x10u, 0, &pvData, &pcbData);
          v15 = ValueW < 0;
          if ( ValueW > 0 )
            v15 = 1;
          if ( !v15 )
            *((_BYTE *)this + 48) = pvData != 0;
          v35 = *v8;
          if ( !(unsigned int)SHWindowsPolicy(POLID_NoChangingStartMenuBackground) )
          {
            pcbData = 4;
            v16 = RegGetValueW(hkey, 0, L"StartColor", 0x10u, 0, &v35, &pcbData);
            v17 = v16 < 0;
            if ( v16 > 0 )
              v17 = 1;
            if ( !v17 )
            {
              pcbData = 4;
              v28 = RegGetValueW(hkey, 0, L"AccentColor", 0x10u, 0, (char *)&v35 + 4, &pcbData);
              v29 = v28 < 0;
              if ( v28 > 0 )
                v29 = 1;
              if ( !v29 )
                *v8 = v35;
            }
          }
        }
      }
      v18 = 0;
      for ( i = 0; i < 0xD; ++i )
      {
        if ( v18 >= 0xD )
          break;
        pvData = 0;
        if ( hkey )
        {
          pcbData = 4;
          v20 = RegGetValueW(hkey, 0, (LPCWSTR)qword_18009E5B0[2 * i + 1], 0x10u, 0, &pvData, &pcbData);
          v21 = v20 < 0;
          if ( v20 > 0 )
            v21 = 1;
          if ( !v21 )
            goto LABEL_27;
        }
        pcbData = 4;
        v22 = RegGetValueW(hKey, 0, (LPCWSTR)qword_18009E5B0[2 * i + 1], 0x10u, 0, &pvData, &pcbData);
        v23 = v22 < 0;
        if ( v22 > 0 )
          v23 = 1;
        if ( !v23 )
        {
LABEL_27:
          v24 = v18++;
          *((_DWORD *)this + v24 + 15) = qword_18009E5B0[2 * i];
          *((_DWORD *)this + v24 + 28) = pvData;
        }
      }
      v25 = hkey;
      *((_DWORD *)this + 41) = v18;
      hkey = 0;
      if ( v25 )
        RegCloseKey(v25);
    }
    v26 = hKey;
    hKey = 0;
    if ( v26 )
      RegCloseKey(v26);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\usercolordata.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    return v6;
  }
}

```

## disassembly

```asm
0x180014f9c  mov     [rsp-8+arg_10], rbx
0x180014fa1  push    rbp
0x180014fa2  push    rsi
0x180014fa3  push    rdi
0x180014fa4  push    r12
0x180014fa6  push    r13
0x180014fa8  push    r14
0x180014faa  push    r15
0x180014fac  lea     rbp, [rsp-180h]
0x180014fb4  sub     rsp, 280h
0x180014fbb  mov     rax, cs:__security_cookie
0x180014fc2  xor     rax, rsp
0x180014fc5  mov     [rbp+1B0h+var_40], rax
0x180014fcc  xor     r15d, r15d
0x180014fcf  lea     rbx, [rcx+0A8h]
0x180014fd6  mov     rdi, rdx
0x180014fd9  mov     rsi, rcx
0x180014fdc  test    rdx, rdx
0x180014fdf  jnz     loc_1800152F9
0x180014fe5  mov     rcx, [rbx]; string
0x180014fe8  call    cs:__imp_WindowsDeleteString
0x180014fee  mov     rdx, rbx; newString
0x180014ff1  mov     [rbx], r15
0x180014ff4  mov     rcx, rdi; string
0x180014ff7  call    cs:__imp_WindowsDuplicateString
0x180014ffd  mov     edi, eax
0x180014fff  test    eax, eax
0x180015001  js      loc_18001535A
0x180015007  mov     rcx, [rbx]; string
0x18001500a  xor     edx, edx; length
0x18001500c  call    cs:__imp_WindowsGetStringRawBuffer
0x180015012  lea     rbx, [rsi+34h]
0x180015016  mov     [rsi+30h], r15b
0x18001501a  mov     rcx, rbx
0x18001501d  mov     [rbx], r15
0x180015020  mov     rdi, rax
0x180015023  call    cs:__imp_GetDefaultColorPreference
0x180015029  mov     [rsi+0A4h], r15d
0x180015030  lea     rax, [rsp+2B0h+hKey]
0x180015035  mov     [rsi+3Ch], r15d
0x180015039  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180015040  mov     r14d, 20019h
0x180015046  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001504b  mov     r9d, r14d; samDesired
0x18001504e  mov     [rsi+70h], r15d
0x180015052  xor     r8d, r8d; ulOptions
0x180015055  mov     [rsp+2B0h+hKey], r15
0x18001505a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015061  call    cs:__imp_RegOpenKeyExW
0x180015067  mov     r12d, 80070000h
0x18001506d  test    eax, eax
0x18001506f  jle     short loc_180015079
0x180015071  movzx   eax, ax
0x180015074  or      eax, r12d
0x180015077  test    eax, eax
0x180015079  js      loc_1800152B8
0x18001507f  lea     rax, aColors; "Colors"
0x180015086  mov     [rsp+2B0h+hkey], r15
0x18001508b  mov     [rsp+2B0h+pcbData], rax
0x180015090  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015097  mov     rax, cs:off_18009E008; "AnyoneRead"
0x18001509e  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800150a5  mov     [rsp+2B0h+pvData], rax
0x1800150aa  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800150af  mov     edx, 104h; unsigned __int64
0x1800150b4  mov     [rsp+2B0h+phkResult], rdi
0x1800150b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150be  mov     edi, 4
0x1800150c3  lea     r13d, [rdi+0Ch]
0x1800150c7  test    eax, eax
0x1800150c9  js      loc_1800151AD
0x1800150cf  lea     rax, [rsp+2B0h+hkey]
0x1800150d4  mov     r9d, r14d; samDesired
0x1800150d7  xor     r8d, r8d; ulOptions
0x1800150da  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800150df  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800150e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800150eb  call    cs:__imp_RegOpenKeyExW
0x1800150f1  test    eax, eax
0x1800150f3  jle     short loc_1800150FD
0x1800150f5  movzx   eax, ax
0x1800150f8  or      eax, r12d
0x1800150fb  test    eax, eax
0x1800150fd  js      loc_1800151AD
0x180015103  mov     rcx, [rsp+2B0h+hkey]; hkey
0x180015108  lea     rax, [rsp+2B0h+var_270]
0x18001510d  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180015112  lea     r8, aHighcontrasten; "HighContrastEnabled"
0x180015119  lea     rax, [rsp+2B0h+var_26C]
0x18001511e  mov     [rsp+2B0h+var_26C], r15d
0x180015123  mov     [rsp+2B0h+pvData], rax; pvData
0x180015128  mov     r9d, r13d; dwFlags
0x18001512b  xor     edx, edx; lpSubKey
0x18001512d  mov     [rsp+2B0h+phkResult], r15; pdwType
0x180015132  mov     [rsp+2B0h+var_270], edi
0x180015136  call    cs:__imp_RegGetValueW
0x18001513c  test    eax, eax
0x18001513e  jle     short loc_180015148
0x180015140  movzx   eax, ax
0x180015143  or      eax, r12d
0x180015146  test    eax, eax
0x180015148  jns     loc_180015388
0x18001514e  mov     rax, [rbx]
0x180015151  lea     rcx, POLID_NoChangingStartMenuBackground
0x180015158  mov     [rsp+2B0h+var_258], rax
0x18001515d  call    cs:__imp_SHWindowsPolicy
0x180015163  test    eax, eax
0x180015165  jnz     short loc_1800151AD
0x180015167  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18001516c  lea     rax, [rsp+2B0h+var_270]
0x180015171  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180015176  lea     r8, aStartcolor; "StartColor"
0x18001517d  lea     rax, [rsp+2B0h+var_258]
0x180015182  mov     [rsp+2B0h+var_270], edi
0x180015186  mov     [rsp+2B0h+pvData], rax; pvData
0x18001518b  mov     r9d, r13d; dwFlags
0x18001518e  xor     edx, edx; lpSubKey
0x180015190  mov     [rsp+2B0h+phkResult], r15; pdwType
0x180015195  call    cs:__imp_RegGetValueW
0x18001519b  test    eax, eax
0x18001519d  jle     short loc_1800151A7
0x18001519f  movzx   eax, ax
0x1800151a2  or      eax, r12d
0x1800151a5  test    eax, eax
0x1800151a7  jns     loc_180015307
0x1800151ad  mov     edi, r15d
0x1800151b0  lea     rdx, qword_18009E5B0
0x1800151b7  mov     r14d, r15d
0x1800151ba  cmp     edi, 0Dh
0x1800151bd  jnb     loc_18001529D
0x1800151c3  mov     rcx, [rsp+2B0h+hkey]; hkey
0x1800151c8  mov     [rsp+2B0h+var_26C], r15d
0x1800151cd  mov     ebx, r14d
0x1800151d0  test    rcx, rcx
0x1800151d3  jz      short loc_180015221
0x1800151d5  lea     rax, [rsp+2B0h+var_270]
0x1800151da  mov     [rsp+2B0h+var_270], 4
0x1800151e2  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800151e7  mov     r8d, ebx
0x1800151ea  add     r8, r8
0x1800151ed  lea     rax, [rsp+2B0h+var_26C]
0x1800151f2  mov     [rsp+2B0h+pvData], rax; pvData
0x1800151f7  mov     r9d, r13d; dwFlags
0x1800151fa  mov     [rsp+2B0h+phkResult], r15; pdwType
0x1800151ff  mov     r8, [rdx+r8*8+8]; lpValue
0x180015204  xor     edx, edx; lpSubKey
0x180015206  call    cs:__imp_RegGetValueW
0x18001520c  test    eax, eax
0x18001520e  jle     short loc_180015218
0x180015210  movzx   eax, ax
0x180015213  or      eax, r12d
0x180015216  test    eax, eax
0x180015218  jns     short loc_18001526F
0x18001521a  lea     rdx, qword_18009E5B0
0x180015221  mov     rcx, [rsp+2B0h+hKey]; hkey
0x180015226  lea     rax, [rsp+2B0h+var_270]
0x18001522b  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180015230  mov     r8, rbx
0x180015233  add     r8, r8
0x180015236  mov     [rsp+2B0h+var_270], 4
0x18001523e  lea     rax, [rsp+2B0h+var_26C]
0x180015243  mov     r9d, r13d; dwFlags
0x180015246  mov     [rsp+2B0h+pvData], rax; pvData
0x18001524b  mov     [rsp+2B0h+phkResult], r15; pdwType
0x180015250  mov     r8, [rdx+r8*8+8]; lpValue
0x180015255  xor     edx, edx; lpSubKey
0x180015257  call    cs:__imp_RegGetValueW
0x18001525d  test    eax, eax
0x18001525f  jle     short loc_180015269
0x180015261  movzx   eax, ax
0x180015264  or      eax, r12d
0x180015267  test    eax, eax
0x180015269  js      loc_18001537C
0x18001526f  mov     ecx, edi
0x180015271  lea     rdx, qword_18009E5B0
0x180015278  mov     rax, r13
0x18001527b  imul    rbx, rax
0x18001527f  inc     edi
0x180015281  mov     eax, [rbx+rdx]
0x180015284  mov     [rsi+rcx*4+3Ch], eax
0x180015288  mov     eax, [rsp+2B0h+var_26C]
0x18001528c  mov     [rsi+rcx*4+70h], eax
0x180015290  inc     r14d
0x180015293  cmp     r14d, 0Dh
0x180015297  jb      loc_1800151BA
0x18001529d  mov     rcx, [rsp+2B0h+hkey]; hKey
0x1800152a2  mov     [rsi+0A4h], edi
0x1800152a8  mov     [rsp+2B0h+hkey], r15
0x1800152ad  test    rcx, rcx
0x1800152b0  jz      short loc_1800152B8
0x1800152b2  call    cs:__imp_RegCloseKey
0x1800152b8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800152bd  mov     [rsp+2B0h+hKey], r15
0x1800152c2  test    rcx, rcx
0x1800152c5  jz      short loc_1800152CD
0x1800152c7  call    cs:__imp_RegCloseKey
0x1800152cd  xor     eax, eax
0x1800152cf  mov     rcx, [rbp+1B0h+var_40]
0x1800152d6  xor     rcx, rsp; StackCookie
0x1800152d9  call    __security_check_cookie
0x1800152de  mov     rbx, [rsp+2B0h+arg_10]
0x1800152e6  add     rsp, 280h
0x1800152ed  pop     r15
0x1800152ef  pop     r14
0x1800152f1  pop     r13
0x1800152f3  pop     r12
0x1800152f5  pop     rdi
0x1800152f6  pop     rsi
0x1800152f7  pop     rbp
0x1800152f8  retn
0x1800152f9  cmp     rdi, [rbx]
0x1800152fc  jnz     loc_180014FE5
0x180015302  jmp     loc_180015007
0x180015307  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18001530c  lea     rax, [rsp+2B0h+var_270]
0x180015311  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180015316  lea     r8, aAccentcolor; "AccentColor"
0x18001531d  lea     rax, [rsp+2B0h+var_258+4]
0x180015322  mov     [rsp+2B0h+var_270], edi
0x180015326  mov     [rsp+2B0h+pvData], rax; pvData
0x18001532b  mov     r9d, r13d; dwFlags
0x18001532e  xor     edx, edx; lpSubKey
0x180015330  mov     [rsp+2B0h+phkResult], r15; pdwType
0x180015335  call    cs:__imp_RegGetValueW
0x18001533b  test    eax, eax
0x18001533d  jle     short loc_180015347
0x18001533f  movzx   eax, ax
0x180015342  or      eax, r12d
0x180015345  test    eax, eax
0x180015347  js      loc_1800151AD
0x18001534d  mov     rax, [rsp+2B0h+var_258]
0x180015352  mov     [rbx], rax
0x180015355  jmp     loc_1800151AD
0x18001535a  mov     rcx, [rbp+1B8h]; this
0x180015361  lea     r8, aPcshellShellAu_6; "pcshell\\shell\\auth\\authux\\controlle"...
0x180015368  mov     r9d, edi; char *
0x18001536b  mov     edx, 4Dh ; 'M'; void *
0x180015370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015375  mov     eax, edi
0x180015377  jmp     loc_1800152CF
0x18001537c  lea     rdx, qword_18009E5B0
0x180015383  jmp     loc_180015290
0x180015388  cmp     [rsp+2B0h+var_26C], r15d
0x18001538d  setnz   al
0x180015390  mov     [rsi+30h], al
0x180015393  jmp     loc_18001514E
```
