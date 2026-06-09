# CInterceptor_IWbemServices_Interceptor::PutInstanceAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140034ee0`
- end: `0x140034ff3`
- name: `?PutInstanceAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400304c8`
- `0x140034ee0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034f91`
- `wbemcomn!GetMemLogObject` at `0x140034f91`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034f9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034f9c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034fdd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140034fdd`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::PutInstanceAsync(
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
      33,
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
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 120LL))(
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
      34,
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
0x140034ee0  push    rbx
0x140034ee2  push    rbp
0x140034ee3  push    rsi
0x140034ee4  push    rdi
0x140034ee5  push    r14
0x140034ee7  push    r15
0x140034ee9  sub     rsp, 48h
0x140034eed  mov     rbx, r9
0x140034ef0  mov     esi, r8d
0x140034ef3  mov     rbp, rdx
0x140034ef6  mov     rdi, rcx
0x140034ef9  lea     r15, WPP_GLOBAL_Control
0x140034f00  mov     r14, [rsp+78h+arg_20]
0x140034f08  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f0f  cmp     rcx, r15
0x140034f12  jz      short loc_140034F47
0x140034f14  test    byte ptr [rcx+1Ch], 4
0x140034f18  jz      short loc_140034F47
0x140034f1a  cmp     byte ptr [rcx+19h], 5
0x140034f1e  jb      short loc_140034F47
0x140034f20  mov     edx, 21h ; '!'
0x140034f25  mov     [rsp+78h+var_48], r14
0x140034f2a  mov     [rsp+78h+var_50], rbx
0x140034f2f  mov     dword ptr [rsp+78h+var_58], r8d
0x140034f34  mov     r9, rbp
0x140034f37  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034f3e  mov     rcx, [rcx+10h]
0x140034f42  call    WPP_SF_qdqq
0x140034f47  mov     edx, [rdi+70h]
0x140034f4a  lea     rcx, [rsp+78h+arg_0]
0x140034f52  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140034f57  nop
0x140034f58  lock inc dword ptr [rdi+20h]
0x140034f5c  cmp     dword ptr [rdi+1Ch], 1
0x140034f60  jnz     short loc_140034F69
0x140034f62  mov     ebx, 80041033h
0x140034f67  jmp     short loc_140034F89
0x140034f69  mov     rcx, [rdi+60h]
0x140034f6d  mov     rax, [rcx]
0x140034f70  mov     [rsp+78h+var_58], r14
0x140034f75  mov     r9, rbx
0x140034f78  mov     r8d, esi
0x140034f7b  mov     rdx, rbp
0x140034f7e  mov     rax, [rax+78h]
0x140034f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034f87  mov     ebx, eax
0x140034f89  lock dec dword ptr [rdi+20h]
0x140034f8d  test    ebx, ebx
0x140034f8f  jns     short loc_140034FA2
0x140034f91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034f97  mov     edx, ebx
0x140034f99  mov     rcx, rax
0x140034f9c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fa9  cmp     rcx, r15
0x140034fac  jz      short loc_140034FD3
0x140034fae  test    byte ptr [rcx+1Ch], 4
0x140034fb2  jz      short loc_140034FD3
0x140034fb4  cmp     byte ptr [rcx+19h], 2
0x140034fb8  jb      short loc_140034FD3
0x140034fba  mov     edx, 22h ; '"'
0x140034fbf  mov     r9d, ebx
0x140034fc2  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034fc9  mov     rcx, [rcx+10h]
0x140034fcd  call    WPP_SF_d
0x140034fd2  nop
0x140034fd3  cmp     [rsp+78h+arg_0], 0
0x140034fdb  jz      short loc_140034FE4
0x140034fdd  call    cs:__imp_CoRevertToSelf
0x140034fe3  nop
0x140034fe4  mov     eax, ebx
0x140034fe6  add     rsp, 48h
0x140034fea  pop     r15
0x140034fec  pop     r14
0x140034fee  pop     rdi
0x140034fef  pop     rsi
0x140034ff0  pop     rbp
0x140034ff1  pop     rbx
0x140034ff2  retn
```
