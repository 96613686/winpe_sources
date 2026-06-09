# __DllMainCRTStartup

- ea: `0x180001d64`
- end: `0x180001f70`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d20`

## callees

- `0x180001af0`
- `0x180001d64`
- `0x180002055`
- `0x1800079e8`
- `0x180007cd0`

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
  if ( (_DWORD)fdwReason || dword_18000D180 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000D184 = 1;
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
            if ( dword_18000D184 )
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
0x180001d64  mov     [rsp+lpvReserved], r8
0x180001d69  mov     [rsp+arg_8], edx
0x180001d6d  mov     [rsp+arg_0], rcx
0x180001d72  push    rbx
0x180001d73  push    rsi
0x180001d74  push    rdi
0x180001d75  sub     rsp, 0F0h
0x180001d7c  mov     edi, edx
0x180001d7e  mov     rsi, rcx
0x180001d81  mov     ebx, 1
0x180001d86  cmp     edx, ebx
0x180001d88  ja      short loc_180001D90
0x180001d8a  mov     cs:__native_dllmain_reason, edx
0x180001d90  test    edx, edx
0x180001d92  jnz     short loc_180001DA7
0x180001d94  cmp     cs:dword_18000D180, edx
0x180001d9a  jnz     short loc_180001DA7
0x180001d9c  xor     ebx, ebx
0x180001d9e  mov     [rsp+108h+var_E8], ebx
0x180001da2  jmp     loc_180001F54
0x180001da7  lea     eax, [rdx-1]
0x180001daa  cmp     eax, 1
0x180001dad  ja      loc_180001E34
0x180001db3  mov     rax, cs:_pRawDllMain
0x180001dba  test    rax, rax
0x180001dbd  jz      short loc_180001DF5
0x180001dbf  cmp     edx, 1
0x180001dc2  jnz     short loc_180001DCA
0x180001dc4  mov     cs:dword_18000D184, edx
0x180001dca  mov     r8, [rsp+108h+lpvReserved]
0x180001dd2  call    cs:__guard_dispatch_icall_fptr
0x180001dd8  mov     ebx, eax
0x180001dda  mov     [rsp+108h+var_E8], eax
0x180001dde  jmp     short loc_180001DF5
0x180001de0  xor     ebx, ebx
0x180001de2  mov     [rsp+108h+var_E8], ebx
0x180001de6  mov     edi, [rsp+108h+arg_8]
0x180001ded  mov     rsi, [rsp+108h+arg_0]
0x180001df5  test    ebx, ebx
0x180001df7  jz      loc_180001F54
0x180001dfd  mov     r8, [rsp+108h+lpvReserved]
0x180001e05  mov     edx, edi
0x180001e07  mov     rcx, rsi
0x180001e0a  call    _CRT_INIT
0x180001e0f  mov     ebx, eax
0x180001e11  mov     [rsp+108h+var_E8], eax
0x180001e15  jmp     short loc_180001E2C
0x180001e17  xor     ebx, ebx
0x180001e19  mov     [rsp+108h+var_E8], ebx
0x180001e1d  mov     edi, [rsp+108h+arg_8]
0x180001e24  mov     rsi, [rsp+108h+arg_0]
0x180001e2c  test    ebx, ebx
0x180001e2e  jz      loc_180001F54
0x180001e34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001e3c  mov     edx, edi; fdwReason
0x180001e3e  mov     rcx, rsi; hinstDLL
0x180001e41  call    DllMain
0x180001e46  mov     ebx, eax
0x180001e48  mov     [rsp+108h+var_E8], eax
0x180001e4c  jmp     short loc_180001E63
0x180001e4e  xor     ebx, ebx
0x180001e50  mov     [rsp+108h+var_E8], ebx
0x180001e54  mov     edi, [rsp+108h+arg_8]
0x180001e5b  mov     rsi, [rsp+108h+arg_0]
0x180001e63  cmp     edi, 1
0x180001e66  jnz     short loc_180001EDF
0x180001e68  test    ebx, ebx
0x180001e6a  jnz     short loc_180001EDF
0x180001e6c  xor     r8d, r8d; lpvReserved
0x180001e6f  xor     edx, edx; fdwReason
0x180001e71  mov     rcx, rsi; hinstDLL
0x180001e74  call    DllMain
0x180001e79  jmp     short loc_180001E8E
0x180001e7b  mov     edi, [rsp+108h+arg_8]
0x180001e82  mov     rsi, [rsp+108h+arg_0]
0x180001e8a  mov     ebx, [rsp+108h+var_E8]
0x180001e8e  xor     r8d, r8d
0x180001e91  xor     edx, edx
0x180001e93  mov     rcx, rsi
0x180001e96  call    _CRT_INIT
0x180001e9b  jmp     short loc_180001EB0
0x180001e9d  mov     edi, [rsp+108h+arg_8]
0x180001ea4  mov     rsi, [rsp+108h+arg_0]
0x180001eac  mov     ebx, [rsp+108h+var_E8]
0x180001eb0  mov     rax, cs:_pRawDllMain
0x180001eb7  test    rax, rax
0x180001eba  jz      short loc_180001EDF
0x180001ebc  xor     r8d, r8d
0x180001ebf  xor     edx, edx
0x180001ec1  mov     rcx, rsi
0x180001ec4  call    cs:__guard_dispatch_icall_fptr
0x180001eca  jmp     short loc_180001EDF
0x180001ecc  mov     edi, [rsp+108h+arg_8]
0x180001ed3  mov     rsi, [rsp+108h+arg_0]
0x180001edb  mov     ebx, [rsp+108h+var_E8]
0x180001edf  test    edi, edi
0x180001ee1  jz      short loc_180001EE8
0x180001ee3  cmp     edi, 3
0x180001ee6  jnz     short loc_180001F54
0x180001ee8  mov     r8, [rsp+108h+lpvReserved]
0x180001ef0  mov     edx, edi
0x180001ef2  mov     rcx, rsi
0x180001ef5  call    _CRT_INIT
0x180001efa  mov     ebx, eax
0x180001efc  mov     [rsp+108h+var_E8], eax
0x180001f00  jmp     short loc_180001F17
0x180001f02  xor     ebx, ebx
0x180001f04  mov     [rsp+108h+var_E8], ebx
0x180001f08  mov     edi, [rsp+108h+arg_8]
0x180001f0f  mov     rsi, [rsp+108h+arg_0]
0x180001f17  mov     rax, cs:_pRawDllMain
0x180001f1e  test    rax, rax
0x180001f21  jz      short loc_180001F54
0x180001f23  cmp     cs:dword_18000D184, 0
0x180001f2a  jz      short loc_180001F54
0x180001f2c  mov     r8, [rsp+108h+lpvReserved]
0x180001f34  mov     edx, edi
0x180001f36  mov     rcx, rsi
0x180001f39  call    cs:__guard_dispatch_icall_fptr
0x180001f3f  mov     ebx, eax
0x180001f41  mov     [rsp+108h+var_E8], eax
0x180001f45  jmp     short loc_180001F54
0x180001f47  xor     ebx, ebx
0x180001f49  mov     [rsp+108h+var_E8], ebx
0x180001f4d  mov     edi, [rsp+108h+arg_8]
0x180001f54  cmp     edi, 1
0x180001f57  ja      short loc_180001F63
0x180001f59  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001f63  mov     eax, ebx
0x180001f65  add     rsp, 0F0h
0x180001f6c  pop     rdi
0x180001f6d  pop     rsi
0x180001f6e  pop     rbx
0x180001f6f  retn
0x180007da0  push    rbp
0x180007da2  sub     rsp, 20h
0x180007da6  mov     rbp, rdx
0x180007da9  mov     rax, [rcx]
0x180007dac  mov     edx, [rax]
0x180007dae  mov     [rbp+0A8h], rcx
0x180007db5  mov     [rbp+28h], edx
0x180007db8  mov     eax, [rbp+28h]
0x180007dbb  cmp     eax, 0E06D7363h
0x180007dc0  jnz     short loc_180007DD6
0x180007dc2  mov     rdx, [rbp+0A8h]
0x180007dc9  mov     ecx, [rbp+28h]
0x180007dcc  call    _XcptFilter_0
0x180007dd1  mov     [rbp+30h], eax
0x180007dd4  jmp     short loc_180007DDD
0x180007dd6  mov     dword ptr [rbp+30h], 0
0x180007ddd  mov     eax, [rbp+30h]
0x180007de0  add     rsp, 20h
0x180007de4  pop     rbp
0x180007de5  retn
0x180007de7  push    rbp
0x180007de9  sub     rsp, 20h
0x180007ded  mov     rbp, rdx
0x180007df0  mov     rax, [rcx]
0x180007df3  mov     edx, [rax]
0x180007df5  mov     [rbp+0B0h], rcx
0x180007dfc  mov     [rbp+38h], edx
0x180007dff  mov     eax, [rbp+38h]
0x180007e02  cmp     eax, 0E06D7363h
0x180007e07  jnz     short loc_180007E1D
0x180007e09  mov     rdx, [rbp+0B0h]
0x180007e10  mov     ecx, [rbp+38h]
0x180007e13  call    _XcptFilter_0
0x180007e18  mov     [rbp+40h], eax
0x180007e1b  jmp     short loc_180007E24
0x180007e1d  mov     dword ptr [rbp+40h], 0
0x180007e24  mov     eax, [rbp+40h]
0x180007e27  add     rsp, 20h
0x180007e2b  pop     rbp
0x180007e2c  retn
0x180007e2e  push    rbp
0x180007e30  sub     rsp, 20h
0x180007e34  mov     rbp, rdx
0x180007e37  mov     rax, [rcx]
0x180007e3a  mov     edx, [rax]
0x180007e3c  mov     [rbp+0B8h], rcx
0x180007e43  mov     [rbp+48h], edx
0x180007e46  mov     eax, [rbp+48h]
0x180007e49  cmp     eax, 0E06D7363h
0x180007e4e  jnz     short loc_180007E64
0x180007e50  mov     rdx, [rbp+0B8h]
0x180007e57  mov     ecx, [rbp+48h]
0x180007e5a  call    _XcptFilter_0
0x180007e5f  mov     [rbp+50h], eax
0x180007e62  jmp     short loc_180007E6B
0x180007e64  mov     dword ptr [rbp+50h], 0
0x180007e6b  mov     eax, [rbp+50h]
0x180007e6e  add     rsp, 20h
0x180007e72  pop     rbp
0x180007e73  retn
0x180007e75  push    rbp
0x180007e77  sub     rsp, 20h
0x180007e7b  mov     rbp, rdx
0x180007e7e  mov     rax, [rcx]
0x180007e81  mov     edx, [rax]
0x180007e83  mov     [rbp+0C0h], rcx
0x180007e8a  mov     [rbp+58h], edx
0x180007e8d  mov     eax, [rbp+58h]
0x180007e90  cmp     eax, 0E06D7363h
0x180007e95  jnz     short loc_180007EAB
0x180007e97  mov     rdx, [rbp+0C0h]
0x180007e9e  mov     ecx, [rbp+58h]
0x180007ea1  call    _XcptFilter_0
0x180007ea6  mov     [rbp+60h], eax
0x180007ea9  jmp     short loc_180007EB2
0x180007eab  mov     dword ptr [rbp+60h], 0
0x180007eb2  mov     eax, [rbp+60h]
0x180007eb5  add     rsp, 20h
0x180007eb9  pop     rbp
0x180007eba  retn
0x180007ebc  push    rbp
0x180007ebe  sub     rsp, 20h
0x180007ec2  mov     rbp, rdx
0x180007ec5  mov     rax, [rcx]
0x180007ec8  mov     edx, [rax]
0x180007eca  mov     [rbp+0C8h], rcx
0x180007ed1  mov     [rbp+68h], edx
0x180007ed4  mov     eax, [rbp+68h]
0x180007ed7  cmp     eax, 0E06D7363h
0x180007edc  jnz     short loc_180007EF2
0x180007ede  mov     rdx, [rbp+0C8h]
0x180007ee5  mov     ecx, [rbp+68h]
0x180007ee8  call    _XcptFilter_0
0x180007eed  mov     [rbp+70h], eax
0x180007ef0  jmp     short loc_180007EF9
0x180007ef2  mov     dword ptr [rbp+70h], 0
0x180007ef9  mov     eax, [rbp+70h]
0x180007efc  add     rsp, 20h
0x180007f00  pop     rbp
0x180007f01  retn
0x180007f03  push    rbp
0x180007f05  sub     rsp, 20h
0x180007f09  mov     rbp, rdx
0x180007f0c  mov     rax, [rcx]
0x180007f0f  mov     edx, [rax]
0x180007f11  mov     [rbp+0D0h], rcx
0x180007f18  mov     [rbp+78h], edx
0x180007f1b  mov     eax, [rbp+78h]
0x180007f1e  cmp     eax, 0E06D7363h
0x180007f23  jnz     short loc_180007F3C
0x180007f25  mov     rdx, [rbp+0D0h]
0x180007f2c  mov     ecx, [rbp+78h]
0x180007f2f  call    _XcptFilter_0
0x180007f34  mov     [rbp+80h], eax
0x180007f3a  jmp     short loc_180007F46
0x180007f3c  mov     dword ptr [rbp+80h], 0
0x180007f46  mov     eax, [rbp+80h]
0x180007f4c  add     rsp, 20h
0x180007f50  pop     rbp
0x180007f51  retn
0x180007f53  push    rbp
0x180007f55  sub     rsp, 20h
0x180007f59  mov     rbp, rdx
0x180007f5c  mov     rax, [rcx]
0x180007f5f  mov     edx, [rax]
0x180007f61  mov     [rbp+0D8h], rcx
0x180007f68  mov     [rbp+88h], edx
0x180007f6e  mov     eax, [rbp+88h]
0x180007f74  cmp     eax, 0E06D7363h
0x180007f79  jnz     short loc_180007F95
0x180007f7b  mov     rdx, [rbp+0D8h]
0x180007f82  mov     ecx, [rbp+88h]
0x180007f88  call    _XcptFilter_0
0x180007f8d  mov     [rbp+90h], eax
0x180007f93  jmp     short loc_180007F9F
0x180007f95  mov     dword ptr [rbp+90h], 0
0x180007f9f  mov     eax, [rbp+90h]
0x180007fa5  add     rsp, 20h
0x180007fa9  pop     rbp
0x180007faa  retn
0x180007fac  push    rbp
0x180007fae  sub     rsp, 20h
0x180007fb2  mov     rbp, rdx
0x180007fb5  mov     rax, [rcx]
0x180007fb8  mov     edx, [rax]
0x180007fba  mov     [rbp+0E0h], rcx
0x180007fc1  mov     [rbp+98h], edx
0x180007fc7  mov     eax, [rbp+98h]
0x180007fcd  cmp     eax, 0E06D7363h
0x180007fd2  jnz     short loc_180007FEE
0x180007fd4  mov     rdx, [rbp+0E0h]
0x180007fdb  mov     ecx, [rbp+98h]
0x180007fe1  call    _XcptFilter_0
0x180007fe6  mov     [rbp+0A0h], eax
0x180007fec  jmp     short loc_180007FF8
0x180007fee  mov     dword ptr [rbp+0A0h], 0
0x180007ff8  mov     eax, [rbp+0A0h]
0x180007ffe  add     rsp, 20h
0x180008002  pop     rbp
0x180008003  retn
0x180008005  push    rbp
0x180008007  sub     rsp, 20h
0x18000800b  mov     rbp, rdx
0x18000800e  cmp     dword ptr [rbp+118h], 1
0x180008015  ja      short loc_180008021
0x180008017  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
