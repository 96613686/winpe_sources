# web::json::details::json_error_category_impl::message(int)

- ea: `0x180029b20`
- end: `0x180029d01`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002829c`
- `0x180029b20`

## string_xrefs

- `0x180029bef`: `Left-over characters in stream after parsing a JSON value`
- `0x180029baf`: `Malformed comment`
- `0x180029ccc`: `Malformed token`
- `0x180029c75`: `Unexpected token`
- `0x180029c55`: `Unknown json error`

## pseudocode

```c
__int64 __fastcall web::json::details::json_error_category_impl::message(__int64 a1, __int64 a2, int a3)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  const char *v8; // rdx
  __int64 v9; // r8
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d

  if ( a3 > 6 )
  {
    v10 = a3 - 7;
    if ( !v10 )
    {
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Malformed string literal";
      goto LABEL_25;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v9 = 15;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Malformed token";
      goto LABEL_26;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v9 = 17;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Mismatched braces";
      goto LABEL_26;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Nesting too deep";
      goto LABEL_26;
    }
    if ( v13 == 1 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Unexpected token";
      goto LABEL_26;
    }
    goto LABEL_19;
  }
  if ( a3 == 6 )
  {
    v9 = 25;
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    v8 = "Malformed numeric literal";
  }
  else
  {
    v4 = a3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            if ( v7 == 1 )
            {
              *(_OWORD *)a2 = 0;
              *(_QWORD *)(a2 + 16) = 0;
              *(_QWORD *)(a2 + 24) = 0;
              v8 = "Malformed object literal";
LABEL_25:
              v9 = 24;
              goto LABEL_26;
            }
LABEL_19:
            v9 = 18;
            *(_OWORD *)a2 = 0;
            *(_QWORD *)(a2 + 16) = 0;
            *(_QWORD *)(a2 + 24) = 0;
            v8 = "Unknown json error";
            goto LABEL_26;
          }
          v9 = 17;
          *(_OWORD *)a2 = 0;
          *(_QWORD *)(a2 + 16) = 0;
          *(_QWORD *)(a2 + 24) = 0;
          v8 = "Malformed literal";
        }
        else
        {
          v9 = 17;
          *(_OWORD *)a2 = 0;
          *(_QWORD *)(a2 + 16) = 0;
          *(_QWORD *)(a2 + 24) = 0;
          v8 = "Malformed comment";
        }
      }
      else
      {
        v9 = 23;
        *(_OWORD *)a2 = 0;
        *(_QWORD *)(a2 + 16) = 0;
        *(_QWORD *)(a2 + 24) = 0;
        v8 = "Malformed array literal";
      }
    }
    else
    {
      v9 = 57;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      v8 = "Left-over characters in stream after parsing a JSON value";
    }
  }
LABEL_26:
  std::string::_Construct<1,char const *>(a2, v8, v9);
  return a2;
}

```

## disassembly

```asm
0x180029b20  push    rbx
0x180029b22  sub     rsp, 30h
0x180029b26  xor     ecx, ecx
0x180029b28  mov     rbx, rdx
0x180029b2b  cmp     r8d, 6
0x180029b2f  jg      loc_180029C1B
0x180029b35  jz      loc_180029BFB
0x180029b3b  sub     r8d, 1
0x180029b3f  jz      loc_180029BDB
0x180029b45  sub     r8d, 1
0x180029b49  jz      short loc_180029BBB
0x180029b4b  sub     r8d, 1
0x180029b4f  jz      short loc_180029B9B
0x180029b51  sub     r8d, 1
0x180029b55  jz      short loc_180029B7B
0x180029b57  cmp     r8d, 1
0x180029b5b  jnz     loc_180029C41
0x180029b61  xorps   xmm0, xmm0
0x180029b64  movups  xmmword ptr [rdx], xmm0
0x180029b67  mov     [rdx+10h], rcx
0x180029b6b  mov     [rdx+18h], rcx
0x180029b6f  lea     rdx, aMalformedObjec; "Malformed object literal"
0x180029b76  jmp     loc_180029CEA
0x180029b7b  xorps   xmm0, xmm0
0x180029b7e  mov     r8d, 11h
0x180029b84  movups  xmmword ptr [rdx], xmm0
0x180029b87  mov     [rdx+10h], rcx
0x180029b8b  mov     [rdx+18h], rcx
0x180029b8f  lea     rdx, aMalformedLiter; "Malformed literal"
0x180029b96  jmp     loc_180029CF0
0x180029b9b  xorps   xmm0, xmm0
0x180029b9e  mov     r8d, 11h
0x180029ba4  movups  xmmword ptr [rdx], xmm0
0x180029ba7  mov     [rdx+10h], rcx
0x180029bab  mov     [rdx+18h], rcx
0x180029baf  lea     rdx, aMalformedComme; "Malformed comment"
0x180029bb6  jmp     loc_180029CF0
0x180029bbb  xorps   xmm0, xmm0
0x180029bbe  mov     r8d, 17h
0x180029bc4  movups  xmmword ptr [rdx], xmm0
0x180029bc7  mov     [rdx+10h], rcx
0x180029bcb  mov     [rdx+18h], rcx
0x180029bcf  lea     rdx, aMalformedArray; "Malformed array literal"
0x180029bd6  jmp     loc_180029CF0
0x180029bdb  xorps   xmm0, xmm0
0x180029bde  mov     r8d, 39h ; '9'
0x180029be4  movups  xmmword ptr [rdx], xmm0
0x180029be7  mov     [rdx+10h], rcx
0x180029beb  mov     [rdx+18h], rcx
0x180029bef  lea     rdx, aLeftOverCharac_0; "Left-over characters in stream after pa"...
0x180029bf6  jmp     loc_180029CF0
0x180029bfb  xorps   xmm0, xmm0
0x180029bfe  mov     r8d, 19h
0x180029c04  movups  xmmword ptr [rdx], xmm0
0x180029c07  mov     [rdx+10h], rcx
0x180029c0b  mov     [rdx+18h], rcx
0x180029c0f  lea     rdx, aMalformedNumer; "Malformed numeric literal"
0x180029c16  jmp     loc_180029CF0
0x180029c1b  sub     r8d, 7
0x180029c1f  jz      loc_180029CD5
0x180029c25  sub     r8d, 1
0x180029c29  jz      loc_180029CB8
0x180029c2f  sub     r8d, 1
0x180029c33  jz      short loc_180029C9B
0x180029c35  sub     r8d, 1
0x180029c39  jz      short loc_180029C7E
0x180029c3b  cmp     r8d, 1
0x180029c3f  jz      short loc_180029C61
0x180029c41  xorps   xmm0, xmm0
0x180029c44  mov     r8d, 12h
0x180029c4a  movups  xmmword ptr [rdx], xmm0
0x180029c4d  mov     [rdx+10h], rcx
0x180029c51  mov     [rdx+18h], rcx
0x180029c55  lea     rdx, aUnknownJsonErr; "Unknown json error"
0x180029c5c  jmp     loc_180029CF0
0x180029c61  xorps   xmm0, xmm0
0x180029c64  mov     r8d, 10h
0x180029c6a  movups  xmmword ptr [rdx], xmm0
0x180029c6d  mov     [rdx+10h], rcx
0x180029c71  mov     [rdx+18h], rcx
0x180029c75  lea     rdx, aUnexpectedToke; "Unexpected token"
0x180029c7c  jmp     short loc_180029CF0
0x180029c7e  xorps   xmm0, xmm0
0x180029c81  mov     r8d, 10h
0x180029c87  movups  xmmword ptr [rdx], xmm0
0x180029c8a  mov     [rdx+10h], rcx
0x180029c8e  mov     [rdx+18h], rcx
0x180029c92  lea     rdx, aNestingTooDeep; "Nesting too deep"
0x180029c99  jmp     short loc_180029CF0
0x180029c9b  xorps   xmm0, xmm0
0x180029c9e  mov     r8d, 11h
0x180029ca4  movups  xmmword ptr [rdx], xmm0
0x180029ca7  mov     [rdx+10h], rcx
0x180029cab  mov     [rdx+18h], rcx
0x180029caf  lea     rdx, aMismatchedBrac; "Mismatched braces"
0x180029cb6  jmp     short loc_180029CF0
0x180029cb8  xorps   xmm0, xmm0
0x180029cbb  mov     r8d, 0Fh
0x180029cc1  movups  xmmword ptr [rdx], xmm0
0x180029cc4  mov     [rdx+10h], rcx
0x180029cc8  mov     [rdx+18h], rcx
0x180029ccc  lea     rdx, aMalformedToken; "Malformed token"
0x180029cd3  jmp     short loc_180029CF0
0x180029cd5  xorps   xmm0, xmm0
0x180029cd8  movups  xmmword ptr [rdx], xmm0
0x180029cdb  mov     [rdx+10h], rcx
0x180029cdf  mov     [rdx+18h], rcx
0x180029ce3  lea     rdx, aMalformedStrin; "Malformed string literal"
0x180029cea  mov     r8d, 18h
0x180029cf0  mov     rcx, rbx
0x180029cf3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180029cf8  mov     rax, rbx
0x180029cfb  add     rsp, 30h
0x180029cff  pop     rbx
0x180029d00  retn
```
