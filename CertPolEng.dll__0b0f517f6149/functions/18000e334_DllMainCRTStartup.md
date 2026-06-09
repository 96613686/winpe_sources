# __DllMainCRTStartup

- ea: `0x18000e334`
- end: `0x18000e540`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e2f0`

## callees

- `0x1800077b0`
- `0x18000e0c0`
- `0x18000e334`
- `0x18000e8ee`
- `0x18001a3f0`

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
  if ( (_DWORD)fdwReason || dword_18002875C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180028760 = 1;
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
            if ( dword_180028760 )
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
0x18000e334  mov     [rsp+lpvReserved], r8
0x18000e339  mov     [rsp+arg_8], edx
0x18000e33d  mov     [rsp+arg_0], rcx
0x18000e342  push    rbx
0x18000e343  push    rsi
0x18000e344  push    rdi
0x18000e345  sub     rsp, 0F0h
0x18000e34c  mov     edi, edx
0x18000e34e  mov     rsi, rcx
0x18000e351  mov     ebx, 1
0x18000e356  cmp     edx, ebx
0x18000e358  ja      short loc_18000E360
0x18000e35a  mov     cs:__native_dllmain_reason, edx
0x18000e360  test    edx, edx
0x18000e362  jnz     short loc_18000E377
0x18000e364  cmp     cs:dword_18002875C, edx
0x18000e36a  jnz     short loc_18000E377
0x18000e36c  xor     ebx, ebx
0x18000e36e  mov     [rsp+108h+var_E8], ebx
0x18000e372  jmp     loc_18000E524
0x18000e377  lea     eax, [rdx-1]
0x18000e37a  cmp     eax, 1
0x18000e37d  ja      loc_18000E404
0x18000e383  mov     rax, cs:_pRawDllMain
0x18000e38a  test    rax, rax
0x18000e38d  jz      short loc_18000E3C5
0x18000e38f  cmp     edx, 1
0x18000e392  jnz     short loc_18000E39A
0x18000e394  mov     cs:dword_180028760, edx
0x18000e39a  mov     r8, [rsp+108h+lpvReserved]
0x18000e3a2  call    cs:__guard_dispatch_icall_fptr
0x18000e3a8  mov     ebx, eax
0x18000e3aa  mov     [rsp+108h+var_E8], eax
0x18000e3ae  jmp     short loc_18000E3C5
0x18000e3b0  xor     ebx, ebx
0x18000e3b2  mov     [rsp+108h+var_E8], ebx
0x18000e3b6  mov     edi, [rsp+108h+arg_8]
0x18000e3bd  mov     rsi, [rsp+108h+arg_0]
0x18000e3c5  test    ebx, ebx
0x18000e3c7  jz      loc_18000E524
0x18000e3cd  mov     r8, [rsp+108h+lpvReserved]
0x18000e3d5  mov     edx, edi
0x18000e3d7  mov     rcx, rsi
0x18000e3da  call    _CRT_INIT
0x18000e3df  mov     ebx, eax
0x18000e3e1  mov     [rsp+108h+var_E8], eax
0x18000e3e5  jmp     short loc_18000E3FC
0x18000e3e7  xor     ebx, ebx
0x18000e3e9  mov     [rsp+108h+var_E8], ebx
0x18000e3ed  mov     edi, [rsp+108h+arg_8]
0x18000e3f4  mov     rsi, [rsp+108h+arg_0]
0x18000e3fc  test    ebx, ebx
0x18000e3fe  jz      loc_18000E524
0x18000e404  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000e40c  mov     edx, edi; fdwReason
0x18000e40e  mov     rcx, rsi; hinstDLL
0x18000e411  call    DllMain
0x18000e416  mov     ebx, eax
0x18000e418  mov     [rsp+108h+var_E8], eax
0x18000e41c  jmp     short loc_18000E433
0x18000e41e  xor     ebx, ebx
0x18000e420  mov     [rsp+108h+var_E8], ebx
0x18000e424  mov     edi, [rsp+108h+arg_8]
0x18000e42b  mov     rsi, [rsp+108h+arg_0]
0x18000e433  cmp     edi, 1
0x18000e436  jnz     short loc_18000E4AF
0x18000e438  test    ebx, ebx
0x18000e43a  jnz     short loc_18000E4AF
0x18000e43c  xor     r8d, r8d; lpvReserved
0x18000e43f  xor     edx, edx; fdwReason
0x18000e441  mov     rcx, rsi; hinstDLL
0x18000e444  call    DllMain
0x18000e449  jmp     short loc_18000E45E
0x18000e44b  mov     edi, [rsp+108h+arg_8]
0x18000e452  mov     rsi, [rsp+108h+arg_0]
0x18000e45a  mov     ebx, [rsp+108h+var_E8]
0x18000e45e  xor     r8d, r8d
0x18000e461  xor     edx, edx
0x18000e463  mov     rcx, rsi
0x18000e466  call    _CRT_INIT
0x18000e46b  jmp     short loc_18000E480
0x18000e46d  mov     edi, [rsp+108h+arg_8]
0x18000e474  mov     rsi, [rsp+108h+arg_0]
0x18000e47c  mov     ebx, [rsp+108h+var_E8]
0x18000e480  mov     rax, cs:_pRawDllMain
0x18000e487  test    rax, rax
0x18000e48a  jz      short loc_18000E4AF
0x18000e48c  xor     r8d, r8d
0x18000e48f  xor     edx, edx
0x18000e491  mov     rcx, rsi
0x18000e494  call    cs:__guard_dispatch_icall_fptr
0x18000e49a  jmp     short loc_18000E4AF
0x18000e49c  mov     edi, [rsp+108h+arg_8]
0x18000e4a3  mov     rsi, [rsp+108h+arg_0]
0x18000e4ab  mov     ebx, [rsp+108h+var_E8]
0x18000e4af  test    edi, edi
0x18000e4b1  jz      short loc_18000E4B8
0x18000e4b3  cmp     edi, 3
0x18000e4b6  jnz     short loc_18000E524
0x18000e4b8  mov     r8, [rsp+108h+lpvReserved]
0x18000e4c0  mov     edx, edi
0x18000e4c2  mov     rcx, rsi
0x18000e4c5  call    _CRT_INIT
0x18000e4ca  mov     ebx, eax
0x18000e4cc  mov     [rsp+108h+var_E8], eax
0x18000e4d0  jmp     short loc_18000E4E7
0x18000e4d2  xor     ebx, ebx
0x18000e4d4  mov     [rsp+108h+var_E8], ebx
0x18000e4d8  mov     edi, [rsp+108h+arg_8]
0x18000e4df  mov     rsi, [rsp+108h+arg_0]
0x18000e4e7  mov     rax, cs:_pRawDllMain
0x18000e4ee  test    rax, rax
0x18000e4f1  jz      short loc_18000E524
0x18000e4f3  cmp     cs:dword_180028760, 0
0x18000e4fa  jz      short loc_18000E524
0x18000e4fc  mov     r8, [rsp+108h+lpvReserved]
0x18000e504  mov     edx, edi
0x18000e506  mov     rcx, rsi
0x18000e509  call    cs:__guard_dispatch_icall_fptr
0x18000e50f  mov     ebx, eax
0x18000e511  mov     [rsp+108h+var_E8], eax
0x18000e515  jmp     short loc_18000E524
0x18000e517  xor     ebx, ebx
0x18000e519  mov     [rsp+108h+var_E8], ebx
0x18000e51d  mov     edi, [rsp+108h+arg_8]
0x18000e524  cmp     edi, 1
0x18000e527  ja      short loc_18000E533
0x18000e529  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000e533  mov     eax, ebx
0x18000e535  add     rsp, 0F0h
0x18000e53c  pop     rdi
0x18000e53d  pop     rsi
0x18000e53e  pop     rbx
0x18000e53f  retn
0x18001a688  push    rbp
0x18001a68a  sub     rsp, 20h
0x18001a68e  mov     rbp, rdx
0x18001a691  mov     rax, [rcx]
0x18001a694  mov     edx, [rax]
0x18001a696  mov     [rbp+0A8h], rcx
0x18001a69d  mov     [rbp+28h], edx
0x18001a6a0  mov     eax, [rbp+28h]
0x18001a6a3  cmp     eax, 0E06D7363h
0x18001a6a8  jnz     short loc_18001A6BE
0x18001a6aa  mov     rdx, [rbp+0A8h]
0x18001a6b1  mov     ecx, [rbp+28h]
0x18001a6b4  call    _XcptFilter_0
0x18001a6b9  mov     [rbp+30h], eax
0x18001a6bc  jmp     short loc_18001A6C5
0x18001a6be  mov     dword ptr [rbp+30h], 0
0x18001a6c5  mov     eax, [rbp+30h]
0x18001a6c8  add     rsp, 20h
0x18001a6cc  pop     rbp
0x18001a6cd  retn
0x18001a6cf  push    rbp
0x18001a6d1  sub     rsp, 20h
0x18001a6d5  mov     rbp, rdx
0x18001a6d8  mov     rax, [rcx]
0x18001a6db  mov     edx, [rax]
0x18001a6dd  mov     [rbp+0B0h], rcx
0x18001a6e4  mov     [rbp+38h], edx
0x18001a6e7  mov     eax, [rbp+38h]
0x18001a6ea  cmp     eax, 0E06D7363h
0x18001a6ef  jnz     short loc_18001A705
0x18001a6f1  mov     rdx, [rbp+0B0h]
0x18001a6f8  mov     ecx, [rbp+38h]
0x18001a6fb  call    _XcptFilter_0
0x18001a700  mov     [rbp+40h], eax
0x18001a703  jmp     short loc_18001A70C
0x18001a705  mov     dword ptr [rbp+40h], 0
0x18001a70c  mov     eax, [rbp+40h]
0x18001a70f  add     rsp, 20h
0x18001a713  pop     rbp
0x18001a714  retn
0x18001a716  push    rbp
0x18001a718  sub     rsp, 20h
0x18001a71c  mov     rbp, rdx
0x18001a71f  mov     rax, [rcx]
0x18001a722  mov     edx, [rax]
0x18001a724  mov     [rbp+0B8h], rcx
0x18001a72b  mov     [rbp+48h], edx
0x18001a72e  mov     eax, [rbp+48h]
0x18001a731  cmp     eax, 0E06D7363h
0x18001a736  jnz     short loc_18001A74C
0x18001a738  mov     rdx, [rbp+0B8h]
0x18001a73f  mov     ecx, [rbp+48h]
0x18001a742  call    _XcptFilter_0
0x18001a747  mov     [rbp+50h], eax
0x18001a74a  jmp     short loc_18001A753
0x18001a74c  mov     dword ptr [rbp+50h], 0
0x18001a753  mov     eax, [rbp+50h]
0x18001a756  add     rsp, 20h
0x18001a75a  pop     rbp
0x18001a75b  retn
0x18001a75d  push    rbp
0x18001a75f  sub     rsp, 20h
0x18001a763  mov     rbp, rdx
0x18001a766  mov     rax, [rcx]
0x18001a769  mov     edx, [rax]
0x18001a76b  mov     [rbp+0C0h], rcx
0x18001a772  mov     [rbp+58h], edx
0x18001a775  mov     eax, [rbp+58h]
0x18001a778  cmp     eax, 0E06D7363h
0x18001a77d  jnz     short loc_18001A793
0x18001a77f  mov     rdx, [rbp+0C0h]
0x18001a786  mov     ecx, [rbp+58h]
0x18001a789  call    _XcptFilter_0
0x18001a78e  mov     [rbp+60h], eax
0x18001a791  jmp     short loc_18001A79A
0x18001a793  mov     dword ptr [rbp+60h], 0
0x18001a79a  mov     eax, [rbp+60h]
0x18001a79d  add     rsp, 20h
0x18001a7a1  pop     rbp
0x18001a7a2  retn
0x18001a7a4  push    rbp
0x18001a7a6  sub     rsp, 20h
0x18001a7aa  mov     rbp, rdx
0x18001a7ad  mov     rax, [rcx]
0x18001a7b0  mov     edx, [rax]
0x18001a7b2  mov     [rbp+0C8h], rcx
0x18001a7b9  mov     [rbp+68h], edx
0x18001a7bc  mov     eax, [rbp+68h]
0x18001a7bf  cmp     eax, 0E06D7363h
0x18001a7c4  jnz     short loc_18001A7DA
0x18001a7c6  mov     rdx, [rbp+0C8h]
0x18001a7cd  mov     ecx, [rbp+68h]
0x18001a7d0  call    _XcptFilter_0
0x18001a7d5  mov     [rbp+70h], eax
0x18001a7d8  jmp     short loc_18001A7E1
0x18001a7da  mov     dword ptr [rbp+70h], 0
0x18001a7e1  mov     eax, [rbp+70h]
0x18001a7e4  add     rsp, 20h
0x18001a7e8  pop     rbp
0x18001a7e9  retn
0x18001a7eb  push    rbp
0x18001a7ed  sub     rsp, 20h
0x18001a7f1  mov     rbp, rdx
0x18001a7f4  mov     rax, [rcx]
0x18001a7f7  mov     edx, [rax]
0x18001a7f9  mov     [rbp+0D0h], rcx
0x18001a800  mov     [rbp+78h], edx
0x18001a803  mov     eax, [rbp+78h]
0x18001a806  cmp     eax, 0E06D7363h
0x18001a80b  jnz     short loc_18001A824
0x18001a80d  mov     rdx, [rbp+0D0h]
0x18001a814  mov     ecx, [rbp+78h]
0x18001a817  call    _XcptFilter_0
0x18001a81c  mov     [rbp+80h], eax
0x18001a822  jmp     short loc_18001A82E
0x18001a824  mov     dword ptr [rbp+80h], 0
0x18001a82e  mov     eax, [rbp+80h]
0x18001a834  add     rsp, 20h
0x18001a838  pop     rbp
0x18001a839  retn
0x18001a83b  push    rbp
0x18001a83d  sub     rsp, 20h
0x18001a841  mov     rbp, rdx
0x18001a844  mov     rax, [rcx]
0x18001a847  mov     edx, [rax]
0x18001a849  mov     [rbp+0D8h], rcx
0x18001a850  mov     [rbp+88h], edx
0x18001a856  mov     eax, [rbp+88h]
0x18001a85c  cmp     eax, 0E06D7363h
0x18001a861  jnz     short loc_18001A87D
0x18001a863  mov     rdx, [rbp+0D8h]
0x18001a86a  mov     ecx, [rbp+88h]
0x18001a870  call    _XcptFilter_0
0x18001a875  mov     [rbp+90h], eax
0x18001a87b  jmp     short loc_18001A887
0x18001a87d  mov     dword ptr [rbp+90h], 0
0x18001a887  mov     eax, [rbp+90h]
0x18001a88d  add     rsp, 20h
0x18001a891  pop     rbp
0x18001a892  retn
0x18001a894  push    rbp
0x18001a896  sub     rsp, 20h
0x18001a89a  mov     rbp, rdx
0x18001a89d  mov     rax, [rcx]
0x18001a8a0  mov     edx, [rax]
0x18001a8a2  mov     [rbp+0E0h], rcx
0x18001a8a9  mov     [rbp+98h], edx
0x18001a8af  mov     eax, [rbp+98h]
0x18001a8b5  cmp     eax, 0E06D7363h
0x18001a8ba  jnz     short loc_18001A8D6
0x18001a8bc  mov     rdx, [rbp+0E0h]
0x18001a8c3  mov     ecx, [rbp+98h]
0x18001a8c9  call    _XcptFilter_0
0x18001a8ce  mov     [rbp+0A0h], eax
0x18001a8d4  jmp     short loc_18001A8E0
0x18001a8d6  mov     dword ptr [rbp+0A0h], 0
0x18001a8e0  mov     eax, [rbp+0A0h]
0x18001a8e6  add     rsp, 20h
0x18001a8ea  pop     rbp
0x18001a8eb  retn
0x18001a8ed  push    rbp
0x18001a8ef  sub     rsp, 20h
0x18001a8f3  mov     rbp, rdx
0x18001a8f6  cmp     dword ptr [rbp+118h], 1
0x18001a8fd  ja      short loc_18001A909
0x18001a8ff  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
