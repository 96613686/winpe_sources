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
- `0x180003f30`

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
  if ( (_DWORD)fdwReason || dword_1800090A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090A4 = 1;
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
            if ( dword_1800090A4 )
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
0x180001344  cmp     cs:dword_1800090A0, edx
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
0x180001374  mov     cs:dword_1800090A4, edx
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
0x1800014d3  cmp     cs:dword_1800090A4, 0
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
0x180003fa0  push    rbp
0x180003fa2  sub     rsp, 20h
0x180003fa6  mov     rbp, rdx
0x180003fa9  mov     rax, [rcx]
0x180003fac  mov     edx, [rax]
0x180003fae  mov     [rbp+0A8h], rcx
0x180003fb5  mov     [rbp+28h], edx
0x180003fb8  mov     eax, [rbp+28h]
0x180003fbb  cmp     eax, 0E06D7363h
0x180003fc0  jnz     short loc_180003FD6
0x180003fc2  mov     rdx, [rbp+0A8h]
0x180003fc9  mov     ecx, [rbp+28h]
0x180003fcc  call    _XcptFilter_0
0x180003fd1  mov     [rbp+30h], eax
0x180003fd4  jmp     short loc_180003FDD
0x180003fd6  mov     dword ptr [rbp+30h], 0
0x180003fdd  mov     eax, [rbp+30h]
0x180003fe0  add     rsp, 20h
0x180003fe4  pop     rbp
0x180003fe5  retn
0x180003fe7  push    rbp
0x180003fe9  sub     rsp, 20h
0x180003fed  mov     rbp, rdx
0x180003ff0  mov     rax, [rcx]
0x180003ff3  mov     edx, [rax]
0x180003ff5  mov     [rbp+0B0h], rcx
0x180003ffc  mov     [rbp+38h], edx
0x180003fff  mov     eax, [rbp+38h]
0x180004002  cmp     eax, 0E06D7363h
0x180004007  jnz     short loc_18000401D
0x180004009  mov     rdx, [rbp+0B0h]
0x180004010  mov     ecx, [rbp+38h]
0x180004013  call    _XcptFilter_0
0x180004018  mov     [rbp+40h], eax
0x18000401b  jmp     short loc_180004024
0x18000401d  mov     dword ptr [rbp+40h], 0
0x180004024  mov     eax, [rbp+40h]
0x180004027  add     rsp, 20h
0x18000402b  pop     rbp
0x18000402c  retn
0x18000402e  push    rbp
0x180004030  sub     rsp, 20h
0x180004034  mov     rbp, rdx
0x180004037  mov     rax, [rcx]
0x18000403a  mov     edx, [rax]
0x18000403c  mov     [rbp+0B8h], rcx
0x180004043  mov     [rbp+48h], edx
0x180004046  mov     eax, [rbp+48h]
0x180004049  cmp     eax, 0E06D7363h
0x18000404e  jnz     short loc_180004064
0x180004050  mov     rdx, [rbp+0B8h]
0x180004057  mov     ecx, [rbp+48h]
0x18000405a  call    _XcptFilter_0
0x18000405f  mov     [rbp+50h], eax
0x180004062  jmp     short loc_18000406B
0x180004064  mov     dword ptr [rbp+50h], 0
0x18000406b  mov     eax, [rbp+50h]
0x18000406e  add     rsp, 20h
0x180004072  pop     rbp
0x180004073  retn
0x180004075  push    rbp
0x180004077  sub     rsp, 20h
0x18000407b  mov     rbp, rdx
0x18000407e  mov     rax, [rcx]
0x180004081  mov     edx, [rax]
0x180004083  mov     [rbp+0C0h], rcx
0x18000408a  mov     [rbp+58h], edx
0x18000408d  mov     eax, [rbp+58h]
0x180004090  cmp     eax, 0E06D7363h
0x180004095  jnz     short loc_1800040AB
0x180004097  mov     rdx, [rbp+0C0h]
0x18000409e  mov     ecx, [rbp+58h]
0x1800040a1  call    _XcptFilter_0
0x1800040a6  mov     [rbp+60h], eax
0x1800040a9  jmp     short loc_1800040B2
0x1800040ab  mov     dword ptr [rbp+60h], 0
0x1800040b2  mov     eax, [rbp+60h]
0x1800040b5  add     rsp, 20h
0x1800040b9  pop     rbp
0x1800040ba  retn
0x1800040bc  push    rbp
0x1800040be  sub     rsp, 20h
0x1800040c2  mov     rbp, rdx
0x1800040c5  mov     rax, [rcx]
0x1800040c8  mov     edx, [rax]
0x1800040ca  mov     [rbp+0C8h], rcx
0x1800040d1  mov     [rbp+68h], edx
0x1800040d4  mov     eax, [rbp+68h]
0x1800040d7  cmp     eax, 0E06D7363h
0x1800040dc  jnz     short loc_1800040F2
0x1800040de  mov     rdx, [rbp+0C8h]
0x1800040e5  mov     ecx, [rbp+68h]
0x1800040e8  call    _XcptFilter_0
0x1800040ed  mov     [rbp+70h], eax
0x1800040f0  jmp     short loc_1800040F9
0x1800040f2  mov     dword ptr [rbp+70h], 0
0x1800040f9  mov     eax, [rbp+70h]
0x1800040fc  add     rsp, 20h
0x180004100  pop     rbp
0x180004101  retn
0x180004103  push    rbp
0x180004105  sub     rsp, 20h
0x180004109  mov     rbp, rdx
0x18000410c  mov     rax, [rcx]
0x18000410f  mov     edx, [rax]
0x180004111  mov     [rbp+0D0h], rcx
0x180004118  mov     [rbp+78h], edx
0x18000411b  mov     eax, [rbp+78h]
0x18000411e  cmp     eax, 0E06D7363h
0x180004123  jnz     short loc_18000413C
0x180004125  mov     rdx, [rbp+0D0h]
0x18000412c  mov     ecx, [rbp+78h]
0x18000412f  call    _XcptFilter_0
0x180004134  mov     [rbp+80h], eax
0x18000413a  jmp     short loc_180004146
0x18000413c  mov     dword ptr [rbp+80h], 0
0x180004146  mov     eax, [rbp+80h]
0x18000414c  add     rsp, 20h
0x180004150  pop     rbp
0x180004151  retn
0x180004153  push    rbp
0x180004155  sub     rsp, 20h
0x180004159  mov     rbp, rdx
0x18000415c  mov     rax, [rcx]
0x18000415f  mov     edx, [rax]
0x180004161  mov     [rbp+0D8h], rcx
0x180004168  mov     [rbp+88h], edx
0x18000416e  mov     eax, [rbp+88h]
0x180004174  cmp     eax, 0E06D7363h
0x180004179  jnz     short loc_180004195
0x18000417b  mov     rdx, [rbp+0D8h]
0x180004182  mov     ecx, [rbp+88h]
0x180004188  call    _XcptFilter_0
0x18000418d  mov     [rbp+90h], eax
0x180004193  jmp     short loc_18000419F
0x180004195  mov     dword ptr [rbp+90h], 0
0x18000419f  mov     eax, [rbp+90h]
0x1800041a5  add     rsp, 20h
0x1800041a9  pop     rbp
0x1800041aa  retn
0x1800041ac  push    rbp
0x1800041ae  sub     rsp, 20h
0x1800041b2  mov     rbp, rdx
0x1800041b5  mov     rax, [rcx]
0x1800041b8  mov     edx, [rax]
0x1800041ba  mov     [rbp+0E0h], rcx
0x1800041c1  mov     [rbp+98h], edx
0x1800041c7  mov     eax, [rbp+98h]
0x1800041cd  cmp     eax, 0E06D7363h
0x1800041d2  jnz     short loc_1800041EE
0x1800041d4  mov     rdx, [rbp+0E0h]
0x1800041db  mov     ecx, [rbp+98h]
0x1800041e1  call    _XcptFilter_0
0x1800041e6  mov     [rbp+0A0h], eax
0x1800041ec  jmp     short loc_1800041F8
0x1800041ee  mov     dword ptr [rbp+0A0h], 0
0x1800041f8  mov     eax, [rbp+0A0h]
0x1800041fe  add     rsp, 20h
0x180004202  pop     rbp
0x180004203  retn
0x180004205  push    rbp
0x180004207  sub     rsp, 20h
0x18000420b  mov     rbp, rdx
0x18000420e  cmp     dword ptr [rbp+118h], 1
0x180004215  ja      short loc_180004221
0x180004217  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
