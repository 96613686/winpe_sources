# __DllMainCRTStartup

- ea: `0x1800022b4`
- end: `0x1800024c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002270`

## callees

- `0x180002040`
- `0x1800022b4`
- `0x1800024c6`
- `0x180002ef0`
- `0x18000e9d0`

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
  if ( (_DWORD)fdwReason || dword_18001F2E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001F2E4 = 1;
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
            if ( dword_18001F2E4 )
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
0x1800022b4  mov     [rsp+lpvReserved], r8
0x1800022b9  mov     [rsp+arg_8], edx
0x1800022bd  mov     [rsp+arg_0], rcx
0x1800022c2  push    rbx
0x1800022c3  push    rsi
0x1800022c4  push    rdi
0x1800022c5  sub     rsp, 0F0h
0x1800022cc  mov     edi, edx
0x1800022ce  mov     rsi, rcx
0x1800022d1  mov     ebx, 1
0x1800022d6  cmp     edx, ebx
0x1800022d8  ja      short loc_1800022E0
0x1800022da  mov     cs:__native_dllmain_reason, edx
0x1800022e0  test    edx, edx
0x1800022e2  jnz     short loc_1800022F7
0x1800022e4  cmp     cs:dword_18001F2E0, edx
0x1800022ea  jnz     short loc_1800022F7
0x1800022ec  xor     ebx, ebx
0x1800022ee  mov     [rsp+108h+var_E8], ebx
0x1800022f2  jmp     loc_1800024A4
0x1800022f7  lea     eax, [rdx-1]
0x1800022fa  cmp     eax, 1
0x1800022fd  ja      loc_180002384
0x180002303  mov     rax, cs:_pRawDllMain
0x18000230a  test    rax, rax
0x18000230d  jz      short loc_180002345
0x18000230f  cmp     edx, 1
0x180002312  jnz     short loc_18000231A
0x180002314  mov     cs:dword_18001F2E4, edx
0x18000231a  mov     r8, [rsp+108h+lpvReserved]
0x180002322  call    cs:__guard_dispatch_icall_fptr
0x180002328  mov     ebx, eax
0x18000232a  mov     [rsp+108h+var_E8], eax
0x18000232e  jmp     short loc_180002345
0x180002330  xor     ebx, ebx
0x180002332  mov     [rsp+108h+var_E8], ebx
0x180002336  mov     edi, [rsp+108h+arg_8]
0x18000233d  mov     rsi, [rsp+108h+arg_0]
0x180002345  test    ebx, ebx
0x180002347  jz      loc_1800024A4
0x18000234d  mov     r8, [rsp+108h+lpvReserved]
0x180002355  mov     edx, edi
0x180002357  mov     rcx, rsi
0x18000235a  call    _CRT_INIT
0x18000235f  mov     ebx, eax
0x180002361  mov     [rsp+108h+var_E8], eax
0x180002365  jmp     short loc_18000237C
0x180002367  xor     ebx, ebx
0x180002369  mov     [rsp+108h+var_E8], ebx
0x18000236d  mov     edi, [rsp+108h+arg_8]
0x180002374  mov     rsi, [rsp+108h+arg_0]
0x18000237c  test    ebx, ebx
0x18000237e  jz      loc_1800024A4
0x180002384  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000238c  mov     edx, edi; fdwReason
0x18000238e  mov     rcx, rsi; hinstDLL
0x180002391  call    DllMain
0x180002396  mov     ebx, eax
0x180002398  mov     [rsp+108h+var_E8], eax
0x18000239c  jmp     short loc_1800023B3
0x18000239e  xor     ebx, ebx
0x1800023a0  mov     [rsp+108h+var_E8], ebx
0x1800023a4  mov     edi, [rsp+108h+arg_8]
0x1800023ab  mov     rsi, [rsp+108h+arg_0]
0x1800023b3  cmp     edi, 1
0x1800023b6  jnz     short loc_18000242F
0x1800023b8  test    ebx, ebx
0x1800023ba  jnz     short loc_18000242F
0x1800023bc  xor     r8d, r8d; lpvReserved
0x1800023bf  xor     edx, edx; fdwReason
0x1800023c1  mov     rcx, rsi; hinstDLL
0x1800023c4  call    DllMain
0x1800023c9  jmp     short loc_1800023DE
0x1800023cb  mov     edi, [rsp+108h+arg_8]
0x1800023d2  mov     rsi, [rsp+108h+arg_0]
0x1800023da  mov     ebx, [rsp+108h+var_E8]
0x1800023de  xor     r8d, r8d
0x1800023e1  xor     edx, edx
0x1800023e3  mov     rcx, rsi
0x1800023e6  call    _CRT_INIT
0x1800023eb  jmp     short loc_180002400
0x1800023ed  mov     edi, [rsp+108h+arg_8]
0x1800023f4  mov     rsi, [rsp+108h+arg_0]
0x1800023fc  mov     ebx, [rsp+108h+var_E8]
0x180002400  mov     rax, cs:_pRawDllMain
0x180002407  test    rax, rax
0x18000240a  jz      short loc_18000242F
0x18000240c  xor     r8d, r8d
0x18000240f  xor     edx, edx
0x180002411  mov     rcx, rsi
0x180002414  call    cs:__guard_dispatch_icall_fptr
0x18000241a  jmp     short loc_18000242F
0x18000241c  mov     edi, [rsp+108h+arg_8]
0x180002423  mov     rsi, [rsp+108h+arg_0]
0x18000242b  mov     ebx, [rsp+108h+var_E8]
0x18000242f  test    edi, edi
0x180002431  jz      short loc_180002438
0x180002433  cmp     edi, 3
0x180002436  jnz     short loc_1800024A4
0x180002438  mov     r8, [rsp+108h+lpvReserved]
0x180002440  mov     edx, edi
0x180002442  mov     rcx, rsi
0x180002445  call    _CRT_INIT
0x18000244a  mov     ebx, eax
0x18000244c  mov     [rsp+108h+var_E8], eax
0x180002450  jmp     short loc_180002467
0x180002452  xor     ebx, ebx
0x180002454  mov     [rsp+108h+var_E8], ebx
0x180002458  mov     edi, [rsp+108h+arg_8]
0x18000245f  mov     rsi, [rsp+108h+arg_0]
0x180002467  mov     rax, cs:_pRawDllMain
0x18000246e  test    rax, rax
0x180002471  jz      short loc_1800024A4
0x180002473  cmp     cs:dword_18001F2E4, 0
0x18000247a  jz      short loc_1800024A4
0x18000247c  mov     r8, [rsp+108h+lpvReserved]
0x180002484  mov     edx, edi
0x180002486  mov     rcx, rsi
0x180002489  call    cs:__guard_dispatch_icall_fptr
0x18000248f  mov     ebx, eax
0x180002491  mov     [rsp+108h+var_E8], eax
0x180002495  jmp     short loc_1800024A4
0x180002497  xor     ebx, ebx
0x180002499  mov     [rsp+108h+var_E8], ebx
0x18000249d  mov     edi, [rsp+108h+arg_8]
0x1800024a4  cmp     edi, 1
0x1800024a7  ja      short loc_1800024B3
0x1800024a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800024b3  mov     eax, ebx
0x1800024b5  add     rsp, 0F0h
0x1800024bc  pop     rdi
0x1800024bd  pop     rsi
0x1800024be  pop     rbx
0x1800024bf  retn
0x18000eaa3  push    rbp
0x18000eaa5  sub     rsp, 20h
0x18000eaa9  mov     rbp, rdx
0x18000eaac  mov     rax, [rcx]
0x18000eaaf  mov     edx, [rax]
0x18000eab1  mov     [rbp+0A8h], rcx
0x18000eab8  mov     [rbp+28h], edx
0x18000eabb  mov     eax, [rbp+28h]
0x18000eabe  cmp     eax, 0E06D7363h
0x18000eac3  jnz     short loc_18000EAD9
0x18000eac5  mov     rdx, [rbp+0A8h]
0x18000eacc  mov     ecx, [rbp+28h]
0x18000eacf  call    _XcptFilter_0
0x18000ead4  mov     [rbp+30h], eax
0x18000ead7  jmp     short loc_18000EAE0
0x18000ead9  mov     dword ptr [rbp+30h], 0
0x18000eae0  mov     eax, [rbp+30h]
0x18000eae3  add     rsp, 20h
0x18000eae7  pop     rbp
0x18000eae8  retn
0x18000eaea  push    rbp
0x18000eaec  sub     rsp, 20h
0x18000eaf0  mov     rbp, rdx
0x18000eaf3  mov     rax, [rcx]
0x18000eaf6  mov     edx, [rax]
0x18000eaf8  mov     [rbp+0B0h], rcx
0x18000eaff  mov     [rbp+38h], edx
0x18000eb02  mov     eax, [rbp+38h]
0x18000eb05  cmp     eax, 0E06D7363h
0x18000eb0a  jnz     short loc_18000EB20
0x18000eb0c  mov     rdx, [rbp+0B0h]
0x18000eb13  mov     ecx, [rbp+38h]
0x18000eb16  call    _XcptFilter_0
0x18000eb1b  mov     [rbp+40h], eax
0x18000eb1e  jmp     short loc_18000EB27
0x18000eb20  mov     dword ptr [rbp+40h], 0
0x18000eb27  mov     eax, [rbp+40h]
0x18000eb2a  add     rsp, 20h
0x18000eb2e  pop     rbp
0x18000eb2f  retn
0x18000eb31  push    rbp
0x18000eb33  sub     rsp, 20h
0x18000eb37  mov     rbp, rdx
0x18000eb3a  mov     rax, [rcx]
0x18000eb3d  mov     edx, [rax]
0x18000eb3f  mov     [rbp+0B8h], rcx
0x18000eb46  mov     [rbp+48h], edx
0x18000eb49  mov     eax, [rbp+48h]
0x18000eb4c  cmp     eax, 0E06D7363h
0x18000eb51  jnz     short loc_18000EB67
0x18000eb53  mov     rdx, [rbp+0B8h]
0x18000eb5a  mov     ecx, [rbp+48h]
0x18000eb5d  call    _XcptFilter_0
0x18000eb62  mov     [rbp+50h], eax
0x18000eb65  jmp     short loc_18000EB6E
0x18000eb67  mov     dword ptr [rbp+50h], 0
0x18000eb6e  mov     eax, [rbp+50h]
0x18000eb71  add     rsp, 20h
0x18000eb75  pop     rbp
0x18000eb76  retn
0x18000eb78  push    rbp
0x18000eb7a  sub     rsp, 20h
0x18000eb7e  mov     rbp, rdx
0x18000eb81  mov     rax, [rcx]
0x18000eb84  mov     edx, [rax]
0x18000eb86  mov     [rbp+0C0h], rcx
0x18000eb8d  mov     [rbp+58h], edx
0x18000eb90  mov     eax, [rbp+58h]
0x18000eb93  cmp     eax, 0E06D7363h
0x18000eb98  jnz     short loc_18000EBAE
0x18000eb9a  mov     rdx, [rbp+0C0h]
0x18000eba1  mov     ecx, [rbp+58h]
0x18000eba4  call    _XcptFilter_0
0x18000eba9  mov     [rbp+60h], eax
0x18000ebac  jmp     short loc_18000EBB5
0x18000ebae  mov     dword ptr [rbp+60h], 0
0x18000ebb5  mov     eax, [rbp+60h]
0x18000ebb8  add     rsp, 20h
0x18000ebbc  pop     rbp
0x18000ebbd  retn
0x18000ebbf  push    rbp
0x18000ebc1  sub     rsp, 20h
0x18000ebc5  mov     rbp, rdx
0x18000ebc8  mov     rax, [rcx]
0x18000ebcb  mov     edx, [rax]
0x18000ebcd  mov     [rbp+0C8h], rcx
0x18000ebd4  mov     [rbp+68h], edx
0x18000ebd7  mov     eax, [rbp+68h]
0x18000ebda  cmp     eax, 0E06D7363h
0x18000ebdf  jnz     short loc_18000EBF5
0x18000ebe1  mov     rdx, [rbp+0C8h]
0x18000ebe8  mov     ecx, [rbp+68h]
0x18000ebeb  call    _XcptFilter_0
0x18000ebf0  mov     [rbp+70h], eax
0x18000ebf3  jmp     short loc_18000EBFC
0x18000ebf5  mov     dword ptr [rbp+70h], 0
0x18000ebfc  mov     eax, [rbp+70h]
0x18000ebff  add     rsp, 20h
0x18000ec03  pop     rbp
0x18000ec04  retn
0x18000ec06  push    rbp
0x18000ec08  sub     rsp, 20h
0x18000ec0c  mov     rbp, rdx
0x18000ec0f  mov     rax, [rcx]
0x18000ec12  mov     edx, [rax]
0x18000ec14  mov     [rbp+0D0h], rcx
0x18000ec1b  mov     [rbp+78h], edx
0x18000ec1e  mov     eax, [rbp+78h]
0x18000ec21  cmp     eax, 0E06D7363h
0x18000ec26  jnz     short loc_18000EC3F
0x18000ec28  mov     rdx, [rbp+0D0h]
0x18000ec2f  mov     ecx, [rbp+78h]
0x18000ec32  call    _XcptFilter_0
0x18000ec37  mov     [rbp+80h], eax
0x18000ec3d  jmp     short loc_18000EC49
0x18000ec3f  mov     dword ptr [rbp+80h], 0
0x18000ec49  mov     eax, [rbp+80h]
0x18000ec4f  add     rsp, 20h
0x18000ec53  pop     rbp
0x18000ec54  retn
0x18000ec56  push    rbp
0x18000ec58  sub     rsp, 20h
0x18000ec5c  mov     rbp, rdx
0x18000ec5f  mov     rax, [rcx]
0x18000ec62  mov     edx, [rax]
0x18000ec64  mov     [rbp+0D8h], rcx
0x18000ec6b  mov     [rbp+88h], edx
0x18000ec71  mov     eax, [rbp+88h]
0x18000ec77  cmp     eax, 0E06D7363h
0x18000ec7c  jnz     short loc_18000EC98
0x18000ec7e  mov     rdx, [rbp+0D8h]
0x18000ec85  mov     ecx, [rbp+88h]
0x18000ec8b  call    _XcptFilter_0
0x18000ec90  mov     [rbp+90h], eax
0x18000ec96  jmp     short loc_18000ECA2
0x18000ec98  mov     dword ptr [rbp+90h], 0
0x18000eca2  mov     eax, [rbp+90h]
0x18000eca8  add     rsp, 20h
0x18000ecac  pop     rbp
0x18000ecad  retn
0x18000ecaf  push    rbp
0x18000ecb1  sub     rsp, 20h
0x18000ecb5  mov     rbp, rdx
0x18000ecb8  mov     rax, [rcx]
0x18000ecbb  mov     edx, [rax]
0x18000ecbd  mov     [rbp+0E0h], rcx
0x18000ecc4  mov     [rbp+98h], edx
0x18000ecca  mov     eax, [rbp+98h]
0x18000ecd0  cmp     eax, 0E06D7363h
0x18000ecd5  jnz     short loc_18000ECF1
0x18000ecd7  mov     rdx, [rbp+0E0h]
0x18000ecde  mov     ecx, [rbp+98h]
0x18000ece4  call    _XcptFilter_0
0x18000ece9  mov     [rbp+0A0h], eax
0x18000ecef  jmp     short loc_18000ECFB
0x18000ecf1  mov     dword ptr [rbp+0A0h], 0
0x18000ecfb  mov     eax, [rbp+0A0h]
0x18000ed01  add     rsp, 20h
0x18000ed05  pop     rbp
0x18000ed06  retn
0x18000ed08  push    rbp
0x18000ed0a  sub     rsp, 20h
0x18000ed0e  mov     rbp, rdx
0x18000ed11  cmp     dword ptr [rbp+118h], 1
0x18000ed18  ja      short loc_18000ED24
0x18000ed1a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
