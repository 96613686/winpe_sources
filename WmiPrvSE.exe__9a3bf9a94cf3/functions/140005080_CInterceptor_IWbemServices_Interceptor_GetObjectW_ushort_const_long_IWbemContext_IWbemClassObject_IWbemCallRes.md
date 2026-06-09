# CInterceptor_IWbemServices_Interceptor::GetObjectW(ushort * const,long,IWbemContext *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x140005080`
- end: `0x1400051f0`
- name: `?GetObjectW@CInterceptor_IWbemServices_Interceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAPEAUIWbemCallResult@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_Interceptor *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140005080`
- `0x1400053dc`
- `0x1400234b8`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400051d9`
- `wbemcomn!GetMemLogObject` at `0x1400051d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400051e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400051e4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140005187`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140005187`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000513f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000513f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInterceptor_IWbemServices_Interceptor::GetObjectW(
        CInterceptor_IWbemServices_Interceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemClassObject **a5,
        struct IWbemCallResult **a6)
{
  BOOL v10; // ebx
  int v11; // esi
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, a3, (_DWORD)a2, a3, (char)a4);
  }
  v10 = 0;
  if ( !*((_DWORD *)this + 28) && (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 < 2 )
    v10 = CoImpersonateClient() >= 0;
  _InterlockedAdd((volatile signed __int32 *)this + 8, 1u);
  if ( *((_DWORD *)this + 7) == 1 )
    v11 = -2147217357;
  else
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemClassObject **, struct IWbemCallResult **))(**((_QWORD **)this + 12) + 48LL))(
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
      16,
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
0x140005080  mov     [rsp+arg_8], rbx
0x140005085  mov     [rsp+arg_10], rbp
0x14000508a  push    rsi
0x14000508b  push    rdi
0x14000508c  push    r12
0x14000508e  push    r14
0x140005090  push    r15
0x140005092  sub     rsp, 40h
0x140005096  mov     rsi, r9
0x140005099  mov     ebp, r8d
0x14000509c  mov     r14, rdx
0x14000509f  mov     rdi, rcx
0x1400050a2  lea     r12, WPP_GLOBAL_Control
0x1400050a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050b0  cmp     rcx, r12
0x1400050b3  jnz     loc_14000519C
0x1400050b9  xor     ebx, ebx
0x1400050bb  mov     [rsp+68h+arg_0], ebx
0x1400050bf  lea     r15d, [rbx+1]
0x1400050c3  cmp     [rdi+70h], ebx
0x1400050c6  jnz     short loc_1400050DF
0x1400050c8  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400050cd  sub     eax, 3
0x1400050d0  jz      loc_140005187
0x1400050d6  cmp     eax, r15d
0x1400050d9  jz      loc_140005187
0x1400050df  lock add [rdi+20h], r15d
0x1400050e4  cmp     [rdi+1Ch], r15d
0x1400050e8  jz      loc_1400051CF
0x1400050ee  mov     rcx, [rdi+60h]
0x1400050f2  mov     rax, [rcx]
0x1400050f5  mov     rdx, [rsp+68h+arg_28]
0x1400050fd  mov     [rsp+68h+var_40], rdx
0x140005102  mov     rdx, [rsp+68h+arg_20]
0x14000510a  mov     [rsp+68h+var_48], rdx
0x14000510f  mov     r9, rsi
0x140005112  mov     r8d, ebp
0x140005115  mov     rdx, r14
0x140005118  mov     rax, [rax+30h]
0x14000511c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005121  mov     esi, eax
0x140005123  lock dec dword ptr [rdi+20h]
0x140005127  test    esi, esi
0x140005129  js      loc_1400051D9
0x14000512f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005136  cmp     rcx, r12
0x140005139  jnz     short loc_140005161
0x14000513b  test    ebx, ebx
0x14000513d  jz      short loc_140005146
0x14000513f  call    cs:__imp_CoRevertToSelf
0x140005145  nop
0x140005146  mov     eax, esi
0x140005148  lea     r11, [rsp+68h+var_28]
0x14000514d  mov     rbx, [r11+38h]
0x140005151  mov     rbp, [r11+40h]
0x140005155  mov     rsp, r11
0x140005158  pop     r15
0x14000515a  pop     r14
0x14000515c  pop     r12
0x14000515e  pop     rdi
0x14000515f  pop     rsi
0x140005160  retn
0x140005161  test    byte ptr [rcx+1Ch], 4
0x140005165  jz      short loc_14000513B
0x140005167  cmp     byte ptr [rcx+19h], 2
0x14000516b  jb      short loc_14000513B
0x14000516d  mov     edx, 10h
0x140005172  mov     r9d, esi
0x140005175  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14000517c  mov     rcx, [rcx+10h]
0x140005180  call    WPP_SF_d
0x140005185  jmp     short loc_14000513B
0x140005187  call    cs:__imp_CoImpersonateClient
0x14000518d  test    eax, eax
0x14000518f  cmovns  ebx, r15d
0x140005193  mov     [rsp+68h+arg_0], ebx
0x140005197  jmp     loc_1400050DF
0x14000519c  test    byte ptr [rcx+1Ch], 4
0x1400051a0  jz      loc_1400050B9
0x1400051a6  cmp     byte ptr [rcx+19h], 5
0x1400051aa  jb      loc_1400050B9
0x1400051b0  mov     edx, 0Fh
0x1400051b5  mov     [rsp+68h+var_40], rsi
0x1400051ba  mov     dword ptr [rsp+68h+var_48], ebp
0x1400051be  mov     r9, r14
0x1400051c1  mov     rcx, [rcx+10h]
0x1400051c5  call    WPP_SF_Sdq
0x1400051ca  jmp     loc_1400050B9
0x1400051cf  mov     esi, 80041033h
0x1400051d4  jmp     loc_140005123
0x1400051d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400051df  mov     edx, esi
0x1400051e1  mov     rcx, rax
0x1400051e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400051ea  jmp     loc_14000512F
```
