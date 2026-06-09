# __DllMainCRTStartup

- ea: `0x1800019f4`
- end: `0x180001c00`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800019b0`

## callees

- `0x180001780`
- `0x1800019f4`
- `0x180001dfe`
- `0x18000c718`
- `0x180010830`

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
  if ( (_DWORD)fdwReason || dword_18001B79C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001B7A0 = 1;
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
            if ( dword_18001B7A0 )
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
0x1800019f4  mov     [rsp+lpvReserved], r8
0x1800019f9  mov     [rsp+arg_8], edx
0x1800019fd  mov     [rsp+arg_0], rcx
0x180001a02  push    rbx
0x180001a03  push    rsi
0x180001a04  push    rdi
0x180001a05  sub     rsp, 0F0h
0x180001a0c  mov     edi, edx
0x180001a0e  mov     rsi, rcx
0x180001a11  mov     ebx, 1
0x180001a16  cmp     edx, ebx
0x180001a18  ja      short loc_180001A20
0x180001a1a  mov     cs:__native_dllmain_reason, edx
0x180001a20  test    edx, edx
0x180001a22  jnz     short loc_180001A37
0x180001a24  cmp     cs:dword_18001B79C, edx
0x180001a2a  jnz     short loc_180001A37
0x180001a2c  xor     ebx, ebx
0x180001a2e  mov     [rsp+108h+var_E8], ebx
0x180001a32  jmp     loc_180001BE4
0x180001a37  lea     eax, [rdx-1]
0x180001a3a  cmp     eax, 1
0x180001a3d  ja      loc_180001AC4
0x180001a43  mov     rax, cs:_pRawDllMain
0x180001a4a  test    rax, rax
0x180001a4d  jz      short loc_180001A85
0x180001a4f  cmp     edx, 1
0x180001a52  jnz     short loc_180001A5A
0x180001a54  mov     cs:dword_18001B7A0, edx
0x180001a5a  mov     r8, [rsp+108h+lpvReserved]
0x180001a62  call    cs:__guard_dispatch_icall_fptr
0x180001a68  mov     ebx, eax
0x180001a6a  mov     [rsp+108h+var_E8], eax
0x180001a6e  jmp     short loc_180001A85
0x180001a70  xor     ebx, ebx
0x180001a72  mov     [rsp+108h+var_E8], ebx
0x180001a76  mov     edi, [rsp+108h+arg_8]
0x180001a7d  mov     rsi, [rsp+108h+arg_0]
0x180001a85  test    ebx, ebx
0x180001a87  jz      loc_180001BE4
0x180001a8d  mov     r8, [rsp+108h+lpvReserved]
0x180001a95  mov     edx, edi
0x180001a97  mov     rcx, rsi
0x180001a9a  call    _CRT_INIT
0x180001a9f  mov     ebx, eax
0x180001aa1  mov     [rsp+108h+var_E8], eax
0x180001aa5  jmp     short loc_180001ABC
0x180001aa7  xor     ebx, ebx
0x180001aa9  mov     [rsp+108h+var_E8], ebx
0x180001aad  mov     edi, [rsp+108h+arg_8]
0x180001ab4  mov     rsi, [rsp+108h+arg_0]
0x180001abc  test    ebx, ebx
0x180001abe  jz      loc_180001BE4
0x180001ac4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001acc  mov     edx, edi; fdwReason
0x180001ace  mov     rcx, rsi; hinstDLL
0x180001ad1  call    DllMain
0x180001ad6  mov     ebx, eax
0x180001ad8  mov     [rsp+108h+var_E8], eax
0x180001adc  jmp     short loc_180001AF3
0x180001ade  xor     ebx, ebx
0x180001ae0  mov     [rsp+108h+var_E8], ebx
0x180001ae4  mov     edi, [rsp+108h+arg_8]
0x180001aeb  mov     rsi, [rsp+108h+arg_0]
0x180001af3  cmp     edi, 1
0x180001af6  jnz     short loc_180001B6F
0x180001af8  test    ebx, ebx
0x180001afa  jnz     short loc_180001B6F
0x180001afc  xor     r8d, r8d; lpvReserved
0x180001aff  xor     edx, edx; fdwReason
0x180001b01  mov     rcx, rsi; hinstDLL
0x180001b04  call    DllMain
0x180001b09  jmp     short loc_180001B1E
0x180001b0b  mov     edi, [rsp+108h+arg_8]
0x180001b12  mov     rsi, [rsp+108h+arg_0]
0x180001b1a  mov     ebx, [rsp+108h+var_E8]
0x180001b1e  xor     r8d, r8d
0x180001b21  xor     edx, edx
0x180001b23  mov     rcx, rsi
0x180001b26  call    _CRT_INIT
0x180001b2b  jmp     short loc_180001B40
0x180001b2d  mov     edi, [rsp+108h+arg_8]
0x180001b34  mov     rsi, [rsp+108h+arg_0]
0x180001b3c  mov     ebx, [rsp+108h+var_E8]
0x180001b40  mov     rax, cs:_pRawDllMain
0x180001b47  test    rax, rax
0x180001b4a  jz      short loc_180001B6F
0x180001b4c  xor     r8d, r8d
0x180001b4f  xor     edx, edx
0x180001b51  mov     rcx, rsi
0x180001b54  call    cs:__guard_dispatch_icall_fptr
0x180001b5a  jmp     short loc_180001B6F
0x180001b5c  mov     edi, [rsp+108h+arg_8]
0x180001b63  mov     rsi, [rsp+108h+arg_0]
0x180001b6b  mov     ebx, [rsp+108h+var_E8]
0x180001b6f  test    edi, edi
0x180001b71  jz      short loc_180001B78
0x180001b73  cmp     edi, 3
0x180001b76  jnz     short loc_180001BE4
0x180001b78  mov     r8, [rsp+108h+lpvReserved]
0x180001b80  mov     edx, edi
0x180001b82  mov     rcx, rsi
0x180001b85  call    _CRT_INIT
0x180001b8a  mov     ebx, eax
0x180001b8c  mov     [rsp+108h+var_E8], eax
0x180001b90  jmp     short loc_180001BA7
0x180001b92  xor     ebx, ebx
0x180001b94  mov     [rsp+108h+var_E8], ebx
0x180001b98  mov     edi, [rsp+108h+arg_8]
0x180001b9f  mov     rsi, [rsp+108h+arg_0]
0x180001ba7  mov     rax, cs:_pRawDllMain
0x180001bae  test    rax, rax
0x180001bb1  jz      short loc_180001BE4
0x180001bb3  cmp     cs:dword_18001B7A0, 0
0x180001bba  jz      short loc_180001BE4
0x180001bbc  mov     r8, [rsp+108h+lpvReserved]
0x180001bc4  mov     edx, edi
0x180001bc6  mov     rcx, rsi
0x180001bc9  call    cs:__guard_dispatch_icall_fptr
0x180001bcf  mov     ebx, eax
0x180001bd1  mov     [rsp+108h+var_E8], eax
0x180001bd5  jmp     short loc_180001BE4
0x180001bd7  xor     ebx, ebx
0x180001bd9  mov     [rsp+108h+var_E8], ebx
0x180001bdd  mov     edi, [rsp+108h+arg_8]
0x180001be4  cmp     edi, 1
0x180001be7  ja      short loc_180001BF3
0x180001be9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001bf3  mov     eax, ebx
0x180001bf5  add     rsp, 0F0h
0x180001bfc  pop     rdi
0x180001bfd  pop     rsi
0x180001bfe  pop     rbx
0x180001bff  retn
0x1800108d3  push    rbp
0x1800108d5  sub     rsp, 20h
0x1800108d9  mov     rbp, rdx
0x1800108dc  mov     rax, [rcx]
0x1800108df  mov     edx, [rax]
0x1800108e1  mov     [rbp+0A8h], rcx
0x1800108e8  mov     [rbp+28h], edx
0x1800108eb  mov     eax, [rbp+28h]
0x1800108ee  cmp     eax, 0E06D7363h
0x1800108f3  jnz     short loc_180010909
0x1800108f5  mov     rdx, [rbp+0A8h]
0x1800108fc  mov     ecx, [rbp+28h]
0x1800108ff  call    _XcptFilter_0
0x180010904  mov     [rbp+30h], eax
0x180010907  jmp     short loc_180010910
0x180010909  mov     dword ptr [rbp+30h], 0
0x180010910  mov     eax, [rbp+30h]
0x180010913  add     rsp, 20h
0x180010917  pop     rbp
0x180010918  retn
0x18001091a  push    rbp
0x18001091c  sub     rsp, 20h
0x180010920  mov     rbp, rdx
0x180010923  mov     rax, [rcx]
0x180010926  mov     edx, [rax]
0x180010928  mov     [rbp+0B0h], rcx
0x18001092f  mov     [rbp+38h], edx
0x180010932  mov     eax, [rbp+38h]
0x180010935  cmp     eax, 0E06D7363h
0x18001093a  jnz     short loc_180010950
0x18001093c  mov     rdx, [rbp+0B0h]
0x180010943  mov     ecx, [rbp+38h]
0x180010946  call    _XcptFilter_0
0x18001094b  mov     [rbp+40h], eax
0x18001094e  jmp     short loc_180010957
0x180010950  mov     dword ptr [rbp+40h], 0
0x180010957  mov     eax, [rbp+40h]
0x18001095a  add     rsp, 20h
0x18001095e  pop     rbp
0x18001095f  retn
0x180010961  push    rbp
0x180010963  sub     rsp, 20h
0x180010967  mov     rbp, rdx
0x18001096a  mov     rax, [rcx]
0x18001096d  mov     edx, [rax]
0x18001096f  mov     [rbp+0B8h], rcx
0x180010976  mov     [rbp+48h], edx
0x180010979  mov     eax, [rbp+48h]
0x18001097c  cmp     eax, 0E06D7363h
0x180010981  jnz     short loc_180010997
0x180010983  mov     rdx, [rbp+0B8h]
0x18001098a  mov     ecx, [rbp+48h]
0x18001098d  call    _XcptFilter_0
0x180010992  mov     [rbp+50h], eax
0x180010995  jmp     short loc_18001099E
0x180010997  mov     dword ptr [rbp+50h], 0
0x18001099e  mov     eax, [rbp+50h]
0x1800109a1  add     rsp, 20h
0x1800109a5  pop     rbp
0x1800109a6  retn
0x1800109a8  push    rbp
0x1800109aa  sub     rsp, 20h
0x1800109ae  mov     rbp, rdx
0x1800109b1  mov     rax, [rcx]
0x1800109b4  mov     edx, [rax]
0x1800109b6  mov     [rbp+0C0h], rcx
0x1800109bd  mov     [rbp+58h], edx
0x1800109c0  mov     eax, [rbp+58h]
0x1800109c3  cmp     eax, 0E06D7363h
0x1800109c8  jnz     short loc_1800109DE
0x1800109ca  mov     rdx, [rbp+0C0h]
0x1800109d1  mov     ecx, [rbp+58h]
0x1800109d4  call    _XcptFilter_0
0x1800109d9  mov     [rbp+60h], eax
0x1800109dc  jmp     short loc_1800109E5
0x1800109de  mov     dword ptr [rbp+60h], 0
0x1800109e5  mov     eax, [rbp+60h]
0x1800109e8  add     rsp, 20h
0x1800109ec  pop     rbp
0x1800109ed  retn
0x1800109ef  push    rbp
0x1800109f1  sub     rsp, 20h
0x1800109f5  mov     rbp, rdx
0x1800109f8  mov     rax, [rcx]
0x1800109fb  mov     edx, [rax]
0x1800109fd  mov     [rbp+0C8h], rcx
0x180010a04  mov     [rbp+68h], edx
0x180010a07  mov     eax, [rbp+68h]
0x180010a0a  cmp     eax, 0E06D7363h
0x180010a0f  jnz     short loc_180010A25
0x180010a11  mov     rdx, [rbp+0C8h]
0x180010a18  mov     ecx, [rbp+68h]
0x180010a1b  call    _XcptFilter_0
0x180010a20  mov     [rbp+70h], eax
0x180010a23  jmp     short loc_180010A2C
0x180010a25  mov     dword ptr [rbp+70h], 0
0x180010a2c  mov     eax, [rbp+70h]
0x180010a2f  add     rsp, 20h
0x180010a33  pop     rbp
0x180010a34  retn
0x180010a36  push    rbp
0x180010a38  sub     rsp, 20h
0x180010a3c  mov     rbp, rdx
0x180010a3f  mov     rax, [rcx]
0x180010a42  mov     edx, [rax]
0x180010a44  mov     [rbp+0D0h], rcx
0x180010a4b  mov     [rbp+78h], edx
0x180010a4e  mov     eax, [rbp+78h]
0x180010a51  cmp     eax, 0E06D7363h
0x180010a56  jnz     short loc_180010A6F
0x180010a58  mov     rdx, [rbp+0D0h]
0x180010a5f  mov     ecx, [rbp+78h]
0x180010a62  call    _XcptFilter_0
0x180010a67  mov     [rbp+80h], eax
0x180010a6d  jmp     short loc_180010A79
0x180010a6f  mov     dword ptr [rbp+80h], 0
0x180010a79  mov     eax, [rbp+80h]
0x180010a7f  add     rsp, 20h
0x180010a83  pop     rbp
0x180010a84  retn
0x180010a86  push    rbp
0x180010a88  sub     rsp, 20h
0x180010a8c  mov     rbp, rdx
0x180010a8f  mov     rax, [rcx]
0x180010a92  mov     edx, [rax]
0x180010a94  mov     [rbp+0D8h], rcx
0x180010a9b  mov     [rbp+88h], edx
0x180010aa1  mov     eax, [rbp+88h]
0x180010aa7  cmp     eax, 0E06D7363h
0x180010aac  jnz     short loc_180010AC8
0x180010aae  mov     rdx, [rbp+0D8h]
0x180010ab5  mov     ecx, [rbp+88h]
0x180010abb  call    _XcptFilter_0
0x180010ac0  mov     [rbp+90h], eax
0x180010ac6  jmp     short loc_180010AD2
0x180010ac8  mov     dword ptr [rbp+90h], 0
0x180010ad2  mov     eax, [rbp+90h]
0x180010ad8  add     rsp, 20h
0x180010adc  pop     rbp
0x180010add  retn
0x180010adf  push    rbp
0x180010ae1  sub     rsp, 20h
0x180010ae5  mov     rbp, rdx
0x180010ae8  mov     rax, [rcx]
0x180010aeb  mov     edx, [rax]
0x180010aed  mov     [rbp+0E0h], rcx
0x180010af4  mov     [rbp+98h], edx
0x180010afa  mov     eax, [rbp+98h]
0x180010b00  cmp     eax, 0E06D7363h
0x180010b05  jnz     short loc_180010B21
0x180010b07  mov     rdx, [rbp+0E0h]
0x180010b0e  mov     ecx, [rbp+98h]
0x180010b14  call    _XcptFilter_0
0x180010b19  mov     [rbp+0A0h], eax
0x180010b1f  jmp     short loc_180010B2B
0x180010b21  mov     dword ptr [rbp+0A0h], 0
0x180010b2b  mov     eax, [rbp+0A0h]
0x180010b31  add     rsp, 20h
0x180010b35  pop     rbp
0x180010b36  retn
0x180010b38  push    rbp
0x180010b3a  sub     rsp, 20h
0x180010b3e  mov     rbp, rdx
0x180010b41  cmp     dword ptr [rbp+118h], 1
0x180010b48  ja      short loc_180010B54
0x180010b4a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
