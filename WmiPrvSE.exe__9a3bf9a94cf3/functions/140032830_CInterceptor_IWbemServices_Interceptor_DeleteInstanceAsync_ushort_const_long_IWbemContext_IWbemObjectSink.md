# CInterceptor_IWbemServices_Interceptor::DeleteInstanceAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140032830`
- end: `0x140032946`
- name: `?DeleteInstanceAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140028cfc`
- `0x140032830`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400328e4`
- `wbemcomn!GetMemLogObject` at `0x1400328e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400328ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400328ef`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032930`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140032930`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::DeleteInstanceAsync(
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
      37,
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
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 136LL))(
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
      38,
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
0x140032830  push    rbx
0x140032832  push    rbp
0x140032833  push    rsi
0x140032834  push    rdi
0x140032835  push    r14
0x140032837  push    r15
0x140032839  sub     rsp, 48h
0x14003283d  mov     rbx, r9
0x140032840  mov     esi, r8d
0x140032843  mov     rbp, rdx
0x140032846  mov     rdi, rcx
0x140032849  lea     r15, WPP_GLOBAL_Control
0x140032850  mov     r14, [rsp+78h+arg_20]
0x140032858  mov     rcx, cs:WPP_GLOBAL_Control
0x14003285f  cmp     rcx, r15
0x140032862  jz      short loc_140032897
0x140032864  test    byte ptr [rcx+1Ch], 4
0x140032868  jz      short loc_140032897
0x14003286a  cmp     byte ptr [rcx+19h], 5
0x14003286e  jb      short loc_140032897
0x140032870  mov     edx, 25h ; '%'
0x140032875  mov     [rsp+78h+var_48], r14
0x14003287a  mov     [rsp+78h+var_50], rbx
0x14003287f  mov     dword ptr [rsp+78h+var_58], r8d
0x140032884  mov     r9, rbp
0x140032887  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003288e  mov     rcx, [rcx+10h]
0x140032892  call    WPP_SF_Sdqq
0x140032897  mov     edx, [rdi+70h]
0x14003289a  lea     rcx, [rsp+78h+arg_0]
0x1400328a2  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400328a7  nop
0x1400328a8  lock inc dword ptr [rdi+20h]
0x1400328ac  cmp     dword ptr [rdi+1Ch], 1
0x1400328b0  jnz     short loc_1400328B9
0x1400328b2  mov     ebx, 80041033h
0x1400328b7  jmp     short loc_1400328DC
0x1400328b9  mov     rcx, [rdi+60h]
0x1400328bd  mov     rax, [rcx]
0x1400328c0  mov     [rsp+78h+var_58], r14
0x1400328c5  mov     r9, rbx
0x1400328c8  mov     r8d, esi
0x1400328cb  mov     rdx, rbp
0x1400328ce  mov     rax, [rax+88h]
0x1400328d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400328da  mov     ebx, eax
0x1400328dc  lock dec dword ptr [rdi+20h]
0x1400328e0  test    ebx, ebx
0x1400328e2  jns     short loc_1400328F5
0x1400328e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400328ea  mov     edx, ebx
0x1400328ec  mov     rcx, rax
0x1400328ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400328f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400328fc  cmp     rcx, r15
0x1400328ff  jz      short loc_140032926
0x140032901  test    byte ptr [rcx+1Ch], 4
0x140032905  jz      short loc_140032926
0x140032907  cmp     byte ptr [rcx+19h], 2
0x14003290b  jb      short loc_140032926
0x14003290d  mov     edx, 26h ; '&'
0x140032912  mov     r9d, ebx
0x140032915  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003291c  mov     rcx, [rcx+10h]
0x140032920  call    WPP_SF_d
0x140032925  nop
0x140032926  cmp     [rsp+78h+arg_0], 0
0x14003292e  jz      short loc_140032937
0x140032930  call    cs:__imp_CoRevertToSelf
0x140032936  nop
0x140032937  mov     eax, ebx
0x140032939  add     rsp, 48h
0x14003293d  pop     r15
0x14003293f  pop     r14
0x140032941  pop     rdi
0x140032942  pop     rsi
0x140032943  pop     rbp
0x140032944  pop     rbx
0x140032945  retn
```
