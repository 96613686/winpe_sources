# WppTraceIndent

- ea: `0x180005700`
- end: `0x1800058e4`
- name: `WppTraceIndent`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029c8`
- `0x180005090`
- `0x180030680`
- `0x180030c98`
- `0x180030d4c`
- `0x180030eb4`

## callees

- `0x180005700`
- `0x180005918`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005715`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, int a2)
{
  DWORD CurrentThreadId; // eax
  size_t v4; // rdx
  char *v5; // rcx
  int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  unsigned int i; // eax
  bool v10; // zf
  int v11; // esi
  const char *v12; // r8
  char *result; // rax
  __int64 v14; // rcx
  int j; // ebp

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  v7 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread != -1 )
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v8 = -1;
      for ( i = 0; ; ++i )
      {
        v10 = i == 32;
        if ( i >= 0x20 )
          break;
        v5 = (char *)(int)i;
        v4 = (unsigned int)`WppTraceIndent'::`2'::ThreadTable[2 * i];
        if ( (_DWORD)v4 == v7 )
        {
          v6 = i;
          `WppTraceIndent'::`2'::idxCurrentThread = i;
          v10 = i == 32;
          break;
        }
        if ( v8 == -1 && !(_DWORD)v4 )
          v8 = i;
      }
      if ( v10 )
      {
        if ( v8 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_29;
        }
        v6 = v8;
        `WppTraceIndent'::`2'::idxCurrentThread = v8;
        `WppTraceIndent'::`2'::ThreadTable[2 * v8] = v7;
        `WppTraceIndent'::`2'::ThreadTable[2 * v8 + 1] = 0;
      }
    }
    if ( v6 >= 0 )
      goto LABEL_15;
LABEL_29:
    v11 = 0;
    goto LABEL_18;
  }
  v6 = 0;
  `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
  `WppTraceIndent'::`2'::idxCurrentThread = 0;
  dword_18004BFB4 = 0;
LABEL_15:
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
  v11 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
LABEL_18:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v11; ++j )
    {
      if ( StringCbCatA(v5, v4, "..") )
        break;
    }
  }
  if ( a2 )
  {
    v5 = (char *)(unsigned int)(a2 - 1);
    if ( a2 == 1 )
    {
      v12 = "<";
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_22;
      v12 = " ";
    }
  }
  else
  {
    v12 = ">";
  }
  StringCbCatA(v5, v4, v12);
LABEL_22:
  if ( v6 >= 0 && a2 == 1 )
  {
    v14 = 2LL * v6;
    v10 = `WppTraceIndent'::`2'::ThreadTable[v14 + 1]-- == 1;
    result = &`WppTraceIndent'::`2'::szIndentPrefix;
    WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
    if ( v10 )
      `WppTraceIndent'::`2'::ThreadTable[v14] = 0;
  }
  else
  {
    result = &`WppTraceIndent'::`2'::szIndentPrefix;
    WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  }
  return result;
}

```

## disassembly

```asm
0x180005700  mov     [rsp+arg_18], rbx
0x180005705  push    rdi
0x180005706  push    r14
0x180005708  push    r15
0x18000570a  sub     rsp, 20h
0x18000570e  mov     [rsp+38h+arg_10], rsi
0x180005713  mov     edi, edx
0x180005715  call    cs:__imp_GetCurrentThreadId
0x18000571b  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x180005722  lea     r15, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180005729  xor     r14d, r14d
0x18000572c  mov     r9d, eax
0x18000572f  cmp     ebx, 0FFFFFFFFh
0x180005732  jz      short loc_18000579B
0x180005734  cmp     ebx, 0FFFFFFFEh
0x180005737  jnz     loc_18000587D
0x18000573d  mov     r8d, 0FFFFFFFFh
0x180005743  mov     eax, r14d
0x180005746  cmp     eax, 20h ; ' '
0x180005749  jnb     short loc_180005770
0x18000574b  movsxd  rcx, eax
0x18000574e  mov     edx, [r15+rcx*8]
0x180005752  cmp     edx, r9d
0x180005755  jz      short loc_180005765
0x180005757  cmp     r8d, 0FFFFFFFFh
0x18000575b  jz      loc_1800058A1
0x180005761  inc     eax
0x180005763  jmp     short loc_180005746
0x180005765  mov     ebx, eax
0x180005767  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, eax; `WppTraceIndent'::`2'::idxCurrentThread
0x18000576d  cmp     eax, 20h ; ' '
0x180005770  jnz     short loc_180005791
0x180005772  cmp     r8d, 0FFFFFFFFh
0x180005776  jz      loc_180005848
0x18000577c  movsxd  rax, r8d
0x18000577f  mov     ebx, r8d
0x180005782  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x180005788  mov     [r15+rax*8], r9d
0x18000578c  mov     [r15+rax*8+4], r14d
0x180005791  test    ebx, ebx
0x180005793  js      loc_180005853
0x180005799  jmp     short loc_1800057B2
0x18000579b  mov     ebx, r14d
0x18000579e  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r9d; `WppTraceIndent'::`2'::ThreadTable
0x1800057a5  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x1800057ab  mov     cs:dword_18004BFB4, r14d
0x1800057b2  movsxd  rax, ebx
0x1800057b5  test    edi, edi
0x1800057b7  jz      loc_18000586E
0x1800057bd  mov     esi, [r15+rax*8+4]
0x1800057c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800057c9  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x1800057d0  test    byte ptr [rax+1Ch], 2
0x1800057d4  jnz     loc_1800058AC
0x1800057da  mov     rsi, [rsp+38h+arg_10]
0x1800057df  test    edi, edi
0x1800057e1  jnz     short loc_18000585B
0x1800057e3  lea     r8, pszSrc; ">"
0x1800057ea  call    StringCbCatA
0x1800057ef  test    ebx, ebx
0x1800057f1  jns     short loc_180005810
0x1800057f3  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x1800057fa  mov     cs:WPP_pszIndent, rax
0x180005801  mov     rbx, [rsp+38h+arg_18]
0x180005806  add     rsp, 20h
0x18000580a  pop     r15
0x18000580c  pop     r14
0x18000580e  pop     rdi
0x18000580f  retn
0x180005810  cmp     edi, 1
0x180005813  jnz     short loc_1800057F3
0x180005815  movsxd  rax, ebx
0x180005818  lea     rcx, ds:0[rax*8]
0x180005820  sub     [rcx+r15+4], edi
0x180005825  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000582c  mov     cs:WPP_pszIndent, rax
0x180005833  jnz     short loc_180005801
0x180005835  mov     rbx, [rsp+38h+arg_18]
0x18000583a  mov     [rcx+r15], r14d
0x18000583e  add     rsp, 20h
0x180005842  pop     r15
0x180005844  pop     r14
0x180005846  pop     rdi
0x180005847  retn
0x180005848  mov     ebx, 0FFFFFFFEh
0x18000584d  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x180005853  mov     esi, r14d
0x180005856  jmp     loc_1800057C2
0x18000585b  mov     ecx, edi
0x18000585d  sub     ecx, 1
0x180005860  jnz     short loc_18000588C
0x180005862  lea     r8, asc_18003BC58; "<"
0x180005869  jmp     loc_1800057EA
0x18000586e  inc     dword ptr [r15+rax*8+4]
0x180005873  mov     esi, [r15+rax*8+4]
0x180005878  jmp     loc_1800057C2
0x18000587d  cmp     [r15+rbx*8], r9d
0x180005881  jnz     loc_18000573D
0x180005887  jmp     loc_180005791
0x18000588c  cmp     ecx, 1
0x18000588f  jnz     loc_1800057EF
0x180005895  lea     r8, asc_18003BC60; " "
0x18000589c  jmp     loc_1800057EA
0x1800058a1  test    edx, edx
0x1800058a3  cmovz   r8d, eax
0x1800058a7  jmp     loc_180005761
0x1800058ac  cmp     byte ptr [rax+19h], 5
0x1800058b0  jb      loc_1800057DA
0x1800058b6  mov     [rsp+38h+arg_8], rbp
0x1800058bb  mov     ebp, 1
0x1800058c0  cmp     esi, ebp
0x1800058c2  jl      short loc_1800058DA
0x1800058c4  lea     r8, asc_1800400D4; ".."
0x1800058cb  call    StringCbCatA
0x1800058d0  test    eax, eax
0x1800058d2  jnz     short loc_1800058DA
0x1800058d4  inc     ebp
0x1800058d6  cmp     ebp, esi
0x1800058d8  jle     short loc_1800058C4
0x1800058da  mov     rbp, [rsp+38h+arg_8]
0x1800058df  jmp     loc_1800057DA
```
