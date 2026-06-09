# __DllMainCRTStartup

- ea: `0x180001984`
- end: `0x180001b90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001940`

## callees

- `0x180001710`
- `0x180001984`
- `0x180001f3e`
- `0x180006ee4`
- `0x18001e090`

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
  if ( (_DWORD)fdwReason || dword_18002B39C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002B3A0 = 1;
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
            if ( dword_18002B3A0 )
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
0x180001984  mov     [rsp+lpvReserved], r8
0x180001989  mov     [rsp+arg_8], edx
0x18000198d  mov     [rsp+arg_0], rcx
0x180001992  push    rbx
0x180001993  push    rsi
0x180001994  push    rdi
0x180001995  sub     rsp, 0F0h
0x18000199c  mov     edi, edx
0x18000199e  mov     rsi, rcx
0x1800019a1  mov     ebx, 1
0x1800019a6  cmp     edx, ebx
0x1800019a8  ja      short loc_1800019B0
0x1800019aa  mov     cs:__native_dllmain_reason, edx
0x1800019b0  test    edx, edx
0x1800019b2  jnz     short loc_1800019C7
0x1800019b4  cmp     cs:dword_18002B39C, edx
0x1800019ba  jnz     short loc_1800019C7
0x1800019bc  xor     ebx, ebx
0x1800019be  mov     [rsp+108h+var_E8], ebx
0x1800019c2  jmp     loc_180001B74
0x1800019c7  lea     eax, [rdx-1]
0x1800019ca  cmp     eax, 1
0x1800019cd  ja      loc_180001A54
0x1800019d3  mov     rax, cs:_pRawDllMain
0x1800019da  test    rax, rax
0x1800019dd  jz      short loc_180001A15
0x1800019df  cmp     edx, 1
0x1800019e2  jnz     short loc_1800019EA
0x1800019e4  mov     cs:dword_18002B3A0, edx
0x1800019ea  mov     r8, [rsp+108h+lpvReserved]
0x1800019f2  call    cs:__guard_dispatch_icall_fptr
0x1800019f8  mov     ebx, eax
0x1800019fa  mov     [rsp+108h+var_E8], eax
0x1800019fe  jmp     short loc_180001A15
0x180001a00  xor     ebx, ebx
0x180001a02  mov     [rsp+108h+var_E8], ebx
0x180001a06  mov     edi, [rsp+108h+arg_8]
0x180001a0d  mov     rsi, [rsp+108h+arg_0]
0x180001a15  test    ebx, ebx
0x180001a17  jz      loc_180001B74
0x180001a1d  mov     r8, [rsp+108h+lpvReserved]
0x180001a25  mov     edx, edi
0x180001a27  mov     rcx, rsi
0x180001a2a  call    _CRT_INIT
0x180001a2f  mov     ebx, eax
0x180001a31  mov     [rsp+108h+var_E8], eax
0x180001a35  jmp     short loc_180001A4C
0x180001a37  xor     ebx, ebx
0x180001a39  mov     [rsp+108h+var_E8], ebx
0x180001a3d  mov     edi, [rsp+108h+arg_8]
0x180001a44  mov     rsi, [rsp+108h+arg_0]
0x180001a4c  test    ebx, ebx
0x180001a4e  jz      loc_180001B74
0x180001a54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a5c  mov     edx, edi; fdwReason
0x180001a5e  mov     rcx, rsi; hinstDLL
0x180001a61  call    DllMain
0x180001a66  mov     ebx, eax
0x180001a68  mov     [rsp+108h+var_E8], eax
0x180001a6c  jmp     short loc_180001A83
0x180001a6e  xor     ebx, ebx
0x180001a70  mov     [rsp+108h+var_E8], ebx
0x180001a74  mov     edi, [rsp+108h+arg_8]
0x180001a7b  mov     rsi, [rsp+108h+arg_0]
0x180001a83  cmp     edi, 1
0x180001a86  jnz     short loc_180001AFF
0x180001a88  test    ebx, ebx
0x180001a8a  jnz     short loc_180001AFF
0x180001a8c  xor     r8d, r8d; lpvReserved
0x180001a8f  xor     edx, edx; fdwReason
0x180001a91  mov     rcx, rsi; hinstDLL
0x180001a94  call    DllMain
0x180001a99  jmp     short loc_180001AAE
0x180001a9b  mov     edi, [rsp+108h+arg_8]
0x180001aa2  mov     rsi, [rsp+108h+arg_0]
0x180001aaa  mov     ebx, [rsp+108h+var_E8]
0x180001aae  xor     r8d, r8d
0x180001ab1  xor     edx, edx
0x180001ab3  mov     rcx, rsi
0x180001ab6  call    _CRT_INIT
0x180001abb  jmp     short loc_180001AD0
0x180001abd  mov     edi, [rsp+108h+arg_8]
0x180001ac4  mov     rsi, [rsp+108h+arg_0]
0x180001acc  mov     ebx, [rsp+108h+var_E8]
0x180001ad0  mov     rax, cs:_pRawDllMain
0x180001ad7  test    rax, rax
0x180001ada  jz      short loc_180001AFF
0x180001adc  xor     r8d, r8d
0x180001adf  xor     edx, edx
0x180001ae1  mov     rcx, rsi
0x180001ae4  call    cs:__guard_dispatch_icall_fptr
0x180001aea  jmp     short loc_180001AFF
0x180001aec  mov     edi, [rsp+108h+arg_8]
0x180001af3  mov     rsi, [rsp+108h+arg_0]
0x180001afb  mov     ebx, [rsp+108h+var_E8]
0x180001aff  test    edi, edi
0x180001b01  jz      short loc_180001B08
0x180001b03  cmp     edi, 3
0x180001b06  jnz     short loc_180001B74
0x180001b08  mov     r8, [rsp+108h+lpvReserved]
0x180001b10  mov     edx, edi
0x180001b12  mov     rcx, rsi
0x180001b15  call    _CRT_INIT
0x180001b1a  mov     ebx, eax
0x180001b1c  mov     [rsp+108h+var_E8], eax
0x180001b20  jmp     short loc_180001B37
0x180001b22  xor     ebx, ebx
0x180001b24  mov     [rsp+108h+var_E8], ebx
0x180001b28  mov     edi, [rsp+108h+arg_8]
0x180001b2f  mov     rsi, [rsp+108h+arg_0]
0x180001b37  mov     rax, cs:_pRawDllMain
0x180001b3e  test    rax, rax
0x180001b41  jz      short loc_180001B74
0x180001b43  cmp     cs:dword_18002B3A0, 0
0x180001b4a  jz      short loc_180001B74
0x180001b4c  mov     r8, [rsp+108h+lpvReserved]
0x180001b54  mov     edx, edi
0x180001b56  mov     rcx, rsi
0x180001b59  call    cs:__guard_dispatch_icall_fptr
0x180001b5f  mov     ebx, eax
0x180001b61  mov     [rsp+108h+var_E8], eax
0x180001b65  jmp     short loc_180001B74
0x180001b67  xor     ebx, ebx
0x180001b69  mov     [rsp+108h+var_E8], ebx
0x180001b6d  mov     edi, [rsp+108h+arg_8]
0x180001b74  cmp     edi, 1
0x180001b77  ja      short loc_180001B83
0x180001b79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b83  mov     eax, ebx
0x180001b85  add     rsp, 0F0h
0x180001b8c  pop     rdi
0x180001b8d  pop     rsi
0x180001b8e  pop     rbx
0x180001b8f  retn
0x18001e133  push    rbp
0x18001e135  sub     rsp, 20h
0x18001e139  mov     rbp, rdx
0x18001e13c  mov     rax, [rcx]
0x18001e13f  mov     edx, [rax]
0x18001e141  mov     [rbp+0A8h], rcx
0x18001e148  mov     [rbp+28h], edx
0x18001e14b  mov     eax, [rbp+28h]
0x18001e14e  cmp     eax, 0E06D7363h
0x18001e153  jnz     short loc_18001E169
0x18001e155  mov     rdx, [rbp+0A8h]
0x18001e15c  mov     ecx, [rbp+28h]
0x18001e15f  call    _XcptFilter_0
0x18001e164  mov     [rbp+30h], eax
0x18001e167  jmp     short loc_18001E170
0x18001e169  mov     dword ptr [rbp+30h], 0
0x18001e170  mov     eax, [rbp+30h]
0x18001e173  add     rsp, 20h
0x18001e177  pop     rbp
0x18001e178  retn
0x18001e17a  push    rbp
0x18001e17c  sub     rsp, 20h
0x18001e180  mov     rbp, rdx
0x18001e183  mov     rax, [rcx]
0x18001e186  mov     edx, [rax]
0x18001e188  mov     [rbp+0B0h], rcx
0x18001e18f  mov     [rbp+38h], edx
0x18001e192  mov     eax, [rbp+38h]
0x18001e195  cmp     eax, 0E06D7363h
0x18001e19a  jnz     short loc_18001E1B0
0x18001e19c  mov     rdx, [rbp+0B0h]
0x18001e1a3  mov     ecx, [rbp+38h]
0x18001e1a6  call    _XcptFilter_0
0x18001e1ab  mov     [rbp+40h], eax
0x18001e1ae  jmp     short loc_18001E1B7
0x18001e1b0  mov     dword ptr [rbp+40h], 0
0x18001e1b7  mov     eax, [rbp+40h]
0x18001e1ba  add     rsp, 20h
0x18001e1be  pop     rbp
0x18001e1bf  retn
0x18001e1c1  push    rbp
0x18001e1c3  sub     rsp, 20h
0x18001e1c7  mov     rbp, rdx
0x18001e1ca  mov     rax, [rcx]
0x18001e1cd  mov     edx, [rax]
0x18001e1cf  mov     [rbp+0B8h], rcx
0x18001e1d6  mov     [rbp+48h], edx
0x18001e1d9  mov     eax, [rbp+48h]
0x18001e1dc  cmp     eax, 0E06D7363h
0x18001e1e1  jnz     short loc_18001E1F7
0x18001e1e3  mov     rdx, [rbp+0B8h]
0x18001e1ea  mov     ecx, [rbp+48h]
0x18001e1ed  call    _XcptFilter_0
0x18001e1f2  mov     [rbp+50h], eax
0x18001e1f5  jmp     short loc_18001E1FE
0x18001e1f7  mov     dword ptr [rbp+50h], 0
0x18001e1fe  mov     eax, [rbp+50h]
0x18001e201  add     rsp, 20h
0x18001e205  pop     rbp
0x18001e206  retn
0x18001e208  push    rbp
0x18001e20a  sub     rsp, 20h
0x18001e20e  mov     rbp, rdx
0x18001e211  mov     rax, [rcx]
0x18001e214  mov     edx, [rax]
0x18001e216  mov     [rbp+0C0h], rcx
0x18001e21d  mov     [rbp+58h], edx
0x18001e220  mov     eax, [rbp+58h]
0x18001e223  cmp     eax, 0E06D7363h
0x18001e228  jnz     short loc_18001E23E
0x18001e22a  mov     rdx, [rbp+0C0h]
0x18001e231  mov     ecx, [rbp+58h]
0x18001e234  call    _XcptFilter_0
0x18001e239  mov     [rbp+60h], eax
0x18001e23c  jmp     short loc_18001E245
0x18001e23e  mov     dword ptr [rbp+60h], 0
0x18001e245  mov     eax, [rbp+60h]
0x18001e248  add     rsp, 20h
0x18001e24c  pop     rbp
0x18001e24d  retn
0x18001e24f  push    rbp
0x18001e251  sub     rsp, 20h
0x18001e255  mov     rbp, rdx
0x18001e258  mov     rax, [rcx]
0x18001e25b  mov     edx, [rax]
0x18001e25d  mov     [rbp+0C8h], rcx
0x18001e264  mov     [rbp+68h], edx
0x18001e267  mov     eax, [rbp+68h]
0x18001e26a  cmp     eax, 0E06D7363h
0x18001e26f  jnz     short loc_18001E285
0x18001e271  mov     rdx, [rbp+0C8h]
0x18001e278  mov     ecx, [rbp+68h]
0x18001e27b  call    _XcptFilter_0
0x18001e280  mov     [rbp+70h], eax
0x18001e283  jmp     short loc_18001E28C
0x18001e285  mov     dword ptr [rbp+70h], 0
0x18001e28c  mov     eax, [rbp+70h]
0x18001e28f  add     rsp, 20h
0x18001e293  pop     rbp
0x18001e294  retn
0x18001e296  push    rbp
0x18001e298  sub     rsp, 20h
0x18001e29c  mov     rbp, rdx
0x18001e29f  mov     rax, [rcx]
0x18001e2a2  mov     edx, [rax]
0x18001e2a4  mov     [rbp+0D0h], rcx
0x18001e2ab  mov     [rbp+78h], edx
0x18001e2ae  mov     eax, [rbp+78h]
0x18001e2b1  cmp     eax, 0E06D7363h
0x18001e2b6  jnz     short loc_18001E2CF
0x18001e2b8  mov     rdx, [rbp+0D0h]
0x18001e2bf  mov     ecx, [rbp+78h]
0x18001e2c2  call    _XcptFilter_0
0x18001e2c7  mov     [rbp+80h], eax
0x18001e2cd  jmp     short loc_18001E2D9
0x18001e2cf  mov     dword ptr [rbp+80h], 0
0x18001e2d9  mov     eax, [rbp+80h]
0x18001e2df  add     rsp, 20h
0x18001e2e3  pop     rbp
0x18001e2e4  retn
0x18001e2e6  push    rbp
0x18001e2e8  sub     rsp, 20h
0x18001e2ec  mov     rbp, rdx
0x18001e2ef  mov     rax, [rcx]
0x18001e2f2  mov     edx, [rax]
0x18001e2f4  mov     [rbp+0D8h], rcx
0x18001e2fb  mov     [rbp+88h], edx
0x18001e301  mov     eax, [rbp+88h]
0x18001e307  cmp     eax, 0E06D7363h
0x18001e30c  jnz     short loc_18001E328
0x18001e30e  mov     rdx, [rbp+0D8h]
0x18001e315  mov     ecx, [rbp+88h]
0x18001e31b  call    _XcptFilter_0
0x18001e320  mov     [rbp+90h], eax
0x18001e326  jmp     short loc_18001E332
0x18001e328  mov     dword ptr [rbp+90h], 0
0x18001e332  mov     eax, [rbp+90h]
0x18001e338  add     rsp, 20h
0x18001e33c  pop     rbp
0x18001e33d  retn
0x18001e33f  push    rbp
0x18001e341  sub     rsp, 20h
0x18001e345  mov     rbp, rdx
0x18001e348  mov     rax, [rcx]
0x18001e34b  mov     edx, [rax]
0x18001e34d  mov     [rbp+0E0h], rcx
0x18001e354  mov     [rbp+98h], edx
0x18001e35a  mov     eax, [rbp+98h]
0x18001e360  cmp     eax, 0E06D7363h
0x18001e365  jnz     short loc_18001E381
0x18001e367  mov     rdx, [rbp+0E0h]
0x18001e36e  mov     ecx, [rbp+98h]
0x18001e374  call    _XcptFilter_0
0x18001e379  mov     [rbp+0A0h], eax
0x18001e37f  jmp     short loc_18001E38B
0x18001e381  mov     dword ptr [rbp+0A0h], 0
0x18001e38b  mov     eax, [rbp+0A0h]
0x18001e391  add     rsp, 20h
0x18001e395  pop     rbp
0x18001e396  retn
0x18001e398  push    rbp
0x18001e39a  sub     rsp, 20h
0x18001e39e  mov     rbp, rdx
0x18001e3a1  cmp     dword ptr [rbp+118h], 1
0x18001e3a8  ja      short loc_18001E3B4
0x18001e3aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
