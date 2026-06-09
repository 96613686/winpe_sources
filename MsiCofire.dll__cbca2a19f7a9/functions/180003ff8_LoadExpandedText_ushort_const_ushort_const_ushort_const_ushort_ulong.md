# LoadExpandedText(ushort const *,ushort const *,ushort const *,ushort *,ulong)

- ea: `0x180003ff8`
- end: `0x180004255`
- name: `?LoadExpandedText@@YAJPEBG00PEAGK@Z`
- size: `605`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800043d8`

## callees

- `0x180002590`
- `0x180003ff8`
- `0x18000434c`
- `0x180007040`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000418e`
- `msvcrt!wcsrchr` at `0x18000418e`
- `KERNEL32!HeapFree` at `0x180004229`
- `KERNEL32!HeapFree` at `0x180004229`
- `KERNEL32!GetLastError` at `0x18000409a`
- `KERNEL32!GetLastError` at `0x1800040c9`
- `KERNEL32!GetLastError` at `0x18000409a`
- `KERNEL32!GetLastError` at `0x1800040c9`
- `KERNEL32!HeapAlloc` at `0x180004100`
- `KERNEL32!HeapAlloc` at `0x180004100`
- `KERNEL32!GetProcessHeap` at `0x1800040f2`
- `KERNEL32!GetProcessHeap` at `0x18000421b`
- `KERNEL32!GetProcessHeap` at `0x1800040f2`
- `KERNEL32!GetProcessHeap` at `0x18000421b`
- `USER32!LoadStringW` at `0x180004090`
- `USER32!LoadStringW` at `0x180004090`

## string_xrefs

- `0x180004045`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x18000420f`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall LoadExpandedText(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v7; // r14
  int v8; // r9d
  unsigned int v9; // ebx
  signed int LastError; // eax
  __int64 v11; // rbp
  signed int v12; // eax
  unsigned __int64 v13; // rdi
  HANDLE ProcessHeap; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  __int64 v17; // rax
  wchar_t *v18; // rdx
  wchar_t *v19; // rcx
  wchar_t *v20; // rax
  wchar_t *v21; // r9
  int v22; // eax
  HANDLE v23; // rax
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-858h] BYREF

  v7 = a1;
  if ( a1 )
  {
    if ( !a2 )
    {
      v8 = 85;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v8 = 86;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v8 = 87;
      goto LABEL_3;
    }
    if ( !LoadStringW(g_hInstance, 0x3F5u, Buffer, 1024) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v8 = 95;
      goto LABEL_4;
    }
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    if ( !(_DWORD)v11 )
    {
      v12 = GetLastError();
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      v8 = 99;
      goto LABEL_4;
    }
    v13 = (unsigned int)(v11 + 1);
    ProcessHeap = GetProcessHeap();
    v15 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2 * v13);
    v16 = v15;
    if ( !v15 )
    {
      v9 = -2147024882;
      v8 = 102;
      goto LABEL_4;
    }
    if ( (_DWORD)v11 == -1 )
    {
      v9 = -2147024809;
    }
    else if ( v13 <= 0x7FFFFFFF )
    {
      v17 = 2147483646;
      v18 = v16;
      do
      {
        if ( !v17 )
          break;
        if ( !*v7 )
          break;
        *v18++ = *v7++;
        --v17;
        --v13;
      }
      while ( v13 );
      v19 = v18 - 1;
      v9 = v13 == 0 ? 0x8007007A : 0;
      if ( v13 )
        v19 = v18;
      *v19 = 0;
      if ( v13 )
      {
        v20 = wcsrchr(v16, 0x5Cu);
        if ( v20 && v20 - v16 < (int)v11 - 1 )
        {
          v21 = v20 + 1;
          *v20 = 0;
        }
        else
        {
          v21 = v16;
        }
        v22 = StringCchPrintfW(a4, 0x800u, Buffer, v21, v16, a2, a3);
        v9 = v22;
        if ( v22 < 0 )
          DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadExpandedText", 129, v22);
        goto LABEL_41;
      }
    }
    else
    {
      v9 = -2147024809;
      *v15 = 0;
    }
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadExpandedText", 105, v9);
LABEL_41:
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v16);
    return v9;
  }
  v8 = 84;
LABEL_3:
  v9 = -2147024809;
LABEL_4:
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadExpandedText", v8, v9);
  return v9;
}

```

## disassembly

```asm
0x180003ff8  push    rbx
0x180003ffa  push    rbp
0x180003ffb  push    rsi
0x180003ffc  push    rdi
0x180003ffd  push    r12
0x180003fff  push    r13
0x180004001  push    r14
0x180004003  push    r15
0x180004005  sub     rsp, 858h
0x18000400c  mov     rax, cs:__security_cookie
0x180004013  xor     rax, rsp
0x180004016  mov     [rsp+898h+var_58], rax
0x18000401e  xor     edi, edi
0x180004020  mov     r13, r9
0x180004023  mov     r12, r8
0x180004026  mov     r15, rdx
0x180004029  mov     r14, rcx
0x18000402c  test    rcx, rcx
0x18000402f  jnz     short loc_180004058
0x180004031  lea     r9d, [rcx+54h]
0x180004035  mov     ebx, 80070057h
0x18000403a  lea     r8, aLoadexpandedte; "LoadExpandedText"
0x180004041  mov     dword ptr [rsp+898h+var_878], ebx
0x180004045  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x18000404c  xor     ecx, ecx; Level
0x18000404e  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180004053  jmp     loc_18000422F
0x180004058  test    r15, r15
0x18000405b  jnz     short loc_180004063
0x18000405d  lea     r9d, [r15+55h]
0x180004061  jmp     short loc_180004035
0x180004063  test    r12, r12
0x180004066  jnz     short loc_18000406F
0x180004068  lea     r9d, [r12+56h]
0x18000406d  jmp     short loc_180004035
0x18000406f  test    r13, r13
0x180004072  jnz     short loc_18000407A
0x180004074  lea     r9d, [r13+57h]
0x180004078  jmp     short loc_180004035
0x18000407a  mov     rcx, cs:g_hInstance; hInstance
0x180004081  lea     r8, [rsp+898h+Buffer]; lpBuffer
0x180004086  mov     r9d, 400h; cchBufferMax
0x18000408c  lea     edx, [r9-0Bh]; uID
0x180004090  call    cs:__imp_LoadStringW
0x180004096  test    eax, eax
0x180004098  jnz     short loc_1800040B7
0x18000409a  call    cs:__imp_GetLastError
0x1800040a0  mov     ebx, eax
0x1800040a2  test    eax, eax
0x1800040a4  jle     short loc_1800040AF
0x1800040a6  movzx   ebx, ax
0x1800040a9  or      ebx, 80070000h
0x1800040af  mov     r9d, 5Fh ; '_'
0x1800040b5  jmp     short loc_18000403A
0x1800040b7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800040bb  inc     rbp
0x1800040be  cmp     [r14+rbp*2], di
0x1800040c3  jnz     short loc_1800040BB
0x1800040c5  test    ebp, ebp
0x1800040c7  jnz     short loc_1800040E9
0x1800040c9  call    cs:__imp_GetLastError
0x1800040cf  mov     ebx, eax
0x1800040d1  test    eax, eax
0x1800040d3  jle     short loc_1800040DE
0x1800040d5  movzx   ebx, ax
0x1800040d8  or      ebx, 80070000h
0x1800040de  mov     r9d, 63h ; 'c'
0x1800040e4  jmp     loc_18000403A
0x1800040e9  lea     eax, [rbp+1]
0x1800040ec  mov     edi, eax
0x1800040ee  lea     rbx, [rax+rax]
0x1800040f2  call    cs:__imp_GetProcessHeap
0x1800040f8  mov     r8, rbx; dwBytes
0x1800040fb  xor     edx, edx; dwFlags
0x1800040fd  mov     rcx, rax; hHeap
0x180004100  call    cs:__imp_HeapAlloc
0x180004106  xor     r8d, r8d
0x180004109  mov     rsi, rax
0x18000410c  test    rax, rax
0x18000410f  jnz     short loc_18000411F
0x180004111  mov     ebx, 8007000Eh
0x180004116  lea     r9d, [rax+66h]
0x18000411a  jmp     loc_18000403A
0x18000411f  test    rdi, rdi
0x180004122  jz      loc_1800041EE
0x180004128  cmp     rdi, 7FFFFFFFh
0x18000412f  jbe     short loc_18000413B
0x180004131  mov     ebx, 80070057h
0x180004136  jmp     loc_1800041F8
0x18000413b  mov     eax, 7FFFFFFEh
0x180004140  mov     rdx, rsi
0x180004143  test    rax, rax
0x180004146  jz      short loc_180004165
0x180004148  movzx   ecx, word ptr [r14]
0x18000414c  test    cx, cx
0x18000414f  jz      short loc_180004165
0x180004151  mov     [rdx], cx
0x180004154  add     r14, 2
0x180004158  add     rdx, 2
0x18000415c  dec     rax
0x18000415f  sub     rdi, 1
0x180004163  jnz     short loc_180004143
0x180004165  mov     rax, rdi
0x180004168  lea     rcx, [rdx-2]
0x18000416c  neg     rax
0x18000416f  sbb     ebx, ebx
0x180004171  not     ebx
0x180004173  and     ebx, 8007007Ah
0x180004179  test    rdi, rdi
0x18000417c  cmovnz  rcx, rdx
0x180004180  mov     [rcx], r8w
0x180004184  jz      short loc_1800041FC
0x180004186  mov     edx, 5Ch ; '\'; Ch
0x18000418b  mov     rcx, rsi; Str
0x18000418e  call    cs:__imp_wcsrchr
0x180004194  test    rax, rax
0x180004197  jz      short loc_1800041B8
0x180004199  mov     r8, rax
0x18000419c  lea     ecx, [rbp-1]
0x18000419f  sub     r8, rsi
0x1800041a2  movsxd  rdx, ecx
0x1800041a5  sar     r8, 1
0x1800041a8  cmp     r8, rdx
0x1800041ab  jge     short loc_1800041B8
0x1800041ad  xor     ecx, ecx
0x1800041af  lea     r9, [rax+2]
0x1800041b3  mov     [rax], cx
0x1800041b6  jmp     short loc_1800041BB
0x1800041b8  mov     r9, rsi
0x1800041bb  mov     [rsp+898h+var_868], r12
0x1800041c0  lea     r8, [rsp+898h+Buffer]; unsigned __int16 *
0x1800041c5  mov     [rsp+898h+var_870], r15
0x1800041ca  mov     edx, 800h; unsigned __int64
0x1800041cf  mov     rcx, r13; unsigned __int16 *
0x1800041d2  mov     [rsp+898h+var_878], rsi
0x1800041d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800041dc  mov     ebx, eax
0x1800041de  test    eax, eax
0x1800041e0  jns     short loc_18000421B
0x1800041e2  mov     dword ptr [rsp+898h+var_878], eax
0x1800041e6  mov     r9d, 81h
0x1800041ec  jmp     short loc_180004206
0x1800041ee  mov     ebx, 80070057h
0x1800041f3  test    rdi, rdi
0x1800041f6  jz      short loc_1800041FC
0x1800041f8  mov     [rax], r8w
0x1800041fc  mov     dword ptr [rsp+898h+var_878], ebx
0x180004200  mov     r9d, 69h ; 'i'
0x180004206  lea     r8, aLoadexpandedte; "LoadExpandedText"
0x18000420d  xor     ecx, ecx; Level
0x18000420f  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180004216  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000421b  call    cs:__imp_GetProcessHeap
0x180004221  mov     r8, rsi; lpMem
0x180004224  xor     edx, edx; dwFlags
0x180004226  mov     rcx, rax; hHeap
0x180004229  call    cs:__imp_HeapFree
0x18000422f  mov     eax, ebx
0x180004231  mov     rcx, [rsp+898h+var_58]
0x180004239  xor     rcx, rsp; StackCookie
0x18000423c  call    __security_check_cookie
0x180004241  add     rsp, 858h
0x180004248  pop     r15
0x18000424a  pop     r14
0x18000424c  pop     r13
0x18000424e  pop     r12
0x180004250  pop     rdi
0x180004251  pop     rsi
0x180004252  pop     rbp
0x180004253  pop     rbx
0x180004254  retn
```
