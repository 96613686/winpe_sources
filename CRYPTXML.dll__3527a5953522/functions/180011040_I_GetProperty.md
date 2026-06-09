# I_GetProperty

- ea: `0x180011040`
- end: `0x1800110ce`
- name: `I_GetProperty`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012600`
- `0x180016820`
- `0x180016a0c`

## callees

- `0x1800070d0`
- `0x180011040`
- `0x180014ce0`
- `0x18001860d`
- `0x180018625`

## string_xrefs

- `0x1800110a1`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`

## pseudocode

```c
__int64 __fastcall I_GetProperty(int a1, __int64 a2, unsigned int a3, void *a4, unsigned int Size)
{
  __int64 i; // rax
  __int64 v7; // rdx
  const char *v9; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a3 )
    {
      memset_0(a4, 0, Size);
      return 1;
    }
    v7 = a2 + 24 * i;
    if ( a1 == *(_DWORD *)v7 )
      break;
  }
  if ( Size == *(_DWORD *)(v7 + 16) )
  {
    memcpy_0(a4, *(const void **)(v7 + 8), Size);
    return 0;
  }
  else
  {
    v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v9, 97);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180011040  push    rbx
0x180011042  sub     rsp, 20h
0x180011046  mov     r11, r9
0x180011049  mov     rbx, rdx
0x18001104c  xor     eax, eax
0x18001104e  cmp     eax, r8d
0x180011051  jnb     short loc_180011082
0x180011053  lea     r9, [rax+rax*2]
0x180011057  cmp     ecx, [rbx+r9*8]
0x18001105b  lea     rdx, [rbx+r9*8]
0x18001105f  jnz     short loc_18001109D
0x180011061  mov     eax, dword ptr [rsp+28h+Size]
0x180011065  cmp     eax, [rdx+10h]
0x180011068  jnz     short loc_1800110A1
0x18001106a  mov     rdx, [rdx+8]; Src
0x18001106e  mov     r8d, eax; Size
0x180011071  mov     rcx, r11; void *
0x180011074  call    memcpy_0
0x180011079  xor     eax, eax
0x18001107b  add     rsp, 20h
0x18001107f  pop     rbx
0x180011080  retn
0x180011082  mov     r8d, dword ptr [rsp+28h+Size]; Size
0x180011087  xor     edx, edx; Val
0x180011089  mov     rcx, r11; void *
0x18001108c  call    memset_0
0x180011091  mov     eax, 1
0x180011096  add     rsp, 20h
0x18001109a  pop     rbx
0x18001109b  retn
0x18001109d  inc     eax
0x18001109f  jmp     short loc_18001104E
0x1800110a1  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800110a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800110ad  mov     r8, rax
0x1800110b0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800110b7  mov     edx, 80070057h
0x1800110bc  mov     r9d, 61h ; 'a'
0x1800110c2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800110c7  mov     eax, 80070057h
0x1800110cc  jmp     short loc_180011096
```
