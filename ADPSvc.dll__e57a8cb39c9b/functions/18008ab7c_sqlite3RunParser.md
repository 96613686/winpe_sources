# sqlite3RunParser

- ea: `0x18008ab7c`
- end: `0x18008af16`
- name: `sqlite3RunParser`
- size: `922`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180060c44`
- `0x1800817f4`
- `0x1800885d4`
- `0x1800a8920`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x180042554`
- `0x18004abdc`
- `0x1800718f8`
- `0x18007281c`
- `0x180073a40`
- `0x180073aec`
- `0x18007ca84`
- `0x180080b64`
- `0x180084094`
- `0x18008ab7c`
- `0x1800a98a0`
- `0x1800aa3b0`
- `0x1800c393c`

## string_xrefs

- `0x18008adb8`: `unrecognized token: "%T"`

## pseudocode

```c
__int64 __fastcall sqlite3RunParser(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // rdi
  int v5; // esi
  int v6; // r12d
  __int64 v7; // r13
  __int64 v8; // rdx
  unsigned int v9; // r15d
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int Token; // eax
  unsigned __int64 v14; // rsi
  _DWORD *v15; // rcx
  __int64 v16; // rdx
  const char *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // esi
  const char *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  bool v24; // zf
  __int64 v25; // rdx
  __int64 v26; // rdx
  int v28[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[3]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v31; // [rsp+58h] [rbp-A8h]
  _DWORD v32[594]; // [rsp+60h] [rbp-A0h] BYREF
  char v33; // [rsp+9A8h] [rbp+8A8h] BYREF

  v2 = *a1;
  v28[0] = 0;
  v5 = -1;
  memset_0(v30, 0, 0x980u);
  v6 = *(_DWORD *)(v2 + 140);
  if ( !*(_DWORD *)(v2 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v31 = v32;
  v30[2] = &v33;
  v30[0] = v32;
  a1[43] = (__int64)a2;
  v30[1] = a1;
  v32[0] = 0;
  v7 = *(_QWORD *)(v2 + 352);
  *(_QWORD *)(v2 + 352) = a1;
  while ( 1 )
  {
    while ( 1 )
    {
      Token = sqlite3GetToken(a2, v28);
      v6 -= Token;
      v9 = Token;
      if ( v6 < 0 )
      {
        *((_DWORD *)a1 + 6) = 18;
LABEL_35:
        ++*((_DWORD *)a1 + 12);
        goto LABEL_36;
      }
      v8 = (unsigned int)v28[0];
      if ( v28[0] >= 164 )
        break;
LABEL_31:
      a1[36] = (__int64)a2;
      *((_DWORD *)a1 + 74) = v9;
      v29 = *((_OWORD *)a1 + 18);
      sqlite3Parser(v30, v8, &v29);
      a2 += (int)v9;
      if ( *((_DWORD *)a1 + 6) )
        goto LABEL_36;
      v5 = v28[0];
    }
    if ( *(_DWORD *)(v2 + 408) )
    {
      *((_DWORD *)a1 + 6) = 9;
      goto LABEL_35;
    }
    v8 = (unsigned int)v28[0];
    if ( v28[0] != 184 )
      break;
    a2 += (int)Token;
  }
  if ( !*a2 )
  {
    if ( v5 == 1 )
    {
      v8 = 0;
    }
    else
    {
      if ( !v5 )
        goto LABEL_36;
      v8 = 1;
    }
    v28[0] = v8;
    v9 = 0;
    goto LABEL_31;
  }
  switch ( v28[0] )
  {
    case 164:
      *(_QWORD *)&v29 = a2 + 6;
      if ( (unsigned int)getToken(&v29) == 59 )
      {
        v10 = getToken(&v29);
        v8 = 164;
        if ( v10 != 24 )
          v8 = 59;
        goto LABEL_29;
      }
LABEL_24:
      v8 = 59;
      goto LABEL_29;
    case 165:
      *(_QWORD *)&v29 = a2 + 4;
      if ( v5 != 23 )
        goto LABEL_24;
      v11 = getToken(&v29);
      if ( v11 != 22 && v11 != 59 )
        goto LABEL_24;
      v8 = 165;
LABEL_29:
      v28[0] = v8;
      goto LABEL_31;
    case 166:
      *(_QWORD *)&v29 = a2 + 6;
      if ( v5 != 23 || (v12 = getToken(&v29), v8 = 166, v12 != 22) )
        v8 = 59;
      goto LABEL_29;
    case 183:
      goto LABEL_31;
  }
  *(_QWORD *)&v29 = a2;
  *((_QWORD *)&v29 + 1) = Token;
  sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v29);
LABEL_36:
  v14 = v30[0];
  v15 = v31;
  while ( v14 > (unsigned __int64)v15 )
  {
    v16 = *(unsigned __int16 *)(v14 + 2);
    if ( (unsigned __int16)v16 >= 0xCDu )
    {
      yy_destructor(v30, v16, v14 + 8);
      v15 = v31;
    }
    v14 -= 24LL;
  }
  if ( v15 != v32 )
    sqlite3_free(v15);
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v17 = (const char *)a1[1];
  if ( v17 )
  {
LABEL_51:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v17, (const char *)a1[43]);
    v19 = 1;
  }
  else
  {
    v18 = *((unsigned int *)a1 + 6);
    v19 = 0;
    if ( (_DWORD)v18 && (_DWORD)v18 != 101 )
    {
      v20 = (const char *)sqlite3ErrStr(v18);
      v17 = (const char *)sqlite3MPrintf(v2, "%s", v20);
      a1[1] = (__int64)v17;
      goto LABEL_51;
    }
  }
  v21 = a1[50];
  a1[43] = (__int64)a2;
  sqlite3_free(v21);
  v23 = a1[44];
  if ( v23 )
  {
    if ( !*((_BYTE *)a1 + 308) )
    {
      if ( *(_QWORD *)(v2 + 776) || (v24 = *(_DWORD *)(v23 + 44) == 1, --*(_DWORD *)(v23 + 44), v24) )
        deleteTable(v2, v23, v22);
    }
  }
  v25 = a1[46];
  if ( v25 && *((_BYTE *)a1 + 308) < 2u )
    sqlite3DeleteTrigger(v2, v25);
  v26 = a1[41];
  if ( v26 )
    sqlite3DbNNFreeNN(v2, v26);
  *(_QWORD *)(v2 + 352) = v7;
  return v19;
}

```

## disassembly

```asm
0x18008ab7c  mov     [rsp-8+arg_10], rbx
0x18008ab81  push    rbp
0x18008ab82  push    rsi
0x18008ab83  push    rdi
0x18008ab84  push    r12
0x18008ab86  push    r13
0x18008ab88  push    r14
0x18008ab8a  push    r15
0x18008ab8c  lea     rbp, [rsp-8D0h]
0x18008ab94  sub     rsp, 9D0h
0x18008ab9b  mov     rax, cs:__security_cookie
0x18008aba2  xor     rax, rsp
0x18008aba5  mov     [rbp+900h+var_40], rax
0x18008abac  mov     rdi, [rcx]
0x18008abaf  mov     r14, rdx
0x18008abb2  mov     rbx, rcx
0x18008abb5  xor     r15d, r15d
0x18008abb8  xor     edx, edx; Val
0x18008abba  mov     [rsp+0A00h+var_9E0], r15d
0x18008abbf  lea     rcx, [rsp+0A00h+var_9C0]; void *
0x18008abc4  mov     r8d, 980h; Size
0x18008abca  or      esi, 0FFFFFFFFh
0x18008abcd  call    memset_0
0x18008abd2  mov     r12d, [rdi+8Ch]
0x18008abd9  cmp     [rdi+0D8h], r15d
0x18008abe0  jnz     short loc_18008ABE9
0x18008abe2  mov     [rdi+198h], r15d
0x18008abe9  lea     rax, [rsp+0A00h+var_9A0]
0x18008abee  mov     [rbx+18h], r15d
0x18008abf2  mov     [rsp+0A00h+var_9A8], rax
0x18008abf7  lea     rax, [rbp+900h+var_58]
0x18008abfe  mov     [rsp+0A00h+var_9B0], rax
0x18008ac03  lea     rax, [rsp+0A00h+var_9A0]
0x18008ac08  mov     [rsp+0A00h+var_9C0], rax
0x18008ac0d  mov     [rbx+158h], r14
0x18008ac14  mov     [rsp+0A00h+var_9B8], rbx
0x18008ac19  mov     [rsp+0A00h+var_9A0], r15d
0x18008ac1e  mov     r13, [rdi+160h]
0x18008ac25  mov     [rdi+160h], rbx
0x18008ac2c  jmp     loc_18008AD7C
0x18008ac31  mov     edx, [rsp+0A00h+var_9E0]
0x18008ac35  cmp     edx, 0A4h
0x18008ac3b  jl      loc_18008AD42
0x18008ac41  mov     eax, [rdi+198h]
0x18008ac47  test    eax, eax
0x18008ac49  jnz     loc_18008ADD3
0x18008ac4f  mov     edx, [rsp+0A00h+var_9E0]
0x18008ac53  cmp     edx, 0B8h
0x18008ac59  jnz     short loc_18008AC66
0x18008ac5b  movsxd  rax, r15d
0x18008ac5e  add     r14, rax
0x18008ac61  jmp     loc_18008AD7C
0x18008ac66  cmp     byte ptr [r14], 0
0x18008ac6a  jnz     short loc_18008AC8E
0x18008ac6c  cmp     esi, 1
0x18008ac6f  jnz     short loc_18008AC75
0x18008ac71  xor     edx, edx
0x18008ac73  jmp     short loc_18008AC82
0x18008ac75  test    esi, esi
0x18008ac77  jz      loc_18008AD9F
0x18008ac7d  mov     edx, 1
0x18008ac82  mov     [rsp+0A00h+var_9E0], edx
0x18008ac86  xor     r15d, r15d
0x18008ac89  jmp     loc_18008AD42
0x18008ac8e  cmp     edx, 0A4h
0x18008ac94  jnz     short loc_18008ACC7
0x18008ac96  lea     rax, [r14+6]
0x18008ac9a  lea     rcx, [rsp+0A00h+var_9D0]
0x18008ac9f  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18008aca4  call    getToken
0x18008aca9  mov     esi, 3Bh ; ';'
0x18008acae  cmp     eax, esi
0x18008acb0  jnz     short loc_18008AD01
0x18008acb2  lea     rcx, [rsp+0A00h+var_9D0]
0x18008acb7  call    getToken
0x18008acbc  cmp     eax, 18h
0x18008acbf  lea     edx, [rsi+69h]
0x18008acc2  cmovnz  edx, esi
0x18008acc5  jmp     short loc_18008AD34
0x18008acc7  cmp     edx, 0A5h
0x18008accd  jnz     short loc_18008AD05
0x18008accf  lea     rax, [r14+4]
0x18008acd3  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18008acd8  cmp     esi, 17h
0x18008acdb  jnz     short loc_18008ACFC
0x18008acdd  lea     rcx, [rsp+0A00h+var_9D0]
0x18008ace2  call    getToken
0x18008ace7  cmp     eax, 16h
0x18008acea  jz      short loc_18008ACF5
0x18008acec  mov     esi, 3Bh ; ';'
0x18008acf1  cmp     eax, esi
0x18008acf3  jnz     short loc_18008AD01
0x18008acf5  mov     edx, 0A5h
0x18008acfa  jmp     short loc_18008AD34
0x18008acfc  mov     esi, 3Bh ; ';'
0x18008ad01  mov     edx, esi
0x18008ad03  jmp     short loc_18008AD34
0x18008ad05  cmp     edx, 0A6h
0x18008ad0b  jnz     short loc_18008AD3A
0x18008ad0d  lea     rax, [r14+6]
0x18008ad11  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x18008ad16  cmp     esi, 17h
0x18008ad19  jnz     short loc_18008AD2F
0x18008ad1b  lea     rcx, [rsp+0A00h+var_9D0]
0x18008ad20  call    getToken
0x18008ad25  mov     edx, 0A6h
0x18008ad2a  cmp     eax, 16h
0x18008ad2d  jz      short loc_18008AD34
0x18008ad2f  mov     edx, 3Bh ; ';'
0x18008ad34  mov     [rsp+0A00h+var_9E0], edx
0x18008ad38  jmp     short loc_18008AD42
0x18008ad3a  cmp     edx, 0B7h
0x18008ad40  jnz     short loc_18008ADAB
0x18008ad42  mov     [rbx+120h], r14
0x18008ad49  lea     r8, [rsp+0A00h+var_9D0]
0x18008ad4e  mov     [rbx+128h], r15d
0x18008ad55  lea     rcx, [rsp+0A00h+var_9C0]
0x18008ad5a  movups  xmm0, xmmword ptr [rbx+120h]
0x18008ad61  movdqu  [rsp+0A00h+var_9D0], xmm0
0x18008ad67  call    sqlite3Parser
0x18008ad6c  movsxd  rax, r15d
0x18008ad6f  add     r14, rax
0x18008ad72  cmp     dword ptr [rbx+18h], 0
0x18008ad76  jnz     short loc_18008AD9F
0x18008ad78  mov     esi, [rsp+0A00h+var_9E0]
0x18008ad7c  lea     rdx, [rsp+0A00h+var_9E0]
0x18008ad81  mov     rcx, r14
0x18008ad84  call    sqlite3GetToken
0x18008ad89  sub     r12d, eax
0x18008ad8c  mov     r15d, eax
0x18008ad8f  jns     loc_18008AC31
0x18008ad95  mov     dword ptr [rbx+18h], 12h
0x18008ad9c  inc     dword ptr [rbx+30h]
0x18008ad9f  mov     rsi, [rsp+0A00h+var_9C0]
0x18008ada4  mov     rcx, [rsp+0A00h+var_9A8]
0x18008ada9  jmp     short loc_18008AE01
0x18008adab  lea     r8, [rsp+0A00h+var_9D0]
0x18008adb0  mov     dword ptr [rsp+0A00h+var_9D0+0Ch], 0
0x18008adb8  lea     rdx, aUnrecognizedTo_0; "unrecognized token: \"%T\""
0x18008adbf  mov     qword ptr [rsp+0A00h+var_9D0], r14
0x18008adc4  mov     rcx, rbx
0x18008adc7  mov     dword ptr [rsp+0A00h+var_9D0+8], r15d
0x18008adcc  call    sqlite3ErrorMsg
0x18008add1  jmp     short loc_18008AD9F
0x18008add3  mov     dword ptr [rbx+18h], 9
0x18008adda  jmp     short loc_18008AD9C
0x18008addc  movzx   edx, word ptr [rsi+2]
0x18008ade0  mov     eax, 0CDh
0x18008ade5  cmp     dx, ax
0x18008ade8  jb      short loc_18008ADFD
0x18008adea  lea     r8, [rsi+8]
0x18008adee  lea     rcx, [rsp+0A00h+var_9C0]
0x18008adf3  call    yy_destructor
0x18008adf8  mov     rcx, [rsp+0A00h+var_9A8]
0x18008adfd  sub     rsi, 18h
0x18008ae01  cmp     rsi, rcx
0x18008ae04  ja      short loc_18008ADDC
0x18008ae06  lea     rax, [rsp+0A00h+var_9A0]
0x18008ae0b  cmp     rcx, rax
0x18008ae0e  jz      short loc_18008AE15
0x18008ae10  call    sqlite3_free
0x18008ae15  cmp     byte ptr [rdi+67h], 0
0x18008ae19  jz      short loc_18008AE22
0x18008ae1b  mov     dword ptr [rbx+18h], 7
0x18008ae22  mov     rax, [rbx+8]
0x18008ae26  test    rax, rax
0x18008ae29  jnz     short loc_18008AE54
0x18008ae2b  mov     ecx, [rbx+18h]
0x18008ae2e  xor     esi, esi
0x18008ae30  test    ecx, ecx
0x18008ae32  jz      short loc_18008AE72
0x18008ae34  cmp     ecx, 65h ; 'e'
0x18008ae37  jz      short loc_18008AE72
0x18008ae39  call    sqlite3ErrStr
0x18008ae3e  mov     r8, rax
0x18008ae41  lea     rdx, aS_7; "%s"
0x18008ae48  mov     rcx, rdi
0x18008ae4b  call    sqlite3MPrintf
0x18008ae50  mov     [rbx+8], rax
0x18008ae54  mov     r9, [rbx+158h]
0x18008ae5b  lea     rdx, aSInS; "%s in \"%s\""
0x18008ae62  mov     ecx, [rbx+18h]
0x18008ae65  mov     r8, rax
0x18008ae68  call    sqlite3_log
0x18008ae6d  mov     esi, 1
0x18008ae72  mov     rcx, [rbx+190h]
0x18008ae79  mov     [rbx+158h], r14
0x18008ae80  call    sqlite3_free
0x18008ae85  mov     rdx, [rbx+160h]
0x18008ae8c  test    rdx, rdx
0x18008ae8f  jz      short loc_18008AEB2
0x18008ae91  cmp     byte ptr [rbx+134h], 0
0x18008ae98  jnz     short loc_18008AEB2
0x18008ae9a  cmp     qword ptr [rdi+308h], 0
0x18008aea2  jnz     short loc_18008AEAA
0x18008aea4  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x18008aea8  jnz     short loc_18008AEB2
0x18008aeaa  mov     rcx, rdi
0x18008aead  call    deleteTable
0x18008aeb2  mov     rdx, [rbx+170h]
0x18008aeb9  test    rdx, rdx
0x18008aebc  jz      short loc_18008AECF
0x18008aebe  cmp     byte ptr [rbx+134h], 2
0x18008aec5  jnb     short loc_18008AECF
0x18008aec7  mov     rcx, rdi
0x18008aeca  call    sqlite3DeleteTrigger
0x18008aecf  mov     rdx, [rbx+148h]
0x18008aed6  test    rdx, rdx
0x18008aed9  jz      short loc_18008AEE3
0x18008aedb  mov     rcx, rdi
0x18008aede  call    sqlite3DbNNFreeNN
0x18008aee3  mov     [rdi+160h], r13
0x18008aeea  mov     eax, esi
0x18008aeec  mov     rcx, [rbp+900h+var_40]
0x18008aef3  xor     rcx, rsp; StackCookie
0x18008aef6  call    __security_check_cookie
0x18008aefb  mov     rbx, [rsp+0A00h+arg_10]
0x18008af03  add     rsp, 9D0h
0x18008af0a  pop     r15
0x18008af0c  pop     r14
0x18008af0e  pop     r13
0x18008af10  pop     r12
0x18008af12  pop     rdi
0x18008af13  pop     rsi
0x18008af14  pop     rbp
0x18008af15  retn
```
