# CInterceptor_IWbemServices_Interceptor::ExecNotificationQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1400334d0`
- end: `0x140033603`
- name: `?ExecNotificationQueryAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140029824`
- `0x1400334d0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033598`
- `wbemcomn!GetMemLogObject` at `0x140033598`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400335a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400335a3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400335e1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400335e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecNotificationQueryAsync(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6)
{
  struct IWbemObjectSink *v10; // r14
  struct IWbemContext *v11; // r15
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+70h] [rbp+8h] BYREF

  v10 = a6;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a5,
      (char)a6);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v15, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v12 = -2147217357;
  else
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 184LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v11,
            v10);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v12 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  if ( v15 )
    CoRevertToSelf();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400334d0  mov     rax, rsp
0x1400334d3  mov     [rax+10h], rbx
0x1400334d7  mov     [rax+18h], rbp
0x1400334db  push    rsi
0x1400334dc  push    rdi
0x1400334dd  push    r12
0x1400334df  push    r14
0x1400334e1  push    r15
0x1400334e3  sub     rsp, 40h
0x1400334e7  mov     ebx, r9d
0x1400334ea  mov     rsi, r8
0x1400334ed  mov     rbp, rdx
0x1400334f0  mov     rdi, rcx
0x1400334f3  lea     r12, WPP_GLOBAL_Control
0x1400334fa  mov     r14, [rsp+68h+arg_28]
0x140033502  mov     r15, [rsp+68h+arg_20]
0x14003350a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033511  cmp     rcx, r12
0x140033514  jz      short loc_140033549
0x140033516  test    byte ptr [rcx+1Ch], 4
0x14003351a  jz      short loc_140033549
0x14003351c  cmp     byte ptr [rcx+19h], 5
0x140033520  jb      short loc_140033549
0x140033522  mov     edx, 31h ; '1'
0x140033527  mov     [rax-30h], r14
0x14003352b  mov     [rax-38h], r15
0x14003352f  mov     [rax-40h], ebx
0x140033532  mov     [rax-48h], r8
0x140033536  mov     r9, rbp
0x140033539  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033540  mov     rcx, [rcx+10h]
0x140033544  call    WPP_SF_SSdqq
0x140033549  mov     edx, [rdi+70h]
0x14003354c  lea     rcx, [rsp+68h+arg_0]
0x140033551  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140033556  nop
0x140033557  lock inc dword ptr [rdi+20h]
0x14003355b  cmp     dword ptr [rdi+1Ch], 1
0x14003355f  jnz     short loc_140033568
0x140033561  mov     ebx, 80041033h
0x140033566  jmp     short loc_140033590
0x140033568  mov     rcx, [rdi+60h]
0x14003356c  mov     rax, [rcx]
0x14003356f  mov     [rsp+68h+var_40], r14
0x140033574  mov     [rsp+68h+var_48], r15
0x140033579  mov     r9d, ebx
0x14003357c  mov     r8, rsi
0x14003357f  mov     rdx, rbp
0x140033582  mov     rax, [rax+0B8h]
0x140033589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003358e  mov     ebx, eax
0x140033590  lock dec dword ptr [rdi+20h]
0x140033594  test    ebx, ebx
0x140033596  jns     short loc_1400335A9
0x140033598  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003359e  mov     edx, ebx
0x1400335a0  mov     rcx, rax
0x1400335a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400335a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335b0  cmp     rcx, r12
0x1400335b3  jz      short loc_1400335DA
0x1400335b5  test    byte ptr [rcx+1Ch], 4
0x1400335b9  jz      short loc_1400335DA
0x1400335bb  cmp     byte ptr [rcx+19h], 2
0x1400335bf  jb      short loc_1400335DA
0x1400335c1  mov     edx, 32h ; '2'
0x1400335c6  mov     r9d, ebx
0x1400335c9  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400335d0  mov     rcx, [rcx+10h]
0x1400335d4  call    WPP_SF_d
0x1400335d9  nop
0x1400335da  cmp     [rsp+68h+arg_0], 0
0x1400335df  jz      short loc_1400335E8
0x1400335e1  call    cs:__imp_CoRevertToSelf
0x1400335e7  nop
0x1400335e8  mov     eax, ebx
0x1400335ea  lea     r11, [rsp+68h+var_28]
0x1400335ef  mov     rbx, [r11+38h]
0x1400335f3  mov     rbp, [r11+40h]
0x1400335f7  mov     rsp, r11
0x1400335fa  pop     r15
0x1400335fc  pop     r14
0x1400335fe  pop     r12
0x140033600  pop     rdi
0x140033601  pop     rsi
0x140033602  retn
```
