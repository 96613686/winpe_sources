# SiLogMessage

- ea: `0x14001c844`
- end: `0x14001c8dd`
- name: `SiLogMessage`
- size: `153`
- prototype: `__int64(int, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140013484`
- `0x140013814`
- `0x140013ac0`
- `0x14001dd64`
- `0x14001e3c0`

## callees

- `0x14001c844`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14001c89f`
- `msvcrt!_vsnwprintf` at `0x14001c89f`

## pseudocode

```c
__int64 SiLogMessage(int a1, const wchar_t *a2, ...)
{
  wchar_t Buffer[256]; // [rsp+30h] [rbp-218h] BYREF
  va_list va; // [rsp+260h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( byte_14003F875 && a1 >= dword_14003F870 && a1 < 5 )
  {
    _vsnwprintf(Buffer, 0xFFu, a2, va);
    Buffer[255] = 0;
    ((void (__fastcall *)(_QWORD, wchar_t *))qword_14003F878)((unsigned int)a1, Buffer);
  }
  return 0;
}

```

## disassembly

```asm
0x14001c844  mov     r11, rsp
0x14001c847  mov     [r11+10h], rdx
0x14001c84b  mov     [r11+18h], r8
0x14001c84f  mov     [r11+20h], r9
0x14001c853  push    rbx
0x14001c854  sub     rsp, 240h
0x14001c85b  mov     rax, cs:__security_cookie
0x14001c862  xor     rax, rsp
0x14001c865  mov     [rsp+248h+var_18], rax
0x14001c86d  cmp     cs:byte_14003F875, 0
0x14001c874  mov     ebx, ecx
0x14001c876  mov     [rsp+248h+var_228], 0
0x14001c87f  jz      short loc_14001C8C2
0x14001c881  cmp     ecx, cs:dword_14003F870
0x14001c887  jl      short loc_14001C8C2
0x14001c889  cmp     ecx, 5
0x14001c88c  jge     short loc_14001C8C2
0x14001c88e  mov     r8, rdx; Format
0x14001c891  lea     r9, [r11+18h]; Args
0x14001c895  mov     edx, 0FFh; BufferCount
0x14001c89a  lea     rcx, [rsp+248h+Buffer]; Buffer
0x14001c89f  call    cs:__imp__vsnwprintf
0x14001c8a5  xor     eax, eax
0x14001c8a7  lea     rdx, [rsp+248h+Buffer]
0x14001c8ac  mov     [rsp+248h+var_1A], ax
0x14001c8b4  mov     ecx, ebx
0x14001c8b6  mov     rax, cs:qword_14003F878
0x14001c8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8c2  xor     eax, eax
0x14001c8c4  mov     rcx, [rsp+248h+var_18]
0x14001c8cc  xor     rcx, rsp; StackCookie
0x14001c8cf  call    __security_check_cookie
0x14001c8d4  add     rsp, 240h
0x14001c8db  pop     rbx
0x14001c8dc  retn
```
