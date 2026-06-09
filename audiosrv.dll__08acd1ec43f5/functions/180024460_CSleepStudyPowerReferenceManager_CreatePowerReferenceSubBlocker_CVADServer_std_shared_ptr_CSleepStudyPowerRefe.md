# CSleepStudyPowerReferenceManager::CreatePowerReferenceSubBlocker(CVADServer *,std::shared_ptr<CSleepStudyPowerReference> *)

- ea: `0x180024460`
- end: `0x1800247c9`
- name: `?CreatePowerReferenceSubBlocker@CSleepStudyPowerReferenceManager@@QEAAJPEAVCVADServer@@PEAV?$shared_ptr@VCSleepStudyPowerReference@@@std@@@Z`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180023834`

## callees

- `0x18001280c`
- `0x1800237e0`
- `0x180024460`
- `0x1800252b0`
- `0x180025310`
- `0x1800ad0c0`
- `0x1800cd8d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800244b1`
- `ntdll!RtlInitUnicodeString` at `0x1800244b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002453f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002453f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002454e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002454e`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002475b`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024766`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024779`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002478f`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800247a2`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800247b5`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002475b`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024766`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x180024779`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002478f`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800247a2`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x1800247b5`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x1800245d1`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x1800245d1`
- `UMPDC!SleepstudyHelperSetBlockerParentHandle` at `0x180024507`
- `UMPDC!SleepstudyHelperSetBlockerParentHandle` at `0x180024507`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002476e`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180024784`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002479a`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800247aa`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002476e`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180024784`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002479a`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800247aa`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x180024528`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x180024528`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800244f0`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x1800244f0`

## string_xrefs

- `0x18002462a`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x18002465a`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800246aa`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x1800246f1`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`
- `0x180024720`: `avcore\audiocore\server\audiosrv\dll\powerreference.cpp`

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
0x180024460  push    rbx
0x180024462  push    rsi
0x180024463  push    rdi
0x180024464  sub     rsp, 70h
0x180024468  mov     rax, cs:__security_cookie
0x18002446f  xor     rax, rsp
0x180024472  mov     [rsp+88h+var_28], rax
0x180024477  mov     rsi, r8
0x18002447a  mov     rdi, rdx
0x18002447d  mov     rbx, rcx
0x180024480  cmp     qword ptr [rcx+8], 0
0x180024485  jz      loc_180024608
0x18002448b  cmp     qword ptr [rcx], 0
0x18002448f  jz      loc_180024608
0x180024495  xorps   xmm0, xmm0
0x180024498  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18002449d  mov     rcx, [rdx+0B0h]; this
0x1800244a4  call    ?GetClientFriendlyName@CAudioStream@@QEAAPEBGXZ; CAudioStream::GetClientFriendlyName(void)
0x1800244a9  mov     rdx, rax; SourceString
0x1800244ac  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800244b1  call    cs:__imp_RtlInitUnicodeString
0x1800244b7  movups  xmm0, xmmword ptr [rdi+100h]
0x1800244be  movdqu  [rsp+88h+var_38], xmm0
0x1800244c4  mov     [rsp+88h+var_58], 0
0x1800244cd  lea     rdx, [rbx+10h]
0x1800244d1  lea     rax, [rsp+88h+var_58]
0x1800244d6  mov     [rsp+88h+var_60], rax
0x1800244db  mov     [rsp+88h+var_68], 8; int
0x1800244e3  lea     r9, [rsp+88h+DestinationString]
0x1800244e8  lea     r8, [rsp+88h+var_38]
0x1800244ed  mov     rcx, [rbx]
0x1800244f0  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x1800244f6  test    eax, eax
0x1800244f8  js      loc_18002461F
0x1800244fe  mov     rdx, [rbx+8]
0x180024502  mov     rcx, [rsp+88h+var_58]
0x180024507  call    cs:__imp_SleepstudyHelperSetBlockerParentHandle
0x18002450d  test    eax, eax
0x18002450f  js      loc_1800246E6
0x180024515  mov     [rsp+88h+var_50], 0
0x18002451e  lea     rdx, [rsp+88h+var_50]
0x180024523  mov     rcx, [rsp+88h+var_58]
0x180024528  call    cs:__imp_SleepstudyHelperBuildBlocker
0x18002452e  test    eax, eax
0x180024530  js      loc_18002464F
0x180024536  mov     [rsp+88h+var_58], 0
0x18002453f  call    cs:__imp_GetProcessHeap
0x180024545  mov     rcx, rax; hHeap
0x180024548  xor     edx, edx; dwFlags
0x18002454a  lea     r8d, [rdx+18h]; dwBytes
0x18002454e  call    cs:__imp_HeapAlloc
0x180024554  mov     rbx, rax
0x180024557  test    rax, rax
0x18002455a  jz      loc_180024690
0x180024560  mov     dword ptr [rax+8], 1
0x180024567  mov     dword ptr [rax+0Ch], 1
0x18002456e  lea     rax, ??_7?$_Ref_count_obj2@VCSleepStudyPowerReference@@@std@@6B@; const std::_Ref_count_obj2<CSleepStudyPowerReference>::`vftable'
0x180024575  mov     [rbx], rax
0x180024578  mov     qword ptr [rbx+10h], 0
0x180024580  lea     rdi, [rbx+10h]
0x180024584  test    rdi, rdi
0x180024587  jz      loc_18002469A
0x18002458d  lea     rax, [rsp+88h+var_50]
0x180024592  cmp     rdi, rax
0x180024595  jz      short loc_1800245AD
0x180024597  mov     rdx, [rsp+88h+var_50]
0x18002459c  mov     rcx, rdi
0x18002459f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_BLOCKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_BLOCKER *)
0x1800245a4  mov     [rsp+88h+var_50], 0
0x1800245ad  test    rbx, rbx
0x1800245b0  jz      short loc_1800245B6
0x1800245b2  lock inc dword ptr [rbx+8]
0x1800245b6  mov     [rsi], rdi
0x1800245b9  mov     rcx, [rsi+8]; this
0x1800245bd  mov     [rsi+8], rbx
0x1800245c1  test    rcx, rcx
0x1800245c4  jz      short loc_1800245CB
0x1800245c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800245cb  mov     rcx, [rsi]
0x1800245ce  mov     rcx, [rcx]
0x1800245d1  call    cs:__imp_SleepstudyHelperBlockerActiveReference
0x1800245d7  test    eax, eax
0x1800245d9  js      loc_180024715
0x1800245df  test    rbx, rbx
0x1800245e2  jz      short loc_1800245EC
0x1800245e4  mov     rcx, rbx; this
0x1800245e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800245ec  mov     rcx, [rsp+88h+var_50]
0x1800245f1  test    rcx, rcx
0x1800245f4  jnz     loc_1800247AA
0x1800245fa  mov     rcx, [rsp+88h+var_58]
0x1800245ff  test    rcx, rcx
0x180024602  jnz     loc_1800247B5
0x180024608  xor     eax, eax
0x18002460a  mov     rcx, [rsp+88h+var_28]
0x18002460f  xor     rcx, rsp; StackCookie
0x180024612  call    __security_check_cookie
0x180024617  add     rsp, 70h
0x18002461b  pop     rdi
0x18002461c  pop     rsi
0x18002461d  pop     rbx
0x18002461e  retn
0x18002461f  mov     rcx, [rsp+88h]; this
0x180024627  mov     r9d, eax; char *
0x18002462a  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180024631  mov     edx, 0F4h; void *
0x180024636  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002463b  mov     ebx, eax
0x18002463d  mov     rcx, [rsp+88h+var_58]
0x180024642  test    rcx, rcx
0x180024645  jnz     loc_18002475B
0x18002464b  mov     eax, ebx
0x18002464d  jmp     short loc_18002460A
0x18002464f  mov     rcx, [rsp+88h]; this
0x180024657  mov     r9d, eax; char *
0x18002465a  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180024661  mov     edx, 0F9h; void *
0x180024666  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002466b  mov     ebx, eax
0x18002466d  mov     rcx, [rsp+88h+var_50]
0x180024672  test    rcx, rcx
0x180024675  jnz     loc_18002476E
0x18002467b  mov     rcx, [rsp+88h+var_58]
0x180024680  test    rcx, rcx
0x180024683  jnz     loc_180024779
0x180024689  mov     eax, ebx
0x18002468b  jmp     loc_18002460A
0x180024690  xor     ebx, ebx
0x180024692  lea     edi, [rbx+10h]
0x180024695  jmp     loc_18002458D
0x18002469a  mov     rcx, [rsp+88h]; this
0x1800246a2  mov     edi, 8007000Eh
0x1800246a7  mov     r9d, edi; char *
0x1800246aa  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800246b1  mov     edx, 0FFh; void *
0x1800246b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246bb  mov     rcx, rbx; this
0x1800246be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800246c3  mov     rcx, [rsp+88h+var_50]
0x1800246c8  test    rcx, rcx
0x1800246cb  jnz     loc_180024784
0x1800246d1  mov     rcx, [rsp+88h+var_58]
0x1800246d6  test    rcx, rcx
0x1800246d9  jnz     loc_18002478F
0x1800246df  mov     eax, edi
0x1800246e1  jmp     loc_18002460A
0x1800246e6  mov     rcx, [rsp+88h]; this
0x1800246ee  mov     r9d, eax; char *
0x1800246f1  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800246f8  mov     edx, 0F6h; void *
0x1800246fd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024702  mov     ebx, eax
0x180024704  mov     rcx, [rsp+88h+var_58]
0x180024709  test    rcx, rcx
0x18002470c  jnz     short loc_180024766
0x18002470e  mov     eax, ebx
0x180024710  jmp     loc_18002460A
0x180024715  mov     rcx, [rsp+88h]; this
0x18002471d  mov     r9d, eax; char *
0x180024720  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180024727  mov     edx, 103h; void *
0x18002472c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024731  mov     edi, eax
0x180024733  test    rbx, rbx
0x180024736  jz      short loc_180024740
0x180024738  mov     rcx, rbx; this
0x18002473b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180024740  mov     rcx, [rsp+88h+var_50]
0x180024745  test    rcx, rcx
0x180024748  jnz     short loc_18002479A
0x18002474a  mov     rcx, [rsp+88h+var_58]
0x18002474f  test    rcx, rcx
0x180024752  jnz     short loc_1800247A2
0x180024754  mov     eax, edi
0x180024756  jmp     loc_18002460A
0x18002475b  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180024761  jmp     loc_18002464B
0x180024766  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002476c  jmp     short loc_18002470E
0x18002476e  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x180024774  jmp     loc_18002467B
0x180024779  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002477f  jmp     loc_180024689
0x180024784  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x18002478a  jmp     loc_1800246D1
0x18002478f  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x180024795  jmp     loc_1800246DF
0x18002479a  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800247a0  jmp     short loc_18002474A
0x1800247a2  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800247a8  jmp     short loc_180024754
0x1800247aa  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1800247b0  jmp     loc_1800245FA
0x1800247b5  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1800247bb  jmp     loc_180024608
0x1800247c0  mov     eax, dword ptr [rsp+88h+var_58]
0x1800247c4  jmp     loc_18002460A
```
