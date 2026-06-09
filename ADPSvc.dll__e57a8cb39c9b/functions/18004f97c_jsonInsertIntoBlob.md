# jsonInsertIntoBlob

- ea: `0x18004f97c`
- end: `0x18004fb37`
- name: `jsonInsertIntoBlob`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180051320`
- `0x180051bd0`

## callees

- `0x180002cf8`
- `0x18004dd50`
- `0x18004dff4`
- `0x18004f658`
- `0x18004f97c`
- `0x18004fca4`
- `0x180050b30`
- `0x180050b6c`
- `0x180050e7c`
- `0x180051828`
- `0x180092290`
- `0x18009b4ec`
- `0x1800ab280`

## string_xrefs

- `0x18004faff`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonInsertIntoBlob(_DWORD *a1, int a2, __int64 *a3, int a4)
{
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // ebp
  int v10; // r12d
  int v11; // r14d
  __int64 *v12; // rdx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  _BYTE *v15; // rsi
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-98h] BYREF
  int v19; // [rsp+38h] [rbp-90h]

  memset_0(&v18, 0, 0x48u);
  result = jsonParseFuncArg(a1, *a3, a2 != 1);
  v8 = result;
  if ( result )
  {
    v9 = 0;
    v10 = a2 - 1;
    v11 = 1;
    if ( a2 - 1 <= 1 )
    {
LABEL_14:
      jsonReturnParse(a1, v8);
      return jsonParseFree(v8);
    }
    else
    {
      while ( 1 )
      {
        v12 = qword_1800FE430;
        v13 = a3[v11];
        if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v13 + 20) & 0x3F)) != 5 )
        {
          LOBYTE(v12) = 1;
          v14 = (_BYTE *)sqlite3ValueText(v13, v12);
          v15 = v14;
          if ( !v14 )
          {
            sqlite3_result_error_nomem(a1);
            return jsonParseFree(v8);
          }
          if ( *v14 != 36 )
            break;
          if ( (unsigned int)jsonFunctionArgToBlob(a1, a3[v11 + 1], &v18) )
          {
            jsonParseReset(&v18);
            return jsonParseFree(v8);
          }
          if ( v15[1] )
          {
            *(_BYTE *)(v8 + 51) = a4;
            *(_DWORD *)(v8 + 56) = v19;
            *(_QWORD *)(v8 + 64) = v18;
            *(_DWORD *)(v8 + 52) = 0;
            v9 = jsonLookupStep(v8, 0, v15 + 1, 0);
          }
          else
          {
            if ( ((a4 - 2) & 0xFFFFFFFD) == 0 )
              jsonBlobEdit(v8, 0, *(unsigned int *)(v8 + 8), v18, v19);
            v9 = 0;
          }
          jsonParseReset(&v18);
          if ( ((v9 + 3) & 0xFFFFFFFD) == 0 )
            break;
        }
        v11 += 2;
        if ( v11 >= v10 )
          goto LABEL_14;
      }
      jsonParseFree(v8);
      if ( v9 == -1 )
      {
        v17 = *(_QWORD *)a1;
        a1[9] = 1;
        LOBYTE(v16) = 1;
        return sqlite3VdbeMemSetStr(v17, "malformed JSON", -1, v16, -1);
      }
      else
      {
        return jsonBadPathError(a1, v15);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004f97c  mov     [rsp+arg_18], r9d
0x18004f981  push    rbx
0x18004f982  push    rbp
0x18004f983  push    rsi
0x18004f984  push    rdi
0x18004f985  push    r12
0x18004f987  push    r13
0x18004f989  push    r14
0x18004f98b  push    r15
0x18004f98d  sub     rsp, 88h
0x18004f994  mov     esi, edx
0x18004f996  mov     r13, r8
0x18004f999  xor     edx, edx; Val
0x18004f99b  mov     rdi, rcx
0x18004f99e  lea     rcx, [rsp+0C8h+var_98]; void *
0x18004f9a3  lea     r8d, [rdx+48h]; Size
0x18004f9a7  call    memset_0
0x18004f9ac  mov     rdx, [r13+0]
0x18004f9b0  xor     r8d, r8d
0x18004f9b3  cmp     esi, 1
0x18004f9b6  mov     rcx, rdi
0x18004f9b9  setnz   r8b
0x18004f9bd  call    jsonParseFuncArg
0x18004f9c2  mov     rbx, rax
0x18004f9c5  test    rax, rax
0x18004f9c8  jz      loc_18004FACF
0x18004f9ce  xor     ebp, ebp
0x18004f9d0  lea     r12d, [rsi-1]
0x18004f9d4  lea     r14d, [rbp+1]
0x18004f9d8  cmp     r12d, r14d
0x18004f9db  jle     loc_18004FABC
0x18004f9e1  movsxd  r15, r14d
0x18004f9e4  lea     rdx, qword_1800FE430
0x18004f9eb  mov     rcx, [r13+r15*8+0]
0x18004f9f0  movzx   eax, word ptr [rcx+14h]
0x18004f9f4  and     eax, 3Fh
0x18004f9f7  cmp     byte ptr [rax+rdx], 5
0x18004f9fb  jz      loc_18004FAAF
0x18004fa01  mov     dl, 1
0x18004fa03  call    sqlite3ValueText
0x18004fa08  mov     rsi, rax
0x18004fa0b  test    rax, rax
0x18004fa0e  jz      loc_18004FB2D
0x18004fa14  cmp     byte ptr [rax], 24h ; '$'
0x18004fa17  jnz     loc_18004FAEF
0x18004fa1d  mov     rdx, [r13+r15*8+8]
0x18004fa22  lea     r8, [rsp+0C8h+var_98]
0x18004fa27  mov     rcx, rdi
0x18004fa2a  call    jsonFunctionArgToBlob
0x18004fa2f  test    eax, eax
0x18004fa31  jnz     loc_18004FAE3
0x18004fa37  mov     eax, [rsp+0C8h+arg_18]
0x18004fa3e  lea     r8, [rsi+1]
0x18004fa42  cmp     byte ptr [r8], 0
0x18004fa46  jnz     short loc_18004FA71
0x18004fa48  add     eax, 0FFFFFFFEh
0x18004fa4b  test    eax, 0FFFFFFFDh
0x18004fa50  jnz     short loc_18004FA6D
0x18004fa52  mov     eax, [rsp+0C8h+var_90]
0x18004fa56  xor     edx, edx
0x18004fa58  mov     r9, [rsp+0C8h+var_98]
0x18004fa5d  mov     rcx, rbx
0x18004fa60  mov     r8d, [rbx+8]
0x18004fa64  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18004fa68  call    jsonBlobEdit
0x18004fa6d  xor     ebp, ebp
0x18004fa6f  jmp     short loc_18004FA9A
0x18004fa71  mov     [rbx+33h], al
0x18004fa74  xor     r9d, r9d
0x18004fa77  mov     eax, [rsp+0C8h+var_90]
0x18004fa7b  xor     edx, edx
0x18004fa7d  mov     [rbx+38h], eax
0x18004fa80  mov     rcx, rbx
0x18004fa83  mov     rax, [rsp+0C8h+var_98]
0x18004fa88  mov     [rbx+40h], rax
0x18004fa8c  mov     dword ptr [rbx+34h], 0
0x18004fa93  call    jsonLookupStep
0x18004fa98  mov     ebp, eax
0x18004fa9a  lea     rcx, [rsp+0C8h+var_98]
0x18004fa9f  call    jsonParseReset
0x18004faa4  lea     ecx, [rbp+3]
0x18004faa7  test    ecx, 0FFFFFFFDh
0x18004faad  jz      short loc_18004FAEF
0x18004faaf  add     r14d, 2
0x18004fab3  cmp     r14d, r12d
0x18004fab6  jl      loc_18004F9E1
0x18004fabc  mov     rdx, rbx
0x18004fabf  mov     rcx, rdi
0x18004fac2  call    jsonReturnParse
0x18004fac7  mov     rcx, rbx
0x18004faca  call    jsonParseFree
0x18004facf  add     rsp, 88h
0x18004fad6  pop     r15
0x18004fad8  pop     r14
0x18004fada  pop     r13
0x18004fadc  pop     r12
0x18004fade  pop     rdi
0x18004fadf  pop     rsi
0x18004fae0  pop     rbp
0x18004fae1  pop     rbx
0x18004fae2  retn
0x18004fae3  lea     rcx, [rsp+0C8h+var_98]
0x18004fae8  call    jsonParseReset
0x18004faed  jmp     short loc_18004FAC7
0x18004faef  mov     rcx, rbx
0x18004faf2  call    jsonParseFree
0x18004faf7  cmp     ebp, 0FFFFFFFFh
0x18004fafa  jnz     short loc_18004FB20
0x18004fafc  mov     rcx, [rdi]
0x18004faff  lea     rdx, aMalformedJson; "malformed JSON"
0x18004fb06  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004fb0a  mov     dword ptr [rdi+24h], 1
0x18004fb11  mov     r9b, 1
0x18004fb14  mov     [rsp+0C8h+var_A8], r8
0x18004fb19  call    sqlite3VdbeMemSetStr
0x18004fb1e  jmp     short loc_18004FACF
0x18004fb20  mov     rdx, rsi
0x18004fb23  mov     rcx, rdi
0x18004fb26  call    jsonBadPathError
0x18004fb2b  jmp     short loc_18004FACF
0x18004fb2d  mov     rcx, rdi
0x18004fb30  call    sqlite3_result_error_nomem
0x18004fb35  jmp     short loc_18004FAC7
```
