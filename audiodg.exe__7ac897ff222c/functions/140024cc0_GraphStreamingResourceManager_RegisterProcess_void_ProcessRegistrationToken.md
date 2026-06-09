# GraphStreamingResourceManager::RegisterProcess(void *,ProcessRegistrationToken__ * *)

- ea: `0x140024cc0`
- end: `0x140024e18`
- name: `?RegisterProcess@GraphStreamingResourceManager@@UEAAJPEAXPEAPEAUProcessRegistrationToken__@@@Z`
- size: `344`
- prototype: `int(GraphStreamingResourceManager *__hidden this, void *, struct ProcessRegistrationToken__ **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1400246b4`
- `0x140024cc0`
- `0x140024e20`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024d54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024d02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024d02`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140024cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140024cf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GraphStreamingResourceManager::RegisterProcess(
        GraphStreamingResourceManager *this,
        void *a2,
        struct ProcessRegistrationToken__ **a3)
{
  struct ProcessRegistrationToken__ **v3; // r15
  void *v4; // r12
  GraphStreamingResourceManager *v5; // r13
  DWORD ProcessId; // esi
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
  ProcessId = GetProcessId(a2);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 16));
  v8 = (char *)v5 + 56;
  v9 = *((_QWORD *)v5 + 7);
  if ( v9 )
  {
    for ( i = *(_QWORD *)(v9 + 8LL * (ProcessId % *((_DWORD *)v5 + 18)));
          i && (*(_DWORD *)(i + 40) != ProcessId || *(_DWORD *)i != ProcessId);
          i = *(_QWORD *)(i + 32) )
    {
      ;
    }
    if ( i )
    {
      _InterlockedIncrement((volatile signed __int32 *)(i + 8));
LABEL_6:
      *v3 = (struct ProcessRegistrationToken__ *)i;
      v11 = 0;
      goto LABEL_9;
    }
  }
  try
  {
    v16 = 0;
    v17 = 0;
    LODWORD(v16) = 1;
    i = ATL::CAtlMap<unsigned long,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::SetAt(
          (char *)v5 + 56,
          ProcessId,
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
    v8 = (char *)v5 + 56;
    if ( v21 < 0 )
      goto LABEL_7;
    v5 = this;
    v3 = a3;
    v4 = a2;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*((_QWORD *)v5 - 1) + 32LL))((__int64)v5 - 8, v4, i + 16);
  if ( v11 >= 0 )
    goto LABEL_6;
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
0x140024cc0  mov     [rsp+arg_10], r8
0x140024cc5  mov     [rsp+arg_8], rdx
0x140024cca  mov     [rsp+arg_0], rcx
0x140024ccf  push    rbx
0x140024cd0  push    rsi
0x140024cd1  push    rdi
0x140024cd2  push    r12
0x140024cd4  push    r13
0x140024cd6  push    r14
0x140024cd8  push    r15
0x140024cda  sub     rsp, 60h
0x140024cde  mov     r15, r8
0x140024ce1  mov     r12, rdx
0x140024ce4  mov     r13, rcx
0x140024ce7  mov     [rsp+98h+var_78], 0
0x140024cf0  mov     rcx, rdx; Process
0x140024cf3  call    cs:__imp_GetProcessId
0x140024cf9  mov     esi, eax
0x140024cfb  lea     rbx, [r13+10h]
0x140024cff  mov     rcx, rbx; lpCriticalSection
0x140024d02  call    cs:__imp_EnterCriticalSection
0x140024d08  mov     [rsp+98h+var_70], rbx
0x140024d0d  lea     r14, [r13+38h]
0x140024d11  mov     [rsp+98h+var_68], r14
0x140024d16  mov     rdi, [r14]
0x140024d19  test    rdi, rdi
0x140024d1c  jz      short loc_140024D6C
0x140024d1e  xor     edx, edx
0x140024d20  mov     eax, esi
0x140024d22  div     dword ptr [r14+10h]
0x140024d26  mov     rdi, [rdi+rdx*8]
0x140024d2a  test    rdi, rdi
0x140024d2d  jnz     loc_140024DB9
0x140024d33  test    rdi, rdi
0x140024d36  jz      short loc_140024D6C
0x140024d38  lock inc dword ptr [rdi+8]
0x140024d3c  mov     [r15], rdi
0x140024d3f  xor     esi, esi
0x140024d41  jmp     short loc_140024D4C
0x140024d43  test    rdi, rdi
0x140024d46  jnz     loc_140024E07
0x140024d4c  test    rbx, rbx
0x140024d4f  jz      short loc_140024D5A
0x140024d51  mov     rcx, rbx; lpCriticalSection
0x140024d54  call    cs:__imp_LeaveCriticalSection
0x140024d5a  mov     eax, esi
0x140024d5c  add     rsp, 60h
0x140024d60  pop     r15
0x140024d62  pop     r14
0x140024d64  pop     r13
0x140024d66  pop     r12
0x140024d68  pop     rdi
0x140024d69  pop     rsi
0x140024d6a  pop     rbx
0x140024d6b  retn
0x140024d6c  xorps   xmm0, xmm0
0x140024d6f  xor     eax, eax
0x140024d71  movups  [rsp+98h+var_58], xmm0
0x140024d76  mov     [rsp+98h+var_48], rax
0x140024d7b  mov     dword ptr [rsp+98h+var_58], 1
0x140024d83  lea     r8, [rsp+98h+var_58]
0x140024d88  mov     edx, esi
0x140024d8a  mov     rcx, r14
0x140024d8d  call    ?SetAt@?$CAtlMap@KUListValue@HandleRegistrations@GraphStreamingResourceManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@GraphStreamingResourceManager@@@5@@ATL@@QEAAPEAU__POSITION@@KAEBUListValue@HandleRegistrations@GraphStreamingResourceManager@@@Z; ATL::CAtlMap<ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::SetAt(ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue const &)
0x140024d92  mov     rdi, rax
0x140024d95  mov     [rsp+98h+var_78], rax
0x140024d9a  lea     rcx, [r13-8]
0x140024d9e  mov     rax, [rcx]
0x140024da1  lea     r8, [rdi+10h]
0x140024da5  mov     rdx, r12
0x140024da8  mov     rax, [rax+20h]
0x140024dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024db1  mov     esi, eax
0x140024db3  test    eax, eax
0x140024db5  jns     short loc_140024D3C
0x140024db7  jmp     short loc_140024D43
0x140024db9  cmp     [rdi+28h], esi
0x140024dbc  jnz     short loc_140024DC6
0x140024dbe  cmp     [rdi], esi
0x140024dc0  jz      loc_140024D33
0x140024dc6  mov     rdi, [rdi+20h]
0x140024dca  jmp     loc_140024D2A
0x140024dcf  mov     esi, [rsp+98h+arg_18]
0x140024dd6  mov     rdi, [rsp+98h+var_78]
0x140024ddb  mov     rbx, [rsp+98h+var_70]
0x140024de0  mov     r14, [rsp+98h+var_68]
0x140024de5  test    esi, esi
0x140024de7  js      loc_140024D43
0x140024ded  mov     r13, [rsp+98h+arg_0]
0x140024df5  mov     r15, [rsp+98h+arg_10]
0x140024dfd  mov     r12, [rsp+98h+arg_8]
0x140024e05  jmp     short loc_140024D9A
0x140024e07  mov     rdx, rdi
0x140024e0a  mov     rcx, r14
0x140024e0d  call    ?RemoveAtPos@?$CAtlMap@KUListValue@HandleRegistrations@GraphStreamingResourceManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@GraphStreamingResourceManager@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,GraphStreamingResourceManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<GraphStreamingResourceManager::HandleRegistrations::ListValue>>::RemoveAtPos(__POSITION *)
0x140024e12  jmp     loc_140024D4C
```
