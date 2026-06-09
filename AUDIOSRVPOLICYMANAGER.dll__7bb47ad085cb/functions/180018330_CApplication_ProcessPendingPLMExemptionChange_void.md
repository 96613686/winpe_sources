# CApplication::ProcessPendingPLMExemptionChange(void)

- ea: `0x180018330`
- end: `0x180018419`
- name: `?ProcessPendingPLMExemptionChange@CApplication@@IEAAXXZ`
- size: `233`
- prototype: `void __fastcall(CApplication *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018d00`

## callees

- `0x180017910`
- `0x180018330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001834d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001834d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018362`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001839b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018362`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001839b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CApplication::ProcessPendingPLMExemptionChange(CApplication *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // edi
  int v4; // r14d
  _QWORD *v5; // rdi
  __int64 v6; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  while ( 1 )
  {
    EnterCriticalSection(v2);
    if ( *((_DWORD *)this + 94) )
    {
      v3 = *((_DWORD *)this + 94);
      if ( v3 != GetCurrentThreadId() )
        break;
    }
    if ( !*((_DWORD *)this + 95) )
    {
      *((_DWORD *)this + 94) = 0;
      if ( !v2 )
        return;
      goto LABEL_6;
    }
    *((_DWORD *)this + 94) = GetCurrentThreadId();
    v4 = *((_DWORD *)this + 95);
    *((_DWORD *)this + 95) = 0;
    if ( v2 )
      LeaveCriticalSection(v2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v5 = (_QWORD *)*((_QWORD *)this + 9);
    while ( v5 )
    {
      v6 = v5[2];
      v5 = (_QWORD *)*v5;
      CProcess::NotifyPLM(v6, v4);
    }
    if ( this != (CApplication *)-32LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
  if ( v2 )
LABEL_6:
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180018330  push    rbx
0x180018332  push    rbp
0x180018333  push    rsi
0x180018334  push    rdi
0x180018335  push    r14
0x180018337  push    r15
0x180018339  sub     rsp, 28h
0x18001833d  mov     rbx, rcx
0x180018340  lea     rsi, [rcx+150h]
0x180018347  xor     r15d, r15d
0x18001834a  mov     rcx, rsi; lpCriticalSection
0x18001834d  call    cs:__imp_EnterCriticalSection
0x180018353  cmp     dword ptr [rbx+178h], 0
0x18001835a  jz      short loc_180018370
0x18001835c  mov     edi, [rbx+178h]
0x180018362  call    cs:__imp_GetCurrentThreadId
0x180018368  cmp     edi, eax
0x18001836a  jnz     loc_18001840B
0x180018370  cmp     dword ptr [rbx+17Ch], 0
0x180018377  jnz     short loc_18001839B
0x180018379  mov     [rbx+178h], r15d
0x180018380  test    rsi, rsi
0x180018383  jz      short loc_18001838E
0x180018385  mov     rcx, rsi; lpCriticalSection
0x180018388  call    cs:__imp_LeaveCriticalSection
0x18001838e  add     rsp, 28h
0x180018392  pop     r15
0x180018394  pop     r14
0x180018396  pop     rdi
0x180018397  pop     rsi
0x180018398  pop     rbp
0x180018399  pop     rbx
0x18001839a  retn
0x18001839b  call    cs:__imp_GetCurrentThreadId
0x1800183a1  mov     [rbx+178h], eax
0x1800183a7  mov     r14d, [rbx+17Ch]
0x1800183ae  mov     [rbx+17Ch], r15d
0x1800183b5  test    rsi, rsi
0x1800183b8  jnz     short loc_180018400
0x1800183ba  lea     rbp, [rbx+20h]
0x1800183be  mov     rcx, rbp; lpCriticalSection
0x1800183c1  call    cs:__imp_EnterCriticalSection
0x1800183c7  mov     [rsp+58h+arg_0], rbp
0x1800183cc  mov     rdi, [rbx+48h]
0x1800183d0  test    rdi, rdi
0x1800183d3  jz      short loc_1800183E9
0x1800183d5  mov     rcx, [rdi+10h]
0x1800183d9  mov     rdi, [rdi]
0x1800183dc  mov     edx, r14d
0x1800183df  call    ?NotifyPLM@CProcess@@QEAAXW4_PLM_EXEMPTION@@@Z; CProcess::NotifyPLM(_PLM_EXEMPTION)
0x1800183e4  test    rdi, rdi
0x1800183e7  jnz     short loc_1800183D5
0x1800183e9  test    rbp, rbp
0x1800183ec  jz      loc_18001834A
0x1800183f2  mov     rcx, rbp; lpCriticalSection
0x1800183f5  call    cs:__imp_LeaveCriticalSection
0x1800183fb  jmp     loc_18001834A
0x180018400  mov     rcx, rsi; lpCriticalSection
0x180018403  call    cs:__imp_LeaveCriticalSection
0x180018409  jmp     short loc_1800183BA
0x18001840b  test    rsi, rsi
0x18001840e  jz      loc_18001838E
0x180018414  jmp     loc_180018385
```
