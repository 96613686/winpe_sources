# SharingPlatform::SessionHost::Connect(void)

- ea: `0x18005bdd0`
- end: `0x18005c0cf`
- name: `?Connect@SessionHost@SharingPlatform@@UEAAJXZ`
- size: `767`
- prototype: `__int64 __fastcall(SharingPlatform::SessionHost *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x180006550`
- `0x18001177c`
- `0x1800130ec`
- `0x18001620c`
- `0x180016248`
- `0x18001a5b4`
- `0x1800225a0`
- `0x180055f04`
- `0x180056874`
- `0x18005715c`
- `0x18005b8e8`
- `0x18005bdd0`
- `0x18005c0d8`
- `0x18005c1f8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005beeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bf0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bfc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005beeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bf0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bfc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005be99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bfb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005be99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bfb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bf45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c0af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c0af`

## pseudocode

```c
__int64 __fastcall SharingPlatform::SessionHost::Connect(SharingPlatform::SessionHost *this)
{
  __int64 v2; // rdx
  __int64 v4; // rax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v6; // rax
  unsigned __int64 v7; // rdx
  int started; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-59h]
  __int16 v14; // [rsp+60h] [rbp-19h] BYREF
  __int16 v15; // [rsp+62h] [rbp-17h] BYREF
  __int16 v16; // [rsp+64h] [rbp-15h] BYREF
  __int16 v17; // [rsp+66h] [rbp-13h] BYREF
  __int16 v18; // [rsp+68h] [rbp-11h] BYREF
  __int16 v19; // [rsp+6Ah] [rbp-Fh] BYREF
  __int16 v20; // [rsp+6Ch] [rbp-Dh] BYREF
  __int16 v21; // [rsp+6Eh] [rbp-Bh] BYREF
  struct IInspectable *p_string; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  __int128 v24; // [rsp+80h] [rbp+7h] BYREF
  __int64 v25; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v14 = *((unsigned __int8 *)this + 127);
  v15 = *((unsigned __int8 *)this + 126);
  v16 = *((unsigned __int8 *)this + 125);
  v17 = *((unsigned __int8 *)this + 124);
  v18 = *((unsigned __int8 *)this + 123);
  v19 = *((unsigned __int8 *)this + 122);
  v20 = *((unsigned __int8 *)this + 121);
  v21 = *((unsigned __int8 *)this + 120);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[112],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    L"SessionHost::Connect sessionGUID={%08lX-%04hX-%04hX-%02hX%02hX-%02hX%02hX%02hX%02hX%02hX%02hX}",
    (__int64)&v21,
    (__int64)&v20,
    (__int64)&v19,
    (__int64)&v18,
    (__int64)&v17,
    (__int64)&v16,
    (__int64)&v15,
    (__int64)&v14);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( !*((_BYTE *)this + 144) )
  {
    if ( *((_BYTE *)this + 145) )
    {
      v2 = 237;
      goto LABEL_7;
    }
    if ( *((_BYTE *)this + 146) )
    {
      v2 = 238;
      goto LABEL_7;
    }
    *((_BYTE *)this + 145) = 1;
    if ( this != (SharingPlatform::SessionHost *)-64LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    string = (HSTRING)this;
    p_string = (struct IInspectable *)&string;
    ScopeWarden__lambda_a4d2f7be06f8df519d7a2767006f083d___::_ScopeWarden__lambda_a4d2f7be06f8df519d7a2767006f083d___(&p_string);
    v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24);
    SharingPlatform::Internal::MakeChannelLocator(&string, (const GUID *)this + 7, *(HSTRING *)(v4 + 24));
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (_QWORD *)std::wstring::wstring(&v24, StringRawBuffer);
    LOBYTE(v7) = 1;
    started = SharingPlatform::SessionHost::CreateAndStartSessionStream((__int64)this, v7, v6, (__int64 *)this + 20);
    std::wstring::_Tidy_deallocate(&v24);
    if ( started >= 0 )
    {
      v11 = SharingPlatform::SessionHost::CreateAndStartAllSessionStreams(this);
      started = v11;
      if ( v11 >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        *((_WORD *)this + 72) = 1;
        if ( this != (SharingPlatform::SessionHost *)-64LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        v25 = 0;
        p_string = 0;
        v24 = 0;
        v12 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
                (SharingPlatform::SessionHost *)((char *)this + 152),
                &p_string);
        started = v12;
        if ( v12 >= 0 )
        {
          if ( p_string )
            ((void (__fastcall *)(struct IInspectable *, _QWORD, __int128 *))p_string->lpVtbl[2].Release)(
              p_string,
              *((_QWORD *)this + 36),
              &v24);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&p_string);
          if ( (_QWORD)v24 )
          {
            std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(
              v24,
              *((__int64 *)&v24 + 1));
            std::_Deallocate<16>((void *)v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
          }
          started = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11C,
            (unsigned int)".\\sessionhost.cpp",
            (const char *)(unsigned int)v12,
            v13);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&p_string);
          if ( (_QWORD)v24 )
          {
            std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(
              v24,
              *((__int64 *)&v24 + 1));
            std::_Deallocate<16>((void *)v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
            v25 = 0;
            v24 = 0;
          }
        }
        goto LABEL_27;
      }
      v9 = (unsigned int)v11;
      v10 = 263;
    }
    else
    {
      v9 = (unsigned int)started;
      v10 = 260;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, (unsigned int)".\\sessionhost.cpp", (const char *)v9, v13);
LABEL_27:
    WindowsDeleteString(string);
    return (unsigned int)started;
  }
  v2 = 236;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)".\\sessionhost.cpp",
    (const char *)0x8007139FLL,
    v13);
  if ( this != (SharingPlatform::SessionHost *)-64LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return 2147947423LL;
}

```

## disassembly

```asm
0x18005bdd0  push    rbp
0x18005bdd2  push    rbx
0x18005bdd3  push    rsi
0x18005bdd4  push    rdi
0x18005bdd5  lea     rbp, [rsp-3Fh]
0x18005bdda  sub     rsp, 0B8h
0x18005bde1  mov     rax, cs:__security_cookie
0x18005bde8  xor     rax, rsp
0x18005bdeb  mov     [rbp+57h+var_30], rax
0x18005bdef  movzx   eax, byte ptr [rcx+7Fh]
0x18005bdf3  lea     r9, [rcx+76h]
0x18005bdf7  mov     word ptr [rbp+57h+var_70], ax
0x18005bdfb  lea     r8, [rcx+74h]
0x18005bdff  movzx   eax, byte ptr [rcx+7Eh]
0x18005be03  lea     rdx, [rcx+70h]
0x18005be07  mov     word ptr [rbp+57h+var_70+2], ax
0x18005be0b  mov     rsi, rcx
0x18005be0e  movzx   eax, byte ptr [rcx+7Dh]
0x18005be12  mov     word ptr [rbp+57h+var_70+4], ax
0x18005be16  movzx   eax, byte ptr [rcx+7Ch]
0x18005be1a  mov     word ptr [rbp+57h+var_70+6], ax
0x18005be1e  movzx   eax, byte ptr [rcx+7Bh]
0x18005be22  mov     word ptr [rbp+57h+var_68], ax
0x18005be26  movzx   eax, byte ptr [rcx+7Ah]
0x18005be2a  mov     word ptr [rbp+57h+var_68+2], ax
0x18005be2e  movzx   eax, byte ptr [rcx+79h]
0x18005be32  mov     word ptr [rbp+57h+var_68+4], ax
0x18005be36  movzx   eax, byte ptr [rcx+78h]
0x18005be3a  lea     rcx, aSessionhostCon; "SessionHost::Connect sessionGUID={%08lX"...
0x18005be41  mov     word ptr [rbp+57h+var_68+6], ax
0x18005be45  lea     rax, [rbp+57h+var_70]
0x18005be49  mov     [rsp+0D0h+var_78], rax; __int64
0x18005be4e  lea     rax, [rbp+57h+var_70+2]
0x18005be52  mov     [rsp+0D0h+var_80], rax; __int64
0x18005be57  lea     rax, [rbp+57h+var_70+4]
0x18005be5b  mov     [rsp+0D0h+var_88], rax; __int64
0x18005be60  lea     rax, [rbp+57h+var_70+6]
0x18005be64  mov     [rsp+0D0h+var_90], rax; __int64
0x18005be69  lea     rax, [rbp+57h+var_68]
0x18005be6d  mov     [rsp+0D0h+var_98], rax; __int64
0x18005be72  lea     rax, [rbp+57h+var_68+2]
0x18005be76  mov     [rsp+0D0h+var_A0], rax; __int64
0x18005be7b  lea     rax, [rbp+57h+var_68+4]
0x18005be7f  mov     [rsp+0D0h+var_A8], rax; __int64
0x18005be84  lea     rax, [rbp+57h+var_68+6]
0x18005be88  mov     [rsp+0D0h+var_B0], rax; int
0x18005be8d  call    ??$LogInfo@AEAY0HA@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0HA@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[112],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[112],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x18005be92  lea     rdi, [rsi+40h]
0x18005be96  mov     rcx, rdi; lpCriticalSection
0x18005be99  call    cs:__imp_EnterCriticalSection
0x18005be9f  cmp     byte ptr [rsi+90h], 0
0x18005bea6  jz      short loc_18005BEAF
0x18005bea8  mov     edx, 0ECh
0x18005bead  jmp     short loc_18005BECD
0x18005beaf  cmp     byte ptr [rsi+91h], 0
0x18005beb6  jz      short loc_18005BEBF
0x18005beb8  mov     edx, 0EDh
0x18005bebd  jmp     short loc_18005BECD
0x18005bebf  cmp     byte ptr [rsi+92h], 0
0x18005bec6  jz      short loc_18005BEFB
0x18005bec8  mov     edx, 0EEh; void *
0x18005becd  mov     rcx, [rbp+5Fh]; this
0x18005bed1  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005bed8  mov     r9d, 8007139Fh; char *
0x18005bede  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bee3  test    rdi, rdi
0x18005bee6  jz      short loc_18005BEF1
0x18005bee8  mov     rcx, rdi; lpCriticalSection
0x18005beeb  call    cs:__imp_LeaveCriticalSection
0x18005bef1  mov     eax, 8007139Fh
0x18005bef6  jmp     loc_18005C0B7
0x18005befb  mov     byte ptr [rsi+91h], 1
0x18005bf02  test    rdi, rdi
0x18005bf05  jz      short loc_18005BF10
0x18005bf07  mov     rcx, rdi; lpCriticalSection
0x18005bf0a  call    cs:__imp_LeaveCriticalSection
0x18005bf10  lea     rax, [rbp+57h+string]
0x18005bf14  mov     [rbp+57h+string], rsi
0x18005bf18  lea     rcx, [rbp+57h+var_60]
0x18005bf1c  mov     [rbp+57h+var_60], rax
0x18005bf20  call    ScopeWarden__lambda_a4d2f7be06f8df519d7a2767006f083d______ScopeWarden__lambda_a4d2f7be06f8df519d7a2767006f083d___
0x18005bf25  lea     rcx, [rbp+57h+var_50]
0x18005bf29  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18005bf2e  lea     rdx, [rsi+70h]
0x18005bf32  lea     rcx, [rbp+57h+string]
0x18005bf36  mov     r8, [rax+18h]
0x18005bf3a  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x18005bf3f  mov     rcx, [rbp+57h+string]; string
0x18005bf43  xor     edx, edx; length
0x18005bf45  call    cs:__imp_WindowsGetStringRawBuffer
0x18005bf4b  mov     rdx, rax
0x18005bf4e  lea     rcx, [rbp+57h+var_50]
0x18005bf52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bf57  mov     r8, rax
0x18005bf5a  lea     r9, [rsi+0A0h]
0x18005bf61  mov     dl, 1
0x18005bf63  mov     rcx, rsi
0x18005bf66  call    ?CreateAndStartSessionStream@SessionHost@SharingPlatform@@AEAAJ_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDPBinaryHostContainer@2@@Z; SharingPlatform::SessionHost::CreateAndStartSessionStream(bool,std::wstring const &,SharingPlatform::CDPBinaryHostContainer *)
0x18005bf6b  lea     rcx, [rbp+57h+var_50]
0x18005bf6f  mov     ebx, eax
0x18005bf71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bf76  test    ebx, ebx
0x18005bf78  jns     short loc_18005BF84
0x18005bf7a  mov     r9d, ebx
0x18005bf7d  mov     edx, 104h
0x18005bf82  jmp     short loc_18005BF9A
0x18005bf84  mov     rcx, rsi; this
0x18005bf87  call    ?CreateAndStartAllSessionStreams@SessionHost@SharingPlatform@@AEAAJXZ; SharingPlatform::SessionHost::CreateAndStartAllSessionStreams(void)
0x18005bf8c  mov     ebx, eax
0x18005bf8e  test    eax, eax
0x18005bf90  jns     short loc_18005BFAF
0x18005bf92  mov     r9d, eax; char *
0x18005bf95  mov     edx, 107h; void *
0x18005bf9a  mov     rcx, [rbp+5Fh]; this
0x18005bf9e  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005bfa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bfaa  jmp     loc_18005C0AB
0x18005bfaf  mov     rcx, rdi; lpCriticalSection
0x18005bfb2  call    cs:__imp_EnterCriticalSection
0x18005bfb8  mov     word ptr [rsi+90h], 1
0x18005bfc1  test    rdi, rdi
0x18005bfc4  jz      short loc_18005BFCF
0x18005bfc6  mov     rcx, rdi; lpCriticalSection
0x18005bfc9  call    cs:__imp_LeaveCriticalSection
0x18005bfcf  xorps   xmm0, xmm0
0x18005bfd2  mov     [rbp+57h+var_40], 0
0x18005bfda  lea     rcx, [rsi+98h]; this
0x18005bfe1  mov     [rbp+57h+var_60], 0
0x18005bfe9  lea     rdx, [rbp+57h+var_60]; struct IInspectable **
0x18005bfed  movdqu  [rbp+57h+var_50], xmm0
0x18005bff2  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x18005bff7  mov     ebx, eax
0x18005bff9  test    eax, eax
0x18005bffb  jns     short loc_18005C05A
0x18005bffd  mov     rcx, [rbp+5Fh]; this
0x18005c001  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005c008  mov     r9d, eax; char *
0x18005c00b  mov     edx, 11Ch; void *
0x18005c010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c015  lea     rcx, [rbp+57h+var_60]
0x18005c019  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c01e  mov     rcx, qword ptr [rbp+57h+var_50]
0x18005c022  test    rcx, rcx
0x18005c025  jz      loc_18005C0AB
0x18005c02b  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18005c02f  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(Microsoft::WRL::ComPtr<SharingPlatform::ISession> *,Microsoft::WRL::ComPtr<SharingPlatform::ISession> * const,std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>> &)
0x18005c034  mov     rcx, qword ptr [rbp+57h+var_50]
0x18005c038  mov     rdx, [rbp+57h+var_40]
0x18005c03c  sub     rdx, rcx
0x18005c03f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005c043  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005c048  xorps   xmm0, xmm0
0x18005c04b  mov     [rbp+57h+var_40], 0
0x18005c053  movdqu  [rbp+57h+var_50], xmm0
0x18005c058  jmp     short loc_18005C0AB
0x18005c05a  mov     rcx, [rbp+57h+var_60]
0x18005c05e  test    rcx, rcx
0x18005c061  jz      short loc_18005C07A
0x18005c063  mov     rax, [rcx]
0x18005c066  lea     r8, [rbp+57h+var_50]
0x18005c06a  mov     rdx, [rsi+120h]
0x18005c071  mov     rax, [rax+70h]
0x18005c075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c07a  lea     rcx, [rbp+57h+var_60]
0x18005c07e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005c083  mov     rcx, qword ptr [rbp+57h+var_50]
0x18005c087  test    rcx, rcx
0x18005c08a  jz      short loc_18005C0A9
0x18005c08c  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18005c090  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(Microsoft::WRL::ComPtr<SharingPlatform::ISession> *,Microsoft::WRL::ComPtr<SharingPlatform::ISession> * const,std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>> &)
0x18005c095  mov     rcx, qword ptr [rbp+57h+var_50]
0x18005c099  mov     rdx, [rbp+57h+var_40]
0x18005c09d  sub     rdx, rcx
0x18005c0a0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005c0a4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005c0a9  xor     ebx, ebx
0x18005c0ab  mov     rcx, [rbp+57h+string]; string
0x18005c0af  call    cs:__imp_WindowsDeleteString
0x18005c0b5  mov     eax, ebx
0x18005c0b7  mov     rcx, [rbp+57h+var_30]
0x18005c0bb  xor     rcx, rsp; StackCookie
0x18005c0be  call    __security_check_cookie
0x18005c0c3  add     rsp, 0B8h
0x18005c0ca  pop     rdi
0x18005c0cb  pop     rsi
0x18005c0cc  pop     rbx
0x18005c0cd  pop     rbp
0x18005c0ce  retn
```
