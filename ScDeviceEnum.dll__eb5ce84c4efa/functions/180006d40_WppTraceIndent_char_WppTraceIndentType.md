# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x180006d40`
- end: `0x180006eaf`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `367`
- prototype: `char *__fastcall(__int64, unsigned int)`
- caller_count: `104`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ebc`
- `0x180005f20`
- `0x180005f7c`
- `0x180005fd8`
- `0x180006130`
- `0x1800064c4`
- `0x180006670`
- `0x180006ad0`
- `0x1800077d4`
- `0x180007830`
- `0x18000788c`
- `0x1800078e8`
- `0x180007944`
- `0x1800079a0`
- `0x180007a10`
- `0x180007a80`
- `0x180007bb4`
- `0x180007d34`
- `0x180008740`
- `0x1800087b0`
- `0x18000880c`
- `0x18000887c`
- `0x1800088ec`
- `0x180008948`
- `0x1800089b8`
- `0x180008a14`
- `0x180008c14`
- `0x180009274`
- `0x180009490`
- `0x1800096f4`
- `0x180009d80`
- `0x180009ddc`
- `0x180009e38`
- `0x180009ea8`
- `0x180009fbc`
- `0x18000a150`
- `0x18000aedc`
- `0x18000b004`
- `0x18000b074`
- `0x18000b0d0`
- `0x18000b12c`
- `0x18000b19c`
- `0x18000b1f8`
- `0x18000b370`
- `0x18000b3e0`
- `0x18000b4a0`
- `0x18000b7cc`
- `0x18000bb00`
- `0x18000cc78`
- `0x18000ccd4`

## callees

- `0x180006c80`
- `0x180006d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d54`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v4; // rdx
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
    dword_18002BBD4 = 0;
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
      if ( (unsigned int)StringCbCatA(i, v4, "..") )
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
    StringCbCatA((char *)v10, v4, v11);
  }
  if ( v6 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * v6] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x180006d40  mov     [rsp+arg_8], rbx
0x180006d45  mov     [rsp+arg_10], rbp
0x180006d4a  push    rsi
0x180006d4b  push    rdi
0x180006d4c  push    r14
0x180006d4e  sub     rsp, 20h
0x180006d52  mov     ebp, edx
0x180006d54  call    cs:__imp_GetCurrentThreadId
0x180006d5a  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006d61  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006d68  mov     r8d, eax
0x180006d6b  cmp     ebx, 0FFFFFFFFh
0x180006d6e  jnz     short loc_180006D86
0x180006d70  xor     ebx, ebx
0x180006d72  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, eax; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006d78  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006d7e  mov     cs:dword_18002BBD4, ebx
0x180006d84  jmp     short loc_180006DF0
0x180006d86  cmp     ebx, 0FFFFFFFEh
0x180006d89  jz      short loc_180006D91
0x180006d8b  cmp     [r14+rbx*8], r8d
0x180006d8f  jz      short loc_180006DEC
0x180006d91  or      edx, 0FFFFFFFFh; unsigned __int64
0x180006d94  xor     ecx, ecx; char *
0x180006d96  cmp     ecx, 20h ; ' '
0x180006d99  jnb     short loc_180006DC0
0x180006d9b  movsxd  rax, ecx
0x180006d9e  cmp     [r14+rax*8], r8d
0x180006da2  jz      short loc_180006DB5
0x180006da4  cmp     edx, 0FFFFFFFFh
0x180006da7  jnz     short loc_180006DB1
0x180006da9  cmp     dword ptr [r14+rax*8], 0
0x180006dae  cmovz   edx, ecx
0x180006db1  inc     ecx
0x180006db3  jmp     short loc_180006D96
0x180006db5  mov     ebx, ecx
0x180006db7  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006dbd  cmp     ecx, 20h ; ' '
0x180006dc0  jnz     short loc_180006DEC
0x180006dc2  cmp     edx, 0FFFFFFFFh
0x180006dc5  jz      short loc_180006DE1
0x180006dc7  movsxd  rax, edx
0x180006dca  mov     ebx, edx
0x180006dcc  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006dd2  mov     [r14+rax*8], r8d
0x180006dd6  mov     dword ptr [r14+rax*8+4], 0
0x180006ddf  jmp     short loc_180006DEC
0x180006de1  mov     ebx, 0FFFFFFFEh
0x180006de6  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006dec  test    ebx, ebx
0x180006dee  js      short loc_180006E0A
0x180006df0  movsxd  rax, ebx
0x180006df3  test    ebp, ebp
0x180006df5  jnz     short loc_180006E03
0x180006df7  inc     dword ptr [r14+rax*8+4]
0x180006dfc  mov     edi, [r14+rax*8+4]
0x180006e01  jmp     short loc_180006E0C
0x180006e03  mov     edi, [r14+rax*8+4]
0x180006e08  jmp     short loc_180006E0C
0x180006e0a  xor     edi, edi
0x180006e0c  mov     rax, cs:WPP_GLOBAL_Control
0x180006e13  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006e1a  test    byte ptr [rax+1Ch], 2
0x180006e1e  jz      short loc_180006E45
0x180006e20  cmp     byte ptr [rax+19h], 5
0x180006e24  jb      short loc_180006E45
0x180006e26  mov     esi, 1
0x180006e2b  cmp     edi, esi
0x180006e2d  jl      short loc_180006E45
0x180006e2f  lea     r8, pszSrc; ".."
0x180006e36  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180006e3b  test    eax, eax
0x180006e3d  jnz     short loc_180006E45
0x180006e3f  inc     esi
0x180006e41  cmp     esi, edi
0x180006e43  jle     short loc_180006E2F
0x180006e45  mov     ecx, ebp; char *
0x180006e47  test    ebp, ebp
0x180006e49  jz      short loc_180006E67
0x180006e4b  sub     ecx, 1
0x180006e4e  jz      short loc_180006E5E
0x180006e50  cmp     ecx, 1
0x180006e53  jnz     short loc_180006E73
0x180006e55  lea     r8, asc_18002399C; " "
0x180006e5c  jmp     short loc_180006E6E
0x180006e5e  lea     r8, asc_1800239A0; "<"
0x180006e65  jmp     short loc_180006E6E
0x180006e67  lea     r8, asc_180023998; ">"
0x180006e6e  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180006e73  test    ebx, ebx
0x180006e75  js      short loc_180006E8E
0x180006e77  cmp     ebp, 1
0x180006e7a  jnz     short loc_180006E8E
0x180006e7c  movsxd  rcx, ebx
0x180006e7f  sub     [r14+rcx*8+4], ebp
0x180006e84  jnz     short loc_180006E8E
0x180006e86  mov     dword ptr [r14+rcx*8], 0
0x180006e8e  mov     rbx, [rsp+38h+arg_8]
0x180006e93  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006e9a  mov     rbp, [rsp+38h+arg_10]
0x180006e9f  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x180006ea6  add     rsp, 20h
0x180006eaa  pop     r14
0x180006eac  pop     rdi
0x180006ead  pop     rsi
0x180006eae  retn
```
