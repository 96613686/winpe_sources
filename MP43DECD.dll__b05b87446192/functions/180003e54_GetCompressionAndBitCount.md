# GetCompressionAndBitCount

- ea: `0x180003e54`
- end: `0x180004013`
- name: `GetCompressionAndBitCount`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000358c`

## callees

- `0x180003e54`

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
0x180003e54  mov     r10, [rsp+arg_20]
0x180003e59  mov     eax, 32595559h
0x180003e5e  mov     r11, rdx
0x180003e61  mov     dword ptr [r10], 0
0x180003e68  cmp     ecx, eax
0x180003e6a  ja      loc_180003F20
0x180003e70  jz      loc_180003FFF
0x180003e76  mov     eax, 30323449h
0x180003e7b  cmp     ecx, eax
0x180003e7d  ja      short loc_180003EC9
0x180003e7f  jz      loc_180003F08
0x180003e85  mov     eax, ecx
0x180003e87  sub     eax, 14h
0x180003e8a  jz      loc_180003FCF
0x180003e90  sub     eax, 2
0x180003e93  jz      loc_180003FBD
0x180003e99  sub     eax, 1
0x180003e9c  jz      loc_180003FE1
0x180003ea2  sub     eax, 1
0x180003ea5  jz      loc_180003FD8
0x180003eab  sub     eax, 11h
0x180003eae  jz      loc_180003FF6
0x180003eb4  sub     eax, 3031324Dh
0x180003eb9  jz      loc_180003FFF
0x180003ebf  cmp     eax, 1E0h
0x180003ec4  jmp     loc_180003F6A
0x180003ec9  mov     eax, ecx
0x180003ecb  mov     edx, 31313259h
0x180003ed0  sub     eax, edx
0x180003ed2  jz      short loc_180003F14
0x180003ed4  sub     eax, 200h
0x180003ed9  jz      loc_180003FFF
0x180003edf  sub     eax, 21F5h
0x180003ee4  jz      short loc_180003F08
0x180003ee6  sub     eax, 11F6FBh
0x180003eeb  jz      loc_180003FFF
0x180003ef1  sub     eax, 0EE0905h
0x180003ef6  jz      short loc_180003F08
0x180003ef8  sub     eax, 0Bh
0x180003efb  jz      short loc_180003F08
0x180003efd  cmp     eax, 11F6F0h
0x180003f02  jnz     loc_180003FB4
0x180003f08  mov     dword ptr [r8], 0Ch
0x180003f0f  jmp     loc_180004006
0x180003f14  mov     dword ptr [r8], 8
0x180003f1b  jmp     loc_180004008
0x180003f20  mov     eax, 56555949h
0x180003f25  cmp     ecx, eax
0x180003f27  ja      short loc_180003F84
0x180003f29  jz      short loc_180003F08
0x180003f2b  cmp     ecx, 33434D49h
0x180003f31  jz      loc_180003FFF
0x180003f37  cmp     ecx, 34434D49h
0x180003f3d  jz      short loc_180003F08
0x180003f3f  cmp     ecx, 36313256h
0x180003f45  jz      short loc_180003F6C
0x180003f47  mov     edx, 39555659h
0x180003f4c  cmp     ecx, edx
0x180003f4e  jz      short loc_180003F78
0x180003f50  cmp     ecx, 50313459h
0x180003f56  jz      short loc_180003F08
0x180003f58  cmp     ecx, 55595659h
0x180003f5e  jz      loc_180003FFF
0x180003f64  cmp     ecx, 56555941h
0x180003f6a  jnz     short loc_180003FB4
0x180003f6c  mov     dword ptr [r8], 20h ; ' '
0x180003f73  jmp     loc_180004006
0x180003f78  mov     dword ptr [r8], 9
0x180003f7f  jmp     loc_180004008
0x180003f84  cmp     ecx, 59565955h
0x180003f8a  jz      short loc_180003FFF
0x180003f8c  cmp     ecx, 0E436EB7Ah
0x180003f92  jz      short loc_180003FF6
0x180003f94  cmp     ecx, 0E436EB7Bh
0x180003f9a  jz      short loc_180003FE1
0x180003f9c  cmp     ecx, 0E436EB7Ch
0x180003fa2  jz      short loc_180003FD8
0x180003fa4  cmp     ecx, 0E436EB7Dh
0x180003faa  jz      short loc_180003FCF
0x180003fac  cmp     ecx, 0E436EB7Eh
0x180003fb2  jz      short loc_180003FBD
0x180003fb4  mov     dword ptr [r8], 0
0x180003fbb  jmp     short loc_180004006
0x180003fbd  mov     dword ptr [r8], 20h ; ' '
0x180003fc4  mov     dword ptr [r10], 1
0x180003fcb  xor     edx, edx
0x180003fcd  jmp     short loc_180004008
0x180003fcf  mov     dword ptr [r8], 18h
0x180003fd6  jmp     short loc_180003FC4
0x180003fd8  mov     dword ptr [r8], 10h
0x180003fdf  jmp     short loc_180003FC4
0x180003fe1  mov     dword ptr [r8], 10h
0x180003fe8  mov     edx, 3
0x180003fed  mov     dword ptr [r10], 1
0x180003ff4  jmp     short loc_180004008
0x180003ff6  mov     dword ptr [r8], 8
0x180003ffd  jmp     short loc_180003FC4
0x180003fff  mov     dword ptr [r8], 10h
0x180004006  mov     edx, ecx
0x180004008  mov     dword ptr [r9], 1
0x18000400f  mov     [r11], edx
0x180004012  retn
```
