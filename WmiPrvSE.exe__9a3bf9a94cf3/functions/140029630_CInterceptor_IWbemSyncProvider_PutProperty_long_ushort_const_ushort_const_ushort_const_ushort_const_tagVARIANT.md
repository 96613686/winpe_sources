# CInterceptor_IWbemSyncProvider::PutProperty(long,ushort * const,ushort * const,ushort * const,ushort * const,tagVARIANT const *)

- ea: `0x140029630`
- end: `0x1400297b4`
- name: `?PutProperty@CInterceptor_IWbemSyncProvider@@UEAAJJQEAG000PEBUtagVARIANT@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, int, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, const struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140029630`
- `0x140030158`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14002971b`
- `wbemcomn!GetMemLogObject` at `0x140029755`
- `wbemcomn!GetMemLogObject` at `0x14002971b`
- `wbemcomn!GetMemLogObject` at `0x140029755`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029726`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029765`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029726`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029765`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140029711`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140029711`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::PutProperty(
        CInterceptor_IWbemSyncProvider *this,
        unsigned int a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        const struct tagVARIANT *a7)
{
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v16; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSSSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      132,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      a2,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6);
  }
  if ( *((_QWORD *)this + 41) && *(_DWORD *)(*((_QWORD *)this + 74) + 2132LL) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 33);
    ++*((_QWORD *)this + 100);
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, const struct tagVARIANT *))(**((_QWORD **)this + 41) + 32LL))(
            *((_QWORD *)this + 41),
            a2,
            a3,
            a4,
            a5,
            a6,
            a7);
    CoRevertToSelf();
    if ( v11 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 133;
      v15 = (unsigned int)v11;
LABEL_19:
      WPP_SF_d(v13[2], v14, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v15);
    }
  }
  else
  {
    v16 = GetMemLogObject();
    v11 = -2147217372;
    CMemoryLog::Write(v16, -2147217372);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 134;
      v15 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140029630  mov     r11, rsp
0x140029633  push    rbx
0x140029634  push    rbp
0x140029635  push    rsi
0x140029636  push    rdi
0x140029637  push    r14
0x140029639  push    r15
0x14002963b  sub     rsp, 48h
0x14002963f  mov     rdi, r9
0x140029642  mov     rsi, r8
0x140029645  mov     ebp, edx
0x140029647  mov     rbx, rcx
0x14002964a  mov     rcx, cs:WPP_GLOBAL_Control
0x140029651  lea     rax, WPP_GLOBAL_Control
0x140029658  mov     r14, [rsp+78h+arg_28]
0x140029660  mov     r15, [rsp+78h+arg_20]
0x140029668  cmp     rcx, rax
0x14002966b  jz      short loc_1400296A1
0x14002966d  test    byte ptr [rcx+1Ch], 4
0x140029671  jz      short loc_1400296A1
0x140029673  cmp     byte ptr [rcx+19h], 5
0x140029677  jb      short loc_1400296A1
0x140029679  mov     rcx, [rcx+10h]
0x14002967d  mov     edx, 84h
0x140029682  mov     [r11-40h], r14
0x140029686  mov     [r11-48h], r15
0x14002968a  mov     [r11-50h], r9
0x14002968e  mov     r9d, ebp
0x140029691  mov     [r11-58h], r8
0x140029695  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14002969c  call    WPP_SF_dSSSS
0x1400296a1  cmp     qword ptr [rbx+148h], 0
0x1400296a9  jz      loc_140029755
0x1400296af  mov     rax, [rbx+250h]
0x1400296b6  cmp     dword ptr [rax+854h], 0
0x1400296bd  jz      loc_140029755
0x1400296c3  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x1400296ca  test    rax, rax
0x1400296cd  jz      short loc_1400296D6
0x1400296cf  inc     qword ptr [rax+108h]
0x1400296d6  inc     qword ptr [rbx+320h]
0x1400296dd  mov     r9, rdi
0x1400296e0  mov     rdx, [rsp+78h+arg_30]
0x1400296e8  mov     r8, rsi
0x1400296eb  mov     rcx, [rbx+148h]
0x1400296f2  mov     [rsp+78h+var_48], rdx
0x1400296f7  mov     edx, ebp
0x1400296f9  mov     [rsp+78h+var_50], r14
0x1400296fe  mov     [rsp+78h+var_58], r15
0x140029703  mov     rax, [rcx]
0x140029706  mov     rax, [rax+20h]
0x14002970a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002970f  mov     ebx, eax
0x140029711  call    cs:__imp_CoRevertToSelf
0x140029717  test    ebx, ebx
0x140029719  jns     short loc_14002972C
0x14002971b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140029721  mov     rcx, rax
0x140029724  mov     edx, ebx
0x140029726  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002972c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029733  lea     rax, WPP_GLOBAL_Control
0x14002973a  cmp     rcx, rax
0x14002973d  jz      short loc_1400297A5
0x14002973f  test    byte ptr [rcx+1Ch], 4
0x140029743  jz      short loc_1400297A5
0x140029745  cmp     byte ptr [rcx+19h], 2
0x140029749  jb      short loc_1400297A5
0x14002974b  mov     edx, 85h
0x140029750  mov     r9d, ebx
0x140029753  jmp     short loc_140029795
0x140029755  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002975b  mov     ebx, 80041024h
0x140029760  mov     rcx, rax
0x140029763  mov     edx, ebx
0x140029765  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002976b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029772  lea     rax, WPP_GLOBAL_Control
0x140029779  cmp     rcx, rax
0x14002977c  jz      short loc_1400297A5
0x14002977e  test    byte ptr [rcx+1Ch], 4
0x140029782  jz      short loc_1400297A5
0x140029784  cmp     byte ptr [rcx+19h], 2
0x140029788  jb      short loc_1400297A5
0x14002978a  mov     edx, 86h
0x14002978f  mov     r9d, 80041024h
0x140029795  mov     rcx, [rcx+10h]
0x140029799  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400297a0  call    WPP_SF_d
0x1400297a5  mov     eax, ebx
0x1400297a7  add     rsp, 48h
0x1400297ab  pop     r15
0x1400297ad  pop     r14
0x1400297af  pop     rdi
0x1400297b0  pop     rsi
0x1400297b1  pop     rbp
0x1400297b2  pop     rbx
0x1400297b3  retn
```
