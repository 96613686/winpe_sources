# __DllMainCRTStartup

- ea: `0x180001494`
- end: `0x180001595`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x180001364`
- `0x180001494`
- `0x180001778`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800122C0 )
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
0x180001494  mov     rax, rsp
0x180001497  mov     [rax+18h], r8
0x18000149b  mov     [rax+10h], edx
0x18000149e  mov     [rax+8], rcx
0x1800014a2  push    rbx
0x1800014a3  push    rsi
0x1800014a4  push    rdi
0x1800014a5  sub     rsp, 50h
0x1800014a9  mov     edi, edx
0x1800014ab  mov     rsi, rcx
0x1800014ae  test    edx, edx
0x1800014b0  jnz     short loc_1800014C4
0x1800014b2  cmp     cs:dword_1800122C0, edx
0x1800014b8  jnz     short loc_1800014C4
0x1800014ba  xor     ebx, ebx
0x1800014bc  mov     [rax-48h], ebx
0x1800014bf  jmp     loc_18000158B
0x1800014c4  lea     eax, [rdx-1]
0x1800014c7  cmp     eax, 1
0x1800014ca  ja      short loc_1800014F8
0x1800014cc  mov     r8, [rsp+68h+lpvReserved]
0x1800014d4  call    _CRT_INIT
0x1800014d9  mov     ebx, eax
0x1800014db  mov     [rsp+68h+var_48], eax
0x1800014df  jmp     short loc_1800014F0
0x1800014e1  xor     ebx, ebx
0x1800014e3  mov     [rsp+68h+var_48], ebx
0x1800014e7  mov     edi, [rsp+68h+arg_8]
0x1800014eb  mov     rsi, [rsp+68h+arg_0]
0x1800014f0  test    ebx, ebx
0x1800014f2  jz      loc_18000158B
0x1800014f8  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x180001500  mov     edx, edi; fdwReason
0x180001502  mov     rcx, rsi; hinstDLL
0x180001505  call    DllMain
0x18000150a  mov     ebx, eax
0x18000150c  mov     [rsp+68h+var_48], eax
0x180001510  jmp     short loc_180001521
0x180001512  xor     ebx, ebx
0x180001514  mov     [rsp+68h+var_48], ebx
0x180001518  mov     edi, [rsp+68h+arg_8]
0x18000151c  mov     rsi, [rsp+68h+arg_0]
0x180001521  cmp     edi, 1
0x180001524  jnz     short loc_180001562
0x180001526  test    ebx, ebx
0x180001528  jnz     short loc_180001562
0x18000152a  xor     r8d, r8d; lpvReserved
0x18000152d  xor     edx, edx; fdwReason
0x18000152f  mov     rcx, rsi; hinstDLL
0x180001532  call    DllMain
0x180001537  jmp     short loc_180001546
0x180001539  mov     edi, [rsp+68h+arg_8]
0x18000153d  mov     rsi, [rsp+68h+arg_0]
0x180001542  mov     ebx, [rsp+68h+var_48]
0x180001546  xor     r8d, r8d
0x180001549  xor     edx, edx
0x18000154b  mov     rcx, rsi
0x18000154e  call    _CRT_INIT
0x180001553  jmp     short loc_180001562
0x180001555  mov     edi, [rsp+68h+arg_8]
0x180001559  mov     rsi, [rsp+68h+arg_0]
0x18000155e  mov     ebx, [rsp+68h+var_48]
0x180001562  test    edi, edi
0x180001564  jz      short loc_18000156B
0x180001566  cmp     edi, 3
0x180001569  jnz     short loc_18000158B
0x18000156b  mov     r8, [rsp+68h+lpvReserved]
0x180001573  mov     edx, edi
0x180001575  mov     rcx, rsi
0x180001578  call    _CRT_INIT
0x18000157d  mov     ebx, eax
0x18000157f  mov     [rsp+68h+var_48], eax
0x180001583  jmp     short loc_18000158B
0x180001585  xor     ebx, ebx
0x180001587  mov     [rsp+68h+var_48], ebx
0x18000158b  mov     eax, ebx
0x18000158d  add     rsp, 50h
0x180001591  pop     rdi
0x180001592  pop     rsi
0x180001593  pop     rbx
0x180001594  retn
0x18000c66c  push    rbp
0x18000c66e  sub     rsp, 20h
0x18000c672  mov     rbp, rdx
0x18000c675  xor     eax, eax
0x18000c677  add     rsp, 20h
0x18000c67b  pop     rbp
0x18000c67c  retn
0x18000c67e  push    rbp
0x18000c680  sub     rsp, 20h
0x18000c684  mov     rbp, rdx
0x18000c687  xor     eax, eax
0x18000c689  add     rsp, 20h
0x18000c68d  pop     rbp
0x18000c68e  retn
0x18000c690  push    rbp
0x18000c692  sub     rsp, 20h
0x18000c696  mov     rbp, rdx
0x18000c699  xor     eax, eax
0x18000c69b  add     rsp, 20h
0x18000c69f  pop     rbp
0x18000c6a0  retn
0x18000c6a2  push    rbp
0x18000c6a4  sub     rsp, 20h
0x18000c6a8  mov     rbp, rdx
0x18000c6ab  xor     eax, eax
0x18000c6ad  add     rsp, 20h
0x18000c6b1  pop     rbp
0x18000c6b2  retn
0x18000c6b4  push    rbp
0x18000c6b6  sub     rsp, 20h
0x18000c6ba  mov     rbp, rdx
0x18000c6bd  xor     eax, eax
0x18000c6bf  add     rsp, 20h
0x18000c6c3  pop     rbp
0x18000c6c4  retn
0x18000c6c6  push    rbp
0x18000c6c8  sub     rsp, 20h
0x18000c6cc  mov     rbp, rdx
0x18000c6cf  add     rsp, 20h
0x18000c6d3  pop     rbp
0x18000c6d4  retn
```
