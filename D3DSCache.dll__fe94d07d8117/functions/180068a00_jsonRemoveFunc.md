# jsonRemoveFunc

- ea: `0x180068a00`
- end: `0x180068ad9`
- name: `jsonRemoveFunc`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180042dc4`
- `0x180065750`
- `0x1800676c0`
- `0x1800683e0`
- `0x18006841c`
- `0x180068a00`
- `0x180068f04`
- `0x180096df0`

## string_xrefs

- `0x180068a9e`: `malformed JSON`

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
0x180068a00  cmp     edx, 1
0x180068a03  jl      locret_180068AD8
0x180068a09  push    rbx
0x180068a0a  push    rbp
0x180068a0b  push    rsi
0x180068a0c  push    rdi
0x180068a0d  push    r14
0x180068a0f  push    r15
0x180068a11  sub     rsp, 28h
0x180068a15  mov     r15, r8
0x180068a18  mov     r14d, edx
0x180068a1b  xor     r8d, r8d
0x180068a1e  mov     rbx, rcx
0x180068a21  cmp     edx, 1
0x180068a24  mov     rdx, [r15]
0x180068a27  setnle  r8b
0x180068a2b  call    jsonParseFuncArg
0x180068a30  mov     rdi, rax
0x180068a33  test    rax, rax
0x180068a36  jz      loc_180068ACC
0x180068a3c  mov     ebp, 1
0x180068a41  cmp     ebp, r14d
0x180068a44  jge     short loc_180068AB9
0x180068a46  movsxd  rcx, ebp
0x180068a49  mov     dl, 1
0x180068a4b  mov     rcx, [r15+rcx*8]
0x180068a4f  call    sqlite3ValueText
0x180068a54  mov     rsi, rax
0x180068a57  test    rax, rax
0x180068a5a  jz      short loc_180068AC4
0x180068a5c  cmp     byte ptr [rax], 24h ; '$'
0x180068a5f  jnz     short loc_180068AAC
0x180068a61  lea     r8, [rax+1]
0x180068a65  cmp     byte ptr [r8], 0
0x180068a69  jz      short loc_180068AC4
0x180068a6b  xor     r9d, r9d
0x180068a6e  mov     byte ptr [rdi+33h], 1
0x180068a72  xor     edx, edx
0x180068a74  mov     dword ptr [rdi+34h], 0
0x180068a7b  mov     rcx, rdi
0x180068a7e  call    jsonLookupStep
0x180068a83  lea     ecx, [rax+3]
0x180068a86  test    ecx, 0FFFFFFFDh
0x180068a8c  jz      short loc_180068A92
0x180068a8e  inc     ebp
0x180068a90  jmp     short loc_180068A41
0x180068a92  mov     rcx, rbx
0x180068a95  cmp     eax, 0FFFFFFFDh
0x180068a98  jz      short loc_180068AAF
0x180068a9a  or      r8d, 0FFFFFFFFh
0x180068a9e  lea     rdx, aMalformedJson; "malformed JSON"
0x180068aa5  call    sqlite3_result_error
0x180068aaa  jmp     short loc_180068AC4
0x180068aac  mov     rcx, rbx
0x180068aaf  mov     rdx, rsi
0x180068ab2  call    jsonBadPathError
0x180068ab7  jmp     short loc_180068AC4
0x180068ab9  mov     rdx, rdi
0x180068abc  mov     rcx, rbx
0x180068abf  call    jsonReturnParse
0x180068ac4  mov     rcx, rdi
0x180068ac7  call    jsonParseFree
0x180068acc  add     rsp, 28h
0x180068ad0  pop     r15
0x180068ad2  pop     r14
0x180068ad4  pop     rdi
0x180068ad5  pop     rsi
0x180068ad6  pop     rbp
0x180068ad7  pop     rbx
0x180068ad8  retn
```
