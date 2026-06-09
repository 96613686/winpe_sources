# __DllMainCRTStartup

- ea: `0x1800045e4`
- end: `0x1800046e5`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800045a0`

## callees

- `0x1800044b4`
- `0x1800045e4`
- `0x180006e74`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_180012080 )
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
0x1800045e4  mov     rax, rsp
0x1800045e7  mov     [rax+18h], r8
0x1800045eb  mov     [rax+10h], edx
0x1800045ee  mov     [rax+8], rcx
0x1800045f2  push    rbx
0x1800045f3  push    rsi
0x1800045f4  push    rdi
0x1800045f5  sub     rsp, 50h
0x1800045f9  mov     edi, edx
0x1800045fb  mov     rsi, rcx
0x1800045fe  test    edx, edx
0x180004600  jnz     short loc_180004614
0x180004602  cmp     cs:dword_180012080, edx
0x180004608  jnz     short loc_180004614
0x18000460a  xor     ebx, ebx
0x18000460c  mov     [rax-48h], ebx
0x18000460f  jmp     loc_1800046DB
0x180004614  lea     eax, [rdx-1]
0x180004617  cmp     eax, 1
0x18000461a  ja      short loc_180004648
0x18000461c  mov     r8, [rsp+68h+lpvReserved]
0x180004624  call    _CRT_INIT
0x180004629  mov     ebx, eax
0x18000462b  mov     [rsp+68h+var_48], eax
0x18000462f  jmp     short loc_180004640
0x180004631  xor     ebx, ebx
0x180004633  mov     [rsp+68h+var_48], ebx
0x180004637  mov     edi, [rsp+68h+arg_8]
0x18000463b  mov     rsi, [rsp+68h+arg_0]
0x180004640  test    ebx, ebx
0x180004642  jz      loc_1800046DB
0x180004648  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x180004650  mov     edx, edi; fdwReason
0x180004652  mov     rcx, rsi; hinstDLL
0x180004655  call    DllMain
0x18000465a  mov     ebx, eax
0x18000465c  mov     [rsp+68h+var_48], eax
0x180004660  jmp     short loc_180004671
0x180004662  xor     ebx, ebx
0x180004664  mov     [rsp+68h+var_48], ebx
0x180004668  mov     edi, [rsp+68h+arg_8]
0x18000466c  mov     rsi, [rsp+68h+arg_0]
0x180004671  cmp     edi, 1
0x180004674  jnz     short loc_1800046B2
0x180004676  test    ebx, ebx
0x180004678  jnz     short loc_1800046B2
0x18000467a  xor     r8d, r8d; lpvReserved
0x18000467d  xor     edx, edx; fdwReason
0x18000467f  mov     rcx, rsi; hinstDLL
0x180004682  call    DllMain
0x180004687  jmp     short loc_180004696
0x180004689  mov     edi, [rsp+68h+arg_8]
0x18000468d  mov     rsi, [rsp+68h+arg_0]
0x180004692  mov     ebx, [rsp+68h+var_48]
0x180004696  xor     r8d, r8d
0x180004699  xor     edx, edx
0x18000469b  mov     rcx, rsi
0x18000469e  call    _CRT_INIT
0x1800046a3  jmp     short loc_1800046B2
0x1800046a5  mov     edi, [rsp+68h+arg_8]
0x1800046a9  mov     rsi, [rsp+68h+arg_0]
0x1800046ae  mov     ebx, [rsp+68h+var_48]
0x1800046b2  test    edi, edi
0x1800046b4  jz      short loc_1800046BB
0x1800046b6  cmp     edi, 3
0x1800046b9  jnz     short loc_1800046DB
0x1800046bb  mov     r8, [rsp+68h+lpvReserved]
0x1800046c3  mov     edx, edi
0x1800046c5  mov     rcx, rsi
0x1800046c8  call    _CRT_INIT
0x1800046cd  mov     ebx, eax
0x1800046cf  mov     [rsp+68h+var_48], eax
0x1800046d3  jmp     short loc_1800046DB
0x1800046d5  xor     ebx, ebx
0x1800046d7  mov     [rsp+68h+var_48], ebx
0x1800046db  mov     eax, ebx
0x1800046dd  add     rsp, 50h
0x1800046e1  pop     rdi
0x1800046e2  pop     rsi
0x1800046e3  pop     rbx
0x1800046e4  retn
0x18000a69c  push    rbp
0x18000a69e  sub     rsp, 20h
0x18000a6a2  mov     rbp, rdx
0x18000a6a5  xor     eax, eax
0x18000a6a7  add     rsp, 20h
0x18000a6ab  pop     rbp
0x18000a6ac  retn
0x18000a6ae  push    rbp
0x18000a6b0  sub     rsp, 20h
0x18000a6b4  mov     rbp, rdx
0x18000a6b7  xor     eax, eax
0x18000a6b9  add     rsp, 20h
0x18000a6bd  pop     rbp
0x18000a6be  retn
0x18000a6c0  push    rbp
0x18000a6c2  sub     rsp, 20h
0x18000a6c6  mov     rbp, rdx
0x18000a6c9  xor     eax, eax
0x18000a6cb  add     rsp, 20h
0x18000a6cf  pop     rbp
0x18000a6d0  retn
0x18000a6d2  push    rbp
0x18000a6d4  sub     rsp, 20h
0x18000a6d8  mov     rbp, rdx
0x18000a6db  xor     eax, eax
0x18000a6dd  add     rsp, 20h
0x18000a6e1  pop     rbp
0x18000a6e2  retn
0x18000a6e4  push    rbp
0x18000a6e6  sub     rsp, 20h
0x18000a6ea  mov     rbp, rdx
0x18000a6ed  xor     eax, eax
0x18000a6ef  add     rsp, 20h
0x18000a6f3  pop     rbp
0x18000a6f4  retn
0x18000a6f6  push    rbp
0x18000a6f8  sub     rsp, 20h
0x18000a6fc  mov     rbp, rdx
0x18000a6ff  add     rsp, 20h
0x18000a703  pop     rbp
0x18000a704  retn
```
