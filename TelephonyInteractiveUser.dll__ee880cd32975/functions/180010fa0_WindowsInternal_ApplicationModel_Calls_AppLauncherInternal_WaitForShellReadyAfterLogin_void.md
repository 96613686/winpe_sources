# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_WaitForShellReadyAfterLogin(void)

- ea: `0x180010fa0`
- end: `0x180011019`
- name: `?_WaitForShellReadyAfterLogin@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@MEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001348`
- `0x18000cf2c`
- `0x180010fa0`

## import_xrefs

- `PhoneUtil!CheckIfShellReady` at `0x180010fab`
- `PhoneUtil!CheckIfShellReady` at `0x180010fab`

## string_xrefs

- `0x180010fc9`: `AppLauncherInternal: Waiting for shell ready after login`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_WaitForShellReadyAfterLogin(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this)
{
  int v1; // eax
  int v2; // r8d
  int v3; // r9d
  int v4; // ebx
  int v6; // [rsp+48h] [rbp+10h] BYREF
  const char *v7; // [rsp+50h] [rbp+18h] BYREF

  v1 = CheckIfShellReady(0x7530u);
  v4 = v1;
  if ( (unsigned int)dword_180025038 > 4 )
  {
    v6 = v1;
    v7 = "AppLauncherInternal: Waiting for shell ready after login";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_180025038,
      (unsigned int)&dword_18002078C,
      v2,
      v3,
      (__int64)&v7,
      (__int64)&v6);
  }
  if ( v4 )
    return 0;
  Log_HREvent_0(2147943860LL, 0, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
  return 2147943860LL;
}

```

## disassembly

```asm
0x180010fa0  push    rbx
0x180010fa2  sub     rsp, 30h
0x180010fa6  mov     ecx, 7530h
0x180010fab  call    cs:__imp_?CheckIfShellReady@@YAHK@Z; CheckIfShellReady(ulong)
0x180010fb1  mov     ecx, cs:dword_180025038
0x180010fb7  mov     ebx, eax
0x180010fb9  cmp     ecx, 4
0x180010fbc  jbe     short loc_180010FEE
0x180010fbe  mov     [rsp+38h+arg_8], eax
0x180010fc2  lea     rdx, dword_18002078C
0x180010fc9  lea     rax, aApplauncherint_2; "AppLauncherInternal: Waiting for shell "...
0x180010fd0  mov     [rsp+38h+arg_10], rax
0x180010fd5  lea     rax, [rsp+38h+arg_8]
0x180010fda  mov     [rsp+38h+var_10], rax
0x180010fdf  lea     rax, [rsp+38h+arg_10]
0x180010fe4  mov     [rsp+38h+var_18], rax
0x180010fe9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180010fee  test    ebx, ebx
0x180010ff0  jnz     short loc_180011011
0x180010ff2  mov     ebx, 800705B4h
0x180010ff7  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010ffe  mov     ecx, ebx
0x180011000  mov     r9d, 129h
0x180011006  xor     edx, edx
0x180011008  call    Log_HREvent_0
0x18001100d  mov     eax, ebx
0x18001100f  jmp     short loc_180011013
0x180011011  xor     eax, eax
0x180011013  add     rsp, 30h
0x180011017  pop     rbx
0x180011018  retn
```
