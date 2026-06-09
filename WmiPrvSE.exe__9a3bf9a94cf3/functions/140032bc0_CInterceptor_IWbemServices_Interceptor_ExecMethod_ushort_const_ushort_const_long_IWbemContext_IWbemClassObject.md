# CInterceptor_IWbemServices_Interceptor::ExecMethod(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x140032bc0`
- end: `0x140032d16`
- name: `?ExecMethod@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAPEAU3@PEAPEAUIWbemCallResult@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140029824`
- `0x140032bc0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032ca8`
- `wbemcomn!GetMemLogObject` at `0x140032ca8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032cb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032cb3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032cf4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032cf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecMethod(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemClassObject **a7,
        struct IWbemCallResult **a8)
{
  struct IWbemClassObject *v12; // r14
  struct IWbemContext *v13; // r15
  int v14; // ebx
  CMemoryLog *MemLogObject; // rax
  int v17; // [rsp+80h] [rbp+8h] BYREF

  v12 = a6;
  v13 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a6,
      (char)a5);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v17, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v14 = -2147217357;
  else
    v14 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemClassObject *, struct IWbemClassObject **, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 192LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v13,
            v12,
            a7,
            a8);
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
      52,
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
0x140032bc0  mov     rax, rsp
0x140032bc3  mov     [rax+10h], rbx
0x140032bc7  mov     [rax+18h], rbp
0x140032bcb  push    rsi
0x140032bcc  push    rdi
0x140032bcd  push    r12
0x140032bcf  push    r14
0x140032bd1  push    r15
0x140032bd3  sub     rsp, 50h
0x140032bd7  mov     ebx, r9d
0x140032bda  mov     rsi, r8
0x140032bdd  mov     rbp, rdx
0x140032be0  mov     rdi, rcx
0x140032be3  lea     r12, WPP_GLOBAL_Control
0x140032bea  mov     r14, [rsp+78h+arg_28]
0x140032bf2  mov     r15, [rsp+78h+arg_20]
0x140032bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c01  cmp     rcx, r12
0x140032c04  jz      short loc_140032C39
0x140032c06  test    byte ptr [rcx+1Ch], 4
0x140032c0a  jz      short loc_140032C39
0x140032c0c  cmp     byte ptr [rcx+19h], 5
0x140032c10  jb      short loc_140032C39
0x140032c12  mov     edx, 33h ; '3'
0x140032c17  mov     [rax-40h], r15
0x140032c1b  mov     [rax-48h], r14
0x140032c1f  mov     [rax-50h], ebx
0x140032c22  mov     [rax-58h], r8
0x140032c26  mov     r9, rbp
0x140032c29  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032c30  mov     rcx, [rcx+10h]
0x140032c34  call    WPP_SF_SSdqq
0x140032c39  mov     edx, [rdi+70h]
0x140032c3c  lea     rcx, [rsp+78h+arg_0]
0x140032c44  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140032c49  nop
0x140032c4a  lock inc dword ptr [rdi+20h]
0x140032c4e  cmp     dword ptr [rdi+1Ch], 1
0x140032c52  jnz     short loc_140032C5B
0x140032c54  mov     ebx, 80041033h
0x140032c59  jmp     short loc_140032CA0
0x140032c5b  mov     rcx, [rdi+60h]
0x140032c5f  mov     rax, [rcx]
0x140032c62  mov     r10, [rax+0C0h]
0x140032c69  mov     rax, [rsp+78h+arg_38]
0x140032c71  mov     [rsp+78h+var_40], rax
0x140032c76  mov     rax, [rsp+78h+arg_30]
0x140032c7e  mov     [rsp+78h+var_48], rax
0x140032c83  mov     [rsp+78h+var_50], r14
0x140032c88  mov     [rsp+78h+var_58], r15
0x140032c8d  mov     r9d, ebx
0x140032c90  mov     r8, rsi
0x140032c93  mov     rdx, rbp
0x140032c96  mov     rax, r10
0x140032c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032c9e  mov     ebx, eax
0x140032ca0  lock dec dword ptr [rdi+20h]
0x140032ca4  test    ebx, ebx
0x140032ca6  jns     short loc_140032CB9
0x140032ca8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032cae  mov     edx, ebx
0x140032cb0  mov     rcx, rax
0x140032cb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140032cc0  cmp     rcx, r12
0x140032cc3  jz      short loc_140032CEA
0x140032cc5  test    byte ptr [rcx+1Ch], 4
0x140032cc9  jz      short loc_140032CEA
0x140032ccb  cmp     byte ptr [rcx+19h], 2
0x140032ccf  jb      short loc_140032CEA
0x140032cd1  mov     edx, 34h ; '4'
0x140032cd6  mov     r9d, ebx
0x140032cd9  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032ce0  mov     rcx, [rcx+10h]
0x140032ce4  call    WPP_SF_d
0x140032ce9  nop
0x140032cea  cmp     [rsp+78h+arg_0], 0
0x140032cf2  jz      short loc_140032CFB
0x140032cf4  call    cs:__imp_CoRevertToSelf
0x140032cfa  nop
0x140032cfb  mov     eax, ebx
0x140032cfd  lea     r11, [rsp+78h+var_28]
0x140032d02  mov     rbx, [r11+38h]
0x140032d06  mov     rbp, [r11+40h]
0x140032d0a  mov     rsp, r11
0x140032d0d  pop     r15
0x140032d0f  pop     r14
0x140032d11  pop     r12
0x140032d13  pop     rdi
0x140032d14  pop     rsi
0x140032d15  retn
```
