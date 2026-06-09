# CInterceptor_IWbemServices_Interceptor::ExecMethodAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x140032ee0`
- end: `0x14003301e`
- name: `?ExecMethodAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400292f8`
- `0x140032ee0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032fb8`
- `wbemcomn!GetMemLogObject` at `0x140032fb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032fc3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032fc3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033004`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033004`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecMethodAsync(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemObjectSink *a7)
{
  struct IWbemObjectSink *v11; // r14
  struct IWbemClassObject *v12; // r15
  struct IWbemContext *v13; // r12
  int v14; // ebx
  CMemoryLog *MemLogObject; // rax
  int v17; // [rsp+A0h] [rbp+8h] BYREF

  v11 = a7;
  v12 = a6;
  v13 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a6,
      (char)a5,
      (char)a7);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v17, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v14 = -2147217357;
  else
    v14 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 200LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v13,
            v12,
            v11);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v14);
  }
  if ( v17 )
    CoRevertToSelf();
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140032ee0  mov     rax, rsp
0x140032ee3  push    rbx
0x140032ee4  push    rbp
0x140032ee5  push    rsi
0x140032ee6  push    rdi
0x140032ee7  push    r12
0x140032ee9  push    r13
0x140032eeb  push    r14
0x140032eed  push    r15
0x140032eef  sub     rsp, 58h
0x140032ef3  mov     ebx, r9d
0x140032ef6  mov     rsi, r8
0x140032ef9  mov     rbp, rdx
0x140032efc  mov     rdi, rcx
0x140032eff  lea     r13, WPP_GLOBAL_Control
0x140032f06  mov     r14, [rsp+98h+arg_30]
0x140032f0e  mov     r15, [rsp+98h+arg_28]
0x140032f16  mov     r12, [rsp+98h+arg_20]
0x140032f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f25  cmp     rcx, r13
0x140032f28  jz      short loc_140032F61
0x140032f2a  test    byte ptr [rcx+1Ch], 4
0x140032f2e  jz      short loc_140032F61
0x140032f30  cmp     byte ptr [rcx+19h], 5
0x140032f34  jb      short loc_140032F61
0x140032f36  mov     edx, 35h ; '5'
0x140032f3b  mov     [rax-58h], r14
0x140032f3f  mov     [rax-60h], r12
0x140032f43  mov     [rax-68h], r15
0x140032f47  mov     [rax-70h], ebx
0x140032f4a  mov     [rax-78h], r8
0x140032f4e  mov     r9, rbp
0x140032f51  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032f58  mov     rcx, [rcx+10h]
0x140032f5c  call    WPP_SF_SSdqqq
0x140032f61  mov     edx, [rdi+70h]
0x140032f64  lea     rcx, [rsp+98h+arg_0]
0x140032f6c  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140032f71  nop
0x140032f72  lock inc dword ptr [rdi+20h]
0x140032f76  cmp     dword ptr [rdi+1Ch], 1
0x140032f7a  jnz     short loc_140032F83
0x140032f7c  mov     ebx, 80041033h
0x140032f81  jmp     short loc_140032FB0
0x140032f83  mov     rcx, [rdi+60h]
0x140032f87  mov     rax, [rcx]
0x140032f8a  mov     [rsp+98h+var_68], r14
0x140032f8f  mov     [rsp+98h+var_70], r15
0x140032f94  mov     [rsp+98h+var_78], r12
0x140032f99  mov     r9d, ebx
0x140032f9c  mov     r8, rsi
0x140032f9f  mov     rdx, rbp
0x140032fa2  mov     rax, [rax+0C8h]
0x140032fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032fae  mov     ebx, eax
0x140032fb0  lock dec dword ptr [rdi+20h]
0x140032fb4  test    ebx, ebx
0x140032fb6  jns     short loc_140032FC9
0x140032fb8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032fbe  mov     edx, ebx
0x140032fc0  mov     rcx, rax
0x140032fc3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fd0  cmp     rcx, r13
0x140032fd3  jz      short loc_140032FFA
0x140032fd5  test    byte ptr [rcx+1Ch], 4
0x140032fd9  jz      short loc_140032FFA
0x140032fdb  cmp     byte ptr [rcx+19h], 2
0x140032fdf  jb      short loc_140032FFA
0x140032fe1  mov     edx, 36h ; '6'
0x140032fe6  mov     r9d, ebx
0x140032fe9  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032ff0  mov     rcx, [rcx+10h]
0x140032ff4  call    WPP_SF_d
0x140032ff9  nop
0x140032ffa  cmp     [rsp+98h+arg_0], 0
0x140033002  jz      short loc_14003300B
0x140033004  call    cs:__imp_CoRevertToSelf
0x14003300a  nop
0x14003300b  mov     eax, ebx
0x14003300d  add     rsp, 58h
0x140033011  pop     r15
0x140033013  pop     r14
0x140033015  pop     r13
0x140033017  pop     r12
0x140033019  pop     rdi
0x14003301a  pop     rsi
0x14003301b  pop     rbp
0x14003301c  pop     rbx
0x14003301d  retn
```
