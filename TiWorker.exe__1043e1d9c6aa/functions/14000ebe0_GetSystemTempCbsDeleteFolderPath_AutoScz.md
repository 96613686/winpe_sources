# GetSystemTempCbsDeleteFolderPath(AutoScz &)

- ea: `0x14000ebe0`
- end: `0x14000ecee`
- name: `?GetSystemTempCbsDeleteFolderPath@@YAJAEAVAutoScz@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(struct AutoScz *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000e550`
- `0x14000ed6c`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000ebe0`
- `0x140017464`
- `0x140026dc4`

## string_xrefs

- `0x14000ec30`: `Failed to obtain the Temp path`
- `0x14000ec75`: `CbsTemp._ForDelete`

## pseudocode

```c
__int64 __fastcall GetSystemTempCbsDeleteFolderPath(struct AutoScz *a1)
{
  int TemporaryPath; // eax
  unsigned int v3; // ebx
  int v4; // edx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-258h]
  __int64 v11; // [rsp+30h] [rbp-248h] BYREF
  int *v12; // [rsp+38h] [rbp-240h] BYREF
  int v13; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v14[528]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v11 = 0;
  TemporaryPath = GetTemporaryPath(a1, v14);
  v3 = TemporaryPath;
  if ( TemporaryPath >= 0 )
  {
    v7 = SczAllocConcat2Sz(&v11, v14, L"CbsTemp._ForDelete");
    v3 = v7;
    if ( v7 >= 0 )
    {
      v8 = *(_QWORD *)a1;
      v3 = 0;
      *(_QWORD *)a1 = v11;
      v11 = v8;
      goto LABEL_9;
    }
    v5 = (unsigned int)v7;
    v6 = 477;
  }
  else
  {
    v13 = TemporaryPath;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to obtain the Temp path");
      v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v12);
    }
    v5 = v3;
    v6 = 475;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)v5,
    v10);
LABEL_9:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v11);
  return v3;
}

```

## disassembly

```asm
0x14000ebe0  mov     [rsp+arg_8], rbx
0x14000ebe5  push    rdi
0x14000ebe6  sub     rsp, 270h
0x14000ebed  mov     rax, cs:__security_cookie
0x14000ebf4  xor     rax, rsp
0x14000ebf7  mov     [rsp+278h+var_18], rax
0x14000ebff  lea     rdx, [rsp+278h+var_228]
0x14000ec04  mov     [rsp+278h+var_248], 0
0x14000ec0d  mov     rdi, rcx
0x14000ec10  call    GetTemporaryPath
0x14000ec15  mov     ebx, eax
0x14000ec17  test    eax, eax
0x14000ec19  jns     short loc_14000EC75
0x14000ec1b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ec22  mov     [rsp+278h+var_238], eax
0x14000ec26  test    rcx, rcx
0x14000ec29  jz      short loc_14000EC6B
0x14000ec2b  mov     edi, 3
0x14000ec30  lea     r9, aFailedToObtain; "Failed to obtain the Temp path"
0x14000ec37  mov     r8d, edi
0x14000ec3a  xor     edx, edx
0x14000ec3c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000ec41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ec48  lea     rax, [rsp+278h+var_238]
0x14000ec4d  mov     [rsp+278h+var_240], rax
0x14000ec52  lea     r9, asc_140030534; ": {}"
0x14000ec59  lea     rax, [rsp+278h+var_240]
0x14000ec5e  mov     r8d, edi
0x14000ec61  mov     qword ptr [rsp+278h+var_258], rax
0x14000ec66  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ec6b  mov     r9d, ebx
0x14000ec6e  mov     edx, 1DBh
0x14000ec73  jmp     short loc_14000EC99
0x14000ec75  lea     r8, aCbstempFordele; "CbsTemp._ForDelete"
0x14000ec7c  lea     rdx, [rsp+278h+var_228]
0x14000ec81  lea     rcx, [rsp+278h+var_248]
0x14000ec86  call    SczAllocConcat2Sz
0x14000ec8b  mov     ebx, eax
0x14000ec8d  test    eax, eax
0x14000ec8f  jns     short loc_14000ECAF
0x14000ec91  mov     r9d, eax; char *
0x14000ec94  mov     edx, 1DDh; void *
0x14000ec99  mov     rcx, [rsp+278h]; this
0x14000eca1  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000eca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ecad  jmp     short loc_14000ECC1
0x14000ecaf  mov     rcx, [rdi]
0x14000ecb2  xor     ebx, ebx
0x14000ecb4  mov     rax, [rsp+278h+var_248]
0x14000ecb9  mov     [rdi], rax
0x14000ecbc  mov     [rsp+278h+var_248], rcx
0x14000ecc1  lea     rcx, [rsp+278h+var_248]
0x14000ecc6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000eccb  mov     eax, ebx
0x14000eccd  mov     rcx, [rsp+278h+var_18]
0x14000ecd5  xor     rcx, rsp; StackCookie
0x14000ecd8  call    __security_check_cookie
0x14000ecdd  mov     rbx, [rsp+278h+arg_8]
0x14000ece5  add     rsp, 270h
0x14000ecec  pop     rdi
0x14000eced  retn
```
