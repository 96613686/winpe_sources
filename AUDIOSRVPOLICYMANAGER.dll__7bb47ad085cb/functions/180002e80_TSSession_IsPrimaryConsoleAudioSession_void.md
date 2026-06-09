# TSSession::IsPrimaryConsoleAudioSession(void)

- ea: `0x180002e80`
- end: `0x180002eb6`
- name: `?IsPrimaryConsoleAudioSession@TSSession@@QEAAHXZ`
- size: `54`
- prototype: `__int64 __fastcall(TSSession *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180002d68`
- `0x180002e04`
- `0x1800037d0`
- `0x18002890c`

## callees

- `0x180002e80`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002e8f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002e8f`

## pseudocode

```c
_BOOL8 __fastcall TSSession::IsPrimaryConsoleAudioSession(TSSession *this)
{
  int v1; // ebx

  v1 = *(_DWORD *)this;
  return v1 != (unsigned int)RtlGetCurrentServiceSessionId() && *((_DWORD *)this + 278);
}

```

## disassembly

```asm
0x180002e80  mov     [rsp+arg_0], rbx
0x180002e85  push    rdi
0x180002e86  sub     rsp, 20h
0x180002e8a  mov     ebx, [rcx]
0x180002e8c  mov     rdi, rcx
0x180002e8f  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180002e95  cmp     ebx, eax
0x180002e97  jz      short loc_180002EA9
0x180002e99  cmp     dword ptr [rdi+458h], 0
0x180002ea0  jz      short loc_180002EA9
0x180002ea2  mov     eax, 1
0x180002ea7  jmp     short loc_180002EAB
0x180002ea9  xor     eax, eax
0x180002eab  mov     rbx, [rsp+28h+arg_0]
0x180002eb0  add     rsp, 20h
0x180002eb4  pop     rdi
0x180002eb5  retn
```
