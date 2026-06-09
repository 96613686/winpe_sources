# CFormatConverterWMPhoto::CheckBufferSize(uint,uint,uint,uint,uint)

- ea: `0x18001c87c`
- end: `0x18001c90e`
- name: `?CheckBufferSize@CFormatConverterWMPhoto@@KAJIIIII@Z`
- size: `146`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, UINT, unsigned int, unsigned int)`
- caller_count: `32`
- callee_count: `3`
- tags: ``

## callers

- `0x180010100`
- `0x180012d10`
- `0x18001ab10`
- `0x18001abc0`
- `0x18001ac70`
- `0x18001ad20`
- `0x18001add0`
- `0x18001ae80`
- `0x18001b120`
- `0x18001b220`
- `0x18001b380`
- `0x18001b4b0`
- `0x18001b5a0`
- `0x18001b650`
- `0x18001b8e0`
- `0x18001bbc0`
- `0x18001bc70`
- `0x18001bf90`
- `0x18001c030`
- `0x18001c190`
- `0x18001c240`
- `0x18001c2f0`
- `0x18001c3a0`
- `0x18001c430`
- `0x18001c5c0`
- `0x18001c660`
- `0x18001c920`
- `0x18001cbc0`
- `0x18001cde0`
- `0x18001cea0`
- `0x18001cf60`
- `0x18001d020`

## callees

- `0x18000bcc0`
- `0x1800171c4`
- `0x18001c87c`

## pseudocode

```c
__int64 __fastcall CFormatConverterWMPhoto::CheckBufferSize(
        unsigned int a1,
        unsigned int a2,
        UINT a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v7; // ebx
  HRESULT v8; // eax
  unsigned int v9; // r11d
  int v10; // ecx
  UINT puResult; // [rsp+38h] [rbp+10h] BYREF

  puResult = 0;
  if ( a5 * (unsigned __int64)a2 > 0xFFFFFFFF )
  {
    v7 = -2147024362;
LABEL_10:
    if ( g_doStackCaptures )
    {
      v10 = v7;
      goto LABEL_12;
    }
    return v7;
  }
  v8 = ULongLongToUInt(a5 * (unsigned __int64)a4, &puResult);
  v7 = v8;
  if ( v8 >= 0 )
  {
    if ( a1 >= v9 && a3 >= puResult )
      return 0;
    v7 = -2003292276;
    goto LABEL_10;
  }
  if ( g_doStackCaptures )
  {
    v10 = v8;
LABEL_12:
    DoStackCapture(v10);
  }
  return v7;
}

```

## disassembly

```asm
0x18001c87c  mov     [rsp+arg_0], rbx
0x18001c881  mov     [rsp+arg_10], rsi
0x18001c886  push    rdi
0x18001c887  sub     rsp, 20h
0x18001c88b  mov     eax, [rsp+28h+arg_20]
0x18001c88f  mov     esi, ecx
0x18001c891  mov     r11d, edx
0x18001c894  mov     ecx, 0FFFFFFFFh
0x18001c899  imul    r11, rax
0x18001c89d  mov     edi, r8d
0x18001c8a0  mov     [rsp+28h+puResult], 0
0x18001c8a8  cmp     r11, rcx
0x18001c8ab  jbe     short loc_18001C8B4
0x18001c8ad  mov     ebx, 80070216h
0x18001c8b2  jmp     short loc_18001C8EC
0x18001c8b4  mov     ecx, r9d
0x18001c8b7  lea     rdx, [rsp+28h+puResult]; puResult
0x18001c8bc  imul    rcx, rax; ullOperand
0x18001c8c0  call    ULongLongToUInt
0x18001c8c5  mov     ebx, eax
0x18001c8c7  test    eax, eax
0x18001c8c9  jns     short loc_18001C8D8
0x18001c8cb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001c8d2  jz      short loc_18001C8FC
0x18001c8d4  mov     ecx, eax
0x18001c8d6  jmp     short loc_18001C8F7
0x18001c8d8  cmp     esi, r11d
0x18001c8db  jb      short loc_18001C8E7
0x18001c8dd  cmp     edi, [rsp+28h+puResult]
0x18001c8e1  jb      short loc_18001C8E7
0x18001c8e3  xor     ebx, ebx
0x18001c8e5  jmp     short loc_18001C8FC
0x18001c8e7  mov     ebx, 88982F8Ch
0x18001c8ec  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001c8f3  jz      short loc_18001C8FC
0x18001c8f5  mov     ecx, ebx; int
0x18001c8f7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001c8fc  mov     rsi, [rsp+28h+arg_10]
0x18001c901  mov     eax, ebx
0x18001c903  mov     rbx, [rsp+28h+arg_0]
0x18001c908  add     rsp, 20h
0x18001c90c  pop     rdi
0x18001c90d  retn
```
