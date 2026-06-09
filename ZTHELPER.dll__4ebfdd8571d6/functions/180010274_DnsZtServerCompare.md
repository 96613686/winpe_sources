# DnsZtServerCompare

- ea: `0x180010274`
- end: `0x1800102dc`
- name: `DnsZtServerCompare`
- size: `104`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800102f0`
- `0x180010300`
- `0x180010480`
- `0x1800105c0`
- `0x180010790`
- `0x180010c18`

## callees

- `0x180010274`
- `0x1800132f0`
- `0x180013f0d`

## pseudocode

```c
__int64 __fastcall DnsZtServerCompare(_WORD *a1, _WORD *a2, int a3)
{
  unsigned int v5; // ecx

  if ( a1 )
  {
    if ( a2 )
    {
      if ( !a3 || (v5 = (unsigned __int16)a1[23] - (unsigned __int16)a2[23]) == 0 )
      {
        v5 = DnsCompareSockaddrInet(a1 + 8, a2 + 8);
        if ( !v5 )
          return (unsigned int)memcmp_0(a1 + 24, a2 + 24, 4u);
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    return (unsigned int)-1;
  }
  return v5;
}

```

## disassembly

```asm
0x180010274  mov     [rsp+arg_0], rbx
0x180010279  push    rdi
0x18001027a  sub     rsp, 20h
0x18001027e  mov     rbx, rdx
0x180010281  mov     rdi, rcx
0x180010284  test    rcx, rcx
0x180010287  jnz     short loc_18001028E
0x180010289  or      ecx, 0FFFFFFFFh
0x18001028c  jmp     short loc_1800102CF
0x18001028e  test    rbx, rbx
0x180010291  jnz     short loc_180010298
0x180010293  lea     ecx, [rbx+1]
0x180010296  jmp     short loc_1800102CF
0x180010298  test    r8d, r8d
0x18001029b  jz      short loc_1800102A9
0x18001029d  movzx   ecx, word ptr [rcx+2Eh]
0x1800102a1  movzx   eax, word ptr [rdx+2Eh]
0x1800102a5  sub     ecx, eax
0x1800102a7  jnz     short loc_1800102CF
0x1800102a9  add     rdx, 10h
0x1800102ad  lea     rcx, [rdi+10h]
0x1800102b1  call    DnsCompareSockaddrInet
0x1800102b6  mov     ecx, eax
0x1800102b8  test    eax, eax
0x1800102ba  jnz     short loc_1800102CF
0x1800102bc  lea     rdx, [rbx+30h]; Buf2
0x1800102c0  lea     rcx, [rdi+30h]; Buf1
0x1800102c4  lea     r8d, [rax+4]; Size
0x1800102c8  call    memcmp_0
0x1800102cd  mov     ecx, eax
0x1800102cf  mov     rbx, [rsp+28h+arg_0]
0x1800102d4  mov     eax, ecx
0x1800102d6  add     rsp, 20h
0x1800102da  pop     rdi
0x1800102db  retn
```
