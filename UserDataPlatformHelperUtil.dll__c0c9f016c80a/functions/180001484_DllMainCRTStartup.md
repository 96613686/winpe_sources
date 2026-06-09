# __DllMainCRTStartup

- ea: `0x180001484`
- end: `0x180001690`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001210`
- `0x180001484`
- `0x1800018e1`
- `0x1800049cc`
- `0x18000a1d0`

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
  if ( (_DWORD)fdwReason || dword_1800112C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800112C4 = 1;
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
            if ( dword_1800112C4 )
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
0x180001484  mov     [rsp+lpvReserved], r8
0x180001489  mov     [rsp+arg_8], edx
0x18000148d  mov     [rsp+arg_0], rcx
0x180001492  push    rbx
0x180001493  push    rsi
0x180001494  push    rdi
0x180001495  sub     rsp, 0F0h
0x18000149c  mov     edi, edx
0x18000149e  mov     rsi, rcx
0x1800014a1  mov     ebx, 1
0x1800014a6  cmp     edx, ebx
0x1800014a8  ja      short loc_1800014B0
0x1800014aa  mov     cs:__native_dllmain_reason, edx
0x1800014b0  test    edx, edx
0x1800014b2  jnz     short loc_1800014C7
0x1800014b4  cmp     cs:dword_1800112C0, edx
0x1800014ba  jnz     short loc_1800014C7
0x1800014bc  xor     ebx, ebx
0x1800014be  mov     [rsp+108h+var_E8], ebx
0x1800014c2  jmp     loc_180001674
0x1800014c7  lea     eax, [rdx-1]
0x1800014ca  cmp     eax, 1
0x1800014cd  ja      loc_180001554
0x1800014d3  mov     rax, cs:_pRawDllMain
0x1800014da  test    rax, rax
0x1800014dd  jz      short loc_180001515
0x1800014df  cmp     edx, 1
0x1800014e2  jnz     short loc_1800014EA
0x1800014e4  mov     cs:dword_1800112C4, edx
0x1800014ea  mov     r8, [rsp+108h+lpvReserved]
0x1800014f2  call    cs:__guard_dispatch_icall_fptr
0x1800014f8  mov     ebx, eax
0x1800014fa  mov     [rsp+108h+var_E8], eax
0x1800014fe  jmp     short loc_180001515
0x180001500  xor     ebx, ebx
0x180001502  mov     [rsp+108h+var_E8], ebx
0x180001506  mov     edi, [rsp+108h+arg_8]
0x18000150d  mov     rsi, [rsp+108h+arg_0]
0x180001515  test    ebx, ebx
0x180001517  jz      loc_180001674
0x18000151d  mov     r8, [rsp+108h+lpvReserved]
0x180001525  mov     edx, edi
0x180001527  mov     rcx, rsi
0x18000152a  call    _CRT_INIT
0x18000152f  mov     ebx, eax
0x180001531  mov     [rsp+108h+var_E8], eax
0x180001535  jmp     short loc_18000154C
0x180001537  xor     ebx, ebx
0x180001539  mov     [rsp+108h+var_E8], ebx
0x18000153d  mov     edi, [rsp+108h+arg_8]
0x180001544  mov     rsi, [rsp+108h+arg_0]
0x18000154c  test    ebx, ebx
0x18000154e  jz      loc_180001674
0x180001554  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000155c  mov     edx, edi; fdwReason
0x18000155e  mov     rcx, rsi; hinstDLL
0x180001561  call    DllMain
0x180001566  mov     ebx, eax
0x180001568  mov     [rsp+108h+var_E8], eax
0x18000156c  jmp     short loc_180001583
0x18000156e  xor     ebx, ebx
0x180001570  mov     [rsp+108h+var_E8], ebx
0x180001574  mov     edi, [rsp+108h+arg_8]
0x18000157b  mov     rsi, [rsp+108h+arg_0]
0x180001583  cmp     edi, 1
0x180001586  jnz     short loc_1800015FF
0x180001588  test    ebx, ebx
0x18000158a  jnz     short loc_1800015FF
0x18000158c  xor     r8d, r8d; lpvReserved
0x18000158f  xor     edx, edx; fdwReason
0x180001591  mov     rcx, rsi; hinstDLL
0x180001594  call    DllMain
0x180001599  jmp     short loc_1800015AE
0x18000159b  mov     edi, [rsp+108h+arg_8]
0x1800015a2  mov     rsi, [rsp+108h+arg_0]
0x1800015aa  mov     ebx, [rsp+108h+var_E8]
0x1800015ae  xor     r8d, r8d
0x1800015b1  xor     edx, edx
0x1800015b3  mov     rcx, rsi
0x1800015b6  call    _CRT_INIT
0x1800015bb  jmp     short loc_1800015D0
0x1800015bd  mov     edi, [rsp+108h+arg_8]
0x1800015c4  mov     rsi, [rsp+108h+arg_0]
0x1800015cc  mov     ebx, [rsp+108h+var_E8]
0x1800015d0  mov     rax, cs:_pRawDllMain
0x1800015d7  test    rax, rax
0x1800015da  jz      short loc_1800015FF
0x1800015dc  xor     r8d, r8d
0x1800015df  xor     edx, edx
0x1800015e1  mov     rcx, rsi
0x1800015e4  call    cs:__guard_dispatch_icall_fptr
0x1800015ea  jmp     short loc_1800015FF
0x1800015ec  mov     edi, [rsp+108h+arg_8]
0x1800015f3  mov     rsi, [rsp+108h+arg_0]
0x1800015fb  mov     ebx, [rsp+108h+var_E8]
0x1800015ff  test    edi, edi
0x180001601  jz      short loc_180001608
0x180001603  cmp     edi, 3
0x180001606  jnz     short loc_180001674
0x180001608  mov     r8, [rsp+108h+lpvReserved]
0x180001610  mov     edx, edi
0x180001612  mov     rcx, rsi
0x180001615  call    _CRT_INIT
0x18000161a  mov     ebx, eax
0x18000161c  mov     [rsp+108h+var_E8], eax
0x180001620  jmp     short loc_180001637
0x180001622  xor     ebx, ebx
0x180001624  mov     [rsp+108h+var_E8], ebx
0x180001628  mov     edi, [rsp+108h+arg_8]
0x18000162f  mov     rsi, [rsp+108h+arg_0]
0x180001637  mov     rax, cs:_pRawDllMain
0x18000163e  test    rax, rax
0x180001641  jz      short loc_180001674
0x180001643  cmp     cs:dword_1800112C4, 0
0x18000164a  jz      short loc_180001674
0x18000164c  mov     r8, [rsp+108h+lpvReserved]
0x180001654  mov     edx, edi
0x180001656  mov     rcx, rsi
0x180001659  call    cs:__guard_dispatch_icall_fptr
0x18000165f  mov     ebx, eax
0x180001661  mov     [rsp+108h+var_E8], eax
0x180001665  jmp     short loc_180001674
0x180001667  xor     ebx, ebx
0x180001669  mov     [rsp+108h+var_E8], ebx
0x18000166d  mov     edi, [rsp+108h+arg_8]
0x180001674  cmp     edi, 1
0x180001677  ja      short loc_180001683
0x180001679  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001683  mov     eax, ebx
0x180001685  add     rsp, 0F0h
0x18000168c  pop     rdi
0x18000168d  pop     rsi
0x18000168e  pop     rbx
0x18000168f  retn
0x18000a240  push    rbp
0x18000a242  sub     rsp, 20h
0x18000a246  mov     rbp, rdx
0x18000a249  mov     rax, [rcx]
0x18000a24c  mov     edx, [rax]
0x18000a24e  mov     [rbp+0A8h], rcx
0x18000a255  mov     [rbp+28h], edx
0x18000a258  mov     eax, [rbp+28h]
0x18000a25b  cmp     eax, 0E06D7363h
0x18000a260  jnz     short loc_18000A276
0x18000a262  mov     rdx, [rbp+0A8h]
0x18000a269  mov     ecx, [rbp+28h]
0x18000a26c  call    _XcptFilter_0
0x18000a271  mov     [rbp+30h], eax
0x18000a274  jmp     short loc_18000A27D
0x18000a276  mov     dword ptr [rbp+30h], 0
0x18000a27d  mov     eax, [rbp+30h]
0x18000a280  add     rsp, 20h
0x18000a284  pop     rbp
0x18000a285  retn
0x18000a287  push    rbp
0x18000a289  sub     rsp, 20h
0x18000a28d  mov     rbp, rdx
0x18000a290  mov     rax, [rcx]
0x18000a293  mov     edx, [rax]
0x18000a295  mov     [rbp+0B0h], rcx
0x18000a29c  mov     [rbp+38h], edx
0x18000a29f  mov     eax, [rbp+38h]
0x18000a2a2  cmp     eax, 0E06D7363h
0x18000a2a7  jnz     short loc_18000A2BD
0x18000a2a9  mov     rdx, [rbp+0B0h]
0x18000a2b0  mov     ecx, [rbp+38h]
0x18000a2b3  call    _XcptFilter_0
0x18000a2b8  mov     [rbp+40h], eax
0x18000a2bb  jmp     short loc_18000A2C4
0x18000a2bd  mov     dword ptr [rbp+40h], 0
0x18000a2c4  mov     eax, [rbp+40h]
0x18000a2c7  add     rsp, 20h
0x18000a2cb  pop     rbp
0x18000a2cc  retn
0x18000a2ce  push    rbp
0x18000a2d0  sub     rsp, 20h
0x18000a2d4  mov     rbp, rdx
0x18000a2d7  mov     rax, [rcx]
0x18000a2da  mov     edx, [rax]
0x18000a2dc  mov     [rbp+0B8h], rcx
0x18000a2e3  mov     [rbp+48h], edx
0x18000a2e6  mov     eax, [rbp+48h]
0x18000a2e9  cmp     eax, 0E06D7363h
0x18000a2ee  jnz     short loc_18000A304
0x18000a2f0  mov     rdx, [rbp+0B8h]
0x18000a2f7  mov     ecx, [rbp+48h]
0x18000a2fa  call    _XcptFilter_0
0x18000a2ff  mov     [rbp+50h], eax
0x18000a302  jmp     short loc_18000A30B
0x18000a304  mov     dword ptr [rbp+50h], 0
0x18000a30b  mov     eax, [rbp+50h]
0x18000a30e  add     rsp, 20h
0x18000a312  pop     rbp
0x18000a313  retn
0x18000a315  push    rbp
0x18000a317  sub     rsp, 20h
0x18000a31b  mov     rbp, rdx
0x18000a31e  mov     rax, [rcx]
0x18000a321  mov     edx, [rax]
0x18000a323  mov     [rbp+0C0h], rcx
0x18000a32a  mov     [rbp+58h], edx
0x18000a32d  mov     eax, [rbp+58h]
0x18000a330  cmp     eax, 0E06D7363h
0x18000a335  jnz     short loc_18000A34B
0x18000a337  mov     rdx, [rbp+0C0h]
0x18000a33e  mov     ecx, [rbp+58h]
0x18000a341  call    _XcptFilter_0
0x18000a346  mov     [rbp+60h], eax
0x18000a349  jmp     short loc_18000A352
0x18000a34b  mov     dword ptr [rbp+60h], 0
0x18000a352  mov     eax, [rbp+60h]
0x18000a355  add     rsp, 20h
0x18000a359  pop     rbp
0x18000a35a  retn
0x18000a35c  push    rbp
0x18000a35e  sub     rsp, 20h
0x18000a362  mov     rbp, rdx
0x18000a365  mov     rax, [rcx]
0x18000a368  mov     edx, [rax]
0x18000a36a  mov     [rbp+0C8h], rcx
0x18000a371  mov     [rbp+68h], edx
0x18000a374  mov     eax, [rbp+68h]
0x18000a377  cmp     eax, 0E06D7363h
0x18000a37c  jnz     short loc_18000A392
0x18000a37e  mov     rdx, [rbp+0C8h]
0x18000a385  mov     ecx, [rbp+68h]
0x18000a388  call    _XcptFilter_0
0x18000a38d  mov     [rbp+70h], eax
0x18000a390  jmp     short loc_18000A399
0x18000a392  mov     dword ptr [rbp+70h], 0
0x18000a399  mov     eax, [rbp+70h]
0x18000a39c  add     rsp, 20h
0x18000a3a0  pop     rbp
0x18000a3a1  retn
0x18000a3a3  push    rbp
0x18000a3a5  sub     rsp, 20h
0x18000a3a9  mov     rbp, rdx
0x18000a3ac  mov     rax, [rcx]
0x18000a3af  mov     edx, [rax]
0x18000a3b1  mov     [rbp+0D0h], rcx
0x18000a3b8  mov     [rbp+78h], edx
0x18000a3bb  mov     eax, [rbp+78h]
0x18000a3be  cmp     eax, 0E06D7363h
0x18000a3c3  jnz     short loc_18000A3DC
0x18000a3c5  mov     rdx, [rbp+0D0h]
0x18000a3cc  mov     ecx, [rbp+78h]
0x18000a3cf  call    _XcptFilter_0
0x18000a3d4  mov     [rbp+80h], eax
0x18000a3da  jmp     short loc_18000A3E6
0x18000a3dc  mov     dword ptr [rbp+80h], 0
0x18000a3e6  mov     eax, [rbp+80h]
0x18000a3ec  add     rsp, 20h
0x18000a3f0  pop     rbp
0x18000a3f1  retn
0x18000a3f3  push    rbp
0x18000a3f5  sub     rsp, 20h
0x18000a3f9  mov     rbp, rdx
0x18000a3fc  mov     rax, [rcx]
0x18000a3ff  mov     edx, [rax]
0x18000a401  mov     [rbp+0D8h], rcx
0x18000a408  mov     [rbp+88h], edx
0x18000a40e  mov     eax, [rbp+88h]
0x18000a414  cmp     eax, 0E06D7363h
0x18000a419  jnz     short loc_18000A435
0x18000a41b  mov     rdx, [rbp+0D8h]
0x18000a422  mov     ecx, [rbp+88h]
0x18000a428  call    _XcptFilter_0
0x18000a42d  mov     [rbp+90h], eax
0x18000a433  jmp     short loc_18000A43F
0x18000a435  mov     dword ptr [rbp+90h], 0
0x18000a43f  mov     eax, [rbp+90h]
0x18000a445  add     rsp, 20h
0x18000a449  pop     rbp
0x18000a44a  retn
0x18000a44c  push    rbp
0x18000a44e  sub     rsp, 20h
0x18000a452  mov     rbp, rdx
0x18000a455  mov     rax, [rcx]
0x18000a458  mov     edx, [rax]
0x18000a45a  mov     [rbp+0E0h], rcx
0x18000a461  mov     [rbp+98h], edx
0x18000a467  mov     eax, [rbp+98h]
0x18000a46d  cmp     eax, 0E06D7363h
0x18000a472  jnz     short loc_18000A48E
0x18000a474  mov     rdx, [rbp+0E0h]
0x18000a47b  mov     ecx, [rbp+98h]
0x18000a481  call    _XcptFilter_0
0x18000a486  mov     [rbp+0A0h], eax
0x18000a48c  jmp     short loc_18000A498
0x18000a48e  mov     dword ptr [rbp+0A0h], 0
0x18000a498  mov     eax, [rbp+0A0h]
0x18000a49e  add     rsp, 20h
0x18000a4a2  pop     rbp
0x18000a4a3  retn
0x18000a4a5  push    rbp
0x18000a4a7  sub     rsp, 20h
0x18000a4ab  mov     rbp, rdx
0x18000a4ae  cmp     dword ptr [rbp+118h], 1
0x18000a4b5  ja      short loc_18000A4C1
0x18000a4b7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
