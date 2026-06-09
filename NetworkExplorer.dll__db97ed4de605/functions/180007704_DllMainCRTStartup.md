# __DllMainCRTStartup

- ea: `0x180007704`
- end: `0x180007910`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800076c0`

## callees

- `0x180006d70`
- `0x180007490`
- `0x180007704`
- `0x180007cbc`
- `0x18000f110`

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
  if ( (_DWORD)fdwReason || dword_1800182C8 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800182CC = 1;
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
            if ( dword_1800182CC )
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
0x180007704  mov     [rsp+lpvReserved], r8
0x180007709  mov     [rsp+arg_8], edx
0x18000770d  mov     [rsp+arg_0], rcx
0x180007712  push    rbx
0x180007713  push    rsi
0x180007714  push    rdi
0x180007715  sub     rsp, 0F0h
0x18000771c  mov     edi, edx
0x18000771e  mov     rsi, rcx
0x180007721  mov     ebx, 1
0x180007726  cmp     edx, ebx
0x180007728  ja      short loc_180007730
0x18000772a  mov     cs:__native_dllmain_reason, edx
0x180007730  test    edx, edx
0x180007732  jnz     short loc_180007747
0x180007734  cmp     cs:dword_1800182C8, edx
0x18000773a  jnz     short loc_180007747
0x18000773c  xor     ebx, ebx
0x18000773e  mov     [rsp+108h+var_E8], ebx
0x180007742  jmp     loc_1800078F4
0x180007747  lea     eax, [rdx-1]
0x18000774a  cmp     eax, 1
0x18000774d  ja      loc_1800077D4
0x180007753  mov     rax, cs:_pRawDllMain
0x18000775a  test    rax, rax
0x18000775d  jz      short loc_180007795
0x18000775f  cmp     edx, 1
0x180007762  jnz     short loc_18000776A
0x180007764  mov     cs:dword_1800182CC, edx
0x18000776a  mov     r8, [rsp+108h+lpvReserved]
0x180007772  call    cs:__guard_dispatch_icall_fptr
0x180007778  mov     ebx, eax
0x18000777a  mov     [rsp+108h+var_E8], eax
0x18000777e  jmp     short loc_180007795
0x180007780  xor     ebx, ebx
0x180007782  mov     [rsp+108h+var_E8], ebx
0x180007786  mov     edi, [rsp+108h+arg_8]
0x18000778d  mov     rsi, [rsp+108h+arg_0]
0x180007795  test    ebx, ebx
0x180007797  jz      loc_1800078F4
0x18000779d  mov     r8, [rsp+108h+lpvReserved]
0x1800077a5  mov     edx, edi
0x1800077a7  mov     rcx, rsi
0x1800077aa  call    _CRT_INIT
0x1800077af  mov     ebx, eax
0x1800077b1  mov     [rsp+108h+var_E8], eax
0x1800077b5  jmp     short loc_1800077CC
0x1800077b7  xor     ebx, ebx
0x1800077b9  mov     [rsp+108h+var_E8], ebx
0x1800077bd  mov     edi, [rsp+108h+arg_8]
0x1800077c4  mov     rsi, [rsp+108h+arg_0]
0x1800077cc  test    ebx, ebx
0x1800077ce  jz      loc_1800078F4
0x1800077d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800077dc  mov     edx, edi; fdwReason
0x1800077de  mov     rcx, rsi; hinstDLL
0x1800077e1  call    DllMain
0x1800077e6  mov     ebx, eax
0x1800077e8  mov     [rsp+108h+var_E8], eax
0x1800077ec  jmp     short loc_180007803
0x1800077ee  xor     ebx, ebx
0x1800077f0  mov     [rsp+108h+var_E8], ebx
0x1800077f4  mov     edi, [rsp+108h+arg_8]
0x1800077fb  mov     rsi, [rsp+108h+arg_0]
0x180007803  cmp     edi, 1
0x180007806  jnz     short loc_18000787F
0x180007808  test    ebx, ebx
0x18000780a  jnz     short loc_18000787F
0x18000780c  xor     r8d, r8d; lpvReserved
0x18000780f  xor     edx, edx; fdwReason
0x180007811  mov     rcx, rsi; hinstDLL
0x180007814  call    DllMain
0x180007819  jmp     short loc_18000782E
0x18000781b  mov     edi, [rsp+108h+arg_8]
0x180007822  mov     rsi, [rsp+108h+arg_0]
0x18000782a  mov     ebx, [rsp+108h+var_E8]
0x18000782e  xor     r8d, r8d
0x180007831  xor     edx, edx
0x180007833  mov     rcx, rsi
0x180007836  call    _CRT_INIT
0x18000783b  jmp     short loc_180007850
0x18000783d  mov     edi, [rsp+108h+arg_8]
0x180007844  mov     rsi, [rsp+108h+arg_0]
0x18000784c  mov     ebx, [rsp+108h+var_E8]
0x180007850  mov     rax, cs:_pRawDllMain
0x180007857  test    rax, rax
0x18000785a  jz      short loc_18000787F
0x18000785c  xor     r8d, r8d
0x18000785f  xor     edx, edx
0x180007861  mov     rcx, rsi
0x180007864  call    cs:__guard_dispatch_icall_fptr
0x18000786a  jmp     short loc_18000787F
0x18000786c  mov     edi, [rsp+108h+arg_8]
0x180007873  mov     rsi, [rsp+108h+arg_0]
0x18000787b  mov     ebx, [rsp+108h+var_E8]
0x18000787f  test    edi, edi
0x180007881  jz      short loc_180007888
0x180007883  cmp     edi, 3
0x180007886  jnz     short loc_1800078F4
0x180007888  mov     r8, [rsp+108h+lpvReserved]
0x180007890  mov     edx, edi
0x180007892  mov     rcx, rsi
0x180007895  call    _CRT_INIT
0x18000789a  mov     ebx, eax
0x18000789c  mov     [rsp+108h+var_E8], eax
0x1800078a0  jmp     short loc_1800078B7
0x1800078a2  xor     ebx, ebx
0x1800078a4  mov     [rsp+108h+var_E8], ebx
0x1800078a8  mov     edi, [rsp+108h+arg_8]
0x1800078af  mov     rsi, [rsp+108h+arg_0]
0x1800078b7  mov     rax, cs:_pRawDllMain
0x1800078be  test    rax, rax
0x1800078c1  jz      short loc_1800078F4
0x1800078c3  cmp     cs:dword_1800182CC, 0
0x1800078ca  jz      short loc_1800078F4
0x1800078cc  mov     r8, [rsp+108h+lpvReserved]
0x1800078d4  mov     edx, edi
0x1800078d6  mov     rcx, rsi
0x1800078d9  call    cs:__guard_dispatch_icall_fptr
0x1800078df  mov     ebx, eax
0x1800078e1  mov     [rsp+108h+var_E8], eax
0x1800078e5  jmp     short loc_1800078F4
0x1800078e7  xor     ebx, ebx
0x1800078e9  mov     [rsp+108h+var_E8], ebx
0x1800078ed  mov     edi, [rsp+108h+arg_8]
0x1800078f4  cmp     edi, 1
0x1800078f7  ja      short loc_180007903
0x1800078f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180007903  mov     eax, ebx
0x180007905  add     rsp, 0F0h
0x18000790c  pop     rdi
0x18000790d  pop     rsi
0x18000790e  pop     rbx
0x18000790f  retn
0x18000f1e4  push    rbp
0x18000f1e6  sub     rsp, 20h
0x18000f1ea  mov     rbp, rdx
0x18000f1ed  mov     rax, [rcx]
0x18000f1f0  mov     edx, [rax]
0x18000f1f2  mov     [rbp+0A8h], rcx
0x18000f1f9  mov     [rbp+28h], edx
0x18000f1fc  mov     eax, [rbp+28h]
0x18000f1ff  cmp     eax, 0E06D7363h
0x18000f204  jnz     short loc_18000F21A
0x18000f206  mov     rdx, [rbp+0A8h]
0x18000f20d  mov     ecx, [rbp+28h]
0x18000f210  call    _XcptFilter_0
0x18000f215  mov     [rbp+30h], eax
0x18000f218  jmp     short loc_18000F221
0x18000f21a  mov     dword ptr [rbp+30h], 0
0x18000f221  mov     eax, [rbp+30h]
0x18000f224  add     rsp, 20h
0x18000f228  pop     rbp
0x18000f229  retn
0x18000f22b  push    rbp
0x18000f22d  sub     rsp, 20h
0x18000f231  mov     rbp, rdx
0x18000f234  mov     rax, [rcx]
0x18000f237  mov     edx, [rax]
0x18000f239  mov     [rbp+0B0h], rcx
0x18000f240  mov     [rbp+38h], edx
0x18000f243  mov     eax, [rbp+38h]
0x18000f246  cmp     eax, 0E06D7363h
0x18000f24b  jnz     short loc_18000F261
0x18000f24d  mov     rdx, [rbp+0B0h]
0x18000f254  mov     ecx, [rbp+38h]
0x18000f257  call    _XcptFilter_0
0x18000f25c  mov     [rbp+40h], eax
0x18000f25f  jmp     short loc_18000F268
0x18000f261  mov     dword ptr [rbp+40h], 0
0x18000f268  mov     eax, [rbp+40h]
0x18000f26b  add     rsp, 20h
0x18000f26f  pop     rbp
0x18000f270  retn
0x18000f272  push    rbp
0x18000f274  sub     rsp, 20h
0x18000f278  mov     rbp, rdx
0x18000f27b  mov     rax, [rcx]
0x18000f27e  mov     edx, [rax]
0x18000f280  mov     [rbp+0B8h], rcx
0x18000f287  mov     [rbp+48h], edx
0x18000f28a  mov     eax, [rbp+48h]
0x18000f28d  cmp     eax, 0E06D7363h
0x18000f292  jnz     short loc_18000F2A8
0x18000f294  mov     rdx, [rbp+0B8h]
0x18000f29b  mov     ecx, [rbp+48h]
0x18000f29e  call    _XcptFilter_0
0x18000f2a3  mov     [rbp+50h], eax
0x18000f2a6  jmp     short loc_18000F2AF
0x18000f2a8  mov     dword ptr [rbp+50h], 0
0x18000f2af  mov     eax, [rbp+50h]
0x18000f2b2  add     rsp, 20h
0x18000f2b6  pop     rbp
0x18000f2b7  retn
0x18000f2b9  push    rbp
0x18000f2bb  sub     rsp, 20h
0x18000f2bf  mov     rbp, rdx
0x18000f2c2  mov     rax, [rcx]
0x18000f2c5  mov     edx, [rax]
0x18000f2c7  mov     [rbp+0C0h], rcx
0x18000f2ce  mov     [rbp+58h], edx
0x18000f2d1  mov     eax, [rbp+58h]
0x18000f2d4  cmp     eax, 0E06D7363h
0x18000f2d9  jnz     short loc_18000F2EF
0x18000f2db  mov     rdx, [rbp+0C0h]
0x18000f2e2  mov     ecx, [rbp+58h]
0x18000f2e5  call    _XcptFilter_0
0x18000f2ea  mov     [rbp+60h], eax
0x18000f2ed  jmp     short loc_18000F2F6
0x18000f2ef  mov     dword ptr [rbp+60h], 0
0x18000f2f6  mov     eax, [rbp+60h]
0x18000f2f9  add     rsp, 20h
0x18000f2fd  pop     rbp
0x18000f2fe  retn
0x18000f300  push    rbp
0x18000f302  sub     rsp, 20h
0x18000f306  mov     rbp, rdx
0x18000f309  mov     rax, [rcx]
0x18000f30c  mov     edx, [rax]
0x18000f30e  mov     [rbp+0C8h], rcx
0x18000f315  mov     [rbp+68h], edx
0x18000f318  mov     eax, [rbp+68h]
0x18000f31b  cmp     eax, 0E06D7363h
0x18000f320  jnz     short loc_18000F336
0x18000f322  mov     rdx, [rbp+0C8h]
0x18000f329  mov     ecx, [rbp+68h]
0x18000f32c  call    _XcptFilter_0
0x18000f331  mov     [rbp+70h], eax
0x18000f334  jmp     short loc_18000F33D
0x18000f336  mov     dword ptr [rbp+70h], 0
0x18000f33d  mov     eax, [rbp+70h]
0x18000f340  add     rsp, 20h
0x18000f344  pop     rbp
0x18000f345  retn
0x18000f347  push    rbp
0x18000f349  sub     rsp, 20h
0x18000f34d  mov     rbp, rdx
0x18000f350  mov     rax, [rcx]
0x18000f353  mov     edx, [rax]
0x18000f355  mov     [rbp+0D0h], rcx
0x18000f35c  mov     [rbp+78h], edx
0x18000f35f  mov     eax, [rbp+78h]
0x18000f362  cmp     eax, 0E06D7363h
0x18000f367  jnz     short loc_18000F380
0x18000f369  mov     rdx, [rbp+0D0h]
0x18000f370  mov     ecx, [rbp+78h]
0x18000f373  call    _XcptFilter_0
0x18000f378  mov     [rbp+80h], eax
0x18000f37e  jmp     short loc_18000F38A
0x18000f380  mov     dword ptr [rbp+80h], 0
0x18000f38a  mov     eax, [rbp+80h]
0x18000f390  add     rsp, 20h
0x18000f394  pop     rbp
0x18000f395  retn
0x18000f397  push    rbp
0x18000f399  sub     rsp, 20h
0x18000f39d  mov     rbp, rdx
0x18000f3a0  mov     rax, [rcx]
0x18000f3a3  mov     edx, [rax]
0x18000f3a5  mov     [rbp+0D8h], rcx
0x18000f3ac  mov     [rbp+88h], edx
0x18000f3b2  mov     eax, [rbp+88h]
0x18000f3b8  cmp     eax, 0E06D7363h
0x18000f3bd  jnz     short loc_18000F3D9
0x18000f3bf  mov     rdx, [rbp+0D8h]
0x18000f3c6  mov     ecx, [rbp+88h]
0x18000f3cc  call    _XcptFilter_0
0x18000f3d1  mov     [rbp+90h], eax
0x18000f3d7  jmp     short loc_18000F3E3
0x18000f3d9  mov     dword ptr [rbp+90h], 0
0x18000f3e3  mov     eax, [rbp+90h]
0x18000f3e9  add     rsp, 20h
0x18000f3ed  pop     rbp
0x18000f3ee  retn
0x18000f3f0  push    rbp
0x18000f3f2  sub     rsp, 20h
0x18000f3f6  mov     rbp, rdx
0x18000f3f9  mov     rax, [rcx]
0x18000f3fc  mov     edx, [rax]
0x18000f3fe  mov     [rbp+0E0h], rcx
0x18000f405  mov     [rbp+98h], edx
0x18000f40b  mov     eax, [rbp+98h]
0x18000f411  cmp     eax, 0E06D7363h
0x18000f416  jnz     short loc_18000F432
0x18000f418  mov     rdx, [rbp+0E0h]
0x18000f41f  mov     ecx, [rbp+98h]
0x18000f425  call    _XcptFilter_0
0x18000f42a  mov     [rbp+0A0h], eax
0x18000f430  jmp     short loc_18000F43C
0x18000f432  mov     dword ptr [rbp+0A0h], 0
0x18000f43c  mov     eax, [rbp+0A0h]
0x18000f442  add     rsp, 20h
0x18000f446  pop     rbp
0x18000f447  retn
0x18000f449  push    rbp
0x18000f44b  sub     rsp, 20h
0x18000f44f  mov     rbp, rdx
0x18000f452  cmp     dword ptr [rbp+118h], 1
0x18000f459  ja      short loc_18000F465
0x18000f45b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
