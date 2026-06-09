# CAppRecorderPlugin::RemoveAppCompatLayer(void)

- ea: `0x14004da2c`
- end: `0x14004dd80`
- name: `?RemoveAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `852`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004d230`

## callees

- `0x140002470`
- `0x140002a30`
- `0x140005468`
- `0x140014474`
- `0x14004da2c`
- `0x14005b7f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004daf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004daf9`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x14004db11`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x14004db25`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x14004db11`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x14004db25`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004daa6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004daa6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004dba2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004dba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004dd4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004dd4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004dc7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004dc7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004db76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004db76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dc88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dcca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dc88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dcca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dcff`

## string_xrefs

- `0x14004da7c`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x14004db68`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x14004dc6a`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::RemoveAppCompatLayer(CAppRecorderPlugin *this)
{
  const WCHAR *v1; // r8
  CAppRecorderPlugin *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // r14
  __int64 v7; // r12
  __int64 v8; // rdx
  HKEY *v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  CUserModeHangReport *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebx
  BYTE *v17; // rcx
  _WORD *v18; // rdx
  size_t v19; // r8
  signed int v20; // eax
  signed int v21; // eax
  signed int LastError; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  CAppRecorderPlugin *v25; // [rsp+48h] [rbp-B8h]
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v28[253]; // [rsp+76h] [rbp-8Ah] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 1);
  v25 = this;
  v2 = this;
  hKey[0] = 0;
  pcbData = 520;
  *(_WORD *)Data = 0;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         v1,
         2u,
         0,
         Data,
         &pcbData)
    || pcbData < 2 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 50;
      goto LABEL_49;
    }
  }
  else
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Data[2 * v4] );
    if ( (unsigned int)v4 >= 0xB )
    {
      v5 = 0;
      while ( 1 )
      {
        if ( !(unsigned int)_o__wcsnicmp(&Data[2 * v5], L"AppRecorder", 11) )
        {
          v6 = v5 - 1;
          if ( !v5 || (unsigned int)_o_isspace(*(unsigned __int16 *)&Data[2 * v6]) )
          {
            v7 = v5 + 11;
            if ( (unsigned int)_o_isspace(*(unsigned __int16 *)&Data[2 * v7]) || !*(_WORD *)&Data[2 * v7] )
              break;
          }
        }
        if ( ++v5 > (int)v4 - 11 )
          goto LABEL_13;
      }
      v14 = v5;
      if ( v5 )
        v14 = (unsigned int)v6;
      v15 = 2 * v14;
      if ( (unsigned int)v7 < (unsigned int)v4 )
      {
        v16 = v4 - v5 - 11;
        v17 = &Data[v15];
        v18 = &v28[v5];
        if ( (_DWORD)v14 )
        {
          v19 = 2LL * (v16 + 1);
        }
        else
        {
          v19 = 2LL * v16;
          ++v18;
        }
        memmove_0(v17, v18, v19);
      }
      else
      {
        if ( v15 >= 0x208 )
          _report_rangecheckfailure(v15, v8, (unsigned int)v14);
        *(_WORD *)&Data[2 * v14] = 0;
      }
LABEL_13:
      v2 = v25;
    }
    v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    if ( RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
           0,
           2u,
           v9)
      || !hKey[0] )
    {
      v21 = GetLastError();
      v11 = v21;
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 51;
        goto LABEL_49;
      }
    }
    else if ( *(_WORD *)Data )
    {
      do
        ++v3;
      while ( *(_WORD *)&Data[2 * v3] );
      if ( !RegSetValueExW(
              hKey[0],
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
              0,
              1u,
              Data,
              2 * v3) )
      {
        v11 = 0;
        goto LABEL_50;
      }
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 53;
        goto LABEL_49;
      }
    }
    else
    {
      RegDeleteValueW(hKey[0], *((LPCWSTR *)v2 + 1));
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 52;
LABEL_49:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v11);
      }
    }
  }
LABEL_50:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v11;
}

```

## disassembly

```asm
0x14004da2c  push    rbp
0x14004da2e  push    rbx
0x14004da2f  push    rsi
0x14004da30  push    rdi
0x14004da31  push    r12
0x14004da33  push    r13
0x14004da35  push    r14
0x14004da37  push    r15
0x14004da39  lea     rbp, [rsp-188h]
0x14004da41  sub     rsp, 288h
0x14004da48  mov     rax, cs:__security_cookie
0x14004da4f  xor     rax, rsp
0x14004da52  mov     [rbp+1C0h+var_50], rax
0x14004da59  mov     r8, [rcx+8]; lpValue
0x14004da5d  lea     rax, [rsp+2C0h+var_280]
0x14004da62  xor     r13d, r13d
0x14004da65  mov     [rsp+2C0h+pcbData], rax; pcbData
0x14004da6a  lea     rax, [rsp+2C0h+Data]
0x14004da6f  mov     [rsp+2C0h+var_278], rcx
0x14004da74  mov     rdi, rcx
0x14004da77  mov     [rsp+2C0h+pvData], rax; pvData
0x14004da7c  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004da83  mov     [rsp+2C0h+pdwType], r13; pdwType
0x14004da88  lea     r9d, [r13+2]; dwFlags
0x14004da8c  mov     [rsp+2C0h+hKey], r13
0x14004da91  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14004da98  mov     [rsp+2C0h+var_280], 208h
0x14004daa0  mov     word ptr [rsp+2C0h+Data], r13w
0x14004daa6  call    cs:__imp_RegGetValueW
0x14004daac  test    eax, eax
0x14004daae  jnz     loc_14004DCFF
0x14004dab4  cmp     [rsp+2C0h+var_280], 2
0x14004dab9  jb      loc_14004DCFF
0x14004dabf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14004dac3  lea     rax, [rsp+2C0h+Data]
0x14004dac8  mov     rbx, rsi
0x14004dacb  inc     rbx
0x14004dace  cmp     [rax+rbx*2], r13w
0x14004dad3  jnz     short loc_14004DACB
0x14004dad5  cmp     ebx, 0Bh
0x14004dad8  jb      short loc_14004DB50
0x14004dada  mov     edi, r13d
0x14004dadd  lea     r13d, [rbx-0Bh]
0x14004dae1  mov     eax, edi
0x14004dae3  lea     rcx, [rsp+2C0h+Data]
0x14004dae8  mov     r8d, 0Bh
0x14004daee  lea     rdx, aApprecorder; "AppRecorder"
0x14004daf5  lea     rcx, [rcx+rax*2]
0x14004daf9  call    cs:__imp__o__wcsnicmp
0x14004daff  test    eax, eax
0x14004db01  jnz     short loc_14004DB41
0x14004db03  lea     r14d, [rdi-1]
0x14004db07  test    edi, edi
0x14004db09  jz      short loc_14004DB1B
0x14004db0b  movzx   ecx, word ptr [rsp+r14*2+2C0h+Data]
0x14004db11  call    cs:__imp__o_isspace
0x14004db17  test    eax, eax
0x14004db19  jz      short loc_14004DB41
0x14004db1b  lea     r12d, [rdi+0Bh]
0x14004db1f  movzx   ecx, word ptr [rsp+r12*2+2C0h+Data]
0x14004db25  call    cs:__imp__o_isspace
0x14004db2b  xor     ecx, ecx
0x14004db2d  test    eax, eax
0x14004db2f  jnz     loc_14004DBE8
0x14004db35  cmp     word ptr [rsp+r12*2+2C0h+Data], cx
0x14004db3b  jz      loc_14004DBE8
0x14004db41  inc     edi
0x14004db43  cmp     edi, r13d
0x14004db46  jbe     short loc_14004DAE1
0x14004db48  xor     r13d, r13d
0x14004db4b  mov     rdi, [rsp+2C0h+var_278]
0x14004db50  lea     rcx, [rsp+2C0h+hKey]
0x14004db55  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004db5a  mov     r9d, 2; samDesired
0x14004db60  mov     [rsp+2C0h+pdwType], rax; phkResult
0x14004db65  xor     r8d, r8d; ulOptions
0x14004db68  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004db6f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004db76  call    cs:__imp_RegOpenKeyExW
0x14004db7c  test    eax, eax
0x14004db7e  jnz     loc_14004DCCA
0x14004db84  mov     rcx, [rsp+2C0h+hKey]; hKey
0x14004db89  test    rcx, rcx
0x14004db8c  jz      loc_14004DCCA
0x14004db92  cmp     word ptr [rsp+2C0h+Data], r13w
0x14004db98  jnz     loc_14004DC4E
0x14004db9e  mov     rdx, [rdi+8]; lpValueName
0x14004dba2  call    cs:__imp_RegDeleteValueW
0x14004dba8  call    cs:__imp_GetLastError
0x14004dbae  mov     ebx, eax
0x14004dbb0  test    eax, eax
0x14004dbb2  jle     short loc_14004DBBD
0x14004dbb4  movzx   ebx, ax
0x14004dbb7  or      ebx, 80070000h
0x14004dbbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dbc4  lea     rax, WPP_GLOBAL_Control
0x14004dbcb  cmp     rcx, rax
0x14004dbce  jz      loc_14004DD45
0x14004dbd4  test    byte ptr [rcx+1Ch], 1
0x14004dbd8  jz      loc_14004DD45
0x14004dbde  mov     edx, 34h ; '4'
0x14004dbe3  jmp     loc_14004DD32
0x14004dbe8  xor     r13d, r13d
0x14004dbeb  mov     eax, edi
0x14004dbed  test    edi, edi
0x14004dbef  cmovnz  eax, r14d
0x14004dbf3  mov     r8d, eax
0x14004dbf6  lea     rcx, [rax+rax]
0x14004dbfa  cmp     r12d, ebx
0x14004dbfd  jb      short loc_14004DC17
0x14004dbff  cmp     rcx, 208h
0x14004dc06  jnb     loc_14004DD7A
0x14004dc0c  mov     word ptr [rsp+rcx+2C0h+Data], r13w
0x14004dc12  jmp     loc_14004DB4B
0x14004dc17  sub     ebx, edi
0x14004dc19  mov     eax, edi
0x14004dc1b  add     ebx, 0FFFFFFF5h
0x14004dc1e  lea     rdx, [rsp+2C0h+var_24A]
0x14004dc23  lea     rcx, [rsp+rcx+2C0h+Data]; void *
0x14004dc28  lea     rdx, [rdx+rax*2]; Src
0x14004dc2c  test    r8d, r8d
0x14004dc2f  jz      short loc_14004DC42
0x14004dc31  lea     r8d, [rbx+1]
0x14004dc35  add     r8, r8; Size
0x14004dc38  call    memmove_0
0x14004dc3d  jmp     loc_14004DB4B
0x14004dc42  mov     r8d, ebx
0x14004dc45  add     r8, r8
0x14004dc48  add     rdx, 2
0x14004dc4c  jmp     short loc_14004DC38
0x14004dc4e  lea     rax, [rsp+2C0h+Data]
0x14004dc53  inc     rsi
0x14004dc56  cmp     [rax+rsi*2], r13w
0x14004dc5b  jnz     short loc_14004DC53
0x14004dc5d  lea     eax, [rsi+rsi]
0x14004dc60  mov     r9d, 1; dwType
0x14004dc66  mov     dword ptr [rsp+2C0h+pvData], eax; cbData
0x14004dc6a  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004dc71  lea     rax, [rsp+2C0h+Data]
0x14004dc76  xor     r8d, r8d; Reserved
0x14004dc79  mov     [rsp+2C0h+pdwType], rax; lpData
0x14004dc7e  call    cs:__imp_RegSetValueExW
0x14004dc84  test    eax, eax
0x14004dc86  jz      short loc_14004DCC5
0x14004dc88  call    cs:__imp_GetLastError
0x14004dc8e  mov     ebx, eax
0x14004dc90  test    eax, eax
0x14004dc92  jle     short loc_14004DC9D
0x14004dc94  movzx   ebx, ax
0x14004dc97  or      ebx, 80070000h
0x14004dc9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dca4  lea     rax, WPP_GLOBAL_Control
0x14004dcab  cmp     rcx, rax
0x14004dcae  jz      loc_14004DD45
0x14004dcb4  test    byte ptr [rcx+1Ch], 1
0x14004dcb8  jz      loc_14004DD45
0x14004dcbe  mov     edx, 35h ; '5'
0x14004dcc3  jmp     short loc_14004DD32
0x14004dcc5  mov     ebx, r13d
0x14004dcc8  jmp     short loc_14004DD45
0x14004dcca  call    cs:__imp_GetLastError
0x14004dcd0  mov     ebx, eax
0x14004dcd2  test    eax, eax
0x14004dcd4  jle     short loc_14004DCDF
0x14004dcd6  movzx   ebx, ax
0x14004dcd9  or      ebx, 80070000h
0x14004dcdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dce6  lea     rax, WPP_GLOBAL_Control
0x14004dced  cmp     rcx, rax
0x14004dcf0  jz      short loc_14004DD45
0x14004dcf2  test    byte ptr [rcx+1Ch], 1
0x14004dcf6  jz      short loc_14004DD45
0x14004dcf8  mov     edx, 33h ; '3'
0x14004dcfd  jmp     short loc_14004DD32
0x14004dcff  call    cs:__imp_GetLastError
0x14004dd05  mov     ebx, eax
0x14004dd07  test    eax, eax
0x14004dd09  jle     short loc_14004DD14
0x14004dd0b  movzx   ebx, ax
0x14004dd0e  or      ebx, 80070000h
0x14004dd14  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dd1b  lea     rax, WPP_GLOBAL_Control
0x14004dd22  cmp     rcx, rax
0x14004dd25  jz      short loc_14004DD45
0x14004dd27  test    byte ptr [rcx+1Ch], 1
0x14004dd2b  jz      short loc_14004DD45
0x14004dd2d  mov     edx, 32h ; '2'
0x14004dd32  mov     rcx, [rcx+10h]
0x14004dd36  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004dd3d  mov     r9d, ebx
0x14004dd40  call    WPP_SF_d
0x14004dd45  mov     rcx, [rsp+2C0h+hKey]; hKey
0x14004dd4a  test    rcx, rcx
0x14004dd4d  jz      short loc_14004DD55
0x14004dd4f  call    cs:__imp_RegCloseKey
0x14004dd55  mov     eax, ebx
0x14004dd57  mov     rcx, [rbp+1C0h+var_50]
0x14004dd5e  xor     rcx, rsp; StackCookie
0x14004dd61  call    __security_check_cookie
0x14004dd66  add     rsp, 288h
0x14004dd6d  pop     r15
0x14004dd6f  pop     r14
0x14004dd71  pop     r13
0x14004dd73  pop     r12
0x14004dd75  pop     rdi
0x14004dd76  pop     rsi
0x14004dd77  pop     rbx
0x14004dd78  pop     rbp
0x14004dd79  retn
0x14004dd7a  call    __report_rangecheckfailure
```
