# __DllMainCRTStartup

- ea: `0x180001504`
- end: `0x180001710`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800014c0`

## callees

- `0x180001290`
- `0x180001504`
- `0x180001b80`
- `0x1800289a8`
- `0x18003d550`

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
  if ( (_DWORD)fdwReason || dword_180050EA0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180050EA4 = 1;
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
            if ( dword_180050EA4 )
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
0x180001504  mov     [rsp+lpvReserved], r8
0x180001509  mov     [rsp+arg_8], edx
0x18000150d  mov     [rsp+arg_0], rcx
0x180001512  push    rbx
0x180001513  push    rsi
0x180001514  push    rdi
0x180001515  sub     rsp, 0F0h
0x18000151c  mov     edi, edx
0x18000151e  mov     rsi, rcx
0x180001521  mov     ebx, 1
0x180001526  cmp     edx, ebx
0x180001528  ja      short loc_180001530
0x18000152a  mov     cs:__native_dllmain_reason, edx
0x180001530  test    edx, edx
0x180001532  jnz     short loc_180001547
0x180001534  cmp     cs:dword_180050EA0, edx
0x18000153a  jnz     short loc_180001547
0x18000153c  xor     ebx, ebx
0x18000153e  mov     [rsp+108h+var_E8], ebx
0x180001542  jmp     loc_1800016F4
0x180001547  lea     eax, [rdx-1]
0x18000154a  cmp     eax, 1
0x18000154d  ja      loc_1800015D4
0x180001553  mov     rax, cs:_pRawDllMain
0x18000155a  test    rax, rax
0x18000155d  jz      short loc_180001595
0x18000155f  cmp     edx, 1
0x180001562  jnz     short loc_18000156A
0x180001564  mov     cs:dword_180050EA4, edx
0x18000156a  mov     r8, [rsp+108h+lpvReserved]
0x180001572  call    cs:__guard_dispatch_icall_fptr
0x180001578  mov     ebx, eax
0x18000157a  mov     [rsp+108h+var_E8], eax
0x18000157e  jmp     short loc_180001595
0x180001580  xor     ebx, ebx
0x180001582  mov     [rsp+108h+var_E8], ebx
0x180001586  mov     edi, [rsp+108h+arg_8]
0x18000158d  mov     rsi, [rsp+108h+arg_0]
0x180001595  test    ebx, ebx
0x180001597  jz      loc_1800016F4
0x18000159d  mov     r8, [rsp+108h+lpvReserved]
0x1800015a5  mov     edx, edi
0x1800015a7  mov     rcx, rsi
0x1800015aa  call    _CRT_INIT
0x1800015af  mov     ebx, eax
0x1800015b1  mov     [rsp+108h+var_E8], eax
0x1800015b5  jmp     short loc_1800015CC
0x1800015b7  xor     ebx, ebx
0x1800015b9  mov     [rsp+108h+var_E8], ebx
0x1800015bd  mov     edi, [rsp+108h+arg_8]
0x1800015c4  mov     rsi, [rsp+108h+arg_0]
0x1800015cc  test    ebx, ebx
0x1800015ce  jz      loc_1800016F4
0x1800015d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800015dc  mov     edx, edi; fdwReason
0x1800015de  mov     rcx, rsi; hinstDLL
0x1800015e1  call    DllMain
0x1800015e6  mov     ebx, eax
0x1800015e8  mov     [rsp+108h+var_E8], eax
0x1800015ec  jmp     short loc_180001603
0x1800015ee  xor     ebx, ebx
0x1800015f0  mov     [rsp+108h+var_E8], ebx
0x1800015f4  mov     edi, [rsp+108h+arg_8]
0x1800015fb  mov     rsi, [rsp+108h+arg_0]
0x180001603  cmp     edi, 1
0x180001606  jnz     short loc_18000167F
0x180001608  test    ebx, ebx
0x18000160a  jnz     short loc_18000167F
0x18000160c  xor     r8d, r8d; lpvReserved
0x18000160f  xor     edx, edx; fdwReason
0x180001611  mov     rcx, rsi; hinstDLL
0x180001614  call    DllMain
0x180001619  jmp     short loc_18000162E
0x18000161b  mov     edi, [rsp+108h+arg_8]
0x180001622  mov     rsi, [rsp+108h+arg_0]
0x18000162a  mov     ebx, [rsp+108h+var_E8]
0x18000162e  xor     r8d, r8d
0x180001631  xor     edx, edx
0x180001633  mov     rcx, rsi
0x180001636  call    _CRT_INIT
0x18000163b  jmp     short loc_180001650
0x18000163d  mov     edi, [rsp+108h+arg_8]
0x180001644  mov     rsi, [rsp+108h+arg_0]
0x18000164c  mov     ebx, [rsp+108h+var_E8]
0x180001650  mov     rax, cs:_pRawDllMain
0x180001657  test    rax, rax
0x18000165a  jz      short loc_18000167F
0x18000165c  xor     r8d, r8d
0x18000165f  xor     edx, edx
0x180001661  mov     rcx, rsi
0x180001664  call    cs:__guard_dispatch_icall_fptr
0x18000166a  jmp     short loc_18000167F
0x18000166c  mov     edi, [rsp+108h+arg_8]
0x180001673  mov     rsi, [rsp+108h+arg_0]
0x18000167b  mov     ebx, [rsp+108h+var_E8]
0x18000167f  test    edi, edi
0x180001681  jz      short loc_180001688
0x180001683  cmp     edi, 3
0x180001686  jnz     short loc_1800016F4
0x180001688  mov     r8, [rsp+108h+lpvReserved]
0x180001690  mov     edx, edi
0x180001692  mov     rcx, rsi
0x180001695  call    _CRT_INIT
0x18000169a  mov     ebx, eax
0x18000169c  mov     [rsp+108h+var_E8], eax
0x1800016a0  jmp     short loc_1800016B7
0x1800016a2  xor     ebx, ebx
0x1800016a4  mov     [rsp+108h+var_E8], ebx
0x1800016a8  mov     edi, [rsp+108h+arg_8]
0x1800016af  mov     rsi, [rsp+108h+arg_0]
0x1800016b7  mov     rax, cs:_pRawDllMain
0x1800016be  test    rax, rax
0x1800016c1  jz      short loc_1800016F4
0x1800016c3  cmp     cs:dword_180050EA4, 0
0x1800016ca  jz      short loc_1800016F4
0x1800016cc  mov     r8, [rsp+108h+lpvReserved]
0x1800016d4  mov     edx, edi
0x1800016d6  mov     rcx, rsi
0x1800016d9  call    cs:__guard_dispatch_icall_fptr
0x1800016df  mov     ebx, eax
0x1800016e1  mov     [rsp+108h+var_E8], eax
0x1800016e5  jmp     short loc_1800016F4
0x1800016e7  xor     ebx, ebx
0x1800016e9  mov     [rsp+108h+var_E8], ebx
0x1800016ed  mov     edi, [rsp+108h+arg_8]
0x1800016f4  cmp     edi, 1
0x1800016f7  ja      short loc_180001703
0x1800016f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001703  mov     eax, ebx
0x180001705  add     rsp, 0F0h
0x18000170c  pop     rdi
0x18000170d  pop     rsi
0x18000170e  pop     rbx
0x18000170f  retn
0x18003d620  push    rbp
0x18003d622  sub     rsp, 20h
0x18003d626  mov     rbp, rdx
0x18003d629  mov     rax, [rcx]
0x18003d62c  mov     edx, [rax]
0x18003d62e  mov     [rbp+0A8h], rcx
0x18003d635  mov     [rbp+28h], edx
0x18003d638  mov     eax, [rbp+28h]
0x18003d63b  cmp     eax, 0E06D7363h
0x18003d640  jnz     short loc_18003D656
0x18003d642  mov     rdx, [rbp+0A8h]
0x18003d649  mov     ecx, [rbp+28h]
0x18003d64c  call    _XcptFilter_0
0x18003d651  mov     [rbp+30h], eax
0x18003d654  jmp     short loc_18003D65D
0x18003d656  mov     dword ptr [rbp+30h], 0
0x18003d65d  mov     eax, [rbp+30h]
0x18003d660  add     rsp, 20h
0x18003d664  pop     rbp
0x18003d665  retn
0x18003d667  push    rbp
0x18003d669  sub     rsp, 20h
0x18003d66d  mov     rbp, rdx
0x18003d670  mov     rax, [rcx]
0x18003d673  mov     edx, [rax]
0x18003d675  mov     [rbp+0B0h], rcx
0x18003d67c  mov     [rbp+38h], edx
0x18003d67f  mov     eax, [rbp+38h]
0x18003d682  cmp     eax, 0E06D7363h
0x18003d687  jnz     short loc_18003D69D
0x18003d689  mov     rdx, [rbp+0B0h]
0x18003d690  mov     ecx, [rbp+38h]
0x18003d693  call    _XcptFilter_0
0x18003d698  mov     [rbp+40h], eax
0x18003d69b  jmp     short loc_18003D6A4
0x18003d69d  mov     dword ptr [rbp+40h], 0
0x18003d6a4  mov     eax, [rbp+40h]
0x18003d6a7  add     rsp, 20h
0x18003d6ab  pop     rbp
0x18003d6ac  retn
0x18003d6ae  push    rbp
0x18003d6b0  sub     rsp, 20h
0x18003d6b4  mov     rbp, rdx
0x18003d6b7  mov     rax, [rcx]
0x18003d6ba  mov     edx, [rax]
0x18003d6bc  mov     [rbp+0B8h], rcx
0x18003d6c3  mov     [rbp+48h], edx
0x18003d6c6  mov     eax, [rbp+48h]
0x18003d6c9  cmp     eax, 0E06D7363h
0x18003d6ce  jnz     short loc_18003D6E4
0x18003d6d0  mov     rdx, [rbp+0B8h]
0x18003d6d7  mov     ecx, [rbp+48h]
0x18003d6da  call    _XcptFilter_0
0x18003d6df  mov     [rbp+50h], eax
0x18003d6e2  jmp     short loc_18003D6EB
0x18003d6e4  mov     dword ptr [rbp+50h], 0
0x18003d6eb  mov     eax, [rbp+50h]
0x18003d6ee  add     rsp, 20h
0x18003d6f2  pop     rbp
0x18003d6f3  retn
0x18003d6f5  push    rbp
0x18003d6f7  sub     rsp, 20h
0x18003d6fb  mov     rbp, rdx
0x18003d6fe  mov     rax, [rcx]
0x18003d701  mov     edx, [rax]
0x18003d703  mov     [rbp+0C0h], rcx
0x18003d70a  mov     [rbp+58h], edx
0x18003d70d  mov     eax, [rbp+58h]
0x18003d710  cmp     eax, 0E06D7363h
0x18003d715  jnz     short loc_18003D72B
0x18003d717  mov     rdx, [rbp+0C0h]
0x18003d71e  mov     ecx, [rbp+58h]
0x18003d721  call    _XcptFilter_0
0x18003d726  mov     [rbp+60h], eax
0x18003d729  jmp     short loc_18003D732
0x18003d72b  mov     dword ptr [rbp+60h], 0
0x18003d732  mov     eax, [rbp+60h]
0x18003d735  add     rsp, 20h
0x18003d739  pop     rbp
0x18003d73a  retn
0x18003d73c  push    rbp
0x18003d73e  sub     rsp, 20h
0x18003d742  mov     rbp, rdx
0x18003d745  mov     rax, [rcx]
0x18003d748  mov     edx, [rax]
0x18003d74a  mov     [rbp+0C8h], rcx
0x18003d751  mov     [rbp+68h], edx
0x18003d754  mov     eax, [rbp+68h]
0x18003d757  cmp     eax, 0E06D7363h
0x18003d75c  jnz     short loc_18003D772
0x18003d75e  mov     rdx, [rbp+0C8h]
0x18003d765  mov     ecx, [rbp+68h]
0x18003d768  call    _XcptFilter_0
0x18003d76d  mov     [rbp+70h], eax
0x18003d770  jmp     short loc_18003D779
0x18003d772  mov     dword ptr [rbp+70h], 0
0x18003d779  mov     eax, [rbp+70h]
0x18003d77c  add     rsp, 20h
0x18003d780  pop     rbp
0x18003d781  retn
0x18003d783  push    rbp
0x18003d785  sub     rsp, 20h
0x18003d789  mov     rbp, rdx
0x18003d78c  mov     rax, [rcx]
0x18003d78f  mov     edx, [rax]
0x18003d791  mov     [rbp+0D0h], rcx
0x18003d798  mov     [rbp+78h], edx
0x18003d79b  mov     eax, [rbp+78h]
0x18003d79e  cmp     eax, 0E06D7363h
0x18003d7a3  jnz     short loc_18003D7BC
0x18003d7a5  mov     rdx, [rbp+0D0h]
0x18003d7ac  mov     ecx, [rbp+78h]
0x18003d7af  call    _XcptFilter_0
0x18003d7b4  mov     [rbp+80h], eax
0x18003d7ba  jmp     short loc_18003D7C6
0x18003d7bc  mov     dword ptr [rbp+80h], 0
0x18003d7c6  mov     eax, [rbp+80h]
0x18003d7cc  add     rsp, 20h
0x18003d7d0  pop     rbp
0x18003d7d1  retn
0x18003d7d3  push    rbp
0x18003d7d5  sub     rsp, 20h
0x18003d7d9  mov     rbp, rdx
0x18003d7dc  mov     rax, [rcx]
0x18003d7df  mov     edx, [rax]
0x18003d7e1  mov     [rbp+0D8h], rcx
0x18003d7e8  mov     [rbp+88h], edx
0x18003d7ee  mov     eax, [rbp+88h]
0x18003d7f4  cmp     eax, 0E06D7363h
0x18003d7f9  jnz     short loc_18003D815
0x18003d7fb  mov     rdx, [rbp+0D8h]
0x18003d802  mov     ecx, [rbp+88h]
0x18003d808  call    _XcptFilter_0
0x18003d80d  mov     [rbp+90h], eax
0x18003d813  jmp     short loc_18003D81F
0x18003d815  mov     dword ptr [rbp+90h], 0
0x18003d81f  mov     eax, [rbp+90h]
0x18003d825  add     rsp, 20h
0x18003d829  pop     rbp
0x18003d82a  retn
0x18003d82c  push    rbp
0x18003d82e  sub     rsp, 20h
0x18003d832  mov     rbp, rdx
0x18003d835  mov     rax, [rcx]
0x18003d838  mov     edx, [rax]
0x18003d83a  mov     [rbp+0E0h], rcx
0x18003d841  mov     [rbp+98h], edx
0x18003d847  mov     eax, [rbp+98h]
0x18003d84d  cmp     eax, 0E06D7363h
0x18003d852  jnz     short loc_18003D86E
0x18003d854  mov     rdx, [rbp+0E0h]
0x18003d85b  mov     ecx, [rbp+98h]
0x18003d861  call    _XcptFilter_0
0x18003d866  mov     [rbp+0A0h], eax
0x18003d86c  jmp     short loc_18003D878
0x18003d86e  mov     dword ptr [rbp+0A0h], 0
0x18003d878  mov     eax, [rbp+0A0h]
0x18003d87e  add     rsp, 20h
0x18003d882  pop     rbp
0x18003d883  retn
0x18003d885  push    rbp
0x18003d887  sub     rsp, 20h
0x18003d88b  mov     rbp, rdx
0x18003d88e  cmp     dword ptr [rbp+118h], 1
0x18003d895  ja      short loc_18003D8A1
0x18003d897  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
