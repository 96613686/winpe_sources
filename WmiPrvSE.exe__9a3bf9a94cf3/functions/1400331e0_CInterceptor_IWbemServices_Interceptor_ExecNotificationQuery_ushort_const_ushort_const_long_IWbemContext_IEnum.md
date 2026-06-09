# CInterceptor_IWbemServices_Interceptor::ExecNotificationQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1400331e0`
- end: `0x1400332fe`
- name: `?ExecNotificationQuery@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400331e0`
- `0x140035b84`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003329c`
- `wbemcomn!GetMemLogObject` at `0x14003329c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400332a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400332a7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400332e8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400332e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecNotificationQuery(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IEnumWbemClassObject **a6)
{
  struct IWbemContext *v10; // r14
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v10 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, (_DWORD)a3, (_DWORD)a2, (__int64)a3, a4, (char)a5);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v14, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v11 = -2147217357;
  else
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))(**((_QWORD **)this + 12) + 176LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v10,
            a6);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  if ( v14 )
    CoRevertToSelf();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400331e0  push    rbx
0x1400331e2  push    rbp
0x1400331e3  push    rsi
0x1400331e4  push    rdi
0x1400331e5  push    r14
0x1400331e7  push    r15
0x1400331e9  sub     rsp, 48h
0x1400331ed  mov     ebx, r9d
0x1400331f0  mov     rsi, r8
0x1400331f3  mov     rbp, rdx
0x1400331f6  mov     rdi, rcx
0x1400331f9  lea     r15, WPP_GLOBAL_Control
0x140033200  mov     r14, [rsp+78h+arg_20]
0x140033208  mov     rcx, cs:WPP_GLOBAL_Control
0x14003320f  cmp     rcx, r15
0x140033212  jz      short loc_14003323F
0x140033214  test    byte ptr [rcx+1Ch], 4
0x140033218  jz      short loc_14003323F
0x14003321a  cmp     byte ptr [rcx+19h], 5
0x14003321e  jb      short loc_14003323F
0x140033220  mov     edx, 2Fh ; '/'
0x140033225  mov     [rsp+78h+var_48], r14
0x14003322a  mov     dword ptr [rsp+78h+var_50], ebx
0x14003322e  mov     [rsp+78h+var_58], r8
0x140033233  mov     r9, rbp
0x140033236  mov     rcx, [rcx+10h]
0x14003323a  call    WPP_SF_SSdq
0x14003323f  mov     edx, [rdi+70h]
0x140033242  lea     rcx, [rsp+78h+arg_0]
0x14003324a  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x14003324f  nop
0x140033250  lock inc dword ptr [rdi+20h]
0x140033254  cmp     dword ptr [rdi+1Ch], 1
0x140033258  jnz     short loc_140033261
0x14003325a  mov     ebx, 80041033h
0x14003325f  jmp     short loc_140033294
0x140033261  mov     rcx, [rdi+60h]
0x140033265  mov     rax, [rcx]
0x140033268  mov     r10, [rax+0B0h]
0x14003326f  mov     rax, [rsp+78h+arg_28]
0x140033277  mov     [rsp+78h+var_50], rax
0x14003327c  mov     [rsp+78h+var_58], r14
0x140033281  mov     r9d, ebx
0x140033284  mov     r8, rsi
0x140033287  mov     rdx, rbp
0x14003328a  mov     rax, r10
0x14003328d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033292  mov     ebx, eax
0x140033294  lock dec dword ptr [rdi+20h]
0x140033298  test    ebx, ebx
0x14003329a  jns     short loc_1400332AD
0x14003329c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400332a2  mov     edx, ebx
0x1400332a4  mov     rcx, rax
0x1400332a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400332ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400332b4  cmp     rcx, r15
0x1400332b7  jz      short loc_1400332DE
0x1400332b9  test    byte ptr [rcx+1Ch], 4
0x1400332bd  jz      short loc_1400332DE
0x1400332bf  cmp     byte ptr [rcx+19h], 2
0x1400332c3  jb      short loc_1400332DE
0x1400332c5  mov     edx, 30h ; '0'
0x1400332ca  mov     r9d, ebx
0x1400332cd  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400332d4  mov     rcx, [rcx+10h]
0x1400332d8  call    WPP_SF_d
0x1400332dd  nop
0x1400332de  cmp     [rsp+78h+arg_0], 0
0x1400332e6  jz      short loc_1400332EF
0x1400332e8  call    cs:__imp_CoRevertToSelf
0x1400332ee  nop
0x1400332ef  mov     eax, ebx
0x1400332f1  add     rsp, 48h
0x1400332f5  pop     r15
0x1400332f7  pop     r14
0x1400332f9  pop     rdi
0x1400332fa  pop     rsi
0x1400332fb  pop     rbp
0x1400332fc  pop     rbx
0x1400332fd  retn
```
