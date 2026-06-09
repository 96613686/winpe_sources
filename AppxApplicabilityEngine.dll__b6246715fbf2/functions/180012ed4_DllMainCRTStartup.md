# __DllMainCRTStartup

- ea: `0x180012ed4`
- end: `0x1800130e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012e90`

## callees

- `0x180012c60`
- `0x180012ed4`
- `0x1800132e6`
- `0x18001bc58`
- `0x180022830`

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
  if ( (_DWORD)fdwReason || dword_18003A2A4 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003A2A8 = 1;
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
            if ( dword_18003A2A8 )
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
0x180012ed4  mov     [rsp+lpvReserved], r8
0x180012ed9  mov     [rsp+arg_8], edx
0x180012edd  mov     [rsp+arg_0], rcx
0x180012ee2  push    rbx
0x180012ee3  push    rsi
0x180012ee4  push    rdi
0x180012ee5  sub     rsp, 0F0h
0x180012eec  mov     edi, edx
0x180012eee  mov     rsi, rcx
0x180012ef1  mov     ebx, 1
0x180012ef6  cmp     edx, ebx
0x180012ef8  ja      short loc_180012F00
0x180012efa  mov     cs:__native_dllmain_reason, edx
0x180012f00  test    edx, edx
0x180012f02  jnz     short loc_180012F17
0x180012f04  cmp     cs:dword_18003A2A4, edx
0x180012f0a  jnz     short loc_180012F17
0x180012f0c  xor     ebx, ebx
0x180012f0e  mov     [rsp+108h+var_E8], ebx
0x180012f12  jmp     loc_1800130C4
0x180012f17  lea     eax, [rdx-1]
0x180012f1a  cmp     eax, 1
0x180012f1d  ja      loc_180012FA4
0x180012f23  mov     rax, cs:_pRawDllMain
0x180012f2a  test    rax, rax
0x180012f2d  jz      short loc_180012F65
0x180012f2f  cmp     edx, 1
0x180012f32  jnz     short loc_180012F3A
0x180012f34  mov     cs:dword_18003A2A8, edx
0x180012f3a  mov     r8, [rsp+108h+lpvReserved]
0x180012f42  call    cs:__guard_dispatch_icall_fptr
0x180012f48  mov     ebx, eax
0x180012f4a  mov     [rsp+108h+var_E8], eax
0x180012f4e  jmp     short loc_180012F65
0x180012f50  xor     ebx, ebx
0x180012f52  mov     [rsp+108h+var_E8], ebx
0x180012f56  mov     edi, [rsp+108h+arg_8]
0x180012f5d  mov     rsi, [rsp+108h+arg_0]
0x180012f65  test    ebx, ebx
0x180012f67  jz      loc_1800130C4
0x180012f6d  mov     r8, [rsp+108h+lpvReserved]
0x180012f75  mov     edx, edi
0x180012f77  mov     rcx, rsi
0x180012f7a  call    _CRT_INIT
0x180012f7f  mov     ebx, eax
0x180012f81  mov     [rsp+108h+var_E8], eax
0x180012f85  jmp     short loc_180012F9C
0x180012f87  xor     ebx, ebx
0x180012f89  mov     [rsp+108h+var_E8], ebx
0x180012f8d  mov     edi, [rsp+108h+arg_8]
0x180012f94  mov     rsi, [rsp+108h+arg_0]
0x180012f9c  test    ebx, ebx
0x180012f9e  jz      loc_1800130C4
0x180012fa4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180012fac  mov     edx, edi; fdwReason
0x180012fae  mov     rcx, rsi; hinstDLL
0x180012fb1  call    DllMain
0x180012fb6  mov     ebx, eax
0x180012fb8  mov     [rsp+108h+var_E8], eax
0x180012fbc  jmp     short loc_180012FD3
0x180012fbe  xor     ebx, ebx
0x180012fc0  mov     [rsp+108h+var_E8], ebx
0x180012fc4  mov     edi, [rsp+108h+arg_8]
0x180012fcb  mov     rsi, [rsp+108h+arg_0]
0x180012fd3  cmp     edi, 1
0x180012fd6  jnz     short loc_18001304F
0x180012fd8  test    ebx, ebx
0x180012fda  jnz     short loc_18001304F
0x180012fdc  xor     r8d, r8d; lpvReserved
0x180012fdf  xor     edx, edx; fdwReason
0x180012fe1  mov     rcx, rsi; hinstDLL
0x180012fe4  call    DllMain
0x180012fe9  jmp     short loc_180012FFE
0x180012feb  mov     edi, [rsp+108h+arg_8]
0x180012ff2  mov     rsi, [rsp+108h+arg_0]
0x180012ffa  mov     ebx, [rsp+108h+var_E8]
0x180012ffe  xor     r8d, r8d
0x180013001  xor     edx, edx
0x180013003  mov     rcx, rsi
0x180013006  call    _CRT_INIT
0x18001300b  jmp     short loc_180013020
0x18001300d  mov     edi, [rsp+108h+arg_8]
0x180013014  mov     rsi, [rsp+108h+arg_0]
0x18001301c  mov     ebx, [rsp+108h+var_E8]
0x180013020  mov     rax, cs:_pRawDllMain
0x180013027  test    rax, rax
0x18001302a  jz      short loc_18001304F
0x18001302c  xor     r8d, r8d
0x18001302f  xor     edx, edx
0x180013031  mov     rcx, rsi
0x180013034  call    cs:__guard_dispatch_icall_fptr
0x18001303a  jmp     short loc_18001304F
0x18001303c  mov     edi, [rsp+108h+arg_8]
0x180013043  mov     rsi, [rsp+108h+arg_0]
0x18001304b  mov     ebx, [rsp+108h+var_E8]
0x18001304f  test    edi, edi
0x180013051  jz      short loc_180013058
0x180013053  cmp     edi, 3
0x180013056  jnz     short loc_1800130C4
0x180013058  mov     r8, [rsp+108h+lpvReserved]
0x180013060  mov     edx, edi
0x180013062  mov     rcx, rsi
0x180013065  call    _CRT_INIT
0x18001306a  mov     ebx, eax
0x18001306c  mov     [rsp+108h+var_E8], eax
0x180013070  jmp     short loc_180013087
0x180013072  xor     ebx, ebx
0x180013074  mov     [rsp+108h+var_E8], ebx
0x180013078  mov     edi, [rsp+108h+arg_8]
0x18001307f  mov     rsi, [rsp+108h+arg_0]
0x180013087  mov     rax, cs:_pRawDllMain
0x18001308e  test    rax, rax
0x180013091  jz      short loc_1800130C4
0x180013093  cmp     cs:dword_18003A2A8, 0
0x18001309a  jz      short loc_1800130C4
0x18001309c  mov     r8, [rsp+108h+lpvReserved]
0x1800130a4  mov     edx, edi
0x1800130a6  mov     rcx, rsi
0x1800130a9  call    cs:__guard_dispatch_icall_fptr
0x1800130af  mov     ebx, eax
0x1800130b1  mov     [rsp+108h+var_E8], eax
0x1800130b5  jmp     short loc_1800130C4
0x1800130b7  xor     ebx, ebx
0x1800130b9  mov     [rsp+108h+var_E8], ebx
0x1800130bd  mov     edi, [rsp+108h+arg_8]
0x1800130c4  cmp     edi, 1
0x1800130c7  ja      short loc_1800130D3
0x1800130c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800130d3  mov     eax, ebx
0x1800130d5  add     rsp, 0F0h
0x1800130dc  pop     rdi
0x1800130dd  pop     rsi
0x1800130de  pop     rbx
0x1800130df  retn
0x180023c08  push    rbp
0x180023c0a  sub     rsp, 20h
0x180023c0e  mov     rbp, rdx
0x180023c11  mov     rax, [rcx]
0x180023c14  mov     edx, [rax]
0x180023c16  mov     [rbp+0A8h], rcx
0x180023c1d  mov     [rbp+28h], edx
0x180023c20  mov     eax, [rbp+28h]
0x180023c23  cmp     eax, 0E06D7363h
0x180023c28  jnz     short loc_180023C3E
0x180023c2a  mov     rdx, [rbp+0A8h]
0x180023c31  mov     ecx, [rbp+28h]
0x180023c34  call    _XcptFilter_0
0x180023c39  mov     [rbp+30h], eax
0x180023c3c  jmp     short loc_180023C45
0x180023c3e  mov     dword ptr [rbp+30h], 0
0x180023c45  mov     eax, [rbp+30h]
0x180023c48  add     rsp, 20h
0x180023c4c  pop     rbp
0x180023c4d  retn
0x180023c4f  push    rbp
0x180023c51  sub     rsp, 20h
0x180023c55  mov     rbp, rdx
0x180023c58  mov     rax, [rcx]
0x180023c5b  mov     edx, [rax]
0x180023c5d  mov     [rbp+0B0h], rcx
0x180023c64  mov     [rbp+38h], edx
0x180023c67  mov     eax, [rbp+38h]
0x180023c6a  cmp     eax, 0E06D7363h
0x180023c6f  jnz     short loc_180023C85
0x180023c71  mov     rdx, [rbp+0B0h]
0x180023c78  mov     ecx, [rbp+38h]
0x180023c7b  call    _XcptFilter_0
0x180023c80  mov     [rbp+40h], eax
0x180023c83  jmp     short loc_180023C8C
0x180023c85  mov     dword ptr [rbp+40h], 0
0x180023c8c  mov     eax, [rbp+40h]
0x180023c8f  add     rsp, 20h
0x180023c93  pop     rbp
0x180023c94  retn
0x180023c96  push    rbp
0x180023c98  sub     rsp, 20h
0x180023c9c  mov     rbp, rdx
0x180023c9f  mov     rax, [rcx]
0x180023ca2  mov     edx, [rax]
0x180023ca4  mov     [rbp+0B8h], rcx
0x180023cab  mov     [rbp+48h], edx
0x180023cae  mov     eax, [rbp+48h]
0x180023cb1  cmp     eax, 0E06D7363h
0x180023cb6  jnz     short loc_180023CCC
0x180023cb8  mov     rdx, [rbp+0B8h]
0x180023cbf  mov     ecx, [rbp+48h]
0x180023cc2  call    _XcptFilter_0
0x180023cc7  mov     [rbp+50h], eax
0x180023cca  jmp     short loc_180023CD3
0x180023ccc  mov     dword ptr [rbp+50h], 0
0x180023cd3  mov     eax, [rbp+50h]
0x180023cd6  add     rsp, 20h
0x180023cda  pop     rbp
0x180023cdb  retn
0x180023cdd  push    rbp
0x180023cdf  sub     rsp, 20h
0x180023ce3  mov     rbp, rdx
0x180023ce6  mov     rax, [rcx]
0x180023ce9  mov     edx, [rax]
0x180023ceb  mov     [rbp+0C0h], rcx
0x180023cf2  mov     [rbp+58h], edx
0x180023cf5  mov     eax, [rbp+58h]
0x180023cf8  cmp     eax, 0E06D7363h
0x180023cfd  jnz     short loc_180023D13
0x180023cff  mov     rdx, [rbp+0C0h]
0x180023d06  mov     ecx, [rbp+58h]
0x180023d09  call    _XcptFilter_0
0x180023d0e  mov     [rbp+60h], eax
0x180023d11  jmp     short loc_180023D1A
0x180023d13  mov     dword ptr [rbp+60h], 0
0x180023d1a  mov     eax, [rbp+60h]
0x180023d1d  add     rsp, 20h
0x180023d21  pop     rbp
0x180023d22  retn
0x180023d24  push    rbp
0x180023d26  sub     rsp, 20h
0x180023d2a  mov     rbp, rdx
0x180023d2d  mov     rax, [rcx]
0x180023d30  mov     edx, [rax]
0x180023d32  mov     [rbp+0C8h], rcx
0x180023d39  mov     [rbp+68h], edx
0x180023d3c  mov     eax, [rbp+68h]
0x180023d3f  cmp     eax, 0E06D7363h
0x180023d44  jnz     short loc_180023D5A
0x180023d46  mov     rdx, [rbp+0C8h]
0x180023d4d  mov     ecx, [rbp+68h]
0x180023d50  call    _XcptFilter_0
0x180023d55  mov     [rbp+70h], eax
0x180023d58  jmp     short loc_180023D61
0x180023d5a  mov     dword ptr [rbp+70h], 0
0x180023d61  mov     eax, [rbp+70h]
0x180023d64  add     rsp, 20h
0x180023d68  pop     rbp
0x180023d69  retn
0x180023d6b  push    rbp
0x180023d6d  sub     rsp, 20h
0x180023d71  mov     rbp, rdx
0x180023d74  mov     rax, [rcx]
0x180023d77  mov     edx, [rax]
0x180023d79  mov     [rbp+0D0h], rcx
0x180023d80  mov     [rbp+78h], edx
0x180023d83  mov     eax, [rbp+78h]
0x180023d86  cmp     eax, 0E06D7363h
0x180023d8b  jnz     short loc_180023DA4
0x180023d8d  mov     rdx, [rbp+0D0h]
0x180023d94  mov     ecx, [rbp+78h]
0x180023d97  call    _XcptFilter_0
0x180023d9c  mov     [rbp+80h], eax
0x180023da2  jmp     short loc_180023DAE
0x180023da4  mov     dword ptr [rbp+80h], 0
0x180023dae  mov     eax, [rbp+80h]
0x180023db4  add     rsp, 20h
0x180023db8  pop     rbp
0x180023db9  retn
0x180023dbb  push    rbp
0x180023dbd  sub     rsp, 20h
0x180023dc1  mov     rbp, rdx
0x180023dc4  mov     rax, [rcx]
0x180023dc7  mov     edx, [rax]
0x180023dc9  mov     [rbp+0D8h], rcx
0x180023dd0  mov     [rbp+88h], edx
0x180023dd6  mov     eax, [rbp+88h]
0x180023ddc  cmp     eax, 0E06D7363h
0x180023de1  jnz     short loc_180023DFD
0x180023de3  mov     rdx, [rbp+0D8h]
0x180023dea  mov     ecx, [rbp+88h]
0x180023df0  call    _XcptFilter_0
0x180023df5  mov     [rbp+90h], eax
0x180023dfb  jmp     short loc_180023E07
0x180023dfd  mov     dword ptr [rbp+90h], 0
0x180023e07  mov     eax, [rbp+90h]
0x180023e0d  add     rsp, 20h
0x180023e11  pop     rbp
0x180023e12  retn
0x180023e14  push    rbp
0x180023e16  sub     rsp, 20h
0x180023e1a  mov     rbp, rdx
0x180023e1d  mov     rax, [rcx]
0x180023e20  mov     edx, [rax]
0x180023e22  mov     [rbp+0E0h], rcx
0x180023e29  mov     [rbp+98h], edx
0x180023e2f  mov     eax, [rbp+98h]
0x180023e35  cmp     eax, 0E06D7363h
0x180023e3a  jnz     short loc_180023E56
0x180023e3c  mov     rdx, [rbp+0E0h]
0x180023e43  mov     ecx, [rbp+98h]
0x180023e49  call    _XcptFilter_0
0x180023e4e  mov     [rbp+0A0h], eax
0x180023e54  jmp     short loc_180023E60
0x180023e56  mov     dword ptr [rbp+0A0h], 0
0x180023e60  mov     eax, [rbp+0A0h]
0x180023e66  add     rsp, 20h
0x180023e6a  pop     rbp
0x180023e6b  retn
0x180023e6d  push    rbp
0x180023e6f  sub     rsp, 20h
0x180023e73  mov     rbp, rdx
0x180023e76  cmp     dword ptr [rbp+118h], 1
0x180023e7d  ja      short loc_180023E89
0x180023e7f  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
