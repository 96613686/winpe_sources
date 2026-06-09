# IsCompressedVideoFormat

- ea: `0x180005508`
- end: `0x1800055ec`
- name: `IsCompressedVideoFormat`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039c0`

## callees

- `0x180005508`

## pseudocode

```c
__int64 __fastcall IsCompressedVideoFormat(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  bool v8; // zf

  v1 = 1;
  if ( *(_QWORD *)(a1 + 4) == *(_QWORD *)&MFVideoFormat_Base.Data2
    && *(_DWORD *)(a1 + 12) == *(_DWORD *)&MFVideoFormat_Base.Data4[4] )
  {
    v2 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 <= 0x32315659u )
    {
      if ( v2 != 842094169 )
      {
        if ( v2 > 0x30313276 )
        {
          if ( v2 != 808531030 && v2 != 808596553 && v2 != 825307737 && v2 != 825308249 && v2 != 825316942 )
          {
            v8 = v2 == 842094158;
LABEL_20:
            if ( !v8 )
              return v1;
          }
        }
        else if ( v2 != 808530550 )
        {
          if ( v2 )
          {
            v3 = v2 - 3;
            if ( v3 )
            {
              v4 = v3 - 17;
              if ( v4 )
              {
                v5 = v4 - 2;
                if ( v5 )
                {
                  v6 = v5 - 1;
                  if ( v6 )
                  {
                    v7 = v6 - 1;
                    if ( v7 )
                    {
                      v8 = v7 == 17;
                      goto LABEL_20;
                    }
                  }
                }
              }
            }
          }
        }
      }
      return 0;
    }
    if ( v2 == 1448433993
      || v2 == 844715353
      || v2 == 909193814
      || v2 == 961893977
      || v2 == 1345401945
      || v2 == 1431918169
      || v2 == 1448433985
      || v2 == 1498831189
      || v2 + 466162822 <= 4 )
    {
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180005508  mov     rax, [rcx+4]
0x18000550c  mov     edx, 1
0x180005511  cmp     rax, qword ptr cs:MFVideoFormat_Base.Data2
0x180005518  jnz     loc_1800055E9
0x18000551e  mov     eax, [rcx+0Ch]
0x180005521  cmp     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x180005527  jnz     loc_1800055E9
0x18000552d  mov     eax, [rcx]
0x18000552f  mov     ecx, 32315659h
0x180005534  cmp     eax, ecx
0x180005536  ja      short loc_1800055A5
0x180005538  jz      loc_1800055E7
0x18000553e  mov     ecx, 30313276h
0x180005543  cmp     eax, ecx
0x180005545  ja      short loc_180005579
0x180005547  jz      loc_1800055E7
0x18000554d  test    eax, eax
0x18000554f  jz      loc_1800055E7
0x180005555  sub     eax, 3
0x180005558  jz      loc_1800055E7
0x18000555e  sub     eax, 11h
0x180005561  jz      loc_1800055E7
0x180005567  sub     eax, 2
0x18000556a  jz      short loc_1800055E7
0x18000556c  sub     eax, edx
0x18000556e  jz      short loc_1800055E7
0x180005570  sub     eax, edx
0x180005572  jz      short loc_1800055E7
0x180005574  cmp     eax, 11h
0x180005577  jmp     short loc_1800055A1
0x180005579  cmp     eax, 30313456h
0x18000557e  jz      short loc_1800055E7
0x180005580  cmp     eax, 30323449h
0x180005585  jz      short loc_1800055E7
0x180005587  cmp     eax, 31313259h
0x18000558c  jz      short loc_1800055E7
0x18000558e  cmp     eax, 31313459h
0x180005593  jz      short loc_1800055E7
0x180005595  cmp     eax, 3131564Eh
0x18000559a  jz      short loc_1800055E7
0x18000559c  cmp     eax, 3231564Eh
0x1800055a1  jz      short loc_1800055E7
0x1800055a3  jmp     short loc_1800055E9
0x1800055a5  cmp     eax, 56555949h
0x1800055aa  jz      short loc_1800055E7
0x1800055ac  cmp     eax, 32595559h
0x1800055b1  jz      short loc_1800055E7
0x1800055b3  cmp     eax, 36313256h
0x1800055b8  jz      short loc_1800055E7
0x1800055ba  cmp     eax, 39555659h
0x1800055bf  jz      short loc_1800055E7
0x1800055c1  cmp     eax, 50313459h
0x1800055c6  jz      short loc_1800055E7
0x1800055c8  cmp     eax, 55595659h
0x1800055cd  jz      short loc_1800055E7
0x1800055cf  cmp     eax, 56555941h
0x1800055d4  jz      short loc_1800055E7
0x1800055d6  cmp     eax, 59565955h
0x1800055db  jz      short loc_1800055E7
0x1800055dd  add     eax, 1BC91486h
0x1800055e2  cmp     eax, 4
0x1800055e5  ja      short loc_1800055E9
0x1800055e7  xor     edx, edx
0x1800055e9  mov     eax, edx
0x1800055eb  retn
```
