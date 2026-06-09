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
- `0x1800014e6`
- `0x1800016b8`
- `0x180003520`

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
  if ( (_DWORD)fdwReason || dword_1800080A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800080A4 = 1;
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
            if ( dword_1800080A4 )
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
0x1800012f4  cmp     cs:dword_1800080A0, edx
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
0x180001324  mov     cs:dword_1800080A4, edx
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
0x180001483  cmp     cs:dword_1800080A4, 0
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
0x180003560  push    rbp
0x180003562  sub     rsp, 20h
0x180003566  mov     rbp, rdx
0x180003569  mov     rax, [rcx]
0x18000356c  mov     edx, [rax]
0x18000356e  mov     [rbp+0A8h], rcx
0x180003575  mov     [rbp+28h], edx
0x180003578  mov     eax, [rbp+28h]
0x18000357b  cmp     eax, 0E06D7363h
0x180003580  jnz     short loc_180003596
0x180003582  mov     rdx, [rbp+0A8h]
0x180003589  mov     ecx, [rbp+28h]
0x18000358c  call    _XcptFilter_0
0x180003591  mov     [rbp+30h], eax
0x180003594  jmp     short loc_18000359D
0x180003596  mov     dword ptr [rbp+30h], 0
0x18000359d  mov     eax, [rbp+30h]
0x1800035a0  add     rsp, 20h
0x1800035a4  pop     rbp
0x1800035a5  retn
0x1800035a7  push    rbp
0x1800035a9  sub     rsp, 20h
0x1800035ad  mov     rbp, rdx
0x1800035b0  mov     rax, [rcx]
0x1800035b3  mov     edx, [rax]
0x1800035b5  mov     [rbp+0B0h], rcx
0x1800035bc  mov     [rbp+38h], edx
0x1800035bf  mov     eax, [rbp+38h]
0x1800035c2  cmp     eax, 0E06D7363h
0x1800035c7  jnz     short loc_1800035DD
0x1800035c9  mov     rdx, [rbp+0B0h]
0x1800035d0  mov     ecx, [rbp+38h]
0x1800035d3  call    _XcptFilter_0
0x1800035d8  mov     [rbp+40h], eax
0x1800035db  jmp     short loc_1800035E4
0x1800035dd  mov     dword ptr [rbp+40h], 0
0x1800035e4  mov     eax, [rbp+40h]
0x1800035e7  add     rsp, 20h
0x1800035eb  pop     rbp
0x1800035ec  retn
0x1800035ee  push    rbp
0x1800035f0  sub     rsp, 20h
0x1800035f4  mov     rbp, rdx
0x1800035f7  mov     rax, [rcx]
0x1800035fa  mov     edx, [rax]
0x1800035fc  mov     [rbp+0B8h], rcx
0x180003603  mov     [rbp+48h], edx
0x180003606  mov     eax, [rbp+48h]
0x180003609  cmp     eax, 0E06D7363h
0x18000360e  jnz     short loc_180003624
0x180003610  mov     rdx, [rbp+0B8h]
0x180003617  mov     ecx, [rbp+48h]
0x18000361a  call    _XcptFilter_0
0x18000361f  mov     [rbp+50h], eax
0x180003622  jmp     short loc_18000362B
0x180003624  mov     dword ptr [rbp+50h], 0
0x18000362b  mov     eax, [rbp+50h]
0x18000362e  add     rsp, 20h
0x180003632  pop     rbp
0x180003633  retn
0x180003635  push    rbp
0x180003637  sub     rsp, 20h
0x18000363b  mov     rbp, rdx
0x18000363e  mov     rax, [rcx]
0x180003641  mov     edx, [rax]
0x180003643  mov     [rbp+0C0h], rcx
0x18000364a  mov     [rbp+58h], edx
0x18000364d  mov     eax, [rbp+58h]
0x180003650  cmp     eax, 0E06D7363h
0x180003655  jnz     short loc_18000366B
0x180003657  mov     rdx, [rbp+0C0h]
0x18000365e  mov     ecx, [rbp+58h]
0x180003661  call    _XcptFilter_0
0x180003666  mov     [rbp+60h], eax
0x180003669  jmp     short loc_180003672
0x18000366b  mov     dword ptr [rbp+60h], 0
0x180003672  mov     eax, [rbp+60h]
0x180003675  add     rsp, 20h
0x180003679  pop     rbp
0x18000367a  retn
0x18000367c  push    rbp
0x18000367e  sub     rsp, 20h
0x180003682  mov     rbp, rdx
0x180003685  mov     rax, [rcx]
0x180003688  mov     edx, [rax]
0x18000368a  mov     [rbp+0C8h], rcx
0x180003691  mov     [rbp+68h], edx
0x180003694  mov     eax, [rbp+68h]
0x180003697  cmp     eax, 0E06D7363h
0x18000369c  jnz     short loc_1800036B2
0x18000369e  mov     rdx, [rbp+0C8h]
0x1800036a5  mov     ecx, [rbp+68h]
0x1800036a8  call    _XcptFilter_0
0x1800036ad  mov     [rbp+70h], eax
0x1800036b0  jmp     short loc_1800036B9
0x1800036b2  mov     dword ptr [rbp+70h], 0
0x1800036b9  mov     eax, [rbp+70h]
0x1800036bc  add     rsp, 20h
0x1800036c0  pop     rbp
0x1800036c1  retn
0x1800036c3  push    rbp
0x1800036c5  sub     rsp, 20h
0x1800036c9  mov     rbp, rdx
0x1800036cc  mov     rax, [rcx]
0x1800036cf  mov     edx, [rax]
0x1800036d1  mov     [rbp+0D0h], rcx
0x1800036d8  mov     [rbp+78h], edx
0x1800036db  mov     eax, [rbp+78h]
0x1800036de  cmp     eax, 0E06D7363h
0x1800036e3  jnz     short loc_1800036FC
0x1800036e5  mov     rdx, [rbp+0D0h]
0x1800036ec  mov     ecx, [rbp+78h]
0x1800036ef  call    _XcptFilter_0
0x1800036f4  mov     [rbp+80h], eax
0x1800036fa  jmp     short loc_180003706
0x1800036fc  mov     dword ptr [rbp+80h], 0
0x180003706  mov     eax, [rbp+80h]
0x18000370c  add     rsp, 20h
0x180003710  pop     rbp
0x180003711  retn
0x180003713  push    rbp
0x180003715  sub     rsp, 20h
0x180003719  mov     rbp, rdx
0x18000371c  mov     rax, [rcx]
0x18000371f  mov     edx, [rax]
0x180003721  mov     [rbp+0D8h], rcx
0x180003728  mov     [rbp+88h], edx
0x18000372e  mov     eax, [rbp+88h]
0x180003734  cmp     eax, 0E06D7363h
0x180003739  jnz     short loc_180003755
0x18000373b  mov     rdx, [rbp+0D8h]
0x180003742  mov     ecx, [rbp+88h]
0x180003748  call    _XcptFilter_0
0x18000374d  mov     [rbp+90h], eax
0x180003753  jmp     short loc_18000375F
0x180003755  mov     dword ptr [rbp+90h], 0
0x18000375f  mov     eax, [rbp+90h]
0x180003765  add     rsp, 20h
0x180003769  pop     rbp
0x18000376a  retn
0x18000376c  push    rbp
0x18000376e  sub     rsp, 20h
0x180003772  mov     rbp, rdx
0x180003775  mov     rax, [rcx]
0x180003778  mov     edx, [rax]
0x18000377a  mov     [rbp+0E0h], rcx
0x180003781  mov     [rbp+98h], edx
0x180003787  mov     eax, [rbp+98h]
0x18000378d  cmp     eax, 0E06D7363h
0x180003792  jnz     short loc_1800037AE
0x180003794  mov     rdx, [rbp+0E0h]
0x18000379b  mov     ecx, [rbp+98h]
0x1800037a1  call    _XcptFilter_0
0x1800037a6  mov     [rbp+0A0h], eax
0x1800037ac  jmp     short loc_1800037B8
0x1800037ae  mov     dword ptr [rbp+0A0h], 0
0x1800037b8  mov     eax, [rbp+0A0h]
0x1800037be  add     rsp, 20h
0x1800037c2  pop     rbp
0x1800037c3  retn
0x1800037c5  push    rbp
0x1800037c7  sub     rsp, 20h
0x1800037cb  mov     rbp, rdx
0x1800037ce  cmp     dword ptr [rbp+118h], 1
0x1800037d5  ja      short loc_1800037E1
0x1800037d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
