# MbbIpGetConfiguration(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x14000f9c0`
- end: `0x14000fa28`
- name: `?MbbIpGetConfiguration@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `104`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000f9c0`
- `0x14001fc2c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f9d7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f9d7`

## pseudocode

```c
__int64 __fastcall MbbIpGetConfiguration(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 Pool2; // rdx
  int v7; // eax

  Pool2 = ExAllocatePool2(64, 60, 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  v7 = *((_DWORD *)a1 + 188);
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *((_QWORD *)a1 + 70) = Pool2;
  *(_OWORD *)(Pool2 + 32) = 0;
  *(_OWORD *)(Pool2 + 44) = 0;
  *(_DWORD *)Pool2 = v7;
  return MbbUtilQueryAttributeWithParameter(a1, (unsigned __int8 *)Pool2, 0x3Cu);
}

```

## disassembly

```asm
0x14000f9c0  push    rbx
0x14000f9c2  sub     rsp, 20h
0x14000f9c6  mov     edx, 3Ch ; '<'
0x14000f9cb  mov     rbx, rcx
0x14000f9ce  mov     r8d, 6458424Dh
0x14000f9d4  lea     ecx, [rdx+4]
0x14000f9d7  call    cs:__imp_ExAllocatePool2
0x14000f9de  nop     dword ptr [rax+rax+00h]
0x14000f9e3  mov     rdx, rax; unsigned __int8 *
0x14000f9e6  test    rax, rax
0x14000f9e9  jnz     short loc_14000F9F2
0x14000f9eb  mov     eax, 0C000009Ah
0x14000f9f0  jmp     short loc_14000FA21
0x14000f9f2  mov     eax, [rbx+2F0h]
0x14000f9f8  xorps   xmm0, xmm0
0x14000f9fb  movups  xmmword ptr [rdx], xmm0
0x14000f9fe  mov     r8d, 3Ch ; '<'; unsigned int
0x14000fa04  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14000fa07  movups  xmmword ptr [rdx+10h], xmm0
0x14000fa0b  mov     [rbx+230h], rdx
0x14000fa12  movups  xmmword ptr [rdx+20h], xmm0
0x14000fa16  movups  xmmword ptr [rdx+2Ch], xmm0
0x14000fa1a  mov     [rdx], eax
0x14000fa1c  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x14000fa21  add     rsp, 20h
0x14000fa25  pop     rbx
0x14000fa26  retn
```
