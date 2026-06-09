# __DllMainCRTStartup

- ea: `0x1800017a4`
- end: `0x1800019b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001760`

## callees

- `0x180001530`
- `0x1800017a4`
- `0x180001d1b`
- `0x18000d028`
- `0x18000f630`

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
  if ( (_DWORD)fdwReason || dword_180017420 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180017424 = 1;
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
            if ( dword_180017424 )
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
0x1800017a4  mov     [rsp+lpvReserved], r8
0x1800017a9  mov     [rsp+arg_8], edx
0x1800017ad  mov     [rsp+arg_0], rcx
0x1800017b2  push    rbx
0x1800017b3  push    rsi
0x1800017b4  push    rdi
0x1800017b5  sub     rsp, 0F0h
0x1800017bc  mov     edi, edx
0x1800017be  mov     rsi, rcx
0x1800017c1  mov     ebx, 1
0x1800017c6  cmp     edx, ebx
0x1800017c8  ja      short loc_1800017D0
0x1800017ca  mov     cs:__native_dllmain_reason, edx
0x1800017d0  test    edx, edx
0x1800017d2  jnz     short loc_1800017E7
0x1800017d4  cmp     cs:dword_180017420, edx
0x1800017da  jnz     short loc_1800017E7
0x1800017dc  xor     ebx, ebx
0x1800017de  mov     [rsp+108h+var_E8], ebx
0x1800017e2  jmp     loc_180001994
0x1800017e7  lea     eax, [rdx-1]
0x1800017ea  cmp     eax, 1
0x1800017ed  ja      loc_180001874
0x1800017f3  mov     rax, cs:_pRawDllMain
0x1800017fa  test    rax, rax
0x1800017fd  jz      short loc_180001835
0x1800017ff  cmp     edx, 1
0x180001802  jnz     short loc_18000180A
0x180001804  mov     cs:dword_180017424, edx
0x18000180a  mov     r8, [rsp+108h+lpvReserved]
0x180001812  call    cs:__guard_dispatch_icall_fptr
0x180001818  mov     ebx, eax
0x18000181a  mov     [rsp+108h+var_E8], eax
0x18000181e  jmp     short loc_180001835
0x180001820  xor     ebx, ebx
0x180001822  mov     [rsp+108h+var_E8], ebx
0x180001826  mov     edi, [rsp+108h+arg_8]
0x18000182d  mov     rsi, [rsp+108h+arg_0]
0x180001835  test    ebx, ebx
0x180001837  jz      loc_180001994
0x18000183d  mov     r8, [rsp+108h+lpvReserved]
0x180001845  mov     edx, edi
0x180001847  mov     rcx, rsi
0x18000184a  call    _CRT_INIT
0x18000184f  mov     ebx, eax
0x180001851  mov     [rsp+108h+var_E8], eax
0x180001855  jmp     short loc_18000186C
0x180001857  xor     ebx, ebx
0x180001859  mov     [rsp+108h+var_E8], ebx
0x18000185d  mov     edi, [rsp+108h+arg_8]
0x180001864  mov     rsi, [rsp+108h+arg_0]
0x18000186c  test    ebx, ebx
0x18000186e  jz      loc_180001994
0x180001874  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000187c  mov     edx, edi; fdwReason
0x18000187e  mov     rcx, rsi; hinstDLL
0x180001881  call    DllMain
0x180001886  mov     ebx, eax
0x180001888  mov     [rsp+108h+var_E8], eax
0x18000188c  jmp     short loc_1800018A3
0x18000188e  xor     ebx, ebx
0x180001890  mov     [rsp+108h+var_E8], ebx
0x180001894  mov     edi, [rsp+108h+arg_8]
0x18000189b  mov     rsi, [rsp+108h+arg_0]
0x1800018a3  cmp     edi, 1
0x1800018a6  jnz     short loc_18000191F
0x1800018a8  test    ebx, ebx
0x1800018aa  jnz     short loc_18000191F
0x1800018ac  xor     r8d, r8d; lpvReserved
0x1800018af  xor     edx, edx; fdwReason
0x1800018b1  mov     rcx, rsi; hinstDLL
0x1800018b4  call    DllMain
0x1800018b9  jmp     short loc_1800018CE
0x1800018bb  mov     edi, [rsp+108h+arg_8]
0x1800018c2  mov     rsi, [rsp+108h+arg_0]
0x1800018ca  mov     ebx, [rsp+108h+var_E8]
0x1800018ce  xor     r8d, r8d
0x1800018d1  xor     edx, edx
0x1800018d3  mov     rcx, rsi
0x1800018d6  call    _CRT_INIT
0x1800018db  jmp     short loc_1800018F0
0x1800018dd  mov     edi, [rsp+108h+arg_8]
0x1800018e4  mov     rsi, [rsp+108h+arg_0]
0x1800018ec  mov     ebx, [rsp+108h+var_E8]
0x1800018f0  mov     rax, cs:_pRawDllMain
0x1800018f7  test    rax, rax
0x1800018fa  jz      short loc_18000191F
0x1800018fc  xor     r8d, r8d
0x1800018ff  xor     edx, edx
0x180001901  mov     rcx, rsi
0x180001904  call    cs:__guard_dispatch_icall_fptr
0x18000190a  jmp     short loc_18000191F
0x18000190c  mov     edi, [rsp+108h+arg_8]
0x180001913  mov     rsi, [rsp+108h+arg_0]
0x18000191b  mov     ebx, [rsp+108h+var_E8]
0x18000191f  test    edi, edi
0x180001921  jz      short loc_180001928
0x180001923  cmp     edi, 3
0x180001926  jnz     short loc_180001994
0x180001928  mov     r8, [rsp+108h+lpvReserved]
0x180001930  mov     edx, edi
0x180001932  mov     rcx, rsi
0x180001935  call    _CRT_INIT
0x18000193a  mov     ebx, eax
0x18000193c  mov     [rsp+108h+var_E8], eax
0x180001940  jmp     short loc_180001957
0x180001942  xor     ebx, ebx
0x180001944  mov     [rsp+108h+var_E8], ebx
0x180001948  mov     edi, [rsp+108h+arg_8]
0x18000194f  mov     rsi, [rsp+108h+arg_0]
0x180001957  mov     rax, cs:_pRawDllMain
0x18000195e  test    rax, rax
0x180001961  jz      short loc_180001994
0x180001963  cmp     cs:dword_180017424, 0
0x18000196a  jz      short loc_180001994
0x18000196c  mov     r8, [rsp+108h+lpvReserved]
0x180001974  mov     edx, edi
0x180001976  mov     rcx, rsi
0x180001979  call    cs:__guard_dispatch_icall_fptr
0x18000197f  mov     ebx, eax
0x180001981  mov     [rsp+108h+var_E8], eax
0x180001985  jmp     short loc_180001994
0x180001987  xor     ebx, ebx
0x180001989  mov     [rsp+108h+var_E8], ebx
0x18000198d  mov     edi, [rsp+108h+arg_8]
0x180001994  cmp     edi, 1
0x180001997  ja      short loc_1800019A3
0x180001999  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800019a3  mov     eax, ebx
0x1800019a5  add     rsp, 0F0h
0x1800019ac  pop     rdi
0x1800019ad  pop     rsi
0x1800019ae  pop     rbx
0x1800019af  retn
0x18000f712  push    rbp
0x18000f714  sub     rsp, 20h
0x18000f718  mov     rbp, rdx
0x18000f71b  mov     rax, [rcx]
0x18000f71e  mov     edx, [rax]
0x18000f720  mov     [rbp+0A8h], rcx
0x18000f727  mov     [rbp+28h], edx
0x18000f72a  mov     eax, [rbp+28h]
0x18000f72d  cmp     eax, 0E06D7363h
0x18000f732  jnz     short loc_18000F748
0x18000f734  mov     rdx, [rbp+0A8h]
0x18000f73b  mov     ecx, [rbp+28h]
0x18000f73e  call    _XcptFilter_0
0x18000f743  mov     [rbp+30h], eax
0x18000f746  jmp     short loc_18000F74F
0x18000f748  mov     dword ptr [rbp+30h], 0
0x18000f74f  mov     eax, [rbp+30h]
0x18000f752  add     rsp, 20h
0x18000f756  pop     rbp
0x18000f757  retn
0x18000f759  push    rbp
0x18000f75b  sub     rsp, 20h
0x18000f75f  mov     rbp, rdx
0x18000f762  mov     rax, [rcx]
0x18000f765  mov     edx, [rax]
0x18000f767  mov     [rbp+0B0h], rcx
0x18000f76e  mov     [rbp+38h], edx
0x18000f771  mov     eax, [rbp+38h]
0x18000f774  cmp     eax, 0E06D7363h
0x18000f779  jnz     short loc_18000F78F
0x18000f77b  mov     rdx, [rbp+0B0h]
0x18000f782  mov     ecx, [rbp+38h]
0x18000f785  call    _XcptFilter_0
0x18000f78a  mov     [rbp+40h], eax
0x18000f78d  jmp     short loc_18000F796
0x18000f78f  mov     dword ptr [rbp+40h], 0
0x18000f796  mov     eax, [rbp+40h]
0x18000f799  add     rsp, 20h
0x18000f79d  pop     rbp
0x18000f79e  retn
0x18000f7a0  push    rbp
0x18000f7a2  sub     rsp, 20h
0x18000f7a6  mov     rbp, rdx
0x18000f7a9  mov     rax, [rcx]
0x18000f7ac  mov     edx, [rax]
0x18000f7ae  mov     [rbp+0B8h], rcx
0x18000f7b5  mov     [rbp+48h], edx
0x18000f7b8  mov     eax, [rbp+48h]
0x18000f7bb  cmp     eax, 0E06D7363h
0x18000f7c0  jnz     short loc_18000F7D6
0x18000f7c2  mov     rdx, [rbp+0B8h]
0x18000f7c9  mov     ecx, [rbp+48h]
0x18000f7cc  call    _XcptFilter_0
0x18000f7d1  mov     [rbp+50h], eax
0x18000f7d4  jmp     short loc_18000F7DD
0x18000f7d6  mov     dword ptr [rbp+50h], 0
0x18000f7dd  mov     eax, [rbp+50h]
0x18000f7e0  add     rsp, 20h
0x18000f7e4  pop     rbp
0x18000f7e5  retn
0x18000f7e7  push    rbp
0x18000f7e9  sub     rsp, 20h
0x18000f7ed  mov     rbp, rdx
0x18000f7f0  mov     rax, [rcx]
0x18000f7f3  mov     edx, [rax]
0x18000f7f5  mov     [rbp+0C0h], rcx
0x18000f7fc  mov     [rbp+58h], edx
0x18000f7ff  mov     eax, [rbp+58h]
0x18000f802  cmp     eax, 0E06D7363h
0x18000f807  jnz     short loc_18000F81D
0x18000f809  mov     rdx, [rbp+0C0h]
0x18000f810  mov     ecx, [rbp+58h]
0x18000f813  call    _XcptFilter_0
0x18000f818  mov     [rbp+60h], eax
0x18000f81b  jmp     short loc_18000F824
0x18000f81d  mov     dword ptr [rbp+60h], 0
0x18000f824  mov     eax, [rbp+60h]
0x18000f827  add     rsp, 20h
0x18000f82b  pop     rbp
0x18000f82c  retn
0x18000f82e  push    rbp
0x18000f830  sub     rsp, 20h
0x18000f834  mov     rbp, rdx
0x18000f837  mov     rax, [rcx]
0x18000f83a  mov     edx, [rax]
0x18000f83c  mov     [rbp+0C8h], rcx
0x18000f843  mov     [rbp+68h], edx
0x18000f846  mov     eax, [rbp+68h]
0x18000f849  cmp     eax, 0E06D7363h
0x18000f84e  jnz     short loc_18000F864
0x18000f850  mov     rdx, [rbp+0C8h]
0x18000f857  mov     ecx, [rbp+68h]
0x18000f85a  call    _XcptFilter_0
0x18000f85f  mov     [rbp+70h], eax
0x18000f862  jmp     short loc_18000F86B
0x18000f864  mov     dword ptr [rbp+70h], 0
0x18000f86b  mov     eax, [rbp+70h]
0x18000f86e  add     rsp, 20h
0x18000f872  pop     rbp
0x18000f873  retn
0x18000f875  push    rbp
0x18000f877  sub     rsp, 20h
0x18000f87b  mov     rbp, rdx
0x18000f87e  mov     rax, [rcx]
0x18000f881  mov     edx, [rax]
0x18000f883  mov     [rbp+0D0h], rcx
0x18000f88a  mov     [rbp+78h], edx
0x18000f88d  mov     eax, [rbp+78h]
0x18000f890  cmp     eax, 0E06D7363h
0x18000f895  jnz     short loc_18000F8AE
0x18000f897  mov     rdx, [rbp+0D0h]
0x18000f89e  mov     ecx, [rbp+78h]
0x18000f8a1  call    _XcptFilter_0
0x18000f8a6  mov     [rbp+80h], eax
0x18000f8ac  jmp     short loc_18000F8B8
0x18000f8ae  mov     dword ptr [rbp+80h], 0
0x18000f8b8  mov     eax, [rbp+80h]
0x18000f8be  add     rsp, 20h
0x18000f8c2  pop     rbp
0x18000f8c3  retn
0x18000f8c5  push    rbp
0x18000f8c7  sub     rsp, 20h
0x18000f8cb  mov     rbp, rdx
0x18000f8ce  mov     rax, [rcx]
0x18000f8d1  mov     edx, [rax]
0x18000f8d3  mov     [rbp+0D8h], rcx
0x18000f8da  mov     [rbp+88h], edx
0x18000f8e0  mov     eax, [rbp+88h]
0x18000f8e6  cmp     eax, 0E06D7363h
0x18000f8eb  jnz     short loc_18000F907
0x18000f8ed  mov     rdx, [rbp+0D8h]
0x18000f8f4  mov     ecx, [rbp+88h]
0x18000f8fa  call    _XcptFilter_0
0x18000f8ff  mov     [rbp+90h], eax
0x18000f905  jmp     short loc_18000F911
0x18000f907  mov     dword ptr [rbp+90h], 0
0x18000f911  mov     eax, [rbp+90h]
0x18000f917  add     rsp, 20h
0x18000f91b  pop     rbp
0x18000f91c  retn
0x18000f91e  push    rbp
0x18000f920  sub     rsp, 20h
0x18000f924  mov     rbp, rdx
0x18000f927  mov     rax, [rcx]
0x18000f92a  mov     edx, [rax]
0x18000f92c  mov     [rbp+0E0h], rcx
0x18000f933  mov     [rbp+98h], edx
0x18000f939  mov     eax, [rbp+98h]
0x18000f93f  cmp     eax, 0E06D7363h
0x18000f944  jnz     short loc_18000F960
0x18000f946  mov     rdx, [rbp+0E0h]
0x18000f94d  mov     ecx, [rbp+98h]
0x18000f953  call    _XcptFilter_0
0x18000f958  mov     [rbp+0A0h], eax
0x18000f95e  jmp     short loc_18000F96A
0x18000f960  mov     dword ptr [rbp+0A0h], 0
0x18000f96a  mov     eax, [rbp+0A0h]
0x18000f970  add     rsp, 20h
0x18000f974  pop     rbp
0x18000f975  retn
0x18000f977  push    rbp
0x18000f979  sub     rsp, 20h
0x18000f97d  mov     rbp, rdx
0x18000f980  cmp     dword ptr [rbp+118h], 1
0x18000f987  ja      short loc_18000F993
0x18000f989  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
