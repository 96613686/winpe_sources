# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180001770`
- `0x180001910`

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
  if ( (_DWORD)fdwReason || dword_1800040A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800040A4 = 1;
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
            if ( dword_1800040A4 )
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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_1800040A0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_1800040A4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_1800040A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180001980  push    rbp
0x180001982  sub     rsp, 20h
0x180001986  mov     rbp, rdx
0x180001989  mov     rax, [rcx]
0x18000198c  mov     edx, [rax]
0x18000198e  mov     [rbp+0A8h], rcx
0x180001995  mov     [rbp+28h], edx
0x180001998  mov     eax, [rbp+28h]
0x18000199b  cmp     eax, 0E06D7363h
0x1800019a0  jnz     short loc_1800019B6
0x1800019a2  mov     rdx, [rbp+0A8h]
0x1800019a9  mov     ecx, [rbp+28h]
0x1800019ac  call    _XcptFilter_0
0x1800019b1  mov     [rbp+30h], eax
0x1800019b4  jmp     short loc_1800019BD
0x1800019b6  mov     dword ptr [rbp+30h], 0
0x1800019bd  mov     eax, [rbp+30h]
0x1800019c0  add     rsp, 20h
0x1800019c4  pop     rbp
0x1800019c5  retn
0x1800019c7  push    rbp
0x1800019c9  sub     rsp, 20h
0x1800019cd  mov     rbp, rdx
0x1800019d0  mov     rax, [rcx]
0x1800019d3  mov     edx, [rax]
0x1800019d5  mov     [rbp+0B0h], rcx
0x1800019dc  mov     [rbp+38h], edx
0x1800019df  mov     eax, [rbp+38h]
0x1800019e2  cmp     eax, 0E06D7363h
0x1800019e7  jnz     short loc_1800019FD
0x1800019e9  mov     rdx, [rbp+0B0h]
0x1800019f0  mov     ecx, [rbp+38h]
0x1800019f3  call    _XcptFilter_0
0x1800019f8  mov     [rbp+40h], eax
0x1800019fb  jmp     short loc_180001A04
0x1800019fd  mov     dword ptr [rbp+40h], 0
0x180001a04  mov     eax, [rbp+40h]
0x180001a07  add     rsp, 20h
0x180001a0b  pop     rbp
0x180001a0c  retn
0x180001a0e  push    rbp
0x180001a10  sub     rsp, 20h
0x180001a14  mov     rbp, rdx
0x180001a17  mov     rax, [rcx]
0x180001a1a  mov     edx, [rax]
0x180001a1c  mov     [rbp+0B8h], rcx
0x180001a23  mov     [rbp+48h], edx
0x180001a26  mov     eax, [rbp+48h]
0x180001a29  cmp     eax, 0E06D7363h
0x180001a2e  jnz     short loc_180001A44
0x180001a30  mov     rdx, [rbp+0B8h]
0x180001a37  mov     ecx, [rbp+48h]
0x180001a3a  call    _XcptFilter_0
0x180001a3f  mov     [rbp+50h], eax
0x180001a42  jmp     short loc_180001A4B
0x180001a44  mov     dword ptr [rbp+50h], 0
0x180001a4b  mov     eax, [rbp+50h]
0x180001a4e  add     rsp, 20h
0x180001a52  pop     rbp
0x180001a53  retn
0x180001a55  push    rbp
0x180001a57  sub     rsp, 20h
0x180001a5b  mov     rbp, rdx
0x180001a5e  mov     rax, [rcx]
0x180001a61  mov     edx, [rax]
0x180001a63  mov     [rbp+0C0h], rcx
0x180001a6a  mov     [rbp+58h], edx
0x180001a6d  mov     eax, [rbp+58h]
0x180001a70  cmp     eax, 0E06D7363h
0x180001a75  jnz     short loc_180001A8B
0x180001a77  mov     rdx, [rbp+0C0h]
0x180001a7e  mov     ecx, [rbp+58h]
0x180001a81  call    _XcptFilter_0
0x180001a86  mov     [rbp+60h], eax
0x180001a89  jmp     short loc_180001A92
0x180001a8b  mov     dword ptr [rbp+60h], 0
0x180001a92  mov     eax, [rbp+60h]
0x180001a95  add     rsp, 20h
0x180001a99  pop     rbp
0x180001a9a  retn
0x180001a9c  push    rbp
0x180001a9e  sub     rsp, 20h
0x180001aa2  mov     rbp, rdx
0x180001aa5  mov     rax, [rcx]
0x180001aa8  mov     edx, [rax]
0x180001aaa  mov     [rbp+0C8h], rcx
0x180001ab1  mov     [rbp+68h], edx
0x180001ab4  mov     eax, [rbp+68h]
0x180001ab7  cmp     eax, 0E06D7363h
0x180001abc  jnz     short loc_180001AD2
0x180001abe  mov     rdx, [rbp+0C8h]
0x180001ac5  mov     ecx, [rbp+68h]
0x180001ac8  call    _XcptFilter_0
0x180001acd  mov     [rbp+70h], eax
0x180001ad0  jmp     short loc_180001AD9
0x180001ad2  mov     dword ptr [rbp+70h], 0
0x180001ad9  mov     eax, [rbp+70h]
0x180001adc  add     rsp, 20h
0x180001ae0  pop     rbp
0x180001ae1  retn
0x180001ae3  push    rbp
0x180001ae5  sub     rsp, 20h
0x180001ae9  mov     rbp, rdx
0x180001aec  mov     rax, [rcx]
0x180001aef  mov     edx, [rax]
0x180001af1  mov     [rbp+0D0h], rcx
0x180001af8  mov     [rbp+78h], edx
0x180001afb  mov     eax, [rbp+78h]
0x180001afe  cmp     eax, 0E06D7363h
0x180001b03  jnz     short loc_180001B1C
0x180001b05  mov     rdx, [rbp+0D0h]
0x180001b0c  mov     ecx, [rbp+78h]
0x180001b0f  call    _XcptFilter_0
0x180001b14  mov     [rbp+80h], eax
0x180001b1a  jmp     short loc_180001B26
0x180001b1c  mov     dword ptr [rbp+80h], 0
0x180001b26  mov     eax, [rbp+80h]
0x180001b2c  add     rsp, 20h
0x180001b30  pop     rbp
0x180001b31  retn
0x180001b33  push    rbp
0x180001b35  sub     rsp, 20h
0x180001b39  mov     rbp, rdx
0x180001b3c  mov     rax, [rcx]
0x180001b3f  mov     edx, [rax]
0x180001b41  mov     [rbp+0D8h], rcx
0x180001b48  mov     [rbp+88h], edx
0x180001b4e  mov     eax, [rbp+88h]
0x180001b54  cmp     eax, 0E06D7363h
0x180001b59  jnz     short loc_180001B75
0x180001b5b  mov     rdx, [rbp+0D8h]
0x180001b62  mov     ecx, [rbp+88h]
0x180001b68  call    _XcptFilter_0
0x180001b6d  mov     [rbp+90h], eax
0x180001b73  jmp     short loc_180001B7F
0x180001b75  mov     dword ptr [rbp+90h], 0
0x180001b7f  mov     eax, [rbp+90h]
0x180001b85  add     rsp, 20h
0x180001b89  pop     rbp
0x180001b8a  retn
0x180001b8c  push    rbp
0x180001b8e  sub     rsp, 20h
0x180001b92  mov     rbp, rdx
0x180001b95  mov     rax, [rcx]
0x180001b98  mov     edx, [rax]
0x180001b9a  mov     [rbp+0E0h], rcx
0x180001ba1  mov     [rbp+98h], edx
0x180001ba7  mov     eax, [rbp+98h]
0x180001bad  cmp     eax, 0E06D7363h
0x180001bb2  jnz     short loc_180001BCE
0x180001bb4  mov     rdx, [rbp+0E0h]
0x180001bbb  mov     ecx, [rbp+98h]
0x180001bc1  call    _XcptFilter_0
0x180001bc6  mov     [rbp+0A0h], eax
0x180001bcc  jmp     short loc_180001BD8
0x180001bce  mov     dword ptr [rbp+0A0h], 0
0x180001bd8  mov     eax, [rbp+0A0h]
0x180001bde  add     rsp, 20h
0x180001be2  pop     rbp
0x180001be3  retn
0x180001be5  push    rbp
0x180001be7  sub     rsp, 20h
0x180001beb  mov     rbp, rdx
0x180001bee  cmp     dword ptr [rbp+118h], 1
0x180001bf5  ja      short loc_180001C01
0x180001bf7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
