# __DllMainCRTStartup

- ea: `0x180001eb4`
- end: `0x180001fb5`
- name: `__DllMainCRTStartup`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001e70`

## callees

- `0x180001d80`
- `0x180001eb4`
- `0x1800020e4`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  if ( (_DWORD)fdwReason || dword_18000A0A0 )
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
0x180001eb4  mov     rax, rsp
0x180001eb7  mov     [rax+18h], r8
0x180001ebb  mov     [rax+10h], edx
0x180001ebe  mov     [rax+8], rcx
0x180001ec2  push    rbx
0x180001ec3  push    rsi
0x180001ec4  push    rdi
0x180001ec5  sub     rsp, 50h
0x180001ec9  mov     edi, edx
0x180001ecb  mov     rsi, rcx
0x180001ece  test    edx, edx
0x180001ed0  jnz     short loc_180001EE4
0x180001ed2  cmp     cs:dword_18000A0A0, edx
0x180001ed8  jnz     short loc_180001EE4
0x180001eda  xor     ebx, ebx
0x180001edc  mov     [rax-48h], ebx
0x180001edf  jmp     loc_180001FAB
0x180001ee4  lea     eax, [rdx-1]
0x180001ee7  cmp     eax, 1
0x180001eea  ja      short loc_180001F18
0x180001eec  mov     r8, [rsp+68h+lpvReserved]
0x180001ef4  call    _CRT_INIT
0x180001ef9  mov     ebx, eax
0x180001efb  mov     [rsp+68h+var_48], eax
0x180001eff  jmp     short loc_180001F10
0x180001f01  xor     ebx, ebx
0x180001f03  mov     [rsp+68h+var_48], ebx
0x180001f07  mov     edi, [rsp+68h+arg_8]
0x180001f0b  mov     rsi, [rsp+68h+arg_0]
0x180001f10  test    ebx, ebx
0x180001f12  jz      loc_180001FAB
0x180001f18  mov     r8, [rsp+68h+lpvReserved]; lpvReserved
0x180001f20  mov     edx, edi; fdwReason
0x180001f22  mov     rcx, rsi; hinstDLL
0x180001f25  call    DllMain
0x180001f2a  mov     ebx, eax
0x180001f2c  mov     [rsp+68h+var_48], eax
0x180001f30  jmp     short loc_180001F41
0x180001f32  xor     ebx, ebx
0x180001f34  mov     [rsp+68h+var_48], ebx
0x180001f38  mov     edi, [rsp+68h+arg_8]
0x180001f3c  mov     rsi, [rsp+68h+arg_0]
0x180001f41  cmp     edi, 1
0x180001f44  jnz     short loc_180001F82
0x180001f46  test    ebx, ebx
0x180001f48  jnz     short loc_180001F82
0x180001f4a  xor     r8d, r8d; lpvReserved
0x180001f4d  xor     edx, edx; fdwReason
0x180001f4f  mov     rcx, rsi; hinstDLL
0x180001f52  call    DllMain
0x180001f57  jmp     short loc_180001F66
0x180001f59  mov     edi, [rsp+68h+arg_8]
0x180001f5d  mov     rsi, [rsp+68h+arg_0]
0x180001f62  mov     ebx, [rsp+68h+var_48]
0x180001f66  xor     r8d, r8d
0x180001f69  xor     edx, edx
0x180001f6b  mov     rcx, rsi
0x180001f6e  call    _CRT_INIT
0x180001f73  jmp     short loc_180001F82
0x180001f75  mov     edi, [rsp+68h+arg_8]
0x180001f79  mov     rsi, [rsp+68h+arg_0]
0x180001f7e  mov     ebx, [rsp+68h+var_48]
0x180001f82  test    edi, edi
0x180001f84  jz      short loc_180001F8B
0x180001f86  cmp     edi, 3
0x180001f89  jnz     short loc_180001FAB
0x180001f8b  mov     r8, [rsp+68h+lpvReserved]
0x180001f93  mov     edx, edi
0x180001f95  mov     rcx, rsi
0x180001f98  call    _CRT_INIT
0x180001f9d  mov     ebx, eax
0x180001f9f  mov     [rsp+68h+var_48], eax
0x180001fa3  jmp     short loc_180001FAB
0x180001fa5  xor     ebx, ebx
0x180001fa7  mov     [rsp+68h+var_48], ebx
0x180001fab  mov     eax, ebx
0x180001fad  add     rsp, 50h
0x180001fb1  pop     rdi
0x180001fb2  pop     rsi
0x180001fb3  pop     rbx
0x180001fb4  retn
0x1800033ec  push    rbp
0x1800033ee  sub     rsp, 20h
0x1800033f2  mov     rbp, rdx
0x1800033f5  xor     eax, eax
0x1800033f7  add     rsp, 20h
0x1800033fb  pop     rbp
0x1800033fc  retn
0x1800033fe  push    rbp
0x180003400  sub     rsp, 20h
0x180003404  mov     rbp, rdx
0x180003407  xor     eax, eax
0x180003409  add     rsp, 20h
0x18000340d  pop     rbp
0x18000340e  retn
0x180003410  push    rbp
0x180003412  sub     rsp, 20h
0x180003416  mov     rbp, rdx
0x180003419  xor     eax, eax
0x18000341b  add     rsp, 20h
0x18000341f  pop     rbp
0x180003420  retn
0x180003422  push    rbp
0x180003424  sub     rsp, 20h
0x180003428  mov     rbp, rdx
0x18000342b  xor     eax, eax
0x18000342d  add     rsp, 20h
0x180003431  pop     rbp
0x180003432  retn
0x180003434  push    rbp
0x180003436  sub     rsp, 20h
0x18000343a  mov     rbp, rdx
0x18000343d  xor     eax, eax
0x18000343f  add     rsp, 20h
0x180003443  pop     rbp
0x180003444  retn
0x180003446  push    rbp
0x180003448  sub     rsp, 20h
0x18000344c  mov     rbp, rdx
0x18000344f  add     rsp, 20h
0x180003453  pop     rbp
0x180003454  retn
```
