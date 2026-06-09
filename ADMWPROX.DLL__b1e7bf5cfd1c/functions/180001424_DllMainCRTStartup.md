# __DllMainCRTStartup

- ea: `0x180001424`
- end: `0x180001630`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800013e0`

## callees

- `0x1800011b0`
- `0x180001424`
- `0x180001666`
- `0x180002400`
- `0x180008450`

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
  if ( (_DWORD)fdwReason || dword_18000F5A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F5A4 = 1;
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
            if ( dword_18000F5A4 )
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
0x180001424  mov     [rsp+lpvReserved], r8
0x180001429  mov     [rsp+arg_8], edx
0x18000142d  mov     [rsp+arg_0], rcx
0x180001432  push    rbx
0x180001433  push    rsi
0x180001434  push    rdi
0x180001435  sub     rsp, 0F0h
0x18000143c  mov     edi, edx
0x18000143e  mov     rsi, rcx
0x180001441  mov     ebx, 1
0x180001446  cmp     edx, ebx
0x180001448  ja      short loc_180001450
0x18000144a  mov     cs:__native_dllmain_reason, edx
0x180001450  test    edx, edx
0x180001452  jnz     short loc_180001467
0x180001454  cmp     cs:dword_18000F5A0, edx
0x18000145a  jnz     short loc_180001467
0x18000145c  xor     ebx, ebx
0x18000145e  mov     [rsp+108h+var_E8], ebx
0x180001462  jmp     loc_180001614
0x180001467  lea     eax, [rdx-1]
0x18000146a  cmp     eax, 1
0x18000146d  ja      loc_1800014F4
0x180001473  mov     rax, cs:_pRawDllMain
0x18000147a  test    rax, rax
0x18000147d  jz      short loc_1800014B5
0x18000147f  cmp     edx, 1
0x180001482  jnz     short loc_18000148A
0x180001484  mov     cs:dword_18000F5A4, edx
0x18000148a  mov     r8, [rsp+108h+lpvReserved]
0x180001492  call    cs:__guard_dispatch_icall_fptr
0x180001498  mov     ebx, eax
0x18000149a  mov     [rsp+108h+var_E8], eax
0x18000149e  jmp     short loc_1800014B5
0x1800014a0  xor     ebx, ebx
0x1800014a2  mov     [rsp+108h+var_E8], ebx
0x1800014a6  mov     edi, [rsp+108h+arg_8]
0x1800014ad  mov     rsi, [rsp+108h+arg_0]
0x1800014b5  test    ebx, ebx
0x1800014b7  jz      loc_180001614
0x1800014bd  mov     r8, [rsp+108h+lpvReserved]
0x1800014c5  mov     edx, edi
0x1800014c7  mov     rcx, rsi
0x1800014ca  call    _CRT_INIT
0x1800014cf  mov     ebx, eax
0x1800014d1  mov     [rsp+108h+var_E8], eax
0x1800014d5  jmp     short loc_1800014EC
0x1800014d7  xor     ebx, ebx
0x1800014d9  mov     [rsp+108h+var_E8], ebx
0x1800014dd  mov     edi, [rsp+108h+arg_8]
0x1800014e4  mov     rsi, [rsp+108h+arg_0]
0x1800014ec  test    ebx, ebx
0x1800014ee  jz      loc_180001614
0x1800014f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800014fc  mov     edx, edi; fdwReason
0x1800014fe  mov     rcx, rsi; hinstDLL
0x180001501  call    DllMain
0x180001506  mov     ebx, eax
0x180001508  mov     [rsp+108h+var_E8], eax
0x18000150c  jmp     short loc_180001523
0x18000150e  xor     ebx, ebx
0x180001510  mov     [rsp+108h+var_E8], ebx
0x180001514  mov     edi, [rsp+108h+arg_8]
0x18000151b  mov     rsi, [rsp+108h+arg_0]
0x180001523  cmp     edi, 1
0x180001526  jnz     short loc_18000159F
0x180001528  test    ebx, ebx
0x18000152a  jnz     short loc_18000159F
0x18000152c  xor     r8d, r8d; lpvReserved
0x18000152f  xor     edx, edx; fdwReason
0x180001531  mov     rcx, rsi; hinstDLL
0x180001534  call    DllMain
0x180001539  jmp     short loc_18000154E
0x18000153b  mov     edi, [rsp+108h+arg_8]
0x180001542  mov     rsi, [rsp+108h+arg_0]
0x18000154a  mov     ebx, [rsp+108h+var_E8]
0x18000154e  xor     r8d, r8d
0x180001551  xor     edx, edx
0x180001553  mov     rcx, rsi
0x180001556  call    _CRT_INIT
0x18000155b  jmp     short loc_180001570
0x18000155d  mov     edi, [rsp+108h+arg_8]
0x180001564  mov     rsi, [rsp+108h+arg_0]
0x18000156c  mov     ebx, [rsp+108h+var_E8]
0x180001570  mov     rax, cs:_pRawDllMain
0x180001577  test    rax, rax
0x18000157a  jz      short loc_18000159F
0x18000157c  xor     r8d, r8d
0x18000157f  xor     edx, edx
0x180001581  mov     rcx, rsi
0x180001584  call    cs:__guard_dispatch_icall_fptr
0x18000158a  jmp     short loc_18000159F
0x18000158c  mov     edi, [rsp+108h+arg_8]
0x180001593  mov     rsi, [rsp+108h+arg_0]
0x18000159b  mov     ebx, [rsp+108h+var_E8]
0x18000159f  test    edi, edi
0x1800015a1  jz      short loc_1800015A8
0x1800015a3  cmp     edi, 3
0x1800015a6  jnz     short loc_180001614
0x1800015a8  mov     r8, [rsp+108h+lpvReserved]
0x1800015b0  mov     edx, edi
0x1800015b2  mov     rcx, rsi
0x1800015b5  call    _CRT_INIT
0x1800015ba  mov     ebx, eax
0x1800015bc  mov     [rsp+108h+var_E8], eax
0x1800015c0  jmp     short loc_1800015D7
0x1800015c2  xor     ebx, ebx
0x1800015c4  mov     [rsp+108h+var_E8], ebx
0x1800015c8  mov     edi, [rsp+108h+arg_8]
0x1800015cf  mov     rsi, [rsp+108h+arg_0]
0x1800015d7  mov     rax, cs:_pRawDllMain
0x1800015de  test    rax, rax
0x1800015e1  jz      short loc_180001614
0x1800015e3  cmp     cs:dword_18000F5A4, 0
0x1800015ea  jz      short loc_180001614
0x1800015ec  mov     r8, [rsp+108h+lpvReserved]
0x1800015f4  mov     edx, edi
0x1800015f6  mov     rcx, rsi
0x1800015f9  call    cs:__guard_dispatch_icall_fptr
0x1800015ff  mov     ebx, eax
0x180001601  mov     [rsp+108h+var_E8], eax
0x180001605  jmp     short loc_180001614
0x180001607  xor     ebx, ebx
0x180001609  mov     [rsp+108h+var_E8], ebx
0x18000160d  mov     edi, [rsp+108h+arg_8]
0x180001614  cmp     edi, 1
0x180001617  ja      short loc_180001623
0x180001619  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001623  mov     eax, ebx
0x180001625  add     rsp, 0F0h
0x18000162c  pop     rdi
0x18000162d  pop     rsi
0x18000162e  pop     rbx
0x18000162f  retn
0x180008520  push    rbp
0x180008522  sub     rsp, 20h
0x180008526  mov     rbp, rdx
0x180008529  mov     rax, [rcx]
0x18000852c  mov     edx, [rax]
0x18000852e  mov     [rbp+0A8h], rcx
0x180008535  mov     [rbp+28h], edx
0x180008538  mov     eax, [rbp+28h]
0x18000853b  cmp     eax, 0E06D7363h
0x180008540  jnz     short loc_180008556
0x180008542  mov     rdx, [rbp+0A8h]
0x180008549  mov     ecx, [rbp+28h]
0x18000854c  call    _XcptFilter_0
0x180008551  mov     [rbp+30h], eax
0x180008554  jmp     short loc_18000855D
0x180008556  mov     dword ptr [rbp+30h], 0
0x18000855d  mov     eax, [rbp+30h]
0x180008560  add     rsp, 20h
0x180008564  pop     rbp
0x180008565  retn
0x180008567  push    rbp
0x180008569  sub     rsp, 20h
0x18000856d  mov     rbp, rdx
0x180008570  mov     rax, [rcx]
0x180008573  mov     edx, [rax]
0x180008575  mov     [rbp+0B0h], rcx
0x18000857c  mov     [rbp+38h], edx
0x18000857f  mov     eax, [rbp+38h]
0x180008582  cmp     eax, 0E06D7363h
0x180008587  jnz     short loc_18000859D
0x180008589  mov     rdx, [rbp+0B0h]
0x180008590  mov     ecx, [rbp+38h]
0x180008593  call    _XcptFilter_0
0x180008598  mov     [rbp+40h], eax
0x18000859b  jmp     short loc_1800085A4
0x18000859d  mov     dword ptr [rbp+40h], 0
0x1800085a4  mov     eax, [rbp+40h]
0x1800085a7  add     rsp, 20h
0x1800085ab  pop     rbp
0x1800085ac  retn
0x1800085ae  push    rbp
0x1800085b0  sub     rsp, 20h
0x1800085b4  mov     rbp, rdx
0x1800085b7  mov     rax, [rcx]
0x1800085ba  mov     edx, [rax]
0x1800085bc  mov     [rbp+0B8h], rcx
0x1800085c3  mov     [rbp+48h], edx
0x1800085c6  mov     eax, [rbp+48h]
0x1800085c9  cmp     eax, 0E06D7363h
0x1800085ce  jnz     short loc_1800085E4
0x1800085d0  mov     rdx, [rbp+0B8h]
0x1800085d7  mov     ecx, [rbp+48h]
0x1800085da  call    _XcptFilter_0
0x1800085df  mov     [rbp+50h], eax
0x1800085e2  jmp     short loc_1800085EB
0x1800085e4  mov     dword ptr [rbp+50h], 0
0x1800085eb  mov     eax, [rbp+50h]
0x1800085ee  add     rsp, 20h
0x1800085f2  pop     rbp
0x1800085f3  retn
0x1800085f5  push    rbp
0x1800085f7  sub     rsp, 20h
0x1800085fb  mov     rbp, rdx
0x1800085fe  mov     rax, [rcx]
0x180008601  mov     edx, [rax]
0x180008603  mov     [rbp+0C0h], rcx
0x18000860a  mov     [rbp+58h], edx
0x18000860d  mov     eax, [rbp+58h]
0x180008610  cmp     eax, 0E06D7363h
0x180008615  jnz     short loc_18000862B
0x180008617  mov     rdx, [rbp+0C0h]
0x18000861e  mov     ecx, [rbp+58h]
0x180008621  call    _XcptFilter_0
0x180008626  mov     [rbp+60h], eax
0x180008629  jmp     short loc_180008632
0x18000862b  mov     dword ptr [rbp+60h], 0
0x180008632  mov     eax, [rbp+60h]
0x180008635  add     rsp, 20h
0x180008639  pop     rbp
0x18000863a  retn
0x18000863c  push    rbp
0x18000863e  sub     rsp, 20h
0x180008642  mov     rbp, rdx
0x180008645  mov     rax, [rcx]
0x180008648  mov     edx, [rax]
0x18000864a  mov     [rbp+0C8h], rcx
0x180008651  mov     [rbp+68h], edx
0x180008654  mov     eax, [rbp+68h]
0x180008657  cmp     eax, 0E06D7363h
0x18000865c  jnz     short loc_180008672
0x18000865e  mov     rdx, [rbp+0C8h]
0x180008665  mov     ecx, [rbp+68h]
0x180008668  call    _XcptFilter_0
0x18000866d  mov     [rbp+70h], eax
0x180008670  jmp     short loc_180008679
0x180008672  mov     dword ptr [rbp+70h], 0
0x180008679  mov     eax, [rbp+70h]
0x18000867c  add     rsp, 20h
0x180008680  pop     rbp
0x180008681  retn
0x180008683  push    rbp
0x180008685  sub     rsp, 20h
0x180008689  mov     rbp, rdx
0x18000868c  mov     rax, [rcx]
0x18000868f  mov     edx, [rax]
0x180008691  mov     [rbp+0D0h], rcx
0x180008698  mov     [rbp+78h], edx
0x18000869b  mov     eax, [rbp+78h]
0x18000869e  cmp     eax, 0E06D7363h
0x1800086a3  jnz     short loc_1800086BC
0x1800086a5  mov     rdx, [rbp+0D0h]
0x1800086ac  mov     ecx, [rbp+78h]
0x1800086af  call    _XcptFilter_0
0x1800086b4  mov     [rbp+80h], eax
0x1800086ba  jmp     short loc_1800086C6
0x1800086bc  mov     dword ptr [rbp+80h], 0
0x1800086c6  mov     eax, [rbp+80h]
0x1800086cc  add     rsp, 20h
0x1800086d0  pop     rbp
0x1800086d1  retn
0x1800086d3  push    rbp
0x1800086d5  sub     rsp, 20h
0x1800086d9  mov     rbp, rdx
0x1800086dc  mov     rax, [rcx]
0x1800086df  mov     edx, [rax]
0x1800086e1  mov     [rbp+0D8h], rcx
0x1800086e8  mov     [rbp+88h], edx
0x1800086ee  mov     eax, [rbp+88h]
0x1800086f4  cmp     eax, 0E06D7363h
0x1800086f9  jnz     short loc_180008715
0x1800086fb  mov     rdx, [rbp+0D8h]
0x180008702  mov     ecx, [rbp+88h]
0x180008708  call    _XcptFilter_0
0x18000870d  mov     [rbp+90h], eax
0x180008713  jmp     short loc_18000871F
0x180008715  mov     dword ptr [rbp+90h], 0
0x18000871f  mov     eax, [rbp+90h]
0x180008725  add     rsp, 20h
0x180008729  pop     rbp
0x18000872a  retn
0x18000872c  push    rbp
0x18000872e  sub     rsp, 20h
0x180008732  mov     rbp, rdx
0x180008735  mov     rax, [rcx]
0x180008738  mov     edx, [rax]
0x18000873a  mov     [rbp+0E0h], rcx
0x180008741  mov     [rbp+98h], edx
0x180008747  mov     eax, [rbp+98h]
0x18000874d  cmp     eax, 0E06D7363h
0x180008752  jnz     short loc_18000876E
0x180008754  mov     rdx, [rbp+0E0h]
0x18000875b  mov     ecx, [rbp+98h]
0x180008761  call    _XcptFilter_0
0x180008766  mov     [rbp+0A0h], eax
0x18000876c  jmp     short loc_180008778
0x18000876e  mov     dword ptr [rbp+0A0h], 0
0x180008778  mov     eax, [rbp+0A0h]
0x18000877e  add     rsp, 20h
0x180008782  pop     rbp
0x180008783  retn
0x180008785  push    rbp
0x180008787  sub     rsp, 20h
0x18000878b  mov     rbp, rdx
0x18000878e  cmp     dword ptr [rbp+118h], 1
0x180008795  ja      short loc_1800087A1
0x180008797  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
