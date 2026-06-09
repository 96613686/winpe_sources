# CInterceptor_IWbemServices_Interceptor::PutClass(IWbemClassObject *,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140034690`
- end: `0x14003479b`
- name: `?PutClass@CInterceptor_IWbemServices_Interceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140034690`
- `0x140035ec0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034736`
- `wbemcomn!GetMemLogObject` at `0x140034736`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034741`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034741`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003477f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003477f`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::PutClass(
        CInterceptor_IWbemServices_Interceptor *this,
        struct IWbemClassObject *a2,
        __int64 a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  unsigned int v6; // esi
  int v9; // edi
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  v6 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, a3, a2, a3, a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 64LL))(
           *((_QWORD *)this + 12),
           a2,
           v6,
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140034690  mov     rax, rsp
0x140034693  mov     [rax+10h], rbx
0x140034697  mov     [rax+18h], rbp
0x14003469b  push    rsi
0x14003469c  push    rdi
0x14003469d  push    r14
0x14003469f  sub     rsp, 30h
0x1400346a3  mov     rdi, r9
0x1400346a6  mov     esi, r8d
0x1400346a9  mov     rbp, rdx
0x1400346ac  mov     rbx, rcx
0x1400346af  lea     r14, WPP_GLOBAL_Control
0x1400346b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346bd  cmp     rcx, r14
0x1400346c0  jz      short loc_1400346E7
0x1400346c2  test    byte ptr [rcx+1Ch], 4
0x1400346c6  jz      short loc_1400346E7
0x1400346c8  cmp     byte ptr [rcx+19h], 5
0x1400346cc  jb      short loc_1400346E7
0x1400346ce  mov     edx, 13h
0x1400346d3  mov     [rax-20h], r9
0x1400346d7  mov     [rax-28h], r8d
0x1400346db  mov     r9, rbp
0x1400346de  mov     rcx, [rcx+10h]
0x1400346e2  call    WPP_SF_qdq
0x1400346e7  mov     edx, [rbx+70h]
0x1400346ea  lea     rcx, [rsp+48h+arg_0]
0x1400346ef  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400346f4  nop
0x1400346f5  lock inc dword ptr [rbx+20h]
0x1400346f9  cmp     dword ptr [rbx+1Ch], 1
0x1400346fd  jnz     short loc_140034706
0x1400346ff  mov     edi, 80041033h
0x140034704  jmp     short loc_14003472E
0x140034706  mov     rcx, [rbx+60h]
0x14003470a  mov     rax, [rcx]
0x14003470d  mov     r10, [rax+40h]
0x140034711  mov     rax, [rsp+48h+arg_20]
0x140034716  mov     [rsp+48h+var_28], rax
0x14003471b  mov     r9, rdi
0x14003471e  mov     r8d, esi
0x140034721  mov     rdx, rbp
0x140034724  mov     rax, r10
0x140034727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003472c  mov     edi, eax
0x14003472e  lock dec dword ptr [rbx+20h]
0x140034732  test    edi, edi
0x140034734  jns     short loc_140034747
0x140034736  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003473c  mov     edx, edi
0x14003473e  mov     rcx, rax
0x140034741  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034747  mov     rcx, cs:WPP_GLOBAL_Control
0x14003474e  cmp     rcx, r14
0x140034751  jz      short loc_140034778
0x140034753  test    byte ptr [rcx+1Ch], 4
0x140034757  jz      short loc_140034778
0x140034759  cmp     byte ptr [rcx+19h], 2
0x14003475d  jb      short loc_140034778
0x14003475f  mov     edx, 14h
0x140034764  mov     r9d, edi
0x140034767  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003476e  mov     rcx, [rcx+10h]
0x140034772  call    WPP_SF_d
0x140034777  nop
0x140034778  cmp     [rsp+48h+arg_0], 0
0x14003477d  jz      short loc_140034786
0x14003477f  call    cs:__imp_CoRevertToSelf
0x140034785  nop
0x140034786  mov     eax, edi
0x140034788  mov     rbx, [rsp+48h+arg_8]
0x14003478d  mov     rbp, [rsp+48h+arg_10]
0x140034792  add     rsp, 30h
0x140034796  pop     r14
0x140034798  pop     rdi
0x140034799  pop     rsi
0x14003479a  retn
```
