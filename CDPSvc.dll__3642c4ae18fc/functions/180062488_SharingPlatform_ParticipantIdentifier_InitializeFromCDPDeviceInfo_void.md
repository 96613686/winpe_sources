# SharingPlatform::ParticipantIdentifier::InitializeFromCDPDeviceInfo(void)

- ea: `0x180062488`
- end: `0x1800625b3`
- name: `?InitializeFromCDPDeviceInfo@ParticipantIdentifier@SharingPlatform@@AEAAJXZ`
- size: `299`
- prototype: `__int64 __fastcall(SharingPlatform::ParticipantIdentifier *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800124c0`
- `0x1800625bc`
- `0x180062664`

## callees

- `0x180004928`
- `0x180010dfc`
- `0x1800130ec`
- `0x180055dbc`
- `0x180062488`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062578`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062578`
- `cdp!CDPCreateDeviceInternal` at `0x1800624e1`
- `cdp!CDPCreateDeviceInternal` at `0x1800624e1`

## pseudocode

```c
__int64 __fastcall SharingPlatform::ParticipantIdentifier::InitializeFromCDPDeviceInfo(
        SharingPlatform::ParticipantIdentifier *this)
{
  int DeviceIpAddress; // ebx
  __int64 v3; // rdx
  _QWORD *v5; // rsi
  SharingPlatform::Internal *v6; // rax
  HSTRING *v7; // r8
  SharingPlatform::Internal *v8; // rax
  HSTRING *v9; // r8
  HSTRING *v10; // r8
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*((_QWORD *)this + 11) )
  {
    DeviceIpAddress = -2147221245;
    v3 = 100;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)".\\participantidentifier.cpp",
      (const char *)(unsigned int)DeviceIpAddress,
      v11);
    return (unsigned int)DeviceIpAddress;
  }
  v5 = (_QWORD *)((char *)this + 80);
  if ( !*((_QWORD *)this + 10) )
  {
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 80);
    DeviceIpAddress = CDPCreateDeviceInternal(*((_QWORD *)this + 11), 0, v5);
    if ( DeviceIpAddress < 0 )
    {
      v3 = 105;
      goto LABEL_3;
    }
  }
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  v6 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 112LL))(*v5);
  DeviceIpAddress = SharingPlatform::Internal::ConvertCStringToHSTRING(v6, (const char *)this + 56, v7);
  if ( DeviceIpAddress < 0 )
  {
    v3 = 108;
    goto LABEL_3;
  }
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  v8 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  DeviceIpAddress = SharingPlatform::Internal::ConvertCStringToHSTRING(v8, (const char *)this + 64, v9);
  if ( DeviceIpAddress < 0 )
  {
    v3 = 109;
    goto LABEL_3;
  }
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  DeviceIpAddress = SharingPlatform::Internal::GetDeviceIpAddress(
                      *((SharingPlatform::Internal **)this + 11),
                      (SharingPlatform::ParticipantIdentifier *)((char *)this + 72),
                      v10);
  if ( DeviceIpAddress < 0 )
  {
    v3 = 112;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180062488  mov     [rsp+arg_0], rbx
0x18006248d  mov     [rsp+arg_8], rsi
0x180062492  push    rdi; int
0x180062493  sub     rsp, 20h
0x180062497  cmp     qword ptr [rcx+58h], 0
0x18006249c  mov     rdi, rcx
0x18006249f  jnz     short loc_1800624C6
0x1800624a1  mov     ebx, 80040103h
0x1800624a6  mov     edx, 64h ; 'd'; void *
0x1800624ab  mov     rcx, [rsp+28h]; this
0x1800624b0  lea     r8, aParticipantide; ".\\participantidentifier.cpp"
0x1800624b7  mov     r9d, ebx; char *
0x1800624ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800624bf  mov     eax, ebx
0x1800624c1  jmp     loc_1800625A3
0x1800624c6  lea     rsi, [rcx+50h]
0x1800624ca  cmp     qword ptr [rsi], 0
0x1800624ce  jnz     short loc_1800624F4
0x1800624d0  mov     rcx, rsi
0x1800624d3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800624d8  mov     rcx, [rdi+58h]
0x1800624dc  mov     r8, rsi
0x1800624df  xor     edx, edx
0x1800624e1  call    cs:__imp_CDPCreateDeviceInternal
0x1800624e7  mov     ebx, eax
0x1800624e9  test    eax, eax
0x1800624eb  jns     short loc_1800624F4
0x1800624ed  mov     edx, 69h ; 'i'
0x1800624f2  jmp     short loc_1800624AB
0x1800624f4  lea     rbx, [rdi+38h]
0x1800624f8  mov     rcx, [rbx]; string
0x1800624fb  call    cs:__imp_WindowsDeleteString
0x180062501  mov     qword ptr [rbx], 0
0x180062508  mov     rcx, [rsi]
0x18006250b  mov     rax, [rcx]
0x18006250e  mov     rax, [rax+70h]
0x180062512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062517  mov     rdx, rbx; char *
0x18006251a  mov     rcx, rax; this
0x18006251d  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180062522  mov     ebx, eax
0x180062524  test    eax, eax
0x180062526  jns     short loc_180062532
0x180062528  mov     edx, 6Ch ; 'l'
0x18006252d  jmp     loc_1800624AB
0x180062532  lea     rbx, [rdi+40h]
0x180062536  mov     rcx, [rbx]; string
0x180062539  call    cs:__imp_WindowsDeleteString
0x18006253f  mov     qword ptr [rbx], 0
0x180062546  mov     rcx, [rdi+58h]
0x18006254a  mov     rax, [rcx]
0x18006254d  mov     rax, [rax+20h]
0x180062551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062556  mov     rdx, rbx; char *
0x180062559  mov     rcx, rax; this
0x18006255c  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180062561  mov     ebx, eax
0x180062563  test    eax, eax
0x180062565  jns     short loc_180062571
0x180062567  mov     edx, 6Dh ; 'm'
0x18006256c  jmp     loc_1800624AB
0x180062571  lea     rbx, [rdi+48h]
0x180062575  mov     rcx, [rbx]; string
0x180062578  call    cs:__imp_WindowsDeleteString
0x18006257e  mov     qword ptr [rbx], 0
0x180062585  mov     rdx, rbx; struct ICDPDeviceInfo *
0x180062588  mov     rcx, [rdi+58h]; this
0x18006258c  call    ?GetDeviceIpAddress@Internal@SharingPlatform@@YAJPEAVICDPDeviceInfo@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::GetDeviceIpAddress(ICDPDeviceInfo *,HSTRING__ * *)
0x180062591  mov     ebx, eax
0x180062593  test    eax, eax
0x180062595  jns     short loc_1800625A1
0x180062597  mov     edx, 70h ; 'p'
0x18006259c  jmp     loc_1800624AB
0x1800625a1  xor     eax, eax
0x1800625a3  mov     rbx, [rsp+28h+arg_0]
0x1800625a8  mov     rsi, [rsp+28h+arg_8]
0x1800625ad  add     rsp, 20h
0x1800625b1  pop     rdi
0x1800625b2  retn
```
