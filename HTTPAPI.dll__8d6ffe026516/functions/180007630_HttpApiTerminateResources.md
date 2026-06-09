# HttpApiTerminateResources

- ea: `0x180007630`
- end: `0x1800076d7`
- name: `HttpApiTerminateResources`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800034a0`
- `0x180003ad0`

## callees

- `0x180007630`
- `0x18000bdd0`
- `0x18000be2c`

## pseudocode

```c
__int64 __fastcall HttpApiTerminateResources(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  unsigned int v4; // edi
  unsigned int v5; // edx

  v3 = a1;
  LOBYTE(a3) = byte_1800126A3;
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_L(a1, 0x18u, (ULONGLONG)WPP_d1f5b049c58935796a293ebb03e09278_Traceguids, a1);
    LOBYTE(a3) = byte_1800126A3;
  }
  if ( (v3 & 0x17) != 0 || (v4 = 87, !v3) )
  {
    v5 = dword_180012770;
    if ( dword_180012770 )
    {
      v4 = 0;
      if ( v3 )
      {
        a1 = 2 * (v3 & 1u);
        if ( (v3 & 2) != 0 )
          a1 = (unsigned int)(a1 + 2);
      }
      else
      {
        a1 = 1;
      }
      dword_180012770 -= a1;
      if ( (unsigned int)a1 >= v5 )
        dword_180012770 = 0;
    }
    else
    {
      v4 = 1114;
    }
  }
  if ( (a3 & 4) != 0 )
    WPP_SF_Dd(a1, 0x19u, a3, v4);
  return v4;
}

```

## disassembly

```asm
0x180007630  mov     [rsp+arg_0], rbx
0x180007635  push    rdi
0x180007636  sub     rsp, 30h
0x18000763a  mov     ebx, ecx
0x18000763c  mov     r8b, cs:byte_1800126A3
0x180007643  test    r8b, 4
0x180007647  jz      short loc_180007664
0x180007649  mov     edx, 18h
0x18000764e  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x180007655  mov     r9d, ecx
0x180007658  call    WPP_SF_L
0x18000765d  mov     r8b, cs:byte_1800126A3
0x180007664  test    bl, 17h
0x180007667  jnz     short loc_180007672
0x180007669  mov     edi, 57h ; 'W'
0x18000766e  test    ebx, ebx
0x180007670  jnz     short loc_1800076B7
0x180007672  mov     edx, cs:dword_180012770
0x180007678  test    edx, edx
0x18000767a  jnz     short loc_180007683
0x18000767c  mov     edi, 45Ah
0x180007681  jmp     short loc_1800076B7
0x180007683  xor     edi, edi
0x180007685  test    ebx, ebx
0x180007687  jnz     short loc_18000768E
0x180007689  lea     ecx, [rdi+1]
0x18000768c  jmp     short loc_18000769E
0x18000768e  mov     eax, ebx
0x180007690  and     eax, 1
0x180007693  lea     ecx, [rax+rax]
0x180007696  test    bl, 2
0x180007699  jz      short loc_18000769E
0x18000769b  add     ecx, 2
0x18000769e  xor     eax, eax
0x1800076a0  cmp     ecx, edx
0x1800076a2  setnb   al
0x1800076a5  sub     edx, ecx
0x1800076a7  mov     cs:dword_180012770, edx
0x1800076ad  test    eax, eax
0x1800076af  jz      short loc_1800076B7
0x1800076b1  mov     cs:dword_180012770, edi
0x1800076b7  test    r8b, 4
0x1800076bb  jz      short loc_1800076CA
0x1800076bd  mov     edx, 19h
0x1800076c2  mov     r9d, edi
0x1800076c5  call    WPP_SF_Dd
0x1800076ca  mov     rbx, [rsp+38h+arg_0]
0x1800076cf  mov     eax, edi
0x1800076d1  add     rsp, 30h
0x1800076d5  pop     rdi
0x1800076d6  retn
```
