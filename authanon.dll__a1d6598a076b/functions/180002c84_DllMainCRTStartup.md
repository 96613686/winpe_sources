# __DllMainCRTStartup

- ea: `0x180002c84`
- end: `0x180002e90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002c40`

## callees

- `0x180002a10`
- `0x180002c84`
- `0x180002eba`
- `0x180004e60`
- `0x180005bb0`

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
0x180002c84  mov     [rsp+lpvReserved], r8
0x180002c89  mov     [rsp+arg_8], edx
0x180002c8d  mov     [rsp+arg_0], rcx
0x180002c92  push    rbx
0x180002c93  push    rsi
0x180002c94  push    rdi
0x180002c95  sub     rsp, 0F0h
0x180002c9c  mov     edi, edx
0x180002c9e  mov     rsi, rcx
0x180002ca1  mov     ebx, 1
0x180002ca6  cmp     edx, ebx
0x180002ca8  ja      short loc_180002CB0
0x180002caa  mov     cs:__native_dllmain_reason, edx
0x180002cb0  test    edx, edx
0x180002cb2  jnz     short loc_180002CC7
0x180002cb4  cmp     cs:dword_18000B1A0, edx
0x180002cba  jnz     short loc_180002CC7
0x180002cbc  xor     ebx, ebx
0x180002cbe  mov     [rsp+108h+var_E8], ebx
0x180002cc2  jmp     loc_180002E74
0x180002cc7  lea     eax, [rdx-1]
0x180002cca  cmp     eax, 1
0x180002ccd  ja      loc_180002D54
0x180002cd3  mov     rax, cs:_pRawDllMain
0x180002cda  test    rax, rax
0x180002cdd  jz      short loc_180002D15
0x180002cdf  cmp     edx, 1
0x180002ce2  jnz     short loc_180002CEA
0x180002ce4  mov     cs:dword_18000B1A4, edx
0x180002cea  mov     r8, [rsp+108h+lpvReserved]
0x180002cf2  call    cs:__guard_dispatch_icall_fptr
0x180002cf8  mov     ebx, eax
0x180002cfa  mov     [rsp+108h+var_E8], eax
0x180002cfe  jmp     short loc_180002D15
0x180002d00  xor     ebx, ebx
0x180002d02  mov     [rsp+108h+var_E8], ebx
0x180002d06  mov     edi, [rsp+108h+arg_8]
0x180002d0d  mov     rsi, [rsp+108h+arg_0]
0x180002d15  test    ebx, ebx
0x180002d17  jz      loc_180002E74
0x180002d1d  mov     r8, [rsp+108h+lpvReserved]
0x180002d25  mov     edx, edi
0x180002d27  mov     rcx, rsi
0x180002d2a  call    _CRT_INIT
0x180002d2f  mov     ebx, eax
0x180002d31  mov     [rsp+108h+var_E8], eax
0x180002d35  jmp     short loc_180002D4C
0x180002d37  xor     ebx, ebx
0x180002d39  mov     [rsp+108h+var_E8], ebx
0x180002d3d  mov     edi, [rsp+108h+arg_8]
0x180002d44  mov     rsi, [rsp+108h+arg_0]
0x180002d4c  test    ebx, ebx
0x180002d4e  jz      loc_180002E74
0x180002d54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002d5c  mov     edx, edi; fdwReason
0x180002d5e  mov     rcx, rsi; hinstDLL
0x180002d61  call    DllMain
0x180002d66  mov     ebx, eax
0x180002d68  mov     [rsp+108h+var_E8], eax
0x180002d6c  jmp     short loc_180002D83
0x180002d6e  xor     ebx, ebx
0x180002d70  mov     [rsp+108h+var_E8], ebx
0x180002d74  mov     edi, [rsp+108h+arg_8]
0x180002d7b  mov     rsi, [rsp+108h+arg_0]
0x180002d83  cmp     edi, 1
0x180002d86  jnz     short loc_180002DFF
0x180002d88  test    ebx, ebx
0x180002d8a  jnz     short loc_180002DFF
0x180002d8c  xor     r8d, r8d; lpvReserved
0x180002d8f  xor     edx, edx; fdwReason
0x180002d91  mov     rcx, rsi; hinstDLL
0x180002d94  call    DllMain
0x180002d99  jmp     short loc_180002DAE
0x180002d9b  mov     edi, [rsp+108h+arg_8]
0x180002da2  mov     rsi, [rsp+108h+arg_0]
0x180002daa  mov     ebx, [rsp+108h+var_E8]
0x180002dae  xor     r8d, r8d
0x180002db1  xor     edx, edx
0x180002db3  mov     rcx, rsi
0x180002db6  call    _CRT_INIT
0x180002dbb  jmp     short loc_180002DD0
0x180002dbd  mov     edi, [rsp+108h+arg_8]
0x180002dc4  mov     rsi, [rsp+108h+arg_0]
0x180002dcc  mov     ebx, [rsp+108h+var_E8]
0x180002dd0  mov     rax, cs:_pRawDllMain
0x180002dd7  test    rax, rax
0x180002dda  jz      short loc_180002DFF
0x180002ddc  xor     r8d, r8d
0x180002ddf  xor     edx, edx
0x180002de1  mov     rcx, rsi
0x180002de4  call    cs:__guard_dispatch_icall_fptr
0x180002dea  jmp     short loc_180002DFF
0x180002dec  mov     edi, [rsp+108h+arg_8]
0x180002df3  mov     rsi, [rsp+108h+arg_0]
0x180002dfb  mov     ebx, [rsp+108h+var_E8]
0x180002dff  test    edi, edi
0x180002e01  jz      short loc_180002E08
0x180002e03  cmp     edi, 3
0x180002e06  jnz     short loc_180002E74
0x180002e08  mov     r8, [rsp+108h+lpvReserved]
0x180002e10  mov     edx, edi
0x180002e12  mov     rcx, rsi
0x180002e15  call    _CRT_INIT
0x180002e1a  mov     ebx, eax
0x180002e1c  mov     [rsp+108h+var_E8], eax
0x180002e20  jmp     short loc_180002E37
0x180002e22  xor     ebx, ebx
0x180002e24  mov     [rsp+108h+var_E8], ebx
0x180002e28  mov     edi, [rsp+108h+arg_8]
0x180002e2f  mov     rsi, [rsp+108h+arg_0]
0x180002e37  mov     rax, cs:_pRawDllMain
0x180002e3e  test    rax, rax
0x180002e41  jz      short loc_180002E74
0x180002e43  cmp     cs:dword_18000B1A4, 0
0x180002e4a  jz      short loc_180002E74
0x180002e4c  mov     r8, [rsp+108h+lpvReserved]
0x180002e54  mov     edx, edi
0x180002e56  mov     rcx, rsi
0x180002e59  call    cs:__guard_dispatch_icall_fptr
0x180002e5f  mov     ebx, eax
0x180002e61  mov     [rsp+108h+var_E8], eax
0x180002e65  jmp     short loc_180002E74
0x180002e67  xor     ebx, ebx
0x180002e69  mov     [rsp+108h+var_E8], ebx
0x180002e6d  mov     edi, [rsp+108h+arg_8]
0x180002e74  cmp     edi, 1
0x180002e77  ja      short loc_180002E83
0x180002e79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002e83  mov     eax, ebx
0x180002e85  add     rsp, 0F0h
0x180002e8c  pop     rdi
0x180002e8d  pop     rsi
0x180002e8e  pop     rbx
0x180002e8f  retn
0x180005c20  push    rbp
0x180005c22  sub     rsp, 20h
0x180005c26  mov     rbp, rdx
0x180005c29  mov     rax, [rcx]
0x180005c2c  mov     edx, [rax]
0x180005c2e  mov     [rbp+0A8h], rcx
0x180005c35  mov     [rbp+28h], edx
0x180005c38  mov     eax, [rbp+28h]
0x180005c3b  cmp     eax, 0E06D7363h
0x180005c40  jnz     short loc_180005C56
0x180005c42  mov     rdx, [rbp+0A8h]
0x180005c49  mov     ecx, [rbp+28h]
0x180005c4c  call    _XcptFilter_0
0x180005c51  mov     [rbp+30h], eax
0x180005c54  jmp     short loc_180005C5D
0x180005c56  mov     dword ptr [rbp+30h], 0
0x180005c5d  mov     eax, [rbp+30h]
0x180005c60  add     rsp, 20h
0x180005c64  pop     rbp
0x180005c65  retn
0x180005c67  push    rbp
0x180005c69  sub     rsp, 20h
0x180005c6d  mov     rbp, rdx
0x180005c70  mov     rax, [rcx]
0x180005c73  mov     edx, [rax]
0x180005c75  mov     [rbp+0B0h], rcx
0x180005c7c  mov     [rbp+38h], edx
0x180005c7f  mov     eax, [rbp+38h]
0x180005c82  cmp     eax, 0E06D7363h
0x180005c87  jnz     short loc_180005C9D
0x180005c89  mov     rdx, [rbp+0B0h]
0x180005c90  mov     ecx, [rbp+38h]
0x180005c93  call    _XcptFilter_0
0x180005c98  mov     [rbp+40h], eax
0x180005c9b  jmp     short loc_180005CA4
0x180005c9d  mov     dword ptr [rbp+40h], 0
0x180005ca4  mov     eax, [rbp+40h]
0x180005ca7  add     rsp, 20h
0x180005cab  pop     rbp
0x180005cac  retn
0x180005cae  push    rbp
0x180005cb0  sub     rsp, 20h
0x180005cb4  mov     rbp, rdx
0x180005cb7  mov     rax, [rcx]
0x180005cba  mov     edx, [rax]
0x180005cbc  mov     [rbp+0B8h], rcx
0x180005cc3  mov     [rbp+48h], edx
0x180005cc6  mov     eax, [rbp+48h]
0x180005cc9  cmp     eax, 0E06D7363h
0x180005cce  jnz     short loc_180005CE4
0x180005cd0  mov     rdx, [rbp+0B8h]
0x180005cd7  mov     ecx, [rbp+48h]
0x180005cda  call    _XcptFilter_0
0x180005cdf  mov     [rbp+50h], eax
0x180005ce2  jmp     short loc_180005CEB
0x180005ce4  mov     dword ptr [rbp+50h], 0
0x180005ceb  mov     eax, [rbp+50h]
0x180005cee  add     rsp, 20h
0x180005cf2  pop     rbp
0x180005cf3  retn
0x180005cf5  push    rbp
0x180005cf7  sub     rsp, 20h
0x180005cfb  mov     rbp, rdx
0x180005cfe  mov     rax, [rcx]
0x180005d01  mov     edx, [rax]
0x180005d03  mov     [rbp+0C0h], rcx
0x180005d0a  mov     [rbp+58h], edx
0x180005d0d  mov     eax, [rbp+58h]
0x180005d10  cmp     eax, 0E06D7363h
0x180005d15  jnz     short loc_180005D2B
0x180005d17  mov     rdx, [rbp+0C0h]
0x180005d1e  mov     ecx, [rbp+58h]
0x180005d21  call    _XcptFilter_0
0x180005d26  mov     [rbp+60h], eax
0x180005d29  jmp     short loc_180005D32
0x180005d2b  mov     dword ptr [rbp+60h], 0
0x180005d32  mov     eax, [rbp+60h]
0x180005d35  add     rsp, 20h
0x180005d39  pop     rbp
0x180005d3a  retn
0x180005d3c  push    rbp
0x180005d3e  sub     rsp, 20h
0x180005d42  mov     rbp, rdx
0x180005d45  mov     rax, [rcx]
0x180005d48  mov     edx, [rax]
0x180005d4a  mov     [rbp+0C8h], rcx
0x180005d51  mov     [rbp+68h], edx
0x180005d54  mov     eax, [rbp+68h]
0x180005d57  cmp     eax, 0E06D7363h
0x180005d5c  jnz     short loc_180005D72
0x180005d5e  mov     rdx, [rbp+0C8h]
0x180005d65  mov     ecx, [rbp+68h]
0x180005d68  call    _XcptFilter_0
0x180005d6d  mov     [rbp+70h], eax
0x180005d70  jmp     short loc_180005D79
0x180005d72  mov     dword ptr [rbp+70h], 0
0x180005d79  mov     eax, [rbp+70h]
0x180005d7c  add     rsp, 20h
0x180005d80  pop     rbp
0x180005d81  retn
0x180005d83  push    rbp
0x180005d85  sub     rsp, 20h
0x180005d89  mov     rbp, rdx
0x180005d8c  mov     rax, [rcx]
0x180005d8f  mov     edx, [rax]
0x180005d91  mov     [rbp+0D0h], rcx
0x180005d98  mov     [rbp+78h], edx
0x180005d9b  mov     eax, [rbp+78h]
0x180005d9e  cmp     eax, 0E06D7363h
0x180005da3  jnz     short loc_180005DBC
0x180005da5  mov     rdx, [rbp+0D0h]
0x180005dac  mov     ecx, [rbp+78h]
0x180005daf  call    _XcptFilter_0
0x180005db4  mov     [rbp+80h], eax
0x180005dba  jmp     short loc_180005DC6
0x180005dbc  mov     dword ptr [rbp+80h], 0
0x180005dc6  mov     eax, [rbp+80h]
0x180005dcc  add     rsp, 20h
0x180005dd0  pop     rbp
0x180005dd1  retn
0x180005dd3  push    rbp
0x180005dd5  sub     rsp, 20h
0x180005dd9  mov     rbp, rdx
0x180005ddc  mov     rax, [rcx]
0x180005ddf  mov     edx, [rax]
0x180005de1  mov     [rbp+0D8h], rcx
0x180005de8  mov     [rbp+88h], edx
0x180005dee  mov     eax, [rbp+88h]
0x180005df4  cmp     eax, 0E06D7363h
0x180005df9  jnz     short loc_180005E15
0x180005dfb  mov     rdx, [rbp+0D8h]
0x180005e02  mov     ecx, [rbp+88h]
0x180005e08  call    _XcptFilter_0
0x180005e0d  mov     [rbp+90h], eax
0x180005e13  jmp     short loc_180005E1F
0x180005e15  mov     dword ptr [rbp+90h], 0
0x180005e1f  mov     eax, [rbp+90h]
0x180005e25  add     rsp, 20h
0x180005e29  pop     rbp
0x180005e2a  retn
0x180005e2c  push    rbp
0x180005e2e  sub     rsp, 20h
0x180005e32  mov     rbp, rdx
0x180005e35  mov     rax, [rcx]
0x180005e38  mov     edx, [rax]
0x180005e3a  mov     [rbp+0E0h], rcx
0x180005e41  mov     [rbp+98h], edx
0x180005e47  mov     eax, [rbp+98h]
0x180005e4d  cmp     eax, 0E06D7363h
0x180005e52  jnz     short loc_180005E6E
0x180005e54  mov     rdx, [rbp+0E0h]
0x180005e5b  mov     ecx, [rbp+98h]
0x180005e61  call    _XcptFilter_0
0x180005e66  mov     [rbp+0A0h], eax
0x180005e6c  jmp     short loc_180005E78
0x180005e6e  mov     dword ptr [rbp+0A0h], 0
0x180005e78  mov     eax, [rbp+0A0h]
0x180005e7e  add     rsp, 20h
0x180005e82  pop     rbp
0x180005e83  retn
0x180005e85  push    rbp
0x180005e87  sub     rsp, 20h
0x180005e8b  mov     rbp, rdx
0x180005e8e  cmp     dword ptr [rbp+118h], 1
0x180005e95  ja      short loc_180005EA1
0x180005e97  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
