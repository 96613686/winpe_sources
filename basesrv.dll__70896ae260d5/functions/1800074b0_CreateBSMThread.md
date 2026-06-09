# CreateBSMThread

- ea: `0x1800074b0`
- end: `0x180007514`
- name: `CreateBSMThread`
- size: `100`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002020`

## callees

- `0x1800074b0`

## import_xrefs

- `ntdll!RtlCreateUserThread` at `0x180007502`
- `ntdll!RtlCreateUserThread` at `0x180007502`

## pseudocode

```c
NTSTATUS CreateBSMThread()
{
  if ( *(_BYTE *)(BaseSrvpStaticServerData + 2508) )
    return RtlCreateUserThread((PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0, 0, 0, BaseSrvBSMThread, 0, 0, 0);
  else
    return -1073741790;
}

```

## disassembly

```asm
0x1800074b0  sub     rsp, 58h
0x1800074b4  mov     rax, cs:BaseSrvpStaticServerData
0x1800074bb  cmp     byte ptr [rax+9CCh], 0
0x1800074c2  jnz     short loc_1800074CF
0x1800074c4  mov     eax, 0C0000022h
0x1800074c9  add     rsp, 58h
0x1800074cd  retn
0x1800074cf  xor     ecx, ecx
0x1800074d1  lea     rax, BaseSrvBSMThread
0x1800074d8  mov     [rsp+58h+Reserved8], rcx; Reserved8
0x1800074dd  xor     edx, edx; OutThreadHandle
0x1800074df  mov     [rsp+58h+Reserved7], rcx; Reserved7
0x1800074e4  xor     r9d, r9d; Reserved2
0x1800074e7  mov     [rsp+58h+Reserved6], rcx; Reserved6
0x1800074ec  xor     r8d, r8d; Reserved1
0x1800074ef  mov     [rsp+58h+Reserved5], rax; Reserved5
0x1800074f4  mov     [rsp+58h+Reserved4], rcx; Reserved4
0x1800074f9  mov     [rsp+58h+Reserved3], rcx; Reserved3
0x1800074fe  lea     rcx, [rdx-1]; ThreadContext
0x180007502  call    cs:__imp_RtlCreateUserThread
0x180007509  nop     dword ptr [rax+rax+00h]
0x18000750e  add     rsp, 58h
0x180007512  retn
```
