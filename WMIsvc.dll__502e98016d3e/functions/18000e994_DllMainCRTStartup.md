# __DllMainCRTStartup

- ea: `0x18000e994`
- end: `0x18000eba0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e950`

## callees

- `0x18000c568`
- `0x18000e720`
- `0x18000e994`
- `0x18000ed91`
- `0x18001d410`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800323C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800323C4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800323C4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x18000e994  mov     [rsp+lpvReserved], r8
0x18000e999  mov     [rsp+arg_8], edx
0x18000e99d  mov     [rsp+arg_0], rcx
0x18000e9a2  push    rbx
0x18000e9a3  push    rsi
0x18000e9a4  push    rdi
0x18000e9a5  sub     rsp, 0F0h
0x18000e9ac  mov     edi, edx
0x18000e9ae  mov     rsi, rcx
0x18000e9b1  mov     ebx, 1
0x18000e9b6  cmp     edx, ebx
0x18000e9b8  ja      short loc_18000E9C0
0x18000e9ba  mov     cs:__native_dllmain_reason, edx
0x18000e9c0  test    edx, edx
0x18000e9c2  jnz     short loc_18000E9D7
0x18000e9c4  cmp     cs:dword_1800323C0, edx
0x18000e9ca  jnz     short loc_18000E9D7
0x18000e9cc  xor     ebx, ebx
0x18000e9ce  mov     [rsp+108h+var_E8], ebx
0x18000e9d2  jmp     loc_18000EB84
0x18000e9d7  lea     eax, [rdx-1]
0x18000e9da  cmp     eax, 1
0x18000e9dd  ja      loc_18000EA64
0x18000e9e3  mov     rax, cs:_pRawDllMain
0x18000e9ea  test    rax, rax
0x18000e9ed  jz      short loc_18000EA25
0x18000e9ef  cmp     edx, 1
0x18000e9f2  jnz     short loc_18000E9FA
0x18000e9f4  mov     cs:dword_1800323C4, edx
0x18000e9fa  mov     r8, [rsp+108h+lpvReserved]
0x18000ea02  call    cs:__guard_dispatch_icall_fptr
0x18000ea08  mov     ebx, eax
0x18000ea0a  mov     [rsp+108h+var_E8], eax
0x18000ea0e  jmp     short loc_18000EA25
0x18000ea10  xor     ebx, ebx
0x18000ea12  mov     [rsp+108h+var_E8], ebx
0x18000ea16  mov     edi, [rsp+108h+arg_8]
0x18000ea1d  mov     rsi, [rsp+108h+arg_0]
0x18000ea25  test    ebx, ebx
0x18000ea27  jz      loc_18000EB84
0x18000ea2d  mov     r8, [rsp+108h+lpvReserved]
0x18000ea35  mov     edx, edi
0x18000ea37  mov     rcx, rsi
0x18000ea3a  call    _CRT_INIT
0x18000ea3f  mov     ebx, eax
0x18000ea41  mov     [rsp+108h+var_E8], eax
0x18000ea45  jmp     short loc_18000EA5C
0x18000ea47  xor     ebx, ebx
0x18000ea49  mov     [rsp+108h+var_E8], ebx
0x18000ea4d  mov     edi, [rsp+108h+arg_8]
0x18000ea54  mov     rsi, [rsp+108h+arg_0]
0x18000ea5c  test    ebx, ebx
0x18000ea5e  jz      loc_18000EB84
0x18000ea64  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000ea6c  mov     edx, edi; fdwReason
0x18000ea6e  mov     rcx, rsi; hinstDLL
0x18000ea71  call    DllMain
0x18000ea76  mov     ebx, eax
0x18000ea78  mov     [rsp+108h+var_E8], eax
0x18000ea7c  jmp     short loc_18000EA93
0x18000ea7e  xor     ebx, ebx
0x18000ea80  mov     [rsp+108h+var_E8], ebx
0x18000ea84  mov     edi, [rsp+108h+arg_8]
0x18000ea8b  mov     rsi, [rsp+108h+arg_0]
0x18000ea93  cmp     edi, 1
0x18000ea96  jnz     short loc_18000EB0F
0x18000ea98  test    ebx, ebx
0x18000ea9a  jnz     short loc_18000EB0F
0x18000ea9c  xor     r8d, r8d; lpvReserved
0x18000ea9f  xor     edx, edx; fdwReason
0x18000eaa1  mov     rcx, rsi; hinstDLL
0x18000eaa4  call    DllMain
0x18000eaa9  jmp     short loc_18000EABE
0x18000eaab  mov     edi, [rsp+108h+arg_8]
0x18000eab2  mov     rsi, [rsp+108h+arg_0]
0x18000eaba  mov     ebx, [rsp+108h+var_E8]
0x18000eabe  xor     r8d, r8d
0x18000eac1  xor     edx, edx
0x18000eac3  mov     rcx, rsi
0x18000eac6  call    _CRT_INIT
0x18000eacb  jmp     short loc_18000EAE0
0x18000eacd  mov     edi, [rsp+108h+arg_8]
0x18000ead4  mov     rsi, [rsp+108h+arg_0]
0x18000eadc  mov     ebx, [rsp+108h+var_E8]
0x18000eae0  mov     rax, cs:_pRawDllMain
0x18000eae7  test    rax, rax
0x18000eaea  jz      short loc_18000EB0F
0x18000eaec  xor     r8d, r8d
0x18000eaef  xor     edx, edx
0x18000eaf1  mov     rcx, rsi
0x18000eaf4  call    cs:__guard_dispatch_icall_fptr
0x18000eafa  jmp     short loc_18000EB0F
0x18000eafc  mov     edi, [rsp+108h+arg_8]
0x18000eb03  mov     rsi, [rsp+108h+arg_0]
0x18000eb0b  mov     ebx, [rsp+108h+var_E8]
0x18000eb0f  test    edi, edi
0x18000eb11  jz      short loc_18000EB18
0x18000eb13  cmp     edi, 3
0x18000eb16  jnz     short loc_18000EB84
0x18000eb18  mov     r8, [rsp+108h+lpvReserved]
0x18000eb20  mov     edx, edi
0x18000eb22  mov     rcx, rsi
0x18000eb25  call    _CRT_INIT
0x18000eb2a  mov     ebx, eax
0x18000eb2c  mov     [rsp+108h+var_E8], eax
0x18000eb30  jmp     short loc_18000EB47
0x18000eb32  xor     ebx, ebx
0x18000eb34  mov     [rsp+108h+var_E8], ebx
0x18000eb38  mov     edi, [rsp+108h+arg_8]
0x18000eb3f  mov     rsi, [rsp+108h+arg_0]
0x18000eb47  mov     rax, cs:_pRawDllMain
0x18000eb4e  test    rax, rax
0x18000eb51  jz      short loc_18000EB84
0x18000eb53  cmp     cs:dword_1800323C4, 0
0x18000eb5a  jz      short loc_18000EB84
0x18000eb5c  mov     r8, [rsp+108h+lpvReserved]
0x18000eb64  mov     edx, edi
0x18000eb66  mov     rcx, rsi
0x18000eb69  call    cs:__guard_dispatch_icall_fptr
0x18000eb6f  mov     ebx, eax
0x18000eb71  mov     [rsp+108h+var_E8], eax
0x18000eb75  jmp     short loc_18000EB84
0x18000eb77  xor     ebx, ebx
0x18000eb79  mov     [rsp+108h+var_E8], ebx
0x18000eb7d  mov     edi, [rsp+108h+arg_8]
0x18000eb84  cmp     edi, 1
0x18000eb87  ja      short loc_18000EB93
0x18000eb89  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000eb93  mov     eax, ebx
0x18000eb95  add     rsp, 0F0h
0x18000eb9c  pop     rdi
0x18000eb9d  pop     rsi
0x18000eb9e  pop     rbx
0x18000eb9f  retn
0x18001e330  push    rbp
0x18001e332  sub     rsp, 20h
0x18001e336  mov     rbp, rdx
0x18001e339  mov     rax, [rcx]
0x18001e33c  mov     edx, [rax]
0x18001e33e  mov     [rbp+0A8h], rcx
0x18001e345  mov     [rbp+28h], edx
0x18001e348  mov     eax, [rbp+28h]
0x18001e34b  cmp     eax, 0E06D7363h
0x18001e350  jnz     short loc_18001E366
0x18001e352  mov     rdx, [rbp+0A8h]
0x18001e359  mov     ecx, [rbp+28h]
0x18001e35c  call    _XcptFilter_0
0x18001e361  mov     [rbp+30h], eax
0x18001e364  jmp     short loc_18001E36D
0x18001e366  mov     dword ptr [rbp+30h], 0
0x18001e36d  mov     eax, [rbp+30h]
0x18001e370  add     rsp, 20h
0x18001e374  pop     rbp
0x18001e375  retn
0x18001e377  push    rbp
0x18001e379  sub     rsp, 20h
0x18001e37d  mov     rbp, rdx
0x18001e380  mov     rax, [rcx]
0x18001e383  mov     edx, [rax]
0x18001e385  mov     [rbp+0B0h], rcx
0x18001e38c  mov     [rbp+38h], edx
0x18001e38f  mov     eax, [rbp+38h]
0x18001e392  cmp     eax, 0E06D7363h
0x18001e397  jnz     short loc_18001E3AD
0x18001e399  mov     rdx, [rbp+0B0h]
0x18001e3a0  mov     ecx, [rbp+38h]
0x18001e3a3  call    _XcptFilter_0
0x18001e3a8  mov     [rbp+40h], eax
0x18001e3ab  jmp     short loc_18001E3B4
0x18001e3ad  mov     dword ptr [rbp+40h], 0
0x18001e3b4  mov     eax, [rbp+40h]
0x18001e3b7  add     rsp, 20h
0x18001e3bb  pop     rbp
0x18001e3bc  retn
0x18001e3be  push    rbp
0x18001e3c0  sub     rsp, 20h
0x18001e3c4  mov     rbp, rdx
0x18001e3c7  mov     rax, [rcx]
0x18001e3ca  mov     edx, [rax]
0x18001e3cc  mov     [rbp+0B8h], rcx
0x18001e3d3  mov     [rbp+48h], edx
0x18001e3d6  mov     eax, [rbp+48h]
0x18001e3d9  cmp     eax, 0E06D7363h
0x18001e3de  jnz     short loc_18001E3F4
0x18001e3e0  mov     rdx, [rbp+0B8h]
0x18001e3e7  mov     ecx, [rbp+48h]
0x18001e3ea  call    _XcptFilter_0
0x18001e3ef  mov     [rbp+50h], eax
0x18001e3f2  jmp     short loc_18001E3FB
0x18001e3f4  mov     dword ptr [rbp+50h], 0
0x18001e3fb  mov     eax, [rbp+50h]
0x18001e3fe  add     rsp, 20h
0x18001e402  pop     rbp
0x18001e403  retn
0x18001e405  push    rbp
0x18001e407  sub     rsp, 20h
0x18001e40b  mov     rbp, rdx
0x18001e40e  mov     rax, [rcx]
0x18001e411  mov     edx, [rax]
0x18001e413  mov     [rbp+0C0h], rcx
0x18001e41a  mov     [rbp+58h], edx
0x18001e41d  mov     eax, [rbp+58h]
0x18001e420  cmp     eax, 0E06D7363h
0x18001e425  jnz     short loc_18001E43B
0x18001e427  mov     rdx, [rbp+0C0h]
0x18001e42e  mov     ecx, [rbp+58h]
0x18001e431  call    _XcptFilter_0
0x18001e436  mov     [rbp+60h], eax
0x18001e439  jmp     short loc_18001E442
0x18001e43b  mov     dword ptr [rbp+60h], 0
0x18001e442  mov     eax, [rbp+60h]
0x18001e445  add     rsp, 20h
0x18001e449  pop     rbp
0x18001e44a  retn
0x18001e44c  push    rbp
0x18001e44e  sub     rsp, 20h
0x18001e452  mov     rbp, rdx
0x18001e455  mov     rax, [rcx]
0x18001e458  mov     edx, [rax]
0x18001e45a  mov     [rbp+0C8h], rcx
0x18001e461  mov     [rbp+68h], edx
0x18001e464  mov     eax, [rbp+68h]
0x18001e467  cmp     eax, 0E06D7363h
0x18001e46c  jnz     short loc_18001E482
0x18001e46e  mov     rdx, [rbp+0C8h]
0x18001e475  mov     ecx, [rbp+68h]
0x18001e478  call    _XcptFilter_0
0x18001e47d  mov     [rbp+70h], eax
0x18001e480  jmp     short loc_18001E489
0x18001e482  mov     dword ptr [rbp+70h], 0
0x18001e489  mov     eax, [rbp+70h]
0x18001e48c  add     rsp, 20h
0x18001e490  pop     rbp
0x18001e491  retn
0x18001e493  push    rbp
0x18001e495  sub     rsp, 20h
0x18001e499  mov     rbp, rdx
0x18001e49c  mov     rax, [rcx]
0x18001e49f  mov     edx, [rax]
0x18001e4a1  mov     [rbp+0D0h], rcx
0x18001e4a8  mov     [rbp+78h], edx
0x18001e4ab  mov     eax, [rbp+78h]
0x18001e4ae  cmp     eax, 0E06D7363h
0x18001e4b3  jnz     short loc_18001E4CC
0x18001e4b5  mov     rdx, [rbp+0D0h]
0x18001e4bc  mov     ecx, [rbp+78h]
0x18001e4bf  call    _XcptFilter_0
0x18001e4c4  mov     [rbp+80h], eax
0x18001e4ca  jmp     short loc_18001E4D6
0x18001e4cc  mov     dword ptr [rbp+80h], 0
0x18001e4d6  mov     eax, [rbp+80h]
0x18001e4dc  add     rsp, 20h
0x18001e4e0  pop     rbp
0x18001e4e1  retn
0x18001e4e3  push    rbp
0x18001e4e5  sub     rsp, 20h
0x18001e4e9  mov     rbp, rdx
0x18001e4ec  mov     rax, [rcx]
0x18001e4ef  mov     edx, [rax]
0x18001e4f1  mov     [rbp+0D8h], rcx
0x18001e4f8  mov     [rbp+88h], edx
0x18001e4fe  mov     eax, [rbp+88h]
0x18001e504  cmp     eax, 0E06D7363h
0x18001e509  jnz     short loc_18001E525
0x18001e50b  mov     rdx, [rbp+0D8h]
0x18001e512  mov     ecx, [rbp+88h]
0x18001e518  call    _XcptFilter_0
0x18001e51d  mov     [rbp+90h], eax
0x18001e523  jmp     short loc_18001E52F
0x18001e525  mov     dword ptr [rbp+90h], 0
0x18001e52f  mov     eax, [rbp+90h]
0x18001e535  add     rsp, 20h
0x18001e539  pop     rbp
0x18001e53a  retn
0x18001e53c  push    rbp
0x18001e53e  sub     rsp, 20h
0x18001e542  mov     rbp, rdx
0x18001e545  mov     rax, [rcx]
0x18001e548  mov     edx, [rax]
0x18001e54a  mov     [rbp+0E0h], rcx
0x18001e551  mov     [rbp+98h], edx
0x18001e557  mov     eax, [rbp+98h]
0x18001e55d  cmp     eax, 0E06D7363h
0x18001e562  jnz     short loc_18001E57E
0x18001e564  mov     rdx, [rbp+0E0h]
0x18001e56b  mov     ecx, [rbp+98h]
0x18001e571  call    _XcptFilter_0
0x18001e576  mov     [rbp+0A0h], eax
0x18001e57c  jmp     short loc_18001E588
0x18001e57e  mov     dword ptr [rbp+0A0h], 0
0x18001e588  mov     eax, [rbp+0A0h]
0x18001e58e  add     rsp, 20h
0x18001e592  pop     rbp
0x18001e593  retn
0x18001e595  push    rbp
0x18001e597  sub     rsp, 20h
0x18001e59b  mov     rbp, rdx
0x18001e59e  cmp     dword ptr [rbp+118h], 1
0x18001e5a5  ja      short loc_18001E5B1
0x18001e5a7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
