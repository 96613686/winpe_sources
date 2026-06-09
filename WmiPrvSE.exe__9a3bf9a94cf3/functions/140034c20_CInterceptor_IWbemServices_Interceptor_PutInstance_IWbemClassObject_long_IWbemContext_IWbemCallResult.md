# CInterceptor_IWbemServices_Interceptor::PutInstance(IWbemClassObject *,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140034c20`
- end: `0x140034d2b`
- name: `?PutInstance@CInterceptor_IWbemServices_Interceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140034c20`
- `0x140035ec0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034cc6`
- `wbemcomn!GetMemLogObject` at `0x140034cc6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034cd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034cd1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034d0f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034d0f`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::PutInstance(
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
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, a3, a2, a3, a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 112LL))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140034c20  mov     rax, rsp
0x140034c23  mov     [rax+10h], rbx
0x140034c27  mov     [rax+18h], rbp
0x140034c2b  push    rsi
0x140034c2c  push    rdi
0x140034c2d  push    r14
0x140034c2f  sub     rsp, 30h
0x140034c33  mov     rdi, r9
0x140034c36  mov     esi, r8d
0x140034c39  mov     rbp, rdx
0x140034c3c  mov     rbx, rcx
0x140034c3f  lea     r14, WPP_GLOBAL_Control
0x140034c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c4d  cmp     rcx, r14
0x140034c50  jz      short loc_140034C77
0x140034c52  test    byte ptr [rcx+1Ch], 4
0x140034c56  jz      short loc_140034C77
0x140034c58  cmp     byte ptr [rcx+19h], 5
0x140034c5c  jb      short loc_140034C77
0x140034c5e  mov     edx, 1Fh
0x140034c63  mov     [rax-20h], r9
0x140034c67  mov     [rax-28h], r8d
0x140034c6b  mov     r9, rbp
0x140034c6e  mov     rcx, [rcx+10h]
0x140034c72  call    WPP_SF_qdq
0x140034c77  mov     edx, [rbx+70h]
0x140034c7a  lea     rcx, [rsp+48h+arg_0]
0x140034c7f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140034c84  nop
0x140034c85  lock inc dword ptr [rbx+20h]
0x140034c89  cmp     dword ptr [rbx+1Ch], 1
0x140034c8d  jnz     short loc_140034C96
0x140034c8f  mov     edi, 80041033h
0x140034c94  jmp     short loc_140034CBE
0x140034c96  mov     rcx, [rbx+60h]
0x140034c9a  mov     rax, [rcx]
0x140034c9d  mov     r10, [rax+70h]
0x140034ca1  mov     rax, [rsp+48h+arg_20]
0x140034ca6  mov     [rsp+48h+var_28], rax
0x140034cab  mov     r9, rdi
0x140034cae  mov     r8d, esi
0x140034cb1  mov     rdx, rbp
0x140034cb4  mov     rax, r10
0x140034cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034cbc  mov     edi, eax
0x140034cbe  lock dec dword ptr [rbx+20h]
0x140034cc2  test    edi, edi
0x140034cc4  jns     short loc_140034CD7
0x140034cc6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034ccc  mov     edx, edi
0x140034cce  mov     rcx, rax
0x140034cd1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cde  cmp     rcx, r14
0x140034ce1  jz      short loc_140034D08
0x140034ce3  test    byte ptr [rcx+1Ch], 4
0x140034ce7  jz      short loc_140034D08
0x140034ce9  cmp     byte ptr [rcx+19h], 2
0x140034ced  jb      short loc_140034D08
0x140034cef  mov     edx, 20h ; ' '
0x140034cf4  mov     r9d, edi
0x140034cf7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034cfe  mov     rcx, [rcx+10h]
0x140034d02  call    WPP_SF_d
0x140034d07  nop
0x140034d08  cmp     [rsp+48h+arg_0], 0
0x140034d0d  jz      short loc_140034D16
0x140034d0f  call    cs:__imp_CoRevertToSelf
0x140034d15  nop
0x140034d16  mov     eax, edi
0x140034d18  mov     rbx, [rsp+48h+arg_8]
0x140034d1d  mov     rbp, [rsp+48h+arg_10]
0x140034d22  add     rsp, 30h
0x140034d26  pop     r14
0x140034d28  pop     rdi
0x140034d29  pop     rsi
0x140034d2a  retn
```
