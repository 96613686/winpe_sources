# CSleepStudyPowerReferenceManager::CreatePowerReferenceSubBlocker(CVADServer *,std::shared_ptr<CSleepStudyPowerReference> *)

- ea: `0x180024310`
- end: `0x180024679`
- name: `?CreatePowerReferenceSubBlocker@CSleepStudyPowerReferenceManager@@QEAAJPEAVCVADServer@@PEAV?$shared_ptr@VCSleepStudyPowerReference@@@std@@@Z`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800236e4`

## callees

- `0x1800126bc`
- `0x180023690`
- `0x180024310`
- `0x180025160`
- `0x1800251c0`
- `0x1800aedc0`
- `0x1800cf8c0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024361`
- `ntdll!RtlInitUnicodeString` at `0x180024361`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800243ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800243ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800243fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800243fe`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002461e`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180024634`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002464a`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002465a`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002461e`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180024634`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002464a`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002465a`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x180024481`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x180024481`
- `UMPDC!SleepstudyHelperSetBlockerParentHandle` at `0x1800243b7`
- `UMPDC!SleepstudyHelperSetBlockerParentHandle` at `0x1800243b7`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002460b`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024616`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024629`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002463f`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024652`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024665`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002460b`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024616`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024629`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002463f`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024652`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024665`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800243d8`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x1800243d8`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800243a0`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800243a0`

## string_xrefs

- `0x1800244da`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x18002450a`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x18002455a`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800245a1`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800245d0`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`

## pseudocode

```c
__int64 __fastcall CSleepStudyPowerReferenceManager::CreatePowerReferenceSubBlocker(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  const WCHAR *ClientFriendlyName; // rax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v12; // rax
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rdi
  std::_Ref_count_base *v15; // rcx
  int active; // eax
  __int64 v17; // rdx
  __int64 result; // rax
  unsigned int v19; // ebx
  unsigned int v20; // edi
  __int64 v21; // [rsp+38h] [rbp-50h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  __int128 v23; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    if ( !a1[1] || !*a1 )
      return 0;
    DestinationString = 0;
    ClientFriendlyName = CAudioStream::GetClientFriendlyName(*(CAudioStream **)(a2 + 176));
    RtlInitUnicodeString(&DestinationString, ClientFriendlyName);
    v23 = *(_OWORD *)(a2 + 256);
    v8 = SleepstudyHelperCreateBlockerFromGuid(*a1, a1 + 2, &v23, &DestinationString);
    if ( v8 < 0 )
      return (unsigned int)wil::details::in1diag3::Return_NtStatus(
                             retaddr,
                             (void *)0xF4,
                             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
                             (const char *)(unsigned int)v8,
                             8);
    v9 = SleepstudyHelperSetBlockerParentHandle(0, a1[1]);
    if ( v9 < 0 )
      return (unsigned int)wil::details::in1diag3::Return_NtStatus(
                             retaddr,
                             (void *)0xF6,
                             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
                             (const char *)(unsigned int)v9,
                             8);
    v21 = 0;
    v10 = SleepstudyHelperBuildBlocker(0, &v21);
    if ( v10 < 0 )
    {
      v19 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xF9,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
              (const char *)(unsigned int)v10,
              8);
      if ( v21 )
        ((void (*)(void))SleepstudyHelperDestroyBlocker)();
      result = v19;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v12 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 0, 0x18u);
      v13 = v12;
      if ( v12 )
      {
        *((_DWORD *)v12 + 2) = 1;
        *((_DWORD *)v12 + 3) = 1;
        *(_QWORD *)v12 = &std::_Ref_count_obj2<CSleepStudyPowerReference>::`vftable';
        *((_QWORD *)v12 + 2) = 0;
        v14 = (__int64)(v12 + 4);
        if ( v12 == (volatile signed __int32 *)-16LL )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
            (const char *)0x8007000ELL,
            8);
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)0xFFFFFFFFFFFFFFF0LL);
          if ( v21 )
            ((void (*)(void))SleepstudyHelperDestroyBlocker)();
          return 2147942414LL;
        }
      }
      else
      {
        v13 = 0;
        v14 = 16;
      }
      if ( (__int64 *)v14 != &v21 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&long SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(
          v14,
          v21);
        v21 = 0;
      }
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      *(_QWORD *)a3 = v14;
      v15 = *(std::_Ref_count_base **)(a3 + 8);
      *(_QWORD *)(a3 + 8) = v13;
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      active = SleepstudyHelperBlockerActiveReference(**(_QWORD **)a3);
      if ( active >= 0 )
      {
        if ( v13 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
        if ( v21 )
          SleepstudyHelperDestroyBlocker(v21, v17);
        return 0;
      }
      v20 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x103,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
              (const char *)(unsigned int)active,
              8);
      if ( v13 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
      if ( v21 )
        ((void (*)(void))SleepstudyHelperDestroyBlocker)();
      result = v20;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x108,
                           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\powerreference.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180024310  push    rbx
0x180024312  push    rsi
0x180024313  push    rdi
0x180024314  sub     rsp, 70h
0x180024318  mov     rax, cs:__security_cookie
0x18002431f  xor     rax, rsp
0x180024322  mov     [rsp+88h+var_28], rax
0x180024327  mov     rsi, r8
0x18002432a  mov     rdi, rdx
0x18002432d  mov     rbx, rcx
0x180024330  cmp     qword ptr [rcx+8], 0
0x180024335  jz      loc_1800244B8
0x18002433b  cmp     qword ptr [rcx], 0
0x18002433f  jz      loc_1800244B8
0x180024345  xorps   xmm0, xmm0
0x180024348  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18002434d  mov     rcx, [rdx+0B0h]; this
0x180024354  call    ?GetClientFriendlyName@CAudioStream@@QEAAPEBGXZ; CAudioStream::GetClientFriendlyName(void)
0x180024359  mov     rdx, rax; SourceString
0x18002435c  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180024361  call    cs:__imp_RtlInitUnicodeString
0x180024367  movups  xmm0, xmmword ptr [rdi+100h]
0x18002436e  movdqu  [rsp+88h+var_38], xmm0
0x180024374  mov     [rsp+88h+var_58], 0
0x18002437d  lea     rdx, [rbx+10h]
0x180024381  lea     rax, [rsp+88h+var_58]
0x180024386  mov     [rsp+88h+var_60], rax
0x18002438b  mov     [rsp+88h+var_68], 8; int
0x180024393  lea     r9, [rsp+88h+DestinationString]
0x180024398  lea     r8, [rsp+88h+var_38]
0x18002439d  mov     rcx, [rbx]
0x1800243a0  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x1800243a6  test    eax, eax
0x1800243a8  js      loc_1800244CF
0x1800243ae  mov     rdx, [rbx+8]
0x1800243b2  mov     rcx, [rsp+88h+var_58]
0x1800243b7  call    cs:__imp_SleepstudyHelperSetBlockerParentHandle
0x1800243bd  test    eax, eax
0x1800243bf  js      loc_180024596
0x1800243c5  mov     [rsp+88h+var_50], 0
0x1800243ce  lea     rdx, [rsp+88h+var_50]
0x1800243d3  mov     rcx, [rsp+88h+var_58]
0x1800243d8  call    cs:__imp_SleepstudyHelperBuildBlocker
0x1800243de  test    eax, eax
0x1800243e0  js      loc_1800244FF
0x1800243e6  mov     [rsp+88h+var_58], 0
0x1800243ef  call    cs:__imp_GetProcessHeap
0x1800243f5  mov     rcx, rax; hHeap
0x1800243f8  xor     edx, edx; dwFlags
0x1800243fa  lea     r8d, [rdx+18h]; dwBytes
0x1800243fe  call    cs:__imp_HeapAlloc
0x180024404  mov     rbx, rax
0x180024407  test    rax, rax
0x18002440a  jz      loc_180024540
0x180024410  mov     dword ptr [rax+8], 1
0x180024417  mov     dword ptr [rax+0Ch], 1
0x18002441e  lea     rax, ??_7?$_Ref_count_obj2@VCSleepStudyPowerReference@@@std@@6B@; const std::_Ref_count_obj2<CSleepStudyPowerReference>::`vftable'
0x180024425  mov     [rbx], rax
0x180024428  mov     qword ptr [rbx+10h], 0
0x180024430  lea     rdi, [rbx+10h]
0x180024434  test    rdi, rdi
0x180024437  jz      loc_18002454A
0x18002443d  lea     rax, [rsp+88h+var_50]
0x180024442  cmp     rdi, rax
0x180024445  jz      short loc_18002445D
0x180024447  mov     rdx, [rsp+88h+var_50]
0x18002444c  mov     rcx, rdi
0x18002444f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_BLOCKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_BLOCKER *)
0x180024454  mov     [rsp+88h+var_50], 0
0x18002445d  test    rbx, rbx
0x180024460  jz      short loc_180024466
0x180024462  lock inc dword ptr [rbx+8]
0x180024466  mov     [rsi], rdi
0x180024469  mov     rcx, [rsi+8]; this
0x18002446d  mov     [rsi+8], rbx
0x180024471  test    rcx, rcx
0x180024474  jz      short loc_18002447B
0x180024476  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002447b  mov     rcx, [rsi]
0x18002447e  mov     rcx, [rcx]
0x180024481  call    cs:__imp_SleepstudyHelperBlockerActiveReference
0x180024487  test    eax, eax
0x180024489  js      loc_1800245C5
0x18002448f  test    rbx, rbx
0x180024492  jz      short loc_18002449C
0x180024494  mov     rcx, rbx; this
0x180024497  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002449c  mov     rcx, [rsp+88h+var_50]
0x1800244a1  test    rcx, rcx
0x1800244a4  jnz     loc_18002465A
0x1800244aa  mov     rcx, [rsp+88h+var_58]
0x1800244af  test    rcx, rcx
0x1800244b2  jnz     loc_180024665
0x1800244b8  xor     eax, eax
0x1800244ba  mov     rcx, [rsp+88h+var_28]
0x1800244bf  xor     rcx, rsp; StackCookie
0x1800244c2  call    __security_check_cookie
0x1800244c7  add     rsp, 70h
0x1800244cb  pop     rdi
0x1800244cc  pop     rsi
0x1800244cd  pop     rbx
0x1800244ce  retn
0x1800244cf  mov     rcx, [rsp+88h]; this
0x1800244d7  mov     r9d, eax; char *
0x1800244da  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800244e1  mov     edx, 0F4h; void *
0x1800244e6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800244eb  mov     ebx, eax
0x1800244ed  mov     rcx, [rsp+88h+var_58]
0x1800244f2  test    rcx, rcx
0x1800244f5  jnz     loc_18002460B
0x1800244fb  mov     eax, ebx
0x1800244fd  jmp     short loc_1800244BA
0x1800244ff  mov     rcx, [rsp+88h]; this
0x180024507  mov     r9d, eax; char *
0x18002450a  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180024511  mov     edx, 0F9h; void *
0x180024516  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002451b  mov     ebx, eax
0x18002451d  mov     rcx, [rsp+88h+var_50]
0x180024522  test    rcx, rcx
0x180024525  jnz     loc_18002461E
0x18002452b  mov     rcx, [rsp+88h+var_58]
0x180024530  test    rcx, rcx
0x180024533  jnz     loc_180024629
0x180024539  mov     eax, ebx
0x18002453b  jmp     loc_1800244BA
0x180024540  xor     ebx, ebx
0x180024542  lea     edi, [rbx+10h]
0x180024545  jmp     loc_18002443D
0x18002454a  mov     rcx, [rsp+88h]; this
0x180024552  mov     edi, 8007000Eh
0x180024557  mov     r9d, edi; char *
0x18002455a  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180024561  mov     edx, 0FFh; void *
0x180024566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002456b  mov     rcx, rbx; this
0x18002456e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180024573  mov     rcx, [rsp+88h+var_50]
0x180024578  test    rcx, rcx
0x18002457b  jnz     loc_180024634
0x180024581  mov     rcx, [rsp+88h+var_58]
0x180024586  test    rcx, rcx
0x180024589  jnz     loc_18002463F
0x18002458f  mov     eax, edi
0x180024591  jmp     loc_1800244BA
0x180024596  mov     rcx, [rsp+88h]; this
0x18002459e  mov     r9d, eax; char *
0x1800245a1  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800245a8  mov     edx, 0F6h; void *
0x1800245ad  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800245b2  mov     ebx, eax
0x1800245b4  mov     rcx, [rsp+88h+var_58]
0x1800245b9  test    rcx, rcx
0x1800245bc  jnz     short loc_180024616
0x1800245be  mov     eax, ebx
0x1800245c0  jmp     loc_1800244BA
0x1800245c5  mov     rcx, [rsp+88h]; this
0x1800245cd  mov     r9d, eax; char *
0x1800245d0  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800245d7  mov     edx, 103h; void *
0x1800245dc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800245e1  mov     edi, eax
0x1800245e3  test    rbx, rbx
0x1800245e6  jz      short loc_1800245F0
0x1800245e8  mov     rcx, rbx; this
0x1800245eb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800245f0  mov     rcx, [rsp+88h+var_50]
0x1800245f5  test    rcx, rcx
0x1800245f8  jnz     short loc_18002464A
0x1800245fa  mov     rcx, [rsp+88h+var_58]
0x1800245ff  test    rcx, rcx
0x180024602  jnz     short loc_180024652
0x180024604  mov     eax, edi
0x180024606  jmp     loc_1800244BA
0x18002460b  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180024611  jmp     loc_1800244FB
0x180024616  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002461c  jmp     short loc_1800245BE
0x18002461e  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x180024624  jmp     loc_18002452B
0x180024629  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002462f  jmp     loc_180024539
0x180024634  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x18002463a  jmp     loc_180024581
0x18002463f  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180024645  jmp     loc_18002458F
0x18002464a  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x180024650  jmp     short loc_1800245FA
0x180024652  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180024658  jmp     short loc_180024604
0x18002465a  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x180024660  jmp     loc_1800244AA
0x180024665  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002466b  jmp     loc_1800244B8
0x180024670  mov     eax, dword ptr [rsp+88h+var_58]
0x180024674  jmp     loc_1800244BA
```
