# WriteSubrs

- ea: `0x18004c5f8`
- end: `0x18004c7ad`
- name: `WriteSubrs`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004bb20`

## callees

- `0x180001ee0`
- `0x180049428`
- `0x180049e14`
- `0x180049e98`
- `0x18004a944`
- `0x18004c5f8`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall WriteSubrs(__int64 a1, int a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  unsigned __int16 v6; // r15
  unsigned int i; // r12d
  unsigned int v8; // ebx
  __int64 v9; // [rsp+20h] [rbp-49h]
  unsigned __int16 v10; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h] BYREF
  _OWORD v12[3]; // [rsp+40h] [rbp-29h] BYREF
  __int16 v13; // [rsp+70h] [rbp+7h]

  result = 0;
  v13 = 0;
  v11 = 0;
  v10 = 0;
  memset(v12, 0, sizeof(v12));
  if ( a2 )
    v5 = *(_DWORD *)(a1 + 6820);
  else
    v5 = *(_DWORD *)(a1 + 14328) - 1;
  if ( !v5 )
  {
    if ( !*(_DWORD *)(a1 + 488) || !a2 )
      return result;
    goto LABEL_9;
  }
  if ( a2 )
  {
LABEL_9:
    if ( *(int *)(a1 + 488) > 0 )
      LODWORD(result) = 2;
  }
  (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(
    v12,
    50,
    "/Subrs %u  array\r\n",
    (unsigned int)result + v5);
  PutString(a1, (const char *)v12);
  v6 = *(_WORD *)(a1 + 7976);
  if ( v6 == 0xFFFF )
    v6 = 0;
  for ( i = 0; i < v5; ++i )
  {
    GetSubr(a1, i, a2, (unsigned int)&v11, (__int64)&v10);
    v8 = v10;
    LODWORD(v9) = v10 + v6;
    (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(v12, 50, "dup %ld %lu -| ", i, v9);
    PutString(a1, (const char *)v12);
    PutType1CharString(a1, v11, v8);
    PutString(a1, " |\r\n");
  }
  if ( a2 )
  {
    if ( *(int *)(a1 + 488) > 0 )
    {
      WriteDVSubr(a1, v5, *(unsigned __int16 *)(a1 + 558), v6);
      WriteDVSubr(a1, v5 + 1, *(unsigned __int16 *)(a1 + 556), v6);
    }
  }
  return PutString(a1, "|-\r\n");
}

```

## disassembly

```asm
0x18004c5f8  push    rbp
0x18004c5fa  push    rbx
0x18004c5fb  push    rsi
0x18004c5fc  push    rdi
0x18004c5fd  push    r12
0x18004c5ff  push    r13
0x18004c601  push    r14
0x18004c603  push    r15
0x18004c605  lea     rbp, [rsp-1Fh]
0x18004c60a  sub     rsp, 88h
0x18004c611  mov     rax, cs:__security_cookie
0x18004c618  xor     rax, rsp
0x18004c61b  mov     [rbp+57h+var_48], rax
0x18004c61f  xor     eax, eax
0x18004c621  xorps   xmm0, xmm0
0x18004c624  mov     [rbp+57h+var_50], ax
0x18004c628  mov     r14d, edx
0x18004c62b  mov     [rbp+57h+var_88], rax
0x18004c62f  mov     rdi, rcx
0x18004c632  mov     [rbp+57h+var_90], ax
0x18004c636  movups  [rbp+57h+var_80], xmm0
0x18004c63a  movups  [rbp+57h+var_70], xmm0
0x18004c63e  movups  [rbp+57h+var_60], xmm0
0x18004c642  test    edx, edx
0x18004c644  jz      short loc_18004C64E
0x18004c646  mov     esi, [rcx+1AA4h]
0x18004c64c  jmp     short loc_18004C656
0x18004c64e  mov     esi, [rcx+37F8h]
0x18004c654  dec     esi
0x18004c656  test    esi, esi
0x18004c658  jnz     short loc_18004C670
0x18004c65a  cmp     [rcx+1E8h], eax
0x18004c660  jz      loc_18004C78D
0x18004c666  test    r14d, r14d
0x18004c669  jnz     short loc_18004C675
0x18004c66b  jmp     loc_18004C78D
0x18004c670  test    r14d, r14d
0x18004c673  jz      short loc_18004C682
0x18004c675  cmp     [rcx+1E8h], eax
0x18004c67b  jle     short loc_18004C682
0x18004c67d  mov     eax, 2
0x18004c682  lea     r9d, [rax+rsi]
0x18004c686  mov     edx, 32h ; '2'
0x18004c68b  mov     rax, [rdi+168h]
0x18004c692  lea     r8, aSubrsUArray; "/Subrs %u  array\r\n"
0x18004c699  lea     rcx, [rbp+57h+var_80]
0x18004c69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6a2  lea     rdx, [rbp+57h+var_80]
0x18004c6a6  mov     rcx, rdi
0x18004c6a9  call    PutString
0x18004c6ae  movzx   r15d, word ptr [rdi+1F28h]
0x18004c6b6  cmp     r15w, 0FFFFh
0x18004c6bb  jnz     short loc_18004C6C0
0x18004c6bd  xor     r15d, r15d
0x18004c6c0  xor     r12d, r12d
0x18004c6c3  test    esi, esi
0x18004c6c5  jz      short loc_18004C743
0x18004c6c7  movzx   r13d, r15w
0x18004c6cb  lea     rax, [rbp+57h+var_90]
0x18004c6cf  mov     r8d, r14d
0x18004c6d2  lea     r9, [rbp+57h+var_88]
0x18004c6d6  mov     [rsp+0C0h+var_A0], rax
0x18004c6db  mov     edx, r12d
0x18004c6de  mov     rcx, rdi
0x18004c6e1  call    GetSubr
0x18004c6e6  movzx   ebx, [rbp+57h+var_90]
0x18004c6ea  lea     r8, aDupLdLu; "dup %ld %lu -| "
0x18004c6f1  mov     rax, [rdi+168h]
0x18004c6f8  mov     r9d, r12d
0x18004c6fb  mov     edx, 32h ; '2'
0x18004c700  lea     ecx, [rbx+r13]
0x18004c704  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x18004c708  lea     rcx, [rbp+57h+var_80]
0x18004c70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c711  lea     rdx, [rbp+57h+var_80]
0x18004c715  mov     rcx, rdi
0x18004c718  call    PutString
0x18004c71d  mov     rdx, [rbp+57h+var_88]
0x18004c721  mov     r8d, ebx
0x18004c724  mov     rcx, rdi
0x18004c727  call    PutType1CharString
0x18004c72c  lea     rdx, asc_18006AA8C; " |\r\n"
0x18004c733  mov     rcx, rdi
0x18004c736  call    PutString
0x18004c73b  inc     r12d
0x18004c73e  cmp     r12d, esi
0x18004c741  jb      short loc_18004C6CB
0x18004c743  test    r14d, r14d
0x18004c746  jz      short loc_18004C77E
0x18004c748  cmp     dword ptr [rdi+1E8h], 0
0x18004c74f  jle     short loc_18004C77E
0x18004c751  movzx   r8d, word ptr [rdi+22Eh]
0x18004c759  movzx   r9d, r15w
0x18004c75d  mov     edx, esi
0x18004c75f  mov     rcx, rdi
0x18004c762  call    WriteDVSubr
0x18004c767  movzx   r8d, word ptr [rdi+22Ch]
0x18004c76f  lea     edx, [rsi+1]
0x18004c772  movzx   r9d, r15w
0x18004c776  mov     rcx, rdi
0x18004c779  call    WriteDVSubr
0x18004c77e  lea     rdx, asc_18006AAC4; "|-\r\n"
0x18004c785  mov     rcx, rdi
0x18004c788  call    PutString
0x18004c78d  mov     rcx, [rbp+57h+var_48]
0x18004c791  xor     rcx, rsp; StackCookie
0x18004c794  call    __security_check_cookie
0x18004c799  add     rsp, 88h
0x18004c7a0  pop     r15
0x18004c7a2  pop     r14
0x18004c7a4  pop     r13
0x18004c7a6  pop     r12
0x18004c7a8  pop     rdi
0x18004c7a9  pop     rsi
0x18004c7aa  pop     rbx
0x18004c7ab  pop     rbp
0x18004c7ac  retn
```
