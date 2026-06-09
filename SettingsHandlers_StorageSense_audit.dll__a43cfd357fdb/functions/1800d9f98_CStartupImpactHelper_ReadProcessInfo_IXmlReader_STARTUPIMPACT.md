# CStartupImpactHelper::ReadProcessInfo(IXmlReader *,_STARTUPIMPACT *)

- ea: `0x1800d9f98`
- end: `0x1800da325`
- name: `?ReadProcessInfo@CStartupImpactHelper@@AEAAJPEAUIXmlReader@@PEAU_STARTUPIMPACT@@@Z`
- size: `909`
- prototype: `__int64 __fastcall(CStartupImpactHelper *__hidden this, struct IXmlReader *, struct _STARTUPIMPACT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d9b1c`

## callees

- `0x18000f038`
- `0x1800d0614`
- `0x1800d95d4`
- `0x1800d9f98`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da056`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da072`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da12c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da159`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da183`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da1b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da1db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da205`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da249`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da267`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da056`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da072`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da12c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da159`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da183`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da1b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da1db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da205`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da249`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800da267`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800da13c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800da193`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800da13c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800da193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da0d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da0d8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800da219`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800da219`

## string_xrefs

- `0x1800da067`: `CommandLine`
- `0x1800da25c`: `CommandLine`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStartupImpactHelper::ReadProcessInfo(
        CStartupImpactHelper *this,
        struct IXmlReader *a2,
        struct _STARTUPIMPACT *a3)
{
  int DetailsFromCrudeCmdLine; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int v7; // eax
  double v8; // xmm0_8
  double v9; // xmm0_8
  CStartupImpactHelper *v10; // rcx
  struct _FILETIME *v11; // r8
  PCWSTR pszString; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v15[4]; // [rsp+30h] [rbp-40h] BYREF
  int v16; // [rsp+90h] [rbp+20h] BYREF
  int v17; // [rsp+94h] [rbp+24h]
  int piRet; // [rsp+98h] [rbp+28h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+38h] BYREF

  v17 = HIDWORD(this);
  DetailsFromCrudeCmdLine = 0;
  v16 = 0;
  v19 = 0;
  pszString = 0;
  v15[0] = 0;
  string = 0;
  piRet = 0;
  while ( !((unsigned int (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->Read)(a2, &v16) )
  {
    switch ( v16 )
    {
      case 1:
        DetailsFromCrudeCmdLine = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a2->lpVtbl->GetLocalName)(
                                    a2,
                                    &v19,
                                    0);
        if ( DetailsFromCrudeCmdLine < 0 )
          goto LABEL_43;
        v15[0] = 0;
        v7 = ((__int64 (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
               a2,
               L"Units",
               0);
        DetailsFromCrudeCmdLine = v7;
        if ( !v7 )
        {
          v7 = ((__int64 (__fastcall *)(struct IXmlReader *, _QWORD *, _QWORD))a2->lpVtbl->GetValue)(a2, v15, 0);
          goto LABEL_14;
        }
        if ( v7 != 1 )
          goto LABEL_15;
LABEL_41:
        DetailsFromCrudeCmdLine = 0;
        break;
      case 3:
        DetailsFromCrudeCmdLine = ((__int64 (__fastcall *)(struct IXmlReader *, PCWSTR *, _QWORD))a2->lpVtbl->GetValue)(
                                    a2,
                                    &pszString,
                                    0);
        if ( DetailsFromCrudeCmdLine < 0 )
          goto LABEL_43;
        if ( (unsigned int)_o__wcsicmp(v19, L"DiskUsage") )
        {
          if ( (unsigned int)_o__wcsicmp(v19, L"CpuUsage") )
          {
            if ( (unsigned int)_o__wcsicmp(v19, L"StartTime") )
            {
              if ( (unsigned int)_o__wcsicmp(v19, L"ParentPID") )
              {
                if ( !(unsigned int)_o__wcsicmp(v19, L"ParentStartTime") )
                {
                  v11 = (struct _FILETIME *)((char *)a3 + 2080);
                  goto LABEL_28;
                }
                if ( !(unsigned int)_o__wcsicmp(v19, L"CommandLine") )
                  goto LABEL_12;
              }
              else if ( StrToIntExW(pszString, 0, &piRet) )
              {
                if ( piRet < 0 )
                {
                  *((_DWORD *)a3 + 519) = -1;
                  DetailsFromCrudeCmdLine = -2147024362;
                  goto LABEL_43;
                }
                *((_DWORD *)a3 + 519) = piRet;
                goto LABEL_41;
              }
            }
            else
            {
              v11 = (struct _FILETIME *)((char *)a3 + 2068);
LABEL_28:
              v7 = CStartupImpactHelper::ConvertStrToTime(v10, pszString, v11);
LABEL_14:
              DetailsFromCrudeCmdLine = v7;
LABEL_15:
              if ( v7 < 0 )
                goto LABEL_43;
            }
          }
          else
          {
            v9 = _o_wcstod(pszString, 0);
            if ( v15[0] && !(unsigned int)_o__wcsicmp(v15[0], L"us") )
              *((double *)a3 + 262) = v9 / 1000.0;
          }
        }
        else
        {
          v8 = _o_wcstod(pszString, 0);
          if ( v15[0] && !(unsigned int)_o__wcsicmp(v15[0], L"bytes") )
            *((double *)a3 + 261) = v8 * 0.00000095367431640625;
        }
        break;
      case 4:
        if ( !(unsigned int)_o__wcsicmp(v19, L"CommandLine") )
        {
          DetailsFromCrudeCmdLine = ((__int64 (__fastcall *)(struct IXmlReader *, PCWSTR *, _QWORD))a2->lpVtbl->GetValue)(
                                      a2,
                                      &pszString,
                                      0);
          if ( DetailsFromCrudeCmdLine < 0 )
            goto LABEL_43;
LABEL_12:
          WindowsDeleteString(string);
          string = 0;
          DetailsFromCrudeCmdLine = TmGetDetailsFromCrudeCmdLine(pszString, &string, 0, 0);
          if ( DetailsFromCrudeCmdLine < 0 )
            goto LABEL_43;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v7 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x400u, StringRawBuffer);
          goto LABEL_14;
        }
        break;
      case 15:
        v15[0] = 0;
        DetailsFromCrudeCmdLine = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a2->lpVtbl->GetLocalName)(
                                    a2,
                                    &v19,
                                    0);
        if ( DetailsFromCrudeCmdLine < 0 )
          goto LABEL_43;
        if ( !(unsigned int)_o__wcsicmp(v19, L"Process") )
        {
          DetailsFromCrudeCmdLine = 0;
          goto LABEL_43;
        }
        break;
    }
  }
LABEL_43:
  WindowsDeleteString(string);
  return (unsigned int)DetailsFromCrudeCmdLine;
}

```

## disassembly

```asm
0x1800d9f98  mov     rax, rsp
0x1800d9f9b  mov     [rax+18h], rbx
0x1800d9f9f  mov     [rax+8], rcx
0x1800d9fa3  push    rbp
0x1800d9fa4  push    rsi
0x1800d9fa5  push    rdi
0x1800d9fa6  mov     rbp, rsp
0x1800d9fa9  sub     rsp, 70h
0x1800d9fad  movaps  xmmword ptr [rax-28h], xmm6
0x1800d9fb1  movaps  xmmword ptr [rax-38h], xmm7
0x1800d9fb5  movaps  xmmword ptr [rax-48h], xmm8
0x1800d9fba  mov     rdi, r8
0x1800d9fbd  mov     rsi, rdx
0x1800d9fc0  xor     ebx, ebx
0x1800d9fc2  mov     [rbp+arg_0], ebx
0x1800d9fc5  mov     [rbp+arg_18], rbx
0x1800d9fc9  mov     [rbp+pszString], rbx
0x1800d9fcd  mov     [rbp+var_40], rbx
0x1800d9fd1  mov     [rbp+string], rbx
0x1800d9fd5  mov     [rbp+piRet], ebx
0x1800d9fd8  movsd   xmm7, cs:__real@3eb0000000000000
0x1800d9fe0  movsd   xmm8, cs:__real@408f400000000000
0x1800d9fe9  mov     rax, [rsi]
0x1800d9fec  lea     rdx, [rbp+arg_0]
0x1800d9ff0  mov     rcx, rsi
0x1800d9ff3  mov     rax, [rax+30h]
0x1800d9ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ffc  test    eax, eax
0x1800d9ffe  jnz     loc_1800DA2FA
0x1800da004  mov     ecx, [rbp+arg_0]
0x1800da007  sub     ecx, 1
0x1800da00a  jz      loc_1800DA27A
0x1800da010  sub     ecx, 2
0x1800da013  jz      loc_1800DA0FE
0x1800da019  sub     ecx, 1
0x1800da01c  jz      short loc_1800DA067
0x1800da01e  cmp     ecx, 0Bh
0x1800da021  jnz     short loc_1800D9FE9
0x1800da023  mov     [rbp+var_40], 0
0x1800da02b  mov     rax, [rsi]
0x1800da02e  xor     r8d, r8d
0x1800da031  lea     rdx, [rbp+arg_18]
0x1800da035  mov     rcx, rsi
0x1800da038  mov     rax, [rax+70h]
0x1800da03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da041  mov     ebx, eax
0x1800da043  test    eax, eax
0x1800da045  js      loc_1800DA2FA
0x1800da04b  lea     rdx, aProcess; "Process"
0x1800da052  mov     rcx, [rbp+arg_18]
0x1800da056  call    cs:__imp__o__wcsicmp
0x1800da05c  test    eax, eax
0x1800da05e  jnz     short loc_1800D9FE9
0x1800da060  xor     ebx, ebx
0x1800da062  jmp     loc_1800DA2FA
0x1800da067  lea     rdx, aCommandline; "CommandLine"
0x1800da06e  mov     rcx, [rbp+arg_18]
0x1800da072  call    cs:__imp__o__wcsicmp
0x1800da078  test    eax, eax
0x1800da07a  jnz     loc_1800D9FE9
0x1800da080  mov     rax, [rsi]
0x1800da083  xor     r8d, r8d
0x1800da086  lea     rdx, [rbp+pszString]
0x1800da08a  mov     rcx, rsi
0x1800da08d  mov     rax, [rax+80h]
0x1800da094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da099  mov     ebx, eax
0x1800da09b  test    eax, eax
0x1800da09d  js      loc_1800DA2FA
0x1800da0a3  mov     rcx, [rbp+string]; string
0x1800da0a7  call    cs:__imp_WindowsDeleteString
0x1800da0ad  mov     [rbp+string], 0
0x1800da0b5  xor     r9d, r9d; HSTRING *
0x1800da0b8  xor     r8d, r8d; HSTRING *
0x1800da0bb  lea     rdx, [rbp+string]; HSTRING *
0x1800da0bf  mov     rcx, [rbp+pszString]; unsigned __int16 *
0x1800da0c3  call    ?TmGetDetailsFromCrudeCmdLine@@YAJPEBGPEAPEAUHSTRING__@@11@Z; TmGetDetailsFromCrudeCmdLine(ushort const *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800da0c8  mov     ebx, eax
0x1800da0ca  test    eax, eax
0x1800da0cc  js      loc_1800DA2FA
0x1800da0d2  xor     edx, edx; length
0x1800da0d4  mov     rcx, [rbp+string]; string
0x1800da0d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800da0de  lea     rcx, [rdi+10h]; unsigned __int16 *
0x1800da0e2  mov     r8, rax; unsigned __int16 *
0x1800da0e5  mov     edx, 400h; unsigned __int64
0x1800da0ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800da0ef  mov     ebx, eax
0x1800da0f1  test    eax, eax
0x1800da0f3  jns     loc_1800D9FE9
0x1800da0f9  jmp     loc_1800DA2FA
0x1800da0fe  mov     rax, [rsi]
0x1800da101  xor     r8d, r8d
0x1800da104  lea     rdx, [rbp+pszString]
0x1800da108  mov     rcx, rsi
0x1800da10b  mov     rax, [rax+80h]
0x1800da112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da117  mov     ebx, eax
0x1800da119  test    eax, eax
0x1800da11b  js      loc_1800DA2FA
0x1800da121  lea     rdx, aDiskusage; "DiskUsage"
0x1800da128  mov     rcx, [rbp+arg_18]
0x1800da12c  call    cs:__imp__o__wcsicmp
0x1800da132  test    eax, eax
0x1800da134  jnz     short loc_1800DA178
0x1800da136  xor     edx, edx
0x1800da138  mov     rcx, [rbp+pszString]
0x1800da13c  call    cs:__imp__o_wcstod
0x1800da142  movaps  xmm6, xmm0
0x1800da145  mov     rcx, [rbp+var_40]
0x1800da149  test    rcx, rcx
0x1800da14c  jz      loc_1800D9FE9
0x1800da152  lea     rdx, aBytes; "bytes"
0x1800da159  call    cs:__imp__o__wcsicmp
0x1800da15f  test    eax, eax
0x1800da161  jnz     loc_1800D9FE9
0x1800da167  mulsd   xmm6, xmm7
0x1800da16b  movsd   qword ptr [rdi+828h], xmm6
0x1800da173  jmp     loc_1800D9FE9
0x1800da178  lea     rdx, aCpuusage; "CpuUsage"
0x1800da17f  mov     rcx, [rbp+arg_18]
0x1800da183  call    cs:__imp__o__wcsicmp
0x1800da189  test    eax, eax
0x1800da18b  jnz     short loc_1800DA1D0
0x1800da18d  xor     edx, edx
0x1800da18f  mov     rcx, [rbp+pszString]
0x1800da193  call    cs:__imp__o_wcstod
0x1800da199  movaps  xmm6, xmm0
0x1800da19c  mov     rcx, [rbp+var_40]
0x1800da1a0  test    rcx, rcx
0x1800da1a3  jz      loc_1800D9FE9
0x1800da1a9  lea     rdx, aUs; "us"
0x1800da1b0  call    cs:__imp__o__wcsicmp
0x1800da1b6  test    eax, eax
0x1800da1b8  jnz     loc_1800D9FE9
0x1800da1be  divsd   xmm6, xmm8
0x1800da1c3  movsd   qword ptr [rdi+830h], xmm6
0x1800da1cb  jmp     loc_1800D9FE9
0x1800da1d0  lea     rdx, aStarttime; "StartTime"
0x1800da1d7  mov     rcx, [rbp+arg_18]
0x1800da1db  call    cs:__imp__o__wcsicmp
0x1800da1e1  test    eax, eax
0x1800da1e3  jnz     short loc_1800DA1FA
0x1800da1e5  lea     r8, [rdi+814h]; struct _FILETIME *
0x1800da1ec  mov     rdx, [rbp+pszString]; unsigned __int16 *
0x1800da1f0  call    ?ConvertStrToTime@CStartupImpactHelper@@AEAAJPEBGPEAU_FILETIME@@@Z; CStartupImpactHelper::ConvertStrToTime(ushort const *,_FILETIME *)
0x1800da1f5  jmp     loc_1800DA0EF
0x1800da1fa  lea     rdx, aParentpid; "ParentPID"
0x1800da201  mov     rcx, [rbp+arg_18]
0x1800da205  call    cs:__imp__o__wcsicmp
0x1800da20b  test    eax, eax
0x1800da20d  jnz     short loc_1800DA23E
0x1800da20f  lea     r8, [rbp+piRet]; piRet
0x1800da213  xor     edx, edx; dwFlags
0x1800da215  mov     rcx, [rbp+pszString]; pszString
0x1800da219  call    cs:__imp_StrToIntExW
0x1800da21f  cmp     eax, 1
0x1800da222  jnz     loc_1800D9FE9
0x1800da228  mov     eax, [rbp+piRet]
0x1800da22b  test    eax, eax
0x1800da22d  js      loc_1800DA2EB
0x1800da233  mov     [rdi+81Ch], eax
0x1800da239  jmp     loc_1800DA2E4
0x1800da23e  lea     rdx, aParentstarttim; "ParentStartTime"
0x1800da245  mov     rcx, [rbp+arg_18]
0x1800da249  call    cs:__imp__o__wcsicmp
0x1800da24f  test    eax, eax
0x1800da251  jnz     short loc_1800DA25C
0x1800da253  lea     r8, [rdi+820h]
0x1800da25a  jmp     short loc_1800DA1EC
0x1800da25c  lea     rdx, aCommandline; "CommandLine"
0x1800da263  mov     rcx, [rbp+arg_18]
0x1800da267  call    cs:__imp__o__wcsicmp
0x1800da26d  test    eax, eax
0x1800da26f  jnz     loc_1800D9FE9
0x1800da275  jmp     loc_1800DA0A3
0x1800da27a  mov     rax, [rsi]
0x1800da27d  xor     r8d, r8d
0x1800da280  lea     rdx, [rbp+arg_18]
0x1800da284  mov     rcx, rsi
0x1800da287  mov     rax, [rax+70h]
0x1800da28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da290  mov     ebx, eax
0x1800da292  test    eax, eax
0x1800da294  js      short loc_1800DA2FA
0x1800da296  mov     [rbp+var_40], 0
0x1800da29e  mov     rax, [rsi]
0x1800da2a1  xor     r8d, r8d
0x1800da2a4  lea     rdx, aUnits; "Units"
0x1800da2ab  mov     rcx, rsi
0x1800da2ae  mov     rax, [rax+50h]
0x1800da2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2b7  mov     ebx, eax
0x1800da2b9  test    eax, eax
0x1800da2bb  jnz     short loc_1800DA2DB
0x1800da2bd  mov     rax, [rsi]
0x1800da2c0  xor     r8d, r8d
0x1800da2c3  lea     rdx, [rbp+var_40]
0x1800da2c7  mov     rcx, rsi
0x1800da2ca  mov     rax, [rax+80h]
0x1800da2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2d6  jmp     loc_1800DA0EF
0x1800da2db  cmp     eax, 1
0x1800da2de  jnz     loc_1800DA0F1
0x1800da2e4  xor     ebx, ebx
0x1800da2e6  jmp     loc_1800D9FE9
0x1800da2eb  mov     dword ptr [rdi+81Ch], 0FFFFFFFFh
0x1800da2f5  mov     ebx, 80070216h
0x1800da2fa  mov     rcx, [rbp+string]; string
0x1800da2fe  call    cs:__imp_WindowsDeleteString
0x1800da304  mov     eax, ebx
0x1800da306  lea     r11, [rsp+70h+var_s0]
0x1800da30b  mov     rbx, [r11+30h]
0x1800da30f  movaps  xmm6, [rsp+70h+var_10]
0x1800da314  movaps  xmm7, [rsp+70h+var_20]
0x1800da319  movaps  xmm8, xmmword ptr [r11-30h]
0x1800da31e  mov     rsp, r11
0x1800da321  pop     rdi
0x1800da322  pop     rsi
0x1800da323  pop     rbp
0x1800da324  retn
```
