# CInterceptor_IWbemServices_Interceptor::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140031d00`
- end: `0x140031e16`
- name: `?CreateInstanceEnumAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140028cfc`
- `0x140031d00`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031db4`
- `wbemcomn!GetMemLogObject` at `0x140031db4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031dbf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031dbf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031e00`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031e00`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::CreateInstanceEnumAsync(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
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
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v13, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v10 = -2147217357;
  else
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 152LL))(
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
      42,
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
0x140031d00  push    rbx
0x140031d02  push    rbp
0x140031d03  push    rsi
0x140031d04  push    rdi
0x140031d05  push    r14
0x140031d07  push    r15
0x140031d09  sub     rsp, 48h
0x140031d0d  mov     rbx, r9
0x140031d10  mov     esi, r8d
0x140031d13  mov     rbp, rdx
0x140031d16  mov     rdi, rcx
0x140031d19  lea     r15, WPP_GLOBAL_Control
0x140031d20  mov     r14, [rsp+78h+arg_20]
0x140031d28  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d2f  cmp     rcx, r15
0x140031d32  jz      short loc_140031D67
0x140031d34  test    byte ptr [rcx+1Ch], 4
0x140031d38  jz      short loc_140031D67
0x140031d3a  cmp     byte ptr [rcx+19h], 5
0x140031d3e  jb      short loc_140031D67
0x140031d40  mov     edx, 29h ; ')'
0x140031d45  mov     [rsp+78h+var_48], r14
0x140031d4a  mov     [rsp+78h+var_50], rbx
0x140031d4f  mov     dword ptr [rsp+78h+var_58], r8d
0x140031d54  mov     r9, rbp
0x140031d57  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031d5e  mov     rcx, [rcx+10h]
0x140031d62  call    WPP_SF_Sdqq
0x140031d67  mov     edx, [rdi+70h]
0x140031d6a  lea     rcx, [rsp+78h+arg_0]
0x140031d72  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140031d77  nop
0x140031d78  lock inc dword ptr [rdi+20h]
0x140031d7c  cmp     dword ptr [rdi+1Ch], 1
0x140031d80  jnz     short loc_140031D89
0x140031d82  mov     ebx, 80041033h
0x140031d87  jmp     short loc_140031DAC
0x140031d89  mov     rcx, [rdi+60h]
0x140031d8d  mov     rax, [rcx]
0x140031d90  mov     [rsp+78h+var_58], r14
0x140031d95  mov     r9, rbx
0x140031d98  mov     r8d, esi
0x140031d9b  mov     rdx, rbp
0x140031d9e  mov     rax, [rax+98h]
0x140031da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031daa  mov     ebx, eax
0x140031dac  lock dec dword ptr [rdi+20h]
0x140031db0  test    ebx, ebx
0x140031db2  jns     short loc_140031DC5
0x140031db4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031dba  mov     edx, ebx
0x140031dbc  mov     rcx, rax
0x140031dbf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140031dcc  cmp     rcx, r15
0x140031dcf  jz      short loc_140031DF6
0x140031dd1  test    byte ptr [rcx+1Ch], 4
0x140031dd5  jz      short loc_140031DF6
0x140031dd7  cmp     byte ptr [rcx+19h], 2
0x140031ddb  jb      short loc_140031DF6
0x140031ddd  mov     edx, 2Ah ; '*'
0x140031de2  mov     r9d, ebx
0x140031de5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031dec  mov     rcx, [rcx+10h]
0x140031df0  call    WPP_SF_d
0x140031df5  nop
0x140031df6  cmp     [rsp+78h+arg_0], 0
0x140031dfe  jz      short loc_140031E07
0x140031e00  call    cs:__imp_CoRevertToSelf
0x140031e06  nop
0x140031e07  mov     eax, ebx
0x140031e09  add     rsp, 48h
0x140031e0d  pop     r15
0x140031e0f  pop     r14
0x140031e11  pop     rdi
0x140031e12  pop     rsi
0x140031e13  pop     rbp
0x140031e14  pop     rbx
0x140031e15  retn
```
