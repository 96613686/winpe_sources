# LegacyActivationShim::Util::GetRuntimeInfo(LegacyActivationShim::Util::RuntimeInfo * *,ushort const *,IStream *,ushort *,ulong *)

- ea: `0x1400032c4`
- end: `0x1400033bb`
- name: `?GetRuntimeInfo@Util@LegacyActivationShim@@YAJPEAPEAURuntimeInfo@12@PEBGPEAUIStream@@PEAGPEAK@Z`
- size: `247`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *this, struct LegacyActivationShim::Util::RuntimeInfo **, const unsigned __int16 *, struct IStream *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002c50`

## callees

- `0x140002f14`
- `0x1400032c4`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x140003308`
- `KERNEL32!SwitchToThread` at `0x140003308`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::GetRuntimeInfo(
        LegacyActivationShim::Util *this,
        struct LegacyActivationShim::Util::RuntimeInfo **a2,
        const unsigned __int16 *a3,
        struct IStream *a4,
        unsigned __int16 *a5)
{
  unsigned int v9; // esi
  __int64 result; // rax
  unsigned int *v11; // [rsp+38h] [rbp-30h]

  v9 = 0;
  if ( !LegacyActivationShim::Util::g_runtimeInfoIsInitialized )
  {
    while ( _InterlockedExchange((volatile __int32 *)&LegacyActivationShim::Util::g_runtimeInfoLock, 1) == 1 )
      SwitchToThread();
    if ( !LegacyActivationShim::Util::g_runtimeInfoIsInitialized )
    {
      LegacyActivationShim::Util::g_runtimeInfo = 0;
      *(_DWORD *)&dword_14000A5C8 = 512;
      word_14000A5CC = 0;
      result = LegacyActivationShim::Util::GetCLRRuntimeInfoHelper(
                 (LegacyActivationShim::Util *)&LegacyActivationShim::Util::g_runtimeInfo,
                 a2,
                 a3,
                 a4,
                 a5,
                 &word_14000A5CC,
                 &dword_14000A5C8,
                 v11);
      v9 = result;
      if ( (int)result < 0 )
      {
        _InterlockedExchange((volatile __int32 *)&LegacyActivationShim::Util::g_runtimeInfoLock, 0);
        return result;
      }
      LegacyActivationShim::Util::g_hRuntimeInfo = (__int64)&LegacyActivationShim::Util::g_runtimeInfo;
      byte_14000A0F8 = 1;
      _InterlockedExchange(&LegacyActivationShim::Util::g_runtimeInfoIsInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&LegacyActivationShim::Util::g_runtimeInfoLock, 0);
  }
  *(_QWORD *)this = &LegacyActivationShim::Util::g_runtimeInfo;
  return v9;
}

```

## disassembly

```asm
0x1400032c4  mov     [rsp+arg_0], rbx
0x1400032c9  mov     [rsp+arg_8], rbp
0x1400032ce  mov     [rsp+arg_10], rsi
0x1400032d3  push    rdi
0x1400032d4  push    r12
0x1400032d6  push    r13
0x1400032d8  push    r14
0x1400032da  push    r15
0x1400032dc  sub     rsp, 40h
0x1400032e0  xor     ebx, ebx
0x1400032e2  lea     r13, ?g_runtimeInfo@Util@LegacyActivationShim@@3URuntimeInfo@12@A; LegacyActivationShim::Util::RuntimeInfo LegacyActivationShim::Util::g_runtimeInfo
0x1400032e9  cmp     cs:?g_runtimeInfoIsInitialized@Util@LegacyActivationShim@@3JA, ebx; long LegacyActivationShim::Util::g_runtimeInfoIsInitialized
0x1400032ef  mov     rbp, r9
0x1400032f2  mov     r15, r8
0x1400032f5  mov     r12, rdx
0x1400032f8  mov     r14, rcx
0x1400032fb  mov     esi, ebx
0x1400032fd  jnz     loc_140003398
0x140003303  lea     edi, [rbx+1]
0x140003306  jmp     short loc_14000330E
0x140003308  call    cs:__imp_SwitchToThread
0x14000330e  mov     eax, edi
0x140003310  xchg    eax, cs:?g_runtimeInfoLock@Util@LegacyActivationShim@@3VZeroInitGlobalSpinLock@12@A; LegacyActivationShim::Util::ZeroInitGlobalSpinLock LegacyActivationShim::Util::g_runtimeInfoLock
0x140003316  cmp     eax, edi
0x140003318  jz      short loc_140003308
0x14000331a  cmp     cs:?g_runtimeInfoIsInitialized@Util@LegacyActivationShim@@3JA, ebx; long LegacyActivationShim::Util::g_runtimeInfoIsInitialized
0x140003320  jnz     short loc_140003392
0x140003322  lea     rax, dword_14000A5C8
0x140003329  mov     cs:?g_runtimeInfo@Util@LegacyActivationShim@@3URuntimeInfo@12@A, rbx; LegacyActivationShim::Util::RuntimeInfo LegacyActivationShim::Util::g_runtimeInfo
0x140003330  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x140003335  mov     r9, rbp; struct IStream *
0x140003338  lea     rax, word_14000A5CC
0x14000333f  mov     cs:dword_14000A5C8, 200h
0x140003349  mov     [rsp+68h+var_40], rax; wchar_t *
0x14000334e  mov     r8, r15; unsigned __int16 *
0x140003351  mov     rax, [rsp+68h+arg_20]
0x140003359  mov     rdx, r12; struct ICLRRuntimeInfo **
0x14000335c  mov     rcx, r13; this
0x14000335f  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140003364  mov     cs:word_14000A5CC, bx
0x14000336b  call    ?GetCLRRuntimeInfoHelper@Util@LegacyActivationShim@@YAJPEAPEAUICLRRuntimeInfo@@PEBGPEAUIStream@@PEAGPEAK34@Z; LegacyActivationShim::Util::GetCLRRuntimeInfoHelper(ICLRRuntimeInfo * *,ushort const *,IStream *,ushort *,ulong *,ushort *,ulong *)
0x140003370  mov     esi, eax
0x140003372  test    eax, eax
0x140003374  jns     short loc_14000337E
0x140003376  xchg    ebx, cs:?g_runtimeInfoLock@Util@LegacyActivationShim@@3VZeroInitGlobalSpinLock@12@A; LegacyActivationShim::Util::ZeroInitGlobalSpinLock LegacyActivationShim::Util::g_runtimeInfoLock
0x14000337c  jmp     short loc_14000339D
0x14000337e  mov     cs:?g_hRuntimeInfo@Util@LegacyActivationShim@@3V?$ZeroInitGlobalReleaseHolder@PEAURuntimeInfo@Util@LegacyActivationShim@@@12@A, r13; LegacyActivationShim::Util::ZeroInitGlobalReleaseHolder<LegacyActivationShim::Util::RuntimeInfo *> LegacyActivationShim::Util::g_hRuntimeInfo
0x140003385  mov     cs:byte_14000A0F8, dil
0x14000338c  xchg    edi, cs:?g_runtimeInfoIsInitialized@Util@LegacyActivationShim@@3JA; long LegacyActivationShim::Util::g_runtimeInfoIsInitialized
0x140003392  xchg    ebx, cs:?g_runtimeInfoLock@Util@LegacyActivationShim@@3VZeroInitGlobalSpinLock@12@A; LegacyActivationShim::Util::ZeroInitGlobalSpinLock LegacyActivationShim::Util::g_runtimeInfoLock
0x140003398  mov     [r14], r13
0x14000339b  mov     eax, esi
0x14000339d  lea     r11, [rsp+68h+var_28]
0x1400033a2  mov     rbx, [r11+30h]
0x1400033a6  mov     rbp, [r11+38h]
0x1400033aa  mov     rsi, [r11+40h]
0x1400033ae  mov     rsp, r11
0x1400033b1  pop     r15
0x1400033b3  pop     r14
0x1400033b5  pop     r13
0x1400033b7  pop     r12
0x1400033b9  pop     rdi
0x1400033ba  retn
```
