# CInterceptor_IWbemServices_Interceptor::CreateClassEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140031770`
- end: `0x140031883`
- name: `?CreateClassEnumAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140028cfc`
- `0x140031770`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031821`
- `wbemcomn!GetMemLogObject` at `0x140031821`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003182c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003182c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003186d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003186d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::CreateClassEnumAsync(
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
      29,
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
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 104LL))(
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
      30,
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
0x140031770  push    rbx
0x140031772  push    rbp
0x140031773  push    rsi
0x140031774  push    rdi
0x140031775  push    r14
0x140031777  push    r15
0x140031779  sub     rsp, 48h
0x14003177d  mov     rbx, r9
0x140031780  mov     esi, r8d
0x140031783  mov     rbp, rdx
0x140031786  mov     rdi, rcx
0x140031789  lea     r15, WPP_GLOBAL_Control
0x140031790  mov     r14, [rsp+78h+arg_20]
0x140031798  mov     rcx, cs:WPP_GLOBAL_Control
0x14003179f  cmp     rcx, r15
0x1400317a2  jz      short loc_1400317D7
0x1400317a4  test    byte ptr [rcx+1Ch], 4
0x1400317a8  jz      short loc_1400317D7
0x1400317aa  cmp     byte ptr [rcx+19h], 5
0x1400317ae  jb      short loc_1400317D7
0x1400317b0  mov     edx, 1Dh
0x1400317b5  mov     [rsp+78h+var_48], r14
0x1400317ba  mov     [rsp+78h+var_50], rbx
0x1400317bf  mov     dword ptr [rsp+78h+var_58], r8d
0x1400317c4  mov     r9, rbp
0x1400317c7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400317ce  mov     rcx, [rcx+10h]
0x1400317d2  call    WPP_SF_Sdqq
0x1400317d7  mov     edx, [rdi+70h]
0x1400317da  lea     rcx, [rsp+78h+arg_0]
0x1400317e2  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400317e7  nop
0x1400317e8  lock inc dword ptr [rdi+20h]
0x1400317ec  cmp     dword ptr [rdi+1Ch], 1
0x1400317f0  jnz     short loc_1400317F9
0x1400317f2  mov     ebx, 80041033h
0x1400317f7  jmp     short loc_140031819
0x1400317f9  mov     rcx, [rdi+60h]
0x1400317fd  mov     rax, [rcx]
0x140031800  mov     [rsp+78h+var_58], r14
0x140031805  mov     r9, rbx
0x140031808  mov     r8d, esi
0x14003180b  mov     rdx, rbp
0x14003180e  mov     rax, [rax+68h]
0x140031812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031817  mov     ebx, eax
0x140031819  lock dec dword ptr [rdi+20h]
0x14003181d  test    ebx, ebx
0x14003181f  jns     short loc_140031832
0x140031821  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031827  mov     edx, ebx
0x140031829  mov     rcx, rax
0x14003182c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031832  mov     rcx, cs:WPP_GLOBAL_Control
0x140031839  cmp     rcx, r15
0x14003183c  jz      short loc_140031863
0x14003183e  test    byte ptr [rcx+1Ch], 4
0x140031842  jz      short loc_140031863
0x140031844  cmp     byte ptr [rcx+19h], 2
0x140031848  jb      short loc_140031863
0x14003184a  mov     edx, 1Eh
0x14003184f  mov     r9d, ebx
0x140031852  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031859  mov     rcx, [rcx+10h]
0x14003185d  call    WPP_SF_d
0x140031862  nop
0x140031863  cmp     [rsp+78h+arg_0], 0
0x14003186b  jz      short loc_140031874
0x14003186d  call    cs:__imp_CoRevertToSelf
0x140031873  nop
0x140031874  mov     eax, ebx
0x140031876  add     rsp, 48h
0x14003187a  pop     r15
0x14003187c  pop     r14
0x14003187e  pop     rdi
0x14003187f  pop     rsi
0x140031880  pop     rbp
0x140031881  pop     rbx
0x140031882  retn
```
