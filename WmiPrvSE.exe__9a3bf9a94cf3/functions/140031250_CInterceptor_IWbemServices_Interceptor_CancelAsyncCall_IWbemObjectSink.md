# CInterceptor_IWbemServices_Interceptor::CancelAsyncCall(IWbemObjectSink *)

- ea: `0x140031250`
- end: `0x14003133a`
- name: `?CancelAsyncCall@CInterceptor_IWbemServices_Interceptor@@UEAAJPEAUIWbemObjectSink@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140030438`
- `0x140031250`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400312d8`
- `wbemcomn!GetMemLogObject` at `0x1400312d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400312e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400312e3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031321`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031321`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::CancelAsyncCall(
        CInterceptor_IWbemServices_Interceptor *this,
        struct IWbemObjectSink *a2)
{
  int v4; // edi
  CMemoryLog *MemLogObject; // rax
  int v7; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, a2);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v7, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v4 = -2147217357;
  else
    v4 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 32LL))(
           *((_QWORD *)this + 12),
           a2);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v4 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v4);
  }
  if ( v7 )
    CoRevertToSelf();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140031250  mov     [rsp+arg_8], rbx
0x140031255  mov     [rsp+arg_10], rsi
0x14003125a  push    rdi
0x14003125b  sub     rsp, 20h
0x14003125f  mov     rdi, rdx
0x140031262  mov     rbx, rcx
0x140031265  lea     rsi, WPP_GLOBAL_Control
0x14003126c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031273  cmp     rcx, rsi
0x140031276  jz      short loc_14003129C
0x140031278  test    byte ptr [rcx+1Ch], 4
0x14003127c  jz      short loc_14003129C
0x14003127e  cmp     byte ptr [rcx+19h], 5
0x140031282  jb      short loc_14003129C
0x140031284  mov     edx, 0Ch
0x140031289  mov     r9, rdi
0x14003128c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031293  mov     rcx, [rcx+10h]
0x140031297  call    WPP_SF_q
0x14003129c  mov     edx, [rbx+70h]
0x14003129f  lea     rcx, [rsp+28h+arg_0]
0x1400312a4  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400312a9  nop
0x1400312aa  lock inc dword ptr [rbx+20h]
0x1400312ae  cmp     dword ptr [rbx+1Ch], 1
0x1400312b2  jnz     short loc_1400312BB
0x1400312b4  mov     edi, 80041033h
0x1400312b9  jmp     short loc_1400312D0
0x1400312bb  mov     rcx, [rbx+60h]
0x1400312bf  mov     rax, [rcx]
0x1400312c2  mov     rdx, rdi
0x1400312c5  mov     rax, [rax+20h]
0x1400312c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400312ce  mov     edi, eax
0x1400312d0  lock dec dword ptr [rbx+20h]
0x1400312d4  test    edi, edi
0x1400312d6  jns     short loc_1400312E9
0x1400312d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400312de  mov     edx, edi
0x1400312e0  mov     rcx, rax
0x1400312e3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400312e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400312f0  cmp     rcx, rsi
0x1400312f3  jz      short loc_14003131A
0x1400312f5  test    byte ptr [rcx+1Ch], 4
0x1400312f9  jz      short loc_14003131A
0x1400312fb  cmp     byte ptr [rcx+19h], 2
0x1400312ff  jb      short loc_14003131A
0x140031301  mov     edx, 0Dh
0x140031306  mov     r9d, edi
0x140031309  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031310  mov     rcx, [rcx+10h]
0x140031314  call    WPP_SF_d
0x140031319  nop
0x14003131a  cmp     [rsp+28h+arg_0], 0
0x14003131f  jz      short loc_140031328
0x140031321  call    cs:__imp_CoRevertToSelf
0x140031327  nop
0x140031328  mov     eax, edi
0x14003132a  mov     rbx, [rsp+28h+arg_8]
0x14003132f  mov     rsi, [rsp+28h+arg_10]
0x140031334  add     rsp, 20h
0x140031338  pop     rdi
0x140031339  retn
```
