# __DllMainCRTStartup

- ea: `0x180001e64`
- end: `0x180002070`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001e20`

## callees

- `0x180001bf0`
- `0x180001e64`
- `0x18000258e`
- `0x180006d30`
- `0x18000c620`

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
  if ( (_DWORD)fdwReason || dword_180015AEC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180015AF0 = 1;
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
            if ( dword_180015AF0 )
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
0x180001e64  mov     [rsp+lpvReserved], r8
0x180001e69  mov     [rsp+arg_8], edx
0x180001e6d  mov     [rsp+arg_0], rcx
0x180001e72  push    rbx
0x180001e73  push    rsi
0x180001e74  push    rdi
0x180001e75  sub     rsp, 0F0h
0x180001e7c  mov     edi, edx
0x180001e7e  mov     rsi, rcx
0x180001e81  mov     ebx, 1
0x180001e86  cmp     edx, ebx
0x180001e88  ja      short loc_180001E90
0x180001e8a  mov     cs:__native_dllmain_reason, edx
0x180001e90  test    edx, edx
0x180001e92  jnz     short loc_180001EA7
0x180001e94  cmp     cs:dword_180015AEC, edx
0x180001e9a  jnz     short loc_180001EA7
0x180001e9c  xor     ebx, ebx
0x180001e9e  mov     [rsp+108h+var_E8], ebx
0x180001ea2  jmp     loc_180002054
0x180001ea7  lea     eax, [rdx-1]
0x180001eaa  cmp     eax, 1
0x180001ead  ja      loc_180001F34
0x180001eb3  mov     rax, cs:_pRawDllMain
0x180001eba  test    rax, rax
0x180001ebd  jz      short loc_180001EF5
0x180001ebf  cmp     edx, 1
0x180001ec2  jnz     short loc_180001ECA
0x180001ec4  mov     cs:dword_180015AF0, edx
0x180001eca  mov     r8, [rsp+108h+lpvReserved]
0x180001ed2  call    cs:__guard_dispatch_icall_fptr
0x180001ed8  mov     ebx, eax
0x180001eda  mov     [rsp+108h+var_E8], eax
0x180001ede  jmp     short loc_180001EF5
0x180001ee0  xor     ebx, ebx
0x180001ee2  mov     [rsp+108h+var_E8], ebx
0x180001ee6  mov     edi, [rsp+108h+arg_8]
0x180001eed  mov     rsi, [rsp+108h+arg_0]
0x180001ef5  test    ebx, ebx
0x180001ef7  jz      loc_180002054
0x180001efd  mov     r8, [rsp+108h+lpvReserved]
0x180001f05  mov     edx, edi
0x180001f07  mov     rcx, rsi
0x180001f0a  call    _CRT_INIT
0x180001f0f  mov     ebx, eax
0x180001f11  mov     [rsp+108h+var_E8], eax
0x180001f15  jmp     short loc_180001F2C
0x180001f17  xor     ebx, ebx
0x180001f19  mov     [rsp+108h+var_E8], ebx
0x180001f1d  mov     edi, [rsp+108h+arg_8]
0x180001f24  mov     rsi, [rsp+108h+arg_0]
0x180001f2c  test    ebx, ebx
0x180001f2e  jz      loc_180002054
0x180001f34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001f3c  mov     edx, edi; fdwReason
0x180001f3e  mov     rcx, rsi; hinstDLL
0x180001f41  call    DllMain
0x180001f46  mov     ebx, eax
0x180001f48  mov     [rsp+108h+var_E8], eax
0x180001f4c  jmp     short loc_180001F63
0x180001f4e  xor     ebx, ebx
0x180001f50  mov     [rsp+108h+var_E8], ebx
0x180001f54  mov     edi, [rsp+108h+arg_8]
0x180001f5b  mov     rsi, [rsp+108h+arg_0]
0x180001f63  cmp     edi, 1
0x180001f66  jnz     short loc_180001FDF
0x180001f68  test    ebx, ebx
0x180001f6a  jnz     short loc_180001FDF
0x180001f6c  xor     r8d, r8d; lpvReserved
0x180001f6f  xor     edx, edx; fdwReason
0x180001f71  mov     rcx, rsi; hinstDLL
0x180001f74  call    DllMain
0x180001f79  jmp     short loc_180001F8E
0x180001f7b  mov     edi, [rsp+108h+arg_8]
0x180001f82  mov     rsi, [rsp+108h+arg_0]
0x180001f8a  mov     ebx, [rsp+108h+var_E8]
0x180001f8e  xor     r8d, r8d
0x180001f91  xor     edx, edx
0x180001f93  mov     rcx, rsi
0x180001f96  call    _CRT_INIT
0x180001f9b  jmp     short loc_180001FB0
0x180001f9d  mov     edi, [rsp+108h+arg_8]
0x180001fa4  mov     rsi, [rsp+108h+arg_0]
0x180001fac  mov     ebx, [rsp+108h+var_E8]
0x180001fb0  mov     rax, cs:_pRawDllMain
0x180001fb7  test    rax, rax
0x180001fba  jz      short loc_180001FDF
0x180001fbc  xor     r8d, r8d
0x180001fbf  xor     edx, edx
0x180001fc1  mov     rcx, rsi
0x180001fc4  call    cs:__guard_dispatch_icall_fptr
0x180001fca  jmp     short loc_180001FDF
0x180001fcc  mov     edi, [rsp+108h+arg_8]
0x180001fd3  mov     rsi, [rsp+108h+arg_0]
0x180001fdb  mov     ebx, [rsp+108h+var_E8]
0x180001fdf  test    edi, edi
0x180001fe1  jz      short loc_180001FE8
0x180001fe3  cmp     edi, 3
0x180001fe6  jnz     short loc_180002054
0x180001fe8  mov     r8, [rsp+108h+lpvReserved]
0x180001ff0  mov     edx, edi
0x180001ff2  mov     rcx, rsi
0x180001ff5  call    _CRT_INIT
0x180001ffa  mov     ebx, eax
0x180001ffc  mov     [rsp+108h+var_E8], eax
0x180002000  jmp     short loc_180002017
0x180002002  xor     ebx, ebx
0x180002004  mov     [rsp+108h+var_E8], ebx
0x180002008  mov     edi, [rsp+108h+arg_8]
0x18000200f  mov     rsi, [rsp+108h+arg_0]
0x180002017  mov     rax, cs:_pRawDllMain
0x18000201e  test    rax, rax
0x180002021  jz      short loc_180002054
0x180002023  cmp     cs:dword_180015AF0, 0
0x18000202a  jz      short loc_180002054
0x18000202c  mov     r8, [rsp+108h+lpvReserved]
0x180002034  mov     edx, edi
0x180002036  mov     rcx, rsi
0x180002039  call    cs:__guard_dispatch_icall_fptr
0x18000203f  mov     ebx, eax
0x180002041  mov     [rsp+108h+var_E8], eax
0x180002045  jmp     short loc_180002054
0x180002047  xor     ebx, ebx
0x180002049  mov     [rsp+108h+var_E8], ebx
0x18000204d  mov     edi, [rsp+108h+arg_8]
0x180002054  cmp     edi, 1
0x180002057  ja      short loc_180002063
0x180002059  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002063  mov     eax, ebx
0x180002065  add     rsp, 0F0h
0x18000206c  pop     rdi
0x18000206d  pop     rsi
0x18000206e  pop     rbx
0x18000206f  retn
0x18000c732  push    rbp
0x18000c734  sub     rsp, 20h
0x18000c738  mov     rbp, rdx
0x18000c73b  mov     rax, [rcx]
0x18000c73e  mov     edx, [rax]
0x18000c740  mov     [rbp+0A8h], rcx
0x18000c747  mov     [rbp+28h], edx
0x18000c74a  mov     eax, [rbp+28h]
0x18000c74d  cmp     eax, 0E06D7363h
0x18000c752  jnz     short loc_18000C768
0x18000c754  mov     rdx, [rbp+0A8h]
0x18000c75b  mov     ecx, [rbp+28h]
0x18000c75e  call    _XcptFilter_0
0x18000c763  mov     [rbp+30h], eax
0x18000c766  jmp     short loc_18000C76F
0x18000c768  mov     dword ptr [rbp+30h], 0
0x18000c76f  mov     eax, [rbp+30h]
0x18000c772  add     rsp, 20h
0x18000c776  pop     rbp
0x18000c777  retn
0x18000c779  push    rbp
0x18000c77b  sub     rsp, 20h
0x18000c77f  mov     rbp, rdx
0x18000c782  mov     rax, [rcx]
0x18000c785  mov     edx, [rax]
0x18000c787  mov     [rbp+0B0h], rcx
0x18000c78e  mov     [rbp+38h], edx
0x18000c791  mov     eax, [rbp+38h]
0x18000c794  cmp     eax, 0E06D7363h
0x18000c799  jnz     short loc_18000C7AF
0x18000c79b  mov     rdx, [rbp+0B0h]
0x18000c7a2  mov     ecx, [rbp+38h]
0x18000c7a5  call    _XcptFilter_0
0x18000c7aa  mov     [rbp+40h], eax
0x18000c7ad  jmp     short loc_18000C7B6
0x18000c7af  mov     dword ptr [rbp+40h], 0
0x18000c7b6  mov     eax, [rbp+40h]
0x18000c7b9  add     rsp, 20h
0x18000c7bd  pop     rbp
0x18000c7be  retn
0x18000c7c0  push    rbp
0x18000c7c2  sub     rsp, 20h
0x18000c7c6  mov     rbp, rdx
0x18000c7c9  mov     rax, [rcx]
0x18000c7cc  mov     edx, [rax]
0x18000c7ce  mov     [rbp+0B8h], rcx
0x18000c7d5  mov     [rbp+48h], edx
0x18000c7d8  mov     eax, [rbp+48h]
0x18000c7db  cmp     eax, 0E06D7363h
0x18000c7e0  jnz     short loc_18000C7F6
0x18000c7e2  mov     rdx, [rbp+0B8h]
0x18000c7e9  mov     ecx, [rbp+48h]
0x18000c7ec  call    _XcptFilter_0
0x18000c7f1  mov     [rbp+50h], eax
0x18000c7f4  jmp     short loc_18000C7FD
0x18000c7f6  mov     dword ptr [rbp+50h], 0
0x18000c7fd  mov     eax, [rbp+50h]
0x18000c800  add     rsp, 20h
0x18000c804  pop     rbp
0x18000c805  retn
0x18000c807  push    rbp
0x18000c809  sub     rsp, 20h
0x18000c80d  mov     rbp, rdx
0x18000c810  mov     rax, [rcx]
0x18000c813  mov     edx, [rax]
0x18000c815  mov     [rbp+0C0h], rcx
0x18000c81c  mov     [rbp+58h], edx
0x18000c81f  mov     eax, [rbp+58h]
0x18000c822  cmp     eax, 0E06D7363h
0x18000c827  jnz     short loc_18000C83D
0x18000c829  mov     rdx, [rbp+0C0h]
0x18000c830  mov     ecx, [rbp+58h]
0x18000c833  call    _XcptFilter_0
0x18000c838  mov     [rbp+60h], eax
0x18000c83b  jmp     short loc_18000C844
0x18000c83d  mov     dword ptr [rbp+60h], 0
0x18000c844  mov     eax, [rbp+60h]
0x18000c847  add     rsp, 20h
0x18000c84b  pop     rbp
0x18000c84c  retn
0x18000c84e  push    rbp
0x18000c850  sub     rsp, 20h
0x18000c854  mov     rbp, rdx
0x18000c857  mov     rax, [rcx]
0x18000c85a  mov     edx, [rax]
0x18000c85c  mov     [rbp+0C8h], rcx
0x18000c863  mov     [rbp+68h], edx
0x18000c866  mov     eax, [rbp+68h]
0x18000c869  cmp     eax, 0E06D7363h
0x18000c86e  jnz     short loc_18000C884
0x18000c870  mov     rdx, [rbp+0C8h]
0x18000c877  mov     ecx, [rbp+68h]
0x18000c87a  call    _XcptFilter_0
0x18000c87f  mov     [rbp+70h], eax
0x18000c882  jmp     short loc_18000C88B
0x18000c884  mov     dword ptr [rbp+70h], 0
0x18000c88b  mov     eax, [rbp+70h]
0x18000c88e  add     rsp, 20h
0x18000c892  pop     rbp
0x18000c893  retn
0x18000c895  push    rbp
0x18000c897  sub     rsp, 20h
0x18000c89b  mov     rbp, rdx
0x18000c89e  mov     rax, [rcx]
0x18000c8a1  mov     edx, [rax]
0x18000c8a3  mov     [rbp+0D0h], rcx
0x18000c8aa  mov     [rbp+78h], edx
0x18000c8ad  mov     eax, [rbp+78h]
0x18000c8b0  cmp     eax, 0E06D7363h
0x18000c8b5  jnz     short loc_18000C8CE
0x18000c8b7  mov     rdx, [rbp+0D0h]
0x18000c8be  mov     ecx, [rbp+78h]
0x18000c8c1  call    _XcptFilter_0
0x18000c8c6  mov     [rbp+80h], eax
0x18000c8cc  jmp     short loc_18000C8D8
0x18000c8ce  mov     dword ptr [rbp+80h], 0
0x18000c8d8  mov     eax, [rbp+80h]
0x18000c8de  add     rsp, 20h
0x18000c8e2  pop     rbp
0x18000c8e3  retn
0x18000c8e5  push    rbp
0x18000c8e7  sub     rsp, 20h
0x18000c8eb  mov     rbp, rdx
0x18000c8ee  mov     rax, [rcx]
0x18000c8f1  mov     edx, [rax]
0x18000c8f3  mov     [rbp+0D8h], rcx
0x18000c8fa  mov     [rbp+88h], edx
0x18000c900  mov     eax, [rbp+88h]
0x18000c906  cmp     eax, 0E06D7363h
0x18000c90b  jnz     short loc_18000C927
0x18000c90d  mov     rdx, [rbp+0D8h]
0x18000c914  mov     ecx, [rbp+88h]
0x18000c91a  call    _XcptFilter_0
0x18000c91f  mov     [rbp+90h], eax
0x18000c925  jmp     short loc_18000C931
0x18000c927  mov     dword ptr [rbp+90h], 0
0x18000c931  mov     eax, [rbp+90h]
0x18000c937  add     rsp, 20h
0x18000c93b  pop     rbp
0x18000c93c  retn
0x18000c93e  push    rbp
0x18000c940  sub     rsp, 20h
0x18000c944  mov     rbp, rdx
0x18000c947  mov     rax, [rcx]
0x18000c94a  mov     edx, [rax]
0x18000c94c  mov     [rbp+0E0h], rcx
0x18000c953  mov     [rbp+98h], edx
0x18000c959  mov     eax, [rbp+98h]
0x18000c95f  cmp     eax, 0E06D7363h
0x18000c964  jnz     short loc_18000C980
0x18000c966  mov     rdx, [rbp+0E0h]
0x18000c96d  mov     ecx, [rbp+98h]
0x18000c973  call    _XcptFilter_0
0x18000c978  mov     [rbp+0A0h], eax
0x18000c97e  jmp     short loc_18000C98A
0x18000c980  mov     dword ptr [rbp+0A0h], 0
0x18000c98a  mov     eax, [rbp+0A0h]
0x18000c990  add     rsp, 20h
0x18000c994  pop     rbp
0x18000c995  retn
0x18000c997  push    rbp
0x18000c999  sub     rsp, 20h
0x18000c99d  mov     rbp, rdx
0x18000c9a0  cmp     dword ptr [rbp+118h], 1
0x18000c9a7  ja      short loc_18000C9B3
0x18000c9a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
