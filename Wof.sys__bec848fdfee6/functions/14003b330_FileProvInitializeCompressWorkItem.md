# FileProvInitializeCompressWorkItem

- ea: `0x14003b330`
- end: `0x14003b3fd`
- name: `FileProvInitializeCompressWorkItem`
- size: `205`
- prototype: `__int64 __fastcall(_DWORD *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b0c8`

## callees

- `0x140011270`
- `0x14003b330`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b36d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b36d`
- `ntoskrnl!KeInitializeEvent` at `0x14003b3a0`
- `ntoskrnl!KeInitializeEvent` at `0x14003b3a0`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompressWorkItem(_DWORD *a1, int a2, __int64 a3, __int64 a4)
{
  _BYTE *v7; // rax
  int v8; // r9d
  unsigned int v9; // edi

  *(_QWORD *)(a4 + 40) = a1;
  *(_DWORD *)(a4 + 32) = a2;
  *(_QWORD *)(a4 + 48) = a3;
  *(_QWORD *)(a4 + 16) = FileProvCompressWorkItem;
  *(_QWORD *)(a4 + 24) = a4;
  *(_QWORD *)a4 = 0;
  v7 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 16));
  *(_QWORD *)(a4 + 80) = v7;
  if ( v7 )
  {
    *(_QWORD *)(a4 + 72) = &v7[a1[2]];
    if ( a2 == 1 )
    {
      *(_QWORD *)(a4 + 120) = v7;
      v7[17348] = 0;
      if ( !(unsigned int)LZX_EncodeInit(*(_QWORD *)(a4 + 120), *a1, *a1, v8) )
        return (unsigned int)-1073741823;
      *(_BYTE *)(*(_QWORD *)(a4 + 120) + 17348LL) = 1;
    }
    v9 = 0;
    KeInitializeEvent((PRKEVENT)(a4 + 96), SynchronizationEvent, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x14003b330  mov     [rsp+arg_0], rbx
0x14003b335  mov     [rsp+arg_8], rsi
0x14003b33a  push    rdi
0x14003b33b  sub     rsp, 40h
0x14003b33f  mov     [r9+28h], rcx
0x14003b343  lea     rax, FileProvCompressWorkItem
0x14003b34a  mov     [r9+20h], edx
0x14003b34e  mov     rbx, r9
0x14003b351  mov     [r9+30h], r8
0x14003b355  mov     rdi, rcx
0x14003b358  add     rcx, 40h ; '@'; Lookaside
0x14003b35c  mov     [r9+10h], rax
0x14003b360  mov     [r9+18h], rbx
0x14003b364  mov     esi, edx
0x14003b366  mov     qword ptr [r9], 0
0x14003b36d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003b374  nop     dword ptr [rax+rax+00h]
0x14003b379  mov     [rbx+50h], rax
0x14003b37d  mov     r8, rax
0x14003b380  test    rax, rax
0x14003b383  jz      short loc_14003B3BF
0x14003b385  mov     eax, [rdi+8]
0x14003b388  add     rax, r8
0x14003b38b  mov     [rbx+48h], rax
0x14003b38f  cmp     esi, 1
0x14003b392  jz      short loc_14003B3C6
0x14003b394  xor     edi, edi
0x14003b396  lea     rcx, [rbx+60h]; Event
0x14003b39a  xor     r8d, r8d; State
0x14003b39d  lea     edx, [rdi+1]; Type
0x14003b3a0  call    cs:__imp_KeInitializeEvent
0x14003b3a7  nop     dword ptr [rax+rax+00h]
0x14003b3ac  mov     rbx, [rsp+48h+arg_0]
0x14003b3b1  mov     eax, edi
0x14003b3b3  mov     rsi, [rsp+48h+arg_8]
0x14003b3b8  add     rsp, 40h
0x14003b3bc  pop     rdi
0x14003b3bd  retn
0x14003b3bf  mov     edi, 0C000009Ah
0x14003b3c4  jmp     short loc_14003B3AC
0x14003b3c6  mov     [rbx+78h], r8
0x14003b3ca  mov     byte ptr [r8+43C4h], 0
0x14003b3d2  mov     rcx, [rbx+78h]
0x14003b3d6  mov     edx, [rdi]
0x14003b3d8  mov     r8d, edx
0x14003b3db  mov     [rsp+48h+var_18], rcx
0x14003b3e0  call    LZX_EncodeInit
0x14003b3e5  test    eax, eax
0x14003b3e7  jnz     short loc_14003B3F0
0x14003b3e9  mov     edi, 0C0000001h
0x14003b3ee  jmp     short loc_14003B3AC
0x14003b3f0  mov     rax, [rbx+78h]
0x14003b3f4  mov     byte ptr [rax+43C4h], 1
0x14003b3fb  jmp     short loc_14003B394
```
