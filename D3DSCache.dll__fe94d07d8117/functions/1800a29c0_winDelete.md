# winDelete

- ea: `0x1800a29c0`
- end: `0x1800a2a9d`
- name: `winDelete`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a4028`

## callees

- `0x180012470`
- `0x1800293d4`
- `0x1800299bc`
- `0x180029cdc`
- `0x1800388f0`
- `0x1800a29c0`
- `0x1800a8010`

## string_xrefs

- `0x1800a2a60`: `winDelete`

## pseudocode

```c
__int64 __fastcall winDelete(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rdi
  int v5; // eax
  DWORD v6; // edx
  unsigned int v7; // ebx
  _DWORD v8[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v9; // [rsp+68h] [rbp+20h] BYREF

  v8[0] = 0;
  v2 = a2;
  v9 = 0;
  v3 = winUtf8ToUnicode(a2);
  if ( !v3 )
    return 3082;
  while ( 1 )
  {
    v5 = ((__int64 (__fastcall *)(__int64))off_1800C4050)(v3);
    if ( v5 == -1 )
    {
      v6 = off_1800C40C8();
      if ( v6 - 2 <= 1 )
      {
        v7 = 5898;
        goto LABEL_12;
      }
LABEL_10:
      v7 = winLogErrorAtLine(2570, v6, (unsigned int)"winDelete", v2, 52092);
      goto LABEL_13;
    }
    if ( (v5 & 0x10) != 0 )
      goto LABEL_7;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64))off_1800C3F48)(v3) )
      break;
    if ( !(unsigned int)winRetryIoerr(v8, &v9) )
    {
LABEL_7:
      v6 = v9;
      goto LABEL_10;
    }
  }
  v7 = 0;
LABEL_12:
  winLogIoerr(v8[0], 52094);
LABEL_13:
  sqlite3_free(v3);
  return v7;
}

```

## disassembly

```asm
0x1800a29c0  mov     [rsp+arg_0], rbx
0x1800a29c5  push    rdi
0x1800a29c6  sub     rsp, 40h
0x1800a29ca  mov     rcx, rdx
0x1800a29cd  mov     [rsp+48h+var_18], 0
0x1800a29d5  mov     rbx, rdx
0x1800a29d8  mov     [rsp+48h+arg_18], 0
0x1800a29e0  call    winUtf8ToUnicode
0x1800a29e5  mov     rdi, rax
0x1800a29e8  test    rax, rax
0x1800a29eb  jnz     short loc_1800A29F7
0x1800a29ed  mov     eax, 0C0Ah
0x1800a29f2  jmp     loc_1800A2A92
0x1800a29f7  mov     rax, cs:off_1800C4050
0x1800a29fe  mov     rcx, rdi
0x1800a2a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a06  cmp     eax, 0FFFFFFFFh
0x1800a2a09  jz      short loc_1800A2A3F
0x1800a2a0b  test    al, 10h
0x1800a2a0d  jnz     short loc_1800A2A35
0x1800a2a0f  mov     rax, cs:off_1800C3F48
0x1800a2a16  mov     rcx, rdi
0x1800a2a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a1e  test    eax, eax
0x1800a2a20  jnz     short loc_1800A2A3B
0x1800a2a22  lea     rdx, [rsp+48h+arg_18]
0x1800a2a27  lea     rcx, [rsp+48h+var_18]
0x1800a2a2c  call    winRetryIoerr
0x1800a2a31  test    eax, eax
0x1800a2a33  jnz     short loc_1800A29F7
0x1800a2a35  mov     edx, [rsp+48h+arg_18]
0x1800a2a39  jmp     short loc_1800A2A55
0x1800a2a3b  xor     ebx, ebx
0x1800a2a3d  jmp     short loc_1800A2A7A
0x1800a2a3f  mov     rax, cs:off_1800C40C8
0x1800a2a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a4b  mov     edx, eax
0x1800a2a4d  add     eax, 0FFFFFFFEh
0x1800a2a50  cmp     eax, 1
0x1800a2a53  jbe     short loc_1800A2A75
0x1800a2a55  mov     r9, rbx
0x1800a2a58  mov     [rsp+48h+var_28], 0CB7Ch
0x1800a2a60  lea     r8, aWindelete; "winDelete"
0x1800a2a67  mov     ecx, 0A0Ah
0x1800a2a6c  call    winLogErrorAtLine
0x1800a2a71  mov     ebx, eax
0x1800a2a73  jmp     short loc_1800A2A88
0x1800a2a75  mov     ebx, 170Ah
0x1800a2a7a  mov     ecx, [rsp+48h+var_18]
0x1800a2a7e  mov     edx, 0CB7Eh
0x1800a2a83  call    winLogIoerr
0x1800a2a88  mov     rcx, rdi
0x1800a2a8b  call    sqlite3_free
0x1800a2a90  mov     eax, ebx
0x1800a2a92  mov     rbx, [rsp+48h+arg_0]
0x1800a2a97  add     rsp, 40h
0x1800a2a9b  pop     rdi
0x1800a2a9c  retn
```
