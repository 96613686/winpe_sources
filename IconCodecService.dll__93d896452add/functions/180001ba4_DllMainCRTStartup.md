# __DllMainCRTStartup

- ea: `0x180001ba4`
- end: `0x180001db0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001b60`

## callees

- `0x1800018c0`
- `0x180001930`
- `0x180001ba4`
- `0x180001dc6`
- `0x180002380`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x180001ba4  mov     [rsp+lpvReserved], r8
0x180001ba9  mov     [rsp+arg_8], edx
0x180001bad  mov     [rsp+arg_0], rcx
0x180001bb2  push    rbx
0x180001bb3  push    rsi
0x180001bb4  push    rdi
0x180001bb5  sub     rsp, 0F0h
0x180001bbc  mov     edi, edx
0x180001bbe  mov     rsi, rcx
0x180001bc1  mov     ebx, 1
0x180001bc6  cmp     edx, ebx
0x180001bc8  ja      short loc_180001BD0
0x180001bca  mov     cs:__native_dllmain_reason, edx
0x180001bd0  test    edx, edx
0x180001bd2  jnz     short loc_180001BE7
0x180001bd4  cmp     cs:dword_1800060A0, edx
0x180001bda  jnz     short loc_180001BE7
0x180001bdc  xor     ebx, ebx
0x180001bde  mov     [rsp+108h+var_E8], ebx
0x180001be2  jmp     loc_180001D94
0x180001be7  lea     eax, [rdx-1]
0x180001bea  cmp     eax, 1
0x180001bed  ja      loc_180001C74
0x180001bf3  mov     rax, cs:_pRawDllMain
0x180001bfa  test    rax, rax
0x180001bfd  jz      short loc_180001C35
0x180001bff  cmp     edx, 1
0x180001c02  jnz     short loc_180001C0A
0x180001c04  mov     cs:dword_1800060A4, edx
0x180001c0a  mov     r8, [rsp+108h+lpvReserved]
0x180001c12  call    cs:__guard_dispatch_icall_fptr
0x180001c18  mov     ebx, eax
0x180001c1a  mov     [rsp+108h+var_E8], eax
0x180001c1e  jmp     short loc_180001C35
0x180001c20  xor     ebx, ebx
0x180001c22  mov     [rsp+108h+var_E8], ebx
0x180001c26  mov     edi, [rsp+108h+arg_8]
0x180001c2d  mov     rsi, [rsp+108h+arg_0]
0x180001c35  test    ebx, ebx
0x180001c37  jz      loc_180001D94
0x180001c3d  mov     r8, [rsp+108h+lpvReserved]
0x180001c45  mov     edx, edi
0x180001c47  mov     rcx, rsi
0x180001c4a  call    _CRT_INIT
0x180001c4f  mov     ebx, eax
0x180001c51  mov     [rsp+108h+var_E8], eax
0x180001c55  jmp     short loc_180001C6C
0x180001c57  xor     ebx, ebx
0x180001c59  mov     [rsp+108h+var_E8], ebx
0x180001c5d  mov     edi, [rsp+108h+arg_8]
0x180001c64  mov     rsi, [rsp+108h+arg_0]
0x180001c6c  test    ebx, ebx
0x180001c6e  jz      loc_180001D94
0x180001c74  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001c7c  mov     edx, edi; fdwReason
0x180001c7e  mov     rcx, rsi; hinstDLL
0x180001c81  call    DllMain
0x180001c86  mov     ebx, eax
0x180001c88  mov     [rsp+108h+var_E8], eax
0x180001c8c  jmp     short loc_180001CA3
0x180001c8e  xor     ebx, ebx
0x180001c90  mov     [rsp+108h+var_E8], ebx
0x180001c94  mov     edi, [rsp+108h+arg_8]
0x180001c9b  mov     rsi, [rsp+108h+arg_0]
0x180001ca3  cmp     edi, 1
0x180001ca6  jnz     short loc_180001D1F
0x180001ca8  test    ebx, ebx
0x180001caa  jnz     short loc_180001D1F
0x180001cac  xor     r8d, r8d; lpvReserved
0x180001caf  xor     edx, edx; fdwReason
0x180001cb1  mov     rcx, rsi; hinstDLL
0x180001cb4  call    DllMain
0x180001cb9  jmp     short loc_180001CCE
0x180001cbb  mov     edi, [rsp+108h+arg_8]
0x180001cc2  mov     rsi, [rsp+108h+arg_0]
0x180001cca  mov     ebx, [rsp+108h+var_E8]
0x180001cce  xor     r8d, r8d
0x180001cd1  xor     edx, edx
0x180001cd3  mov     rcx, rsi
0x180001cd6  call    _CRT_INIT
0x180001cdb  jmp     short loc_180001CF0
0x180001cdd  mov     edi, [rsp+108h+arg_8]
0x180001ce4  mov     rsi, [rsp+108h+arg_0]
0x180001cec  mov     ebx, [rsp+108h+var_E8]
0x180001cf0  mov     rax, cs:_pRawDllMain
0x180001cf7  test    rax, rax
0x180001cfa  jz      short loc_180001D1F
0x180001cfc  xor     r8d, r8d
0x180001cff  xor     edx, edx
0x180001d01  mov     rcx, rsi
0x180001d04  call    cs:__guard_dispatch_icall_fptr
0x180001d0a  jmp     short loc_180001D1F
0x180001d0c  mov     edi, [rsp+108h+arg_8]
0x180001d13  mov     rsi, [rsp+108h+arg_0]
0x180001d1b  mov     ebx, [rsp+108h+var_E8]
0x180001d1f  test    edi, edi
0x180001d21  jz      short loc_180001D28
0x180001d23  cmp     edi, 3
0x180001d26  jnz     short loc_180001D94
0x180001d28  mov     r8, [rsp+108h+lpvReserved]
0x180001d30  mov     edx, edi
0x180001d32  mov     rcx, rsi
0x180001d35  call    _CRT_INIT
0x180001d3a  mov     ebx, eax
0x180001d3c  mov     [rsp+108h+var_E8], eax
0x180001d40  jmp     short loc_180001D57
0x180001d42  xor     ebx, ebx
0x180001d44  mov     [rsp+108h+var_E8], ebx
0x180001d48  mov     edi, [rsp+108h+arg_8]
0x180001d4f  mov     rsi, [rsp+108h+arg_0]
0x180001d57  mov     rax, cs:_pRawDllMain
0x180001d5e  test    rax, rax
0x180001d61  jz      short loc_180001D94
0x180001d63  cmp     cs:dword_1800060A4, 0
0x180001d6a  jz      short loc_180001D94
0x180001d6c  mov     r8, [rsp+108h+lpvReserved]
0x180001d74  mov     edx, edi
0x180001d76  mov     rcx, rsi
0x180001d79  call    cs:__guard_dispatch_icall_fptr
0x180001d7f  mov     ebx, eax
0x180001d81  mov     [rsp+108h+var_E8], eax
0x180001d85  jmp     short loc_180001D94
0x180001d87  xor     ebx, ebx
0x180001d89  mov     [rsp+108h+var_E8], ebx
0x180001d8d  mov     edi, [rsp+108h+arg_8]
0x180001d94  cmp     edi, 1
0x180001d97  ja      short loc_180001DA3
0x180001d99  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001da3  mov     eax, ebx
0x180001da5  add     rsp, 0F0h
0x180001dac  pop     rdi
0x180001dad  pop     rsi
0x180001dae  pop     rbx
0x180001daf  retn
0x1800023f0  push    rbp
0x1800023f2  sub     rsp, 20h
0x1800023f6  mov     rbp, rdx
0x1800023f9  mov     rax, [rcx]
0x1800023fc  mov     edx, [rax]
0x1800023fe  mov     [rbp+0A8h], rcx
0x180002405  mov     [rbp+28h], edx
0x180002408  mov     eax, [rbp+28h]
0x18000240b  cmp     eax, 0E06D7363h
0x180002410  jnz     short loc_180002426
0x180002412  mov     rdx, [rbp+0A8h]
0x180002419  mov     ecx, [rbp+28h]
0x18000241c  call    _XcptFilter_0
0x180002421  mov     [rbp+30h], eax
0x180002424  jmp     short loc_18000242D
0x180002426  mov     dword ptr [rbp+30h], 0
0x18000242d  mov     eax, [rbp+30h]
0x180002430  add     rsp, 20h
0x180002434  pop     rbp
0x180002435  retn
0x180002437  push    rbp
0x180002439  sub     rsp, 20h
0x18000243d  mov     rbp, rdx
0x180002440  mov     rax, [rcx]
0x180002443  mov     edx, [rax]
0x180002445  mov     [rbp+0B0h], rcx
0x18000244c  mov     [rbp+38h], edx
0x18000244f  mov     eax, [rbp+38h]
0x180002452  cmp     eax, 0E06D7363h
0x180002457  jnz     short loc_18000246D
0x180002459  mov     rdx, [rbp+0B0h]
0x180002460  mov     ecx, [rbp+38h]
0x180002463  call    _XcptFilter_0
0x180002468  mov     [rbp+40h], eax
0x18000246b  jmp     short loc_180002474
0x18000246d  mov     dword ptr [rbp+40h], 0
0x180002474  mov     eax, [rbp+40h]
0x180002477  add     rsp, 20h
0x18000247b  pop     rbp
0x18000247c  retn
0x18000247e  push    rbp
0x180002480  sub     rsp, 20h
0x180002484  mov     rbp, rdx
0x180002487  mov     rax, [rcx]
0x18000248a  mov     edx, [rax]
0x18000248c  mov     [rbp+0B8h], rcx
0x180002493  mov     [rbp+48h], edx
0x180002496  mov     eax, [rbp+48h]
0x180002499  cmp     eax, 0E06D7363h
0x18000249e  jnz     short loc_1800024B4
0x1800024a0  mov     rdx, [rbp+0B8h]
0x1800024a7  mov     ecx, [rbp+48h]
0x1800024aa  call    _XcptFilter_0
0x1800024af  mov     [rbp+50h], eax
0x1800024b2  jmp     short loc_1800024BB
0x1800024b4  mov     dword ptr [rbp+50h], 0
0x1800024bb  mov     eax, [rbp+50h]
0x1800024be  add     rsp, 20h
0x1800024c2  pop     rbp
0x1800024c3  retn
0x1800024c5  push    rbp
0x1800024c7  sub     rsp, 20h
0x1800024cb  mov     rbp, rdx
0x1800024ce  mov     rax, [rcx]
0x1800024d1  mov     edx, [rax]
0x1800024d3  mov     [rbp+0C0h], rcx
0x1800024da  mov     [rbp+58h], edx
0x1800024dd  mov     eax, [rbp+58h]
0x1800024e0  cmp     eax, 0E06D7363h
0x1800024e5  jnz     short loc_1800024FB
0x1800024e7  mov     rdx, [rbp+0C0h]
0x1800024ee  mov     ecx, [rbp+58h]
0x1800024f1  call    _XcptFilter_0
0x1800024f6  mov     [rbp+60h], eax
0x1800024f9  jmp     short loc_180002502
0x1800024fb  mov     dword ptr [rbp+60h], 0
0x180002502  mov     eax, [rbp+60h]
0x180002505  add     rsp, 20h
0x180002509  pop     rbp
0x18000250a  retn
0x18000250c  push    rbp
0x18000250e  sub     rsp, 20h
0x180002512  mov     rbp, rdx
0x180002515  mov     rax, [rcx]
0x180002518  mov     edx, [rax]
0x18000251a  mov     [rbp+0C8h], rcx
0x180002521  mov     [rbp+68h], edx
0x180002524  mov     eax, [rbp+68h]
0x180002527  cmp     eax, 0E06D7363h
0x18000252c  jnz     short loc_180002542
0x18000252e  mov     rdx, [rbp+0C8h]
0x180002535  mov     ecx, [rbp+68h]
0x180002538  call    _XcptFilter_0
0x18000253d  mov     [rbp+70h], eax
0x180002540  jmp     short loc_180002549
0x180002542  mov     dword ptr [rbp+70h], 0
0x180002549  mov     eax, [rbp+70h]
0x18000254c  add     rsp, 20h
0x180002550  pop     rbp
0x180002551  retn
0x180002553  push    rbp
0x180002555  sub     rsp, 20h
0x180002559  mov     rbp, rdx
0x18000255c  mov     rax, [rcx]
0x18000255f  mov     edx, [rax]
0x180002561  mov     [rbp+0D0h], rcx
0x180002568  mov     [rbp+78h], edx
0x18000256b  mov     eax, [rbp+78h]
0x18000256e  cmp     eax, 0E06D7363h
0x180002573  jnz     short loc_18000258C
0x180002575  mov     rdx, [rbp+0D0h]
0x18000257c  mov     ecx, [rbp+78h]
0x18000257f  call    _XcptFilter_0
0x180002584  mov     [rbp+80h], eax
0x18000258a  jmp     short loc_180002596
0x18000258c  mov     dword ptr [rbp+80h], 0
0x180002596  mov     eax, [rbp+80h]
0x18000259c  add     rsp, 20h
0x1800025a0  pop     rbp
0x1800025a1  retn
0x1800025a3  push    rbp
0x1800025a5  sub     rsp, 20h
0x1800025a9  mov     rbp, rdx
0x1800025ac  mov     rax, [rcx]
0x1800025af  mov     edx, [rax]
0x1800025b1  mov     [rbp+0D8h], rcx
0x1800025b8  mov     [rbp+88h], edx
0x1800025be  mov     eax, [rbp+88h]
0x1800025c4  cmp     eax, 0E06D7363h
0x1800025c9  jnz     short loc_1800025E5
0x1800025cb  mov     rdx, [rbp+0D8h]
0x1800025d2  mov     ecx, [rbp+88h]
0x1800025d8  call    _XcptFilter_0
0x1800025dd  mov     [rbp+90h], eax
0x1800025e3  jmp     short loc_1800025EF
0x1800025e5  mov     dword ptr [rbp+90h], 0
0x1800025ef  mov     eax, [rbp+90h]
0x1800025f5  add     rsp, 20h
0x1800025f9  pop     rbp
0x1800025fa  retn
0x1800025fc  push    rbp
0x1800025fe  sub     rsp, 20h
0x180002602  mov     rbp, rdx
0x180002605  mov     rax, [rcx]
0x180002608  mov     edx, [rax]
0x18000260a  mov     [rbp+0E0h], rcx
0x180002611  mov     [rbp+98h], edx
0x180002617  mov     eax, [rbp+98h]
0x18000261d  cmp     eax, 0E06D7363h
0x180002622  jnz     short loc_18000263E
0x180002624  mov     rdx, [rbp+0E0h]
0x18000262b  mov     ecx, [rbp+98h]
0x180002631  call    _XcptFilter_0
0x180002636  mov     [rbp+0A0h], eax
0x18000263c  jmp     short loc_180002648
0x18000263e  mov     dword ptr [rbp+0A0h], 0
0x180002648  mov     eax, [rbp+0A0h]
0x18000264e  add     rsp, 20h
0x180002652  pop     rbp
0x180002653  retn
0x180002655  push    rbp
0x180002657  sub     rsp, 20h
0x18000265b  mov     rbp, rdx
0x18000265e  cmp     dword ptr [rbp+118h], 1
0x180002665  ja      short loc_180002671
0x180002667  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
