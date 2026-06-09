# sqlite3AutoLoadExtensions

- ea: `0x18007888c`
- end: `0x18007895c`
- name: `sqlite3AutoLoadExtensions`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800204f0`

## callees

- `0x180012470`
- `0x180034900`
- `0x180042500`
- `0x18007888c`
- `0x18007edf0`
- `0x180086758`
- `0x1800a8010`

## string_xrefs

- `0x180078922`: `automatic extension loading failed: %s`

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

  if ( dword_1800C79D0 )
  {
    v2 = 1;
    v3 = 0;
    do
    {
      v7 = 0;
      v4 = sqlite3MutexAlloc(2);
      sqlite3_mutex_enter(v4);
      if ( (unsigned int)v3 < dword_1800C79D0 )
      {
        v5 = *(__int64 (__fastcall **)(__int64, const char **, __int64 (__fastcall **)()))(qword_1800C79D8 + 8 * v3);
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
        v6 = v5(a1, &v7, off_1800A9840);
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
0x18007888c  mov     [rsp+arg_0], rbx
0x180078891  mov     [rsp+arg_10], rbp
0x180078896  push    rsi
0x180078897  push    rdi
0x180078898  push    r14
0x18007889a  sub     rsp, 20h
0x18007889e  cmp     cs:dword_1800C79D0, 0
0x1800788a5  mov     r14, rcx
0x1800788a8  jz      loc_180078949
0x1800788ae  mov     edi, 1
0x1800788b3  xor     ebx, ebx
0x1800788b5  mov     ecx, 2
0x1800788ba  mov     [rsp+38h+arg_8], 0
0x1800788c3  call    sqlite3MutexAlloc
0x1800788c8  mov     rcx, rax
0x1800788cb  mov     rbp, rax
0x1800788ce  call    sqlite3_mutex_enter
0x1800788d3  cmp     ebx, cs:dword_1800C79D0
0x1800788d9  jb      short loc_1800788E1
0x1800788db  xor     esi, esi
0x1800788dd  xor     edi, edi
0x1800788df  jmp     short loc_1800788EC
0x1800788e1  mov     rax, cs:qword_1800C79D8
0x1800788e8  mov     rsi, [rax+rbx*8]
0x1800788ec  mov     rcx, rbp
0x1800788ef  call    sqlite3_mutex_leave
0x1800788f4  mov     [rsp+38h+arg_8], 0
0x1800788fd  test    rsi, rsi
0x180078900  jz      short loc_180078935
0x180078902  lea     r8, off_1800A9840
0x180078909  mov     rcx, r14
0x18007890c  lea     rdx, [rsp+38h+arg_8]
0x180078911  mov     rax, rsi
0x180078914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078919  test    eax, eax
0x18007891b  jz      short loc_180078935
0x18007891d  mov     r9, [rsp+38h+arg_8]
0x180078922  lea     r8, aAutomaticExten; "automatic extension loading failed: %s"
0x180078929  mov     edx, eax
0x18007892b  mov     rcx, r14
0x18007892e  call    sqlite3ErrorWithMsg
0x180078933  xor     edi, edi
0x180078935  mov     rcx, [rsp+38h+arg_8]
0x18007893a  call    sqlite3_free
0x18007893f  inc     ebx
0x180078941  test    edi, edi
0x180078943  jnz     loc_1800788B5
0x180078949  mov     rbx, [rsp+38h+arg_0]
0x18007894e  mov     rbp, [rsp+38h+arg_10]
0x180078953  add     rsp, 20h
0x180078957  pop     r14
0x180078959  pop     rdi
0x18007895a  pop     rsi
0x18007895b  retn
```
