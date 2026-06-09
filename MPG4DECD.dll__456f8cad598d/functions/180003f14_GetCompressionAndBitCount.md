# GetCompressionAndBitCount

- ea: `0x180003f14`
- end: `0x1800040d3`
- name: `GetCompressionAndBitCount`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000364c`

## callees

- `0x180003f14`

## pseudocode

```c
__int64 __fastcall GetCompressionAndBitCount(unsigned int a1, int *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5)
{
  __int64 result; // rax
  bool v7; // zf
  int v8; // edx

  result = 844715353;
  *a5 = 0;
  if ( a1 > 0x32595559 )
  {
    result = 1448433993;
    if ( a1 > 0x56555949 )
    {
      switch ( a1 )
      {
        case 0x59565955u:
          goto LABEL_46;
        case 0xE436EB7A:
LABEL_45:
          *a3 = 8;
          goto LABEL_41;
        case 0xE436EB7B:
          goto LABEL_44;
        case 0xE436EB7C:
LABEL_43:
          *a3 = 16;
          goto LABEL_41;
      }
      if ( a1 != -466162819 )
      {
        if ( a1 != -466162818 )
          goto LABEL_39;
LABEL_40:
        *a3 = 32;
LABEL_41:
        *a5 = 1;
        v8 = 0;
        goto LABEL_48;
      }
LABEL_42:
      *a3 = 24;
      goto LABEL_41;
    }
    switch ( a1 )
    {
      case 0x56555949u:
        goto LABEL_19;
      case 0x33434D49u:
        goto LABEL_46;
      case 0x34434D49u:
LABEL_19:
        *a3 = 12;
LABEL_47:
        v8 = a1;
        goto LABEL_48;
      case 0x36313256u:
LABEL_31:
        *a3 = 32;
        goto LABEL_47;
    }
    v8 = 961893977;
    if ( a1 != 961893977 )
    {
      if ( a1 != 1345401945 )
      {
        if ( a1 != 1431918169 )
        {
          v7 = a1 == 1448433985;
LABEL_30:
          if ( v7 )
            goto LABEL_31;
LABEL_39:
          *a3 = 0;
          goto LABEL_47;
        }
LABEL_46:
        *a3 = 16;
        goto LABEL_47;
      }
      goto LABEL_19;
    }
    *a3 = 9;
  }
  else
  {
    if ( a1 == 844715353 )
      goto LABEL_46;
    result = 808596553;
    if ( a1 <= 0x30323449 )
    {
      if ( a1 != 808596553 )
      {
        result = a1 - 20;
        if ( a1 != 20 )
        {
          result = a1 - 22;
          if ( a1 != 22 )
          {
            result = a1 - 23;
            if ( a1 != 23 )
            {
              result = a1 - 24;
              if ( a1 != 24 )
              {
                result = a1 - 41;
                if ( a1 != 41 )
                {
                  result = a1 - 808530550;
                  if ( a1 != 808530550 )
                  {
                    v7 = (_DWORD)result == 480;
                    goto LABEL_30;
                  }
                  goto LABEL_46;
                }
                goto LABEL_45;
              }
              goto LABEL_43;
            }
LABEL_44:
            *a3 = 16;
            v8 = 3;
            *a5 = 1;
            goto LABEL_48;
          }
          goto LABEL_40;
        }
        goto LABEL_42;
      }
      goto LABEL_19;
    }
    v8 = 825307737;
    result = a1 - 825307737;
    if ( a1 != 825307737 )
    {
      result = a1 - 825308249;
      if ( a1 == 825308249 )
        goto LABEL_46;
      result = a1 - 825316942;
      if ( a1 != 825316942 )
      {
        result = a1 - 826494281;
        if ( a1 == 826494281 )
          goto LABEL_46;
        result = a1 - 842094158;
        if ( a1 != 842094158 )
        {
          result = a1 - 842094169;
          if ( a1 != 842094169 && a1 != 843271497 )
            goto LABEL_39;
        }
      }
      goto LABEL_19;
    }
    *a3 = 8;
  }
LABEL_48:
  *a4 = 1;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x180003f14  mov     r10, [rsp+arg_20]
0x180003f19  mov     eax, 32595559h
0x180003f1e  mov     r11, rdx
0x180003f21  mov     dword ptr [r10], 0
0x180003f28  cmp     ecx, eax
0x180003f2a  ja      loc_180003FE0
0x180003f30  jz      loc_1800040BF
0x180003f36  mov     eax, 30323449h
0x180003f3b  cmp     ecx, eax
0x180003f3d  ja      short loc_180003F89
0x180003f3f  jz      loc_180003FC8
0x180003f45  mov     eax, ecx
0x180003f47  sub     eax, 14h
0x180003f4a  jz      loc_18000408F
0x180003f50  sub     eax, 2
0x180003f53  jz      loc_18000407D
0x180003f59  sub     eax, 1
0x180003f5c  jz      loc_1800040A1
0x180003f62  sub     eax, 1
0x180003f65  jz      loc_180004098
0x180003f6b  sub     eax, 11h
0x180003f6e  jz      loc_1800040B6
0x180003f74  sub     eax, 3031324Dh
0x180003f79  jz      loc_1800040BF
0x180003f7f  cmp     eax, 1E0h
0x180003f84  jmp     loc_18000402A
0x180003f89  mov     eax, ecx
0x180003f8b  mov     edx, 31313259h
0x180003f90  sub     eax, edx
0x180003f92  jz      short loc_180003FD4
0x180003f94  sub     eax, 200h
0x180003f99  jz      loc_1800040BF
0x180003f9f  sub     eax, 21F5h
0x180003fa4  jz      short loc_180003FC8
0x180003fa6  sub     eax, 11F6FBh
0x180003fab  jz      loc_1800040BF
0x180003fb1  sub     eax, 0EE0905h
0x180003fb6  jz      short loc_180003FC8
0x180003fb8  sub     eax, 0Bh
0x180003fbb  jz      short loc_180003FC8
0x180003fbd  cmp     eax, 11F6F0h
0x180003fc2  jnz     loc_180004074
0x180003fc8  mov     dword ptr [r8], 0Ch
0x180003fcf  jmp     loc_1800040C6
0x180003fd4  mov     dword ptr [r8], 8
0x180003fdb  jmp     loc_1800040C8
0x180003fe0  mov     eax, 56555949h
0x180003fe5  cmp     ecx, eax
0x180003fe7  ja      short loc_180004044
0x180003fe9  jz      short loc_180003FC8
0x180003feb  cmp     ecx, 33434D49h
0x180003ff1  jz      loc_1800040BF
0x180003ff7  cmp     ecx, 34434D49h
0x180003ffd  jz      short loc_180003FC8
0x180003fff  cmp     ecx, 36313256h
0x180004005  jz      short loc_18000402C
0x180004007  mov     edx, 39555659h
0x18000400c  cmp     ecx, edx
0x18000400e  jz      short loc_180004038
0x180004010  cmp     ecx, 50313459h
0x180004016  jz      short loc_180003FC8
0x180004018  cmp     ecx, 55595659h
0x18000401e  jz      loc_1800040BF
0x180004024  cmp     ecx, 56555941h
0x18000402a  jnz     short loc_180004074
0x18000402c  mov     dword ptr [r8], 20h ; ' '
0x180004033  jmp     loc_1800040C6
0x180004038  mov     dword ptr [r8], 9
0x18000403f  jmp     loc_1800040C8
0x180004044  cmp     ecx, 59565955h
0x18000404a  jz      short loc_1800040BF
0x18000404c  cmp     ecx, 0E436EB7Ah
0x180004052  jz      short loc_1800040B6
0x180004054  cmp     ecx, 0E436EB7Bh
0x18000405a  jz      short loc_1800040A1
0x18000405c  cmp     ecx, 0E436EB7Ch
0x180004062  jz      short loc_180004098
0x180004064  cmp     ecx, 0E436EB7Dh
0x18000406a  jz      short loc_18000408F
0x18000406c  cmp     ecx, 0E436EB7Eh
0x180004072  jz      short loc_18000407D
0x180004074  mov     dword ptr [r8], 0
0x18000407b  jmp     short loc_1800040C6
0x18000407d  mov     dword ptr [r8], 20h ; ' '
0x180004084  mov     dword ptr [r10], 1
0x18000408b  xor     edx, edx
0x18000408d  jmp     short loc_1800040C8
0x18000408f  mov     dword ptr [r8], 18h
0x180004096  jmp     short loc_180004084
0x180004098  mov     dword ptr [r8], 10h
0x18000409f  jmp     short loc_180004084
0x1800040a1  mov     dword ptr [r8], 10h
0x1800040a8  mov     edx, 3
0x1800040ad  mov     dword ptr [r10], 1
0x1800040b4  jmp     short loc_1800040C8
0x1800040b6  mov     dword ptr [r8], 8
0x1800040bd  jmp     short loc_180004084
0x1800040bf  mov     dword ptr [r8], 10h
0x1800040c6  mov     edx, ecx
0x1800040c8  mov     dword ptr [r9], 1
0x1800040cf  mov     [r11], edx
0x1800040d2  retn
```
