# CInterceptor_IWbemServices_Interceptor::CreateClassEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1400314b0`
- end: `0x1400315bb`
- name: `?CreateClassEnum@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400314b0`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031556`
- `wbemcomn!GetMemLogObject` at `0x140031556`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031561`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031561`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003159f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003159f`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::CreateClassEnum(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  int v9; // edi
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, a3, (_DWORD)a2, a3, (char)a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))(**((_QWORD **)this + 12) + 96LL))(
           *((_QWORD *)this + 12),
           a2,
           a3,
           a4,
           a5);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400314b0  mov     rax, rsp
0x1400314b3  mov     [rax+10h], rbx
0x1400314b7  mov     [rax+18h], rbp
0x1400314bb  push    rsi
0x1400314bc  push    rdi
0x1400314bd  push    r14
0x1400314bf  sub     rsp, 30h
0x1400314c3  mov     rdi, r9
0x1400314c6  mov     esi, r8d
0x1400314c9  mov     rbp, rdx
0x1400314cc  mov     rbx, rcx
0x1400314cf  lea     r14, WPP_GLOBAL_Control
0x1400314d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400314dd  cmp     rcx, r14
0x1400314e0  jz      short loc_140031507
0x1400314e2  test    byte ptr [rcx+1Ch], 4
0x1400314e6  jz      short loc_140031507
0x1400314e8  cmp     byte ptr [rcx+19h], 5
0x1400314ec  jb      short loc_140031507
0x1400314ee  mov     edx, 1Bh
0x1400314f3  mov     [rax-20h], r9
0x1400314f7  mov     [rax-28h], r8d
0x1400314fb  mov     r9, rbp
0x1400314fe  mov     rcx, [rcx+10h]
0x140031502  call    WPP_SF_Sdq
0x140031507  mov     edx, [rbx+70h]
0x14003150a  lea     rcx, [rsp+48h+arg_0]
0x14003150f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140031514  nop
0x140031515  lock inc dword ptr [rbx+20h]
0x140031519  cmp     dword ptr [rbx+1Ch], 1
0x14003151d  jnz     short loc_140031526
0x14003151f  mov     edi, 80041033h
0x140031524  jmp     short loc_14003154E
0x140031526  mov     rcx, [rbx+60h]
0x14003152a  mov     rax, [rcx]
0x14003152d  mov     r10, [rax+60h]
0x140031531  mov     rax, [rsp+48h+arg_20]
0x140031536  mov     [rsp+48h+var_28], rax
0x14003153b  mov     r9, rdi
0x14003153e  mov     r8d, esi
0x140031541  mov     rdx, rbp
0x140031544  mov     rax, r10
0x140031547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003154c  mov     edi, eax
0x14003154e  lock dec dword ptr [rbx+20h]
0x140031552  test    edi, edi
0x140031554  jns     short loc_140031567
0x140031556  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003155c  mov     edx, edi
0x14003155e  mov     rcx, rax
0x140031561  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031567  mov     rcx, cs:WPP_GLOBAL_Control
0x14003156e  cmp     rcx, r14
0x140031571  jz      short loc_140031598
0x140031573  test    byte ptr [rcx+1Ch], 4
0x140031577  jz      short loc_140031598
0x140031579  cmp     byte ptr [rcx+19h], 2
0x14003157d  jb      short loc_140031598
0x14003157f  mov     edx, 1Ch
0x140031584  mov     r9d, edi
0x140031587  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003158e  mov     rcx, [rcx+10h]
0x140031592  call    WPP_SF_d
0x140031597  nop
0x140031598  cmp     [rsp+48h+arg_0], 0
0x14003159d  jz      short loc_1400315A6
0x14003159f  call    cs:__imp_CoRevertToSelf
0x1400315a5  nop
0x1400315a6  mov     eax, edi
0x1400315a8  mov     rbx, [rsp+48h+arg_8]
0x1400315ad  mov     rbp, [rsp+48h+arg_10]
0x1400315b2  add     rsp, 30h
0x1400315b6  pop     r14
0x1400315b8  pop     rdi
0x1400315b9  pop     rsi
0x1400315ba  retn
```
