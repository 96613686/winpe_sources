# MbbUtilIsNativeMbnService(_GUID *)

- ea: `0x14001f5b8`
- end: `0x14001f60b`
- name: `?MbbUtilIsNativeMbnService@@YAEPEAU_GUID@@@Z`
- size: `83`
- prototype: `unsigned __int8 __fastcall(struct _GUID *Source2)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400101d0`
- `0x140011dd0`
- `0x140014540`
- `0x14002373c`

## callees

- `0x14001f5b8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001f5e0`
- `ntoskrnl!RtlCompareMemory` at `0x14001f5e0`

## pseudocode

```c
unsigned __int8 __fastcall MbbUtilIsNativeMbnService(struct _GUID *Source2)
{
  int v2; // ebx

  v2 = 0;
  while ( RtlCompareMemory(&xmmword_14005E160[v2], Source2, 0x10u) != 16 )
  {
    if ( (unsigned int)++v2 >= 7 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14001f5b8  mov     [rsp+arg_0], rbx
0x14001f5bd  push    rdi
0x14001f5be  sub     rsp, 20h
0x14001f5c2  mov     rdi, rcx
0x14001f5c5  xor     ebx, ebx
0x14001f5c7  lea     rax, xmmword_14005E160
0x14001f5ce  mov     ecx, ebx
0x14001f5d0  shl     rcx, 4
0x14001f5d4  mov     r8d, 10h; Length
0x14001f5da  add     rcx, rax; Source1
0x14001f5dd  mov     rdx, rdi; Source2
0x14001f5e0  call    cs:__imp_RtlCompareMemory
0x14001f5e7  nop     dword ptr [rax+rax+00h]
0x14001f5ec  cmp     rax, 10h
0x14001f5f0  jz      short loc_14001F5FD
0x14001f5f2  inc     ebx
0x14001f5f4  cmp     ebx, 7
0x14001f5f7  jb      short loc_14001F5C7
0x14001f5f9  xor     al, al
0x14001f5fb  jmp     short loc_14001F5FF
0x14001f5fd  mov     al, 1
0x14001f5ff  mov     rbx, [rsp+28h+arg_0]
0x14001f604  add     rsp, 20h
0x14001f608  pop     rdi
0x14001f609  retn
```
