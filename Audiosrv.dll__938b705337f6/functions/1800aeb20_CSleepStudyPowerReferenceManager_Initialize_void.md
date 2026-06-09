# CSleepStudyPowerReferenceManager::Initialize(void)

- ea: `0x1800aeb20`
- end: `0x1800aed0f`
- name: `?Initialize@CSleepStudyPowerReferenceManager@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(CSleepStudyPowerReferenceManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ee68c`

## callees

- `0x180025160`
- `0x180026b14`
- `0x1800aeacc`
- `0x1800aeb20`
- `0x1800aed18`
- `0x1800aedc0`
- `0x1800cf8c0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800aebb9`
- `ntdll!RtlInitUnicodeString` at `0x1800aebb9`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800aec84`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800aecd0`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800aec84`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800aecd0`
- `UMPDC!SleepstudyHelperCreateLibraryEx` at `0x1800aeb73`
- `UMPDC!SleepstudyHelperCreateLibraryEx` at `0x1800aeb73`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800aec31`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800aecdf`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800aec31`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800aecdf`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800aec57`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800aec57`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800aec00`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800aec00`

## string_xrefs

- `0x1800aeb8c`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800aec0e`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800aec65`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`

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
0x1800aeb20  mov     [rsp-8+arg_8], rbx
0x1800aeb25  push    rbp
0x1800aeb26  lea     rbp, [rsp-57h]
0x1800aeb2b  sub     rsp, 90h
0x1800aeb32  mov     rax, cs:__security_cookie
0x1800aeb39  xor     rax, rsp
0x1800aeb3c  mov     [rbp+57h+var_8], rax
0x1800aeb40  mov     rbx, rcx
0x1800aeb43  mov     [rbp+57h+var_60], 0
0x1800aeb4b  lea     rcx, [rbp+57h+var_60]
0x1800aeb4f  mov     [rbp+57h+var_38], 1
0x1800aeb56  xor     edx, edx
0x1800aeb58  mov     [rbp+57h+var_34], 70726Dh
0x1800aeb5f  mov     [rbp+57h+var_30], 2
0x1800aeb66  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_LIBRARY@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_LIBRARY *)
0x1800aeb6b  lea     rdx, [rbp+57h+var_60]
0x1800aeb6f  lea     rcx, [rbp+57h+var_38]
0x1800aeb73  call    cs:__imp_SleepstudyHelperCreateLibraryEx
0x1800aeb79  cmp     eax, 0C00000BBh
0x1800aeb7e  jz      loc_1800AECE5
0x1800aeb84  test    eax, eax
0x1800aeb86  jns     short loc_1800AEBA7
0x1800aeb88  mov     rcx, [rbp+5Fh]; this
0x1800aeb8c  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800aeb93  mov     r9d, eax; char *
0x1800aeb96  mov     edx, 0BEh; void *
0x1800aeb9b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aeba0  mov     ebx, eax
0x1800aeba2  jmp     loc_1800AECE7
0x1800aeba7  xorps   xmm0, xmm0
0x1800aebaa  lea     rdx, SourceString; "Audio Streams"
0x1800aebb1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800aebb5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800aebb9  call    cs:__imp_RtlInitUnicodeString
0x1800aebbf  movups  xmm0, xmmword ptr cs:GUID_SPR_BLOCKER_GROUP_AUDIO_ACTIVITY.Data1
0x1800aebc6  mov     rcx, [rbp+57h+var_60]
0x1800aebca  lea     rax, [rbp+57h+var_58]
0x1800aebce  movups  xmm1, xmmword ptr cs:GUID_AUDIOSRV_VIRTUAL_POWER_REFERENCE_BLOCKER.Data1
0x1800aebd5  mov     [rsp+90h+var_68], rax
0x1800aebda  lea     r9, [rbp+57h+DestinationString]
0x1800aebde  lea     r8, [rbp+57h+var_28]
0x1800aebe2  mov     [rbp+57h+var_58], 0
0x1800aebea  lea     rdx, [rbp+57h+var_18]
0x1800aebee  mov     [rsp+90h+var_70], 8; int
0x1800aebf6  movdqu  [rbp+57h+var_18], xmm0
0x1800aebfb  movdqu  [rbp+57h+var_28], xmm1
0x1800aec00  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x1800aec06  test    eax, eax
0x1800aec08  jns     short loc_1800AEC3C
0x1800aec0a  mov     rcx, [rbp+5Fh]; this
0x1800aec0e  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800aec15  mov     r9d, eax; char *
0x1800aec18  mov     edx, 0D1h; void *
0x1800aec1d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aec22  mov     ebx, eax
0x1800aec24  mov     rcx, [rbp+57h+var_58]
0x1800aec28  test    rcx, rcx
0x1800aec2b  jz      loc_1800AECE7
0x1800aec31  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800aec37  jmp     loc_1800AECE7
0x1800aec3c  xor     edx, edx
0x1800aec3e  mov     [rbp+57h+var_50], 0
0x1800aec46  lea     rcx, [rbp+57h+var_50]
0x1800aec4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_BLOCKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_BLOCKER *)
0x1800aec4f  mov     rcx, [rbp+57h+var_58]
0x1800aec53  lea     rdx, [rbp+57h+var_50]
0x1800aec57  call    cs:__imp_SleepstudyHelperBuildBlocker
0x1800aec5d  test    eax, eax
0x1800aec5f  jns     short loc_1800AEC8C
0x1800aec61  mov     rcx, [rbp+5Fh]; this
0x1800aec65  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800aec6c  mov     r9d, eax; char *
0x1800aec6f  mov     edx, 0D4h; void *
0x1800aec74  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aec79  mov     rcx, [rbp+57h+var_50]
0x1800aec7d  mov     ebx, eax
0x1800aec7f  test    rcx, rcx
0x1800aec82  jz      short loc_1800AEC24
0x1800aec84  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800aec8a  jmp     short loc_1800AEC24
0x1800aec8c  lea     rcx, [rbx+8]
0x1800aec90  mov     [rbp+57h+var_58], 0
0x1800aec98  lea     rdx, [rbp+57h+var_50]
0x1800aec9c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>> &&)
0x1800aeca1  lea     rax, [rbp+57h+var_60]
0x1800aeca5  cmp     rbx, rax
0x1800aeca8  jz      short loc_1800AECBE
0x1800aecaa  mov     rdx, [rbp+57h+var_60]
0x1800aecae  mov     rcx, rbx
0x1800aecb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_LIBRARY@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_LIBRARY *)
0x1800aecb6  mov     [rbp+57h+var_60], 0
0x1800aecbe  movups  xmm0, [rbp+57h+var_28]
0x1800aecc2  mov     rcx, [rbp+57h+var_50]
0x1800aecc6  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800aeccb  test    rcx, rcx
0x1800aecce  jz      short loc_1800AECD6
0x1800aecd0  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800aecd6  mov     rcx, [rbp+57h+var_58]
0x1800aecda  test    rcx, rcx
0x1800aecdd  jz      short loc_1800AECE5
0x1800aecdf  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800aece5  xor     ebx, ebx
0x1800aece7  lea     rcx, [rbp+57h+var_60]
0x1800aeceb  call    ??1?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_LIBRARY@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyLibrary@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SLEEPSTUDY_LIBRARY *,long (*)(_SLEEPSTUDY_LIBRARY *),&SleepstudyHelperDestroyLibrary(_SLEEPSTUDY_LIBRARY *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_LIBRARY *,_SLEEPSTUDY_LIBRARY *,0,std::nullptr_t>>(void)
0x1800aecf0  mov     eax, ebx
0x1800aecf2  mov     rcx, [rbp+57h+var_8]
0x1800aecf6  xor     rcx, rsp; StackCookie
0x1800aecf9  call    __security_check_cookie
0x1800aecfe  mov     rbx, [rsp+90h+arg_8]
0x1800aed06  add     rsp, 90h
0x1800aed0d  pop     rbp
0x1800aed0e  retn
```
