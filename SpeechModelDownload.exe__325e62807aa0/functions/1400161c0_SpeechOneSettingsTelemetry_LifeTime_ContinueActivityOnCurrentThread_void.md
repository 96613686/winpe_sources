# SpeechOneSettingsTelemetry::LifeTime::ContinueActivityOnCurrentThread(void)

- ea: `0x1400161c0`
- end: `0x140016268`
- name: `?ContinueActivityOnCurrentThread@LifeTime@SpeechOneSettingsTelemetry@@UEAA?AVActivityThreadWatcher@wil@@XZ`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140014f68`
- `0x1400161c0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400161e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400161e3`

## pseudocode

```c
__int64 __fastcall SpeechOneSettingsTelemetry::LifeTime::ContinueActivityOnCurrentThread(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  struct _TP_TIMER *v4; // rcx
  __int64 v5; // r8

  v2 = a2;
  v4 = *(struct _TP_TIMER **)(a1 + 96);
  if ( v4 )
    SetThreadpoolTimer(v4, (PFILETIME)(a1 + 104), 0, 0);
  if ( !*(_BYTE *)(a1 + 8) )
  {
    LOBYTE(a2) = 1;
    (**(void (__fastcall ***)(__int64, __int64))a1)(a1, a2);
  }
  v5 = *(_QWORD *)(a1 + 424);
  if ( *(_DWORD *)v5 == 1 )
  {
    wil::ActivityThreadWatcher::ActivityThreadWatcher(
      (wil::ActivityThreadWatcher *)v2,
      (struct wil::details::IFailureCallback *)(a1 + 152),
      (const struct wil::details::StoredCallContextInfo *)(v5 + 40));
  }
  else
  {
    *(_BYTE *)(v2 + 24) = 0;
    *(_OWORD *)v2 = 0;
    *(_OWORD *)(v2 + 16) = 0;
    *(_QWORD *)(v2 + 32) = 0;
    *(_QWORD *)(v2 + 40) = 0;
    *(_QWORD *)(v2 + 48) = 0;
    *(_DWORD *)(v2 + 56) = 0;
    *(_QWORD *)(v2 + 64) = 0;
    *(_BYTE *)(v2 + 72) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1400161c0  mov     [rsp+arg_0], rbx
0x1400161c5  push    rdi
0x1400161c6  sub     rsp, 30h
0x1400161ca  mov     rbx, rdx
0x1400161cd  mov     rdi, rcx
0x1400161d0  mov     rcx, [rcx+60h]; pti
0x1400161d4  test    rcx, rcx
0x1400161d7  jz      short loc_1400161E9
0x1400161d9  lea     rdx, [rdi+68h]; pftDueTime
0x1400161dd  xor     r9d, r9d; msWindowLength
0x1400161e0  xor     r8d, r8d; msPeriod
0x1400161e3  call    cs:__imp_SetThreadpoolTimer
0x1400161e9  cmp     byte ptr [rdi+8], 0
0x1400161ed  jnz     short loc_1400161FF
0x1400161ef  mov     rax, [rdi]
0x1400161f2  mov     dl, 1
0x1400161f4  mov     rcx, rdi
0x1400161f7  mov     rax, [rax]
0x1400161fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161ff  lea     rdx, [rdi+98h]; struct wil::details::IFailureCallback *
0x140016206  mov     r8, [rdx+110h]
0x14001620d  cmp     dword ptr [r8], 1
0x140016211  jnz     short loc_140016221
0x140016213  add     r8, 28h ; '('; struct wil::details::StoredCallContextInfo *
0x140016217  mov     rcx, rbx; this
0x14001621a  call    ??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)
0x14001621f  jmp     short loc_14001625A
0x140016221  mov     byte ptr [rbx+18h], 0
0x140016225  xorps   xmm0, xmm0
0x140016228  movups  xmmword ptr [rbx], xmm0
0x14001622b  movups  xmmword ptr [rbx+10h], xmm0
0x14001622f  mov     qword ptr [rbx+20h], 0
0x140016237  mov     qword ptr [rbx+28h], 0
0x14001623f  mov     qword ptr [rbx+30h], 0
0x140016247  mov     dword ptr [rbx+38h], 0
0x14001624e  mov     qword ptr [rbx+40h], 0
0x140016256  mov     byte ptr [rbx+48h], 0
0x14001625a  mov     rax, rbx
0x14001625d  mov     rbx, [rsp+38h+arg_0]
0x140016262  add     rsp, 30h
0x140016266  pop     rdi
0x140016267  retn
```
