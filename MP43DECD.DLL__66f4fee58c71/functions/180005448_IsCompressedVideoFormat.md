# IsCompressedVideoFormat

- ea: `0x180005448`
- end: `0x18000552c`
- name: `IsCompressedVideoFormat`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003900`

## callees

- `0x180005448`

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
0x180005448  mov     rax, [rcx+4]
0x18000544c  mov     edx, 1
0x180005451  cmp     rax, qword ptr cs:MFVideoFormat_Base.Data2
0x180005458  jnz     loc_180005529
0x18000545e  mov     eax, [rcx+0Ch]
0x180005461  cmp     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x180005467  jnz     loc_180005529
0x18000546d  mov     eax, [rcx]
0x18000546f  mov     ecx, 32315659h
0x180005474  cmp     eax, ecx
0x180005476  ja      short loc_1800054E5
0x180005478  jz      loc_180005527
0x18000547e  mov     ecx, 30313276h
0x180005483  cmp     eax, ecx
0x180005485  ja      short loc_1800054B9
0x180005487  jz      loc_180005527
0x18000548d  test    eax, eax
0x18000548f  jz      loc_180005527
0x180005495  sub     eax, 3
0x180005498  jz      loc_180005527
0x18000549e  sub     eax, 11h
0x1800054a1  jz      loc_180005527
0x1800054a7  sub     eax, 2
0x1800054aa  jz      short loc_180005527
0x1800054ac  sub     eax, edx
0x1800054ae  jz      short loc_180005527
0x1800054b0  sub     eax, edx
0x1800054b2  jz      short loc_180005527
0x1800054b4  cmp     eax, 11h
0x1800054b7  jmp     short loc_1800054E1
0x1800054b9  cmp     eax, 30313456h
0x1800054be  jz      short loc_180005527
0x1800054c0  cmp     eax, 30323449h
0x1800054c5  jz      short loc_180005527
0x1800054c7  cmp     eax, 31313259h
0x1800054cc  jz      short loc_180005527
0x1800054ce  cmp     eax, 31313459h
0x1800054d3  jz      short loc_180005527
0x1800054d5  cmp     eax, 3131564Eh
0x1800054da  jz      short loc_180005527
0x1800054dc  cmp     eax, 3231564Eh
0x1800054e1  jz      short loc_180005527
0x1800054e3  jmp     short loc_180005529
0x1800054e5  cmp     eax, 56555949h
0x1800054ea  jz      short loc_180005527
0x1800054ec  cmp     eax, 32595559h
0x1800054f1  jz      short loc_180005527
0x1800054f3  cmp     eax, 36313256h
0x1800054f8  jz      short loc_180005527
0x1800054fa  cmp     eax, 39555659h
0x1800054ff  jz      short loc_180005527
0x180005501  cmp     eax, 50313459h
0x180005506  jz      short loc_180005527
0x180005508  cmp     eax, 55595659h
0x18000550d  jz      short loc_180005527
0x18000550f  cmp     eax, 56555941h
0x180005514  jz      short loc_180005527
0x180005516  cmp     eax, 59565955h
0x18000551b  jz      short loc_180005527
0x18000551d  add     eax, 1BC91486h
0x180005522  cmp     eax, 4
0x180005525  ja      short loc_180005529
0x180005527  xor     edx, edx
0x180005529  mov     eax, edx
0x18000552b  retn
```
