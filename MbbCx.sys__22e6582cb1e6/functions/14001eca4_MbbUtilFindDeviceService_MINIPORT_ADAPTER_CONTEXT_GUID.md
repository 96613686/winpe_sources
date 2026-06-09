# MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)

- ea: `0x14001eca4`
- end: `0x14001ed0a`
- name: `?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z`
- size: `102`
- prototype: `struct _MBB_DS *__fastcall(struct _MINIPORT_ADAPTER_CONTEXT *, struct _GUID *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002edc`
- `0x140004004`
- `0x140004c70`
- `0x14000bb48`
- `0x14000ff80`
- `0x14002373c`

## callees

- `0x14001eca4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001ecd5`
- `ntoskrnl!RtlCompareMemory` at `0x14001ecd5`

## pseudocode

```c
struct _MBB_DS *__fastcall MbbUtilFindDeviceService(struct _MINIPORT_ADAPTER_CONTEXT *a1, struct _GUID *a2)
{
  __int64 v2; // rbx

  v2 = 0;
  if ( !*((_DWORD *)a1 + 276) )
    return 0;
  while ( RtlCompareMemory((const void *)(*((_QWORD *)a1 + 139) + 40 * v2), a2, 0x10u) != 16 )
  {
    v2 = (unsigned int)(v2 + 1);
    if ( (unsigned int)v2 >= *((_DWORD *)a1 + 276) )
      return 0;
  }
  return (struct _MBB_DS *)(*((_QWORD *)a1 + 139) + 40 * v2);
}

```

## disassembly

```asm
0x14001eca4  push    rbx
0x14001eca6  push    rbp
0x14001eca7  push    rsi
0x14001eca8  push    rdi
0x14001eca9  sub     rsp, 28h
0x14001ecad  xor     ebx, ebx
0x14001ecaf  mov     rbp, rdx
0x14001ecb2  mov     rdi, rcx
0x14001ecb5  cmp     [rcx+450h], ebx
0x14001ecbb  jbe     short loc_14001ECF1
0x14001ecbd  mov     rax, [rdi+458h]
0x14001ecc4  lea     rsi, [rbx+rbx*4]
0x14001ecc8  mov     r8d, 10h; Length
0x14001ecce  mov     rdx, rbp; Source2
0x14001ecd1  lea     rcx, [rax+rsi*8]; Source1
0x14001ecd5  call    cs:__imp_RtlCompareMemory
0x14001ecdc  nop     dword ptr [rax+rax+00h]
0x14001ece1  cmp     rax, 10h
0x14001ece5  jz      short loc_14001ECFD
0x14001ece7  inc     ebx
0x14001ece9  cmp     ebx, [rdi+450h]
0x14001ecef  jb      short loc_14001ECBD
0x14001ecf1  xor     eax, eax
0x14001ecf3  add     rsp, 28h
0x14001ecf7  pop     rdi
0x14001ecf8  pop     rsi
0x14001ecf9  pop     rbp
0x14001ecfa  pop     rbx
0x14001ecfb  retn
0x14001ecfd  mov     rax, [rdi+458h]
0x14001ed04  lea     rax, [rax+rsi*8]
0x14001ed08  jmp     short loc_14001ECF3
```
