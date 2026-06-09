# __DllMainCRTStartup

- ea: `0x180001444`
- end: `0x180001650`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x1800011d0`
- `0x180001444`
- `0x180001676`
- `0x180002a70`
- `0x180007080`

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
  if ( (_DWORD)fdwReason || dword_18000E1E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000E1E4 = 1;
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
            if ( dword_18000E1E4 )
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
0x180001444  mov     [rsp+lpvReserved], r8
0x180001449  mov     [rsp+arg_8], edx
0x18000144d  mov     [rsp+arg_0], rcx
0x180001452  push    rbx
0x180001453  push    rsi
0x180001454  push    rdi
0x180001455  sub     rsp, 0F0h
0x18000145c  mov     edi, edx
0x18000145e  mov     rsi, rcx
0x180001461  mov     ebx, 1
0x180001466  cmp     edx, ebx
0x180001468  ja      short loc_180001470
0x18000146a  mov     cs:__native_dllmain_reason, edx
0x180001470  test    edx, edx
0x180001472  jnz     short loc_180001487
0x180001474  cmp     cs:dword_18000E1E0, edx
0x18000147a  jnz     short loc_180001487
0x18000147c  xor     ebx, ebx
0x18000147e  mov     [rsp+108h+var_E8], ebx
0x180001482  jmp     loc_180001634
0x180001487  lea     eax, [rdx-1]
0x18000148a  cmp     eax, 1
0x18000148d  ja      loc_180001514
0x180001493  mov     rax, cs:_pRawDllMain
0x18000149a  test    rax, rax
0x18000149d  jz      short loc_1800014D5
0x18000149f  cmp     edx, 1
0x1800014a2  jnz     short loc_1800014AA
0x1800014a4  mov     cs:dword_18000E1E4, edx
0x1800014aa  mov     r8, [rsp+108h+lpvReserved]
0x1800014b2  call    cs:__guard_dispatch_icall_fptr
0x1800014b8  mov     ebx, eax
0x1800014ba  mov     [rsp+108h+var_E8], eax
0x1800014be  jmp     short loc_1800014D5
0x1800014c0  xor     ebx, ebx
0x1800014c2  mov     [rsp+108h+var_E8], ebx
0x1800014c6  mov     edi, [rsp+108h+arg_8]
0x1800014cd  mov     rsi, [rsp+108h+arg_0]
0x1800014d5  test    ebx, ebx
0x1800014d7  jz      loc_180001634
0x1800014dd  mov     r8, [rsp+108h+lpvReserved]
0x1800014e5  mov     edx, edi
0x1800014e7  mov     rcx, rsi
0x1800014ea  call    _CRT_INIT
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_18000150C
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  mov     rsi, [rsp+108h+arg_0]
0x18000150c  test    ebx, ebx
0x18000150e  jz      loc_180001634
0x180001514  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000151c  mov     edx, edi; fdwReason
0x18000151e  mov     rcx, rsi; hinstDLL
0x180001521  call    DllMain
0x180001526  mov     ebx, eax
0x180001528  mov     [rsp+108h+var_E8], eax
0x18000152c  jmp     short loc_180001543
0x18000152e  xor     ebx, ebx
0x180001530  mov     [rsp+108h+var_E8], ebx
0x180001534  mov     edi, [rsp+108h+arg_8]
0x18000153b  mov     rsi, [rsp+108h+arg_0]
0x180001543  cmp     edi, 1
0x180001546  jnz     short loc_1800015BF
0x180001548  test    ebx, ebx
0x18000154a  jnz     short loc_1800015BF
0x18000154c  xor     r8d, r8d; lpvReserved
0x18000154f  xor     edx, edx; fdwReason
0x180001551  mov     rcx, rsi; hinstDLL
0x180001554  call    DllMain
0x180001559  jmp     short loc_18000156E
0x18000155b  mov     edi, [rsp+108h+arg_8]
0x180001562  mov     rsi, [rsp+108h+arg_0]
0x18000156a  mov     ebx, [rsp+108h+var_E8]
0x18000156e  xor     r8d, r8d
0x180001571  xor     edx, edx
0x180001573  mov     rcx, rsi
0x180001576  call    _CRT_INIT
0x18000157b  jmp     short loc_180001590
0x18000157d  mov     edi, [rsp+108h+arg_8]
0x180001584  mov     rsi, [rsp+108h+arg_0]
0x18000158c  mov     ebx, [rsp+108h+var_E8]
0x180001590  mov     rax, cs:_pRawDllMain
0x180001597  test    rax, rax
0x18000159a  jz      short loc_1800015BF
0x18000159c  xor     r8d, r8d
0x18000159f  xor     edx, edx
0x1800015a1  mov     rcx, rsi
0x1800015a4  call    cs:__guard_dispatch_icall_fptr
0x1800015aa  jmp     short loc_1800015BF
0x1800015ac  mov     edi, [rsp+108h+arg_8]
0x1800015b3  mov     rsi, [rsp+108h+arg_0]
0x1800015bb  mov     ebx, [rsp+108h+var_E8]
0x1800015bf  test    edi, edi
0x1800015c1  jz      short loc_1800015C8
0x1800015c3  cmp     edi, 3
0x1800015c6  jnz     short loc_180001634
0x1800015c8  mov     r8, [rsp+108h+lpvReserved]
0x1800015d0  mov     edx, edi
0x1800015d2  mov     rcx, rsi
0x1800015d5  call    _CRT_INIT
0x1800015da  mov     ebx, eax
0x1800015dc  mov     [rsp+108h+var_E8], eax
0x1800015e0  jmp     short loc_1800015F7
0x1800015e2  xor     ebx, ebx
0x1800015e4  mov     [rsp+108h+var_E8], ebx
0x1800015e8  mov     edi, [rsp+108h+arg_8]
0x1800015ef  mov     rsi, [rsp+108h+arg_0]
0x1800015f7  mov     rax, cs:_pRawDllMain
0x1800015fe  test    rax, rax
0x180001601  jz      short loc_180001634
0x180001603  cmp     cs:dword_18000E1E4, 0
0x18000160a  jz      short loc_180001634
0x18000160c  mov     r8, [rsp+108h+lpvReserved]
0x180001614  mov     edx, edi
0x180001616  mov     rcx, rsi
0x180001619  call    cs:__guard_dispatch_icall_fptr
0x18000161f  mov     ebx, eax
0x180001621  mov     [rsp+108h+var_E8], eax
0x180001625  jmp     short loc_180001634
0x180001627  xor     ebx, ebx
0x180001629  mov     [rsp+108h+var_E8], ebx
0x18000162d  mov     edi, [rsp+108h+arg_8]
0x180001634  cmp     edi, 1
0x180001637  ja      short loc_180001643
0x180001639  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001643  mov     eax, ebx
0x180001645  add     rsp, 0F0h
0x18000164c  pop     rdi
0x18000164d  pop     rsi
0x18000164e  pop     rbx
0x18000164f  retn
0x1800070f0  push    rbp
0x1800070f2  sub     rsp, 20h
0x1800070f6  mov     rbp, rdx
0x1800070f9  mov     rax, [rcx]
0x1800070fc  mov     edx, [rax]
0x1800070fe  mov     [rbp+0A8h], rcx
0x180007105  mov     [rbp+28h], edx
0x180007108  mov     eax, [rbp+28h]
0x18000710b  cmp     eax, 0E06D7363h
0x180007110  jnz     short loc_180007126
0x180007112  mov     rdx, [rbp+0A8h]
0x180007119  mov     ecx, [rbp+28h]
0x18000711c  call    _XcptFilter_0
0x180007121  mov     [rbp+30h], eax
0x180007124  jmp     short loc_18000712D
0x180007126  mov     dword ptr [rbp+30h], 0
0x18000712d  mov     eax, [rbp+30h]
0x180007130  add     rsp, 20h
0x180007134  pop     rbp
0x180007135  retn
0x180007137  push    rbp
0x180007139  sub     rsp, 20h
0x18000713d  mov     rbp, rdx
0x180007140  mov     rax, [rcx]
0x180007143  mov     edx, [rax]
0x180007145  mov     [rbp+0B0h], rcx
0x18000714c  mov     [rbp+38h], edx
0x18000714f  mov     eax, [rbp+38h]
0x180007152  cmp     eax, 0E06D7363h
0x180007157  jnz     short loc_18000716D
0x180007159  mov     rdx, [rbp+0B0h]
0x180007160  mov     ecx, [rbp+38h]
0x180007163  call    _XcptFilter_0
0x180007168  mov     [rbp+40h], eax
0x18000716b  jmp     short loc_180007174
0x18000716d  mov     dword ptr [rbp+40h], 0
0x180007174  mov     eax, [rbp+40h]
0x180007177  add     rsp, 20h
0x18000717b  pop     rbp
0x18000717c  retn
0x18000717e  push    rbp
0x180007180  sub     rsp, 20h
0x180007184  mov     rbp, rdx
0x180007187  mov     rax, [rcx]
0x18000718a  mov     edx, [rax]
0x18000718c  mov     [rbp+0B8h], rcx
0x180007193  mov     [rbp+48h], edx
0x180007196  mov     eax, [rbp+48h]
0x180007199  cmp     eax, 0E06D7363h
0x18000719e  jnz     short loc_1800071B4
0x1800071a0  mov     rdx, [rbp+0B8h]
0x1800071a7  mov     ecx, [rbp+48h]
0x1800071aa  call    _XcptFilter_0
0x1800071af  mov     [rbp+50h], eax
0x1800071b2  jmp     short loc_1800071BB
0x1800071b4  mov     dword ptr [rbp+50h], 0
0x1800071bb  mov     eax, [rbp+50h]
0x1800071be  add     rsp, 20h
0x1800071c2  pop     rbp
0x1800071c3  retn
0x1800071c5  push    rbp
0x1800071c7  sub     rsp, 20h
0x1800071cb  mov     rbp, rdx
0x1800071ce  mov     rax, [rcx]
0x1800071d1  mov     edx, [rax]
0x1800071d3  mov     [rbp+0C0h], rcx
0x1800071da  mov     [rbp+58h], edx
0x1800071dd  mov     eax, [rbp+58h]
0x1800071e0  cmp     eax, 0E06D7363h
0x1800071e5  jnz     short loc_1800071FB
0x1800071e7  mov     rdx, [rbp+0C0h]
0x1800071ee  mov     ecx, [rbp+58h]
0x1800071f1  call    _XcptFilter_0
0x1800071f6  mov     [rbp+60h], eax
0x1800071f9  jmp     short loc_180007202
0x1800071fb  mov     dword ptr [rbp+60h], 0
0x180007202  mov     eax, [rbp+60h]
0x180007205  add     rsp, 20h
0x180007209  pop     rbp
0x18000720a  retn
0x18000720c  push    rbp
0x18000720e  sub     rsp, 20h
0x180007212  mov     rbp, rdx
0x180007215  mov     rax, [rcx]
0x180007218  mov     edx, [rax]
0x18000721a  mov     [rbp+0C8h], rcx
0x180007221  mov     [rbp+68h], edx
0x180007224  mov     eax, [rbp+68h]
0x180007227  cmp     eax, 0E06D7363h
0x18000722c  jnz     short loc_180007242
0x18000722e  mov     rdx, [rbp+0C8h]
0x180007235  mov     ecx, [rbp+68h]
0x180007238  call    _XcptFilter_0
0x18000723d  mov     [rbp+70h], eax
0x180007240  jmp     short loc_180007249
0x180007242  mov     dword ptr [rbp+70h], 0
0x180007249  mov     eax, [rbp+70h]
0x18000724c  add     rsp, 20h
0x180007250  pop     rbp
0x180007251  retn
0x180007253  push    rbp
0x180007255  sub     rsp, 20h
0x180007259  mov     rbp, rdx
0x18000725c  mov     rax, [rcx]
0x18000725f  mov     edx, [rax]
0x180007261  mov     [rbp+0D0h], rcx
0x180007268  mov     [rbp+78h], edx
0x18000726b  mov     eax, [rbp+78h]
0x18000726e  cmp     eax, 0E06D7363h
0x180007273  jnz     short loc_18000728C
0x180007275  mov     rdx, [rbp+0D0h]
0x18000727c  mov     ecx, [rbp+78h]
0x18000727f  call    _XcptFilter_0
0x180007284  mov     [rbp+80h], eax
0x18000728a  jmp     short loc_180007296
0x18000728c  mov     dword ptr [rbp+80h], 0
0x180007296  mov     eax, [rbp+80h]
0x18000729c  add     rsp, 20h
0x1800072a0  pop     rbp
0x1800072a1  retn
0x1800072a3  push    rbp
0x1800072a5  sub     rsp, 20h
0x1800072a9  mov     rbp, rdx
0x1800072ac  mov     rax, [rcx]
0x1800072af  mov     edx, [rax]
0x1800072b1  mov     [rbp+0D8h], rcx
0x1800072b8  mov     [rbp+88h], edx
0x1800072be  mov     eax, [rbp+88h]
0x1800072c4  cmp     eax, 0E06D7363h
0x1800072c9  jnz     short loc_1800072E5
0x1800072cb  mov     rdx, [rbp+0D8h]
0x1800072d2  mov     ecx, [rbp+88h]
0x1800072d8  call    _XcptFilter_0
0x1800072dd  mov     [rbp+90h], eax
0x1800072e3  jmp     short loc_1800072EF
0x1800072e5  mov     dword ptr [rbp+90h], 0
0x1800072ef  mov     eax, [rbp+90h]
0x1800072f5  add     rsp, 20h
0x1800072f9  pop     rbp
0x1800072fa  retn
0x1800072fc  push    rbp
0x1800072fe  sub     rsp, 20h
0x180007302  mov     rbp, rdx
0x180007305  mov     rax, [rcx]
0x180007308  mov     edx, [rax]
0x18000730a  mov     [rbp+0E0h], rcx
0x180007311  mov     [rbp+98h], edx
0x180007317  mov     eax, [rbp+98h]
0x18000731d  cmp     eax, 0E06D7363h
0x180007322  jnz     short loc_18000733E
0x180007324  mov     rdx, [rbp+0E0h]
0x18000732b  mov     ecx, [rbp+98h]
0x180007331  call    _XcptFilter_0
0x180007336  mov     [rbp+0A0h], eax
0x18000733c  jmp     short loc_180007348
0x18000733e  mov     dword ptr [rbp+0A0h], 0
0x180007348  mov     eax, [rbp+0A0h]
0x18000734e  add     rsp, 20h
0x180007352  pop     rbp
0x180007353  retn
0x180007355  push    rbp
0x180007357  sub     rsp, 20h
0x18000735b  mov     rbp, rdx
0x18000735e  cmp     dword ptr [rbp+118h], 1
0x180007365  ja      short loc_180007371
0x180007367  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
