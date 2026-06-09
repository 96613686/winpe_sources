# CAppRecorderPlugin::RemoveAppCompatLayer(void)

- ea: `0x140050f9c`
- end: `0x140051340`
- name: `?RemoveAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `932`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005009c`

## callees

- `0x140002490`
- `0x140002a80`
- `0x14000551c`
- `0x140014f14`
- `0x140050f9c`
- `0x14005f594`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140051073`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140051073`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140051091`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1400510ab`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x140051091`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1400510ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140051016`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140051016`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140051134`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140051134`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051308`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005121c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005121c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051102`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005122c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400512b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005122c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400512b2`

## string_xrefs

- `0x140050fec`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x1400510f4`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x140051208`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

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
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v11);
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
0x140050f9c  push    rbp
0x140050f9e  push    rbx
0x140050f9f  push    rsi
0x140050fa0  push    rdi
0x140050fa1  push    r12
0x140050fa3  push    r13
0x140050fa5  push    r14
0x140050fa7  push    r15
0x140050fa9  lea     rbp, [rsp-188h]
0x140050fb1  sub     rsp, 288h
0x140050fb8  mov     rax, cs:__security_cookie
0x140050fbf  xor     rax, rsp
0x140050fc2  mov     [rbp+1C0h+var_50], rax
0x140050fc9  mov     r8, [rcx+8]; lpValue
0x140050fcd  lea     rax, [rsp+2C0h+var_280]
0x140050fd2  xor     r13d, r13d
0x140050fd5  mov     [rsp+2C0h+pcbData], rax; pcbData
0x140050fda  lea     rax, [rsp+2C0h+Data]
0x140050fdf  mov     [rsp+2C0h+var_278], rcx
0x140050fe4  mov     rdi, rcx
0x140050fe7  mov     [rsp+2C0h+pvData], rax; pvData
0x140050fec  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x140050ff3  mov     [rsp+2C0h+pdwType], r13; pdwType
0x140050ff8  lea     r9d, [r13+2]; dwFlags
0x140050ffc  mov     [rsp+2C0h+hKey], r13
0x140051001  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140051008  mov     [rsp+2C0h+var_280], 208h
0x140051010  mov     word ptr [rsp+2C0h+Data], r13w
0x140051016  call    cs:__imp_RegGetValueW
0x14005101d  nop     dword ptr [rax+rax+00h]
0x140051022  test    eax, eax
0x140051024  jnz     loc_1400512B2
0x14005102a  cmp     [rsp+2C0h+var_280], 2
0x14005102f  jb      loc_1400512B2
0x140051035  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140051039  lea     rax, [rsp+2C0h+Data]
0x14005103e  mov     rbx, rsi
0x140051041  inc     rbx
0x140051044  cmp     [rax+rbx*2], r13w
0x140051049  jnz     short loc_140051041
0x14005104b  cmp     ebx, 0Bh
0x14005104e  jb      loc_1400510DC
0x140051054  mov     edi, r13d
0x140051057  lea     r13d, [rbx-0Bh]
0x14005105b  mov     eax, edi
0x14005105d  lea     rcx, [rsp+2C0h+Data]
0x140051062  mov     r8d, 0Bh
0x140051068  lea     rdx, aApprecorder; "AppRecorder"
0x14005106f  lea     rcx, [rcx+rax*2]
0x140051073  call    cs:__imp__o__wcsnicmp
0x14005107a  nop     dword ptr [rax+rax+00h]
0x14005107f  test    eax, eax
0x140051081  jnz     short loc_1400510CD
0x140051083  lea     r14d, [rdi-1]
0x140051087  test    edi, edi
0x140051089  jz      short loc_1400510A1
0x14005108b  movzx   ecx, word ptr [rsp+r14*2+2C0h+Data]
0x140051091  call    cs:__imp__o_isspace
0x140051098  nop     dword ptr [rax+rax+00h]
0x14005109d  test    eax, eax
0x14005109f  jz      short loc_1400510CD
0x1400510a1  lea     r12d, [rdi+0Bh]
0x1400510a5  movzx   ecx, word ptr [rsp+r12*2+2C0h+Data]
0x1400510ab  call    cs:__imp__o_isspace
0x1400510b2  nop     dword ptr [rax+rax+00h]
0x1400510b7  xor     ecx, ecx
0x1400510b9  test    eax, eax
0x1400510bb  jnz     loc_140051186
0x1400510c1  cmp     word ptr [rsp+r12*2+2C0h+Data], cx
0x1400510c7  jz      loc_140051186
0x1400510cd  inc     edi
0x1400510cf  cmp     edi, r13d
0x1400510d2  jbe     short loc_14005105B
0x1400510d4  xor     r13d, r13d
0x1400510d7  mov     rdi, [rsp+2C0h+var_278]
0x1400510dc  lea     rcx, [rsp+2C0h+hKey]
0x1400510e1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400510e6  mov     r9d, 2; samDesired
0x1400510ec  mov     [rsp+2C0h+pdwType], rax; phkResult
0x1400510f1  xor     r8d, r8d; ulOptions
0x1400510f4  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400510fb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140051102  call    cs:__imp_RegOpenKeyExW
0x140051109  nop     dword ptr [rax+rax+00h]
0x14005110e  test    eax, eax
0x140051110  jnz     loc_140051277
0x140051116  mov     rcx, [rsp+2C0h+hKey]; hKey
0x14005111b  test    rcx, rcx
0x14005111e  jz      loc_140051277
0x140051124  cmp     word ptr [rsp+2C0h+Data], r13w
0x14005112a  jnz     loc_1400511EC
0x140051130  mov     rdx, [rdi+8]; lpValueName
0x140051134  call    cs:__imp_RegDeleteValueW
0x14005113b  nop     dword ptr [rax+rax+00h]
0x140051140  call    cs:__imp_GetLastError
0x140051147  nop     dword ptr [rax+rax+00h]
0x14005114c  mov     ebx, eax
0x14005114e  test    eax, eax
0x140051150  jle     short loc_14005115B
0x140051152  movzx   ebx, ax
0x140051155  or      ebx, 80070000h
0x14005115b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051162  lea     rax, WPP_GLOBAL_Control
0x140051169  cmp     rcx, rax
0x14005116c  jz      loc_1400512FE
0x140051172  test    byte ptr [rcx+1Ch], 1
0x140051176  jz      loc_1400512FE
0x14005117c  mov     edx, 34h ; '4'
0x140051181  jmp     loc_1400512EB
0x140051186  xor     r13d, r13d
0x140051189  mov     eax, edi
0x14005118b  test    edi, edi
0x14005118d  cmovnz  eax, r14d
0x140051191  mov     r8d, eax
0x140051194  lea     rcx, [rax+rax]
0x140051198  cmp     r12d, ebx
0x14005119b  jb      short loc_1400511B5
0x14005119d  cmp     rcx, 208h
0x1400511a4  jnb     loc_14005133A
0x1400511aa  mov     word ptr [rsp+rcx+2C0h+Data], r13w
0x1400511b0  jmp     loc_1400510D7
0x1400511b5  sub     ebx, edi
0x1400511b7  mov     eax, edi
0x1400511b9  add     ebx, 0FFFFFFF5h
0x1400511bc  lea     rdx, [rsp+2C0h+var_24A]
0x1400511c1  lea     rcx, [rsp+rcx+2C0h+Data]; void *
0x1400511c6  lea     rdx, [rdx+rax*2]; Src
0x1400511ca  test    r8d, r8d
0x1400511cd  jz      short loc_1400511E0
0x1400511cf  lea     r8d, [rbx+1]
0x1400511d3  add     r8, r8; Size
0x1400511d6  call    memmove_0
0x1400511db  jmp     loc_1400510D7
0x1400511e0  mov     r8d, ebx
0x1400511e3  add     r8, r8
0x1400511e6  add     rdx, 2
0x1400511ea  jmp     short loc_1400511D6
0x1400511ec  lea     rax, [rsp+2C0h+Data]
0x1400511f1  inc     rsi
0x1400511f4  cmp     [rax+rsi*2], r13w
0x1400511f9  jnz     short loc_1400511F1
0x1400511fb  lea     eax, [rsi+rsi]
0x1400511fe  mov     r9d, 1; dwType
0x140051204  mov     dword ptr [rsp+2C0h+pvData], eax; cbData
0x140051208  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14005120f  lea     rax, [rsp+2C0h+Data]
0x140051214  xor     r8d, r8d; Reserved
0x140051217  mov     [rsp+2C0h+pdwType], rax; lpData
0x14005121c  call    cs:__imp_RegSetValueExW
0x140051223  nop     dword ptr [rax+rax+00h]
0x140051228  test    eax, eax
0x14005122a  jz      short loc_14005126F
0x14005122c  call    cs:__imp_GetLastError
0x140051233  nop     dword ptr [rax+rax+00h]
0x140051238  mov     ebx, eax
0x14005123a  test    eax, eax
0x14005123c  jle     short loc_140051247
0x14005123e  movzx   ebx, ax
0x140051241  or      ebx, 80070000h
0x140051247  mov     rcx, cs:WPP_GLOBAL_Control
0x14005124e  lea     rax, WPP_GLOBAL_Control
0x140051255  cmp     rcx, rax
0x140051258  jz      loc_1400512FE
0x14005125e  test    byte ptr [rcx+1Ch], 1
0x140051262  jz      loc_1400512FE
0x140051268  mov     edx, 35h ; '5'
0x14005126d  jmp     short loc_1400512EB
0x14005126f  mov     ebx, r13d
0x140051272  jmp     loc_1400512FE
0x140051277  call    cs:__imp_GetLastError
0x14005127e  nop     dword ptr [rax+rax+00h]
0x140051283  mov     ebx, eax
0x140051285  test    eax, eax
0x140051287  jle     short loc_140051292
0x140051289  movzx   ebx, ax
0x14005128c  or      ebx, 80070000h
0x140051292  mov     rcx, cs:WPP_GLOBAL_Control
0x140051299  lea     rax, WPP_GLOBAL_Control
0x1400512a0  cmp     rcx, rax
0x1400512a3  jz      short loc_1400512FE
0x1400512a5  test    byte ptr [rcx+1Ch], 1
0x1400512a9  jz      short loc_1400512FE
0x1400512ab  mov     edx, 33h ; '3'
0x1400512b0  jmp     short loc_1400512EB
0x1400512b2  call    cs:__imp_GetLastError
0x1400512b9  nop     dword ptr [rax+rax+00h]
0x1400512be  mov     ebx, eax
0x1400512c0  test    eax, eax
0x1400512c2  jle     short loc_1400512CD
0x1400512c4  movzx   ebx, ax
0x1400512c7  or      ebx, 80070000h
0x1400512cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400512d4  lea     rax, WPP_GLOBAL_Control
0x1400512db  cmp     rcx, rax
0x1400512de  jz      short loc_1400512FE
0x1400512e0  test    byte ptr [rcx+1Ch], 1
0x1400512e4  jz      short loc_1400512FE
0x1400512e6  mov     edx, 32h ; '2'
0x1400512eb  mov     rcx, [rcx+10h]
0x1400512ef  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1400512f6  mov     r9d, ebx
0x1400512f9  call    WPP_SF_d
0x1400512fe  mov     rcx, [rsp+2C0h+hKey]; hKey
0x140051303  test    rcx, rcx
0x140051306  jz      short loc_140051314
0x140051308  call    cs:__imp_RegCloseKey
0x14005130f  nop     dword ptr [rax+rax+00h]
0x140051314  mov     eax, ebx
0x140051316  mov     rcx, [rbp+1C0h+var_50]
0x14005131d  xor     rcx, rsp; StackCookie
0x140051320  call    __security_check_cookie
0x140051325  add     rsp, 288h
0x14005132c  pop     r15
0x14005132e  pop     r14
0x140051330  pop     r13
0x140051332  pop     r12
0x140051334  pop     rdi
0x140051335  pop     rsi
0x140051336  pop     rbx
0x140051337  pop     rbp
0x140051338  retn
0x14005133a  call    __report_rangecheckfailure
```
