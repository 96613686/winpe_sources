# MbbNdisSmsDelete(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140016ed0`
- end: `0x140016f3c`
- name: `?MbbNdisSmsDelete@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `108`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140016ed0`
- `0x1400208bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140016ef5`
- `ntoskrnl!ExAllocatePool2` at `0x140016ef5`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsDelete(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 Pool2; // rax

  *a3 = 12;
  Pool2 = ExAllocatePool2(64, 8, 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  *((_QWORD *)a1 + 70) = Pool2;
  *(_DWORD *)Pool2 = *((_DWORD *)a2 + 1);
  *(_DWORD *)(Pool2 + 4) = *((_DWORD *)a2 + 2);
  return MbbUtilSetAttributeWithParameter(a1, (unsigned __int8 *)Pool2, 8u);
}

```

## disassembly

```asm
0x140016ed0  mov     [rsp+arg_0], rbx
0x140016ed5  push    rdi
0x140016ed6  sub     rsp, 20h
0x140016eda  mov     rbx, rdx
0x140016edd  mov     dword ptr [r8], 0Ch
0x140016ee4  mov     edx, 8
0x140016ee9  mov     rdi, rcx
0x140016eec  mov     r8d, 6458424Dh
0x140016ef2  lea     ecx, [rdx+38h]
0x140016ef5  call    cs:__imp_ExAllocatePool2
0x140016efc  nop     dword ptr [rax+rax+00h]
0x140016f01  mov     rdx, rax; unsigned __int8 *
0x140016f04  test    rax, rax
0x140016f07  jnz     short loc_140016F10
0x140016f09  mov     eax, 0C000009Ah
0x140016f0e  jmp     short loc_140016F30
0x140016f10  mov     [rdi+230h], rdx
0x140016f17  mov     r8d, 8; unsigned int
0x140016f1d  mov     eax, [rbx+4]
0x140016f20  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x140016f23  mov     [rdx], eax
0x140016f25  mov     eax, [rbx+8]
0x140016f28  mov     [rdx+4], eax
0x140016f2b  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140016f30  mov     rbx, [rsp+28h+arg_0]
0x140016f35  add     rsp, 20h
0x140016f39  pop     rdi
0x140016f3a  retn
```
