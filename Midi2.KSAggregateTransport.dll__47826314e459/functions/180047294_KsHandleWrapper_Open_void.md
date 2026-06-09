# KsHandleWrapper::Open(void)

- ea: `0x180047294`
- end: `0x18004755f`
- name: `?Open@KsHandleWrapper@@QEAAJXZ`
- size: `715`
- prototype: `__int64 __fastcall(KsHandleWrapper *__hidden this)`
- caller_count: `9`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800163a8`
- `0x180025ca0`
- `0x18003b408`
- `0x18003c890`
- `0x180047570`
- `0x180048b80`
- `0x180048e60`
- `0x180049708`
- `0x180049b78`

## callees

- `0x18000b394`
- `0x1800106c8`
- `0x180047294`
- `0x180047614`
- `0x180047c74`
- `0x180047d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004754a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004754a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800472a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800472a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047336`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800473fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800474fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047336`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800473fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800474fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800474e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800474e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004732e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004748e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004732e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004748e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047517`

## string_xrefs

- `0x1800472eb`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x1800473a5`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x18004746a`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x1800474ab`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x180047532`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KsHandleWrapper::Open(RTL_SRWLOCK *this)
{
  int Ptr; // eax
  const unsigned __int16 *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  char *v6; // rcx
  void **p_Ptr; // rsi
  void *v8; // r15
  void *v9; // r14
  DWORD LastError; // ebx
  char *v11; // rcx
  HANDLE *v12; // rsi
  const unsigned __int16 *v13; // rcx
  int v14; // eax
  HANDLE v15; // r15
  HANDLE v16; // r14
  DWORD v17; // ebx
  char *v18; // rcx
  char IsEnabled; // al
  int v20; // r8d
  ULONG Ptr_high; // edx
  HANDLE v22; // rcx
  int v23; // eax
  bool v24; // cc
  int v25; // eax
  void **v26; // rsi
  HANDLE v27; // r15
  void *v28; // r14
  DWORD v29; // ebx
  int v30; // eax
  HANDLE v32; // [rsp+20h] [rbp-28h] BYREF
  void *v33; // [rsp+28h] [rbp-20h] BYREF
  HANDLE hObject[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  AcquireSRWLockExclusive(this);
  Ptr = (int)this[24].Ptr;
  if ( !Ptr )
  {
    v33 = 0;
    v3 = (const unsigned __int16 *)&this[2];
    if ( this[5].Ptr > (PVOID)7 )
      v3 = *(const unsigned __int16 **)v3;
    v4 = FilterInstantiate(v3, &v33);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\kshandlewrapper.cpp",
        (const char *)(unsigned int)v4,
        (int)v32);
      v6 = (char *)v33;
LABEL_36:
      v24 = (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_32:
      if ( v24 )
        CloseHandle(v6);
      goto LABEL_47;
    }
    p_Ptr = &this[1].Ptr;
    if ( &this[1] == (RTL_SRWLOCK *)&v33 )
    {
      v11 = (char *)v33;
    }
    else
    {
      v8 = v33;
      v9 = *p_Ptr;
      if ( (char *)*p_Ptr - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v9);
        SetLastError(LastError);
      }
      *p_Ptr = v8;
      v11 = 0;
    }
LABEL_42:
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v11);
    goto LABEL_44;
  }
  if ( Ptr != 1 )
  {
LABEL_44:
    v30 = KsHandleWrapper::RegisterForNotifications((KsHandleWrapper *)this);
    v5 = v30;
    if ( v30 >= 0 )
      v5 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\kshandlewrapper.cpp",
        (const char *)(unsigned int)v30,
        (int)v32);
    goto LABEL_47;
  }
  v32 = 0;
  v12 = &this[26].Ptr;
  if ( (((unsigned __int64)this[26].Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_26:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl);
    v32 = 0;
    v20 = (int)this[25].Ptr;
    Ptr_high = HIDWORD(this[24].Ptr);
    v22 = *v12;
    if ( IsEnabled )
    {
      v23 = InstantiateMidiPin(v22, Ptr_high, v20, &v32);
      v5 = v23;
      if ( v23 < 0 )
      {
        if ( v23 != -2147023727 && v23 != -2147024865 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"avcore\\midi2\\libs\\midikscommon\\kshandlewrapper.cpp",
            (const char *)(unsigned int)v23,
            (int)v32);
        v6 = (char *)v32;
        v24 = (char *)v32 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
        goto LABEL_32;
      }
    }
    else
    {
      v25 = InstantiateMidiPin(v22, Ptr_high, v20, &v32);
      v5 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"avcore\\midi2\\libs\\midikscommon\\kshandlewrapper.cpp",
          (const char *)(unsigned int)v25,
          (int)v32);
        v6 = (char *)v32;
        goto LABEL_36;
      }
    }
    v26 = &this[1].Ptr;
    if ( &this[1] == (RTL_SRWLOCK *)&v32 )
    {
      v11 = (char *)v32;
    }
    else
    {
      v27 = v32;
      v28 = *v26;
      if ( (char *)*v26 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v29 = GetLastError();
        CloseHandle(v28);
        SetLastError(v29);
      }
      *v26 = v27;
      v11 = 0;
    }
    goto LABEL_42;
  }
  hObject[0] = 0;
  v13 = (const unsigned __int16 *)&this[2];
  if ( this[5].Ptr > (PVOID)7 )
    v13 = *(const unsigned __int16 **)v13;
  v14 = FilterInstantiate(v13, hObject);
  v5 = v14;
  if ( v14 >= 0 )
  {
    if ( v12 == hObject )
    {
      v18 = (char *)hObject[0];
    }
    else
    {
      v15 = hObject[0];
      v16 = *v12;
      if ( (char *)*v12 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v17 = GetLastError();
        CloseHandle(v16);
        SetLastError(v17);
      }
      *v12 = v15;
      v18 = 0;
    }
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v18);
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5F,
    (unsigned int)"avcore\\midi2\\libs\\midikscommon\\kshandlewrapper.cpp",
    (const char *)(unsigned int)v14,
    (int)v32);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
LABEL_47:
  ReleaseSRWLockExclusive(this);
  return v5;
}

```

## disassembly

```asm
0x180047294  push    rbp
0x180047296  push    rbx
0x180047297  push    rsi
0x180047298  push    rdi
0x180047299  push    r14
0x18004729b  push    r15
0x18004729d  mov     rbp, rsp
0x1800472a0  sub     rsp, 48h
0x1800472a4  mov     rdi, rcx
0x1800472a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800472ad  mov     [rbp+arg_0], rdi
0x1800472b1  mov     eax, [rdi+0C0h]
0x1800472b7  test    eax, eax
0x1800472b9  jnz     loc_18004734F
0x1800472bf  mov     [rbp+var_20], 0
0x1800472c7  lea     rcx, [rdi+10h]
0x1800472cb  cmp     qword ptr [rcx+18h], 7
0x1800472d0  jbe     short loc_1800472D5
0x1800472d2  mov     rcx, [rcx]; unsigned __int16 *
0x1800472d5  lea     rdx, [rbp+var_20]; void **
0x1800472d9  call    ?FilterInstantiate@@YAJPEBGPEAPEAX@Z; FilterInstantiate(ushort const *,void * *)
0x1800472de  mov     ebx, eax
0x1800472e0  test    eax, eax
0x1800472e2  jns     short loc_180047305
0x1800472e4  mov     rcx, [rbp+30h]; this
0x1800472e8  mov     r9d, eax; char *
0x1800472eb  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x1800472f2  mov     edx, 52h ; 'R'; void *
0x1800472f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800472fc  mov     rcx, [rbp+var_20]
0x180047300  jmp     loc_1800474C1
0x180047305  lea     rsi, [rdi+8]
0x180047309  lea     rax, [rbp+var_20]
0x18004730d  cmp     rsi, rax
0x180047310  jz      short loc_180047346
0x180047312  mov     r15, [rbp+var_20]
0x180047316  mov     r14, [rsi]
0x180047319  lea     rax, [r14-1]
0x18004731d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047321  ja      short loc_18004733C
0x180047323  call    cs:__imp_GetLastError
0x180047329  mov     ebx, eax
0x18004732b  mov     rcx, r14; hObject
0x18004732e  call    cs:__imp_CloseHandle
0x180047334  mov     ecx, ebx; dwErrCode
0x180047336  call    cs:__imp_SetLastError
0x18004733c  mov     [rsi], r15
0x18004733f  xor     ecx, ecx
0x180047341  jmp     loc_18004750D
0x180047346  mov     rcx, [rbp+var_20]
0x18004734a  jmp     loc_18004750D
0x18004734f  cmp     eax, 1
0x180047352  jnz     loc_18004751D
0x180047358  mov     [rbp+var_28], 0
0x180047360  lea     rsi, [rdi+0D0h]
0x180047367  mov     rax, [rsi]
0x18004736a  inc     rax
0x18004736d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180047373  jnz     loc_18004741E
0x180047379  mov     [rbp+hObject], 0
0x180047381  lea     rcx, [rdi+10h]
0x180047385  cmp     qword ptr [rcx+18h], 7
0x18004738a  jbe     short loc_18004738F
0x18004738c  mov     rcx, [rcx]; unsigned __int16 *
0x18004738f  lea     rdx, [rbp+hObject]; void **
0x180047393  call    ?FilterInstantiate@@YAJPEBGPEAPEAX@Z; FilterInstantiate(ushort const *,void * *)
0x180047398  mov     ebx, eax
0x18004739a  test    eax, eax
0x18004739c  jns     short loc_1800473D0
0x18004739e  mov     rcx, [rbp+30h]; this
0x1800473a2  mov     r9d, eax; char *
0x1800473a5  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x1800473ac  mov     edx, 5Fh ; '_'; void *
0x1800473b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800473b6  mov     rcx, [rbp+hObject]; hObject
0x1800473ba  lea     rdx, [rcx-1]
0x1800473be  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800473c2  ja      short loc_1800473CB
0x1800473c4  call    cs:__imp_CloseHandle
0x1800473ca  nop
0x1800473cb  jmp     loc_180047547
0x1800473d0  lea     rax, [rbp+hObject]
0x1800473d4  cmp     rsi, rax
0x1800473d7  jz      short loc_18004740A
0x1800473d9  mov     r15, [rbp+hObject]
0x1800473dd  mov     r14, [rsi]
0x1800473e0  lea     rax, [r14-1]
0x1800473e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800473e8  ja      short loc_180047403
0x1800473ea  call    cs:__imp_GetLastError
0x1800473f0  mov     ebx, eax
0x1800473f2  mov     rcx, r14; hObject
0x1800473f5  call    cs:__imp_CloseHandle
0x1800473fb  mov     ecx, ebx; dwErrCode
0x1800473fd  call    cs:__imp_SetLastError
0x180047403  mov     [rsi], r15
0x180047406  xor     ecx, ecx
0x180047408  jmp     short loc_18004740E
0x18004740a  mov     rcx, [rbp+hObject]; hObject
0x18004740e  lea     rax, [rcx-1]
0x180047412  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047416  ja      short loc_18004741E
0x180047418  call    cs:__imp_CloseHandle
0x18004741e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180047425  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18004742a  mov     [rbp+var_28], 0
0x180047432  lea     r9, [rbp+var_28]
0x180047436  mov     r8d, [rdi+0C8h]
0x18004743d  mov     edx, [rdi+0C4h]
0x180047443  mov     rcx, [rsi]
0x180047446  test    al, al
0x180047448  jz      short loc_180047499
0x18004744a  call    ?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z; InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)
0x18004744f  mov     ebx, eax
0x180047451  test    eax, eax
0x180047453  jns     short loc_1800474CB
0x180047455  cmp     eax, 80070491h
0x18004745a  jz      short loc_18004747C
0x18004745c  cmp     eax, 8007001Fh
0x180047461  jz      short loc_18004747C
0x180047463  mov     rcx, [rbp+30h]; this
0x180047467  mov     r9d, eax; char *
0x18004746a  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x180047471  mov     edx, 68h ; 'h'; void *
0x180047476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004747b  nop
0x18004747c  mov     rcx, [rbp+var_28]; hObject
0x180047480  lea     rax, [rcx-1]
0x180047484  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047488  ja      loc_180047547
0x18004748e  call    cs:__imp_CloseHandle
0x180047494  jmp     loc_180047547
0x180047499  call    ?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z; InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)
0x18004749e  mov     ebx, eax
0x1800474a0  test    eax, eax
0x1800474a2  jns     short loc_1800474CB
0x1800474a4  mov     rcx, [rbp+30h]; this
0x1800474a8  mov     r9d, eax; char *
0x1800474ab  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x1800474b2  mov     edx, 6Ch ; 'l'; void *
0x1800474b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800474bc  nop
0x1800474bd  mov     rcx, [rbp+var_28]
0x1800474c1  lea     rdx, [rcx-1]
0x1800474c5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800474c9  jmp     short loc_180047488
0x1800474cb  lea     rsi, [rdi+8]
0x1800474cf  lea     rax, [rbp+var_28]
0x1800474d3  cmp     rsi, rax
0x1800474d6  jz      short loc_180047509
0x1800474d8  mov     r15, [rbp+var_28]
0x1800474dc  mov     r14, [rsi]
0x1800474df  lea     rax, [r14-1]
0x1800474e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800474e7  ja      short loc_180047502
0x1800474e9  call    cs:__imp_GetLastError
0x1800474ef  mov     ebx, eax
0x1800474f1  mov     rcx, r14; hObject
0x1800474f4  call    cs:__imp_CloseHandle
0x1800474fa  mov     ecx, ebx; dwErrCode
0x1800474fc  call    cs:__imp_SetLastError
0x180047502  mov     [rsi], r15
0x180047505  xor     ecx, ecx
0x180047507  jmp     short loc_18004750D
0x180047509  mov     rcx, [rbp+var_28]; hObject
0x18004750d  lea     rax, [rcx-1]
0x180047511  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047515  ja      short loc_18004751D
0x180047517  call    cs:__imp_CloseHandle
0x18004751d  mov     rcx, rdi; this
0x180047520  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x180047525  mov     ebx, eax
0x180047527  test    eax, eax
0x180047529  jns     short loc_180047545
0x18004752b  mov     rcx, [rbp+30h]; this
0x18004752f  mov     r9d, eax; char *
0x180047532  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x180047539  mov     edx, 71h ; 'q'; void *
0x18004753e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047543  jmp     short loc_180047547
0x180047545  xor     ebx, ebx
0x180047547  mov     rcx, rdi; SRWLock
0x18004754a  call    cs:__imp_ReleaseSRWLockExclusive
0x180047550  mov     eax, ebx
0x180047552  add     rsp, 48h
0x180047556  pop     r15
0x180047558  pop     r14
0x18004755a  pop     rdi
0x18004755b  pop     rsi
0x18004755c  pop     rbx
0x18004755d  pop     rbp
0x18004755e  retn
```
