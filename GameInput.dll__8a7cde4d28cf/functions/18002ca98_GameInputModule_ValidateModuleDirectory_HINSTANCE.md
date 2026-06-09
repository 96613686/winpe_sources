# GameInputModule::ValidateModuleDirectory(HINSTANCE__ *)

- ea: `0x18002ca98`
- end: `0x18002cb97`
- name: `?ValidateModuleDirectory@GameInputModule@@SAJPEAUHINSTANCE__@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(HINSTANCE hModule)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000389c`

## callees

- `0x18000c11c`
- `0x18002c3b4`
- `0x18002c4d8`
- `0x18002ca98`

## pseudocode

```c
__int64 __fastcall GameInputModule::ValidateModuleDirectory(HINSTANCE hModule)
{
  const struct std::nothrow_t *v2; // rdx
  signed int SystemDirPath; // ebx
  PVOID v5; // rbx
  PVOID P; // [rsp+58h] [rbp+28h] BYREF
  PVOID v7; // [rsp+60h] [rbp+30h]
  unsigned __int64 v8; // [rsp+68h] [rbp+38h] BYREF

  v8 = 0;
  P = 0;
  SystemDirPath = GameInputModule::GetSystemDirPath(0, (const struct std::nothrow_t *)&P, &v8);
  if ( SystemDirPath < 0 )
  {
LABEL_2:
    if ( P )
      operator delete(P, v2);
    return (unsigned int)SystemDirPath;
  }
  v7 = 0;
  SystemDirPath = GameInputModule::GetModulePath(hModule);
  if ( SystemDirPath < 0 )
  {
    if ( v7 )
      operator delete(v7, v2);
    goto LABEL_2;
  }
  v5 = P;
  if ( v7 )
    operator delete(v7, v2);
  if ( v5 )
    operator delete(v5, v2);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002ca98  mov     [rsp-18h+arg_0], rbx
0x18002ca9d  push    rbp
0x18002ca9e  push    rsi
0x18002ca9f  push    rdi
0x18002caa0  mov     rbp, rsp
0x18002caa3  sub     rsp, 30h
0x18002caa7  mov     rsi, rcx
0x18002caaa  mov     [rbp+arg_18], 0
0x18002cab2  xor     ecx, ecx
0x18002cab4  mov     [rbp+P], 0
0x18002cabc  lea     r8, [rbp+arg_18]
0x18002cac0  lea     rdx, [rbp+P]
0x18002cac4  call    ?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z; GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)
0x18002cac9  mov     ebx, eax
0x18002cacb  test    eax, eax
0x18002cacd  jns     short loc_18002CAE4
0x18002cacf  mov     rcx, [rbp+P]; P
0x18002cad3  test    rcx, rcx
0x18002cad6  jz      short loc_18002CADD
0x18002cad8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cadd  mov     eax, ebx
0x18002cadf  jmp     loc_18002CB89
0x18002cae4  mov     rdi, [rbp+arg_18]
0x18002cae8  lea     r9, [rbp+var_10]
0x18002caec  mov     rdx, rdi
0x18002caef  mov     [rbp+var_10], 0
0x18002caf7  lea     r8, [rbp+arg_10]
0x18002cafb  mov     [rbp+arg_10], 0
0x18002cb03  mov     rcx, rsi; hModule
0x18002cb06  call    ?GetModulePath@GameInputModule@@CAJPEAUHINSTANCE__@@_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z; GameInputModule::GetModulePath(HINSTANCE__ *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)
0x18002cb0b  mov     rcx, [rbp+arg_10]; P
0x18002cb0f  mov     ebx, eax
0x18002cb11  test    eax, eax
0x18002cb13  jns     short loc_18002CB21
0x18002cb15  test    rcx, rcx
0x18002cb18  jz      short loc_18002CACF
0x18002cb1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb1f  jmp     short loc_18002CACF
0x18002cb21  mov     rbx, [rbp+P]
0x18002cb25  cmp     [rbp+var_10], rdi
0x18002cb29  jbe     short loc_18002CB6D
0x18002cb2b  lea     r9, [rbx+rdi*2]
0x18002cb2f  mov     r8, rcx
0x18002cb32  mov     rdx, rbx; struct std::nothrow_t *
0x18002cb35  cmp     rbx, r9
0x18002cb38  jz      short loc_18002CB52
0x18002cb3a  movzx   eax, word ptr [r8]
0x18002cb3e  cmp     [rdx], ax
0x18002cb41  jnz     short loc_18002CB6D
0x18002cb43  add     rdx, 2
0x18002cb47  cmp     rdx, r9
0x18002cb4a  jz      short loc_18002CB52
0x18002cb4c  add     r8, 2
0x18002cb50  jmp     short loc_18002CB3A
0x18002cb52  test    rcx, rcx
0x18002cb55  jz      short loc_18002CB5C
0x18002cb57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb5c  test    rbx, rbx
0x18002cb5f  jz      short loc_18002CB69
0x18002cb61  mov     rcx, rbx; P
0x18002cb64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb69  xor     eax, eax
0x18002cb6b  jmp     short loc_18002CB89
0x18002cb6d  test    rcx, rcx
0x18002cb70  jz      short loc_18002CB77
0x18002cb72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb77  test    rbx, rbx
0x18002cb7a  jz      short loc_18002CB84
0x18002cb7c  mov     rcx, rbx; P
0x18002cb7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cb84  mov     eax, 8000FFFFh
0x18002cb89  mov     rbx, [rsp+30h+arg_0]
0x18002cb8e  add     rsp, 30h
0x18002cb92  pop     rdi
0x18002cb93  pop     rsi
0x18002cb94  pop     rbp
0x18002cb95  retn
```
