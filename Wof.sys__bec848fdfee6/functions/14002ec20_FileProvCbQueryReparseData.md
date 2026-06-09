# FileProvCbQueryReparseData

- ea: `0x14002ec20`
- end: `0x14002ecd3`
- name: `FileProvCbQueryReparseData`
- size: `179`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, _DWORD *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x1400115b0`
- `0x1400230a8`
- `0x140023198`
- `0x14002ec20`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryReparseData(__int64 a1, __int64 a2, unsigned int *a3, _DWORD *a4, char a5)
{
  size_t v10; // r8
  unsigned int *v11; // rcx
  unsigned int v12; // eax

  if ( *a4 >= 8u )
  {
    v10 = *a4 < 0xCu ? 8 : 12;
    *a4 = v10;
    if ( a5 )
    {
      RtlSetUserMemory(a3);
      RtlWriteULongToUser(a3, 1);
    }
    else
    {
      RtlSetVolatileMemory(a3, 0, v10);
      *a3 = 1;
    }
    v11 = a3 + 1;
    v12 = *(_DWORD *)(a2 + 4);
    if ( a5 )
      RtlWriteULongToUser(v11, v12);
    else
      *v11 = v12;
    if ( *a4 >= 0xCu )
    {
      if ( a5 )
        RtlWriteULongToUser(a3 + 2, 0);
      else
        a3[2] = 0;
    }
    return 0;
  }
  else
  {
    *a4 = 8;
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x14002ec20  mov     [rsp+arg_0], rbx
0x14002ec25  mov     [rsp+arg_8], rbp
0x14002ec2a  push    rdi
0x14002ec2b  sub     rsp, 20h
0x14002ec2f  mov     eax, [r9]
0x14002ec32  mov     rdi, r9
0x14002ec35  mov     rbx, r8
0x14002ec38  mov     rbp, rdx
0x14002ec3b  cmp     eax, 8
0x14002ec3e  jnb     short loc_14002EC4E
0x14002ec40  mov     dword ptr [r9], 8
0x14002ec47  mov     eax, 0C0000023h
0x14002ec4c  jmp     short loc_14002ECC2
0x14002ec4e  cmp     eax, 0Ch
0x14002ec51  mov     rcx, rbx; void *
0x14002ec54  sbb     eax, eax
0x14002ec56  xor     edx, edx; Val
0x14002ec58  and     eax, 0FFFFFFFCh
0x14002ec5b  lea     r8d, [rax+0Ch]; Size
0x14002ec5f  mov     [r9], r8d
0x14002ec62  cmp     [rsp+28h+arg_20], dl
0x14002ec66  jz      short loc_14002EC7C
0x14002ec68  call    RtlSetUserMemory
0x14002ec6d  mov     edx, 1
0x14002ec72  mov     rcx, rbx
0x14002ec75  call    RtlWriteULongToUser
0x14002ec7a  jmp     short loc_14002EC87
0x14002ec7c  call    RtlSetVolatileMemory
0x14002ec81  mov     dword ptr [rbx], 1
0x14002ec87  cmp     [rsp+28h+arg_20], 0
0x14002ec8c  lea     rcx, [rbx+4]
0x14002ec90  mov     eax, [rbp+4]
0x14002ec93  jz      short loc_14002EC9E
0x14002ec95  mov     edx, eax
0x14002ec97  call    RtlWriteULongToUser
0x14002ec9c  jmp     short loc_14002ECA0
0x14002ec9e  mov     [rcx], eax
0x14002eca0  cmp     dword ptr [rdi], 0Ch
0x14002eca3  jb      short loc_14002ECC0
0x14002eca5  cmp     [rsp+28h+arg_20], 0
0x14002ecaa  jz      short loc_14002ECB9
0x14002ecac  xor     edx, edx
0x14002ecae  lea     rcx, [rbx+8]
0x14002ecb2  call    RtlWriteULongToUser
0x14002ecb7  jmp     short loc_14002ECC0
0x14002ecb9  mov     dword ptr [rbx+8], 0
0x14002ecc0  xor     eax, eax
0x14002ecc2  mov     rbx, [rsp+28h+arg_0]
0x14002ecc7  mov     rbp, [rsp+28h+arg_8]
0x14002eccc  add     rsp, 20h
0x14002ecd0  pop     rdi
0x14002ecd1  retn
```
