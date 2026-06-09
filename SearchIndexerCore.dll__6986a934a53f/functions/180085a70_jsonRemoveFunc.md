# jsonRemoveFunc

- ea: `0x180085a70`
- end: `0x180085b49`
- name: `jsonRemoveFunc`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180024b60`
- `0x180082760`
- `0x180084730`
- `0x180085450`
- `0x18008548c`
- `0x180085a70`
- `0x180085f74`
- `0x18009d650`

## string_xrefs

- `0x180085b0e`: `malformed JSON`

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
0x180085a70  cmp     edx, 1
0x180085a73  jl      locret_180085B48
0x180085a79  push    rbx
0x180085a7a  push    rbp
0x180085a7b  push    rsi
0x180085a7c  push    rdi
0x180085a7d  push    r14
0x180085a7f  push    r15
0x180085a81  sub     rsp, 28h
0x180085a85  mov     r15, r8
0x180085a88  mov     r14d, edx
0x180085a8b  xor     r8d, r8d
0x180085a8e  mov     rbx, rcx
0x180085a91  cmp     edx, 1
0x180085a94  mov     rdx, [r15]
0x180085a97  setnle  r8b
0x180085a9b  call    jsonParseFuncArg
0x180085aa0  mov     rdi, rax
0x180085aa3  test    rax, rax
0x180085aa6  jz      loc_180085B3C
0x180085aac  mov     ebp, 1
0x180085ab1  cmp     ebp, r14d
0x180085ab4  jge     short loc_180085B29
0x180085ab6  movsxd  rcx, ebp
0x180085ab9  mov     dl, 1
0x180085abb  mov     rcx, [r15+rcx*8]
0x180085abf  call    sqlite3ValueText
0x180085ac4  mov     rsi, rax
0x180085ac7  test    rax, rax
0x180085aca  jz      short loc_180085B34
0x180085acc  cmp     byte ptr [rax], 24h ; '$'
0x180085acf  jnz     short loc_180085B1C
0x180085ad1  lea     r8, [rax+1]
0x180085ad5  cmp     byte ptr [r8], 0
0x180085ad9  jz      short loc_180085B34
0x180085adb  xor     r9d, r9d
0x180085ade  mov     byte ptr [rdi+33h], 1
0x180085ae2  xor     edx, edx
0x180085ae4  mov     dword ptr [rdi+34h], 0
0x180085aeb  mov     rcx, rdi
0x180085aee  call    jsonLookupStep
0x180085af3  lea     ecx, [rax+3]
0x180085af6  test    ecx, 0FFFFFFFDh
0x180085afc  jz      short loc_180085B02
0x180085afe  inc     ebp
0x180085b00  jmp     short loc_180085AB1
0x180085b02  mov     rcx, rbx
0x180085b05  cmp     eax, 0FFFFFFFDh
0x180085b08  jz      short loc_180085B1F
0x180085b0a  or      r8d, 0FFFFFFFFh
0x180085b0e  lea     rdx, aMalformedJson; "malformed JSON"
0x180085b15  call    sqlite3_result_error
0x180085b1a  jmp     short loc_180085B34
0x180085b1c  mov     rcx, rbx
0x180085b1f  mov     rdx, rsi
0x180085b22  call    jsonBadPathError
0x180085b27  jmp     short loc_180085B34
0x180085b29  mov     rdx, rdi
0x180085b2c  mov     rcx, rbx
0x180085b2f  call    jsonReturnParse
0x180085b34  mov     rcx, rdi
0x180085b37  call    jsonParseFree
0x180085b3c  add     rsp, 28h
0x180085b40  pop     r15
0x180085b42  pop     r14
0x180085b44  pop     rdi
0x180085b45  pop     rsi
0x180085b46  pop     rbp
0x180085b47  pop     rbx
0x180085b48  retn
```
