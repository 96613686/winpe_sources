# DdcCommandController::HandleSmsCommand(ushort *,ISmsSharedSecret *)

- ea: `0x180006748`
- end: `0x180006bfa`
- name: `?HandleSmsCommand@DdcCommandController@@SAJPEAGPEAUISmsSharedSecret@@@Z`
- size: `1202`
- prototype: `__int64 __fastcall(wchar_t *String1, struct ISmsSharedSecret *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180006c00`

## callees

- `0x1800028d4`
- `0x180002fc0`
- `0x180003288`
- `0x1800050b8`
- `0x1800054cc`
- `0x180006230`
- `0x180006748`
- `0x18000f600`
- `0x180028b24`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800067a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800067a7`
- `MdmCommon!MdmParseEncryptedRequest` at `0x180006acf`
- `MdmCommon!MdmParseEncryptedRequest` at `0x180006acf`

## string_xrefs

- `0x180006ba3`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x1800067d6`: `CBR(wcsncmp(pwszCommand, SMS_NOTIFICATION_PREFIX, SMS_NOTIFICATION_PREFIX_LENGTH) == 0)`
- `0x18000681d`: `CHR(b64coder.Decode(pwszCommand + 4, wcslen(pwszCommand + 4)))`
- `0x180006b8c`: `CHR(HandleCommandData( dwProfileId, dwRequestId, dwTimestamp, pbCommandData, cbCommandData, MdmCommandChannelType_SMS, ftUtc))`

## pseudocode

```c
__int64 __fastcall DdcCommandController::HandleSmsCommand(wchar_t *String1, struct ISmsSharedSecret *a2)
{
  unsigned __int8 *v4; // r14
  unsigned __int8 *v5; // rsi
  int v6; // edx
  int v7; // ecx
  int v8; // ebx
  const unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // r8
  unsigned __int8 *v11; // rax
  int v12; // edx
  int v13; // ecx
  unsigned __int8 *v14; // rax
  int v15; // edx
  int v16; // ecx
  char v18; // [rsp+20h] [rbp-59h]
  const char *v19; // [rsp+28h] [rbp-51h]
  unsigned int v20; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v21; // [rsp+74h] [rbp-5h] BYREF
  unsigned int v22; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v23; // [rsp+7Ch] [rbp+3h] BYREF
  int v24; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v25; // [rsp+84h] [rbp+Bh] BYREF
  unsigned int v26; // [rsp+88h] [rbp+Fh] BYREF
  void *Block; // [rsp+90h] [rbp+17h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+1Fh] BYREF
  void *v29; // [rsp+A0h] [rbp+27h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp+2Fh]
  size_t v31; // [rsp+F0h] [rbp+77h] BYREF
  size_t Size; // [rsp+F8h] [rbp+7Fh] BYREF

  v29 = 0;
  v30 = 0;
  v20 = 0;
  v21 = 0;
  SystemTimeAsFileTime = 0;
  v23 = 0;
  v22 = 0;
  v26 = 0;
  Block = 0;
  v25 = 0;
  v4 = 0;
  LODWORD(Size) = 0;
  v5 = 0;
  LODWORD(v31) = 0;
  v24 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( wcsncmp_0(String1, L"SkY#", 4u) )
  {
    v8 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_44;
    v19 = "CBR(wcsncmp(pwszCommand, SMS_NOTIFICATION_PREFIX, SMS_NOTIFICATION_PREFIX_LENGTH) == 0)";
    v18 = -124;
    goto LABEL_43;
  }
  v9 = String1 + 4;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  v8 = DdcBase64Coder::Decode(&v29, v9, v10);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_44;
    v19 = "CHR(b64coder.Decode(pwszCommand + 4, wcslen(pwszCommand + 4)))";
    v18 = -121;
    goto LABEL_43;
  }
  v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, &v21);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_44;
    v19 = "CHR(pSmsSharedSecret->GetSecretCurrentId(&dwCurrentSecretId))";
    v18 = -118;
    goto LABEL_43;
  }
  v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, unsigned int *))(*(_QWORD *)a2 + 88LL))(a2, &v20);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_44;
    v19 = "CHR(pSmsSharedSecret->GetSecretUpdatingId(&dwUpdatingSecretId))";
    v18 = -117;
    goto LABEL_43;
  }
  v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, _QWORD, _QWORD, size_t *))(*(_QWORD *)a2 + 72LL))(
         a2,
         v21,
         0,
         &Size);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_44;
    v19 = "CHR(pSmsSharedSecret->GetSharedSecret(dwCurrentSecretId, 0, &cbCurrentSecretSize))";
    v18 = -114;
    goto LABEL_43;
  }
  v11 = (unsigned __int8 *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, (unsigned int)Size);
    v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, _QWORD, unsigned __int8 *, size_t *))(*(_QWORD *)a2 + 72LL))(
           a2,
           v21,
           v4,
           &Size);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_44;
      v19 = "CHR(pSmsSharedSecret->GetSharedSecret(dwCurrentSecretId, pbCurrentSecret, &cbCurrentSecretSize))";
      v18 = -110;
      goto LABEL_43;
    }
    v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, _QWORD, _QWORD, size_t *))(*(_QWORD *)a2 + 72LL))(
           a2,
           v20,
           0,
           &v31);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_44;
      v19 = "CHR(pSmsSharedSecret->GetSharedSecret(dwUpdatingSecretId, 0, &cbUpdatingSecretSize))";
      v18 = -108;
      goto LABEL_43;
    }
    v14 = (unsigned __int8 *)operator new[]((unsigned int)v31, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v14;
    if ( v14 )
    {
      memset_0(v14, 0, (unsigned int)v31);
      v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *, _QWORD, unsigned __int8 *, size_t *))(*(_QWORD *)a2 + 72LL))(
             a2,
             v20,
             v5,
             &v31);
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_44;
        v19 = "CHR(pSmsSharedSecret->GetSharedSecret(dwUpdatingSecretId, pbUpdatingSecret, &cbUpdatingSecretSize))";
        v18 = -104;
        goto LABEL_43;
      }
      v8 = MdmParseEncryptedRequest(
             (const unsigned __int8 *)v29,
             v30,
             v21,
             v20,
             v4,
             Size,
             v5,
             v31,
             &v24,
             &v23,
             &v22,
             &v26,
             (unsigned __int8 **)&Block,
             &v25);
      DdcTraceHelper::TraceHandleSmsCommandResult(v21, v20, v23, v22, v8);
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_44;
        v19 = "CHR(hr)";
        v18 = -78;
        goto LABEL_43;
      }
      if ( v24 )
      {
        v8 = (*(__int64 (__fastcall **)(struct ISmsSharedSecret *))(*(_QWORD *)a2 + 56LL))(a2);
        if ( v8 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_44;
          v19 = "CHR(pSmsSharedSecret->SetUpdatingSecretAsCurrentSecret())";
          v18 = -73;
          goto LABEL_43;
        }
      }
      v8 = DdcCommandController::HandleCommandData(v23, v22, v26, Block, v25, 2, *(_QWORD *)&SystemTimeAsFileTime);
      if ( v8 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v19 = "CHR(HandleCommandData( dwProfileId, dwRequestId, dwTimestamp, pbCommandData, cbCommandData, MdmCommandChan"
              "nelType_SMS, ftUtc))";
        v18 = -62;
LABEL_43:
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          v18,
          v19);
      }
    }
    else
    {
      v8 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v16,
          v15,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          150,
          "CPR(pbUpdatingSecret)");
    }
  }
  else
  {
    v8 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v13,
        v12,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        144,
        "CPR(pbCurrentSecret)");
  }
LABEL_44:
  if ( Block )
    operator delete(Block);
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  operator delete(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006748  mov     [rsp-8+arg_0], rbx
0x18000674d  push    rbp
0x18000674e  push    rsi
0x18000674f  push    rdi
0x180006750  push    r14
0x180006752  push    r15
0x180006754  lea     rbp, [rsp-37h]
0x180006759  sub     rsp, 0B0h
0x180006760  mov     rdi, rdx
0x180006763  mov     rbx, rcx
0x180006766  xor     r15d, r15d
0x180006769  mov     [rbp+57h+var_30], r15
0x18000676d  mov     [rbp+57h+var_28], r15d
0x180006771  mov     [rbp+57h+var_60], r15d
0x180006775  mov     [rbp+57h+var_5C], r15d
0x180006779  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18000677d  mov     [rbp+57h+var_54], r15d
0x180006781  mov     [rbp+57h+var_58], r15d
0x180006785  mov     [rbp+57h+var_48], r15d
0x180006789  mov     [rbp+57h+Block], r15
0x18000678d  mov     [rbp+57h+var_4C], r15d
0x180006791  mov     r14d, r15d
0x180006794  mov     dword ptr [rbp+57h+Size], r15d
0x180006798  mov     esi, r15d
0x18000679b  mov     dword ptr [rbp+57h+arg_10], r15d
0x18000679f  mov     [rbp+57h+var_50], r15d
0x1800067a3  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800067a7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800067ad  lea     r8d, [r15+4]; MaxCount
0x1800067b1  lea     rdx, aSky; "SkY#"
0x1800067b8  mov     rcx, rbx; String1
0x1800067bb  call    wcsncmp_0
0x1800067c0  test    eax, eax
0x1800067c2  jz      short loc_1800067EF
0x1800067c4  mov     ebx, 80004005h
0x1800067c9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800067d0  jz      loc_180006BAF
0x1800067d6  lea     rax, aCbrWcsncmpPwsz; "CBR(wcsncmp(pwszCommand, SMS_NOTIFICATI"...
0x1800067dd  mov     [rsp+0D0h+var_A8], rax
0x1800067e2  mov     [rsp+0D0h+var_B0], 84h
0x1800067ea  jmp     loc_180006BA0
0x1800067ef  lea     rdx, [rbx+8]; unsigned __int16 *
0x1800067f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800067f7  inc     r8; unsigned __int64
0x1800067fa  cmp     [rdx+r8*2], r15w
0x1800067ff  jnz     short loc_1800067F7
0x180006801  lea     rcx, [rbp+57h+var_30]; this
0x180006805  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x18000680a  mov     ebx, eax
0x18000680c  test    eax, eax
0x18000680e  jns     short loc_180006836
0x180006810  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006817  jz      loc_180006BAF
0x18000681d  lea     rax, aChrB64coderDec; "CHR(b64coder.Decode(pwszCommand + 4, wc"...
0x180006824  mov     [rsp+0D0h+var_A8], rax
0x180006829  mov     [rsp+0D0h+var_B0], 87h
0x180006831  jmp     loc_180006BA0
0x180006836  mov     rax, [rdi]
0x180006839  lea     rdx, [rbp+57h+var_5C]
0x18000683d  mov     rcx, rdi
0x180006840  mov     rax, [rax+50h]
0x180006844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006849  mov     ebx, eax
0x18000684b  test    eax, eax
0x18000684d  jns     short loc_180006875
0x18000684f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006856  jz      loc_180006BAF
0x18000685c  lea     rax, aChrPsmsshareds_6; "CHR(pSmsSharedSecret->GetSecretCurrentI"...
0x180006863  mov     [rsp+0D0h+var_A8], rax
0x180006868  mov     [rsp+0D0h+var_B0], 8Ah
0x180006870  jmp     loc_180006BA0
0x180006875  mov     rax, [rdi]
0x180006878  lea     rdx, [rbp+57h+var_60]
0x18000687c  mov     rcx, rdi
0x18000687f  mov     rax, [rax+58h]
0x180006883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006888  mov     ebx, eax
0x18000688a  test    eax, eax
0x18000688c  jns     short loc_1800068B4
0x18000688e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006895  jz      loc_180006BAF
0x18000689b  lea     rax, aChrPsmsshareds_2; "CHR(pSmsSharedSecret->GetSecretUpdating"...
0x1800068a2  mov     [rsp+0D0h+var_A8], rax
0x1800068a7  mov     [rsp+0D0h+var_B0], 8Bh
0x1800068af  jmp     loc_180006BA0
0x1800068b4  mov     rax, [rdi]
0x1800068b7  lea     r9, [rbp+57h+Size]
0x1800068bb  xor     r8d, r8d
0x1800068be  mov     edx, [rbp+57h+var_5C]
0x1800068c1  mov     rcx, rdi
0x1800068c4  mov     rax, [rax+48h]
0x1800068c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068cd  mov     ebx, eax
0x1800068cf  test    eax, eax
0x1800068d1  jns     short loc_1800068F9
0x1800068d3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800068da  jz      loc_180006BAF
0x1800068e0  lea     rax, aChrPsmsshareds_5; "CHR(pSmsSharedSecret->GetSharedSecret(d"...
0x1800068e7  mov     [rsp+0D0h+var_A8], rax
0x1800068ec  mov     [rsp+0D0h+var_B0], 8Eh
0x1800068f4  jmp     loc_180006BA0
0x1800068f9  mov     ecx, dword ptr [rbp+57h+Size]; unsigned __int64
0x1800068fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006903  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006908  mov     r14, rax
0x18000690b  test    rax, rax
0x18000690e  jnz     short loc_18000693F
0x180006910  mov     r8d, 8007000Eh
0x180006916  mov     ebx, r8d
0x180006919  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006920  jz      loc_180006BAF
0x180006926  lea     rax, aCprPbcurrentse; "CPR(pbCurrentSecret)"
0x18000692d  mov     [rsp+0D0h+var_A8], rax
0x180006932  mov     [rsp+0D0h+var_B0], 90h
0x18000693a  jmp     loc_180006BA3
0x18000693f  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180006943  xor     edx, edx; Val
0x180006945  mov     rcx, r14; void *
0x180006948  call    memset_0
0x18000694d  mov     rax, [rdi]
0x180006950  lea     r9, [rbp+57h+Size]
0x180006954  mov     r8, r14
0x180006957  mov     edx, [rbp+57h+var_5C]
0x18000695a  mov     rcx, rdi
0x18000695d  mov     rax, [rax+48h]
0x180006961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006966  mov     ebx, eax
0x180006968  test    eax, eax
0x18000696a  jns     short loc_180006992
0x18000696c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006973  jz      loc_180006BAF
0x180006979  lea     rax, aChrPsmsshareds; "CHR(pSmsSharedSecret->GetSharedSecret(d"...
0x180006980  mov     [rsp+0D0h+var_A8], rax
0x180006985  mov     [rsp+0D0h+var_B0], 92h
0x18000698d  jmp     loc_180006BA0
0x180006992  mov     rax, [rdi]
0x180006995  lea     r9, [rbp+57h+arg_10]
0x180006999  xor     r8d, r8d
0x18000699c  mov     edx, [rbp+57h+var_60]
0x18000699f  mov     rcx, rdi
0x1800069a2  mov     rax, [rax+48h]
0x1800069a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ab  mov     ebx, eax
0x1800069ad  test    eax, eax
0x1800069af  jns     short loc_1800069D7
0x1800069b1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800069b8  jz      loc_180006BAF
0x1800069be  lea     rax, aChrPsmsshareds_0; "CHR(pSmsSharedSecret->GetSharedSecret(d"...
0x1800069c5  mov     [rsp+0D0h+var_A8], rax
0x1800069ca  mov     [rsp+0D0h+var_B0], 94h
0x1800069d2  jmp     loc_180006BA0
0x1800069d7  mov     ecx, dword ptr [rbp+57h+arg_10]; unsigned __int64
0x1800069da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800069e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800069e6  mov     rsi, rax
0x1800069e9  test    rax, rax
0x1800069ec  jnz     short loc_180006A1D
0x1800069ee  mov     r8d, 8007000Eh
0x1800069f4  mov     ebx, r8d
0x1800069f7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800069fe  jz      loc_180006BAF
0x180006a04  lea     rax, aCprPbupdatings; "CPR(pbUpdatingSecret)"
0x180006a0b  mov     [rsp+0D0h+var_A8], rax
0x180006a10  mov     [rsp+0D0h+var_B0], 96h
0x180006a18  jmp     loc_180006BA3
0x180006a1d  mov     r8d, dword ptr [rbp+57h+arg_10]; Size
0x180006a21  xor     edx, edx; Val
0x180006a23  mov     rcx, rsi; void *
0x180006a26  call    memset_0
0x180006a2b  mov     rax, [rdi]
0x180006a2e  lea     r9, [rbp+57h+arg_10]
0x180006a32  mov     r8, rsi
0x180006a35  mov     edx, [rbp+57h+var_60]
0x180006a38  mov     rcx, rdi
0x180006a3b  mov     rax, [rax+48h]
0x180006a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a44  mov     ebx, eax
0x180006a46  test    eax, eax
0x180006a48  jns     short loc_180006A70
0x180006a4a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006a51  jz      loc_180006BAF
0x180006a57  lea     rax, aChrPsmsshareds_4; "CHR(pSmsSharedSecret->GetSharedSecret(d"...
0x180006a5e  mov     [rsp+0D0h+var_A8], rax
0x180006a63  mov     [rsp+0D0h+var_B0], 98h
0x180006a6b  jmp     loc_180006BA0
0x180006a70  mov     eax, dword ptr [rbp+57h+arg_10]
0x180006a73  mov     r10d, dword ptr [rbp+57h+Size]
0x180006a77  lea     rcx, [rbp+57h+var_4C]
0x180006a7b  mov     [rsp+0D0h+var_68], rcx
0x180006a80  lea     rcx, [rbp+57h+Block]
0x180006a84  mov     [rsp+0D0h+var_70], rcx
0x180006a89  lea     rcx, [rbp+57h+var_48]
0x180006a8d  mov     [rsp+0D0h+var_78], rcx
0x180006a92  lea     rcx, [rbp+57h+var_58]
0x180006a96  mov     [rsp+0D0h+var_80], rcx
0x180006a9b  lea     rcx, [rbp+57h+var_54]
0x180006a9f  mov     [rsp+0D0h+var_88], rcx
0x180006aa4  lea     rcx, [rbp+57h+var_50]
0x180006aa8  mov     [rsp+0D0h+var_90], rcx
0x180006aad  mov     [rsp+0D0h+var_98], eax
0x180006ab1  mov     [rsp+0D0h+var_A0], rsi
0x180006ab6  mov     dword ptr [rsp+0D0h+var_A8], r10d
0x180006abb  mov     qword ptr [rsp+0D0h+var_B0], r14
0x180006ac0  mov     r9d, [rbp+57h+var_60]
0x180006ac4  mov     r8d, [rbp+57h+var_5C]
0x180006ac8  mov     edx, [rbp+57h+var_28]
0x180006acb  mov     rcx, [rbp+57h+var_30]
0x180006acf  call    cs:__imp_?MdmParseEncryptedRequest@@YAJPEBEKKKPEAEK1KPEAHPEAK33PEAPEAE3@Z; MdmParseEncryptedRequest(uchar const *,ulong,ulong,ulong,uchar *,ulong,uchar *,ulong,int *,ulong *,ulong *,ulong *,uchar * *,ulong *)
0x180006ad5  mov     ebx, eax
0x180006ad7  mov     [rsp+0D0h+var_B0], eax; int
0x180006adb  mov     r9d, [rbp+57h+var_58]; unsigned int
0x180006adf  mov     r8d, [rbp+57h+var_54]; unsigned int
0x180006ae3  mov     edx, [rbp+57h+var_60]; unsigned int
0x180006ae6  mov     ecx, [rbp+57h+var_5C]; unsigned int
0x180006ae9  call    ?TraceHandleSmsCommandResult@DdcTraceHelper@@SAXKKKKJ@Z; DdcTraceHelper::TraceHandleSmsCommandResult(ulong,ulong,ulong,ulong,long)
0x180006aee  test    ebx, ebx
0x180006af0  jns     short loc_180006B18
0x180006af2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006af9  jz      loc_180006BAF
0x180006aff  lea     rax, aChrHr; "CHR(hr)"
0x180006b06  mov     [rsp+0D0h+var_A8], rax
0x180006b0b  mov     [rsp+0D0h+var_B0], 0B2h
0x180006b13  jmp     loc_180006BA0
0x180006b18  cmp     [rbp+57h+var_50], r15d
0x180006b1c  jz      short loc_180006B52
0x180006b1e  mov     rax, [rdi]
0x180006b21  mov     rcx, rdi
0x180006b24  mov     rax, [rax+38h]
0x180006b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2d  mov     ebx, eax
0x180006b2f  test    eax, eax
0x180006b31  jns     short loc_180006B52
0x180006b33  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006b3a  jz      short loc_180006BAF
0x180006b3c  lea     rax, aChrPsmsshareds_3; "CHR(pSmsSharedSecret->SetUpdatingSecret"...
0x180006b43  mov     [rsp+0D0h+var_A8], rax
0x180006b48  mov     [rsp+0D0h+var_B0], 0B7h
0x180006b50  jmp     short loc_180006BA0
0x180006b52  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180006b56  mov     [rsp+0D0h+var_A0], rax
0x180006b5b  mov     dword ptr [rsp+0D0h+var_A8], 2
0x180006b63  mov     eax, [rbp+57h+var_4C]
0x180006b66  mov     [rsp+0D0h+var_B0], eax
0x180006b6a  mov     r9, [rbp+57h+Block]
0x180006b6e  mov     r8d, [rbp+57h+var_48]
0x180006b72  mov     edx, [rbp+57h+var_58]
0x180006b75  mov     ecx, [rbp+57h+var_54]
0x180006b78  call    ?HandleCommandData@DdcCommandController@@CAJKKKPEAEKW4MdmCommandChannelType@@U_FILETIME@@@Z; DdcCommandController::HandleCommandData(ulong,ulong,ulong,uchar *,ulong,MdmCommandChannelType,_FILETIME)
0x180006b7d  mov     ebx, eax
0x180006b7f  test    eax, eax
0x180006b81  jns     short loc_180006BAF
0x180006b83  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006b8a  jz      short loc_180006BAF
0x180006b8c  lea     rax, aChrHandlecomma; "CHR(HandleCommandData( dwProfileId, dwR"...
0x180006b93  mov     [rsp+0D0h+var_A8], rax
0x180006b98  mov     [rsp+0D0h+var_B0], 0C2h
0x180006ba0  mov     r8d, ebx
0x180006ba3  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180006baa  call    McTemplateU0dsqs_EventWriteTransfer
0x180006baf  mov     rcx, [rbp+57h+Block]; Block
0x180006bb3  test    rcx, rcx
0x180006bb6  jz      short loc_180006BBD
0x180006bb8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006bbd  test    r14, r14
0x180006bc0  jz      short loc_180006BCA
0x180006bc2  mov     rcx, r14; Block
0x180006bc5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006bca  test    rsi, rsi
0x180006bcd  jz      short loc_180006BD8
0x180006bcf  mov     rcx, rsi; Block
0x180006bd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006bd7  nop
0x180006bd8  mov     rcx, [rbp+57h+var_30]; Block
0x180006bdc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006be1  mov     eax, ebx
0x180006be3  mov     rbx, [rsp+0D0h+arg_0]
0x180006beb  add     rsp, 0B0h
0x180006bf2  pop     r15
0x180006bf4  pop     r14
0x180006bf6  pop     rdi
0x180006bf7  pop     rsi
0x180006bf8  pop     rbp
0x180006bf9  retn
```
