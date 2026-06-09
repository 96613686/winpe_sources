# __DllMainCRTStartup

- ea: `0x180001b84`
- end: `0x180001d90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001b40`

## callees

- `0x180001910`
- `0x180001b84`
- `0x180001e9d`
- `0x180013280`
- `0x180013880`

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
  if ( (_DWORD)fdwReason || dword_18001A4C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001A4C4 = 1;
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
            if ( dword_18001A4C4 )
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
0x180001b84  mov     [rsp+lpvReserved], r8
0x180001b89  mov     [rsp+arg_8], edx
0x180001b8d  mov     [rsp+arg_0], rcx
0x180001b92  push    rbx
0x180001b93  push    rsi
0x180001b94  push    rdi
0x180001b95  sub     rsp, 0F0h
0x180001b9c  mov     edi, edx
0x180001b9e  mov     rsi, rcx
0x180001ba1  mov     ebx, 1
0x180001ba6  cmp     edx, ebx
0x180001ba8  ja      short loc_180001BB0
0x180001baa  mov     cs:__native_dllmain_reason, edx
0x180001bb0  test    edx, edx
0x180001bb2  jnz     short loc_180001BC7
0x180001bb4  cmp     cs:dword_18001A4C0, edx
0x180001bba  jnz     short loc_180001BC7
0x180001bbc  xor     ebx, ebx
0x180001bbe  mov     [rsp+108h+var_E8], ebx
0x180001bc2  jmp     loc_180001D74
0x180001bc7  lea     eax, [rdx-1]
0x180001bca  cmp     eax, 1
0x180001bcd  ja      loc_180001C54
0x180001bd3  mov     rax, cs:_pRawDllMain
0x180001bda  test    rax, rax
0x180001bdd  jz      short loc_180001C15
0x180001bdf  cmp     edx, 1
0x180001be2  jnz     short loc_180001BEA
0x180001be4  mov     cs:dword_18001A4C4, edx
0x180001bea  mov     r8, [rsp+108h+lpvReserved]
0x180001bf2  call    cs:__guard_dispatch_icall_fptr
0x180001bf8  mov     ebx, eax
0x180001bfa  mov     [rsp+108h+var_E8], eax
0x180001bfe  jmp     short loc_180001C15
0x180001c00  xor     ebx, ebx
0x180001c02  mov     [rsp+108h+var_E8], ebx
0x180001c06  mov     edi, [rsp+108h+arg_8]
0x180001c0d  mov     rsi, [rsp+108h+arg_0]
0x180001c15  test    ebx, ebx
0x180001c17  jz      loc_180001D74
0x180001c1d  mov     r8, [rsp+108h+lpvReserved]
0x180001c25  mov     edx, edi
0x180001c27  mov     rcx, rsi
0x180001c2a  call    _CRT_INIT
0x180001c2f  mov     ebx, eax
0x180001c31  mov     [rsp+108h+var_E8], eax
0x180001c35  jmp     short loc_180001C4C
0x180001c37  xor     ebx, ebx
0x180001c39  mov     [rsp+108h+var_E8], ebx
0x180001c3d  mov     edi, [rsp+108h+arg_8]
0x180001c44  mov     rsi, [rsp+108h+arg_0]
0x180001c4c  test    ebx, ebx
0x180001c4e  jz      loc_180001D74
0x180001c54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001c5c  mov     edx, edi; fdwReason
0x180001c5e  mov     rcx, rsi; hinstDLL
0x180001c61  call    DllMain
0x180001c66  mov     ebx, eax
0x180001c68  mov     [rsp+108h+var_E8], eax
0x180001c6c  jmp     short loc_180001C83
0x180001c6e  xor     ebx, ebx
0x180001c70  mov     [rsp+108h+var_E8], ebx
0x180001c74  mov     edi, [rsp+108h+arg_8]
0x180001c7b  mov     rsi, [rsp+108h+arg_0]
0x180001c83  cmp     edi, 1
0x180001c86  jnz     short loc_180001CFF
0x180001c88  test    ebx, ebx
0x180001c8a  jnz     short loc_180001CFF
0x180001c8c  xor     r8d, r8d; lpvReserved
0x180001c8f  xor     edx, edx; fdwReason
0x180001c91  mov     rcx, rsi; hinstDLL
0x180001c94  call    DllMain
0x180001c99  jmp     short loc_180001CAE
0x180001c9b  mov     edi, [rsp+108h+arg_8]
0x180001ca2  mov     rsi, [rsp+108h+arg_0]
0x180001caa  mov     ebx, [rsp+108h+var_E8]
0x180001cae  xor     r8d, r8d
0x180001cb1  xor     edx, edx
0x180001cb3  mov     rcx, rsi
0x180001cb6  call    _CRT_INIT
0x180001cbb  jmp     short loc_180001CD0
0x180001cbd  mov     edi, [rsp+108h+arg_8]
0x180001cc4  mov     rsi, [rsp+108h+arg_0]
0x180001ccc  mov     ebx, [rsp+108h+var_E8]
0x180001cd0  mov     rax, cs:_pRawDllMain
0x180001cd7  test    rax, rax
0x180001cda  jz      short loc_180001CFF
0x180001cdc  xor     r8d, r8d
0x180001cdf  xor     edx, edx
0x180001ce1  mov     rcx, rsi
0x180001ce4  call    cs:__guard_dispatch_icall_fptr
0x180001cea  jmp     short loc_180001CFF
0x180001cec  mov     edi, [rsp+108h+arg_8]
0x180001cf3  mov     rsi, [rsp+108h+arg_0]
0x180001cfb  mov     ebx, [rsp+108h+var_E8]
0x180001cff  test    edi, edi
0x180001d01  jz      short loc_180001D08
0x180001d03  cmp     edi, 3
0x180001d06  jnz     short loc_180001D74
0x180001d08  mov     r8, [rsp+108h+lpvReserved]
0x180001d10  mov     edx, edi
0x180001d12  mov     rcx, rsi
0x180001d15  call    _CRT_INIT
0x180001d1a  mov     ebx, eax
0x180001d1c  mov     [rsp+108h+var_E8], eax
0x180001d20  jmp     short loc_180001D37
0x180001d22  xor     ebx, ebx
0x180001d24  mov     [rsp+108h+var_E8], ebx
0x180001d28  mov     edi, [rsp+108h+arg_8]
0x180001d2f  mov     rsi, [rsp+108h+arg_0]
0x180001d37  mov     rax, cs:_pRawDllMain
0x180001d3e  test    rax, rax
0x180001d41  jz      short loc_180001D74
0x180001d43  cmp     cs:dword_18001A4C4, 0
0x180001d4a  jz      short loc_180001D74
0x180001d4c  mov     r8, [rsp+108h+lpvReserved]
0x180001d54  mov     edx, edi
0x180001d56  mov     rcx, rsi
0x180001d59  call    cs:__guard_dispatch_icall_fptr
0x180001d5f  mov     ebx, eax
0x180001d61  mov     [rsp+108h+var_E8], eax
0x180001d65  jmp     short loc_180001D74
0x180001d67  xor     ebx, ebx
0x180001d69  mov     [rsp+108h+var_E8], ebx
0x180001d6d  mov     edi, [rsp+108h+arg_8]
0x180001d74  cmp     edi, 1
0x180001d77  ja      short loc_180001D83
0x180001d79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001d83  mov     eax, ebx
0x180001d85  add     rsp, 0F0h
0x180001d8c  pop     rdi
0x180001d8d  pop     rsi
0x180001d8e  pop     rbx
0x180001d8f  retn
0x180013950  push    rbp
0x180013952  sub     rsp, 20h
0x180013956  mov     rbp, rdx
0x180013959  mov     rax, [rcx]
0x18001395c  mov     edx, [rax]
0x18001395e  mov     [rbp+0A8h], rcx
0x180013965  mov     [rbp+28h], edx
0x180013968  mov     eax, [rbp+28h]
0x18001396b  cmp     eax, 0E06D7363h
0x180013970  jnz     short loc_180013986
0x180013972  mov     rdx, [rbp+0A8h]
0x180013979  mov     ecx, [rbp+28h]
0x18001397c  call    _XcptFilter_0
0x180013981  mov     [rbp+30h], eax
0x180013984  jmp     short loc_18001398D
0x180013986  mov     dword ptr [rbp+30h], 0
0x18001398d  mov     eax, [rbp+30h]
0x180013990  add     rsp, 20h
0x180013994  pop     rbp
0x180013995  retn
0x180013997  push    rbp
0x180013999  sub     rsp, 20h
0x18001399d  mov     rbp, rdx
0x1800139a0  mov     rax, [rcx]
0x1800139a3  mov     edx, [rax]
0x1800139a5  mov     [rbp+0B0h], rcx
0x1800139ac  mov     [rbp+38h], edx
0x1800139af  mov     eax, [rbp+38h]
0x1800139b2  cmp     eax, 0E06D7363h
0x1800139b7  jnz     short loc_1800139CD
0x1800139b9  mov     rdx, [rbp+0B0h]
0x1800139c0  mov     ecx, [rbp+38h]
0x1800139c3  call    _XcptFilter_0
0x1800139c8  mov     [rbp+40h], eax
0x1800139cb  jmp     short loc_1800139D4
0x1800139cd  mov     dword ptr [rbp+40h], 0
0x1800139d4  mov     eax, [rbp+40h]
0x1800139d7  add     rsp, 20h
0x1800139db  pop     rbp
0x1800139dc  retn
0x1800139de  push    rbp
0x1800139e0  sub     rsp, 20h
0x1800139e4  mov     rbp, rdx
0x1800139e7  mov     rax, [rcx]
0x1800139ea  mov     edx, [rax]
0x1800139ec  mov     [rbp+0B8h], rcx
0x1800139f3  mov     [rbp+48h], edx
0x1800139f6  mov     eax, [rbp+48h]
0x1800139f9  cmp     eax, 0E06D7363h
0x1800139fe  jnz     short loc_180013A14
0x180013a00  mov     rdx, [rbp+0B8h]
0x180013a07  mov     ecx, [rbp+48h]
0x180013a0a  call    _XcptFilter_0
0x180013a0f  mov     [rbp+50h], eax
0x180013a12  jmp     short loc_180013A1B
0x180013a14  mov     dword ptr [rbp+50h], 0
0x180013a1b  mov     eax, [rbp+50h]
0x180013a1e  add     rsp, 20h
0x180013a22  pop     rbp
0x180013a23  retn
0x180013a25  push    rbp
0x180013a27  sub     rsp, 20h
0x180013a2b  mov     rbp, rdx
0x180013a2e  mov     rax, [rcx]
0x180013a31  mov     edx, [rax]
0x180013a33  mov     [rbp+0C0h], rcx
0x180013a3a  mov     [rbp+58h], edx
0x180013a3d  mov     eax, [rbp+58h]
0x180013a40  cmp     eax, 0E06D7363h
0x180013a45  jnz     short loc_180013A5B
0x180013a47  mov     rdx, [rbp+0C0h]
0x180013a4e  mov     ecx, [rbp+58h]
0x180013a51  call    _XcptFilter_0
0x180013a56  mov     [rbp+60h], eax
0x180013a59  jmp     short loc_180013A62
0x180013a5b  mov     dword ptr [rbp+60h], 0
0x180013a62  mov     eax, [rbp+60h]
0x180013a65  add     rsp, 20h
0x180013a69  pop     rbp
0x180013a6a  retn
0x180013a6c  push    rbp
0x180013a6e  sub     rsp, 20h
0x180013a72  mov     rbp, rdx
0x180013a75  mov     rax, [rcx]
0x180013a78  mov     edx, [rax]
0x180013a7a  mov     [rbp+0C8h], rcx
0x180013a81  mov     [rbp+68h], edx
0x180013a84  mov     eax, [rbp+68h]
0x180013a87  cmp     eax, 0E06D7363h
0x180013a8c  jnz     short loc_180013AA2
0x180013a8e  mov     rdx, [rbp+0C8h]
0x180013a95  mov     ecx, [rbp+68h]
0x180013a98  call    _XcptFilter_0
0x180013a9d  mov     [rbp+70h], eax
0x180013aa0  jmp     short loc_180013AA9
0x180013aa2  mov     dword ptr [rbp+70h], 0
0x180013aa9  mov     eax, [rbp+70h]
0x180013aac  add     rsp, 20h
0x180013ab0  pop     rbp
0x180013ab1  retn
0x180013ab3  push    rbp
0x180013ab5  sub     rsp, 20h
0x180013ab9  mov     rbp, rdx
0x180013abc  mov     rax, [rcx]
0x180013abf  mov     edx, [rax]
0x180013ac1  mov     [rbp+0D0h], rcx
0x180013ac8  mov     [rbp+78h], edx
0x180013acb  mov     eax, [rbp+78h]
0x180013ace  cmp     eax, 0E06D7363h
0x180013ad3  jnz     short loc_180013AEC
0x180013ad5  mov     rdx, [rbp+0D0h]
0x180013adc  mov     ecx, [rbp+78h]
0x180013adf  call    _XcptFilter_0
0x180013ae4  mov     [rbp+80h], eax
0x180013aea  jmp     short loc_180013AF6
0x180013aec  mov     dword ptr [rbp+80h], 0
0x180013af6  mov     eax, [rbp+80h]
0x180013afc  add     rsp, 20h
0x180013b00  pop     rbp
0x180013b01  retn
0x180013b03  push    rbp
0x180013b05  sub     rsp, 20h
0x180013b09  mov     rbp, rdx
0x180013b0c  mov     rax, [rcx]
0x180013b0f  mov     edx, [rax]
0x180013b11  mov     [rbp+0D8h], rcx
0x180013b18  mov     [rbp+88h], edx
0x180013b1e  mov     eax, [rbp+88h]
0x180013b24  cmp     eax, 0E06D7363h
0x180013b29  jnz     short loc_180013B45
0x180013b2b  mov     rdx, [rbp+0D8h]
0x180013b32  mov     ecx, [rbp+88h]
0x180013b38  call    _XcptFilter_0
0x180013b3d  mov     [rbp+90h], eax
0x180013b43  jmp     short loc_180013B4F
0x180013b45  mov     dword ptr [rbp+90h], 0
0x180013b4f  mov     eax, [rbp+90h]
0x180013b55  add     rsp, 20h
0x180013b59  pop     rbp
0x180013b5a  retn
0x180013b5c  push    rbp
0x180013b5e  sub     rsp, 20h
0x180013b62  mov     rbp, rdx
0x180013b65  mov     rax, [rcx]
0x180013b68  mov     edx, [rax]
0x180013b6a  mov     [rbp+0E0h], rcx
0x180013b71  mov     [rbp+98h], edx
0x180013b77  mov     eax, [rbp+98h]
0x180013b7d  cmp     eax, 0E06D7363h
0x180013b82  jnz     short loc_180013B9E
0x180013b84  mov     rdx, [rbp+0E0h]
0x180013b8b  mov     ecx, [rbp+98h]
0x180013b91  call    _XcptFilter_0
0x180013b96  mov     [rbp+0A0h], eax
0x180013b9c  jmp     short loc_180013BA8
0x180013b9e  mov     dword ptr [rbp+0A0h], 0
0x180013ba8  mov     eax, [rbp+0A0h]
0x180013bae  add     rsp, 20h
0x180013bb2  pop     rbp
0x180013bb3  retn
0x180013bb5  push    rbp
0x180013bb7  sub     rsp, 20h
0x180013bbb  mov     rbp, rdx
0x180013bbe  cmp     dword ptr [rbp+118h], 1
0x180013bc5  ja      short loc_180013BD1
0x180013bc7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
