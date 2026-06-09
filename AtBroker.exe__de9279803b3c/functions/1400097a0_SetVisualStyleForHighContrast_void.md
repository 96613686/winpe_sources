# SetVisualStyleForHighContrast(void)

- ea: `0x1400097a0`
- end: `0x140009912`
- name: `?SetVisualStyleForHighContrast@@YAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000b250`

## callees

- `0x140006b3c`
- `0x1400097a0`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400098e5`
- `KERNEL32!Sleep` at `0x1400098e5`
- `KERNEL32!GetVersionExW` at `0x14000981a`
- `KERNEL32!GetVersionExW` at `0x14000981a`
- `USER32!SystemParametersInfoW` at `0x1400097e5`
- `USER32!SystemParametersInfoW` at `0x1400097e5`
- `UxTheme!__imp_SetSystemVisualStyle` at `0x1400098d6`
- `UxTheme!__imp_SetSystemVisualStyle` at `0x1400098d6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400098b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400098b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1400098a2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1400098a2`

## pseudocode

```c
void SetVisualStyleForHighContrast(void)
{
  int i; // ebx
  int pvParam; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v2; // [rsp+24h] [rbp-DCh]
  int v3; // [rsp+2Ch] [rbp-D4h]
  _OWORD v4[5]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v5[2]; // [rsp+80h] [rbp-80h]
  _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  char v7; // [rsp+1BAh] [rbp+BAh]

  pvParam = 16;
  v2 = 0;
  v3 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
  {
    if ( (v2 & 1) != 0 )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( (!GetVersionExW(&VersionInformation) || (unsigned __int8)(v7 - 2) > 1u) && IsThemeServiceAutoStart() )
      {
        v4[0] = *(_OWORD *)L"%SystemRoot%\\Resources\\Themes\\Aero\\AeroLite.msstyles";
        v4[2] = *(_OWORD *)L"ources\\Themes\\Aero\\AeroLite.msstyles";
        v4[1] = *(_OWORD *)L"oot%\\Resources\\Themes\\Aero\\AeroLite.msstyles";
        v4[4] = *(_OWORD *)L"ro\\AeroLite.msstyles";
        v4[3] = *(_OWORD *)L"hemes\\Aero\\AeroLite.msstyles";
        v5[0] = *(_OWORD *)L"ite.msstyles";
        *(_OWORD *)((char *)v5 + 10) = *(_OWORD *)L"sstyles";
        if ( (unsigned int)SHExpandEnvironmentStringsW(v4, &VersionInformation, 260) - 1 <= 0x103 )
        {
          if ( PathFileExistsW((LPCWSTR)&VersionInformation) )
          {
            for ( i = 0; i < 30; ++i )
            {
              if ( (int)SetSystemVisualStyle(&VersionInformation, L"NormalColor", L"NormalSize", 0) >= 0 )
                break;
              Sleep(0x64u);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400097a0  mov     [rsp-8+arg_0], rbx
0x1400097a5  push    rbp
0x1400097a6  lea     rbp, [rsp-1C0h]
0x1400097ae  sub     rsp, 2C0h
0x1400097b5  mov     rax, cs:__security_cookie
0x1400097bc  xor     rax, rsp
0x1400097bf  mov     [rbp+1C0h+var_10], rax
0x1400097c6  mov     edx, 10h; uiParam
0x1400097cb  lea     r8, [rsp+2C0h+pvParam]; pvParam
0x1400097d0  xor     eax, eax
0x1400097d2  mov     [rsp+2C0h+pvParam], edx
0x1400097d6  xor     r9d, r9d; fWinIni
0x1400097d9  mov     [rsp+2C0h+var_29C], rax
0x1400097de  mov     [rsp+2C0h+var_294], eax
0x1400097e2  lea     ecx, [rdx+32h]; uiAction
0x1400097e5  call    cs:__imp_SystemParametersInfoW
0x1400097eb  test    eax, eax
0x1400097ed  jz      loc_1400098F2
0x1400097f3  test    byte ptr [rsp+2C0h+var_29C], 1
0x1400097f8  jz      loc_1400098F2
0x1400097fe  xor     edx, edx; Val
0x140009800  lea     rcx, [rbp+1C0h+VersionInformation.dwMajorVersion]; void *
0x140009804  mov     r8d, 118h; Size
0x14000980a  call    memset_0
0x14000980f  lea     rcx, [rbp+1C0h+VersionInformation]; lpVersionInformation
0x140009813  mov     [rbp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000981a  call    cs:__imp_GetVersionExW
0x140009820  test    eax, eax
0x140009822  jz      short loc_140009834
0x140009824  mov     al, [rbp+1C0h+var_106]
0x14000982a  sub     al, 2
0x14000982c  cmp     al, 1
0x14000982e  jbe     loc_1400098F2
0x140009834  call    ?IsThemeServiceAutoStart@@YA_NXZ; IsThemeServiceAutoStart(void)
0x140009839  test    al, al
0x14000983b  jz      loc_1400098F2
0x140009841  movaps  xmm0, xmmword ptr cs:aSystemrootReso; "%SystemRoot%\\Resources\\Themes\\Aero\\"...
0x140009848  lea     rdx, [rbp+1C0h+VersionInformation]
0x14000984c  movaps  xmm1, xmmword ptr cs:aSystemrootReso+10h; "oot%\\Resources\\Themes\\Aero\\AeroLite"...
0x140009853  lea     rcx, [rsp+2C0h+var_290]
0x140009858  movaps  [rsp+2C0h+var_290], xmm0
0x14000985d  mov     r8d, 104h
0x140009863  movaps  xmm0, xmmword ptr cs:aSystemrootReso+20h; "ources\\Themes\\Aero\\AeroLite.msstyles"
0x14000986a  movaps  [rsp+2C0h+var_270], xmm0
0x14000986f  movaps  xmm0, xmmword ptr cs:aSystemrootReso+40h; "ro\\AeroLite.msstyles"
0x140009876  movaps  [rsp+2C0h+var_280], xmm1
0x14000987b  movaps  xmm1, xmmword ptr cs:aSystemrootReso+30h; "hemes\\Aero\\AeroLite.msstyles"
0x140009882  movaps  [rsp+2C0h+var_250], xmm0
0x140009887  movups  xmm0, xmmword ptr cs:aSystemrootReso+5Ah; "sstyles"
0x14000988e  movaps  [rsp+2C0h+var_260], xmm1
0x140009893  movaps  xmm1, xmmword ptr cs:aSystemrootReso+50h; "ite.msstyles"
0x14000989a  movaps  xmmword ptr [rbp+1C0h+var_240], xmm1
0x14000989e  movups  xmmword ptr [rbp+1C0h+var_240+0Ah], xmm0
0x1400098a2  call    cs:__imp_SHExpandEnvironmentStringsW
0x1400098a8  dec     eax
0x1400098aa  cmp     eax, 103h
0x1400098af  ja      short loc_1400098F2
0x1400098b1  lea     rcx, [rbp+1C0h+VersionInformation]; pszPath
0x1400098b5  call    cs:__imp_PathFileExistsW
0x1400098bb  test    eax, eax
0x1400098bd  jz      short loc_1400098F2
0x1400098bf  xor     ebx, ebx
0x1400098c1  xor     r9d, r9d
0x1400098c4  lea     r8, aNormalsize; "NormalSize"
0x1400098cb  lea     rdx, aNormalcolor; "NormalColor"
0x1400098d2  lea     rcx, [rbp+1C0h+VersionInformation]
0x1400098d6  call    cs:__imp_SetSystemVisualStyle
0x1400098dc  test    eax, eax
0x1400098de  jns     short loc_1400098F2
0x1400098e0  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1400098e5  call    cs:__imp_Sleep
0x1400098eb  inc     ebx
0x1400098ed  cmp     ebx, 1Eh
0x1400098f0  jl      short loc_1400098C1
0x1400098f2  mov     rcx, [rbp+1C0h+var_10]
0x1400098f9  xor     rcx, rsp; StackCookie
0x1400098fc  call    __security_check_cookie
0x140009901  mov     rbx, [rsp+2C0h+arg_0]
0x140009909  add     rsp, 2C0h
0x140009910  pop     rbp
0x140009911  retn
```
