# MapPlatformConfig::GetSystemLocaleInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000db14`
- end: `0x18000dcbf`
- name: `?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `427`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d6c4`

## callees

- `0x180001c80`
- `0x18000c860`
- `0x18000db14`
- `0x18000e7f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbc`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000db59`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000dbb2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000db59`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000dbb2`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000db90`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000db90`

## string_xrefs

- `0x18000db87`: `MapPlatformConfig::GetSystemLocaleInfo`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetSystemLocaleInfo(__int64 a1, __int64 a2)
{
  signed int LastError; // eax
  int v5; // r8d
  unsigned int v6; // r14d
  __int64 v7; // r8
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  char *v10; // rbp
  __int64 v11; // rbx
  __int64 v12; // r8
  char *v13; // rbp
  WCHAR Src[88]; // [rsp+20h] [rbp-198h] BYREF
  WCHAR LCData[88]; // [rsp+D0h] [rbp-E8h] BYREF

  if ( GetLocaleInfoEx(L"!x-sys-default-locale", 0x5Cu, LCData, 85) <= 0 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 293;
    return (unsigned int)ZTraceReportOriginationNoThis(LastError, "MapPlatformConfig::GetSystemLocaleInfo", v5);
  }
  if ( GetLocaleInfoEx(L"!x-sys-default-locale", 0x5Au, Src, 85) <= 0 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 294;
    return (unsigned int)ZTraceReportOriginationNoThis(LastError, "MapPlatformConfig::GetSystemLocaleInfo", v5);
  }
  v8 = -1;
  v9 = -1;
  v6 = 0;
  do
    ++v9;
  while ( Src[v9] );
  if ( v9 > *(_QWORD *)(a1 + 24) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a1,
      v9,
      v7,
      Src);
  }
  else
  {
    if ( *(_QWORD *)(a1 + 24) <= 7u )
      v10 = (char *)a1;
    else
      v10 = *(char **)a1;
    *(_QWORD *)(a1 + 16) = v9;
    v11 = 2 * v9;
    memmove_0(v10, Src, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  do
    ++v8;
  while ( LCData[v8] );
  if ( v8 > *(_QWORD *)(a2 + 24) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      v8,
      v12,
      LCData);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v13 = (char *)a2;
    else
      v13 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = v8;
    memmove_0(v13, LCData, 2 * v8);
    *(_WORD *)&v13[2 * v8] = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000db14  mov     [rsp+arg_10], rbx
0x18000db19  push    rbp
0x18000db1a  push    rsi
0x18000db1b  push    rdi
0x18000db1c  push    r14
0x18000db1e  push    r15
0x18000db20  sub     rsp, 190h
0x18000db27  mov     rax, cs:__security_cookie
0x18000db2e  xor     rax, rsp
0x18000db31  mov     [rsp+1B8h+var_38], rax
0x18000db39  mov     edi, 55h ; 'U'
0x18000db3e  lea     r8, [rsp+1B8h+LCData]; lpLCData
0x18000db46  mov     rsi, rdx
0x18000db49  mov     rbx, rcx
0x18000db4c  mov     r9d, edi; cchData
0x18000db4f  lea     rcx, LocaleName; "!x-sys-default-locale"
0x18000db56  lea     edx, [rdi+7]; LCType
0x18000db59  call    cs:__imp_GetLocaleInfoEx
0x18000db5f  xor     r15d, r15d
0x18000db62  test    eax, eax
0x18000db64  jg      short loc_18000DB9E
0x18000db66  call    cs:__imp_GetLastError
0x18000db6c  test    eax, eax
0x18000db6e  jz      short loc_18000DB7C
0x18000db70  jle     short loc_18000DB81
0x18000db72  movzx   eax, ax
0x18000db75  or      eax, 80070000h
0x18000db7a  jmp     short loc_18000DB81
0x18000db7c  mov     eax, 80390004h
0x18000db81  mov     r8d, 125h
0x18000db87  lea     rdx, aMapplatformcon_3; "MapPlatformConfig::GetSystemLocaleInfo"
0x18000db8e  mov     ecx, eax
0x18000db90  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000db96  mov     r14d, eax
0x18000db99  jmp     loc_18000DC95
0x18000db9e  mov     r9d, edi; cchData
0x18000dba1  lea     r8, [rsp+1B8h+Src]; lpLCData
0x18000dba6  mov     edx, 5Ah ; 'Z'; LCType
0x18000dbab  lea     rcx, LocaleName; "!x-sys-default-locale"
0x18000dbb2  call    cs:__imp_GetLocaleInfoEx
0x18000dbb8  test    eax, eax
0x18000dbba  jg      short loc_18000DBDF
0x18000dbbc  call    cs:__imp_GetLastError
0x18000dbc2  test    eax, eax
0x18000dbc4  jz      short loc_18000DBD2
0x18000dbc6  jle     short loc_18000DBD7
0x18000dbc8  movzx   eax, ax
0x18000dbcb  or      eax, 80070000h
0x18000dbd0  jmp     short loc_18000DBD7
0x18000dbd2  mov     eax, 80390004h
0x18000dbd7  mov     r8d, 126h
0x18000dbdd  jmp     short loc_18000DB87
0x18000dbdf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dbe3  lea     rax, [rsp+1B8h+Src]
0x18000dbe8  mov     rdx, rdi
0x18000dbeb  mov     r14d, r15d
0x18000dbee  inc     rdx
0x18000dbf1  cmp     [rax+rdx*2], r15w
0x18000dbf6  jnz     short loc_18000DBEE
0x18000dbf8  cmp     rdx, [rbx+18h]
0x18000dbfc  ja      short loc_18000DC2C
0x18000dbfe  cmp     qword ptr [rbx+18h], 7
0x18000dc03  jbe     short loc_18000DC0A
0x18000dc05  mov     rbp, [rbx]
0x18000dc08  jmp     short loc_18000DC0D
0x18000dc0a  mov     rbp, rbx
0x18000dc0d  mov     [rbx+10h], rdx
0x18000dc11  mov     rcx, rbp; void *
0x18000dc14  lea     rbx, [rdx+rdx]
0x18000dc18  mov     r8, rbx; Size
0x18000dc1b  lea     rdx, [rsp+1B8h+Src]; Src
0x18000dc20  call    memmove_0
0x18000dc25  mov     [rbx+rbp], r15w
0x18000dc2a  jmp     short loc_18000DC39
0x18000dc2c  lea     r9, [rsp+1B8h+Src]
0x18000dc31  mov     rcx, rbx
0x18000dc34  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000dc39  lea     rax, [rsp+1B8h+LCData]
0x18000dc41  inc     rdi
0x18000dc44  cmp     [rax+rdi*2], r15w
0x18000dc49  jnz     short loc_18000DC41
0x18000dc4b  cmp     rdi, [rsi+18h]
0x18000dc4f  ja      short loc_18000DC82
0x18000dc51  cmp     qword ptr [rsi+18h], 7
0x18000dc56  jbe     short loc_18000DC5D
0x18000dc58  mov     rbp, [rsi]
0x18000dc5b  jmp     short loc_18000DC60
0x18000dc5d  mov     rbp, rsi
0x18000dc60  lea     rbx, [rdi+rdi]
0x18000dc64  mov     [rsi+10h], rdi
0x18000dc68  mov     r8, rbx; Size
0x18000dc6b  lea     rdx, [rsp+1B8h+LCData]; Src
0x18000dc73  mov     rcx, rbp; void *
0x18000dc76  call    memmove_0
0x18000dc7b  mov     [rbx+rbp], r15w
0x18000dc80  jmp     short loc_18000DC95
0x18000dc82  lea     r9, [rsp+1B8h+LCData]
0x18000dc8a  mov     rdx, rdi
0x18000dc8d  mov     rcx, rsi
0x18000dc90  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000dc95  mov     eax, r14d
0x18000dc98  mov     rcx, [rsp+1B8h+var_38]
0x18000dca0  xor     rcx, rsp; StackCookie
0x18000dca3  call    __security_check_cookie
0x18000dca8  mov     rbx, [rsp+1B8h+arg_10]
0x18000dcb0  add     rsp, 190h
0x18000dcb7  pop     r15
0x18000dcb9  pop     r14
0x18000dcbb  pop     rdi
0x18000dcbc  pop     rsi
0x18000dcbd  pop     rbp
0x18000dcbe  retn
```
