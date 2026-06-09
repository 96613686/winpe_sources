# Em_AmrNB_Dec_div_s

- ea: `0x18000688c`
- end: `0x180006943`
- name: `Em_AmrNB_Dec_div_s`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180004dd0`
- `0x1800051e0`
- `0x180006eb4`
- `0x1800085b4`
- `0x180009a74`

## callees

- `0x18000688c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_div_s(__int16 a1, __int16 a2)
{
  int v2; // ecx
  unsigned int v3; // r9d
  int v4; // r10d
  __int16 v5; // r11
  int v6; // edx

  if ( a1 > a2 || a1 < 0 || a2 < 1 )
    return 0;
  if ( a1 )
  {
    if ( a1 == a2 )
    {
      LOWORD(v2) = 0x7FFF;
    }
    else
    {
      v3 = a1;
      v4 = a2;
      LOWORD(v2) = 0;
      v5 = 15;
      do
      {
        v6 = 2 * v3;
        LOWORD(v2) = 2 * v2;
        v3 = v6;
        if ( v6 >= v4 )
        {
          v3 = v6 - v4;
          if ( (v4 ^ v6) < 0 && ((v6 ^ v3) & 0x80000000) != 0 )
          {
            v3 = 0x7FFFFFFF;
            if ( v6 < 0 )
              v3 = 0x80000000;
          }
          v2 = (__int16)v2 + 1;
          if ( v2 <= 0x7FFF )
          {
            if ( v2 < -32768 )
              LOWORD(v2) = 0x8000;
          }
          else
          {
            LOWORD(v2) = 0x7FFF;
          }
        }
        --v5;
      }
      while ( v5 );
    }
  }
  else
  {
    LOWORD(v2) = 0;
  }
  return (unsigned __int16)v2;
}

```

## disassembly

```asm
0x18000688c  mov     [rsp+arg_0], rbx
0x180006891  movsx   r8d, cx
0x180006895  xor     ebx, ebx
0x180006897  cmp     r8w, dx
0x18000689b  jg      loc_18000693B
0x1800068a1  test    r8w, r8w
0x1800068a5  js      loc_18000693B
0x1800068ab  cmp     dx, 1
0x1800068af  jl      loc_18000693B
0x1800068b5  test    r8w, r8w
0x1800068b9  jnz     short loc_1800068BF
0x1800068bb  mov     ecx, ebx
0x1800068bd  jmp     short loc_180006936
0x1800068bf  cmp     r8w, dx
0x1800068c3  jnz     short loc_1800068CC
0x1800068c5  mov     ecx, 7FFFh
0x1800068ca  jmp     short loc_180006936
0x1800068cc  mov     r9d, r8d
0x1800068cf  movsx   r10d, dx
0x1800068d3  mov     r8d, 7FFFh
0x1800068d9  mov     ecx, ebx
0x1800068db  mov     r11d, 0Fh
0x1800068e1  lea     edx, [r9+r9]
0x1800068e5  add     cx, cx
0x1800068e8  mov     r9d, edx
0x1800068eb  cmp     edx, r10d
0x1800068ee  jl      short loc_18000692F
0x1800068f0  sub     r9d, r10d
0x1800068f3  mov     eax, edx
0x1800068f5  xor     eax, r10d
0x1800068f8  jge     short loc_180006912
0x1800068fa  mov     eax, r9d
0x1800068fd  xor     eax, edx
0x1800068ff  jge     short loc_180006912
0x180006901  test    edx, edx
0x180006903  mov     eax, 80000000h
0x180006908  mov     r9d, 7FFFFFFFh
0x18000690e  cmovs   r9d, eax
0x180006912  movsx   ecx, cx
0x180006915  inc     ecx
0x180006917  cmp     ecx, r8d
0x18000691a  jle     short loc_180006922
0x18000691c  movzx   ecx, r8w
0x180006920  jmp     short loc_18000692F
0x180006922  cmp     ecx, 0FFFF8000h
0x180006928  jge     short loc_18000692F
0x18000692a  mov     ecx, 0FFFF8000h
0x18000692f  sub     r11w, 1
0x180006934  jnz     short loc_1800068E1
0x180006936  movzx   eax, cx
0x180006939  jmp     short loc_18000693D
0x18000693b  mov     eax, ebx
0x18000693d  mov     rbx, [rsp+arg_0]
0x180006942  retn
```
