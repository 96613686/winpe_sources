# __DllMainCRTStartup

- ea: `0x180013ad4`
- end: `0x180013ce0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013a90`

## callees

- `0x18000bc30`
- `0x180013860`
- `0x180013ad4`
- `0x180013df4`
- `0x18001af00`

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
  if ( (_DWORD)fdwReason || dword_18002E420 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002E424 = 1;
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
            if ( dword_18002E424 )
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
0x180013ad4  mov     [rsp+lpvReserved], r8
0x180013ad9  mov     [rsp+arg_8], edx
0x180013add  mov     [rsp+arg_0], rcx
0x180013ae2  push    rbx
0x180013ae3  push    rsi
0x180013ae4  push    rdi
0x180013ae5  sub     rsp, 0F0h
0x180013aec  mov     edi, edx
0x180013aee  mov     rsi, rcx
0x180013af1  mov     ebx, 1
0x180013af6  cmp     edx, ebx
0x180013af8  ja      short loc_180013B00
0x180013afa  mov     cs:__native_dllmain_reason, edx
0x180013b00  test    edx, edx
0x180013b02  jnz     short loc_180013B17
0x180013b04  cmp     cs:dword_18002E420, edx
0x180013b0a  jnz     short loc_180013B17
0x180013b0c  xor     ebx, ebx
0x180013b0e  mov     [rsp+108h+var_E8], ebx
0x180013b12  jmp     loc_180013CC4
0x180013b17  lea     eax, [rdx-1]
0x180013b1a  cmp     eax, 1
0x180013b1d  ja      loc_180013BA4
0x180013b23  mov     rax, cs:_pRawDllMain
0x180013b2a  test    rax, rax
0x180013b2d  jz      short loc_180013B65
0x180013b2f  cmp     edx, 1
0x180013b32  jnz     short loc_180013B3A
0x180013b34  mov     cs:dword_18002E424, edx
0x180013b3a  mov     r8, [rsp+108h+lpvReserved]
0x180013b42  call    cs:__guard_dispatch_icall_fptr
0x180013b48  mov     ebx, eax
0x180013b4a  mov     [rsp+108h+var_E8], eax
0x180013b4e  jmp     short loc_180013B65
0x180013b50  xor     ebx, ebx
0x180013b52  mov     [rsp+108h+var_E8], ebx
0x180013b56  mov     edi, [rsp+108h+arg_8]
0x180013b5d  mov     rsi, [rsp+108h+arg_0]
0x180013b65  test    ebx, ebx
0x180013b67  jz      loc_180013CC4
0x180013b6d  mov     r8, [rsp+108h+lpvReserved]
0x180013b75  mov     edx, edi
0x180013b77  mov     rcx, rsi
0x180013b7a  call    _CRT_INIT
0x180013b7f  mov     ebx, eax
0x180013b81  mov     [rsp+108h+var_E8], eax
0x180013b85  jmp     short loc_180013B9C
0x180013b87  xor     ebx, ebx
0x180013b89  mov     [rsp+108h+var_E8], ebx
0x180013b8d  mov     edi, [rsp+108h+arg_8]
0x180013b94  mov     rsi, [rsp+108h+arg_0]
0x180013b9c  test    ebx, ebx
0x180013b9e  jz      loc_180013CC4
0x180013ba4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180013bac  mov     edx, edi; fdwReason
0x180013bae  mov     rcx, rsi; hinstDLL
0x180013bb1  call    DllMain
0x180013bb6  mov     ebx, eax
0x180013bb8  mov     [rsp+108h+var_E8], eax
0x180013bbc  jmp     short loc_180013BD3
0x180013bbe  xor     ebx, ebx
0x180013bc0  mov     [rsp+108h+var_E8], ebx
0x180013bc4  mov     edi, [rsp+108h+arg_8]
0x180013bcb  mov     rsi, [rsp+108h+arg_0]
0x180013bd3  cmp     edi, 1
0x180013bd6  jnz     short loc_180013C4F
0x180013bd8  test    ebx, ebx
0x180013bda  jnz     short loc_180013C4F
0x180013bdc  xor     r8d, r8d; lpvReserved
0x180013bdf  xor     edx, edx; fdwReason
0x180013be1  mov     rcx, rsi; hinstDLL
0x180013be4  call    DllMain
0x180013be9  jmp     short loc_180013BFE
0x180013beb  mov     edi, [rsp+108h+arg_8]
0x180013bf2  mov     rsi, [rsp+108h+arg_0]
0x180013bfa  mov     ebx, [rsp+108h+var_E8]
0x180013bfe  xor     r8d, r8d
0x180013c01  xor     edx, edx
0x180013c03  mov     rcx, rsi
0x180013c06  call    _CRT_INIT
0x180013c0b  jmp     short loc_180013C20
0x180013c0d  mov     edi, [rsp+108h+arg_8]
0x180013c14  mov     rsi, [rsp+108h+arg_0]
0x180013c1c  mov     ebx, [rsp+108h+var_E8]
0x180013c20  mov     rax, cs:_pRawDllMain
0x180013c27  test    rax, rax
0x180013c2a  jz      short loc_180013C4F
0x180013c2c  xor     r8d, r8d
0x180013c2f  xor     edx, edx
0x180013c31  mov     rcx, rsi
0x180013c34  call    cs:__guard_dispatch_icall_fptr
0x180013c3a  jmp     short loc_180013C4F
0x180013c3c  mov     edi, [rsp+108h+arg_8]
0x180013c43  mov     rsi, [rsp+108h+arg_0]
0x180013c4b  mov     ebx, [rsp+108h+var_E8]
0x180013c4f  test    edi, edi
0x180013c51  jz      short loc_180013C58
0x180013c53  cmp     edi, 3
0x180013c56  jnz     short loc_180013CC4
0x180013c58  mov     r8, [rsp+108h+lpvReserved]
0x180013c60  mov     edx, edi
0x180013c62  mov     rcx, rsi
0x180013c65  call    _CRT_INIT
0x180013c6a  mov     ebx, eax
0x180013c6c  mov     [rsp+108h+var_E8], eax
0x180013c70  jmp     short loc_180013C87
0x180013c72  xor     ebx, ebx
0x180013c74  mov     [rsp+108h+var_E8], ebx
0x180013c78  mov     edi, [rsp+108h+arg_8]
0x180013c7f  mov     rsi, [rsp+108h+arg_0]
0x180013c87  mov     rax, cs:_pRawDllMain
0x180013c8e  test    rax, rax
0x180013c91  jz      short loc_180013CC4
0x180013c93  cmp     cs:dword_18002E424, 0
0x180013c9a  jz      short loc_180013CC4
0x180013c9c  mov     r8, [rsp+108h+lpvReserved]
0x180013ca4  mov     edx, edi
0x180013ca6  mov     rcx, rsi
0x180013ca9  call    cs:__guard_dispatch_icall_fptr
0x180013caf  mov     ebx, eax
0x180013cb1  mov     [rsp+108h+var_E8], eax
0x180013cb5  jmp     short loc_180013CC4
0x180013cb7  xor     ebx, ebx
0x180013cb9  mov     [rsp+108h+var_E8], ebx
0x180013cbd  mov     edi, [rsp+108h+arg_8]
0x180013cc4  cmp     edi, 1
0x180013cc7  ja      short loc_180013CD3
0x180013cc9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180013cd3  mov     eax, ebx
0x180013cd5  add     rsp, 0F0h
0x180013cdc  pop     rdi
0x180013cdd  pop     rsi
0x180013cde  pop     rbx
0x180013cdf  retn
0x18001b780  push    rbp
0x18001b782  sub     rsp, 20h
0x18001b786  mov     rbp, rdx
0x18001b789  mov     rax, [rcx]
0x18001b78c  mov     edx, [rax]
0x18001b78e  mov     [rbp+0A8h], rcx
0x18001b795  mov     [rbp+28h], edx
0x18001b798  mov     eax, [rbp+28h]
0x18001b79b  cmp     eax, 0E06D7363h
0x18001b7a0  jnz     short loc_18001B7B6
0x18001b7a2  mov     rdx, [rbp+0A8h]
0x18001b7a9  mov     ecx, [rbp+28h]
0x18001b7ac  call    _XcptFilter_0
0x18001b7b1  mov     [rbp+30h], eax
0x18001b7b4  jmp     short loc_18001B7BD
0x18001b7b6  mov     dword ptr [rbp+30h], 0
0x18001b7bd  mov     eax, [rbp+30h]
0x18001b7c0  add     rsp, 20h
0x18001b7c4  pop     rbp
0x18001b7c5  retn
0x18001b7c7  push    rbp
0x18001b7c9  sub     rsp, 20h
0x18001b7cd  mov     rbp, rdx
0x18001b7d0  mov     rax, [rcx]
0x18001b7d3  mov     edx, [rax]
0x18001b7d5  mov     [rbp+0B0h], rcx
0x18001b7dc  mov     [rbp+38h], edx
0x18001b7df  mov     eax, [rbp+38h]
0x18001b7e2  cmp     eax, 0E06D7363h
0x18001b7e7  jnz     short loc_18001B7FD
0x18001b7e9  mov     rdx, [rbp+0B0h]
0x18001b7f0  mov     ecx, [rbp+38h]
0x18001b7f3  call    _XcptFilter_0
0x18001b7f8  mov     [rbp+40h], eax
0x18001b7fb  jmp     short loc_18001B804
0x18001b7fd  mov     dword ptr [rbp+40h], 0
0x18001b804  mov     eax, [rbp+40h]
0x18001b807  add     rsp, 20h
0x18001b80b  pop     rbp
0x18001b80c  retn
0x18001b80e  push    rbp
0x18001b810  sub     rsp, 20h
0x18001b814  mov     rbp, rdx
0x18001b817  mov     rax, [rcx]
0x18001b81a  mov     edx, [rax]
0x18001b81c  mov     [rbp+0B8h], rcx
0x18001b823  mov     [rbp+48h], edx
0x18001b826  mov     eax, [rbp+48h]
0x18001b829  cmp     eax, 0E06D7363h
0x18001b82e  jnz     short loc_18001B844
0x18001b830  mov     rdx, [rbp+0B8h]
0x18001b837  mov     ecx, [rbp+48h]
0x18001b83a  call    _XcptFilter_0
0x18001b83f  mov     [rbp+50h], eax
0x18001b842  jmp     short loc_18001B84B
0x18001b844  mov     dword ptr [rbp+50h], 0
0x18001b84b  mov     eax, [rbp+50h]
0x18001b84e  add     rsp, 20h
0x18001b852  pop     rbp
0x18001b853  retn
0x18001b855  push    rbp
0x18001b857  sub     rsp, 20h
0x18001b85b  mov     rbp, rdx
0x18001b85e  mov     rax, [rcx]
0x18001b861  mov     edx, [rax]
0x18001b863  mov     [rbp+0C0h], rcx
0x18001b86a  mov     [rbp+58h], edx
0x18001b86d  mov     eax, [rbp+58h]
0x18001b870  cmp     eax, 0E06D7363h
0x18001b875  jnz     short loc_18001B88B
0x18001b877  mov     rdx, [rbp+0C0h]
0x18001b87e  mov     ecx, [rbp+58h]
0x18001b881  call    _XcptFilter_0
0x18001b886  mov     [rbp+60h], eax
0x18001b889  jmp     short loc_18001B892
0x18001b88b  mov     dword ptr [rbp+60h], 0
0x18001b892  mov     eax, [rbp+60h]
0x18001b895  add     rsp, 20h
0x18001b899  pop     rbp
0x18001b89a  retn
0x18001b89c  push    rbp
0x18001b89e  sub     rsp, 20h
0x18001b8a2  mov     rbp, rdx
0x18001b8a5  mov     rax, [rcx]
0x18001b8a8  mov     edx, [rax]
0x18001b8aa  mov     [rbp+0C8h], rcx
0x18001b8b1  mov     [rbp+68h], edx
0x18001b8b4  mov     eax, [rbp+68h]
0x18001b8b7  cmp     eax, 0E06D7363h
0x18001b8bc  jnz     short loc_18001B8D2
0x18001b8be  mov     rdx, [rbp+0C8h]
0x18001b8c5  mov     ecx, [rbp+68h]
0x18001b8c8  call    _XcptFilter_0
0x18001b8cd  mov     [rbp+70h], eax
0x18001b8d0  jmp     short loc_18001B8D9
0x18001b8d2  mov     dword ptr [rbp+70h], 0
0x18001b8d9  mov     eax, [rbp+70h]
0x18001b8dc  add     rsp, 20h
0x18001b8e0  pop     rbp
0x18001b8e1  retn
0x18001b8e3  push    rbp
0x18001b8e5  sub     rsp, 20h
0x18001b8e9  mov     rbp, rdx
0x18001b8ec  mov     rax, [rcx]
0x18001b8ef  mov     edx, [rax]
0x18001b8f1  mov     [rbp+0D0h], rcx
0x18001b8f8  mov     [rbp+78h], edx
0x18001b8fb  mov     eax, [rbp+78h]
0x18001b8fe  cmp     eax, 0E06D7363h
0x18001b903  jnz     short loc_18001B91C
0x18001b905  mov     rdx, [rbp+0D0h]
0x18001b90c  mov     ecx, [rbp+78h]
0x18001b90f  call    _XcptFilter_0
0x18001b914  mov     [rbp+80h], eax
0x18001b91a  jmp     short loc_18001B926
0x18001b91c  mov     dword ptr [rbp+80h], 0
0x18001b926  mov     eax, [rbp+80h]
0x18001b92c  add     rsp, 20h
0x18001b930  pop     rbp
0x18001b931  retn
0x18001b933  push    rbp
0x18001b935  sub     rsp, 20h
0x18001b939  mov     rbp, rdx
0x18001b93c  mov     rax, [rcx]
0x18001b93f  mov     edx, [rax]
0x18001b941  mov     [rbp+0D8h], rcx
0x18001b948  mov     [rbp+88h], edx
0x18001b94e  mov     eax, [rbp+88h]
0x18001b954  cmp     eax, 0E06D7363h
0x18001b959  jnz     short loc_18001B975
0x18001b95b  mov     rdx, [rbp+0D8h]
0x18001b962  mov     ecx, [rbp+88h]
0x18001b968  call    _XcptFilter_0
0x18001b96d  mov     [rbp+90h], eax
0x18001b973  jmp     short loc_18001B97F
0x18001b975  mov     dword ptr [rbp+90h], 0
0x18001b97f  mov     eax, [rbp+90h]
0x18001b985  add     rsp, 20h
0x18001b989  pop     rbp
0x18001b98a  retn
0x18001b98c  push    rbp
0x18001b98e  sub     rsp, 20h
0x18001b992  mov     rbp, rdx
0x18001b995  mov     rax, [rcx]
0x18001b998  mov     edx, [rax]
0x18001b99a  mov     [rbp+0E0h], rcx
0x18001b9a1  mov     [rbp+98h], edx
0x18001b9a7  mov     eax, [rbp+98h]
0x18001b9ad  cmp     eax, 0E06D7363h
0x18001b9b2  jnz     short loc_18001B9CE
0x18001b9b4  mov     rdx, [rbp+0E0h]
0x18001b9bb  mov     ecx, [rbp+98h]
0x18001b9c1  call    _XcptFilter_0
0x18001b9c6  mov     [rbp+0A0h], eax
0x18001b9cc  jmp     short loc_18001B9D8
0x18001b9ce  mov     dword ptr [rbp+0A0h], 0
0x18001b9d8  mov     eax, [rbp+0A0h]
0x18001b9de  add     rsp, 20h
0x18001b9e2  pop     rbp
0x18001b9e3  retn
0x18001b9e5  push    rbp
0x18001b9e7  sub     rsp, 20h
0x18001b9eb  mov     rbp, rdx
0x18001b9ee  cmp     dword ptr [rbp+118h], 1
0x18001b9f5  ja      short loc_18001BA01
0x18001b9f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
