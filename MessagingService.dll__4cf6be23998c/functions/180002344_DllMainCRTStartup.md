# __DllMainCRTStartup

- ea: `0x180002344`
- end: `0x180002550`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002300`

## callees

- `0x1800020d0`
- `0x180002344`
- `0x180002756`
- `0x180002e70`
- `0x18000aac0`

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
  if ( (_DWORD)fdwReason || dword_18001336C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180013370 = 1;
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
            if ( dword_180013370 )
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
0x180002344  mov     [rsp+lpvReserved], r8
0x180002349  mov     [rsp+arg_8], edx
0x18000234d  mov     [rsp+arg_0], rcx
0x180002352  push    rbx
0x180002353  push    rsi
0x180002354  push    rdi
0x180002355  sub     rsp, 0F0h
0x18000235c  mov     edi, edx
0x18000235e  mov     rsi, rcx
0x180002361  mov     ebx, 1
0x180002366  cmp     edx, ebx
0x180002368  ja      short loc_180002370
0x18000236a  mov     cs:__native_dllmain_reason, edx
0x180002370  test    edx, edx
0x180002372  jnz     short loc_180002387
0x180002374  cmp     cs:dword_18001336C, edx
0x18000237a  jnz     short loc_180002387
0x18000237c  xor     ebx, ebx
0x18000237e  mov     [rsp+108h+var_E8], ebx
0x180002382  jmp     loc_180002534
0x180002387  lea     eax, [rdx-1]
0x18000238a  cmp     eax, 1
0x18000238d  ja      loc_180002414
0x180002393  mov     rax, cs:_pRawDllMain
0x18000239a  test    rax, rax
0x18000239d  jz      short loc_1800023D5
0x18000239f  cmp     edx, 1
0x1800023a2  jnz     short loc_1800023AA
0x1800023a4  mov     cs:dword_180013370, edx
0x1800023aa  mov     r8, [rsp+108h+lpvReserved]
0x1800023b2  call    cs:__guard_dispatch_icall_fptr
0x1800023b8  mov     ebx, eax
0x1800023ba  mov     [rsp+108h+var_E8], eax
0x1800023be  jmp     short loc_1800023D5
0x1800023c0  xor     ebx, ebx
0x1800023c2  mov     [rsp+108h+var_E8], ebx
0x1800023c6  mov     edi, [rsp+108h+arg_8]
0x1800023cd  mov     rsi, [rsp+108h+arg_0]
0x1800023d5  test    ebx, ebx
0x1800023d7  jz      loc_180002534
0x1800023dd  mov     r8, [rsp+108h+lpvReserved]
0x1800023e5  mov     edx, edi
0x1800023e7  mov     rcx, rsi
0x1800023ea  call    _CRT_INIT
0x1800023ef  mov     ebx, eax
0x1800023f1  mov     [rsp+108h+var_E8], eax
0x1800023f5  jmp     short loc_18000240C
0x1800023f7  xor     ebx, ebx
0x1800023f9  mov     [rsp+108h+var_E8], ebx
0x1800023fd  mov     edi, [rsp+108h+arg_8]
0x180002404  mov     rsi, [rsp+108h+arg_0]
0x18000240c  test    ebx, ebx
0x18000240e  jz      loc_180002534
0x180002414  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000241c  mov     edx, edi; fdwReason
0x18000241e  mov     rcx, rsi; hinstDLL
0x180002421  call    DllMain
0x180002426  mov     ebx, eax
0x180002428  mov     [rsp+108h+var_E8], eax
0x18000242c  jmp     short loc_180002443
0x18000242e  xor     ebx, ebx
0x180002430  mov     [rsp+108h+var_E8], ebx
0x180002434  mov     edi, [rsp+108h+arg_8]
0x18000243b  mov     rsi, [rsp+108h+arg_0]
0x180002443  cmp     edi, 1
0x180002446  jnz     short loc_1800024BF
0x180002448  test    ebx, ebx
0x18000244a  jnz     short loc_1800024BF
0x18000244c  xor     r8d, r8d; lpvReserved
0x18000244f  xor     edx, edx; fdwReason
0x180002451  mov     rcx, rsi; hinstDLL
0x180002454  call    DllMain
0x180002459  jmp     short loc_18000246E
0x18000245b  mov     edi, [rsp+108h+arg_8]
0x180002462  mov     rsi, [rsp+108h+arg_0]
0x18000246a  mov     ebx, [rsp+108h+var_E8]
0x18000246e  xor     r8d, r8d
0x180002471  xor     edx, edx
0x180002473  mov     rcx, rsi
0x180002476  call    _CRT_INIT
0x18000247b  jmp     short loc_180002490
0x18000247d  mov     edi, [rsp+108h+arg_8]
0x180002484  mov     rsi, [rsp+108h+arg_0]
0x18000248c  mov     ebx, [rsp+108h+var_E8]
0x180002490  mov     rax, cs:_pRawDllMain
0x180002497  test    rax, rax
0x18000249a  jz      short loc_1800024BF
0x18000249c  xor     r8d, r8d
0x18000249f  xor     edx, edx
0x1800024a1  mov     rcx, rsi
0x1800024a4  call    cs:__guard_dispatch_icall_fptr
0x1800024aa  jmp     short loc_1800024BF
0x1800024ac  mov     edi, [rsp+108h+arg_8]
0x1800024b3  mov     rsi, [rsp+108h+arg_0]
0x1800024bb  mov     ebx, [rsp+108h+var_E8]
0x1800024bf  test    edi, edi
0x1800024c1  jz      short loc_1800024C8
0x1800024c3  cmp     edi, 3
0x1800024c6  jnz     short loc_180002534
0x1800024c8  mov     r8, [rsp+108h+lpvReserved]
0x1800024d0  mov     edx, edi
0x1800024d2  mov     rcx, rsi
0x1800024d5  call    _CRT_INIT
0x1800024da  mov     ebx, eax
0x1800024dc  mov     [rsp+108h+var_E8], eax
0x1800024e0  jmp     short loc_1800024F7
0x1800024e2  xor     ebx, ebx
0x1800024e4  mov     [rsp+108h+var_E8], ebx
0x1800024e8  mov     edi, [rsp+108h+arg_8]
0x1800024ef  mov     rsi, [rsp+108h+arg_0]
0x1800024f7  mov     rax, cs:_pRawDllMain
0x1800024fe  test    rax, rax
0x180002501  jz      short loc_180002534
0x180002503  cmp     cs:dword_180013370, 0
0x18000250a  jz      short loc_180002534
0x18000250c  mov     r8, [rsp+108h+lpvReserved]
0x180002514  mov     edx, edi
0x180002516  mov     rcx, rsi
0x180002519  call    cs:__guard_dispatch_icall_fptr
0x18000251f  mov     ebx, eax
0x180002521  mov     [rsp+108h+var_E8], eax
0x180002525  jmp     short loc_180002534
0x180002527  xor     ebx, ebx
0x180002529  mov     [rsp+108h+var_E8], ebx
0x18000252d  mov     edi, [rsp+108h+arg_8]
0x180002534  cmp     edi, 1
0x180002537  ja      short loc_180002543
0x180002539  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002543  mov     eax, ebx
0x180002545  add     rsp, 0F0h
0x18000254c  pop     rdi
0x18000254d  pop     rsi
0x18000254e  pop     rbx
0x18000254f  retn
0x18000ab6f  push    rbp
0x18000ab71  sub     rsp, 20h
0x18000ab75  mov     rbp, rdx
0x18000ab78  mov     rax, [rcx]
0x18000ab7b  mov     edx, [rax]
0x18000ab7d  mov     [rbp+0A8h], rcx
0x18000ab84  mov     [rbp+28h], edx
0x18000ab87  mov     eax, [rbp+28h]
0x18000ab8a  cmp     eax, 0E06D7363h
0x18000ab8f  jnz     short loc_18000ABA5
0x18000ab91  mov     rdx, [rbp+0A8h]
0x18000ab98  mov     ecx, [rbp+28h]
0x18000ab9b  call    _XcptFilter_0
0x18000aba0  mov     [rbp+30h], eax
0x18000aba3  jmp     short loc_18000ABAC
0x18000aba5  mov     dword ptr [rbp+30h], 0
0x18000abac  mov     eax, [rbp+30h]
0x18000abaf  add     rsp, 20h
0x18000abb3  pop     rbp
0x18000abb4  retn
0x18000abb6  push    rbp
0x18000abb8  sub     rsp, 20h
0x18000abbc  mov     rbp, rdx
0x18000abbf  mov     rax, [rcx]
0x18000abc2  mov     edx, [rax]
0x18000abc4  mov     [rbp+0B0h], rcx
0x18000abcb  mov     [rbp+38h], edx
0x18000abce  mov     eax, [rbp+38h]
0x18000abd1  cmp     eax, 0E06D7363h
0x18000abd6  jnz     short loc_18000ABEC
0x18000abd8  mov     rdx, [rbp+0B0h]
0x18000abdf  mov     ecx, [rbp+38h]
0x18000abe2  call    _XcptFilter_0
0x18000abe7  mov     [rbp+40h], eax
0x18000abea  jmp     short loc_18000ABF3
0x18000abec  mov     dword ptr [rbp+40h], 0
0x18000abf3  mov     eax, [rbp+40h]
0x18000abf6  add     rsp, 20h
0x18000abfa  pop     rbp
0x18000abfb  retn
0x18000abfd  push    rbp
0x18000abff  sub     rsp, 20h
0x18000ac03  mov     rbp, rdx
0x18000ac06  mov     rax, [rcx]
0x18000ac09  mov     edx, [rax]
0x18000ac0b  mov     [rbp+0B8h], rcx
0x18000ac12  mov     [rbp+48h], edx
0x18000ac15  mov     eax, [rbp+48h]
0x18000ac18  cmp     eax, 0E06D7363h
0x18000ac1d  jnz     short loc_18000AC33
0x18000ac1f  mov     rdx, [rbp+0B8h]
0x18000ac26  mov     ecx, [rbp+48h]
0x18000ac29  call    _XcptFilter_0
0x18000ac2e  mov     [rbp+50h], eax
0x18000ac31  jmp     short loc_18000AC3A
0x18000ac33  mov     dword ptr [rbp+50h], 0
0x18000ac3a  mov     eax, [rbp+50h]
0x18000ac3d  add     rsp, 20h
0x18000ac41  pop     rbp
0x18000ac42  retn
0x18000ac44  push    rbp
0x18000ac46  sub     rsp, 20h
0x18000ac4a  mov     rbp, rdx
0x18000ac4d  mov     rax, [rcx]
0x18000ac50  mov     edx, [rax]
0x18000ac52  mov     [rbp+0C0h], rcx
0x18000ac59  mov     [rbp+58h], edx
0x18000ac5c  mov     eax, [rbp+58h]
0x18000ac5f  cmp     eax, 0E06D7363h
0x18000ac64  jnz     short loc_18000AC7A
0x18000ac66  mov     rdx, [rbp+0C0h]
0x18000ac6d  mov     ecx, [rbp+58h]
0x18000ac70  call    _XcptFilter_0
0x18000ac75  mov     [rbp+60h], eax
0x18000ac78  jmp     short loc_18000AC81
0x18000ac7a  mov     dword ptr [rbp+60h], 0
0x18000ac81  mov     eax, [rbp+60h]
0x18000ac84  add     rsp, 20h
0x18000ac88  pop     rbp
0x18000ac89  retn
0x18000ac8b  push    rbp
0x18000ac8d  sub     rsp, 20h
0x18000ac91  mov     rbp, rdx
0x18000ac94  mov     rax, [rcx]
0x18000ac97  mov     edx, [rax]
0x18000ac99  mov     [rbp+0C8h], rcx
0x18000aca0  mov     [rbp+68h], edx
0x18000aca3  mov     eax, [rbp+68h]
0x18000aca6  cmp     eax, 0E06D7363h
0x18000acab  jnz     short loc_18000ACC1
0x18000acad  mov     rdx, [rbp+0C8h]
0x18000acb4  mov     ecx, [rbp+68h]
0x18000acb7  call    _XcptFilter_0
0x18000acbc  mov     [rbp+70h], eax
0x18000acbf  jmp     short loc_18000ACC8
0x18000acc1  mov     dword ptr [rbp+70h], 0
0x18000acc8  mov     eax, [rbp+70h]
0x18000accb  add     rsp, 20h
0x18000accf  pop     rbp
0x18000acd0  retn
0x18000acd2  push    rbp
0x18000acd4  sub     rsp, 20h
0x18000acd8  mov     rbp, rdx
0x18000acdb  mov     rax, [rcx]
0x18000acde  mov     edx, [rax]
0x18000ace0  mov     [rbp+0D0h], rcx
0x18000ace7  mov     [rbp+78h], edx
0x18000acea  mov     eax, [rbp+78h]
0x18000aced  cmp     eax, 0E06D7363h
0x18000acf2  jnz     short loc_18000AD0B
0x18000acf4  mov     rdx, [rbp+0D0h]
0x18000acfb  mov     ecx, [rbp+78h]
0x18000acfe  call    _XcptFilter_0
0x18000ad03  mov     [rbp+80h], eax
0x18000ad09  jmp     short loc_18000AD15
0x18000ad0b  mov     dword ptr [rbp+80h], 0
0x18000ad15  mov     eax, [rbp+80h]
0x18000ad1b  add     rsp, 20h
0x18000ad1f  pop     rbp
0x18000ad20  retn
0x18000ad22  push    rbp
0x18000ad24  sub     rsp, 20h
0x18000ad28  mov     rbp, rdx
0x18000ad2b  mov     rax, [rcx]
0x18000ad2e  mov     edx, [rax]
0x18000ad30  mov     [rbp+0D8h], rcx
0x18000ad37  mov     [rbp+88h], edx
0x18000ad3d  mov     eax, [rbp+88h]
0x18000ad43  cmp     eax, 0E06D7363h
0x18000ad48  jnz     short loc_18000AD64
0x18000ad4a  mov     rdx, [rbp+0D8h]
0x18000ad51  mov     ecx, [rbp+88h]
0x18000ad57  call    _XcptFilter_0
0x18000ad5c  mov     [rbp+90h], eax
0x18000ad62  jmp     short loc_18000AD6E
0x18000ad64  mov     dword ptr [rbp+90h], 0
0x18000ad6e  mov     eax, [rbp+90h]
0x18000ad74  add     rsp, 20h
0x18000ad78  pop     rbp
0x18000ad79  retn
0x18000ad7b  push    rbp
0x18000ad7d  sub     rsp, 20h
0x18000ad81  mov     rbp, rdx
0x18000ad84  mov     rax, [rcx]
0x18000ad87  mov     edx, [rax]
0x18000ad89  mov     [rbp+0E0h], rcx
0x18000ad90  mov     [rbp+98h], edx
0x18000ad96  mov     eax, [rbp+98h]
0x18000ad9c  cmp     eax, 0E06D7363h
0x18000ada1  jnz     short loc_18000ADBD
0x18000ada3  mov     rdx, [rbp+0E0h]
0x18000adaa  mov     ecx, [rbp+98h]
0x18000adb0  call    _XcptFilter_0
0x18000adb5  mov     [rbp+0A0h], eax
0x18000adbb  jmp     short loc_18000ADC7
0x18000adbd  mov     dword ptr [rbp+0A0h], 0
0x18000adc7  mov     eax, [rbp+0A0h]
0x18000adcd  add     rsp, 20h
0x18000add1  pop     rbp
0x18000add2  retn
0x18000add4  push    rbp
0x18000add6  sub     rsp, 20h
0x18000adda  mov     rbp, rdx
0x18000addd  cmp     dword ptr [rbp+118h], 1
0x18000ade4  ja      short loc_18000ADF0
0x18000ade6  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
