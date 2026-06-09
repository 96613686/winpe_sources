# __DllMainCRTStartup

- ea: `0x180009e34`
- end: `0x18000a040`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009df0`

## callees

- `0x1800070a0`
- `0x180009bc0`
- `0x180009e34`
- `0x18000a186`
- `0x18000d340`

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
  if ( (_DWORD)fdwReason || dword_1800132E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800132E4 = 1;
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
            if ( dword_1800132E4 )
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
0x180009e34  mov     [rsp+lpvReserved], r8
0x180009e39  mov     [rsp+arg_8], edx
0x180009e3d  mov     [rsp+arg_0], rcx
0x180009e42  push    rbx
0x180009e43  push    rsi
0x180009e44  push    rdi
0x180009e45  sub     rsp, 0F0h
0x180009e4c  mov     edi, edx
0x180009e4e  mov     rsi, rcx
0x180009e51  mov     ebx, 1
0x180009e56  cmp     edx, ebx
0x180009e58  ja      short loc_180009E60
0x180009e5a  mov     cs:__native_dllmain_reason, edx
0x180009e60  test    edx, edx
0x180009e62  jnz     short loc_180009E77
0x180009e64  cmp     cs:dword_1800132E0, edx
0x180009e6a  jnz     short loc_180009E77
0x180009e6c  xor     ebx, ebx
0x180009e6e  mov     [rsp+108h+var_E8], ebx
0x180009e72  jmp     loc_18000A024
0x180009e77  lea     eax, [rdx-1]
0x180009e7a  cmp     eax, 1
0x180009e7d  ja      loc_180009F04
0x180009e83  mov     rax, cs:_pRawDllMain
0x180009e8a  test    rax, rax
0x180009e8d  jz      short loc_180009EC5
0x180009e8f  cmp     edx, 1
0x180009e92  jnz     short loc_180009E9A
0x180009e94  mov     cs:dword_1800132E4, edx
0x180009e9a  mov     r8, [rsp+108h+lpvReserved]
0x180009ea2  call    cs:__guard_dispatch_icall_fptr
0x180009ea8  mov     ebx, eax
0x180009eaa  mov     [rsp+108h+var_E8], eax
0x180009eae  jmp     short loc_180009EC5
0x180009eb0  xor     ebx, ebx
0x180009eb2  mov     [rsp+108h+var_E8], ebx
0x180009eb6  mov     edi, [rsp+108h+arg_8]
0x180009ebd  mov     rsi, [rsp+108h+arg_0]
0x180009ec5  test    ebx, ebx
0x180009ec7  jz      loc_18000A024
0x180009ecd  mov     r8, [rsp+108h+lpvReserved]
0x180009ed5  mov     edx, edi
0x180009ed7  mov     rcx, rsi
0x180009eda  call    _CRT_INIT
0x180009edf  mov     ebx, eax
0x180009ee1  mov     [rsp+108h+var_E8], eax
0x180009ee5  jmp     short loc_180009EFC
0x180009ee7  xor     ebx, ebx
0x180009ee9  mov     [rsp+108h+var_E8], ebx
0x180009eed  mov     edi, [rsp+108h+arg_8]
0x180009ef4  mov     rsi, [rsp+108h+arg_0]
0x180009efc  test    ebx, ebx
0x180009efe  jz      loc_18000A024
0x180009f04  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180009f0c  mov     edx, edi; fdwReason
0x180009f0e  mov     rcx, rsi; hinstDLL
0x180009f11  call    DllMain
0x180009f16  mov     ebx, eax
0x180009f18  mov     [rsp+108h+var_E8], eax
0x180009f1c  jmp     short loc_180009F33
0x180009f1e  xor     ebx, ebx
0x180009f20  mov     [rsp+108h+var_E8], ebx
0x180009f24  mov     edi, [rsp+108h+arg_8]
0x180009f2b  mov     rsi, [rsp+108h+arg_0]
0x180009f33  cmp     edi, 1
0x180009f36  jnz     short loc_180009FAF
0x180009f38  test    ebx, ebx
0x180009f3a  jnz     short loc_180009FAF
0x180009f3c  xor     r8d, r8d; lpvReserved
0x180009f3f  xor     edx, edx; fdwReason
0x180009f41  mov     rcx, rsi; hinstDLL
0x180009f44  call    DllMain
0x180009f49  jmp     short loc_180009F5E
0x180009f4b  mov     edi, [rsp+108h+arg_8]
0x180009f52  mov     rsi, [rsp+108h+arg_0]
0x180009f5a  mov     ebx, [rsp+108h+var_E8]
0x180009f5e  xor     r8d, r8d
0x180009f61  xor     edx, edx
0x180009f63  mov     rcx, rsi
0x180009f66  call    _CRT_INIT
0x180009f6b  jmp     short loc_180009F80
0x180009f6d  mov     edi, [rsp+108h+arg_8]
0x180009f74  mov     rsi, [rsp+108h+arg_0]
0x180009f7c  mov     ebx, [rsp+108h+var_E8]
0x180009f80  mov     rax, cs:_pRawDllMain
0x180009f87  test    rax, rax
0x180009f8a  jz      short loc_180009FAF
0x180009f8c  xor     r8d, r8d
0x180009f8f  xor     edx, edx
0x180009f91  mov     rcx, rsi
0x180009f94  call    cs:__guard_dispatch_icall_fptr
0x180009f9a  jmp     short loc_180009FAF
0x180009f9c  mov     edi, [rsp+108h+arg_8]
0x180009fa3  mov     rsi, [rsp+108h+arg_0]
0x180009fab  mov     ebx, [rsp+108h+var_E8]
0x180009faf  test    edi, edi
0x180009fb1  jz      short loc_180009FB8
0x180009fb3  cmp     edi, 3
0x180009fb6  jnz     short loc_18000A024
0x180009fb8  mov     r8, [rsp+108h+lpvReserved]
0x180009fc0  mov     edx, edi
0x180009fc2  mov     rcx, rsi
0x180009fc5  call    _CRT_INIT
0x180009fca  mov     ebx, eax
0x180009fcc  mov     [rsp+108h+var_E8], eax
0x180009fd0  jmp     short loc_180009FE7
0x180009fd2  xor     ebx, ebx
0x180009fd4  mov     [rsp+108h+var_E8], ebx
0x180009fd8  mov     edi, [rsp+108h+arg_8]
0x180009fdf  mov     rsi, [rsp+108h+arg_0]
0x180009fe7  mov     rax, cs:_pRawDllMain
0x180009fee  test    rax, rax
0x180009ff1  jz      short loc_18000A024
0x180009ff3  cmp     cs:dword_1800132E4, 0
0x180009ffa  jz      short loc_18000A024
0x180009ffc  mov     r8, [rsp+108h+lpvReserved]
0x18000a004  mov     edx, edi
0x18000a006  mov     rcx, rsi
0x18000a009  call    cs:__guard_dispatch_icall_fptr
0x18000a00f  mov     ebx, eax
0x18000a011  mov     [rsp+108h+var_E8], eax
0x18000a015  jmp     short loc_18000A024
0x18000a017  xor     ebx, ebx
0x18000a019  mov     [rsp+108h+var_E8], ebx
0x18000a01d  mov     edi, [rsp+108h+arg_8]
0x18000a024  cmp     edi, 1
0x18000a027  ja      short loc_18000A033
0x18000a029  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000a033  mov     eax, ebx
0x18000a035  add     rsp, 0F0h
0x18000a03c  pop     rdi
0x18000a03d  pop     rsi
0x18000a03e  pop     rbx
0x18000a03f  retn
0x18000d514  push    rbp
0x18000d516  sub     rsp, 20h
0x18000d51a  mov     rbp, rdx
0x18000d51d  mov     rax, [rcx]
0x18000d520  mov     edx, [rax]
0x18000d522  mov     [rbp+0A8h], rcx
0x18000d529  mov     [rbp+28h], edx
0x18000d52c  mov     eax, [rbp+28h]
0x18000d52f  cmp     eax, 0E06D7363h
0x18000d534  jnz     short loc_18000D54A
0x18000d536  mov     rdx, [rbp+0A8h]
0x18000d53d  mov     ecx, [rbp+28h]
0x18000d540  call    _XcptFilter_0
0x18000d545  mov     [rbp+30h], eax
0x18000d548  jmp     short loc_18000D551
0x18000d54a  mov     dword ptr [rbp+30h], 0
0x18000d551  mov     eax, [rbp+30h]
0x18000d554  add     rsp, 20h
0x18000d558  pop     rbp
0x18000d559  retn
0x18000d55b  push    rbp
0x18000d55d  sub     rsp, 20h
0x18000d561  mov     rbp, rdx
0x18000d564  mov     rax, [rcx]
0x18000d567  mov     edx, [rax]
0x18000d569  mov     [rbp+0B0h], rcx
0x18000d570  mov     [rbp+38h], edx
0x18000d573  mov     eax, [rbp+38h]
0x18000d576  cmp     eax, 0E06D7363h
0x18000d57b  jnz     short loc_18000D591
0x18000d57d  mov     rdx, [rbp+0B0h]
0x18000d584  mov     ecx, [rbp+38h]
0x18000d587  call    _XcptFilter_0
0x18000d58c  mov     [rbp+40h], eax
0x18000d58f  jmp     short loc_18000D598
0x18000d591  mov     dword ptr [rbp+40h], 0
0x18000d598  mov     eax, [rbp+40h]
0x18000d59b  add     rsp, 20h
0x18000d59f  pop     rbp
0x18000d5a0  retn
0x18000d5a2  push    rbp
0x18000d5a4  sub     rsp, 20h
0x18000d5a8  mov     rbp, rdx
0x18000d5ab  mov     rax, [rcx]
0x18000d5ae  mov     edx, [rax]
0x18000d5b0  mov     [rbp+0B8h], rcx
0x18000d5b7  mov     [rbp+48h], edx
0x18000d5ba  mov     eax, [rbp+48h]
0x18000d5bd  cmp     eax, 0E06D7363h
0x18000d5c2  jnz     short loc_18000D5D8
0x18000d5c4  mov     rdx, [rbp+0B8h]
0x18000d5cb  mov     ecx, [rbp+48h]
0x18000d5ce  call    _XcptFilter_0
0x18000d5d3  mov     [rbp+50h], eax
0x18000d5d6  jmp     short loc_18000D5DF
0x18000d5d8  mov     dword ptr [rbp+50h], 0
0x18000d5df  mov     eax, [rbp+50h]
0x18000d5e2  add     rsp, 20h
0x18000d5e6  pop     rbp
0x18000d5e7  retn
0x18000d5e9  push    rbp
0x18000d5eb  sub     rsp, 20h
0x18000d5ef  mov     rbp, rdx
0x18000d5f2  mov     rax, [rcx]
0x18000d5f5  mov     edx, [rax]
0x18000d5f7  mov     [rbp+0C0h], rcx
0x18000d5fe  mov     [rbp+58h], edx
0x18000d601  mov     eax, [rbp+58h]
0x18000d604  cmp     eax, 0E06D7363h
0x18000d609  jnz     short loc_18000D61F
0x18000d60b  mov     rdx, [rbp+0C0h]
0x18000d612  mov     ecx, [rbp+58h]
0x18000d615  call    _XcptFilter_0
0x18000d61a  mov     [rbp+60h], eax
0x18000d61d  jmp     short loc_18000D626
0x18000d61f  mov     dword ptr [rbp+60h], 0
0x18000d626  mov     eax, [rbp+60h]
0x18000d629  add     rsp, 20h
0x18000d62d  pop     rbp
0x18000d62e  retn
0x18000d630  push    rbp
0x18000d632  sub     rsp, 20h
0x18000d636  mov     rbp, rdx
0x18000d639  mov     rax, [rcx]
0x18000d63c  mov     edx, [rax]
0x18000d63e  mov     [rbp+0C8h], rcx
0x18000d645  mov     [rbp+68h], edx
0x18000d648  mov     eax, [rbp+68h]
0x18000d64b  cmp     eax, 0E06D7363h
0x18000d650  jnz     short loc_18000D666
0x18000d652  mov     rdx, [rbp+0C8h]
0x18000d659  mov     ecx, [rbp+68h]
0x18000d65c  call    _XcptFilter_0
0x18000d661  mov     [rbp+70h], eax
0x18000d664  jmp     short loc_18000D66D
0x18000d666  mov     dword ptr [rbp+70h], 0
0x18000d66d  mov     eax, [rbp+70h]
0x18000d670  add     rsp, 20h
0x18000d674  pop     rbp
0x18000d675  retn
0x18000d677  push    rbp
0x18000d679  sub     rsp, 20h
0x18000d67d  mov     rbp, rdx
0x18000d680  mov     rax, [rcx]
0x18000d683  mov     edx, [rax]
0x18000d685  mov     [rbp+0D0h], rcx
0x18000d68c  mov     [rbp+78h], edx
0x18000d68f  mov     eax, [rbp+78h]
0x18000d692  cmp     eax, 0E06D7363h
0x18000d697  jnz     short loc_18000D6B0
0x18000d699  mov     rdx, [rbp+0D0h]
0x18000d6a0  mov     ecx, [rbp+78h]
0x18000d6a3  call    _XcptFilter_0
0x18000d6a8  mov     [rbp+80h], eax
0x18000d6ae  jmp     short loc_18000D6BA
0x18000d6b0  mov     dword ptr [rbp+80h], 0
0x18000d6ba  mov     eax, [rbp+80h]
0x18000d6c0  add     rsp, 20h
0x18000d6c4  pop     rbp
0x18000d6c5  retn
0x18000d6c7  push    rbp
0x18000d6c9  sub     rsp, 20h
0x18000d6cd  mov     rbp, rdx
0x18000d6d0  mov     rax, [rcx]
0x18000d6d3  mov     edx, [rax]
0x18000d6d5  mov     [rbp+0D8h], rcx
0x18000d6dc  mov     [rbp+88h], edx
0x18000d6e2  mov     eax, [rbp+88h]
0x18000d6e8  cmp     eax, 0E06D7363h
0x18000d6ed  jnz     short loc_18000D709
0x18000d6ef  mov     rdx, [rbp+0D8h]
0x18000d6f6  mov     ecx, [rbp+88h]
0x18000d6fc  call    _XcptFilter_0
0x18000d701  mov     [rbp+90h], eax
0x18000d707  jmp     short loc_18000D713
0x18000d709  mov     dword ptr [rbp+90h], 0
0x18000d713  mov     eax, [rbp+90h]
0x18000d719  add     rsp, 20h
0x18000d71d  pop     rbp
0x18000d71e  retn
0x18000d720  push    rbp
0x18000d722  sub     rsp, 20h
0x18000d726  mov     rbp, rdx
0x18000d729  mov     rax, [rcx]
0x18000d72c  mov     edx, [rax]
0x18000d72e  mov     [rbp+0E0h], rcx
0x18000d735  mov     [rbp+98h], edx
0x18000d73b  mov     eax, [rbp+98h]
0x18000d741  cmp     eax, 0E06D7363h
0x18000d746  jnz     short loc_18000D762
0x18000d748  mov     rdx, [rbp+0E0h]
0x18000d74f  mov     ecx, [rbp+98h]
0x18000d755  call    _XcptFilter_0
0x18000d75a  mov     [rbp+0A0h], eax
0x18000d760  jmp     short loc_18000D76C
0x18000d762  mov     dword ptr [rbp+0A0h], 0
0x18000d76c  mov     eax, [rbp+0A0h]
0x18000d772  add     rsp, 20h
0x18000d776  pop     rbp
0x18000d777  retn
0x18000d779  push    rbp
0x18000d77b  sub     rsp, 20h
0x18000d77f  mov     rbp, rdx
0x18000d782  cmp     dword ptr [rbp+118h], 1
0x18000d789  ja      short loc_18000D795
0x18000d78b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
