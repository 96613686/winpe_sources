# GraphStreamingResourceManager::RegisterThread(void *,ThreadRegistrationToken__ * *)

- ea: `0x140024120`
- end: `0x140024274`
- name: `?RegisterThread@GraphStreamingResourceManager@@UEAAJPEAXPEAPEAUThreadRegistrationToken__@@@Z`
- size: `340`
- prototype: `int(GraphStreamingResourceManager *__hidden this, void *, struct ThreadRegistrationToken__ **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140024120`
- `0x1400246b4`
- `0x140024e20`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400241f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400241f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024162`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140024153`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x140024153`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GraphStreamingResourceManager::RegisterThread(
        GraphStreamingResourceManager *this,
        void *a2,
        struct ThreadRegistrationToken__ **a3)
{
  struct ThreadRegistrationToken__ **v3; // r15
  void *v4; // r12
  GraphStreamingResourceManager *v5; // r13
  DWORD ThreadId; // esi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  char *v8; // r14
  __int64 v9; // rdi
  __int64 i; // rdi
  int v11; // esi
  ATL::CAtlException *v13; // rbx
  __int64 v14; // [rsp+20h] [rbp-78h]
  ATL::CAtlException *v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]
  int v21; // [rsp+B8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  ThreadId = GetThreadId(a2);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 16));
  v8 = (char *)v5 + 128;
  v9 = *((_QWORD *)v5 + 16);
  if ( v9 )
  {
    for ( i = *(_QWORD *)(v9 + 8LL * (ThreadId % *((_DWORD *)v5 + 36)));
          i && (*(_DWORD *)(i + 40) != ThreadId || *(_DWORD *)i != ThreadId);
          i = *(_QWORD *)(i + 32) )
    {
      ;
    }
    if ( i )
    {
      _InterlockedIncrement((volatile signed __int32 *)(i + 8));
      goto LABEL_16;
    }
  }
  try
  {
    v16 = 0;
    v17 = 0;
    LODWORD(v16) = 1;
    i = ATL::CAtlMap<unsigned long,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::SetAt(
          (char *)v5 + 128,
          ThreadId,
          &v16);
    v14 = i;
  }
  catch ( ATL::CAtlException *v15 )
  {
    v13 = v15;
    if ( *(_DWORD *)v15 == -1073741571 )
      _o__resetstkoflw();
    v21 = *(_DWORD *)v13;
    v11 = *(_DWORD *)v13;
    i = v14;
    v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
    v8 = (char *)v5 + 128;
    if ( v21 < 0 )
      goto LABEL_7;
    v5 = this;
    v3 = a3;
    v4 = a2;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*((_QWORD *)v5 - 1) + 48LL))((__int64)v5 - 8, v4, i + 16);
  if ( v11 >= 0 )
  {
LABEL_16:
    *v3 = (struct ThreadRegistrationToken__ *)i;
    v11 = 0;
    goto LABEL_9;
  }
LABEL_7:
  if ( i )
    ATL::CAtlMap<unsigned long,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::RemoveAtPos(
      v8,
      i);
LABEL_9:
  if ( v7 )
    LeaveCriticalSection(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140024120  mov     [rsp+arg_10], r8
0x140024125  mov     [rsp+arg_8], rdx
0x14002412a  mov     [rsp+arg_0], rcx
0x14002412f  push    rbx
0x140024130  push    rsi
0x140024131  push    rdi
0x140024132  push    r12
0x140024134  push    r13
0x140024136  push    r14
0x140024138  push    r15
0x14002413a  sub     rsp, 60h
0x14002413e  mov     r15, r8
0x140024141  mov     r12, rdx
0x140024144  mov     r13, rcx
0x140024147  mov     [rsp+98h+var_78], 0
0x140024150  mov     rcx, rdx; Thread
0x140024153  call    cs:__imp_GetThreadId
0x140024159  mov     esi, eax
0x14002415b  lea     rbx, [r13+10h]
0x14002415f  mov     rcx, rbx; lpCriticalSection
0x140024162  call    cs:__imp_EnterCriticalSection
0x140024168  mov     [rsp+98h+var_70], rbx
0x14002416d  lea     r14, [r13+80h]
0x140024174  mov     [rsp+98h+var_68], r14
0x140024179  mov     rdi, [r14]
0x14002417c  test    rdi, rdi
0x14002417f  jz      short loc_14002419B
0x140024181  xor     edx, edx
0x140024183  mov     eax, esi
0x140024185  div     dword ptr [r14+10h]
0x140024189  mov     rdi, [rdi+rdx*8]
0x14002418d  test    rdi, rdi
0x140024190  jnz     short loc_14002420B
0x140024192  test    rdi, rdi
0x140024195  jnz     loc_140024221
0x14002419b  xorps   xmm0, xmm0
0x14002419e  xor     eax, eax
0x1400241a0  movups  [rsp+98h+var_58], xmm0
0x1400241a5  mov     [rsp+98h+var_48], rax
0x1400241aa  mov     dword ptr [rsp+98h+var_58], 1
0x1400241b2  lea     r8, [rsp+98h+var_58]
0x1400241b7  mov     edx, esi
0x1400241b9  mov     rcx, r14
0x1400241bc  call    ?SetAt@?$CAtlMap@KUListValue@HandleRegistrations@GraphStreamingResourceManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@GraphStreamingResourceManager@@@5@@ATL@@QEAAPEAU__POSITION@@KAEBUListValue@HandleRegistrations@GraphStreamingResourceManager@@@Z; ATL::CAtlMap<ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::SetAt(ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue const &)
0x1400241c1  mov     rdi, rax
0x1400241c4  mov     [rsp+98h+var_78], rax
0x1400241c9  lea     rcx, [r13-8]
0x1400241cd  mov     rax, [rcx]
0x1400241d0  lea     r8, [rdi+10h]
0x1400241d4  mov     rdx, r12
0x1400241d7  mov     rax, [rax+30h]
0x1400241db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400241e0  mov     esi, eax
0x1400241e2  test    eax, eax
0x1400241e4  jns     short loc_140024225
0x1400241e6  test    rdi, rdi
0x1400241e9  jnz     short loc_140024263
0x1400241eb  test    rbx, rbx
0x1400241ee  jz      short loc_1400241F9
0x1400241f0  mov     rcx, rbx; lpCriticalSection
0x1400241f3  call    cs:__imp_LeaveCriticalSection
0x1400241f9  mov     eax, esi
0x1400241fb  add     rsp, 60h
0x1400241ff  pop     r15
0x140024201  pop     r14
0x140024203  pop     r13
0x140024205  pop     r12
0x140024207  pop     rdi
0x140024208  pop     rsi
0x140024209  pop     rbx
0x14002420a  retn
0x14002420b  cmp     [rdi+28h], esi
0x14002420e  jnz     short loc_140024218
0x140024210  cmp     [rdi], esi
0x140024212  jz      loc_140024192
0x140024218  mov     rdi, [rdi+20h]
0x14002421c  jmp     loc_14002418D
0x140024221  lock inc dword ptr [rdi+8]
0x140024225  mov     [r15], rdi
0x140024228  xor     esi, esi
0x14002422a  jmp     short loc_1400241EB
0x14002422c  mov     esi, [rsp+98h+arg_18]
0x140024233  mov     rdi, [rsp+98h+var_78]
0x140024238  mov     rbx, [rsp+98h+var_70]
0x14002423d  mov     r14, [rsp+98h+var_68]
0x140024242  test    esi, esi
0x140024244  js      short loc_1400241E6
0x140024246  mov     r13, [rsp+98h+arg_0]
0x14002424e  mov     r15, [rsp+98h+arg_10]
0x140024256  mov     r12, [rsp+98h+arg_8]
0x14002425e  jmp     loc_1400241C9
0x140024263  mov     rdx, rdi
0x140024266  mov     rcx, r14
0x140024269  call    ?RemoveAtPos@?$CAtlMap@KUListValue@HandleRegistrations@GraphStreamingResourceManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@GraphStreamingResourceManager@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::RemoveAtPos(__POSITION *)
0x14002426e  jmp     loc_1400241EB
```
