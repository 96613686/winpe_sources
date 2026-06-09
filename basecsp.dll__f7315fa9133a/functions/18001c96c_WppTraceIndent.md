# WppTraceIndent

- ea: `0x18001c96c`
- end: `0x18001cad5`
- name: `WppTraceIndent`
- size: `361`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a398`
- `0x18001a674`
- `0x18001a944`
- `0x18001ab74`
- `0x18001acf4`
- `0x18001b108`
- `0x18001b818`
- `0x18001bb2c`
- `0x18001c81c`
- `0x180028008`
- `0x1800282ac`
- `0x18002835c`
- `0x180028494`
- `0x180028730`
- `0x180028810`
- `0x18002896c`
- `0x180028c88`
- `0x18002bf00`
- `0x18002bf84`

## callees

- `0x18001c66c`
- `0x18001c96c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c978`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  size_t i; // rdx
  __int64 v5; // rcx
  unsigned int v6; // r8d
  bool v7; // zf
  int v8; // ebx
  int v9; // edi
  size_t v10; // rdx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = (int)`WppTraceIndent'::`2'::idxCurrentThread;
  if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v5 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = 0;
    dword_18003C754 = 0;
  }
  else
  {
    if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * (int)`WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v6 = -1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v5 = (unsigned int)i;
          LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( v6 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v6 = i;
      }
      if ( v7 )
      {
        if ( v6 == -1 )
        {
          v5 = 4294967294LL;
        }
        else
        {
          v5 = v6;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1] = 0;
        }
        LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = v5;
      }
    }
    if ( (int)v5 < 0 )
    {
      v8 = 0;
      goto LABEL_24;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
LABEL_24:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = 1;
    if ( v8 >= 1 )
    {
      do
      {
        if ( StringCbCatA((STRSAFE_LPSTR)v5, i, "..") )
          break;
        ++v9;
      }
      while ( v9 <= v8 );
      v5 = (unsigned int)`WppTraceIndent'::`2'::idxCurrentThread;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_36;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_36;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_36:
    StringCbCatA((STRSAFE_LPSTR)v5, v10, v11);
    LODWORD(v5) = (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread;
  }
  if ( (int)v5 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x18001c96c  push    rbx
0x18001c96e  push    rsi
0x18001c96f  push    rdi
0x18001c970  push    r14
0x18001c972  sub     rsp, 28h
0x18001c976  mov     esi, edx
0x18001c978  call    cs:__imp_GetCurrentThreadId
0x18001c97e  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18001c985  lea     r14, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18001c98c  mov     r9d, eax
0x18001c98f  cmp     ecx, 0FFFFFFFFh
0x18001c992  jnz     short loc_18001C9AA
0x18001c994  xor     ecx, ecx
0x18001c996  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, eax; `WppTraceIndent'::`2'::ThreadTable
0x18001c99c  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001c9a2  mov     cs:dword_18003C754, ecx
0x18001c9a8  jmp     short loc_18001CA13
0x18001c9aa  cmp     ecx, 0FFFFFFFEh
0x18001c9ad  jz      short loc_18001C9B5
0x18001c9af  cmp     [r14+rcx*8], r9d
0x18001c9b3  jz      short loc_18001CA0F
0x18001c9b5  or      r8d, 0FFFFFFFFh
0x18001c9b9  xor     edx, edx; cbDest
0x18001c9bb  cmp     edx, 20h ; ' '
0x18001c9be  jnb     short loc_18001C9E7
0x18001c9c0  movsxd  rax, edx
0x18001c9c3  cmp     [r14+rax*8], r9d
0x18001c9c7  jz      short loc_18001C9DC
0x18001c9c9  cmp     r8d, 0FFFFFFFFh
0x18001c9cd  jnz     short loc_18001C9D8
0x18001c9cf  cmp     dword ptr [r14+rax*8], 0
0x18001c9d4  cmovz   r8d, edx
0x18001c9d8  inc     edx
0x18001c9da  jmp     short loc_18001C9BB
0x18001c9dc  mov     ecx, edx
0x18001c9de  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001c9e4  cmp     edx, 20h ; ' '
0x18001c9e7  jnz     short loc_18001CA0F
0x18001c9e9  cmp     r8d, 0FFFFFFFFh
0x18001c9ed  jz      short loc_18001CA04
0x18001c9ef  movsxd  rax, r8d
0x18001c9f2  mov     ecx, r8d
0x18001c9f5  mov     [r14+rax*8], r9d
0x18001c9f9  mov     dword ptr [r14+rax*8+4], 0
0x18001ca02  jmp     short loc_18001CA09
0x18001ca04  mov     ecx, 0FFFFFFFEh; pszDest
0x18001ca09  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18001ca0f  test    ecx, ecx
0x18001ca11  js      short loc_18001CA2D
0x18001ca13  movsxd  rax, ecx
0x18001ca16  test    esi, esi
0x18001ca18  jnz     short loc_18001CA26
0x18001ca1a  inc     dword ptr [r14+rax*8+4]
0x18001ca1f  mov     ebx, [r14+rax*8+4]
0x18001ca24  jmp     short loc_18001CA2F
0x18001ca26  mov     ebx, [r14+rax*8+4]
0x18001ca2b  jmp     short loc_18001CA2F
0x18001ca2d  xor     ebx, ebx
0x18001ca2f  mov     rax, cs:WPP_GLOBAL_Control
0x18001ca36  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18001ca3d  test    byte ptr [rax+1Ch], 2
0x18001ca41  jz      short loc_18001CA6E
0x18001ca43  cmp     byte ptr [rax+19h], 5
0x18001ca47  jb      short loc_18001CA6E
0x18001ca49  mov     edi, 1
0x18001ca4e  cmp     ebx, edi
0x18001ca50  jl      short loc_18001CA6E
0x18001ca52  lea     r8, pszSrc; ".."
0x18001ca59  call    StringCbCatA
0x18001ca5e  test    eax, eax
0x18001ca60  jnz     short loc_18001CA68
0x18001ca62  inc     edi
0x18001ca64  cmp     edi, ebx
0x18001ca66  jle     short loc_18001CA52
0x18001ca68  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; pszDest
0x18001ca6e  mov     edx, esi; cbDest
0x18001ca70  test    esi, esi
0x18001ca72  jz      short loc_18001CA90
0x18001ca74  sub     edx, 1
0x18001ca77  jz      short loc_18001CA87
0x18001ca79  cmp     edx, 1
0x18001ca7c  jnz     short loc_18001CAA2
0x18001ca7e  lea     r8, asc_180034264; " "
0x18001ca85  jmp     short loc_18001CA97
0x18001ca87  lea     r8, asc_180034268; "<"
0x18001ca8e  jmp     short loc_18001CA97
0x18001ca90  lea     r8, asc_180034260; ">"
0x18001ca97  call    StringCbCatA
0x18001ca9c  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18001caa2  test    ecx, ecx
0x18001caa4  js      short loc_18001CABD
0x18001caa6  cmp     esi, 1
0x18001caa9  jnz     short loc_18001CABD
0x18001caab  movsxd  rdx, ecx
0x18001caae  sub     [r14+rdx*8+4], esi
0x18001cab3  jnz     short loc_18001CABD
0x18001cab5  mov     dword ptr [r14+rdx*8], 0
0x18001cabd  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18001cac4  mov     cs:WPP_pszIndent, rax
0x18001cacb  add     rsp, 28h
0x18001cacf  pop     r14
0x18001cad1  pop     rdi
0x18001cad2  pop     rsi
0x18001cad3  pop     rbx
0x18001cad4  retn
```
