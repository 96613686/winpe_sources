# __DllMainCRTStartup

- ea: `0x1800013b4`
- end: `0x1800015c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001370`

## callees

- `0x180001040`
- `0x180001140`
- `0x1800013b4`
- `0x180001b65`
- `0x18002e0d0`

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
  if ( (_DWORD)fdwReason || dword_180044F20 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180044F24 = 1;
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
            if ( dword_180044F24 )
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
0x1800013b4  mov     [rsp+lpvReserved], r8
0x1800013b9  mov     [rsp+arg_8], edx
0x1800013bd  mov     [rsp+arg_0], rcx
0x1800013c2  push    rbx
0x1800013c3  push    rsi
0x1800013c4  push    rdi
0x1800013c5  sub     rsp, 0F0h
0x1800013cc  mov     edi, edx
0x1800013ce  mov     rsi, rcx
0x1800013d1  mov     ebx, 1
0x1800013d6  cmp     edx, ebx
0x1800013d8  ja      short loc_1800013E0
0x1800013da  mov     cs:__native_dllmain_reason, edx
0x1800013e0  test    edx, edx
0x1800013e2  jnz     short loc_1800013F7
0x1800013e4  cmp     cs:dword_180044F20, edx
0x1800013ea  jnz     short loc_1800013F7
0x1800013ec  xor     ebx, ebx
0x1800013ee  mov     [rsp+108h+var_E8], ebx
0x1800013f2  jmp     loc_1800015A4
0x1800013f7  lea     eax, [rdx-1]
0x1800013fa  cmp     eax, 1
0x1800013fd  ja      loc_180001484
0x180001403  mov     rax, cs:_pRawDllMain
0x18000140a  test    rax, rax
0x18000140d  jz      short loc_180001445
0x18000140f  cmp     edx, 1
0x180001412  jnz     short loc_18000141A
0x180001414  mov     cs:dword_180044F24, edx
0x18000141a  mov     r8, [rsp+108h+lpvReserved]
0x180001422  call    cs:__guard_dispatch_icall_fptr
0x180001428  mov     ebx, eax
0x18000142a  mov     [rsp+108h+var_E8], eax
0x18000142e  jmp     short loc_180001445
0x180001430  xor     ebx, ebx
0x180001432  mov     [rsp+108h+var_E8], ebx
0x180001436  mov     edi, [rsp+108h+arg_8]
0x18000143d  mov     rsi, [rsp+108h+arg_0]
0x180001445  test    ebx, ebx
0x180001447  jz      loc_1800015A4
0x18000144d  mov     r8, [rsp+108h+lpvReserved]
0x180001455  mov     edx, edi
0x180001457  mov     rcx, rsi
0x18000145a  call    _CRT_INIT
0x18000145f  mov     ebx, eax
0x180001461  mov     [rsp+108h+var_E8], eax
0x180001465  jmp     short loc_18000147C
0x180001467  xor     ebx, ebx
0x180001469  mov     [rsp+108h+var_E8], ebx
0x18000146d  mov     edi, [rsp+108h+arg_8]
0x180001474  mov     rsi, [rsp+108h+arg_0]
0x18000147c  test    ebx, ebx
0x18000147e  jz      loc_1800015A4
0x180001484  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000148c  mov     edx, edi; fdwReason
0x18000148e  mov     rcx, rsi; hinstDLL
0x180001491  call    DllMain
0x180001496  mov     ebx, eax
0x180001498  mov     [rsp+108h+var_E8], eax
0x18000149c  jmp     short loc_1800014B3
0x18000149e  xor     ebx, ebx
0x1800014a0  mov     [rsp+108h+var_E8], ebx
0x1800014a4  mov     edi, [rsp+108h+arg_8]
0x1800014ab  mov     rsi, [rsp+108h+arg_0]
0x1800014b3  cmp     edi, 1
0x1800014b6  jnz     short loc_18000152F
0x1800014b8  test    ebx, ebx
0x1800014ba  jnz     short loc_18000152F
0x1800014bc  xor     r8d, r8d; lpvReserved
0x1800014bf  xor     edx, edx; fdwReason
0x1800014c1  mov     rcx, rsi; hinstDLL
0x1800014c4  call    DllMain
0x1800014c9  jmp     short loc_1800014DE
0x1800014cb  mov     edi, [rsp+108h+arg_8]
0x1800014d2  mov     rsi, [rsp+108h+arg_0]
0x1800014da  mov     ebx, [rsp+108h+var_E8]
0x1800014de  xor     r8d, r8d
0x1800014e1  xor     edx, edx
0x1800014e3  mov     rcx, rsi
0x1800014e6  call    _CRT_INIT
0x1800014eb  jmp     short loc_180001500
0x1800014ed  mov     edi, [rsp+108h+arg_8]
0x1800014f4  mov     rsi, [rsp+108h+arg_0]
0x1800014fc  mov     ebx, [rsp+108h+var_E8]
0x180001500  mov     rax, cs:_pRawDllMain
0x180001507  test    rax, rax
0x18000150a  jz      short loc_18000152F
0x18000150c  xor     r8d, r8d
0x18000150f  xor     edx, edx
0x180001511  mov     rcx, rsi
0x180001514  call    cs:__guard_dispatch_icall_fptr
0x18000151a  jmp     short loc_18000152F
0x18000151c  mov     edi, [rsp+108h+arg_8]
0x180001523  mov     rsi, [rsp+108h+arg_0]
0x18000152b  mov     ebx, [rsp+108h+var_E8]
0x18000152f  test    edi, edi
0x180001531  jz      short loc_180001538
0x180001533  cmp     edi, 3
0x180001536  jnz     short loc_1800015A4
0x180001538  mov     r8, [rsp+108h+lpvReserved]
0x180001540  mov     edx, edi
0x180001542  mov     rcx, rsi
0x180001545  call    _CRT_INIT
0x18000154a  mov     ebx, eax
0x18000154c  mov     [rsp+108h+var_E8], eax
0x180001550  jmp     short loc_180001567
0x180001552  xor     ebx, ebx
0x180001554  mov     [rsp+108h+var_E8], ebx
0x180001558  mov     edi, [rsp+108h+arg_8]
0x18000155f  mov     rsi, [rsp+108h+arg_0]
0x180001567  mov     rax, cs:_pRawDllMain
0x18000156e  test    rax, rax
0x180001571  jz      short loc_1800015A4
0x180001573  cmp     cs:dword_180044F24, 0
0x18000157a  jz      short loc_1800015A4
0x18000157c  mov     r8, [rsp+108h+lpvReserved]
0x180001584  mov     edx, edi
0x180001586  mov     rcx, rsi
0x180001589  call    cs:__guard_dispatch_icall_fptr
0x18000158f  mov     ebx, eax
0x180001591  mov     [rsp+108h+var_E8], eax
0x180001595  jmp     short loc_1800015A4
0x180001597  xor     ebx, ebx
0x180001599  mov     [rsp+108h+var_E8], ebx
0x18000159d  mov     edi, [rsp+108h+arg_8]
0x1800015a4  cmp     edi, 1
0x1800015a7  ja      short loc_1800015B3
0x1800015a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015b3  mov     eax, ebx
0x1800015b5  add     rsp, 0F0h
0x1800015bc  pop     rdi
0x1800015bd  pop     rsi
0x1800015be  pop     rbx
0x1800015bf  retn
0x18002e1a4  push    rbp
0x18002e1a6  sub     rsp, 20h
0x18002e1aa  mov     rbp, rdx
0x18002e1ad  mov     rax, [rcx]
0x18002e1b0  mov     edx, [rax]
0x18002e1b2  mov     [rbp+0A8h], rcx
0x18002e1b9  mov     [rbp+28h], edx
0x18002e1bc  mov     eax, [rbp+28h]
0x18002e1bf  cmp     eax, 0E06D7363h
0x18002e1c4  jnz     short loc_18002E1DA
0x18002e1c6  mov     rdx, [rbp+0A8h]
0x18002e1cd  mov     ecx, [rbp+28h]
0x18002e1d0  call    _XcptFilter_0
0x18002e1d5  mov     [rbp+30h], eax
0x18002e1d8  jmp     short loc_18002E1E1
0x18002e1da  mov     dword ptr [rbp+30h], 0
0x18002e1e1  mov     eax, [rbp+30h]
0x18002e1e4  add     rsp, 20h
0x18002e1e8  pop     rbp
0x18002e1e9  retn
0x18002e1eb  push    rbp
0x18002e1ed  sub     rsp, 20h
0x18002e1f1  mov     rbp, rdx
0x18002e1f4  mov     rax, [rcx]
0x18002e1f7  mov     edx, [rax]
0x18002e1f9  mov     [rbp+0B0h], rcx
0x18002e200  mov     [rbp+38h], edx
0x18002e203  mov     eax, [rbp+38h]
0x18002e206  cmp     eax, 0E06D7363h
0x18002e20b  jnz     short loc_18002E221
0x18002e20d  mov     rdx, [rbp+0B0h]
0x18002e214  mov     ecx, [rbp+38h]
0x18002e217  call    _XcptFilter_0
0x18002e21c  mov     [rbp+40h], eax
0x18002e21f  jmp     short loc_18002E228
0x18002e221  mov     dword ptr [rbp+40h], 0
0x18002e228  mov     eax, [rbp+40h]
0x18002e22b  add     rsp, 20h
0x18002e22f  pop     rbp
0x18002e230  retn
0x18002e232  push    rbp
0x18002e234  sub     rsp, 20h
0x18002e238  mov     rbp, rdx
0x18002e23b  mov     rax, [rcx]
0x18002e23e  mov     edx, [rax]
0x18002e240  mov     [rbp+0B8h], rcx
0x18002e247  mov     [rbp+48h], edx
0x18002e24a  mov     eax, [rbp+48h]
0x18002e24d  cmp     eax, 0E06D7363h
0x18002e252  jnz     short loc_18002E268
0x18002e254  mov     rdx, [rbp+0B8h]
0x18002e25b  mov     ecx, [rbp+48h]
0x18002e25e  call    _XcptFilter_0
0x18002e263  mov     [rbp+50h], eax
0x18002e266  jmp     short loc_18002E26F
0x18002e268  mov     dword ptr [rbp+50h], 0
0x18002e26f  mov     eax, [rbp+50h]
0x18002e272  add     rsp, 20h
0x18002e276  pop     rbp
0x18002e277  retn
0x18002e279  push    rbp
0x18002e27b  sub     rsp, 20h
0x18002e27f  mov     rbp, rdx
0x18002e282  mov     rax, [rcx]
0x18002e285  mov     edx, [rax]
0x18002e287  mov     [rbp+0C0h], rcx
0x18002e28e  mov     [rbp+58h], edx
0x18002e291  mov     eax, [rbp+58h]
0x18002e294  cmp     eax, 0E06D7363h
0x18002e299  jnz     short loc_18002E2AF
0x18002e29b  mov     rdx, [rbp+0C0h]
0x18002e2a2  mov     ecx, [rbp+58h]
0x18002e2a5  call    _XcptFilter_0
0x18002e2aa  mov     [rbp+60h], eax
0x18002e2ad  jmp     short loc_18002E2B6
0x18002e2af  mov     dword ptr [rbp+60h], 0
0x18002e2b6  mov     eax, [rbp+60h]
0x18002e2b9  add     rsp, 20h
0x18002e2bd  pop     rbp
0x18002e2be  retn
0x18002e2c0  push    rbp
0x18002e2c2  sub     rsp, 20h
0x18002e2c6  mov     rbp, rdx
0x18002e2c9  mov     rax, [rcx]
0x18002e2cc  mov     edx, [rax]
0x18002e2ce  mov     [rbp+0C8h], rcx
0x18002e2d5  mov     [rbp+68h], edx
0x18002e2d8  mov     eax, [rbp+68h]
0x18002e2db  cmp     eax, 0E06D7363h
0x18002e2e0  jnz     short loc_18002E2F6
0x18002e2e2  mov     rdx, [rbp+0C8h]
0x18002e2e9  mov     ecx, [rbp+68h]
0x18002e2ec  call    _XcptFilter_0
0x18002e2f1  mov     [rbp+70h], eax
0x18002e2f4  jmp     short loc_18002E2FD
0x18002e2f6  mov     dword ptr [rbp+70h], 0
0x18002e2fd  mov     eax, [rbp+70h]
0x18002e300  add     rsp, 20h
0x18002e304  pop     rbp
0x18002e305  retn
0x18002e307  push    rbp
0x18002e309  sub     rsp, 20h
0x18002e30d  mov     rbp, rdx
0x18002e310  mov     rax, [rcx]
0x18002e313  mov     edx, [rax]
0x18002e315  mov     [rbp+0D0h], rcx
0x18002e31c  mov     [rbp+78h], edx
0x18002e31f  mov     eax, [rbp+78h]
0x18002e322  cmp     eax, 0E06D7363h
0x18002e327  jnz     short loc_18002E340
0x18002e329  mov     rdx, [rbp+0D0h]
0x18002e330  mov     ecx, [rbp+78h]
0x18002e333  call    _XcptFilter_0
0x18002e338  mov     [rbp+80h], eax
0x18002e33e  jmp     short loc_18002E34A
0x18002e340  mov     dword ptr [rbp+80h], 0
0x18002e34a  mov     eax, [rbp+80h]
0x18002e350  add     rsp, 20h
0x18002e354  pop     rbp
0x18002e355  retn
0x18002e357  push    rbp
0x18002e359  sub     rsp, 20h
0x18002e35d  mov     rbp, rdx
0x18002e360  mov     rax, [rcx]
0x18002e363  mov     edx, [rax]
0x18002e365  mov     [rbp+0D8h], rcx
0x18002e36c  mov     [rbp+88h], edx
0x18002e372  mov     eax, [rbp+88h]
0x18002e378  cmp     eax, 0E06D7363h
0x18002e37d  jnz     short loc_18002E399
0x18002e37f  mov     rdx, [rbp+0D8h]
0x18002e386  mov     ecx, [rbp+88h]
0x18002e38c  call    _XcptFilter_0
0x18002e391  mov     [rbp+90h], eax
0x18002e397  jmp     short loc_18002E3A3
0x18002e399  mov     dword ptr [rbp+90h], 0
0x18002e3a3  mov     eax, [rbp+90h]
0x18002e3a9  add     rsp, 20h
0x18002e3ad  pop     rbp
0x18002e3ae  retn
0x18002e3b0  push    rbp
0x18002e3b2  sub     rsp, 20h
0x18002e3b6  mov     rbp, rdx
0x18002e3b9  mov     rax, [rcx]
0x18002e3bc  mov     edx, [rax]
0x18002e3be  mov     [rbp+0E0h], rcx
0x18002e3c5  mov     [rbp+98h], edx
0x18002e3cb  mov     eax, [rbp+98h]
0x18002e3d1  cmp     eax, 0E06D7363h
0x18002e3d6  jnz     short loc_18002E3F2
0x18002e3d8  mov     rdx, [rbp+0E0h]
0x18002e3df  mov     ecx, [rbp+98h]
0x18002e3e5  call    _XcptFilter_0
0x18002e3ea  mov     [rbp+0A0h], eax
0x18002e3f0  jmp     short loc_18002E3FC
0x18002e3f2  mov     dword ptr [rbp+0A0h], 0
0x18002e3fc  mov     eax, [rbp+0A0h]
0x18002e402  add     rsp, 20h
0x18002e406  pop     rbp
0x18002e407  retn
0x18002e409  push    rbp
0x18002e40b  sub     rsp, 20h
0x18002e40f  mov     rbp, rdx
0x18002e412  cmp     dword ptr [rbp+118h], 1
0x18002e419  ja      short loc_18002E425
0x18002e41b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
