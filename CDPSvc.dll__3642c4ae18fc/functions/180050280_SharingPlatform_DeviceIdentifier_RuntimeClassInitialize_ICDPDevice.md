# SharingPlatform::DeviceIdentifier::RuntimeClassInitialize(ICDPDevice *)

- ea: `0x180050280`
- end: `0x18005039f`
- name: `?RuntimeClassInitialize@DeviceIdentifier@SharingPlatform@@QEAAJPEAVICDPDevice@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(SharingPlatform::DeviceIdentifier *__hidden this, struct ICDPDevice *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004fff0`

## callees

- `0x180004928`
- `0x180010dfc`
- `0x1800130ec`
- `0x180048218`
- `0x180050280`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050351`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::DeviceIdentifier::RuntimeClassInitialize(HSTRING *this, struct ICDPDevice *a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // r14
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  SharingPlatform::Internal *v9; // rax
  HSTRING *v10; // r8
  SharingPlatform::Internal *v11; // rax
  HSTRING *v12; // r8
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    v4 = this + 8;
    Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>::operator=(this + 8);
    v16 = 0;
    v5 = *v4;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v4 + 32LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
    v7 = v6(v5, &v16);
    v3 = v7;
    if ( v7 >= 0 )
    {
      WindowsDeleteString(this[6]);
      this[6] = 0;
      v9 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 112LL))(*v4);
      v7 = SharingPlatform::Internal::ConvertCStringToHSTRING(v9, (const char *)this + 48, v10);
      v3 = v7;
      if ( v7 >= 0 )
      {
        WindowsDeleteString(this[7]);
        this[7] = 0;
        v11 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
        v7 = SharingPlatform::Internal::ConvertCStringToHSTRING(v11, (const char *)this + 56, v12);
        v3 = v7;
        if ( v7 >= 0 )
        {
          v3 = 0;
          goto LABEL_11;
        }
        v8 = 49;
      }
      else
      {
        v8 = 48;
      }
    }
    else
    {
      v8 = 45;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v7,
      v14);
LABEL_11:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
    return v3;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29,
    (unsigned int)".\\deviceidentifier.cpp",
    (const char *)0x80004003LL,
    v14);
  return v3;
}

```

## disassembly

```asm
0x180050280  push    rbx
0x180050282  push    rsi
0x180050283  push    rdi
0x180050284  push    r14
0x180050286  sub     rsp, 28h
0x18005028a  mov     rsi, rcx
0x18005028d  test    rdx, rdx
0x180050290  jnz     short loc_1800502B5
0x180050292  mov     rcx, [rsp+48h]; this
0x180050297  mov     ebx, 80004003h
0x18005029c  mov     r9d, ebx; char *
0x18005029f  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x1800502a6  mov     edx, 29h ; ')'; void *
0x1800502ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800502b0  jmp     loc_180050393
0x1800502b5  lea     r14, [rcx+40h]
0x1800502b9  mov     rcx, r14
0x1800502bc  call    ??4?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@QEAAAEAV012@PEAUIParticipantIdentifier@SharingPlatform@@@Z; Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>::operator=(SharingPlatform::IParticipantIdentifier *)
0x1800502c1  mov     [rsp+48h+arg_8], 0
0x1800502ca  mov     rdi, [r14]
0x1800502cd  mov     rax, [rdi]
0x1800502d0  mov     rbx, [rax+20h]
0x1800502d4  lea     rcx, [rsp+48h+arg_8]
0x1800502d9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800502de  lea     rdx, [rsp+48h+arg_8]
0x1800502e3  mov     rcx, rdi
0x1800502e6  mov     rax, rbx
0x1800502e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502ee  mov     ebx, eax
0x1800502f0  test    eax, eax
0x1800502f2  jns     short loc_1800502FB
0x1800502f4  mov     edx, 2Dh ; '-'
0x1800502f9  jmp     short loc_180050334
0x1800502fb  lea     rbx, [rsi+30h]
0x1800502ff  mov     rcx, [rbx]; string
0x180050302  call    cs:__imp_WindowsDeleteString
0x180050308  mov     qword ptr [rbx], 0
0x18005030f  mov     rcx, [r14]
0x180050312  mov     rax, [rcx]
0x180050315  mov     rax, [rax+70h]
0x180050319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005031e  mov     rdx, rbx; char *
0x180050321  mov     rcx, rax; this
0x180050324  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180050329  mov     ebx, eax
0x18005032b  test    eax, eax
0x18005032d  jns     short loc_18005034A
0x18005032f  mov     edx, 30h ; '0'; void *
0x180050334  mov     rcx, [rsp+48h]; this
0x180050339  mov     r9d, eax; char *
0x18005033c  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180050343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050348  jmp     short loc_180050389
0x18005034a  lea     rbx, [rsi+38h]
0x18005034e  mov     rcx, [rbx]; string
0x180050351  call    cs:__imp_WindowsDeleteString
0x180050357  mov     qword ptr [rbx], 0
0x18005035e  mov     rcx, [rsp+48h+arg_8]
0x180050363  mov     rax, [rcx]
0x180050366  mov     rax, [rax+20h]
0x18005036a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005036f  mov     rdx, rbx; char *
0x180050372  mov     rcx, rax; this
0x180050375  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x18005037a  mov     ebx, eax
0x18005037c  test    eax, eax
0x18005037e  jns     short loc_180050387
0x180050380  mov     edx, 31h ; '1'
0x180050385  jmp     short loc_180050334
0x180050387  xor     ebx, ebx
0x180050389  lea     rcx, [rsp+48h+arg_8]
0x18005038e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180050393  mov     eax, ebx
0x180050395  add     rsp, 28h
0x180050399  pop     r14
0x18005039b  pop     rdi
0x18005039c  pop     rsi
0x18005039d  pop     rbx
0x18005039e  retn
```
