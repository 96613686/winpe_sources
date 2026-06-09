# __DllMainCRTStartup

- ea: `0x1800017b4`
- end: `0x1800019c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001770`

## callees

- `0x180001540`
- `0x1800017b4`
- `0x180001cfe`
- `0x1800025d8`
- `0x1800094b0`

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
  if ( (_DWORD)fdwReason || dword_18001318C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180013190 = 1;
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
            if ( dword_180013190 )
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
0x1800017b4  mov     [rsp+lpvReserved], r8
0x1800017b9  mov     [rsp+arg_8], edx
0x1800017bd  mov     [rsp+arg_0], rcx
0x1800017c2  push    rbx
0x1800017c3  push    rsi
0x1800017c4  push    rdi
0x1800017c5  sub     rsp, 0F0h
0x1800017cc  mov     edi, edx
0x1800017ce  mov     rsi, rcx
0x1800017d1  mov     ebx, 1
0x1800017d6  cmp     edx, ebx
0x1800017d8  ja      short loc_1800017E0
0x1800017da  mov     cs:__native_dllmain_reason, edx
0x1800017e0  test    edx, edx
0x1800017e2  jnz     short loc_1800017F7
0x1800017e4  cmp     cs:dword_18001318C, edx
0x1800017ea  jnz     short loc_1800017F7
0x1800017ec  xor     ebx, ebx
0x1800017ee  mov     [rsp+108h+var_E8], ebx
0x1800017f2  jmp     loc_1800019A4
0x1800017f7  lea     eax, [rdx-1]
0x1800017fa  cmp     eax, 1
0x1800017fd  ja      loc_180001884
0x180001803  mov     rax, cs:_pRawDllMain
0x18000180a  test    rax, rax
0x18000180d  jz      short loc_180001845
0x18000180f  cmp     edx, 1
0x180001812  jnz     short loc_18000181A
0x180001814  mov     cs:dword_180013190, edx
0x18000181a  mov     r8, [rsp+108h+lpvReserved]
0x180001822  call    cs:__guard_dispatch_icall_fptr
0x180001828  mov     ebx, eax
0x18000182a  mov     [rsp+108h+var_E8], eax
0x18000182e  jmp     short loc_180001845
0x180001830  xor     ebx, ebx
0x180001832  mov     [rsp+108h+var_E8], ebx
0x180001836  mov     edi, [rsp+108h+arg_8]
0x18000183d  mov     rsi, [rsp+108h+arg_0]
0x180001845  test    ebx, ebx
0x180001847  jz      loc_1800019A4
0x18000184d  mov     r8, [rsp+108h+lpvReserved]
0x180001855  mov     edx, edi
0x180001857  mov     rcx, rsi
0x18000185a  call    _CRT_INIT
0x18000185f  mov     ebx, eax
0x180001861  mov     [rsp+108h+var_E8], eax
0x180001865  jmp     short loc_18000187C
0x180001867  xor     ebx, ebx
0x180001869  mov     [rsp+108h+var_E8], ebx
0x18000186d  mov     edi, [rsp+108h+arg_8]
0x180001874  mov     rsi, [rsp+108h+arg_0]
0x18000187c  test    ebx, ebx
0x18000187e  jz      loc_1800019A4
0x180001884  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000188c  mov     edx, edi; fdwReason
0x18000188e  mov     rcx, rsi; hinstDLL
0x180001891  call    DllMain
0x180001896  mov     ebx, eax
0x180001898  mov     [rsp+108h+var_E8], eax
0x18000189c  jmp     short loc_1800018B3
0x18000189e  xor     ebx, ebx
0x1800018a0  mov     [rsp+108h+var_E8], ebx
0x1800018a4  mov     edi, [rsp+108h+arg_8]
0x1800018ab  mov     rsi, [rsp+108h+arg_0]
0x1800018b3  cmp     edi, 1
0x1800018b6  jnz     short loc_18000192F
0x1800018b8  test    ebx, ebx
0x1800018ba  jnz     short loc_18000192F
0x1800018bc  xor     r8d, r8d; lpvReserved
0x1800018bf  xor     edx, edx; fdwReason
0x1800018c1  mov     rcx, rsi; hinstDLL
0x1800018c4  call    DllMain
0x1800018c9  jmp     short loc_1800018DE
0x1800018cb  mov     edi, [rsp+108h+arg_8]
0x1800018d2  mov     rsi, [rsp+108h+arg_0]
0x1800018da  mov     ebx, [rsp+108h+var_E8]
0x1800018de  xor     r8d, r8d
0x1800018e1  xor     edx, edx
0x1800018e3  mov     rcx, rsi
0x1800018e6  call    _CRT_INIT
0x1800018eb  jmp     short loc_180001900
0x1800018ed  mov     edi, [rsp+108h+arg_8]
0x1800018f4  mov     rsi, [rsp+108h+arg_0]
0x1800018fc  mov     ebx, [rsp+108h+var_E8]
0x180001900  mov     rax, cs:_pRawDllMain
0x180001907  test    rax, rax
0x18000190a  jz      short loc_18000192F
0x18000190c  xor     r8d, r8d
0x18000190f  xor     edx, edx
0x180001911  mov     rcx, rsi
0x180001914  call    cs:__guard_dispatch_icall_fptr
0x18000191a  jmp     short loc_18000192F
0x18000191c  mov     edi, [rsp+108h+arg_8]
0x180001923  mov     rsi, [rsp+108h+arg_0]
0x18000192b  mov     ebx, [rsp+108h+var_E8]
0x18000192f  test    edi, edi
0x180001931  jz      short loc_180001938
0x180001933  cmp     edi, 3
0x180001936  jnz     short loc_1800019A4
0x180001938  mov     r8, [rsp+108h+lpvReserved]
0x180001940  mov     edx, edi
0x180001942  mov     rcx, rsi
0x180001945  call    _CRT_INIT
0x18000194a  mov     ebx, eax
0x18000194c  mov     [rsp+108h+var_E8], eax
0x180001950  jmp     short loc_180001967
0x180001952  xor     ebx, ebx
0x180001954  mov     [rsp+108h+var_E8], ebx
0x180001958  mov     edi, [rsp+108h+arg_8]
0x18000195f  mov     rsi, [rsp+108h+arg_0]
0x180001967  mov     rax, cs:_pRawDllMain
0x18000196e  test    rax, rax
0x180001971  jz      short loc_1800019A4
0x180001973  cmp     cs:dword_180013190, 0
0x18000197a  jz      short loc_1800019A4
0x18000197c  mov     r8, [rsp+108h+lpvReserved]
0x180001984  mov     edx, edi
0x180001986  mov     rcx, rsi
0x180001989  call    cs:__guard_dispatch_icall_fptr
0x18000198f  mov     ebx, eax
0x180001991  mov     [rsp+108h+var_E8], eax
0x180001995  jmp     short loc_1800019A4
0x180001997  xor     ebx, ebx
0x180001999  mov     [rsp+108h+var_E8], ebx
0x18000199d  mov     edi, [rsp+108h+arg_8]
0x1800019a4  cmp     edi, 1
0x1800019a7  ja      short loc_1800019B3
0x1800019a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800019b3  mov     eax, ebx
0x1800019b5  add     rsp, 0F0h
0x1800019bc  pop     rdi
0x1800019bd  pop     rsi
0x1800019be  pop     rbx
0x1800019bf  retn
0x1800094f0  push    rbp
0x1800094f2  sub     rsp, 20h
0x1800094f6  mov     rbp, rdx
0x1800094f9  mov     rax, [rcx]
0x1800094fc  mov     edx, [rax]
0x1800094fe  mov     [rbp+0A8h], rcx
0x180009505  mov     [rbp+28h], edx
0x180009508  mov     eax, [rbp+28h]
0x18000950b  cmp     eax, 0E06D7363h
0x180009510  jnz     short loc_180009526
0x180009512  mov     rdx, [rbp+0A8h]
0x180009519  mov     ecx, [rbp+28h]
0x18000951c  call    _XcptFilter_0
0x180009521  mov     [rbp+30h], eax
0x180009524  jmp     short loc_18000952D
0x180009526  mov     dword ptr [rbp+30h], 0
0x18000952d  mov     eax, [rbp+30h]
0x180009530  add     rsp, 20h
0x180009534  pop     rbp
0x180009535  retn
0x180009537  push    rbp
0x180009539  sub     rsp, 20h
0x18000953d  mov     rbp, rdx
0x180009540  mov     rax, [rcx]
0x180009543  mov     edx, [rax]
0x180009545  mov     [rbp+0B0h], rcx
0x18000954c  mov     [rbp+38h], edx
0x18000954f  mov     eax, [rbp+38h]
0x180009552  cmp     eax, 0E06D7363h
0x180009557  jnz     short loc_18000956D
0x180009559  mov     rdx, [rbp+0B0h]
0x180009560  mov     ecx, [rbp+38h]
0x180009563  call    _XcptFilter_0
0x180009568  mov     [rbp+40h], eax
0x18000956b  jmp     short loc_180009574
0x18000956d  mov     dword ptr [rbp+40h], 0
0x180009574  mov     eax, [rbp+40h]
0x180009577  add     rsp, 20h
0x18000957b  pop     rbp
0x18000957c  retn
0x18000957e  push    rbp
0x180009580  sub     rsp, 20h
0x180009584  mov     rbp, rdx
0x180009587  mov     rax, [rcx]
0x18000958a  mov     edx, [rax]
0x18000958c  mov     [rbp+0B8h], rcx
0x180009593  mov     [rbp+48h], edx
0x180009596  mov     eax, [rbp+48h]
0x180009599  cmp     eax, 0E06D7363h
0x18000959e  jnz     short loc_1800095B4
0x1800095a0  mov     rdx, [rbp+0B8h]
0x1800095a7  mov     ecx, [rbp+48h]
0x1800095aa  call    _XcptFilter_0
0x1800095af  mov     [rbp+50h], eax
0x1800095b2  jmp     short loc_1800095BB
0x1800095b4  mov     dword ptr [rbp+50h], 0
0x1800095bb  mov     eax, [rbp+50h]
0x1800095be  add     rsp, 20h
0x1800095c2  pop     rbp
0x1800095c3  retn
0x1800095c5  push    rbp
0x1800095c7  sub     rsp, 20h
0x1800095cb  mov     rbp, rdx
0x1800095ce  mov     rax, [rcx]
0x1800095d1  mov     edx, [rax]
0x1800095d3  mov     [rbp+0C0h], rcx
0x1800095da  mov     [rbp+58h], edx
0x1800095dd  mov     eax, [rbp+58h]
0x1800095e0  cmp     eax, 0E06D7363h
0x1800095e5  jnz     short loc_1800095FB
0x1800095e7  mov     rdx, [rbp+0C0h]
0x1800095ee  mov     ecx, [rbp+58h]
0x1800095f1  call    _XcptFilter_0
0x1800095f6  mov     [rbp+60h], eax
0x1800095f9  jmp     short loc_180009602
0x1800095fb  mov     dword ptr [rbp+60h], 0
0x180009602  mov     eax, [rbp+60h]
0x180009605  add     rsp, 20h
0x180009609  pop     rbp
0x18000960a  retn
0x18000960c  push    rbp
0x18000960e  sub     rsp, 20h
0x180009612  mov     rbp, rdx
0x180009615  mov     rax, [rcx]
0x180009618  mov     edx, [rax]
0x18000961a  mov     [rbp+0C8h], rcx
0x180009621  mov     [rbp+68h], edx
0x180009624  mov     eax, [rbp+68h]
0x180009627  cmp     eax, 0E06D7363h
0x18000962c  jnz     short loc_180009642
0x18000962e  mov     rdx, [rbp+0C8h]
0x180009635  mov     ecx, [rbp+68h]
0x180009638  call    _XcptFilter_0
0x18000963d  mov     [rbp+70h], eax
0x180009640  jmp     short loc_180009649
0x180009642  mov     dword ptr [rbp+70h], 0
0x180009649  mov     eax, [rbp+70h]
0x18000964c  add     rsp, 20h
0x180009650  pop     rbp
0x180009651  retn
0x180009653  push    rbp
0x180009655  sub     rsp, 20h
0x180009659  mov     rbp, rdx
0x18000965c  mov     rax, [rcx]
0x18000965f  mov     edx, [rax]
0x180009661  mov     [rbp+0D0h], rcx
0x180009668  mov     [rbp+78h], edx
0x18000966b  mov     eax, [rbp+78h]
0x18000966e  cmp     eax, 0E06D7363h
0x180009673  jnz     short loc_18000968C
0x180009675  mov     rdx, [rbp+0D0h]
0x18000967c  mov     ecx, [rbp+78h]
0x18000967f  call    _XcptFilter_0
0x180009684  mov     [rbp+80h], eax
0x18000968a  jmp     short loc_180009696
0x18000968c  mov     dword ptr [rbp+80h], 0
0x180009696  mov     eax, [rbp+80h]
0x18000969c  add     rsp, 20h
0x1800096a0  pop     rbp
0x1800096a1  retn
0x1800096a3  push    rbp
0x1800096a5  sub     rsp, 20h
0x1800096a9  mov     rbp, rdx
0x1800096ac  mov     rax, [rcx]
0x1800096af  mov     edx, [rax]
0x1800096b1  mov     [rbp+0D8h], rcx
0x1800096b8  mov     [rbp+88h], edx
0x1800096be  mov     eax, [rbp+88h]
0x1800096c4  cmp     eax, 0E06D7363h
0x1800096c9  jnz     short loc_1800096E5
0x1800096cb  mov     rdx, [rbp+0D8h]
0x1800096d2  mov     ecx, [rbp+88h]
0x1800096d8  call    _XcptFilter_0
0x1800096dd  mov     [rbp+90h], eax
0x1800096e3  jmp     short loc_1800096EF
0x1800096e5  mov     dword ptr [rbp+90h], 0
0x1800096ef  mov     eax, [rbp+90h]
0x1800096f5  add     rsp, 20h
0x1800096f9  pop     rbp
0x1800096fa  retn
0x1800096fc  push    rbp
0x1800096fe  sub     rsp, 20h
0x180009702  mov     rbp, rdx
0x180009705  mov     rax, [rcx]
0x180009708  mov     edx, [rax]
0x18000970a  mov     [rbp+0E0h], rcx
0x180009711  mov     [rbp+98h], edx
0x180009717  mov     eax, [rbp+98h]
0x18000971d  cmp     eax, 0E06D7363h
0x180009722  jnz     short loc_18000973E
0x180009724  mov     rdx, [rbp+0E0h]
0x18000972b  mov     ecx, [rbp+98h]
0x180009731  call    _XcptFilter_0
0x180009736  mov     [rbp+0A0h], eax
0x18000973c  jmp     short loc_180009748
0x18000973e  mov     dword ptr [rbp+0A0h], 0
0x180009748  mov     eax, [rbp+0A0h]
0x18000974e  add     rsp, 20h
0x180009752  pop     rbp
0x180009753  retn
0x180009755  push    rbp
0x180009757  sub     rsp, 20h
0x18000975b  mov     rbp, rdx
0x18000975e  cmp     dword ptr [rbp+118h], 1
0x180009765  ja      short loc_180009771
0x180009767  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
