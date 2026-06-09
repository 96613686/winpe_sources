# __DllMainCRTStartup

- ea: `0x180005e34`
- end: `0x180005f35`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005df0`

## callees

- `0x180005d08`
- `0x180005e34`
- `0x180006090`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800134C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 || (v5 = CRT_INIT(hinstDLL, fdwReason, a3)) != 0 )
    {
      v5 = DllMain(hinstDLL, v3, a3);
      if ( v3 == 1 && !v5 )
      {
        DllMain(hinstDLL, 0, 0);
        CRT_INIT(hinstDLL, 0, 0);
      }
      if ( !v3 || v3 == 3 )
        return (unsigned int)CRT_INIT(hinstDLL, v3, a3);
    }
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180005e34  mov     rax, rsp
0x180005e37  mov     [rax+18h], r8
0x180005e3b  mov     [rax+10h], edx
0x180005e3e  mov     [rax+8], rcx
0x180005e42  push    rbx
0x180005e43  push    rsi
0x180005e44  push    rdi
0x180005e45  sub     rsp, 50h
0x180005e49  mov     edi, edx
0x180005e4b  mov     rsi, rcx
0x180005e4e  test    edx, edx
0x180005e50  jnz     short loc_180005E64
0x180005e52  cmp     cs:dword_1800134C0, edx
0x180005e58  jnz     short loc_180005E64
0x180005e5a  xor     ebx, ebx
0x180005e5c  mov     [rax-48h], ebx
0x180005e5f  jmp     loc_180005F2B
0x180005e64  lea     eax, [rdx-1]
0x180005e67  cmp     eax, 1
0x180005e6a  ja      short loc_180005E98
0x180005e6c  mov     r8, [rsp+68h+lpvReserved]
0x180005e74  call    _CRT_INIT
0x180005e79  mov     ebx, eax
0x180005e7b  mov     [rsp+68h+var_48], eax
0x180005e7f  jmp     short loc_180005E90
0x180005e81  xor     ebx, ebx
0x180005e83  mov     [rsp+68h+var_48], ebx
0x180005e87  mov     edi, [rsp+68h+arg_8]
0x180005e8b  mov     rsi, [rsp+68h+arg_0]
0x180005e90  test    ebx, ebx
0x180005e92  jz      loc_180005F2B
0x180005e98  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x180005ea0  mov     edx, edi; fdwReason
0x180005ea2  mov     rcx, rsi; hinstDLL
0x180005ea5  call    DllMain
0x180005eaa  mov     ebx, eax
0x180005eac  mov     [rsp+68h+var_48], eax
0x180005eb0  jmp     short loc_180005EC1
0x180005eb2  xor     ebx, ebx
0x180005eb4  mov     [rsp+68h+var_48], ebx
0x180005eb8  mov     edi, [rsp+68h+arg_8]
0x180005ebc  mov     rsi, [rsp+68h+arg_0]
0x180005ec1  cmp     edi, 1
0x180005ec4  jnz     short loc_180005F02
0x180005ec6  test    ebx, ebx
0x180005ec8  jnz     short loc_180005F02
0x180005eca  xor     r8d, r8d; lpvReserved
0x180005ecd  xor     edx, edx; fdwReason
0x180005ecf  mov     rcx, rsi; hinstDLL
0x180005ed2  call    DllMain
0x180005ed7  jmp     short loc_180005EE6
0x180005ed9  mov     edi, [rsp+68h+arg_8]
0x180005edd  mov     rsi, [rsp+68h+arg_0]
0x180005ee2  mov     ebx, [rsp+68h+var_48]
0x180005ee6  xor     r8d, r8d
0x180005ee9  xor     edx, edx
0x180005eeb  mov     rcx, rsi
0x180005eee  call    _CRT_INIT
0x180005ef3  jmp     short loc_180005F02
0x180005ef5  mov     edi, [rsp+68h+arg_8]
0x180005ef9  mov     rsi, [rsp+68h+arg_0]
0x180005efe  mov     ebx, [rsp+68h+var_48]
0x180005f02  test    edi, edi
0x180005f04  jz      short loc_180005F0B
0x180005f06  cmp     edi, 3
0x180005f09  jnz     short loc_180005F2B
0x180005f0b  mov     r8, [rsp+68h+lpvReserved]
0x180005f13  mov     edx, edi
0x180005f15  mov     rcx, rsi
0x180005f18  call    _CRT_INIT
0x180005f1d  mov     ebx, eax
0x180005f1f  mov     [rsp+68h+var_48], eax
0x180005f23  jmp     short loc_180005F2B
0x180005f25  xor     ebx, ebx
0x180005f27  mov     [rsp+68h+var_48], ebx
0x180005f2b  mov     eax, ebx
0x180005f2d  add     rsp, 50h
0x180005f31  pop     rdi
0x180005f32  pop     rsi
0x180005f33  pop     rbx
0x180005f34  retn
0x18000aa79  push    rbp
0x18000aa7b  sub     rsp, 20h
0x18000aa7f  mov     rbp, rdx
0x18000aa82  xor     eax, eax
0x18000aa84  add     rsp, 20h
0x18000aa88  pop     rbp
0x18000aa89  retn
0x18000aa8b  push    rbp
0x18000aa8d  sub     rsp, 20h
0x18000aa91  mov     rbp, rdx
0x18000aa94  xor     eax, eax
0x18000aa96  add     rsp, 20h
0x18000aa9a  pop     rbp
0x18000aa9b  retn
0x18000aa9d  push    rbp
0x18000aa9f  sub     rsp, 20h
0x18000aaa3  mov     rbp, rdx
0x18000aaa6  xor     eax, eax
0x18000aaa8  add     rsp, 20h
0x18000aaac  pop     rbp
0x18000aaad  retn
0x18000aaaf  push    rbp
0x18000aab1  sub     rsp, 20h
0x18000aab5  mov     rbp, rdx
0x18000aab8  xor     eax, eax
0x18000aaba  add     rsp, 20h
0x18000aabe  pop     rbp
0x18000aabf  retn
0x18000aac1  push    rbp
0x18000aac3  sub     rsp, 20h
0x18000aac7  mov     rbp, rdx
0x18000aaca  xor     eax, eax
0x18000aacc  add     rsp, 20h
0x18000aad0  pop     rbp
0x18000aad1  retn
0x18000aad3  push    rbp
0x18000aad5  sub     rsp, 20h
0x18000aad9  mov     rbp, rdx
0x18000aadc  add     rsp, 20h
0x18000aae0  pop     rbp
0x18000aae1  retn
```
