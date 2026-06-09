# winDelete

- ea: `0x180049c50`
- end: `0x180049d5f`
- name: `winDelete`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180037f5c`

## callees

- `0x180036380`
- `0x180037710`
- `0x180041eb0`
- `0x18004909c`
- `0x180049994`
- `0x180049c50`
- `0x1800b0010`

## string_xrefs

- `0x180049d19`: `winDelete`

## pseudocode

```c
__int64 __fastcall winDelete(__int64 a1, __int64 a2)
{
  int v2; // ebp
  __int64 v3; // rsi
  int v4; // edi
  unsigned int v5; // ebx
  int v6; // eax
  DWORD v8; // eax
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax

  v2 = a2;
  v3 = winUtf8ToUnicode(a2);
  if ( !v3 )
    return 3082;
  v4 = 0;
  v5 = 0;
  while ( 1 )
  {
    v6 = ((__int64 (__fastcall *)(__int64))off_1800CE000)(v3);
    if ( v6 == -1 )
      break;
    if ( (v6 & 0x10) != 0 )
      goto LABEL_15;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64))off_1800CDEF8)(v3) )
      goto LABEL_6;
    v8 = off_1800CE078();
    if ( v4 >= dword_1800D0858
      || v8 != 1231
      && ((v9 = v8 - 5, (unsigned int)v9 > 0x3B) || (v10 = 0x804000018000001LL, !_bittest64(&v10, v9)))
      && v8 != 121 )
    {
      v5 = v8;
      goto LABEL_15;
    }
    ++v4;
    sqlite3_win32_sleep((unsigned int)(dword_1800D0C70 * v4));
  }
  v11 = off_1800CE078();
  v5 = v11;
  if ( v11 == 2 || v11 == 3 )
  {
    v5 = 5898;
LABEL_6:
    winLogIoerr((unsigned int)v4, 52189);
    goto LABEL_7;
  }
LABEL_15:
  v5 = winLogErrorAtLine(2570, v5, (unsigned int)"winDelete", v2, 52187);
LABEL_7:
  sqlite3_free(v3);
  return v5;
}

```

## disassembly

```asm
0x180049c50  push    rbx
0x180049c52  push    rbp
0x180049c53  push    rsi
0x180049c54  push    rdi
0x180049c55  sub     rsp, 38h
0x180049c59  mov     rcx, rdx
0x180049c5c  mov     rbp, rdx
0x180049c5f  call    winUtf8ToUnicode
0x180049c64  mov     rsi, rax
0x180049c67  test    rax, rax
0x180049c6a  jz      loc_180049D33
0x180049c70  xor     edi, edi
0x180049c72  xor     ebx, ebx
0x180049c74  mov     rax, cs:off_1800CE000
0x180049c7b  mov     rcx, rsi
0x180049c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c83  cmp     eax, 0FFFFFFFFh
0x180049c86  jz      loc_180049D3D
0x180049c8c  test    al, 10h
0x180049c8e  jnz     short loc_180049D0E
0x180049c90  mov     rax, cs:off_1800CDEF8
0x180049c97  mov     rcx, rsi
0x180049c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c9f  test    eax, eax
0x180049ca1  jz      short loc_180049CC2
0x180049ca3  mov     edx, 0CBDDh
0x180049ca8  mov     ecx, edi
0x180049caa  call    winLogIoerr
0x180049caf  mov     rcx, rsi
0x180049cb2  call    sqlite3_free
0x180049cb7  mov     eax, ebx
0x180049cb9  add     rsp, 38h
0x180049cbd  pop     rdi
0x180049cbe  pop     rsi
0x180049cbf  pop     rbp
0x180049cc0  pop     rbx
0x180049cc1  retn
0x180049cc2  mov     rax, cs:off_1800CE078
0x180049cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cce  cmp     edi, cs:dword_1800D0858
0x180049cd4  jge     short loc_180049D0C
0x180049cd6  cmp     eax, 4CFh
0x180049cdb  jnz     short loc_180049CEF
0x180049cdd  inc     edi
0x180049cdf  mov     ecx, edi
0x180049ce1  imul    ecx, cs:dword_1800D0C70
0x180049ce8  call    sqlite3_win32_sleep
0x180049ced  jmp     short loc_180049C74
0x180049cef  lea     ecx, [rax-5]
0x180049cf2  cmp     ecx, 3Bh ; ';'
0x180049cf5  ja      short loc_180049D07
0x180049cf7  mov     rdx, 804000018000001h
0x180049d01  bt      rdx, rcx
0x180049d05  jb      short loc_180049CDD
0x180049d07  cmp     eax, 79h ; 'y'
0x180049d0a  jz      short loc_180049CDD
0x180049d0c  mov     ebx, eax
0x180049d0e  mov     r9, rbp
0x180049d11  mov     [rsp+58h+var_38], 0CBDBh
0x180049d19  lea     r8, aWindelete; "winDelete"
0x180049d20  mov     edx, ebx
0x180049d22  mov     ecx, 0A0Ah
0x180049d27  call    winLogErrorAtLine
0x180049d2c  mov     ebx, eax
0x180049d2e  jmp     loc_180049CAF
0x180049d33  mov     eax, 0C0Ah
0x180049d38  jmp     loc_180049CB9
0x180049d3d  mov     rax, cs:off_1800CE078
0x180049d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d49  mov     ebx, eax
0x180049d4b  cmp     eax, 2
0x180049d4e  jz      short loc_180049D55
0x180049d50  cmp     eax, 3
0x180049d53  jnz     short loc_180049D0E
0x180049d55  mov     ebx, 170Ah
0x180049d5a  jmp     loc_180049CA3
```
