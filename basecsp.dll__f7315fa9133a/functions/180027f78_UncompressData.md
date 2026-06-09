# UncompressData

- ea: `0x180027f78`
- end: `0x180028000`
- name: `UncompressData`
- size: `136`
- prototype: `__int64 __fastcall(int, __int64, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020638`
- `0x180020cdc`

## callees

- `0x180002bc0`
- `0x180027f78`

## pseudocode

```c
__int64 __fastcall UncompressData(int a1, __int64 a2, unsigned int *a3, __int64 a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // edx

  if ( a2 )
  {
    v9 = *(unsigned __int16 *)(a2 + 2);
    v8 = 0;
    if ( a4 )
    {
      v10 = *a3;
      *a3 = v9;
      if ( v10 >= v9 )
      {
        if ( (unsigned int)uncompress(a4, a3, a2 + 4, (unsigned int)(a1 - 4)) )
        {
          return 1359;
        }
        else
        {
          v11 = 0;
          if ( *(unsigned __int16 *)(a2 + 2) != *a3 )
            return 1359;
          return v11;
        }
      }
      else
      {
        return 234;
      }
    }
    else
    {
      *a3 = v9;
    }
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x180027f78  mov     [rsp+arg_0], rbx
0x180027f7d  mov     [rsp+arg_8], rsi
0x180027f82  push    rdi
0x180027f83  sub     rsp, 20h
0x180027f87  mov     r10, r9
0x180027f8a  mov     r9d, ecx
0x180027f8d  mov     rdi, r8
0x180027f90  mov     rsi, rdx
0x180027f93  test    rdx, rdx
0x180027f96  jnz     short loc_180027F9D
0x180027f98  lea     ebx, [rdx+57h]
0x180027f9b  jmp     short loc_180027FEE
0x180027f9d  movzx   ecx, word ptr [rdx+2]
0x180027fa1  xor     ebx, ebx
0x180027fa3  test    r10, r10
0x180027fa6  jnz     short loc_180027FAD
0x180027fa8  mov     [r8], ecx
0x180027fab  jmp     short loc_180027FEE
0x180027fad  mov     eax, [r8]
0x180027fb0  mov     [r8], ecx
0x180027fb3  cmp     eax, ecx
0x180027fb5  jnb     short loc_180027FBE
0x180027fb7  mov     ebx, 0EAh
0x180027fbc  jmp     short loc_180027FEE
0x180027fbe  lea     r8, [rdx+4]
0x180027fc2  add     r9d, 0FFFFFFFCh
0x180027fc6  mov     rdx, rdi
0x180027fc9  mov     rcx, r10
0x180027fcc  call    uncompress
0x180027fd1  test    eax, eax
0x180027fd3  jz      short loc_180027FDC
0x180027fd5  mov     ebx, 54Fh
0x180027fda  jmp     short loc_180027FEE
0x180027fdc  movzx   ecx, word ptr [rsi+2]
0x180027fe0  mov     edx, ebx
0x180027fe2  cmp     ecx, [rdi]
0x180027fe4  mov     ebx, 54Fh
0x180027fe9  cmovnz  edx, ebx
0x180027fec  mov     ebx, edx
0x180027fee  mov     rsi, [rsp+28h+arg_8]
0x180027ff3  mov     eax, ebx
0x180027ff5  mov     rbx, [rsp+28h+arg_0]
0x180027ffa  add     rsp, 20h
0x180027ffe  pop     rdi
0x180027fff  retn
```
