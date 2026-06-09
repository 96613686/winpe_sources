# SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &)

- ea: `0x180097fd0`
- end: `0x1800980e0`
- name: `?Initialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@@Z`
- size: `272`
- prototype: `__int64 __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this, const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18009830c`

## callees

- `0x180097fd0`
- `0x1800980e8`
- `0x180098f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009801f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009801f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180098088`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180098088`

## pseudocode

```c
signed int __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this,
        const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *a2)
{
  char *v2; // rdi
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int64 v6; // rcx
  __int64 PoolWithTag; // rax
  signed int result; // eax
  PTP_WORK ThreadpoolWork; // rax

  v2 = (char *)this + 976;
  v4 = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 888) = *(_OWORD *)a2;
  v5 = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 904) = v4;
  *(_QWORD *)&v4 = *((_QWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 920) = v5;
  *((_QWORD *)this + 117) = v4;
  if ( !*((_BYTE *)this + 1016) )
  {
    InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 976), 0xFA0u);
    v2[40] = 1;
  }
  v6 = 16;
  if ( *((_BYTE *)this + 937) )
    v6 = *((unsigned __int8 *)this + 937);
  *((_BYTE *)this + 864) = v6;
  PoolWithTag = SmFx::Memory::AllocatePoolWithTag(v6, 2LL * (unsigned __int8)v6);
  *((_QWORD *)this + 109) = PoolWithTag;
  if ( !PoolWithTag )
    return -1073741670;
  if ( !*((_BYTE *)this + 936) )
    goto LABEL_17;
  if ( *((_QWORD *)this + 128) )
    return -1073278049;
  ThreadpoolWork = CreateThreadpoolWork(
                     lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_,
                     (char *)this + 1024,
                     0);
  *((_QWORD *)this + 128) = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    *((_QWORD *)this + 130) = this;
    *((_QWORD *)this + 129) = lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_;
LABEL_17:
    SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(this);
    return 0;
  }
  if ( (int)GetLastError() > 0 )
    result = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    result = GetLastError();
  if ( result >= 0 )
    goto LABEL_17;
  return result;
}

```

## disassembly

```asm
0x180097fd0  mov     [rsp+arg_0], rbx
0x180097fd5  push    rdi
0x180097fd6  sub     rsp, 20h
0x180097fda  movups  xmm0, xmmword ptr [rdx]
0x180097fdd  lea     rdi, [rcx+3D0h]
0x180097fe4  mov     rbx, rcx
0x180097fe7  movups  xmm1, xmmword ptr [rdx+10h]
0x180097feb  movups  xmmword ptr [rcx+378h], xmm0
0x180097ff2  movups  xmm0, xmmword ptr [rdx+20h]
0x180097ff6  movups  xmmword ptr [rcx+388h], xmm1
0x180097ffd  movsd   xmm1, qword ptr [rdx+30h]
0x180098002  movups  xmmword ptr [rcx+398h], xmm0
0x180098009  movsd   qword ptr [rcx+3A8h], xmm1
0x180098011  cmp     byte ptr [rdi+28h], 0
0x180098015  jnz     short loc_180098029
0x180098017  mov     edx, 0FA0h; dwSpinCount
0x18009801c  mov     rcx, rdi; lpCriticalSection
0x18009801f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180098025  mov     byte ptr [rdi+28h], 1
0x180098029  movzx   eax, byte ptr [rbx+3A9h]
0x180098030  mov     ecx, 10h
0x180098035  test    al, al
0x180098037  cmovnz  ecx, eax
0x18009803a  movzx   edx, cl
0x18009803d  add     rdx, rdx
0x180098040  mov     [rbx+360h], cl
0x180098046  call    ?AllocatePoolWithTag@Memory@SmFx@@YAPEAXW4PoolType@12@_KI@Z; SmFx::Memory::AllocatePoolWithTag(SmFx::Memory::PoolType,unsigned __int64,uint)
0x18009804b  mov     [rbx+368h], rax
0x180098052  test    rax, rax
0x180098055  jnz     short loc_18009805E
0x180098057  mov     eax, 0C000009Ah
0x18009805c  jmp     short loc_1800980D5
0x18009805e  cmp     byte ptr [rbx+3A8h], 0
0x180098065  jz      short loc_1800980CB
0x180098067  lea     rdi, [rbx+400h]
0x18009806e  cmp     qword ptr [rdi], 0
0x180098072  jz      short loc_18009807B
0x180098074  mov     eax, 0C007139Fh
0x180098079  jmp     short loc_1800980D5
0x18009807b  xor     r8d, r8d; pcbe
0x18009807e  lea     rcx, _lambda_8a03d23fdee2c1785e106aafab25a0f7____lambda_invoker_cdecl_; pfnwk
0x180098085  mov     rdx, rdi; pv
0x180098088  call    cs:__imp_CreateThreadpoolWork
0x18009808e  mov     [rdi], rax
0x180098091  test    rax, rax
0x180098094  jnz     short loc_1800980BC
0x180098096  call    cs:__imp_GetLastError
0x18009809c  test    eax, eax
0x18009809e  jg      short loc_1800980A8
0x1800980a0  call    cs:__imp_GetLastError
0x1800980a6  jmp     short loc_1800980B6
0x1800980a8  call    cs:__imp_GetLastError
0x1800980ae  movzx   eax, ax
0x1800980b1  or      eax, 0C0070000h
0x1800980b6  test    eax, eax
0x1800980b8  jns     short loc_1800980CB
0x1800980ba  jmp     short loc_1800980D5
0x1800980bc  lea     rax, _lambda_c276094d149607b901f7fae525da7e78____lambda_invoker_cdecl_
0x1800980c3  mov     [rdi+10h], rbx
0x1800980c7  mov     [rdi+8], rax
0x1800980cb  mov     rcx, rbx; this
0x1800980ce  call    ?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)
0x1800980d3  xor     eax, eax
0x1800980d5  mov     rbx, [rsp+28h+arg_0]
0x1800980da  add     rsp, 20h
0x1800980de  pop     rdi
0x1800980df  retn
```
