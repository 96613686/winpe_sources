# __DllMainCRTStartup

- ea: `0x1800014d4`
- end: `0x1800016e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x180001260`
- `0x1800014d4`
- `0x180001e11`
- `0x180007210`
- `0x18000b6b0`

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
  if ( (_DWORD)fdwReason || dword_1800122E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800122E4 = 1;
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
            if ( dword_1800122E4 )
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
0x1800014d4  mov     [rsp+lpvReserved], r8
0x1800014d9  mov     [rsp+arg_8], edx
0x1800014dd  mov     [rsp+arg_0], rcx
0x1800014e2  push    rbx
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  sub     rsp, 0F0h
0x1800014ec  mov     edi, edx
0x1800014ee  mov     rsi, rcx
0x1800014f1  mov     ebx, 1
0x1800014f6  cmp     edx, ebx
0x1800014f8  ja      short loc_180001500
0x1800014fa  mov     cs:__native_dllmain_reason, edx
0x180001500  test    edx, edx
0x180001502  jnz     short loc_180001517
0x180001504  cmp     cs:dword_1800122E0, edx
0x18000150a  jnz     short loc_180001517
0x18000150c  xor     ebx, ebx
0x18000150e  mov     [rsp+108h+var_E8], ebx
0x180001512  jmp     loc_1800016C4
0x180001517  lea     eax, [rdx-1]
0x18000151a  cmp     eax, 1
0x18000151d  ja      loc_1800015A4
0x180001523  mov     rax, cs:_pRawDllMain
0x18000152a  test    rax, rax
0x18000152d  jz      short loc_180001565
0x18000152f  cmp     edx, 1
0x180001532  jnz     short loc_18000153A
0x180001534  mov     cs:dword_1800122E4, edx
0x18000153a  mov     r8, [rsp+108h+lpvReserved]
0x180001542  call    cs:__guard_dispatch_icall_fptr
0x180001548  mov     ebx, eax
0x18000154a  mov     [rsp+108h+var_E8], eax
0x18000154e  jmp     short loc_180001565
0x180001550  xor     ebx, ebx
0x180001552  mov     [rsp+108h+var_E8], ebx
0x180001556  mov     edi, [rsp+108h+arg_8]
0x18000155d  mov     rsi, [rsp+108h+arg_0]
0x180001565  test    ebx, ebx
0x180001567  jz      loc_1800016C4
0x18000156d  mov     r8, [rsp+108h+lpvReserved]
0x180001575  mov     edx, edi
0x180001577  mov     rcx, rsi
0x18000157a  call    _CRT_INIT
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_18000159C
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  mov     rsi, [rsp+108h+arg_0]
0x18000159c  test    ebx, ebx
0x18000159e  jz      loc_1800016C4
0x1800015a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800015ac  mov     edx, edi; fdwReason
0x1800015ae  mov     rcx, rsi; hinstDLL
0x1800015b1  call    DllMain
0x1800015b6  mov     ebx, eax
0x1800015b8  mov     [rsp+108h+var_E8], eax
0x1800015bc  jmp     short loc_1800015D3
0x1800015be  xor     ebx, ebx
0x1800015c0  mov     [rsp+108h+var_E8], ebx
0x1800015c4  mov     edi, [rsp+108h+arg_8]
0x1800015cb  mov     rsi, [rsp+108h+arg_0]
0x1800015d3  cmp     edi, 1
0x1800015d6  jnz     short loc_18000164F
0x1800015d8  test    ebx, ebx
0x1800015da  jnz     short loc_18000164F
0x1800015dc  xor     r8d, r8d; lpvReserved
0x1800015df  xor     edx, edx; fdwReason
0x1800015e1  mov     rcx, rsi; hinstDLL
0x1800015e4  call    DllMain
0x1800015e9  jmp     short loc_1800015FE
0x1800015eb  mov     edi, [rsp+108h+arg_8]
0x1800015f2  mov     rsi, [rsp+108h+arg_0]
0x1800015fa  mov     ebx, [rsp+108h+var_E8]
0x1800015fe  xor     r8d, r8d
0x180001601  xor     edx, edx
0x180001603  mov     rcx, rsi
0x180001606  call    _CRT_INIT
0x18000160b  jmp     short loc_180001620
0x18000160d  mov     edi, [rsp+108h+arg_8]
0x180001614  mov     rsi, [rsp+108h+arg_0]
0x18000161c  mov     ebx, [rsp+108h+var_E8]
0x180001620  mov     rax, cs:_pRawDllMain
0x180001627  test    rax, rax
0x18000162a  jz      short loc_18000164F
0x18000162c  xor     r8d, r8d
0x18000162f  xor     edx, edx
0x180001631  mov     rcx, rsi
0x180001634  call    cs:__guard_dispatch_icall_fptr
0x18000163a  jmp     short loc_18000164F
0x18000163c  mov     edi, [rsp+108h+arg_8]
0x180001643  mov     rsi, [rsp+108h+arg_0]
0x18000164b  mov     ebx, [rsp+108h+var_E8]
0x18000164f  test    edi, edi
0x180001651  jz      short loc_180001658
0x180001653  cmp     edi, 3
0x180001656  jnz     short loc_1800016C4
0x180001658  mov     r8, [rsp+108h+lpvReserved]
0x180001660  mov     edx, edi
0x180001662  mov     rcx, rsi
0x180001665  call    _CRT_INIT
0x18000166a  mov     ebx, eax
0x18000166c  mov     [rsp+108h+var_E8], eax
0x180001670  jmp     short loc_180001687
0x180001672  xor     ebx, ebx
0x180001674  mov     [rsp+108h+var_E8], ebx
0x180001678  mov     edi, [rsp+108h+arg_8]
0x18000167f  mov     rsi, [rsp+108h+arg_0]
0x180001687  mov     rax, cs:_pRawDllMain
0x18000168e  test    rax, rax
0x180001691  jz      short loc_1800016C4
0x180001693  cmp     cs:dword_1800122E4, 0
0x18000169a  jz      short loc_1800016C4
0x18000169c  mov     r8, [rsp+108h+lpvReserved]
0x1800016a4  mov     edx, edi
0x1800016a6  mov     rcx, rsi
0x1800016a9  call    cs:__guard_dispatch_icall_fptr
0x1800016af  mov     ebx, eax
0x1800016b1  mov     [rsp+108h+var_E8], eax
0x1800016b5  jmp     short loc_1800016C4
0x1800016b7  xor     ebx, ebx
0x1800016b9  mov     [rsp+108h+var_E8], ebx
0x1800016bd  mov     edi, [rsp+108h+arg_8]
0x1800016c4  cmp     edi, 1
0x1800016c7  ja      short loc_1800016D3
0x1800016c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016d3  mov     eax, ebx
0x1800016d5  add     rsp, 0F0h
0x1800016dc  pop     rdi
0x1800016dd  pop     rsi
0x1800016de  pop     rbx
0x1800016df  retn
0x18000b753  push    rbp
0x18000b755  sub     rsp, 20h
0x18000b759  mov     rbp, rdx
0x18000b75c  mov     rax, [rcx]
0x18000b75f  mov     edx, [rax]
0x18000b761  mov     [rbp+0A8h], rcx
0x18000b768  mov     [rbp+28h], edx
0x18000b76b  mov     eax, [rbp+28h]
0x18000b76e  cmp     eax, 0E06D7363h
0x18000b773  jnz     short loc_18000B789
0x18000b775  mov     rdx, [rbp+0A8h]
0x18000b77c  mov     ecx, [rbp+28h]
0x18000b77f  call    _XcptFilter_0
0x18000b784  mov     [rbp+30h], eax
0x18000b787  jmp     short loc_18000B790
0x18000b789  mov     dword ptr [rbp+30h], 0
0x18000b790  mov     eax, [rbp+30h]
0x18000b793  add     rsp, 20h
0x18000b797  pop     rbp
0x18000b798  retn
0x18000b79a  push    rbp
0x18000b79c  sub     rsp, 20h
0x18000b7a0  mov     rbp, rdx
0x18000b7a3  mov     rax, [rcx]
0x18000b7a6  mov     edx, [rax]
0x18000b7a8  mov     [rbp+0B0h], rcx
0x18000b7af  mov     [rbp+38h], edx
0x18000b7b2  mov     eax, [rbp+38h]
0x18000b7b5  cmp     eax, 0E06D7363h
0x18000b7ba  jnz     short loc_18000B7D0
0x18000b7bc  mov     rdx, [rbp+0B0h]
0x18000b7c3  mov     ecx, [rbp+38h]
0x18000b7c6  call    _XcptFilter_0
0x18000b7cb  mov     [rbp+40h], eax
0x18000b7ce  jmp     short loc_18000B7D7
0x18000b7d0  mov     dword ptr [rbp+40h], 0
0x18000b7d7  mov     eax, [rbp+40h]
0x18000b7da  add     rsp, 20h
0x18000b7de  pop     rbp
0x18000b7df  retn
0x18000b7e1  push    rbp
0x18000b7e3  sub     rsp, 20h
0x18000b7e7  mov     rbp, rdx
0x18000b7ea  mov     rax, [rcx]
0x18000b7ed  mov     edx, [rax]
0x18000b7ef  mov     [rbp+0B8h], rcx
0x18000b7f6  mov     [rbp+48h], edx
0x18000b7f9  mov     eax, [rbp+48h]
0x18000b7fc  cmp     eax, 0E06D7363h
0x18000b801  jnz     short loc_18000B817
0x18000b803  mov     rdx, [rbp+0B8h]
0x18000b80a  mov     ecx, [rbp+48h]
0x18000b80d  call    _XcptFilter_0
0x18000b812  mov     [rbp+50h], eax
0x18000b815  jmp     short loc_18000B81E
0x18000b817  mov     dword ptr [rbp+50h], 0
0x18000b81e  mov     eax, [rbp+50h]
0x18000b821  add     rsp, 20h
0x18000b825  pop     rbp
0x18000b826  retn
0x18000b828  push    rbp
0x18000b82a  sub     rsp, 20h
0x18000b82e  mov     rbp, rdx
0x18000b831  mov     rax, [rcx]
0x18000b834  mov     edx, [rax]
0x18000b836  mov     [rbp+0C0h], rcx
0x18000b83d  mov     [rbp+58h], edx
0x18000b840  mov     eax, [rbp+58h]
0x18000b843  cmp     eax, 0E06D7363h
0x18000b848  jnz     short loc_18000B85E
0x18000b84a  mov     rdx, [rbp+0C0h]
0x18000b851  mov     ecx, [rbp+58h]
0x18000b854  call    _XcptFilter_0
0x18000b859  mov     [rbp+60h], eax
0x18000b85c  jmp     short loc_18000B865
0x18000b85e  mov     dword ptr [rbp+60h], 0
0x18000b865  mov     eax, [rbp+60h]
0x18000b868  add     rsp, 20h
0x18000b86c  pop     rbp
0x18000b86d  retn
0x18000b86f  push    rbp
0x18000b871  sub     rsp, 20h
0x18000b875  mov     rbp, rdx
0x18000b878  mov     rax, [rcx]
0x18000b87b  mov     edx, [rax]
0x18000b87d  mov     [rbp+0C8h], rcx
0x18000b884  mov     [rbp+68h], edx
0x18000b887  mov     eax, [rbp+68h]
0x18000b88a  cmp     eax, 0E06D7363h
0x18000b88f  jnz     short loc_18000B8A5
0x18000b891  mov     rdx, [rbp+0C8h]
0x18000b898  mov     ecx, [rbp+68h]
0x18000b89b  call    _XcptFilter_0
0x18000b8a0  mov     [rbp+70h], eax
0x18000b8a3  jmp     short loc_18000B8AC
0x18000b8a5  mov     dword ptr [rbp+70h], 0
0x18000b8ac  mov     eax, [rbp+70h]
0x18000b8af  add     rsp, 20h
0x18000b8b3  pop     rbp
0x18000b8b4  retn
0x18000b8b6  push    rbp
0x18000b8b8  sub     rsp, 20h
0x18000b8bc  mov     rbp, rdx
0x18000b8bf  mov     rax, [rcx]
0x18000b8c2  mov     edx, [rax]
0x18000b8c4  mov     [rbp+0D0h], rcx
0x18000b8cb  mov     [rbp+78h], edx
0x18000b8ce  mov     eax, [rbp+78h]
0x18000b8d1  cmp     eax, 0E06D7363h
0x18000b8d6  jnz     short loc_18000B8EF
0x18000b8d8  mov     rdx, [rbp+0D0h]
0x18000b8df  mov     ecx, [rbp+78h]
0x18000b8e2  call    _XcptFilter_0
0x18000b8e7  mov     [rbp+80h], eax
0x18000b8ed  jmp     short loc_18000B8F9
0x18000b8ef  mov     dword ptr [rbp+80h], 0
0x18000b8f9  mov     eax, [rbp+80h]
0x18000b8ff  add     rsp, 20h
0x18000b903  pop     rbp
0x18000b904  retn
0x18000b906  push    rbp
0x18000b908  sub     rsp, 20h
0x18000b90c  mov     rbp, rdx
0x18000b90f  mov     rax, [rcx]
0x18000b912  mov     edx, [rax]
0x18000b914  mov     [rbp+0D8h], rcx
0x18000b91b  mov     [rbp+88h], edx
0x18000b921  mov     eax, [rbp+88h]
0x18000b927  cmp     eax, 0E06D7363h
0x18000b92c  jnz     short loc_18000B948
0x18000b92e  mov     rdx, [rbp+0D8h]
0x18000b935  mov     ecx, [rbp+88h]
0x18000b93b  call    _XcptFilter_0
0x18000b940  mov     [rbp+90h], eax
0x18000b946  jmp     short loc_18000B952
0x18000b948  mov     dword ptr [rbp+90h], 0
0x18000b952  mov     eax, [rbp+90h]
0x18000b958  add     rsp, 20h
0x18000b95c  pop     rbp
0x18000b95d  retn
0x18000b95f  push    rbp
0x18000b961  sub     rsp, 20h
0x18000b965  mov     rbp, rdx
0x18000b968  mov     rax, [rcx]
0x18000b96b  mov     edx, [rax]
0x18000b96d  mov     [rbp+0E0h], rcx
0x18000b974  mov     [rbp+98h], edx
0x18000b97a  mov     eax, [rbp+98h]
0x18000b980  cmp     eax, 0E06D7363h
0x18000b985  jnz     short loc_18000B9A1
0x18000b987  mov     rdx, [rbp+0E0h]
0x18000b98e  mov     ecx, [rbp+98h]
0x18000b994  call    _XcptFilter_0
0x18000b999  mov     [rbp+0A0h], eax
0x18000b99f  jmp     short loc_18000B9AB
0x18000b9a1  mov     dword ptr [rbp+0A0h], 0
0x18000b9ab  mov     eax, [rbp+0A0h]
0x18000b9b1  add     rsp, 20h
0x18000b9b5  pop     rbp
0x18000b9b6  retn
0x18000b9b8  push    rbp
0x18000b9ba  sub     rsp, 20h
0x18000b9be  mov     rbp, rdx
0x18000b9c1  cmp     dword ptr [rbp+118h], 1
0x18000b9c8  ja      short loc_18000B9D4
0x18000b9ca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
