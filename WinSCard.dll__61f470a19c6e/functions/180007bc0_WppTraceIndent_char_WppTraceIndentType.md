# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x180007bc0`
- end: `0x180007eb3`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `76`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x18000396c`
- `0x18000534c`
- `0x1800054a4`
- `0x180005898`
- `0x180005de0`
- `0x18000605c`
- `0x180006400`
- `0x180006910`
- `0x180006bf0`
- `0x180006c80`
- `0x180007940`
- `0x180007f40`
- `0x180008d20`
- `0x18000d554`
- `0x18000dab0`
- `0x18000ebe0`
- `0x18000f270`
- `0x180010298`
- `0x1800107a8`
- `0x1800108f0`
- `0x180010e74`
- `0x180011244`
- `0x180011318`
- `0x1800114e0`
- `0x180012878`
- `0x180012a78`
- `0x180012c10`
- `0x18001326c`
- `0x180013d34`
- `0x1800151b0`
- `0x180015280`
- `0x180015468`
- `0x1800157d8`
- `0x180015e24`
- `0x180016040`
- `0x180016788`
- `0x180016a4c`
- `0x180016d20`
- `0x1800170f8`
- `0x180017580`
- `0x1800176a0`
- `0x180017ac0`
- `0x180017b70`
- `0x180018b48`
- `0x1800190cc`
- `0x1800193b8`
- `0x180019b80`
- `0x180019f1c`
- `0x18001a5c4`

## callees

- `0x180006890`
- `0x180007bc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bcc`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  int v6; // r10d
  DWORD v7; // r9d
  unsigned int v8; // eax
  int v9; // r8d
  bool v10; // zf
  int v11; // r11d
  char *result; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  char *v15; // rcx
  const char *v16; // r8
  __int64 v17; // rax
  const char *v18; // r8
  __int64 v19; // rax
  const char *v20; // r8
  __int64 v21; // rcx
  int v22; // edi
  int v23; // r11d

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  v7 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180045874 = 0;
    goto LABEL_15;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v8 = 0;
    v9 = -1;
    while ( 1 )
    {
      v10 = v8 == 32;
      if ( v8 >= 0x20 )
        break;
      v5 = (char *)(int)v8;
      v4 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v8);
      if ( (_DWORD)v4 == v7 )
      {
        v6 = v8;
        `WppTraceIndent'::`2'::idxCurrentThread = v8;
        v10 = v8 == 32;
        break;
      }
      if ( v9 == -1 && !(_DWORD)v4 )
        v9 = v8;
      ++v8;
    }
    if ( v10 )
    {
      if ( v9 == -1 )
      {
        v6 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_50;
      }
      v6 = v9;
      `WppTraceIndent'::`2'::idxCurrentThread = v9;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9) = v7;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9 + 1) = 0;
    }
  }
  if ( v6 < 0 )
  {
LABEL_50:
    v11 = 0;
    goto LABEL_18;
  }
LABEL_15:
  if ( !a2 )
    ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v6 + 1);
  v11 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v6 + 1);
LABEL_18:
  result = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v22 = 1;
    if ( v11 >= 1 )
    {
      do
      {
        result = (char *)StringCbCatA(v5, v4, "..");
        if ( (_DWORD)result )
          break;
        ++v22;
      }
      while ( v22 <= v23 );
    }
  }
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v13 = 256;
      result = &`WppTraceIndent'::`2'::szIndentPrefix;
      while ( *result )
      {
        ++result;
        if ( !--v13 )
          goto LABEL_31;
      }
      v17 = 2147483646;
      v15 = (char *)&`wil::SetLastError'::`5'::depth - v13;
      v18 = "<";
      do
      {
        if ( !v17 )
          break;
        if ( !*v18 )
          break;
        *v15++ = *v18++;
        --v17;
        --v13;
      }
      while ( v13 );
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_31;
      v13 = 256;
      result = &`WppTraceIndent'::`2'::szIndentPrefix;
      while ( *result )
      {
        ++result;
        if ( !--v13 )
          goto LABEL_31;
      }
      v14 = 2147483646;
      v15 = (char *)&`wil::SetLastError'::`5'::depth - v13;
      v16 = " ";
      do
      {
        if ( !v14 )
          break;
        if ( !*v16 )
          break;
        *v15++ = *v16++;
        --v14;
        --v13;
      }
      while ( v13 );
    }
  }
  else
  {
    v13 = 256;
    result = &`WppTraceIndent'::`2'::szIndentPrefix;
    while ( *result )
    {
      ++result;
      if ( !--v13 )
        goto LABEL_31;
    }
    v19 = 2147483646;
    v15 = (char *)&`wil::SetLastError'::`5'::depth - v13;
    v20 = ">";
    do
    {
      if ( !v19 )
        break;
      if ( !*v20 )
        break;
      *v15++ = *v20++;
      --v19;
      --v13;
    }
    while ( v13 );
  }
  result = v15 - 1;
  if ( v13 )
    result = v15;
  *result = 0;
LABEL_31:
  if ( v6 >= 0 && a2 == 1 )
  {
    result = (char *)v6;
    WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
    v21 = 8LL * v6;
    v10 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v21 + 4))-- == 1;
    if ( v10 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v21) = 0;
  }
  else
  {
    WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  }
  return result;
}

```

## disassembly

```asm
0x180007bc0  mov     [rsp+arg_10], rbx
0x180007bc5  push    rsi
0x180007bc6  sub     rsp, 20h
0x180007bca  mov     ebx, edx
0x180007bcc  call    cs:__imp_GetCurrentThreadId
0x180007bd2  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007bd9  lea     rsi, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180007be0  mov     r9d, eax
0x180007be3  cmp     r10d, 0FFFFFFFFh
0x180007be7  jz      loc_180007CFA
0x180007bed  cmp     r10d, 0FFFFFFFEh
0x180007bf1  jz      short loc_180007BF9
0x180007bf3  cmp     [rsi+r10*8], eax
0x180007bf7  jz      short loc_180007C35
0x180007bf9  xor     eax, eax
0x180007bfb  mov     r8d, 0FFFFFFFFh
0x180007c01  cmp     eax, 20h ; ' '
0x180007c04  jnb     short loc_180007C2F
0x180007c06  movsxd  rcx, eax; char *
0x180007c09  mov     edx, [rsi+rcx*8]; unsigned __int64
0x180007c0c  cmp     edx, r9d
0x180007c0f  jz      short loc_180007C23
0x180007c11  cmp     r8d, 0FFFFFFFFh
0x180007c15  jz      short loc_180007C1B
0x180007c17  inc     eax
0x180007c19  jmp     short loc_180007C01
0x180007c1b  test    edx, edx
0x180007c1d  cmovz   r8d, eax
0x180007c21  jmp     short loc_180007C17
0x180007c23  mov     r10d, eax
0x180007c26  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007c2c  cmp     eax, 20h ; ' '
0x180007c2f  jz      loc_180007E1F
0x180007c35  test    r10d, r10d
0x180007c38  js      loc_180007DD2
0x180007c3e  movsxd  rax, r10d
0x180007c41  test    ebx, ebx
0x180007c43  jz      loc_180007E11
0x180007c49  mov     r11d, [rsi+rax*8+4]
0x180007c4e  mov     rax, cs:WPP_GLOBAL_Control
0x180007c55  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180007c5c  test    byte ptr [rax+1Ch], 2
0x180007c60  jnz     loc_180007E79
0x180007c66  lea     r11, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180007c6d  mov     ecx, ebx
0x180007c6f  test    ebx, ebx
0x180007c71  jz      loc_180007D68
0x180007c77  sub     ecx, 1
0x180007c7a  jz      loc_180007D17
0x180007c80  cmp     ecx, 1
0x180007c83  jnz     short loc_180007CDF
0x180007c85  mov     edx, 100h
0x180007c8a  mov     rax, r11
0x180007c8d  cmp     byte ptr [rax], 0
0x180007c90  jnz     loc_180007E43
0x180007c96  lea     rcx, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007c9d  mov     eax, 7FFFFFFEh
0x180007ca2  sub     rcx, rdx
0x180007ca5  lea     r8, asc_1800382C8; " "
0x180007cac  test    rdx, rdx
0x180007caf  jz      short loc_180007CD1
0x180007cb1  test    rax, rax
0x180007cb4  jz      short loc_180007CD1
0x180007cb6  movzx   r9d, byte ptr [r8]
0x180007cba  test    r9b, r9b
0x180007cbd  jz      short loc_180007CD1
0x180007cbf  mov     [rcx], r9b
0x180007cc2  inc     r8
0x180007cc5  inc     rcx
0x180007cc8  dec     rax
0x180007ccb  sub     rdx, 1
0x180007ccf  jnz     short loc_180007CB1
0x180007cd1  test    rdx, rdx
0x180007cd4  lea     rax, [rcx-1]
0x180007cd8  cmovnz  rax, rcx
0x180007cdc  mov     byte ptr [rax], 0
0x180007cdf  test    r10d, r10d
0x180007ce2  jns     loc_180007DDA
0x180007ce8  mov     cs:?WPP_pszIndent@@3PEADEA, r11; char * WPP_pszIndent
0x180007cef  mov     rbx, [rsp+28h+arg_10]
0x180007cf4  add     rsp, 20h
0x180007cf8  pop     rsi
0x180007cf9  retn
0x180007cfa  xor     r10d, r10d
0x180007cfd  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180007d04  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007d0b  mov     cs:dword_180045874, r10d
0x180007d12  jmp     loc_180007C3E
0x180007d17  mov     edx, 100h
0x180007d1c  mov     rax, r11
0x180007d1f  cmp     byte ptr [rax], 0
0x180007d22  jnz     loc_180007E55
0x180007d28  lea     rcx, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007d2f  mov     eax, 7FFFFFFEh
0x180007d34  sub     rcx, rdx
0x180007d37  lea     r8, asc_1800382CC; "<"
0x180007d3e  test    rdx, rdx
0x180007d41  jz      short loc_180007CD1
0x180007d43  test    rax, rax
0x180007d46  jz      short loc_180007CD1
0x180007d48  movzx   r9d, byte ptr [r8]
0x180007d4c  test    r9b, r9b
0x180007d4f  jz      short loc_180007CD1
0x180007d51  mov     [rcx], r9b
0x180007d54  inc     r8
0x180007d57  inc     rcx
0x180007d5a  dec     rax
0x180007d5d  sub     rdx, 1
0x180007d61  jnz     short loc_180007D43
0x180007d63  jmp     loc_180007CD1
0x180007d68  mov     edx, 100h
0x180007d6d  mov     rax, r11
0x180007d70  cmp     byte ptr [rax], 0
0x180007d73  jnz     loc_180007E67
0x180007d79  lea     rcx, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007d80  mov     eax, 7FFFFFFEh
0x180007d85  sub     rcx, rdx
0x180007d88  lea     r8, asc_1800382D0; ">"
0x180007d8f  test    rdx, rdx
0x180007d92  jz      loc_180007CD1
0x180007d98  test    rax, rax
0x180007d9b  jz      loc_180007CD1
0x180007da1  movzx   r9d, byte ptr [r8]
0x180007da5  test    r9b, r9b
0x180007da8  jz      loc_180007CD1
0x180007dae  mov     [rcx], r9b
0x180007db1  inc     r8
0x180007db4  inc     rcx
0x180007db7  dec     rax
0x180007dba  sub     rdx, 1
0x180007dbe  jnz     short loc_180007D98
0x180007dc0  jmp     loc_180007CD1
0x180007dc5  mov     r10d, 0FFFFFFFEh
0x180007dcb  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007dd2  xor     r11d, r11d
0x180007dd5  jmp     loc_180007C4E
0x180007dda  cmp     ebx, 1
0x180007ddd  jnz     loc_180007CE8
0x180007de3  movsxd  rax, r10d
0x180007de6  mov     cs:?WPP_pszIndent@@3PEADEA, r11; char * WPP_pszIndent
0x180007ded  lea     rcx, ds:0[rax*8]
0x180007df5  sub     [rcx+rsi+4], ebx
0x180007df9  jnz     loc_180007CEF
0x180007dff  mov     rbx, [rsp+28h+arg_10]
0x180007e04  mov     dword ptr [rcx+rsi], 0
0x180007e0b  add     rsp, 20h
0x180007e0f  pop     rsi
0x180007e10  retn
0x180007e11  inc     dword ptr [rsi+rax*8+4]
0x180007e15  mov     r11d, [rsi+rax*8+4]
0x180007e1a  jmp     loc_180007C4E
0x180007e1f  cmp     r8d, 0FFFFFFFFh
0x180007e23  jz      short loc_180007DC5
0x180007e25  movsxd  rax, r8d
0x180007e28  mov     r10d, r8d
0x180007e2b  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180007e32  mov     [rsi+rax*8], r9d
0x180007e36  mov     dword ptr [rsi+rax*8+4], 0
0x180007e3e  jmp     loc_180007C35
0x180007e43  inc     rax
0x180007e46  sub     rdx, 1
0x180007e4a  jnz     loc_180007C8D
0x180007e50  jmp     loc_180007CDF
0x180007e55  inc     rax
0x180007e58  sub     rdx, 1
0x180007e5c  jnz     loc_180007D1F
0x180007e62  jmp     loc_180007CDF
0x180007e67  inc     rax
0x180007e6a  sub     rdx, 1
0x180007e6e  jnz     loc_180007D70
0x180007e74  jmp     loc_180007CDF
0x180007e79  cmp     byte ptr [rax+19h], 5
0x180007e7d  jb      loc_180007C66
0x180007e83  mov     [rsp+28h+arg_8], rdi
0x180007e88  mov     edi, 1
0x180007e8d  cmp     r11d, edi
0x180007e90  jl      short loc_180007EA9
0x180007e92  lea     r8, asc_18003926C; ".."
0x180007e99  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180007e9e  test    eax, eax
0x180007ea0  jnz     short loc_180007EA9
0x180007ea2  inc     edi
0x180007ea4  cmp     edi, r11d
0x180007ea7  jle     short loc_180007E92
0x180007ea9  mov     rdi, [rsp+28h+arg_8]
0x180007eae  jmp     loc_180007C66
```
