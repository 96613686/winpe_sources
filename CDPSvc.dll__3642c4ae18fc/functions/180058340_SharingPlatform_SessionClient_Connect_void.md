# SharingPlatform::SessionClient::Connect(void)

- ea: `0x180058340`
- end: `0x180058853`
- name: `?Connect@SessionClient@SharingPlatform@@UEAAJXZ`
- size: `1299`
- prototype: `__int64 __fastcall(SharingPlatform::SessionClient *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x180006550`
- `0x180010c58`
- `0x18001177c`
- `0x1800130ec`
- `0x18001620c`
- `0x180016248`
- `0x18001b404`
- `0x1800225a0`
- `0x180041874`
- `0x180055f04`
- `0x18005715c`
- `0x180057220`
- `0x180057a34`
- `0x180058340`
- `0x180058974`
- `0x1800591b0`
- `0x18005e778`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005845f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005847d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005864c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800586a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005845f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005847d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005864c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800586a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800587b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800587b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800585e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800585e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058609`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800586d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800586d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005880e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005880e`

## pseudocode

```c
__int64 __fastcall SharingPlatform::SessionClient::Connect(SharingPlatform::SessionClient *this)
{
  unsigned int v2; // edi
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  SharingPlatform::Internal::CDPDeviceCallback *v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rax
  HSTRING v15; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // rax
  int started; // r15d
  int v19; // eax
  int v21; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  __int16 v23; // [rsp+68h] [rbp-21h] BYREF
  __int16 v24; // [rsp+6Ah] [rbp-1Fh] BYREF
  __int16 v25; // [rsp+6Ch] [rbp-1Dh] BYREF
  __int16 v26; // [rsp+6Eh] [rbp-1Bh] BYREF
  __int16 v27; // [rsp+70h] [rbp-19h] BYREF
  __int16 v28; // [rsp+72h] [rbp-17h] BYREF
  __int16 v29; // [rsp+74h] [rbp-15h] BYREF
  __int16 v30; // [rsp+76h] [rbp-13h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-11h] BYREF
  __int64 v32; // [rsp+80h] [rbp-9h] BYREF
  __int64 v33; // [rsp+88h] [rbp-1h] BYREF
  SharingPlatform::Internal::CDPDeviceCallback *v34; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v35[32]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v23 = *((unsigned __int8 *)this + 111);
  v24 = *((unsigned __int8 *)this + 110);
  v25 = *((unsigned __int8 *)this + 109);
  v26 = *((unsigned __int8 *)this + 108);
  v27 = *((unsigned __int8 *)this + 107);
  v28 = *((unsigned __int8 *)this + 106);
  v29 = *((unsigned __int8 *)this + 105);
  v30 = *((unsigned __int8 *)this + 104);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[112],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    L"SessionClient::Connect sessionId={%08lX-%04hX-%04hX-%02hX%02hX-%02hX%02hX%02hX%02hX%02hX%02hX}",
    (__int64)&v30,
    (__int64)&v29,
    (__int64)&v28,
    (__int64)&v27,
    (__int64)&v26,
    (__int64)&v25,
    (__int64)&v24,
    (__int64)&v23);
  v32 = 0;
  v34 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_DWORD *)this + 144) )
  {
    v2 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)0x8007139FLL,
      v21);
    if ( this != (SharingPlatform::SessionClient *)-56LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    goto LABEL_48;
  }
  *((_DWORD *)this + 144) = 1;
  if ( this != (SharingPlatform::SessionClient *)-56LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v3 = *((_QWORD *)this + 14);
  v31 = 0;
  v33 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v3 + 64LL);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  v5 = v4(v3, &v31);
  v2 = v5;
  if ( v5 < 0 )
  {
    v6 = 491;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)(unsigned int)v5,
      v21);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
    goto LABEL_48;
  }
  v5 = Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifier>::As<SharingPlatform::IDeviceIdentifierInternal>(
         &v31,
         (__int64)&v33);
  v2 = v5;
  if ( v5 < 0 )
  {
    v6 = 492;
    goto LABEL_8;
  }
  v7 = v33;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 56LL);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v32);
  v5 = v8(v7, &v32);
  v2 = v5;
  if ( v5 < 0 )
  {
    v6 = 496;
    goto LABEL_8;
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
  string = (HSTRING)this;
  Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(&v34);
  v9 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPDeviceCallback,SharingPlatform::Internal::CDPDeviceCallback,SharingPlatform::SessionClient *>(
         &v34,
         &string);
  v2 = v9;
  if ( v9 < 0 )
  {
    v10 = 507;
LABEL_15:
    v11 = (unsigned int)v9;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)v11,
      v21);
    goto LABEL_48;
  }
  v12 = v34;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v32 + 48LL))(
         v32,
         -(__int64)(v34 != 0) & ((unsigned __int64)v34 + 8));
  v2 = v9;
  if ( v9 < 0 )
  {
    v10 = 508;
    goto LABEL_15;
  }
  LOBYTE(v13) = 1;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 56LL))(v32, 18, v13);
  v2 = v9;
  if ( v9 < 0 )
  {
    v10 = 511;
    goto LABEL_15;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 63), 0x7530u) )
  {
    v2 = -2147023436;
    v10 = 525;
    v11 = 2147943860LL;
    goto LABEL_16;
  }
  ResetEvent(*((HANDLE *)this + 63));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_DWORD *)this + 144) )
  {
    Microsoft::WRL::ComPtr<ICDPDevice>::operator=((char *)this + 488, &v32);
    if ( *((SharingPlatform::Internal::CDPDeviceCallback **)this + 59) != v12 )
    {
      string = (HSTRING)v12;
      Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPDeviceCallback>::InternalAddRef(&string);
      string = (HSTRING)*((_QWORD *)this + 59);
      *((_QWORD *)this + 59) = v12;
      Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(&string);
    }
    if ( this != (SharingPlatform::SessionClient *)-56LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v35);
    SharingPlatform::Internal::MakeChannelLocator(&string, (const GUID *)this + 6, *(HSTRING *)(v14 + 24));
    v15 = string;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v17 = std::wstring::wstring(v35, StringRawBuffer);
    started = SharingPlatform::SessionClient::CreateAndStartSessionStream(this, v17, (char *)this + 128);
    std::wstring::_Tidy_deallocate(v35);
    if ( started < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)".\\sessionclient.cpp",
        (const char *)(unsigned int)started,
        v21);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      SharingPlatform::Internal::CDPDeviceCallback::Close(*((SharingPlatform::Internal::CDPDeviceCallback **)this + 59));
      if ( *((int *)this + 144) >= 2 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 61) + 72LL))(*((_QWORD *)this + 61));
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 488);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 128);
      *((_DWORD *)this + 144) = 0;
      if ( this != (SharingPlatform::SessionClient *)-56LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      *((_DWORD *)this + 144) = 3;
      if ( this != (SharingPlatform::SessionClient *)-56LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      string = 0;
      v19 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
              (SharingPlatform::SessionClient *)((char *)this + 568),
              (struct IInspectable **)&string);
      v2 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)".\\sessionclient.cpp",
          (const char *)(unsigned int)v19,
          v21);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&string);
        WindowsDeleteString(v15);
        goto LABEL_48;
      }
      if ( string )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 104LL))(string);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&string);
    }
    WindowsDeleteString(v15);
    v2 = started;
    goto LABEL_48;
  }
  if ( v12 )
    SharingPlatform::Internal::CDPDeviceCallback::Close(v12);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 72LL))(v32);
  if ( this != (SharingPlatform::SessionClient *)-56LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v2 = -2147467260;
LABEL_48:
  Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v32);
  return v2;
}

```

## disassembly

```asm
0x180058340  mov     [rsp-8+arg_8], rbx
0x180058345  mov     [rsp-8+arg_10], rsi
0x18005834a  push    rbp
0x18005834b  push    rdi
0x18005834c  push    r12
0x18005834e  push    r14
0x180058350  push    r15
0x180058352  lea     rbp, [rsp-37h]
0x180058357  sub     rsp, 0C0h
0x18005835e  mov     rax, cs:__security_cookie
0x180058365  xor     rax, rsp
0x180058368  mov     [rbp+57h+var_28], rax
0x18005836c  movzx   eax, byte ptr [rcx+6Fh]
0x180058370  lea     r9, [rcx+66h]
0x180058374  mov     word ptr [rbp+57h+var_78], ax
0x180058378  lea     r8, [rcx+64h]
0x18005837c  movzx   eax, byte ptr [rcx+6Eh]
0x180058380  lea     rdx, [rcx+60h]
0x180058384  mov     word ptr [rbp+57h+var_78+2], ax
0x180058388  mov     r14, rcx
0x18005838b  movzx   eax, byte ptr [rcx+6Dh]
0x18005838f  mov     word ptr [rbp+57h+var_78+4], ax
0x180058393  movzx   eax, byte ptr [rcx+6Ch]
0x180058397  mov     word ptr [rbp+57h+var_78+6], ax
0x18005839b  movzx   eax, byte ptr [rcx+6Bh]
0x18005839f  mov     word ptr [rbp+57h+var_70], ax
0x1800583a3  movzx   eax, byte ptr [rcx+6Ah]
0x1800583a7  mov     word ptr [rbp+57h+var_70+2], ax
0x1800583ab  movzx   eax, byte ptr [rcx+69h]
0x1800583af  mov     word ptr [rbp+57h+var_70+4], ax
0x1800583b3  movzx   eax, byte ptr [rcx+68h]
0x1800583b7  lea     rcx, aSessionclientC; "SessionClient::Connect sessionId={%08lX"...
0x1800583be  mov     word ptr [rbp+57h+var_70+6], ax
0x1800583c2  lea     rax, [rbp+57h+var_78]
0x1800583c6  mov     [rsp+0E0h+var_88], rax; __int64
0x1800583cb  lea     rax, [rbp+57h+var_78+2]
0x1800583cf  mov     [rsp+0E0h+var_90], rax; __int64
0x1800583d4  lea     rax, [rbp+57h+var_78+4]
0x1800583d8  mov     [rsp+0E0h+var_98], rax; __int64
0x1800583dd  lea     rax, [rbp+57h+var_78+6]
0x1800583e1  mov     [rsp+0E0h+var_A0], rax; __int64
0x1800583e6  lea     rax, [rbp+57h+var_70]
0x1800583ea  mov     [rsp+0E0h+var_A8], rax; __int64
0x1800583ef  lea     rax, [rbp+57h+var_70+2]
0x1800583f3  mov     [rsp+0E0h+var_B0], rax; __int64
0x1800583f8  lea     rax, [rbp+57h+var_70+4]
0x1800583fc  mov     [rsp+0E0h+var_B8], rax; __int64
0x180058401  lea     rax, [rbp+57h+var_70+6]
0x180058405  mov     [rsp+0E0h+var_C0], rax; int
0x18005840a  call    ??$LogInfo@AEAY0HA@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0HA@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[112],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[112],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x18005840f  lea     rsi, [r14+38h]
0x180058413  mov     [rbp+57h+var_60], 0
0x18005841b  mov     rcx, rsi; lpCriticalSection
0x18005841e  mov     [rbp+57h+var_50], 0
0x180058426  call    cs:__imp_EnterCriticalSection
0x18005842c  cmp     dword ptr [r14+240h], 0
0x180058434  jz      short loc_18005846A
0x180058436  mov     rcx, [rbp+5Fh]; this
0x18005843a  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180058441  mov     edi, 8007139Fh
0x180058446  mov     edx, 1E3h; void *
0x18005844b  mov     r9d, edi; char *
0x18005844e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058453  test    rsi, rsi
0x180058456  jz      loc_180058817
0x18005845c  mov     rcx, rsi; lpCriticalSection
0x18005845f  call    cs:__imp_LeaveCriticalSection
0x180058465  jmp     loc_180058817
0x18005846a  mov     dword ptr [r14+240h], 1
0x180058475  test    rsi, rsi
0x180058478  jz      short loc_180058483
0x18005847a  mov     rcx, rsi; lpCriticalSection
0x18005847d  call    cs:__imp_LeaveCriticalSection
0x180058483  mov     rdi, [r14+70h]
0x180058487  lea     rcx, [rbp+57h+var_68]
0x18005848b  mov     [rbp+57h+var_68], 0
0x180058493  mov     [rbp+57h+var_58], 0
0x18005849b  mov     rax, [rdi]
0x18005849e  mov     rbx, [rax+40h]
0x1800584a2  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800584a7  lea     rdx, [rbp+57h+var_68]
0x1800584ab  mov     rcx, rdi
0x1800584ae  mov     rax, rbx
0x1800584b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584b6  mov     edi, eax
0x1800584b8  test    eax, eax
0x1800584ba  jns     short loc_1800584EB
0x1800584bc  mov     edx, 1EBh; void *
0x1800584c1  mov     rcx, [rbp+5Fh]; this
0x1800584c5  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x1800584cc  mov     r9d, eax; char *
0x1800584cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800584d4  lea     rcx, [rbp+57h+var_58]
0x1800584d8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800584dd  lea     rcx, [rbp+57h+var_68]
0x1800584e1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800584e6  jmp     loc_180058817
0x1800584eb  lea     rdx, [rbp+57h+var_58]
0x1800584ef  lea     rcx, [rbp+57h+var_68]
0x1800584f3  call    ??$As@UIDeviceIdentifierInternal@SharingPlatform@@@?$ComPtr@UIDeviceIdentifier@SharingPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDeviceIdentifierInternal@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifier>::As<SharingPlatform::IDeviceIdentifierInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifierInternal>>)
0x1800584f8  mov     edi, eax
0x1800584fa  test    eax, eax
0x1800584fc  jns     short loc_180058505
0x1800584fe  mov     edx, 1ECh
0x180058503  jmp     short loc_1800584C1
0x180058505  mov     rdi, [rbp+57h+var_58]
0x180058509  lea     rcx, [rbp+57h+var_60]
0x18005850d  mov     rax, [rdi]
0x180058510  mov     rbx, [rax+38h]
0x180058514  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058519  lea     rdx, [rbp+57h+var_60]
0x18005851d  mov     rcx, rdi
0x180058520  mov     rax, rbx
0x180058523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058528  mov     edi, eax
0x18005852a  test    eax, eax
0x18005852c  jns     short loc_180058535
0x18005852e  mov     edx, 1F0h
0x180058533  jmp     short loc_1800584C1
0x180058535  lea     rcx, [rbp+57h+var_58]
0x180058539  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005853e  lea     rcx, [rbp+57h+var_68]
0x180058542  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058547  lea     rcx, [rbp+57h+var_50]
0x18005854b  mov     [rbp+57h+string], r14
0x18005854f  call    ?InternalRelease@?$ComPtr@VCDPBinaryClientCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(void)
0x180058554  lea     rdx, [rbp+57h+string]
0x180058558  lea     rcx, [rbp+57h+var_50]
0x18005855c  call    ??$MakeAndInitialize@VCDPDeviceCallback@Internal@SharingPlatform@@V123@PEAVSessionClient@3@@Details@WRL@Microsoft@@YAJPEAPEAVCDPDeviceCallback@Internal@SharingPlatform@@$$QEAPEAVSessionClient@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPDeviceCallback,SharingPlatform::Internal::CDPDeviceCallback,SharingPlatform::SessionClient *>(SharingPlatform::Internal::CDPDeviceCallback * *,SharingPlatform::SessionClient * &&)
0x180058561  mov     edi, eax
0x180058563  test    eax, eax
0x180058565  jns     short loc_180058584
0x180058567  mov     edx, 1FBh; void *
0x18005856c  mov     r9d, eax; char *
0x18005856f  mov     rcx, [rbp+5Fh]; this
0x180058573  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x18005857a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005857f  jmp     loc_180058817
0x180058584  mov     rcx, [rbp+57h+var_60]
0x180058588  mov     rbx, [rbp+57h+var_50]
0x18005858c  mov     rax, rbx
0x18005858f  neg     rax
0x180058592  mov     r9, [rcx]
0x180058595  sbb     r8, r8
0x180058598  lea     rdx, [rbx+8]
0x18005859c  and     rdx, r8
0x18005859f  mov     rax, [r9+30h]
0x1800585a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585a8  mov     edi, eax
0x1800585aa  test    eax, eax
0x1800585ac  jns     short loc_1800585B5
0x1800585ae  mov     edx, 1FCh
0x1800585b3  jmp     short loc_18005856C
0x1800585b5  mov     rcx, [rbp+57h+var_60]
0x1800585b9  mov     r8b, 1
0x1800585bc  mov     edx, 12h
0x1800585c1  mov     rax, [rcx]
0x1800585c4  mov     rax, [rax+38h]
0x1800585c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585cd  mov     edi, eax
0x1800585cf  test    eax, eax
0x1800585d1  jns     short loc_1800585DA
0x1800585d3  mov     edx, 1FFh
0x1800585d8  jmp     short loc_18005856C
0x1800585da  mov     rcx, [r14+1F8h]; hHandle
0x1800585e1  mov     edx, 7530h; dwMilliseconds
0x1800585e6  call    cs:__imp_WaitForSingleObject
0x1800585ec  test    eax, eax
0x1800585ee  jz      short loc_180058602
0x1800585f0  mov     edi, 800705B4h
0x1800585f5  mov     edx, 20Dh
0x1800585fa  mov     r9d, edi
0x1800585fd  jmp     loc_18005856F
0x180058602  mov     rcx, [r14+1F8h]; hEvent
0x180058609  call    cs:__imp_ResetEvent
0x18005860f  mov     rcx, rsi; lpCriticalSection
0x180058612  call    cs:__imp_EnterCriticalSection
0x180058618  cmp     dword ptr [r14+240h], 0
0x180058620  jnz     short loc_18005865C
0x180058622  test    rbx, rbx
0x180058625  jz      short loc_18005862F
0x180058627  mov     rcx, rbx; this
0x18005862a  call    ?Close@CDPDeviceCallback@Internal@SharingPlatform@@QEAAXXZ; SharingPlatform::Internal::CDPDeviceCallback::Close(void)
0x18005862f  mov     rcx, [rbp+57h+var_60]
0x180058633  test    rcx, rcx
0x180058636  jz      short loc_180058644
0x180058638  mov     rax, [rcx]
0x18005863b  mov     rax, [rax+48h]
0x18005863f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058644  test    rsi, rsi
0x180058647  jz      short loc_180058652
0x180058649  mov     rcx, rsi; lpCriticalSection
0x18005864c  call    cs:__imp_LeaveCriticalSection
0x180058652  mov     edi, 80004004h
0x180058657  jmp     loc_180058817
0x18005865c  lea     rdi, [r14+1E8h]
0x180058663  mov     rcx, rdi
0x180058666  lea     rdx, [rbp+57h+var_60]
0x18005866a  call    ??4?$ComPtr@VICDPDevice@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ICDPDevice>::operator=(Microsoft::WRL::ComPtr<ICDPDevice> const &)
0x18005866f  cmp     [r14+1D8h], rbx
0x180058676  jz      short loc_1800586A0
0x180058678  lea     rcx, [rbp+57h+string]
0x18005867c  mov     [rbp+57h+string], rbx
0x180058680  call    ?InternalAddRef@?$ComPtr@VCDPDeviceCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPDeviceCallback>::InternalAddRef(void)
0x180058685  mov     r8, [r14+1D8h]
0x18005868c  lea     rcx, [rbp+57h+string]
0x180058690  mov     [rbp+57h+string], r8
0x180058694  mov     [r14+1D8h], rbx
0x18005869b  call    ?InternalRelease@?$ComPtr@VCDPBinaryClientCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(void)
0x1800586a0  test    rsi, rsi
0x1800586a3  jz      short loc_1800586AE
0x1800586a5  mov     rcx, rsi; lpCriticalSection
0x1800586a8  call    cs:__imp_LeaveCriticalSection
0x1800586ae  lea     rcx, [rbp+57h+var_48]
0x1800586b2  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800586b7  lea     rdx, [r14+60h]
0x1800586bb  lea     rcx, [rbp+57h+string]
0x1800586bf  mov     r8, [rax+18h]
0x1800586c3  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x1800586c8  mov     rbx, [rbp+57h+string]
0x1800586cc  xor     edx, edx; length
0x1800586ce  mov     rcx, rbx; string
0x1800586d1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800586d7  mov     rdx, rax
0x1800586da  lea     rcx, [rbp+57h+var_48]
0x1800586de  lea     r12, [r14+80h]
0x1800586e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800586ea  mov     rdx, rax
0x1800586ed  mov     r8, r12
0x1800586f0  mov     rcx, r14
0x1800586f3  call    ?CreateAndStartSessionStream@SessionClient@SharingPlatform@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDPBinaryClientContainer@2@@Z; SharingPlatform::SessionClient::CreateAndStartSessionStream(std::wstring const &,SharingPlatform::CDPBinaryClientContainer *)
0x1800586f8  lea     rcx, [rbp+57h+var_48]
0x1800586fc  mov     r15d, eax
0x1800586ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058704  test    r15d, r15d
0x180058707  js      loc_18005879C
0x18005870d  mov     rcx, rsi; lpCriticalSection
0x180058710  call    cs:__imp_EnterCriticalSection
0x180058716  mov     dword ptr [r14+240h], 3
0x180058721  test    rsi, rsi
0x180058724  jz      short loc_18005872F
0x180058726  mov     rcx, rsi; lpCriticalSection
0x180058729  call    cs:__imp_LeaveCriticalSection
0x18005872f  lea     rcx, [r14+238h]; this
0x180058736  mov     [rbp+57h+string], 0
0x18005873e  lea     rdx, [rbp+57h+string]; struct IInspectable **
0x180058742  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x180058747  mov     edi, eax
0x180058749  test    eax, eax
0x18005874b  jns     short loc_18005877C
0x18005874d  mov     rcx, [rbp+5Fh]; this
0x180058751  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180058758  mov     r9d, eax; char *
0x18005875b  mov     edx, 236h; void *
0x180058760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058765  lea     rcx, [rbp+57h+string]
0x180058769  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005876e  mov     rcx, rbx; string
0x180058771  call    cs:__imp_WindowsDeleteString
0x180058777  jmp     loc_180058817
0x18005877c  mov     rcx, [rbp+57h+string]
0x180058780  test    rcx, rcx
0x180058783  jz      short loc_180058791
0x180058785  mov     rax, [rcx]
0x180058788  mov     rax, [rax+68h]
0x18005878c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058791  lea     rcx, [rbp+57h+string]
0x180058795  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005879a  jmp     short loc_18005880B
0x18005879c  mov     rcx, [rbp+5Fh]; this
0x1800587a0  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x1800587a7  mov     r9d, r15d; char *
0x1800587aa  mov     edx, 23Dh; void *
0x1800587af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800587b4  mov     rcx, rsi; lpCriticalSection
0x1800587b7  call    cs:__imp_EnterCriticalSection
0x1800587bd  mov     rcx, [r14+1D8h]; this
0x1800587c4  call    ?Close@CDPDeviceCallback@Internal@SharingPlatform@@QEAAXXZ; SharingPlatform::Internal::CDPDeviceCallback::Close(void)
0x1800587c9  cmp     dword ptr [r14+240h], 2
0x1800587d1  jl      short loc_1800587E2
0x1800587d3  mov     rcx, [rdi]
0x1800587d6  mov     rax, [rcx]
0x1800587d9  mov     rax, [rax+48h]
0x1800587dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587e2  mov     rcx, rdi
0x1800587e5  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800587ea  mov     rcx, r12
0x1800587ed  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800587f2  mov     dword ptr [r14+240h], 0
0x1800587fd  test    rsi, rsi
0x180058800  jz      short loc_18005880B
0x180058802  mov     rcx, rsi; lpCriticalSection
0x180058805  call    cs:__imp_LeaveCriticalSection
0x18005880b  mov     rcx, rbx; string
0x18005880e  call    cs:__imp_WindowsDeleteString
0x180058814  mov     edi, r15d
0x180058817  lea     rcx, [rbp+57h+var_50]
0x18005881b  call    ?InternalRelease@?$ComPtr@VCDPBinaryClientCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(void)
0x180058820  lea     rcx, [rbp+57h+var_60]
0x180058824  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
  ... truncated ...
```
