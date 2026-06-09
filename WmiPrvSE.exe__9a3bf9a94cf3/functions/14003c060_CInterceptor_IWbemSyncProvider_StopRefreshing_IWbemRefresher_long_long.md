# CInterceptor_IWbemSyncProvider::StopRefreshing(IWbemRefresher *,long,long)

- ea: `0x14003c060`
- end: `0x14003c1e0`
- name: `?StopRefreshing@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemRefresher@@JJ@Z`
- size: `384`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemRefresher *, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x14003c060`
- `0x14003c54c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003c14f`
- `wbemcomn!GetMemLogObject` at `0x14003c182`
- `wbemcomn!GetMemLogObject` at `0x14003c14f`
- `wbemcomn!GetMemLogObject` at `0x14003c182`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c15a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c192`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c15a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c192`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003c131`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003c131`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::StopRefreshing(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemRefresher *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v5; // esi
  int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  CMemoryLog *v13; // rax
  struct IServerSecurity *v15; // [rsp+30h] [rbp-28h] BYREF
  struct IUnknown *ppInterface; // [rsp+38h] [rbp-20h] BYREF
  int v17; // [rsp+60h] [rbp+8h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3, a4);
  }
  if ( *((_QWORD *)this + 35)
    && (v17 = 0,
        ppInterface = 0,
        v15 = 0,
        (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v15, &v17, 0) >= 0) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 29);
    ++*((_QWORD *)this + 89);
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemRefresher *, _QWORD, _QWORD))(**((_QWORD **)this + 35) + 48LL))(
           *((_QWORD *)this + 35),
           a2,
           v5,
           a4);
    CoRevertToSelf();
    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v15, v17);
    if ( v8 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 162;
      v12 = (unsigned int)v8;
LABEL_19:
      WPP_SF_d(v10[2], v11, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v12);
    }
  }
  else
  {
    v13 = GetMemLogObject();
    v8 = -2147217372;
    CMemoryLog::Write(v13, -2147217372);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 163;
      v12 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003c060  mov     rax, rsp
0x14003c063  mov     [rax+10h], rbx
0x14003c067  mov     [rax+18h], rbp
0x14003c06b  push    rsi
0x14003c06c  push    rdi
0x14003c06d  push    r12
0x14003c06f  sub     rsp, 40h
0x14003c073  mov     edi, r9d
0x14003c076  mov     esi, r8d
0x14003c079  mov     rbp, rdx
0x14003c07c  mov     rbx, rcx
0x14003c07f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c086  lea     r12, WPP_GLOBAL_Control
0x14003c08d  cmp     rcx, r12
0x14003c090  jz      short loc_14003C0B2
0x14003c092  test    byte ptr [rcx+1Ch], 4
0x14003c096  jz      short loc_14003C0B2
0x14003c098  cmp     byte ptr [rcx+19h], 5
0x14003c09c  jb      short loc_14003C0B2
0x14003c09e  mov     rcx, [rcx+10h]
0x14003c0a2  mov     [rax-30h], r9d
0x14003c0a6  mov     r9, rdx
0x14003c0a9  mov     [rax-38h], r8d
0x14003c0ad  call    WPP_SF_qdd
0x14003c0b2  cmp     qword ptr [rbx+118h], 0
0x14003c0ba  jz      loc_14003C182
0x14003c0c0  xor     r9d, r9d; unsigned int *
0x14003c0c3  mov     [rsp+58h+arg_0], 0
0x14003c0cb  lea     r8, [rsp+58h+arg_0]; int *
0x14003c0d0  mov     [rsp+58h+ppInterface], 0
0x14003c0d9  lea     rdx, [rsp+58h+var_28]; struct IServerSecurity **
0x14003c0de  mov     [rsp+58h+var_28], 0
0x14003c0e7  lea     rcx, [rsp+58h+ppInterface]; ppInterface
0x14003c0ec  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003c0f1  test    eax, eax
0x14003c0f3  js      loc_14003C182
0x14003c0f9  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14003c100  test    rax, rax
0x14003c103  jz      short loc_14003C10C
0x14003c105  inc     qword ptr [rax+0E8h]
0x14003c10c  inc     qword ptr [rbx+2C8h]
0x14003c113  mov     r9d, edi
0x14003c116  mov     rcx, [rbx+118h]
0x14003c11d  mov     r8d, esi
0x14003c120  mov     rdx, rbp
0x14003c123  mov     rax, [rcx]
0x14003c126  mov     rax, [rax+30h]
0x14003c12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c12f  mov     ebx, eax
0x14003c131  call    cs:__imp_CoRevertToSelf
0x14003c137  mov     r8d, [rsp+58h+arg_0]; int
0x14003c13c  mov     rdx, [rsp+58h+var_28]; struct IServerSecurity *
0x14003c141  mov     rcx, [rsp+58h+ppInterface]; struct IUnknown *
0x14003c146  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003c14b  test    ebx, ebx
0x14003c14d  jns     short loc_14003C160
0x14003c14f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003c155  mov     rcx, rax
0x14003c158  mov     edx, ebx
0x14003c15a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003c160  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c167  cmp     rcx, r12
0x14003c16a  jz      short loc_14003C1CB
0x14003c16c  test    byte ptr [rcx+1Ch], 4
0x14003c170  jz      short loc_14003C1CB
0x14003c172  cmp     byte ptr [rcx+19h], 2
0x14003c176  jb      short loc_14003C1CB
0x14003c178  mov     edx, 0A2h
0x14003c17d  mov     r9d, ebx
0x14003c180  jmp     short loc_14003C1BB
0x14003c182  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003c188  mov     ebx, 80041024h
0x14003c18d  mov     rcx, rax
0x14003c190  mov     edx, ebx
0x14003c192  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003c198  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c19f  cmp     rcx, r12
0x14003c1a2  jz      short loc_14003C1CB
0x14003c1a4  test    byte ptr [rcx+1Ch], 4
0x14003c1a8  jz      short loc_14003C1CB
0x14003c1aa  cmp     byte ptr [rcx+19h], 2
0x14003c1ae  jb      short loc_14003C1CB
0x14003c1b0  mov     edx, 0A3h
0x14003c1b5  mov     r9d, 80041024h
0x14003c1bb  mov     rcx, [rcx+10h]
0x14003c1bf  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003c1c6  call    WPP_SF_d
0x14003c1cb  mov     rbp, [rsp+58h+arg_10]
0x14003c1d0  mov     eax, ebx
0x14003c1d2  mov     rbx, [rsp+58h+arg_8]
0x14003c1d7  add     rsp, 40h
0x14003c1db  pop     r12
0x14003c1dd  pop     rdi
0x14003c1de  pop     rsi
0x14003c1df  retn
```
