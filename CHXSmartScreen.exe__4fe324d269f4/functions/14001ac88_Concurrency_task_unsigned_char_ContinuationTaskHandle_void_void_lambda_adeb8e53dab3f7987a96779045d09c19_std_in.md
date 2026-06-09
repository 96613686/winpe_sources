# Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_Continue

- ea: `0x14001ac88`
- end: `0x14001afb7`
- name: `Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_Continue`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14001676c`

## callees

- `0x1400016e8`
- `0x140001710`
- `0x1400017a0`
- `0x140012fdc`
- `0x14001471c`
- `0x14001ac88`
- `0x14001cda8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001af3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001af3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001af26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001af35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001af26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001af35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001af15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001af15`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_Continue(
        _QWORD *a1)
{
  __int64 *v2; // rax
  volatile signed __int32 *v3; // r14
  __int64 v4; // r15
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 (__fastcall **v7)(); // rax
  __int64 v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  _BYTE *v13; // rdx
  _QWORD *v14; // rdx
  char v15; // si
  volatile signed __int32 *v16; // rbx
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  _BYTE *v18; // rcx
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  __int128 v21; // [rsp+28h] [rbp-71h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  volatile signed __int32 *v23; // [rsp+40h] [rbp-59h]
  _QWORD *v24; // [rsp+48h] [rbp-51h]
  __int64 *v25; // [rsp+50h] [rbp-49h]
  _QWORD v26[3]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD *v27; // [rsp+70h] [rbp-29h]
  _BYTE v28[24]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE *v29; // [rsp+90h] [rbp-9h]
  _BYTE *v30; // [rsp+98h] [rbp-1h]
  _BYTE v31[24]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE *v32; // [rsp+B8h] [rbp+1Fh]
  char v33; // [rsp+C0h] [rbp+27h] BYREF

  v21 = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::_Resetp<Concurrency::details::_Task_impl<unsigned char>>(&v21);
  v2 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
         &v22,
         a1 + 8);
  v3 = (volatile signed __int32 *)v2[1];
  v2[1] = *((_QWORD *)&v21 + 1);
  *((_QWORD *)&v21 + 1) = v3;
  v4 = *v2;
  *v2 = v21;
  *(_QWORD *)&v21 = v4;
  v5 = v23;
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = a1[6];
  v24 = v26;
  v27 = 0;
  v7 = off_140049248;
  v26[0] = off_140049248;
  v8 = a1[10];
  if ( v8 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(a1[10]);
    v7 = (__int64 (__fastcall **)())v26[0];
  }
  v26[1] = v8;
  v27 = v26;
  v24 = v26;
  v30 = v28;
  v29 = 0;
  v29 = (_BYTE *)((__int64 (__fastcall *)(_QWORD *, _BYTE *))*v7)(v26, v28);
  v32 = 0;
  v9 = operator new(0x30u);
  v10 = v9;
  if ( !v9 )
    std::_Xbad_alloc();
  v30 = v9;
  *v9 = &std::_Func_impl<std::_Callable_obj<_lambda_ce564f7947f0b9d2442134a983f8f3c7_,0>,std::allocator<std::_Func_class<unsigned char,Concurrency::task<void>,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,unsigned char,Concurrency::task<void>,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  v25 = v9 + 1;
  v9[4] = 0;
  if ( v29 )
  {
    if ( v29 == v28 )
      v12 = v9 + 1;
    else
      v12 = 0;
    v11 = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v29)(v29, v12);
  }
  else
  {
    v11 = 0;
  }
  v10[4] = v11;
  v32 = v10;
  if ( v29 )
  {
    v13 = v28;
    LOBYTE(v13) = v29 != v28;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v29 + 32LL))(v29, v13);
    v29 = 0;
  }
  if ( v27 )
  {
    v14 = v26;
    LOBYTE(v14) = v27 != v26;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v27 + 32LL))(v27, v14);
    v27 = 0;
  }
  v23 = v3;
  v22 = v4;
  v21 = 0u;
  v25 = &v22;
  if ( !v32 )
    std::_Xbad_function_call();
  v15 = (*(__int64 (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v32 + 16LL))(v32, &v22);
  v16 = v23;
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  *(_BYTE *)(v6 + 160) = v15;
  if ( (char *)(v6 + 176) != &v33 )
    *(_QWORD *)(v6 + 176) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 40));
  v17 = (struct _RTL_CRITICAL_SECTION *)(v6 + 40);
  if ( *(_DWORD *)(v6 + 16) == 4 )
  {
    LeaveCriticalSection(v17);
  }
  else
  {
    *(_DWORD *)(v6 + 16) = 3;
    LeaveCriticalSection(v17);
    SetEvent(*(HANDLE *)(v6 + 8));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v6);
  }
  v18 = v32;
  if ( v32 )
  {
    v19 = v31;
    LOBYTE(v19) = v32 != v31;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v32 + 32LL))(v32, v19);
    v18 = 0;
    v32 = 0;
  }
  if ( v18 )
  {
    v20 = v31;
    LOBYTE(v20) = v18 != v31;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v18 + 32LL))(v18, v20);
  }
}

```

## disassembly

```asm
0x14001ac88  mov     [rsp-8+arg_8], rbx
0x14001ac8d  mov     [rsp-8+arg_10], rsi
0x14001ac92  push    rbp
0x14001ac93  push    rdi
0x14001ac94  push    r13
0x14001ac96  push    r14
0x14001ac98  push    r15
0x14001ac9a  lea     rbp, [rsp-37h]
0x14001ac9f  sub     rsp, 0D0h
0x14001aca6  mov     rsi, rcx
0x14001aca9  mov     [rbp+57h+var_D0], 0
0x14001acb0  xorps   xmm0, xmm0
0x14001acb3  movdqu  [rbp+57h+var_C8], xmm0
0x14001acb8  lea     rcx, [rbp+57h+var_C8]
0x14001acbc  call    ??$_Resetp@U?$_Task_impl@E@details@Concurrency@@@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@AEAAXPEAU?$_Task_impl@E@details@Concurrency@@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::_Resetp<Concurrency::details::_Task_impl<uchar>>(Concurrency::details::_Task_impl<uchar> *)
0x14001acc1  nop
0x14001acc2  lea     rdx, [rsi+40h]
0x14001acc6  lea     rcx, [rbp+57h+var_B8]
0x14001acca  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x14001accf  mov     r14, [rax+8]
0x14001acd3  mov     rcx, qword ptr [rbp+57h+var_C8+8]
0x14001acd7  mov     [rax+8], rcx
0x14001acdb  mov     qword ptr [rbp+57h+var_C8+8], r14
0x14001acdf  mov     r15, [rax]
0x14001ace2  mov     rcx, qword ptr [rbp+57h+var_C8]
0x14001ace6  mov     [rax], rcx
0x14001ace9  mov     qword ptr [rbp+57h+var_C8], r15
0x14001aced  or      r13d, 0FFFFFFFFh
0x14001acf1  mov     rbx, [rbp+57h+var_B0]
0x14001acf5  test    rbx, rbx
0x14001acf8  jz      short loc_14001AD32
0x14001acfa  mov     eax, r13d
0x14001acfd  lock xadd [rbx+8], eax
0x14001ad02  add     eax, r13d
0x14001ad05  jnz     short loc_14001AD32
0x14001ad07  mov     rax, [rbx]
0x14001ad0a  mov     rcx, rbx
0x14001ad0d  mov     rax, [rax]
0x14001ad10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ad15  mov     eax, r13d
0x14001ad18  lock xadd [rbx+0Ch], eax
0x14001ad1d  add     eax, r13d
0x14001ad20  jnz     short loc_14001AD32
0x14001ad22  mov     rax, [rbx]
0x14001ad25  mov     rcx, rbx
0x14001ad28  mov     rax, [rax+8]
0x14001ad2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ad31  nop
0x14001ad32  mov     rdi, [rsi+30h]
0x14001ad36  lea     rax, [rbp+57h+var_98]
0x14001ad3a  mov     [rbp+57h+var_A8], rax
0x14001ad3e  mov     [rbp+57h+var_80], 0
0x14001ad46  lea     rax, off_140049248
0x14001ad4d  mov     [rbp+57h+var_98], rax
0x14001ad51  mov     rbx, [rsi+50h]
0x14001ad55  test    rbx, rbx
0x14001ad58  jz      short loc_14001AD6D
0x14001ad5a  mov     rax, [rbx]
0x14001ad5d  mov     rcx, rbx
0x14001ad60  mov     rax, [rax+8]
0x14001ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ad69  mov     rax, [rbp+57h+var_98]
0x14001ad6d  mov     [rbp+57h+var_90], rbx
0x14001ad71  lea     rcx, [rbp+57h+var_98]
0x14001ad75  mov     [rbp+57h+var_80], rcx
0x14001ad79  lea     rcx, [rbp+57h+var_98]
0x14001ad7d  mov     [rbp+57h+var_A8], rcx
0x14001ad81  lea     rcx, [rbp+57h+var_78]
0x14001ad85  mov     [rbp+57h+var_58], rcx
0x14001ad89  mov     [rbp+57h+var_60], 0
0x14001ad91  lea     rdx, [rbp+57h+var_78]
0x14001ad95  lea     rcx, [rbp+57h+var_98]
0x14001ad99  mov     rax, [rax]
0x14001ad9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ada1  nop
0x14001ada2  mov     [rbp+57h+var_60], rax
0x14001ada6  mov     [rbp+57h+var_38], 0
0x14001adae  mov     ecx, 30h ; '0'; Size
0x14001adb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001adb8  mov     rbx, rax
0x14001adbb  test    rax, rax
0x14001adbe  jz      loc_14001AFB1
0x14001adc4  mov     [rbp+57h+var_58], rax
0x14001adc8  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_ce564f7947f0b9d2442134a983f8f3c7_@@$0A@@std@@V?$allocator@V?$_Func_class@EV?$task@X@Concurrency@@U_Nil@std@@U34@U34@U34@U34@U34@@std@@@2@EV?$task@X@Concurrency@@U_Nil@2@U62@U62@U62@U62@U62@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_ce564f7947f0b9d2442134a983f8f3c7_,0>,std::allocator<std::_Func_class<uchar,Concurrency::task<void>,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,uchar,Concurrency::task<void>,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14001adcf  mov     [rbx], rax
0x14001add2  lea     rsi, [rbx+8]
0x14001add6  mov     [rbp+57h+var_A0], rsi
0x14001adda  mov     qword ptr [rsi+18h], 0
0x14001ade2  mov     rcx, [rbp+57h+var_60]
0x14001ade6  test    rcx, rcx
0x14001ade9  jnz     short loc_14001ADEF
0x14001adeb  xor     eax, eax
0x14001aded  jmp     short loc_14001AE0B
0x14001adef  mov     rax, [rcx]
0x14001adf2  mov     rax, [rax]
0x14001adf5  lea     rdx, [rbp+57h+var_78]
0x14001adf9  cmp     rcx, rdx
0x14001adfc  jnz     short loc_14001AE03
0x14001adfe  mov     rdx, rsi
0x14001ae01  jmp     short loc_14001AE05
0x14001ae03  xor     edx, edx
0x14001ae05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae0a  nop
0x14001ae0b  mov     [rsi+18h], rax
0x14001ae0f  mov     [rbp+57h+var_38], rbx
0x14001ae13  mov     [rbp+57h+var_D0], 2
0x14001ae1a  mov     rcx, [rbp+57h+var_60]
0x14001ae1e  test    rcx, rcx
0x14001ae21  jz      short loc_14001AE41
0x14001ae23  mov     rax, [rcx]
0x14001ae26  lea     rdx, [rbp+57h+var_78]
0x14001ae2a  cmp     rcx, rdx
0x14001ae2d  setnz   dl
0x14001ae30  mov     rax, [rax+20h]
0x14001ae34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae39  mov     [rbp+57h+var_60], 0
0x14001ae41  mov     [rbp+57h+var_D0], 1
0x14001ae48  mov     rcx, [rbp+57h+var_80]
0x14001ae4c  test    rcx, rcx
0x14001ae4f  jz      short loc_14001AE6F
0x14001ae51  mov     rax, [rcx]
0x14001ae54  lea     rdx, [rbp+57h+var_98]
0x14001ae58  cmp     rcx, rdx
0x14001ae5b  setnz   dl
0x14001ae5e  mov     rax, [rax+20h]
0x14001ae62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae67  mov     [rbp+57h+var_80], 0
0x14001ae6f  mov     [rbp+57h+var_B0], r14
0x14001ae73  mov     qword ptr [rbp+57h+var_C8+8], 0
0x14001ae7b  mov     [rbp+57h+var_B8], r15
0x14001ae7f  mov     qword ptr [rbp+57h+var_C8], 0
0x14001ae87  lea     rax, [rbp+57h+var_B8]
0x14001ae8b  mov     [rbp+57h+var_A0], rax
0x14001ae8f  mov     rcx, [rbp+57h+var_38]
0x14001ae93  test    rcx, rcx
0x14001ae96  jz      loc_14001AFAB
0x14001ae9c  mov     rax, [rcx]
0x14001ae9f  lea     rdx, [rbp+57h+var_B8]
0x14001aea3  mov     rax, [rax+10h]
0x14001aea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aeac  mov     sil, al
0x14001aeaf  mov     rbx, [rbp+57h+var_B0]
0x14001aeb3  test    rbx, rbx
0x14001aeb6  jz      short loc_14001AEF0
0x14001aeb8  mov     ecx, r13d
0x14001aebb  lock xadd [rbx+8], ecx
0x14001aec0  add     ecx, r13d
0x14001aec3  jnz     short loc_14001AEF0
0x14001aec5  mov     rdx, [rbx]
0x14001aec8  mov     rcx, rbx
0x14001aecb  mov     rax, [rdx]
0x14001aece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aed3  mov     eax, r13d
0x14001aed6  lock xadd [rbx+0Ch], eax
0x14001aedb  add     eax, r13d
0x14001aede  jnz     short loc_14001AEF0
0x14001aee0  mov     rax, [rbx]
0x14001aee3  mov     rcx, rbx
0x14001aee6  mov     rax, [rax+8]
0x14001aeea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aeef  nop
0x14001aef0  mov     [rdi+0A0h], sil
0x14001aef7  lea     rax, [rdi+0B0h]
0x14001aefe  lea     rcx, [rbp+57h+var_30]
0x14001af02  cmp     rax, rcx
0x14001af05  jz      short loc_14001AF0E
0x14001af07  mov     qword ptr [rax], 0
0x14001af0e  lea     rbx, [rdi+28h]
0x14001af12  mov     rcx, rbx; lpCriticalSection
0x14001af15  call    cs:__imp_EnterCriticalSection
0x14001af1b  mov     eax, [rdi+10h]
0x14001af1e  mov     rcx, rbx; lpCriticalSection
0x14001af21  cmp     eax, 4
0x14001af24  jnz     short loc_14001AF2E
0x14001af26  call    cs:__imp_LeaveCriticalSection
0x14001af2c  jmp     short loc_14001AF4E
0x14001af2e  mov     dword ptr [rdi+10h], 3
0x14001af35  call    cs:__imp_LeaveCriticalSection
0x14001af3b  mov     rcx, [rdi+8]; hEvent
0x14001af3f  call    cs:__imp_SetEvent
0x14001af45  mov     rcx, rdi; this
0x14001af48  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x14001af4d  nop
0x14001af4e  mov     rcx, [rbp+57h+var_38]
0x14001af52  test    rcx, rcx
0x14001af55  jz      short loc_14001AF73
0x14001af57  mov     rax, [rcx]
0x14001af5a  lea     rdx, [rbp+57h+var_50]
0x14001af5e  cmp     rcx, rdx
0x14001af61  setnz   dl
0x14001af64  mov     rax, [rax+20h]
0x14001af68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af6d  xor     ecx, ecx
0x14001af6f  mov     [rbp+57h+var_38], rcx
0x14001af73  test    rcx, rcx
0x14001af76  jz      short loc_14001AF8F
0x14001af78  mov     rax, [rcx]
0x14001af7b  lea     rdx, [rbp+57h+var_50]
0x14001af7f  cmp     rcx, rdx
0x14001af82  setnz   dl
0x14001af85  mov     rax, [rax+20h]
0x14001af89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af8e  nop
0x14001af8f  lea     r11, [rsp+0F0h+var_20]
0x14001af97  mov     rbx, [r11+38h]
0x14001af9b  mov     rsi, [r11+40h]
0x14001af9f  mov     rsp, r11
0x14001afa2  pop     r15
0x14001afa4  pop     r14
0x14001afa6  pop     r13
0x14001afa8  pop     rdi
0x14001afa9  pop     rbp
0x14001afaa  retn
0x14001afab  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001afb1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
