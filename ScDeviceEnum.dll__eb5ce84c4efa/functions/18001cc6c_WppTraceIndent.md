# WppTraceIndent

- ea: `0x18001cc6c`
- end: `0x18001cddb`
- name: `WppTraceIndent`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `40`
- callee_count: `2`
- tags: ``

## callers

- `0x18001317c`
- `0x1800135d0`
- `0x180013910`
- `0x180013ca8`
- `0x180014278`
- `0x18001446c`
- `0x180014854`
- `0x180014ca0`
- `0x180014f60`
- `0x180015324`
- `0x180015850`
- `0x180015c10`
- `0x1800160c8`
- `0x1800163b8`
- `0x180016500`
- `0x180016958`
- `0x180016d74`
- `0x180017304`
- `0x180017544`
- `0x180017954`
- `0x180017da8`
- `0x180017f9c`
- `0x180018edc`
- `0x180019250`
- `0x180019c84`
- `0x180019d6c`
- `0x18001a260`
- `0x18001aab0`
- `0x18001ad14`
- `0x18001ae54`
- `0x18001b00c`
- `0x18001b284`
- `0x18001b420`
- `0x18001b53c`
- `0x18001b660`
- `0x18001b8c0`
- `0x18001ba4c`
- `0x18001bee0`
- `0x18001bfd4`
- `0x18001c158`

## callees

- `0x18001ca08`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cc80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cc80`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  size_t v4; // rdx
  char *i; // rcx
  int v6; // ebx
  bool v7; // zf
  int v8; // edi
  int j; // esi
  unsigned __int64 v10; // rcx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18002BEE4 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v4 = 0xFFFFFFFFLL;
      for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v6 = (int)i;
          `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( (_DWORD)v4 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v4 = (unsigned int)i;
      }
      if ( v7 )
      {
        if ( (_DWORD)v4 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
        }
        else
        {
          v6 = v4;
          `WppTraceIndent'::`2'::idxCurrentThread = v4;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4 + 1] = 0;
        }
      }
    }
    if ( v6 < 0 )
    {
      v8 = 0;
      goto LABEL_23;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
LABEL_23:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v8; ++j )
    {
      if ( StringCbCatA(i, v4, "..") )
        break;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_34;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_34;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_34:
    StringCbCatA((STRSAFE_LPSTR)v10, v4, v11);
  }
  if ( v6 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * v6] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x18001cc6c  mov     [rsp+arg_8], rbx
0x18001cc71  mov     [rsp+arg_10], rbp
0x18001cc76  push    rsi
0x18001cc77  push    rdi
0x18001cc78  push    r14
0x18001cc7a  sub     rsp, 20h
0x18001cc7e  mov     ebp, edx
0x18001cc80  call    cs:__imp_GetCurrentThreadId
0x18001cc86  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18001cc8d  lea     r14, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18001cc94  mov     r8d, eax
0x18001cc97  cmp     ebx, 0FFFFFFFFh
0x18001cc9a  jnz     short loc_18001CCB2
0x18001cc9c  xor     ebx, ebx
0x18001cc9e  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, eax; `WppTraceIndent'::`2'::ThreadTable
0x18001cca4  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001ccaa  mov     cs:dword_18002BEE4, ebx
0x18001ccb0  jmp     short loc_18001CD1C
0x18001ccb2  cmp     ebx, 0FFFFFFFEh
0x18001ccb5  jz      short loc_18001CCBD
0x18001ccb7  cmp     [r14+rbx*8], r8d
0x18001ccbb  jz      short loc_18001CD18
0x18001ccbd  or      edx, 0FFFFFFFFh; cbDest
0x18001ccc0  xor     ecx, ecx; pszDest
0x18001ccc2  cmp     ecx, 20h ; ' '
0x18001ccc5  jnb     short loc_18001CCEC
0x18001ccc7  movsxd  rax, ecx
0x18001ccca  cmp     [r14+rax*8], r8d
0x18001ccce  jz      short loc_18001CCE1
0x18001ccd0  cmp     edx, 0FFFFFFFFh
0x18001ccd3  jnz     short loc_18001CCDD
0x18001ccd5  cmp     dword ptr [r14+rax*8], 0
0x18001ccda  cmovz   edx, ecx
0x18001ccdd  inc     ecx
0x18001ccdf  jmp     short loc_18001CCC2
0x18001cce1  mov     ebx, ecx
0x18001cce3  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001cce9  cmp     ecx, 20h ; ' '
0x18001ccec  jnz     short loc_18001CD18
0x18001ccee  cmp     edx, 0FFFFFFFFh
0x18001ccf1  jz      short loc_18001CD0D
0x18001ccf3  movsxd  rax, edx
0x18001ccf6  mov     ebx, edx
0x18001ccf8  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001ccfe  mov     [r14+rax*8], r8d
0x18001cd02  mov     dword ptr [r14+rax*8+4], 0
0x18001cd0b  jmp     short loc_18001CD18
0x18001cd0d  mov     ebx, 0FFFFFFFEh
0x18001cd12  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001cd18  test    ebx, ebx
0x18001cd1a  js      short loc_18001CD36
0x18001cd1c  movsxd  rax, ebx
0x18001cd1f  test    ebp, ebp
0x18001cd21  jnz     short loc_18001CD2F
0x18001cd23  inc     dword ptr [r14+rax*8+4]
0x18001cd28  mov     edi, [r14+rax*8+4]
0x18001cd2d  jmp     short loc_18001CD38
0x18001cd2f  mov     edi, [r14+rax*8+4]
0x18001cd34  jmp     short loc_18001CD38
0x18001cd36  xor     edi, edi
0x18001cd38  mov     rax, cs:WPP_GLOBAL_Control
0x18001cd3f  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18001cd46  test    byte ptr [rax+1Ch], 2
0x18001cd4a  jz      short loc_18001CD71
0x18001cd4c  cmp     byte ptr [rax+19h], 5
0x18001cd50  jb      short loc_18001CD71
0x18001cd52  mov     esi, 1
0x18001cd57  cmp     edi, esi
0x18001cd59  jl      short loc_18001CD71
0x18001cd5b  lea     r8, pszSrc; ".."
0x18001cd62  call    StringCbCatA
0x18001cd67  test    eax, eax
0x18001cd69  jnz     short loc_18001CD71
0x18001cd6b  inc     esi
0x18001cd6d  cmp     esi, edi
0x18001cd6f  jle     short loc_18001CD5B
0x18001cd71  mov     ecx, ebp; pszDest
0x18001cd73  test    ebp, ebp
0x18001cd75  jz      short loc_18001CD93
0x18001cd77  sub     ecx, 1
0x18001cd7a  jz      short loc_18001CD8A
0x18001cd7c  cmp     ecx, 1
0x18001cd7f  jnz     short loc_18001CD9F
0x18001cd81  lea     r8, asc_18002399C; " "
0x18001cd88  jmp     short loc_18001CD9A
0x18001cd8a  lea     r8, asc_1800239A0; "<"
0x18001cd91  jmp     short loc_18001CD9A
0x18001cd93  lea     r8, asc_180023998; ">"
0x18001cd9a  call    StringCbCatA
0x18001cd9f  test    ebx, ebx
0x18001cda1  js      short loc_18001CDBA
0x18001cda3  cmp     ebp, 1
0x18001cda6  jnz     short loc_18001CDBA
0x18001cda8  movsxd  rcx, ebx
0x18001cdab  sub     [r14+rcx*8+4], ebp
0x18001cdb0  jnz     short loc_18001CDBA
0x18001cdb2  mov     dword ptr [r14+rcx*8], 0
0x18001cdba  mov     rbx, [rsp+38h+arg_8]
0x18001cdbf  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18001cdc6  mov     rbp, [rsp+38h+arg_10]
0x18001cdcb  mov     cs:WPP_pszIndent, rax
0x18001cdd2  add     rsp, 20h
0x18001cdd6  pop     r14
0x18001cdd8  pop     rdi
0x18001cdd9  pop     rsi
0x18001cdda  retn
```
