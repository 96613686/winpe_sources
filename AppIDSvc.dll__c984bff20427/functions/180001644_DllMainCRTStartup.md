# __DllMainCRTStartup

- ea: `0x180001644`
- end: `0x180001850`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001600`

## callees

- `0x1800013d0`
- `0x180001644`
- `0x180001bda`
- `0x180001db8`
- `0x18000c150`

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
  if ( (_DWORD)fdwReason || dword_180017218 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001721C = 1;
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
            if ( dword_18001721C )
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
0x180001644  mov     [rsp+lpvReserved], r8
0x180001649  mov     [rsp+arg_8], edx
0x18000164d  mov     [rsp+arg_0], rcx
0x180001652  push    rbx
0x180001653  push    rsi
0x180001654  push    rdi
0x180001655  sub     rsp, 0F0h
0x18000165c  mov     edi, edx
0x18000165e  mov     rsi, rcx
0x180001661  mov     ebx, 1
0x180001666  cmp     edx, ebx
0x180001668  ja      short loc_180001670
0x18000166a  mov     cs:__native_dllmain_reason, edx
0x180001670  test    edx, edx
0x180001672  jnz     short loc_180001687
0x180001674  cmp     cs:dword_180017218, edx
0x18000167a  jnz     short loc_180001687
0x18000167c  xor     ebx, ebx
0x18000167e  mov     [rsp+108h+var_E8], ebx
0x180001682  jmp     loc_180001834
0x180001687  lea     eax, [rdx-1]
0x18000168a  cmp     eax, 1
0x18000168d  ja      loc_180001714
0x180001693  mov     rax, cs:_pRawDllMain
0x18000169a  test    rax, rax
0x18000169d  jz      short loc_1800016D5
0x18000169f  cmp     edx, 1
0x1800016a2  jnz     short loc_1800016AA
0x1800016a4  mov     cs:dword_18001721C, edx
0x1800016aa  mov     r8, [rsp+108h+lpvReserved]
0x1800016b2  call    cs:__guard_dispatch_icall_fptr
0x1800016b8  mov     ebx, eax
0x1800016ba  mov     [rsp+108h+var_E8], eax
0x1800016be  jmp     short loc_1800016D5
0x1800016c0  xor     ebx, ebx
0x1800016c2  mov     [rsp+108h+var_E8], ebx
0x1800016c6  mov     edi, [rsp+108h+arg_8]
0x1800016cd  mov     rsi, [rsp+108h+arg_0]
0x1800016d5  test    ebx, ebx
0x1800016d7  jz      loc_180001834
0x1800016dd  mov     r8, [rsp+108h+lpvReserved]
0x1800016e5  mov     edx, edi
0x1800016e7  mov     rcx, rsi
0x1800016ea  call    _CRT_INIT
0x1800016ef  mov     ebx, eax
0x1800016f1  mov     [rsp+108h+var_E8], eax
0x1800016f5  jmp     short loc_18000170C
0x1800016f7  xor     ebx, ebx
0x1800016f9  mov     [rsp+108h+var_E8], ebx
0x1800016fd  mov     edi, [rsp+108h+arg_8]
0x180001704  mov     rsi, [rsp+108h+arg_0]
0x18000170c  test    ebx, ebx
0x18000170e  jz      loc_180001834
0x180001714  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000171c  mov     edx, edi; fdwReason
0x18000171e  mov     rcx, rsi; hinstDLL
0x180001721  call    DllMain
0x180001726  mov     ebx, eax
0x180001728  mov     [rsp+108h+var_E8], eax
0x18000172c  jmp     short loc_180001743
0x18000172e  xor     ebx, ebx
0x180001730  mov     [rsp+108h+var_E8], ebx
0x180001734  mov     edi, [rsp+108h+arg_8]
0x18000173b  mov     rsi, [rsp+108h+arg_0]
0x180001743  cmp     edi, 1
0x180001746  jnz     short loc_1800017BF
0x180001748  test    ebx, ebx
0x18000174a  jnz     short loc_1800017BF
0x18000174c  xor     r8d, r8d; lpvReserved
0x18000174f  xor     edx, edx; fdwReason
0x180001751  mov     rcx, rsi; hinstDLL
0x180001754  call    DllMain
0x180001759  jmp     short loc_18000176E
0x18000175b  mov     edi, [rsp+108h+arg_8]
0x180001762  mov     rsi, [rsp+108h+arg_0]
0x18000176a  mov     ebx, [rsp+108h+var_E8]
0x18000176e  xor     r8d, r8d
0x180001771  xor     edx, edx
0x180001773  mov     rcx, rsi
0x180001776  call    _CRT_INIT
0x18000177b  jmp     short loc_180001790
0x18000177d  mov     edi, [rsp+108h+arg_8]
0x180001784  mov     rsi, [rsp+108h+arg_0]
0x18000178c  mov     ebx, [rsp+108h+var_E8]
0x180001790  mov     rax, cs:_pRawDllMain
0x180001797  test    rax, rax
0x18000179a  jz      short loc_1800017BF
0x18000179c  xor     r8d, r8d
0x18000179f  xor     edx, edx
0x1800017a1  mov     rcx, rsi
0x1800017a4  call    cs:__guard_dispatch_icall_fptr
0x1800017aa  jmp     short loc_1800017BF
0x1800017ac  mov     edi, [rsp+108h+arg_8]
0x1800017b3  mov     rsi, [rsp+108h+arg_0]
0x1800017bb  mov     ebx, [rsp+108h+var_E8]
0x1800017bf  test    edi, edi
0x1800017c1  jz      short loc_1800017C8
0x1800017c3  cmp     edi, 3
0x1800017c6  jnz     short loc_180001834
0x1800017c8  mov     r8, [rsp+108h+lpvReserved]
0x1800017d0  mov     edx, edi
0x1800017d2  mov     rcx, rsi
0x1800017d5  call    _CRT_INIT
0x1800017da  mov     ebx, eax
0x1800017dc  mov     [rsp+108h+var_E8], eax
0x1800017e0  jmp     short loc_1800017F7
0x1800017e2  xor     ebx, ebx
0x1800017e4  mov     [rsp+108h+var_E8], ebx
0x1800017e8  mov     edi, [rsp+108h+arg_8]
0x1800017ef  mov     rsi, [rsp+108h+arg_0]
0x1800017f7  mov     rax, cs:_pRawDllMain
0x1800017fe  test    rax, rax
0x180001801  jz      short loc_180001834
0x180001803  cmp     cs:dword_18001721C, 0
0x18000180a  jz      short loc_180001834
0x18000180c  mov     r8, [rsp+108h+lpvReserved]
0x180001814  mov     edx, edi
0x180001816  mov     rcx, rsi
0x180001819  call    cs:__guard_dispatch_icall_fptr
0x18000181f  mov     ebx, eax
0x180001821  mov     [rsp+108h+var_E8], eax
0x180001825  jmp     short loc_180001834
0x180001827  xor     ebx, ebx
0x180001829  mov     [rsp+108h+var_E8], ebx
0x18000182d  mov     edi, [rsp+108h+arg_8]
0x180001834  cmp     edi, 1
0x180001837  ja      short loc_180001843
0x180001839  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001843  mov     eax, ebx
0x180001845  add     rsp, 0F0h
0x18000184c  pop     rdi
0x18000184d  pop     rsi
0x18000184e  pop     rbx
0x18000184f  retn
0x18000c1f3  push    rbp
0x18000c1f5  sub     rsp, 20h
0x18000c1f9  mov     rbp, rdx
0x18000c1fc  mov     rax, [rcx]
0x18000c1ff  mov     edx, [rax]
0x18000c201  mov     [rbp+0A8h], rcx
0x18000c208  mov     [rbp+28h], edx
0x18000c20b  mov     eax, [rbp+28h]
0x18000c20e  cmp     eax, 0E06D7363h
0x18000c213  jnz     short loc_18000C229
0x18000c215  mov     rdx, [rbp+0A8h]
0x18000c21c  mov     ecx, [rbp+28h]
0x18000c21f  call    _XcptFilter_0
0x18000c224  mov     [rbp+30h], eax
0x18000c227  jmp     short loc_18000C230
0x18000c229  mov     dword ptr [rbp+30h], 0
0x18000c230  mov     eax, [rbp+30h]
0x18000c233  add     rsp, 20h
0x18000c237  pop     rbp
0x18000c238  retn
0x18000c23a  push    rbp
0x18000c23c  sub     rsp, 20h
0x18000c240  mov     rbp, rdx
0x18000c243  mov     rax, [rcx]
0x18000c246  mov     edx, [rax]
0x18000c248  mov     [rbp+0B0h], rcx
0x18000c24f  mov     [rbp+38h], edx
0x18000c252  mov     eax, [rbp+38h]
0x18000c255  cmp     eax, 0E06D7363h
0x18000c25a  jnz     short loc_18000C270
0x18000c25c  mov     rdx, [rbp+0B0h]
0x18000c263  mov     ecx, [rbp+38h]
0x18000c266  call    _XcptFilter_0
0x18000c26b  mov     [rbp+40h], eax
0x18000c26e  jmp     short loc_18000C277
0x18000c270  mov     dword ptr [rbp+40h], 0
0x18000c277  mov     eax, [rbp+40h]
0x18000c27a  add     rsp, 20h
0x18000c27e  pop     rbp
0x18000c27f  retn
0x18000c281  push    rbp
0x18000c283  sub     rsp, 20h
0x18000c287  mov     rbp, rdx
0x18000c28a  mov     rax, [rcx]
0x18000c28d  mov     edx, [rax]
0x18000c28f  mov     [rbp+0B8h], rcx
0x18000c296  mov     [rbp+48h], edx
0x18000c299  mov     eax, [rbp+48h]
0x18000c29c  cmp     eax, 0E06D7363h
0x18000c2a1  jnz     short loc_18000C2B7
0x18000c2a3  mov     rdx, [rbp+0B8h]
0x18000c2aa  mov     ecx, [rbp+48h]
0x18000c2ad  call    _XcptFilter_0
0x18000c2b2  mov     [rbp+50h], eax
0x18000c2b5  jmp     short loc_18000C2BE
0x18000c2b7  mov     dword ptr [rbp+50h], 0
0x18000c2be  mov     eax, [rbp+50h]
0x18000c2c1  add     rsp, 20h
0x18000c2c5  pop     rbp
0x18000c2c6  retn
0x18000c2c8  push    rbp
0x18000c2ca  sub     rsp, 20h
0x18000c2ce  mov     rbp, rdx
0x18000c2d1  mov     rax, [rcx]
0x18000c2d4  mov     edx, [rax]
0x18000c2d6  mov     [rbp+0C0h], rcx
0x18000c2dd  mov     [rbp+58h], edx
0x18000c2e0  mov     eax, [rbp+58h]
0x18000c2e3  cmp     eax, 0E06D7363h
0x18000c2e8  jnz     short loc_18000C2FE
0x18000c2ea  mov     rdx, [rbp+0C0h]
0x18000c2f1  mov     ecx, [rbp+58h]
0x18000c2f4  call    _XcptFilter_0
0x18000c2f9  mov     [rbp+60h], eax
0x18000c2fc  jmp     short loc_18000C305
0x18000c2fe  mov     dword ptr [rbp+60h], 0
0x18000c305  mov     eax, [rbp+60h]
0x18000c308  add     rsp, 20h
0x18000c30c  pop     rbp
0x18000c30d  retn
0x18000c30f  push    rbp
0x18000c311  sub     rsp, 20h
0x18000c315  mov     rbp, rdx
0x18000c318  mov     rax, [rcx]
0x18000c31b  mov     edx, [rax]
0x18000c31d  mov     [rbp+0C8h], rcx
0x18000c324  mov     [rbp+68h], edx
0x18000c327  mov     eax, [rbp+68h]
0x18000c32a  cmp     eax, 0E06D7363h
0x18000c32f  jnz     short loc_18000C345
0x18000c331  mov     rdx, [rbp+0C8h]
0x18000c338  mov     ecx, [rbp+68h]
0x18000c33b  call    _XcptFilter_0
0x18000c340  mov     [rbp+70h], eax
0x18000c343  jmp     short loc_18000C34C
0x18000c345  mov     dword ptr [rbp+70h], 0
0x18000c34c  mov     eax, [rbp+70h]
0x18000c34f  add     rsp, 20h
0x18000c353  pop     rbp
0x18000c354  retn
0x18000c356  push    rbp
0x18000c358  sub     rsp, 20h
0x18000c35c  mov     rbp, rdx
0x18000c35f  mov     rax, [rcx]
0x18000c362  mov     edx, [rax]
0x18000c364  mov     [rbp+0D0h], rcx
0x18000c36b  mov     [rbp+78h], edx
0x18000c36e  mov     eax, [rbp+78h]
0x18000c371  cmp     eax, 0E06D7363h
0x18000c376  jnz     short loc_18000C38F
0x18000c378  mov     rdx, [rbp+0D0h]
0x18000c37f  mov     ecx, [rbp+78h]
0x18000c382  call    _XcptFilter_0
0x18000c387  mov     [rbp+80h], eax
0x18000c38d  jmp     short loc_18000C399
0x18000c38f  mov     dword ptr [rbp+80h], 0
0x18000c399  mov     eax, [rbp+80h]
0x18000c39f  add     rsp, 20h
0x18000c3a3  pop     rbp
0x18000c3a4  retn
0x18000c3a6  push    rbp
0x18000c3a8  sub     rsp, 20h
0x18000c3ac  mov     rbp, rdx
0x18000c3af  mov     rax, [rcx]
0x18000c3b2  mov     edx, [rax]
0x18000c3b4  mov     [rbp+0D8h], rcx
0x18000c3bb  mov     [rbp+88h], edx
0x18000c3c1  mov     eax, [rbp+88h]
0x18000c3c7  cmp     eax, 0E06D7363h
0x18000c3cc  jnz     short loc_18000C3E8
0x18000c3ce  mov     rdx, [rbp+0D8h]
0x18000c3d5  mov     ecx, [rbp+88h]
0x18000c3db  call    _XcptFilter_0
0x18000c3e0  mov     [rbp+90h], eax
0x18000c3e6  jmp     short loc_18000C3F2
0x18000c3e8  mov     dword ptr [rbp+90h], 0
0x18000c3f2  mov     eax, [rbp+90h]
0x18000c3f8  add     rsp, 20h
0x18000c3fc  pop     rbp
0x18000c3fd  retn
0x18000c3ff  push    rbp
0x18000c401  sub     rsp, 20h
0x18000c405  mov     rbp, rdx
0x18000c408  mov     rax, [rcx]
0x18000c40b  mov     edx, [rax]
0x18000c40d  mov     [rbp+0E0h], rcx
0x18000c414  mov     [rbp+98h], edx
0x18000c41a  mov     eax, [rbp+98h]
0x18000c420  cmp     eax, 0E06D7363h
0x18000c425  jnz     short loc_18000C441
0x18000c427  mov     rdx, [rbp+0E0h]
0x18000c42e  mov     ecx, [rbp+98h]
0x18000c434  call    _XcptFilter_0
0x18000c439  mov     [rbp+0A0h], eax
0x18000c43f  jmp     short loc_18000C44B
0x18000c441  mov     dword ptr [rbp+0A0h], 0
0x18000c44b  mov     eax, [rbp+0A0h]
0x18000c451  add     rsp, 20h
0x18000c455  pop     rbp
0x18000c456  retn
0x18000c458  push    rbp
0x18000c45a  sub     rsp, 20h
0x18000c45e  mov     rbp, rdx
0x18000c461  cmp     dword ptr [rbp+118h], 1
0x18000c468  ja      short loc_18000C474
0x18000c46a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
