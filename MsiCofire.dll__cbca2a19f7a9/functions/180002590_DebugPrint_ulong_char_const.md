# DebugPrint(ulong,char const *,...)

- ea: `0x180002590`
- end: `0x18000262c`
- name: `?DebugPrint@@YAXKPEBDZZ`
- size: `156`
- prototype: `void(ULONG Level, const char *Format, ...)`
- caller_count: `26`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800026f0`
- `0x180002770`
- `0x180002a88`
- `0x180002f08`
- `0x1800032a8`
- `0x1800035f4`
- `0x1800036f0`
- `0x1800038cc`
- `0x180003ac8`
- `0x180003ff8`
- `0x18000425c`
- `0x1800043d8`
- `0x18000465c`
- `0x18000480c`
- `0x180004a70`
- `0x180005020`
- `0x180005410`
- `0x180005784`
- `0x18000595c`
- `0x180005b1c`
- `0x180005b78`
- `0x180005d44`
- `0x180005ee4`
- `0x180006370`
- `0x180006530`
- `0x180006830`

## callees

- `0x180002590`
- `0x180007040`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800025d5`
- `msvcrt!_vsnprintf` at `0x1800025d5`
- `ntdll!DbgPrintEx` at `0x180002603`
- `ntdll!DbgPrintEx` at `0x180002603`

## pseudocode

```c
void DebugPrint(ULONG Level, const char *Format, ...)
{
  unsigned int v3; // eax
  char Buffer[1024]; // [rsp+30h] [rbp-418h] BYREF
  va_list va; // [rsp+460h] [rbp+18h] BYREF

  va_start(va, Format);
  v3 = _vsnprintf(Buffer, 0x3FFu, Format, va);
  if ( v3 < 0x400 )
  {
    if ( v3 == 1023 )
      Buffer[1023] = 0;
    DbgPrintEx(0x81u, Level, "%s", Buffer);
  }
}

```

## disassembly

```asm
0x180002590  mov     r11, rsp
0x180002593  mov     [r11+10h], rdx
0x180002597  mov     [r11+18h], r8
0x18000259b  mov     [r11+20h], r9
0x18000259f  push    rbx
0x1800025a0  sub     rsp, 440h
0x1800025a7  mov     rax, cs:__security_cookie
0x1800025ae  xor     rax, rsp
0x1800025b1  mov     [rsp+448h+var_18], rax
0x1800025b9  mov     ebx, ecx
0x1800025bb  mov     [rsp+448h+var_428], 0
0x1800025c4  mov     r8, rdx; Format
0x1800025c7  lea     rcx, [rsp+448h+Buffer]; Buffer
0x1800025cc  mov     edx, 3FFh; BufferCount
0x1800025d1  lea     r9, [r11+18h]; ArgList
0x1800025d5  call    cs:__imp__vsnprintf
0x1800025db  test    eax, eax
0x1800025dd  js      short loc_18000260B
0x1800025df  cmp     eax, 3FFh
0x1800025e4  ja      short loc_18000260B
0x1800025e6  jnz     short loc_1800025F0
0x1800025e8  mov     [rsp+448h+var_19], 0
0x1800025f0  lea     r9, [rsp+448h+Buffer]
0x1800025f5  mov     edx, ebx; Level
0x1800025f7  lea     r8, Format; "%s"
0x1800025fe  mov     ecx, 81h; ComponentId
0x180002603  call    cs:__imp_DbgPrintEx
0x180002609  jmp     short loc_180002613
0x18000260b  mov     [rsp+448h+var_19], 0
0x180002613  mov     rcx, [rsp+448h+var_18]
0x18000261b  xor     rcx, rsp; StackCookie
0x18000261e  call    __security_check_cookie
0x180002623  add     rsp, 440h
0x18000262a  pop     rbx
0x18000262b  retn
```
