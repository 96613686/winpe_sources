# __DllMainCRTStartup

- ea: `0x1800024a4`
- end: `0x1800026b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002460`

## callees

- `0x180002230`
- `0x1800024a4`
- `0x180002b9e`
- `0x180006b40`
- `0x1800197d0`

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
  if ( (_DWORD)fdwReason || dword_180027504 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180027508 = 1;
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
            if ( dword_180027508 )
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
0x1800024a4  mov     [rsp+lpvReserved], r8
0x1800024a9  mov     [rsp+arg_8], edx
0x1800024ad  mov     [rsp+arg_0], rcx
0x1800024b2  push    rbx
0x1800024b3  push    rsi
0x1800024b4  push    rdi
0x1800024b5  sub     rsp, 0F0h
0x1800024bc  mov     edi, edx
0x1800024be  mov     rsi, rcx
0x1800024c1  mov     ebx, 1
0x1800024c6  cmp     edx, ebx
0x1800024c8  ja      short loc_1800024D0
0x1800024ca  mov     cs:__native_dllmain_reason, edx
0x1800024d0  test    edx, edx
0x1800024d2  jnz     short loc_1800024E7
0x1800024d4  cmp     cs:dword_180027504, edx
0x1800024da  jnz     short loc_1800024E7
0x1800024dc  xor     ebx, ebx
0x1800024de  mov     [rsp+108h+var_E8], ebx
0x1800024e2  jmp     loc_180002694
0x1800024e7  lea     eax, [rdx-1]
0x1800024ea  cmp     eax, 1
0x1800024ed  ja      loc_180002574
0x1800024f3  mov     rax, cs:_pRawDllMain
0x1800024fa  test    rax, rax
0x1800024fd  jz      short loc_180002535
0x1800024ff  cmp     edx, 1
0x180002502  jnz     short loc_18000250A
0x180002504  mov     cs:dword_180027508, edx
0x18000250a  mov     r8, [rsp+108h+lpvReserved]
0x180002512  call    cs:__guard_dispatch_icall_fptr
0x180002518  mov     ebx, eax
0x18000251a  mov     [rsp+108h+var_E8], eax
0x18000251e  jmp     short loc_180002535
0x180002520  xor     ebx, ebx
0x180002522  mov     [rsp+108h+var_E8], ebx
0x180002526  mov     edi, [rsp+108h+arg_8]
0x18000252d  mov     rsi, [rsp+108h+arg_0]
0x180002535  test    ebx, ebx
0x180002537  jz      loc_180002694
0x18000253d  mov     r8, [rsp+108h+lpvReserved]
0x180002545  mov     edx, edi
0x180002547  mov     rcx, rsi
0x18000254a  call    _CRT_INIT
0x18000254f  mov     ebx, eax
0x180002551  mov     [rsp+108h+var_E8], eax
0x180002555  jmp     short loc_18000256C
0x180002557  xor     ebx, ebx
0x180002559  mov     [rsp+108h+var_E8], ebx
0x18000255d  mov     edi, [rsp+108h+arg_8]
0x180002564  mov     rsi, [rsp+108h+arg_0]
0x18000256c  test    ebx, ebx
0x18000256e  jz      loc_180002694
0x180002574  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000257c  mov     edx, edi; fdwReason
0x18000257e  mov     rcx, rsi; hinstDLL
0x180002581  call    DllMain
0x180002586  mov     ebx, eax
0x180002588  mov     [rsp+108h+var_E8], eax
0x18000258c  jmp     short loc_1800025A3
0x18000258e  xor     ebx, ebx
0x180002590  mov     [rsp+108h+var_E8], ebx
0x180002594  mov     edi, [rsp+108h+arg_8]
0x18000259b  mov     rsi, [rsp+108h+arg_0]
0x1800025a3  cmp     edi, 1
0x1800025a6  jnz     short loc_18000261F
0x1800025a8  test    ebx, ebx
0x1800025aa  jnz     short loc_18000261F
0x1800025ac  xor     r8d, r8d; lpvReserved
0x1800025af  xor     edx, edx; fdwReason
0x1800025b1  mov     rcx, rsi; hinstDLL
0x1800025b4  call    DllMain
0x1800025b9  jmp     short loc_1800025CE
0x1800025bb  mov     edi, [rsp+108h+arg_8]
0x1800025c2  mov     rsi, [rsp+108h+arg_0]
0x1800025ca  mov     ebx, [rsp+108h+var_E8]
0x1800025ce  xor     r8d, r8d
0x1800025d1  xor     edx, edx
0x1800025d3  mov     rcx, rsi
0x1800025d6  call    _CRT_INIT
0x1800025db  jmp     short loc_1800025F0
0x1800025dd  mov     edi, [rsp+108h+arg_8]
0x1800025e4  mov     rsi, [rsp+108h+arg_0]
0x1800025ec  mov     ebx, [rsp+108h+var_E8]
0x1800025f0  mov     rax, cs:_pRawDllMain
0x1800025f7  test    rax, rax
0x1800025fa  jz      short loc_18000261F
0x1800025fc  xor     r8d, r8d
0x1800025ff  xor     edx, edx
0x180002601  mov     rcx, rsi
0x180002604  call    cs:__guard_dispatch_icall_fptr
0x18000260a  jmp     short loc_18000261F
0x18000260c  mov     edi, [rsp+108h+arg_8]
0x180002613  mov     rsi, [rsp+108h+arg_0]
0x18000261b  mov     ebx, [rsp+108h+var_E8]
0x18000261f  test    edi, edi
0x180002621  jz      short loc_180002628
0x180002623  cmp     edi, 3
0x180002626  jnz     short loc_180002694
0x180002628  mov     r8, [rsp+108h+lpvReserved]
0x180002630  mov     edx, edi
0x180002632  mov     rcx, rsi
0x180002635  call    _CRT_INIT
0x18000263a  mov     ebx, eax
0x18000263c  mov     [rsp+108h+var_E8], eax
0x180002640  jmp     short loc_180002657
0x180002642  xor     ebx, ebx
0x180002644  mov     [rsp+108h+var_E8], ebx
0x180002648  mov     edi, [rsp+108h+arg_8]
0x18000264f  mov     rsi, [rsp+108h+arg_0]
0x180002657  mov     rax, cs:_pRawDllMain
0x18000265e  test    rax, rax
0x180002661  jz      short loc_180002694
0x180002663  cmp     cs:dword_180027508, 0
0x18000266a  jz      short loc_180002694
0x18000266c  mov     r8, [rsp+108h+lpvReserved]
0x180002674  mov     edx, edi
0x180002676  mov     rcx, rsi
0x180002679  call    cs:__guard_dispatch_icall_fptr
0x18000267f  mov     ebx, eax
0x180002681  mov     [rsp+108h+var_E8], eax
0x180002685  jmp     short loc_180002694
0x180002687  xor     ebx, ebx
0x180002689  mov     [rsp+108h+var_E8], ebx
0x18000268d  mov     edi, [rsp+108h+arg_8]
0x180002694  cmp     edi, 1
0x180002697  ja      short loc_1800026A3
0x180002699  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800026a3  mov     eax, ebx
0x1800026a5  add     rsp, 0F0h
0x1800026ac  pop     rdi
0x1800026ad  pop     rsi
0x1800026ae  pop     rbx
0x1800026af  retn
0x180019873  push    rbp
0x180019875  sub     rsp, 20h
0x180019879  mov     rbp, rdx
0x18001987c  mov     rax, [rcx]
0x18001987f  mov     edx, [rax]
0x180019881  mov     [rbp+0A8h], rcx
0x180019888  mov     [rbp+28h], edx
0x18001988b  mov     eax, [rbp+28h]
0x18001988e  cmp     eax, 0E06D7363h
0x180019893  jnz     short loc_1800198A9
0x180019895  mov     rdx, [rbp+0A8h]
0x18001989c  mov     ecx, [rbp+28h]
0x18001989f  call    _XcptFilter_0
0x1800198a4  mov     [rbp+30h], eax
0x1800198a7  jmp     short loc_1800198B0
0x1800198a9  mov     dword ptr [rbp+30h], 0
0x1800198b0  mov     eax, [rbp+30h]
0x1800198b3  add     rsp, 20h
0x1800198b7  pop     rbp
0x1800198b8  retn
0x1800198ba  push    rbp
0x1800198bc  sub     rsp, 20h
0x1800198c0  mov     rbp, rdx
0x1800198c3  mov     rax, [rcx]
0x1800198c6  mov     edx, [rax]
0x1800198c8  mov     [rbp+0B0h], rcx
0x1800198cf  mov     [rbp+38h], edx
0x1800198d2  mov     eax, [rbp+38h]
0x1800198d5  cmp     eax, 0E06D7363h
0x1800198da  jnz     short loc_1800198F0
0x1800198dc  mov     rdx, [rbp+0B0h]
0x1800198e3  mov     ecx, [rbp+38h]
0x1800198e6  call    _XcptFilter_0
0x1800198eb  mov     [rbp+40h], eax
0x1800198ee  jmp     short loc_1800198F7
0x1800198f0  mov     dword ptr [rbp+40h], 0
0x1800198f7  mov     eax, [rbp+40h]
0x1800198fa  add     rsp, 20h
0x1800198fe  pop     rbp
0x1800198ff  retn
0x180019901  push    rbp
0x180019903  sub     rsp, 20h
0x180019907  mov     rbp, rdx
0x18001990a  mov     rax, [rcx]
0x18001990d  mov     edx, [rax]
0x18001990f  mov     [rbp+0B8h], rcx
0x180019916  mov     [rbp+48h], edx
0x180019919  mov     eax, [rbp+48h]
0x18001991c  cmp     eax, 0E06D7363h
0x180019921  jnz     short loc_180019937
0x180019923  mov     rdx, [rbp+0B8h]
0x18001992a  mov     ecx, [rbp+48h]
0x18001992d  call    _XcptFilter_0
0x180019932  mov     [rbp+50h], eax
0x180019935  jmp     short loc_18001993E
0x180019937  mov     dword ptr [rbp+50h], 0
0x18001993e  mov     eax, [rbp+50h]
0x180019941  add     rsp, 20h
0x180019945  pop     rbp
0x180019946  retn
0x180019948  push    rbp
0x18001994a  sub     rsp, 20h
0x18001994e  mov     rbp, rdx
0x180019951  mov     rax, [rcx]
0x180019954  mov     edx, [rax]
0x180019956  mov     [rbp+0C0h], rcx
0x18001995d  mov     [rbp+58h], edx
0x180019960  mov     eax, [rbp+58h]
0x180019963  cmp     eax, 0E06D7363h
0x180019968  jnz     short loc_18001997E
0x18001996a  mov     rdx, [rbp+0C0h]
0x180019971  mov     ecx, [rbp+58h]
0x180019974  call    _XcptFilter_0
0x180019979  mov     [rbp+60h], eax
0x18001997c  jmp     short loc_180019985
0x18001997e  mov     dword ptr [rbp+60h], 0
0x180019985  mov     eax, [rbp+60h]
0x180019988  add     rsp, 20h
0x18001998c  pop     rbp
0x18001998d  retn
0x18001998f  push    rbp
0x180019991  sub     rsp, 20h
0x180019995  mov     rbp, rdx
0x180019998  mov     rax, [rcx]
0x18001999b  mov     edx, [rax]
0x18001999d  mov     [rbp+0C8h], rcx
0x1800199a4  mov     [rbp+68h], edx
0x1800199a7  mov     eax, [rbp+68h]
0x1800199aa  cmp     eax, 0E06D7363h
0x1800199af  jnz     short loc_1800199C5
0x1800199b1  mov     rdx, [rbp+0C8h]
0x1800199b8  mov     ecx, [rbp+68h]
0x1800199bb  call    _XcptFilter_0
0x1800199c0  mov     [rbp+70h], eax
0x1800199c3  jmp     short loc_1800199CC
0x1800199c5  mov     dword ptr [rbp+70h], 0
0x1800199cc  mov     eax, [rbp+70h]
0x1800199cf  add     rsp, 20h
0x1800199d3  pop     rbp
0x1800199d4  retn
0x1800199d6  push    rbp
0x1800199d8  sub     rsp, 20h
0x1800199dc  mov     rbp, rdx
0x1800199df  mov     rax, [rcx]
0x1800199e2  mov     edx, [rax]
0x1800199e4  mov     [rbp+0D0h], rcx
0x1800199eb  mov     [rbp+78h], edx
0x1800199ee  mov     eax, [rbp+78h]
0x1800199f1  cmp     eax, 0E06D7363h
0x1800199f6  jnz     short loc_180019A0F
0x1800199f8  mov     rdx, [rbp+0D0h]
0x1800199ff  mov     ecx, [rbp+78h]
0x180019a02  call    _XcptFilter_0
0x180019a07  mov     [rbp+80h], eax
0x180019a0d  jmp     short loc_180019A19
0x180019a0f  mov     dword ptr [rbp+80h], 0
0x180019a19  mov     eax, [rbp+80h]
0x180019a1f  add     rsp, 20h
0x180019a23  pop     rbp
0x180019a24  retn
0x180019a26  push    rbp
0x180019a28  sub     rsp, 20h
0x180019a2c  mov     rbp, rdx
0x180019a2f  mov     rax, [rcx]
0x180019a32  mov     edx, [rax]
0x180019a34  mov     [rbp+0D8h], rcx
0x180019a3b  mov     [rbp+88h], edx
0x180019a41  mov     eax, [rbp+88h]
0x180019a47  cmp     eax, 0E06D7363h
0x180019a4c  jnz     short loc_180019A68
0x180019a4e  mov     rdx, [rbp+0D8h]
0x180019a55  mov     ecx, [rbp+88h]
0x180019a5b  call    _XcptFilter_0
0x180019a60  mov     [rbp+90h], eax
0x180019a66  jmp     short loc_180019A72
0x180019a68  mov     dword ptr [rbp+90h], 0
0x180019a72  mov     eax, [rbp+90h]
0x180019a78  add     rsp, 20h
0x180019a7c  pop     rbp
0x180019a7d  retn
0x180019a7f  push    rbp
0x180019a81  sub     rsp, 20h
0x180019a85  mov     rbp, rdx
0x180019a88  mov     rax, [rcx]
0x180019a8b  mov     edx, [rax]
0x180019a8d  mov     [rbp+0E0h], rcx
0x180019a94  mov     [rbp+98h], edx
0x180019a9a  mov     eax, [rbp+98h]
0x180019aa0  cmp     eax, 0E06D7363h
0x180019aa5  jnz     short loc_180019AC1
0x180019aa7  mov     rdx, [rbp+0E0h]
0x180019aae  mov     ecx, [rbp+98h]
0x180019ab4  call    _XcptFilter_0
0x180019ab9  mov     [rbp+0A0h], eax
0x180019abf  jmp     short loc_180019ACB
0x180019ac1  mov     dword ptr [rbp+0A0h], 0
0x180019acb  mov     eax, [rbp+0A0h]
0x180019ad1  add     rsp, 20h
0x180019ad5  pop     rbp
0x180019ad6  retn
0x180019ad8  push    rbp
0x180019ada  sub     rsp, 20h
0x180019ade  mov     rbp, rdx
0x180019ae1  cmp     dword ptr [rbp+118h], 1
0x180019ae8  ja      short loc_180019AF4
0x180019aea  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
