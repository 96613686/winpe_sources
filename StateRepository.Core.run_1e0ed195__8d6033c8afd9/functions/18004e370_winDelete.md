# winDelete

- ea: `0x18004e370`
- end: `0x18004e475`
- name: `winDelete`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007e64`

## callees

- `0x1800061e4`
- `0x18000aac0`
- `0x18004e370`
- `0x18004e670`
- `0x18004e684`
- `0x18004e8b4`
- `0x18009a010`

## string_xrefs

- `0x18004e43a`: `winDelete`

## pseudocode

```c
__int64 __fastcall winDelete(__int64 a1, __int64 a2)
{
  int v2; // ebp
  __int64 v3; // rsi
  int v5; // edi
  unsigned int v6; // ebx
  int v7; // eax
  DWORD v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  DWORD v11; // eax

  v2 = a2;
  v3 = winUtf8ToUnicode(a2);
  if ( !v3 )
    return 3082;
  v5 = 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = ((__int64 (__fastcall *)(__int64))off_1800B3000)(v3);
    if ( v7 == -1 )
      break;
    if ( (v7 & 0x10) != 0 )
      goto LABEL_16;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64))off_1800B2EF8)(v3) )
      goto LABEL_18;
    v8 = off_1800B3078();
    if ( v5 >= dword_1800B5618
      || v8 != 1231
      && ((v10 = v8 - 5, (unsigned int)v10 > 0x3B) || (v9 = 0x804000018000001LL, !_bittest64(&v9, v10)))
      && v8 != 121 )
    {
      v6 = v8;
LABEL_16:
      v6 = winLogErrorAtLine(2570, v6, (unsigned int)"winDelete", v2, 52188);
      goto LABEL_19;
    }
    ++v5;
    sqlite3_win32_sleep((unsigned int)(dword_1800B5A30 * v5), v9);
  }
  v11 = off_1800B3078();
  v6 = v11;
  if ( v11 != 2 && v11 != 3 )
    goto LABEL_16;
  v6 = 5898;
LABEL_18:
  winLogIoerr((unsigned int)v5, 52190);
LABEL_19:
  sqlite3_free(v3);
  return v6;
}

```

## disassembly

```asm
0x18004e370  push    rbx
0x18004e372  push    rbp
0x18004e373  push    rsi
0x18004e374  push    rdi
0x18004e375  sub     rsp, 38h
0x18004e379  mov     rcx, rdx
0x18004e37c  mov     rbp, rdx
0x18004e37f  call    winUtf8ToUnicode
0x18004e384  mov     rsi, rax
0x18004e387  test    rax, rax
0x18004e38a  jnz     short loc_18004E396
0x18004e38c  mov     eax, 0C0Ah
0x18004e391  jmp     loc_18004E46C
0x18004e396  xor     edi, edi
0x18004e398  xor     ebx, ebx
0x18004e39a  mov     rax, cs:off_1800B3000
0x18004e3a1  mov     rcx, rsi
0x18004e3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3a9  cmp     eax, 0FFFFFFFFh
0x18004e3ac  jz      short loc_18004E417
0x18004e3ae  test    al, 10h
0x18004e3b0  jnz     short loc_18004E42F
0x18004e3b2  mov     rax, cs:off_1800B2EF8
0x18004e3b9  mov     rcx, rsi
0x18004e3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3c1  test    eax, eax
0x18004e3c3  jnz     loc_18004E456
0x18004e3c9  mov     rax, cs:off_1800B3078
0x18004e3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3d5  cmp     edi, cs:dword_1800B5618
0x18004e3db  jge     short loc_18004E413
0x18004e3dd  cmp     eax, 4CFh
0x18004e3e2  jz      short loc_18004E401
0x18004e3e4  lea     ecx, [rax-5]
0x18004e3e7  cmp     ecx, 3Bh ; ';'
0x18004e3ea  ja      short loc_18004E3FC
0x18004e3ec  mov     rdx, 804000018000001h
0x18004e3f6  bt      rdx, rcx
0x18004e3fa  jb      short loc_18004E401
0x18004e3fc  cmp     eax, 79h ; 'y'
0x18004e3ff  jnz     short loc_18004E413
0x18004e401  inc     edi
0x18004e403  mov     ecx, edi
0x18004e405  imul    ecx, cs:dword_1800B5A30
0x18004e40c  call    sqlite3_win32_sleep
0x18004e411  jmp     short loc_18004E39A
0x18004e413  mov     ebx, eax
0x18004e415  jmp     short loc_18004E42F
0x18004e417  mov     rax, cs:off_1800B3078
0x18004e41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e423  mov     ebx, eax
0x18004e425  cmp     eax, 2
0x18004e428  jz      short loc_18004E451
0x18004e42a  cmp     eax, 3
0x18004e42d  jz      short loc_18004E451
0x18004e42f  mov     r9, rbp
0x18004e432  mov     [rsp+58h+var_38], 0CBDCh
0x18004e43a  lea     r8, aWindelete; "winDelete"
0x18004e441  mov     edx, ebx
0x18004e443  mov     ecx, 0A0Ah
0x18004e448  call    winLogErrorAtLine
0x18004e44d  mov     ebx, eax
0x18004e44f  jmp     short loc_18004E462
0x18004e451  mov     ebx, 170Ah
0x18004e456  mov     edx, 0CBDEh
0x18004e45b  mov     ecx, edi
0x18004e45d  call    winLogIoerr
0x18004e462  mov     rcx, rsi
0x18004e465  call    sqlite3_free
0x18004e46a  mov     eax, ebx
0x18004e46c  add     rsp, 38h
0x18004e470  pop     rdi
0x18004e471  pop     rsi
0x18004e472  pop     rbp
0x18004e473  pop     rbx
0x18004e474  retn
```
