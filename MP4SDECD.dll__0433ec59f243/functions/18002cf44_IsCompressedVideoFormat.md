# IsCompressedVideoFormat

- ea: `0x18002cf44`
- end: `0x18002d05c`
- name: `IsCompressedVideoFormat`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029d58`

## callees

- `0x18002cf44`

## pseudocode

```c
__int64 __fastcall IsCompressedVideoFormat(__int64 a1)
{
  unsigned int v1; // r8d
  unsigned __int64 v2; // rdx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  bool v9; // zf

  v1 = 1;
  v2 = *(_QWORD *)(a1 + 4) - *(_QWORD *)&MFVideoFormat_Base.Data2;
  if ( !v2 )
    v2 = *(unsigned int *)(a1 + 12) - (unsigned __int64)*(unsigned int *)&MFVideoFormat_Base.Data4[4];
  if ( !v2 )
  {
    v3 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 <= 0x32315659u )
    {
      if ( v3 == 842094169 )
        return 0;
      if ( v3 <= 0x30313276 )
      {
        if ( v3 != 808530550 )
        {
          if ( v3 )
          {
            v4 = v3 - 3;
            if ( v4 )
            {
              v5 = v4 - 17;
              if ( v5 )
              {
                v6 = v5 - 2;
                if ( v6 )
                {
                  v7 = v6 - 1;
                  if ( v7 )
                  {
                    v8 = v7 - 1;
                    if ( v8 )
                    {
                      v9 = v8 == 17;
                      goto LABEL_21;
                    }
                  }
                }
              }
            }
          }
        }
        return 0;
      }
      if ( v3 == 808531030 || v3 == 808596553 || v3 == 825307737 || v3 == 825308249 || v3 == 825316942 )
        return 0;
      v9 = v3 == 842094158;
LABEL_21:
      if ( !v9 )
        return v1;
      return 0;
    }
    if ( v3 <= 0x56555949 )
    {
      if ( v3 == 1448433993
        || v3 == 844715353
        || v3 == 909193814
        || v3 == 961893977
        || v3 == 1345401945
        || v3 == 1431918169 )
      {
        return 0;
      }
      v9 = v3 == 1448433985;
      goto LABEL_21;
    }
    if ( v3 == 1498831189
      || v3 == -466162822
      || v3 == -466162821
      || v3 == -466162820
      || v3 == -466162819
      || v3 == -466162818 )
    {
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18002cf44  mov     rdx, [rcx+4]
0x18002cf48  mov     r8d, 1
0x18002cf4e  sub     rdx, qword ptr cs:MFVideoFormat_Base.Data2
0x18002cf55  jnz     short loc_18002CF63
0x18002cf57  mov     edx, [rcx+0Ch]
0x18002cf5a  mov     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x18002cf60  sub     rdx, rax
0x18002cf63  test    rdx, rdx
0x18002cf66  jnz     loc_18002D058
0x18002cf6c  mov     eax, [rcx]
0x18002cf6e  mov     ecx, 32315659h
0x18002cf73  cmp     eax, ecx
0x18002cf75  ja      short loc_18002CFF6
0x18002cf77  jz      loc_18002D055
0x18002cf7d  mov     ecx, 30313276h
0x18002cf82  cmp     eax, ecx
0x18002cf84  ja      short loc_18002CFC6
0x18002cf86  jz      loc_18002D055
0x18002cf8c  test    eax, eax
0x18002cf8e  jz      loc_18002D055
0x18002cf94  sub     eax, 3
0x18002cf97  jz      loc_18002D055
0x18002cf9d  sub     eax, 11h
0x18002cfa0  jz      loc_18002D055
0x18002cfa6  sub     eax, 2
0x18002cfa9  jz      loc_18002D055
0x18002cfaf  sub     eax, r8d
0x18002cfb2  jz      loc_18002D055
0x18002cfb8  sub     eax, r8d
0x18002cfbb  jz      loc_18002D055
0x18002cfc1  cmp     eax, 11h
0x18002cfc4  jmp     short loc_18002CFF2
0x18002cfc6  cmp     eax, 30313456h
0x18002cfcb  jz      loc_18002D055
0x18002cfd1  cmp     eax, 30323449h
0x18002cfd6  jz      short loc_18002D055
0x18002cfd8  cmp     eax, 31313259h
0x18002cfdd  jz      short loc_18002D055
0x18002cfdf  cmp     eax, 31313459h
0x18002cfe4  jz      short loc_18002D055
0x18002cfe6  cmp     eax, 3131564Eh
0x18002cfeb  jz      short loc_18002D055
0x18002cfed  cmp     eax, 3231564Eh
0x18002cff2  jz      short loc_18002D055
0x18002cff4  jmp     short loc_18002D058
0x18002cff6  mov     ecx, 56555949h
0x18002cffb  cmp     eax, ecx
0x18002cffd  ja      short loc_18002D02B
0x18002cfff  jz      short loc_18002D055
0x18002d001  cmp     eax, 32595559h
0x18002d006  jz      short loc_18002D055
0x18002d008  cmp     eax, 36313256h
0x18002d00d  jz      short loc_18002D055
0x18002d00f  cmp     eax, 39555659h
0x18002d014  jz      short loc_18002D055
0x18002d016  cmp     eax, 50313459h
0x18002d01b  jz      short loc_18002D055
0x18002d01d  cmp     eax, 55595659h
0x18002d022  jz      short loc_18002D055
0x18002d024  cmp     eax, 56555941h
0x18002d029  jmp     short loc_18002CFF2
0x18002d02b  cmp     eax, 59565955h
0x18002d030  jz      short loc_18002D055
0x18002d032  cmp     eax, 0E436EB7Ah
0x18002d037  jz      short loc_18002D055
0x18002d039  cmp     eax, 0E436EB7Bh
0x18002d03e  jz      short loc_18002D055
0x18002d040  cmp     eax, 0E436EB7Ch
0x18002d045  jz      short loc_18002D055
0x18002d047  cmp     eax, 0E436EB7Dh
0x18002d04c  jz      short loc_18002D055
0x18002d04e  cmp     eax, 0E436EB7Eh
0x18002d053  jnz     short loc_18002D058
0x18002d055  xor     r8d, r8d
0x18002d058  mov     eax, r8d
0x18002d05b  retn
```
