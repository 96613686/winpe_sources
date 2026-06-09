# ReadBuffer::ParseHeader(void)

- ea: `0x140001468`
- end: `0x1400017aa`
- name: `?ParseHeader@ReadBuffer@@AEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(ReadBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400017ac`

## callees

- `0x140001468`
- `0x1400051ac`
- `0x140005254`
- `0x140006488`
- `0x14000648e`

## import_xrefs

- `ucrtbase_clr0400!strtol` at `0x1400015da`
- `ucrtbase_clr0400!strtol` at `0x140001645`
- `ucrtbase_clr0400!strtol` at `0x1400016f5`
- `ucrtbase_clr0400!strtol` at `0x140001728`
- `ucrtbase_clr0400!strtol` at `0x1400015da`
- `ucrtbase_clr0400!strtol` at `0x140001645`
- `ucrtbase_clr0400!strtol` at `0x1400016f5`
- `ucrtbase_clr0400!strtol` at `0x140001728`

## pseudocode

```c
__int64 __fastcall ReadBuffer::ParseHeader(ReadBuffer *this)
{
  __int64 v1; // rdx
  unsigned int v2; // ebx
  __int64 v3; // rax
  char v5; // r14
  _DWORD *v6; // rsi
  const char *v7; // rsi
  char *v8; // rsi
  char *v9; // rax
  unsigned __int16 *v10; // rax
  unsigned int v11; // eax
  char *v12; // rax
  unsigned int v13; // eax
  int v14; // eax
  __int64 result; // rax
  char *String; // [rsp+50h] [rbp+30h] BYREF
  char *EndPtr; // [rsp+58h] [rbp+38h] BYREF

  v1 = *((int *)this + 7);
  v2 = 0;
  v3 = *((_QWORD *)this + 1);
  v5 = *(_BYTE *)(v1 + v3);
  *(_BYTE *)(v1 + v3) = 0;
  v6 = (_DWORD *)*((_QWORD *)this + 1);
  switch ( *v6 )
  {
    case 0x20544547:
      *((_DWORD *)this + 8) = 1;
      goto LABEL_11;
    case 0x20545550:
      *((_DWORD *)this + 8) = 2;
LABEL_11:
      v7 = (const char *)(v6 + 1);
      break;
    case 0x44414548:
      v8 = (char *)(v6 + 1);
      String = v8;
      if ( *v8 != 32 )
        goto LABEL_50;
      *((_DWORD *)this + 8) = 4;
      v7 = v8 + 1;
      break;
    default:
      if ( *v6 != 1162626372 || (v6[1] & 0xFFFFFF) != 0x204554 )
        goto LABEL_50;
      *((_DWORD *)this + 8) = 3;
      v7 = (char *)v6 + 7;
      break;
  }
  v9 = strchr_0(v7, 32);
  String = v9;
  if ( !v9 || v9 == v7 )
  {
LABEL_50:
    v2 = -2147024809;
    goto LABEL_51;
  }
  *v9 = 0;
  v10 = DupStrW(v7, 0);
  *((_QWORD *)this + 5) = v10;
  if ( !v10 )
  {
    v2 = -2147024882;
    goto LABEL_51;
  }
  *String++ = 32;
  if ( !StrEquals(&String, "HTTP/1.1\r\n", 10) )
    goto LABEL_50;
  while ( *String != 13 )
  {
    switch ( *String )
    {
      case 'C':
        if ( StrEquals(&String, "Content-Length:", 15) )
        {
          v11 = strtol(String, &EndPtr, 10);
          *((_DWORD *)this + 12) = v11;
          goto LABEL_24;
        }
        goto LABEL_43;
      case 'E':
        if ( StrEquals(&String, "Exclusive: ", 11) )
        {
          if ( StrEquals(&String, "acquire\r\n", 9) )
          {
            v14 = 1;
          }
          else
          {
            if ( !StrEquals(&String, "release\r\n", 9) )
              goto LABEL_50;
            v14 = 2;
          }
          *((_DWORD *)this + 14) = v14;
        }
        else
        {
          if ( StrEquals(&String, "ExtraFlags:", 11) )
          {
            *((_DWORD *)this + 17) = strtol(String, &EndPtr, 10);
            goto LABEL_25;
          }
LABEL_43:
          String = strstr_0(String, "\r\n");
          if ( !String )
          {
            v2 = -2147418113;
            goto LABEL_51;
          }
          String += 2;
        }
        break;
      case 'L':
        if ( !StrEquals(&String, "LockCookie:", 11) )
          goto LABEL_43;
        v13 = strtol(String, &EndPtr, 10);
        *((_DWORD *)this + 16) = v13;
        if ( v13 > 0x7FFFFFFE )
          goto LABEL_50;
        v12 = EndPtr;
        if ( EndPtr == String )
          goto LABEL_50;
        *((_DWORD *)this + 15) = 1;
LABEL_26:
        String = v12;
        if ( !StrEquals(&String, "\r\n", 2) )
          goto LABEL_50;
        break;
      default:
        if ( *String == 84 && StrEquals(&String, "Timeout:", 8) )
        {
          v11 = strtol(String, &EndPtr, 10);
          *((_DWORD *)this + 13) = v11;
LABEL_24:
          if ( v11 > 0x7FFFFFFE )
            goto LABEL_50;
LABEL_25:
          v12 = EndPtr;
          if ( EndPtr == String )
            goto LABEL_50;
          goto LABEL_26;
        }
        goto LABEL_43;
    }
  }
  if ( !StrEquals(&String, "\r\n", 2) )
    goto LABEL_43;
  if ( *((_DWORD *)this + 8) == 2 )
  {
    if ( *((int *)this + 12) <= 0 )
      goto LABEL_50;
  }
  else if ( *((int *)this + 12) > 0 )
  {
    goto LABEL_50;
  }
LABEL_51:
  result = v2;
  *(_BYTE *)(*((int *)this + 7) + *((_QWORD *)this + 1)) = v5;
  return result;
}

```

## disassembly

```asm
0x140001468  mov     [rsp-28h+arg_10], rbx
0x14000146d  mov     [rsp-28h+arg_18], rsi
0x140001472  push    rbp
0x140001473  push    rdi
0x140001474  push    r12
0x140001476  push    r14
0x140001478  push    r15
0x14000147a  mov     rbp, rsp
0x14000147d  sub     rsp, 20h
0x140001481  movsxd  rdx, dword ptr [rcx+1Ch]
0x140001485  xor     ebx, ebx
0x140001487  mov     rax, [rcx+8]
0x14000148b  mov     rdi, rcx
0x14000148e  lea     r15d, [rbx+2]
0x140001492  mov     r14b, [rdx+rax]
0x140001496  mov     [rdx+rax], bl
0x140001499  mov     rsi, [rcx+8]
0x14000149d  cmp     dword ptr [rsi], 20544547h
0x1400014a3  jz      short loc_140001504
0x1400014a5  cmp     dword ptr [rsi], 20545550h
0x1400014ab  jz      short loc_1400014FE
0x1400014ad  cmp     dword ptr [rsi], 44414548h
0x1400014b3  jz      short loc_1400014E1
0x1400014b5  cmp     dword ptr [rsi], 454C4544h
0x1400014bb  jnz     loc_140001780
0x1400014c1  mov     eax, [rsi+4]
0x1400014c4  and     eax, 0FFFFFFh
0x1400014c9  cmp     eax, 204554h
0x1400014ce  jnz     loc_140001780
0x1400014d4  mov     dword ptr [rcx+20h], 3
0x1400014db  add     rsi, 7
0x1400014df  jmp     short loc_14000150F
0x1400014e1  add     rsi, 4
0x1400014e5  mov     [rbp+String], rsi
0x1400014e9  cmp     byte ptr [rsi], 20h ; ' '
0x1400014ec  jnz     loc_140001780
0x1400014f2  mov     dword ptr [rcx+20h], 4
0x1400014f9  inc     rsi
0x1400014fc  jmp     short loc_14000150F
0x1400014fe  mov     [rcx+20h], r15d
0x140001502  jmp     short loc_14000150B
0x140001504  mov     dword ptr [rcx+20h], 1
0x14000150b  add     rsi, 4
0x14000150f  mov     edx, 20h ; ' '; Val
0x140001514  mov     rcx, rsi; Str
0x140001517  call    strchr_0
0x14000151c  mov     [rbp+String], rax
0x140001520  test    rax, rax
0x140001523  jz      loc_140001780
0x140001529  cmp     rax, rsi
0x14000152c  jz      loc_140001780
0x140001532  xor     edx, edx; CodePage
0x140001534  mov     [rax], bl
0x140001536  mov     rcx, rsi; lpMultiByteStr
0x140001539  call    ?DupStrW@@YAPEAGPEBDI@Z; DupStrW(char const *,uint)
0x14000153e  mov     [rdi+28h], rax
0x140001542  test    rax, rax
0x140001545  jnz     short loc_140001551
0x140001547  mov     ebx, 8007000Eh
0x14000154c  jmp     loc_140001785
0x140001551  mov     rax, [rbp+String]
0x140001555  lea     rdx, aHttp11; "HTTP/1.1\r\n"
0x14000155c  mov     r12d, 0Ah
0x140001562  lea     rcx, [rbp+String]; char **
0x140001566  mov     r8d, r12d; int
0x140001569  mov     byte ptr [rax], 20h ; ' '
0x14000156c  inc     [rbp+String]
0x140001570  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x140001575  test    al, al
0x140001577  jz      loc_140001780
0x14000157d  lea     rsi, SubStr; "\r\n"
0x140001584  mov     rax, [rbp+String]
0x140001588  cmp     byte ptr [rax], 0Dh
0x14000158b  jz      loc_140001736
0x140001591  cmp     byte ptr [rax], 43h ; 'C'
0x140001594  jz      loc_140001703
0x14000159a  cmp     byte ptr [rax], 45h ; 'E'
0x14000159d  jz      loc_140001670
0x1400015a3  cmp     byte ptr [rax], 4Ch ; 'L'
0x1400015a6  jz      short loc_14000161C
0x1400015a8  cmp     byte ptr [rax], 54h ; 'T'
0x1400015ab  jnz     loc_140001749
0x1400015b1  mov     r8d, 8; int
0x1400015b7  lea     rdx, aTimeout; "Timeout:"
0x1400015be  lea     rcx, [rbp+String]; char **
0x1400015c2  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x1400015c7  test    al, al
0x1400015c9  jz      loc_140001749
0x1400015cf  mov     rcx, [rbp+String]; String
0x1400015d3  lea     rdx, [rbp+EndPtr]; EndPtr
0x1400015d7  mov     r8d, r12d; Radix
0x1400015da  call    cs:__imp_strtol
0x1400015e0  mov     [rdi+34h], eax
0x1400015e3  cmp     eax, 7FFFFFFEh
0x1400015e8  ja      loc_140001780
0x1400015ee  mov     rax, [rbp+EndPtr]
0x1400015f2  cmp     rax, [rbp+String]
0x1400015f6  jz      loc_140001780
0x1400015fc  mov     r8d, r15d; int
0x1400015ff  mov     [rbp+String], rax
0x140001603  mov     rdx, rsi; char *
0x140001606  lea     rcx, [rbp+String]; char **
0x14000160a  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x14000160f  test    al, al
0x140001611  jz      loc_140001780
0x140001617  jmp     loc_140001584
0x14000161c  mov     r8d, 0Bh; int
0x140001622  lea     rdx, aLockcookie; "LockCookie:"
0x140001629  lea     rcx, [rbp+String]; char **
0x14000162d  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x140001632  test    al, al
0x140001634  jz      loc_140001749
0x14000163a  mov     rcx, [rbp+String]; String
0x14000163e  lea     rdx, [rbp+EndPtr]; EndPtr
0x140001642  mov     r8d, r12d; Radix
0x140001645  call    cs:__imp_strtol
0x14000164b  mov     [rdi+40h], eax
0x14000164e  cmp     eax, 7FFFFFFEh
0x140001653  ja      loc_140001780
0x140001659  mov     rax, [rbp+EndPtr]
0x14000165d  cmp     rax, [rbp+String]
0x140001661  jz      loc_140001780
0x140001667  mov     dword ptr [rdi+3Ch], 1
0x14000166e  jmp     short loc_1400015FC
0x140001670  mov     r8d, 0Bh; int
0x140001676  lea     rdx, aExclusive; "Exclusive: "
0x14000167d  lea     rcx, [rbp+String]; char **
0x140001681  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x140001686  lea     rcx, [rbp+String]; char **
0x14000168a  test    al, al
0x14000168c  jz      short loc_1400016D4
0x14000168e  mov     r8d, 9; int
0x140001694  lea     rdx, aAcquire; "acquire\r\n"
0x14000169b  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x1400016a0  test    al, al
0x1400016a2  jz      short loc_1400016AB
0x1400016a4  mov     eax, 1
0x1400016a9  jmp     short loc_1400016CC
0x1400016ab  mov     r8d, 9; int
0x1400016b1  lea     rdx, aRelease; "release\r\n"
0x1400016b8  lea     rcx, [rbp+String]; char **
0x1400016bc  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x1400016c1  test    al, al
0x1400016c3  jz      loc_140001780
0x1400016c9  mov     eax, r15d
0x1400016cc  mov     [rdi+38h], eax
0x1400016cf  jmp     loc_140001584
0x1400016d4  mov     r8d, 0Bh; int
0x1400016da  lea     rdx, aExtraflags; "ExtraFlags:"
0x1400016e1  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x1400016e6  test    al, al
0x1400016e8  jz      short loc_140001749
0x1400016ea  mov     rcx, [rbp+String]; String
0x1400016ee  lea     rdx, [rbp+EndPtr]; EndPtr
0x1400016f2  mov     r8d, r12d; Radix
0x1400016f5  call    cs:__imp_strtol
0x1400016fb  mov     [rdi+44h], eax
0x1400016fe  jmp     loc_1400015EE
0x140001703  mov     r8d, 0Fh; int
0x140001709  lea     rdx, aContentLength_0; "Content-Length:"
0x140001710  lea     rcx, [rbp+String]; char **
0x140001714  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x140001719  test    al, al
0x14000171b  jz      short loc_140001749
0x14000171d  mov     rcx, [rbp+String]; String
0x140001721  lea     rdx, [rbp+EndPtr]; EndPtr
0x140001725  mov     r8d, r12d; Radix
0x140001728  call    cs:__imp_strtol
0x14000172e  mov     [rdi+30h], eax
0x140001731  jmp     loc_1400015E3
0x140001736  mov     r8d, r15d; int
0x140001739  lea     rcx, [rbp+String]; char **
0x14000173d  mov     rdx, rsi; char *
0x140001740  call    ?StrEquals@@YA_NPEAPEADPEBDH@Z; StrEquals(char * *,char const *,int)
0x140001745  test    al, al
0x140001747  jnz     short loc_14000176E
0x140001749  mov     rcx, [rbp+String]; Str
0x14000174d  mov     rdx, rsi; SubStr
0x140001750  call    strstr_0
0x140001755  mov     [rbp+String], rax
0x140001759  test    rax, rax
0x14000175c  jz      short loc_140001767
0x14000175e  add     [rbp+String], r15
0x140001762  jmp     loc_140001584
0x140001767  mov     ebx, 8000FFFFh
0x14000176c  jmp     short loc_140001785
0x14000176e  cmp     [rdi+20h], r15d
0x140001772  jz      short loc_14000177B
0x140001774  cmp     [rdi+30h], ebx
0x140001777  jle     short loc_140001785
0x140001779  jmp     short loc_140001780
0x14000177b  cmp     [rdi+30h], ebx
0x14000177e  jg      short loc_140001785
0x140001780  mov     ebx, 80070057h
0x140001785  movsxd  rdx, dword ptr [rdi+1Ch]
0x140001789  mov     eax, ebx
0x14000178b  mov     rcx, [rdi+8]
0x14000178f  mov     rbx, [rsp+20h+arg_10]
0x140001794  mov     rsi, [rsp+20h+arg_18]
0x140001799  mov     [rdx+rcx], r14b
0x14000179d  add     rsp, 20h
0x1400017a1  pop     r15
0x1400017a3  pop     r14
0x1400017a5  pop     r12
0x1400017a7  pop     rdi
0x1400017a8  pop     rbp
0x1400017a9  retn
```
