# sqlite3AuthReadCol

- ea: `0x18006b1fc`
- end: `0x18006b2e7`
- name: `sqlite3AuthReadCol`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18005d77c`
- `0x1800923ec`

## callees

- `0x180011bcc`
- `0x1800310a0`
- `0x18006b1fc`
- `0x1800b0010`

## string_xrefs

- `0x18006b2a0`: `access to %z is prohibited`

## pseudocode

```c
__int64 __fastcall sqlite3AuthReadCol(__int64 *a1, const char *a2, const char *a3, int a4)
{
  __int64 v4; // rdi
  __int64 v10; // r12
  unsigned int v11; // esi
  __int64 v12; // rax

  v4 = *a1;
  if ( *(_BYTE *)(*a1 + 197) )
    return 0;
  v10 = *(_QWORD *)(32LL * a4 + *(_QWORD *)(v4 + 32));
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, const char *, __int64, __int64))(v4 + 512))(
          *(_QWORD *)(v4 + 520),
          20,
          a2,
          a3,
          v10,
          a1[47]);
  if ( v11 == 1 )
  {
    v12 = sqlite3_mprintf("%s.%s", a2, a3);
    if ( *(int *)(v4 + 40) > 2 || a4 )
      v12 = sqlite3_mprintf("%s.%z", v10, v12);
    sqlite3ErrorMsg(a1, "access to %z is prohibited", v12);
    *((_DWORD *)a1 + 6) = 23;
  }
  else if ( (v11 & 0xFFFFFFFD) != 0 )
  {
    sqlite3ErrorMsg(a1, "authorizer malfunction");
    *((_DWORD *)a1 + 6) = 1;
  }
  return v11;
}

```

## disassembly

```asm
0x18006b1fc  push    rbx
0x18006b1fe  push    rbp
0x18006b1ff  push    rsi
0x18006b200  push    rdi
0x18006b201  push    r12
0x18006b203  push    r14
0x18006b205  push    r15
0x18006b207  sub     rsp, 40h
0x18006b20b  mov     rdi, [rcx]
0x18006b20e  mov     r14, r8
0x18006b211  movsxd  rbp, r9d
0x18006b214  mov     r15, rdx
0x18006b217  mov     rbx, rcx
0x18006b21a  cmp     byte ptr [rdi+0C5h], 0
0x18006b221  jz      short loc_18006B22A
0x18006b223  xor     eax, eax
0x18006b225  jmp     loc_18006B2D8
0x18006b22a  mov     rax, [rdi+20h]
0x18006b22e  mov     rcx, rbp
0x18006b231  shl     rcx, 5
0x18006b235  mov     r9, r14
0x18006b238  mov     r8, r15
0x18006b23b  mov     edx, 14h
0x18006b240  mov     r12, [rcx+rax]
0x18006b244  mov     rcx, [rbx+178h]
0x18006b24b  mov     rax, [rdi+200h]
0x18006b252  mov     [rsp+78h+var_50], rcx
0x18006b257  mov     rcx, [rdi+208h]
0x18006b25e  mov     [rsp+78h+var_58], r12
0x18006b263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b268  mov     esi, eax
0x18006b26a  cmp     eax, 1
0x18006b26d  jnz     short loc_18006B2B8
0x18006b26f  mov     r8, r14
0x18006b272  lea     rcx, aSS_2; "%s.%s"
0x18006b279  mov     rdx, r15
0x18006b27c  call    sqlite3_mprintf
0x18006b281  cmp     dword ptr [rdi+28h], 2
0x18006b285  jg      short loc_18006B28B
0x18006b287  test    ebp, ebp
0x18006b289  jz      short loc_18006B29D
0x18006b28b  mov     r8, rax
0x18006b28e  lea     rcx, aSZ; "%s.%z"
0x18006b295  mov     rdx, r12
0x18006b298  call    sqlite3_mprintf
0x18006b29d  mov     r8, rax
0x18006b2a0  lea     rdx, aAccessToZIsPro; "access to %z is prohibited"
0x18006b2a7  mov     rcx, rbx
0x18006b2aa  call    sqlite3ErrorMsg
0x18006b2af  mov     dword ptr [rbx+18h], 17h
0x18006b2b6  jmp     short loc_18006B2D6
0x18006b2b8  test    esi, 0FFFFFFFDh
0x18006b2be  jz      short loc_18006B2D6
0x18006b2c0  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x18006b2c7  mov     rcx, rbx
0x18006b2ca  call    sqlite3ErrorMsg
0x18006b2cf  mov     dword ptr [rbx+18h], 1
0x18006b2d6  mov     eax, esi
0x18006b2d8  add     rsp, 40h
0x18006b2dc  pop     r15
0x18006b2de  pop     r14
0x18006b2e0  pop     r12
0x18006b2e2  pop     rdi
0x18006b2e3  pop     rsi
0x18006b2e4  pop     rbp
0x18006b2e5  pop     rbx
0x18006b2e6  retn
```
