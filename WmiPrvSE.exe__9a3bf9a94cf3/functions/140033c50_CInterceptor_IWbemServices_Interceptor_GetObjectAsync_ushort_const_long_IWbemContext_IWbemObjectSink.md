# CInterceptor_IWbemServices_Interceptor::GetObjectAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140033c50`
- end: `0x140033d63`
- name: `?GetObjectAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140028cfc`
- `0x140033c50`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033d01`
- `wbemcomn!GetMemLogObject` at `0x140033d01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033d0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033d0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033d4d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033d4d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::GetObjectAsync(
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
      17,
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
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 56LL))(
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
      18,
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
0x140033c50  push    rbx
0x140033c52  push    rbp
0x140033c53  push    rsi
0x140033c54  push    rdi
0x140033c55  push    r14
0x140033c57  push    r15
0x140033c59  sub     rsp, 48h
0x140033c5d  mov     rbx, r9
0x140033c60  mov     esi, r8d
0x140033c63  mov     rbp, rdx
0x140033c66  mov     rdi, rcx
0x140033c69  lea     r15, WPP_GLOBAL_Control
0x140033c70  mov     r14, [rsp+78h+arg_20]
0x140033c78  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c7f  cmp     rcx, r15
0x140033c82  jz      short loc_140033CB7
0x140033c84  test    byte ptr [rcx+1Ch], 4
0x140033c88  jz      short loc_140033CB7
0x140033c8a  cmp     byte ptr [rcx+19h], 5
0x140033c8e  jb      short loc_140033CB7
0x140033c90  mov     edx, 11h
0x140033c95  mov     [rsp+78h+var_48], r14
0x140033c9a  mov     [rsp+78h+var_50], rbx
0x140033c9f  mov     dword ptr [rsp+78h+var_58], r8d
0x140033ca4  mov     r9, rbp
0x140033ca7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033cae  mov     rcx, [rcx+10h]
0x140033cb2  call    WPP_SF_Sdqq
0x140033cb7  mov     edx, [rdi+70h]
0x140033cba  lea     rcx, [rsp+78h+arg_0]
0x140033cc2  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140033cc7  nop
0x140033cc8  lock inc dword ptr [rdi+20h]
0x140033ccc  cmp     dword ptr [rdi+1Ch], 1
0x140033cd0  jnz     short loc_140033CD9
0x140033cd2  mov     ebx, 80041033h
0x140033cd7  jmp     short loc_140033CF9
0x140033cd9  mov     rcx, [rdi+60h]
0x140033cdd  mov     rax, [rcx]
0x140033ce0  mov     [rsp+78h+var_58], r14
0x140033ce5  mov     r9, rbx
0x140033ce8  mov     r8d, esi
0x140033ceb  mov     rdx, rbp
0x140033cee  mov     rax, [rax+38h]
0x140033cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033cf7  mov     ebx, eax
0x140033cf9  lock dec dword ptr [rdi+20h]
0x140033cfd  test    ebx, ebx
0x140033cff  jns     short loc_140033D12
0x140033d01  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140033d07  mov     edx, ebx
0x140033d09  mov     rcx, rax
0x140033d0c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140033d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d19  cmp     rcx, r15
0x140033d1c  jz      short loc_140033D43
0x140033d1e  test    byte ptr [rcx+1Ch], 4
0x140033d22  jz      short loc_140033D43
0x140033d24  cmp     byte ptr [rcx+19h], 2
0x140033d28  jb      short loc_140033D43
0x140033d2a  mov     edx, 12h
0x140033d2f  mov     r9d, ebx
0x140033d32  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033d39  mov     rcx, [rcx+10h]
0x140033d3d  call    WPP_SF_d
0x140033d42  nop
0x140033d43  cmp     [rsp+78h+arg_0], 0
0x140033d4b  jz      short loc_140033D54
0x140033d4d  call    cs:__imp_CoRevertToSelf
0x140033d53  nop
0x140033d54  mov     eax, ebx
0x140033d56  add     rsp, 48h
0x140033d5a  pop     r15
0x140033d5c  pop     r14
0x140033d5e  pop     rdi
0x140033d5f  pop     rsi
0x140033d60  pop     rbp
0x140033d61  pop     rbx
0x140033d62  retn
```
