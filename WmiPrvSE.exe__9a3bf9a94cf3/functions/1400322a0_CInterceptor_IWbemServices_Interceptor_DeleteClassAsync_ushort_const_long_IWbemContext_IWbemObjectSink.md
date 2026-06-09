# CInterceptor_IWbemServices_Interceptor::DeleteClassAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1400322a0`
- end: `0x1400323b3`
- name: `?DeleteClassAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140028cfc`
- `0x1400322a0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032351`
- `wbemcomn!GetMemLogObject` at `0x140032351`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003235c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003235c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003239d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003239d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::DeleteClassAsync(
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
      25,
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
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 88LL))(
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
      26,
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
0x1400322a0  push    rbx
0x1400322a2  push    rbp
0x1400322a3  push    rsi
0x1400322a4  push    rdi
0x1400322a5  push    r14
0x1400322a7  push    r15
0x1400322a9  sub     rsp, 48h
0x1400322ad  mov     rbx, r9
0x1400322b0  mov     esi, r8d
0x1400322b3  mov     rbp, rdx
0x1400322b6  mov     rdi, rcx
0x1400322b9  lea     r15, WPP_GLOBAL_Control
0x1400322c0  mov     r14, [rsp+78h+arg_20]
0x1400322c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400322cf  cmp     rcx, r15
0x1400322d2  jz      short loc_140032307
0x1400322d4  test    byte ptr [rcx+1Ch], 4
0x1400322d8  jz      short loc_140032307
0x1400322da  cmp     byte ptr [rcx+19h], 5
0x1400322de  jb      short loc_140032307
0x1400322e0  mov     edx, 19h
0x1400322e5  mov     [rsp+78h+var_48], r14
0x1400322ea  mov     [rsp+78h+var_50], rbx
0x1400322ef  mov     dword ptr [rsp+78h+var_58], r8d
0x1400322f4  mov     r9, rbp
0x1400322f7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400322fe  mov     rcx, [rcx+10h]
0x140032302  call    WPP_SF_Sdqq
0x140032307  mov     edx, [rdi+70h]
0x14003230a  lea     rcx, [rsp+78h+arg_0]
0x140032312  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140032317  nop
0x140032318  lock inc dword ptr [rdi+20h]
0x14003231c  cmp     dword ptr [rdi+1Ch], 1
0x140032320  jnz     short loc_140032329
0x140032322  mov     ebx, 80041033h
0x140032327  jmp     short loc_140032349
0x140032329  mov     rcx, [rdi+60h]
0x14003232d  mov     rax, [rcx]
0x140032330  mov     [rsp+78h+var_58], r14
0x140032335  mov     r9, rbx
0x140032338  mov     r8d, esi
0x14003233b  mov     rdx, rbp
0x14003233e  mov     rax, [rax+58h]
0x140032342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032347  mov     ebx, eax
0x140032349  lock dec dword ptr [rdi+20h]
0x14003234d  test    ebx, ebx
0x14003234f  jns     short loc_140032362
0x140032351  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032357  mov     edx, ebx
0x140032359  mov     rcx, rax
0x14003235c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032362  mov     rcx, cs:WPP_GLOBAL_Control
0x140032369  cmp     rcx, r15
0x14003236c  jz      short loc_140032393
0x14003236e  test    byte ptr [rcx+1Ch], 4
0x140032372  jz      short loc_140032393
0x140032374  cmp     byte ptr [rcx+19h], 2
0x140032378  jb      short loc_140032393
0x14003237a  mov     edx, 1Ah
0x14003237f  mov     r9d, ebx
0x140032382  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032389  mov     rcx, [rcx+10h]
0x14003238d  call    WPP_SF_d
0x140032392  nop
0x140032393  cmp     [rsp+78h+arg_0], 0
0x14003239b  jz      short loc_1400323A4
0x14003239d  call    cs:__imp_CoRevertToSelf
0x1400323a3  nop
0x1400323a4  mov     eax, ebx
0x1400323a6  add     rsp, 48h
0x1400323aa  pop     r15
0x1400323ac  pop     r14
0x1400323ae  pop     rdi
0x1400323af  pop     rsi
0x1400323b0  pop     rbp
0x1400323b1  pop     rbx
0x1400323b2  retn
```
