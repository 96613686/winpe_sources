# __DllMainCRTStartup

- ea: `0x180001494`
- end: `0x1800016a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x180001220`
- `0x180001494`
- `0x180001b18`
- `0x180004f18`
- `0x180005fa0`

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
  if ( (_DWORD)fdwReason || dword_18000B260 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B264 = 1;
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
            if ( dword_18000B264 )
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
0x180001494  mov     [rsp+lpvReserved], r8
0x180001499  mov     [rsp+arg_8], edx
0x18000149d  mov     [rsp+arg_0], rcx
0x1800014a2  push    rbx
0x1800014a3  push    rsi
0x1800014a4  push    rdi
0x1800014a5  sub     rsp, 0F0h
0x1800014ac  mov     edi, edx
0x1800014ae  mov     rsi, rcx
0x1800014b1  mov     ebx, 1
0x1800014b6  cmp     edx, ebx
0x1800014b8  ja      short loc_1800014C0
0x1800014ba  mov     cs:__native_dllmain_reason, edx
0x1800014c0  test    edx, edx
0x1800014c2  jnz     short loc_1800014D7
0x1800014c4  cmp     cs:dword_18000B260, edx
0x1800014ca  jnz     short loc_1800014D7
0x1800014cc  xor     ebx, ebx
0x1800014ce  mov     [rsp+108h+var_E8], ebx
0x1800014d2  jmp     loc_180001684
0x1800014d7  lea     eax, [rdx-1]
0x1800014da  cmp     eax, 1
0x1800014dd  ja      loc_180001564
0x1800014e3  mov     rax, cs:_pRawDllMain
0x1800014ea  test    rax, rax
0x1800014ed  jz      short loc_180001525
0x1800014ef  cmp     edx, 1
0x1800014f2  jnz     short loc_1800014FA
0x1800014f4  mov     cs:dword_18000B264, edx
0x1800014fa  mov     r8, [rsp+108h+lpvReserved]
0x180001502  call    cs:__guard_dispatch_icall_fptr
0x180001508  mov     ebx, eax
0x18000150a  mov     [rsp+108h+var_E8], eax
0x18000150e  jmp     short loc_180001525
0x180001510  xor     ebx, ebx
0x180001512  mov     [rsp+108h+var_E8], ebx
0x180001516  mov     edi, [rsp+108h+arg_8]
0x18000151d  mov     rsi, [rsp+108h+arg_0]
0x180001525  test    ebx, ebx
0x180001527  jz      loc_180001684
0x18000152d  mov     r8, [rsp+108h+lpvReserved]
0x180001535  mov     edx, edi
0x180001537  mov     rcx, rsi
0x18000153a  call    _CRT_INIT
0x18000153f  mov     ebx, eax
0x180001541  mov     [rsp+108h+var_E8], eax
0x180001545  jmp     short loc_18000155C
0x180001547  xor     ebx, ebx
0x180001549  mov     [rsp+108h+var_E8], ebx
0x18000154d  mov     edi, [rsp+108h+arg_8]
0x180001554  mov     rsi, [rsp+108h+arg_0]
0x18000155c  test    ebx, ebx
0x18000155e  jz      loc_180001684
0x180001564  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000156c  mov     edx, edi; fdwReason
0x18000156e  mov     rcx, rsi; hinstDLL
0x180001571  call    DllMain
0x180001576  mov     ebx, eax
0x180001578  mov     [rsp+108h+var_E8], eax
0x18000157c  jmp     short loc_180001593
0x18000157e  xor     ebx, ebx
0x180001580  mov     [rsp+108h+var_E8], ebx
0x180001584  mov     edi, [rsp+108h+arg_8]
0x18000158b  mov     rsi, [rsp+108h+arg_0]
0x180001593  cmp     edi, 1
0x180001596  jnz     short loc_18000160F
0x180001598  test    ebx, ebx
0x18000159a  jnz     short loc_18000160F
0x18000159c  xor     r8d, r8d; lpvReserved
0x18000159f  xor     edx, edx; fdwReason
0x1800015a1  mov     rcx, rsi; hinstDLL
0x1800015a4  call    DllMain
0x1800015a9  jmp     short loc_1800015BE
0x1800015ab  mov     edi, [rsp+108h+arg_8]
0x1800015b2  mov     rsi, [rsp+108h+arg_0]
0x1800015ba  mov     ebx, [rsp+108h+var_E8]
0x1800015be  xor     r8d, r8d
0x1800015c1  xor     edx, edx
0x1800015c3  mov     rcx, rsi
0x1800015c6  call    _CRT_INIT
0x1800015cb  jmp     short loc_1800015E0
0x1800015cd  mov     edi, [rsp+108h+arg_8]
0x1800015d4  mov     rsi, [rsp+108h+arg_0]
0x1800015dc  mov     ebx, [rsp+108h+var_E8]
0x1800015e0  mov     rax, cs:_pRawDllMain
0x1800015e7  test    rax, rax
0x1800015ea  jz      short loc_18000160F
0x1800015ec  xor     r8d, r8d
0x1800015ef  xor     edx, edx
0x1800015f1  mov     rcx, rsi
0x1800015f4  call    cs:__guard_dispatch_icall_fptr
0x1800015fa  jmp     short loc_18000160F
0x1800015fc  mov     edi, [rsp+108h+arg_8]
0x180001603  mov     rsi, [rsp+108h+arg_0]
0x18000160b  mov     ebx, [rsp+108h+var_E8]
0x18000160f  test    edi, edi
0x180001611  jz      short loc_180001618
0x180001613  cmp     edi, 3
0x180001616  jnz     short loc_180001684
0x180001618  mov     r8, [rsp+108h+lpvReserved]
0x180001620  mov     edx, edi
0x180001622  mov     rcx, rsi
0x180001625  call    _CRT_INIT
0x18000162a  mov     ebx, eax
0x18000162c  mov     [rsp+108h+var_E8], eax
0x180001630  jmp     short loc_180001647
0x180001632  xor     ebx, ebx
0x180001634  mov     [rsp+108h+var_E8], ebx
0x180001638  mov     edi, [rsp+108h+arg_8]
0x18000163f  mov     rsi, [rsp+108h+arg_0]
0x180001647  mov     rax, cs:_pRawDllMain
0x18000164e  test    rax, rax
0x180001651  jz      short loc_180001684
0x180001653  cmp     cs:dword_18000B264, 0
0x18000165a  jz      short loc_180001684
0x18000165c  mov     r8, [rsp+108h+lpvReserved]
0x180001664  mov     edx, edi
0x180001666  mov     rcx, rsi
0x180001669  call    cs:__guard_dispatch_icall_fptr
0x18000166f  mov     ebx, eax
0x180001671  mov     [rsp+108h+var_E8], eax
0x180001675  jmp     short loc_180001684
0x180001677  xor     ebx, ebx
0x180001679  mov     [rsp+108h+var_E8], ebx
0x18000167d  mov     edi, [rsp+108h+arg_8]
0x180001684  cmp     edi, 1
0x180001687  ja      short loc_180001693
0x180001689  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001693  mov     eax, ebx
0x180001695  add     rsp, 0F0h
0x18000169c  pop     rdi
0x18000169d  pop     rsi
0x18000169e  pop     rbx
0x18000169f  retn
0x180006070  push    rbp
0x180006072  sub     rsp, 20h
0x180006076  mov     rbp, rdx
0x180006079  mov     rax, [rcx]
0x18000607c  mov     edx, [rax]
0x18000607e  mov     [rbp+0A8h], rcx
0x180006085  mov     [rbp+28h], edx
0x180006088  mov     eax, [rbp+28h]
0x18000608b  cmp     eax, 0E06D7363h
0x180006090  jnz     short loc_1800060A6
0x180006092  mov     rdx, [rbp+0A8h]
0x180006099  mov     ecx, [rbp+28h]
0x18000609c  call    _XcptFilter_0
0x1800060a1  mov     [rbp+30h], eax
0x1800060a4  jmp     short loc_1800060AD
0x1800060a6  mov     dword ptr [rbp+30h], 0
0x1800060ad  mov     eax, [rbp+30h]
0x1800060b0  add     rsp, 20h
0x1800060b4  pop     rbp
0x1800060b5  retn
0x1800060b7  push    rbp
0x1800060b9  sub     rsp, 20h
0x1800060bd  mov     rbp, rdx
0x1800060c0  mov     rax, [rcx]
0x1800060c3  mov     edx, [rax]
0x1800060c5  mov     [rbp+0B0h], rcx
0x1800060cc  mov     [rbp+38h], edx
0x1800060cf  mov     eax, [rbp+38h]
0x1800060d2  cmp     eax, 0E06D7363h
0x1800060d7  jnz     short loc_1800060ED
0x1800060d9  mov     rdx, [rbp+0B0h]
0x1800060e0  mov     ecx, [rbp+38h]
0x1800060e3  call    _XcptFilter_0
0x1800060e8  mov     [rbp+40h], eax
0x1800060eb  jmp     short loc_1800060F4
0x1800060ed  mov     dword ptr [rbp+40h], 0
0x1800060f4  mov     eax, [rbp+40h]
0x1800060f7  add     rsp, 20h
0x1800060fb  pop     rbp
0x1800060fc  retn
0x1800060fe  push    rbp
0x180006100  sub     rsp, 20h
0x180006104  mov     rbp, rdx
0x180006107  mov     rax, [rcx]
0x18000610a  mov     edx, [rax]
0x18000610c  mov     [rbp+0B8h], rcx
0x180006113  mov     [rbp+48h], edx
0x180006116  mov     eax, [rbp+48h]
0x180006119  cmp     eax, 0E06D7363h
0x18000611e  jnz     short loc_180006134
0x180006120  mov     rdx, [rbp+0B8h]
0x180006127  mov     ecx, [rbp+48h]
0x18000612a  call    _XcptFilter_0
0x18000612f  mov     [rbp+50h], eax
0x180006132  jmp     short loc_18000613B
0x180006134  mov     dword ptr [rbp+50h], 0
0x18000613b  mov     eax, [rbp+50h]
0x18000613e  add     rsp, 20h
0x180006142  pop     rbp
0x180006143  retn
0x180006145  push    rbp
0x180006147  sub     rsp, 20h
0x18000614b  mov     rbp, rdx
0x18000614e  mov     rax, [rcx]
0x180006151  mov     edx, [rax]
0x180006153  mov     [rbp+0C0h], rcx
0x18000615a  mov     [rbp+58h], edx
0x18000615d  mov     eax, [rbp+58h]
0x180006160  cmp     eax, 0E06D7363h
0x180006165  jnz     short loc_18000617B
0x180006167  mov     rdx, [rbp+0C0h]
0x18000616e  mov     ecx, [rbp+58h]
0x180006171  call    _XcptFilter_0
0x180006176  mov     [rbp+60h], eax
0x180006179  jmp     short loc_180006182
0x18000617b  mov     dword ptr [rbp+60h], 0
0x180006182  mov     eax, [rbp+60h]
0x180006185  add     rsp, 20h
0x180006189  pop     rbp
0x18000618a  retn
0x18000618c  push    rbp
0x18000618e  sub     rsp, 20h
0x180006192  mov     rbp, rdx
0x180006195  mov     rax, [rcx]
0x180006198  mov     edx, [rax]
0x18000619a  mov     [rbp+0C8h], rcx
0x1800061a1  mov     [rbp+68h], edx
0x1800061a4  mov     eax, [rbp+68h]
0x1800061a7  cmp     eax, 0E06D7363h
0x1800061ac  jnz     short loc_1800061C2
0x1800061ae  mov     rdx, [rbp+0C8h]
0x1800061b5  mov     ecx, [rbp+68h]
0x1800061b8  call    _XcptFilter_0
0x1800061bd  mov     [rbp+70h], eax
0x1800061c0  jmp     short loc_1800061C9
0x1800061c2  mov     dword ptr [rbp+70h], 0
0x1800061c9  mov     eax, [rbp+70h]
0x1800061cc  add     rsp, 20h
0x1800061d0  pop     rbp
0x1800061d1  retn
0x1800061d3  push    rbp
0x1800061d5  sub     rsp, 20h
0x1800061d9  mov     rbp, rdx
0x1800061dc  mov     rax, [rcx]
0x1800061df  mov     edx, [rax]
0x1800061e1  mov     [rbp+0D0h], rcx
0x1800061e8  mov     [rbp+78h], edx
0x1800061eb  mov     eax, [rbp+78h]
0x1800061ee  cmp     eax, 0E06D7363h
0x1800061f3  jnz     short loc_18000620C
0x1800061f5  mov     rdx, [rbp+0D0h]
0x1800061fc  mov     ecx, [rbp+78h]
0x1800061ff  call    _XcptFilter_0
0x180006204  mov     [rbp+80h], eax
0x18000620a  jmp     short loc_180006216
0x18000620c  mov     dword ptr [rbp+80h], 0
0x180006216  mov     eax, [rbp+80h]
0x18000621c  add     rsp, 20h
0x180006220  pop     rbp
0x180006221  retn
0x180006223  push    rbp
0x180006225  sub     rsp, 20h
0x180006229  mov     rbp, rdx
0x18000622c  mov     rax, [rcx]
0x18000622f  mov     edx, [rax]
0x180006231  mov     [rbp+0D8h], rcx
0x180006238  mov     [rbp+88h], edx
0x18000623e  mov     eax, [rbp+88h]
0x180006244  cmp     eax, 0E06D7363h
0x180006249  jnz     short loc_180006265
0x18000624b  mov     rdx, [rbp+0D8h]
0x180006252  mov     ecx, [rbp+88h]
0x180006258  call    _XcptFilter_0
0x18000625d  mov     [rbp+90h], eax
0x180006263  jmp     short loc_18000626F
0x180006265  mov     dword ptr [rbp+90h], 0
0x18000626f  mov     eax, [rbp+90h]
0x180006275  add     rsp, 20h
0x180006279  pop     rbp
0x18000627a  retn
0x18000627c  push    rbp
0x18000627e  sub     rsp, 20h
0x180006282  mov     rbp, rdx
0x180006285  mov     rax, [rcx]
0x180006288  mov     edx, [rax]
0x18000628a  mov     [rbp+0E0h], rcx
0x180006291  mov     [rbp+98h], edx
0x180006297  mov     eax, [rbp+98h]
0x18000629d  cmp     eax, 0E06D7363h
0x1800062a2  jnz     short loc_1800062BE
0x1800062a4  mov     rdx, [rbp+0E0h]
0x1800062ab  mov     ecx, [rbp+98h]
0x1800062b1  call    _XcptFilter_0
0x1800062b6  mov     [rbp+0A0h], eax
0x1800062bc  jmp     short loc_1800062C8
0x1800062be  mov     dword ptr [rbp+0A0h], 0
0x1800062c8  mov     eax, [rbp+0A0h]
0x1800062ce  add     rsp, 20h
0x1800062d2  pop     rbp
0x1800062d3  retn
0x1800062d5  push    rbp
0x1800062d7  sub     rsp, 20h
0x1800062db  mov     rbp, rdx
0x1800062de  cmp     dword ptr [rbp+118h], 1
0x1800062e5  ja      short loc_1800062F1
0x1800062e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
