# Em_AmrNB_Dec_L_shr_r

- ea: `0x180006844`
- end: `0x180006883`
- name: `Em_AmrNB_Dec_L_shr_r`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d24`
- `0x1800085b4`

## callees

- `0x180006808`
- `0x180006844`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_L_shr_r(__int64 a1, __int16 a2)
{
  int v3; // edi
  __int64 result; // rax

  v3 = a1;
  if ( a2 > 31 )
    return 0;
  result = Em_AmrNB_Dec_L_shr(a1, a2);
  if ( a2 > 0 )
  {
    if ( _bittest(&v3, (unsigned __int8)(a2 - 1)) )
      return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x180006844  mov     [rsp+arg_0], rbx
0x180006849  push    rdi
0x18000684a  sub     rsp, 20h
0x18000684e  movsx   ebx, dx
0x180006851  mov     edi, ecx
0x180006853  cmp     ebx, 1Fh
0x180006856  jle     short loc_18000685E
0x180006858  xor     ecx, ecx
0x18000685a  mov     eax, ecx
0x18000685c  jmp     short loc_180006878
0x18000685e  movzx   edx, bx
0x180006861  call    Em_AmrNB_Dec_L_shr
0x180006866  test    bx, bx
0x180006869  jle     short loc_180006878
0x18000686b  lea     ecx, [rbx-1]
0x18000686e  movzx   ecx, cl
0x180006871  bt      edi, ecx
0x180006874  jnb     short loc_180006878
0x180006876  inc     eax
0x180006878  mov     rbx, [rsp+28h+arg_0]
0x18000687d  add     rsp, 20h
0x180006881  pop     rdi
0x180006882  retn
```
