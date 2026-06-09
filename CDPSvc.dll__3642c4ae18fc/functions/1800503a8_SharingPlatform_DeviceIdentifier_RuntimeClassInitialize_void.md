# SharingPlatform::DeviceIdentifier::RuntimeClassInitialize(void)

- ea: `0x1800503a8`
- end: `0x180050505`
- name: `?RuntimeClassInitialize@DeviceIdentifier@SharingPlatform@@QEAAJXZ`
- size: `349`
- prototype: `int(SharingPlatform::DeviceIdentifier *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180045e78`
- `0x1800500b0`

## callees

- `0x180004928`
- `0x180010dfc`
- `0x1800130ec`
- `0x1800503a8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005046f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800504aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005046f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800504aa`
- `cdp!CDPCreateDeviceQueryInternal` at `0x1800503d3`
- `cdp!CDPCreateDeviceQueryInternal` at `0x1800503d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SharingPlatform::DeviceIdentifier::RuntimeClassInitialize(HSTRING *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  _QWORD *v6; // rdi
  int v7; // eax
  __int64 v8; // rdx
  SharingPlatform::Internal *v9; // rax
  HSTRING *v10; // r8
  SharingPlatform::Internal *v11; // rax
  HSTRING *v12; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v16; // [rsp+48h] [rbp+28h] BYREF
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  v17 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
  LOBYTE(v2) = 1;
  v3 = CDPCreateDeviceQueryInternal(v2, 0, &v17);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 25;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    goto LABEL_14;
  }
  v6 = this + 8;
  v3 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 72LL))(v17, (char *)this + 64);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 26;
    goto LABEL_5;
  }
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v6 + 32LL))(*v6, &v16);
  v4 = v7;
  if ( v7 >= 0 )
  {
    WindowsDeleteString(this[6]);
    this[6] = 0;
    v9 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 112LL))(*v6);
    v7 = SharingPlatform::Internal::ConvertCStringToHSTRING(v9, (const char *)this + 48, v10);
    v4 = v7;
    if ( v7 >= 0 )
    {
      WindowsDeleteString(this[7]);
      this[7] = 0;
      v11 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
      v7 = SharingPlatform::Internal::ConvertCStringToHSTRING(v11, (const char *)this + 56, v12);
      v4 = v7;
      if ( v7 >= 0 )
      {
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
        v4 = 0;
        goto LABEL_14;
      }
      v8 = 33;
    }
    else
    {
      v8 = 32;
    }
  }
  else
  {
    v8 = 29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)".\\deviceidentifier.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
LABEL_14:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
  return v4;
}

```

## disassembly

```asm
0x1800503a8  mov     [rsp-18h+arg_0], rbx
0x1800503ad  push    rbp
0x1800503ae  push    rsi
0x1800503af  push    rdi; int
0x1800503b0  mov     rbp, rsp
0x1800503b3  sub     rsp, 20h
0x1800503b7  mov     rsi, rcx
0x1800503ba  mov     [rbp+arg_10], 0
0x1800503c2  lea     rcx, [rbp+arg_10]
0x1800503c6  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800503cb  lea     r8, [rbp+arg_10]
0x1800503cf  xor     edx, edx
0x1800503d1  mov     cl, 1
0x1800503d3  call    cs:__imp_CDPCreateDeviceQueryInternal
0x1800503d9  mov     ebx, eax
0x1800503db  test    eax, eax
0x1800503dd  jns     short loc_1800503E6
0x1800503df  mov     edx, 19h
0x1800503e4  jmp     short loc_180050408
0x1800503e6  mov     rcx, [rbp+arg_10]
0x1800503ea  lea     rdi, [rsi+40h]
0x1800503ee  mov     rax, [rcx]
0x1800503f1  mov     rdx, rdi
0x1800503f4  mov     rax, [rax+48h]
0x1800503f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503fd  mov     ebx, eax
0x1800503ff  test    eax, eax
0x180050401  jns     short loc_180050420
0x180050403  mov     edx, 1Ah; void *
0x180050408  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x18005040f  mov     r9d, eax; char *
0x180050412  mov     rcx, [rbp+18h]; this
0x180050416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005041b  jmp     loc_1800504ED
0x180050420  mov     [rbp+arg_8], 0
0x180050428  mov     rcx, [rdi]
0x18005042b  mov     rax, [rcx]
0x18005042e  lea     rdx, [rbp+arg_8]
0x180050432  mov     rax, [rax+20h]
0x180050436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005043b  mov     ebx, eax
0x18005043d  test    eax, eax
0x18005043f  jns     short loc_180050468
0x180050441  mov     edx, 1Dh; void *
0x180050446  mov     rcx, [rbp+18h]; this
0x18005044a  mov     r9d, eax; char *
0x18005044d  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180050454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050459  nop
0x18005045a  lea     rcx, [rbp+arg_8]
0x18005045e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180050463  jmp     loc_1800504ED
0x180050468  lea     rbx, [rsi+30h]
0x18005046c  mov     rcx, [rbx]; string
0x18005046f  call    cs:__imp_WindowsDeleteString
0x180050475  mov     qword ptr [rbx], 0
0x18005047c  mov     rcx, [rdi]
0x18005047f  mov     rax, [rcx]
0x180050482  mov     rax, [rax+70h]
0x180050486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005048b  mov     rdx, rbx; char *
0x18005048e  mov     rcx, rax; this
0x180050491  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180050496  mov     ebx, eax
0x180050498  test    eax, eax
0x18005049a  jns     short loc_1800504A3
0x18005049c  mov     edx, 20h ; ' '
0x1800504a1  jmp     short loc_180050446
0x1800504a3  lea     rbx, [rsi+38h]
0x1800504a7  mov     rcx, [rbx]; string
0x1800504aa  call    cs:__imp_WindowsDeleteString
0x1800504b0  mov     qword ptr [rbx], 0
0x1800504b7  mov     rcx, [rbp+arg_8]
0x1800504bb  mov     rax, [rcx]
0x1800504be  mov     rax, [rax+20h]
0x1800504c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504c7  mov     rdx, rbx; char *
0x1800504ca  mov     rcx, rax; this
0x1800504cd  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x1800504d2  mov     ebx, eax
0x1800504d4  test    eax, eax
0x1800504d6  jns     short loc_1800504E2
0x1800504d8  mov     edx, 21h ; '!'
0x1800504dd  jmp     loc_180050446
0x1800504e2  lea     rcx, [rbp+arg_8]
0x1800504e6  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800504eb  xor     ebx, ebx
0x1800504ed  lea     rcx, [rbp+arg_10]
0x1800504f1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800504f6  mov     eax, ebx
0x1800504f8  mov     rbx, [rsp+20h+arg_0]
0x1800504fd  add     rsp, 20h
0x180050501  pop     rdi
0x180050502  pop     rsi
0x180050503  pop     rbp
0x180050504  retn
```
