# CInterceptor_IWbemServices_Interceptor::QueryObjectSink(long,IWbemObjectSink * *)

- ea: `0x1400351f0`
- end: `0x1400352ae`
- name: `?QueryObjectSink@CInterceptor_IWbemServices_Interceptor@@UEAAJJPEAPEAUIWbemObjectSink@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, int, struct IWbemObjectSink **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140027afc`
- `0x1400351f0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140035245`
- `wbemcomn!GetMemLogObject` at `0x140035245`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140035250`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140035250`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140035295`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140035295`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::QueryObjectSink(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned int a2,
        struct IWbemObjectSink **a3)
{
  int v6; // ebx
  CMemoryLog *MemLogObject; // rax
  int v9; // [rsp+30h] [rbp+8h] BYREF

  ImpersonateClientHelper::ImpersonateClientHelper(&v9, *((_DWORD *)this + 28));
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
    v6 = -2147217357;
  else
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemObjectSink **))(**((_QWORD **)this + 12) + 40LL))(
           *((_QWORD *)this + 12),
           a2,
           a3);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v6);
  }
  if ( v9 )
    CoRevertToSelf();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400351f0  mov     [rsp+arg_8], rbx
0x1400351f5  mov     [rsp+arg_10], rsi
0x1400351fa  push    rdi
0x1400351fb  sub     rsp, 20h
0x1400351ff  mov     rbx, r8
0x140035202  mov     esi, edx
0x140035204  mov     rdi, rcx
0x140035207  mov     edx, [rcx+70h]
0x14003520a  lea     rcx, [rsp+28h+arg_0]
0x14003520f  call    ??0ImpersonateClientHelper@@QEAA@W4Enum_ThreadingModel@@@Z; ImpersonateClientHelper::ImpersonateClientHelper(Enum_ThreadingModel)
0x140035214  nop
0x140035215  lock inc dword ptr [rdi+20h]
0x140035219  cmp     dword ptr [rdi+1Ch], 1
0x14003521d  jnz     short loc_140035226
0x14003521f  mov     ebx, 80041033h
0x140035224  jmp     short loc_14003523D
0x140035226  mov     rcx, [rdi+60h]
0x14003522a  mov     rax, [rcx]
0x14003522d  mov     r8, rbx
0x140035230  mov     edx, esi
0x140035232  mov     rax, [rax+28h]
0x140035236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003523b  mov     ebx, eax
0x14003523d  lock dec dword ptr [rdi+20h]
0x140035241  test    ebx, ebx
0x140035243  jns     short loc_140035256
0x140035245  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003524b  mov     edx, ebx
0x14003524d  mov     rcx, rax
0x140035250  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140035256  lea     rax, WPP_GLOBAL_Control
0x14003525d  mov     rcx, cs:WPP_GLOBAL_Control
0x140035264  cmp     rcx, rax
0x140035267  jz      short loc_14003528E
0x140035269  test    byte ptr [rcx+1Ch], 4
0x14003526d  jz      short loc_14003528E
0x14003526f  cmp     byte ptr [rcx+19h], 2
0x140035273  jb      short loc_14003528E
0x140035275  mov     edx, 0Eh
0x14003527a  mov     r9d, ebx
0x14003527d  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140035284  mov     rcx, [rcx+10h]
0x140035288  call    WPP_SF_d
0x14003528d  nop
0x14003528e  cmp     [rsp+28h+arg_0], 0
0x140035293  jz      short loc_14003529C
0x140035295  call    cs:__imp_CoRevertToSelf
0x14003529b  nop
0x14003529c  mov     eax, ebx
0x14003529e  mov     rbx, [rsp+28h+arg_8]
0x1400352a3  mov     rsi, [rsp+28h+arg_10]
0x1400352a8  add     rsp, 20h
0x1400352ac  pop     rdi
0x1400352ad  retn
```
