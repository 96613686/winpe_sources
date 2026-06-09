# KsHandleWrapper::Open(void)

- ea: `0x1800267e4`
- end: `0x180026aaf`
- name: `?Open@KsHandleWrapper@@QEAAJXZ`
- size: `715`
- prototype: `__int64 __fastcall(KsHandleWrapper *__hidden this)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800124c8`
- `0x18001b7a0`
- `0x180026ac0`
- `0x180028020`
- `0x180028300`
- `0x180028bc8`
- `0x180029038`

## callees

- `0x18000a814`
- `0x18001fe98`
- `0x1800267e4`
- `0x180026b64`
- `0x1800271f4`
- `0x1800272a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026a9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800267f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800267f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002694d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002694d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002693a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002693a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002687e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002687e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a67`

## string_xrefs

- `0x18002683b`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x1800268f5`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x1800269ba`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x1800269fb`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`
- `0x180026a82`: `avcore\midi2\libs\midikscommon\kshandlewrapper.cpp`

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
0x1800267e4  push    rbp
0x1800267e6  push    rbx
0x1800267e7  push    rsi
0x1800267e8  push    rdi
0x1800267e9  push    r14
0x1800267eb  push    r15
0x1800267ed  mov     rbp, rsp
0x1800267f0  sub     rsp, 48h
0x1800267f4  mov     rdi, rcx
0x1800267f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800267fd  mov     [rbp+arg_0], rdi
0x180026801  mov     eax, [rdi+0C0h]
0x180026807  test    eax, eax
0x180026809  jnz     loc_18002689F
0x18002680f  mov     [rbp+var_20], 0
0x180026817  lea     rcx, [rdi+10h]
0x18002681b  cmp     qword ptr [rcx+18h], 7
0x180026820  jbe     short loc_180026825
0x180026822  mov     rcx, [rcx]; unsigned __int16 *
0x180026825  lea     rdx, [rbp+var_20]; void **
0x180026829  call    ?FilterInstantiate@@YAJPEBGPEAPEAX@Z; FilterInstantiate(ushort const *,void * *)
0x18002682e  mov     ebx, eax
0x180026830  test    eax, eax
0x180026832  jns     short loc_180026855
0x180026834  mov     rcx, [rbp+30h]; this
0x180026838  mov     r9d, eax; char *
0x18002683b  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x180026842  mov     edx, 52h ; 'R'; void *
0x180026847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002684c  mov     rcx, [rbp+var_20]
0x180026850  jmp     loc_180026A11
0x180026855  lea     rsi, [rdi+8]
0x180026859  lea     rax, [rbp+var_20]
0x18002685d  cmp     rsi, rax
0x180026860  jz      short loc_180026896
0x180026862  mov     r15, [rbp+var_20]
0x180026866  mov     r14, [rsi]
0x180026869  lea     rax, [r14-1]
0x18002686d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026871  ja      short loc_18002688C
0x180026873  call    cs:__imp_GetLastError
0x180026879  mov     ebx, eax
0x18002687b  mov     rcx, r14; hObject
0x18002687e  call    cs:__imp_CloseHandle
0x180026884  mov     ecx, ebx; dwErrCode
0x180026886  call    cs:__imp_SetLastError
0x18002688c  mov     [rsi], r15
0x18002688f  xor     ecx, ecx
0x180026891  jmp     loc_180026A5D
0x180026896  mov     rcx, [rbp+var_20]
0x18002689a  jmp     loc_180026A5D
0x18002689f  cmp     eax, 1
0x1800268a2  jnz     loc_180026A6D
0x1800268a8  mov     [rbp+var_28], 0
0x1800268b0  lea     rsi, [rdi+0D0h]
0x1800268b7  mov     rax, [rsi]
0x1800268ba  inc     rax
0x1800268bd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800268c3  jnz     loc_18002696E
0x1800268c9  mov     [rbp+hObject], 0
0x1800268d1  lea     rcx, [rdi+10h]
0x1800268d5  cmp     qword ptr [rcx+18h], 7
0x1800268da  jbe     short loc_1800268DF
0x1800268dc  mov     rcx, [rcx]; unsigned __int16 *
0x1800268df  lea     rdx, [rbp+hObject]; void **
0x1800268e3  call    ?FilterInstantiate@@YAJPEBGPEAPEAX@Z; FilterInstantiate(ushort const *,void * *)
0x1800268e8  mov     ebx, eax
0x1800268ea  test    eax, eax
0x1800268ec  jns     short loc_180026920
0x1800268ee  mov     rcx, [rbp+30h]; this
0x1800268f2  mov     r9d, eax; char *
0x1800268f5  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x1800268fc  mov     edx, 5Fh ; '_'; void *
0x180026901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026906  mov     rcx, [rbp+hObject]; hObject
0x18002690a  lea     rdx, [rcx-1]
0x18002690e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026912  ja      short loc_18002691B
0x180026914  call    cs:__imp_CloseHandle
0x18002691a  nop
0x18002691b  jmp     loc_180026A97
0x180026920  lea     rax, [rbp+hObject]
0x180026924  cmp     rsi, rax
0x180026927  jz      short loc_18002695A
0x180026929  mov     r15, [rbp+hObject]
0x18002692d  mov     r14, [rsi]
0x180026930  lea     rax, [r14-1]
0x180026934  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026938  ja      short loc_180026953
0x18002693a  call    cs:__imp_GetLastError
0x180026940  mov     ebx, eax
0x180026942  mov     rcx, r14; hObject
0x180026945  call    cs:__imp_CloseHandle
0x18002694b  mov     ecx, ebx; dwErrCode
0x18002694d  call    cs:__imp_SetLastError
0x180026953  mov     [rsi], r15
0x180026956  xor     ecx, ecx
0x180026958  jmp     short loc_18002695E
0x18002695a  mov     rcx, [rbp+hObject]; hObject
0x18002695e  lea     rax, [rcx-1]
0x180026962  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026966  ja      short loc_18002696E
0x180026968  call    cs:__imp_CloseHandle
0x18002696e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180026975  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18002697a  mov     [rbp+var_28], 0
0x180026982  lea     r9, [rbp+var_28]
0x180026986  mov     r8d, [rdi+0C8h]
0x18002698d  mov     edx, [rdi+0C4h]
0x180026993  mov     rcx, [rsi]
0x180026996  test    al, al
0x180026998  jz      short loc_1800269E9
0x18002699a  call    ?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z; InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)
0x18002699f  mov     ebx, eax
0x1800269a1  test    eax, eax
0x1800269a3  jns     short loc_180026A1B
0x1800269a5  cmp     eax, 80070491h
0x1800269aa  jz      short loc_1800269CC
0x1800269ac  cmp     eax, 8007001Fh
0x1800269b1  jz      short loc_1800269CC
0x1800269b3  mov     rcx, [rbp+30h]; this
0x1800269b7  mov     r9d, eax; char *
0x1800269ba  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x1800269c1  mov     edx, 68h ; 'h'; void *
0x1800269c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269cb  nop
0x1800269cc  mov     rcx, [rbp+var_28]; hObject
0x1800269d0  lea     rax, [rcx-1]
0x1800269d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800269d8  ja      loc_180026A97
0x1800269de  call    cs:__imp_CloseHandle
0x1800269e4  jmp     loc_180026A97
0x1800269e9  call    ?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z; InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)
0x1800269ee  mov     ebx, eax
0x1800269f0  test    eax, eax
0x1800269f2  jns     short loc_180026A1B
0x1800269f4  mov     rcx, [rbp+30h]; this
0x1800269f8  mov     r9d, eax; char *
0x1800269fb  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x180026a02  mov     edx, 6Ch ; 'l'; void *
0x180026a07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a0c  nop
0x180026a0d  mov     rcx, [rbp+var_28]
0x180026a11  lea     rdx, [rcx-1]
0x180026a15  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026a19  jmp     short loc_1800269D8
0x180026a1b  lea     rsi, [rdi+8]
0x180026a1f  lea     rax, [rbp+var_28]
0x180026a23  cmp     rsi, rax
0x180026a26  jz      short loc_180026A59
0x180026a28  mov     r15, [rbp+var_28]
0x180026a2c  mov     r14, [rsi]
0x180026a2f  lea     rax, [r14-1]
0x180026a33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026a37  ja      short loc_180026A52
0x180026a39  call    cs:__imp_GetLastError
0x180026a3f  mov     ebx, eax
0x180026a41  mov     rcx, r14; hObject
0x180026a44  call    cs:__imp_CloseHandle
0x180026a4a  mov     ecx, ebx; dwErrCode
0x180026a4c  call    cs:__imp_SetLastError
0x180026a52  mov     [rsi], r15
0x180026a55  xor     ecx, ecx
0x180026a57  jmp     short loc_180026A5D
0x180026a59  mov     rcx, [rbp+var_28]; hObject
0x180026a5d  lea     rax, [rcx-1]
0x180026a61  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026a65  ja      short loc_180026A6D
0x180026a67  call    cs:__imp_CloseHandle
0x180026a6d  mov     rcx, rdi; this
0x180026a70  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x180026a75  mov     ebx, eax
0x180026a77  test    eax, eax
0x180026a79  jns     short loc_180026A95
0x180026a7b  mov     rcx, [rbp+30h]; this
0x180026a7f  mov     r9d, eax; char *
0x180026a82  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midikscommon\\ksha"...
0x180026a89  mov     edx, 71h ; 'q'; void *
0x180026a8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a93  jmp     short loc_180026A97
0x180026a95  xor     ebx, ebx
0x180026a97  mov     rcx, rdi; SRWLock
0x180026a9a  call    cs:__imp_ReleaseSRWLockExclusive
0x180026aa0  mov     eax, ebx
0x180026aa2  add     rsp, 48h
0x180026aa6  pop     r15
0x180026aa8  pop     r14
0x180026aaa  pop     rdi
0x180026aab  pop     rsi
0x180026aac  pop     rbx
0x180026aad  pop     rbp
0x180026aae  retn
```
