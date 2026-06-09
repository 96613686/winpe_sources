# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_DefaultAudioEndpointsExist(void)

- ea: `0x1800136d0`
- end: `0x1800138e7`
- name: `?_DefaultAudioEndpointsExist@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAA_NXZ`
- size: `535`
- prototype: `bool __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x18000e284`
- `0x180011e68`
- `0x1800136d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001389d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001389d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013714`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013751`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013751`

## pseudocode

```c
bool __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_DefaultAudioEndpointsExist(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this)
{
  HRESULT v1; // eax
  int v2; // edx
  unsigned int v3; // r8d
  int ActivationFactory; // eax
  __int64 v5; // r8
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  BOOL IsStringEmpty; // eax
  bool v13; // bl
  __int64 v14; // rcx
  BOOL v15; // [rsp+30h] [rbp-19h] BYREF
  BOOL v16; // [rsp+34h] [rbp-15h] BYREF
  __int64 v17; // [rsp+38h] [rbp-11h] BYREF
  HSTRING v18; // [rsp+40h] [rbp-9h] BYREF
  HSTRING v19; // [rsp+48h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string[5]; // [rsp+68h] [rbp+1Fh] BYREF

  v17 = 0;
  string[0] = 0;
  v1 = WindowsCreateStringReference(L"Windows.Media.Devices.MediaDevice", 0x21u, &hstringHeader, string);
  if ( v1 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
    JUMPOUT(0x1800138E6LL);
  }
  ActivationFactory = RoGetActivationFactory(string[0], &GUID_aa2d9a40_909f_4bba_bf8b_0c0d296f14f0, &v17);
  if ( ActivationFactory >= 0 )
  {
    v19 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v17 + 80LL))(v17, 0, &v19);
    if ( v8 < 0 )
      Log_HREvent_1((unsigned int)v8, 0, v9, 610);
    v18 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v17 + 72LL))(v17, 0, &v18);
    if ( v10 < 0 )
      Log_HREvent_1((unsigned int)v10, 0, v11, 613);
    if ( (unsigned int)dword_180025038 > 4 )
    {
      v15 = !WindowsIsStringEmpty(v18);
      IsStringEmpty = WindowsIsStringEmpty(v19);
      string[4] = (HSTRING)4;
      string[2] = (HSTRING)4;
      string[3] = (HSTRING)&v15;
      v16 = !IsStringEmpty;
      string[1] = (HSTRING)&v16;
      tlgWriteTransfer_EventWriteTransfer(
        (int)&dword_180025038,
        (int)&byte_180020BBF,
        0,
        0,
        4u,
        (PEVENT_DATA_DESCRIPTOR)&hstringHeader);
    }
    v13 = !WindowsIsStringEmpty(v19) && !WindowsIsStringEmpty(v18);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v19 )
      WindowsDeleteString(v19);
    v14 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v13;
  }
  else
  {
    Log_HREvent_1((unsigned int)ActivationFactory, 0, v5, 603);
    v6 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800136d0  mov     [rsp-8+arg_0], rbx
0x1800136d5  push    rbp
0x1800136d6  lea     rbp, [rsp-57h]
0x1800136db  sub     rsp, 0A0h
0x1800136e2  mov     rax, cs:__security_cookie
0x1800136e9  xor     rax, rsp
0x1800136ec  mov     [rbp+57h+var_10], rax
0x1800136f0  lea     r9, [rbp+57h+string]; string
0x1800136f4  mov     [rbp+57h+var_68], 0
0x1800136fc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180013700  mov     [rbp+57h+string], 0
0x180013708  mov     edx, 21h ; '!'; length
0x18001370d  lea     rcx, ?RuntimeClass_Windows_Media_Devices_MediaDevice@@3QBGB; "Windows.Media.Devices.MediaDevice"
0x180013714  call    cs:__imp_WindowsCreateStringReference
0x18001371a  test    eax, eax
0x18001371c  js      loc_1800138DF
0x180013722  mov     rcx, [rbp+57h+var_68]
0x180013726  mov     rbx, [rbp+57h+string]
0x18001372a  test    rcx, rcx
0x18001372d  jz      short loc_180013743
0x18001372f  mov     [rbp+57h+var_68], 0
0x180013737  mov     rax, [rcx]
0x18001373a  mov     rax, [rax+10h]
0x18001373e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013743  lea     r8, [rbp+57h+var_68]
0x180013747  mov     rcx, rbx
0x18001374a  lea     rdx, _GUID_aa2d9a40_909f_4bba_bf8b_0c0d296f14f0
0x180013751  call    cs:__imp_RoGetActivationFactory
0x180013757  xor     edx, edx
0x180013759  test    eax, eax
0x18001375b  jns     short loc_18001378E
0x18001375d  mov     r9d, 25Bh
0x180013763  mov     ecx, eax
0x180013765  call    Log_HREvent_1
0x18001376a  mov     rcx, [rbp+57h+var_68]
0x18001376e  test    rcx, rcx
0x180013771  jz      short loc_180013787
0x180013773  mov     [rbp+57h+var_68], 0
0x18001377b  mov     rax, [rcx]
0x18001377e  mov     rax, [rax+10h]
0x180013782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013787  xor     al, al
0x180013789  jmp     loc_1800138C2
0x18001378e  mov     rcx, [rbp+57h+var_68]
0x180013792  lea     r8, [rbp+57h+var_58]
0x180013796  mov     [rbp+57h+var_58], 0
0x18001379e  mov     rax, [rcx]
0x1800137a1  mov     rax, [rax+50h]
0x1800137a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137aa  test    eax, eax
0x1800137ac  jns     short loc_1800137BD
0x1800137ae  xor     edx, edx
0x1800137b0  mov     r9d, 262h
0x1800137b6  mov     ecx, eax
0x1800137b8  call    Log_HREvent_1
0x1800137bd  mov     rcx, [rbp+57h+var_68]
0x1800137c1  lea     r8, [rbp+57h+var_60]
0x1800137c5  mov     [rbp+57h+var_60], 0
0x1800137cd  xor     edx, edx
0x1800137cf  mov     rax, [rcx]
0x1800137d2  mov     rax, [rax+48h]
0x1800137d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137db  test    eax, eax
0x1800137dd  jns     short loc_1800137EE
0x1800137df  xor     edx, edx
0x1800137e1  mov     r9d, 265h
0x1800137e7  mov     ecx, eax
0x1800137e9  call    Log_HREvent_1
0x1800137ee  mov     eax, cs:dword_180025038
0x1800137f4  mov     ebx, 4
0x1800137f9  cmp     eax, ebx
0x1800137fb  jbe     short loc_180013863
0x1800137fd  mov     rcx, [rbp+57h+var_60]; string
0x180013801  call    cs:__imp_WindowsIsStringEmpty
0x180013807  xor     ecx, ecx
0x180013809  test    eax, eax
0x18001380b  setz    cl
0x18001380e  mov     [rbp+57h+var_70], ecx
0x180013811  mov     rcx, [rbp+57h+var_58]; string
0x180013815  call    cs:__imp_WindowsIsStringEmpty
0x18001381b  xor     ecx, ecx
0x18001381d  mov     [rbp+57h+var_18], rbx
0x180013821  test    eax, eax
0x180013823  mov     [rbp+57h+var_28], rbx
0x180013827  lea     rax, [rbp+57h+var_70]
0x18001382b  setz    cl
0x18001382e  mov     [rbp+57h+var_20], rax
0x180013832  lea     rax, [rbp+57h+var_6C]
0x180013836  mov     [rbp+57h+var_6C], ecx
0x180013839  mov     [rbp+57h+var_30], rax
0x18001383d  lea     rdx, byte_180020BBF; int
0x180013844  lea     rax, [rbp+57h+hstringHeader]
0x180013848  xor     r9d, r9d; int
0x18001384b  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x180013850  lea     rcx, dword_180025038; int
0x180013857  xor     r8d, r8d; int
0x18001385a  mov     [rsp+0A0h+var_80], ebx; ULONG
0x18001385e  call    _tlgWriteTransfer_EventWriteTransfer
0x180013863  mov     rcx, [rbp+57h+var_58]; string
0x180013867  call    cs:__imp_WindowsIsStringEmpty
0x18001386d  test    eax, eax
0x18001386f  jnz     short loc_180013883
0x180013871  mov     rcx, [rbp+57h+var_60]; string
0x180013875  call    cs:__imp_WindowsIsStringEmpty
0x18001387b  test    eax, eax
0x18001387d  jnz     short loc_180013883
0x18001387f  mov     bl, 1
0x180013881  jmp     short loc_180013885
0x180013883  xor     bl, bl
0x180013885  mov     rcx, [rbp+57h+var_60]; string
0x180013889  test    rcx, rcx
0x18001388c  jz      short loc_180013894
0x18001388e  call    cs:__imp_WindowsDeleteString
0x180013894  mov     rcx, [rbp+57h+var_58]; string
0x180013898  test    rcx, rcx
0x18001389b  jz      short loc_1800138A3
0x18001389d  call    cs:__imp_WindowsDeleteString
0x1800138a3  mov     rcx, [rbp+57h+var_68]
0x1800138a7  test    rcx, rcx
0x1800138aa  jz      short loc_1800138C0
0x1800138ac  mov     [rbp+57h+var_68], 0
0x1800138b4  mov     rdx, [rcx]
0x1800138b7  mov     rax, [rdx+10h]
0x1800138bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138c0  mov     al, bl
0x1800138c2  mov     rcx, [rbp+57h+var_10]
0x1800138c6  xor     rcx, rsp; StackCookie
0x1800138c9  call    __security_check_cookie
0x1800138ce  mov     rbx, [rsp+0A0h+arg_0]
0x1800138d6  add     rsp, 0A0h
0x1800138dd  pop     rbp
0x1800138de  retn
0x1800138df  mov     ecx, eax; this
0x1800138e1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
