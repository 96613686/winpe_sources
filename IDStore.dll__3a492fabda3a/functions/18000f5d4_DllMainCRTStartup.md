# __DllMainCRTStartup

- ea: `0x18000f5d4`
- end: `0x18000f7e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f590`

## callees

- `0x18000f360`
- `0x18000f5d4`
- `0x18000fbae`
- `0x180012778`
- `0x1800197c0`

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
  if ( (_DWORD)fdwReason || dword_18002639C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800263A0 = 1;
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
            if ( dword_1800263A0 )
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
0x18000f5d4  mov     [rsp+lpvReserved], r8
0x18000f5d9  mov     [rsp+arg_8], edx
0x18000f5dd  mov     [rsp+arg_0], rcx
0x18000f5e2  push    rbx
0x18000f5e3  push    rsi
0x18000f5e4  push    rdi
0x18000f5e5  sub     rsp, 0F0h
0x18000f5ec  mov     edi, edx
0x18000f5ee  mov     rsi, rcx
0x18000f5f1  mov     ebx, 1
0x18000f5f6  cmp     edx, ebx
0x18000f5f8  ja      short loc_18000F600
0x18000f5fa  mov     cs:__native_dllmain_reason, edx
0x18000f600  test    edx, edx
0x18000f602  jnz     short loc_18000F617
0x18000f604  cmp     cs:dword_18002639C, edx
0x18000f60a  jnz     short loc_18000F617
0x18000f60c  xor     ebx, ebx
0x18000f60e  mov     [rsp+108h+var_E8], ebx
0x18000f612  jmp     loc_18000F7C4
0x18000f617  lea     eax, [rdx-1]
0x18000f61a  cmp     eax, 1
0x18000f61d  ja      loc_18000F6A4
0x18000f623  mov     rax, cs:_pRawDllMain
0x18000f62a  test    rax, rax
0x18000f62d  jz      short loc_18000F665
0x18000f62f  cmp     edx, 1
0x18000f632  jnz     short loc_18000F63A
0x18000f634  mov     cs:dword_1800263A0, edx
0x18000f63a  mov     r8, [rsp+108h+lpvReserved]
0x18000f642  call    cs:__guard_dispatch_icall_fptr
0x18000f648  mov     ebx, eax
0x18000f64a  mov     [rsp+108h+var_E8], eax
0x18000f64e  jmp     short loc_18000F665
0x18000f650  xor     ebx, ebx
0x18000f652  mov     [rsp+108h+var_E8], ebx
0x18000f656  mov     edi, [rsp+108h+arg_8]
0x18000f65d  mov     rsi, [rsp+108h+arg_0]
0x18000f665  test    ebx, ebx
0x18000f667  jz      loc_18000F7C4
0x18000f66d  mov     r8, [rsp+108h+lpvReserved]
0x18000f675  mov     edx, edi
0x18000f677  mov     rcx, rsi
0x18000f67a  call    _CRT_INIT
0x18000f67f  mov     ebx, eax
0x18000f681  mov     [rsp+108h+var_E8], eax
0x18000f685  jmp     short loc_18000F69C
0x18000f687  xor     ebx, ebx
0x18000f689  mov     [rsp+108h+var_E8], ebx
0x18000f68d  mov     edi, [rsp+108h+arg_8]
0x18000f694  mov     rsi, [rsp+108h+arg_0]
0x18000f69c  test    ebx, ebx
0x18000f69e  jz      loc_18000F7C4
0x18000f6a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000f6ac  mov     edx, edi; fdwReason
0x18000f6ae  mov     rcx, rsi; hinstDLL
0x18000f6b1  call    DllMain
0x18000f6b6  mov     ebx, eax
0x18000f6b8  mov     [rsp+108h+var_E8], eax
0x18000f6bc  jmp     short loc_18000F6D3
0x18000f6be  xor     ebx, ebx
0x18000f6c0  mov     [rsp+108h+var_E8], ebx
0x18000f6c4  mov     edi, [rsp+108h+arg_8]
0x18000f6cb  mov     rsi, [rsp+108h+arg_0]
0x18000f6d3  cmp     edi, 1
0x18000f6d6  jnz     short loc_18000F74F
0x18000f6d8  test    ebx, ebx
0x18000f6da  jnz     short loc_18000F74F
0x18000f6dc  xor     r8d, r8d; lpvReserved
0x18000f6df  xor     edx, edx; fdwReason
0x18000f6e1  mov     rcx, rsi; hinstDLL
0x18000f6e4  call    DllMain
0x18000f6e9  jmp     short loc_18000F6FE
0x18000f6eb  mov     edi, [rsp+108h+arg_8]
0x18000f6f2  mov     rsi, [rsp+108h+arg_0]
0x18000f6fa  mov     ebx, [rsp+108h+var_E8]
0x18000f6fe  xor     r8d, r8d
0x18000f701  xor     edx, edx
0x18000f703  mov     rcx, rsi
0x18000f706  call    _CRT_INIT
0x18000f70b  jmp     short loc_18000F720
0x18000f70d  mov     edi, [rsp+108h+arg_8]
0x18000f714  mov     rsi, [rsp+108h+arg_0]
0x18000f71c  mov     ebx, [rsp+108h+var_E8]
0x18000f720  mov     rax, cs:_pRawDllMain
0x18000f727  test    rax, rax
0x18000f72a  jz      short loc_18000F74F
0x18000f72c  xor     r8d, r8d
0x18000f72f  xor     edx, edx
0x18000f731  mov     rcx, rsi
0x18000f734  call    cs:__guard_dispatch_icall_fptr
0x18000f73a  jmp     short loc_18000F74F
0x18000f73c  mov     edi, [rsp+108h+arg_8]
0x18000f743  mov     rsi, [rsp+108h+arg_0]
0x18000f74b  mov     ebx, [rsp+108h+var_E8]
0x18000f74f  test    edi, edi
0x18000f751  jz      short loc_18000F758
0x18000f753  cmp     edi, 3
0x18000f756  jnz     short loc_18000F7C4
0x18000f758  mov     r8, [rsp+108h+lpvReserved]
0x18000f760  mov     edx, edi
0x18000f762  mov     rcx, rsi
0x18000f765  call    _CRT_INIT
0x18000f76a  mov     ebx, eax
0x18000f76c  mov     [rsp+108h+var_E8], eax
0x18000f770  jmp     short loc_18000F787
0x18000f772  xor     ebx, ebx
0x18000f774  mov     [rsp+108h+var_E8], ebx
0x18000f778  mov     edi, [rsp+108h+arg_8]
0x18000f77f  mov     rsi, [rsp+108h+arg_0]
0x18000f787  mov     rax, cs:_pRawDllMain
0x18000f78e  test    rax, rax
0x18000f791  jz      short loc_18000F7C4
0x18000f793  cmp     cs:dword_1800263A0, 0
0x18000f79a  jz      short loc_18000F7C4
0x18000f79c  mov     r8, [rsp+108h+lpvReserved]
0x18000f7a4  mov     edx, edi
0x18000f7a6  mov     rcx, rsi
0x18000f7a9  call    cs:__guard_dispatch_icall_fptr
0x18000f7af  mov     ebx, eax
0x18000f7b1  mov     [rsp+108h+var_E8], eax
0x18000f7b5  jmp     short loc_18000F7C4
0x18000f7b7  xor     ebx, ebx
0x18000f7b9  mov     [rsp+108h+var_E8], ebx
0x18000f7bd  mov     edi, [rsp+108h+arg_8]
0x18000f7c4  cmp     edi, 1
0x18000f7c7  ja      short loc_18000F7D3
0x18000f7c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000f7d3  mov     eax, ebx
0x18000f7d5  add     rsp, 0F0h
0x18000f7dc  pop     rdi
0x18000f7dd  pop     rsi
0x18000f7de  pop     rbx
0x18000f7df  retn
0x180019bf6  push    rbp
0x180019bf8  sub     rsp, 20h
0x180019bfc  mov     rbp, rdx
0x180019bff  mov     rax, [rcx]
0x180019c02  mov     edx, [rax]
0x180019c04  mov     [rbp+0A8h], rcx
0x180019c0b  mov     [rbp+28h], edx
0x180019c0e  mov     eax, [rbp+28h]
0x180019c11  cmp     eax, 0E06D7363h
0x180019c16  jnz     short loc_180019C2C
0x180019c18  mov     rdx, [rbp+0A8h]
0x180019c1f  mov     ecx, [rbp+28h]
0x180019c22  call    _XcptFilter_0
0x180019c27  mov     [rbp+30h], eax
0x180019c2a  jmp     short loc_180019C33
0x180019c2c  mov     dword ptr [rbp+30h], 0
0x180019c33  mov     eax, [rbp+30h]
0x180019c36  add     rsp, 20h
0x180019c3a  pop     rbp
0x180019c3b  retn
0x180019c3d  push    rbp
0x180019c3f  sub     rsp, 20h
0x180019c43  mov     rbp, rdx
0x180019c46  mov     rax, [rcx]
0x180019c49  mov     edx, [rax]
0x180019c4b  mov     [rbp+0B0h], rcx
0x180019c52  mov     [rbp+38h], edx
0x180019c55  mov     eax, [rbp+38h]
0x180019c58  cmp     eax, 0E06D7363h
0x180019c5d  jnz     short loc_180019C73
0x180019c5f  mov     rdx, [rbp+0B0h]
0x180019c66  mov     ecx, [rbp+38h]
0x180019c69  call    _XcptFilter_0
0x180019c6e  mov     [rbp+40h], eax
0x180019c71  jmp     short loc_180019C7A
0x180019c73  mov     dword ptr [rbp+40h], 0
0x180019c7a  mov     eax, [rbp+40h]
0x180019c7d  add     rsp, 20h
0x180019c81  pop     rbp
0x180019c82  retn
0x180019c84  push    rbp
0x180019c86  sub     rsp, 20h
0x180019c8a  mov     rbp, rdx
0x180019c8d  mov     rax, [rcx]
0x180019c90  mov     edx, [rax]
0x180019c92  mov     [rbp+0B8h], rcx
0x180019c99  mov     [rbp+48h], edx
0x180019c9c  mov     eax, [rbp+48h]
0x180019c9f  cmp     eax, 0E06D7363h
0x180019ca4  jnz     short loc_180019CBA
0x180019ca6  mov     rdx, [rbp+0B8h]
0x180019cad  mov     ecx, [rbp+48h]
0x180019cb0  call    _XcptFilter_0
0x180019cb5  mov     [rbp+50h], eax
0x180019cb8  jmp     short loc_180019CC1
0x180019cba  mov     dword ptr [rbp+50h], 0
0x180019cc1  mov     eax, [rbp+50h]
0x180019cc4  add     rsp, 20h
0x180019cc8  pop     rbp
0x180019cc9  retn
0x180019ccb  push    rbp
0x180019ccd  sub     rsp, 20h
0x180019cd1  mov     rbp, rdx
0x180019cd4  mov     rax, [rcx]
0x180019cd7  mov     edx, [rax]
0x180019cd9  mov     [rbp+0C0h], rcx
0x180019ce0  mov     [rbp+58h], edx
0x180019ce3  mov     eax, [rbp+58h]
0x180019ce6  cmp     eax, 0E06D7363h
0x180019ceb  jnz     short loc_180019D01
0x180019ced  mov     rdx, [rbp+0C0h]
0x180019cf4  mov     ecx, [rbp+58h]
0x180019cf7  call    _XcptFilter_0
0x180019cfc  mov     [rbp+60h], eax
0x180019cff  jmp     short loc_180019D08
0x180019d01  mov     dword ptr [rbp+60h], 0
0x180019d08  mov     eax, [rbp+60h]
0x180019d0b  add     rsp, 20h
0x180019d0f  pop     rbp
0x180019d10  retn
0x180019d12  push    rbp
0x180019d14  sub     rsp, 20h
0x180019d18  mov     rbp, rdx
0x180019d1b  mov     rax, [rcx]
0x180019d1e  mov     edx, [rax]
0x180019d20  mov     [rbp+0C8h], rcx
0x180019d27  mov     [rbp+68h], edx
0x180019d2a  mov     eax, [rbp+68h]
0x180019d2d  cmp     eax, 0E06D7363h
0x180019d32  jnz     short loc_180019D48
0x180019d34  mov     rdx, [rbp+0C8h]
0x180019d3b  mov     ecx, [rbp+68h]
0x180019d3e  call    _XcptFilter_0
0x180019d43  mov     [rbp+70h], eax
0x180019d46  jmp     short loc_180019D4F
0x180019d48  mov     dword ptr [rbp+70h], 0
0x180019d4f  mov     eax, [rbp+70h]
0x180019d52  add     rsp, 20h
0x180019d56  pop     rbp
0x180019d57  retn
0x180019d59  push    rbp
0x180019d5b  sub     rsp, 20h
0x180019d5f  mov     rbp, rdx
0x180019d62  mov     rax, [rcx]
0x180019d65  mov     edx, [rax]
0x180019d67  mov     [rbp+0D0h], rcx
0x180019d6e  mov     [rbp+78h], edx
0x180019d71  mov     eax, [rbp+78h]
0x180019d74  cmp     eax, 0E06D7363h
0x180019d79  jnz     short loc_180019D92
0x180019d7b  mov     rdx, [rbp+0D0h]
0x180019d82  mov     ecx, [rbp+78h]
0x180019d85  call    _XcptFilter_0
0x180019d8a  mov     [rbp+80h], eax
0x180019d90  jmp     short loc_180019D9C
0x180019d92  mov     dword ptr [rbp+80h], 0
0x180019d9c  mov     eax, [rbp+80h]
0x180019da2  add     rsp, 20h
0x180019da6  pop     rbp
0x180019da7  retn
0x180019da9  push    rbp
0x180019dab  sub     rsp, 20h
0x180019daf  mov     rbp, rdx
0x180019db2  mov     rax, [rcx]
0x180019db5  mov     edx, [rax]
0x180019db7  mov     [rbp+0D8h], rcx
0x180019dbe  mov     [rbp+88h], edx
0x180019dc4  mov     eax, [rbp+88h]
0x180019dca  cmp     eax, 0E06D7363h
0x180019dcf  jnz     short loc_180019DEB
0x180019dd1  mov     rdx, [rbp+0D8h]
0x180019dd8  mov     ecx, [rbp+88h]
0x180019dde  call    _XcptFilter_0
0x180019de3  mov     [rbp+90h], eax
0x180019de9  jmp     short loc_180019DF5
0x180019deb  mov     dword ptr [rbp+90h], 0
0x180019df5  mov     eax, [rbp+90h]
0x180019dfb  add     rsp, 20h
0x180019dff  pop     rbp
0x180019e00  retn
0x180019e02  push    rbp
0x180019e04  sub     rsp, 20h
0x180019e08  mov     rbp, rdx
0x180019e0b  mov     rax, [rcx]
0x180019e0e  mov     edx, [rax]
0x180019e10  mov     [rbp+0E0h], rcx
0x180019e17  mov     [rbp+98h], edx
0x180019e1d  mov     eax, [rbp+98h]
0x180019e23  cmp     eax, 0E06D7363h
0x180019e28  jnz     short loc_180019E44
0x180019e2a  mov     rdx, [rbp+0E0h]
0x180019e31  mov     ecx, [rbp+98h]
0x180019e37  call    _XcptFilter_0
0x180019e3c  mov     [rbp+0A0h], eax
0x180019e42  jmp     short loc_180019E4E
0x180019e44  mov     dword ptr [rbp+0A0h], 0
0x180019e4e  mov     eax, [rbp+0A0h]
0x180019e54  add     rsp, 20h
0x180019e58  pop     rbp
0x180019e59  retn
0x180019e5b  push    rbp
0x180019e5d  sub     rsp, 20h
0x180019e61  mov     rbp, rdx
0x180019e64  cmp     dword ptr [rbp+118h], 1
0x180019e6b  ja      short loc_180019E77
0x180019e6d  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
