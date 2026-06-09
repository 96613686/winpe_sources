# DllInitCodec

- ea: `0x18002575c`
- end: `0x1800257bc`
- name: `DllInitCodec`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ea68`

## callees

- `0x18002575c`
- `0x1800378d0`
- `0x180037920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257a9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025773`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025773`

## pseudocode

```c
void __fastcall DllInitCodec(int a1)
{
  if ( a1 == 1 )
  {
    g_petwPro = malloc(0x38u);
    if ( g_petwPro )
      ETWInit();
  }
  else if ( !a1 && g_petwPro )
  {
    ETWClean();
    if ( g_petwPro )
    {
      free(g_petwPro);
      g_petwPro = 0;
    }
  }
}

```

## disassembly

```asm
0x18002575c  sub     rsp, 28h
0x180025760  cmp     ecx, 1
0x180025763  jz      short loc_18002576E
0x180025765  test    ecx, ecx
0x180025767  jz      short loc_18002578E
0x180025769  add     rsp, 28h
0x18002576d  retn
0x18002576e  mov     ecx, 38h ; '8'; Size
0x180025773  call    cs:__imp_malloc
0x180025779  mov     cs:g_petwPro, rax
0x180025780  test    rax, rax
0x180025783  jz      short loc_180025769
0x180025785  add     rsp, 28h
0x180025789  jmp     ETWInit
0x18002578e  cmp     cs:g_petwPro, 0
0x180025796  jz      short loc_180025769
0x180025798  call    ETWClean
0x18002579d  mov     rcx, cs:g_petwPro; Block
0x1800257a4  test    rcx, rcx
0x1800257a7  jz      short loc_180025769
0x1800257a9  call    cs:__imp_free
0x1800257af  mov     cs:g_petwPro, 0
0x1800257ba  jmp     short loc_180025769
```
