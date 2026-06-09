# CInterceptor_IWbemServices_Interceptor::PutClassAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140034950`
- end: `0x140034a63`
- name: `?PutClassAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400304c8`
- `0x140034950`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034a01`
- `wbemcomn!GetMemLogObject` at `0x140034a01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034a0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034a0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034a4d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034a4d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::PutClassAsync(
        CInterceptor_IWbemServices_Interceptor *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IWbemObjectSink *v9; // r14
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  int v13; // [rsp+80h] [rbp+8h] BYREF

  v9 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      a2,
      a3,
      a4,
      a5);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v13, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v10 = -2147217357;
  else
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 72LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v9);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  if ( v13 )
    CoRevertToSelf();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140034950  push    rbx
0x140034952  push    rbp
0x140034953  push    rsi
0x140034954  push    rdi
0x140034955  push    r14
0x140034957  push    r15
0x140034959  sub     rsp, 48h
0x14003495d  mov     rbx, r9
0x140034960  mov     esi, r8d
0x140034963  mov     rbp, rdx
0x140034966  mov     rdi, rcx
0x140034969  lea     r15, WPP_GLOBAL_Control
0x140034970  mov     r14, [rsp+78h+arg_20]
0x140034978  mov     rcx, cs:WPP_GLOBAL_Control
0x14003497f  cmp     rcx, r15
0x140034982  jz      short loc_1400349B7
0x140034984  test    byte ptr [rcx+1Ch], 4
0x140034988  jz      short loc_1400349B7
0x14003498a  cmp     byte ptr [rcx+19h], 5
0x14003498e  jb      short loc_1400349B7
0x140034990  mov     edx, 15h
0x140034995  mov     [rsp+78h+var_48], r14
0x14003499a  mov     [rsp+78h+var_50], rbx
0x14003499f  mov     dword ptr [rsp+78h+var_58], r8d
0x1400349a4  mov     r9, rbp
0x1400349a7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400349ae  mov     rcx, [rcx+10h]
0x1400349b2  call    WPP_SF_qdqq
0x1400349b7  mov     edx, [rdi+70h]
0x1400349ba  lea     rcx, [rsp+78h+arg_0]
0x1400349c2  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400349c7  nop
0x1400349c8  lock inc dword ptr [rdi+20h]
0x1400349cc  cmp     dword ptr [rdi+1Ch], 1
0x1400349d0  jnz     short loc_1400349D9
0x1400349d2  mov     ebx, 80041033h
0x1400349d7  jmp     short loc_1400349F9
0x1400349d9  mov     rcx, [rdi+60h]
0x1400349dd  mov     rax, [rcx]
0x1400349e0  mov     [rsp+78h+var_58], r14
0x1400349e5  mov     r9, rbx
0x1400349e8  mov     r8d, esi
0x1400349eb  mov     rdx, rbp
0x1400349ee  mov     rax, [rax+48h]
0x1400349f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400349f7  mov     ebx, eax
0x1400349f9  lock dec dword ptr [rdi+20h]
0x1400349fd  test    ebx, ebx
0x1400349ff  jns     short loc_140034A12
0x140034a01  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034a07  mov     edx, ebx
0x140034a09  mov     rcx, rax
0x140034a0c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a19  cmp     rcx, r15
0x140034a1c  jz      short loc_140034A43
0x140034a1e  test    byte ptr [rcx+1Ch], 4
0x140034a22  jz      short loc_140034A43
0x140034a24  cmp     byte ptr [rcx+19h], 2
0x140034a28  jb      short loc_140034A43
0x140034a2a  mov     edx, 16h
0x140034a2f  mov     r9d, ebx
0x140034a32  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034a39  mov     rcx, [rcx+10h]
0x140034a3d  call    WPP_SF_d
0x140034a42  nop
0x140034a43  cmp     [rsp+78h+arg_0], 0
0x140034a4b  jz      short loc_140034A54
0x140034a4d  call    cs:__imp_CoRevertToSelf
0x140034a53  nop
0x140034a54  mov     eax, ebx
0x140034a56  add     rsp, 48h
0x140034a5a  pop     r15
0x140034a5c  pop     r14
0x140034a5e  pop     rdi
0x140034a5f  pop     rsi
0x140034a60  pop     rbp
0x140034a61  pop     rbx
0x140034a62  retn
```
