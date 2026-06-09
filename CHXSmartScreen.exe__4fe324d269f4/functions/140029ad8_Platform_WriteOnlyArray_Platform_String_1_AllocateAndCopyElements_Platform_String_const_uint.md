# Platform::WriteOnlyArray<Platform::String *,1>::AllocateAndCopyElements(Platform::String * const *,uint)

- ea: `0x140029ad8`
- end: `0x140029b4f`
- name: `?AllocateAndCopyElements@?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@KAPEAPE$AAVString@2@PEBQE$AAV32@I@Z`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14002921c`
- `0x14002ab34`

## callees

- `0x14000342d`
- `0x1400039f2`
- `0x140008900`
- `0x140029ad8`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140029af7`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140029af7`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x140029b15`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x140029b15`

## pseudocode

```c
char *__fastcall Platform::WriteOnlyArray<Platform::String __gc *,1>::AllocateAndCopyElements(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // rdi
  char *v4; // rbx
  char *v5; // rax
  __int64 i; // rsi

  v2 = a2;
  if ( !a2 )
    return 0;
  if ( a2 > 0x1FFFFFFF )
  {
    __abi_WinRTraiseInvalidCastException();
    __debugbreak();
  }
  v5 = (char *)_Platform_CoTaskMemAlloc(8LL * a2);
  v4 = v5;
  if ( !v5 )
  {
    __abi_WinRTraiseOutOfMemoryException();
    __debugbreak();
  }
  memset_0(v5, 0, 8 * v2);
  for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
    __abi_winrt_ptrto_string_assign(&v4[8 * i], *(_QWORD *)(a1 + 8 * i));
  return v4;
}

```

## disassembly

```asm
0x140029ad8  push    rbx
0x140029ada  push    rsi
0x140029adb  push    rdi
0x140029adc  push    r14
0x140029ade  sub     rsp, 28h
0x140029ae2  mov     edi, edx
0x140029ae4  mov     r14, rcx
0x140029ae7  test    edx, edx
0x140029ae9  jnz     short loc_140029AEF
0x140029aeb  xor     ebx, ebx
0x140029aed  jmp     short loc_140029B42
0x140029aef  cmp     edi, 1FFFFFFFh
0x140029af5  jbe     short loc_140029AFE
0x140029af7  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x140029afd  int     3; Trap to Debugger
0x140029afe  mov     rsi, rdi
0x140029b01  shl     rsi, 3
0x140029b05  mov     rcx, rsi; cb
0x140029b08  call    __Platform_CoTaskMemAlloc
0x140029b0d  mov     rbx, rax
0x140029b10  test    rax, rax
0x140029b13  jnz     short loc_140029B1C
0x140029b15  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x140029b1b  int     3; Trap to Debugger
0x140029b1c  mov     r8, rsi; Size
0x140029b1f  xor     edx, edx; Val
0x140029b21  mov     rcx, rbx; void *
0x140029b24  call    memset_0
0x140029b29  xor     esi, esi
0x140029b2b  test    edi, edi
0x140029b2d  jz      short loc_140029B42
0x140029b2f  mov     rdx, [r14+rsi*8]
0x140029b33  lea     rcx, [rbx+rsi*8]
0x140029b37  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x140029b3c  inc     esi
0x140029b3e  cmp     esi, edi
0x140029b40  jb      short loc_140029B2F
0x140029b42  mov     rax, rbx
0x140029b45  add     rsp, 28h
0x140029b49  pop     r14
0x140029b4b  pop     rdi
0x140029b4c  pop     rsi
0x140029b4d  pop     rbx
0x140029b4e  retn
```
