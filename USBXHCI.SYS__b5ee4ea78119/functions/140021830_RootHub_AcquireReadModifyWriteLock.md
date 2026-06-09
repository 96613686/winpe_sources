# RootHub_AcquireReadModifyWriteLock

- ea: `0x140021830`
- end: `0x140021896`
- name: `RootHub_AcquireReadModifyWriteLock`
- size: `102`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018514`
- `0x140019454`
- `0x140019828`
- `0x14001999c`
- `0x14001a6fc`
- `0x14001d1d0`
- `0x14001fe00`
- `0x140023cd4`
- `0x14002aea0`
- `0x140032ba4`
- `0x14004a044`
- `0x14004b16c`
- `0x14004f9e0`

## callees

- `0x1400110e0`
- `0x140021830`
- `0x1400218a0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140021847`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021847`

## pseudocode

```c
__int64 __fastcall RootHub_AcquireReadModifyWriteLock(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  char v4; // si
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 result; // rax

  v2 = a2;
  v4 = 0;
  if ( KeGetCurrentIrql() == 2 )
  {
    v5 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE *)(v5 + 1041) )
    {
      Controller_LowerAndTrackIrql(v5);
      v4 = 1;
    }
  }
  v6 = *(_QWORD *)(a1 + 48);
  v7 = 120 * v2;
  result = DynamicLock_Acquire(*(_QWORD *)(v7 + v6 + 24));
  *(_BYTE *)(v7 + v6 + 32) = v4;
  return result;
}

```

## disassembly

```asm
0x140021830  mov     [rsp+arg_0], rbx
0x140021835  mov     [rsp+arg_8], rsi
0x14002183a  push    rdi
0x14002183b  sub     rsp, 20h
0x14002183f  mov     edi, edx
0x140021841  mov     rbx, rcx
0x140021844  xor     sil, sil
0x140021847  call    cs:__imp_KeGetCurrentIrql
0x14002184e  nop     dword ptr [rax+rax+00h]
0x140021853  cmp     al, 2
0x140021855  jnz     short loc_140021864
0x140021857  mov     rcx, [rbx+8]
0x14002185b  cmp     [rcx+411h], sil
0x140021862  jnz     short loc_14002188C
0x140021864  mov     rbx, [rbx+30h]
0x140021868  imul    rdi, 78h ; 'x'
0x14002186c  mov     rcx, [rdi+rbx+18h]
0x140021871  call    DynamicLock_Acquire
0x140021876  mov     [rdi+rbx+20h], sil
0x14002187b  mov     rbx, [rsp+28h+arg_0]
0x140021880  mov     rsi, [rsp+28h+arg_8]
0x140021885  add     rsp, 20h
0x140021889  pop     rdi
0x14002188a  retn
0x14002188c  call    Controller_LowerAndTrackIrql
0x140021891  mov     sil, 1
0x140021894  jmp     short loc_140021864
```
