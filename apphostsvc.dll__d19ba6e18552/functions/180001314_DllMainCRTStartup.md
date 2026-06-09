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
- `0x180001650`
- `0x180006d40`
- `0x180008cc0`

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
  if ( (_DWORD)fdwReason || dword_1800130C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800130C4 = 1;
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
            if ( dword_1800130C4 )
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
0x180001344  cmp     cs:dword_1800130C0, edx
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
0x180001374  mov     cs:dword_1800130C4, edx
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
0x1800014d3  cmp     cs:dword_1800130C4, 0
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
0x180008d00  push    rbp
0x180008d02  sub     rsp, 20h
0x180008d06  mov     rbp, rdx
0x180008d09  mov     rax, [rcx]
0x180008d0c  mov     edx, [rax]
0x180008d0e  mov     [rbp+0A8h], rcx
0x180008d15  mov     [rbp+28h], edx
0x180008d18  mov     eax, [rbp+28h]
0x180008d1b  cmp     eax, 0E06D7363h
0x180008d20  jnz     short loc_180008D36
0x180008d22  mov     rdx, [rbp+0A8h]
0x180008d29  mov     ecx, [rbp+28h]
0x180008d2c  call    _XcptFilter_0
0x180008d31  mov     [rbp+30h], eax
0x180008d34  jmp     short loc_180008D3D
0x180008d36  mov     dword ptr [rbp+30h], 0
0x180008d3d  mov     eax, [rbp+30h]
0x180008d40  add     rsp, 20h
0x180008d44  pop     rbp
0x180008d45  retn
0x180008d47  push    rbp
0x180008d49  sub     rsp, 20h
0x180008d4d  mov     rbp, rdx
0x180008d50  mov     rax, [rcx]
0x180008d53  mov     edx, [rax]
0x180008d55  mov     [rbp+0B0h], rcx
0x180008d5c  mov     [rbp+38h], edx
0x180008d5f  mov     eax, [rbp+38h]
0x180008d62  cmp     eax, 0E06D7363h
0x180008d67  jnz     short loc_180008D7D
0x180008d69  mov     rdx, [rbp+0B0h]
0x180008d70  mov     ecx, [rbp+38h]
0x180008d73  call    _XcptFilter_0
0x180008d78  mov     [rbp+40h], eax
0x180008d7b  jmp     short loc_180008D84
0x180008d7d  mov     dword ptr [rbp+40h], 0
0x180008d84  mov     eax, [rbp+40h]
0x180008d87  add     rsp, 20h
0x180008d8b  pop     rbp
0x180008d8c  retn
0x180008d8e  push    rbp
0x180008d90  sub     rsp, 20h
0x180008d94  mov     rbp, rdx
0x180008d97  mov     rax, [rcx]
0x180008d9a  mov     edx, [rax]
0x180008d9c  mov     [rbp+0B8h], rcx
0x180008da3  mov     [rbp+48h], edx
0x180008da6  mov     eax, [rbp+48h]
0x180008da9  cmp     eax, 0E06D7363h
0x180008dae  jnz     short loc_180008DC4
0x180008db0  mov     rdx, [rbp+0B8h]
0x180008db7  mov     ecx, [rbp+48h]
0x180008dba  call    _XcptFilter_0
0x180008dbf  mov     [rbp+50h], eax
0x180008dc2  jmp     short loc_180008DCB
0x180008dc4  mov     dword ptr [rbp+50h], 0
0x180008dcb  mov     eax, [rbp+50h]
0x180008dce  add     rsp, 20h
0x180008dd2  pop     rbp
0x180008dd3  retn
0x180008dd5  push    rbp
0x180008dd7  sub     rsp, 20h
0x180008ddb  mov     rbp, rdx
0x180008dde  mov     rax, [rcx]
0x180008de1  mov     edx, [rax]
0x180008de3  mov     [rbp+0C0h], rcx
0x180008dea  mov     [rbp+58h], edx
0x180008ded  mov     eax, [rbp+58h]
0x180008df0  cmp     eax, 0E06D7363h
0x180008df5  jnz     short loc_180008E0B
0x180008df7  mov     rdx, [rbp+0C0h]
0x180008dfe  mov     ecx, [rbp+58h]
0x180008e01  call    _XcptFilter_0
0x180008e06  mov     [rbp+60h], eax
0x180008e09  jmp     short loc_180008E12
0x180008e0b  mov     dword ptr [rbp+60h], 0
0x180008e12  mov     eax, [rbp+60h]
0x180008e15  add     rsp, 20h
0x180008e19  pop     rbp
0x180008e1a  retn
0x180008e1c  push    rbp
0x180008e1e  sub     rsp, 20h
0x180008e22  mov     rbp, rdx
0x180008e25  mov     rax, [rcx]
0x180008e28  mov     edx, [rax]
0x180008e2a  mov     [rbp+0C8h], rcx
0x180008e31  mov     [rbp+68h], edx
0x180008e34  mov     eax, [rbp+68h]
0x180008e37  cmp     eax, 0E06D7363h
0x180008e3c  jnz     short loc_180008E52
0x180008e3e  mov     rdx, [rbp+0C8h]
0x180008e45  mov     ecx, [rbp+68h]
0x180008e48  call    _XcptFilter_0
0x180008e4d  mov     [rbp+70h], eax
0x180008e50  jmp     short loc_180008E59
0x180008e52  mov     dword ptr [rbp+70h], 0
0x180008e59  mov     eax, [rbp+70h]
0x180008e5c  add     rsp, 20h
0x180008e60  pop     rbp
0x180008e61  retn
0x180008e63  push    rbp
0x180008e65  sub     rsp, 20h
0x180008e69  mov     rbp, rdx
0x180008e6c  mov     rax, [rcx]
0x180008e6f  mov     edx, [rax]
0x180008e71  mov     [rbp+0D0h], rcx
0x180008e78  mov     [rbp+78h], edx
0x180008e7b  mov     eax, [rbp+78h]
0x180008e7e  cmp     eax, 0E06D7363h
0x180008e83  jnz     short loc_180008E9C
0x180008e85  mov     rdx, [rbp+0D0h]
0x180008e8c  mov     ecx, [rbp+78h]
0x180008e8f  call    _XcptFilter_0
0x180008e94  mov     [rbp+80h], eax
0x180008e9a  jmp     short loc_180008EA6
0x180008e9c  mov     dword ptr [rbp+80h], 0
0x180008ea6  mov     eax, [rbp+80h]
0x180008eac  add     rsp, 20h
0x180008eb0  pop     rbp
0x180008eb1  retn
0x180008eb3  push    rbp
0x180008eb5  sub     rsp, 20h
0x180008eb9  mov     rbp, rdx
0x180008ebc  mov     rax, [rcx]
0x180008ebf  mov     edx, [rax]
0x180008ec1  mov     [rbp+0D8h], rcx
0x180008ec8  mov     [rbp+88h], edx
0x180008ece  mov     eax, [rbp+88h]
0x180008ed4  cmp     eax, 0E06D7363h
0x180008ed9  jnz     short loc_180008EF5
0x180008edb  mov     rdx, [rbp+0D8h]
0x180008ee2  mov     ecx, [rbp+88h]
0x180008ee8  call    _XcptFilter_0
0x180008eed  mov     [rbp+90h], eax
0x180008ef3  jmp     short loc_180008EFF
0x180008ef5  mov     dword ptr [rbp+90h], 0
0x180008eff  mov     eax, [rbp+90h]
0x180008f05  add     rsp, 20h
0x180008f09  pop     rbp
0x180008f0a  retn
0x180008f0c  push    rbp
0x180008f0e  sub     rsp, 20h
0x180008f12  mov     rbp, rdx
0x180008f15  mov     rax, [rcx]
0x180008f18  mov     edx, [rax]
0x180008f1a  mov     [rbp+0E0h], rcx
0x180008f21  mov     [rbp+98h], edx
0x180008f27  mov     eax, [rbp+98h]
0x180008f2d  cmp     eax, 0E06D7363h
0x180008f32  jnz     short loc_180008F4E
0x180008f34  mov     rdx, [rbp+0E0h]
0x180008f3b  mov     ecx, [rbp+98h]
0x180008f41  call    _XcptFilter_0
0x180008f46  mov     [rbp+0A0h], eax
0x180008f4c  jmp     short loc_180008F58
0x180008f4e  mov     dword ptr [rbp+0A0h], 0
0x180008f58  mov     eax, [rbp+0A0h]
0x180008f5e  add     rsp, 20h
0x180008f62  pop     rbp
0x180008f63  retn
0x180008f65  push    rbp
0x180008f67  sub     rsp, 20h
0x180008f6b  mov     rbp, rdx
0x180008f6e  cmp     dword ptr [rbp+118h], 1
0x180008f75  ja      short loc_180008F81
0x180008f77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
