# CInterceptor_IWbemServices_Interceptor::CreateInstanceEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x140031a40`
- end: `0x140031b4e`
- name: `?CreateInstanceEnum@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140031a40`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031ae9`
- `wbemcomn!GetMemLogObject` at `0x140031ae9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031af4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031af4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031b32`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031b32`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::CreateInstanceEnum(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  int v9; // edi
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, a3, (_DWORD)a2, a3, (char)a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))(**((_QWORD **)this + 12) + 144LL))(
           *((_QWORD *)this + 12),
           a2,
           a3,
           a4,
           a5);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140031a40  mov     rax, rsp
0x140031a43  mov     [rax+10h], rbx
0x140031a47  mov     [rax+18h], rbp
0x140031a4b  push    rsi
0x140031a4c  push    rdi
0x140031a4d  push    r14
0x140031a4f  sub     rsp, 30h
0x140031a53  mov     rdi, r9
0x140031a56  mov     esi, r8d
0x140031a59  mov     rbp, rdx
0x140031a5c  mov     rbx, rcx
0x140031a5f  lea     r14, WPP_GLOBAL_Control
0x140031a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a6d  cmp     rcx, r14
0x140031a70  jz      short loc_140031A97
0x140031a72  test    byte ptr [rcx+1Ch], 4
0x140031a76  jz      short loc_140031A97
0x140031a78  cmp     byte ptr [rcx+19h], 5
0x140031a7c  jb      short loc_140031A97
0x140031a7e  mov     edx, 27h ; '''
0x140031a83  mov     [rax-20h], r9
0x140031a87  mov     [rax-28h], r8d
0x140031a8b  mov     r9, rbp
0x140031a8e  mov     rcx, [rcx+10h]
0x140031a92  call    WPP_SF_Sdq
0x140031a97  mov     edx, [rbx+70h]
0x140031a9a  lea     rcx, [rsp+48h+arg_0]
0x140031a9f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140031aa4  nop
0x140031aa5  lock inc dword ptr [rbx+20h]
0x140031aa9  cmp     dword ptr [rbx+1Ch], 1
0x140031aad  jnz     short loc_140031AB6
0x140031aaf  mov     edi, 80041033h
0x140031ab4  jmp     short loc_140031AE1
0x140031ab6  mov     rcx, [rbx+60h]
0x140031aba  mov     rax, [rcx]
0x140031abd  mov     r10, [rax+90h]
0x140031ac4  mov     rax, [rsp+48h+arg_20]
0x140031ac9  mov     [rsp+48h+var_28], rax
0x140031ace  mov     r9, rdi
0x140031ad1  mov     r8d, esi
0x140031ad4  mov     rdx, rbp
0x140031ad7  mov     rax, r10
0x140031ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031adf  mov     edi, eax
0x140031ae1  lock dec dword ptr [rbx+20h]
0x140031ae5  test    edi, edi
0x140031ae7  jns     short loc_140031AFA
0x140031ae9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031aef  mov     edx, edi
0x140031af1  mov     rcx, rax
0x140031af4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b01  cmp     rcx, r14
0x140031b04  jz      short loc_140031B2B
0x140031b06  test    byte ptr [rcx+1Ch], 4
0x140031b0a  jz      short loc_140031B2B
0x140031b0c  cmp     byte ptr [rcx+19h], 2
0x140031b10  jb      short loc_140031B2B
0x140031b12  mov     edx, 28h ; '('
0x140031b17  mov     r9d, edi
0x140031b1a  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031b21  mov     rcx, [rcx+10h]
0x140031b25  call    WPP_SF_d
0x140031b2a  nop
0x140031b2b  cmp     [rsp+48h+arg_0], 0
0x140031b30  jz      short loc_140031B39
0x140031b32  call    cs:__imp_CoRevertToSelf
0x140031b38  nop
0x140031b39  mov     eax, edi
0x140031b3b  mov     rbx, [rsp+48h+arg_8]
0x140031b40  mov     rbp, [rsp+48h+arg_10]
0x140031b45  add     rsp, 30h
0x140031b49  pop     r14
0x140031b4b  pop     rdi
0x140031b4c  pop     rsi
0x140031b4d  retn
```
