# utl::_SharedAtomic::_EnterLock_acq<KerbDigestAlgorithmPolicy const *>(utl::_SharedBase<KerbDigestAlgorithmPolicy const *> &)

- ea: `0x1800134dc`
- end: `0x180013542`
- name: `??$_EnterLock_acq@PEBVKerbDigestAlgorithmPolicy@@@_SharedAtomic@utl@@CAPEAV_RefCountBase@1@AEAV?$_SharedBase@PEBVKerbDigestAlgorithmPolicy@@@1@@Z`
- size: `102`
- prototype: `signed __int64()`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b898`
- `0x180035ec8`
- `0x18004009c`
- `0x180050e78`
- `0x18005490c`
- `0x180054b24`

## callees

- `0x1800134dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18001350f`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18001350f`

## pseudocode

```c
signed __int64 utl::_SharedAtomic::_EnterLock_acq<KerbDigestAlgorithmPolicy const *>()
{
  unsigned int v0; // ebx
  signed __int64 result; // rax

  v0 = 0;
  _m_prefetchw(&qword_1800B2D40);
  for ( result = _InterlockedOr64((volatile signed __int64 *)&qword_1800B2D40, 1u);
        (result & 7) != 0;
        result = _InterlockedOr64((volatile signed __int64 *)&qword_1800B2D40, 1u) )
  {
    if ( v0 >= 0x20 )
      SwitchToThread();
    else
      _mm_pause();
    ++v0;
    _m_prefetchw(&qword_1800B2D40);
  }
  return result;
}

```

## disassembly

```asm
0x1800134dc  push    rbx
0x1800134de  sub     rsp, 20h
0x1800134e2  xor     ebx, ebx
0x1800134e4  prefetchw byte ptr cs:qword_1800B2D40
0x1800134eb  mov     rax, cs:qword_1800B2D40
0x1800134f2  mov     rcx, rax
0x1800134f5  or      rcx, 1
0x1800134f9  lock cmpxchg cs:qword_1800B2D40, rcx
0x180013502  jnz     short loc_1800134F2
0x180013504  jmp     short loc_180013537
0x180013506  cmp     ebx, 20h ; ' '
0x180013509  jnb     short loc_18001350F
0x18001350b  pause
0x18001350d  jmp     short loc_180013515
0x18001350f  call    cs:__imp_SwitchToThread
0x180013515  inc     ebx
0x180013517  prefetchw byte ptr cs:qword_1800B2D40
0x18001351e  mov     rax, cs:qword_1800B2D40
0x180013525  mov     rcx, rax
0x180013528  or      rcx, 1
0x18001352c  lock cmpxchg cs:qword_1800B2D40, rcx
0x180013535  jnz     short loc_180013525
0x180013537  test    al, 7
0x180013539  jnz     short loc_180013506
0x18001353b  nop
0x18001353c  add     rsp, 20h
0x180013540  pop     rbx
0x180013541  retn
```
