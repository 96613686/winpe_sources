# ZTracer::DebugMsg(char const *,...)

- ea: `0x1800024bc`
- end: `0x180002546`
- name: `?DebugMsg@ZTracer@@QEAAXPEBDZZ`
- size: `138`
- prototype: `void(ZTracer *__hidden this, const char *, ...)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000258c`
- `0x1800027d4`
- `0x1800028d4`
- `0x180002a54`
- `0x180002bd4`
- `0x180003360`

## callees

- `0x180001730`
- `0x1800022d8`
- `0x1800024bc`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000251b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002528`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000251b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002528`

## pseudocode

```c
void ZTracer::DebugMsg(ZTracer *this, const char *a2, ...)
{
  char Buffer[1024]; // [rsp+30h] [rbp-418h] BYREF
  va_list va; // [rsp+460h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( (unsigned int)vsnprintf(Buffer, 0x3FFu, a2, va) > 0x3FE )
    Buffer[1023] = 0;
  OutputDebugStringA(Buffer);
  OutputDebugStringA("\n");
}

```

## disassembly

```asm
0x1800024bc  mov     r11, rsp
0x1800024bf  mov     [r11+10h], rdx
0x1800024c3  mov     [r11+18h], r8
0x1800024c7  mov     [r11+20h], r9
0x1800024cb  sub     rsp, 448h
0x1800024d2  mov     rax, cs:__security_cookie
0x1800024d9  xor     rax, rsp
0x1800024dc  mov     [rsp+448h+var_18], rax
0x1800024e4  mov     r8, rdx; Format
0x1800024e7  mov     [rsp+448h+var_428], 0
0x1800024f0  mov     edx, 3FFh; BufferCount
0x1800024f5  lea     r9, [r11+18h]; ArgList
0x1800024f9  lea     rcx, [rsp+448h+Buffer]; Buffer
0x1800024fe  call    _vsnprintf
0x180002503  test    eax, eax
0x180002505  js      short loc_18000250E
0x180002507  cmp     eax, 3FFh
0x18000250c  jb      short loc_180002516
0x18000250e  mov     [rsp+448h+var_19], 0
0x180002516  lea     rcx, [rsp+448h+Buffer]; lpOutputString
0x18000251b  call    cs:__imp_OutputDebugStringA
0x180002521  lea     rcx, OutputString; "\n"
0x180002528  call    cs:__imp_OutputDebugStringA
0x18000252e  mov     rcx, [rsp+448h+var_18]
0x180002536  xor     rcx, rsp; StackCookie
0x180002539  call    __security_check_cookie
0x18000253e  add     rsp, 448h
0x180002545  retn
```
