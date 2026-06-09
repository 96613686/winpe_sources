# sqlite3AutoLoadExtensions

- ea: `0x18005879c`
- end: `0x18005886d`
- name: `sqlite3AutoLoadExtensions`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180001fbc`

## callees

- `0x180005d14`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18005879c`
- `0x18005cf6c`
- `0x18009a010`

## string_xrefs

- `0x180058841`: `automatic extension loading failed: %s`

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

  if ( dword_1800B5C00 )
  {
    v2 = 1;
    v3 = 0;
    do
    {
      v7 = 0;
      v4 = sqlite3MutexAlloc(2);
      sqlite3_mutex_enter(v4);
      if ( (unsigned int)v3 < dword_1800B5C00 )
      {
        v5 = *(__int64 (__fastcall **)(__int64, const char **, __int64 (__fastcall **)()))(qword_1800B5C08 + 8 * v3);
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
        v6 = v5(a1, &v7, off_18009B6E0);
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
0x18005879c  mov     [rsp+arg_0], rbx
0x1800587a1  mov     [rsp+arg_10], rbp
0x1800587a6  push    rsi
0x1800587a7  push    rdi
0x1800587a8  push    r14
0x1800587aa  sub     rsp, 20h
0x1800587ae  cmp     cs:dword_1800B5C00, 0
0x1800587b5  mov     r14, rcx
0x1800587b8  jnz     short loc_1800587CD
0x1800587ba  mov     rbx, [rsp+38h+arg_0]
0x1800587bf  mov     rbp, [rsp+38h+arg_10]
0x1800587c4  add     rsp, 20h
0x1800587c8  pop     r14
0x1800587ca  pop     rdi
0x1800587cb  pop     rsi
0x1800587cc  retn
0x1800587cd  mov     edi, 1
0x1800587d2  xor     ebx, ebx
0x1800587d4  mov     ecx, 2
0x1800587d9  mov     [rsp+38h+arg_8], 0
0x1800587e2  call    sqlite3MutexAlloc
0x1800587e7  mov     rcx, rax
0x1800587ea  mov     rbp, rax
0x1800587ed  call    sqlite3_mutex_enter
0x1800587f2  cmp     ebx, cs:dword_1800B5C00
0x1800587f8  jb      short loc_180058800
0x1800587fa  xor     esi, esi
0x1800587fc  xor     edi, edi
0x1800587fe  jmp     short loc_18005880B
0x180058800  mov     rax, cs:qword_1800B5C08
0x180058807  mov     rsi, [rax+rbx*8]
0x18005880b  mov     rcx, rbp
0x18005880e  call    sqlite3_mutex_leave
0x180058813  mov     [rsp+38h+arg_8], 0
0x18005881c  test    rsi, rsi
0x18005881f  jz      short loc_180058854
0x180058821  lea     r8, off_18009B6E0
0x180058828  mov     rcx, r14
0x18005882b  lea     rdx, [rsp+38h+arg_8]
0x180058830  mov     rax, rsi
0x180058833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058838  test    eax, eax
0x18005883a  jz      short loc_180058854
0x18005883c  mov     r9, [rsp+38h+arg_8]
0x180058841  lea     r8, aAutomaticExten; "automatic extension loading failed: %s"
0x180058848  mov     edx, eax
0x18005884a  mov     rcx, r14
0x18005884d  call    sqlite3ErrorWithMsg
0x180058852  xor     edi, edi
0x180058854  mov     rcx, [rsp+38h+arg_8]
0x180058859  call    sqlite3_free
0x18005885e  inc     ebx
0x180058860  test    edi, edi
0x180058862  jnz     loc_1800587D4
0x180058868  jmp     loc_1800587BA
```
