# __DllMainCRTStartup

- ea: `0x1800023d4`
- end: `0x1800025e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002390`

## callees

- `0x180002160`
- `0x1800023d4`
- `0x1800027be`
- `0x180002ffc`
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
  if ( (_DWORD)fdwReason || dword_18001245C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180012460 = 1;
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
            if ( dword_180012460 )
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
0x1800023d4  mov     [rsp+lpvReserved], r8
0x1800023d9  mov     [rsp+arg_8], edx
0x1800023dd  mov     [rsp+arg_0], rcx
0x1800023e2  push    rbx
0x1800023e3  push    rsi
0x1800023e4  push    rdi
0x1800023e5  sub     rsp, 0F0h
0x1800023ec  mov     edi, edx
0x1800023ee  mov     rsi, rcx
0x1800023f1  mov     ebx, 1
0x1800023f6  cmp     edx, ebx
0x1800023f8  ja      short loc_180002400
0x1800023fa  mov     cs:__native_dllmain_reason, edx
0x180002400  test    edx, edx
0x180002402  jnz     short loc_180002417
0x180002404  cmp     cs:dword_18001245C, edx
0x18000240a  jnz     short loc_180002417
0x18000240c  xor     ebx, ebx
0x18000240e  mov     [rsp+108h+var_E8], ebx
0x180002412  jmp     loc_1800025C4
0x180002417  lea     eax, [rdx-1]
0x18000241a  cmp     eax, 1
0x18000241d  ja      loc_1800024A4
0x180002423  mov     rax, cs:_pRawDllMain
0x18000242a  test    rax, rax
0x18000242d  jz      short loc_180002465
0x18000242f  cmp     edx, 1
0x180002432  jnz     short loc_18000243A
0x180002434  mov     cs:dword_180012460, edx
0x18000243a  mov     r8, [rsp+108h+lpvReserved]
0x180002442  call    cs:__guard_dispatch_icall_fptr
0x180002448  mov     ebx, eax
0x18000244a  mov     [rsp+108h+var_E8], eax
0x18000244e  jmp     short loc_180002465
0x180002450  xor     ebx, ebx
0x180002452  mov     [rsp+108h+var_E8], ebx
0x180002456  mov     edi, [rsp+108h+arg_8]
0x18000245d  mov     rsi, [rsp+108h+arg_0]
0x180002465  test    ebx, ebx
0x180002467  jz      loc_1800025C4
0x18000246d  mov     r8, [rsp+108h+lpvReserved]
0x180002475  mov     edx, edi
0x180002477  mov     rcx, rsi
0x18000247a  call    _CRT_INIT
0x18000247f  mov     ebx, eax
0x180002481  mov     [rsp+108h+var_E8], eax
0x180002485  jmp     short loc_18000249C
0x180002487  xor     ebx, ebx
0x180002489  mov     [rsp+108h+var_E8], ebx
0x18000248d  mov     edi, [rsp+108h+arg_8]
0x180002494  mov     rsi, [rsp+108h+arg_0]
0x18000249c  test    ebx, ebx
0x18000249e  jz      loc_1800025C4
0x1800024a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800024ac  mov     edx, edi; fdwReason
0x1800024ae  mov     rcx, rsi; hinstDLL
0x1800024b1  call    DllMain
0x1800024b6  mov     ebx, eax
0x1800024b8  mov     [rsp+108h+var_E8], eax
0x1800024bc  jmp     short loc_1800024D3
0x1800024be  xor     ebx, ebx
0x1800024c0  mov     [rsp+108h+var_E8], ebx
0x1800024c4  mov     edi, [rsp+108h+arg_8]
0x1800024cb  mov     rsi, [rsp+108h+arg_0]
0x1800024d3  cmp     edi, 1
0x1800024d6  jnz     short loc_18000254F
0x1800024d8  test    ebx, ebx
0x1800024da  jnz     short loc_18000254F
0x1800024dc  xor     r8d, r8d; lpvReserved
0x1800024df  xor     edx, edx; fdwReason
0x1800024e1  mov     rcx, rsi; hinstDLL
0x1800024e4  call    DllMain
0x1800024e9  jmp     short loc_1800024FE
0x1800024eb  mov     edi, [rsp+108h+arg_8]
0x1800024f2  mov     rsi, [rsp+108h+arg_0]
0x1800024fa  mov     ebx, [rsp+108h+var_E8]
0x1800024fe  xor     r8d, r8d
0x180002501  xor     edx, edx
0x180002503  mov     rcx, rsi
0x180002506  call    _CRT_INIT
0x18000250b  jmp     short loc_180002520
0x18000250d  mov     edi, [rsp+108h+arg_8]
0x180002514  mov     rsi, [rsp+108h+arg_0]
0x18000251c  mov     ebx, [rsp+108h+var_E8]
0x180002520  mov     rax, cs:_pRawDllMain
0x180002527  test    rax, rax
0x18000252a  jz      short loc_18000254F
0x18000252c  xor     r8d, r8d
0x18000252f  xor     edx, edx
0x180002531  mov     rcx, rsi
0x180002534  call    cs:__guard_dispatch_icall_fptr
0x18000253a  jmp     short loc_18000254F
0x18000253c  mov     edi, [rsp+108h+arg_8]
0x180002543  mov     rsi, [rsp+108h+arg_0]
0x18000254b  mov     ebx, [rsp+108h+var_E8]
0x18000254f  test    edi, edi
0x180002551  jz      short loc_180002558
0x180002553  cmp     edi, 3
0x180002556  jnz     short loc_1800025C4
0x180002558  mov     r8, [rsp+108h+lpvReserved]
0x180002560  mov     edx, edi
0x180002562  mov     rcx, rsi
0x180002565  call    _CRT_INIT
0x18000256a  mov     ebx, eax
0x18000256c  mov     [rsp+108h+var_E8], eax
0x180002570  jmp     short loc_180002587
0x180002572  xor     ebx, ebx
0x180002574  mov     [rsp+108h+var_E8], ebx
0x180002578  mov     edi, [rsp+108h+arg_8]
0x18000257f  mov     rsi, [rsp+108h+arg_0]
0x180002587  mov     rax, cs:_pRawDllMain
0x18000258e  test    rax, rax
0x180002591  jz      short loc_1800025C4
0x180002593  cmp     cs:dword_180012460, 0
0x18000259a  jz      short loc_1800025C4
0x18000259c  mov     r8, [rsp+108h+lpvReserved]
0x1800025a4  mov     edx, edi
0x1800025a6  mov     rcx, rsi
0x1800025a9  call    cs:__guard_dispatch_icall_fptr
0x1800025af  mov     ebx, eax
0x1800025b1  mov     [rsp+108h+var_E8], eax
0x1800025b5  jmp     short loc_1800025C4
0x1800025b7  xor     ebx, ebx
0x1800025b9  mov     [rsp+108h+var_E8], ebx
0x1800025bd  mov     edi, [rsp+108h+arg_8]
0x1800025c4  cmp     edi, 1
0x1800025c7  ja      short loc_1800025D3
0x1800025c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800025d3  mov     eax, ebx
0x1800025d5  add     rsp, 0F0h
0x1800025dc  pop     rdi
0x1800025dd  pop     rsi
0x1800025de  pop     rbx
0x1800025df  retn
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
