# CBdeCfgConsole::ParseCommandLine(void)

- ea: `0x140002bc4`
- end: `0x1400031bd`
- name: `?ParseCommandLine@CBdeCfgConsole@@AEAAJXZ`
- size: `1529`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001fac`

## callees

- `0x1400016f3`
- `0x140002bc4`
- `0x1400031c4`
- `0x140003340`
- `0x140004460`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140003160`
- `KERNEL32!LocalFree` at `0x1400046db`
- `KERNEL32!LocalFree` at `0x140003160`
- `KERNEL32!LocalFree` at `0x1400046db`
- `KERNEL32!GetDriveTypeW` at `0x140003096`
- `KERNEL32!GetDriveTypeW` at `0x140003103`
- `KERNEL32!GetDriveTypeW` at `0x140003096`
- `KERNEL32!GetDriveTypeW` at `0x140003103`
- `KERNEL32!GetLastError` at `0x140002c6a`
- `KERNEL32!GetLastError` at `0x140002c6a`
- `KERNEL32!GetCommandLineW` at `0x140002c49`
- `KERNEL32!GetCommandLineW` at `0x140003166`
- `KERNEL32!GetCommandLineW` at `0x1400046e6`
- `KERNEL32!GetCommandLineW` at `0x140002c49`
- `KERNEL32!GetCommandLineW` at `0x140003166`
- `KERNEL32!GetCommandLineW` at `0x1400046e6`
- `msvcrt!_wcsicmp` at `0x140002cd8`
- `msvcrt!_wcsicmp` at `0x140002d27`
- `msvcrt!_wcsicmp` at `0x140002d58`
- `msvcrt!_wcsicmp` at `0x140002d71`
- `msvcrt!_wcsicmp` at `0x140002da4`
- `msvcrt!_wcsicmp` at `0x140002dcd`
- `msvcrt!_wcsicmp` at `0x140002e10`
- `msvcrt!_wcsicmp` at `0x140002e33`
- `msvcrt!_wcsicmp` at `0x140002edc`
- `msvcrt!_wcsicmp` at `0x140002eff`
- `msvcrt!_wcsicmp` at `0x140002f30`
- `msvcrt!_wcsicmp` at `0x140002fae`
- `msvcrt!_wcsicmp` at `0x140002cd8`
- `msvcrt!_wcsicmp` at `0x140002d27`
- `msvcrt!_wcsicmp` at `0x140002d58`
- `msvcrt!_wcsicmp` at `0x140002d71`
- `msvcrt!_wcsicmp` at `0x140002da4`
- `msvcrt!_wcsicmp` at `0x140002dcd`
- `msvcrt!_wcsicmp` at `0x140002e10`
- `msvcrt!_wcsicmp` at `0x140002e33`
- `msvcrt!_wcsicmp` at `0x140002edc`
- `msvcrt!_wcsicmp` at `0x140002eff`
- `msvcrt!_wcsicmp` at `0x140002f30`
- `msvcrt!_wcsicmp` at `0x140002fae`
- `msvcrt!_wcsnicmp` at `0x140002e64`
- `msvcrt!_wcsnicmp` at `0x140002e64`
- `msvcrt!iswalpha` at `0x140002e9d`
- `msvcrt!iswalpha` at `0x140002f6e`
- `msvcrt!iswalpha` at `0x14000307b`
- `msvcrt!iswalpha` at `0x140002e9d`
- `msvcrt!iswalpha` at `0x140002f6e`
- `msvcrt!iswalpha` at `0x14000307b`
- `msvcrt!towupper` at `0x140002eba`
- `msvcrt!towupper` at `0x140002f8b`
- `msvcrt!towupper` at `0x140002eba`
- `msvcrt!towupper` at `0x140002f8b`
- `msvcrt!_wtoi64` at `0x140002fe6`
- `msvcrt!_wtoi64` at `0x140002fe6`
- `SHELL32!CommandLineToArgvW` at `0x140002c57`
- `SHELL32!CommandLineToArgvW` at `0x140002c57`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x1400030ae`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x1400030ae`
- `BDEHDCFGLIB!BdeCfgLogCommandLineParams` at `0x140003172`
- `BDEHDCFGLIB!BdeCfgLogCommandLineParams` at `0x1400046f6`
- `BDEHDCFGLIB!BdeCfgLogCommandLineParams` at `0x140003172`
- `BDEHDCFGLIB!BdeCfgLogCommandLineParams` at `0x1400046f6`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::ParseCommandLine(CBdeCfgConsole *this)
{
  signed int v2; // ebx
  _BYTE *v3; // r12
  const WCHAR *CommandLineW; // rax
  LPWSTR *v5; // r15
  signed int LastError; // eax
  int v7; // esi
  LPWSTR v8; // rcx
  int v9; // esi
  LPWSTR v10; // r14
  const wchar_t *v11; // r14
  wint_t *v12; // r14
  wint_t *v13; // rcx
  const wchar_t *v14; // r14
  wint_t *v15; // r14
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  int v18; // eax
  UINT DriveTypeW; // eax
  int v20; // eax
  unsigned __int16 v21; // ax
  LPWSTR v22; // rax
  int pNumArgs; // [rsp+24h] [rbp-274h] BYREF
  int v25; // [rsp+28h] [rbp-270h]
  wint_t *v26; // [rsp+30h] [rbp-268h]
  LPWSTR *v27; // [rsp+38h] [rbp-260h]
  CBdeCfgConsole *v28; // [rsp+40h] [rbp-258h]
  WCHAR RootPathName[3]; // [rsp+50h] [rbp-248h] BYREF
  _BYTE v30[522]; // [rsp+56h] [rbp-242h] BYREF

  v28 = this;
  pNumArgs = 0;
  v27 = 0;
  wcscpy(RootPathName, L"X:");
  memset_0(v30, 0, 0x202u);
  v2 = 0;
  v3 = (char *)this + 1360;
  *((_OWORD *)this + 85) = 0;
  *((_OWORD *)this + 86) = 0;
  CommandLineW = GetCommandLineW();
  v5 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  v27 = v5;
  if ( v5 )
  {
    if ( pNumArgs <= 1 )
    {
      *v3 = 1;
      goto LABEL_94;
    }
    v7 = 1;
    v25 = 1;
    while ( v7 < pNumArgs )
    {
      v8 = v5[v7];
      if ( v8 && ((*v8 - 45) & 0xFFFD) == 0 && !_wcsicmp(v8 + 1, L"quiet") )
      {
        *((_BYTE *)this + 1384) = 1;
        break;
      }
      v25 = ++v7;
    }
    v9 = 1;
    v25 = 1;
    while ( v9 < pNumArgs )
    {
      v10 = v5[v9];
      if ( !v10 || ((*v10 - 45) & 0xFFFD) != 0 )
      {
LABEL_22:
        v2 = -1063256022;
        goto LABEL_94;
      }
      v11 = v10 + 1;
      if ( !_wcsicmp(v11, L"?") )
      {
        *v3 = 1;
        goto LABEL_94;
      }
      if ( _wcsicmp(v11, L"quiet") )
      {
        if ( _wcsicmp(v11, L"restart") )
        {
          if ( _wcsicmp(v11, L"driveinfo") )
          {
            if ( _wcsicmp(v11, L"target") )
            {
              if ( _wcsicmp(v11, L"newdriveletter") )
              {
                if ( _wcsicmp(v11, L"size") || *((_QWORD *)this + 172) )
                  goto LABEL_22;
                if ( ++v9 >= pNumArgs )
                {
                  v2 = -1063256028;
                  goto LABEL_94;
                }
                v25 = v9;
                v16 = _wtoi64(v5[v9]);
                if ( v16 < 0 || (v17 = v16 << 20, *((_QWORD *)this + 172) = v17, v17 < *((_QWORD *)this + 174)) )
                {
                  v2 = -1063256027;
                  goto LABEL_94;
                }
              }
              else
              {
                if ( *((_WORD *)this + 684) )
                  goto LABEL_22;
                if ( ++v9 >= pNumArgs )
                {
                  v2 = -1063256031;
                  goto LABEL_94;
                }
                v25 = v9;
                v15 = v5[v9];
                v26 = v15;
                if ( !iswalpha(*v15) || v15[1] != 58 || v15[2] )
                {
                  v2 = -1063256030;
                  goto LABEL_94;
                }
                *((_WORD *)this + 684) = towupper(*v15);
              }
            }
            else
            {
              if ( *((_DWORD *)this + 341) )
                goto LABEL_22;
              if ( ++v9 >= pNumArgs )
              {
LABEL_30:
                v2 = -1063256036;
                goto LABEL_94;
              }
              v25 = v9;
              v12 = v5[v9];
              v26 = v12;
              if ( _wcsicmp(v12, L"unallocated") )
              {
                if ( _wcsicmp(v12, L"default") )
                {
                  if ( ++v9 >= pNumArgs )
                    goto LABEL_30;
                  if ( _wcsnicmp(v12, L"partition", 9u) )
                  {
                    if ( !iswalpha(*v12) || v12[1] != 58 || v12[2] )
                    {
                      v2 = -1063256035;
                      goto LABEL_94;
                    }
                  }
                  else
                  {
                    v13 = v12 + 9;
                    v12 = v13;
                    v26 = v13;
                    if ( (unsigned __int16)(*v13 - 49) > 8u || v13[1] )
                      v2 = -1063256035;
                  }
                  *((_WORD *)this + 681) = towupper(*v12);
                  v25 = v9;
                  v14 = v5[v9];
                  if ( _wcsicmp(v14, L"shrink") )
                  {
                    if ( _wcsicmp(v14, L"merge") )
                      goto LABEL_30;
                    *((_DWORD *)this + 341) = 3;
                  }
                  else
                  {
                    *((_DWORD *)this + 341) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)this + 341) = 1;
                }
              }
              else
              {
                *((_DWORD *)this + 341) = 4;
              }
            }
          }
          else
          {
            if ( *((_BYTE *)this + 1361) )
              goto LABEL_22;
            *((_BYTE *)this + 1361) = 1;
          }
        }
        else
        {
          if ( *((_BYTE *)this + 1385) )
            goto LABEL_22;
          *((_BYTE *)this + 1385) = 1;
        }
      }
      v25 = ++v9;
    }
    v18 = *((_DWORD *)this + 341);
    if ( v18 == 3 )
    {
      if ( *((_QWORD *)this + 172) )
      {
        v2 = -1063256026;
        goto LABEL_94;
      }
      if ( *((_WORD *)this + 684) )
      {
        v2 = -1063256024;
        goto LABEL_94;
      }
    }
    if ( !v18 && !*((_BYTE *)this + 1361) )
    {
      v2 = -1063256025;
      goto LABEL_94;
    }
    if ( !iswalpha(*((_WORD *)this + 681)) )
      goto LABEL_82;
    RootPathName[0] = *((_WORD *)this + 681);
    DriveTypeW = GetDriveTypeW(RootPathName);
    if ( DriveTypeW < 2 )
    {
      v2 = -1063256034;
      goto LABEL_94;
    }
    if ( DriveTypeW == 3 )
    {
LABEL_82:
      v21 = *((_WORD *)this + 684);
      if ( v21 && (v21 < 0x43u || (RootPathName[0] = *((_WORD *)this + 684), GetDriveTypeW(RootPathName) != 1)) )
      {
        v2 = -1063256029;
      }
      else if ( *((_BYTE *)this + 1361)
             && (*((_DWORD *)this + 341)
              || *((_WORD *)this + 681)
              || *((_WORD *)this + 684)
              || *((_QWORD *)this + 172)
              || *((_BYTE *)this + 1384)
              || *((_BYTE *)this + 1385)) )
      {
        v2 = -1063256023;
      }
    }
    else
    {
      BdeCfgLogError(1, 1084227645);
      v20 = *((_DWORD *)this + 341);
      if ( v20 == 3 )
      {
        v2 = -1063256032;
      }
      else
      {
        v2 = -1063256037;
        if ( v20 == 2 )
          v2 = -1063256033;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_94:
  if ( v5 )
    LocalFree(v5);
  v22 = GetCommandLineW();
  BdeCfgLogCommandLineParams(v22, (char *)this + 1360);
  if ( v2 < 0 )
  {
    CBdeCfgConsole::PrintProgramBanner(this);
    CBdeCfgConsole::PrintConsoleMessage(this, v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140002bc4  mov     [rsp+arg_8], rbx
0x140002bc9  mov     [rsp+arg_10], rsi
0x140002bce  push    rdi
0x140002bcf  push    r12
0x140002bd1  push    r13
0x140002bd3  push    r14
0x140002bd5  push    r15
0x140002bd7  sub     rsp, 270h
0x140002bde  mov     rax, cs:__security_cookie
0x140002be5  xor     rax, rsp
0x140002be8  mov     [rsp+298h+var_38], rax
0x140002bf0  mov     rdi, rcx
0x140002bf3  mov     [rsp+298h+var_258], rcx
0x140002bf8  xor     r13d, r13d
0x140002bfb  mov     [rsp+298h+pNumArgs], r13d
0x140002c00  mov     [rsp+298h+var_260], r13
0x140002c05  mov     eax, dword ptr cs:asc_1400067E0; "X:"
0x140002c0b  mov     dword ptr [rsp+298h+RootPathName], eax
0x140002c0f  movzx   eax, word ptr cs:asc_1400067E0+4; ""
0x140002c16  mov     [rsp+298h+var_244], ax
0x140002c1b  xor     edx, edx; Val
0x140002c1d  mov     r8d, 202h; Size
0x140002c23  lea     rcx, [rsp+298h+var_242]; void *
0x140002c28  call    memset_0
0x140002c2d  mov     ebx, r13d
0x140002c30  mov     [rsp+298h+var_278], ebx
0x140002c34  lea     r12, [rdi+550h]
0x140002c3b  xorps   xmm0, xmm0
0x140002c3e  movups  xmmword ptr [r12], xmm0
0x140002c43  movups  xmmword ptr [r12+10h], xmm0
0x140002c49  call    cs:__imp_GetCommandLineW
0x140002c4f  mov     rcx, rax; lpCmdLine
0x140002c52  lea     rdx, [rsp+298h+pNumArgs]; pNumArgs
0x140002c57  call    cs:__imp_CommandLineToArgvW
0x140002c5d  mov     r15, rax
0x140002c60  mov     [rsp+298h+var_260], rax
0x140002c65  test    rax, rax
0x140002c68  jnz     short loc_140002C88
0x140002c6a  call    cs:__imp_GetLastError
0x140002c70  mov     ebx, eax
0x140002c72  test    eax, eax
0x140002c74  jle     loc_140003154
0x140002c7a  movzx   ebx, ax
0x140002c7d  or      ebx, 80070000h
0x140002c83  jmp     loc_140003154
0x140002c88  mov     r14d, 1
0x140002c8e  cmp     [rsp+298h+pNumArgs], r14d
0x140002c93  jg      short loc_140002C9E
0x140002c95  mov     [r12], r14b
0x140002c99  jmp     loc_140003158
0x140002c9e  mov     esi, r14d
0x140002ca1  mov     [rsp+298h+var_270], r14d
0x140002ca6  mov     edx, 0FFFDh
0x140002cab  cmp     esi, [rsp+298h+pNumArgs]
0x140002caf  jge     short loc_140002CEE
0x140002cb1  movsxd  rax, esi
0x140002cb4  mov     rcx, [r15+rax*8]
0x140002cb8  test    rcx, rcx
0x140002cbb  jz      loc_140002D42
0x140002cc1  movzx   eax, word ptr [rcx]
0x140002cc4  sub     ax, 2Dh ; '-'
0x140002cc8  test    dx, ax
0x140002ccb  jnz     short loc_140002D42
0x140002ccd  add     rcx, 2; String1
0x140002cd1  lea     rdx, aQuiet; "quiet"
0x140002cd8  call    cs:__imp__wcsicmp
0x140002cde  test    eax, eax
0x140002ce0  jnz     short loc_140002D3B
0x140002ce2  mov     [rdi+568h], r14b
0x140002ce9  mov     edx, 0FFFDh
0x140002cee  mov     esi, r14d
0x140002cf1  mov     [rsp+298h+var_270], r14d
0x140002cf6  cmp     esi, [rsp+298h+pNumArgs]
0x140002cfa  jge     loc_140003026
0x140002d00  movsxd  rax, esi
0x140002d03  mov     r14, [r15+rax*8]
0x140002d07  test    r14, r14
0x140002d0a  jz      short loc_140002D84
0x140002d0c  movzx   eax, word ptr [r14]
0x140002d10  sub     ax, 2Dh ; '-'
0x140002d14  test    dx, ax
0x140002d17  jnz     short loc_140002D84
0x140002d19  add     r14, 2
0x140002d1d  lea     rdx, asc_14000668C; "?"
0x140002d24  mov     rcx, r14; String1
0x140002d27  call    cs:__imp__wcsicmp
0x140002d2d  test    eax, eax
0x140002d2f  jnz     short loc_140002D4E
0x140002d31  mov     byte ptr [r12], 1
0x140002d36  jmp     loc_140003158
0x140002d3b  mov     edx, 0FFFDh
0x140002d40  jmp     short $+2
0x140002d42  add     esi, r14d
0x140002d45  mov     [rsp+298h+var_270], esi
0x140002d49  jmp     loc_140002CAB
0x140002d4e  lea     rdx, aQuiet; "quiet"
0x140002d55  mov     rcx, r14; String1
0x140002d58  call    cs:__imp__wcsicmp
0x140002d5e  test    eax, eax
0x140002d60  jnz     short loc_140002D67
0x140002d62  jmp     loc_14000300F
0x140002d67  lea     rdx, aRestart; "restart"
0x140002d6e  mov     rcx, r14; String1
0x140002d71  call    cs:__imp__wcsicmp
0x140002d77  test    eax, eax
0x140002d79  jnz     short loc_140002D9A
0x140002d7b  cmp     [rdi+569h], r13b
0x140002d82  jz      short loc_140002D8E
0x140002d84  mov     ebx, 0C0A0002Ah
0x140002d89  jmp     loc_140003154
0x140002d8e  mov     byte ptr [rdi+569h], 1
0x140002d95  jmp     loc_14000300F
0x140002d9a  lea     rdx, aDriveinfo; "driveinfo"
0x140002da1  mov     rcx, r14; String1
0x140002da4  call    cs:__imp__wcsicmp
0x140002daa  test    eax, eax
0x140002dac  jnz     short loc_140002DC3
0x140002dae  cmp     [rdi+551h], r13b
0x140002db5  jnz     short loc_140002D84
0x140002db7  mov     byte ptr [rdi+551h], 1
0x140002dbe  jmp     loc_14000300F
0x140002dc3  lea     rdx, aTarget; "target"
0x140002dca  mov     rcx, r14; String1
0x140002dcd  call    cs:__imp__wcsicmp
0x140002dd3  test    eax, eax
0x140002dd5  jnz     loc_140002F26
0x140002ddb  cmp     [rdi+554h], r13d
0x140002de2  jnz     short loc_140002D84
0x140002de4  inc     esi
0x140002de6  cmp     esi, [rsp+298h+pNumArgs]
0x140002dea  jl      short loc_140002DF6
0x140002dec  mov     ebx, 0C0A0001Ch
0x140002df1  jmp     loc_140003154
0x140002df6  mov     [rsp+298h+var_270], esi
0x140002dfa  movsxd  rax, esi
0x140002dfd  mov     r14, [r15+rax*8]
0x140002e01  mov     [rsp+298h+var_268], r14
0x140002e06  lea     rdx, aUnallocated; "unallocated"
0x140002e0d  mov     rcx, r14; String1
0x140002e10  call    cs:__imp__wcsicmp
0x140002e16  test    eax, eax
0x140002e18  jnz     short loc_140002E29
0x140002e1a  mov     dword ptr [rdi+554h], 4
0x140002e24  jmp     loc_14000300F
0x140002e29  lea     rdx, aDefault; "default"
0x140002e30  mov     rcx, r14; String1
0x140002e33  call    cs:__imp__wcsicmp
0x140002e39  test    eax, eax
0x140002e3b  jnz     short loc_140002E4C
0x140002e3d  mov     dword ptr [rdi+554h], 1
0x140002e47  jmp     loc_14000300F
0x140002e4c  inc     esi
0x140002e4e  cmp     esi, [rsp+298h+pNumArgs]
0x140002e52  jge     short loc_140002DEC
0x140002e54  mov     r8d, 9; MaxCount
0x140002e5a  lea     rdx, aPartition; "partition"
0x140002e61  mov     rcx, r14; String1
0x140002e64  call    cs:__imp__wcsnicmp
0x140002e6a  test    eax, eax
0x140002e6c  jnz     short loc_140002E99
0x140002e6e  lea     rcx, [r14+12h]
0x140002e72  mov     r14, rcx
0x140002e75  mov     [rsp+298h+var_268], rcx
0x140002e7a  movzx   eax, word ptr [rcx]
0x140002e7d  sub     ax, 31h ; '1'
0x140002e81  cmp     ax, 8
0x140002e85  ja      short loc_140002E8E
0x140002e87  cmp     [rcx+2], r13w
0x140002e8c  jz      short loc_140002EB6
0x140002e8e  mov     ebx, 0C0A0001Dh
0x140002e93  mov     [rsp+298h+var_278], ebx
0x140002e97  jmp     short loc_140002EB6
0x140002e99  movzx   ecx, word ptr [r14]; C
0x140002e9d  call    cs:__imp_iswalpha
0x140002ea3  test    eax, eax
0x140002ea5  jz      short loc_140002F1C
0x140002ea7  cmp     word ptr [r14+2], 3Ah ; ':'
0x140002ead  jnz     short loc_140002F1C
0x140002eaf  cmp     [r14+4], r13w
0x140002eb4  jnz     short loc_140002F1C
0x140002eb6  movzx   ecx, word ptr [r14]; C
0x140002eba  call    cs:__imp_towupper
0x140002ec0  mov     [rdi+552h], ax
0x140002ec7  mov     [rsp+298h+var_270], esi
0x140002ecb  movsxd  rax, esi
0x140002ece  mov     r14, [r15+rax*8]
0x140002ed2  lea     rdx, aShrink; "shrink"
0x140002ed9  mov     rcx, r14; String1
0x140002edc  call    cs:__imp__wcsicmp
0x140002ee2  test    eax, eax
0x140002ee4  jnz     short loc_140002EF5
0x140002ee6  mov     dword ptr [rdi+554h], 2
0x140002ef0  jmp     loc_14000300F
0x140002ef5  lea     rdx, aMerge; "merge"
0x140002efc  mov     rcx, r14; String1
0x140002eff  call    cs:__imp__wcsicmp
0x140002f05  test    eax, eax
0x140002f07  jnz     loc_140002DEC
0x140002f0d  mov     dword ptr [rdi+554h], 3
0x140002f17  jmp     loc_14000300F
0x140002f1c  mov     ebx, 0C0A0001Dh
0x140002f21  jmp     loc_140003154
0x140002f26  lea     rdx, aNewdriveletter; "newdriveletter"
0x140002f2d  mov     rcx, r14; String1
0x140002f30  call    cs:__imp__wcsicmp
0x140002f36  test    eax, eax
0x140002f38  jnz     short loc_140002FA4
0x140002f3a  cmp     [rdi+558h], r13w
0x140002f42  jnz     loc_140002D84
0x140002f48  inc     esi
0x140002f4a  cmp     esi, [rsp+298h+pNumArgs]
0x140002f4e  jl      short loc_140002F5A
0x140002f50  mov     ebx, 0C0A00021h
0x140002f55  jmp     loc_140003154
0x140002f5a  mov     [rsp+298h+var_270], esi
0x140002f5e  movsxd  rax, esi
0x140002f61  mov     r14, [r15+rax*8]
0x140002f65  mov     [rsp+298h+var_268], r14
0x140002f6a  movzx   ecx, word ptr [r14]; C
0x140002f6e  call    cs:__imp_iswalpha
0x140002f74  test    eax, eax
0x140002f76  jz      short loc_140002F9A
0x140002f78  cmp     word ptr [r14+2], 3Ah ; ':'
0x140002f7e  jnz     short loc_140002F9A
0x140002f80  cmp     [r14+4], r13w
0x140002f85  jnz     short loc_140002F9A
0x140002f87  movzx   ecx, word ptr [r14]; C
0x140002f8b  call    cs:__imp_towupper
0x140002f91  mov     [rdi+558h], ax
0x140002f98  jmp     short loc_14000300F
0x140002f9a  mov     ebx, 0C0A00022h
0x140002f9f  jmp     loc_140003154
0x140002fa4  lea     rdx, aSize; "size"
0x140002fab  mov     rcx, r14; String1
0x140002fae  call    cs:__imp__wcsicmp
0x140002fb4  test    eax, eax
0x140002fb6  jnz     loc_140002D84
0x140002fbc  cmp     [rdi+560h], r13
0x140002fc3  jnz     loc_140002D84
0x140002fc9  inc     esi
0x140002fcb  cmp     esi, [rsp+298h+pNumArgs]
0x140002fcf  jl      short loc_140002FDB
0x140002fd1  mov     ebx, 0C0A00024h
0x140002fd6  jmp     loc_140003154
0x140002fdb  mov     [rsp+298h+var_270], esi
0x140002fdf  movsxd  rcx, esi
0x140002fe2  mov     rcx, [r15+rcx*8]; String
0x140002fe6  call    cs:__imp__wtoi64
0x140002fec  test    rax, rax
0x140002fef  jns     short loc_140002FFB
0x140002ff1  mov     ebx, 0C0A00025h
0x140002ff6  jmp     loc_140003154
0x140002ffb  shl     rax, 14h
0x140002fff  mov     [rdi+560h], rax
0x140003006  cmp     rax, [rdi+570h]
0x14000300d  jb      short loc_140002FF1
0x14000300f  mov     r14d, 1
0x140003015  add     esi, r14d
0x140003018  mov     [rsp+298h+var_270], esi
0x14000301c  mov     edx, 0FFFDh
0x140003021  jmp     loc_140002CF6
0x140003026  mov     eax, [rdi+554h]
0x14000302c  cmp     eax, 3
0x14000302f  jnz     short loc_14000305D
0x140003031  cmp     [rdi+560h], r13
0x140003038  jz      short loc_140003044
0x14000303a  mov     ebx, 0C0A00026h
0x14000303f  jmp     loc_140003154
0x140003044  cmp     eax, 3
0x140003047  jnz     short loc_14000305D
0x140003049  cmp     [rdi+558h], r13w
0x140003051  jz      short loc_14000305D
0x140003053  mov     ebx, 0C0A00028h
0x140003058  jmp     loc_140003154
0x14000305d  test    eax, eax
0x14000305f  jnz     short loc_140003074
0x140003061  cmp     [rdi+551h], r13b
0x140003068  jnz     short loc_140003074
0x14000306a  mov     ebx, 0C0A00027h
0x14000306f  jmp     loc_140003154
0x140003074  movzx   ecx, word ptr [rdi+552h]; C
0x14000307b  call    cs:__imp_iswalpha
0x140003081  test    eax, eax
0x140003083  jz      short loc_1400030E0
0x140003085  movzx   eax, word ptr [rdi+552h]
0x14000308c  mov     [rsp+298h+RootPathName], ax
0x140003091  lea     rcx, [rsp+298h+RootPathName]; lpRootPathName
0x140003096  call    cs:__imp_GetDriveTypeW
0x14000309c  cmp     eax, 2
0x14000309f  jb      short loc_1400030D9
0x1400030a1  cmp     eax, 3
0x1400030a4  jz      short loc_1400030E0
0x1400030a6  mov     edx, 40A0003Dh
0x1400030ab  mov     ecx, r14d
0x1400030ae  call    cs:__imp_BdeCfgLogError
0x1400030b4  mov     eax, [rdi+554h]
0x1400030ba  cmp     eax, 3
0x1400030bd  jnz     short loc_1400030C9
0x1400030bf  mov     ebx, 0C0A00020h
0x1400030c4  jmp     loc_140003154
  ... truncated ...
```
