# jsonValidFunc

- ea: `0x180053800`
- end: `0x180053979`
- name: `jsonValidFunc`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180002cf8`
- `0x18004f598`
- `0x180050b30`
- `0x180050b6c`
- `0x180053800`
- `0x180053b3c`
- `0x18009a310`
- `0x18009b4ec`
- `0x1800ab280`
- `0x1800ae6c0`
- `0x1800ae720`
- `0x1800b58d0`

## string_xrefs

- `0x18005383f`: `FLAGS parameter to json_valid() must be between 1 and 15`

## pseudocode

```c
__int64 __fastcall jsonValidFunc(_DWORD *a1, int a2, __int64 *a3)
{
  __int64 v4; // rdi
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rbx
  _BYTE *v10; // rax
  _BYTE *v11; // rbp
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // [rsp+30h] [rbp-88h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-80h]

  LOBYTE(v4) = 1;
  if ( a2 == 2 )
  {
    v4 = sqlite3VdbeIntValue(a3[1]);
    if ( (unsigned __int64)(v4 - 1) > 0xE )
    {
      v7 = *(_QWORD *)a1;
      a1[9] = 1;
      LOBYTE(v6) = 1;
      return sqlite3VdbeMemSetStr(v7, "FLAGS parameter to json_valid() must be between 1 and 15", -1, v6, -1);
    }
  }
  result = *(_WORD *)(*a3 + 20) & 0x3F;
  if ( *((_BYTE *)qword_1800FE430 + result) == 4 )
  {
    if ( (unsigned int)jsonFuncArgMightBeBinary(*a3) )
    {
      if ( (v4 & 4) != 0 )
      {
        v9 = 1;
      }
      else
      {
        v9 = 0;
        if ( (v4 & 8) != 0 )
        {
          memset_0(&v14, 0, 0x48u);
          v12 = sqlite3_value_blob(*a3);
          v13 = *a3;
          v14 = v12;
          v15 = sqlite3_value_bytes(v13);
          LOBYTE(v9) = (unsigned int)jsonbValidityCheck(&v14, 0, v15, 1) == 0;
        }
      }
      goto LABEL_21;
    }
  }
  else if ( *((_BYTE *)qword_1800FE430 + result) == 5 )
  {
    return result;
  }
  v9 = 0;
  if ( (v4 & 3) != 0 )
  {
    v10 = (_BYTE *)jsonParseFuncArg(a1, *a3, 2);
    v11 = v10;
    if ( v10 )
    {
      if ( v10[47] )
      {
        sqlite3_result_error_nomem(a1);
      }
      else if ( !v10[46] && ((v4 & 2) != 0 || !v10[49]) )
      {
        v9 = 1;
      }
      jsonParseFree(v11);
    }
    else
    {
      sqlite3_result_error_nomem(a1);
    }
  }
LABEL_21:
  result = *(_QWORD *)a1;
  if ( (*(_WORD *)(*(_QWORD *)a1 + 20LL) & 0x9000) != 0 )
    return vdbeReleaseAndSetInt64(*(_QWORD *)a1, v9);
  *(_QWORD *)result = v9;
  *(_WORD *)(result + 20) = 4;
  return result;
}

```

## disassembly

```asm
0x180053800  push    rbx
0x180053802  push    rbp
0x180053803  push    rsi
0x180053804  push    rdi
0x180053805  push    r12
0x180053807  push    r13
0x180053809  push    r14
0x18005380b  sub     rsp, 80h
0x180053812  mov     r12d, 1
0x180053818  mov     r14, r8
0x18005381b  mov     dil, r12b
0x18005381e  mov     rsi, rcx
0x180053821  cmp     edx, 2
0x180053824  jnz     short loc_180053860
0x180053826  mov     rcx, [r8+8]
0x18005382a  call    sqlite3VdbeIntValue
0x18005382f  mov     rdi, rax
0x180053832  lea     rdx, [rax-1]
0x180053836  cmp     rdx, 0Eh
0x18005383a  jbe     short loc_180053860
0x18005383c  mov     rcx, [rsi]
0x18005383f  lea     rdx, aFlagsParameter; "FLAGS parameter to json_valid() must be"...
0x180053846  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005384a  mov     [rsi+24h], r12d
0x18005384e  mov     r9b, r12b
0x180053851  mov     [rsp+0B8h+var_98], r8
0x180053856  call    sqlite3VdbeMemSetStr
0x18005385b  jmp     loc_180053967
0x180053860  mov     rdx, [r14]
0x180053863  lea     rcx, qword_1800FE430
0x18005386a  mov     r13d, 4
0x180053870  movzx   eax, word ptr [rdx+14h]
0x180053874  and     eax, 3Fh
0x180053877  movzx   ecx, byte ptr [rax+rcx]
0x18005387b  sub     ecx, r13d
0x18005387e  jz      short loc_1800538BF
0x180053880  cmp     ecx, r12d
0x180053883  jz      loc_180053967
0x180053889  xor     ebx, ebx
0x18005388b  test    dil, 3
0x18005388f  jz      loc_180053944
0x180053895  mov     rdx, [r14]
0x180053898  lea     r8d, [rbx+2]
0x18005389c  mov     rcx, rsi
0x18005389f  call    jsonParseFuncArg
0x1800538a4  mov     rbp, rax
0x1800538a7  test    rax, rax
0x1800538aa  jz      loc_18005393C
0x1800538b0  cmp     [rax+2Fh], bl
0x1800538b3  jz      short loc_18005391F
0x1800538b5  mov     rcx, rsi
0x1800538b8  call    sqlite3_result_error_nomem
0x1800538bd  jmp     short loc_180053932
0x1800538bf  mov     rcx, rdx
0x1800538c2  call    jsonFuncArgMightBeBinary
0x1800538c7  test    eax, eax
0x1800538c9  jz      short loc_180053889
0x1800538cb  test    r13b, dil
0x1800538ce  jz      short loc_1800538D5
0x1800538d0  mov     rbx, r12
0x1800538d3  jmp     short loc_180053944
0x1800538d5  xor     ebx, ebx
0x1800538d7  test    dil, 8
0x1800538db  jz      short loc_180053944
0x1800538dd  xor     edx, edx; Val
0x1800538df  lea     r8d, [rbx+48h]; Size
0x1800538e3  lea     rcx, [rsp+0B8h+var_88]; void *
0x1800538e8  call    memset_0
0x1800538ed  mov     rcx, [r14]
0x1800538f0  call    sqlite3_value_blob
0x1800538f5  mov     rcx, [r14]
0x1800538f8  mov     [rsp+0B8h+var_88], rax
0x1800538fd  call    sqlite3_value_bytes
0x180053902  mov     r9d, r12d
0x180053905  mov     [rsp+0B8h+var_80], eax
0x180053909  mov     r8d, eax
0x18005390c  lea     rcx, [rsp+0B8h+var_88]
0x180053911  xor     edx, edx
0x180053913  call    jsonbValidityCheck
0x180053918  test    eax, eax
0x18005391a  setz    bl
0x18005391d  jmp     short loc_180053944
0x18005391f  cmp     [rax+2Eh], bl
0x180053922  jnz     short loc_180053932
0x180053924  test    dil, 2
0x180053928  jnz     short loc_18005392F
0x18005392a  cmp     [rax+31h], bl
0x18005392d  jnz     short loc_180053932
0x18005392f  mov     rbx, r12
0x180053932  mov     rcx, rbp
0x180053935  call    jsonParseFree
0x18005393a  jmp     short loc_180053944
0x18005393c  mov     rcx, rsi
0x18005393f  call    sqlite3_result_error_nomem
0x180053944  mov     rax, [rsi]
0x180053947  mov     ecx, 9000h
0x18005394c  test    [rax+14h], cx
0x180053950  jz      short loc_18005395F
0x180053952  mov     rdx, rbx
0x180053955  mov     rcx, rax
0x180053958  call    vdbeReleaseAndSetInt64
0x18005395d  jmp     short loc_180053967
0x18005395f  mov     [rax], rbx
0x180053962  mov     [rax+14h], r13w
0x180053967  add     rsp, 80h
0x18005396e  pop     r14
0x180053970  pop     r13
0x180053972  pop     r12
0x180053974  pop     rdi
0x180053975  pop     rsi
0x180053976  pop     rbp
0x180053977  pop     rbx
0x180053978  retn
```
