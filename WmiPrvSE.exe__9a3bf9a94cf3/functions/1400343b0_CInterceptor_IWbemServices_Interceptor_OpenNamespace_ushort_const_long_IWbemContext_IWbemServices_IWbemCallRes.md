# CInterceptor_IWbemServices_Interceptor::OpenNamespace(ushort * const,long,IWbemContext *,IWbemServices * *,IWbemCallResult * *)

- ea: `0x1400343b0`
- end: `0x1400344cb`
- name: `?OpenNamespace@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemServices@@PEAPEAUIWbemCallResult@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemServices **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400343b0`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034466`
- `wbemcomn!GetMemLogObject` at `0x140034466`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034471`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034471`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400344af`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400344af`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::OpenNamespace(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemServices **a5,
        struct IWbemCallResult **a6)
{
  int v10; // edi
  CMemoryLog *MemLogObject; // rax
  int v13; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, (_DWORD)a2, a3, (char)a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v13, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v10 = -2147217357;
  else
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemServices **, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 24LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            a5,
            a6);
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
      11,
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
0x1400343b0  mov     rax, rsp
0x1400343b3  mov     [rax+10h], rbx
0x1400343b7  mov     [rax+18h], rbp
0x1400343bb  push    rsi
0x1400343bc  push    rdi
0x1400343bd  push    r14
0x1400343bf  sub     rsp, 40h
0x1400343c3  mov     rdi, r9
0x1400343c6  mov     esi, r8d
0x1400343c9  mov     rbp, rdx
0x1400343cc  mov     rbx, rcx
0x1400343cf  lea     r14, WPP_GLOBAL_Control
0x1400343d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400343dd  cmp     rcx, r14
0x1400343e0  jz      short loc_140034407
0x1400343e2  test    byte ptr [rcx+1Ch], 4
0x1400343e6  jz      short loc_140034407
0x1400343e8  cmp     byte ptr [rcx+19h], 5
0x1400343ec  jb      short loc_140034407
0x1400343ee  mov     edx, 0Ah
0x1400343f3  mov     [rax-30h], r9
0x1400343f7  mov     [rax-38h], r8d
0x1400343fb  mov     r9, rbp
0x1400343fe  mov     rcx, [rcx+10h]
0x140034402  call    WPP_SF_Sdq
0x140034407  mov     edx, [rbx+70h]
0x14003440a  lea     rcx, [rsp+58h+arg_0]
0x14003440f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140034414  nop
0x140034415  lock inc dword ptr [rbx+20h]
0x140034419  cmp     dword ptr [rbx+1Ch], 1
0x14003441d  jnz     short loc_140034426
0x14003441f  mov     edi, 80041033h
0x140034424  jmp     short loc_14003445E
0x140034426  mov     rcx, [rbx+60h]
0x14003442a  mov     rax, [rcx]
0x14003442d  mov     r10, [rax+18h]
0x140034431  mov     rax, [rsp+58h+arg_28]
0x140034439  mov     [rsp+58h+var_30], rax
0x14003443e  mov     rax, [rsp+58h+arg_20]
0x140034446  mov     [rsp+58h+var_38], rax
0x14003444b  mov     r9, rdi
0x14003444e  mov     r8d, esi
0x140034451  mov     rdx, rbp
0x140034454  mov     rax, r10
0x140034457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003445c  mov     edi, eax
0x14003445e  lock dec dword ptr [rbx+20h]
0x140034462  test    edi, edi
0x140034464  jns     short loc_140034477
0x140034466  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003446c  mov     edx, edi
0x14003446e  mov     rcx, rax
0x140034471  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034477  mov     rcx, cs:WPP_GLOBAL_Control
0x14003447e  cmp     rcx, r14
0x140034481  jz      short loc_1400344A8
0x140034483  test    byte ptr [rcx+1Ch], 4
0x140034487  jz      short loc_1400344A8
0x140034489  cmp     byte ptr [rcx+19h], 2
0x14003448d  jb      short loc_1400344A8
0x14003448f  mov     edx, 0Bh
0x140034494  mov     r9d, edi
0x140034497  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003449e  mov     rcx, [rcx+10h]
0x1400344a2  call    WPP_SF_d
0x1400344a7  nop
0x1400344a8  cmp     [rsp+58h+arg_0], 0
0x1400344ad  jz      short loc_1400344B6
0x1400344af  call    cs:__imp_CoRevertToSelf
0x1400344b5  nop
0x1400344b6  mov     eax, edi
0x1400344b8  mov     rbx, [rsp+58h+arg_8]
0x1400344bd  mov     rbp, [rsp+58h+arg_10]
0x1400344c2  add     rsp, 40h
0x1400344c6  pop     r14
0x1400344c8  pop     rdi
0x1400344c9  pop     rsi
0x1400344ca  retn
```
