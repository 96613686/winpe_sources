# BampProcessesWindowStateUpdate

- ea: `0x140012ea0`
- end: `0x140012ee3`
- name: `BampProcessesWindowStateUpdate`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140012ea0`
- `0x140012eec`

## pseudocode

```c
__int64 __fastcall BampProcessesWindowStateUpdate(unsigned int a1, __int64 a2)
{
  unsigned int i; // ebx
  __int64 result; // rax

  if ( a1 )
  {
    for ( i = 0; i < a1; ++i )
      result = BampProcessWindowStateUpdate(*(_QWORD *)(a2 + 16LL * i), *(_DWORD *)(a2 + 16LL * i + 8));
  }
  return result;
}

```

## disassembly

```asm
0x140012ea0  test    ecx, ecx
0x140012ea2  jz      short locret_140012EE1
0x140012ea4  mov     [rsp+arg_0], rbx
0x140012ea9  mov     [rsp+arg_8], rsi
0x140012eae  push    rdi
0x140012eaf  sub     rsp, 20h
0x140012eb3  mov     rdi, rdx
0x140012eb6  mov     esi, ecx
0x140012eb8  xor     ebx, ebx
0x140012eba  mov     ecx, ebx
0x140012ebc  add     rcx, rcx
0x140012ebf  mov     edx, [rdi+rcx*8+8]
0x140012ec3  mov     rcx, [rdi+rcx*8]
0x140012ec7  call    BampProcessWindowStateUpdate
0x140012ecc  inc     ebx
0x140012ece  cmp     ebx, esi
0x140012ed0  jb      short loc_140012EBA
0x140012ed2  mov     rbx, [rsp+28h+arg_0]
0x140012ed7  mov     rsi, [rsp+28h+arg_8]
0x140012edc  add     rsp, 20h
0x140012ee0  pop     rdi
0x140012ee1  retn
```
