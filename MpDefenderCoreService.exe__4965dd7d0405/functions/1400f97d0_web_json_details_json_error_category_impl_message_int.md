# web::json::details::json_error_category_impl::message(int)

- ea: `0x1400f97d0`
- end: `0x1400f99b1`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14007e088`
- `0x1400f97d0`

## string_xrefs

- `0x1400f989f`: `Left-over characters in stream after parsing a JSON value`
- `0x1400f985f`: `Malformed comment`
- `0x1400f997c`: `Malformed token`
- `0x1400f9905`: `Unknown json error`
- `0x1400f9925`: `Unexpected token`

## pseudocode

```c
_QWORD *__fastcall web::json::details::json_error_category_impl::message(__int64 a1, _QWORD *a2, int a3)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  const char *v8; // rdx
  size_t v9; // r8
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
      a2[2] = 0;
      a2[3] = 0;
      v8 = "Malformed string literal";
      goto LABEL_25;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v9 = 15;
      *(_OWORD *)a2 = 0;
      a2[2] = 0;
      a2[3] = 0;
      v8 = "Malformed token";
      goto LABEL_26;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v9 = 17;
      *(_OWORD *)a2 = 0;
      a2[2] = 0;
      a2[3] = 0;
      v8 = "Mismatched braces";
      goto LABEL_26;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      a2[2] = 0;
      a2[3] = 0;
      v8 = "Nesting too deep";
      goto LABEL_26;
    }
    if ( v13 == 1 )
    {
      v9 = 16;
      *(_OWORD *)a2 = 0;
      a2[2] = 0;
      a2[3] = 0;
      v8 = "Unexpected token";
      goto LABEL_26;
    }
    goto LABEL_19;
  }
  if ( a3 == 6 )
  {
    v9 = 25;
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 0;
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
              a2[2] = 0;
              a2[3] = 0;
              v8 = "Malformed object literal";
LABEL_25:
              v9 = 24;
              goto LABEL_26;
            }
LABEL_19:
            v9 = 18;
            *(_OWORD *)a2 = 0;
            a2[2] = 0;
            a2[3] = 0;
            v8 = "Unknown json error";
            goto LABEL_26;
          }
          v9 = 17;
          *(_OWORD *)a2 = 0;
          a2[2] = 0;
          a2[3] = 0;
          v8 = "Malformed literal";
        }
        else
        {
          v9 = 17;
          *(_OWORD *)a2 = 0;
          a2[2] = 0;
          a2[3] = 0;
          v8 = "Malformed comment";
        }
      }
      else
      {
        v9 = 23;
        *(_OWORD *)a2 = 0;
        a2[2] = 0;
        a2[3] = 0;
        v8 = "Malformed array literal";
      }
    }
    else
    {
      v9 = 57;
      *(_OWORD *)a2 = 0;
      a2[2] = 0;
      a2[3] = 0;
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
0x1400f97d0  push    rbx
0x1400f97d2  sub     rsp, 30h
0x1400f97d6  xor     ecx, ecx
0x1400f97d8  mov     rbx, rdx
0x1400f97db  cmp     r8d, 6
0x1400f97df  jg      loc_1400F98CB
0x1400f97e5  jz      loc_1400F98AB
0x1400f97eb  sub     r8d, 1
0x1400f97ef  jz      loc_1400F988B
0x1400f97f5  sub     r8d, 1
0x1400f97f9  jz      short loc_1400F986B
0x1400f97fb  sub     r8d, 1
0x1400f97ff  jz      short loc_1400F984B
0x1400f9801  sub     r8d, 1
0x1400f9805  jz      short loc_1400F982B
0x1400f9807  cmp     r8d, 1
0x1400f980b  jnz     loc_1400F98F1
0x1400f9811  xorps   xmm0, xmm0
0x1400f9814  movups  xmmword ptr [rdx], xmm0
0x1400f9817  mov     [rdx+10h], rcx
0x1400f981b  mov     [rdx+18h], rcx
0x1400f981f  lea     rdx, aMalformedObjec; "Malformed object literal"
0x1400f9826  jmp     loc_1400F999A
0x1400f982b  xorps   xmm0, xmm0
0x1400f982e  mov     r8d, 11h
0x1400f9834  movups  xmmword ptr [rdx], xmm0
0x1400f9837  mov     [rdx+10h], rcx
0x1400f983b  mov     [rdx+18h], rcx
0x1400f983f  lea     rdx, aMalformedLiter; "Malformed literal"
0x1400f9846  jmp     loc_1400F99A0
0x1400f984b  xorps   xmm0, xmm0
0x1400f984e  mov     r8d, 11h
0x1400f9854  movups  xmmword ptr [rdx], xmm0
0x1400f9857  mov     [rdx+10h], rcx
0x1400f985b  mov     [rdx+18h], rcx
0x1400f985f  lea     rdx, aMalformedComme; "Malformed comment"
0x1400f9866  jmp     loc_1400F99A0
0x1400f986b  xorps   xmm0, xmm0
0x1400f986e  mov     r8d, 17h
0x1400f9874  movups  xmmword ptr [rdx], xmm0
0x1400f9877  mov     [rdx+10h], rcx
0x1400f987b  mov     [rdx+18h], rcx
0x1400f987f  lea     rdx, aMalformedArray; "Malformed array literal"
0x1400f9886  jmp     loc_1400F99A0
0x1400f988b  xorps   xmm0, xmm0
0x1400f988e  mov     r8d, 39h ; '9'
0x1400f9894  movups  xmmword ptr [rdx], xmm0
0x1400f9897  mov     [rdx+10h], rcx
0x1400f989b  mov     [rdx+18h], rcx
0x1400f989f  lea     rdx, aLeftOverCharac_0; "Left-over characters in stream after pa"...
0x1400f98a6  jmp     loc_1400F99A0
0x1400f98ab  xorps   xmm0, xmm0
0x1400f98ae  mov     r8d, 19h
0x1400f98b4  movups  xmmword ptr [rdx], xmm0
0x1400f98b7  mov     [rdx+10h], rcx
0x1400f98bb  mov     [rdx+18h], rcx
0x1400f98bf  lea     rdx, aMalformedNumer; "Malformed numeric literal"
0x1400f98c6  jmp     loc_1400F99A0
0x1400f98cb  sub     r8d, 7
0x1400f98cf  jz      loc_1400F9985
0x1400f98d5  sub     r8d, 1
0x1400f98d9  jz      loc_1400F9968
0x1400f98df  sub     r8d, 1
0x1400f98e3  jz      short loc_1400F994B
0x1400f98e5  sub     r8d, 1
0x1400f98e9  jz      short loc_1400F992E
0x1400f98eb  cmp     r8d, 1
0x1400f98ef  jz      short loc_1400F9911
0x1400f98f1  xorps   xmm0, xmm0
0x1400f98f4  mov     r8d, 12h
0x1400f98fa  movups  xmmword ptr [rdx], xmm0
0x1400f98fd  mov     [rdx+10h], rcx
0x1400f9901  mov     [rdx+18h], rcx
0x1400f9905  lea     rdx, aUnknownJsonErr; "Unknown json error"
0x1400f990c  jmp     loc_1400F99A0
0x1400f9911  xorps   xmm0, xmm0
0x1400f9914  mov     r8d, 10h
0x1400f991a  movups  xmmword ptr [rdx], xmm0
0x1400f991d  mov     [rdx+10h], rcx
0x1400f9921  mov     [rdx+18h], rcx
0x1400f9925  lea     rdx, aUnexpectedToke; "Unexpected token"
0x1400f992c  jmp     short loc_1400F99A0
0x1400f992e  xorps   xmm0, xmm0
0x1400f9931  mov     r8d, 10h
0x1400f9937  movups  xmmword ptr [rdx], xmm0
0x1400f993a  mov     [rdx+10h], rcx
0x1400f993e  mov     [rdx+18h], rcx
0x1400f9942  lea     rdx, aNestingTooDeep; "Nesting too deep"
0x1400f9949  jmp     short loc_1400F99A0
0x1400f994b  xorps   xmm0, xmm0
0x1400f994e  mov     r8d, 11h
0x1400f9954  movups  xmmword ptr [rdx], xmm0
0x1400f9957  mov     [rdx+10h], rcx
0x1400f995b  mov     [rdx+18h], rcx
0x1400f995f  lea     rdx, aMismatchedBrac; "Mismatched braces"
0x1400f9966  jmp     short loc_1400F99A0
0x1400f9968  xorps   xmm0, xmm0
0x1400f996b  mov     r8d, 0Fh
0x1400f9971  movups  xmmword ptr [rdx], xmm0
0x1400f9974  mov     [rdx+10h], rcx
0x1400f9978  mov     [rdx+18h], rcx
0x1400f997c  lea     rdx, aMalformedToken; "Malformed token"
0x1400f9983  jmp     short loc_1400F99A0
0x1400f9985  xorps   xmm0, xmm0
0x1400f9988  movups  xmmword ptr [rdx], xmm0
0x1400f998b  mov     [rdx+10h], rcx
0x1400f998f  mov     [rdx+18h], rcx
0x1400f9993  lea     rdx, aMalformedStrin; "Malformed string literal"
0x1400f999a  mov     r8d, 18h
0x1400f99a0  mov     rcx, rbx
0x1400f99a3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400f99a8  mov     rax, rbx
0x1400f99ab  add     rsp, 30h
0x1400f99af  pop     rbx
0x1400f99b0  retn
```
