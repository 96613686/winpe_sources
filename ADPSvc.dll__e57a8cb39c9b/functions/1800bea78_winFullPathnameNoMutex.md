# winFullPathnameNoMutex

- ea: `0x1800bea78`
- end: `0x1800bec3e`
- name: `winFullPathnameNoMutex`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800be9f0`

## callees

- `0x180080cc8`
- `0x1800a98a0`
- `0x1800abbf0`
- `0x1800bea78`
- `0x1800bf47c`
- `0x1800c0c30`
- `0x1800c0f54`
- `0x1800ca010`

## string_xrefs

- `0x1800beb5e`: `winFullPathname1`
- `0x1800bebe3`: `winFullPathname2`

## pseudocode

```c
__int64 __fastcall winFullPathnameNoMutex(__int64 a1, unsigned __int64 a2, int a3, __int64 a4)
{
  unsigned __int8 *v7; // rbx
  __int64 v8; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  DWORD v13; // eax
  unsigned int v14; // ebp
  __int64 v15; // rsi
  DWORD v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rcx

  v7 = (unsigned __int8 *)a2;
  if ( *(_BYTE *)a2 == 47 )
  {
    if ( (a2 = *(unsigned __int8 *)(a2 + 1), (*((_BYTE *)&qword_1800FB500 + a2) & 2) != 0) && v7[2] == 58
      || (_BYTE)a2 == 92 && v7[2] == 92 && v7[3] == 63 && v7[4] == 92 )
    {
      ++v7;
    }
  }
  if ( sqlite3_data_directory
    && *v7 != 47
    && *v7 != 92
    && ((*((_BYTE *)&qword_1800FB500 + *v7) & 2) == 0 || v7[1] != 58) )
  {
    v8 = *(unsigned int *)(a1 + 8);
    if ( a3 < (int)v8 )
      v8 = (unsigned int)a3;
    sqlite3_snprintf(v8, a4, "%s%c%s");
    return 0;
  }
  v10 = winUtf8ToUnicode(v7, a2, 92);
  v11 = v10;
  if ( !v10 )
    return 3082;
  v12 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))off_18010C060)(v10, 0, 0, 0);
  if ( v12 )
  {
    v14 = v12 + 3;
    v15 = sqlite3MallocZero(2LL * (unsigned int)(v12 + 3));
    if ( v15 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))off_18010C060)(v11, v14, v15, 0) )
      {
        sqlite3_free(v11);
        sqlite3_free(v15);
        v16 = off_18010C078();
        return winLogErrorAtLine(782, v16, (unsigned int)"winFullPathname2", (_DWORD)v7, 52481);
      }
      sqlite3_free(v11);
      v17 = winUnicodeToUtf8(v15);
      sqlite3_free(v15);
      if ( v17 )
      {
        v18 = *(unsigned int *)(a1 + 8);
        if ( a3 < (int)v18 )
          v18 = (unsigned int)a3;
        sqlite3_snprintf(v18, a4, "%s", v17);
        sqlite3_free(v17);
        return 0;
      }
    }
    else
    {
      sqlite3_free(v11);
    }
    return 3082;
  }
  sqlite3_free(v11);
  v13 = off_18010C078();
  return winLogErrorAtLine(782, v13, (unsigned int)"winFullPathname1", (_DWORD)v7, 52468);
}

```

## disassembly

```asm
0x1800bea78  push    rbx
0x1800bea7a  push    rbp
0x1800bea7b  push    rsi
0x1800bea7c  push    rdi
0x1800bea7d  push    r13
0x1800bea7f  push    r14
0x1800bea81  push    r15
0x1800bea83  sub     rsp, 30h
0x1800bea87  cmp     byte ptr [rdx], 2Fh ; '/'
0x1800bea8a  mov     r14d, r8d
0x1800bea8d  mov     r13, rcx
0x1800bea90  mov     r8d, 5Ch ; '\'
0x1800bea96  lea     rcx, qword_1800FB500
0x1800bea9d  mov     r15, r9
0x1800beaa0  mov     rbx, rdx
0x1800beaa3  jnz     short loc_1800BEACF
0x1800beaa5  movzx   edx, byte ptr [rdx+1]
0x1800beaa9  test    byte ptr [rdx+rcx], 2
0x1800beaad  jz      short loc_1800BEAB5
0x1800beaaf  cmp     byte ptr [rbx+2], 3Ah ; ':'
0x1800beab3  jz      short loc_1800BEACC
0x1800beab5  cmp     dl, r8b
0x1800beab8  jnz     short loc_1800BEACF
0x1800beaba  cmp     [rbx+2], r8b
0x1800beabe  jnz     short loc_1800BEACF
0x1800beac0  cmp     byte ptr [rbx+3], 3Fh ; '?'
0x1800beac4  jnz     short loc_1800BEACF
0x1800beac6  cmp     [rbx+4], r8b
0x1800beaca  jnz     short loc_1800BEACF
0x1800beacc  inc     rbx
0x1800beacf  mov     r9, cs:sqlite3_data_directory
0x1800bead6  test    r9, r9
0x1800bead9  jz      short loc_1800BEB1F
0x1800beadb  cmp     byte ptr [rbx], 2Fh ; '/'
0x1800beade  jz      short loc_1800BEB1F
0x1800beae0  cmp     [rbx], r8b
0x1800beae3  jz      short loc_1800BEB1F
0x1800beae5  movzx   eax, byte ptr [rbx]
0x1800beae8  test    byte ptr [rax+rcx], 2
0x1800beaec  jz      short loc_1800BEAF4
0x1800beaee  cmp     byte ptr [rbx+1], 3Ah ; ':'
0x1800beaf2  jz      short loc_1800BEB1F
0x1800beaf4  mov     ecx, [r13+8]
0x1800beaf8  mov     rdx, r15
0x1800beafb  cmp     r14d, ecx
0x1800beafe  mov     [rsp+68h+var_40], rbx
0x1800beb03  mov     [rsp+68h+var_48], r8d
0x1800beb08  lea     r8, aSCS; "%s%c%s"
0x1800beb0f  cmovl   ecx, r14d
0x1800beb13  call    sqlite3_snprintf
0x1800beb18  xor     eax, eax
0x1800beb1a  jmp     loc_1800BEBA0
0x1800beb1f  mov     rcx, rbx
0x1800beb22  call    winUtf8ToUnicode
0x1800beb27  mov     rdi, rax
0x1800beb2a  test    rax, rax
0x1800beb2d  jz      short loc_1800BEB9B
0x1800beb2f  mov     rcx, rax
0x1800beb32  xor     r9d, r9d
0x1800beb35  mov     rax, cs:off_18010C060
0x1800beb3c  xor     r8d, r8d
0x1800beb3f  xor     edx, edx
0x1800beb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb46  test    eax, eax
0x1800beb48  jnz     short loc_1800BEB7E
0x1800beb4a  mov     rcx, rdi
0x1800beb4d  call    sqlite3_free
0x1800beb52  mov     rax, cs:off_18010C078
0x1800beb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb5e  lea     r8, aWinfullpathnam; "winFullPathname1"
0x1800beb65  mov     [rsp+68h+var_48], 0CCF4h
0x1800beb6d  mov     r9, rbx
0x1800beb70  mov     edx, eax
0x1800beb72  mov     ecx, 30Eh
0x1800beb77  call    winLogErrorAtLine
0x1800beb7c  jmp     short loc_1800BEBA0
0x1800beb7e  lea     ebp, [rax+3]
0x1800beb81  mov     ecx, ebp
0x1800beb83  add     rcx, rcx; Size
0x1800beb86  call    sqlite3MallocZero
0x1800beb8b  mov     rsi, rax
0x1800beb8e  mov     rcx, rdi
0x1800beb91  test    rax, rax
0x1800beb94  jnz     short loc_1800BEBAF
0x1800beb96  call    sqlite3_free
0x1800beb9b  mov     eax, 0C0Ah
0x1800beba0  add     rsp, 30h
0x1800beba4  pop     r15
0x1800beba6  pop     r14
0x1800beba8  pop     r13
0x1800bebaa  pop     rdi
0x1800bebab  pop     rsi
0x1800bebac  pop     rbp
0x1800bebad  pop     rbx
0x1800bebae  retn
0x1800bebaf  mov     rax, cs:off_18010C060
0x1800bebb6  xor     r9d, r9d
0x1800bebb9  mov     r8, rsi
0x1800bebbc  mov     edx, ebp
0x1800bebbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebc3  mov     rcx, rdi
0x1800bebc6  test    eax, eax
0x1800bebc8  jnz     short loc_1800BEBF7
0x1800bebca  call    sqlite3_free
0x1800bebcf  mov     rcx, rsi
0x1800bebd2  call    sqlite3_free
0x1800bebd7  mov     rax, cs:off_18010C078
0x1800bebde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebe3  lea     r8, aWinfullpathnam_0; "winFullPathname2"
0x1800bebea  mov     [rsp+68h+var_48], 0CD01h
0x1800bebf2  jmp     loc_1800BEB6D
0x1800bebf7  call    sqlite3_free
0x1800bebfc  mov     rcx, rsi
0x1800bebff  call    winUnicodeToUtf8
0x1800bec04  mov     rcx, rsi
0x1800bec07  mov     rbx, rax
0x1800bec0a  call    sqlite3_free
0x1800bec0f  test    rbx, rbx
0x1800bec12  jz      short loc_1800BEB9B
0x1800bec14  mov     ecx, [r13+8]
0x1800bec18  lea     r8, aS_7; "%s"
0x1800bec1f  cmp     r14d, ecx
0x1800bec22  mov     r9, rbx
0x1800bec25  mov     rdx, r15
0x1800bec28  cmovl   ecx, r14d
0x1800bec2c  call    sqlite3_snprintf
0x1800bec31  mov     rcx, rbx
0x1800bec34  call    sqlite3_free
0x1800bec39  jmp     loc_1800BEB18
```
