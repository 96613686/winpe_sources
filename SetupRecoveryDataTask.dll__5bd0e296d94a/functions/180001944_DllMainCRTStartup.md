# __DllMainCRTStartup

- ea: `0x180001944`
- end: `0x180001b50`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x1800016d0`
- `0x180001944`
- `0x180001d1e`
- `0x18000b748`
- `0x18000c680`

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
  if ( (_DWORD)fdwReason || dword_1800157AC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800157B0 = 1;
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
            if ( dword_1800157B0 )
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
0x180001944  mov     [rsp+lpvReserved], r8
0x180001949  mov     [rsp+arg_8], edx
0x18000194d  mov     [rsp+arg_0], rcx
0x180001952  push    rbx
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  sub     rsp, 0F0h
0x18000195c  mov     edi, edx
0x18000195e  mov     rsi, rcx
0x180001961  mov     ebx, 1
0x180001966  cmp     edx, ebx
0x180001968  ja      short loc_180001970
0x18000196a  mov     cs:__native_dllmain_reason, edx
0x180001970  test    edx, edx
0x180001972  jnz     short loc_180001987
0x180001974  cmp     cs:dword_1800157AC, edx
0x18000197a  jnz     short loc_180001987
0x18000197c  xor     ebx, ebx
0x18000197e  mov     [rsp+108h+var_E8], ebx
0x180001982  jmp     loc_180001B34
0x180001987  lea     eax, [rdx-1]
0x18000198a  cmp     eax, 1
0x18000198d  ja      loc_180001A14
0x180001993  mov     rax, cs:_pRawDllMain
0x18000199a  test    rax, rax
0x18000199d  jz      short loc_1800019D5
0x18000199f  cmp     edx, 1
0x1800019a2  jnz     short loc_1800019AA
0x1800019a4  mov     cs:dword_1800157B0, edx
0x1800019aa  mov     r8, [rsp+108h+lpvReserved]
0x1800019b2  call    cs:__guard_dispatch_icall_fptr
0x1800019b8  mov     ebx, eax
0x1800019ba  mov     [rsp+108h+var_E8], eax
0x1800019be  jmp     short loc_1800019D5
0x1800019c0  xor     ebx, ebx
0x1800019c2  mov     [rsp+108h+var_E8], ebx
0x1800019c6  mov     edi, [rsp+108h+arg_8]
0x1800019cd  mov     rsi, [rsp+108h+arg_0]
0x1800019d5  test    ebx, ebx
0x1800019d7  jz      loc_180001B34
0x1800019dd  mov     r8, [rsp+108h+lpvReserved]
0x1800019e5  mov     edx, edi
0x1800019e7  mov     rcx, rsi
0x1800019ea  call    _CRT_INIT
0x1800019ef  mov     ebx, eax
0x1800019f1  mov     [rsp+108h+var_E8], eax
0x1800019f5  jmp     short loc_180001A0C
0x1800019f7  xor     ebx, ebx
0x1800019f9  mov     [rsp+108h+var_E8], ebx
0x1800019fd  mov     edi, [rsp+108h+arg_8]
0x180001a04  mov     rsi, [rsp+108h+arg_0]
0x180001a0c  test    ebx, ebx
0x180001a0e  jz      loc_180001B34
0x180001a14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a1c  mov     edx, edi; fdwReason
0x180001a1e  mov     rcx, rsi; hinstDLL
0x180001a21  call    DllMain
0x180001a26  mov     ebx, eax
0x180001a28  mov     [rsp+108h+var_E8], eax
0x180001a2c  jmp     short loc_180001A43
0x180001a2e  xor     ebx, ebx
0x180001a30  mov     [rsp+108h+var_E8], ebx
0x180001a34  mov     edi, [rsp+108h+arg_8]
0x180001a3b  mov     rsi, [rsp+108h+arg_0]
0x180001a43  cmp     edi, 1
0x180001a46  jnz     short loc_180001ABF
0x180001a48  test    ebx, ebx
0x180001a4a  jnz     short loc_180001ABF
0x180001a4c  xor     r8d, r8d; lpvReserved
0x180001a4f  xor     edx, edx; fdwReason
0x180001a51  mov     rcx, rsi; hinstDLL
0x180001a54  call    DllMain
0x180001a59  jmp     short loc_180001A6E
0x180001a5b  mov     edi, [rsp+108h+arg_8]
0x180001a62  mov     rsi, [rsp+108h+arg_0]
0x180001a6a  mov     ebx, [rsp+108h+var_E8]
0x180001a6e  xor     r8d, r8d
0x180001a71  xor     edx, edx
0x180001a73  mov     rcx, rsi
0x180001a76  call    _CRT_INIT
0x180001a7b  jmp     short loc_180001A90
0x180001a7d  mov     edi, [rsp+108h+arg_8]
0x180001a84  mov     rsi, [rsp+108h+arg_0]
0x180001a8c  mov     ebx, [rsp+108h+var_E8]
0x180001a90  mov     rax, cs:_pRawDllMain
0x180001a97  test    rax, rax
0x180001a9a  jz      short loc_180001ABF
0x180001a9c  xor     r8d, r8d
0x180001a9f  xor     edx, edx
0x180001aa1  mov     rcx, rsi
0x180001aa4  call    cs:__guard_dispatch_icall_fptr
0x180001aaa  jmp     short loc_180001ABF
0x180001aac  mov     edi, [rsp+108h+arg_8]
0x180001ab3  mov     rsi, [rsp+108h+arg_0]
0x180001abb  mov     ebx, [rsp+108h+var_E8]
0x180001abf  test    edi, edi
0x180001ac1  jz      short loc_180001AC8
0x180001ac3  cmp     edi, 3
0x180001ac6  jnz     short loc_180001B34
0x180001ac8  mov     r8, [rsp+108h+lpvReserved]
0x180001ad0  mov     edx, edi
0x180001ad2  mov     rcx, rsi
0x180001ad5  call    _CRT_INIT
0x180001ada  mov     ebx, eax
0x180001adc  mov     [rsp+108h+var_E8], eax
0x180001ae0  jmp     short loc_180001AF7
0x180001ae2  xor     ebx, ebx
0x180001ae4  mov     [rsp+108h+var_E8], ebx
0x180001ae8  mov     edi, [rsp+108h+arg_8]
0x180001aef  mov     rsi, [rsp+108h+arg_0]
0x180001af7  mov     rax, cs:_pRawDllMain
0x180001afe  test    rax, rax
0x180001b01  jz      short loc_180001B34
0x180001b03  cmp     cs:dword_1800157B0, 0
0x180001b0a  jz      short loc_180001B34
0x180001b0c  mov     r8, [rsp+108h+lpvReserved]
0x180001b14  mov     edx, edi
0x180001b16  mov     rcx, rsi
0x180001b19  call    cs:__guard_dispatch_icall_fptr
0x180001b1f  mov     ebx, eax
0x180001b21  mov     [rsp+108h+var_E8], eax
0x180001b25  jmp     short loc_180001B34
0x180001b27  xor     ebx, ebx
0x180001b29  mov     [rsp+108h+var_E8], ebx
0x180001b2d  mov     edi, [rsp+108h+arg_8]
0x180001b34  cmp     edi, 1
0x180001b37  ja      short loc_180001B43
0x180001b39  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b43  mov     eax, ebx
0x180001b45  add     rsp, 0F0h
0x180001b4c  pop     rdi
0x180001b4d  pop     rsi
0x180001b4e  pop     rbx
0x180001b4f  retn
0x18000c723  push    rbp
0x18000c725  sub     rsp, 20h
0x18000c729  mov     rbp, rdx
0x18000c72c  mov     rax, [rcx]
0x18000c72f  mov     edx, [rax]
0x18000c731  mov     [rbp+0A8h], rcx
0x18000c738  mov     [rbp+28h], edx
0x18000c73b  mov     eax, [rbp+28h]
0x18000c73e  cmp     eax, 0E06D7363h
0x18000c743  jnz     short loc_18000C759
0x18000c745  mov     rdx, [rbp+0A8h]
0x18000c74c  mov     ecx, [rbp+28h]
0x18000c74f  call    _XcptFilter_0
0x18000c754  mov     [rbp+30h], eax
0x18000c757  jmp     short loc_18000C760
0x18000c759  mov     dword ptr [rbp+30h], 0
0x18000c760  mov     eax, [rbp+30h]
0x18000c763  add     rsp, 20h
0x18000c767  pop     rbp
0x18000c768  retn
0x18000c76a  push    rbp
0x18000c76c  sub     rsp, 20h
0x18000c770  mov     rbp, rdx
0x18000c773  mov     rax, [rcx]
0x18000c776  mov     edx, [rax]
0x18000c778  mov     [rbp+0B0h], rcx
0x18000c77f  mov     [rbp+38h], edx
0x18000c782  mov     eax, [rbp+38h]
0x18000c785  cmp     eax, 0E06D7363h
0x18000c78a  jnz     short loc_18000C7A0
0x18000c78c  mov     rdx, [rbp+0B0h]
0x18000c793  mov     ecx, [rbp+38h]
0x18000c796  call    _XcptFilter_0
0x18000c79b  mov     [rbp+40h], eax
0x18000c79e  jmp     short loc_18000C7A7
0x18000c7a0  mov     dword ptr [rbp+40h], 0
0x18000c7a7  mov     eax, [rbp+40h]
0x18000c7aa  add     rsp, 20h
0x18000c7ae  pop     rbp
0x18000c7af  retn
0x18000c7b1  push    rbp
0x18000c7b3  sub     rsp, 20h
0x18000c7b7  mov     rbp, rdx
0x18000c7ba  mov     rax, [rcx]
0x18000c7bd  mov     edx, [rax]
0x18000c7bf  mov     [rbp+0B8h], rcx
0x18000c7c6  mov     [rbp+48h], edx
0x18000c7c9  mov     eax, [rbp+48h]
0x18000c7cc  cmp     eax, 0E06D7363h
0x18000c7d1  jnz     short loc_18000C7E7
0x18000c7d3  mov     rdx, [rbp+0B8h]
0x18000c7da  mov     ecx, [rbp+48h]
0x18000c7dd  call    _XcptFilter_0
0x18000c7e2  mov     [rbp+50h], eax
0x18000c7e5  jmp     short loc_18000C7EE
0x18000c7e7  mov     dword ptr [rbp+50h], 0
0x18000c7ee  mov     eax, [rbp+50h]
0x18000c7f1  add     rsp, 20h
0x18000c7f5  pop     rbp
0x18000c7f6  retn
0x18000c7f8  push    rbp
0x18000c7fa  sub     rsp, 20h
0x18000c7fe  mov     rbp, rdx
0x18000c801  mov     rax, [rcx]
0x18000c804  mov     edx, [rax]
0x18000c806  mov     [rbp+0C0h], rcx
0x18000c80d  mov     [rbp+58h], edx
0x18000c810  mov     eax, [rbp+58h]
0x18000c813  cmp     eax, 0E06D7363h
0x18000c818  jnz     short loc_18000C82E
0x18000c81a  mov     rdx, [rbp+0C0h]
0x18000c821  mov     ecx, [rbp+58h]
0x18000c824  call    _XcptFilter_0
0x18000c829  mov     [rbp+60h], eax
0x18000c82c  jmp     short loc_18000C835
0x18000c82e  mov     dword ptr [rbp+60h], 0
0x18000c835  mov     eax, [rbp+60h]
0x18000c838  add     rsp, 20h
0x18000c83c  pop     rbp
0x18000c83d  retn
0x18000c83f  push    rbp
0x18000c841  sub     rsp, 20h
0x18000c845  mov     rbp, rdx
0x18000c848  mov     rax, [rcx]
0x18000c84b  mov     edx, [rax]
0x18000c84d  mov     [rbp+0C8h], rcx
0x18000c854  mov     [rbp+68h], edx
0x18000c857  mov     eax, [rbp+68h]
0x18000c85a  cmp     eax, 0E06D7363h
0x18000c85f  jnz     short loc_18000C875
0x18000c861  mov     rdx, [rbp+0C8h]
0x18000c868  mov     ecx, [rbp+68h]
0x18000c86b  call    _XcptFilter_0
0x18000c870  mov     [rbp+70h], eax
0x18000c873  jmp     short loc_18000C87C
0x18000c875  mov     dword ptr [rbp+70h], 0
0x18000c87c  mov     eax, [rbp+70h]
0x18000c87f  add     rsp, 20h
0x18000c883  pop     rbp
0x18000c884  retn
0x18000c886  push    rbp
0x18000c888  sub     rsp, 20h
0x18000c88c  mov     rbp, rdx
0x18000c88f  mov     rax, [rcx]
0x18000c892  mov     edx, [rax]
0x18000c894  mov     [rbp+0D0h], rcx
0x18000c89b  mov     [rbp+78h], edx
0x18000c89e  mov     eax, [rbp+78h]
0x18000c8a1  cmp     eax, 0E06D7363h
0x18000c8a6  jnz     short loc_18000C8BF
0x18000c8a8  mov     rdx, [rbp+0D0h]
0x18000c8af  mov     ecx, [rbp+78h]
0x18000c8b2  call    _XcptFilter_0
0x18000c8b7  mov     [rbp+80h], eax
0x18000c8bd  jmp     short loc_18000C8C9
0x18000c8bf  mov     dword ptr [rbp+80h], 0
0x18000c8c9  mov     eax, [rbp+80h]
0x18000c8cf  add     rsp, 20h
0x18000c8d3  pop     rbp
0x18000c8d4  retn
0x18000c8d6  push    rbp
0x18000c8d8  sub     rsp, 20h
0x18000c8dc  mov     rbp, rdx
0x18000c8df  mov     rax, [rcx]
0x18000c8e2  mov     edx, [rax]
0x18000c8e4  mov     [rbp+0D8h], rcx
0x18000c8eb  mov     [rbp+88h], edx
0x18000c8f1  mov     eax, [rbp+88h]
0x18000c8f7  cmp     eax, 0E06D7363h
0x18000c8fc  jnz     short loc_18000C918
0x18000c8fe  mov     rdx, [rbp+0D8h]
0x18000c905  mov     ecx, [rbp+88h]
0x18000c90b  call    _XcptFilter_0
0x18000c910  mov     [rbp+90h], eax
0x18000c916  jmp     short loc_18000C922
0x18000c918  mov     dword ptr [rbp+90h], 0
0x18000c922  mov     eax, [rbp+90h]
0x18000c928  add     rsp, 20h
0x18000c92c  pop     rbp
0x18000c92d  retn
0x18000c92f  push    rbp
0x18000c931  sub     rsp, 20h
0x18000c935  mov     rbp, rdx
0x18000c938  mov     rax, [rcx]
0x18000c93b  mov     edx, [rax]
0x18000c93d  mov     [rbp+0E0h], rcx
0x18000c944  mov     [rbp+98h], edx
0x18000c94a  mov     eax, [rbp+98h]
0x18000c950  cmp     eax, 0E06D7363h
0x18000c955  jnz     short loc_18000C971
0x18000c957  mov     rdx, [rbp+0E0h]
0x18000c95e  mov     ecx, [rbp+98h]
0x18000c964  call    _XcptFilter_0
0x18000c969  mov     [rbp+0A0h], eax
0x18000c96f  jmp     short loc_18000C97B
0x18000c971  mov     dword ptr [rbp+0A0h], 0
0x18000c97b  mov     eax, [rbp+0A0h]
0x18000c981  add     rsp, 20h
0x18000c985  pop     rbp
0x18000c986  retn
0x18000c988  push    rbp
0x18000c98a  sub     rsp, 20h
0x18000c98e  mov     rbp, rdx
0x18000c991  cmp     dword ptr [rbp+118h], 1
0x18000c998  ja      short loc_18000C9A4
0x18000c99a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
