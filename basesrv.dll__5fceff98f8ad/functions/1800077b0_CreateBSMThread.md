# CreateBSMThread

- ea: `0x1800077b0`
- end: `0x180007817`
- name: `CreateBSMThread`
- size: `103`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002010`

## callees

- `0x1800077b0`

## import_xrefs

- `ntdll!RtlCreateUserThread` at `0x180007805`
- `ntdll!RtlCreateUserThread` at `0x180007805`

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
0x1800077b0  sub     rsp, 58h
0x1800077b4  mov     rax, cs:BaseSrvpStaticServerData
0x1800077bb  cmp     byte ptr [rax+9CCh], 0
0x1800077c2  jnz     short loc_1800077CF
0x1800077c4  mov     eax, 0C0000022h
0x1800077c9  add     rsp, 58h
0x1800077cd  retn
0x1800077cf  xor     ecx, ecx
0x1800077d1  lea     rax, BaseSrvBSMThread
0x1800077d8  mov     [rsp+58h+Reserved8], rcx; Reserved8
0x1800077dd  xor     r9d, r9d; Reserved2
0x1800077e0  mov     [rsp+58h+Reserved7], rcx; Reserved7
0x1800077e5  xor     r8d, r8d; Reserved1
0x1800077e8  mov     [rsp+58h+Reserved6], rcx; Reserved6
0x1800077ed  xor     edx, edx; OutThreadHandle
0x1800077ef  mov     [rsp+58h+Reserved5], rax; Reserved5
0x1800077f4  mov     [rsp+58h+Reserved4], rcx; Reserved4
0x1800077f9  mov     [rsp+58h+Reserved3], rcx; Reserved3
0x1800077fe  mov     rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180007805  call    cs:__imp_RtlCreateUserThread
0x18000780c  nop     dword ptr [rax+rax+00h]
0x180007811  add     rsp, 58h
0x180007815  retn
```
