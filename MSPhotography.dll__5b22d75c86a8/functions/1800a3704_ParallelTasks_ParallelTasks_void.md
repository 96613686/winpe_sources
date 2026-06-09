# ParallelTasks::ParallelTasks(void)

- ea: `0x1800a3704`
- end: `0x1800a37bf`
- name: `??0ParallelTasks@@QEAA@XZ`
- size: `187`
- prototype: `ParallelTasks *__fastcall(ParallelTasks *__hidden this)`
- caller_count: `42`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031bd0`
- `0x180031e18`
- `0x180032060`
- `0x1800322a8`
- `0x1800324f0`
- `0x180032738`
- `0x180032f34`
- `0x180077a44`
- `0x180077b20`
- `0x180080dd8`
- `0x180080f88`
- `0x18008113c`
- `0x180081bf8`
- `0x180082544`
- `0x1800826cc`
- `0x180084d3c`
- `0x1800857e4`
- `0x180089090`
- `0x18008ae34`
- `0x18008af20`
- `0x18008b00c`
- `0x18008b0f8`
- `0x18008b990`
- `0x18008ba44`
- `0x18008bd0c`
- `0x18008bec0`
- `0x18008c074`
- `0x18008c228`
- `0x18008c470`
- `0x18008c6b8`
- `0x18008c900`
- `0x18008da4c`
- `0x18008db20`
- `0x18008dbf4`
- `0x18008dcc8`
- `0x18008dd9c`
- `0x18008de70`
- `0x18008df44`
- `0x18008e018`
- `0x180090e9c`
- `0x18013b658`
- `0x18013b6fc`

## callees

- `0x180002420`
- `0x180003094`
- `0x180005660`
- `0x18001171c`
- `0x180032d30`
- `0x1800a3704`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3779`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3779`

## string_xrefs

- `0x1800a374e`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ParallelTasks *__fastcall ParallelTasks::ParallelTasks(ParallelTasks *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  ParallelTasks *v7; // [rsp+28h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h]

  v7 = this;
  std::vector<std::shared_ptr<PImage<unsigned char,1>>>::vector<std::shared_ptr<PImage<unsigned char,1>>>();
  v3 = v2 + 24;
  *(_QWORD *)(v2 + 24) = 0;
  v9 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Threading.ThreadPool",
    0x24u,
    0x23u);
  v4 = v9;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
  if ( (int)RoGetActivationFactory(v4, &GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91, v3) < 0 )
  {
    pExceptionObject = 4;
    throw (ErrorCode *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800a3704  mov     [rsp+arg_8], rbx
0x1800a3709  mov     [rsp+arg_10], rsi
0x1800a370e  push    rdi
0x1800a370f  sub     rsp, 60h
0x1800a3713  mov     rax, cs:__security_cookie
0x1800a371a  xor     rax, rsp
0x1800a371d  mov     [rsp+68h+var_18], rax
0x1800a3722  mov     rsi, rcx
0x1800a3725  mov     [rsp+68h+var_40], rcx
0x1800a372a  call    ??0?$vector@V?$shared_ptr@V?$PImage@E$00@@@std@@V?$allocator@V?$shared_ptr@V?$PImage@E$00@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PImage<uchar,1>>>::vector<std::shared_ptr<PImage<uchar,1>>>(void)
0x1800a372f  nop
0x1800a3730  lea     rdi, [rcx+18h]
0x1800a3734  mov     qword ptr [rdi], 0
0x1800a373b  mov     [rsp+68h+var_20], 0
0x1800a3744  mov     r9d, 23h ; '#'; unsigned int
0x1800a374a  lea     r8d, [r9+1]; unsigned int
0x1800a374e  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x1800a3755  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800a375a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a375f  mov     rbx, [rsp+68h+var_20]
0x1800a3764  mov     rcx, rdi
0x1800a3767  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a376c  mov     r8, rdi
0x1800a376f  lea     rdx, _GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91
0x1800a3776  mov     rcx, rbx
0x1800a3779  call    cs:__imp_RoGetActivationFactory
0x1800a377f  test    eax, eax
0x1800a3781  jns     short loc_1800A379D
0x1800a3783  mov     [rsp+68h+pExceptionObject], 4
0x1800a378b  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a3792  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800a3797  call    _CxxThrowException_0
0x1800a379d  mov     rax, rsi
0x1800a37a0  mov     rcx, [rsp+68h+var_18]
0x1800a37a5  xor     rcx, rsp; StackCookie
0x1800a37a8  call    __security_check_cookie
0x1800a37ad  lea     r11, [rsp+68h+var_8]
0x1800a37b2  mov     rbx, [r11+18h]
0x1800a37b6  mov     rsi, [r11+20h]
0x1800a37ba  mov     rsp, r11
0x1800a37bd  pop     rdi
0x1800a37be  retn
```
