# SmsMessageFilterBuilder::CreateTextMessageFilter(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180009524`
- end: `0x180009ac4`
- name: `?CreateTextMessageFilter@SmsMessageFilterBuilder@@SAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1440`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180007930`

## callees

- `0x18000266c`
- `0x1800093e4`
- `0x180009524`
- `0x180009acc`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009585`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009661`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009585`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000964d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000964d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800098a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800098a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800098e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800098e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009a02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000959a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009676`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000959a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009676`

## pseudocode

```c
__int64 __fastcall SmsMessageFilterBuilder::CreateTextMessageFilter(__int64 a1)
{
  int ActivationFactory; // eax
  __int64 v3; // r8
  int v4; // ebx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  void (*v11)(void); // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  void (*v16)(void); // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rcx
  void (*v21)(void); // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  void (*v26)(void); // rax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // rcx
  void (*v31)(void); // rax
  __int64 v32; // rcx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING *); // rbx
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // rcx
  WCHAR *StringRawBuffer; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int128 *v45; // r14
  __int128 *v46; // rcx
  char *v47; // rdi
  __int128 v48; // kr00_16
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-61h] BYREF
  __int64 v57; // [rsp+50h] [rbp-49h] BYREF
  __int64 v58; // [rsp+58h] [rbp-41h] BYREF
  __int64 v59; // [rsp+60h] [rbp-39h] BYREF
  __int64 v60; // [rsp+68h] [rbp-31h] BYREF
  __int64 v61; // [rsp+70h] [rbp-29h] BYREF
  __int64 v62; // [rsp+78h] [rbp-21h] BYREF
  HSTRING v63; // [rsp+80h] [rbp-19h] BYREF
  void *v64; // [rsp+88h] [rbp-11h] BYREF
  char *v65; // [rsp+90h] [rbp-9h]
  __int128 v66; // [rsp+98h] [rbp-1h] BYREF

  v57 = 0;
  if ( WindowsCreateStringReference(L"Windows.Devices.Sms.SmsFilterRule", 0x21u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_00c36508_6296_4f29_9aad_8920ceba3ce8, &v57);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_4((unsigned int)ActivationFactory, 1, v3, 10);
LABEL_5:
    v5 = v57;
    if ( !v57 )
      return (unsigned int)v4;
    v57 = 0;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 16LL);
LABEL_7:
    v6();
    return (unsigned int)v4;
  }
  v58 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 48LL))(v57, 1, &v58);
  v4 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_4((unsigned int)v8, 1, v9, 13);
    v10 = v58;
    if ( !v58 )
    {
LABEL_13:
      v12 = v57;
      if ( !v57 )
        return (unsigned int)v4;
      v57 = 0;
      v6 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
      goto LABEL_7;
    }
    v58 = 0;
    v11 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
LABEL_12:
    v11();
    goto LABEL_13;
  }
  v59 = 0;
  if ( WindowsCreateStringReference(L"Windows.Devices.Sms.SmsFilterRules", 0x22u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v13 = RoGetActivationFactory(string, &GUID_a09924ed_6e2e_4530_9fde_465d02eed00e, &v59);
  v4 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_4((unsigned int)v13, 1, v14, 17);
    v15 = v59;
    if ( !v59 )
    {
LABEL_21:
      v17 = v58;
      if ( !v58 )
        goto LABEL_13;
      v58 = 0;
      v11 = *(void (**)(void))(*(_QWORD *)v17 + 16LL);
      goto LABEL_12;
    }
    v59 = 0;
    v16 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_20:
    v16();
    goto LABEL_21;
  }
  v60 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v59 + 48LL))(v59, 3, &v60);
  v4 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_4((unsigned int)v18, 1, v19, 20);
    v20 = v60;
    if ( !v60 )
    {
LABEL_27:
      v22 = v59;
      if ( !v59 )
        goto LABEL_21;
      v59 = 0;
      v16 = *(void (**)(void))(*(_QWORD *)v22 + 16LL);
      goto LABEL_20;
    }
    v60 = 0;
    v21 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
LABEL_26:
    v21();
    goto LABEL_27;
  }
  v61 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 56LL))(v60, &v61);
  if ( v4 < 0 )
  {
    v24 = 23;
LABEL_31:
    Log_HREvent_4((unsigned int)v4, 1, v23, v24);
    v25 = v61;
    if ( !v61 )
    {
LABEL_34:
      v27 = v60;
      if ( !v60 )
        goto LABEL_27;
      v60 = 0;
      v21 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
      goto LABEL_26;
    }
    v61 = 0;
    v26 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_33:
    v26();
    goto LABEL_34;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 104LL))(v61, v58);
  if ( v4 < 0 )
  {
    v24 = 25;
    goto LABEL_31;
  }
  v62 = 0;
  v28 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v60)(
          v60,
          &GUID_bbd4bcdf_17a5_45cd_a333_c0ef70cbc203,
          &v62);
  v4 = v28;
  if ( v28 < 0 )
  {
    Log_HREvent_4((unsigned int)v28, 1, v29, 28);
    v30 = v62;
    if ( !v62 )
    {
LABEL_42:
      v32 = v61;
      if ( !v61 )
        goto LABEL_34;
      v61 = 0;
      v26 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
      goto LABEL_33;
    }
    v62 = 0;
    v31 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
LABEL_41:
    v31();
    goto LABEL_42;
  }
  v33 = v62;
  v63 = 0;
  v34 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v62 + 48LL);
  WindowsDeleteString(0);
  v63 = 0;
  v35 = v34(v33, &v63);
  v4 = v35;
  if ( v35 < 0 )
  {
    Log_HREvent_4((unsigned int)v35, 1, v36, 31);
    WindowsDeleteString(v63);
    v37 = v62;
    v63 = 0;
    if ( !v62 )
      goto LABEL_42;
    v62 = 0;
    v31 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
    goto LABEL_41;
  }
  v64 = &v66;
  v66 = 0u;
  v65 = (char *)&v66;
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v63, 0);
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)&v64,
          StringRawBuffer) )
  {
    v4 = -2147024882;
    Log_HREvent_4(2147942414LL, 0, v39, 34);
    if ( v64 != &v66 )
      operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
    WindowsDeleteString(v63);
    v40 = v62;
    v63 = 0;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    goto LABEL_5;
  }
  v45 = (__int128 *)v64;
  v46 = &v66;
  v47 = v65;
  v48 = v66;
  v64 = &v66;
  v65 = (char *)&v66;
  LOWORD(v66) = 0;
  if ( *(_QWORD *)a1 != a1 + 16 )
  {
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
    v46 = (__int128 *)v64;
  }
  if ( v45 == &v66 )
  {
    v45 = (__int128 *)(a1 + 16);
    v47 = (char *)(a1 + 2 * (((v47 - (char *)&v64 - 16) >> 1) + 8));
  }
  *(_QWORD *)a1 = v45;
  *(_QWORD *)(a1 + 8) = v47;
  *(_OWORD *)(a1 + 16) = v48;
  if ( v46 != &v66 )
    operator delete(v46, (const struct std::nothrow_t *)&std::nothrow);
  WindowsDeleteString(v63);
  v49 = v62;
  v63 = 0;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v52 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v53 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  v54 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  return 0;
}

```

## disassembly

```asm
0x180009524  push    rbp
0x180009526  push    rbx
0x180009527  push    rsi
0x180009528  push    rdi
0x180009529  push    r12
0x18000952b  push    r13
0x18000952d  push    r14
0x18000952f  push    r15
0x180009531  lea     rbp, [rsp-1Fh]
0x180009536  sub     rsp, 0B8h
0x18000953d  mov     rax, cs:__security_cookie
0x180009544  xor     rax, rsp
0x180009547  mov     [rbp+57h+var_48], rax
0x18000954b  xor     r13d, r13d
0x18000954e  lea     r9, [rbp+57h+string]; string
0x180009552  mov     r15, rcx
0x180009555  mov     [rbp+57h+var_A0], r13
0x180009559  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000955d  lea     rcx, ?RuntimeClass_Windows_Devices_Sms_SmsFilterRule@@3QBGB; "Windows.Devices.Sms.SmsFilterRule"
0x180009564  lea     edx, [r13+21h]; length
0x180009568  call    cs:__imp_WindowsCreateStringReference
0x18000956e  lea     esi, [r13+1]
0x180009572  mov     edi, 0C000000Dh
0x180009577  test    eax, eax
0x180009579  jns     short loc_18000958B
0x18000957b  xor     r9d, r9d; lpArguments
0x18000957e  xor     r8d, r8d; nNumberOfArguments
0x180009581  mov     edx, esi; dwExceptionFlags
0x180009583  mov     ecx, edi; dwExceptionCode
0x180009585  call    cs:__imp_RaiseException
0x18000958b  mov     rcx, [rbp+57h+string]
0x18000958f  lea     r8, [rbp+57h+var_A0]
0x180009593  lea     rdx, _GUID_00c36508_6296_4f29_9aad_8920ceba3ce8
0x18000959a  call    cs:__imp_RoGetActivationFactory
0x1800095a0  mov     ebx, eax
0x1800095a2  mov     edx, esi
0x1800095a4  test    eax, eax
0x1800095a6  jns     short loc_1800095D5
0x1800095a8  mov     r9d, 0Ah
0x1800095ae  mov     ecx, eax
0x1800095b0  call    Log_HREvent_4
0x1800095b5  mov     rcx, [rbp+57h+var_A0]
0x1800095b9  test    rcx, rcx
0x1800095bc  jz      short loc_1800095CE
0x1800095be  mov     [rbp+57h+var_A0], r13
0x1800095c2  mov     rdx, [rcx]
0x1800095c5  mov     rax, [rdx+10h]
0x1800095c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ce  mov     eax, ebx
0x1800095d0  jmp     loc_180009AA4
0x1800095d5  mov     rcx, [rbp+57h+var_A0]
0x1800095d9  lea     r8, [rbp+57h+var_98]
0x1800095dd  mov     [rbp+57h+var_98], r13
0x1800095e1  mov     rax, [rcx]
0x1800095e4  mov     rax, [rax+30h]
0x1800095e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ed  mov     ebx, eax
0x1800095ef  test    eax, eax
0x1800095f1  jns     short loc_180009631
0x1800095f3  mov     r9d, 0Dh
0x1800095f9  mov     edx, esi
0x1800095fb  mov     ecx, eax
0x1800095fd  call    Log_HREvent_4
0x180009602  mov     rcx, [rbp+57h+var_98]
0x180009606  test    rcx, rcx
0x180009609  jz      short loc_18000961B
0x18000960b  mov     [rbp+57h+var_98], r13
0x18000960f  mov     rdx, [rcx]
0x180009612  mov     rax, [rdx+10h]
0x180009616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000961b  mov     rcx, [rbp+57h+var_A0]
0x18000961f  test    rcx, rcx
0x180009622  jz      short loc_1800095CE
0x180009624  mov     [rbp+57h+var_A0], r13
0x180009628  mov     rax, [rcx]
0x18000962b  mov     rax, [rax+10h]
0x18000962f  jmp     short loc_1800095C9
0x180009631  mov     r14d, 22h ; '"'
0x180009637  mov     [rbp+57h+var_90], r13
0x18000963b  mov     edx, r14d; length
0x18000963e  lea     r9, [rbp+57h+string]; string
0x180009642  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180009646  lea     rcx, ?RuntimeClass_Windows_Devices_Sms_SmsFilterRules@@3QBGB; "Windows.Devices.Sms.SmsFilterRules"
0x18000964d  call    cs:__imp_WindowsCreateStringReference
0x180009653  test    eax, eax
0x180009655  jns     short loc_180009667
0x180009657  xor     r9d, r9d; lpArguments
0x18000965a  xor     r8d, r8d; nNumberOfArguments
0x18000965d  mov     edx, esi; dwExceptionFlags
0x18000965f  mov     ecx, edi; dwExceptionCode
0x180009661  call    cs:__imp_RaiseException
0x180009667  mov     rcx, [rbp+57h+string]
0x18000966b  lea     r8, [rbp+57h+var_90]
0x18000966f  lea     rdx, _GUID_a09924ed_6e2e_4530_9fde_465d02eed00e
0x180009676  call    cs:__imp_RoGetActivationFactory
0x18000967c  mov     ebx, eax
0x18000967e  test    eax, eax
0x180009680  jns     short loc_1800096C7
0x180009682  mov     r9d, 11h
0x180009688  mov     edx, esi
0x18000968a  mov     ecx, eax
0x18000968c  call    Log_HREvent_4
0x180009691  mov     rcx, [rbp+57h+var_90]
0x180009695  test    rcx, rcx
0x180009698  jz      short loc_1800096AA
0x18000969a  mov     [rbp+57h+var_90], r13
0x18000969e  mov     rdx, [rcx]
0x1800096a1  mov     rax, [rdx+10h]
0x1800096a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096aa  mov     rcx, [rbp+57h+var_98]
0x1800096ae  test    rcx, rcx
0x1800096b1  jz      loc_18000961B
0x1800096b7  mov     [rbp+57h+var_98], r13
0x1800096bb  mov     rax, [rcx]
0x1800096be  mov     rax, [rax+10h]
0x1800096c2  jmp     loc_180009616
0x1800096c7  mov     rcx, [rbp+57h+var_90]
0x1800096cb  lea     r8, [rbp+57h+var_88]
0x1800096cf  mov     [rbp+57h+var_88], r13
0x1800096d3  mov     edx, 3
0x1800096d8  mov     rax, [rcx]
0x1800096db  mov     rax, [rax+30h]
0x1800096df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e4  mov     ebx, eax
0x1800096e6  test    eax, eax
0x1800096e8  jns     short loc_18000972B
0x1800096ea  mov     r9d, 14h
0x1800096f0  mov     edx, esi
0x1800096f2  mov     ecx, eax
0x1800096f4  call    Log_HREvent_4
0x1800096f9  mov     rcx, [rbp+57h+var_88]
0x1800096fd  test    rcx, rcx
0x180009700  jz      short loc_180009712
0x180009702  mov     [rbp+57h+var_88], r13
0x180009706  mov     rdx, [rcx]
0x180009709  mov     rax, [rdx+10h]
0x18000970d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009712  mov     rcx, [rbp+57h+var_90]
0x180009716  test    rcx, rcx
0x180009719  jz      short loc_1800096AA
0x18000971b  mov     [rbp+57h+var_90], r13
0x18000971f  mov     rax, [rcx]
0x180009722  mov     rax, [rax+10h]
0x180009726  jmp     loc_1800096A5
0x18000972b  mov     rcx, [rbp+57h+var_88]
0x18000972f  lea     rdx, [rbp+57h+var_80]
0x180009733  mov     [rbp+57h+var_80], r13
0x180009737  mov     rax, [rcx]
0x18000973a  mov     rax, [rax+38h]
0x18000973e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009743  mov     ebx, eax
0x180009745  test    eax, eax
0x180009747  jns     short loc_180009787
0x180009749  mov     r9d, 17h
0x18000974f  mov     edx, esi
0x180009751  mov     ecx, ebx
0x180009753  call    Log_HREvent_4
0x180009758  mov     rcx, [rbp+57h+var_80]
0x18000975c  test    rcx, rcx
0x18000975f  jz      short loc_180009771
0x180009761  mov     [rbp+57h+var_80], r13
0x180009765  mov     rdx, [rcx]
0x180009768  mov     rax, [rdx+10h]
0x18000976c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009771  mov     rcx, [rbp+57h+var_88]
0x180009775  test    rcx, rcx
0x180009778  jz      short loc_180009712
0x18000977a  mov     [rbp+57h+var_88], r13
0x18000977e  mov     rax, [rcx]
0x180009781  mov     rax, [rax+10h]
0x180009785  jmp     short loc_18000970D
0x180009787  mov     rcx, [rbp+57h+var_80]
0x18000978b  mov     rdx, [rbp+57h+var_98]
0x18000978f  mov     rax, [rcx]
0x180009792  mov     rax, [rax+68h]
0x180009796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979b  mov     ebx, eax
0x18000979d  test    eax, eax
0x18000979f  jns     short loc_1800097A9
0x1800097a1  mov     r9d, 19h
0x1800097a7  jmp     short loc_18000974F
0x1800097a9  mov     rcx, [rbp+57h+var_88]
0x1800097ad  lea     r8, [rbp+57h+var_78]
0x1800097b1  mov     [rbp+57h+var_78], r13
0x1800097b5  lea     rdx, _GUID_bbd4bcdf_17a5_45cd_a333_c0ef70cbc203
0x1800097bc  mov     rax, [rcx]
0x1800097bf  mov     rax, [rax]
0x1800097c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097c7  mov     ebx, eax
0x1800097c9  test    eax, eax
0x1800097cb  jns     short loc_180009812
0x1800097cd  mov     r9d, 1Ch
0x1800097d3  mov     edx, esi
0x1800097d5  mov     ecx, eax
0x1800097d7  call    Log_HREvent_4
0x1800097dc  mov     rcx, [rbp+57h+var_78]
0x1800097e0  test    rcx, rcx
0x1800097e3  jz      short loc_1800097F5
0x1800097e5  mov     [rbp+57h+var_78], r13
0x1800097e9  mov     rdx, [rcx]
0x1800097ec  mov     rax, [rdx+10h]
0x1800097f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f5  mov     rcx, [rbp+57h+var_80]
0x1800097f9  test    rcx, rcx
0x1800097fc  jz      loc_180009771
0x180009802  mov     [rbp+57h+var_80], r13
0x180009806  mov     rax, [rcx]
0x180009809  mov     rax, [rax+10h]
0x18000980d  jmp     loc_18000976C
0x180009812  mov     rdi, [rbp+57h+var_78]
0x180009816  xor     ecx, ecx; string
0x180009818  mov     [rbp+57h+var_70], r13
0x18000981c  mov     rax, [rdi]
0x18000981f  mov     rbx, [rax+30h]
0x180009823  call    cs:__imp_WindowsDeleteString
0x180009829  lea     rdx, [rbp+57h+var_70]
0x18000982d  mov     [rbp+57h+var_70], r13
0x180009831  mov     rcx, rdi
0x180009834  mov     rax, rbx
0x180009837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983c  mov     ebx, eax
0x18000983e  test    eax, eax
0x180009840  jns     short loc_180009878
0x180009842  mov     r9d, 1Fh
0x180009848  mov     edx, esi
0x18000984a  mov     ecx, eax
0x18000984c  call    Log_HREvent_4
0x180009851  mov     rcx, [rbp+57h+var_70]; string
0x180009855  call    cs:__imp_WindowsDeleteString
0x18000985b  mov     rcx, [rbp+57h+var_78]
0x18000985f  mov     [rbp+57h+var_70], r13
0x180009863  test    rcx, rcx
0x180009866  jz      short loc_1800097F5
0x180009868  mov     [rbp+57h+var_78], r13
0x18000986c  mov     rax, [rcx]
0x18000986f  mov     rax, [rax+10h]
0x180009873  jmp     loc_1800097F0
0x180009878  mov     rcx, [rbp+57h+var_70]; string
0x18000987c  lea     rax, [rbp+57h+var_58]
0x180009880  mov     [rbp+57h+var_68], rax
0x180009884  xor     edx, edx; length
0x180009886  lea     rax, [rbp+57h+var_58]
0x18000988a  mov     [rbp+57h+var_58+2], r13
0x18000988e  mov     [rbp+57h+var_60], rax
0x180009892  mov     [rbp+57h+var_4E], r13d
0x180009896  mov     [rbp+57h+var_4A], r13w
0x18000989b  mov     word ptr [rbp+57h+var_58], r13w
0x1800098a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800098a6  mov     rdx, rax
0x1800098a9  lea     rcx, [rbp+57h+var_68]
0x1800098ad  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800098b2  test    al, al
0x1800098b4  jnz     loc_180009978
0x1800098ba  mov     ebx, 8007000Eh
0x1800098bf  mov     r9d, r14d
0x1800098c2  mov     ecx, ebx
0x1800098c4  xor     edx, edx
0x1800098c6  call    Log_HREvent_4
0x1800098cb  mov     rcx, [rbp+57h+var_68]; void *
0x1800098cf  lea     rax, [rbp+57h+var_58]
0x1800098d3  cmp     rcx, rax
0x1800098d6  jz      short loc_1800098E4
0x1800098d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800098df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800098e4  mov     rcx, [rbp+57h+var_70]; string
0x1800098e8  call    cs:__imp_WindowsDeleteString
0x1800098ee  mov     rcx, [rbp+57h+var_78]
0x1800098f2  mov     [rbp+57h+var_70], r13
0x1800098f6  test    rcx, rcx
0x1800098f9  jz      short loc_18000990B
0x1800098fb  mov     [rbp+57h+var_78], r13
0x1800098ff  mov     rax, [rcx]
0x180009902  mov     rax, [rax+10h]
0x180009906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000990b  mov     rcx, [rbp+57h+var_80]
0x18000990f  test    rcx, rcx
0x180009912  jz      short loc_180009924
0x180009914  mov     [rbp+57h+var_80], r13
0x180009918  mov     rax, [rcx]
0x18000991b  mov     rax, [rax+10h]
0x18000991f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009924  mov     rcx, [rbp+57h+var_88]
0x180009928  test    rcx, rcx
0x18000992b  jz      short loc_18000993D
0x18000992d  mov     [rbp+57h+var_88], r13
0x180009931  mov     rax, [rcx]
0x180009934  mov     rax, [rax+10h]
0x180009938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993d  mov     rcx, [rbp+57h+var_90]
0x180009941  test    rcx, rcx
0x180009944  jz      short loc_180009956
0x180009946  mov     [rbp+57h+var_90], r13
0x18000994a  mov     rax, [rcx]
0x18000994d  mov     rax, [rax+10h]
0x180009951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009956  mov     rcx, [rbp+57h+var_98]
0x18000995a  test    rcx, rcx
0x18000995d  jz      loc_1800095B5
0x180009963  mov     [rbp+57h+var_98], r13
0x180009967  mov     rax, [rcx]
  ... truncated ...
```
