# __DllMainCRTStartup

- ea: `0x180002374`
- end: `0x180002580`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x180002100`
- `0x180002374`
- `0x18000277e`
- `0x1800079b4`
- `0x18000c5a0`

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
  if ( (_DWORD)fdwReason || dword_1800153DC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800153E0 = 1;
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
            if ( dword_1800153E0 )
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
0x180002374  mov     [rsp+lpvReserved], r8
0x180002379  mov     [rsp+arg_8], edx
0x18000237d  mov     [rsp+arg_0], rcx
0x180002382  push    rbx
0x180002383  push    rsi
0x180002384  push    rdi
0x180002385  sub     rsp, 0F0h
0x18000238c  mov     edi, edx
0x18000238e  mov     rsi, rcx
0x180002391  mov     ebx, 1
0x180002396  cmp     edx, ebx
0x180002398  ja      short loc_1800023A0
0x18000239a  mov     cs:__native_dllmain_reason, edx
0x1800023a0  test    edx, edx
0x1800023a2  jnz     short loc_1800023B7
0x1800023a4  cmp     cs:dword_1800153DC, edx
0x1800023aa  jnz     short loc_1800023B7
0x1800023ac  xor     ebx, ebx
0x1800023ae  mov     [rsp+108h+var_E8], ebx
0x1800023b2  jmp     loc_180002564
0x1800023b7  lea     eax, [rdx-1]
0x1800023ba  cmp     eax, 1
0x1800023bd  ja      loc_180002444
0x1800023c3  mov     rax, cs:_pRawDllMain
0x1800023ca  test    rax, rax
0x1800023cd  jz      short loc_180002405
0x1800023cf  cmp     edx, 1
0x1800023d2  jnz     short loc_1800023DA
0x1800023d4  mov     cs:dword_1800153E0, edx
0x1800023da  mov     r8, [rsp+108h+lpvReserved]
0x1800023e2  call    cs:__guard_dispatch_icall_fptr
0x1800023e8  mov     ebx, eax
0x1800023ea  mov     [rsp+108h+var_E8], eax
0x1800023ee  jmp     short loc_180002405
0x1800023f0  xor     ebx, ebx
0x1800023f2  mov     [rsp+108h+var_E8], ebx
0x1800023f6  mov     edi, [rsp+108h+arg_8]
0x1800023fd  mov     rsi, [rsp+108h+arg_0]
0x180002405  test    ebx, ebx
0x180002407  jz      loc_180002564
0x18000240d  mov     r8, [rsp+108h+lpvReserved]
0x180002415  mov     edx, edi
0x180002417  mov     rcx, rsi
0x18000241a  call    _CRT_INIT
0x18000241f  mov     ebx, eax
0x180002421  mov     [rsp+108h+var_E8], eax
0x180002425  jmp     short loc_18000243C
0x180002427  xor     ebx, ebx
0x180002429  mov     [rsp+108h+var_E8], ebx
0x18000242d  mov     edi, [rsp+108h+arg_8]
0x180002434  mov     rsi, [rsp+108h+arg_0]
0x18000243c  test    ebx, ebx
0x18000243e  jz      loc_180002564
0x180002444  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000244c  mov     edx, edi; fdwReason
0x18000244e  mov     rcx, rsi; hinstDLL
0x180002451  call    DllMain
0x180002456  mov     ebx, eax
0x180002458  mov     [rsp+108h+var_E8], eax
0x18000245c  jmp     short loc_180002473
0x18000245e  xor     ebx, ebx
0x180002460  mov     [rsp+108h+var_E8], ebx
0x180002464  mov     edi, [rsp+108h+arg_8]
0x18000246b  mov     rsi, [rsp+108h+arg_0]
0x180002473  cmp     edi, 1
0x180002476  jnz     short loc_1800024EF
0x180002478  test    ebx, ebx
0x18000247a  jnz     short loc_1800024EF
0x18000247c  xor     r8d, r8d; lpvReserved
0x18000247f  xor     edx, edx; fdwReason
0x180002481  mov     rcx, rsi; hinstDLL
0x180002484  call    DllMain
0x180002489  jmp     short loc_18000249E
0x18000248b  mov     edi, [rsp+108h+arg_8]
0x180002492  mov     rsi, [rsp+108h+arg_0]
0x18000249a  mov     ebx, [rsp+108h+var_E8]
0x18000249e  xor     r8d, r8d
0x1800024a1  xor     edx, edx
0x1800024a3  mov     rcx, rsi
0x1800024a6  call    _CRT_INIT
0x1800024ab  jmp     short loc_1800024C0
0x1800024ad  mov     edi, [rsp+108h+arg_8]
0x1800024b4  mov     rsi, [rsp+108h+arg_0]
0x1800024bc  mov     ebx, [rsp+108h+var_E8]
0x1800024c0  mov     rax, cs:_pRawDllMain
0x1800024c7  test    rax, rax
0x1800024ca  jz      short loc_1800024EF
0x1800024cc  xor     r8d, r8d
0x1800024cf  xor     edx, edx
0x1800024d1  mov     rcx, rsi
0x1800024d4  call    cs:__guard_dispatch_icall_fptr
0x1800024da  jmp     short loc_1800024EF
0x1800024dc  mov     edi, [rsp+108h+arg_8]
0x1800024e3  mov     rsi, [rsp+108h+arg_0]
0x1800024eb  mov     ebx, [rsp+108h+var_E8]
0x1800024ef  test    edi, edi
0x1800024f1  jz      short loc_1800024F8
0x1800024f3  cmp     edi, 3
0x1800024f6  jnz     short loc_180002564
0x1800024f8  mov     r8, [rsp+108h+lpvReserved]
0x180002500  mov     edx, edi
0x180002502  mov     rcx, rsi
0x180002505  call    _CRT_INIT
0x18000250a  mov     ebx, eax
0x18000250c  mov     [rsp+108h+var_E8], eax
0x180002510  jmp     short loc_180002527
0x180002512  xor     ebx, ebx
0x180002514  mov     [rsp+108h+var_E8], ebx
0x180002518  mov     edi, [rsp+108h+arg_8]
0x18000251f  mov     rsi, [rsp+108h+arg_0]
0x180002527  mov     rax, cs:_pRawDllMain
0x18000252e  test    rax, rax
0x180002531  jz      short loc_180002564
0x180002533  cmp     cs:dword_1800153E0, 0
0x18000253a  jz      short loc_180002564
0x18000253c  mov     r8, [rsp+108h+lpvReserved]
0x180002544  mov     edx, edi
0x180002546  mov     rcx, rsi
0x180002549  call    cs:__guard_dispatch_icall_fptr
0x18000254f  mov     ebx, eax
0x180002551  mov     [rsp+108h+var_E8], eax
0x180002555  jmp     short loc_180002564
0x180002557  xor     ebx, ebx
0x180002559  mov     [rsp+108h+var_E8], ebx
0x18000255d  mov     edi, [rsp+108h+arg_8]
0x180002564  cmp     edi, 1
0x180002567  ja      short loc_180002573
0x180002569  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002573  mov     eax, ebx
0x180002575  add     rsp, 0F0h
0x18000257c  pop     rdi
0x18000257d  pop     rsi
0x18000257e  pop     rbx
0x18000257f  retn
0x18000c643  push    rbp
0x18000c645  sub     rsp, 20h
0x18000c649  mov     rbp, rdx
0x18000c64c  mov     rax, [rcx]
0x18000c64f  mov     edx, [rax]
0x18000c651  mov     [rbp+0A8h], rcx
0x18000c658  mov     [rbp+28h], edx
0x18000c65b  mov     eax, [rbp+28h]
0x18000c65e  cmp     eax, 0E06D7363h
0x18000c663  jnz     short loc_18000C679
0x18000c665  mov     rdx, [rbp+0A8h]
0x18000c66c  mov     ecx, [rbp+28h]
0x18000c66f  call    _XcptFilter_0
0x18000c674  mov     [rbp+30h], eax
0x18000c677  jmp     short loc_18000C680
0x18000c679  mov     dword ptr [rbp+30h], 0
0x18000c680  mov     eax, [rbp+30h]
0x18000c683  add     rsp, 20h
0x18000c687  pop     rbp
0x18000c688  retn
0x18000c68a  push    rbp
0x18000c68c  sub     rsp, 20h
0x18000c690  mov     rbp, rdx
0x18000c693  mov     rax, [rcx]
0x18000c696  mov     edx, [rax]
0x18000c698  mov     [rbp+0B0h], rcx
0x18000c69f  mov     [rbp+38h], edx
0x18000c6a2  mov     eax, [rbp+38h]
0x18000c6a5  cmp     eax, 0E06D7363h
0x18000c6aa  jnz     short loc_18000C6C0
0x18000c6ac  mov     rdx, [rbp+0B0h]
0x18000c6b3  mov     ecx, [rbp+38h]
0x18000c6b6  call    _XcptFilter_0
0x18000c6bb  mov     [rbp+40h], eax
0x18000c6be  jmp     short loc_18000C6C7
0x18000c6c0  mov     dword ptr [rbp+40h], 0
0x18000c6c7  mov     eax, [rbp+40h]
0x18000c6ca  add     rsp, 20h
0x18000c6ce  pop     rbp
0x18000c6cf  retn
0x18000c6d1  push    rbp
0x18000c6d3  sub     rsp, 20h
0x18000c6d7  mov     rbp, rdx
0x18000c6da  mov     rax, [rcx]
0x18000c6dd  mov     edx, [rax]
0x18000c6df  mov     [rbp+0B8h], rcx
0x18000c6e6  mov     [rbp+48h], edx
0x18000c6e9  mov     eax, [rbp+48h]
0x18000c6ec  cmp     eax, 0E06D7363h
0x18000c6f1  jnz     short loc_18000C707
0x18000c6f3  mov     rdx, [rbp+0B8h]
0x18000c6fa  mov     ecx, [rbp+48h]
0x18000c6fd  call    _XcptFilter_0
0x18000c702  mov     [rbp+50h], eax
0x18000c705  jmp     short loc_18000C70E
0x18000c707  mov     dword ptr [rbp+50h], 0
0x18000c70e  mov     eax, [rbp+50h]
0x18000c711  add     rsp, 20h
0x18000c715  pop     rbp
0x18000c716  retn
0x18000c718  push    rbp
0x18000c71a  sub     rsp, 20h
0x18000c71e  mov     rbp, rdx
0x18000c721  mov     rax, [rcx]
0x18000c724  mov     edx, [rax]
0x18000c726  mov     [rbp+0C0h], rcx
0x18000c72d  mov     [rbp+58h], edx
0x18000c730  mov     eax, [rbp+58h]
0x18000c733  cmp     eax, 0E06D7363h
0x18000c738  jnz     short loc_18000C74E
0x18000c73a  mov     rdx, [rbp+0C0h]
0x18000c741  mov     ecx, [rbp+58h]
0x18000c744  call    _XcptFilter_0
0x18000c749  mov     [rbp+60h], eax
0x18000c74c  jmp     short loc_18000C755
0x18000c74e  mov     dword ptr [rbp+60h], 0
0x18000c755  mov     eax, [rbp+60h]
0x18000c758  add     rsp, 20h
0x18000c75c  pop     rbp
0x18000c75d  retn
0x18000c75f  push    rbp
0x18000c761  sub     rsp, 20h
0x18000c765  mov     rbp, rdx
0x18000c768  mov     rax, [rcx]
0x18000c76b  mov     edx, [rax]
0x18000c76d  mov     [rbp+0C8h], rcx
0x18000c774  mov     [rbp+68h], edx
0x18000c777  mov     eax, [rbp+68h]
0x18000c77a  cmp     eax, 0E06D7363h
0x18000c77f  jnz     short loc_18000C795
0x18000c781  mov     rdx, [rbp+0C8h]
0x18000c788  mov     ecx, [rbp+68h]
0x18000c78b  call    _XcptFilter_0
0x18000c790  mov     [rbp+70h], eax
0x18000c793  jmp     short loc_18000C79C
0x18000c795  mov     dword ptr [rbp+70h], 0
0x18000c79c  mov     eax, [rbp+70h]
0x18000c79f  add     rsp, 20h
0x18000c7a3  pop     rbp
0x18000c7a4  retn
0x18000c7a6  push    rbp
0x18000c7a8  sub     rsp, 20h
0x18000c7ac  mov     rbp, rdx
0x18000c7af  mov     rax, [rcx]
0x18000c7b2  mov     edx, [rax]
0x18000c7b4  mov     [rbp+0D0h], rcx
0x18000c7bb  mov     [rbp+78h], edx
0x18000c7be  mov     eax, [rbp+78h]
0x18000c7c1  cmp     eax, 0E06D7363h
0x18000c7c6  jnz     short loc_18000C7DF
0x18000c7c8  mov     rdx, [rbp+0D0h]
0x18000c7cf  mov     ecx, [rbp+78h]
0x18000c7d2  call    _XcptFilter_0
0x18000c7d7  mov     [rbp+80h], eax
0x18000c7dd  jmp     short loc_18000C7E9
0x18000c7df  mov     dword ptr [rbp+80h], 0
0x18000c7e9  mov     eax, [rbp+80h]
0x18000c7ef  add     rsp, 20h
0x18000c7f3  pop     rbp
0x18000c7f4  retn
0x18000c7f6  push    rbp
0x18000c7f8  sub     rsp, 20h
0x18000c7fc  mov     rbp, rdx
0x18000c7ff  mov     rax, [rcx]
0x18000c802  mov     edx, [rax]
0x18000c804  mov     [rbp+0D8h], rcx
0x18000c80b  mov     [rbp+88h], edx
0x18000c811  mov     eax, [rbp+88h]
0x18000c817  cmp     eax, 0E06D7363h
0x18000c81c  jnz     short loc_18000C838
0x18000c81e  mov     rdx, [rbp+0D8h]
0x18000c825  mov     ecx, [rbp+88h]
0x18000c82b  call    _XcptFilter_0
0x18000c830  mov     [rbp+90h], eax
0x18000c836  jmp     short loc_18000C842
0x18000c838  mov     dword ptr [rbp+90h], 0
0x18000c842  mov     eax, [rbp+90h]
0x18000c848  add     rsp, 20h
0x18000c84c  pop     rbp
0x18000c84d  retn
0x18000c84f  push    rbp
0x18000c851  sub     rsp, 20h
0x18000c855  mov     rbp, rdx
0x18000c858  mov     rax, [rcx]
0x18000c85b  mov     edx, [rax]
0x18000c85d  mov     [rbp+0E0h], rcx
0x18000c864  mov     [rbp+98h], edx
0x18000c86a  mov     eax, [rbp+98h]
0x18000c870  cmp     eax, 0E06D7363h
0x18000c875  jnz     short loc_18000C891
0x18000c877  mov     rdx, [rbp+0E0h]
0x18000c87e  mov     ecx, [rbp+98h]
0x18000c884  call    _XcptFilter_0
0x18000c889  mov     [rbp+0A0h], eax
0x18000c88f  jmp     short loc_18000C89B
0x18000c891  mov     dword ptr [rbp+0A0h], 0
0x18000c89b  mov     eax, [rbp+0A0h]
0x18000c8a1  add     rsp, 20h
0x18000c8a5  pop     rbp
0x18000c8a6  retn
0x18000c8a8  push    rbp
0x18000c8aa  sub     rsp, 20h
0x18000c8ae  mov     rbp, rdx
0x18000c8b1  cmp     dword ptr [rbp+118h], 1
0x18000c8b8  ja      short loc_18000C8C4
0x18000c8ba  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
