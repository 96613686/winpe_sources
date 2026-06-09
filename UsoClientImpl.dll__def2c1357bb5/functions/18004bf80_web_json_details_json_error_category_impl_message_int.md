# web::json::details::json_error_category_impl::message(int)

- ea: `0x18004bf80`
- end: `0x18004c161`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180031ab0`
- `0x18004bf80`

## string_xrefs

- `0x18004c00f`: `Malformed comment`
- `0x18004c04f`: `Left-over characters in stream after parsing a JSON value`
- `0x18004c12c`: `Malformed token`
- `0x18004c0d5`: `Unexpected token`
- `0x18004c0b5`: `Unknown json error`

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
0x18004bf80  push    rbx
0x18004bf82  sub     rsp, 30h
0x18004bf86  xor     ecx, ecx
0x18004bf88  mov     rbx, rdx
0x18004bf8b  cmp     r8d, 6
0x18004bf8f  jg      loc_18004C07B
0x18004bf95  jz      loc_18004C05B
0x18004bf9b  sub     r8d, 1
0x18004bf9f  jz      loc_18004C03B
0x18004bfa5  sub     r8d, 1
0x18004bfa9  jz      short loc_18004C01B
0x18004bfab  sub     r8d, 1
0x18004bfaf  jz      short loc_18004BFFB
0x18004bfb1  sub     r8d, 1
0x18004bfb5  jz      short loc_18004BFDB
0x18004bfb7  cmp     r8d, 1
0x18004bfbb  jnz     loc_18004C0A1
0x18004bfc1  xorps   xmm0, xmm0
0x18004bfc4  movups  xmmword ptr [rdx], xmm0
0x18004bfc7  mov     [rdx+10h], rcx
0x18004bfcb  mov     [rdx+18h], rcx
0x18004bfcf  lea     rdx, aMalformedObjec; "Malformed object literal"
0x18004bfd6  jmp     loc_18004C14A
0x18004bfdb  xorps   xmm0, xmm0
0x18004bfde  mov     r8d, 11h
0x18004bfe4  movups  xmmword ptr [rdx], xmm0
0x18004bfe7  mov     [rdx+10h], rcx
0x18004bfeb  mov     [rdx+18h], rcx
0x18004bfef  lea     rdx, aMalformedLiter; "Malformed literal"
0x18004bff6  jmp     loc_18004C150
0x18004bffb  xorps   xmm0, xmm0
0x18004bffe  mov     r8d, 11h
0x18004c004  movups  xmmword ptr [rdx], xmm0
0x18004c007  mov     [rdx+10h], rcx
0x18004c00b  mov     [rdx+18h], rcx
0x18004c00f  lea     rdx, aMalformedComme; "Malformed comment"
0x18004c016  jmp     loc_18004C150
0x18004c01b  xorps   xmm0, xmm0
0x18004c01e  mov     r8d, 17h
0x18004c024  movups  xmmword ptr [rdx], xmm0
0x18004c027  mov     [rdx+10h], rcx
0x18004c02b  mov     [rdx+18h], rcx
0x18004c02f  lea     rdx, aMalformedArray; "Malformed array literal"
0x18004c036  jmp     loc_18004C150
0x18004c03b  xorps   xmm0, xmm0
0x18004c03e  mov     r8d, 39h ; '9'
0x18004c044  movups  xmmword ptr [rdx], xmm0
0x18004c047  mov     [rdx+10h], rcx
0x18004c04b  mov     [rdx+18h], rcx
0x18004c04f  lea     rdx, aLeftOverCharac_0; "Left-over characters in stream after pa"...
0x18004c056  jmp     loc_18004C150
0x18004c05b  xorps   xmm0, xmm0
0x18004c05e  mov     r8d, 19h
0x18004c064  movups  xmmword ptr [rdx], xmm0
0x18004c067  mov     [rdx+10h], rcx
0x18004c06b  mov     [rdx+18h], rcx
0x18004c06f  lea     rdx, aMalformedNumer; "Malformed numeric literal"
0x18004c076  jmp     loc_18004C150
0x18004c07b  sub     r8d, 7
0x18004c07f  jz      loc_18004C135
0x18004c085  sub     r8d, 1
0x18004c089  jz      loc_18004C118
0x18004c08f  sub     r8d, 1
0x18004c093  jz      short loc_18004C0FB
0x18004c095  sub     r8d, 1
0x18004c099  jz      short loc_18004C0DE
0x18004c09b  cmp     r8d, 1
0x18004c09f  jz      short loc_18004C0C1
0x18004c0a1  xorps   xmm0, xmm0
0x18004c0a4  mov     r8d, 12h
0x18004c0aa  movups  xmmword ptr [rdx], xmm0
0x18004c0ad  mov     [rdx+10h], rcx
0x18004c0b1  mov     [rdx+18h], rcx
0x18004c0b5  lea     rdx, aUnknownJsonErr; "Unknown json error"
0x18004c0bc  jmp     loc_18004C150
0x18004c0c1  xorps   xmm0, xmm0
0x18004c0c4  mov     r8d, 10h
0x18004c0ca  movups  xmmword ptr [rdx], xmm0
0x18004c0cd  mov     [rdx+10h], rcx
0x18004c0d1  mov     [rdx+18h], rcx
0x18004c0d5  lea     rdx, aUnexpectedToke; "Unexpected token"
0x18004c0dc  jmp     short loc_18004C150
0x18004c0de  xorps   xmm0, xmm0
0x18004c0e1  mov     r8d, 10h
0x18004c0e7  movups  xmmword ptr [rdx], xmm0
0x18004c0ea  mov     [rdx+10h], rcx
0x18004c0ee  mov     [rdx+18h], rcx
0x18004c0f2  lea     rdx, aNestingTooDeep; "Nesting too deep"
0x18004c0f9  jmp     short loc_18004C150
0x18004c0fb  xorps   xmm0, xmm0
0x18004c0fe  mov     r8d, 11h
0x18004c104  movups  xmmword ptr [rdx], xmm0
0x18004c107  mov     [rdx+10h], rcx
0x18004c10b  mov     [rdx+18h], rcx
0x18004c10f  lea     rdx, aMismatchedBrac; "Mismatched braces"
0x18004c116  jmp     short loc_18004C150
0x18004c118  xorps   xmm0, xmm0
0x18004c11b  mov     r8d, 0Fh
0x18004c121  movups  xmmword ptr [rdx], xmm0
0x18004c124  mov     [rdx+10h], rcx
0x18004c128  mov     [rdx+18h], rcx
0x18004c12c  lea     rdx, aMalformedToken; "Malformed token"
0x18004c133  jmp     short loc_18004C150
0x18004c135  xorps   xmm0, xmm0
0x18004c138  movups  xmmword ptr [rdx], xmm0
0x18004c13b  mov     [rdx+10h], rcx
0x18004c13f  mov     [rdx+18h], rcx
0x18004c143  lea     rdx, aMalformedStrin; "Malformed string literal"
0x18004c14a  mov     r8d, 18h
0x18004c150  mov     rcx, rbx
0x18004c153  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004c158  mov     rax, rbx
0x18004c15b  add     rsp, 30h
0x18004c15f  pop     rbx
0x18004c160  retn
```
