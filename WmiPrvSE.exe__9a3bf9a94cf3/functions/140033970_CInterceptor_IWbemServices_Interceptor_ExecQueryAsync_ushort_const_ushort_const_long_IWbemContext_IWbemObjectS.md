# CInterceptor_IWbemServices_Interceptor::ExecQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140033970`
- end: `0x140033aa3`
- name: `?ExecQueryAsync@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x140029824`
- `0x140033970`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033a38`
- `wbemcomn!GetMemLogObject` at `0x140033a38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033a43`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033a43`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033a81`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140033a81`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecQueryAsync(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6)
{
  struct IWbemObjectSink *v10; // r14
  struct IWbemContext *v11; // r15
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+70h] [rbp+8h] BYREF

  v10 = a6;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a5,
      (char)a6);
  }
  ImpersonateClientHelper::ImpersonateClientHelper(&v15, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v12 = -2147217357;
  else
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 12) + 168LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            v11,
            v10);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v12 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  if ( v15 )
    CoRevertToSelf();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140033970  mov     rax, rsp
0x140033973  mov     [rax+10h], rbx
0x140033977  mov     [rax+18h], rbp
0x14003397b  push    rsi
0x14003397c  push    rdi
0x14003397d  push    r12
0x14003397f  push    r14
0x140033981  push    r15
0x140033983  sub     rsp, 40h
0x140033987  mov     ebx, r9d
0x14003398a  mov     rsi, r8
0x14003398d  mov     rbp, rdx
0x140033990  mov     rdi, rcx
0x140033993  lea     r12, WPP_GLOBAL_Control
0x14003399a  mov     r14, [rsp+68h+arg_28]
0x1400339a2  mov     r15, [rsp+68h+arg_20]
0x1400339aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400339b1  cmp     rcx, r12
0x1400339b4  jz      short loc_1400339E9
0x1400339b6  test    byte ptr [rcx+1Ch], 4
0x1400339ba  jz      short loc_1400339E9
0x1400339bc  cmp     byte ptr [rcx+19h], 5
0x1400339c0  jb      short loc_1400339E9
0x1400339c2  mov     edx, 2Dh ; '-'
0x1400339c7  mov     [rax-30h], r14
0x1400339cb  mov     [rax-38h], r15
0x1400339cf  mov     [rax-40h], ebx
0x1400339d2  mov     [rax-48h], r8
0x1400339d6  mov     r9, rbp
0x1400339d9  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400339e0  mov     rcx, [rcx+10h]
0x1400339e4  call    WPP_SF_SSdqq
0x1400339e9  mov     edx, [rdi+70h]
0x1400339ec  lea     rcx, [rsp+68h+arg_0]
0x1400339f1  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x1400339f6  nop
0x1400339f7  lock inc dword ptr [rdi+20h]
0x1400339fb  cmp     dword ptr [rdi+1Ch], 1
0x1400339ff  jnz     short loc_140033A08
0x140033a01  mov     ebx, 80041033h
0x140033a06  jmp     short loc_140033A30
0x140033a08  mov     rcx, [rdi+60h]
0x140033a0c  mov     rax, [rcx]
0x140033a0f  mov     [rsp+68h+var_40], r14
0x140033a14  mov     [rsp+68h+var_48], r15
0x140033a19  mov     r9d, ebx
0x140033a1c  mov     r8, rsi
0x140033a1f  mov     rdx, rbp
0x140033a22  mov     rax, [rax+0A8h]
0x140033a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a2e  mov     ebx, eax
0x140033a30  lock dec dword ptr [rdi+20h]
0x140033a34  test    ebx, ebx
0x140033a36  jns     short loc_140033A49
0x140033a38  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140033a3e  mov     edx, ebx
0x140033a40  mov     rcx, rax
0x140033a43  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140033a49  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a50  cmp     rcx, r12
0x140033a53  jz      short loc_140033A7A
0x140033a55  test    byte ptr [rcx+1Ch], 4
0x140033a59  jz      short loc_140033A7A
0x140033a5b  cmp     byte ptr [rcx+19h], 2
0x140033a5f  jb      short loc_140033A7A
0x140033a61  mov     edx, 2Eh ; '.'
0x140033a66  mov     r9d, ebx
0x140033a69  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033a70  mov     rcx, [rcx+10h]
0x140033a74  call    WPP_SF_d
0x140033a79  nop
0x140033a7a  cmp     [rsp+68h+arg_0], 0
0x140033a7f  jz      short loc_140033A88
0x140033a81  call    cs:__imp_CoRevertToSelf
0x140033a87  nop
0x140033a88  mov     eax, ebx
0x140033a8a  lea     r11, [rsp+68h+var_28]
0x140033a8f  mov     rbx, [r11+38h]
0x140033a93  mov     rbp, [r11+40h]
0x140033a97  mov     rsp, r11
0x140033a9a  pop     r15
0x140033a9c  pop     r14
0x140033a9e  pop     r12
0x140033aa0  pop     rdi
0x140033aa1  pop     rsi
0x140033aa2  retn
```
