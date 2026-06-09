# pplx::details::_Task_impl<bool>::_TransitionedToStarted(void)

- ea: `0x180015838`
- end: `0x180015884`
- name: `?_TransitionedToStarted@?$_Task_impl@_N@details@pplx@@QEAA_NXZ`
- size: `76`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180015af0`
- `0x180015b50`
- `0x18001da40`
- `0x18001daa0`
- `0x18001db00`
- `0x18002e470`
- `0x18002e4d0`
- `0x18002e530`
- `0x18002e590`
- `0x18002e5f0`
- `0x18002e650`
- `0x18002e6b0`
- `0x18002e710`
- `0x18002e770`
- `0x18002e7d0`
- `0x18002e830`
- `0x18002e890`
- `0x18002e970`
- `0x18002ea70`
- `0x18002ead0`
- `0x1800384d0`
- `0x180038530`
- `0x180038590`
- `0x1800385f0`
- `0x1800386b0`
- `0x180038770`
- `0x18004d7f0`
- `0x18004d850`
- `0x18004d8b0`
- `0x18004d910`
- `0x18004d970`
- `0x18004d9d0`
- `0x18004da30`
- `0x18004dbb0`
- `0x18004dc10`
- `0x18004dc70`
- `0x18004dcd0`

## callees

- `0x180015838`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001584e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001584e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001586c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001586c`

## pseudocode

```c
char __fastcall pplx::details::_Task_impl<bool>::_TransitionedToStarted(__int64 a1)
{
  char v2; // bl

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  if ( *(_DWORD *)(a1 + 8) == 2 )
  {
    v2 = 0;
  }
  else
  {
    v2 = 1;
    *(_DWORD *)(a1 + 8) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  return v2;
}

```

## disassembly

```asm
0x180015838  mov     [rsp+arg_0], rbx
0x18001583d  mov     [rsp+arg_8], rsi
0x180015842  push    rdi
0x180015843  sub     rsp, 20h
0x180015847  mov     rdi, rcx
0x18001584a  add     rcx, 20h ; ' '; lpCriticalSection
0x18001584e  call    cs:__imp_EnterCriticalSection
0x180015854  mov     eax, [rdi+8]
0x180015857  cmp     eax, 2
0x18001585a  jnz     short loc_180015860
0x18001585c  xor     bl, bl
0x18001585e  jmp     short loc_180015868
0x180015860  mov     ebx, 1
0x180015865  mov     [rdi+8], ebx
0x180015868  lea     rcx, [rdi+20h]; lpCriticalSection
0x18001586c  call    cs:__imp_LeaveCriticalSection
0x180015872  mov     rsi, [rsp+28h+arg_8]
0x180015877  mov     al, bl
0x180015879  mov     rbx, [rsp+28h+arg_0]
0x18001587e  add     rsp, 20h
0x180015882  pop     rdi
0x180015883  retn
```
