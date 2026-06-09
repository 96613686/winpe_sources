# __DllMainCRTStartup

- ea: `0x180001504`
- end: `0x180001710`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800014c0`

## callees

- `0x180001290`
- `0x180001504`
- `0x180001725`
- `0x18000ee54`
- `0x180018a10`

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
  if ( (_DWORD)fdwReason || dword_180071300 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180071304 = 1;
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
            if ( dword_180071304 )
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
0x180001504  mov     [rsp+lpvReserved], r8
0x180001509  mov     [rsp+arg_8], edx
0x18000150d  mov     [rsp+arg_0], rcx
0x180001512  push    rbx
0x180001513  push    rsi
0x180001514  push    rdi
0x180001515  sub     rsp, 0F0h
0x18000151c  mov     edi, edx
0x18000151e  mov     rsi, rcx
0x180001521  mov     ebx, 1
0x180001526  cmp     edx, ebx
0x180001528  ja      short loc_180001530
0x18000152a  mov     cs:__native_dllmain_reason, edx
0x180001530  test    edx, edx
0x180001532  jnz     short loc_180001547
0x180001534  cmp     cs:dword_180071300, edx
0x18000153a  jnz     short loc_180001547
0x18000153c  xor     ebx, ebx
0x18000153e  mov     [rsp+108h+var_E8], ebx
0x180001542  jmp     loc_1800016F4
0x180001547  lea     eax, [rdx-1]
0x18000154a  cmp     eax, 1
0x18000154d  ja      loc_1800015D4
0x180001553  mov     rax, cs:_pRawDllMain
0x18000155a  test    rax, rax
0x18000155d  jz      short loc_180001595
0x18000155f  cmp     edx, 1
0x180001562  jnz     short loc_18000156A
0x180001564  mov     cs:dword_180071304, edx
0x18000156a  mov     r8, [rsp+108h+lpvReserved]
0x180001572  call    cs:__guard_dispatch_icall_fptr
0x180001578  mov     ebx, eax
0x18000157a  mov     [rsp+108h+var_E8], eax
0x18000157e  jmp     short loc_180001595
0x180001580  xor     ebx, ebx
0x180001582  mov     [rsp+108h+var_E8], ebx
0x180001586  mov     edi, [rsp+108h+arg_8]
0x18000158d  mov     rsi, [rsp+108h+arg_0]
0x180001595  test    ebx, ebx
0x180001597  jz      loc_1800016F4
0x18000159d  mov     r8, [rsp+108h+lpvReserved]
0x1800015a5  mov     edx, edi
0x1800015a7  mov     rcx, rsi
0x1800015aa  call    _CRT_INIT
0x1800015af  mov     ebx, eax
0x1800015b1  mov     [rsp+108h+var_E8], eax
0x1800015b5  jmp     short loc_1800015CC
0x1800015b7  xor     ebx, ebx
0x1800015b9  mov     [rsp+108h+var_E8], ebx
0x1800015bd  mov     edi, [rsp+108h+arg_8]
0x1800015c4  mov     rsi, [rsp+108h+arg_0]
0x1800015cc  test    ebx, ebx
0x1800015ce  jz      loc_1800016F4
0x1800015d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800015dc  mov     edx, edi; fdwReason
0x1800015de  mov     rcx, rsi; hinstDLL
0x1800015e1  call    DllMain
0x1800015e6  mov     ebx, eax
0x1800015e8  mov     [rsp+108h+var_E8], eax
0x1800015ec  jmp     short loc_180001603
0x1800015ee  xor     ebx, ebx
0x1800015f0  mov     [rsp+108h+var_E8], ebx
0x1800015f4  mov     edi, [rsp+108h+arg_8]
0x1800015fb  mov     rsi, [rsp+108h+arg_0]
0x180001603  cmp     edi, 1
0x180001606  jnz     short loc_18000167F
0x180001608  test    ebx, ebx
0x18000160a  jnz     short loc_18000167F
0x18000160c  xor     r8d, r8d; lpvReserved
0x18000160f  xor     edx, edx; fdwReason
0x180001611  mov     rcx, rsi; hinstDLL
0x180001614  call    DllMain
0x180001619  jmp     short loc_18000162E
0x18000161b  mov     edi, [rsp+108h+arg_8]
0x180001622  mov     rsi, [rsp+108h+arg_0]
0x18000162a  mov     ebx, [rsp+108h+var_E8]
0x18000162e  xor     r8d, r8d
0x180001631  xor     edx, edx
0x180001633  mov     rcx, rsi
0x180001636  call    _CRT_INIT
0x18000163b  jmp     short loc_180001650
0x18000163d  mov     edi, [rsp+108h+arg_8]
0x180001644  mov     rsi, [rsp+108h+arg_0]
0x18000164c  mov     ebx, [rsp+108h+var_E8]
0x180001650  mov     rax, cs:_pRawDllMain
0x180001657  test    rax, rax
0x18000165a  jz      short loc_18000167F
0x18000165c  xor     r8d, r8d
0x18000165f  xor     edx, edx
0x180001661  mov     rcx, rsi
0x180001664  call    cs:__guard_dispatch_icall_fptr
0x18000166a  jmp     short loc_18000167F
0x18000166c  mov     edi, [rsp+108h+arg_8]
0x180001673  mov     rsi, [rsp+108h+arg_0]
0x18000167b  mov     ebx, [rsp+108h+var_E8]
0x18000167f  test    edi, edi
0x180001681  jz      short loc_180001688
0x180001683  cmp     edi, 3
0x180001686  jnz     short loc_1800016F4
0x180001688  mov     r8, [rsp+108h+lpvReserved]
0x180001690  mov     edx, edi
0x180001692  mov     rcx, rsi
0x180001695  call    _CRT_INIT
0x18000169a  mov     ebx, eax
0x18000169c  mov     [rsp+108h+var_E8], eax
0x1800016a0  jmp     short loc_1800016B7
0x1800016a2  xor     ebx, ebx
0x1800016a4  mov     [rsp+108h+var_E8], ebx
0x1800016a8  mov     edi, [rsp+108h+arg_8]
0x1800016af  mov     rsi, [rsp+108h+arg_0]
0x1800016b7  mov     rax, cs:_pRawDllMain
0x1800016be  test    rax, rax
0x1800016c1  jz      short loc_1800016F4
0x1800016c3  cmp     cs:dword_180071304, 0
0x1800016ca  jz      short loc_1800016F4
0x1800016cc  mov     r8, [rsp+108h+lpvReserved]
0x1800016d4  mov     edx, edi
0x1800016d6  mov     rcx, rsi
0x1800016d9  call    cs:__guard_dispatch_icall_fptr
0x1800016df  mov     ebx, eax
0x1800016e1  mov     [rsp+108h+var_E8], eax
0x1800016e5  jmp     short loc_1800016F4
0x1800016e7  xor     ebx, ebx
0x1800016e9  mov     [rsp+108h+var_E8], ebx
0x1800016ed  mov     edi, [rsp+108h+arg_8]
0x1800016f4  cmp     edi, 1
0x1800016f7  ja      short loc_180001703
0x1800016f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001703  mov     eax, ebx
0x180001705  add     rsp, 0F0h
0x18000170c  pop     rdi
0x18000170d  pop     rsi
0x18000170e  pop     rbx
0x18000170f  retn
0x180018ae0  push    rbp
0x180018ae2  sub     rsp, 20h
0x180018ae6  mov     rbp, rdx
0x180018ae9  mov     rax, [rcx]
0x180018aec  mov     edx, [rax]
0x180018aee  mov     [rbp+0A8h], rcx
0x180018af5  mov     [rbp+28h], edx
0x180018af8  mov     eax, [rbp+28h]
0x180018afb  cmp     eax, 0E06D7363h
0x180018b00  jnz     short loc_180018B16
0x180018b02  mov     rdx, [rbp+0A8h]
0x180018b09  mov     ecx, [rbp+28h]
0x180018b0c  call    _XcptFilter_0
0x180018b11  mov     [rbp+30h], eax
0x180018b14  jmp     short loc_180018B1D
0x180018b16  mov     dword ptr [rbp+30h], 0
0x180018b1d  mov     eax, [rbp+30h]
0x180018b20  add     rsp, 20h
0x180018b24  pop     rbp
0x180018b25  retn
0x180018b27  push    rbp
0x180018b29  sub     rsp, 20h
0x180018b2d  mov     rbp, rdx
0x180018b30  mov     rax, [rcx]
0x180018b33  mov     edx, [rax]
0x180018b35  mov     [rbp+0B0h], rcx
0x180018b3c  mov     [rbp+38h], edx
0x180018b3f  mov     eax, [rbp+38h]
0x180018b42  cmp     eax, 0E06D7363h
0x180018b47  jnz     short loc_180018B5D
0x180018b49  mov     rdx, [rbp+0B0h]
0x180018b50  mov     ecx, [rbp+38h]
0x180018b53  call    _XcptFilter_0
0x180018b58  mov     [rbp+40h], eax
0x180018b5b  jmp     short loc_180018B64
0x180018b5d  mov     dword ptr [rbp+40h], 0
0x180018b64  mov     eax, [rbp+40h]
0x180018b67  add     rsp, 20h
0x180018b6b  pop     rbp
0x180018b6c  retn
0x180018b6e  push    rbp
0x180018b70  sub     rsp, 20h
0x180018b74  mov     rbp, rdx
0x180018b77  mov     rax, [rcx]
0x180018b7a  mov     edx, [rax]
0x180018b7c  mov     [rbp+0B8h], rcx
0x180018b83  mov     [rbp+48h], edx
0x180018b86  mov     eax, [rbp+48h]
0x180018b89  cmp     eax, 0E06D7363h
0x180018b8e  jnz     short loc_180018BA4
0x180018b90  mov     rdx, [rbp+0B8h]
0x180018b97  mov     ecx, [rbp+48h]
0x180018b9a  call    _XcptFilter_0
0x180018b9f  mov     [rbp+50h], eax
0x180018ba2  jmp     short loc_180018BAB
0x180018ba4  mov     dword ptr [rbp+50h], 0
0x180018bab  mov     eax, [rbp+50h]
0x180018bae  add     rsp, 20h
0x180018bb2  pop     rbp
0x180018bb3  retn
0x180018bb5  push    rbp
0x180018bb7  sub     rsp, 20h
0x180018bbb  mov     rbp, rdx
0x180018bbe  mov     rax, [rcx]
0x180018bc1  mov     edx, [rax]
0x180018bc3  mov     [rbp+0C0h], rcx
0x180018bca  mov     [rbp+58h], edx
0x180018bcd  mov     eax, [rbp+58h]
0x180018bd0  cmp     eax, 0E06D7363h
0x180018bd5  jnz     short loc_180018BEB
0x180018bd7  mov     rdx, [rbp+0C0h]
0x180018bde  mov     ecx, [rbp+58h]
0x180018be1  call    _XcptFilter_0
0x180018be6  mov     [rbp+60h], eax
0x180018be9  jmp     short loc_180018BF2
0x180018beb  mov     dword ptr [rbp+60h], 0
0x180018bf2  mov     eax, [rbp+60h]
0x180018bf5  add     rsp, 20h
0x180018bf9  pop     rbp
0x180018bfa  retn
0x180018bfc  push    rbp
0x180018bfe  sub     rsp, 20h
0x180018c02  mov     rbp, rdx
0x180018c05  mov     rax, [rcx]
0x180018c08  mov     edx, [rax]
0x180018c0a  mov     [rbp+0C8h], rcx
0x180018c11  mov     [rbp+68h], edx
0x180018c14  mov     eax, [rbp+68h]
0x180018c17  cmp     eax, 0E06D7363h
0x180018c1c  jnz     short loc_180018C32
0x180018c1e  mov     rdx, [rbp+0C8h]
0x180018c25  mov     ecx, [rbp+68h]
0x180018c28  call    _XcptFilter_0
0x180018c2d  mov     [rbp+70h], eax
0x180018c30  jmp     short loc_180018C39
0x180018c32  mov     dword ptr [rbp+70h], 0
0x180018c39  mov     eax, [rbp+70h]
0x180018c3c  add     rsp, 20h
0x180018c40  pop     rbp
0x180018c41  retn
0x180018c43  push    rbp
0x180018c45  sub     rsp, 20h
0x180018c49  mov     rbp, rdx
0x180018c4c  mov     rax, [rcx]
0x180018c4f  mov     edx, [rax]
0x180018c51  mov     [rbp+0D0h], rcx
0x180018c58  mov     [rbp+78h], edx
0x180018c5b  mov     eax, [rbp+78h]
0x180018c5e  cmp     eax, 0E06D7363h
0x180018c63  jnz     short loc_180018C7C
0x180018c65  mov     rdx, [rbp+0D0h]
0x180018c6c  mov     ecx, [rbp+78h]
0x180018c6f  call    _XcptFilter_0
0x180018c74  mov     [rbp+80h], eax
0x180018c7a  jmp     short loc_180018C86
0x180018c7c  mov     dword ptr [rbp+80h], 0
0x180018c86  mov     eax, [rbp+80h]
0x180018c8c  add     rsp, 20h
0x180018c90  pop     rbp
0x180018c91  retn
0x180018c93  push    rbp
0x180018c95  sub     rsp, 20h
0x180018c99  mov     rbp, rdx
0x180018c9c  mov     rax, [rcx]
0x180018c9f  mov     edx, [rax]
0x180018ca1  mov     [rbp+0D8h], rcx
0x180018ca8  mov     [rbp+88h], edx
0x180018cae  mov     eax, [rbp+88h]
0x180018cb4  cmp     eax, 0E06D7363h
0x180018cb9  jnz     short loc_180018CD5
0x180018cbb  mov     rdx, [rbp+0D8h]
0x180018cc2  mov     ecx, [rbp+88h]
0x180018cc8  call    _XcptFilter_0
0x180018ccd  mov     [rbp+90h], eax
0x180018cd3  jmp     short loc_180018CDF
0x180018cd5  mov     dword ptr [rbp+90h], 0
0x180018cdf  mov     eax, [rbp+90h]
0x180018ce5  add     rsp, 20h
0x180018ce9  pop     rbp
0x180018cea  retn
0x180018cec  push    rbp
0x180018cee  sub     rsp, 20h
0x180018cf2  mov     rbp, rdx
0x180018cf5  mov     rax, [rcx]
0x180018cf8  mov     edx, [rax]
0x180018cfa  mov     [rbp+0E0h], rcx
0x180018d01  mov     [rbp+98h], edx
0x180018d07  mov     eax, [rbp+98h]
0x180018d0d  cmp     eax, 0E06D7363h
0x180018d12  jnz     short loc_180018D2E
0x180018d14  mov     rdx, [rbp+0E0h]
0x180018d1b  mov     ecx, [rbp+98h]
0x180018d21  call    _XcptFilter_0
0x180018d26  mov     [rbp+0A0h], eax
0x180018d2c  jmp     short loc_180018D38
0x180018d2e  mov     dword ptr [rbp+0A0h], 0
0x180018d38  mov     eax, [rbp+0A0h]
0x180018d3e  add     rsp, 20h
0x180018d42  pop     rbp
0x180018d43  retn
0x180018d45  push    rbp
0x180018d47  sub     rsp, 20h
0x180018d4b  mov     rbp, rdx
0x180018d4e  cmp     dword ptr [rbp+118h], 1
0x180018d55  ja      short loc_180018D61
0x180018d57  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
