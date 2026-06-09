# sqlite3CreateFunc

- ea: `0x18000ba34`
- end: `0x18000bd3c`
- name: `sqlite3CreateFunc`
- size: `776`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000b670`
- `0x18000b850`
- `0x18000ba34`
- `0x180086b54`
- `0x18008dac0`

## callees

- `0x180005810`
- `0x18000ba34`
- `0x18000cc50`
- `0x18004a4c0`
- `0x18005cf6c`
- `0x180060134`

## string_xrefs

- `0x18000bd04`: `unable to delete/modify user-function due to active statements`

## pseudocode

```c
__int64 __fastcall sqlite3CreateFunc(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11)
{
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r10
  int v20; // r13d
  int v21; // ebx
  int v22; // r13d
  char *Function; // rax
  __int64 v24; // r9
  __int64 i; // rax
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-88h]
  int v30; // [rsp+20h] [rbp-88h]

  if ( !a2 )
    return sqlite3ReportError(21, 183007, "misuse");
  v15 = a6;
  if ( a6 )
  {
    if ( a8 )
      return sqlite3ReportError(21, 183007, "misuse");
  }
  if ( (a8 == 0) != (a7 == 0) || (a9 == 0) != (a10 == 0) || a3 + 1 > 0x80 || (int)sqlite3Strlen30(a2, a7, a9) > 255 )
    return sqlite3ReportError(21, 183007, "misuse");
  v20 = a4 & 0x3380800;
  v21 = a4 & 7;
  v22 = v20 ^ 0x200000;
  if ( v21 == 1 || v21 == 2 || v21 == 3 )
  {
LABEL_10:
    LOBYTE(v18) = v21;
    LOBYTE(v29) = 0;
    Function = (char *)sqlite3FindFunction(a1, a2, a3, v18, v29);
    if ( Function && (*((_DWORD *)Function + 1) & 3) == v21 && *Function == a3 )
    {
      if ( *(_DWORD *)(a1 + 216) )
      {
        sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify user-function due to active statements", v24);
        return 5;
      }
      for ( i = *(_QWORD *)(a1 + 8); i; i = *(_QWORD *)(i + 16) )
      {
        *(_DWORD *)(i + 200) &= ~2u;
        *(_DWORD *)(i + 200) |= 1u;
      }
    }
    else if ( !a6 && !a8 )
    {
      return 0;
    }
    LOBYTE(v24) = v21;
    LOBYTE(v30) = 1;
    v26 = sqlite3FindFunction(a1, a2, a3, v24, v30);
    v27 = v26;
    if ( !v26 )
      return 7;
    functionDestroy(a1, v26);
    if ( a11 )
      ++*a11;
    *(_DWORD *)(v27 + 4) &= 3u;
    *(_DWORD *)(v27 + 4) |= v22;
    *(_QWORD *)(v27 + 40) = a9;
    if ( !a6 )
      v15 = a7;
    *(_QWORD *)(v27 + 48) = a10;
    *(_QWORD *)(v27 + 24) = v15;
    *(_QWORD *)(v27 + 8) = a5;
    *(_QWORD *)(v27 + 64) = a11;
    *(_QWORD *)(v27 + 32) = a8;
    *(_BYTE *)v27 = a3;
    return 0;
  }
  if ( v21 == 4 )
  {
    v21 = 2;
    goto LABEL_10;
  }
  if ( v21 != 5 )
  {
    v21 = 1;
    goto LABEL_10;
  }
  result = sqlite3CreateFunc(a1, a2, a3, (v22 | 1) ^ 0x200000u, a5, a6, v16, a8, v17, v19, (__int64)a11);
  if ( !(_DWORD)result )
  {
    result = sqlite3CreateFunc(a1, a2, a3, (v22 | 2) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
    if ( !(_DWORD)result )
    {
      v21 = 3;
      goto LABEL_10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ba34  push    rbx
0x18000ba36  push    rbp
0x18000ba37  push    rsi
0x18000ba38  push    rdi
0x18000ba39  push    r12
0x18000ba3b  push    r13
0x18000ba3d  push    r14
0x18000ba3f  push    r15
0x18000ba41  sub     rsp, 68h
0x18000ba45  mov     ebx, r9d
0x18000ba48  mov     r14d, r8d
0x18000ba4b  mov     r15, rdx
0x18000ba4e  mov     rsi, rcx
0x18000ba51  test    rdx, rdx
0x18000ba54  jz      loc_18000BCDA
0x18000ba5a  mov     rdi, [rsp+0A8h+arg_28]
0x18000ba62  mov     rbp, [rsp+0A8h+arg_38]
0x18000ba6a  test    rdi, rdi
0x18000ba6d  jnz     loc_18000BCD1
0x18000ba73  mov     rdx, [rsp+0A8h+arg_30]
0x18000ba7b  xor     ecx, ecx
0x18000ba7d  test    rdx, rdx
0x18000ba80  setz    cl
0x18000ba83  xor     eax, eax
0x18000ba85  test    rbp, rbp
0x18000ba88  setz    al
0x18000ba8b  cmp     eax, ecx
0x18000ba8d  jnz     loc_18000BCDA
0x18000ba93  mov     r8, [rsp+0A8h+arg_40]
0x18000ba9b  xor     ecx, ecx
0x18000ba9d  mov     r10, [rsp+0A8h+arg_48]
0x18000baa5  test    r8, r8
0x18000baa8  setz    cl
0x18000baab  xor     eax, eax
0x18000baad  test    r10, r10
0x18000bab0  setz    al
0x18000bab3  cmp     ecx, eax
0x18000bab5  jnz     loc_18000BCDA
0x18000babb  lea     eax, [r14+1]
0x18000babf  cmp     eax, 80h
0x18000bac4  ja      loc_18000BCDA
0x18000baca  mov     rcx, r15
0x18000bacd  call    sqlite3Strlen30
0x18000bad2  cmp     eax, 0FFh
0x18000bad7  jg      loc_18000BCDA
0x18000badd  mov     r12, [rsp+0A8h+arg_50]
0x18000bae5  mov     r13d, ebx
0x18000bae8  and     r13d, 3380800h
0x18000baef  and     ebx, 7
0x18000baf2  mov     r11d, 200000h
0x18000baf8  mov     ecx, ebx
0x18000bafa  xor     r13d, r11d
0x18000bafd  sub     ecx, 1
0x18000bb00  jz      short loc_18000BB10
0x18000bb02  sub     ecx, 1
0x18000bb05  jz      short loc_18000BB10
0x18000bb07  sub     ecx, 1
0x18000bb0a  jnz     loc_18000BC04
0x18000bb10  mov     r9b, bl
0x18000bb13  mov     byte ptr [rsp+0A8h+var_88], 0
0x18000bb18  mov     r8d, r14d
0x18000bb1b  mov     rdx, r15
0x18000bb1e  mov     rcx, rsi
0x18000bb21  call    sqlite3FindFunction
0x18000bb26  test    rax, rax
0x18000bb29  jz      loc_18000BD1C
0x18000bb2f  mov     ecx, [rax+4]
0x18000bb32  and     ecx, 3
0x18000bb35  cmp     ecx, ebx
0x18000bb37  jnz     loc_18000BD1C
0x18000bb3d  movsx   eax, byte ptr [rax]
0x18000bb40  cmp     eax, r14d
0x18000bb43  jnz     loc_18000BD1C
0x18000bb49  cmp     dword ptr [rsi+0D8h], 0
0x18000bb50  jnz     loc_18000BCFF
0x18000bb56  mov     rax, [rsi+8]
0x18000bb5a  jmp     short loc_18000BB6E
0x18000bb5c  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x18000bb63  or      dword ptr [rax+0C8h], 1
0x18000bb6a  mov     rax, [rax+10h]
0x18000bb6e  test    rax, rax
0x18000bb71  jnz     short loc_18000BB5C
0x18000bb73  mov     r9b, bl
0x18000bb76  mov     byte ptr [rsp+0A8h+var_88], 1
0x18000bb7b  mov     r8d, r14d
0x18000bb7e  mov     rdx, r15
0x18000bb81  mov     rcx, rsi
0x18000bb84  call    sqlite3FindFunction
0x18000bb89  mov     rbx, rax
0x18000bb8c  test    rax, rax
0x18000bb8f  jnz     short loc_18000BBA5
0x18000bb91  lea     eax, [rbx+7]
0x18000bb94  add     rsp, 68h
0x18000bb98  pop     r15
0x18000bb9a  pop     r14
0x18000bb9c  pop     r13
0x18000bb9e  pop     r12
0x18000bba0  pop     rdi
0x18000bba1  pop     rsi
0x18000bba2  pop     rbp
0x18000bba3  pop     rbx
0x18000bba4  retn
0x18000bba5  mov     rdx, rbx
0x18000bba8  mov     rcx, rsi
0x18000bbab  call    functionDestroy
0x18000bbb0  test    r12, r12
0x18000bbb3  jnz     loc_18000BD33
0x18000bbb9  and     dword ptr [rbx+4], 3
0x18000bbbd  mov     rax, [rsp+0A8h+arg_40]
0x18000bbc5  or      [rbx+4], r13d
0x18000bbc9  mov     [rbx+28h], rax
0x18000bbcd  test    rdi, rdi
0x18000bbd0  mov     rax, [rsp+0A8h+arg_48]
0x18000bbd8  cmovz   rdi, [rsp+0A8h+arg_30]
0x18000bbe1  mov     [rbx+30h], rax
0x18000bbe5  mov     rax, [rsp+0A8h+arg_20]
0x18000bbed  mov     [rbx+18h], rdi
0x18000bbf1  mov     [rbx+8], rax
0x18000bbf5  mov     [rbx+40h], r12
0x18000bbf9  mov     [rbx+20h], rbp
0x18000bbfd  mov     [rbx], r14b
0x18000bc00  xor     eax, eax
0x18000bc02  jmp     short loc_18000BB94
0x18000bc04  sub     ecx, 1
0x18000bc07  jnz     short loc_18000BC11
0x18000bc09  lea     ebx, [rcx+2]
0x18000bc0c  jmp     loc_18000BB10
0x18000bc11  cmp     ecx, 1
0x18000bc14  jnz     loc_18000BCF5
0x18000bc1a  mov     rax, [rsp+0A8h+arg_20]
0x18000bc22  mov     r9d, r13d
0x18000bc25  mov     [rsp+0A8h+var_58], r12
0x18000bc2a  or      r9d, ecx
0x18000bc2d  mov     [rsp+0A8h+var_60], r10
0x18000bc32  xor     r9d, r11d
0x18000bc35  mov     [rsp+0A8h+var_68], r8
0x18000bc3a  mov     rcx, rsi
0x18000bc3d  mov     [rsp+0A8h+var_70], rbp
0x18000bc42  mov     r8d, r14d
0x18000bc45  mov     [rsp+0A8h+var_78], rdx
0x18000bc4a  mov     rdx, r15
0x18000bc4d  mov     [rsp+0A8h+var_80], rdi
0x18000bc52  mov     [rsp+0A8h+var_88], rax
0x18000bc57  call    sqlite3CreateFunc
0x18000bc5c  test    eax, eax
0x18000bc5e  jnz     loc_18000BB94
0x18000bc64  mov     rax, [rsp+0A8h+arg_48]
0x18000bc6c  mov     r9d, r13d
0x18000bc6f  mov     [rsp+0A8h+var_58], r12
0x18000bc74  or      r9d, 2
0x18000bc78  mov     [rsp+0A8h+var_60], rax
0x18000bc7d  btc     r9d, 15h
0x18000bc82  mov     rax, [rsp+0A8h+arg_40]
0x18000bc8a  mov     r8d, r14d
0x18000bc8d  mov     [rsp+0A8h+var_68], rax
0x18000bc92  mov     rdx, r15
0x18000bc95  mov     rax, [rsp+0A8h+arg_30]
0x18000bc9d  mov     rcx, rsi
0x18000bca0  mov     [rsp+0A8h+var_70], rbp
0x18000bca5  mov     [rsp+0A8h+var_78], rax
0x18000bcaa  mov     rax, [rsp+0A8h+arg_20]
0x18000bcb2  mov     [rsp+0A8h+var_80], rdi
0x18000bcb7  mov     [rsp+0A8h+var_88], rax
0x18000bcbc  call    sqlite3CreateFunc
0x18000bcc1  test    eax, eax
0x18000bcc3  jnz     loc_18000BB94
0x18000bcc9  lea     ebx, [rax+3]
0x18000bccc  jmp     loc_18000BB10
0x18000bcd1  test    rbp, rbp
0x18000bcd4  jz      loc_18000BA73
0x18000bcda  lea     r8, aMisuse; "misuse"
0x18000bce1  mov     edx, 2CADFh
0x18000bce6  mov     ecx, 15h
0x18000bceb  call    sqlite3ReportError
0x18000bcf0  jmp     loc_18000BB94
0x18000bcf5  mov     ebx, 1
0x18000bcfa  jmp     loc_18000BB10
0x18000bcff  mov     ebx, 5
0x18000bd04  lea     r8, aUnableToDelete_0; "unable to delete/modify user-function d"...
0x18000bd0b  mov     edx, ebx
0x18000bd0d  mov     rcx, rsi
0x18000bd10  call    sqlite3ErrorWithMsg
0x18000bd15  mov     eax, ebx
0x18000bd17  jmp     loc_18000BB94
0x18000bd1c  test    rdi, rdi
0x18000bd1f  jnz     loc_18000BB73
0x18000bd25  test    rbp, rbp
0x18000bd28  jnz     loc_18000BB73
0x18000bd2e  jmp     loc_18000BC00
0x18000bd33  inc     dword ptr [r12]
0x18000bd37  jmp     loc_18000BBB9
```
