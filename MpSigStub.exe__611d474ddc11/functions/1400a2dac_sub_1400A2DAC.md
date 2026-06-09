# sub_1400A2DAC

- ea: `0x1400a2dac`
- end: `0x1400a2e94`
- name: `sub_1400A2DAC`
- size: `232`
- prototype: `__int64 __fastcall(HMODULE *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002fbe8`
- `0x1400a2348`
- `0x1400a7e84`

## callees

- `0x1400a2be4`
- `0x1400a2dac`
- `0x1400a5d88`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400a2e40`
- `KERNEL32!FreeLibrary` at `0x1400a2e56`
- `KERNEL32!FreeLibrary` at `0x1400a2e70`
- `KERNEL32!FreeLibrary` at `0x1400a2e40`
- `KERNEL32!FreeLibrary` at `0x1400a2e56`
- `KERNEL32!FreeLibrary` at `0x1400a2e70`

## string_xrefs

- `0x1400a2dcf`: `kernelbase.dll`
- `0x1400a2dbf`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_1400A2DAC(HMODULE *a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // edi
  HMODULE v8; // rdi
  HMODULE v9; // rdx
  int v10; // esi
  _QWORD v12[5]; // [rsp+20h] [rbp-28h]
  HMODULE hLibModule; // [rsp+68h] [rbp+20h] BYREF

  v12[0] = L"kernel32.dll";
  hLibModule = 0;
  v12[1] = L"kernelbase.dll";
  v4 = 0;
  while ( 1 )
  {
    v5 = v12[v4];
    if ( !v5 )
      return (unsigned int)-2147024809;
    v6 = sub_1400A2BE4((__int64)&hLibModule, v5);
    v7 = v6;
    if ( v6 != -2147024770 )
      break;
    if ( (unsigned __int64)++v4 >= 2 )
      return v7;
  }
  if ( v6 < 0 )
    return v7;
  v8 = hLibModule;
  v9 = hLibModule;
  hLibModule = 0;
  v10 = sub_1400A5D88(&hLibModule, v9, a2);
  if ( v10 == -2147024769 )
  {
    if ( v8 )
      FreeLibrary(v8);
    return 2147942527LL;
  }
  else if ( v10 >= 0 )
  {
    *a1 = hLibModule;
    if ( v8 )
      FreeLibrary(v8);
    return 0;
  }
  else
  {
    if ( v8 )
      FreeLibrary(v8);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x1400a2dac  mov     r11, rsp
0x1400a2daf  mov     [r11+8], rbx
0x1400a2db3  mov     [r11+10h], rbp
0x1400a2db7  push    rsi
0x1400a2db8  push    rdi
0x1400a2db9  push    r14
0x1400a2dbb  sub     rsp, 30h
0x1400a2dbf  lea     rax, aKernel32Dll_0; "kernel32.dll"
0x1400a2dc6  xor     ebx, ebx
0x1400a2dc8  mov     [r11-28h], rax
0x1400a2dcc  mov     rbp, rdx
0x1400a2dcf  lea     rax, aKernelbaseDll; "kernelbase.dll"
0x1400a2dd6  mov     [r11+20h], rbx
0x1400a2dda  mov     [r11-20h], rax
0x1400a2dde  mov     r14, rcx
0x1400a2de1  mov     esi, ebx
0x1400a2de3  mov     rdx, [rsp+rsi*8+48h+var_28]
0x1400a2de8  test    rdx, rdx
0x1400a2deb  jz      loc_1400A2E7A
0x1400a2df1  lea     rcx, [rsp+48h+hLibModule]
0x1400a2df6  call    sub_1400A2BE4
0x1400a2dfb  mov     edi, eax
0x1400a2dfd  cmp     eax, 8007007Eh
0x1400a2e02  jnz     short loc_1400A2E0F
0x1400a2e04  inc     rsi
0x1400a2e07  cmp     rsi, 2
0x1400a2e0b  jb      short loc_1400A2DE3
0x1400a2e0d  jmp     short loc_1400A2E7F
0x1400a2e0f  test    eax, eax
0x1400a2e11  js      short loc_1400A2E7F
0x1400a2e13  mov     rdi, [rsp+48h+hLibModule]
0x1400a2e18  lea     rcx, [rsp+48h+hLibModule]
0x1400a2e1d  mov     rdx, rdi
0x1400a2e20  mov     [rsp+48h+hLibModule], rbx
0x1400a2e25  mov     r8, rbp
0x1400a2e28  call    sub_1400A5D88
0x1400a2e2d  mov     ebp, 8007007Fh
0x1400a2e32  mov     esi, eax
0x1400a2e34  cmp     eax, ebp
0x1400a2e36  jnz     short loc_1400A2E4A
0x1400a2e38  test    rdi, rdi
0x1400a2e3b  jz      short loc_1400A2E46
0x1400a2e3d  mov     rcx, rdi; hLibModule
0x1400a2e40  call    cs:FreeLibrary
0x1400a2e46  mov     eax, ebp
0x1400a2e48  jmp     short loc_1400A2E81
0x1400a2e4a  test    esi, esi
0x1400a2e4c  jns     short loc_1400A2E60
0x1400a2e4e  test    rdi, rdi
0x1400a2e51  jz      short loc_1400A2E5C
0x1400a2e53  mov     rcx, rdi; hLibModule
0x1400a2e56  call    cs:FreeLibrary
0x1400a2e5c  mov     eax, esi
0x1400a2e5e  jmp     short loc_1400A2E81
0x1400a2e60  mov     rax, [rsp+48h+hLibModule]
0x1400a2e65  mov     [r14], rax
0x1400a2e68  test    rdi, rdi
0x1400a2e6b  jz      short loc_1400A2E76
0x1400a2e6d  mov     rcx, rdi; hLibModule
0x1400a2e70  call    cs:FreeLibrary
0x1400a2e76  xor     eax, eax
0x1400a2e78  jmp     short loc_1400A2E81
0x1400a2e7a  mov     edi, 80070057h
0x1400a2e7f  mov     eax, edi
0x1400a2e81  mov     rbx, [rsp+48h+arg_0]
0x1400a2e86  mov     rbp, [rsp+48h+arg_8]
0x1400a2e8b  add     rsp, 30h
0x1400a2e8f  pop     r14
0x1400a2e91  pop     rdi
0x1400a2e92  pop     rsi
0x1400a2e93  retn
```
