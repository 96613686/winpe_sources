# CInterceptor_IWbemServices_Interceptor::DeleteInstance(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140032570`
- end: `0x14003267e`
- name: `?DeleteInstance@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140032570`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032619`
- `wbemcomn!GetMemLogObject` at `0x140032619`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032624`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032624`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032662`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032662`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::DeleteInstance(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  int v9; // edi
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, a3, (_DWORD)a2, a3, (char)a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 128LL))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140032570  mov     rax, rsp
0x140032573  mov     [rax+10h], rbx
0x140032577  mov     [rax+18h], rbp
0x14003257b  push    rsi
0x14003257c  push    rdi
0x14003257d  push    r14
0x14003257f  sub     rsp, 30h
0x140032583  mov     rdi, r9
0x140032586  mov     esi, r8d
0x140032589  mov     rbp, rdx
0x14003258c  mov     rbx, rcx
0x14003258f  lea     r14, WPP_GLOBAL_Control
0x140032596  mov     rcx, cs:WPP_GLOBAL_Control
0x14003259d  cmp     rcx, r14
0x1400325a0  jz      short loc_1400325C7
0x1400325a2  test    byte ptr [rcx+1Ch], 4
0x1400325a6  jz      short loc_1400325C7
0x1400325a8  cmp     byte ptr [rcx+19h], 5
0x1400325ac  jb      short loc_1400325C7
0x1400325ae  mov     edx, 23h ; '#'
0x1400325b3  mov     [rax-20h], r9
0x1400325b7  mov     [rax-28h], r8d
0x1400325bb  mov     r9, rbp
0x1400325be  mov     rcx, [rcx+10h]
0x1400325c2  call    WPP_SF_Sdq
0x1400325c7  mov     edx, [rbx+70h]
0x1400325ca  lea     rcx, [rsp+48h+arg_0]
0x1400325cf  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400325d4  nop
0x1400325d5  lock inc dword ptr [rbx+20h]
0x1400325d9  cmp     dword ptr [rbx+1Ch], 1
0x1400325dd  jnz     short loc_1400325E6
0x1400325df  mov     edi, 80041033h
0x1400325e4  jmp     short loc_140032611
0x1400325e6  mov     rcx, [rbx+60h]
0x1400325ea  mov     rax, [rcx]
0x1400325ed  mov     r10, [rax+80h]
0x1400325f4  mov     rax, [rsp+48h+arg_20]
0x1400325f9  mov     [rsp+48h+var_28], rax
0x1400325fe  mov     r9, rdi
0x140032601  mov     r8d, esi
0x140032604  mov     rdx, rbp
0x140032607  mov     rax, r10
0x14003260a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003260f  mov     edi, eax
0x140032611  lock dec dword ptr [rbx+20h]
0x140032615  test    edi, edi
0x140032617  jns     short loc_14003262A
0x140032619  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003261f  mov     edx, edi
0x140032621  mov     rcx, rax
0x140032624  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003262a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032631  cmp     rcx, r14
0x140032634  jz      short loc_14003265B
0x140032636  test    byte ptr [rcx+1Ch], 4
0x14003263a  jz      short loc_14003265B
0x14003263c  cmp     byte ptr [rcx+19h], 2
0x140032640  jb      short loc_14003265B
0x140032642  mov     edx, 24h ; '$'
0x140032647  mov     r9d, edi
0x14003264a  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032651  mov     rcx, [rcx+10h]
0x140032655  call    WPP_SF_d
0x14003265a  nop
0x14003265b  cmp     [rsp+48h+arg_0], 0
0x140032660  jz      short loc_140032669
0x140032662  call    cs:__imp_CoRevertToSelf
0x140032668  nop
0x140032669  mov     eax, edi
0x14003266b  mov     rbx, [rsp+48h+arg_8]
0x140032670  mov     rbp, [rsp+48h+arg_10]
0x140032675  add     rsp, 30h
0x140032679  pop     r14
0x14003267b  pop     rdi
0x14003267c  pop     rsi
0x14003267d  retn
```
