# __DllMainCRTStartup

- ea: `0x180001f74`
- end: `0x180002180`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001f30`

## callees

- `0x180001d00`
- `0x180001f74`
- `0x18000233e`
- `0x1800074a4`
- `0x1800218c0`

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
  if ( (_DWORD)fdwReason || dword_18003039C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800303A0 = 1;
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
            if ( dword_1800303A0 )
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
0x180001f74  mov     [rsp+lpvReserved], r8
0x180001f79  mov     [rsp+arg_8], edx
0x180001f7d  mov     [rsp+arg_0], rcx
0x180001f82  push    rbx
0x180001f83  push    rsi
0x180001f84  push    rdi
0x180001f85  sub     rsp, 0F0h
0x180001f8c  mov     edi, edx
0x180001f8e  mov     rsi, rcx
0x180001f91  mov     ebx, 1
0x180001f96  cmp     edx, ebx
0x180001f98  ja      short loc_180001FA0
0x180001f9a  mov     cs:__native_dllmain_reason, edx
0x180001fa0  test    edx, edx
0x180001fa2  jnz     short loc_180001FB7
0x180001fa4  cmp     cs:dword_18003039C, edx
0x180001faa  jnz     short loc_180001FB7
0x180001fac  xor     ebx, ebx
0x180001fae  mov     [rsp+108h+var_E8], ebx
0x180001fb2  jmp     loc_180002164
0x180001fb7  lea     eax, [rdx-1]
0x180001fba  cmp     eax, 1
0x180001fbd  ja      loc_180002044
0x180001fc3  mov     rax, cs:_pRawDllMain
0x180001fca  test    rax, rax
0x180001fcd  jz      short loc_180002005
0x180001fcf  cmp     edx, 1
0x180001fd2  jnz     short loc_180001FDA
0x180001fd4  mov     cs:dword_1800303A0, edx
0x180001fda  mov     r8, [rsp+108h+lpvReserved]
0x180001fe2  call    cs:__guard_dispatch_icall_fptr
0x180001fe8  mov     ebx, eax
0x180001fea  mov     [rsp+108h+var_E8], eax
0x180001fee  jmp     short loc_180002005
0x180001ff0  xor     ebx, ebx
0x180001ff2  mov     [rsp+108h+var_E8], ebx
0x180001ff6  mov     edi, [rsp+108h+arg_8]
0x180001ffd  mov     rsi, [rsp+108h+arg_0]
0x180002005  test    ebx, ebx
0x180002007  jz      loc_180002164
0x18000200d  mov     r8, [rsp+108h+lpvReserved]
0x180002015  mov     edx, edi
0x180002017  mov     rcx, rsi
0x18000201a  call    _CRT_INIT
0x18000201f  mov     ebx, eax
0x180002021  mov     [rsp+108h+var_E8], eax
0x180002025  jmp     short loc_18000203C
0x180002027  xor     ebx, ebx
0x180002029  mov     [rsp+108h+var_E8], ebx
0x18000202d  mov     edi, [rsp+108h+arg_8]
0x180002034  mov     rsi, [rsp+108h+arg_0]
0x18000203c  test    ebx, ebx
0x18000203e  jz      loc_180002164
0x180002044  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000204c  mov     edx, edi; fdwReason
0x18000204e  mov     rcx, rsi; hinstDLL
0x180002051  call    DllMain
0x180002056  mov     ebx, eax
0x180002058  mov     [rsp+108h+var_E8], eax
0x18000205c  jmp     short loc_180002073
0x18000205e  xor     ebx, ebx
0x180002060  mov     [rsp+108h+var_E8], ebx
0x180002064  mov     edi, [rsp+108h+arg_8]
0x18000206b  mov     rsi, [rsp+108h+arg_0]
0x180002073  cmp     edi, 1
0x180002076  jnz     short loc_1800020EF
0x180002078  test    ebx, ebx
0x18000207a  jnz     short loc_1800020EF
0x18000207c  xor     r8d, r8d; lpvReserved
0x18000207f  xor     edx, edx; fdwReason
0x180002081  mov     rcx, rsi; hinstDLL
0x180002084  call    DllMain
0x180002089  jmp     short loc_18000209E
0x18000208b  mov     edi, [rsp+108h+arg_8]
0x180002092  mov     rsi, [rsp+108h+arg_0]
0x18000209a  mov     ebx, [rsp+108h+var_E8]
0x18000209e  xor     r8d, r8d
0x1800020a1  xor     edx, edx
0x1800020a3  mov     rcx, rsi
0x1800020a6  call    _CRT_INIT
0x1800020ab  jmp     short loc_1800020C0
0x1800020ad  mov     edi, [rsp+108h+arg_8]
0x1800020b4  mov     rsi, [rsp+108h+arg_0]
0x1800020bc  mov     ebx, [rsp+108h+var_E8]
0x1800020c0  mov     rax, cs:_pRawDllMain
0x1800020c7  test    rax, rax
0x1800020ca  jz      short loc_1800020EF
0x1800020cc  xor     r8d, r8d
0x1800020cf  xor     edx, edx
0x1800020d1  mov     rcx, rsi
0x1800020d4  call    cs:__guard_dispatch_icall_fptr
0x1800020da  jmp     short loc_1800020EF
0x1800020dc  mov     edi, [rsp+108h+arg_8]
0x1800020e3  mov     rsi, [rsp+108h+arg_0]
0x1800020eb  mov     ebx, [rsp+108h+var_E8]
0x1800020ef  test    edi, edi
0x1800020f1  jz      short loc_1800020F8
0x1800020f3  cmp     edi, 3
0x1800020f6  jnz     short loc_180002164
0x1800020f8  mov     r8, [rsp+108h+lpvReserved]
0x180002100  mov     edx, edi
0x180002102  mov     rcx, rsi
0x180002105  call    _CRT_INIT
0x18000210a  mov     ebx, eax
0x18000210c  mov     [rsp+108h+var_E8], eax
0x180002110  jmp     short loc_180002127
0x180002112  xor     ebx, ebx
0x180002114  mov     [rsp+108h+var_E8], ebx
0x180002118  mov     edi, [rsp+108h+arg_8]
0x18000211f  mov     rsi, [rsp+108h+arg_0]
0x180002127  mov     rax, cs:_pRawDllMain
0x18000212e  test    rax, rax
0x180002131  jz      short loc_180002164
0x180002133  cmp     cs:dword_1800303A0, 0
0x18000213a  jz      short loc_180002164
0x18000213c  mov     r8, [rsp+108h+lpvReserved]
0x180002144  mov     edx, edi
0x180002146  mov     rcx, rsi
0x180002149  call    cs:__guard_dispatch_icall_fptr
0x18000214f  mov     ebx, eax
0x180002151  mov     [rsp+108h+var_E8], eax
0x180002155  jmp     short loc_180002164
0x180002157  xor     ebx, ebx
0x180002159  mov     [rsp+108h+var_E8], ebx
0x18000215d  mov     edi, [rsp+108h+arg_8]
0x180002164  cmp     edi, 1
0x180002167  ja      short loc_180002173
0x180002169  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002173  mov     eax, ebx
0x180002175  add     rsp, 0F0h
0x18000217c  pop     rdi
0x18000217d  pop     rsi
0x18000217e  pop     rbx
0x18000217f  retn
0x180021963  push    rbp
0x180021965  sub     rsp, 20h
0x180021969  mov     rbp, rdx
0x18002196c  mov     rax, [rcx]
0x18002196f  mov     edx, [rax]
0x180021971  mov     [rbp+0A8h], rcx
0x180021978  mov     [rbp+28h], edx
0x18002197b  mov     eax, [rbp+28h]
0x18002197e  cmp     eax, 0E06D7363h
0x180021983  jnz     short loc_180021999
0x180021985  mov     rdx, [rbp+0A8h]
0x18002198c  mov     ecx, [rbp+28h]
0x18002198f  call    _XcptFilter_0
0x180021994  mov     [rbp+30h], eax
0x180021997  jmp     short loc_1800219A0
0x180021999  mov     dword ptr [rbp+30h], 0
0x1800219a0  mov     eax, [rbp+30h]
0x1800219a3  add     rsp, 20h
0x1800219a7  pop     rbp
0x1800219a8  retn
0x1800219aa  push    rbp
0x1800219ac  sub     rsp, 20h
0x1800219b0  mov     rbp, rdx
0x1800219b3  mov     rax, [rcx]
0x1800219b6  mov     edx, [rax]
0x1800219b8  mov     [rbp+0B0h], rcx
0x1800219bf  mov     [rbp+38h], edx
0x1800219c2  mov     eax, [rbp+38h]
0x1800219c5  cmp     eax, 0E06D7363h
0x1800219ca  jnz     short loc_1800219E0
0x1800219cc  mov     rdx, [rbp+0B0h]
0x1800219d3  mov     ecx, [rbp+38h]
0x1800219d6  call    _XcptFilter_0
0x1800219db  mov     [rbp+40h], eax
0x1800219de  jmp     short loc_1800219E7
0x1800219e0  mov     dword ptr [rbp+40h], 0
0x1800219e7  mov     eax, [rbp+40h]
0x1800219ea  add     rsp, 20h
0x1800219ee  pop     rbp
0x1800219ef  retn
0x1800219f1  push    rbp
0x1800219f3  sub     rsp, 20h
0x1800219f7  mov     rbp, rdx
0x1800219fa  mov     rax, [rcx]
0x1800219fd  mov     edx, [rax]
0x1800219ff  mov     [rbp+0B8h], rcx
0x180021a06  mov     [rbp+48h], edx
0x180021a09  mov     eax, [rbp+48h]
0x180021a0c  cmp     eax, 0E06D7363h
0x180021a11  jnz     short loc_180021A27
0x180021a13  mov     rdx, [rbp+0B8h]
0x180021a1a  mov     ecx, [rbp+48h]
0x180021a1d  call    _XcptFilter_0
0x180021a22  mov     [rbp+50h], eax
0x180021a25  jmp     short loc_180021A2E
0x180021a27  mov     dword ptr [rbp+50h], 0
0x180021a2e  mov     eax, [rbp+50h]
0x180021a31  add     rsp, 20h
0x180021a35  pop     rbp
0x180021a36  retn
0x180021a38  push    rbp
0x180021a3a  sub     rsp, 20h
0x180021a3e  mov     rbp, rdx
0x180021a41  mov     rax, [rcx]
0x180021a44  mov     edx, [rax]
0x180021a46  mov     [rbp+0C0h], rcx
0x180021a4d  mov     [rbp+58h], edx
0x180021a50  mov     eax, [rbp+58h]
0x180021a53  cmp     eax, 0E06D7363h
0x180021a58  jnz     short loc_180021A6E
0x180021a5a  mov     rdx, [rbp+0C0h]
0x180021a61  mov     ecx, [rbp+58h]
0x180021a64  call    _XcptFilter_0
0x180021a69  mov     [rbp+60h], eax
0x180021a6c  jmp     short loc_180021A75
0x180021a6e  mov     dword ptr [rbp+60h], 0
0x180021a75  mov     eax, [rbp+60h]
0x180021a78  add     rsp, 20h
0x180021a7c  pop     rbp
0x180021a7d  retn
0x180021a7f  push    rbp
0x180021a81  sub     rsp, 20h
0x180021a85  mov     rbp, rdx
0x180021a88  mov     rax, [rcx]
0x180021a8b  mov     edx, [rax]
0x180021a8d  mov     [rbp+0C8h], rcx
0x180021a94  mov     [rbp+68h], edx
0x180021a97  mov     eax, [rbp+68h]
0x180021a9a  cmp     eax, 0E06D7363h
0x180021a9f  jnz     short loc_180021AB5
0x180021aa1  mov     rdx, [rbp+0C8h]
0x180021aa8  mov     ecx, [rbp+68h]
0x180021aab  call    _XcptFilter_0
0x180021ab0  mov     [rbp+70h], eax
0x180021ab3  jmp     short loc_180021ABC
0x180021ab5  mov     dword ptr [rbp+70h], 0
0x180021abc  mov     eax, [rbp+70h]
0x180021abf  add     rsp, 20h
0x180021ac3  pop     rbp
0x180021ac4  retn
0x180021ac6  push    rbp
0x180021ac8  sub     rsp, 20h
0x180021acc  mov     rbp, rdx
0x180021acf  mov     rax, [rcx]
0x180021ad2  mov     edx, [rax]
0x180021ad4  mov     [rbp+0D0h], rcx
0x180021adb  mov     [rbp+78h], edx
0x180021ade  mov     eax, [rbp+78h]
0x180021ae1  cmp     eax, 0E06D7363h
0x180021ae6  jnz     short loc_180021AFF
0x180021ae8  mov     rdx, [rbp+0D0h]
0x180021aef  mov     ecx, [rbp+78h]
0x180021af2  call    _XcptFilter_0
0x180021af7  mov     [rbp+80h], eax
0x180021afd  jmp     short loc_180021B09
0x180021aff  mov     dword ptr [rbp+80h], 0
0x180021b09  mov     eax, [rbp+80h]
0x180021b0f  add     rsp, 20h
0x180021b13  pop     rbp
0x180021b14  retn
0x180021b16  push    rbp
0x180021b18  sub     rsp, 20h
0x180021b1c  mov     rbp, rdx
0x180021b1f  mov     rax, [rcx]
0x180021b22  mov     edx, [rax]
0x180021b24  mov     [rbp+0D8h], rcx
0x180021b2b  mov     [rbp+88h], edx
0x180021b31  mov     eax, [rbp+88h]
0x180021b37  cmp     eax, 0E06D7363h
0x180021b3c  jnz     short loc_180021B58
0x180021b3e  mov     rdx, [rbp+0D8h]
0x180021b45  mov     ecx, [rbp+88h]
0x180021b4b  call    _XcptFilter_0
0x180021b50  mov     [rbp+90h], eax
0x180021b56  jmp     short loc_180021B62
0x180021b58  mov     dword ptr [rbp+90h], 0
0x180021b62  mov     eax, [rbp+90h]
0x180021b68  add     rsp, 20h
0x180021b6c  pop     rbp
0x180021b6d  retn
0x180021b6f  push    rbp
0x180021b71  sub     rsp, 20h
0x180021b75  mov     rbp, rdx
0x180021b78  mov     rax, [rcx]
0x180021b7b  mov     edx, [rax]
0x180021b7d  mov     [rbp+0E0h], rcx
0x180021b84  mov     [rbp+98h], edx
0x180021b8a  mov     eax, [rbp+98h]
0x180021b90  cmp     eax, 0E06D7363h
0x180021b95  jnz     short loc_180021BB1
0x180021b97  mov     rdx, [rbp+0E0h]
0x180021b9e  mov     ecx, [rbp+98h]
0x180021ba4  call    _XcptFilter_0
0x180021ba9  mov     [rbp+0A0h], eax
0x180021baf  jmp     short loc_180021BBB
0x180021bb1  mov     dword ptr [rbp+0A0h], 0
0x180021bbb  mov     eax, [rbp+0A0h]
0x180021bc1  add     rsp, 20h
0x180021bc5  pop     rbp
0x180021bc6  retn
0x180021bc8  push    rbp
0x180021bca  sub     rsp, 20h
0x180021bce  mov     rbp, rdx
0x180021bd1  cmp     dword ptr [rbp+118h], 1
0x180021bd8  ja      short loc_180021BE4
0x180021bda  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
