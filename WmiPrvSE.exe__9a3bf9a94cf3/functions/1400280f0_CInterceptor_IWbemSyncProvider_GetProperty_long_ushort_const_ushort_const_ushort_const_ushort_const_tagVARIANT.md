# CInterceptor_IWbemSyncProvider::GetProperty(long,ushort * const,ushort * const,ushort * const,ushort * const,tagVARIANT *)

- ea: `0x1400280f0`
- end: `0x1400282a2`
- name: `?GetProperty@CInterceptor_IWbemSyncProvider@@UEAAJJQEAG000PEAUtagVARIANT@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, int, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400280f0`
- `0x140030158`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400281dc`
- `wbemcomn!GetMemLogObject` at `0x140028275`
- `wbemcomn!GetMemLogObject` at `0x1400281dc`
- `wbemcomn!GetMemLogObject` at `0x140028275`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400281ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140028280`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400281ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140028280`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400281a2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400281a2`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::GetProperty(
        CInterceptor_IWbemSyncProvider *this,
        unsigned int a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        struct tagVARIANT *a7)
{
  int v11; // ebx
  _QWORD *v12; // rcx
  CMemoryLog *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSSSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      a2,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6);
  }
  if ( *((_QWORD *)this + 41) && *(_DWORD *)(*((_QWORD *)this + 74) + 2136LL) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 32);
    ++*((_QWORD *)this + 99);
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, struct tagVARIANT *))(**((_QWORD **)this + 41) + 24LL))(
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
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 130;
      v16 = (unsigned int)v11;
      goto LABEL_16;
    }
  }
  else
  {
    v14 = GetMemLogObject();
    v11 = -2147217372;
    CMemoryLog::Write(v14, -2147217372);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 131;
      v16 = 2147749924LL;
LABEL_16:
      WPP_SF_d(v12[2], v15, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v16);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400280f0  push    rbx
0x1400280f2  push    rbp
0x1400280f3  push    rsi
0x1400280f4  push    rdi
0x1400280f5  push    r14
0x1400280f7  push    r15
0x1400280f9  sub     rsp, 48h
0x1400280fd  mov     rdi, r9
0x140028100  mov     rsi, r8
0x140028103  mov     ebp, edx
0x140028105  mov     rbx, rcx
0x140028108  mov     rcx, cs:WPP_GLOBAL_Control
0x14002810f  lea     rax, WPP_GLOBAL_Control
0x140028116  mov     r14, [rsp+78h+arg_28]
0x14002811e  mov     r15, [rsp+78h+arg_20]
0x140028126  cmp     rcx, rax
0x140028129  jz      short loc_140028135
0x14002812b  test    byte ptr [rcx+1Ch], 4
0x14002812f  jnz     loc_14002822E
0x140028135  cmp     qword ptr [rbx+148h], 0
0x14002813d  jz      loc_1400281DC
0x140028143  mov     rax, [rbx+250h]
0x14002814a  cmp     dword ptr [rax+858h], 0
0x140028151  jz      loc_1400281DC
0x140028157  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14002815e  test    rax, rax
0x140028161  jnz     loc_140028269
0x140028167  inc     qword ptr [rbx+318h]
0x14002816e  mov     r9, rdi
0x140028171  mov     rdx, [rsp+78h+arg_30]
0x140028179  mov     r8, rsi
0x14002817c  mov     rcx, [rbx+148h]
0x140028183  mov     [rsp+78h+var_48], rdx
0x140028188  mov     edx, ebp
0x14002818a  mov     [rsp+78h+var_50], r14
0x14002818f  mov     [rsp+78h+var_58], r15
0x140028194  mov     rax, [rcx]
0x140028197  mov     rax, [rax+18h]
0x14002819b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400281a0  mov     ebx, eax
0x1400281a2  call    cs:__imp_CoRevertToSelf
0x1400281a8  test    ebx, ebx
0x1400281aa  js      loc_140028275
0x1400281b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400281b7  lea     rax, WPP_GLOBAL_Control
0x1400281be  cmp     rcx, rax
0x1400281c1  jz      short loc_1400281CD
0x1400281c3  test    byte ptr [rcx+1Ch], 4
0x1400281c7  jnz     loc_14002828B
0x1400281cd  mov     eax, ebx
0x1400281cf  add     rsp, 48h
0x1400281d3  pop     r15
0x1400281d5  pop     r14
0x1400281d7  pop     rdi
0x1400281d8  pop     rsi
0x1400281d9  pop     rbp
0x1400281da  pop     rbx
0x1400281db  retn
0x1400281dc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400281e2  mov     ebx, 80041024h
0x1400281e7  mov     rcx, rax
0x1400281ea  mov     edx, ebx
0x1400281ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400281f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400281f9  lea     rax, WPP_GLOBAL_Control
0x140028200  cmp     rcx, rax
0x140028203  jz      short loc_1400281CD
0x140028205  test    byte ptr [rcx+1Ch], 4
0x140028209  jz      short loc_1400281CD
0x14002820b  cmp     byte ptr [rcx+19h], 2
0x14002820f  jb      short loc_1400281CD
0x140028211  mov     edx, 83h
0x140028216  mov     r9d, 80041024h
0x14002821c  mov     rcx, [rcx+10h]
0x140028220  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140028227  call    WPP_SF_d
0x14002822c  jmp     short loc_1400281CD
0x14002822e  cmp     byte ptr [rcx+19h], 5
0x140028232  jb      loc_140028135
0x140028238  mov     rcx, [rcx+10h]
0x14002823c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140028243  mov     [rsp+78h+var_40], r14
0x140028248  mov     edx, 81h
0x14002824d  mov     [rsp+78h+var_48], r15
0x140028252  mov     r9d, ebp
0x140028255  mov     [rsp+78h+var_50], rdi
0x14002825a  mov     [rsp+78h+var_58], rsi
0x14002825f  call    WPP_SF_dSSSS
0x140028264  jmp     loc_140028135
0x140028269  inc     qword ptr [rax+100h]
0x140028270  jmp     loc_140028167
0x140028275  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002827b  mov     rcx, rax
0x14002827e  mov     edx, ebx
0x140028280  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140028286  jmp     loc_1400281B0
0x14002828b  cmp     byte ptr [rcx+19h], 2
0x14002828f  jb      loc_1400281CD
0x140028295  mov     edx, 82h
0x14002829a  mov     r9d, ebx
0x14002829d  jmp     loc_14002821C
```
