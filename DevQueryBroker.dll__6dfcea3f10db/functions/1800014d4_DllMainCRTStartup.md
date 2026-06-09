# __DllMainCRTStartup

- ea: `0x1800014d4`
- end: `0x1800016e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x180001260`
- `0x1800014d4`
- `0x180001716`
- `0x180002974`
- `0x18000a210`

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
  if ( (_DWORD)fdwReason || dword_180011280 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180011284 = 1;
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
            if ( dword_180011284 )
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
0x1800014d4  mov     [rsp+lpvReserved], r8
0x1800014d9  mov     [rsp+arg_8], edx
0x1800014dd  mov     [rsp+arg_0], rcx
0x1800014e2  push    rbx
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  sub     rsp, 0F0h
0x1800014ec  mov     edi, edx
0x1800014ee  mov     rsi, rcx
0x1800014f1  mov     ebx, 1
0x1800014f6  cmp     edx, ebx
0x1800014f8  ja      short loc_180001500
0x1800014fa  mov     cs:__native_dllmain_reason, edx
0x180001500  test    edx, edx
0x180001502  jnz     short loc_180001517
0x180001504  cmp     cs:dword_180011280, edx
0x18000150a  jnz     short loc_180001517
0x18000150c  xor     ebx, ebx
0x18000150e  mov     [rsp+108h+var_E8], ebx
0x180001512  jmp     loc_1800016C4
0x180001517  lea     eax, [rdx-1]
0x18000151a  cmp     eax, 1
0x18000151d  ja      loc_1800015A4
0x180001523  mov     rax, cs:_pRawDllMain
0x18000152a  test    rax, rax
0x18000152d  jz      short loc_180001565
0x18000152f  cmp     edx, 1
0x180001532  jnz     short loc_18000153A
0x180001534  mov     cs:dword_180011284, edx
0x18000153a  mov     r8, [rsp+108h+lpvReserved]
0x180001542  call    cs:__guard_dispatch_icall_fptr
0x180001548  mov     ebx, eax
0x18000154a  mov     [rsp+108h+var_E8], eax
0x18000154e  jmp     short loc_180001565
0x180001550  xor     ebx, ebx
0x180001552  mov     [rsp+108h+var_E8], ebx
0x180001556  mov     edi, [rsp+108h+arg_8]
0x18000155d  mov     rsi, [rsp+108h+arg_0]
0x180001565  test    ebx, ebx
0x180001567  jz      loc_1800016C4
0x18000156d  mov     r8, [rsp+108h+lpvReserved]
0x180001575  mov     edx, edi
0x180001577  mov     rcx, rsi
0x18000157a  call    _CRT_INIT
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_18000159C
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  mov     rsi, [rsp+108h+arg_0]
0x18000159c  test    ebx, ebx
0x18000159e  jz      loc_1800016C4
0x1800015a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800015ac  mov     edx, edi; fdwReason
0x1800015ae  mov     rcx, rsi; hinstDLL
0x1800015b1  call    DllMain
0x1800015b6  mov     ebx, eax
0x1800015b8  mov     [rsp+108h+var_E8], eax
0x1800015bc  jmp     short loc_1800015D3
0x1800015be  xor     ebx, ebx
0x1800015c0  mov     [rsp+108h+var_E8], ebx
0x1800015c4  mov     edi, [rsp+108h+arg_8]
0x1800015cb  mov     rsi, [rsp+108h+arg_0]
0x1800015d3  cmp     edi, 1
0x1800015d6  jnz     short loc_18000164F
0x1800015d8  test    ebx, ebx
0x1800015da  jnz     short loc_18000164F
0x1800015dc  xor     r8d, r8d; lpvReserved
0x1800015df  xor     edx, edx; fdwReason
0x1800015e1  mov     rcx, rsi; hinstDLL
0x1800015e4  call    DllMain
0x1800015e9  jmp     short loc_1800015FE
0x1800015eb  mov     edi, [rsp+108h+arg_8]
0x1800015f2  mov     rsi, [rsp+108h+arg_0]
0x1800015fa  mov     ebx, [rsp+108h+var_E8]
0x1800015fe  xor     r8d, r8d
0x180001601  xor     edx, edx
0x180001603  mov     rcx, rsi
0x180001606  call    _CRT_INIT
0x18000160b  jmp     short loc_180001620
0x18000160d  mov     edi, [rsp+108h+arg_8]
0x180001614  mov     rsi, [rsp+108h+arg_0]
0x18000161c  mov     ebx, [rsp+108h+var_E8]
0x180001620  mov     rax, cs:_pRawDllMain
0x180001627  test    rax, rax
0x18000162a  jz      short loc_18000164F
0x18000162c  xor     r8d, r8d
0x18000162f  xor     edx, edx
0x180001631  mov     rcx, rsi
0x180001634  call    cs:__guard_dispatch_icall_fptr
0x18000163a  jmp     short loc_18000164F
0x18000163c  mov     edi, [rsp+108h+arg_8]
0x180001643  mov     rsi, [rsp+108h+arg_0]
0x18000164b  mov     ebx, [rsp+108h+var_E8]
0x18000164f  test    edi, edi
0x180001651  jz      short loc_180001658
0x180001653  cmp     edi, 3
0x180001656  jnz     short loc_1800016C4
0x180001658  mov     r8, [rsp+108h+lpvReserved]
0x180001660  mov     edx, edi
0x180001662  mov     rcx, rsi
0x180001665  call    _CRT_INIT
0x18000166a  mov     ebx, eax
0x18000166c  mov     [rsp+108h+var_E8], eax
0x180001670  jmp     short loc_180001687
0x180001672  xor     ebx, ebx
0x180001674  mov     [rsp+108h+var_E8], ebx
0x180001678  mov     edi, [rsp+108h+arg_8]
0x18000167f  mov     rsi, [rsp+108h+arg_0]
0x180001687  mov     rax, cs:_pRawDllMain
0x18000168e  test    rax, rax
0x180001691  jz      short loc_1800016C4
0x180001693  cmp     cs:dword_180011284, 0
0x18000169a  jz      short loc_1800016C4
0x18000169c  mov     r8, [rsp+108h+lpvReserved]
0x1800016a4  mov     edx, edi
0x1800016a6  mov     rcx, rsi
0x1800016a9  call    cs:__guard_dispatch_icall_fptr
0x1800016af  mov     ebx, eax
0x1800016b1  mov     [rsp+108h+var_E8], eax
0x1800016b5  jmp     short loc_1800016C4
0x1800016b7  xor     ebx, ebx
0x1800016b9  mov     [rsp+108h+var_E8], ebx
0x1800016bd  mov     edi, [rsp+108h+arg_8]
0x1800016c4  cmp     edi, 1
0x1800016c7  ja      short loc_1800016D3
0x1800016c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016d3  mov     eax, ebx
0x1800016d5  add     rsp, 0F0h
0x1800016dc  pop     rdi
0x1800016dd  pop     rsi
0x1800016de  pop     rbx
0x1800016df  retn
0x18000a2e0  push    rbp
0x18000a2e2  sub     rsp, 20h
0x18000a2e6  mov     rbp, rdx
0x18000a2e9  mov     rax, [rcx]
0x18000a2ec  mov     edx, [rax]
0x18000a2ee  mov     [rbp+0A8h], rcx
0x18000a2f5  mov     [rbp+28h], edx
0x18000a2f8  mov     eax, [rbp+28h]
0x18000a2fb  cmp     eax, 0E06D7363h
0x18000a300  jnz     short loc_18000A316
0x18000a302  mov     rdx, [rbp+0A8h]
0x18000a309  mov     ecx, [rbp+28h]
0x18000a30c  call    _XcptFilter_0
0x18000a311  mov     [rbp+30h], eax
0x18000a314  jmp     short loc_18000A31D
0x18000a316  mov     dword ptr [rbp+30h], 0
0x18000a31d  mov     eax, [rbp+30h]
0x18000a320  add     rsp, 20h
0x18000a324  pop     rbp
0x18000a325  retn
0x18000a327  push    rbp
0x18000a329  sub     rsp, 20h
0x18000a32d  mov     rbp, rdx
0x18000a330  mov     rax, [rcx]
0x18000a333  mov     edx, [rax]
0x18000a335  mov     [rbp+0B0h], rcx
0x18000a33c  mov     [rbp+38h], edx
0x18000a33f  mov     eax, [rbp+38h]
0x18000a342  cmp     eax, 0E06D7363h
0x18000a347  jnz     short loc_18000A35D
0x18000a349  mov     rdx, [rbp+0B0h]
0x18000a350  mov     ecx, [rbp+38h]
0x18000a353  call    _XcptFilter_0
0x18000a358  mov     [rbp+40h], eax
0x18000a35b  jmp     short loc_18000A364
0x18000a35d  mov     dword ptr [rbp+40h], 0
0x18000a364  mov     eax, [rbp+40h]
0x18000a367  add     rsp, 20h
0x18000a36b  pop     rbp
0x18000a36c  retn
0x18000a36e  push    rbp
0x18000a370  sub     rsp, 20h
0x18000a374  mov     rbp, rdx
0x18000a377  mov     rax, [rcx]
0x18000a37a  mov     edx, [rax]
0x18000a37c  mov     [rbp+0B8h], rcx
0x18000a383  mov     [rbp+48h], edx
0x18000a386  mov     eax, [rbp+48h]
0x18000a389  cmp     eax, 0E06D7363h
0x18000a38e  jnz     short loc_18000A3A4
0x18000a390  mov     rdx, [rbp+0B8h]
0x18000a397  mov     ecx, [rbp+48h]
0x18000a39a  call    _XcptFilter_0
0x18000a39f  mov     [rbp+50h], eax
0x18000a3a2  jmp     short loc_18000A3AB
0x18000a3a4  mov     dword ptr [rbp+50h], 0
0x18000a3ab  mov     eax, [rbp+50h]
0x18000a3ae  add     rsp, 20h
0x18000a3b2  pop     rbp
0x18000a3b3  retn
0x18000a3b5  push    rbp
0x18000a3b7  sub     rsp, 20h
0x18000a3bb  mov     rbp, rdx
0x18000a3be  mov     rax, [rcx]
0x18000a3c1  mov     edx, [rax]
0x18000a3c3  mov     [rbp+0C0h], rcx
0x18000a3ca  mov     [rbp+58h], edx
0x18000a3cd  mov     eax, [rbp+58h]
0x18000a3d0  cmp     eax, 0E06D7363h
0x18000a3d5  jnz     short loc_18000A3EB
0x18000a3d7  mov     rdx, [rbp+0C0h]
0x18000a3de  mov     ecx, [rbp+58h]
0x18000a3e1  call    _XcptFilter_0
0x18000a3e6  mov     [rbp+60h], eax
0x18000a3e9  jmp     short loc_18000A3F2
0x18000a3eb  mov     dword ptr [rbp+60h], 0
0x18000a3f2  mov     eax, [rbp+60h]
0x18000a3f5  add     rsp, 20h
0x18000a3f9  pop     rbp
0x18000a3fa  retn
0x18000a3fc  push    rbp
0x18000a3fe  sub     rsp, 20h
0x18000a402  mov     rbp, rdx
0x18000a405  mov     rax, [rcx]
0x18000a408  mov     edx, [rax]
0x18000a40a  mov     [rbp+0C8h], rcx
0x18000a411  mov     [rbp+68h], edx
0x18000a414  mov     eax, [rbp+68h]
0x18000a417  cmp     eax, 0E06D7363h
0x18000a41c  jnz     short loc_18000A432
0x18000a41e  mov     rdx, [rbp+0C8h]
0x18000a425  mov     ecx, [rbp+68h]
0x18000a428  call    _XcptFilter_0
0x18000a42d  mov     [rbp+70h], eax
0x18000a430  jmp     short loc_18000A439
0x18000a432  mov     dword ptr [rbp+70h], 0
0x18000a439  mov     eax, [rbp+70h]
0x18000a43c  add     rsp, 20h
0x18000a440  pop     rbp
0x18000a441  retn
0x18000a443  push    rbp
0x18000a445  sub     rsp, 20h
0x18000a449  mov     rbp, rdx
0x18000a44c  mov     rax, [rcx]
0x18000a44f  mov     edx, [rax]
0x18000a451  mov     [rbp+0D0h], rcx
0x18000a458  mov     [rbp+78h], edx
0x18000a45b  mov     eax, [rbp+78h]
0x18000a45e  cmp     eax, 0E06D7363h
0x18000a463  jnz     short loc_18000A47C
0x18000a465  mov     rdx, [rbp+0D0h]
0x18000a46c  mov     ecx, [rbp+78h]
0x18000a46f  call    _XcptFilter_0
0x18000a474  mov     [rbp+80h], eax
0x18000a47a  jmp     short loc_18000A486
0x18000a47c  mov     dword ptr [rbp+80h], 0
0x18000a486  mov     eax, [rbp+80h]
0x18000a48c  add     rsp, 20h
0x18000a490  pop     rbp
0x18000a491  retn
0x18000a493  push    rbp
0x18000a495  sub     rsp, 20h
0x18000a499  mov     rbp, rdx
0x18000a49c  mov     rax, [rcx]
0x18000a49f  mov     edx, [rax]
0x18000a4a1  mov     [rbp+0D8h], rcx
0x18000a4a8  mov     [rbp+88h], edx
0x18000a4ae  mov     eax, [rbp+88h]
0x18000a4b4  cmp     eax, 0E06D7363h
0x18000a4b9  jnz     short loc_18000A4D5
0x18000a4bb  mov     rdx, [rbp+0D8h]
0x18000a4c2  mov     ecx, [rbp+88h]
0x18000a4c8  call    _XcptFilter_0
0x18000a4cd  mov     [rbp+90h], eax
0x18000a4d3  jmp     short loc_18000A4DF
0x18000a4d5  mov     dword ptr [rbp+90h], 0
0x18000a4df  mov     eax, [rbp+90h]
0x18000a4e5  add     rsp, 20h
0x18000a4e9  pop     rbp
0x18000a4ea  retn
0x18000a4ec  push    rbp
0x18000a4ee  sub     rsp, 20h
0x18000a4f2  mov     rbp, rdx
0x18000a4f5  mov     rax, [rcx]
0x18000a4f8  mov     edx, [rax]
0x18000a4fa  mov     [rbp+0E0h], rcx
0x18000a501  mov     [rbp+98h], edx
0x18000a507  mov     eax, [rbp+98h]
0x18000a50d  cmp     eax, 0E06D7363h
0x18000a512  jnz     short loc_18000A52E
0x18000a514  mov     rdx, [rbp+0E0h]
0x18000a51b  mov     ecx, [rbp+98h]
0x18000a521  call    _XcptFilter_0
0x18000a526  mov     [rbp+0A0h], eax
0x18000a52c  jmp     short loc_18000A538
0x18000a52e  mov     dword ptr [rbp+0A0h], 0
0x18000a538  mov     eax, [rbp+0A0h]
0x18000a53e  add     rsp, 20h
0x18000a542  pop     rbp
0x18000a543  retn
0x18000a545  push    rbp
0x18000a547  sub     rsp, 20h
0x18000a54b  mov     rbp, rdx
0x18000a54e  cmp     dword ptr [rbp+118h], 1
0x18000a555  ja      short loc_18000A561
0x18000a557  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
