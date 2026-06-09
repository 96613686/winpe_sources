# __DllMainCRTStartup

- ea: `0x1800014a4`
- end: `0x1800016b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001460`

## callees

- `0x180001230`
- `0x1800014a4`
- `0x18000178c`
- `0x18000214c`
- `0x1800096f0`

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
  if ( (_DWORD)fdwReason || dword_18000F240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F244 = 1;
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
            if ( dword_18000F244 )
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
0x1800014a4  mov     [rsp+lpvReserved], r8
0x1800014a9  mov     [rsp+arg_8], edx
0x1800014ad  mov     [rsp+arg_0], rcx
0x1800014b2  push    rbx
0x1800014b3  push    rsi
0x1800014b4  push    rdi
0x1800014b5  sub     rsp, 0F0h
0x1800014bc  mov     edi, edx
0x1800014be  mov     rsi, rcx
0x1800014c1  mov     ebx, 1
0x1800014c6  cmp     edx, ebx
0x1800014c8  ja      short loc_1800014D0
0x1800014ca  mov     cs:__native_dllmain_reason, edx
0x1800014d0  test    edx, edx
0x1800014d2  jnz     short loc_1800014E7
0x1800014d4  cmp     cs:dword_18000F240, edx
0x1800014da  jnz     short loc_1800014E7
0x1800014dc  xor     ebx, ebx
0x1800014de  mov     [rsp+108h+var_E8], ebx
0x1800014e2  jmp     loc_180001694
0x1800014e7  lea     eax, [rdx-1]
0x1800014ea  cmp     eax, 1
0x1800014ed  ja      loc_180001574
0x1800014f3  mov     rax, cs:_pRawDllMain
0x1800014fa  test    rax, rax
0x1800014fd  jz      short loc_180001535
0x1800014ff  cmp     edx, 1
0x180001502  jnz     short loc_18000150A
0x180001504  mov     cs:dword_18000F244, edx
0x18000150a  mov     r8, [rsp+108h+lpvReserved]
0x180001512  call    cs:__guard_dispatch_icall_fptr
0x180001518  mov     ebx, eax
0x18000151a  mov     [rsp+108h+var_E8], eax
0x18000151e  jmp     short loc_180001535
0x180001520  xor     ebx, ebx
0x180001522  mov     [rsp+108h+var_E8], ebx
0x180001526  mov     edi, [rsp+108h+arg_8]
0x18000152d  mov     rsi, [rsp+108h+arg_0]
0x180001535  test    ebx, ebx
0x180001537  jz      loc_180001694
0x18000153d  mov     r8, [rsp+108h+lpvReserved]
0x180001545  mov     edx, edi
0x180001547  mov     rcx, rsi
0x18000154a  call    _CRT_INIT
0x18000154f  mov     ebx, eax
0x180001551  mov     [rsp+108h+var_E8], eax
0x180001555  jmp     short loc_18000156C
0x180001557  xor     ebx, ebx
0x180001559  mov     [rsp+108h+var_E8], ebx
0x18000155d  mov     edi, [rsp+108h+arg_8]
0x180001564  mov     rsi, [rsp+108h+arg_0]
0x18000156c  test    ebx, ebx
0x18000156e  jz      loc_180001694
0x180001574  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000157c  mov     edx, edi; fdwReason
0x18000157e  mov     rcx, rsi; hinstDLL
0x180001581  call    DllMain
0x180001586  mov     ebx, eax
0x180001588  mov     [rsp+108h+var_E8], eax
0x18000158c  jmp     short loc_1800015A3
0x18000158e  xor     ebx, ebx
0x180001590  mov     [rsp+108h+var_E8], ebx
0x180001594  mov     edi, [rsp+108h+arg_8]
0x18000159b  mov     rsi, [rsp+108h+arg_0]
0x1800015a3  cmp     edi, 1
0x1800015a6  jnz     short loc_18000161F
0x1800015a8  test    ebx, ebx
0x1800015aa  jnz     short loc_18000161F
0x1800015ac  xor     r8d, r8d; lpvReserved
0x1800015af  xor     edx, edx; fdwReason
0x1800015b1  mov     rcx, rsi; hinstDLL
0x1800015b4  call    DllMain
0x1800015b9  jmp     short loc_1800015CE
0x1800015bb  mov     edi, [rsp+108h+arg_8]
0x1800015c2  mov     rsi, [rsp+108h+arg_0]
0x1800015ca  mov     ebx, [rsp+108h+var_E8]
0x1800015ce  xor     r8d, r8d
0x1800015d1  xor     edx, edx
0x1800015d3  mov     rcx, rsi
0x1800015d6  call    _CRT_INIT
0x1800015db  jmp     short loc_1800015F0
0x1800015dd  mov     edi, [rsp+108h+arg_8]
0x1800015e4  mov     rsi, [rsp+108h+arg_0]
0x1800015ec  mov     ebx, [rsp+108h+var_E8]
0x1800015f0  mov     rax, cs:_pRawDllMain
0x1800015f7  test    rax, rax
0x1800015fa  jz      short loc_18000161F
0x1800015fc  xor     r8d, r8d
0x1800015ff  xor     edx, edx
0x180001601  mov     rcx, rsi
0x180001604  call    cs:__guard_dispatch_icall_fptr
0x18000160a  jmp     short loc_18000161F
0x18000160c  mov     edi, [rsp+108h+arg_8]
0x180001613  mov     rsi, [rsp+108h+arg_0]
0x18000161b  mov     ebx, [rsp+108h+var_E8]
0x18000161f  test    edi, edi
0x180001621  jz      short loc_180001628
0x180001623  cmp     edi, 3
0x180001626  jnz     short loc_180001694
0x180001628  mov     r8, [rsp+108h+lpvReserved]
0x180001630  mov     edx, edi
0x180001632  mov     rcx, rsi
0x180001635  call    _CRT_INIT
0x18000163a  mov     ebx, eax
0x18000163c  mov     [rsp+108h+var_E8], eax
0x180001640  jmp     short loc_180001657
0x180001642  xor     ebx, ebx
0x180001644  mov     [rsp+108h+var_E8], ebx
0x180001648  mov     edi, [rsp+108h+arg_8]
0x18000164f  mov     rsi, [rsp+108h+arg_0]
0x180001657  mov     rax, cs:_pRawDllMain
0x18000165e  test    rax, rax
0x180001661  jz      short loc_180001694
0x180001663  cmp     cs:dword_18000F244, 0
0x18000166a  jz      short loc_180001694
0x18000166c  mov     r8, [rsp+108h+lpvReserved]
0x180001674  mov     edx, edi
0x180001676  mov     rcx, rsi
0x180001679  call    cs:__guard_dispatch_icall_fptr
0x18000167f  mov     ebx, eax
0x180001681  mov     [rsp+108h+var_E8], eax
0x180001685  jmp     short loc_180001694
0x180001687  xor     ebx, ebx
0x180001689  mov     [rsp+108h+var_E8], ebx
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  cmp     edi, 1
0x180001697  ja      short loc_1800016A3
0x180001699  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016a3  mov     eax, ebx
0x1800016a5  add     rsp, 0F0h
0x1800016ac  pop     rdi
0x1800016ad  pop     rsi
0x1800016ae  pop     rbx
0x1800016af  retn
0x1800097c0  push    rbp
0x1800097c2  sub     rsp, 20h
0x1800097c6  mov     rbp, rdx
0x1800097c9  mov     rax, [rcx]
0x1800097cc  mov     edx, [rax]
0x1800097ce  mov     [rbp+0A8h], rcx
0x1800097d5  mov     [rbp+28h], edx
0x1800097d8  mov     eax, [rbp+28h]
0x1800097db  cmp     eax, 0E06D7363h
0x1800097e0  jnz     short loc_1800097F6
0x1800097e2  mov     rdx, [rbp+0A8h]
0x1800097e9  mov     ecx, [rbp+28h]
0x1800097ec  call    _XcptFilter_0
0x1800097f1  mov     [rbp+30h], eax
0x1800097f4  jmp     short loc_1800097FD
0x1800097f6  mov     dword ptr [rbp+30h], 0
0x1800097fd  mov     eax, [rbp+30h]
0x180009800  add     rsp, 20h
0x180009804  pop     rbp
0x180009805  retn
0x180009807  push    rbp
0x180009809  sub     rsp, 20h
0x18000980d  mov     rbp, rdx
0x180009810  mov     rax, [rcx]
0x180009813  mov     edx, [rax]
0x180009815  mov     [rbp+0B0h], rcx
0x18000981c  mov     [rbp+38h], edx
0x18000981f  mov     eax, [rbp+38h]
0x180009822  cmp     eax, 0E06D7363h
0x180009827  jnz     short loc_18000983D
0x180009829  mov     rdx, [rbp+0B0h]
0x180009830  mov     ecx, [rbp+38h]
0x180009833  call    _XcptFilter_0
0x180009838  mov     [rbp+40h], eax
0x18000983b  jmp     short loc_180009844
0x18000983d  mov     dword ptr [rbp+40h], 0
0x180009844  mov     eax, [rbp+40h]
0x180009847  add     rsp, 20h
0x18000984b  pop     rbp
0x18000984c  retn
0x18000984e  push    rbp
0x180009850  sub     rsp, 20h
0x180009854  mov     rbp, rdx
0x180009857  mov     rax, [rcx]
0x18000985a  mov     edx, [rax]
0x18000985c  mov     [rbp+0B8h], rcx
0x180009863  mov     [rbp+48h], edx
0x180009866  mov     eax, [rbp+48h]
0x180009869  cmp     eax, 0E06D7363h
0x18000986e  jnz     short loc_180009884
0x180009870  mov     rdx, [rbp+0B8h]
0x180009877  mov     ecx, [rbp+48h]
0x18000987a  call    _XcptFilter_0
0x18000987f  mov     [rbp+50h], eax
0x180009882  jmp     short loc_18000988B
0x180009884  mov     dword ptr [rbp+50h], 0
0x18000988b  mov     eax, [rbp+50h]
0x18000988e  add     rsp, 20h
0x180009892  pop     rbp
0x180009893  retn
0x180009895  push    rbp
0x180009897  sub     rsp, 20h
0x18000989b  mov     rbp, rdx
0x18000989e  mov     rax, [rcx]
0x1800098a1  mov     edx, [rax]
0x1800098a3  mov     [rbp+0C0h], rcx
0x1800098aa  mov     [rbp+58h], edx
0x1800098ad  mov     eax, [rbp+58h]
0x1800098b0  cmp     eax, 0E06D7363h
0x1800098b5  jnz     short loc_1800098CB
0x1800098b7  mov     rdx, [rbp+0C0h]
0x1800098be  mov     ecx, [rbp+58h]
0x1800098c1  call    _XcptFilter_0
0x1800098c6  mov     [rbp+60h], eax
0x1800098c9  jmp     short loc_1800098D2
0x1800098cb  mov     dword ptr [rbp+60h], 0
0x1800098d2  mov     eax, [rbp+60h]
0x1800098d5  add     rsp, 20h
0x1800098d9  pop     rbp
0x1800098da  retn
0x1800098dc  push    rbp
0x1800098de  sub     rsp, 20h
0x1800098e2  mov     rbp, rdx
0x1800098e5  mov     rax, [rcx]
0x1800098e8  mov     edx, [rax]
0x1800098ea  mov     [rbp+0C8h], rcx
0x1800098f1  mov     [rbp+68h], edx
0x1800098f4  mov     eax, [rbp+68h]
0x1800098f7  cmp     eax, 0E06D7363h
0x1800098fc  jnz     short loc_180009912
0x1800098fe  mov     rdx, [rbp+0C8h]
0x180009905  mov     ecx, [rbp+68h]
0x180009908  call    _XcptFilter_0
0x18000990d  mov     [rbp+70h], eax
0x180009910  jmp     short loc_180009919
0x180009912  mov     dword ptr [rbp+70h], 0
0x180009919  mov     eax, [rbp+70h]
0x18000991c  add     rsp, 20h
0x180009920  pop     rbp
0x180009921  retn
0x180009923  push    rbp
0x180009925  sub     rsp, 20h
0x180009929  mov     rbp, rdx
0x18000992c  mov     rax, [rcx]
0x18000992f  mov     edx, [rax]
0x180009931  mov     [rbp+0D0h], rcx
0x180009938  mov     [rbp+78h], edx
0x18000993b  mov     eax, [rbp+78h]
0x18000993e  cmp     eax, 0E06D7363h
0x180009943  jnz     short loc_18000995C
0x180009945  mov     rdx, [rbp+0D0h]
0x18000994c  mov     ecx, [rbp+78h]
0x18000994f  call    _XcptFilter_0
0x180009954  mov     [rbp+80h], eax
0x18000995a  jmp     short loc_180009966
0x18000995c  mov     dword ptr [rbp+80h], 0
0x180009966  mov     eax, [rbp+80h]
0x18000996c  add     rsp, 20h
0x180009970  pop     rbp
0x180009971  retn
0x180009973  push    rbp
0x180009975  sub     rsp, 20h
0x180009979  mov     rbp, rdx
0x18000997c  mov     rax, [rcx]
0x18000997f  mov     edx, [rax]
0x180009981  mov     [rbp+0D8h], rcx
0x180009988  mov     [rbp+88h], edx
0x18000998e  mov     eax, [rbp+88h]
0x180009994  cmp     eax, 0E06D7363h
0x180009999  jnz     short loc_1800099B5
0x18000999b  mov     rdx, [rbp+0D8h]
0x1800099a2  mov     ecx, [rbp+88h]
0x1800099a8  call    _XcptFilter_0
0x1800099ad  mov     [rbp+90h], eax
0x1800099b3  jmp     short loc_1800099BF
0x1800099b5  mov     dword ptr [rbp+90h], 0
0x1800099bf  mov     eax, [rbp+90h]
0x1800099c5  add     rsp, 20h
0x1800099c9  pop     rbp
0x1800099ca  retn
0x1800099cc  push    rbp
0x1800099ce  sub     rsp, 20h
0x1800099d2  mov     rbp, rdx
0x1800099d5  mov     rax, [rcx]
0x1800099d8  mov     edx, [rax]
0x1800099da  mov     [rbp+0E0h], rcx
0x1800099e1  mov     [rbp+98h], edx
0x1800099e7  mov     eax, [rbp+98h]
0x1800099ed  cmp     eax, 0E06D7363h
0x1800099f2  jnz     short loc_180009A0E
0x1800099f4  mov     rdx, [rbp+0E0h]
0x1800099fb  mov     ecx, [rbp+98h]
0x180009a01  call    _XcptFilter_0
0x180009a06  mov     [rbp+0A0h], eax
0x180009a0c  jmp     short loc_180009A18
0x180009a0e  mov     dword ptr [rbp+0A0h], 0
0x180009a18  mov     eax, [rbp+0A0h]
0x180009a1e  add     rsp, 20h
0x180009a22  pop     rbp
0x180009a23  retn
0x180009a25  push    rbp
0x180009a27  sub     rsp, 20h
0x180009a2b  mov     rbp, rdx
0x180009a2e  cmp     dword ptr [rbp+118h], 1
0x180009a35  ja      short loc_180009A41
0x180009a37  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
