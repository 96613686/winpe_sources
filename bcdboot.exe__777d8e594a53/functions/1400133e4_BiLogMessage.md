# BiLogMessage

- ea: `0x1400133e4`
- end: `0x14001347d`
- name: `BiLogMessage`
- size: `153`
- prototype: `__int64(int, const wchar_t *, ...)`
- caller_count: `64`
- callee_count: `3`
- tags: ``

## callers

- `0x140013b48`
- `0x140013b9c`
- `0x140013c1c`
- `0x140013ee8`
- `0x1400140c4`
- `0x140014130`
- `0x14001474c`
- `0x140014ec8`
- `0x140015cd8`
- `0x140016784`
- `0x140016e08`
- `0x1400186fc`
- `0x140018890`
- `0x140018b54`
- `0x140019544`
- `0x140019990`
- `0x140019bb8`
- `0x14001a264`
- `0x14001a6b0`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001ac80`
- `0x14001acec`
- `0x14001ae30`
- `0x14001af00`
- `0x14001b1f4`
- `0x14001b4bc`
- `0x14001b764`
- `0x14001bb00`
- `0x14001bd44`
- `0x14001c14c`
- `0x14001c794`
- `0x14001f324`
- `0x14001f570`
- `0x140020324`
- `0x140020e68`
- `0x1400211b0`
- `0x140021298`
- `0x1400218e4`
- `0x140021c10`
- `0x140021f58`
- `0x1400221ac`
- `0x140022258`
- `0x1400228bc`
- `0x140022cb8`
- `0x140022e8c`
- `0x140023218`
- `0x140023448`
- `0x1400235bc`
- `0x140023714`

## callees

- `0x1400133e4`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14001343f`
- `msvcrt!_vsnwprintf` at `0x14001343f`

## pseudocode

```c
__int64 BiLogMessage(int a1, const wchar_t *a2, ...)
{
  wchar_t Buffer[256]; // [rsp+30h] [rbp-218h] BYREF
  va_list va; // [rsp+260h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( byte_14003F840 && a1 >= dword_14003F830 && a1 < 5 )
  {
    _vsnwprintf(Buffer, 0xFFu, a2, va);
    Buffer[255] = 0;
    ((void (__fastcall *)(_QWORD, wchar_t *))qword_14003F838)((unsigned int)a1, Buffer);
  }
  return 0;
}

```

## disassembly

```asm
0x1400133e4  mov     r11, rsp
0x1400133e7  mov     [r11+10h], rdx
0x1400133eb  mov     [r11+18h], r8
0x1400133ef  mov     [r11+20h], r9
0x1400133f3  push    rbx
0x1400133f4  sub     rsp, 240h
0x1400133fb  mov     rax, cs:__security_cookie
0x140013402  xor     rax, rsp
0x140013405  mov     [rsp+248h+var_18], rax
0x14001340d  cmp     cs:byte_14003F840, 0
0x140013414  mov     ebx, ecx
0x140013416  mov     [rsp+248h+var_228], 0
0x14001341f  jz      short loc_140013462
0x140013421  cmp     ecx, cs:dword_14003F830
0x140013427  jl      short loc_140013462
0x140013429  cmp     ecx, 5
0x14001342c  jge     short loc_140013462
0x14001342e  mov     r8, rdx; Format
0x140013431  lea     r9, [r11+18h]; Args
0x140013435  mov     edx, 0FFh; BufferCount
0x14001343a  lea     rcx, [rsp+248h+Buffer]; Buffer
0x14001343f  call    cs:__imp__vsnwprintf
0x140013445  xor     eax, eax
0x140013447  lea     rdx, [rsp+248h+Buffer]
0x14001344c  mov     [rsp+248h+var_1A], ax
0x140013454  mov     ecx, ebx
0x140013456  mov     rax, cs:qword_14003F838
0x14001345d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013462  xor     eax, eax
0x140013464  mov     rcx, [rsp+248h+var_18]
0x14001346c  xor     rcx, rsp; StackCookie
0x14001346f  call    __security_check_cookie
0x140013474  add     rsp, 240h
0x14001347b  pop     rbx
0x14001347c  retn
```
