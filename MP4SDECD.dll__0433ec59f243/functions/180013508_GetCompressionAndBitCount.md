# GetCompressionAndBitCount

- ea: `0x180013508`
- end: `0x1800136d0`
- name: `GetCompressionAndBitCount`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800131e8`

## callees

- `0x180013508`

## pseudocode

```c
__int64 __fastcall GetCompressionAndBitCount(unsigned int a1, int *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5)
{
  __int64 result; // rax
  int v7; // edx
  bool v8; // zf

  result = 844715353;
  *a5 = 0;
  if ( a1 <= 0x32595559 )
  {
    if ( a1 == 844715353 )
      goto LABEL_47;
    result = 808596553;
    if ( a1 > 0x30323449 )
    {
      v7 = 825307737;
      result = a1 - 825307737;
      if ( a1 == 825307737 )
      {
        *a3 = 8;
        goto LABEL_6;
      }
      result = a1 - 825308249;
      if ( a1 == 825308249 )
        goto LABEL_47;
      result = a1 - 825316942;
      if ( a1 != 825316942 )
      {
        result = a1 - 826494281;
        if ( a1 == 826494281 )
          goto LABEL_47;
        result = a1 - 842094158;
        if ( a1 != 842094158 )
        {
          result = a1 - 842094169;
          if ( a1 != 842094169 && a1 != 843271497 )
            goto LABEL_43;
        }
      }
    }
    else if ( a1 != 808596553 )
    {
      result = a1 - 20;
      if ( a1 == 20 )
        goto LABEL_11;
      result = a1 - 22;
      if ( a1 == 22 )
        goto LABEL_44;
      result = a1 - 23;
      if ( a1 == 23 )
        goto LABEL_46;
      result = a1 - 24;
      if ( a1 == 24 )
        goto LABEL_45;
      result = a1 - 41;
      if ( a1 == 41 )
        goto LABEL_4;
      result = a1 - 808530550;
      if ( a1 == 808530550 )
      {
LABEL_47:
        *a3 = 16;
        goto LABEL_48;
      }
      v8 = (_DWORD)result == 480;
      goto LABEL_35;
    }
LABEL_25:
    *a3 = 12;
LABEL_48:
    v7 = a1;
    goto LABEL_6;
  }
  result = 1448433993;
  if ( a1 <= 0x56555949 )
  {
    if ( a1 != 1448433993 )
    {
      if ( a1 == 860048713 )
        goto LABEL_47;
      if ( a1 != 876825929 )
      {
        if ( a1 == 909193814 )
        {
LABEL_36:
          *a3 = 32;
          goto LABEL_48;
        }
        v7 = 961893977;
        if ( a1 == 961893977 )
        {
          *a3 = 9;
          goto LABEL_6;
        }
        if ( a1 != 1345401945 )
        {
          if ( a1 == 1431918169 )
            goto LABEL_47;
          v8 = a1 == 1448433985;
LABEL_35:
          if ( !v8 )
          {
LABEL_43:
            *a3 = 0;
            goto LABEL_48;
          }
          goto LABEL_36;
        }
      }
    }
    goto LABEL_25;
  }
  if ( a1 != -466162822 )
  {
    if ( a1 != 1498831189 )
    {
      if ( a1 != -466162821 )
      {
        if ( a1 != -466162820 )
        {
          if ( a1 != -466162819 )
          {
            if ( a1 != -466162818 )
              goto LABEL_43;
LABEL_44:
            *a3 = 32;
            goto LABEL_5;
          }
LABEL_11:
          *a3 = 24;
          goto LABEL_5;
        }
LABEL_45:
        *a3 = 16;
        goto LABEL_5;
      }
LABEL_46:
      *a3 = 16;
      v7 = 3;
      *a5 = 1;
      goto LABEL_6;
    }
    goto LABEL_47;
  }
LABEL_4:
  *a3 = 8;
LABEL_5:
  *a5 = 1;
  v7 = 0;
LABEL_6:
  *a4 = 1;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x180013508  mov     r10, [rsp+arg_20]
0x18001350d  mov     eax, 32595559h
0x180013512  mov     r11, rdx
0x180013515  mov     dword ptr [r10], 0
0x18001351c  cmp     ecx, eax
0x18001351e  jbe     short loc_180013554
0x180013520  mov     eax, 56555949h
0x180013525  cmp     ecx, eax
0x180013527  jbe     loc_180013605
0x18001352d  cmp     ecx, 0E436EB7Ah
0x180013533  jnz     loc_18001365D
0x180013539  mov     dword ptr [r8], 8
0x180013540  mov     dword ptr [r10], 1
0x180013547  xor     edx, edx
0x180013549  mov     dword ptr [r9], 1
0x180013550  mov     [r11], edx
0x180013553  retn
0x180013554  jz      loc_1800136C2
0x18001355a  mov     eax, 30323449h
0x18001355f  cmp     ecx, eax
0x180013561  ja      short loc_1800135AE
0x180013563  jz      loc_1800135ED
0x180013569  mov     eax, ecx
0x18001356b  sub     eax, 14h
0x18001356e  jnz     short loc_180013579
0x180013570  mov     dword ptr [r8], 18h
0x180013577  jmp     short loc_180013540
0x180013579  sub     eax, 2
0x18001357c  jz      loc_180013692
0x180013582  sub     eax, 1
0x180013585  jz      loc_1800136AA
0x18001358b  sub     eax, 1
0x18001358e  jz      loc_18001369E
0x180013594  sub     eax, 11h
0x180013597  jz      short loc_180013539
0x180013599  sub     eax, 3031324Dh
0x18001359e  jz      loc_1800136C2
0x1800135a4  cmp     eax, 1E0h
0x1800135a9  jmp     loc_180013646
0x1800135ae  mov     eax, ecx
0x1800135b0  mov     edx, 31313259h
0x1800135b5  sub     eax, edx
0x1800135b7  jz      short loc_1800135F9
0x1800135b9  sub     eax, 200h
0x1800135be  jz      loc_1800136C2
0x1800135c4  sub     eax, 21F5h
0x1800135c9  jz      short loc_1800135ED
0x1800135cb  sub     eax, 11F6FBh
0x1800135d0  jz      loc_1800136C2
0x1800135d6  sub     eax, 0EE0905h
0x1800135db  jz      short loc_1800135ED
0x1800135dd  sub     eax, 0Bh
0x1800135e0  jz      short loc_1800135ED
0x1800135e2  cmp     eax, 11F6F0h
0x1800135e7  jnz     loc_180013689
0x1800135ed  mov     dword ptr [r8], 0Ch
0x1800135f4  jmp     loc_1800136C9
0x1800135f9  mov     dword ptr [r8], 8
0x180013600  jmp     loc_180013549
0x180013605  jz      short loc_1800135ED
0x180013607  cmp     ecx, 33434D49h
0x18001360d  jz      loc_1800136C2
0x180013613  cmp     ecx, 34434D49h
0x180013619  jz      short loc_1800135ED
0x18001361b  cmp     ecx, 36313256h
0x180013621  jz      short loc_180013648
0x180013623  mov     edx, 39555659h
0x180013628  cmp     ecx, edx
0x18001362a  jz      short loc_180013651
0x18001362c  cmp     ecx, 50313459h
0x180013632  jz      short loc_1800135ED
0x180013634  cmp     ecx, 55595659h
0x18001363a  jz      loc_1800136C2
0x180013640  cmp     ecx, 56555941h
0x180013646  jnz     short loc_180013689
0x180013648  mov     dword ptr [r8], 20h ; ' '
0x18001364f  jmp     short loc_1800136C9
0x180013651  mov     dword ptr [r8], 9
0x180013658  jmp     loc_180013549
0x18001365d  cmp     ecx, 59565955h
0x180013663  jz      short loc_1800136C2
0x180013665  cmp     ecx, 0E436EB7Bh
0x18001366b  jz      short loc_1800136AA
0x18001366d  cmp     ecx, 0E436EB7Ch
0x180013673  jz      short loc_18001369E
0x180013675  cmp     ecx, 0E436EB7Dh
0x18001367b  jz      loc_180013570
0x180013681  cmp     ecx, 0E436EB7Eh
0x180013687  jz      short loc_180013692
0x180013689  mov     dword ptr [r8], 0
0x180013690  jmp     short loc_1800136C9
0x180013692  mov     dword ptr [r8], 20h ; ' '
0x180013699  jmp     loc_180013540
0x18001369e  mov     dword ptr [r8], 10h
0x1800136a5  jmp     loc_180013540
0x1800136aa  mov     dword ptr [r8], 10h
0x1800136b1  mov     edx, 3
0x1800136b6  mov     dword ptr [r10], 1
0x1800136bd  jmp     loc_180013549
0x1800136c2  mov     dword ptr [r8], 10h
0x1800136c9  mov     edx, ecx
0x1800136cb  jmp     loc_180013549
```
