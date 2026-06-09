# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::IsAppGPStateLocked(HSTRING__ *)

- ea: `0x180048b00`
- end: `0x180048c1d`
- name: `?IsAppGPStateLocked@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAEPEAUHSTRING__@@@Z`
- size: `285`
- prototype: `unsigned __int8 __fastcall(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, HSTRING)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b824`
- `0x18004e044`

## callees

- `0x18002e2b0`
- `0x18002fa74`
- `0x18004896c`
- `0x180048b00`
- `0x180049164`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048be4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048be4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048ba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048ba7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::IsAppGPStateLocked(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        HSTRING a2)
{
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v2; // rcx
  int CurrentUserSidString; // eax
  int v4; // eax
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, unsigned __int16 *, PCWSTR, int *); // rbx
  PCWSTR StringRawBuffer; // rax
  bool v10; // bl
  int v12; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h]
  __int64 v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v17; // [rsp+70h] [rbp+20h] BYREF
  int v18; // [rsp+74h] [rbp+24h]
  HSTRING v19; // [rsp+78h] [rbp+28h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  v19 = a2;
  v18 = HIDWORD(this);
  v17 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v13);
  v14 = -1;
  v15 = -1;
  CurrentUserSidString = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(
                           v2,
                           &v13);
  if ( CurrentUserSidString >= 0 )
  {
    string = 0;
    v4 = Microsoft::WRL::Wrappers::HString::Set(&string, &v19);
    v5 = retaddr;
    if ( v4 >= 0 )
    {
      v7 = *((_QWORD *)&xmmword_18007A0A0 + 1);
      v8 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, int *))(**((_QWORD **)&xmmword_18007A0A0 + 1)
                                                                                + 40LL);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v4 = v8(v7, v13, StringRawBuffer, &v17);
      v5 = retaddr;
      if ( v4 >= 0 )
      {
        v10 = (v17 & 4) != 0;
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_10;
      }
      v6 = 369;
    }
    else
    {
      v6 = 367;
    }
    wil::details::in1diag3::_Log_Hr(
      v5,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)v4,
      v12);
    WindowsDeleteString(string);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      v12);
  }
  v10 = 0;
LABEL_10:
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v13);
  return v10;
}

```

## disassembly

```asm
0x180048b00  mov     [rsp-18h+arg_8], rdx
0x180048b05  mov     [rsp-18h+arg_0], rcx
0x180048b0a  push    rbp
0x180048b0b  push    rbx
0x180048b0c  push    rdi
0x180048b0d  mov     rbp, rsp
0x180048b10  sub     rsp, 50h
0x180048b14  mov     dword ptr [rbp+arg_0], 0
0x180048b1b  mov     [rbp+var_20], 0
0x180048b23  mov     [rbp+var_18], 0
0x180048b2b  mov     [rbp+var_10], 0
0x180048b33  lea     rcx, [rbp+var_20]
0x180048b37  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048b3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048b40  mov     [rbp+var_18], rax
0x180048b44  mov     [rbp+var_10], rax
0x180048b48  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180048b4c  call    ?GetCurrentUserSidString@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAG@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(ushort * *)
0x180048b51  mov     rcx, [rbp+18h]; this
0x180048b55  test    eax, eax
0x180048b57  jns     short loc_180048B6F
0x180048b59  mov     r9d, eax; char *
0x180048b5c  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048b63  mov     edx, 16Ch; void *
0x180048b68  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048b6d  jmp     short loc_180048BEA
0x180048b6f  mov     [rbp+string], 0
0x180048b77  lea     rdx, [rbp+arg_8]; HSTRING *
0x180048b7b  lea     rcx, [rbp+string]; newString
0x180048b7f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180048b84  mov     rcx, [rbp+18h]
0x180048b88  test    eax, eax
0x180048b8a  jns     short loc_180048B93
0x180048b8c  mov     edx, 16Fh
0x180048b91  jmp     short loc_180048BD0
0x180048b93  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x180048b9a  mov     rax, [rdi]
0x180048b9d  mov     rbx, [rax+28h]
0x180048ba1  xor     edx, edx; length
0x180048ba3  mov     rcx, [rbp+string]; string
0x180048ba7  call    cs:__imp_WindowsGetStringRawBuffer
0x180048bad  lea     r9, [rbp+arg_0]
0x180048bb1  mov     r8, rax
0x180048bb4  mov     rdx, [rbp+var_20]
0x180048bb8  mov     rcx, rdi
0x180048bbb  mov     rax, rbx
0x180048bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bc3  mov     rcx, [rbp+18h]; this
0x180048bc7  test    eax, eax
0x180048bc9  jns     short loc_180048BEE
0x180048bcb  mov     edx, 171h; void *
0x180048bd0  mov     r9d, eax; char *
0x180048bd3  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048bda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048bdf  nop
0x180048be0  mov     rcx, [rbp+string]; string
0x180048be4  call    cs:__imp_WindowsDeleteString
0x180048bea  xor     ebx, ebx
0x180048bec  jmp     short loc_180048C0A
0x180048bee  test    dword ptr [rbp+arg_0], 4
0x180048bf5  setnz   bl
0x180048bf8  mov     rcx, [rbp+string]; string
0x180048bfc  call    cs:__imp_WindowsDeleteString
0x180048c02  mov     [rbp+string], 0
0x180048c0a  lea     rcx, [rbp+var_20]
0x180048c0e  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048c13  mov     al, bl
0x180048c15  add     rsp, 50h
0x180048c19  pop     rdi
0x180048c1a  pop     rbx
0x180048c1b  pop     rbp
0x180048c1c  retn
```
