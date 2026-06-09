# ReadLATM

- ea: `0x18005d170`
- end: `0x18005d1f1`
- name: `ReadLATM`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002550`

## callees

- `0x18003e3ec`
- `0x18005d170`
- `0x18005d26c`
- `0x18005d308`

## pseudocode

```c
__int64 __fastcall ReadLATM(unsigned int *a1, _DWORD *a2)
{
  unsigned int PayloadLengthInfo; // edi
  bool v5; // zf
  unsigned int i; // ebp

  PayloadLengthInfo = 0;
  if ( !a2[1] )
    goto LABEL_16;
  if ( !*a1 )
    FillBitCache(a1, 1u);
  v5 = ((a1[1] >> --*a1) & 1) == 0;
  a2[3] = (a1[1] >> *a1) & 1;
  if ( !v5 || (PayloadLengthInfo = ReadStreamMuxConfig(a1, (__int64)a2)) == 0 )
  {
LABEL_16:
    if ( a2[5] )
    {
      return 2;
    }
    else
    {
      for ( i = 0; i < a2[7]; ++i )
      {
        PayloadLengthInfo = ReadPayloadLengthInfo(a1, a2);
        if ( PayloadLengthInfo )
          return PayloadLengthInfo;
      }
      a2[2] = 1;
    }
  }
  return PayloadLengthInfo;
}

```

## disassembly

```asm
0x18005d170  push    rbx
0x18005d172  push    rbp
0x18005d173  push    rsi
0x18005d174  push    rdi
0x18005d175  sub     rsp, 28h
0x18005d179  xor     edi, edi
0x18005d17b  mov     rbx, rdx
0x18005d17e  mov     rsi, rcx
0x18005d181  cmp     [rdx+4], edi
0x18005d184  jz      short loc_18005D1B5
0x18005d186  cmp     dword ptr [rcx], 1
0x18005d189  jnb     short loc_18005D193
0x18005d18b  lea     edx, [rdi+1]
0x18005d18e  call    FillBitCache
0x18005d193  dec     dword ptr [rsi]
0x18005d195  mov     eax, [rsi+4]
0x18005d198  mov     ecx, [rsi]
0x18005d19a  shr     eax, cl
0x18005d19c  and     eax, 1
0x18005d19f  mov     [rbx+0Ch], eax
0x18005d1a2  jnz     short loc_18005D1B5
0x18005d1a4  mov     rdx, rbx
0x18005d1a7  mov     rcx, rsi
0x18005d1aa  call    ReadStreamMuxConfig
0x18005d1af  mov     edi, eax
0x18005d1b1  test    eax, eax
0x18005d1b3  jnz     short loc_18005D1E5
0x18005d1b5  cmp     dword ptr [rbx+14h], 0
0x18005d1b9  jnz     short loc_18005D1E0
0x18005d1bb  xor     ebp, ebp
0x18005d1bd  cmp     ebp, [rbx+1Ch]
0x18005d1c0  jnb     short loc_18005D1D7
0x18005d1c2  mov     rdx, rbx
0x18005d1c5  mov     rcx, rsi
0x18005d1c8  call    ReadPayloadLengthInfo
0x18005d1cd  mov     edi, eax
0x18005d1cf  test    eax, eax
0x18005d1d1  jnz     short loc_18005D1E5
0x18005d1d3  inc     ebp
0x18005d1d5  jmp     short loc_18005D1BD
0x18005d1d7  mov     dword ptr [rbx+8], 1
0x18005d1de  jmp     short loc_18005D1E5
0x18005d1e0  mov     edi, 2
0x18005d1e5  mov     eax, edi
0x18005d1e7  add     rsp, 28h
0x18005d1eb  pop     rdi
0x18005d1ec  pop     rsi
0x18005d1ed  pop     rbp
0x18005d1ee  pop     rbx
0x18005d1ef  retn
```
