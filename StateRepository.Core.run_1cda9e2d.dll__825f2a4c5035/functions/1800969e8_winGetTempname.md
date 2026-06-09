# winGetTempname

- ea: `0x1800969e8`
- end: `0x180096cb6`
- name: `winGetTempname`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180003e50`
- `0x1800553f0`

## callees

- `0x180005810`
- `0x180005d14`
- `0x1800061e4`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18000bd44`
- `0x180058b7c`
- `0x180067830`
- `0x180067b40`
- `0x1800969e8`
- `0x18009a010`

## string_xrefs

- `0x180096b50`: `winGetTempname1`
- `0x180096ac2`: `winGetTempname2`
- `0x180096c89`: `winGetTempname4`
- `0x180096bd5`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rsi
  int v5; // r14d
  int v6; // r12d
  __int64 v7; // rbx
  __int64 result; // rax
  int v9; // r15d
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rdi
  DWORD v15; // edx
  const char *v16; // rax
  const char *v17; // rbp
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  const char *v21; // r9
  __int64 v22; // rax
  const char *v23; // r8
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdi
  __int64 v31; // rsi
  DWORD v32; // r9d
  unsigned __int8 v33; // cl
  int v34; // [rsp+20h] [rbp-58h]

  v3 = *(int *)(a1 + 8);
  v5 = v3 + 2;
  v6 = sqlite3Strlen30("etilqs_", a2, a3);
  v7 = sqlite3MallocZero((int)v3 + 2);
  if ( !v7 )
    return 3082;
  v9 = v3 - v6 - 15;
  v10 = sqlite3MutexAlloc(11);
  sqlite3_mutex_enter(v10);
  if ( sqlite3_temp_directory )
  {
    v20 = sqlite3Strlen30(sqlite3_temp_directory, v11, v12);
    if ( v20 > 0 )
    {
      if ( v21[v20 - 1] != 47 && v21[v20 - 1] != 92 )
        ++v20;
      if ( v20 > v9 )
      {
        v22 = sqlite3MutexAlloc(11);
        sqlite3_mutex_leave(v22);
        sqlite3_free(v7);
        v23 = "winGetTempname1";
        v34 = 51539;
        return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
      }
      sqlite3_snprintf((unsigned int)v3, v7, "%s", v21);
    }
    v24 = sqlite3MutexAlloc(11);
    sqlite3_mutex_leave(v24);
  }
  else
  {
    v13 = sqlite3MutexAlloc(11);
    sqlite3_mutex_leave(v13);
    v14 = sqlite3MallocZero(2 * v3);
    if ( !v14 )
    {
LABEL_5:
      sqlite3_free(v7);
      return 3082;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64))off_1800B3108)((unsigned int)v3, v14) )
    {
      sqlite3_free(v14);
      sqlite3_free(v7);
      v15 = off_1800B3078();
      return winLogErrorAtLine(6410, v15, (unsigned int)"winGetTempname2", 0, 51640);
    }
    v16 = (const char *)winUnicodeToUtf8(v14);
    v17 = v16;
    if ( !v16 )
    {
      sqlite3_free(v14);
      goto LABEL_5;
    }
    sqlite3_snprintf((unsigned int)v3, v7, "%s", v16);
    sqlite3_free(v17);
    sqlite3_free(v14);
  }
  v25 = sqlite3Strlen30(v7, v18, v19);
  if ( v25 <= 0 )
    goto LABEL_29;
  if ( *(_BYTE *)(v25 + v7 - 1) != 47 && *(_BYTE *)(v25 + v7 - 1) != 92 )
  {
    if ( v25 + 1 < v9 + 1 )
    {
      *(_WORD *)(v25 + v7) = 92;
      goto LABEL_24;
    }
LABEL_29:
    sqlite3_free(v7);
    v23 = "winGetTempname4";
    v34 = 51690;
    return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
  }
LABEL_24:
  v27 = sqlite3Strlen30(v7, v25, v26);
  if ( v6 + v27 + 17 > v5 )
  {
    sqlite3_free(v7);
    v23 = "winGetTempname5";
    v34 = 51708;
    return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
  }
  sqlite3_snprintf((unsigned int)(v5 - v27 - 16), v7 + v27, "etilqs_");
  v30 = (int)sqlite3Strlen30(v7, v28, v29);
  v31 = 15;
  sqlite3_randomness(15, v7 + v30);
  v32 = off_1800B2FA0();
  do
  {
    v33 = *(_BYTE *)(v7 + v30) + v32;
    v32 >>= 8;
    *(_BYTE *)(v7 + v30++) = aAbcdefghijklmn[v33 % 0x3EuLL];
    --v31;
  }
  while ( v31 );
  *(_WORD *)(v7 + v30) = 0;
  result = 0;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x1800969e8  push    rbx
0x1800969ea  push    rbp
0x1800969eb  push    rsi
0x1800969ec  push    rdi
0x1800969ed  push    r12
0x1800969ef  push    r13
0x1800969f1  push    r14
0x1800969f3  push    r15
0x1800969f5  sub     rsp, 38h
0x1800969f9  movsxd  rsi, dword ptr [rcx+8]
0x1800969fd  mov     r13, rdx
0x180096a00  lea     rcx, aEtilqs; "etilqs_"
0x180096a07  call    sqlite3Strlen30
0x180096a0c  lea     r14d, [rsi+2]
0x180096a10  mov     r12d, eax
0x180096a13  movsxd  rcx, r14d; Size
0x180096a16  call    sqlite3MallocZero
0x180096a1b  mov     rbx, rax
0x180096a1e  test    rax, rax
0x180096a21  jnz     short loc_180096A2D
0x180096a23  mov     eax, 0C0Ah
0x180096a28  jmp     loc_180096CA5
0x180096a2d  mov     r15d, esi
0x180096a30  mov     edi, 0Bh
0x180096a35  sub     r15d, r12d
0x180096a38  mov     ecx, edi
0x180096a3a  add     r15d, 0FFFFFFF1h
0x180096a3e  call    sqlite3MutexAlloc
0x180096a43  mov     rcx, rax
0x180096a46  call    sqlite3_mutex_enter
0x180096a4b  mov     r9, cs:sqlite3_temp_directory
0x180096a52  test    r9, r9
0x180096a55  jnz     loc_180096B13
0x180096a5b  mov     ecx, edi
0x180096a5d  call    sqlite3MutexAlloc
0x180096a62  mov     rcx, rax
0x180096a65  call    sqlite3_mutex_leave
0x180096a6a  mov     rcx, rsi
0x180096a6d  add     rcx, rcx; Size
0x180096a70  call    sqlite3MallocZero
0x180096a75  mov     rdi, rax
0x180096a78  test    rax, rax
0x180096a7b  jnz     short loc_180096A87
0x180096a7d  mov     rcx, rbx
0x180096a80  call    sqlite3_free
0x180096a85  jmp     short loc_180096A23
0x180096a87  mov     rax, cs:off_1800B3108
0x180096a8e  mov     rdx, rdi
0x180096a91  mov     ecx, esi
0x180096a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096a98  mov     rcx, rdi
0x180096a9b  test    eax, eax
0x180096a9d  jnz     short loc_180096AD3
0x180096a9f  call    sqlite3_free
0x180096aa4  mov     rcx, rbx
0x180096aa7  call    sqlite3_free
0x180096aac  mov     rax, cs:off_1800B3078
0x180096ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096ab8  mov     edx, eax
0x180096aba  mov     [rsp+78h+var_58], 0C9B8h
0x180096ac2  lea     r8, aWingettempname_2; "winGetTempname2"
0x180096ac9  mov     ecx, 190Ah
0x180096ace  jmp     loc_180096C9D
0x180096ad3  call    winUnicodeToUtf8
0x180096ad8  mov     rbp, rax
0x180096adb  test    rax, rax
0x180096ade  jz      short loc_180096B06
0x180096ae0  mov     r9, rax
0x180096ae3  lea     r8, aS_7; "%s"
0x180096aea  mov     rdx, rbx
0x180096aed  mov     ecx, esi
0x180096aef  call    sqlite3_snprintf
0x180096af4  mov     rcx, rbp
0x180096af7  call    sqlite3_free
0x180096afc  mov     rcx, rdi
0x180096aff  call    sqlite3_free
0x180096b04  jmp     short loc_180096B84
0x180096b06  mov     rcx, rdi
0x180096b09  call    sqlite3_free
0x180096b0e  jmp     loc_180096A7D
0x180096b13  mov     rcx, r9
0x180096b16  call    sqlite3Strlen30
0x180096b1b  test    eax, eax
0x180096b1d  jle     short loc_180096B75
0x180096b1f  movsxd  rcx, eax
0x180096b22  cmp     byte ptr [rcx+r9-1], 2Fh ; '/'
0x180096b28  jz      short loc_180096B34
0x180096b2a  cmp     byte ptr [rcx+r9-1], 5Ch ; '\'
0x180096b30  jz      short loc_180096B34
0x180096b32  inc     eax
0x180096b34  cmp     eax, r15d
0x180096b37  jle     short loc_180096B64
0x180096b39  mov     ecx, edi
0x180096b3b  call    sqlite3MutexAlloc
0x180096b40  mov     rcx, rax
0x180096b43  call    sqlite3_mutex_leave
0x180096b48  mov     rcx, rbx
0x180096b4b  call    sqlite3_free
0x180096b50  lea     r8, aWingettempname; "winGetTempname1"
0x180096b57  mov     [rsp+78h+var_58], 0C953h
0x180096b5f  jmp     loc_180096C98
0x180096b64  lea     r8, aS_7; "%s"
0x180096b6b  mov     rdx, rbx
0x180096b6e  mov     ecx, esi
0x180096b70  call    sqlite3_snprintf
0x180096b75  mov     ecx, edi
0x180096b77  call    sqlite3MutexAlloc
0x180096b7c  mov     rcx, rax
0x180096b7f  call    sqlite3_mutex_leave
0x180096b84  mov     rcx, rbx
0x180096b87  call    sqlite3Strlen30
0x180096b8c  test    eax, eax
0x180096b8e  jle     loc_180096C81
0x180096b94  movsxd  rdx, eax
0x180096b97  cmp     byte ptr [rdx+rbx-1], 2Fh ; '/'
0x180096b9c  jz      short loc_180096BBA
0x180096b9e  cmp     byte ptr [rdx+rbx-1], 5Ch ; '\'
0x180096ba3  jz      short loc_180096BBA
0x180096ba5  lea     ecx, [rax+1]
0x180096ba8  lea     eax, [r15+1]
0x180096bac  cmp     ecx, eax
0x180096bae  jge     loc_180096C81
0x180096bb4  mov     word ptr [rdx+rbx], 5Ch ; '\'
0x180096bba  mov     rcx, rbx
0x180096bbd  call    sqlite3Strlen30
0x180096bc2  lea     ecx, [rax+11h]
0x180096bc5  add     ecx, r12d
0x180096bc8  cmp     ecx, r14d
0x180096bcb  jle     short loc_180096BE9
0x180096bcd  mov     rcx, rbx
0x180096bd0  call    sqlite3_free
0x180096bd5  lea     r8, aWingettempname_1; "winGetTempname5"
0x180096bdc  mov     [rsp+78h+var_58], 0C9FCh
0x180096be4  jmp     loc_180096C98
0x180096be9  sub     r14d, eax
0x180096bec  movsxd  rdx, eax
0x180096bef  add     rdx, rbx
0x180096bf2  lea     r8, aEtilqs; "etilqs_"
0x180096bf9  lea     ecx, [r14-10h]
0x180096bfd  call    sqlite3_snprintf
0x180096c02  mov     rcx, rbx
0x180096c05  call    sqlite3Strlen30
0x180096c0a  movsxd  rdi, eax
0x180096c0d  mov     esi, 0Fh
0x180096c12  mov     ecx, esi
0x180096c14  lea     rdx, [rbx+rdi]
0x180096c18  call    sqlite3_randomness
0x180096c1d  mov     rax, cs:off_1800B2FA0
0x180096c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c29  mov     r9d, eax
0x180096c2c  mov     cl, r9b
0x180096c2f  mov     rax, 842108421084211h
0x180096c39  add     cl, [rbx+rdi]
0x180096c3c  movzx   r8d, cl
0x180096c40  mul     r8
0x180096c43  mov     eax, r8d
0x180096c46  shr     r9d, 8
0x180096c4a  sub     rax, rdx
0x180096c4d  shr     rax, 1
0x180096c50  add     rax, rdx
0x180096c53  shr     rax, 5
0x180096c57  imul    rax, 3Eh ; '>'
0x180096c5b  sub     r8, rax
0x180096c5e  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x180096c65  mov     al, [r8+rax]
0x180096c69  mov     [rbx+rdi], al
0x180096c6c  inc     rdi
0x180096c6f  sub     rsi, 1
0x180096c73  jnz     short loc_180096C2C
0x180096c75  mov     [rbx+rdi], si
0x180096c79  xor     eax, eax
0x180096c7b  mov     [r13+0], rbx
0x180096c7f  jmp     short loc_180096CA5
0x180096c81  mov     rcx, rbx
0x180096c84  call    sqlite3_free
0x180096c89  lea     r8, aWingettempname_0; "winGetTempname4"
0x180096c90  mov     [rsp+78h+var_58], 0C9EAh
0x180096c98  xor     edx, edx
0x180096c9a  lea     ecx, [rdx+1]
0x180096c9d  xor     r9d, r9d
0x180096ca0  call    winLogErrorAtLine
0x180096ca5  add     rsp, 38h
0x180096ca9  pop     r15
0x180096cab  pop     r14
0x180096cad  pop     r13
0x180096caf  pop     r12
0x180096cb1  pop     rdi
0x180096cb2  pop     rsi
0x180096cb3  pop     rbp
0x180096cb4  pop     rbx
0x180096cb5  retn
```
