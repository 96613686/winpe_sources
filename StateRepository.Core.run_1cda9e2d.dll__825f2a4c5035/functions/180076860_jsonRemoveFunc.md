# jsonRemoveFunc

- ea: `0x180076860`
- end: `0x180076939`
- name: `jsonRemoveFunc`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180028540`
- `0x1800734f0`
- `0x1800754f0`
- `0x180076240`
- `0x18007627c`
- `0x180076860`
- `0x180076d64`
- `0x18008f3f0`

## string_xrefs

- `0x1800768fe`: `malformed JSON`

## pseudocode

```c
void __fastcall jsonRemoveFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdi
  int i; // ebp
  _BYTE *v9; // rax
  int v10; // eax
  __int64 v11; // rcx

  if ( a2 >= 1 )
  {
    v7 = jsonParseFuncArg(a1, *a3, a2 > 1);
    if ( v7 )
    {
      for ( i = 1; i < a2; ++i )
      {
        LOBYTE(v6) = 1;
        v9 = (_BYTE *)sqlite3ValueText(a3[i], v6);
        if ( !v9 )
          goto LABEL_15;
        if ( *v9 != 36 )
        {
          v11 = a1;
LABEL_13:
          jsonBadPathError(v11);
          goto LABEL_15;
        }
        if ( !v9[1] )
          goto LABEL_15;
        *(_BYTE *)(v7 + 51) = 1;
        *(_DWORD *)(v7 + 52) = 0;
        v10 = jsonLookupStep(v7, 0, v9 + 1, 0);
        if ( ((v10 + 3) & 0xFFFFFFFD) == 0 )
        {
          v11 = a1;
          if ( v10 != -3 )
          {
            sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
            goto LABEL_15;
          }
          goto LABEL_13;
        }
      }
      jsonReturnParse(a1, v7);
LABEL_15:
      jsonParseFree(v7);
    }
  }
}

```

## disassembly

```asm
0x180076860  cmp     edx, 1
0x180076863  jl      locret_180076938
0x180076869  push    rbx
0x18007686a  push    rbp
0x18007686b  push    rsi
0x18007686c  push    rdi
0x18007686d  push    r14
0x18007686f  push    r15
0x180076871  sub     rsp, 28h
0x180076875  mov     r15, r8
0x180076878  mov     r14d, edx
0x18007687b  xor     r8d, r8d
0x18007687e  mov     rbx, rcx
0x180076881  cmp     edx, 1
0x180076884  mov     rdx, [r15]
0x180076887  setnle  r8b
0x18007688b  call    jsonParseFuncArg
0x180076890  mov     rdi, rax
0x180076893  test    rax, rax
0x180076896  jz      loc_18007692C
0x18007689c  mov     ebp, 1
0x1800768a1  cmp     ebp, r14d
0x1800768a4  jge     short loc_180076919
0x1800768a6  movsxd  rcx, ebp
0x1800768a9  mov     dl, 1
0x1800768ab  mov     rcx, [r15+rcx*8]
0x1800768af  call    sqlite3ValueText
0x1800768b4  mov     rsi, rax
0x1800768b7  test    rax, rax
0x1800768ba  jz      short loc_180076924
0x1800768bc  cmp     byte ptr [rax], 24h ; '$'
0x1800768bf  jnz     short loc_18007690C
0x1800768c1  lea     r8, [rax+1]
0x1800768c5  cmp     byte ptr [r8], 0
0x1800768c9  jz      short loc_180076924
0x1800768cb  xor     r9d, r9d
0x1800768ce  mov     byte ptr [rdi+33h], 1
0x1800768d2  xor     edx, edx
0x1800768d4  mov     dword ptr [rdi+34h], 0
0x1800768db  mov     rcx, rdi
0x1800768de  call    jsonLookupStep
0x1800768e3  lea     ecx, [rax+3]
0x1800768e6  test    ecx, 0FFFFFFFDh
0x1800768ec  jz      short loc_1800768F2
0x1800768ee  inc     ebp
0x1800768f0  jmp     short loc_1800768A1
0x1800768f2  mov     rcx, rbx
0x1800768f5  cmp     eax, 0FFFFFFFDh
0x1800768f8  jz      short loc_18007690F
0x1800768fa  or      r8d, 0FFFFFFFFh
0x1800768fe  lea     rdx, aMalformedJson; "malformed JSON"
0x180076905  call    sqlite3_result_error
0x18007690a  jmp     short loc_180076924
0x18007690c  mov     rcx, rbx
0x18007690f  mov     rdx, rsi
0x180076912  call    jsonBadPathError
0x180076917  jmp     short loc_180076924
0x180076919  mov     rdx, rdi
0x18007691c  mov     rcx, rbx
0x18007691f  call    jsonReturnParse
0x180076924  mov     rcx, rdi
0x180076927  call    jsonParseFree
0x18007692c  add     rsp, 28h
0x180076930  pop     r15
0x180076932  pop     r14
0x180076934  pop     rdi
0x180076935  pop     rsi
0x180076936  pop     rbp
0x180076937  pop     rbx
0x180076938  retn
```
