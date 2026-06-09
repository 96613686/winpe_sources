# __DllMainCRTStartup

- ea: `0x1800018e4`
- end: `0x180001af0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800018a0`

## callees

- `0x180001670`
- `0x1800018e4`
- `0x1800020f6`
- `0x18001c424`
- `0x18002cfe0`

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
  if ( (_DWORD)fdwReason || dword_18003B640 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003B644 = 1;
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
            if ( dword_18003B644 )
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
0x1800018e4  mov     [rsp+lpvReserved], r8
0x1800018e9  mov     [rsp+arg_8], edx
0x1800018ed  mov     [rsp+arg_0], rcx
0x1800018f2  push    rbx
0x1800018f3  push    rsi
0x1800018f4  push    rdi
0x1800018f5  sub     rsp, 0F0h
0x1800018fc  mov     edi, edx
0x1800018fe  mov     rsi, rcx
0x180001901  mov     ebx, 1
0x180001906  cmp     edx, ebx
0x180001908  ja      short loc_180001910
0x18000190a  mov     cs:__native_dllmain_reason, edx
0x180001910  test    edx, edx
0x180001912  jnz     short loc_180001927
0x180001914  cmp     cs:dword_18003B640, edx
0x18000191a  jnz     short loc_180001927
0x18000191c  xor     ebx, ebx
0x18000191e  mov     [rsp+108h+var_E8], ebx
0x180001922  jmp     loc_180001AD4
0x180001927  lea     eax, [rdx-1]
0x18000192a  cmp     eax, 1
0x18000192d  ja      loc_1800019B4
0x180001933  mov     rax, cs:_pRawDllMain
0x18000193a  test    rax, rax
0x18000193d  jz      short loc_180001975
0x18000193f  cmp     edx, 1
0x180001942  jnz     short loc_18000194A
0x180001944  mov     cs:dword_18003B644, edx
0x18000194a  mov     r8, [rsp+108h+lpvReserved]
0x180001952  call    cs:__guard_dispatch_icall_fptr
0x180001958  mov     ebx, eax
0x18000195a  mov     [rsp+108h+var_E8], eax
0x18000195e  jmp     short loc_180001975
0x180001960  xor     ebx, ebx
0x180001962  mov     [rsp+108h+var_E8], ebx
0x180001966  mov     edi, [rsp+108h+arg_8]
0x18000196d  mov     rsi, [rsp+108h+arg_0]
0x180001975  test    ebx, ebx
0x180001977  jz      loc_180001AD4
0x18000197d  mov     r8, [rsp+108h+lpvReserved]
0x180001985  mov     edx, edi
0x180001987  mov     rcx, rsi
0x18000198a  call    _CRT_INIT
0x18000198f  mov     ebx, eax
0x180001991  mov     [rsp+108h+var_E8], eax
0x180001995  jmp     short loc_1800019AC
0x180001997  xor     ebx, ebx
0x180001999  mov     [rsp+108h+var_E8], ebx
0x18000199d  mov     edi, [rsp+108h+arg_8]
0x1800019a4  mov     rsi, [rsp+108h+arg_0]
0x1800019ac  test    ebx, ebx
0x1800019ae  jz      loc_180001AD4
0x1800019b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800019bc  mov     edx, edi; fdwReason
0x1800019be  mov     rcx, rsi; hinstDLL
0x1800019c1  call    DllMain
0x1800019c6  mov     ebx, eax
0x1800019c8  mov     [rsp+108h+var_E8], eax
0x1800019cc  jmp     short loc_1800019E3
0x1800019ce  xor     ebx, ebx
0x1800019d0  mov     [rsp+108h+var_E8], ebx
0x1800019d4  mov     edi, [rsp+108h+arg_8]
0x1800019db  mov     rsi, [rsp+108h+arg_0]
0x1800019e3  cmp     edi, 1
0x1800019e6  jnz     short loc_180001A5F
0x1800019e8  test    ebx, ebx
0x1800019ea  jnz     short loc_180001A5F
0x1800019ec  xor     r8d, r8d; lpvReserved
0x1800019ef  xor     edx, edx; fdwReason
0x1800019f1  mov     rcx, rsi; hinstDLL
0x1800019f4  call    DllMain
0x1800019f9  jmp     short loc_180001A0E
0x1800019fb  mov     edi, [rsp+108h+arg_8]
0x180001a02  mov     rsi, [rsp+108h+arg_0]
0x180001a0a  mov     ebx, [rsp+108h+var_E8]
0x180001a0e  xor     r8d, r8d
0x180001a11  xor     edx, edx
0x180001a13  mov     rcx, rsi
0x180001a16  call    _CRT_INIT
0x180001a1b  jmp     short loc_180001A30
0x180001a1d  mov     edi, [rsp+108h+arg_8]
0x180001a24  mov     rsi, [rsp+108h+arg_0]
0x180001a2c  mov     ebx, [rsp+108h+var_E8]
0x180001a30  mov     rax, cs:_pRawDllMain
0x180001a37  test    rax, rax
0x180001a3a  jz      short loc_180001A5F
0x180001a3c  xor     r8d, r8d
0x180001a3f  xor     edx, edx
0x180001a41  mov     rcx, rsi
0x180001a44  call    cs:__guard_dispatch_icall_fptr
0x180001a4a  jmp     short loc_180001A5F
0x180001a4c  mov     edi, [rsp+108h+arg_8]
0x180001a53  mov     rsi, [rsp+108h+arg_0]
0x180001a5b  mov     ebx, [rsp+108h+var_E8]
0x180001a5f  test    edi, edi
0x180001a61  jz      short loc_180001A68
0x180001a63  cmp     edi, 3
0x180001a66  jnz     short loc_180001AD4
0x180001a68  mov     r8, [rsp+108h+lpvReserved]
0x180001a70  mov     edx, edi
0x180001a72  mov     rcx, rsi
0x180001a75  call    _CRT_INIT
0x180001a7a  mov     ebx, eax
0x180001a7c  mov     [rsp+108h+var_E8], eax
0x180001a80  jmp     short loc_180001A97
0x180001a82  xor     ebx, ebx
0x180001a84  mov     [rsp+108h+var_E8], ebx
0x180001a88  mov     edi, [rsp+108h+arg_8]
0x180001a8f  mov     rsi, [rsp+108h+arg_0]
0x180001a97  mov     rax, cs:_pRawDllMain
0x180001a9e  test    rax, rax
0x180001aa1  jz      short loc_180001AD4
0x180001aa3  cmp     cs:dword_18003B644, 0
0x180001aaa  jz      short loc_180001AD4
0x180001aac  mov     r8, [rsp+108h+lpvReserved]
0x180001ab4  mov     edx, edi
0x180001ab6  mov     rcx, rsi
0x180001ab9  call    cs:__guard_dispatch_icall_fptr
0x180001abf  mov     ebx, eax
0x180001ac1  mov     [rsp+108h+var_E8], eax
0x180001ac5  jmp     short loc_180001AD4
0x180001ac7  xor     ebx, ebx
0x180001ac9  mov     [rsp+108h+var_E8], ebx
0x180001acd  mov     edi, [rsp+108h+arg_8]
0x180001ad4  cmp     edi, 1
0x180001ad7  ja      short loc_180001AE3
0x180001ad9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ae3  mov     eax, ebx
0x180001ae5  add     rsp, 0F0h
0x180001aec  pop     rdi
0x180001aed  pop     rsi
0x180001aee  pop     rbx
0x180001aef  retn
0x18002d0b3  push    rbp
0x18002d0b5  sub     rsp, 20h
0x18002d0b9  mov     rbp, rdx
0x18002d0bc  mov     rax, [rcx]
0x18002d0bf  mov     edx, [rax]
0x18002d0c1  mov     [rbp+0A8h], rcx
0x18002d0c8  mov     [rbp+28h], edx
0x18002d0cb  mov     eax, [rbp+28h]
0x18002d0ce  cmp     eax, 0E06D7363h
0x18002d0d3  jnz     short loc_18002D0E9
0x18002d0d5  mov     rdx, [rbp+0A8h]
0x18002d0dc  mov     ecx, [rbp+28h]
0x18002d0df  call    _XcptFilter_0
0x18002d0e4  mov     [rbp+30h], eax
0x18002d0e7  jmp     short loc_18002D0F0
0x18002d0e9  mov     dword ptr [rbp+30h], 0
0x18002d0f0  mov     eax, [rbp+30h]
0x18002d0f3  add     rsp, 20h
0x18002d0f7  pop     rbp
0x18002d0f8  retn
0x18002d0fa  push    rbp
0x18002d0fc  sub     rsp, 20h
0x18002d100  mov     rbp, rdx
0x18002d103  mov     rax, [rcx]
0x18002d106  mov     edx, [rax]
0x18002d108  mov     [rbp+0B0h], rcx
0x18002d10f  mov     [rbp+38h], edx
0x18002d112  mov     eax, [rbp+38h]
0x18002d115  cmp     eax, 0E06D7363h
0x18002d11a  jnz     short loc_18002D130
0x18002d11c  mov     rdx, [rbp+0B0h]
0x18002d123  mov     ecx, [rbp+38h]
0x18002d126  call    _XcptFilter_0
0x18002d12b  mov     [rbp+40h], eax
0x18002d12e  jmp     short loc_18002D137
0x18002d130  mov     dword ptr [rbp+40h], 0
0x18002d137  mov     eax, [rbp+40h]
0x18002d13a  add     rsp, 20h
0x18002d13e  pop     rbp
0x18002d13f  retn
0x18002d141  push    rbp
0x18002d143  sub     rsp, 20h
0x18002d147  mov     rbp, rdx
0x18002d14a  mov     rax, [rcx]
0x18002d14d  mov     edx, [rax]
0x18002d14f  mov     [rbp+0B8h], rcx
0x18002d156  mov     [rbp+48h], edx
0x18002d159  mov     eax, [rbp+48h]
0x18002d15c  cmp     eax, 0E06D7363h
0x18002d161  jnz     short loc_18002D177
0x18002d163  mov     rdx, [rbp+0B8h]
0x18002d16a  mov     ecx, [rbp+48h]
0x18002d16d  call    _XcptFilter_0
0x18002d172  mov     [rbp+50h], eax
0x18002d175  jmp     short loc_18002D17E
0x18002d177  mov     dword ptr [rbp+50h], 0
0x18002d17e  mov     eax, [rbp+50h]
0x18002d181  add     rsp, 20h
0x18002d185  pop     rbp
0x18002d186  retn
0x18002d188  push    rbp
0x18002d18a  sub     rsp, 20h
0x18002d18e  mov     rbp, rdx
0x18002d191  mov     rax, [rcx]
0x18002d194  mov     edx, [rax]
0x18002d196  mov     [rbp+0C0h], rcx
0x18002d19d  mov     [rbp+58h], edx
0x18002d1a0  mov     eax, [rbp+58h]
0x18002d1a3  cmp     eax, 0E06D7363h
0x18002d1a8  jnz     short loc_18002D1BE
0x18002d1aa  mov     rdx, [rbp+0C0h]
0x18002d1b1  mov     ecx, [rbp+58h]
0x18002d1b4  call    _XcptFilter_0
0x18002d1b9  mov     [rbp+60h], eax
0x18002d1bc  jmp     short loc_18002D1C5
0x18002d1be  mov     dword ptr [rbp+60h], 0
0x18002d1c5  mov     eax, [rbp+60h]
0x18002d1c8  add     rsp, 20h
0x18002d1cc  pop     rbp
0x18002d1cd  retn
0x18002d1cf  push    rbp
0x18002d1d1  sub     rsp, 20h
0x18002d1d5  mov     rbp, rdx
0x18002d1d8  mov     rax, [rcx]
0x18002d1db  mov     edx, [rax]
0x18002d1dd  mov     [rbp+0C8h], rcx
0x18002d1e4  mov     [rbp+68h], edx
0x18002d1e7  mov     eax, [rbp+68h]
0x18002d1ea  cmp     eax, 0E06D7363h
0x18002d1ef  jnz     short loc_18002D205
0x18002d1f1  mov     rdx, [rbp+0C8h]
0x18002d1f8  mov     ecx, [rbp+68h]
0x18002d1fb  call    _XcptFilter_0
0x18002d200  mov     [rbp+70h], eax
0x18002d203  jmp     short loc_18002D20C
0x18002d205  mov     dword ptr [rbp+70h], 0
0x18002d20c  mov     eax, [rbp+70h]
0x18002d20f  add     rsp, 20h
0x18002d213  pop     rbp
0x18002d214  retn
0x18002d216  push    rbp
0x18002d218  sub     rsp, 20h
0x18002d21c  mov     rbp, rdx
0x18002d21f  mov     rax, [rcx]
0x18002d222  mov     edx, [rax]
0x18002d224  mov     [rbp+0D0h], rcx
0x18002d22b  mov     [rbp+78h], edx
0x18002d22e  mov     eax, [rbp+78h]
0x18002d231  cmp     eax, 0E06D7363h
0x18002d236  jnz     short loc_18002D24F
0x18002d238  mov     rdx, [rbp+0D0h]
0x18002d23f  mov     ecx, [rbp+78h]
0x18002d242  call    _XcptFilter_0
0x18002d247  mov     [rbp+80h], eax
0x18002d24d  jmp     short loc_18002D259
0x18002d24f  mov     dword ptr [rbp+80h], 0
0x18002d259  mov     eax, [rbp+80h]
0x18002d25f  add     rsp, 20h
0x18002d263  pop     rbp
0x18002d264  retn
0x18002d266  push    rbp
0x18002d268  sub     rsp, 20h
0x18002d26c  mov     rbp, rdx
0x18002d26f  mov     rax, [rcx]
0x18002d272  mov     edx, [rax]
0x18002d274  mov     [rbp+0D8h], rcx
0x18002d27b  mov     [rbp+88h], edx
0x18002d281  mov     eax, [rbp+88h]
0x18002d287  cmp     eax, 0E06D7363h
0x18002d28c  jnz     short loc_18002D2A8
0x18002d28e  mov     rdx, [rbp+0D8h]
0x18002d295  mov     ecx, [rbp+88h]
0x18002d29b  call    _XcptFilter_0
0x18002d2a0  mov     [rbp+90h], eax
0x18002d2a6  jmp     short loc_18002D2B2
0x18002d2a8  mov     dword ptr [rbp+90h], 0
0x18002d2b2  mov     eax, [rbp+90h]
0x18002d2b8  add     rsp, 20h
0x18002d2bc  pop     rbp
0x18002d2bd  retn
0x18002d2bf  push    rbp
0x18002d2c1  sub     rsp, 20h
0x18002d2c5  mov     rbp, rdx
0x18002d2c8  mov     rax, [rcx]
0x18002d2cb  mov     edx, [rax]
0x18002d2cd  mov     [rbp+0E0h], rcx
0x18002d2d4  mov     [rbp+98h], edx
0x18002d2da  mov     eax, [rbp+98h]
0x18002d2e0  cmp     eax, 0E06D7363h
0x18002d2e5  jnz     short loc_18002D301
0x18002d2e7  mov     rdx, [rbp+0E0h]
0x18002d2ee  mov     ecx, [rbp+98h]
0x18002d2f4  call    _XcptFilter_0
0x18002d2f9  mov     [rbp+0A0h], eax
0x18002d2ff  jmp     short loc_18002D30B
0x18002d301  mov     dword ptr [rbp+0A0h], 0
0x18002d30b  mov     eax, [rbp+0A0h]
0x18002d311  add     rsp, 20h
0x18002d315  pop     rbp
0x18002d316  retn
0x18002d318  push    rbp
0x18002d31a  sub     rsp, 20h
0x18002d31e  mov     rbp, rdx
0x18002d321  cmp     dword ptr [rbp+118h], 1
0x18002d328  ja      short loc_18002D334
0x18002d32a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
