# GetSystemTempCbsDeleteFolderPath(AutoScz &)

- ea: `0x140017d40`
- end: `0x140017e4e`
- name: `?GetSystemTempCbsDeleteFolderPath@@YAJAEAVAutoScz@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(struct AutoScz *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140017ecc`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x140017d40`
- `0x14001c9a0`
- `0x140026b00`

## string_xrefs

- `0x140017d90`: `Failed to obtain the Temp path`
- `0x140017dd5`: `CbsTemp._ForDelete`

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
0x140017d40  mov     [rsp+arg_8], rbx
0x140017d45  push    rdi
0x140017d46  sub     rsp, 270h
0x140017d4d  mov     rax, cs:__security_cookie
0x140017d54  xor     rax, rsp
0x140017d57  mov     [rsp+278h+var_18], rax
0x140017d5f  lea     rdx, [rsp+278h+var_228]
0x140017d64  mov     [rsp+278h+var_248], 0
0x140017d6d  mov     rdi, rcx
0x140017d70  call    GetTemporaryPath
0x140017d75  mov     ebx, eax
0x140017d77  test    eax, eax
0x140017d79  jns     short loc_140017DD5
0x140017d7b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017d82  mov     [rsp+278h+var_238], eax
0x140017d86  test    rcx, rcx
0x140017d89  jz      short loc_140017DCB
0x140017d8b  mov     edi, 3
0x140017d90  lea     r9, aFailedToObtain; "Failed to obtain the Temp path"
0x140017d97  mov     r8d, edi
0x140017d9a  xor     edx, edx
0x140017d9c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017da1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017da8  lea     rax, [rsp+278h+var_238]
0x140017dad  mov     [rsp+278h+var_240], rax
0x140017db2  lea     r9, asc_1400353E8; ": {}"
0x140017db9  lea     rax, [rsp+278h+var_240]
0x140017dbe  mov     r8d, edi
0x140017dc1  mov     qword ptr [rsp+278h+var_258], rax
0x140017dc6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017dcb  mov     r9d, ebx
0x140017dce  mov     edx, 1DBh
0x140017dd3  jmp     short loc_140017DF9
0x140017dd5  lea     r8, aCbstempFordele; "CbsTemp._ForDelete"
0x140017ddc  lea     rdx, [rsp+278h+var_228]
0x140017de1  lea     rcx, [rsp+278h+var_248]
0x140017de6  call    SczAllocConcat2Sz
0x140017deb  mov     ebx, eax
0x140017ded  test    eax, eax
0x140017def  jns     short loc_140017E0F
0x140017df1  mov     r9d, eax; char *
0x140017df4  mov     edx, 1DDh; void *
0x140017df9  mov     rcx, [rsp+278h]; this
0x140017e01  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017e0d  jmp     short loc_140017E21
0x140017e0f  mov     rcx, [rdi]
0x140017e12  xor     ebx, ebx
0x140017e14  mov     rax, [rsp+278h+var_248]
0x140017e19  mov     [rdi], rax
0x140017e1c  mov     [rsp+278h+var_248], rcx
0x140017e21  lea     rcx, [rsp+278h+var_248]
0x140017e26  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017e2b  mov     eax, ebx
0x140017e2d  mov     rcx, [rsp+278h+var_18]
0x140017e35  xor     rcx, rsp; StackCookie
0x140017e38  call    __security_check_cookie
0x140017e3d  mov     rbx, [rsp+278h+arg_8]
0x140017e45  add     rsp, 270h
0x140017e4c  pop     rdi
0x140017e4d  retn
```
