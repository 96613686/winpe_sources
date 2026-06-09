# __DllMainCRTStartup

- ea: `0x180001384`
- end: `0x180001590`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001340`

## callees

- `0x180001060`
- `0x180001110`
- `0x180001384`
- `0x1800017ba`
- `0x180011880`

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
  if ( (_DWORD)fdwReason || dword_180026AA0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180026AA4 = 1;
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
            if ( dword_180026AA4 )
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
0x180001384  mov     [rsp+lpvReserved], r8
0x180001389  mov     [rsp+arg_8], edx
0x18000138d  mov     [rsp+arg_0], rcx
0x180001392  push    rbx
0x180001393  push    rsi
0x180001394  push    rdi
0x180001395  sub     rsp, 0F0h
0x18000139c  mov     edi, edx
0x18000139e  mov     rsi, rcx
0x1800013a1  mov     ebx, 1
0x1800013a6  cmp     edx, ebx
0x1800013a8  ja      short loc_1800013B0
0x1800013aa  mov     cs:__native_dllmain_reason, edx
0x1800013b0  test    edx, edx
0x1800013b2  jnz     short loc_1800013C7
0x1800013b4  cmp     cs:dword_180026AA0, edx
0x1800013ba  jnz     short loc_1800013C7
0x1800013bc  xor     ebx, ebx
0x1800013be  mov     [rsp+108h+var_E8], ebx
0x1800013c2  jmp     loc_180001574
0x1800013c7  lea     eax, [rdx-1]
0x1800013ca  cmp     eax, 1
0x1800013cd  ja      loc_180001454
0x1800013d3  mov     rax, cs:_pRawDllMain
0x1800013da  test    rax, rax
0x1800013dd  jz      short loc_180001415
0x1800013df  cmp     edx, 1
0x1800013e2  jnz     short loc_1800013EA
0x1800013e4  mov     cs:dword_180026AA4, edx
0x1800013ea  mov     r8, [rsp+108h+lpvReserved]
0x1800013f2  call    cs:__guard_dispatch_icall_fptr
0x1800013f8  mov     ebx, eax
0x1800013fa  mov     [rsp+108h+var_E8], eax
0x1800013fe  jmp     short loc_180001415
0x180001400  xor     ebx, ebx
0x180001402  mov     [rsp+108h+var_E8], ebx
0x180001406  mov     edi, [rsp+108h+arg_8]
0x18000140d  mov     rsi, [rsp+108h+arg_0]
0x180001415  test    ebx, ebx
0x180001417  jz      loc_180001574
0x18000141d  mov     r8, [rsp+108h+lpvReserved]
0x180001425  mov     edx, edi
0x180001427  mov     rcx, rsi
0x18000142a  call    _CRT_INIT
0x18000142f  mov     ebx, eax
0x180001431  mov     [rsp+108h+var_E8], eax
0x180001435  jmp     short loc_18000144C
0x180001437  xor     ebx, ebx
0x180001439  mov     [rsp+108h+var_E8], ebx
0x18000143d  mov     edi, [rsp+108h+arg_8]
0x180001444  mov     rsi, [rsp+108h+arg_0]
0x18000144c  test    ebx, ebx
0x18000144e  jz      loc_180001574
0x180001454  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000145c  mov     edx, edi; fdwReason
0x18000145e  mov     rcx, rsi; hinstDLL
0x180001461  call    DllMain
0x180001466  mov     ebx, eax
0x180001468  mov     [rsp+108h+var_E8], eax
0x18000146c  jmp     short loc_180001483
0x18000146e  xor     ebx, ebx
0x180001470  mov     [rsp+108h+var_E8], ebx
0x180001474  mov     edi, [rsp+108h+arg_8]
0x18000147b  mov     rsi, [rsp+108h+arg_0]
0x180001483  cmp     edi, 1
0x180001486  jnz     short loc_1800014FF
0x180001488  test    ebx, ebx
0x18000148a  jnz     short loc_1800014FF
0x18000148c  xor     r8d, r8d; lpvReserved
0x18000148f  xor     edx, edx; fdwReason
0x180001491  mov     rcx, rsi; hinstDLL
0x180001494  call    DllMain
0x180001499  jmp     short loc_1800014AE
0x18000149b  mov     edi, [rsp+108h+arg_8]
0x1800014a2  mov     rsi, [rsp+108h+arg_0]
0x1800014aa  mov     ebx, [rsp+108h+var_E8]
0x1800014ae  xor     r8d, r8d
0x1800014b1  xor     edx, edx
0x1800014b3  mov     rcx, rsi
0x1800014b6  call    _CRT_INIT
0x1800014bb  jmp     short loc_1800014D0
0x1800014bd  mov     edi, [rsp+108h+arg_8]
0x1800014c4  mov     rsi, [rsp+108h+arg_0]
0x1800014cc  mov     ebx, [rsp+108h+var_E8]
0x1800014d0  mov     rax, cs:_pRawDllMain
0x1800014d7  test    rax, rax
0x1800014da  jz      short loc_1800014FF
0x1800014dc  xor     r8d, r8d
0x1800014df  xor     edx, edx
0x1800014e1  mov     rcx, rsi
0x1800014e4  call    cs:__guard_dispatch_icall_fptr
0x1800014ea  jmp     short loc_1800014FF
0x1800014ec  mov     edi, [rsp+108h+arg_8]
0x1800014f3  mov     rsi, [rsp+108h+arg_0]
0x1800014fb  mov     ebx, [rsp+108h+var_E8]
0x1800014ff  test    edi, edi
0x180001501  jz      short loc_180001508
0x180001503  cmp     edi, 3
0x180001506  jnz     short loc_180001574
0x180001508  mov     r8, [rsp+108h+lpvReserved]
0x180001510  mov     edx, edi
0x180001512  mov     rcx, rsi
0x180001515  call    _CRT_INIT
0x18000151a  mov     ebx, eax
0x18000151c  mov     [rsp+108h+var_E8], eax
0x180001520  jmp     short loc_180001537
0x180001522  xor     ebx, ebx
0x180001524  mov     [rsp+108h+var_E8], ebx
0x180001528  mov     edi, [rsp+108h+arg_8]
0x18000152f  mov     rsi, [rsp+108h+arg_0]
0x180001537  mov     rax, cs:_pRawDllMain
0x18000153e  test    rax, rax
0x180001541  jz      short loc_180001574
0x180001543  cmp     cs:dword_180026AA4, 0
0x18000154a  jz      short loc_180001574
0x18000154c  mov     r8, [rsp+108h+lpvReserved]
0x180001554  mov     edx, edi
0x180001556  mov     rcx, rsi
0x180001559  call    cs:__guard_dispatch_icall_fptr
0x18000155f  mov     ebx, eax
0x180001561  mov     [rsp+108h+var_E8], eax
0x180001565  jmp     short loc_180001574
0x180001567  xor     ebx, ebx
0x180001569  mov     [rsp+108h+var_E8], ebx
0x18000156d  mov     edi, [rsp+108h+arg_8]
0x180001574  cmp     edi, 1
0x180001577  ja      short loc_180001583
0x180001579  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001583  mov     eax, ebx
0x180001585  add     rsp, 0F0h
0x18000158c  pop     rdi
0x18000158d  pop     rsi
0x18000158e  pop     rbx
0x18000158f  retn
0x1800118f0  push    rbp
0x1800118f2  sub     rsp, 20h
0x1800118f6  mov     rbp, rdx
0x1800118f9  mov     rax, [rcx]
0x1800118fc  mov     edx, [rax]
0x1800118fe  mov     [rbp+0A8h], rcx
0x180011905  mov     [rbp+28h], edx
0x180011908  mov     eax, [rbp+28h]
0x18001190b  cmp     eax, 0E06D7363h
0x180011910  jnz     short loc_180011926
0x180011912  mov     rdx, [rbp+0A8h]
0x180011919  mov     ecx, [rbp+28h]
0x18001191c  call    _XcptFilter_0
0x180011921  mov     [rbp+30h], eax
0x180011924  jmp     short loc_18001192D
0x180011926  mov     dword ptr [rbp+30h], 0
0x18001192d  mov     eax, [rbp+30h]
0x180011930  add     rsp, 20h
0x180011934  pop     rbp
0x180011935  retn
0x180011937  push    rbp
0x180011939  sub     rsp, 20h
0x18001193d  mov     rbp, rdx
0x180011940  mov     rax, [rcx]
0x180011943  mov     edx, [rax]
0x180011945  mov     [rbp+0B0h], rcx
0x18001194c  mov     [rbp+38h], edx
0x18001194f  mov     eax, [rbp+38h]
0x180011952  cmp     eax, 0E06D7363h
0x180011957  jnz     short loc_18001196D
0x180011959  mov     rdx, [rbp+0B0h]
0x180011960  mov     ecx, [rbp+38h]
0x180011963  call    _XcptFilter_0
0x180011968  mov     [rbp+40h], eax
0x18001196b  jmp     short loc_180011974
0x18001196d  mov     dword ptr [rbp+40h], 0
0x180011974  mov     eax, [rbp+40h]
0x180011977  add     rsp, 20h
0x18001197b  pop     rbp
0x18001197c  retn
0x18001197e  push    rbp
0x180011980  sub     rsp, 20h
0x180011984  mov     rbp, rdx
0x180011987  mov     rax, [rcx]
0x18001198a  mov     edx, [rax]
0x18001198c  mov     [rbp+0B8h], rcx
0x180011993  mov     [rbp+48h], edx
0x180011996  mov     eax, [rbp+48h]
0x180011999  cmp     eax, 0E06D7363h
0x18001199e  jnz     short loc_1800119B4
0x1800119a0  mov     rdx, [rbp+0B8h]
0x1800119a7  mov     ecx, [rbp+48h]
0x1800119aa  call    _XcptFilter_0
0x1800119af  mov     [rbp+50h], eax
0x1800119b2  jmp     short loc_1800119BB
0x1800119b4  mov     dword ptr [rbp+50h], 0
0x1800119bb  mov     eax, [rbp+50h]
0x1800119be  add     rsp, 20h
0x1800119c2  pop     rbp
0x1800119c3  retn
0x1800119c5  push    rbp
0x1800119c7  sub     rsp, 20h
0x1800119cb  mov     rbp, rdx
0x1800119ce  mov     rax, [rcx]
0x1800119d1  mov     edx, [rax]
0x1800119d3  mov     [rbp+0C0h], rcx
0x1800119da  mov     [rbp+58h], edx
0x1800119dd  mov     eax, [rbp+58h]
0x1800119e0  cmp     eax, 0E06D7363h
0x1800119e5  jnz     short loc_1800119FB
0x1800119e7  mov     rdx, [rbp+0C0h]
0x1800119ee  mov     ecx, [rbp+58h]
0x1800119f1  call    _XcptFilter_0
0x1800119f6  mov     [rbp+60h], eax
0x1800119f9  jmp     short loc_180011A02
0x1800119fb  mov     dword ptr [rbp+60h], 0
0x180011a02  mov     eax, [rbp+60h]
0x180011a05  add     rsp, 20h
0x180011a09  pop     rbp
0x180011a0a  retn
0x180011a0c  push    rbp
0x180011a0e  sub     rsp, 20h
0x180011a12  mov     rbp, rdx
0x180011a15  mov     rax, [rcx]
0x180011a18  mov     edx, [rax]
0x180011a1a  mov     [rbp+0C8h], rcx
0x180011a21  mov     [rbp+68h], edx
0x180011a24  mov     eax, [rbp+68h]
0x180011a27  cmp     eax, 0E06D7363h
0x180011a2c  jnz     short loc_180011A42
0x180011a2e  mov     rdx, [rbp+0C8h]
0x180011a35  mov     ecx, [rbp+68h]
0x180011a38  call    _XcptFilter_0
0x180011a3d  mov     [rbp+70h], eax
0x180011a40  jmp     short loc_180011A49
0x180011a42  mov     dword ptr [rbp+70h], 0
0x180011a49  mov     eax, [rbp+70h]
0x180011a4c  add     rsp, 20h
0x180011a50  pop     rbp
0x180011a51  retn
0x180011a53  push    rbp
0x180011a55  sub     rsp, 20h
0x180011a59  mov     rbp, rdx
0x180011a5c  mov     rax, [rcx]
0x180011a5f  mov     edx, [rax]
0x180011a61  mov     [rbp+0D0h], rcx
0x180011a68  mov     [rbp+78h], edx
0x180011a6b  mov     eax, [rbp+78h]
0x180011a6e  cmp     eax, 0E06D7363h
0x180011a73  jnz     short loc_180011A8C
0x180011a75  mov     rdx, [rbp+0D0h]
0x180011a7c  mov     ecx, [rbp+78h]
0x180011a7f  call    _XcptFilter_0
0x180011a84  mov     [rbp+80h], eax
0x180011a8a  jmp     short loc_180011A96
0x180011a8c  mov     dword ptr [rbp+80h], 0
0x180011a96  mov     eax, [rbp+80h]
0x180011a9c  add     rsp, 20h
0x180011aa0  pop     rbp
0x180011aa1  retn
0x180011aa3  push    rbp
0x180011aa5  sub     rsp, 20h
0x180011aa9  mov     rbp, rdx
0x180011aac  mov     rax, [rcx]
0x180011aaf  mov     edx, [rax]
0x180011ab1  mov     [rbp+0D8h], rcx
0x180011ab8  mov     [rbp+88h], edx
0x180011abe  mov     eax, [rbp+88h]
0x180011ac4  cmp     eax, 0E06D7363h
0x180011ac9  jnz     short loc_180011AE5
0x180011acb  mov     rdx, [rbp+0D8h]
0x180011ad2  mov     ecx, [rbp+88h]
0x180011ad8  call    _XcptFilter_0
0x180011add  mov     [rbp+90h], eax
0x180011ae3  jmp     short loc_180011AEF
0x180011ae5  mov     dword ptr [rbp+90h], 0
0x180011aef  mov     eax, [rbp+90h]
0x180011af5  add     rsp, 20h
0x180011af9  pop     rbp
0x180011afa  retn
0x180011afc  push    rbp
0x180011afe  sub     rsp, 20h
0x180011b02  mov     rbp, rdx
0x180011b05  mov     rax, [rcx]
0x180011b08  mov     edx, [rax]
0x180011b0a  mov     [rbp+0E0h], rcx
0x180011b11  mov     [rbp+98h], edx
0x180011b17  mov     eax, [rbp+98h]
0x180011b1d  cmp     eax, 0E06D7363h
0x180011b22  jnz     short loc_180011B3E
0x180011b24  mov     rdx, [rbp+0E0h]
0x180011b2b  mov     ecx, [rbp+98h]
0x180011b31  call    _XcptFilter_0
0x180011b36  mov     [rbp+0A0h], eax
0x180011b3c  jmp     short loc_180011B48
0x180011b3e  mov     dword ptr [rbp+0A0h], 0
0x180011b48  mov     eax, [rbp+0A0h]
0x180011b4e  add     rsp, 20h
0x180011b52  pop     rbp
0x180011b53  retn
0x180011b55  push    rbp
0x180011b57  sub     rsp, 20h
0x180011b5b  mov     rbp, rdx
0x180011b5e  cmp     dword ptr [rbp+118h], 1
0x180011b65  ja      short loc_180011B71
0x180011b67  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
