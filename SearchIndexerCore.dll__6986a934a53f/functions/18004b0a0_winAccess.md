# winAccess

- ea: `0x18004b0a0`
- end: `0x18004b247`
- name: `winAccess`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180035850`

## callees

- `0x180036380`
- `0x180037710`
- `0x180041eb0`
- `0x18004909c`
- `0x180049994`
- `0x18004b0a0`
- `0x1800789c0`
- `0x1800b0010`

## string_xrefs

- `0x18004b1f4`: `winAccess`

## pseudocode

```c
__int64 __fastcall winAccess(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  int v6; // r15d
  __int64 v7; // r14
  int v8; // ebp
  int v9; // esi
  int v10; // edi
  int v11; // ebx
  DWORD v13; // eax
  DWORD v14; // edi
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  _BYTE v17[36]; // [rsp+30h] [rbp-58h] BYREF

  v6 = a2;
  if ( a2 )
  {
    v7 = winUtf8ToUnicode(a2);
    if ( v7 )
    {
      v8 = 0;
      memset(v17, 0, sizeof(v17));
      while ( 1 )
      {
        v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _BYTE *))off_1800CE018)(v7, 0, v17);
        if ( v9 )
        {
          if ( !a3 && !*(_QWORD *)&v17[28] )
            goto LABEL_7;
          v10 = *(_DWORD *)v17;
          goto LABEL_8;
        }
        v13 = off_1800CE078();
        v14 = v13;
        if ( v8 >= dword_1800D0858 )
          break;
        if ( v13 != 1231 )
        {
          v15 = v13 - 5;
          if ( (unsigned int)v15 > 0x3B || (v16 = 0x804000018000001LL, !_bittest64(&v16, v15)) )
          {
            if ( v14 != 121 )
              break;
          }
        }
        ++v8;
        sqlite3_win32_sleep((unsigned int)(dword_1800D0C70 * v8));
      }
      winLogIoerr((unsigned int)v8, 52246);
      if ( v14 - 2 > 1 )
      {
        sqlite3_free(v7);
        return winLogErrorAtLine(3338, v14, (unsigned int)"winAccess", v6, 52250);
      }
LABEL_7:
      v10 = -1;
LABEL_8:
      sqlite3_free(v7);
      if ( !a3 )
        goto LABEL_14;
      v11 = a3 - 1;
      if ( !v11 )
      {
        v9 = v10 != -1 && (v10 & 1) == 0;
        goto LABEL_11;
      }
      if ( v11 == 1 )
LABEL_14:
        v9 = v10 != -1;
LABEL_11:
      *a4 = v9;
      return 0;
    }
    return 3082;
  }
  else
  {
    *a4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18004b0a0  mov     [rsp+arg_0], rbx
0x18004b0a5  mov     [rsp+arg_10], rbp
0x18004b0aa  push    rsi
0x18004b0ab  push    rdi
0x18004b0ac  push    r12
0x18004b0ae  push    r14
0x18004b0b0  push    r15
0x18004b0b2  sub     rsp, 60h
0x18004b0b6  mov     rax, cs:__security_cookie
0x18004b0bd  xor     rax, rsp
0x18004b0c0  mov     [rsp+88h+var_30], rax
0x18004b0c5  mov     r12, r9
0x18004b0c8  mov     ebx, r8d
0x18004b0cb  mov     r15, rdx
0x18004b0ce  test    rdx, rdx
0x18004b0d1  jz      loc_18004B186
0x18004b0d7  mov     rcx, rdx
0x18004b0da  call    winUtf8ToUnicode
0x18004b0df  mov     r14, rax
0x18004b0e2  test    rax, rax
0x18004b0e5  jz      loc_18004B221
0x18004b0eb  xorps   xmm0, xmm0
0x18004b0ee  xor     ebp, ebp
0x18004b0f0  xor     eax, eax
0x18004b0f2  mov     dword ptr [rsp+88h+var_48+10h], eax
0x18004b0f6  movups  [rsp+88h+var_58], xmm0
0x18004b0fb  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x18004b100  mov     rax, cs:off_1800CE018
0x18004b107  lea     r8, [rsp+88h+var_58]
0x18004b10c  xor     edx, edx
0x18004b10e  mov     rcx, r14
0x18004b111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b116  mov     esi, eax
0x18004b118  test    eax, eax
0x18004b11a  jz      short loc_18004B18F
0x18004b11c  test    ebx, ebx
0x18004b11e  jnz     short loc_18004B175
0x18004b120  cmp     dword ptr [rsp+88h+var_48+10h], ebx
0x18004b124  jnz     short loc_18004B175
0x18004b126  cmp     dword ptr [rsp+88h+var_48+0Ch], ebx
0x18004b12a  jnz     short loc_18004B175
0x18004b12c  or      edi, 0FFFFFFFFh
0x18004b12f  mov     rcx, r14
0x18004b132  call    sqlite3_free
0x18004b137  test    ebx, ebx
0x18004b139  jz      short loc_18004B17B
0x18004b13b  sub     ebx, 1
0x18004b13e  jz      loc_18004B22B
0x18004b144  cmp     ebx, 1
0x18004b147  jz      short loc_18004B17B
0x18004b149  mov     [r12], esi
0x18004b14d  xor     eax, eax
0x18004b14f  mov     rcx, [rsp+88h+var_30]
0x18004b154  xor     rcx, rsp; StackCookie
0x18004b157  call    __security_check_cookie
0x18004b15c  lea     r11, [rsp+88h+var_28]
0x18004b161  mov     rbx, [r11+30h]
0x18004b165  mov     rbp, [r11+40h]
0x18004b169  mov     rsp, r11
0x18004b16c  pop     r15
0x18004b16e  pop     r14
0x18004b170  pop     r12
0x18004b172  pop     rdi
0x18004b173  pop     rsi
0x18004b174  retn
0x18004b175  mov     edi, dword ptr [rsp+88h+var_58]
0x18004b179  jmp     short loc_18004B12F
0x18004b17b  xor     esi, esi
0x18004b17d  cmp     edi, 0FFFFFFFFh
0x18004b180  setnz   sil
0x18004b184  jmp     short loc_18004B149
0x18004b186  mov     dword ptr [r9], 0
0x18004b18d  jmp     short loc_18004B14D
0x18004b18f  mov     rax, cs:off_1800CE078
0x18004b196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b19b  cmp     ebp, cs:dword_1800D0858
0x18004b1a1  mov     edi, eax
0x18004b1a3  jge     short loc_18004B1C9
0x18004b1a5  cmp     eax, 4CFh
0x18004b1aa  jz      short loc_18004B20C
0x18004b1ac  add     eax, 0FFFFFFFBh
0x18004b1af  cmp     eax, 3Bh ; ';'
0x18004b1b2  ja      short loc_18004B1C4
0x18004b1b4  mov     rcx, 804000018000001h
0x18004b1be  bt      rcx, rax
0x18004b1c2  jb      short loc_18004B20C
0x18004b1c4  cmp     edi, 79h ; 'y'
0x18004b1c7  jz      short loc_18004B20C
0x18004b1c9  mov     edx, 0CC16h
0x18004b1ce  mov     ecx, ebp
0x18004b1d0  call    winLogIoerr
0x18004b1d5  lea     eax, [rdi-2]
0x18004b1d8  cmp     eax, 1
0x18004b1db  jbe     loc_18004B12C
0x18004b1e1  mov     rcx, r14
0x18004b1e4  call    sqlite3_free
0x18004b1e9  mov     r9, r15
0x18004b1ec  mov     [rsp+88h+var_68], 0CC1Ah
0x18004b1f4  lea     r8, aWinaccess; "winAccess"
0x18004b1fb  mov     edx, edi
0x18004b1fd  mov     ecx, 0D0Ah
0x18004b202  call    winLogErrorAtLine
0x18004b207  jmp     loc_18004B14F
0x18004b20c  inc     ebp
0x18004b20e  mov     ecx, ebp
0x18004b210  imul    ecx, cs:dword_1800D0C70
0x18004b217  call    sqlite3_win32_sleep
0x18004b21c  jmp     loc_18004B100
0x18004b221  mov     eax, 0C0Ah
0x18004b226  jmp     loc_18004B14F
0x18004b22b  cmp     edi, 0FFFFFFFFh
0x18004b22e  jz      short loc_18004B240
0x18004b230  test    dil, 1
0x18004b234  jnz     short loc_18004B240
0x18004b236  mov     esi, 1
0x18004b23b  jmp     loc_18004B149
0x18004b240  xor     esi, esi
0x18004b242  jmp     loc_18004B149
```
