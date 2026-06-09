# __DllMainCRTStartup

- ea: `0x180001d84`
- end: `0x180001f90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001d40`

## callees

- `0x180001b10`
- `0x180001d84`
- `0x18000251e`
- `0x1800069f0`
- `0x18000aa40`

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
  if ( (_DWORD)fdwReason || dword_1800133EC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800133F0 = 1;
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
            if ( dword_1800133F0 )
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
0x180001d84  mov     [rsp+lpvReserved], r8
0x180001d89  mov     [rsp+arg_8], edx
0x180001d8d  mov     [rsp+arg_0], rcx
0x180001d92  push    rbx
0x180001d93  push    rsi
0x180001d94  push    rdi
0x180001d95  sub     rsp, 0F0h
0x180001d9c  mov     edi, edx
0x180001d9e  mov     rsi, rcx
0x180001da1  mov     ebx, 1
0x180001da6  cmp     edx, ebx
0x180001da8  ja      short loc_180001DB0
0x180001daa  mov     cs:__native_dllmain_reason, edx
0x180001db0  test    edx, edx
0x180001db2  jnz     short loc_180001DC7
0x180001db4  cmp     cs:dword_1800133EC, edx
0x180001dba  jnz     short loc_180001DC7
0x180001dbc  xor     ebx, ebx
0x180001dbe  mov     [rsp+108h+var_E8], ebx
0x180001dc2  jmp     loc_180001F74
0x180001dc7  lea     eax, [rdx-1]
0x180001dca  cmp     eax, 1
0x180001dcd  ja      loc_180001E54
0x180001dd3  mov     rax, cs:_pRawDllMain
0x180001dda  test    rax, rax
0x180001ddd  jz      short loc_180001E15
0x180001ddf  cmp     edx, 1
0x180001de2  jnz     short loc_180001DEA
0x180001de4  mov     cs:dword_1800133F0, edx
0x180001dea  mov     r8, [rsp+108h+lpvReserved]
0x180001df2  call    cs:__guard_dispatch_icall_fptr
0x180001df8  mov     ebx, eax
0x180001dfa  mov     [rsp+108h+var_E8], eax
0x180001dfe  jmp     short loc_180001E15
0x180001e00  xor     ebx, ebx
0x180001e02  mov     [rsp+108h+var_E8], ebx
0x180001e06  mov     edi, [rsp+108h+arg_8]
0x180001e0d  mov     rsi, [rsp+108h+arg_0]
0x180001e15  test    ebx, ebx
0x180001e17  jz      loc_180001F74
0x180001e1d  mov     r8, [rsp+108h+lpvReserved]
0x180001e25  mov     edx, edi
0x180001e27  mov     rcx, rsi
0x180001e2a  call    _CRT_INIT
0x180001e2f  mov     ebx, eax
0x180001e31  mov     [rsp+108h+var_E8], eax
0x180001e35  jmp     short loc_180001E4C
0x180001e37  xor     ebx, ebx
0x180001e39  mov     [rsp+108h+var_E8], ebx
0x180001e3d  mov     edi, [rsp+108h+arg_8]
0x180001e44  mov     rsi, [rsp+108h+arg_0]
0x180001e4c  test    ebx, ebx
0x180001e4e  jz      loc_180001F74
0x180001e54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001e5c  mov     edx, edi; fdwReason
0x180001e5e  mov     rcx, rsi; hinstDLL
0x180001e61  call    DllMain
0x180001e66  mov     ebx, eax
0x180001e68  mov     [rsp+108h+var_E8], eax
0x180001e6c  jmp     short loc_180001E83
0x180001e6e  xor     ebx, ebx
0x180001e70  mov     [rsp+108h+var_E8], ebx
0x180001e74  mov     edi, [rsp+108h+arg_8]
0x180001e7b  mov     rsi, [rsp+108h+arg_0]
0x180001e83  cmp     edi, 1
0x180001e86  jnz     short loc_180001EFF
0x180001e88  test    ebx, ebx
0x180001e8a  jnz     short loc_180001EFF
0x180001e8c  xor     r8d, r8d; lpvReserved
0x180001e8f  xor     edx, edx; fdwReason
0x180001e91  mov     rcx, rsi; hinstDLL
0x180001e94  call    DllMain
0x180001e99  jmp     short loc_180001EAE
0x180001e9b  mov     edi, [rsp+108h+arg_8]
0x180001ea2  mov     rsi, [rsp+108h+arg_0]
0x180001eaa  mov     ebx, [rsp+108h+var_E8]
0x180001eae  xor     r8d, r8d
0x180001eb1  xor     edx, edx
0x180001eb3  mov     rcx, rsi
0x180001eb6  call    _CRT_INIT
0x180001ebb  jmp     short loc_180001ED0
0x180001ebd  mov     edi, [rsp+108h+arg_8]
0x180001ec4  mov     rsi, [rsp+108h+arg_0]
0x180001ecc  mov     ebx, [rsp+108h+var_E8]
0x180001ed0  mov     rax, cs:_pRawDllMain
0x180001ed7  test    rax, rax
0x180001eda  jz      short loc_180001EFF
0x180001edc  xor     r8d, r8d
0x180001edf  xor     edx, edx
0x180001ee1  mov     rcx, rsi
0x180001ee4  call    cs:__guard_dispatch_icall_fptr
0x180001eea  jmp     short loc_180001EFF
0x180001eec  mov     edi, [rsp+108h+arg_8]
0x180001ef3  mov     rsi, [rsp+108h+arg_0]
0x180001efb  mov     ebx, [rsp+108h+var_E8]
0x180001eff  test    edi, edi
0x180001f01  jz      short loc_180001F08
0x180001f03  cmp     edi, 3
0x180001f06  jnz     short loc_180001F74
0x180001f08  mov     r8, [rsp+108h+lpvReserved]
0x180001f10  mov     edx, edi
0x180001f12  mov     rcx, rsi
0x180001f15  call    _CRT_INIT
0x180001f1a  mov     ebx, eax
0x180001f1c  mov     [rsp+108h+var_E8], eax
0x180001f20  jmp     short loc_180001F37
0x180001f22  xor     ebx, ebx
0x180001f24  mov     [rsp+108h+var_E8], ebx
0x180001f28  mov     edi, [rsp+108h+arg_8]
0x180001f2f  mov     rsi, [rsp+108h+arg_0]
0x180001f37  mov     rax, cs:_pRawDllMain
0x180001f3e  test    rax, rax
0x180001f41  jz      short loc_180001F74
0x180001f43  cmp     cs:dword_1800133F0, 0
0x180001f4a  jz      short loc_180001F74
0x180001f4c  mov     r8, [rsp+108h+lpvReserved]
0x180001f54  mov     edx, edi
0x180001f56  mov     rcx, rsi
0x180001f59  call    cs:__guard_dispatch_icall_fptr
0x180001f5f  mov     ebx, eax
0x180001f61  mov     [rsp+108h+var_E8], eax
0x180001f65  jmp     short loc_180001F74
0x180001f67  xor     ebx, ebx
0x180001f69  mov     [rsp+108h+var_E8], ebx
0x180001f6d  mov     edi, [rsp+108h+arg_8]
0x180001f74  cmp     edi, 1
0x180001f77  ja      short loc_180001F83
0x180001f79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001f83  mov     eax, ebx
0x180001f85  add     rsp, 0F0h
0x180001f8c  pop     rdi
0x180001f8d  pop     rsi
0x180001f8e  pop     rbx
0x180001f8f  retn
0x18000ab52  push    rbp
0x18000ab54  sub     rsp, 20h
0x18000ab58  mov     rbp, rdx
0x18000ab5b  mov     rax, [rcx]
0x18000ab5e  mov     edx, [rax]
0x18000ab60  mov     [rbp+0A8h], rcx
0x18000ab67  mov     [rbp+28h], edx
0x18000ab6a  mov     eax, [rbp+28h]
0x18000ab6d  cmp     eax, 0E06D7363h
0x18000ab72  jnz     short loc_18000AB88
0x18000ab74  mov     rdx, [rbp+0A8h]
0x18000ab7b  mov     ecx, [rbp+28h]
0x18000ab7e  call    _XcptFilter_0
0x18000ab83  mov     [rbp+30h], eax
0x18000ab86  jmp     short loc_18000AB8F
0x18000ab88  mov     dword ptr [rbp+30h], 0
0x18000ab8f  mov     eax, [rbp+30h]
0x18000ab92  add     rsp, 20h
0x18000ab96  pop     rbp
0x18000ab97  retn
0x18000ab99  push    rbp
0x18000ab9b  sub     rsp, 20h
0x18000ab9f  mov     rbp, rdx
0x18000aba2  mov     rax, [rcx]
0x18000aba5  mov     edx, [rax]
0x18000aba7  mov     [rbp+0B0h], rcx
0x18000abae  mov     [rbp+38h], edx
0x18000abb1  mov     eax, [rbp+38h]
0x18000abb4  cmp     eax, 0E06D7363h
0x18000abb9  jnz     short loc_18000ABCF
0x18000abbb  mov     rdx, [rbp+0B0h]
0x18000abc2  mov     ecx, [rbp+38h]
0x18000abc5  call    _XcptFilter_0
0x18000abca  mov     [rbp+40h], eax
0x18000abcd  jmp     short loc_18000ABD6
0x18000abcf  mov     dword ptr [rbp+40h], 0
0x18000abd6  mov     eax, [rbp+40h]
0x18000abd9  add     rsp, 20h
0x18000abdd  pop     rbp
0x18000abde  retn
0x18000abe0  push    rbp
0x18000abe2  sub     rsp, 20h
0x18000abe6  mov     rbp, rdx
0x18000abe9  mov     rax, [rcx]
0x18000abec  mov     edx, [rax]
0x18000abee  mov     [rbp+0B8h], rcx
0x18000abf5  mov     [rbp+48h], edx
0x18000abf8  mov     eax, [rbp+48h]
0x18000abfb  cmp     eax, 0E06D7363h
0x18000ac00  jnz     short loc_18000AC16
0x18000ac02  mov     rdx, [rbp+0B8h]
0x18000ac09  mov     ecx, [rbp+48h]
0x18000ac0c  call    _XcptFilter_0
0x18000ac11  mov     [rbp+50h], eax
0x18000ac14  jmp     short loc_18000AC1D
0x18000ac16  mov     dword ptr [rbp+50h], 0
0x18000ac1d  mov     eax, [rbp+50h]
0x18000ac20  add     rsp, 20h
0x18000ac24  pop     rbp
0x18000ac25  retn
0x18000ac27  push    rbp
0x18000ac29  sub     rsp, 20h
0x18000ac2d  mov     rbp, rdx
0x18000ac30  mov     rax, [rcx]
0x18000ac33  mov     edx, [rax]
0x18000ac35  mov     [rbp+0C0h], rcx
0x18000ac3c  mov     [rbp+58h], edx
0x18000ac3f  mov     eax, [rbp+58h]
0x18000ac42  cmp     eax, 0E06D7363h
0x18000ac47  jnz     short loc_18000AC5D
0x18000ac49  mov     rdx, [rbp+0C0h]
0x18000ac50  mov     ecx, [rbp+58h]
0x18000ac53  call    _XcptFilter_0
0x18000ac58  mov     [rbp+60h], eax
0x18000ac5b  jmp     short loc_18000AC64
0x18000ac5d  mov     dword ptr [rbp+60h], 0
0x18000ac64  mov     eax, [rbp+60h]
0x18000ac67  add     rsp, 20h
0x18000ac6b  pop     rbp
0x18000ac6c  retn
0x18000ac6e  push    rbp
0x18000ac70  sub     rsp, 20h
0x18000ac74  mov     rbp, rdx
0x18000ac77  mov     rax, [rcx]
0x18000ac7a  mov     edx, [rax]
0x18000ac7c  mov     [rbp+0C8h], rcx
0x18000ac83  mov     [rbp+68h], edx
0x18000ac86  mov     eax, [rbp+68h]
0x18000ac89  cmp     eax, 0E06D7363h
0x18000ac8e  jnz     short loc_18000ACA4
0x18000ac90  mov     rdx, [rbp+0C8h]
0x18000ac97  mov     ecx, [rbp+68h]
0x18000ac9a  call    _XcptFilter_0
0x18000ac9f  mov     [rbp+70h], eax
0x18000aca2  jmp     short loc_18000ACAB
0x18000aca4  mov     dword ptr [rbp+70h], 0
0x18000acab  mov     eax, [rbp+70h]
0x18000acae  add     rsp, 20h
0x18000acb2  pop     rbp
0x18000acb3  retn
0x18000acb5  push    rbp
0x18000acb7  sub     rsp, 20h
0x18000acbb  mov     rbp, rdx
0x18000acbe  mov     rax, [rcx]
0x18000acc1  mov     edx, [rax]
0x18000acc3  mov     [rbp+0D0h], rcx
0x18000acca  mov     [rbp+78h], edx
0x18000accd  mov     eax, [rbp+78h]
0x18000acd0  cmp     eax, 0E06D7363h
0x18000acd5  jnz     short loc_18000ACEE
0x18000acd7  mov     rdx, [rbp+0D0h]
0x18000acde  mov     ecx, [rbp+78h]
0x18000ace1  call    _XcptFilter_0
0x18000ace6  mov     [rbp+80h], eax
0x18000acec  jmp     short loc_18000ACF8
0x18000acee  mov     dword ptr [rbp+80h], 0
0x18000acf8  mov     eax, [rbp+80h]
0x18000acfe  add     rsp, 20h
0x18000ad02  pop     rbp
0x18000ad03  retn
0x18000ad05  push    rbp
0x18000ad07  sub     rsp, 20h
0x18000ad0b  mov     rbp, rdx
0x18000ad0e  mov     rax, [rcx]
0x18000ad11  mov     edx, [rax]
0x18000ad13  mov     [rbp+0D8h], rcx
0x18000ad1a  mov     [rbp+88h], edx
0x18000ad20  mov     eax, [rbp+88h]
0x18000ad26  cmp     eax, 0E06D7363h
0x18000ad2b  jnz     short loc_18000AD47
0x18000ad2d  mov     rdx, [rbp+0D8h]
0x18000ad34  mov     ecx, [rbp+88h]
0x18000ad3a  call    _XcptFilter_0
0x18000ad3f  mov     [rbp+90h], eax
0x18000ad45  jmp     short loc_18000AD51
0x18000ad47  mov     dword ptr [rbp+90h], 0
0x18000ad51  mov     eax, [rbp+90h]
0x18000ad57  add     rsp, 20h
0x18000ad5b  pop     rbp
0x18000ad5c  retn
0x18000ad5e  push    rbp
0x18000ad60  sub     rsp, 20h
0x18000ad64  mov     rbp, rdx
0x18000ad67  mov     rax, [rcx]
0x18000ad6a  mov     edx, [rax]
0x18000ad6c  mov     [rbp+0E0h], rcx
0x18000ad73  mov     [rbp+98h], edx
0x18000ad79  mov     eax, [rbp+98h]
0x18000ad7f  cmp     eax, 0E06D7363h
0x18000ad84  jnz     short loc_18000ADA0
0x18000ad86  mov     rdx, [rbp+0E0h]
0x18000ad8d  mov     ecx, [rbp+98h]
0x18000ad93  call    _XcptFilter_0
0x18000ad98  mov     [rbp+0A0h], eax
0x18000ad9e  jmp     short loc_18000ADAA
0x18000ada0  mov     dword ptr [rbp+0A0h], 0
0x18000adaa  mov     eax, [rbp+0A0h]
0x18000adb0  add     rsp, 20h
0x18000adb4  pop     rbp
0x18000adb5  retn
0x18000adb7  push    rbp
0x18000adb9  sub     rsp, 20h
0x18000adbd  mov     rbp, rdx
0x18000adc0  cmp     dword ptr [rbp+118h], 1
0x18000adc7  ja      short loc_18000ADD3
0x18000adc9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
