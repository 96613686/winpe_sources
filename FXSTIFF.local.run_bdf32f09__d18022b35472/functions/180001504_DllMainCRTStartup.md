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
- `0x18000e7e4`
- `0x180017c40`

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
  if ( (_DWORD)fdwReason || dword_180070300 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180070304 = 1;
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
            if ( dword_180070304 )
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
0x180001534  cmp     cs:dword_180070300, edx
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
0x180001564  mov     cs:dword_180070304, edx
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
0x1800016c3  cmp     cs:dword_180070304, 0
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
0x180017d10  push    rbp
0x180017d12  sub     rsp, 20h
0x180017d16  mov     rbp, rdx
0x180017d19  mov     rax, [rcx]
0x180017d1c  mov     edx, [rax]
0x180017d1e  mov     [rbp+0A8h], rcx
0x180017d25  mov     [rbp+28h], edx
0x180017d28  mov     eax, [rbp+28h]
0x180017d2b  cmp     eax, 0E06D7363h
0x180017d30  jnz     short loc_180017D46
0x180017d32  mov     rdx, [rbp+0A8h]
0x180017d39  mov     ecx, [rbp+28h]
0x180017d3c  call    _XcptFilter_0
0x180017d41  mov     [rbp+30h], eax
0x180017d44  jmp     short loc_180017D4D
0x180017d46  mov     dword ptr [rbp+30h], 0
0x180017d4d  mov     eax, [rbp+30h]
0x180017d50  add     rsp, 20h
0x180017d54  pop     rbp
0x180017d55  retn
0x180017d57  push    rbp
0x180017d59  sub     rsp, 20h
0x180017d5d  mov     rbp, rdx
0x180017d60  mov     rax, [rcx]
0x180017d63  mov     edx, [rax]
0x180017d65  mov     [rbp+0B0h], rcx
0x180017d6c  mov     [rbp+38h], edx
0x180017d6f  mov     eax, [rbp+38h]
0x180017d72  cmp     eax, 0E06D7363h
0x180017d77  jnz     short loc_180017D8D
0x180017d79  mov     rdx, [rbp+0B0h]
0x180017d80  mov     ecx, [rbp+38h]
0x180017d83  call    _XcptFilter_0
0x180017d88  mov     [rbp+40h], eax
0x180017d8b  jmp     short loc_180017D94
0x180017d8d  mov     dword ptr [rbp+40h], 0
0x180017d94  mov     eax, [rbp+40h]
0x180017d97  add     rsp, 20h
0x180017d9b  pop     rbp
0x180017d9c  retn
0x180017d9e  push    rbp
0x180017da0  sub     rsp, 20h
0x180017da4  mov     rbp, rdx
0x180017da7  mov     rax, [rcx]
0x180017daa  mov     edx, [rax]
0x180017dac  mov     [rbp+0B8h], rcx
0x180017db3  mov     [rbp+48h], edx
0x180017db6  mov     eax, [rbp+48h]
0x180017db9  cmp     eax, 0E06D7363h
0x180017dbe  jnz     short loc_180017DD4
0x180017dc0  mov     rdx, [rbp+0B8h]
0x180017dc7  mov     ecx, [rbp+48h]
0x180017dca  call    _XcptFilter_0
0x180017dcf  mov     [rbp+50h], eax
0x180017dd2  jmp     short loc_180017DDB
0x180017dd4  mov     dword ptr [rbp+50h], 0
0x180017ddb  mov     eax, [rbp+50h]
0x180017dde  add     rsp, 20h
0x180017de2  pop     rbp
0x180017de3  retn
0x180017de5  push    rbp
0x180017de7  sub     rsp, 20h
0x180017deb  mov     rbp, rdx
0x180017dee  mov     rax, [rcx]
0x180017df1  mov     edx, [rax]
0x180017df3  mov     [rbp+0C0h], rcx
0x180017dfa  mov     [rbp+58h], edx
0x180017dfd  mov     eax, [rbp+58h]
0x180017e00  cmp     eax, 0E06D7363h
0x180017e05  jnz     short loc_180017E1B
0x180017e07  mov     rdx, [rbp+0C0h]
0x180017e0e  mov     ecx, [rbp+58h]
0x180017e11  call    _XcptFilter_0
0x180017e16  mov     [rbp+60h], eax
0x180017e19  jmp     short loc_180017E22
0x180017e1b  mov     dword ptr [rbp+60h], 0
0x180017e22  mov     eax, [rbp+60h]
0x180017e25  add     rsp, 20h
0x180017e29  pop     rbp
0x180017e2a  retn
0x180017e2c  push    rbp
0x180017e2e  sub     rsp, 20h
0x180017e32  mov     rbp, rdx
0x180017e35  mov     rax, [rcx]
0x180017e38  mov     edx, [rax]
0x180017e3a  mov     [rbp+0C8h], rcx
0x180017e41  mov     [rbp+68h], edx
0x180017e44  mov     eax, [rbp+68h]
0x180017e47  cmp     eax, 0E06D7363h
0x180017e4c  jnz     short loc_180017E62
0x180017e4e  mov     rdx, [rbp+0C8h]
0x180017e55  mov     ecx, [rbp+68h]
0x180017e58  call    _XcptFilter_0
0x180017e5d  mov     [rbp+70h], eax
0x180017e60  jmp     short loc_180017E69
0x180017e62  mov     dword ptr [rbp+70h], 0
0x180017e69  mov     eax, [rbp+70h]
0x180017e6c  add     rsp, 20h
0x180017e70  pop     rbp
0x180017e71  retn
0x180017e73  push    rbp
0x180017e75  sub     rsp, 20h
0x180017e79  mov     rbp, rdx
0x180017e7c  mov     rax, [rcx]
0x180017e7f  mov     edx, [rax]
0x180017e81  mov     [rbp+0D0h], rcx
0x180017e88  mov     [rbp+78h], edx
0x180017e8b  mov     eax, [rbp+78h]
0x180017e8e  cmp     eax, 0E06D7363h
0x180017e93  jnz     short loc_180017EAC
0x180017e95  mov     rdx, [rbp+0D0h]
0x180017e9c  mov     ecx, [rbp+78h]
0x180017e9f  call    _XcptFilter_0
0x180017ea4  mov     [rbp+80h], eax
0x180017eaa  jmp     short loc_180017EB6
0x180017eac  mov     dword ptr [rbp+80h], 0
0x180017eb6  mov     eax, [rbp+80h]
0x180017ebc  add     rsp, 20h
0x180017ec0  pop     rbp
0x180017ec1  retn
0x180017ec3  push    rbp
0x180017ec5  sub     rsp, 20h
0x180017ec9  mov     rbp, rdx
0x180017ecc  mov     rax, [rcx]
0x180017ecf  mov     edx, [rax]
0x180017ed1  mov     [rbp+0D8h], rcx
0x180017ed8  mov     [rbp+88h], edx
0x180017ede  mov     eax, [rbp+88h]
0x180017ee4  cmp     eax, 0E06D7363h
0x180017ee9  jnz     short loc_180017F05
0x180017eeb  mov     rdx, [rbp+0D8h]
0x180017ef2  mov     ecx, [rbp+88h]
0x180017ef8  call    _XcptFilter_0
0x180017efd  mov     [rbp+90h], eax
0x180017f03  jmp     short loc_180017F0F
0x180017f05  mov     dword ptr [rbp+90h], 0
0x180017f0f  mov     eax, [rbp+90h]
0x180017f15  add     rsp, 20h
0x180017f19  pop     rbp
0x180017f1a  retn
0x180017f1c  push    rbp
0x180017f1e  sub     rsp, 20h
0x180017f22  mov     rbp, rdx
0x180017f25  mov     rax, [rcx]
0x180017f28  mov     edx, [rax]
0x180017f2a  mov     [rbp+0E0h], rcx
0x180017f31  mov     [rbp+98h], edx
0x180017f37  mov     eax, [rbp+98h]
0x180017f3d  cmp     eax, 0E06D7363h
0x180017f42  jnz     short loc_180017F5E
0x180017f44  mov     rdx, [rbp+0E0h]
0x180017f4b  mov     ecx, [rbp+98h]
0x180017f51  call    _XcptFilter_0
0x180017f56  mov     [rbp+0A0h], eax
0x180017f5c  jmp     short loc_180017F68
0x180017f5e  mov     dword ptr [rbp+0A0h], 0
0x180017f68  mov     eax, [rbp+0A0h]
0x180017f6e  add     rsp, 20h
0x180017f72  pop     rbp
0x180017f73  retn
0x180017f75  push    rbp
0x180017f77  sub     rsp, 20h
0x180017f7b  mov     rbp, rdx
0x180017f7e  cmp     dword ptr [rbp+118h], 1
0x180017f85  ja      short loc_180017F91
0x180017f87  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
