# VfsDispatchControl

- ea: `0x1400085f0`
- end: `0x140008643`
- name: `VfsDispatchControl`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400085f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000862e`
- `ntoskrnl!IofCompleteRequest` at `0x14000862e`

## pseudocode

```c
__int64 __fastcall VfsDispatchControl(__int64 a1, __int64 a2)
{
  char v2; // cl
  unsigned int v3; // ebx

  v2 = **(_BYTE **)(a2 + 184);
  if ( !v2 || v2 == 2 || v2 == 16 || v2 == 18 )
    v3 = 0;
  else
    v3 = -1073741811;
  *(_DWORD *)(a2 + 48) = v3;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
  return v3;
}

```

## disassembly

```asm
0x1400085f0  push    rbx
0x1400085f2  sub     rsp, 20h
0x1400085f6  mov     rax, [rdx+0B8h]
0x1400085fd  mov     r8, rdx
0x140008600  mov     cl, [rax]
0x140008602  test    cl, cl
0x140008604  jz      short loc_14000861C
0x140008606  cmp     cl, 2
0x140008609  jz      short loc_14000861C
0x14000860b  cmp     cl, 10h
0x14000860e  jz      short loc_14000861C
0x140008610  cmp     cl, 12h
0x140008613  jz      short loc_14000861C
0x140008615  mov     ebx, 0C000000Dh
0x14000861a  jmp     short loc_14000861E
0x14000861c  xor     ebx, ebx
0x14000861e  mov     [rdx+30h], ebx
0x140008621  mov     rcx, r8; Irp
0x140008624  mov     qword ptr [rdx+38h], 0
0x14000862c  xor     edx, edx; PriorityBoost
0x14000862e  call    cs:__imp_IofCompleteRequest
0x140008635  nop     dword ptr [rax+rax+00h]
0x14000863a  mov     eax, ebx
0x14000863c  add     rsp, 20h
0x140008640  pop     rbx
0x140008641  retn
```
