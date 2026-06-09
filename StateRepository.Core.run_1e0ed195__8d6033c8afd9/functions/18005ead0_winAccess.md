# winAccess

- ea: `0x18005ead0`
- end: `0x18005ec34`
- name: `winAccess`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003e50`

## callees

- `0x1800061e4`
- `0x18000aac0`
- `0x18004e684`
- `0x18004e8b4`
- `0x1800577f8`
- `0x18005ead0`
- `0x180068880`
- `0x18009a010`

## string_xrefs

- `0x18005eba2`: `winAccess`

## pseudocode

```c
__int64 __fastcall winAccess(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  int v6; // esi
  __int64 v7; // r14
  int v9; // edi
  int v10; // r13d
  int v11; // esi
  int v12; // ebx
  unsigned int v13; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v15; // [rsp+38h] [rbp-38h] BYREF
  __int128 v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-18h]

  v14 = 0;
  v6 = a2;
  if ( a2 )
  {
    v7 = winUtf8ToUnicode(a2);
    if ( !v7 )
      return 3082;
    v13 = 0;
    v15 = 0;
    v17 = 0;
    v16 = 0;
    do
    {
      v9 = ((__int64 (__fastcall *)(__int64, _QWORD, __int128 *))off_1800B3018)(v7, 0, &v15);
      if ( v9 )
      {
        if ( a3 || HIDWORD(v16) || (v11 = -1, v17) )
          v11 = v15;
        goto LABEL_15;
      }
    }
    while ( (unsigned int)winRetryIoerr(&v13, &v14) );
    winLogIoerr(v13, 52247);
    v10 = v14;
    if ( (unsigned int)(v14 - 2) > 1 )
    {
      sqlite3_free(v7);
      return winLogErrorAtLine(3338, v10, (unsigned int)"winAccess", v6, 52251);
    }
    v11 = -1;
LABEL_15:
    sqlite3_free(v7);
    if ( !a3 )
      goto LABEL_18;
    v12 = a3 - 1;
    if ( !v12 )
    {
      v9 = v11 != -1 && (v11 & 1) == 0;
      goto LABEL_19;
    }
    if ( v12 == 1 )
LABEL_18:
      v9 = v11 != -1;
LABEL_19:
    *a4 = v9;
    return 0;
  }
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x18005ead0  mov     [rsp-28h+arg_0], rbx
0x18005ead5  mov     [rsp-28h+arg_10], rsi
0x18005eada  push    rbp
0x18005eadb  push    rdi
0x18005eadc  push    r13
0x18005eade  push    r14
0x18005eae0  push    r15
0x18005eae2  mov     rbp, rsp
0x18005eae5  sub     rsp, 70h
0x18005eae9  mov     rax, cs:__security_cookie
0x18005eaf0  xor     rax, rsp
0x18005eaf3  mov     [rbp+var_10], rax
0x18005eaf7  mov     [rbp+var_3C], 0
0x18005eafe  mov     r15, r9
0x18005eb01  mov     ebx, r8d
0x18005eb04  mov     rsi, rdx
0x18005eb07  test    rdx, rdx
0x18005eb0a  jnz     short loc_18005EB14
0x18005eb0c  mov     [r9], edx
0x18005eb0f  jmp     loc_18005EBF7
0x18005eb14  mov     rcx, rsi
0x18005eb17  call    winUtf8ToUnicode
0x18005eb1c  mov     r14, rax
0x18005eb1f  test    rax, rax
0x18005eb22  jnz     short loc_18005EB2E
0x18005eb24  mov     eax, 0C0Ah
0x18005eb29  jmp     loc_18005EBF9
0x18005eb2e  xorps   xmm0, xmm0
0x18005eb31  mov     [rbp+var_40], 0
0x18005eb38  xor     eax, eax
0x18005eb3a  movups  [rbp+var_38], xmm0
0x18005eb3e  mov     [rbp+var_18], eax
0x18005eb41  movups  [rbp+var_28], xmm0
0x18005eb45  mov     rax, cs:off_1800B3018
0x18005eb4c  lea     r8, [rbp+var_38]
0x18005eb50  xor     edx, edx
0x18005eb52  mov     rcx, r14
0x18005eb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb5a  or      r13d, 0FFFFFFFFh
0x18005eb5e  mov     edi, eax
0x18005eb60  test    eax, eax
0x18005eb62  jnz     short loc_18005EBC1
0x18005eb64  lea     rdx, [rbp+var_3C]
0x18005eb68  lea     rcx, [rbp+var_40]
0x18005eb6c  call    winRetryIoerr
0x18005eb71  test    eax, eax
0x18005eb73  jnz     short loc_18005EB45
0x18005eb75  mov     ecx, [rbp+var_40]
0x18005eb78  mov     edx, 0CC17h
0x18005eb7d  call    winLogIoerr
0x18005eb82  mov     r13d, [rbp+var_3C]
0x18005eb86  lea     eax, [r13-2]
0x18005eb8a  cmp     eax, 1
0x18005eb8d  jbe     short loc_18005EBB8
0x18005eb8f  mov     rcx, r14
0x18005eb92  call    sqlite3_free
0x18005eb97  mov     r9, rsi
0x18005eb9a  mov     [rsp+70h+var_50], 0CC1Bh
0x18005eba2  lea     r8, aWinaccess; "winAccess"
0x18005eba9  mov     edx, r13d
0x18005ebac  mov     ecx, 0D0Ah
0x18005ebb1  call    winLogErrorAtLine
0x18005ebb6  jmp     short loc_18005EBF9
0x18005ebb8  or      r13d, 0FFFFFFFFh
0x18005ebbc  mov     esi, r13d
0x18005ebbf  jmp     short loc_18005EBD5
0x18005ebc1  test    ebx, ebx
0x18005ebc3  jnz     short loc_18005EBD2
0x18005ebc5  cmp     dword ptr [rbp+var_28+0Ch], ebx
0x18005ebc8  jnz     short loc_18005EBD2
0x18005ebca  mov     esi, r13d
0x18005ebcd  cmp     [rbp+var_18], ebx
0x18005ebd0  jz      short loc_18005EBD5
0x18005ebd2  mov     esi, dword ptr [rbp+var_38]
0x18005ebd5  mov     rcx, r14
0x18005ebd8  call    sqlite3_free
0x18005ebdd  test    ebx, ebx
0x18005ebdf  jz      short loc_18005EBEB
0x18005ebe1  sub     ebx, 1
0x18005ebe4  jz      short loc_18005EC1E
0x18005ebe6  cmp     ebx, 1
0x18005ebe9  jnz     short loc_18005EBF4
0x18005ebeb  xor     edi, edi
0x18005ebed  cmp     esi, r13d
0x18005ebf0  setnz   dil
0x18005ebf4  mov     [r15], edi
0x18005ebf7  xor     eax, eax
0x18005ebf9  mov     rcx, [rbp+var_10]
0x18005ebfd  xor     rcx, rsp; StackCookie
0x18005ec00  call    __security_check_cookie
0x18005ec05  lea     r11, [rsp+70h+var_s0]
0x18005ec0a  mov     rbx, [r11+30h]
0x18005ec0e  mov     rsi, [r11+40h]
0x18005ec12  mov     rsp, r11
0x18005ec15  pop     r15
0x18005ec17  pop     r14
0x18005ec19  pop     r13
0x18005ec1b  pop     rdi
0x18005ec1c  pop     rbp
0x18005ec1d  retn
0x18005ec1e  cmp     esi, r13d
0x18005ec21  jz      short loc_18005EC30
0x18005ec23  test    sil, 1
0x18005ec27  jnz     short loc_18005EC30
0x18005ec29  mov     edi, 1
0x18005ec2e  jmp     short loc_18005EBF4
0x18005ec30  xor     edi, edi
0x18005ec32  jmp     short loc_18005EBF4
```
