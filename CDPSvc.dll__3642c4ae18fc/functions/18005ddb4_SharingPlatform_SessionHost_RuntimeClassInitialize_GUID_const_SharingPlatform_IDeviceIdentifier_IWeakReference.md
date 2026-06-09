# SharingPlatform::SessionHost::RuntimeClassInitialize(_GUID const &,SharingPlatform::IDeviceIdentifier *,IWeakReference *)

- ea: `0x18005ddb4`
- end: `0x18005e093`
- name: `?RuntimeClassInitialize@SessionHost@SharingPlatform@@QEAAJAEBU_GUID@@PEAUIDeviceIdentifier@2@PEAUIWeakReference@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(SharingPlatform::SessionHost *__hidden this, const struct _GUID *, struct SharingPlatform::IDeviceIdentifier *, struct IWeakReference *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180046724`

## callees

- `0x180004928`
- `0x180010d04`
- `0x1800130ec`
- `0x18001620c`
- `0x1800225a0`
- `0x18003f9c8`
- `0x1800506bc`
- `0x180057220`
- `0x18005a138`
- `0x18005af4c`
- `0x18005ddb4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005df66`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005df66`

## string_xrefs

- `0x18005decf`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::SessionHost::RuntimeClassInitialize(
        GUID *this,
        const struct _GUID *a2,
        struct SharingPlatform::IDeviceIdentifier *a3,
        struct IWeakReference *a4)
{
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  HRESULT Guid; // eax
  int v14; // eax
  __int64 v15; // rdx
  struct IWeakReference *v16; // rdi
  ULONG (__stdcall *Release)(IWeakReference *); // rbx
  int v19; // [rsp+20h] [rbp-89h]
  struct IWeakReference *v20; // [rsp+60h] [rbp-49h] BYREF
  __int16 v21; // [rsp+68h] [rbp-41h] BYREF
  __int16 v22; // [rsp+6Ah] [rbp-3Fh] BYREF
  __int16 v23; // [rsp+6Ch] [rbp-3Dh] BYREF
  __int16 v24; // [rsp+6Eh] [rbp-3Bh] BYREF
  __int16 v25; // [rsp+70h] [rbp-39h] BYREF
  __int16 v26; // [rsp+72h] [rbp-37h] BYREF
  __int16 v27; // [rsp+74h] [rbp-35h] BYREF
  _WORD v28[5]; // [rsp+76h] [rbp-33h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp-29h] BYREF
  struct IInspectable *v30; // [rsp+88h] [rbp-21h] BYREF
  __int64 v31; // [rsp+90h] [rbp-19h] BYREF
  GUID *v32; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  this[7] = *a2;
  LOWORD(this[9].Data1) = 0;
  BYTE2(this[9].Data1) = 0;
  v20 = a4;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v20);
  v7 = *(_QWORD *)this[9].Data4;
  *(_QWORD *)this[9].Data4 = a4;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v21 = this[7].Data4[7];
  v22 = this[7].Data4[6];
  v23 = this[7].Data4[5];
  v24 = this[7].Data4[4];
  v25 = this[7].Data4[3];
  v26 = this[7].Data4[2];
  v27 = this[7].Data4[1];
  v28[0] = this[7].Data4[0];
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[110],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    v7,
    (_DWORD)this + 112,
    (_DWORD)this + 116,
    (_DWORD)this + 118,
    (__int64)v28,
    (__int64)&v27,
    (__int64)&v26,
    (__int64)&v25,
    (__int64)&v24,
    (__int64)&v23,
    (__int64)&v22,
    (__int64)&v21);
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Storage.Streams.DataReader",
    0x23u,
    0x22u);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>(
         v34,
         (__int64)this[6].Data4);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v30 = 0;
    v10 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
            (Microsoft::WRL::WeakRef *)this[9].Data4,
            &v30);
    v9 = v10;
    if ( v10 >= 0 )
    {
      if ( v30 )
      {
        Guid = CoCreateGuid(this + 8);
        v9 = Guid;
        if ( Guid >= 0 )
        {
          *(_QWORD *)&v28[1] = 0;
          v20 = 0;
          v29 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v29);
          v14 = Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifier>::As<SharingPlatform::IDeviceIdentifierInternal>(
                  &v29,
                  (__int64)&v20);
          v9 = v14;
          if ( v14 >= 0 )
          {
            v16 = v20;
            Release = v20->lpVtbl[1].Release;
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28[1]);
            v14 = ((__int64 (__fastcall *)(struct IWeakReference *, _WORD *))Release)(v16, &v28[1]);
            v9 = v14;
            if ( v14 >= 0 )
            {
              v31 = *(_QWORD *)&v28[1];
              v32 = this + 8;
              Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&this[18]);
              v14 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::ParticipantIdentifier,SharingPlatform::IParticipantIdentifier,_GUID *,ICDPDevice *>(
                      &this[18],
                      &v32,
                      &v31);
              v9 = v14;
              if ( v14 >= 0 )
              {
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28[1]);
                v9 = 0;
                goto LABEL_20;
              }
              v15 = 66;
            }
            else
            {
              v15 = 64;
            }
          }
          else
          {
            v15 = 63;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)".\\sessionhost.cpp",
            (const char *)(unsigned int)v14,
            v19);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28[1]);
LABEL_20:
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
          return v9;
        }
        v11 = (unsigned int)Guid;
        v12 = 58;
      }
      else
      {
        v9 = -2147024809;
        v11 = 2147942487LL;
        v12 = 54;
      }
    }
    else
    {
      v11 = (unsigned int)v10;
      v12 = 53;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)".\\sessionhost.cpp", (const char *)v11, v19);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)".\\sessionhost.cpp",
    (const char *)(unsigned int)v8,
    v19);
  return v9;
}

```

## disassembly

```asm
0x18005ddb4  push    rbp
0x18005ddb6  push    rbx
0x18005ddb7  push    rsi
0x18005ddb8  push    rdi
0x18005ddb9  push    r14
0x18005ddbb  push    r15
0x18005ddbd  lea     rbp, [rsp-2Fh]
0x18005ddc2  sub     rsp, 0D8h
0x18005ddc9  mov     rax, cs:__security_cookie
0x18005ddd0  xor     rax, rsp
0x18005ddd3  mov     [rbp+57h+var_40], rax
0x18005ddd7  mov     rbx, r9
0x18005ddda  mov     r15, r8
0x18005dddd  mov     rsi, rcx
0x18005dde0  movups  xmm0, xmmword ptr [rdx]
0x18005dde3  movdqu  xmmword ptr [rcx+70h], xmm0
0x18005dde8  mov     word ptr [rcx+90h], 0
0x18005ddf1  mov     byte ptr [rcx+92h], 0
0x18005ddf8  mov     [rbp+57h+var_A0], rbx
0x18005ddfc  lea     rcx, [rbp+57h+var_A0]
0x18005de00  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18005de05  lea     rdi, [rsi+98h]
0x18005de0c  mov     rcx, [rdi]
0x18005de0f  mov     [rdi], rbx
0x18005de12  test    rcx, rcx
0x18005de15  jz      short loc_18005DE24
0x18005de17  mov     rax, [rcx]
0x18005de1a  mov     rax, [rax+10h]
0x18005de1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de23  nop
0x18005de24  movzx   eax, byte ptr [rsi+7Fh]
0x18005de28  mov     [rbp+57h+var_98], ax
0x18005de2c  movzx   eax, byte ptr [rsi+7Eh]
0x18005de30  mov     [rbp+57h+var_96], ax
0x18005de34  movzx   eax, byte ptr [rsi+7Dh]
0x18005de38  mov     [rbp+57h+var_94], ax
0x18005de3c  movzx   eax, byte ptr [rsi+7Ch]
0x18005de40  mov     [rbp+57h+var_92], ax
0x18005de44  movzx   eax, byte ptr [rsi+7Bh]
0x18005de48  mov     [rbp+57h+var_90], ax
0x18005de4c  movzx   eax, byte ptr [rsi+7Ah]
0x18005de50  mov     [rbp+57h+var_8E], ax
0x18005de54  movzx   eax, byte ptr [rsi+79h]
0x18005de58  mov     [rbp+57h+var_8C], ax
0x18005de5c  movzx   eax, byte ptr [rsi+78h]
0x18005de60  mov     word ptr [rbp+57h+var_8A], ax
0x18005de64  lea     r9, [rsi+76h]
0x18005de68  lea     r8, [rsi+74h]
0x18005de6c  lea     rax, [rbp+57h+var_98]
0x18005de70  mov     [rsp+100h+var_A8], rax
0x18005de75  lea     rax, [rbp+57h+var_96]
0x18005de79  mov     [rsp+100h+var_B0], rax
0x18005de7e  lea     rax, [rbp+57h+var_94]
0x18005de82  mov     [rsp+100h+var_B8], rax
0x18005de87  lea     rax, [rbp+57h+var_92]
0x18005de8b  mov     [rsp+100h+var_C0], rax
0x18005de90  lea     rax, [rbp+57h+var_90]
0x18005de94  mov     [rsp+100h+var_C8], rax
0x18005de99  lea     rax, [rbp+57h+var_8E]
0x18005de9d  mov     [rsp+100h+var_D0], rax
0x18005dea2  lea     rax, [rbp+57h+var_8C]
0x18005dea6  mov     [rsp+100h+var_D8], rax
0x18005deab  lea     rax, [rbp+57h+var_8A]
0x18005deaf  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18005deb4  lea     rdx, [rsi+70h]
0x18005deb8  call    ??$LogInfo@AEAY0GO@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0GO@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[110],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[110],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x18005debd  mov     [rbp+57h+var_48], 0
0x18005dec5  mov     r9d, 22h ; '"'; unsigned int
0x18005decb  lea     r8d, [r9+1]; unsigned int
0x18005decf  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataReader@@3QBGB; "Windows.Storage.Streams.DataReader"
0x18005ded6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005deda  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005dedf  lea     rdx, [rsi+68h]
0x18005dee3  mov     rcx, [rbp+57h+var_48]
0x18005dee7  call    ??$GetActivationFactory@V?$ComPtr@UIDataReaderStatics@Streams@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDataReaderStatics@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>)
0x18005deec  mov     ebx, eax
0x18005deee  test    eax, eax
0x18005def0  jns     short loc_18005DF0F
0x18005def2  mov     rcx, [rbp+5Fh]; this
0x18005def6  mov     r9d, eax; char *
0x18005def9  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005df00  mov     edx, 31h ; '1'; void *
0x18005df05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df0a  jmp     loc_18005E075
0x18005df0f  mov     [rbp+57h+var_78], 0
0x18005df17  lea     rdx, [rbp+57h+var_78]; struct IInspectable **
0x18005df1b  mov     rcx, rdi; this
0x18005df1e  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x18005df23  mov     ebx, eax
0x18005df25  test    eax, eax
0x18005df27  jns     short loc_18005DF33
0x18005df29  mov     r9d, eax
0x18005df2c  mov     edx, 35h ; '5'
0x18005df31  jmp     short loc_18005DF47
0x18005df33  cmp     [rbp+57h+var_78], 0
0x18005df38  jnz     short loc_18005DF5C
0x18005df3a  mov     ebx, 80070057h
0x18005df3f  mov     r9d, ebx; char *
0x18005df42  mov     edx, 36h ; '6'; void *
0x18005df47  mov     rcx, [rbp+5Fh]; this
0x18005df4b  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005df52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df57  jmp     loc_18005E06C
0x18005df5c  lea     r14, [rsi+80h]
0x18005df63  mov     rcx, r14; pguid
0x18005df66  call    cs:__imp_CoCreateGuid
0x18005df6c  mov     ebx, eax
0x18005df6e  test    eax, eax
0x18005df70  jns     short loc_18005DF7C
0x18005df72  mov     r9d, eax
0x18005df75  mov     edx, 3Ah ; ':'
0x18005df7a  jmp     short loc_18005DF47
0x18005df7c  mov     qword ptr [rbp+57h+var_8A+2], 0
0x18005df84  mov     [rbp+57h+var_A0], 0
0x18005df8c  mov     [rbp+57h+var_80], r15
0x18005df90  lea     rcx, [rbp+57h+var_80]
0x18005df94  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x18005df99  lea     rdx, [rbp+57h+var_A0]
0x18005df9d  lea     rcx, [rbp+57h+var_80]
0x18005dfa1  call    ??$As@UIDeviceIdentifierInternal@SharingPlatform@@@?$ComPtr@UIDeviceIdentifier@SharingPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDeviceIdentifierInternal@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifier>::As<SharingPlatform::IDeviceIdentifierInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::IDeviceIdentifierInternal>>)
0x18005dfa6  mov     ebx, eax
0x18005dfa8  test    eax, eax
0x18005dfaa  jns     short loc_18005DFE4
0x18005dfac  mov     edx, 3Fh ; '?'; void *
0x18005dfb1  mov     rcx, [rbp+5Fh]; this
0x18005dfb5  mov     r9d, eax; char *
0x18005dfb8  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005dfbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dfc4  lea     rcx, [rbp+57h+var_80]
0x18005dfc8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005dfcd  lea     rcx, [rbp+57h+var_A0]
0x18005dfd1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005dfd6  lea     rcx, [rbp+57h+var_8A+2]
0x18005dfda  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005dfdf  jmp     loc_18005E06C
0x18005dfe4  mov     rdi, [rbp+57h+var_A0]
0x18005dfe8  mov     rax, [rdi]
0x18005dfeb  mov     rbx, [rax+30h]
0x18005dfef  lea     rcx, [rbp+57h+var_8A+2]
0x18005dff3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005dff8  lea     rdx, [rbp+57h+var_8A+2]
0x18005dffc  mov     rcx, rdi
0x18005dfff  mov     rax, rbx
0x18005e002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e007  mov     ebx, eax
0x18005e009  test    eax, eax
0x18005e00b  jns     short loc_18005E014
0x18005e00d  mov     edx, 40h ; '@'
0x18005e012  jmp     short loc_18005DFB1
0x18005e014  mov     rax, qword ptr [rbp+57h+var_8A+2]
0x18005e018  mov     [rbp+57h+var_70], rax
0x18005e01c  mov     [rbp+57h+var_68], r14
0x18005e020  lea     rbx, [rsi+120h]
0x18005e027  mov     rcx, rbx
0x18005e02a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005e02f  lea     r8, [rbp+57h+var_70]
0x18005e033  lea     rdx, [rbp+57h+var_68]
0x18005e037  mov     rcx, rbx
0x18005e03a  call    ??$MakeAndInitialize@VParticipantIdentifier@SharingPlatform@@UIParticipantIdentifier@2@PEAU_GUID@@PEAVICDPDevice@@@Details@WRL@Microsoft@@YAJPEAPEAUIParticipantIdentifier@SharingPlatform@@$$QEAPEAU_GUID@@$$QEAPEAVICDPDevice@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::ParticipantIdentifier,SharingPlatform::IParticipantIdentifier,_GUID *,ICDPDevice *>(SharingPlatform::IParticipantIdentifier * *,_GUID * &&,ICDPDevice * &&)
0x18005e03f  mov     ebx, eax
0x18005e041  test    eax, eax
0x18005e043  jns     short loc_18005E04F
0x18005e045  mov     edx, 42h ; 'B'
0x18005e04a  jmp     loc_18005DFB1
0x18005e04f  lea     rcx, [rbp+57h+var_80]
0x18005e053  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005e058  lea     rcx, [rbp+57h+var_A0]
0x18005e05c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005e061  lea     rcx, [rbp+57h+var_8A+2]
0x18005e065  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005e06a  xor     ebx, ebx
0x18005e06c  lea     rcx, [rbp+57h+var_78]
0x18005e070  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005e075  mov     eax, ebx
0x18005e077  mov     rcx, [rbp+57h+var_40]
0x18005e07b  xor     rcx, rsp; StackCookie
0x18005e07e  call    __security_check_cookie
0x18005e083  add     rsp, 0D8h
0x18005e08a  pop     r15
0x18005e08c  pop     r14
0x18005e08e  pop     rdi
0x18005e08f  pop     rsi
0x18005e090  pop     rbx
0x18005e091  pop     rbp
0x18005e092  retn
```
