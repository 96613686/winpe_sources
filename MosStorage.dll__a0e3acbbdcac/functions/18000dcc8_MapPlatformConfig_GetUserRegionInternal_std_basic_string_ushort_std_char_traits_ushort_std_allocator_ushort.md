# MapPlatformConfig::GetUserRegionInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000dcc8`
- end: `0x18000dec8`
- name: `?GetUserRegionInternal@MapPlatformConfig@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d8b8`

## callees

- `0x180001c80`
- `0x18000c860`
- `0x18000dcc8`
- `0x18000e7e0`
- `0x18000e7f8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dd22`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dd22`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000de6f`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000de6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000de05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000de05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dd0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dd0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dddd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dddd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de7c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000dd5b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000dd5b`

## string_xrefs

- `0x18000de68`: `MapPlatformConfig::GetUserRegionInternal`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetUserRegionInternal(__int64 a1)
{
  int v2; // ebx
  int v3; // r8d
  int v4; // ecx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  char *v12; // r15
  __int64 v13; // rbx
  wil *v14; // rcx
  __int64 v15; // rcx
  int v17; // eax
  __int64 v18; // [rsp+20h] [rbp-58h] BYREF
  __int64 v19; // [rsp+28h] [rbp-50h] BYREF
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER v22; // [rsp+40h] [rbp-38h] BYREF

  v18 = 0;
  string = 0;
  if ( WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &v22, &v21) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v18 = 0;
  v19 = 0;
  v2 = RoActivateInstance(v21, &v19);
  if ( v2 >= 0 )
  {
    if ( !memcmp_0(&GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v18 = v19;
    }
    else
    {
      v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
             v19,
             &GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903,
             &v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  if ( v2 < 0 )
  {
    v3 = 185;
    v4 = v2;
LABEL_19:
    v8 = ZTraceReportOriginationNoThis(v4, "MapPlatformConfig::GetUserRegionInternal", v3);
    goto LABEL_20;
  }
  v5 = v18;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  v7 = v6(v5, &string);
  if ( v7 < 0 )
  {
    v3 = 187;
    v4 = v7;
    goto LABEL_19;
  }
  v8 = 0;
  try
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v11 = -1;
    do
      ++v11;
    while ( StringRawBuffer[v11] );
    if ( v11 > *(_QWORD *)(a1 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a1,
        v11,
        v10,
        StringRawBuffer);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v12 = (char *)a1;
      else
        v12 = *(char **)a1;
      *(_QWORD *)(a1 + 16) = v11;
      v13 = 2 * v11;
      memmove_0(v12, StringRawBuffer, 2 * v11);
      *(_WORD *)&v12[v13] = 0;
    }
  }
  catch ( ... )
  {
    v17 = wil::ResultFromCaughtException(v14);
    LODWORD(v19) = ZTraceReportOriginationNoThis(v17, "MapPlatformConfig::GetUserRegionInternal", 194);
    v8 = v19;
  }
LABEL_20:
  WindowsDeleteString(string);
  string = 0;
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v8;
}

```

## disassembly

```asm
0x18000dcc8  mov     r11, rsp
0x18000dccb  mov     [r11+10h], rbx
0x18000dccf  mov     [r11+18h], rsi
0x18000dcd3  push    rdi
0x18000dcd4  push    r14
0x18000dcd6  push    r15
0x18000dcd8  sub     rsp, 60h
0x18000dcdc  mov     rax, cs:__security_cookie
0x18000dce3  xor     rax, rsp
0x18000dce6  mov     [rsp+78h+var_20], rax
0x18000dceb  mov     r14, rcx
0x18000dcee  xor     esi, esi
0x18000dcf0  mov     [r11-58h], rsi
0x18000dcf4  mov     [r11-48h], rsi
0x18000dcf8  lea     r9, [r11-40h]; string
0x18000dcfc  lea     r8, [r11-38h]; hstringHeader
0x18000dd00  lea     edx, [rsi+26h]; length
0x18000dd03  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18000dd0a  call    cs:__imp_WindowsCreateStringReference
0x18000dd10  test    eax, eax
0x18000dd12  jns     short loc_18000DD28
0x18000dd14  xor     r9d, r9d; lpArguments
0x18000dd17  xor     r8d, r8d; nNumberOfArguments
0x18000dd1a  lea     edx, [rsi+1]; dwExceptionFlags
0x18000dd1d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000dd22  call    cs:__imp_RaiseException
0x18000dd28  mov     rbx, [rsp+78h+var_40]
0x18000dd2d  mov     rcx, [rsp+78h+var_58]
0x18000dd32  test    rcx, rcx
0x18000dd35  jz      short loc_18000DD49
0x18000dd37  mov     [rsp+78h+var_58], rsi
0x18000dd3c  mov     rax, [rcx]
0x18000dd3f  mov     rax, [rax+10h]
0x18000dd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd48  nop
0x18000dd49  mov     [rsp+78h+var_58], rsi
0x18000dd4e  mov     [rsp+78h+var_50], rsi
0x18000dd53  lea     rdx, [rsp+78h+var_50]
0x18000dd58  mov     rcx, rbx
0x18000dd5b  call    cs:__imp_RoActivateInstance
0x18000dd61  mov     ebx, eax
0x18000dd63  test    eax, eax
0x18000dd65  js      short loc_18000DDBB
0x18000dd67  mov     r8d, 10h; Size
0x18000dd6d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000dd74  lea     rcx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903; Buf1
0x18000dd7b  call    memcmp_0
0x18000dd80  mov     rcx, [rsp+78h+var_50]
0x18000dd85  test    eax, eax
0x18000dd87  jnz     short loc_18000DD90
0x18000dd89  mov     [rsp+78h+var_58], rcx
0x18000dd8e  jmp     short loc_18000DDBB
0x18000dd90  mov     rax, [rcx]
0x18000dd93  lea     r8, [rsp+78h+var_58]
0x18000dd98  lea     rdx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903
0x18000dd9f  mov     rax, [rax]
0x18000dda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda7  mov     ebx, eax
0x18000dda9  mov     rcx, [rsp+78h+var_50]
0x18000ddae  mov     rax, [rcx]
0x18000ddb1  mov     rax, [rax+10h]
0x18000ddb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddba  nop
0x18000ddbb  test    ebx, ebx
0x18000ddbd  jns     short loc_18000DDCC
0x18000ddbf  mov     r8d, 0B9h
0x18000ddc5  mov     ecx, ebx
0x18000ddc7  jmp     loc_18000DE68
0x18000ddcc  mov     rdi, [rsp+78h+var_58]
0x18000ddd1  mov     rax, [rdi]
0x18000ddd4  mov     rbx, [rax+40h]
0x18000ddd8  mov     rcx, [rsp+78h+string]; string
0x18000dddd  call    cs:__imp_WindowsDeleteString
0x18000dde3  mov     [rsp+78h+string], rsi
0x18000dde8  lea     rdx, [rsp+78h+string]
0x18000dded  mov     rcx, rdi
0x18000ddf0  mov     rax, rbx
0x18000ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf8  test    eax, eax
0x18000ddfa  js      short loc_18000DE60
0x18000ddfc  mov     edi, esi
0x18000ddfe  xor     edx, edx; length
0x18000de00  mov     rcx, [rsp+78h+string]; string
0x18000de05  call    cs:__imp_WindowsGetStringRawBuffer
0x18000de0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000de0f  inc     rdx
0x18000de12  cmp     [rax+rdx*2], si
0x18000de16  jnz     short loc_18000DE0F
0x18000de18  cmp     rdx, [r14+18h]
0x18000de1c  ja      short loc_18000DE4A
0x18000de1e  cmp     qword ptr [r14+18h], 7
0x18000de23  jbe     short loc_18000DE2A
0x18000de25  mov     r15, [r14]
0x18000de28  jmp     short loc_18000DE2D
0x18000de2a  mov     r15, r14
0x18000de2d  mov     [r14+10h], rdx
0x18000de31  lea     rbx, [rdx+rdx]
0x18000de35  mov     r8, rbx; Size
0x18000de38  mov     rdx, rax; Src
0x18000de3b  mov     rcx, r15; void *
0x18000de3e  call    memmove_0
0x18000de43  mov     [rbx+r15], si
0x18000de48  jmp     short loc_18000DE56
0x18000de4a  mov     r9, rax
0x18000de4d  mov     rcx, r14
0x18000de50  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000de55  nop
0x18000de56  jmp     short loc_18000DE77
0x18000de58  xor     esi, esi
0x18000de5a  mov     edi, dword ptr [rsp+78h+var_50]
0x18000de5e  jmp     short loc_18000DE77
0x18000de60  mov     r8d, 0BBh
0x18000de66  mov     ecx, eax
0x18000de68  lea     rdx, aMapplatformcon; "MapPlatformConfig::GetUserRegionInterna"...
0x18000de6f  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000de75  mov     edi, eax
0x18000de77  mov     rcx, [rsp+78h+string]; string
0x18000de7c  call    cs:__imp_WindowsDeleteString
0x18000de82  mov     [rsp+78h+string], rsi
0x18000de87  mov     rcx, [rsp+78h+var_58]
0x18000de8c  test    rcx, rcx
0x18000de8f  jz      short loc_18000DEA3
0x18000de91  mov     [rsp+78h+var_58], rsi
0x18000de96  mov     rax, [rcx]
0x18000de99  mov     rax, [rax+10h]
0x18000de9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dea2  nop
0x18000dea3  mov     eax, edi
0x18000dea5  mov     rcx, [rsp+78h+var_20]
0x18000deaa  xor     rcx, rsp; StackCookie
0x18000dead  call    __security_check_cookie
0x18000deb2  lea     r11, [rsp+78h+var_18]
0x18000deb7  mov     rbx, [r11+28h]
0x18000debb  mov     rsi, [r11+30h]
0x18000debf  mov     rsp, r11
0x18000dec2  pop     r15
0x18000dec4  pop     r14
0x18000dec6  pop     rdi
0x18000dec7  retn
```
