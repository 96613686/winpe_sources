# __DllMainCRTStartup

- ea: `0x18001c634`
- end: `0x18001c840`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c5f0`

## callees

- `0x18001527c`
- `0x18001c3c0`
- `0x18001c634`
- `0x18001ccca`
- `0x180032710`

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
  if ( (_DWORD)fdwReason || dword_18004B340 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18004B344 = 1;
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
            if ( dword_18004B344 )
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
0x18001c634  mov     [rsp+lpvReserved], r8
0x18001c639  mov     [rsp+arg_8], edx
0x18001c63d  mov     [rsp+arg_0], rcx
0x18001c642  push    rbx
0x18001c643  push    rsi
0x18001c644  push    rdi
0x18001c645  sub     rsp, 0F0h
0x18001c64c  mov     edi, edx
0x18001c64e  mov     rsi, rcx
0x18001c651  mov     ebx, 1
0x18001c656  cmp     edx, ebx
0x18001c658  ja      short loc_18001C660
0x18001c65a  mov     cs:__native_dllmain_reason, edx
0x18001c660  test    edx, edx
0x18001c662  jnz     short loc_18001C677
0x18001c664  cmp     cs:dword_18004B340, edx
0x18001c66a  jnz     short loc_18001C677
0x18001c66c  xor     ebx, ebx
0x18001c66e  mov     [rsp+108h+var_E8], ebx
0x18001c672  jmp     loc_18001C824
0x18001c677  lea     eax, [rdx-1]
0x18001c67a  cmp     eax, 1
0x18001c67d  ja      loc_18001C704
0x18001c683  mov     rax, cs:_pRawDllMain
0x18001c68a  test    rax, rax
0x18001c68d  jz      short loc_18001C6C5
0x18001c68f  cmp     edx, 1
0x18001c692  jnz     short loc_18001C69A
0x18001c694  mov     cs:dword_18004B344, edx
0x18001c69a  mov     r8, [rsp+108h+lpvReserved]
0x18001c6a2  call    cs:__guard_dispatch_icall_fptr
0x18001c6a8  mov     ebx, eax
0x18001c6aa  mov     [rsp+108h+var_E8], eax
0x18001c6ae  jmp     short loc_18001C6C5
0x18001c6b0  xor     ebx, ebx
0x18001c6b2  mov     [rsp+108h+var_E8], ebx
0x18001c6b6  mov     edi, [rsp+108h+arg_8]
0x18001c6bd  mov     rsi, [rsp+108h+arg_0]
0x18001c6c5  test    ebx, ebx
0x18001c6c7  jz      loc_18001C824
0x18001c6cd  mov     r8, [rsp+108h+lpvReserved]
0x18001c6d5  mov     edx, edi
0x18001c6d7  mov     rcx, rsi
0x18001c6da  call    _CRT_INIT
0x18001c6df  mov     ebx, eax
0x18001c6e1  mov     [rsp+108h+var_E8], eax
0x18001c6e5  jmp     short loc_18001C6FC
0x18001c6e7  xor     ebx, ebx
0x18001c6e9  mov     [rsp+108h+var_E8], ebx
0x18001c6ed  mov     edi, [rsp+108h+arg_8]
0x18001c6f4  mov     rsi, [rsp+108h+arg_0]
0x18001c6fc  test    ebx, ebx
0x18001c6fe  jz      loc_18001C824
0x18001c704  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001c70c  mov     edx, edi; fdwReason
0x18001c70e  mov     rcx, rsi; hinstDLL
0x18001c711  call    DllMain
0x18001c716  mov     ebx, eax
0x18001c718  mov     [rsp+108h+var_E8], eax
0x18001c71c  jmp     short loc_18001C733
0x18001c71e  xor     ebx, ebx
0x18001c720  mov     [rsp+108h+var_E8], ebx
0x18001c724  mov     edi, [rsp+108h+arg_8]
0x18001c72b  mov     rsi, [rsp+108h+arg_0]
0x18001c733  cmp     edi, 1
0x18001c736  jnz     short loc_18001C7AF
0x18001c738  test    ebx, ebx
0x18001c73a  jnz     short loc_18001C7AF
0x18001c73c  xor     r8d, r8d; lpvReserved
0x18001c73f  xor     edx, edx; fdwReason
0x18001c741  mov     rcx, rsi; hinstDLL
0x18001c744  call    DllMain
0x18001c749  jmp     short loc_18001C75E
0x18001c74b  mov     edi, [rsp+108h+arg_8]
0x18001c752  mov     rsi, [rsp+108h+arg_0]
0x18001c75a  mov     ebx, [rsp+108h+var_E8]
0x18001c75e  xor     r8d, r8d
0x18001c761  xor     edx, edx
0x18001c763  mov     rcx, rsi
0x18001c766  call    _CRT_INIT
0x18001c76b  jmp     short loc_18001C780
0x18001c76d  mov     edi, [rsp+108h+arg_8]
0x18001c774  mov     rsi, [rsp+108h+arg_0]
0x18001c77c  mov     ebx, [rsp+108h+var_E8]
0x18001c780  mov     rax, cs:_pRawDllMain
0x18001c787  test    rax, rax
0x18001c78a  jz      short loc_18001C7AF
0x18001c78c  xor     r8d, r8d
0x18001c78f  xor     edx, edx
0x18001c791  mov     rcx, rsi
0x18001c794  call    cs:__guard_dispatch_icall_fptr
0x18001c79a  jmp     short loc_18001C7AF
0x18001c79c  mov     edi, [rsp+108h+arg_8]
0x18001c7a3  mov     rsi, [rsp+108h+arg_0]
0x18001c7ab  mov     ebx, [rsp+108h+var_E8]
0x18001c7af  test    edi, edi
0x18001c7b1  jz      short loc_18001C7B8
0x18001c7b3  cmp     edi, 3
0x18001c7b6  jnz     short loc_18001C824
0x18001c7b8  mov     r8, [rsp+108h+lpvReserved]
0x18001c7c0  mov     edx, edi
0x18001c7c2  mov     rcx, rsi
0x18001c7c5  call    _CRT_INIT
0x18001c7ca  mov     ebx, eax
0x18001c7cc  mov     [rsp+108h+var_E8], eax
0x18001c7d0  jmp     short loc_18001C7E7
0x18001c7d2  xor     ebx, ebx
0x18001c7d4  mov     [rsp+108h+var_E8], ebx
0x18001c7d8  mov     edi, [rsp+108h+arg_8]
0x18001c7df  mov     rsi, [rsp+108h+arg_0]
0x18001c7e7  mov     rax, cs:_pRawDllMain
0x18001c7ee  test    rax, rax
0x18001c7f1  jz      short loc_18001C824
0x18001c7f3  cmp     cs:dword_18004B344, 0
0x18001c7fa  jz      short loc_18001C824
0x18001c7fc  mov     r8, [rsp+108h+lpvReserved]
0x18001c804  mov     edx, edi
0x18001c806  mov     rcx, rsi
0x18001c809  call    cs:__guard_dispatch_icall_fptr
0x18001c80f  mov     ebx, eax
0x18001c811  mov     [rsp+108h+var_E8], eax
0x18001c815  jmp     short loc_18001C824
0x18001c817  xor     ebx, ebx
0x18001c819  mov     [rsp+108h+var_E8], ebx
0x18001c81d  mov     edi, [rsp+108h+arg_8]
0x18001c824  cmp     edi, 1
0x18001c827  ja      short loc_18001C833
0x18001c829  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18001c833  mov     eax, ebx
0x18001c835  add     rsp, 0F0h
0x18001c83c  pop     rdi
0x18001c83d  pop     rsi
0x18001c83e  pop     rbx
0x18001c83f  retn
0x1800352c0  push    rbp
0x1800352c2  sub     rsp, 20h
0x1800352c6  mov     rbp, rdx
0x1800352c9  mov     rax, [rcx]
0x1800352cc  mov     edx, [rax]
0x1800352ce  mov     [rbp+0A8h], rcx
0x1800352d5  mov     [rbp+28h], edx
0x1800352d8  mov     eax, [rbp+28h]
0x1800352db  cmp     eax, 0E06D7363h
0x1800352e0  jnz     short loc_1800352F6
0x1800352e2  mov     rdx, [rbp+0A8h]
0x1800352e9  mov     ecx, [rbp+28h]
0x1800352ec  call    _XcptFilter_0
0x1800352f1  mov     [rbp+30h], eax
0x1800352f4  jmp     short loc_1800352FD
0x1800352f6  mov     dword ptr [rbp+30h], 0
0x1800352fd  mov     eax, [rbp+30h]
0x180035300  add     rsp, 20h
0x180035304  pop     rbp
0x180035305  retn
0x180035307  push    rbp
0x180035309  sub     rsp, 20h
0x18003530d  mov     rbp, rdx
0x180035310  mov     rax, [rcx]
0x180035313  mov     edx, [rax]
0x180035315  mov     [rbp+0B0h], rcx
0x18003531c  mov     [rbp+38h], edx
0x18003531f  mov     eax, [rbp+38h]
0x180035322  cmp     eax, 0E06D7363h
0x180035327  jnz     short loc_18003533D
0x180035329  mov     rdx, [rbp+0B0h]
0x180035330  mov     ecx, [rbp+38h]
0x180035333  call    _XcptFilter_0
0x180035338  mov     [rbp+40h], eax
0x18003533b  jmp     short loc_180035344
0x18003533d  mov     dword ptr [rbp+40h], 0
0x180035344  mov     eax, [rbp+40h]
0x180035347  add     rsp, 20h
0x18003534b  pop     rbp
0x18003534c  retn
0x18003534e  push    rbp
0x180035350  sub     rsp, 20h
0x180035354  mov     rbp, rdx
0x180035357  mov     rax, [rcx]
0x18003535a  mov     edx, [rax]
0x18003535c  mov     [rbp+0B8h], rcx
0x180035363  mov     [rbp+48h], edx
0x180035366  mov     eax, [rbp+48h]
0x180035369  cmp     eax, 0E06D7363h
0x18003536e  jnz     short loc_180035384
0x180035370  mov     rdx, [rbp+0B8h]
0x180035377  mov     ecx, [rbp+48h]
0x18003537a  call    _XcptFilter_0
0x18003537f  mov     [rbp+50h], eax
0x180035382  jmp     short loc_18003538B
0x180035384  mov     dword ptr [rbp+50h], 0
0x18003538b  mov     eax, [rbp+50h]
0x18003538e  add     rsp, 20h
0x180035392  pop     rbp
0x180035393  retn
0x180035395  push    rbp
0x180035397  sub     rsp, 20h
0x18003539b  mov     rbp, rdx
0x18003539e  mov     rax, [rcx]
0x1800353a1  mov     edx, [rax]
0x1800353a3  mov     [rbp+0C0h], rcx
0x1800353aa  mov     [rbp+58h], edx
0x1800353ad  mov     eax, [rbp+58h]
0x1800353b0  cmp     eax, 0E06D7363h
0x1800353b5  jnz     short loc_1800353CB
0x1800353b7  mov     rdx, [rbp+0C0h]
0x1800353be  mov     ecx, [rbp+58h]
0x1800353c1  call    _XcptFilter_0
0x1800353c6  mov     [rbp+60h], eax
0x1800353c9  jmp     short loc_1800353D2
0x1800353cb  mov     dword ptr [rbp+60h], 0
0x1800353d2  mov     eax, [rbp+60h]
0x1800353d5  add     rsp, 20h
0x1800353d9  pop     rbp
0x1800353da  retn
0x1800353dc  push    rbp
0x1800353de  sub     rsp, 20h
0x1800353e2  mov     rbp, rdx
0x1800353e5  mov     rax, [rcx]
0x1800353e8  mov     edx, [rax]
0x1800353ea  mov     [rbp+0C8h], rcx
0x1800353f1  mov     [rbp+68h], edx
0x1800353f4  mov     eax, [rbp+68h]
0x1800353f7  cmp     eax, 0E06D7363h
0x1800353fc  jnz     short loc_180035412
0x1800353fe  mov     rdx, [rbp+0C8h]
0x180035405  mov     ecx, [rbp+68h]
0x180035408  call    _XcptFilter_0
0x18003540d  mov     [rbp+70h], eax
0x180035410  jmp     short loc_180035419
0x180035412  mov     dword ptr [rbp+70h], 0
0x180035419  mov     eax, [rbp+70h]
0x18003541c  add     rsp, 20h
0x180035420  pop     rbp
0x180035421  retn
0x180035423  push    rbp
0x180035425  sub     rsp, 20h
0x180035429  mov     rbp, rdx
0x18003542c  mov     rax, [rcx]
0x18003542f  mov     edx, [rax]
0x180035431  mov     [rbp+0D0h], rcx
0x180035438  mov     [rbp+78h], edx
0x18003543b  mov     eax, [rbp+78h]
0x18003543e  cmp     eax, 0E06D7363h
0x180035443  jnz     short loc_18003545C
0x180035445  mov     rdx, [rbp+0D0h]
0x18003544c  mov     ecx, [rbp+78h]
0x18003544f  call    _XcptFilter_0
0x180035454  mov     [rbp+80h], eax
0x18003545a  jmp     short loc_180035466
0x18003545c  mov     dword ptr [rbp+80h], 0
0x180035466  mov     eax, [rbp+80h]
0x18003546c  add     rsp, 20h
0x180035470  pop     rbp
0x180035471  retn
0x180035473  push    rbp
0x180035475  sub     rsp, 20h
0x180035479  mov     rbp, rdx
0x18003547c  mov     rax, [rcx]
0x18003547f  mov     edx, [rax]
0x180035481  mov     [rbp+0D8h], rcx
0x180035488  mov     [rbp+88h], edx
0x18003548e  mov     eax, [rbp+88h]
0x180035494  cmp     eax, 0E06D7363h
0x180035499  jnz     short loc_1800354B5
0x18003549b  mov     rdx, [rbp+0D8h]
0x1800354a2  mov     ecx, [rbp+88h]
0x1800354a8  call    _XcptFilter_0
0x1800354ad  mov     [rbp+90h], eax
0x1800354b3  jmp     short loc_1800354BF
0x1800354b5  mov     dword ptr [rbp+90h], 0
0x1800354bf  mov     eax, [rbp+90h]
0x1800354c5  add     rsp, 20h
0x1800354c9  pop     rbp
0x1800354ca  retn
0x1800354cc  push    rbp
0x1800354ce  sub     rsp, 20h
0x1800354d2  mov     rbp, rdx
0x1800354d5  mov     rax, [rcx]
0x1800354d8  mov     edx, [rax]
0x1800354da  mov     [rbp+0E0h], rcx
0x1800354e1  mov     [rbp+98h], edx
0x1800354e7  mov     eax, [rbp+98h]
0x1800354ed  cmp     eax, 0E06D7363h
0x1800354f2  jnz     short loc_18003550E
0x1800354f4  mov     rdx, [rbp+0E0h]
0x1800354fb  mov     ecx, [rbp+98h]
0x180035501  call    _XcptFilter_0
0x180035506  mov     [rbp+0A0h], eax
0x18003550c  jmp     short loc_180035518
0x18003550e  mov     dword ptr [rbp+0A0h], 0
0x180035518  mov     eax, [rbp+0A0h]
0x18003551e  add     rsp, 20h
0x180035522  pop     rbp
0x180035523  retn
0x180035525  push    rbp
0x180035527  sub     rsp, 20h
0x18003552b  mov     rbp, rdx
0x18003552e  cmp     dword ptr [rbp+118h], 1
0x180035535  ja      short loc_180035541
0x180035537  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
