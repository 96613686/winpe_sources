# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x1800027c0`
- `0x180003320`

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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800060A0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800060A4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800060A4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180003376  push    rbp
0x180003378  sub     rsp, 20h
0x18000337c  mov     rbp, rdx
0x18000337f  mov     rax, [rcx]
0x180003382  mov     edx, [rax]
0x180003384  mov     [rbp+0A8h], rcx
0x18000338b  mov     [rbp+28h], edx
0x18000338e  mov     eax, [rbp+28h]
0x180003391  cmp     eax, 0E06D7363h
0x180003396  jnz     short loc_1800033AC
0x180003398  mov     rdx, [rbp+0A8h]
0x18000339f  mov     ecx, [rbp+28h]
0x1800033a2  call    _XcptFilter_0
0x1800033a7  mov     [rbp+30h], eax
0x1800033aa  jmp     short loc_1800033B3
0x1800033ac  mov     dword ptr [rbp+30h], 0
0x1800033b3  mov     eax, [rbp+30h]
0x1800033b6  add     rsp, 20h
0x1800033ba  pop     rbp
0x1800033bb  retn
0x1800033bd  push    rbp
0x1800033bf  sub     rsp, 20h
0x1800033c3  mov     rbp, rdx
0x1800033c6  mov     rax, [rcx]
0x1800033c9  mov     edx, [rax]
0x1800033cb  mov     [rbp+0B0h], rcx
0x1800033d2  mov     [rbp+38h], edx
0x1800033d5  mov     eax, [rbp+38h]
0x1800033d8  cmp     eax, 0E06D7363h
0x1800033dd  jnz     short loc_1800033F3
0x1800033df  mov     rdx, [rbp+0B0h]
0x1800033e6  mov     ecx, [rbp+38h]
0x1800033e9  call    _XcptFilter_0
0x1800033ee  mov     [rbp+40h], eax
0x1800033f1  jmp     short loc_1800033FA
0x1800033f3  mov     dword ptr [rbp+40h], 0
0x1800033fa  mov     eax, [rbp+40h]
0x1800033fd  add     rsp, 20h
0x180003401  pop     rbp
0x180003402  retn
0x180003404  push    rbp
0x180003406  sub     rsp, 20h
0x18000340a  mov     rbp, rdx
0x18000340d  mov     rax, [rcx]
0x180003410  mov     edx, [rax]
0x180003412  mov     [rbp+0B8h], rcx
0x180003419  mov     [rbp+48h], edx
0x18000341c  mov     eax, [rbp+48h]
0x18000341f  cmp     eax, 0E06D7363h
0x180003424  jnz     short loc_18000343A
0x180003426  mov     rdx, [rbp+0B8h]
0x18000342d  mov     ecx, [rbp+48h]
0x180003430  call    _XcptFilter_0
0x180003435  mov     [rbp+50h], eax
0x180003438  jmp     short loc_180003441
0x18000343a  mov     dword ptr [rbp+50h], 0
0x180003441  mov     eax, [rbp+50h]
0x180003444  add     rsp, 20h
0x180003448  pop     rbp
0x180003449  retn
0x18000344b  push    rbp
0x18000344d  sub     rsp, 20h
0x180003451  mov     rbp, rdx
0x180003454  mov     rax, [rcx]
0x180003457  mov     edx, [rax]
0x180003459  mov     [rbp+0C0h], rcx
0x180003460  mov     [rbp+58h], edx
0x180003463  mov     eax, [rbp+58h]
0x180003466  cmp     eax, 0E06D7363h
0x18000346b  jnz     short loc_180003481
0x18000346d  mov     rdx, [rbp+0C0h]
0x180003474  mov     ecx, [rbp+58h]
0x180003477  call    _XcptFilter_0
0x18000347c  mov     [rbp+60h], eax
0x18000347f  jmp     short loc_180003488
0x180003481  mov     dword ptr [rbp+60h], 0
0x180003488  mov     eax, [rbp+60h]
0x18000348b  add     rsp, 20h
0x18000348f  pop     rbp
0x180003490  retn
0x180003492  push    rbp
0x180003494  sub     rsp, 20h
0x180003498  mov     rbp, rdx
0x18000349b  mov     rax, [rcx]
0x18000349e  mov     edx, [rax]
0x1800034a0  mov     [rbp+0C8h], rcx
0x1800034a7  mov     [rbp+68h], edx
0x1800034aa  mov     eax, [rbp+68h]
0x1800034ad  cmp     eax, 0E06D7363h
0x1800034b2  jnz     short loc_1800034C8
0x1800034b4  mov     rdx, [rbp+0C8h]
0x1800034bb  mov     ecx, [rbp+68h]
0x1800034be  call    _XcptFilter_0
0x1800034c3  mov     [rbp+70h], eax
0x1800034c6  jmp     short loc_1800034CF
0x1800034c8  mov     dword ptr [rbp+70h], 0
0x1800034cf  mov     eax, [rbp+70h]
0x1800034d2  add     rsp, 20h
0x1800034d6  pop     rbp
0x1800034d7  retn
0x1800034d9  push    rbp
0x1800034db  sub     rsp, 20h
0x1800034df  mov     rbp, rdx
0x1800034e2  mov     rax, [rcx]
0x1800034e5  mov     edx, [rax]
0x1800034e7  mov     [rbp+0D0h], rcx
0x1800034ee  mov     [rbp+78h], edx
0x1800034f1  mov     eax, [rbp+78h]
0x1800034f4  cmp     eax, 0E06D7363h
0x1800034f9  jnz     short loc_180003512
0x1800034fb  mov     rdx, [rbp+0D0h]
0x180003502  mov     ecx, [rbp+78h]
0x180003505  call    _XcptFilter_0
0x18000350a  mov     [rbp+80h], eax
0x180003510  jmp     short loc_18000351C
0x180003512  mov     dword ptr [rbp+80h], 0
0x18000351c  mov     eax, [rbp+80h]
0x180003522  add     rsp, 20h
0x180003526  pop     rbp
0x180003527  retn
0x180003529  push    rbp
0x18000352b  sub     rsp, 20h
0x18000352f  mov     rbp, rdx
0x180003532  mov     rax, [rcx]
0x180003535  mov     edx, [rax]
0x180003537  mov     [rbp+0D8h], rcx
0x18000353e  mov     [rbp+88h], edx
0x180003544  mov     eax, [rbp+88h]
0x18000354a  cmp     eax, 0E06D7363h
0x18000354f  jnz     short loc_18000356B
0x180003551  mov     rdx, [rbp+0D8h]
0x180003558  mov     ecx, [rbp+88h]
0x18000355e  call    _XcptFilter_0
0x180003563  mov     [rbp+90h], eax
0x180003569  jmp     short loc_180003575
0x18000356b  mov     dword ptr [rbp+90h], 0
0x180003575  mov     eax, [rbp+90h]
0x18000357b  add     rsp, 20h
0x18000357f  pop     rbp
0x180003580  retn
0x180003582  push    rbp
0x180003584  sub     rsp, 20h
0x180003588  mov     rbp, rdx
0x18000358b  mov     rax, [rcx]
0x18000358e  mov     edx, [rax]
0x180003590  mov     [rbp+0E0h], rcx
0x180003597  mov     [rbp+98h], edx
0x18000359d  mov     eax, [rbp+98h]
0x1800035a3  cmp     eax, 0E06D7363h
0x1800035a8  jnz     short loc_1800035C4
0x1800035aa  mov     rdx, [rbp+0E0h]
0x1800035b1  mov     ecx, [rbp+98h]
0x1800035b7  call    _XcptFilter_0
0x1800035bc  mov     [rbp+0A0h], eax
0x1800035c2  jmp     short loc_1800035CE
0x1800035c4  mov     dword ptr [rbp+0A0h], 0
0x1800035ce  mov     eax, [rbp+0A0h]
0x1800035d4  add     rsp, 20h
0x1800035d8  pop     rbp
0x1800035d9  retn
0x1800035db  push    rbp
0x1800035dd  sub     rsp, 20h
0x1800035e1  mov     rbp, rdx
0x1800035e4  cmp     dword ptr [rbp+118h], 1
0x1800035eb  ja      short loc_1800035F7
0x1800035ed  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
