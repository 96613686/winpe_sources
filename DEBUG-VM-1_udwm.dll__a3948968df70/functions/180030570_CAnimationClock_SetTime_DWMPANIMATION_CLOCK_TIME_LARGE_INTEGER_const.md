# CAnimationClock::_SetTime(DWMPANIMATION_CLOCK_TIME,_LARGE_INTEGER const *)

- ea: `0x180030570`
- end: `0x1800306e2`
- name: `?_SetTime@CAnimationClock@@AEAAJW4DWMPANIMATION_CLOCK_TIME@@PEBT_LARGE_INTEGER@@@Z`
- size: `370`
- prototype: `int __high(enum DWMPANIMATION_CLOCK_TIME, const union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800255e8`
- `0x1800303c4`
- `0x18009d7c0`

## callees

- `0x1800255e8`
- `0x180030570`
- `0x1800306e8`
- `0x180045c20`
- `0x1800688cc`
- `0x18008ea04`
- `0x18009db24`
- `0x18009dbd8`

## import_xrefs

- `win32u!NtDCompositionCommitSynchronizationObject` at `0x180030648`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x180030648`

## pseudocode

```c
int __fastcall CAnimationClock::_SetTime(union _LARGE_INTEGER *a1, int a2, const union _LARGE_INTEGER *a3)
{
  union _LARGE_INTEGER *v6; // r8
  int Frame; // ebx
  __int64 v8; // rcx
  __int64 ElapsedMillsecondsFromTime; // rax
  __int64 v11; // r9
  CAnimationClock *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  union _LARGE_INTEGER v17; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    ElapsedMillsecondsFromTime = CAnimationClock::s_GetElapsedMillsecondsFromTime(a3);
    v11 = -ElapsedMillsecondsFromTime;
    if ( ElapsedMillsecondsFromTime > 0 )
      v11 = ElapsedMillsecondsFromTime;
    if ( v11 > 5000 )
      return -2147024809;
  }
  if ( !a2 )
  {
    if ( ((a1[10].LowPart - 1) & 0xFFFFFFFD) == 0 )
    {
      v17.QuadPart = 0;
      v6 = &v17;
      if ( a3 )
        v6 = a1 + 11;
      Frame = CAnimationClock::_SetTimeToNextFrame((CAnimationClock *)a1, a3, v6);
      if ( Frame >= 0 )
      {
        Frame = CAnimationClock::_SetState(a1, 2);
        if ( !a3 )
          a1[11] = v17;
        if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0ji_EtwEventWriteTransfer)(
            v8,
            &UdwmAnimationClock_Start,
            &a1[15],
            (union _LARGE_INTEGER)a1[11].QuadPart);
      }
      return Frame;
    }
    return -2147019873;
  }
  if ( a2 != 1 )
    return -2147024809;
  if ( a1[10].LowPart - 1 > 3 )
    return -2147019873;
  if ( !(unsigned __int8)wil::operator!=<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(&a1[14]) )
  {
LABEL_22:
    Frame = CAnimationClock::_SetTimeToNextFrame(v12, a3, a1 + 12);
    if ( Frame >= 0 )
    {
      if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0ji_EtwEventWriteTransfer)(
          v14,
          &UdwmAnimationClock_Cancel,
          &a1[15],
          (union _LARGE_INTEGER)a1[12].QuadPart);
      return CAnimationClock::_SetState(a1, 5);
    }
    return Frame;
  }
  v13 = ((__int64 (__fastcall *)(_QWORD))NtDCompositionCommitSynchronizationObject)((union _LARGE_INTEGER)a1[14].QuadPart);
  if ( v13 >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(&a1[14]);
    goto LABEL_22;
  }
  return wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x1E1,
           (unsigned int)"clientcore\\windows\\dwm\\udwm\\animationclock.cpp",
           (const char *)(unsigned int)v13,
           v15);
}

```

## disassembly

```asm
0x180030570  push    rbx
0x180030572  push    rsi
0x180030573  push    rdi
0x180030574  push    r14
0x180030576  sub     rsp, 28h
0x18003057a  mov     rsi, r8
0x18003057d  mov     ebx, edx
0x18003057f  mov     rdi, rcx
0x180030582  test    r8, r8
0x180030585  jnz     short loc_1800305FC
0x180030587  test    ebx, ebx
0x180030589  jnz     loc_180030622
0x18003058f  mov     eax, [rdi+50h]
0x180030592  dec     eax
0x180030594  test    eax, 0FFFFFFFDh
0x180030599  jnz     loc_1800306BF
0x18003059f  mov     qword ptr [rsp+48h+arg_10], 0
0x1800305a8  lea     r8, [rsp+48h+arg_10]; union _LARGE_INTEGER *
0x1800305ad  test    rsi, rsi
0x1800305b0  jnz     short loc_1800305F6
0x1800305b2  mov     rdx, rsi; union _LARGE_INTEGER *
0x1800305b5  call    ?_SetTimeToNextFrame@CAnimationClock@@AEAAJPEBT_LARGE_INTEGER@@PEAT2@@Z; CAnimationClock::_SetTimeToNextFrame(_LARGE_INTEGER const *,_LARGE_INTEGER *)
0x1800305ba  mov     ebx, eax
0x1800305bc  test    eax, eax
0x1800305be  js      short loc_1800305EA
0x1800305c0  mov     edx, 2
0x1800305c5  mov     rcx, rdi
0x1800305c8  call    ?_SetState@CAnimationClock@@AEAAJW4AnimationClockState@@@Z; CAnimationClock::_SetState(AnimationClockState)
0x1800305cd  mov     ebx, eax
0x1800305cf  test    rsi, rsi
0x1800305d2  jnz     short loc_1800305DD
0x1800305d4  mov     rax, qword ptr [rsp+48h+arg_10]
0x1800305d9  mov     [rdi+58h], rax
0x1800305dd  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x1800305e4  jnz     loc_1800306C9
0x1800305ea  mov     eax, ebx
0x1800305ec  add     rsp, 28h
0x1800305f0  pop     r14
0x1800305f2  pop     rdi
0x1800305f3  pop     rsi
0x1800305f4  pop     rbx
0x1800305f5  retn
0x1800305f6  lea     r8, [rdi+58h]
0x1800305fa  jmp     short loc_1800305B2
0x1800305fc  mov     rcx, rsi; union _LARGE_INTEGER *
0x1800305ff  call    ?s_GetElapsedMillsecondsFromTime@CAnimationClock@@CA_JPEBT_LARGE_INTEGER@@@Z; CAnimationClock::s_GetElapsedMillsecondsFromTime(_LARGE_INTEGER const *)
0x180030604  mov     r9, rax
0x180030607  neg     r9
0x18003060a  cmovs   r9, rax
0x18003060e  cmp     r9, 1388h
0x180030615  jle     loc_180030587
0x18003061b  mov     ebx, 80070057h
0x180030620  jmp     short loc_1800305EA
0x180030622  cmp     ebx, 1
0x180030625  jnz     short loc_18003061B
0x180030627  mov     eax, [rdi+50h]
0x18003062a  dec     eax
0x18003062c  cmp     eax, 3
0x18003062f  ja      loc_1800306BF
0x180030635  lea     rbx, [rdi+70h]
0x180030639  mov     rcx, rbx
0x18003063c  call    ??$?9V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@0@$$T@Z; wil::operator!=<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::nullptr_t)
0x180030641  test    al, al
0x180030643  jz      short loc_180030678
0x180030645  mov     rcx, [rbx]
0x180030648  call    cs:__imp_NtDCompositionCommitSynchronizationObject
0x18003064e  test    eax, eax
0x180030650  jns     short loc_180030670
0x180030652  mov     rcx, [rsp+48h]; this
0x180030657  lea     r8, aClientcoreWind_83; "clientcore\\windows\\dwm\\udwm\\animati"...
0x18003065e  mov     r9d, eax; char *
0x180030661  mov     edx, 1E1h; void *
0x180030666  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003066b  jmp     loc_1800305EC
0x180030670  mov     rcx, rbx
0x180030673  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x180030678  lea     r8, [rdi+60h]; union _LARGE_INTEGER *
0x18003067c  mov     rdx, rsi; union _LARGE_INTEGER *
0x18003067f  call    ?_SetTimeToNextFrame@CAnimationClock@@AEAAJPEBT_LARGE_INTEGER@@PEAT2@@Z; CAnimationClock::_SetTimeToNextFrame(_LARGE_INTEGER const *,_LARGE_INTEGER *)
0x180030684  mov     ebx, eax
0x180030686  test    eax, eax
0x180030688  js      loc_1800305EA
0x18003068e  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x180030695  jz      short loc_1800306AB
0x180030697  mov     r9, [rdi+60h]
0x18003069b  lea     r8, [rdi+78h]
0x18003069f  lea     rdx, UdwmAnimationClock_Cancel
0x1800306a6  call    McTemplateU0ji_EtwEventWriteTransfer
0x1800306ab  mov     edx, 5
0x1800306b0  mov     rcx, rdi
0x1800306b3  call    ?_SetState@CAnimationClock@@AEAAJW4AnimationClockState@@@Z; CAnimationClock::_SetState(AnimationClockState)
0x1800306b8  mov     ebx, eax
0x1800306ba  jmp     loc_1800305EA
0x1800306bf  mov     ebx, 8007139Fh
0x1800306c4  jmp     loc_1800305EA
0x1800306c9  mov     r9, [rdi+58h]
0x1800306cd  lea     r8, [rdi+78h]
0x1800306d1  lea     rdx, UdwmAnimationClock_Start
0x1800306d8  call    McTemplateU0ji_EtwEventWriteTransfer
0x1800306dd  jmp     loc_1800305EA
```
