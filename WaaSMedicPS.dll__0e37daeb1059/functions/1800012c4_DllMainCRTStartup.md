# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x1800019a4`
- `0x1800019f0`

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
  if ( (_DWORD)fdwReason || dword_1800070A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070A4 = 1;
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
            if ( dword_1800070A4 )
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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800070A0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800070A4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800070A4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180001a30  push    rbp
0x180001a32  sub     rsp, 20h
0x180001a36  mov     rbp, rdx
0x180001a39  mov     rax, [rcx]
0x180001a3c  mov     edx, [rax]
0x180001a3e  mov     [rbp+0A8h], rcx
0x180001a45  mov     [rbp+28h], edx
0x180001a48  mov     eax, [rbp+28h]
0x180001a4b  cmp     eax, 0E06D7363h
0x180001a50  jnz     short loc_180001A66
0x180001a52  mov     rdx, [rbp+0A8h]
0x180001a59  mov     ecx, [rbp+28h]
0x180001a5c  call    _XcptFilter_0
0x180001a61  mov     [rbp+30h], eax
0x180001a64  jmp     short loc_180001A6D
0x180001a66  mov     dword ptr [rbp+30h], 0
0x180001a6d  mov     eax, [rbp+30h]
0x180001a70  add     rsp, 20h
0x180001a74  pop     rbp
0x180001a75  retn
0x180001a77  push    rbp
0x180001a79  sub     rsp, 20h
0x180001a7d  mov     rbp, rdx
0x180001a80  mov     rax, [rcx]
0x180001a83  mov     edx, [rax]
0x180001a85  mov     [rbp+0B0h], rcx
0x180001a8c  mov     [rbp+38h], edx
0x180001a8f  mov     eax, [rbp+38h]
0x180001a92  cmp     eax, 0E06D7363h
0x180001a97  jnz     short loc_180001AAD
0x180001a99  mov     rdx, [rbp+0B0h]
0x180001aa0  mov     ecx, [rbp+38h]
0x180001aa3  call    _XcptFilter_0
0x180001aa8  mov     [rbp+40h], eax
0x180001aab  jmp     short loc_180001AB4
0x180001aad  mov     dword ptr [rbp+40h], 0
0x180001ab4  mov     eax, [rbp+40h]
0x180001ab7  add     rsp, 20h
0x180001abb  pop     rbp
0x180001abc  retn
0x180001abe  push    rbp
0x180001ac0  sub     rsp, 20h
0x180001ac4  mov     rbp, rdx
0x180001ac7  mov     rax, [rcx]
0x180001aca  mov     edx, [rax]
0x180001acc  mov     [rbp+0B8h], rcx
0x180001ad3  mov     [rbp+48h], edx
0x180001ad6  mov     eax, [rbp+48h]
0x180001ad9  cmp     eax, 0E06D7363h
0x180001ade  jnz     short loc_180001AF4
0x180001ae0  mov     rdx, [rbp+0B8h]
0x180001ae7  mov     ecx, [rbp+48h]
0x180001aea  call    _XcptFilter_0
0x180001aef  mov     [rbp+50h], eax
0x180001af2  jmp     short loc_180001AFB
0x180001af4  mov     dword ptr [rbp+50h], 0
0x180001afb  mov     eax, [rbp+50h]
0x180001afe  add     rsp, 20h
0x180001b02  pop     rbp
0x180001b03  retn
0x180001b05  push    rbp
0x180001b07  sub     rsp, 20h
0x180001b0b  mov     rbp, rdx
0x180001b0e  mov     rax, [rcx]
0x180001b11  mov     edx, [rax]
0x180001b13  mov     [rbp+0C0h], rcx
0x180001b1a  mov     [rbp+58h], edx
0x180001b1d  mov     eax, [rbp+58h]
0x180001b20  cmp     eax, 0E06D7363h
0x180001b25  jnz     short loc_180001B3B
0x180001b27  mov     rdx, [rbp+0C0h]
0x180001b2e  mov     ecx, [rbp+58h]
0x180001b31  call    _XcptFilter_0
0x180001b36  mov     [rbp+60h], eax
0x180001b39  jmp     short loc_180001B42
0x180001b3b  mov     dword ptr [rbp+60h], 0
0x180001b42  mov     eax, [rbp+60h]
0x180001b45  add     rsp, 20h
0x180001b49  pop     rbp
0x180001b4a  retn
0x180001b4c  push    rbp
0x180001b4e  sub     rsp, 20h
0x180001b52  mov     rbp, rdx
0x180001b55  mov     rax, [rcx]
0x180001b58  mov     edx, [rax]
0x180001b5a  mov     [rbp+0C8h], rcx
0x180001b61  mov     [rbp+68h], edx
0x180001b64  mov     eax, [rbp+68h]
0x180001b67  cmp     eax, 0E06D7363h
0x180001b6c  jnz     short loc_180001B82
0x180001b6e  mov     rdx, [rbp+0C8h]
0x180001b75  mov     ecx, [rbp+68h]
0x180001b78  call    _XcptFilter_0
0x180001b7d  mov     [rbp+70h], eax
0x180001b80  jmp     short loc_180001B89
0x180001b82  mov     dword ptr [rbp+70h], 0
0x180001b89  mov     eax, [rbp+70h]
0x180001b8c  add     rsp, 20h
0x180001b90  pop     rbp
0x180001b91  retn
0x180001b93  push    rbp
0x180001b95  sub     rsp, 20h
0x180001b99  mov     rbp, rdx
0x180001b9c  mov     rax, [rcx]
0x180001b9f  mov     edx, [rax]
0x180001ba1  mov     [rbp+0D0h], rcx
0x180001ba8  mov     [rbp+78h], edx
0x180001bab  mov     eax, [rbp+78h]
0x180001bae  cmp     eax, 0E06D7363h
0x180001bb3  jnz     short loc_180001BCC
0x180001bb5  mov     rdx, [rbp+0D0h]
0x180001bbc  mov     ecx, [rbp+78h]
0x180001bbf  call    _XcptFilter_0
0x180001bc4  mov     [rbp+80h], eax
0x180001bca  jmp     short loc_180001BD6
0x180001bcc  mov     dword ptr [rbp+80h], 0
0x180001bd6  mov     eax, [rbp+80h]
0x180001bdc  add     rsp, 20h
0x180001be0  pop     rbp
0x180001be1  retn
0x180001be3  push    rbp
0x180001be5  sub     rsp, 20h
0x180001be9  mov     rbp, rdx
0x180001bec  mov     rax, [rcx]
0x180001bef  mov     edx, [rax]
0x180001bf1  mov     [rbp+0D8h], rcx
0x180001bf8  mov     [rbp+88h], edx
0x180001bfe  mov     eax, [rbp+88h]
0x180001c04  cmp     eax, 0E06D7363h
0x180001c09  jnz     short loc_180001C25
0x180001c0b  mov     rdx, [rbp+0D8h]
0x180001c12  mov     ecx, [rbp+88h]
0x180001c18  call    _XcptFilter_0
0x180001c1d  mov     [rbp+90h], eax
0x180001c23  jmp     short loc_180001C2F
0x180001c25  mov     dword ptr [rbp+90h], 0
0x180001c2f  mov     eax, [rbp+90h]
0x180001c35  add     rsp, 20h
0x180001c39  pop     rbp
0x180001c3a  retn
0x180001c3c  push    rbp
0x180001c3e  sub     rsp, 20h
0x180001c42  mov     rbp, rdx
0x180001c45  mov     rax, [rcx]
0x180001c48  mov     edx, [rax]
0x180001c4a  mov     [rbp+0E0h], rcx
0x180001c51  mov     [rbp+98h], edx
0x180001c57  mov     eax, [rbp+98h]
0x180001c5d  cmp     eax, 0E06D7363h
0x180001c62  jnz     short loc_180001C7E
0x180001c64  mov     rdx, [rbp+0E0h]
0x180001c6b  mov     ecx, [rbp+98h]
0x180001c71  call    _XcptFilter_0
0x180001c76  mov     [rbp+0A0h], eax
0x180001c7c  jmp     short loc_180001C88
0x180001c7e  mov     dword ptr [rbp+0A0h], 0
0x180001c88  mov     eax, [rbp+0A0h]
0x180001c8e  add     rsp, 20h
0x180001c92  pop     rbp
0x180001c93  retn
0x180001c95  push    rbp
0x180001c97  sub     rsp, 20h
0x180001c9b  mov     rbp, rdx
0x180001c9e  cmp     dword ptr [rbp+118h], 1
0x180001ca5  ja      short loc_180001CB1
0x180001ca7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
