# __DllMainCRTStartup

- ea: `0x1800012d4`
- end: `0x1800014e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001290`

## callees

- `0x180001060`
- `0x1800012d4`
- `0x1800014f2`
- `0x180001b60`
- `0x180002190`

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
  if ( (_DWORD)fdwReason || dword_1800050A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800050A4 = 1;
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
            if ( dword_1800050A4 )
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
0x1800012d4  mov     [rsp+lpvReserved], r8
0x1800012d9  mov     [rsp+arg_8], edx
0x1800012dd  mov     [rsp+arg_0], rcx
0x1800012e2  push    rbx
0x1800012e3  push    rsi
0x1800012e4  push    rdi
0x1800012e5  sub     rsp, 0F0h
0x1800012ec  mov     edi, edx
0x1800012ee  mov     rsi, rcx
0x1800012f1  mov     ebx, 1
0x1800012f6  cmp     edx, ebx
0x1800012f8  ja      short loc_180001300
0x1800012fa  mov     cs:__native_dllmain_reason, edx
0x180001300  test    edx, edx
0x180001302  jnz     short loc_180001317
0x180001304  cmp     cs:dword_1800050A0, edx
0x18000130a  jnz     short loc_180001317
0x18000130c  xor     ebx, ebx
0x18000130e  mov     [rsp+108h+var_E8], ebx
0x180001312  jmp     loc_1800014C4
0x180001317  lea     eax, [rdx-1]
0x18000131a  cmp     eax, 1
0x18000131d  ja      loc_1800013A4
0x180001323  mov     rax, cs:_pRawDllMain
0x18000132a  test    rax, rax
0x18000132d  jz      short loc_180001365
0x18000132f  cmp     edx, 1
0x180001332  jnz     short loc_18000133A
0x180001334  mov     cs:dword_1800050A4, edx
0x18000133a  mov     r8, [rsp+108h+lpvReserved]
0x180001342  call    cs:__guard_dispatch_icall_fptr
0x180001348  mov     ebx, eax
0x18000134a  mov     [rsp+108h+var_E8], eax
0x18000134e  jmp     short loc_180001365
0x180001350  xor     ebx, ebx
0x180001352  mov     [rsp+108h+var_E8], ebx
0x180001356  mov     edi, [rsp+108h+arg_8]
0x18000135d  mov     rsi, [rsp+108h+arg_0]
0x180001365  test    ebx, ebx
0x180001367  jz      loc_1800014C4
0x18000136d  mov     r8, [rsp+108h+lpvReserved]
0x180001375  mov     edx, edi
0x180001377  mov     rcx, rsi
0x18000137a  call    _CRT_INIT
0x18000137f  mov     ebx, eax
0x180001381  mov     [rsp+108h+var_E8], eax
0x180001385  jmp     short loc_18000139C
0x180001387  xor     ebx, ebx
0x180001389  mov     [rsp+108h+var_E8], ebx
0x18000138d  mov     edi, [rsp+108h+arg_8]
0x180001394  mov     rsi, [rsp+108h+arg_0]
0x18000139c  test    ebx, ebx
0x18000139e  jz      loc_1800014C4
0x1800013a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ac  mov     edx, edi; fdwReason
0x1800013ae  mov     rcx, rsi; hinstDLL
0x1800013b1  call    DllMain
0x1800013b6  mov     ebx, eax
0x1800013b8  mov     [rsp+108h+var_E8], eax
0x1800013bc  jmp     short loc_1800013D3
0x1800013be  xor     ebx, ebx
0x1800013c0  mov     [rsp+108h+var_E8], ebx
0x1800013c4  mov     edi, [rsp+108h+arg_8]
0x1800013cb  mov     rsi, [rsp+108h+arg_0]
0x1800013d3  cmp     edi, 1
0x1800013d6  jnz     short loc_18000144F
0x1800013d8  test    ebx, ebx
0x1800013da  jnz     short loc_18000144F
0x1800013dc  xor     r8d, r8d; lpvReserved
0x1800013df  xor     edx, edx; fdwReason
0x1800013e1  mov     rcx, rsi; hinstDLL
0x1800013e4  call    DllMain
0x1800013e9  jmp     short loc_1800013FE
0x1800013eb  mov     edi, [rsp+108h+arg_8]
0x1800013f2  mov     rsi, [rsp+108h+arg_0]
0x1800013fa  mov     ebx, [rsp+108h+var_E8]
0x1800013fe  xor     r8d, r8d
0x180001401  xor     edx, edx
0x180001403  mov     rcx, rsi
0x180001406  call    _CRT_INIT
0x18000140b  jmp     short loc_180001420
0x18000140d  mov     edi, [rsp+108h+arg_8]
0x180001414  mov     rsi, [rsp+108h+arg_0]
0x18000141c  mov     ebx, [rsp+108h+var_E8]
0x180001420  mov     rax, cs:_pRawDllMain
0x180001427  test    rax, rax
0x18000142a  jz      short loc_18000144F
0x18000142c  xor     r8d, r8d
0x18000142f  xor     edx, edx
0x180001431  mov     rcx, rsi
0x180001434  call    cs:__guard_dispatch_icall_fptr
0x18000143a  jmp     short loc_18000144F
0x18000143c  mov     edi, [rsp+108h+arg_8]
0x180001443  mov     rsi, [rsp+108h+arg_0]
0x18000144b  mov     ebx, [rsp+108h+var_E8]
0x18000144f  test    edi, edi
0x180001451  jz      short loc_180001458
0x180001453  cmp     edi, 3
0x180001456  jnz     short loc_1800014C4
0x180001458  mov     r8, [rsp+108h+lpvReserved]
0x180001460  mov     edx, edi
0x180001462  mov     rcx, rsi
0x180001465  call    _CRT_INIT
0x18000146a  mov     ebx, eax
0x18000146c  mov     [rsp+108h+var_E8], eax
0x180001470  jmp     short loc_180001487
0x180001472  xor     ebx, ebx
0x180001474  mov     [rsp+108h+var_E8], ebx
0x180001478  mov     edi, [rsp+108h+arg_8]
0x18000147f  mov     rsi, [rsp+108h+arg_0]
0x180001487  mov     rax, cs:_pRawDllMain
0x18000148e  test    rax, rax
0x180001491  jz      short loc_1800014C4
0x180001493  cmp     cs:dword_1800050A4, 0
0x18000149a  jz      short loc_1800014C4
0x18000149c  mov     r8, [rsp+108h+lpvReserved]
0x1800014a4  mov     edx, edi
0x1800014a6  mov     rcx, rsi
0x1800014a9  call    cs:__guard_dispatch_icall_fptr
0x1800014af  mov     ebx, eax
0x1800014b1  mov     [rsp+108h+var_E8], eax
0x1800014b5  jmp     short loc_1800014C4
0x1800014b7  xor     ebx, ebx
0x1800014b9  mov     [rsp+108h+var_E8], ebx
0x1800014bd  mov     edi, [rsp+108h+arg_8]
0x1800014c4  cmp     edi, 1
0x1800014c7  ja      short loc_1800014D3
0x1800014c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014d3  mov     eax, ebx
0x1800014d5  add     rsp, 0F0h
0x1800014dc  pop     rdi
0x1800014dd  pop     rsi
0x1800014de  pop     rbx
0x1800014df  retn
0x180002200  push    rbp
0x180002202  sub     rsp, 20h
0x180002206  mov     rbp, rdx
0x180002209  mov     rax, [rcx]
0x18000220c  mov     edx, [rax]
0x18000220e  mov     [rbp+0A8h], rcx
0x180002215  mov     [rbp+28h], edx
0x180002218  mov     eax, [rbp+28h]
0x18000221b  cmp     eax, 0E06D7363h
0x180002220  jnz     short loc_180002236
0x180002222  mov     rdx, [rbp+0A8h]
0x180002229  mov     ecx, [rbp+28h]
0x18000222c  call    _XcptFilter_0
0x180002231  mov     [rbp+30h], eax
0x180002234  jmp     short loc_18000223D
0x180002236  mov     dword ptr [rbp+30h], 0
0x18000223d  mov     eax, [rbp+30h]
0x180002240  add     rsp, 20h
0x180002244  pop     rbp
0x180002245  retn
0x180002247  push    rbp
0x180002249  sub     rsp, 20h
0x18000224d  mov     rbp, rdx
0x180002250  mov     rax, [rcx]
0x180002253  mov     edx, [rax]
0x180002255  mov     [rbp+0B0h], rcx
0x18000225c  mov     [rbp+38h], edx
0x18000225f  mov     eax, [rbp+38h]
0x180002262  cmp     eax, 0E06D7363h
0x180002267  jnz     short loc_18000227D
0x180002269  mov     rdx, [rbp+0B0h]
0x180002270  mov     ecx, [rbp+38h]
0x180002273  call    _XcptFilter_0
0x180002278  mov     [rbp+40h], eax
0x18000227b  jmp     short loc_180002284
0x18000227d  mov     dword ptr [rbp+40h], 0
0x180002284  mov     eax, [rbp+40h]
0x180002287  add     rsp, 20h
0x18000228b  pop     rbp
0x18000228c  retn
0x18000228e  push    rbp
0x180002290  sub     rsp, 20h
0x180002294  mov     rbp, rdx
0x180002297  mov     rax, [rcx]
0x18000229a  mov     edx, [rax]
0x18000229c  mov     [rbp+0B8h], rcx
0x1800022a3  mov     [rbp+48h], edx
0x1800022a6  mov     eax, [rbp+48h]
0x1800022a9  cmp     eax, 0E06D7363h
0x1800022ae  jnz     short loc_1800022C4
0x1800022b0  mov     rdx, [rbp+0B8h]
0x1800022b7  mov     ecx, [rbp+48h]
0x1800022ba  call    _XcptFilter_0
0x1800022bf  mov     [rbp+50h], eax
0x1800022c2  jmp     short loc_1800022CB
0x1800022c4  mov     dword ptr [rbp+50h], 0
0x1800022cb  mov     eax, [rbp+50h]
0x1800022ce  add     rsp, 20h
0x1800022d2  pop     rbp
0x1800022d3  retn
0x1800022d5  push    rbp
0x1800022d7  sub     rsp, 20h
0x1800022db  mov     rbp, rdx
0x1800022de  mov     rax, [rcx]
0x1800022e1  mov     edx, [rax]
0x1800022e3  mov     [rbp+0C0h], rcx
0x1800022ea  mov     [rbp+58h], edx
0x1800022ed  mov     eax, [rbp+58h]
0x1800022f0  cmp     eax, 0E06D7363h
0x1800022f5  jnz     short loc_18000230B
0x1800022f7  mov     rdx, [rbp+0C0h]
0x1800022fe  mov     ecx, [rbp+58h]
0x180002301  call    _XcptFilter_0
0x180002306  mov     [rbp+60h], eax
0x180002309  jmp     short loc_180002312
0x18000230b  mov     dword ptr [rbp+60h], 0
0x180002312  mov     eax, [rbp+60h]
0x180002315  add     rsp, 20h
0x180002319  pop     rbp
0x18000231a  retn
0x18000231c  push    rbp
0x18000231e  sub     rsp, 20h
0x180002322  mov     rbp, rdx
0x180002325  mov     rax, [rcx]
0x180002328  mov     edx, [rax]
0x18000232a  mov     [rbp+0C8h], rcx
0x180002331  mov     [rbp+68h], edx
0x180002334  mov     eax, [rbp+68h]
0x180002337  cmp     eax, 0E06D7363h
0x18000233c  jnz     short loc_180002352
0x18000233e  mov     rdx, [rbp+0C8h]
0x180002345  mov     ecx, [rbp+68h]
0x180002348  call    _XcptFilter_0
0x18000234d  mov     [rbp+70h], eax
0x180002350  jmp     short loc_180002359
0x180002352  mov     dword ptr [rbp+70h], 0
0x180002359  mov     eax, [rbp+70h]
0x18000235c  add     rsp, 20h
0x180002360  pop     rbp
0x180002361  retn
0x180002363  push    rbp
0x180002365  sub     rsp, 20h
0x180002369  mov     rbp, rdx
0x18000236c  mov     rax, [rcx]
0x18000236f  mov     edx, [rax]
0x180002371  mov     [rbp+0D0h], rcx
0x180002378  mov     [rbp+78h], edx
0x18000237b  mov     eax, [rbp+78h]
0x18000237e  cmp     eax, 0E06D7363h
0x180002383  jnz     short loc_18000239C
0x180002385  mov     rdx, [rbp+0D0h]
0x18000238c  mov     ecx, [rbp+78h]
0x18000238f  call    _XcptFilter_0
0x180002394  mov     [rbp+80h], eax
0x18000239a  jmp     short loc_1800023A6
0x18000239c  mov     dword ptr [rbp+80h], 0
0x1800023a6  mov     eax, [rbp+80h]
0x1800023ac  add     rsp, 20h
0x1800023b0  pop     rbp
0x1800023b1  retn
0x1800023b3  push    rbp
0x1800023b5  sub     rsp, 20h
0x1800023b9  mov     rbp, rdx
0x1800023bc  mov     rax, [rcx]
0x1800023bf  mov     edx, [rax]
0x1800023c1  mov     [rbp+0D8h], rcx
0x1800023c8  mov     [rbp+88h], edx
0x1800023ce  mov     eax, [rbp+88h]
0x1800023d4  cmp     eax, 0E06D7363h
0x1800023d9  jnz     short loc_1800023F5
0x1800023db  mov     rdx, [rbp+0D8h]
0x1800023e2  mov     ecx, [rbp+88h]
0x1800023e8  call    _XcptFilter_0
0x1800023ed  mov     [rbp+90h], eax
0x1800023f3  jmp     short loc_1800023FF
0x1800023f5  mov     dword ptr [rbp+90h], 0
0x1800023ff  mov     eax, [rbp+90h]
0x180002405  add     rsp, 20h
0x180002409  pop     rbp
0x18000240a  retn
0x18000240c  push    rbp
0x18000240e  sub     rsp, 20h
0x180002412  mov     rbp, rdx
0x180002415  mov     rax, [rcx]
0x180002418  mov     edx, [rax]
0x18000241a  mov     [rbp+0E0h], rcx
0x180002421  mov     [rbp+98h], edx
0x180002427  mov     eax, [rbp+98h]
0x18000242d  cmp     eax, 0E06D7363h
0x180002432  jnz     short loc_18000244E
0x180002434  mov     rdx, [rbp+0E0h]
0x18000243b  mov     ecx, [rbp+98h]
0x180002441  call    _XcptFilter_0
0x180002446  mov     [rbp+0A0h], eax
0x18000244c  jmp     short loc_180002458
0x18000244e  mov     dword ptr [rbp+0A0h], 0
0x180002458  mov     eax, [rbp+0A0h]
0x18000245e  add     rsp, 20h
0x180002462  pop     rbp
0x180002463  retn
0x180002465  push    rbp
0x180002467  sub     rsp, 20h
0x18000246b  mov     rbp, rdx
0x18000246e  cmp     dword ptr [rbp+118h], 1
0x180002475  ja      short loc_180002481
0x180002477  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
