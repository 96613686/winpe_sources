# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180001728`
- `0x180005b70`

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
  if ( (_DWORD)fdwReason || dword_18000B1A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B1A4 = 1;
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
            if ( dword_18000B1A4 )
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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_18000B1A0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_18000B1A4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_18000B1A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180005be0  push    rbp
0x180005be2  sub     rsp, 20h
0x180005be6  mov     rbp, rdx
0x180005be9  mov     rax, [rcx]
0x180005bec  mov     edx, [rax]
0x180005bee  mov     [rbp+0A8h], rcx
0x180005bf5  mov     [rbp+28h], edx
0x180005bf8  mov     eax, [rbp+28h]
0x180005bfb  cmp     eax, 0E06D7363h
0x180005c00  jnz     short loc_180005C16
0x180005c02  mov     rdx, [rbp+0A8h]
0x180005c09  mov     ecx, [rbp+28h]
0x180005c0c  call    _XcptFilter_0
0x180005c11  mov     [rbp+30h], eax
0x180005c14  jmp     short loc_180005C1D
0x180005c16  mov     dword ptr [rbp+30h], 0
0x180005c1d  mov     eax, [rbp+30h]
0x180005c20  add     rsp, 20h
0x180005c24  pop     rbp
0x180005c25  retn
0x180005c27  push    rbp
0x180005c29  sub     rsp, 20h
0x180005c2d  mov     rbp, rdx
0x180005c30  mov     rax, [rcx]
0x180005c33  mov     edx, [rax]
0x180005c35  mov     [rbp+0B0h], rcx
0x180005c3c  mov     [rbp+38h], edx
0x180005c3f  mov     eax, [rbp+38h]
0x180005c42  cmp     eax, 0E06D7363h
0x180005c47  jnz     short loc_180005C5D
0x180005c49  mov     rdx, [rbp+0B0h]
0x180005c50  mov     ecx, [rbp+38h]
0x180005c53  call    _XcptFilter_0
0x180005c58  mov     [rbp+40h], eax
0x180005c5b  jmp     short loc_180005C64
0x180005c5d  mov     dword ptr [rbp+40h], 0
0x180005c64  mov     eax, [rbp+40h]
0x180005c67  add     rsp, 20h
0x180005c6b  pop     rbp
0x180005c6c  retn
0x180005c6e  push    rbp
0x180005c70  sub     rsp, 20h
0x180005c74  mov     rbp, rdx
0x180005c77  mov     rax, [rcx]
0x180005c7a  mov     edx, [rax]
0x180005c7c  mov     [rbp+0B8h], rcx
0x180005c83  mov     [rbp+48h], edx
0x180005c86  mov     eax, [rbp+48h]
0x180005c89  cmp     eax, 0E06D7363h
0x180005c8e  jnz     short loc_180005CA4
0x180005c90  mov     rdx, [rbp+0B8h]
0x180005c97  mov     ecx, [rbp+48h]
0x180005c9a  call    _XcptFilter_0
0x180005c9f  mov     [rbp+50h], eax
0x180005ca2  jmp     short loc_180005CAB
0x180005ca4  mov     dword ptr [rbp+50h], 0
0x180005cab  mov     eax, [rbp+50h]
0x180005cae  add     rsp, 20h
0x180005cb2  pop     rbp
0x180005cb3  retn
0x180005cb5  push    rbp
0x180005cb7  sub     rsp, 20h
0x180005cbb  mov     rbp, rdx
0x180005cbe  mov     rax, [rcx]
0x180005cc1  mov     edx, [rax]
0x180005cc3  mov     [rbp+0C0h], rcx
0x180005cca  mov     [rbp+58h], edx
0x180005ccd  mov     eax, [rbp+58h]
0x180005cd0  cmp     eax, 0E06D7363h
0x180005cd5  jnz     short loc_180005CEB
0x180005cd7  mov     rdx, [rbp+0C0h]
0x180005cde  mov     ecx, [rbp+58h]
0x180005ce1  call    _XcptFilter_0
0x180005ce6  mov     [rbp+60h], eax
0x180005ce9  jmp     short loc_180005CF2
0x180005ceb  mov     dword ptr [rbp+60h], 0
0x180005cf2  mov     eax, [rbp+60h]
0x180005cf5  add     rsp, 20h
0x180005cf9  pop     rbp
0x180005cfa  retn
0x180005cfc  push    rbp
0x180005cfe  sub     rsp, 20h
0x180005d02  mov     rbp, rdx
0x180005d05  mov     rax, [rcx]
0x180005d08  mov     edx, [rax]
0x180005d0a  mov     [rbp+0C8h], rcx
0x180005d11  mov     [rbp+68h], edx
0x180005d14  mov     eax, [rbp+68h]
0x180005d17  cmp     eax, 0E06D7363h
0x180005d1c  jnz     short loc_180005D32
0x180005d1e  mov     rdx, [rbp+0C8h]
0x180005d25  mov     ecx, [rbp+68h]
0x180005d28  call    _XcptFilter_0
0x180005d2d  mov     [rbp+70h], eax
0x180005d30  jmp     short loc_180005D39
0x180005d32  mov     dword ptr [rbp+70h], 0
0x180005d39  mov     eax, [rbp+70h]
0x180005d3c  add     rsp, 20h
0x180005d40  pop     rbp
0x180005d41  retn
0x180005d43  push    rbp
0x180005d45  sub     rsp, 20h
0x180005d49  mov     rbp, rdx
0x180005d4c  mov     rax, [rcx]
0x180005d4f  mov     edx, [rax]
0x180005d51  mov     [rbp+0D0h], rcx
0x180005d58  mov     [rbp+78h], edx
0x180005d5b  mov     eax, [rbp+78h]
0x180005d5e  cmp     eax, 0E06D7363h
0x180005d63  jnz     short loc_180005D7C
0x180005d65  mov     rdx, [rbp+0D0h]
0x180005d6c  mov     ecx, [rbp+78h]
0x180005d6f  call    _XcptFilter_0
0x180005d74  mov     [rbp+80h], eax
0x180005d7a  jmp     short loc_180005D86
0x180005d7c  mov     dword ptr [rbp+80h], 0
0x180005d86  mov     eax, [rbp+80h]
0x180005d8c  add     rsp, 20h
0x180005d90  pop     rbp
0x180005d91  retn
0x180005d93  push    rbp
0x180005d95  sub     rsp, 20h
0x180005d99  mov     rbp, rdx
0x180005d9c  mov     rax, [rcx]
0x180005d9f  mov     edx, [rax]
0x180005da1  mov     [rbp+0D8h], rcx
0x180005da8  mov     [rbp+88h], edx
0x180005dae  mov     eax, [rbp+88h]
0x180005db4  cmp     eax, 0E06D7363h
0x180005db9  jnz     short loc_180005DD5
0x180005dbb  mov     rdx, [rbp+0D8h]
0x180005dc2  mov     ecx, [rbp+88h]
0x180005dc8  call    _XcptFilter_0
0x180005dcd  mov     [rbp+90h], eax
0x180005dd3  jmp     short loc_180005DDF
0x180005dd5  mov     dword ptr [rbp+90h], 0
0x180005ddf  mov     eax, [rbp+90h]
0x180005de5  add     rsp, 20h
0x180005de9  pop     rbp
0x180005dea  retn
0x180005dec  push    rbp
0x180005dee  sub     rsp, 20h
0x180005df2  mov     rbp, rdx
0x180005df5  mov     rax, [rcx]
0x180005df8  mov     edx, [rax]
0x180005dfa  mov     [rbp+0E0h], rcx
0x180005e01  mov     [rbp+98h], edx
0x180005e07  mov     eax, [rbp+98h]
0x180005e0d  cmp     eax, 0E06D7363h
0x180005e12  jnz     short loc_180005E2E
0x180005e14  mov     rdx, [rbp+0E0h]
0x180005e1b  mov     ecx, [rbp+98h]
0x180005e21  call    _XcptFilter_0
0x180005e26  mov     [rbp+0A0h], eax
0x180005e2c  jmp     short loc_180005E38
0x180005e2e  mov     dword ptr [rbp+0A0h], 0
0x180005e38  mov     eax, [rbp+0A0h]
0x180005e3e  add     rsp, 20h
0x180005e42  pop     rbp
0x180005e43  retn
0x180005e45  push    rbp
0x180005e47  sub     rsp, 20h
0x180005e4b  mov     rbp, rdx
0x180005e4e  cmp     dword ptr [rbp+118h], 1
0x180005e55  ja      short loc_180005E61
0x180005e57  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
