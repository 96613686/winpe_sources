# __DllMainCRTStartup

- ea: `0x1800014a4`
- end: `0x1800016b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001460`

## callees

- `0x180001170`
- `0x180001230`
- `0x1800014a4`
- `0x180001d70`
- `0x180013110`

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
  if ( (_DWORD)fdwReason || dword_18001DFA0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001DFA4 = 1;
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
            if ( dword_18001DFA4 )
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
0x1800014a4  mov     [rsp+lpvReserved], r8
0x1800014a9  mov     [rsp+arg_8], edx
0x1800014ad  mov     [rsp+arg_0], rcx
0x1800014b2  push    rbx
0x1800014b3  push    rsi
0x1800014b4  push    rdi
0x1800014b5  sub     rsp, 0F0h
0x1800014bc  mov     edi, edx
0x1800014be  mov     rsi, rcx
0x1800014c1  mov     ebx, 1
0x1800014c6  cmp     edx, ebx
0x1800014c8  ja      short loc_1800014D0
0x1800014ca  mov     cs:__native_dllmain_reason, edx
0x1800014d0  test    edx, edx
0x1800014d2  jnz     short loc_1800014E7
0x1800014d4  cmp     cs:dword_18001DFA0, edx
0x1800014da  jnz     short loc_1800014E7
0x1800014dc  xor     ebx, ebx
0x1800014de  mov     [rsp+108h+var_E8], ebx
0x1800014e2  jmp     loc_180001694
0x1800014e7  lea     eax, [rdx-1]
0x1800014ea  cmp     eax, 1
0x1800014ed  ja      loc_180001574
0x1800014f3  mov     rax, cs:_pRawDllMain
0x1800014fa  test    rax, rax
0x1800014fd  jz      short loc_180001535
0x1800014ff  cmp     edx, 1
0x180001502  jnz     short loc_18000150A
0x180001504  mov     cs:dword_18001DFA4, edx
0x18000150a  mov     r8, [rsp+108h+lpvReserved]
0x180001512  call    cs:__guard_dispatch_icall_fptr
0x180001518  mov     ebx, eax
0x18000151a  mov     [rsp+108h+var_E8], eax
0x18000151e  jmp     short loc_180001535
0x180001520  xor     ebx, ebx
0x180001522  mov     [rsp+108h+var_E8], ebx
0x180001526  mov     edi, [rsp+108h+arg_8]
0x18000152d  mov     rsi, [rsp+108h+arg_0]
0x180001535  test    ebx, ebx
0x180001537  jz      loc_180001694
0x18000153d  mov     r8, [rsp+108h+lpvReserved]
0x180001545  mov     edx, edi
0x180001547  mov     rcx, rsi
0x18000154a  call    _CRT_INIT
0x18000154f  mov     ebx, eax
0x180001551  mov     [rsp+108h+var_E8], eax
0x180001555  jmp     short loc_18000156C
0x180001557  xor     ebx, ebx
0x180001559  mov     [rsp+108h+var_E8], ebx
0x18000155d  mov     edi, [rsp+108h+arg_8]
0x180001564  mov     rsi, [rsp+108h+arg_0]
0x18000156c  test    ebx, ebx
0x18000156e  jz      loc_180001694
0x180001574  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000157c  mov     edx, edi; fdwReason
0x18000157e  mov     rcx, rsi; hinstDLL
0x180001581  call    DllMain
0x180001586  mov     ebx, eax
0x180001588  mov     [rsp+108h+var_E8], eax
0x18000158c  jmp     short loc_1800015A3
0x18000158e  xor     ebx, ebx
0x180001590  mov     [rsp+108h+var_E8], ebx
0x180001594  mov     edi, [rsp+108h+arg_8]
0x18000159b  mov     rsi, [rsp+108h+arg_0]
0x1800015a3  cmp     edi, 1
0x1800015a6  jnz     short loc_18000161F
0x1800015a8  test    ebx, ebx
0x1800015aa  jnz     short loc_18000161F
0x1800015ac  xor     r8d, r8d; lpvReserved
0x1800015af  xor     edx, edx; fdwReason
0x1800015b1  mov     rcx, rsi; hinstDLL
0x1800015b4  call    DllMain
0x1800015b9  jmp     short loc_1800015CE
0x1800015bb  mov     edi, [rsp+108h+arg_8]
0x1800015c2  mov     rsi, [rsp+108h+arg_0]
0x1800015ca  mov     ebx, [rsp+108h+var_E8]
0x1800015ce  xor     r8d, r8d
0x1800015d1  xor     edx, edx
0x1800015d3  mov     rcx, rsi
0x1800015d6  call    _CRT_INIT
0x1800015db  jmp     short loc_1800015F0
0x1800015dd  mov     edi, [rsp+108h+arg_8]
0x1800015e4  mov     rsi, [rsp+108h+arg_0]
0x1800015ec  mov     ebx, [rsp+108h+var_E8]
0x1800015f0  mov     rax, cs:_pRawDllMain
0x1800015f7  test    rax, rax
0x1800015fa  jz      short loc_18000161F
0x1800015fc  xor     r8d, r8d
0x1800015ff  xor     edx, edx
0x180001601  mov     rcx, rsi
0x180001604  call    cs:__guard_dispatch_icall_fptr
0x18000160a  jmp     short loc_18000161F
0x18000160c  mov     edi, [rsp+108h+arg_8]
0x180001613  mov     rsi, [rsp+108h+arg_0]
0x18000161b  mov     ebx, [rsp+108h+var_E8]
0x18000161f  test    edi, edi
0x180001621  jz      short loc_180001628
0x180001623  cmp     edi, 3
0x180001626  jnz     short loc_180001694
0x180001628  mov     r8, [rsp+108h+lpvReserved]
0x180001630  mov     edx, edi
0x180001632  mov     rcx, rsi
0x180001635  call    _CRT_INIT
0x18000163a  mov     ebx, eax
0x18000163c  mov     [rsp+108h+var_E8], eax
0x180001640  jmp     short loc_180001657
0x180001642  xor     ebx, ebx
0x180001644  mov     [rsp+108h+var_E8], ebx
0x180001648  mov     edi, [rsp+108h+arg_8]
0x18000164f  mov     rsi, [rsp+108h+arg_0]
0x180001657  mov     rax, cs:_pRawDllMain
0x18000165e  test    rax, rax
0x180001661  jz      short loc_180001694
0x180001663  cmp     cs:dword_18001DFA4, 0
0x18000166a  jz      short loc_180001694
0x18000166c  mov     r8, [rsp+108h+lpvReserved]
0x180001674  mov     edx, edi
0x180001676  mov     rcx, rsi
0x180001679  call    cs:__guard_dispatch_icall_fptr
0x18000167f  mov     ebx, eax
0x180001681  mov     [rsp+108h+var_E8], eax
0x180001685  jmp     short loc_180001694
0x180001687  xor     ebx, ebx
0x180001689  mov     [rsp+108h+var_E8], ebx
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  cmp     edi, 1
0x180001697  ja      short loc_1800016A3
0x180001699  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016a3  mov     eax, ebx
0x1800016a5  add     rsp, 0F0h
0x1800016ac  pop     rdi
0x1800016ad  pop     rsi
0x1800016ae  pop     rbx
0x1800016af  retn
0x1800131b3  push    rbp
0x1800131b5  sub     rsp, 20h
0x1800131b9  mov     rbp, rdx
0x1800131bc  mov     rax, [rcx]
0x1800131bf  mov     edx, [rax]
0x1800131c1  mov     [rbp+0A8h], rcx
0x1800131c8  mov     [rbp+28h], edx
0x1800131cb  mov     eax, [rbp+28h]
0x1800131ce  cmp     eax, 0E06D7363h
0x1800131d3  jnz     short loc_1800131E9
0x1800131d5  mov     rdx, [rbp+0A8h]
0x1800131dc  mov     ecx, [rbp+28h]
0x1800131df  call    _XcptFilter_0
0x1800131e4  mov     [rbp+30h], eax
0x1800131e7  jmp     short loc_1800131F0
0x1800131e9  mov     dword ptr [rbp+30h], 0
0x1800131f0  mov     eax, [rbp+30h]
0x1800131f3  add     rsp, 20h
0x1800131f7  pop     rbp
0x1800131f8  retn
0x1800131fa  push    rbp
0x1800131fc  sub     rsp, 20h
0x180013200  mov     rbp, rdx
0x180013203  mov     rax, [rcx]
0x180013206  mov     edx, [rax]
0x180013208  mov     [rbp+0B0h], rcx
0x18001320f  mov     [rbp+38h], edx
0x180013212  mov     eax, [rbp+38h]
0x180013215  cmp     eax, 0E06D7363h
0x18001321a  jnz     short loc_180013230
0x18001321c  mov     rdx, [rbp+0B0h]
0x180013223  mov     ecx, [rbp+38h]
0x180013226  call    _XcptFilter_0
0x18001322b  mov     [rbp+40h], eax
0x18001322e  jmp     short loc_180013237
0x180013230  mov     dword ptr [rbp+40h], 0
0x180013237  mov     eax, [rbp+40h]
0x18001323a  add     rsp, 20h
0x18001323e  pop     rbp
0x18001323f  retn
0x180013241  push    rbp
0x180013243  sub     rsp, 20h
0x180013247  mov     rbp, rdx
0x18001324a  mov     rax, [rcx]
0x18001324d  mov     edx, [rax]
0x18001324f  mov     [rbp+0B8h], rcx
0x180013256  mov     [rbp+48h], edx
0x180013259  mov     eax, [rbp+48h]
0x18001325c  cmp     eax, 0E06D7363h
0x180013261  jnz     short loc_180013277
0x180013263  mov     rdx, [rbp+0B8h]
0x18001326a  mov     ecx, [rbp+48h]
0x18001326d  call    _XcptFilter_0
0x180013272  mov     [rbp+50h], eax
0x180013275  jmp     short loc_18001327E
0x180013277  mov     dword ptr [rbp+50h], 0
0x18001327e  mov     eax, [rbp+50h]
0x180013281  add     rsp, 20h
0x180013285  pop     rbp
0x180013286  retn
0x180013288  push    rbp
0x18001328a  sub     rsp, 20h
0x18001328e  mov     rbp, rdx
0x180013291  mov     rax, [rcx]
0x180013294  mov     edx, [rax]
0x180013296  mov     [rbp+0C0h], rcx
0x18001329d  mov     [rbp+58h], edx
0x1800132a0  mov     eax, [rbp+58h]
0x1800132a3  cmp     eax, 0E06D7363h
0x1800132a8  jnz     short loc_1800132BE
0x1800132aa  mov     rdx, [rbp+0C0h]
0x1800132b1  mov     ecx, [rbp+58h]
0x1800132b4  call    _XcptFilter_0
0x1800132b9  mov     [rbp+60h], eax
0x1800132bc  jmp     short loc_1800132C5
0x1800132be  mov     dword ptr [rbp+60h], 0
0x1800132c5  mov     eax, [rbp+60h]
0x1800132c8  add     rsp, 20h
0x1800132cc  pop     rbp
0x1800132cd  retn
0x1800132cf  push    rbp
0x1800132d1  sub     rsp, 20h
0x1800132d5  mov     rbp, rdx
0x1800132d8  mov     rax, [rcx]
0x1800132db  mov     edx, [rax]
0x1800132dd  mov     [rbp+0C8h], rcx
0x1800132e4  mov     [rbp+68h], edx
0x1800132e7  mov     eax, [rbp+68h]
0x1800132ea  cmp     eax, 0E06D7363h
0x1800132ef  jnz     short loc_180013305
0x1800132f1  mov     rdx, [rbp+0C8h]
0x1800132f8  mov     ecx, [rbp+68h]
0x1800132fb  call    _XcptFilter_0
0x180013300  mov     [rbp+70h], eax
0x180013303  jmp     short loc_18001330C
0x180013305  mov     dword ptr [rbp+70h], 0
0x18001330c  mov     eax, [rbp+70h]
0x18001330f  add     rsp, 20h
0x180013313  pop     rbp
0x180013314  retn
0x180013316  push    rbp
0x180013318  sub     rsp, 20h
0x18001331c  mov     rbp, rdx
0x18001331f  mov     rax, [rcx]
0x180013322  mov     edx, [rax]
0x180013324  mov     [rbp+0D0h], rcx
0x18001332b  mov     [rbp+78h], edx
0x18001332e  mov     eax, [rbp+78h]
0x180013331  cmp     eax, 0E06D7363h
0x180013336  jnz     short loc_18001334F
0x180013338  mov     rdx, [rbp+0D0h]
0x18001333f  mov     ecx, [rbp+78h]
0x180013342  call    _XcptFilter_0
0x180013347  mov     [rbp+80h], eax
0x18001334d  jmp     short loc_180013359
0x18001334f  mov     dword ptr [rbp+80h], 0
0x180013359  mov     eax, [rbp+80h]
0x18001335f  add     rsp, 20h
0x180013363  pop     rbp
0x180013364  retn
0x180013366  push    rbp
0x180013368  sub     rsp, 20h
0x18001336c  mov     rbp, rdx
0x18001336f  mov     rax, [rcx]
0x180013372  mov     edx, [rax]
0x180013374  mov     [rbp+0D8h], rcx
0x18001337b  mov     [rbp+88h], edx
0x180013381  mov     eax, [rbp+88h]
0x180013387  cmp     eax, 0E06D7363h
0x18001338c  jnz     short loc_1800133A8
0x18001338e  mov     rdx, [rbp+0D8h]
0x180013395  mov     ecx, [rbp+88h]
0x18001339b  call    _XcptFilter_0
0x1800133a0  mov     [rbp+90h], eax
0x1800133a6  jmp     short loc_1800133B2
0x1800133a8  mov     dword ptr [rbp+90h], 0
0x1800133b2  mov     eax, [rbp+90h]
0x1800133b8  add     rsp, 20h
0x1800133bc  pop     rbp
0x1800133bd  retn
0x1800133bf  push    rbp
0x1800133c1  sub     rsp, 20h
0x1800133c5  mov     rbp, rdx
0x1800133c8  mov     rax, [rcx]
0x1800133cb  mov     edx, [rax]
0x1800133cd  mov     [rbp+0E0h], rcx
0x1800133d4  mov     [rbp+98h], edx
0x1800133da  mov     eax, [rbp+98h]
0x1800133e0  cmp     eax, 0E06D7363h
0x1800133e5  jnz     short loc_180013401
0x1800133e7  mov     rdx, [rbp+0E0h]
0x1800133ee  mov     ecx, [rbp+98h]
0x1800133f4  call    _XcptFilter_0
0x1800133f9  mov     [rbp+0A0h], eax
0x1800133ff  jmp     short loc_18001340B
0x180013401  mov     dword ptr [rbp+0A0h], 0
0x18001340b  mov     eax, [rbp+0A0h]
0x180013411  add     rsp, 20h
0x180013415  pop     rbp
0x180013416  retn
0x180013418  push    rbp
0x18001341a  sub     rsp, 20h
0x18001341e  mov     rbp, rdx
0x180013421  cmp     dword ptr [rbp+118h], 1
0x180013428  ja      short loc_180013434
0x18001342a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
