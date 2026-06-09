# AhcpStoreFreeAvlEntry

- ea: `0x14004bcd0`
- end: `0x14004bd7a`
- name: `AhcpStoreFreeAvlEntry`
- size: `170`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, char *Buffer)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14004b8ac`
- `0x14004bc98`

## callees

- `0x140007ad0`
- `0x140007e40`
- `0x14003e364`
- `0x140045d44`
- `0x14004b2b0`
- `0x14004bcd0`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14004bd08`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14004bd08`

## string_xrefs

- `0x14004bd18`: `Failed to delete an element from the AVL table`

## pseudocode

```c
__int64 __fastcall AhcpStoreFreeAvlEntry(PRTL_AVL_TABLE Table, char *Buffer)
{
  __int128 v4; // xmm0
  __int64 v6; // rcx
  void *v7[2]; // [rsp+20h] [rbp-18h] BYREF

  (*(void (__fastcall **)(_QWORD))&Table[1].WhichOrderedElement)(*((_QWORD *)Buffer + 5));
  v4 = *(_OWORD *)(Buffer + 24);
  *((_QWORD *)Buffer + 5) = 0;
  *(_OWORD *)v7 = v4;
  if ( RtlDeleteElementGenericTableAvl(Table, Buffer) )
  {
    if ( v7[1] )
    {
      memset(v7[1], 66, WORD1(v7[0]));
      AslFree(v6, v7[1]);
    }
    return 0;
  }
  else
  {
    AslLogCallPrintf(1, "AhcpStoreFreeAvlEntry", 889, "Failed to delete an element from the AVL table", v7[0]);
    AslAnsiStringFree(v7);
    return 3221226021LL;
  }
}

```

## disassembly

```asm
0x14004bcd0  mov     [rsp+arg_0], rbx
0x14004bcd5  push    rdi
0x14004bcd6  sub     rsp, 30h
0x14004bcda  mov     rax, [rcx+90h]
0x14004bce1  mov     rdi, rcx
0x14004bce4  mov     rcx, [rdx+28h]
0x14004bce8  mov     rbx, rdx
0x14004bceb  call    _guard_dispatch_icall
0x14004bcf0  movups  xmm0, xmmword ptr [rbx+18h]
0x14004bcf4  mov     rdx, rbx; Buffer
0x14004bcf7  mov     qword ptr [rbx+28h], 0
0x14004bcff  mov     rcx, rdi; Table
0x14004bd02  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x14004bd08  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14004bd0f  nop     dword ptr [rax+rax+00h]
0x14004bd14  test    al, al
0x14004bd16  jnz     short loc_14004BD47
0x14004bd18  lea     r9, aFailedToDelete_1; "Failed to delete an element from the AV"...
0x14004bd1f  mov     r8d, 379h
0x14004bd25  lea     rdx, aAhcpstorefreea; "AhcpStoreFreeAvlEntry"
0x14004bd2c  mov     ecx, 1
0x14004bd31  call    AslLogCallPrintf
0x14004bd36  lea     rcx, [rsp+38h+var_18]
0x14004bd3b  call    AslAnsiStringFree
0x14004bd40  mov     eax, 0C0000225h
0x14004bd45  jmp     short loc_14004BD6E
0x14004bd47  mov     rbx, [rsp+38h+var_18+8]
0x14004bd4c  test    rbx, rbx
0x14004bd4f  jz      short loc_14004BD6C
0x14004bd51  movzx   r8d, word ptr [rsp+38h+var_18+2]; Size
0x14004bd57  mov     edx, 42h ; 'B'; Val
0x14004bd5c  mov     rcx, rbx; void *
0x14004bd5f  call    memset
0x14004bd64  mov     rdx, rbx
0x14004bd67  call    AslFree
0x14004bd6c  xor     eax, eax
0x14004bd6e  mov     rbx, [rsp+38h+arg_0]
0x14004bd73  add     rsp, 30h
0x14004bd77  pop     rdi
0x14004bd78  retn
```
