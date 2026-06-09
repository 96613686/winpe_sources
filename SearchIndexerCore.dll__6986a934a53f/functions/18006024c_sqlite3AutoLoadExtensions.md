# sqlite3AutoLoadExtensions

- ea: `0x18006024c`
- end: `0x18006031d`
- name: `sqlite3AutoLoadExtensions`
- size: `209`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003182c`

## callees

- `0x180020928`
- `0x180024640`
- `0x180038d00`
- `0x180041eb0`
- `0x18004b758`
- `0x18006024c`
- `0x1800b0010`

## string_xrefs

- `0x1800602f1`: `automatic extension loading failed: %s`

## pseudocode

```c
void __fastcall sqlite3AutoLoadExtensions(__int64 a1)
{
  int v2; // edi
  __int64 v3; // rbx
  __int64 v4; // rbp
  __int64 (__fastcall *v5)(__int64, const char **, __int64 (__fastcall **)()); // rsi
  unsigned int v6; // eax
  const char *v7; // [rsp+48h] [rbp+10h] BYREF

  if ( dword_1800D0EB0 )
  {
    v2 = 1;
    v3 = 0;
    do
    {
      v7 = 0;
      v4 = sqlite3MutexAlloc(2);
      sqlite3_mutex_enter(v4);
      if ( (unsigned int)v3 < dword_1800D0EB0 )
      {
        v5 = *(__int64 (__fastcall **)(__int64, const char **, __int64 (__fastcall **)()))(qword_1800D0EB8 + 8 * v3);
      }
      else
      {
        v5 = 0;
        v2 = 0;
      }
      sqlite3_mutex_leave(v4);
      v7 = 0;
      if ( v5 )
      {
        v6 = v5(a1, &v7, off_1800B1DA0);
        if ( v6 )
        {
          sqlite3ErrorWithMsg(a1, v6, "automatic extension loading failed: %s", v7);
          v2 = 0;
        }
      }
      sqlite3_free(v7);
      v3 = (unsigned int)(v3 + 1);
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x18006024c  mov     [rsp+arg_0], rbx
0x180060251  mov     [rsp+arg_10], rbp
0x180060256  push    rsi
0x180060257  push    rdi
0x180060258  push    r14
0x18006025a  sub     rsp, 20h
0x18006025e  cmp     cs:dword_1800D0EB0, 0
0x180060265  mov     r14, rcx
0x180060268  jnz     short loc_18006027D
0x18006026a  mov     rbx, [rsp+38h+arg_0]
0x18006026f  mov     rbp, [rsp+38h+arg_10]
0x180060274  add     rsp, 20h
0x180060278  pop     r14
0x18006027a  pop     rdi
0x18006027b  pop     rsi
0x18006027c  retn
0x18006027d  mov     edi, 1
0x180060282  xor     ebx, ebx
0x180060284  mov     ecx, 2
0x180060289  mov     [rsp+38h+arg_8], 0
0x180060292  call    sqlite3MutexAlloc
0x180060297  mov     rcx, rax
0x18006029a  mov     rbp, rax
0x18006029d  call    sqlite3_mutex_enter
0x1800602a2  cmp     ebx, cs:dword_1800D0EB0
0x1800602a8  jb      short loc_1800602B0
0x1800602aa  xor     esi, esi
0x1800602ac  xor     edi, edi
0x1800602ae  jmp     short loc_1800602BB
0x1800602b0  mov     rax, cs:qword_1800D0EB8
0x1800602b7  mov     rsi, [rax+rbx*8]
0x1800602bb  mov     rcx, rbp
0x1800602be  call    sqlite3_mutex_leave
0x1800602c3  mov     [rsp+38h+arg_8], 0
0x1800602cc  test    rsi, rsi
0x1800602cf  jz      short loc_180060304
0x1800602d1  lea     r8, off_1800B1DA0
0x1800602d8  mov     rcx, r14
0x1800602db  lea     rdx, [rsp+38h+arg_8]
0x1800602e0  mov     rax, rsi
0x1800602e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602e8  test    eax, eax
0x1800602ea  jz      short loc_180060304
0x1800602ec  mov     r9, [rsp+38h+arg_8]
0x1800602f1  lea     r8, aAutomaticExten; "automatic extension loading failed: %s"
0x1800602f8  mov     edx, eax
0x1800602fa  mov     rcx, r14
0x1800602fd  call    sqlite3ErrorWithMsg
0x180060302  xor     edi, edi
0x180060304  mov     rcx, [rsp+38h+arg_8]
0x180060309  call    sqlite3_free
0x18006030e  inc     ebx
0x180060310  test    edi, edi
0x180060312  jnz     loc_180060284
0x180060318  jmp     loc_18006026A
```
