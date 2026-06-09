# SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEvent(ushort)

- ea: `0x18009775c`
- end: `0x1800977f4`
- name: `?EnqueueEvent@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAXG@Z`
- size: `152`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this, unsigned __int16)`
- caller_count: `122`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fa8c`
- `0x1800200f8`
- `0x180020e00`
- `0x180023e50`
- `0x180028890`
- `0x18002b718`
- `0x18002b7d0`
- `0x180030630`
- `0x180030a0c`
- `0x180030adc`
- `0x180030d5c`
- `0x180031050`
- `0x18003255c`
- `0x180032624`
- `0x18003471c`
- `0x180036640`
- `0x180036820`
- `0x180036a00`
- `0x180036bf0`
- `0x180036fa0`
- `0x1800385f0`
- `0x180039a50`
- `0x18004930c`
- `0x180049844`
- `0x18004a51c`
- `0x18004c98c`
- `0x18004cff0`
- `0x180050d28`
- `0x18005153c`
- `0x18005194c`
- `0x180053aa4`
- `0x180054158`
- `0x1800586c0`
- `0x180059180`
- `0x180059248`
- `0x180059318`
- `0x18005aab0`
- `0x18005ab70`
- `0x18005ad90`
- `0x18005aeb0`
- `0x18005c798`
- `0x18005d060`
- `0x18005eaf0`
- `0x18005eee0`
- `0x18005f390`
- `0x18005f800`
- `0x18006cf08`
- `0x18006ee10`
- `0x18006ee30`
- `0x180071940`

## callees

- `0x18009775c`
- `0x1800977fc`
- `0x1800981a8`
- `0x180098454`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800977b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800977b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180097775`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180097775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800977ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800977ec`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEvent(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this,
        unsigned __int16 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // eax
  bool v6; // di

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  v5 = *((_DWORD *)this + 243);
  if ( v5 == 5 )
  {
    if ( a2 == *((_WORD *)this + 440) )
    {
      SmFx::StateMachineEngine::StateMachineEngineImpl::LogEventEnqueue(this, a2);
      *((_WORD *)this + 440) = 0;
LABEL_5:
      *((_WORD *)this + 483) = 0;
      *((_DWORD *)this + 242) = GetCurrentThreadId();
      SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(this);
      return;
    }
    v6 = 0;
  }
  else
  {
    v6 = v5 == 1;
  }
  if ( SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(this, a2) )
  {
    if ( !v6 )
    {
      LeaveCriticalSection(v2);
      return;
    }
    goto LABEL_5;
  }
}

```

## disassembly

```asm
0x18009775c  push    rbx
0x18009775e  push    rbp
0x18009775f  push    rsi
0x180097760  push    rdi
0x180097761  sub     rsp, 28h
0x180097765  lea     rbp, [rcx+3D0h]
0x18009776c  mov     rbx, rcx
0x18009776f  mov     rcx, rbp; lpCriticalSection
0x180097772  movzx   esi, dx
0x180097775  call    cs:__imp_EnterCriticalSection
0x18009777b  mov     eax, [rbx+3CCh]
0x180097781  cmp     eax, 5
0x180097784  jnz     short loc_1800977CE
0x180097786  cmp     si, [rbx+370h]
0x18009778d  jz      short loc_180097794
0x18009778f  xor     dil, dil
0x180097792  jmp     short loc_1800977D5
0x180097794  movzx   edx, si; unsigned __int16
0x180097797  mov     rcx, rbx; this
0x18009779a  call    ?LogEventEnqueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXG@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::LogEventEnqueue(ushort)
0x18009779f  xor     eax, eax
0x1800977a1  mov     [rbx+370h], ax
0x1800977a8  mov     word ptr [rbx+3C6h], 0
0x1800977b1  call    cs:__imp_GetCurrentThreadId
0x1800977b7  mov     rcx, rbx; this
0x1800977ba  mov     [rbx+3C8h], eax
0x1800977c0  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x1800977c5  add     rsp, 28h
0x1800977c9  pop     rdi
0x1800977ca  pop     rsi
0x1800977cb  pop     rbp
0x1800977cc  pop     rbx
0x1800977cd  retn
0x1800977ce  cmp     eax, 1
0x1800977d1  setz    dil
0x1800977d5  movzx   edx, si; unsigned __int16
0x1800977d8  mov     rcx, rbx; this
0x1800977db  call    ?EnqueueEventWithDisposition@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA_NG@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(ushort)
0x1800977e0  test    al, al
0x1800977e2  jz      short loc_1800977C5
0x1800977e4  test    dil, dil
0x1800977e7  jnz     short loc_1800977A8
0x1800977e9  mov     rcx, rbp; lpCriticalSection
0x1800977ec  call    cs:__imp_LeaveCriticalSection
0x1800977f2  jmp     short loc_1800977C5
```
