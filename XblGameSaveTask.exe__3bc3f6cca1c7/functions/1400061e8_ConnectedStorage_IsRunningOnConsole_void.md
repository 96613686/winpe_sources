# ConnectedStorage::IsRunningOnConsole(void)

- ea: `0x1400061e8`
- end: `0x14000639b`
- name: `?IsRunningOnConsole@ConnectedStorage@@YA_NXZ`
- size: `435`
- prototype: `bool __fastcall(ConnectedStorage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005ec0`

## callees

- `0x140001480`
- `0x1400061e8`
- `0x1400063a4`
- `0x140007010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400062c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400062c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400062b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400062b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140006292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400062d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000632b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140006292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400062d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000632b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000623c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000623c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006259`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006259`

## pseudocode

```c
bool __fastcall ConnectedStorage::IsRunningOnConsole(ConnectedStorage *this)
{
  HRESULT v1; // eax
  int v2; // edx
  unsigned int v3; // r8d
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  bool v7; // bl
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  HSTRING v13; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  v15 = 0;
  v14 = 0;
  v13 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(L"Windows.System.Profile.AnalyticsInfo", 0x24u, &hstringHeader, &string);
  if ( v1 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
    JUMPOUT(0x14000639ALL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305, &v15) < 0
    || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, &v14) < 0
    || (v4 = v14,
        v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 48LL),
        WindowsDeleteString(v13),
        v13 = 0,
        v5(v4, &v13) < 0) )
  {
    WindowsDeleteString(v13);
    v13 = 0;
    v11 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 0;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v13, 0);
    v7 = (unsigned int)_o__wcsicmp(L"Windows.Xbox", StringRawBuffer) == 0;
    WindowsDeleteString(v13);
    v13 = 0;
    v8 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x1400061e8  mov     [rsp-8+arg_0], rbx
0x1400061ed  mov     [rsp-8+arg_8], rdi
0x1400061f2  push    rbp
0x1400061f3  mov     rbp, rsp
0x1400061f6  sub     rsp, 60h
0x1400061fa  mov     rax, cs:__security_cookie
0x140006201  xor     rax, rsp
0x140006204  mov     [rbp+var_8], rax
0x140006208  mov     [rbp+var_30], 0
0x140006210  mov     [rbp+var_38], 0
0x140006218  mov     [rbp+var_40], 0
0x140006220  mov     [rbp+string], 0
0x140006228  lea     r9, [rbp+string]; string
0x14000622c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140006230  mov     edx, 24h ; '$'; length
0x140006235  lea     rcx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QBGB; "Windows.System.Profile.AnalyticsInfo"
0x14000623c  call    cs:__imp_WindowsCreateStringReference
0x140006242  test    eax, eax
0x140006244  js      loc_140006393
0x14000624a  lea     r8, [rbp+var_30]
0x14000624e  lea     rdx, _GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305
0x140006255  mov     rcx, [rbp+string]
0x140006259  call    cs:__imp_RoGetActivationFactory
0x14000625f  test    eax, eax
0x140006261  js      loc_140006327
0x140006267  mov     rcx, [rbp+var_30]
0x14000626b  mov     rax, [rcx]
0x14000626e  lea     rdx, [rbp+var_38]
0x140006272  mov     rax, [rax+30h]
0x140006276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000627b  test    eax, eax
0x14000627d  js      loc_140006327
0x140006283  mov     rdi, [rbp+var_38]
0x140006287  mov     rax, [rdi]
0x14000628a  mov     rbx, [rax+30h]
0x14000628e  mov     rcx, [rbp+var_40]; string
0x140006292  call    cs:__imp_WindowsDeleteString
0x140006298  mov     [rbp+var_40], 0
0x1400062a0  lea     rdx, [rbp+var_40]
0x1400062a4  mov     rcx, rdi
0x1400062a7  mov     rax, rbx
0x1400062aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062af  test    eax, eax
0x1400062b1  js      short loc_140006327
0x1400062b3  xor     edx, edx; length
0x1400062b5  mov     rcx, [rbp+var_40]; string
0x1400062b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1400062bf  mov     rdx, rax
0x1400062c2  lea     rcx, aWindowsXbox; "Windows.Xbox"
0x1400062c9  call    cs:__imp__o__wcsicmp
0x1400062cf  nop
0x1400062d0  test    eax, eax
0x1400062d2  setz    bl
0x1400062d5  mov     rcx, [rbp+var_40]; string
0x1400062d9  call    cs:__imp_WindowsDeleteString
0x1400062df  mov     [rbp+var_40], 0
0x1400062e7  mov     rcx, [rbp+var_38]
0x1400062eb  test    rcx, rcx
0x1400062ee  jz      short loc_140006305
0x1400062f0  mov     [rbp+var_38], 0
0x1400062f8  mov     rax, [rcx]
0x1400062fb  mov     rax, [rax+10h]
0x1400062ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006304  nop
0x140006305  mov     rcx, [rbp+var_30]
0x140006309  test    rcx, rcx
0x14000630c  jz      short loc_140006323
0x14000630e  mov     [rbp+var_30], 0
0x140006316  mov     rdx, [rcx]
0x140006319  mov     rax, [rdx+10h]
0x14000631d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006322  nop
0x140006323  mov     al, bl
0x140006325  jmp     short loc_140006377
0x140006327  mov     rcx, [rbp+var_40]; string
0x14000632b  call    cs:__imp_WindowsDeleteString
0x140006331  mov     [rbp+var_40], 0
0x140006339  mov     rcx, [rbp+var_38]
0x14000633d  test    rcx, rcx
0x140006340  jz      short loc_140006357
0x140006342  mov     [rbp+var_38], 0
0x14000634a  mov     rax, [rcx]
0x14000634d  mov     rax, [rax+10h]
0x140006351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006356  nop
0x140006357  mov     rcx, [rbp+var_30]
0x14000635b  test    rcx, rcx
0x14000635e  jz      short loc_140006375
0x140006360  mov     [rbp+var_30], 0
0x140006368  mov     rax, [rcx]
0x14000636b  mov     rax, [rax+10h]
0x14000636f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006374  nop
0x140006375  xor     al, al
0x140006377  mov     rcx, [rbp+var_8]
0x14000637b  xor     rcx, rsp; StackCookie
0x14000637e  call    __security_check_cookie
0x140006383  mov     rbx, [rsp+60h+arg_0]
0x140006388  mov     rdi, [rsp+60h+arg_8]
0x14000638d  add     rsp, 60h
0x140006391  pop     rbp
0x140006392  retn
0x140006393  mov     ecx, eax; this
0x140006395  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
