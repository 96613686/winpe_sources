# FileProvCbQueryStreamSizeCompressed

- ea: `0x14003b9c0`
- end: `0x14003ba0e`
- name: `FileProvCbQueryStreamSizeCompressed`
- size: `78`
- prototype: `__int64 __fastcall(__int64, __int64 *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140023150`
- `0x14003b9c0`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryStreamSizeCompressed(__int64 a1, __int64 *a2, char a3)
{
  _DWORD *v3; // rax
  __int64 v5; // rdx

  v3 = *(_DWORD **)(a1 + 24);
  if ( v3 )
  {
    v5 = -(__int64)(unsigned int)*v3 & (*(_QWORD *)(a1 + 16) + (unsigned int)(*v3 - 1));
    if ( !a3 )
    {
      *a2 = v5;
      return 0;
    }
  }
  else
  {
    if ( !a3 )
    {
      *a2 = *(_QWORD *)(a1 + 16);
      return 0;
    }
    v5 = *(_QWORD *)(a1 + 16);
  }
  RtlWriteULong64ToUser(a2, v5);
  return 0;
}

```

## disassembly

```asm
0x14003b9c0  sub     rsp, 28h
0x14003b9c4  mov     rax, [rcx+18h]
0x14003b9c8  mov     r10, rdx
0x14003b9cb  test    rax, rax
0x14003b9ce  jz      short loc_14003B9FB
0x14003b9d0  mov     r9d, [rax]
0x14003b9d3  lea     edx, [r9-1]
0x14003b9d7  neg     r9
0x14003b9da  add     rdx, [rcx+10h]
0x14003b9de  and     rdx, r9
0x14003b9e1  test    r8b, r8b
0x14003b9e4  jz      short loc_14003B9F6
0x14003b9e6  mov     rcx, r10
0x14003b9e9  call    RtlWriteULong64ToUser
0x14003b9ee  xor     eax, eax
0x14003b9f0  add     rsp, 28h
0x14003b9f4  retn
0x14003b9f6  mov     [r10], rdx
0x14003b9f9  jmp     short loc_14003B9EE
0x14003b9fb  mov     rax, [rcx+10h]
0x14003b9ff  test    r8b, r8b
0x14003ba02  jz      short loc_14003BA09
0x14003ba04  mov     rdx, rax
0x14003ba07  jmp     short loc_14003B9E6
0x14003ba09  mov     [rdx], rax
0x14003ba0c  jmp     short loc_14003B9EE
```
