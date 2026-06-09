# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x1800023a8`
- `0x180002690`

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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_1800060A0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_1800060A4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_1800060A4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180002700  push    rbp
0x180002702  sub     rsp, 20h
0x180002706  mov     rbp, rdx
0x180002709  mov     rax, [rcx]
0x18000270c  mov     edx, [rax]
0x18000270e  mov     [rbp+0A8h], rcx
0x180002715  mov     [rbp+28h], edx
0x180002718  mov     eax, [rbp+28h]
0x18000271b  cmp     eax, 0E06D7363h
0x180002720  jnz     short loc_180002736
0x180002722  mov     rdx, [rbp+0A8h]
0x180002729  mov     ecx, [rbp+28h]
0x18000272c  call    _XcptFilter_0
0x180002731  mov     [rbp+30h], eax
0x180002734  jmp     short loc_18000273D
0x180002736  mov     dword ptr [rbp+30h], 0
0x18000273d  mov     eax, [rbp+30h]
0x180002740  add     rsp, 20h
0x180002744  pop     rbp
0x180002745  retn
0x180002747  push    rbp
0x180002749  sub     rsp, 20h
0x18000274d  mov     rbp, rdx
0x180002750  mov     rax, [rcx]
0x180002753  mov     edx, [rax]
0x180002755  mov     [rbp+0B0h], rcx
0x18000275c  mov     [rbp+38h], edx
0x18000275f  mov     eax, [rbp+38h]
0x180002762  cmp     eax, 0E06D7363h
0x180002767  jnz     short loc_18000277D
0x180002769  mov     rdx, [rbp+0B0h]
0x180002770  mov     ecx, [rbp+38h]
0x180002773  call    _XcptFilter_0
0x180002778  mov     [rbp+40h], eax
0x18000277b  jmp     short loc_180002784
0x18000277d  mov     dword ptr [rbp+40h], 0
0x180002784  mov     eax, [rbp+40h]
0x180002787  add     rsp, 20h
0x18000278b  pop     rbp
0x18000278c  retn
0x18000278e  push    rbp
0x180002790  sub     rsp, 20h
0x180002794  mov     rbp, rdx
0x180002797  mov     rax, [rcx]
0x18000279a  mov     edx, [rax]
0x18000279c  mov     [rbp+0B8h], rcx
0x1800027a3  mov     [rbp+48h], edx
0x1800027a6  mov     eax, [rbp+48h]
0x1800027a9  cmp     eax, 0E06D7363h
0x1800027ae  jnz     short loc_1800027C4
0x1800027b0  mov     rdx, [rbp+0B8h]
0x1800027b7  mov     ecx, [rbp+48h]
0x1800027ba  call    _XcptFilter_0
0x1800027bf  mov     [rbp+50h], eax
0x1800027c2  jmp     short loc_1800027CB
0x1800027c4  mov     dword ptr [rbp+50h], 0
0x1800027cb  mov     eax, [rbp+50h]
0x1800027ce  add     rsp, 20h
0x1800027d2  pop     rbp
0x1800027d3  retn
0x1800027d5  push    rbp
0x1800027d7  sub     rsp, 20h
0x1800027db  mov     rbp, rdx
0x1800027de  mov     rax, [rcx]
0x1800027e1  mov     edx, [rax]
0x1800027e3  mov     [rbp+0C0h], rcx
0x1800027ea  mov     [rbp+58h], edx
0x1800027ed  mov     eax, [rbp+58h]
0x1800027f0  cmp     eax, 0E06D7363h
0x1800027f5  jnz     short loc_18000280B
0x1800027f7  mov     rdx, [rbp+0C0h]
0x1800027fe  mov     ecx, [rbp+58h]
0x180002801  call    _XcptFilter_0
0x180002806  mov     [rbp+60h], eax
0x180002809  jmp     short loc_180002812
0x18000280b  mov     dword ptr [rbp+60h], 0
0x180002812  mov     eax, [rbp+60h]
0x180002815  add     rsp, 20h
0x180002819  pop     rbp
0x18000281a  retn
0x18000281c  push    rbp
0x18000281e  sub     rsp, 20h
0x180002822  mov     rbp, rdx
0x180002825  mov     rax, [rcx]
0x180002828  mov     edx, [rax]
0x18000282a  mov     [rbp+0C8h], rcx
0x180002831  mov     [rbp+68h], edx
0x180002834  mov     eax, [rbp+68h]
0x180002837  cmp     eax, 0E06D7363h
0x18000283c  jnz     short loc_180002852
0x18000283e  mov     rdx, [rbp+0C8h]
0x180002845  mov     ecx, [rbp+68h]
0x180002848  call    _XcptFilter_0
0x18000284d  mov     [rbp+70h], eax
0x180002850  jmp     short loc_180002859
0x180002852  mov     dword ptr [rbp+70h], 0
0x180002859  mov     eax, [rbp+70h]
0x18000285c  add     rsp, 20h
0x180002860  pop     rbp
0x180002861  retn
0x180002863  push    rbp
0x180002865  sub     rsp, 20h
0x180002869  mov     rbp, rdx
0x18000286c  mov     rax, [rcx]
0x18000286f  mov     edx, [rax]
0x180002871  mov     [rbp+0D0h], rcx
0x180002878  mov     [rbp+78h], edx
0x18000287b  mov     eax, [rbp+78h]
0x18000287e  cmp     eax, 0E06D7363h
0x180002883  jnz     short loc_18000289C
0x180002885  mov     rdx, [rbp+0D0h]
0x18000288c  mov     ecx, [rbp+78h]
0x18000288f  call    _XcptFilter_0
0x180002894  mov     [rbp+80h], eax
0x18000289a  jmp     short loc_1800028A6
0x18000289c  mov     dword ptr [rbp+80h], 0
0x1800028a6  mov     eax, [rbp+80h]
0x1800028ac  add     rsp, 20h
0x1800028b0  pop     rbp
0x1800028b1  retn
0x1800028b3  push    rbp
0x1800028b5  sub     rsp, 20h
0x1800028b9  mov     rbp, rdx
0x1800028bc  mov     rax, [rcx]
0x1800028bf  mov     edx, [rax]
0x1800028c1  mov     [rbp+0D8h], rcx
0x1800028c8  mov     [rbp+88h], edx
0x1800028ce  mov     eax, [rbp+88h]
0x1800028d4  cmp     eax, 0E06D7363h
0x1800028d9  jnz     short loc_1800028F5
0x1800028db  mov     rdx, [rbp+0D8h]
0x1800028e2  mov     ecx, [rbp+88h]
0x1800028e8  call    _XcptFilter_0
0x1800028ed  mov     [rbp+90h], eax
0x1800028f3  jmp     short loc_1800028FF
0x1800028f5  mov     dword ptr [rbp+90h], 0
0x1800028ff  mov     eax, [rbp+90h]
0x180002905  add     rsp, 20h
0x180002909  pop     rbp
0x18000290a  retn
0x18000290c  push    rbp
0x18000290e  sub     rsp, 20h
0x180002912  mov     rbp, rdx
0x180002915  mov     rax, [rcx]
0x180002918  mov     edx, [rax]
0x18000291a  mov     [rbp+0E0h], rcx
0x180002921  mov     [rbp+98h], edx
0x180002927  mov     eax, [rbp+98h]
0x18000292d  cmp     eax, 0E06D7363h
0x180002932  jnz     short loc_18000294E
0x180002934  mov     rdx, [rbp+0E0h]
0x18000293b  mov     ecx, [rbp+98h]
0x180002941  call    _XcptFilter_0
0x180002946  mov     [rbp+0A0h], eax
0x18000294c  jmp     short loc_180002958
0x18000294e  mov     dword ptr [rbp+0A0h], 0
0x180002958  mov     eax, [rbp+0A0h]
0x18000295e  add     rsp, 20h
0x180002962  pop     rbp
0x180002963  retn
0x180002965  push    rbp
0x180002967  sub     rsp, 20h
0x18000296b  mov     rbp, rdx
0x18000296e  cmp     dword ptr [rbp+118h], 1
0x180002975  ja      short loc_180002981
0x180002977  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
