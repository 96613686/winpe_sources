# MbbNdisSmsRead(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x140016f50`
- end: `0x140016fc9`
- name: `?MbbNdisSmsRead@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `121`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140016f50`
- `0x14001fc2c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140016f6e`
- `ntoskrnl!ExAllocatePool2` at `0x140016f6e`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsRead(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 Pool2; // rax
  __int64 v7; // rdx
  int v9; // eax
  int v10; // ecx

  Pool2 = ExAllocatePool2(64, 12, 1683505741);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *((_QWORD *)a1 + 70) = Pool2;
  v9 = 0;
  v10 = *((_DWORD *)a2 + 1);
  if ( v10 )
  {
    LOBYTE(v9) = v10 != 4;
    ++v9;
  }
  *(_DWORD *)v7 = v9;
  *(_DWORD *)(v7 + 4) = *((_DWORD *)a2 + 2);
  *(_DWORD *)(v7 + 8) = *((_DWORD *)a2 + 3);
  return MbbUtilQueryAttributeWithParameter(a1, (unsigned __int8 *)v7, 0xCu);
}

```

## disassembly

```asm
0x140016f50  mov     [rsp+arg_0], rbx
0x140016f55  push    rdi
0x140016f56  sub     rsp, 20h
0x140016f5a  mov     rbx, rdx
0x140016f5d  mov     rdi, rcx
0x140016f60  mov     edx, 0Ch
0x140016f65  mov     r8d, 6458424Dh
0x140016f6b  lea     ecx, [rdx+34h]
0x140016f6e  call    cs:__imp_ExAllocatePool2
0x140016f75  nop     dword ptr [rax+rax+00h]
0x140016f7a  mov     rdx, rax; unsigned __int8 *
0x140016f7d  test    rax, rax
0x140016f80  jnz     short loc_140016F89
0x140016f82  mov     eax, 0C000009Ah
0x140016f87  jmp     short loc_140016FBD
0x140016f89  mov     [rdi+230h], rdx
0x140016f90  xor     eax, eax
0x140016f92  mov     ecx, [rbx+4]
0x140016f95  test    ecx, ecx
0x140016f97  jz      short loc_140016FA1
0x140016f99  cmp     ecx, 4
0x140016f9c  setnz   al
0x140016f9f  inc     eax
0x140016fa1  mov     [rdx], eax
0x140016fa3  mov     r8d, 0Ch; unsigned int
0x140016fa9  mov     eax, [rbx+8]
0x140016fac  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x140016faf  mov     [rdx+4], eax
0x140016fb2  mov     eax, [rbx+0Ch]
0x140016fb5  mov     [rdx+8], eax
0x140016fb8  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140016fbd  mov     rbx, [rsp+28h+arg_0]
0x140016fc2  add     rsp, 20h
0x140016fc6  pop     rdi
0x140016fc7  retn
```
