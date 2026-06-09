# CInterceptor_IWbemServices_Interceptor::ExecQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1400260d0`
- end: `0x14002623c`
- name: `?ExecQuery@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400234b8`
- `0x1400260d0`
- `0x140035b84`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140026225`
- `wbemcomn!GetMemLogObject` at `0x140026225`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140026230`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140026230`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400261a2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400261a2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026188`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026188`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::ExecQuery(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IEnumWbemClassObject **a6)
{
  BOOL v10; // ebx
  int v11; // esi
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, (_DWORD)a3, (_DWORD)a2, (__int64)a3, a4, (char)a5);
  }
  v10 = 0;
  if ( !*((_DWORD *)this + 28) && (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 < 2 )
    v10 = CoImpersonateClient() >= 0;
  _InterlockedAdd((volatile signed __int32 *)this + 8, 1u);
  if ( *((_DWORD *)this + 7) == 1 )
    v11 = -2147217357;
  else
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))(**((_QWORD **)this + 12) + 160LL))(
            *((_QWORD *)this + 12),
            a2,
            a3,
            a4,
            a5,
            a6);
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  if ( v10 )
    CoRevertToSelf();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400260d0  push    rbx
0x1400260d2  push    rbp
0x1400260d3  push    rsi
0x1400260d4  push    rdi
0x1400260d5  push    r12
0x1400260d7  push    r13
0x1400260d9  push    r14
0x1400260db  push    r15
0x1400260dd  sub     rsp, 48h
0x1400260e1  mov     esi, r9d
0x1400260e4  mov     rbp, r8
0x1400260e7  mov     r14, rdx
0x1400260ea  mov     rdi, rcx
0x1400260ed  lea     r13, WPP_GLOBAL_Control
0x1400260f4  mov     r15, [rsp+88h+arg_20]
0x1400260fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140026103  cmp     rcx, r13
0x140026106  jnz     loc_1400261BA
0x14002610c  xor     ebx, ebx
0x14002610e  mov     [rsp+88h+arg_0], ebx
0x140026115  lea     r12d, [rbx+1]
0x140026119  cmp     [rdi+70h], ebx
0x14002611c  jnz     short loc_14002612D
0x14002611e  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140026123  sub     eax, 3
0x140026126  jz      short loc_1400261A2
0x140026128  cmp     eax, r12d
0x14002612b  jz      short loc_1400261A2
0x14002612d  lock add [rdi+20h], r12d
0x140026132  cmp     [rdi+1Ch], r12d
0x140026136  jz      loc_14002621B
0x14002613c  mov     rcx, [rdi+60h]
0x140026140  mov     rax, [rcx]
0x140026143  mov     rdx, [rsp+88h+arg_28]
0x14002614b  mov     [rsp+88h+var_60], rdx
0x140026150  mov     [rsp+88h+var_68], r15
0x140026155  mov     r9d, esi
0x140026158  mov     r8, rbp
0x14002615b  mov     rdx, r14
0x14002615e  mov     rax, [rax+0A0h]
0x140026165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002616a  mov     esi, eax
0x14002616c  lock dec dword ptr [rdi+20h]
0x140026170  test    esi, esi
0x140026172  js      loc_140026225
0x140026178  mov     rcx, cs:WPP_GLOBAL_Control
0x14002617f  cmp     rcx, r13
0x140026182  jnz     short loc_1400261F2
0x140026184  test    ebx, ebx
0x140026186  jz      short loc_14002618F
0x140026188  call    cs:__imp_CoRevertToSelf
0x14002618e  nop
0x14002618f  mov     eax, esi
0x140026191  add     rsp, 48h
0x140026195  pop     r15
0x140026197  pop     r14
0x140026199  pop     r13
0x14002619b  pop     r12
0x14002619d  pop     rdi
0x14002619e  pop     rsi
0x14002619f  pop     rbp
0x1400261a0  pop     rbx
0x1400261a1  retn
0x1400261a2  call    cs:__imp_CoImpersonateClient
0x1400261a8  test    eax, eax
0x1400261aa  cmovns  ebx, r12d
0x1400261ae  mov     [rsp+88h+arg_0], ebx
0x1400261b5  jmp     loc_14002612D
0x1400261ba  test    byte ptr [rcx+1Ch], 4
0x1400261be  jz      loc_14002610C
0x1400261c4  cmp     byte ptr [rcx+19h], 5
0x1400261c8  jb      loc_14002610C
0x1400261ce  mov     edx, 2Bh ; '+'
0x1400261d3  mov     [rsp+88h+var_58], r15
0x1400261d8  mov     dword ptr [rsp+88h+var_60], esi
0x1400261dc  mov     [rsp+88h+var_68], rbp
0x1400261e1  mov     r9, r14
0x1400261e4  mov     rcx, [rcx+10h]
0x1400261e8  call    WPP_SF_SSdq
0x1400261ed  jmp     loc_14002610C
0x1400261f2  test    byte ptr [rcx+1Ch], 4
0x1400261f6  jz      short loc_140026184
0x1400261f8  cmp     byte ptr [rcx+19h], 2
0x1400261fc  jb      short loc_140026184
0x1400261fe  mov     edx, 2Ch ; ','
0x140026203  mov     r9d, esi
0x140026206  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14002620d  mov     rcx, [rcx+10h]
0x140026211  call    WPP_SF_d
0x140026216  jmp     loc_140026184
0x14002621b  mov     esi, 80041033h
0x140026220  jmp     loc_14002616C
0x140026225  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002622b  mov     edx, esi
0x14002622d  mov     rcx, rax
0x140026230  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140026236  jmp     loc_140026178
```
