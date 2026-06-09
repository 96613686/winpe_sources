# CSleepStudyPowerReferenceManager::Initialize(void)

- ea: `0x1800ace20`
- end: `0x1800ad00f`
- name: `?Initialize@CSleepStudyPowerReferenceManager@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(CSleepStudyPowerReferenceManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800edee8`

## callees

- `0x1800252b0`
- `0x180026c70`
- `0x1800acdcc`
- `0x1800ace20`
- `0x1800ad018`
- `0x1800ad0c0`
- `0x1800cd8d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800aceb9`
- `ntdll!RtlInitUnicodeString` at `0x1800aceb9`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800acf31`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800acfdf`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800acf31`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800acfdf`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800acf84`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800acfd0`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800acf84`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800acfd0`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800acf57`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800acf57`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800acf00`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800acf00`
- `UMPDC!SleepstudyHelperCreateLibraryEx` at `0x1800ace73`
- `UMPDC!SleepstudyHelperCreateLibraryEx` at `0x1800ace73`

## string_xrefs

- `0x1800ace8c`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800acf0e`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800acf65`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`

## pseudocode

```c
__int64 __fastcall CSleepStudyPowerReferenceManager::Initialize(GUID *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-19h]
  __int64 v9; // [rsp+30h] [rbp-9h] BYREF
  __int64 v10; // [rsp+38h] [rbp-1h]
  __int64 v11; // [rsp+40h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp+Fh] BYREF
  _DWORD v13[4]; // [rsp+58h] [rbp+1Fh] BYREF
  GUID v14; // [rsp+68h] [rbp+2Fh] BYREF
  GUID v15; // [rsp+78h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v9 = 0;
  v13[0] = 1;
  v13[1] = 7369325;
  v13[2] = 2;
  wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&long SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(
    &v9,
    0);
  v2 = SleepstudyHelperCreateLibraryEx(v13, &v9);
  if ( v2 == -1073741637 )
    goto LABEL_17;
  if ( v2 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0xBE,
           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
           (const char *)(unsigned int)v2,
           v8);
    goto LABEL_18;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Audio Streams");
  v10 = 0;
  v15 = GUID_SPR_BLOCKER_GROUP_AUDIO_ACTIVITY;
  v14 = GUID_AUDIOSRV_VIRTUAL_POWER_REFERENCE_BLOCKER;
  v4 = SleepstudyHelperCreateBlockerFromGuid(v9, &v15, &v14, &DestinationString);
  if ( v4 >= 0 )
  {
    v11 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&long SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(
      &v11,
      0);
    v5 = SleepstudyHelperBuildBlocker(v10, &v11);
    if ( v5 < 0 )
    {
      v3 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xD4,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
             (const char *)(unsigned int)v5,
             8);
      if ( v11 )
        SleepstudyHelperDestroyBlocker();
      goto LABEL_6;
    }
    v10 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&long SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>>::operator=(
      this->Data4,
      &v11);
    if ( this != (GUID *)&v9 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&long SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(
        this,
        v9);
      v9 = 0;
    }
    v6 = v11;
    this[1] = v14;
    if ( v6 )
      SleepstudyHelperDestroyBlocker();
    if ( v10 )
      SleepstudyHelperDestroyBlockerBuilder();
LABEL_17:
    v3 = 0;
    goto LABEL_18;
  }
  v3 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0xD1,
         (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
         (const char *)(unsigned int)v4,
         8);
LABEL_6:
  if ( v10 )
    SleepstudyHelperDestroyBlockerBuilder();
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&long SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&long SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>(&v9);
  return v3;
}

```

## disassembly

```asm
0x1800ace20  mov     [rsp-8+arg_8], rbx
0x1800ace25  push    rbp
0x1800ace26  lea     rbp, [rsp-57h]
0x1800ace2b  sub     rsp, 90h
0x1800ace32  mov     rax, cs:__security_cookie
0x1800ace39  xor     rax, rsp
0x1800ace3c  mov     [rbp+57h+var_8], rax
0x1800ace40  mov     rbx, rcx
0x1800ace43  mov     [rbp+57h+var_60], 0
0x1800ace4b  lea     rcx, [rbp+57h+var_60]
0x1800ace4f  mov     [rbp+57h+var_38], 1
0x1800ace56  xor     edx, edx
0x1800ace58  mov     [rbp+57h+var_34], 70726Dh
0x1800ace5f  mov     [rbp+57h+var_30], 2
0x1800ace66  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_LIBRARY@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_LIBRARY *)
0x1800ace6b  lea     rdx, [rbp+57h+var_60]
0x1800ace6f  lea     rcx, [rbp+57h+var_38]
0x1800ace73  call    cs:__imp_SleepstudyHelperCreateLibraryEx
0x1800ace79  cmp     eax, 0C00000BBh
0x1800ace7e  jz      loc_1800ACFE5
0x1800ace84  test    eax, eax
0x1800ace86  jns     short loc_1800ACEA7
0x1800ace88  mov     rcx, [rbp+5Fh]; this
0x1800ace8c  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800ace93  mov     r9d, eax; char *
0x1800ace96  mov     edx, 0BEh; void *
0x1800ace9b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800acea0  mov     ebx, eax
0x1800acea2  jmp     loc_1800ACFE7
0x1800acea7  xorps   xmm0, xmm0
0x1800aceaa  lea     rdx, SourceString; "Audio Streams"
0x1800aceb1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800aceb5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800aceb9  call    cs:__imp_RtlInitUnicodeString
0x1800acebf  movups  xmm0, xmmword ptr cs:GUID_SPR_BLOCKER_GROUP_AUDIO_ACTIVITY.Data1
0x1800acec6  mov     rcx, [rbp+57h+var_60]
0x1800aceca  lea     rax, [rbp+57h+var_58]
0x1800acece  movups  xmm1, xmmword ptr cs:GUID_AUDIOSRV_VIRTUAL_POWER_REFERENCE_BLOCKER.Data1
0x1800aced5  mov     [rsp+90h+var_68], rax
0x1800aceda  lea     r9, [rbp+57h+DestinationString]
0x1800acede  lea     r8, [rbp+57h+var_28]
0x1800acee2  mov     [rbp+57h+var_58], 0
0x1800aceea  lea     rdx, [rbp+57h+var_18]
0x1800aceee  mov     [rsp+90h+var_70], 8; int
0x1800acef6  movdqu  [rbp+57h+var_18], xmm0
0x1800acefb  movdqu  [rbp+57h+var_28], xmm1
0x1800acf00  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x1800acf06  test    eax, eax
0x1800acf08  jns     short loc_1800ACF3C
0x1800acf0a  mov     rcx, [rbp+5Fh]; this
0x1800acf0e  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800acf15  mov     r9d, eax; char *
0x1800acf18  mov     edx, 0D1h; void *
0x1800acf1d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800acf22  mov     ebx, eax
0x1800acf24  mov     rcx, [rbp+57h+var_58]
0x1800acf28  test    rcx, rcx
0x1800acf2b  jz      loc_1800ACFE7
0x1800acf31  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800acf37  jmp     loc_1800ACFE7
0x1800acf3c  xor     edx, edx
0x1800acf3e  mov     [rbp+57h+var_50], 0
0x1800acf46  lea     rcx, [rbp+57h+var_50]
0x1800acf4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_BLOCKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_BLOCKER *)
0x1800acf4f  mov     rcx, [rbp+57h+var_58]
0x1800acf53  lea     rdx, [rbp+57h+var_50]
0x1800acf57  call    cs:__imp_SleepstudyHelperBuildBlocker
0x1800acf5d  test    eax, eax
0x1800acf5f  jns     short loc_1800ACF8C
0x1800acf61  mov     rcx, [rbp+5Fh]; this
0x1800acf65  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800acf6c  mov     r9d, eax; char *
0x1800acf6f  mov     edx, 0D4h; void *
0x1800acf74  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800acf79  mov     rcx, [rbp+57h+var_50]
0x1800acf7d  mov     ebx, eax
0x1800acf7f  test    rcx, rcx
0x1800acf82  jz      short loc_1800ACF24
0x1800acf84  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800acf8a  jmp     short loc_1800ACF24
0x1800acf8c  lea     rcx, [rbx+8]
0x1800acf90  mov     [rbp+57h+var_58], 0
0x1800acf98  lea     rdx, [rbp+57h+var_50]
0x1800acf9c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>> &&)
0x1800acfa1  lea     rax, [rbp+57h+var_60]
0x1800acfa5  cmp     rbx, rax
0x1800acfa8  jz      short loc_1800ACFBE
0x1800acfaa  mov     rdx, [rbp+57h+var_60]
0x1800acfae  mov     rcx, rbx
0x1800acfb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_LIBRARY@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_LIBRARY *)
0x1800acfb6  mov     [rbp+57h+var_60], 0
0x1800acfbe  movups  xmm0, [rbp+57h+var_28]
0x1800acfc2  mov     rcx, [rbp+57h+var_50]
0x1800acfc6  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800acfcb  test    rcx, rcx
0x1800acfce  jz      short loc_1800ACFD6
0x1800acfd0  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800acfd6  mov     rcx, [rbp+57h+var_58]
0x1800acfda  test    rcx, rcx
0x1800acfdd  jz      short loc_1800ACFE5
0x1800acfdf  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800acfe5  xor     ebx, ebx
0x1800acfe7  lea     rcx, [rbp+57h+var_60]
0x1800acfeb  call    ??1?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>(void)
0x1800acff0  mov     eax, ebx
0x1800acff2  mov     rcx, [rbp+57h+var_8]
0x1800acff6  xor     rcx, rsp; StackCookie
0x1800acff9  call    __security_check_cookie
0x1800acffe  mov     rbx, [rsp+90h+arg_8]
0x1800ad006  add     rsp, 90h
0x1800ad00d  pop     rbp
0x1800ad00e  retn
```
