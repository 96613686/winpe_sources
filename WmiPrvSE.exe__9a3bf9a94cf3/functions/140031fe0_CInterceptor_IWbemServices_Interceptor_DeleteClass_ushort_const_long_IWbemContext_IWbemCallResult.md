# CInterceptor_IWbemServices_Interceptor::DeleteClass(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140031fe0`
- end: `0x1400320eb`
- name: `?DeleteClass@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140031fe0`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032086`
- `wbemcomn!GetMemLogObject` at `0x140032086`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032091`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032091`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400320cf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400320cf`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::DeleteClass(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  int v9; // edi
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, a3, (_DWORD)a2, a3, (char)a4);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v12, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v9 = -2147217357;
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 80LL))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  if ( v12 )
    CoRevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140031fe0  mov     rax, rsp
0x140031fe3  mov     [rax+10h], rbx
0x140031fe7  mov     [rax+18h], rbp
0x140031feb  push    rsi
0x140031fec  push    rdi
0x140031fed  push    r14
0x140031fef  sub     rsp, 30h
0x140031ff3  mov     rdi, r9
0x140031ff6  mov     esi, r8d
0x140031ff9  mov     rbp, rdx
0x140031ffc  mov     rbx, rcx
0x140031fff  lea     r14, WPP_GLOBAL_Control
0x140032006  mov     rcx, cs:WPP_GLOBAL_Control
0x14003200d  cmp     rcx, r14
0x140032010  jz      short loc_140032037
0x140032012  test    byte ptr [rcx+1Ch], 4
0x140032016  jz      short loc_140032037
0x140032018  cmp     byte ptr [rcx+19h], 5
0x14003201c  jb      short loc_140032037
0x14003201e  mov     edx, 17h
0x140032023  mov     [rax-20h], r9
0x140032027  mov     [rax-28h], r8d
0x14003202b  mov     r9, rbp
0x14003202e  mov     rcx, [rcx+10h]
0x140032032  call    WPP_SF_Sdq
0x140032037  mov     edx, [rbx+70h]
0x14003203a  lea     rcx, [rsp+48h+arg_0]
0x14003203f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140032044  nop
0x140032045  lock inc dword ptr [rbx+20h]
0x140032049  cmp     dword ptr [rbx+1Ch], 1
0x14003204d  jnz     short loc_140032056
0x14003204f  mov     edi, 80041033h
0x140032054  jmp     short loc_14003207E
0x140032056  mov     rcx, [rbx+60h]
0x14003205a  mov     rax, [rcx]
0x14003205d  mov     r10, [rax+50h]
0x140032061  mov     rax, [rsp+48h+arg_20]
0x140032066  mov     [rsp+48h+var_28], rax
0x14003206b  mov     r9, rdi
0x14003206e  mov     r8d, esi
0x140032071  mov     rdx, rbp
0x140032074  mov     rax, r10
0x140032077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003207c  mov     edi, eax
0x14003207e  lock dec dword ptr [rbx+20h]
0x140032082  test    edi, edi
0x140032084  jns     short loc_140032097
0x140032086  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003208c  mov     edx, edi
0x14003208e  mov     rcx, rax
0x140032091  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032097  mov     rcx, cs:WPP_GLOBAL_Control
0x14003209e  cmp     rcx, r14
0x1400320a1  jz      short loc_1400320C8
0x1400320a3  test    byte ptr [rcx+1Ch], 4
0x1400320a7  jz      short loc_1400320C8
0x1400320a9  cmp     byte ptr [rcx+19h], 2
0x1400320ad  jb      short loc_1400320C8
0x1400320af  mov     edx, 18h
0x1400320b4  mov     r9d, edi
0x1400320b7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400320be  mov     rcx, [rcx+10h]
0x1400320c2  call    WPP_SF_d
0x1400320c7  nop
0x1400320c8  cmp     [rsp+48h+arg_0], 0
0x1400320cd  jz      short loc_1400320D6
0x1400320cf  call    cs:__imp_CoRevertToSelf
0x1400320d5  nop
0x1400320d6  mov     eax, edi
0x1400320d8  mov     rbx, [rsp+48h+arg_8]
0x1400320dd  mov     rbp, [rsp+48h+arg_10]
0x1400320e2  add     rsp, 30h
0x1400320e6  pop     r14
0x1400320e8  pop     rdi
0x1400320e9  pop     rsi
0x1400320ea  retn
```
