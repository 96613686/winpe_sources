# readJournalHdr

- ea: `0x18007ce18`
- end: `0x18007cfc8`
- name: `readJournalHdr`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180046ccc`
- `0x18007ae78`

## callees

- `0x1800084bc`
- `0x180049508`
- `0x180067ca4`
- `0x180068880`
- `0x18007cde4`
- `0x18007ce18`
- `0x180099808`

## pseudocode

```c
__int64 __fastcall readJournalHdr(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax
  int v8; // r10d
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 result; // rax
  unsigned int v13; // ecx
  __int64 v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // edi
  unsigned int v17; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-34h] BYREF
  char Buf1[8]; // [rsp+28h] [rbp-30h] BYREF

  v7 = journalHdrOffset(a1, a2, a3, a3);
  v9 = v7;
  v10 = v7 + *(unsigned int *)(a1 + 184);
  *(_QWORD *)(a1 + 96) = v7;
  if ( v10 > v11 )
    return 101;
  if ( v8 || v7 != *(_QWORD *)(a1 + 104) )
  {
    result = sqlite3OsRead(*(_QWORD *)(a1 + 80));
    if ( (_DWORD)result )
      return result;
    if ( memcmp_0(Buf1, &qword_1800A7BA8, 8u) )
      return 101;
  }
  v13 = read32bits(*(_QWORD *)(a1 + 80), v9 + 8, a4);
  if ( v13 )
    return v13;
  v13 = read32bits(*(_QWORD *)(a1 + 80), v9 + 12, a1 + 56);
  if ( v13 )
    return v13;
  v13 = read32bits(*(_QWORD *)(a1 + 80), v9 + 16, a5);
  if ( v13 )
    return v13;
  if ( *(_QWORD *)(a1 + 96) )
  {
LABEL_20:
    *(_QWORD *)(a1 + 96) += *(unsigned int *)(a1 + 184);
    return v13;
  }
  v14 = *(_QWORD *)(a1 + 80);
  v17 = 0;
  v18 = 0;
  result = read32bits(v14, v9 + 20, &v18);
  if ( !(_DWORD)result )
  {
    result = read32bits(*(_QWORD *)(a1 + 80), v9 + 24, &v17);
    if ( !(_DWORD)result )
    {
      v15 = v17;
      if ( !v17 )
      {
        v15 = *(_DWORD *)(a1 + 200);
        v17 = v15;
      }
      if ( v15 >= 0x200 )
      {
        v16 = v18;
        if ( v18 >= 0x20 && v15 <= 0x10000 && v18 <= 0x10000 && ((v18 - 1) & v18) == 0 && ((v15 - 1) & v15) == 0 )
        {
          v13 = sqlite3PagerSetPagesize(a1, &v17, 0xFFFFFFFFLL);
          *(_DWORD *)(a1 + 184) = v16;
          goto LABEL_20;
        }
      }
      return 101;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007ce18  mov     [rsp+arg_8], rbx
0x18007ce1d  push    rbp
0x18007ce1e  push    rsi
0x18007ce1f  push    rdi
0x18007ce20  sub     rsp, 40h
0x18007ce24  mov     rax, cs:__security_cookie
0x18007ce2b  xor     rax, rsp
0x18007ce2e  mov     [rsp+58h+var_28], rax
0x18007ce33  mov     rbp, [rsp+58h+arg_20]
0x18007ce3b  mov     rsi, r9
0x18007ce3e  mov     r9, r8
0x18007ce41  mov     r10d, edx
0x18007ce44  mov     rbx, rcx
0x18007ce47  call    journalHdrOffset
0x18007ce4c  mov     ecx, [rbx+0B8h]
0x18007ce52  mov     rdi, rax
0x18007ce55  add     rcx, rax
0x18007ce58  mov     [rbx+60h], rax
0x18007ce5c  cmp     rcx, r9
0x18007ce5f  jg      loc_18007CFA9
0x18007ce65  test    r10d, r10d
0x18007ce68  jnz     short loc_18007CE70
0x18007ce6a  cmp     rax, [rbx+68h]
0x18007ce6e  jz      short loc_18007CEAC
0x18007ce70  mov     rcx, [rbx+50h]
0x18007ce74  lea     rdx, [rsp+58h+Buf1]
0x18007ce79  mov     r9, rdi
0x18007ce7c  mov     r8d, 8
0x18007ce82  call    sqlite3OsRead
0x18007ce87  test    eax, eax
0x18007ce89  jnz     loc_18007CFAE
0x18007ce8f  lea     r8d, [rax+8]; Size
0x18007ce93  lea     rdx, qword_1800A7BA8; Buf2
0x18007ce9a  lea     rcx, [rsp+58h+Buf1]; Buf1
0x18007ce9f  call    memcmp_0
0x18007cea4  test    eax, eax
0x18007cea6  jnz     loc_18007CFA9
0x18007ceac  mov     rcx, [rbx+50h]
0x18007ceb0  lea     rdx, [rdi+8]
0x18007ceb4  mov     r8, rsi
0x18007ceb7  call    read32bits
0x18007cebc  mov     ecx, eax
0x18007cebe  test    eax, eax
0x18007cec0  jnz     loc_18007CFA5
0x18007cec6  mov     rcx, [rbx+50h]
0x18007ceca  lea     r8, [rbx+38h]
0x18007cece  lea     rdx, [rdi+0Ch]
0x18007ced2  call    read32bits
0x18007ced7  mov     ecx, eax
0x18007ced9  test    eax, eax
0x18007cedb  jnz     loc_18007CFA5
0x18007cee1  mov     rcx, [rbx+50h]
0x18007cee5  lea     rdx, [rdi+10h]
0x18007cee9  mov     r8, rbp
0x18007ceec  call    read32bits
0x18007cef1  mov     ecx, eax
0x18007cef3  test    eax, eax
0x18007cef5  jnz     loc_18007CFA5
0x18007cefb  cmp     qword ptr [rbx+60h], 0
0x18007cf00  jnz     loc_18007CF9B
0x18007cf06  mov     rcx, [rbx+50h]
0x18007cf0a  lea     rdx, [rdi+14h]
0x18007cf0e  lea     r8, [rsp+58h+var_34]
0x18007cf13  mov     [rsp+58h+var_38], eax
0x18007cf17  mov     [rsp+58h+var_34], eax
0x18007cf1b  call    read32bits
0x18007cf20  test    eax, eax
0x18007cf22  jnz     loc_18007CFAE
0x18007cf28  mov     rcx, [rbx+50h]
0x18007cf2c  lea     rdx, [rdi+18h]
0x18007cf30  lea     r8, [rsp+58h+var_38]
0x18007cf35  call    read32bits
0x18007cf3a  test    eax, eax
0x18007cf3c  jnz     short loc_18007CFAE
0x18007cf3e  mov     edx, [rsp+58h+var_38]
0x18007cf42  test    edx, edx
0x18007cf44  jnz     short loc_18007CF50
0x18007cf46  mov     edx, [rbx+0C8h]
0x18007cf4c  mov     [rsp+58h+var_38], edx
0x18007cf50  cmp     edx, 200h
0x18007cf56  jb      short loc_18007CFA9
0x18007cf58  mov     edi, [rsp+58h+var_34]
0x18007cf5c  cmp     edi, 20h ; ' '
0x18007cf5f  jb      short loc_18007CFA9
0x18007cf61  mov     eax, 10000h
0x18007cf66  cmp     edx, eax
0x18007cf68  ja      short loc_18007CFA9
0x18007cf6a  cmp     edi, eax
0x18007cf6c  ja      short loc_18007CFA9
0x18007cf6e  lea     eax, [rdi-1]
0x18007cf71  test    edi, eax
0x18007cf73  lea     eax, [rdx-1]
0x18007cf76  setz    cl
0x18007cf79  test    edx, eax
0x18007cf7b  setz    al
0x18007cf7e  test    al, cl
0x18007cf80  jz      short loc_18007CFA9
0x18007cf82  or      r8d, 0FFFFFFFFh
0x18007cf86  lea     rdx, [rsp+58h+var_38]
0x18007cf8b  mov     rcx, rbx
0x18007cf8e  call    sqlite3PagerSetPagesize
0x18007cf93  mov     ecx, eax
0x18007cf95  mov     [rbx+0B8h], edi
0x18007cf9b  mov     eax, [rbx+0B8h]
0x18007cfa1  add     [rbx+60h], rax
0x18007cfa5  mov     eax, ecx
0x18007cfa7  jmp     short loc_18007CFAE
0x18007cfa9  mov     eax, 65h ; 'e'
0x18007cfae  mov     rcx, [rsp+58h+var_28]
0x18007cfb3  xor     rcx, rsp; StackCookie
0x18007cfb6  call    __security_check_cookie
0x18007cfbb  mov     rbx, [rsp+58h+arg_8]
0x18007cfc0  add     rsp, 40h
0x18007cfc4  pop     rdi
0x18007cfc5  pop     rsi
0x18007cfc6  pop     rbp
0x18007cfc7  retn
```
