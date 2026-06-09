# CSession::_GetReaderKind(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,Windows::Devices::SmartCards::SmartCardReaderKind &)

- ea: `0x18000dda0`
- end: `0x18000e157`
- name: `?_GetReaderKind@CSession@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4SmartCardReaderKind@SmartCards@Devices@Windows@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000cf60`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x18000c874`
- `0x18000d06c`
- `0x18000d4f0`
- `0x18000d890`
- `0x18000dda0`
- `0x18000f844`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e02b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e10e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e02b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e10e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000de32`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000de32`
- `WinSCard!SCardEstablishContext` at `0x18000dede`
- `WinSCard!SCardEstablishContext` at `0x18000dede`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x18000df9a`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x18000df9a`

## string_xrefs

- `0x18000ddc6`: `CSession::_GetReaderKind`

## pseudocode

```c
__int64 __fastcall CSession::_GetReaderKind(__int64 a1, _QWORD *a2, int *a3)
{
  void *v6; // rdx
  signed int LastError; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v11; // eax
  bool v12; // cf
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  LONG DeviceTypeIdW; // [rsp+30h] [rbp-49h] BYREF
  void **v23; // [rsp+38h] [rbp-41h] BYREF
  SCARDCONTEXT phContext; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v26; // [rsp+4Ch] [rbp-2Dh] BYREF
  _QWORD *v27; // [rsp+50h] [rbp-29h] BYREF
  LONG *v28; // [rsp+58h] [rbp-21h] BYREF
  __int16 v29; // [rsp+60h] [rbp-19h]
  _QWORD v30[3]; // [rsp+68h] [rbp-11h] BYREF
  char v31[32]; // [rsp+80h] [rbp+7h] BYREF

  v30[0] = v31;
  DeviceTypeIdW = 0;
  v30[1] = &v25;
  v25 = 0;
  strcpy(v31, "CSession::_GetReaderKind");
  v30[2] = &DeviceTypeIdW;
  lambda_b8f1e8e03e8d3ba79384b7eb640514dd_::operator()(v30);
  *a3 = 0;
  v6 = *(void **)(a1 + 24);
  v27 = v30;
  v25 = 1;
  if ( !SetThreadToken(0, v6) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DeviceTypeIdW = LastError;
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        DeviceTypeIdW);
    }
LABEL_56:
    v10 = DeviceTypeIdW;
    goto LABEL_57;
  }
  v29 = 258;
  v28 = &DeviceTypeIdW;
  v23 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
  phContext = 0;
  DeviceTypeIdW = SCardEstablishContext(0, 0, 0, &phContext);
  if ( !DeviceTypeIdW )
  {
    v12 = a2[3] < 8u;
    v26 = 0;
    if ( v12 )
      v13 = a2;
    else
      v13 = (_QWORD *)*a2;
    DeviceTypeIdW = SCardGetDeviceTypeIdW(phContext, v13, &v26);
    if ( DeviceTypeIdW )
    {
      WppTraceIndent(v14, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
          (_DWORD)WPP_pszIndent,
          DeviceTypeIdW);
      }
      v10 = DeviceTypeIdW;
      v23 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
      if ( !phContext )
        goto LABEL_32;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v23) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        RaiseException(v15, 1u, 0, 0);
        __debugbreak();
      }
      goto LABEL_31;
    }
    v16 = v26;
    if ( v26 != 128 )
    {
      if ( v26 == 256 )
      {
        v17 = 3;
        goto LABEL_43;
      }
      if ( v26 == 512 )
      {
        v17 = 4;
        goto LABEL_43;
      }
      if ( v26 != 1024 )
      {
        v17 = 5;
        if ( v26 != 2048 )
          v17 = 1;
        goto LABEL_43;
      }
    }
    v17 = 2;
LABEL_43:
    *a3 = v17;
    WppTraceIndent(v16, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( a2[3] >= 8u )
        a2 = (_QWORD *)*a2;
      WPP_SF_sSL(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)WPP_pszIndent, (__int64)a2, *a3);
    }
    v23 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
    if ( phContext )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v23) )
      {
        v20 = GetLastError();
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        RaiseException(v20, 1u, 0, 0);
        __debugbreak();
      }
      phContext = 0;
    }
    wil::details::ScopeExitFnGuard__lambda_33c973db47aa98135e43f600059bdb99___::operator()(&v28);
    goto LABEL_56;
  }
  WppTraceIndent(v9, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
      (_DWORD)WPP_pszIndent,
      DeviceTypeIdW);
  }
  v10 = DeviceTypeIdW;
  v23 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
  if ( !phContext )
    goto LABEL_32;
  if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v23) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
LABEL_31:
  phContext = 0;
LABEL_32:
  wil::details::ScopeExitFnGuard__lambda_33c973db47aa98135e43f600059bdb99___::operator()(&v28);
LABEL_57:
  WppTraceUnwinder__lambda_b8f1e8e03e8d3ba79384b7eb640514dd____::_WppTraceUnwinder__lambda_b8f1e8e03e8d3ba79384b7eb640514dd____(&v27);
  return v10;
}

```

## disassembly

```asm
0x18000dda0  mov     [rsp-8+arg_18], rbx
0x18000dda5  push    rbp
0x18000dda6  push    rsi
0x18000dda7  push    rdi
0x18000dda8  push    r12
0x18000ddaa  push    r15
0x18000ddac  lea     rbp, [rsp-37h]
0x18000ddb1  sub     rsp, 0B0h
0x18000ddb8  mov     rax, cs:__security_cookie
0x18000ddbf  xor     rax, rsp
0x18000ddc2  mov     [rbp+57h+var_30], rax
0x18000ddc6  movups  xmm0, xmmword ptr cs:aCsessionGetrea; "CSession::_GetReaderKind"
0x18000ddcd  lea     rax, [rbp+57h+var_50]
0x18000ddd1  mov     rbx, rcx
0x18000ddd4  movups  xmm1, xmmword ptr cs:aCsessionGetrea+9; ":_GetReaderKind"
0x18000dddb  mov     [rbp+57h+var_68], rax
0x18000dddf  lea     rcx, [rbp+57h+var_68]
0x18000dde3  lea     rax, [rbp+57h+var_88]
0x18000dde7  mov     [rbp+57h+var_A0], 0
0x18000ddee  mov     [rbp+57h+var_60], rax
0x18000ddf2  mov     rsi, r8
0x18000ddf5  lea     rax, [rbp+57h+var_A0]
0x18000ddf9  mov     [rbp+57h+var_88], 0
0x18000de00  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000de04  mov     [rbp+57h+var_58], rax
0x18000de08  mov     rdi, rdx
0x18000de0b  movups  xmmword ptr [rbp+57h+var_50+9], xmm1
0x18000de0f  call    _lambda_b8f1e8e03e8d3ba79384b7eb640514dd___operator__
0x18000de14  lea     rax, [rbp+57h+var_68]
0x18000de18  mov     dword ptr [rsi], 0
0x18000de1e  mov     rdx, [rbx+18h]; Token
0x18000de22  mov     r15d, 1
0x18000de28  xor     ecx, ecx; Thread
0x18000de2a  mov     [rbp+57h+var_80], rax
0x18000de2e  mov     [rbp+57h+var_88], r15d
0x18000de32  call    cs:__imp_SetThreadToken
0x18000de38  test    eax, eax
0x18000de3a  jnz     short loc_18000DEAD
0x18000de3c  call    cs:__imp_GetLastError
0x18000de42  test    eax, eax
0x18000de44  jle     short loc_18000DE4E
0x18000de46  movzx   eax, ax
0x18000de49  or      eax, 80070000h
0x18000de4e  mov     ebx, 2
0x18000de53  mov     [rbp+57h+var_A0], eax
0x18000de56  mov     edx, ebx
0x18000de58  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000de5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de64  lea     rax, WPP_GLOBAL_Control
0x18000de6b  cmp     rcx, rax
0x18000de6e  jz      loc_18000E126
0x18000de74  test    [rcx+1Ch], r15b
0x18000de78  jz      loc_18000E126
0x18000de7e  cmp     [rcx+19h], bl
0x18000de81  jb      loc_18000E126
0x18000de87  mov     eax, [rbp+57h+var_A0]
0x18000de8a  lea     edx, [rbx+18h]
0x18000de8d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000de94  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000de9b  mov     rcx, [rcx+10h]
0x18000de9f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000dea3  call    WPP_SF_sd
0x18000dea8  jmp     loc_18000E126
0x18000dead  lea     rax, [rbp+57h+var_A0]
0x18000deb1  mov     [rbp+57h+var_70], 102h
0x18000deb7  lea     r12, ??_7?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable'
0x18000debe  mov     [rbp+57h+var_78], rax
0x18000dec2  lea     r9, [rbp+57h+phContext]; phContext
0x18000dec6  mov     [rbp+57h+var_98], r12
0x18000deca  xor     r8d, r8d; pvReserved2
0x18000decd  mov     [rbp+57h+phContext], 0
0x18000ded5  xor     edx, edx; pvReserved1
0x18000ded7  xor     ecx, ecx; dwScope
0x18000ded9  mov     ebx, 2
0x18000dede  call    cs:__imp_SCardEstablishContext
0x18000dee4  mov     [rbp+57h+var_A0], eax
0x18000dee7  test    eax, eax
0x18000dee9  jz      loc_18000DF7C
0x18000deef  mov     edx, ebx
0x18000def1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000def6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000defd  lea     rax, WPP_GLOBAL_Control
0x18000df04  cmp     rcx, rax
0x18000df07  jz      short loc_18000DF35
0x18000df09  test    [rcx+1Ch], r15b
0x18000df0d  jz      short loc_18000DF35
0x18000df0f  cmp     [rcx+19h], bl
0x18000df12  jb      short loc_18000DF35
0x18000df14  mov     eax, [rbp+57h+var_A0]
0x18000df17  lea     edx, [rbx+19h]
0x18000df1a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000df21  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000df28  mov     rcx, [rcx+10h]
0x18000df2c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000df30  call    WPP_SF_sd
0x18000df35  cmp     [rbp+57h+phContext], 0
0x18000df3a  mov     ebx, [rbp+57h+var_A0]
0x18000df3d  mov     [rbp+57h+var_98], r12
0x18000df41  jz      loc_18000E03A
0x18000df47  lea     rcx, [rbp+57h+var_98]
0x18000df4b  call    ?InternalClose@?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(void)
0x18000df50  test    al, al
0x18000df52  jnz     loc_18000E032
0x18000df58  call    cs:__imp_GetLastError
0x18000df5e  test    eax, eax
0x18000df60  jle     short loc_18000DF6A
0x18000df62  movzx   eax, ax
0x18000df65  or      eax, 80070000h
0x18000df6a  xor     r9d, r9d; lpArguments
0x18000df6d  xor     r8d, r8d; nNumberOfArguments
0x18000df70  mov     edx, r15d; dwExceptionFlags
0x18000df73  mov     ecx, eax; dwExceptionCode
0x18000df75  call    cs:__imp_RaiseException
0x18000df7b  int     3; Trap to Debugger
0x18000df7c  cmp     qword ptr [rdi+18h], 8
0x18000df81  mov     [rbp+57h+var_84], 0
0x18000df88  jb      short loc_18000DF8F
0x18000df8a  mov     rdx, [rdi]
0x18000df8d  jmp     short loc_18000DF92
0x18000df8f  mov     rdx, rdi
0x18000df92  mov     rcx, [rbp+57h+phContext]
0x18000df96  lea     r8, [rbp+57h+var_84]
0x18000df9a  call    cs:__imp_SCardGetDeviceTypeIdW
0x18000dfa0  mov     [rbp+57h+var_A0], eax
0x18000dfa3  test    eax, eax
0x18000dfa5  jz      loc_18000E048
0x18000dfab  mov     edx, ebx
0x18000dfad  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000dfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfb9  lea     rax, WPP_GLOBAL_Control
0x18000dfc0  cmp     rcx, rax
0x18000dfc3  jz      short loc_18000DFF3
0x18000dfc5  test    [rcx+1Ch], r15b
0x18000dfc9  jz      short loc_18000DFF3
0x18000dfcb  cmp     [rcx+19h], bl
0x18000dfce  jb      short loc_18000DFF3
0x18000dfd0  mov     eax, [rbp+57h+var_A0]
0x18000dfd3  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000dfda  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000dfe1  mov     edx, 1Ch
0x18000dfe6  mov     rcx, [rcx+10h]
0x18000dfea  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000dfee  call    WPP_SF_sd
0x18000dff3  cmp     [rbp+57h+phContext], 0
0x18000dff8  mov     ebx, [rbp+57h+var_A0]
0x18000dffb  mov     [rbp+57h+var_98], r12
0x18000dfff  jz      short loc_18000E03A
0x18000e001  lea     rcx, [rbp+57h+var_98]
0x18000e005  call    ?InternalClose@?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(void)
0x18000e00a  test    al, al
0x18000e00c  jnz     short loc_18000E032
0x18000e00e  call    cs:__imp_GetLastError
0x18000e014  test    eax, eax
0x18000e016  jle     short loc_18000E020
0x18000e018  movzx   eax, ax
0x18000e01b  or      eax, 80070000h
0x18000e020  xor     r9d, r9d; lpArguments
0x18000e023  xor     r8d, r8d; nNumberOfArguments
0x18000e026  mov     edx, r15d; dwExceptionFlags
0x18000e029  mov     ecx, eax; dwExceptionCode
0x18000e02b  call    cs:__imp_RaiseException
0x18000e031  int     3; Trap to Debugger
0x18000e032  mov     [rbp+57h+phContext], 0
0x18000e03a  lea     rcx, [rbp+57h+var_78]
0x18000e03e  call    wil__details__ScopeExitFnGuard__lambda_33c973db47aa98135e43f600059bdb99_____operator__
0x18000e043  jmp     loc_18000E129
0x18000e048  mov     ecx, [rbp+57h+var_84]
0x18000e04b  cmp     ecx, 80h
0x18000e051  jz      short loc_18000E08A
0x18000e053  cmp     ecx, 100h
0x18000e059  jz      short loc_18000E083
0x18000e05b  cmp     ecx, 200h
0x18000e061  jz      short loc_18000E07C
0x18000e063  cmp     ecx, 400h
0x18000e069  jz      short loc_18000E08A
0x18000e06b  cmp     ecx, 800h
0x18000e071  mov     eax, 5
0x18000e076  cmovnz  eax, r15d
0x18000e07a  jmp     short loc_18000E08C
0x18000e07c  mov     eax, 4
0x18000e081  jmp     short loc_18000E08C
0x18000e083  mov     eax, 3
0x18000e088  jmp     short loc_18000E08C
0x18000e08a  mov     eax, ebx
0x18000e08c  mov     edx, ebx
0x18000e08e  mov     [rsi], eax
0x18000e090  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e095  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e09c  lea     rax, WPP_GLOBAL_Control
0x18000e0a3  cmp     rcx, rax
0x18000e0a6  jz      short loc_18000E0D9
0x18000e0a8  test    [rcx+1Ch], r15b
0x18000e0ac  jz      short loc_18000E0D9
0x18000e0ae  cmp     byte ptr [rcx+19h], 4
0x18000e0b2  jb      short loc_18000E0D9
0x18000e0b4  cmp     qword ptr [rdi+18h], 8
0x18000e0b9  mov     eax, [rsi]
0x18000e0bb  jb      short loc_18000E0C0
0x18000e0bd  mov     rdi, [rdi]
0x18000e0c0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000e0c7  mov     rcx, [rcx+10h]
0x18000e0cb  mov     [rsp+0D0h+var_A8], eax
0x18000e0cf  mov     [rsp+0D0h+var_B0], rdi
0x18000e0d4  call    WPP_SF_sSL
0x18000e0d9  cmp     [rbp+57h+phContext], 0
0x18000e0de  mov     [rbp+57h+var_98], r12
0x18000e0e2  jz      short loc_18000E11D
0x18000e0e4  lea     rcx, [rbp+57h+var_98]
0x18000e0e8  call    ?InternalClose@?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(void)
0x18000e0ed  test    al, al
0x18000e0ef  jnz     short loc_18000E115
0x18000e0f1  call    cs:__imp_GetLastError
0x18000e0f7  test    eax, eax
0x18000e0f9  jle     short loc_18000E103
0x18000e0fb  movzx   eax, ax
0x18000e0fe  or      eax, 80070000h
0x18000e103  xor     r9d, r9d; lpArguments
0x18000e106  xor     r8d, r8d; nNumberOfArguments
0x18000e109  mov     edx, r15d; dwExceptionFlags
0x18000e10c  mov     ecx, eax; dwExceptionCode
0x18000e10e  call    cs:__imp_RaiseException
0x18000e114  int     3; Trap to Debugger
0x18000e115  mov     [rbp+57h+phContext], 0
0x18000e11d  lea     rcx, [rbp+57h+var_78]
0x18000e121  call    wil__details__ScopeExitFnGuard__lambda_33c973db47aa98135e43f600059bdb99_____operator__
0x18000e126  mov     ebx, [rbp+57h+var_A0]
0x18000e129  lea     rcx, [rbp+57h+var_80]
0x18000e12d  call    WppTraceUnwinder__lambda_b8f1e8e03e8d3ba79384b7eb640514dd_______WppTraceUnwinder__lambda_b8f1e8e03e8d3ba79384b7eb640514dd____
0x18000e132  mov     eax, ebx
0x18000e134  mov     rcx, [rbp+57h+var_30]
0x18000e138  xor     rcx, rsp; StackCookie
0x18000e13b  call    __security_check_cookie
0x18000e140  mov     rbx, [rsp+0D0h+arg_18]
0x18000e148  add     rsp, 0B0h
0x18000e14f  pop     r15
0x18000e151  pop     r12
0x18000e153  pop     rdi
0x18000e154  pop     rsi
0x18000e155  pop     rbp
0x18000e156  retn
```
