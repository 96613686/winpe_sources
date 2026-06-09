# __DllMainCRTStartup

- ea: `0x1800085a4`
- end: `0x1800087b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008560`

## callees

- `0x1800054ac`
- `0x180008330`
- `0x1800085a4`
- `0x18000898e`
- `0x180011a60`

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
  if ( (_DWORD)fdwReason || dword_180025348 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002534C = 1;
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
            if ( dword_18002534C )
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
0x1800085a4  mov     [rsp+lpvReserved], r8
0x1800085a9  mov     [rsp+arg_8], edx
0x1800085ad  mov     [rsp+arg_0], rcx
0x1800085b2  push    rbx
0x1800085b3  push    rsi
0x1800085b4  push    rdi
0x1800085b5  sub     rsp, 0F0h
0x1800085bc  mov     edi, edx
0x1800085be  mov     rsi, rcx
0x1800085c1  mov     ebx, 1
0x1800085c6  cmp     edx, ebx
0x1800085c8  ja      short loc_1800085D0
0x1800085ca  mov     cs:__native_dllmain_reason, edx
0x1800085d0  test    edx, edx
0x1800085d2  jnz     short loc_1800085E7
0x1800085d4  cmp     cs:dword_180025348, edx
0x1800085da  jnz     short loc_1800085E7
0x1800085dc  xor     ebx, ebx
0x1800085de  mov     [rsp+108h+var_E8], ebx
0x1800085e2  jmp     loc_180008794
0x1800085e7  lea     eax, [rdx-1]
0x1800085ea  cmp     eax, 1
0x1800085ed  ja      loc_180008674
0x1800085f3  mov     rax, cs:_pRawDllMain
0x1800085fa  test    rax, rax
0x1800085fd  jz      short loc_180008635
0x1800085ff  cmp     edx, 1
0x180008602  jnz     short loc_18000860A
0x180008604  mov     cs:dword_18002534C, edx
0x18000860a  mov     r8, [rsp+108h+lpvReserved]
0x180008612  call    cs:__guard_dispatch_icall_fptr
0x180008618  mov     ebx, eax
0x18000861a  mov     [rsp+108h+var_E8], eax
0x18000861e  jmp     short loc_180008635
0x180008620  xor     ebx, ebx
0x180008622  mov     [rsp+108h+var_E8], ebx
0x180008626  mov     edi, [rsp+108h+arg_8]
0x18000862d  mov     rsi, [rsp+108h+arg_0]
0x180008635  test    ebx, ebx
0x180008637  jz      loc_180008794
0x18000863d  mov     r8, [rsp+108h+lpvReserved]
0x180008645  mov     edx, edi
0x180008647  mov     rcx, rsi
0x18000864a  call    _CRT_INIT
0x18000864f  mov     ebx, eax
0x180008651  mov     [rsp+108h+var_E8], eax
0x180008655  jmp     short loc_18000866C
0x180008657  xor     ebx, ebx
0x180008659  mov     [rsp+108h+var_E8], ebx
0x18000865d  mov     edi, [rsp+108h+arg_8]
0x180008664  mov     rsi, [rsp+108h+arg_0]
0x18000866c  test    ebx, ebx
0x18000866e  jz      loc_180008794
0x180008674  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000867c  mov     edx, edi; fdwReason
0x18000867e  mov     rcx, rsi; hinstDLL
0x180008681  call    DllMain
0x180008686  mov     ebx, eax
0x180008688  mov     [rsp+108h+var_E8], eax
0x18000868c  jmp     short loc_1800086A3
0x18000868e  xor     ebx, ebx
0x180008690  mov     [rsp+108h+var_E8], ebx
0x180008694  mov     edi, [rsp+108h+arg_8]
0x18000869b  mov     rsi, [rsp+108h+arg_0]
0x1800086a3  cmp     edi, 1
0x1800086a6  jnz     short loc_18000871F
0x1800086a8  test    ebx, ebx
0x1800086aa  jnz     short loc_18000871F
0x1800086ac  xor     r8d, r8d; lpvReserved
0x1800086af  xor     edx, edx; fdwReason
0x1800086b1  mov     rcx, rsi; hinstDLL
0x1800086b4  call    DllMain
0x1800086b9  jmp     short loc_1800086CE
0x1800086bb  mov     edi, [rsp+108h+arg_8]
0x1800086c2  mov     rsi, [rsp+108h+arg_0]
0x1800086ca  mov     ebx, [rsp+108h+var_E8]
0x1800086ce  xor     r8d, r8d
0x1800086d1  xor     edx, edx
0x1800086d3  mov     rcx, rsi
0x1800086d6  call    _CRT_INIT
0x1800086db  jmp     short loc_1800086F0
0x1800086dd  mov     edi, [rsp+108h+arg_8]
0x1800086e4  mov     rsi, [rsp+108h+arg_0]
0x1800086ec  mov     ebx, [rsp+108h+var_E8]
0x1800086f0  mov     rax, cs:_pRawDllMain
0x1800086f7  test    rax, rax
0x1800086fa  jz      short loc_18000871F
0x1800086fc  xor     r8d, r8d
0x1800086ff  xor     edx, edx
0x180008701  mov     rcx, rsi
0x180008704  call    cs:__guard_dispatch_icall_fptr
0x18000870a  jmp     short loc_18000871F
0x18000870c  mov     edi, [rsp+108h+arg_8]
0x180008713  mov     rsi, [rsp+108h+arg_0]
0x18000871b  mov     ebx, [rsp+108h+var_E8]
0x18000871f  test    edi, edi
0x180008721  jz      short loc_180008728
0x180008723  cmp     edi, 3
0x180008726  jnz     short loc_180008794
0x180008728  mov     r8, [rsp+108h+lpvReserved]
0x180008730  mov     edx, edi
0x180008732  mov     rcx, rsi
0x180008735  call    _CRT_INIT
0x18000873a  mov     ebx, eax
0x18000873c  mov     [rsp+108h+var_E8], eax
0x180008740  jmp     short loc_180008757
0x180008742  xor     ebx, ebx
0x180008744  mov     [rsp+108h+var_E8], ebx
0x180008748  mov     edi, [rsp+108h+arg_8]
0x18000874f  mov     rsi, [rsp+108h+arg_0]
0x180008757  mov     rax, cs:_pRawDllMain
0x18000875e  test    rax, rax
0x180008761  jz      short loc_180008794
0x180008763  cmp     cs:dword_18002534C, 0
0x18000876a  jz      short loc_180008794
0x18000876c  mov     r8, [rsp+108h+lpvReserved]
0x180008774  mov     edx, edi
0x180008776  mov     rcx, rsi
0x180008779  call    cs:__guard_dispatch_icall_fptr
0x18000877f  mov     ebx, eax
0x180008781  mov     [rsp+108h+var_E8], eax
0x180008785  jmp     short loc_180008794
0x180008787  xor     ebx, ebx
0x180008789  mov     [rsp+108h+var_E8], ebx
0x18000878d  mov     edi, [rsp+108h+arg_8]
0x180008794  cmp     edi, 1
0x180008797  ja      short loc_1800087A3
0x180008799  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800087a3  mov     eax, ebx
0x1800087a5  add     rsp, 0F0h
0x1800087ac  pop     rdi
0x1800087ad  pop     rsi
0x1800087ae  pop     rbx
0x1800087af  retn
0x180012a5d  push    rbp
0x180012a5f  sub     rsp, 20h
0x180012a63  mov     rbp, rdx
0x180012a66  mov     rax, [rcx]
0x180012a69  mov     edx, [rax]
0x180012a6b  mov     [rbp+0A8h], rcx
0x180012a72  mov     [rbp+28h], edx
0x180012a75  mov     eax, [rbp+28h]
0x180012a78  cmp     eax, 0E06D7363h
0x180012a7d  jnz     short loc_180012A93
0x180012a7f  mov     rdx, [rbp+0A8h]
0x180012a86  mov     ecx, [rbp+28h]
0x180012a89  call    _XcptFilter_0
0x180012a8e  mov     [rbp+30h], eax
0x180012a91  jmp     short loc_180012A9A
0x180012a93  mov     dword ptr [rbp+30h], 0
0x180012a9a  mov     eax, [rbp+30h]
0x180012a9d  add     rsp, 20h
0x180012aa1  pop     rbp
0x180012aa2  retn
0x180012aa4  push    rbp
0x180012aa6  sub     rsp, 20h
0x180012aaa  mov     rbp, rdx
0x180012aad  mov     rax, [rcx]
0x180012ab0  mov     edx, [rax]
0x180012ab2  mov     [rbp+0B0h], rcx
0x180012ab9  mov     [rbp+38h], edx
0x180012abc  mov     eax, [rbp+38h]
0x180012abf  cmp     eax, 0E06D7363h
0x180012ac4  jnz     short loc_180012ADA
0x180012ac6  mov     rdx, [rbp+0B0h]
0x180012acd  mov     ecx, [rbp+38h]
0x180012ad0  call    _XcptFilter_0
0x180012ad5  mov     [rbp+40h], eax
0x180012ad8  jmp     short loc_180012AE1
0x180012ada  mov     dword ptr [rbp+40h], 0
0x180012ae1  mov     eax, [rbp+40h]
0x180012ae4  add     rsp, 20h
0x180012ae8  pop     rbp
0x180012ae9  retn
0x180012aeb  push    rbp
0x180012aed  sub     rsp, 20h
0x180012af1  mov     rbp, rdx
0x180012af4  mov     rax, [rcx]
0x180012af7  mov     edx, [rax]
0x180012af9  mov     [rbp+0B8h], rcx
0x180012b00  mov     [rbp+48h], edx
0x180012b03  mov     eax, [rbp+48h]
0x180012b06  cmp     eax, 0E06D7363h
0x180012b0b  jnz     short loc_180012B21
0x180012b0d  mov     rdx, [rbp+0B8h]
0x180012b14  mov     ecx, [rbp+48h]
0x180012b17  call    _XcptFilter_0
0x180012b1c  mov     [rbp+50h], eax
0x180012b1f  jmp     short loc_180012B28
0x180012b21  mov     dword ptr [rbp+50h], 0
0x180012b28  mov     eax, [rbp+50h]
0x180012b2b  add     rsp, 20h
0x180012b2f  pop     rbp
0x180012b30  retn
0x180012b32  push    rbp
0x180012b34  sub     rsp, 20h
0x180012b38  mov     rbp, rdx
0x180012b3b  mov     rax, [rcx]
0x180012b3e  mov     edx, [rax]
0x180012b40  mov     [rbp+0C0h], rcx
0x180012b47  mov     [rbp+58h], edx
0x180012b4a  mov     eax, [rbp+58h]
0x180012b4d  cmp     eax, 0E06D7363h
0x180012b52  jnz     short loc_180012B68
0x180012b54  mov     rdx, [rbp+0C0h]
0x180012b5b  mov     ecx, [rbp+58h]
0x180012b5e  call    _XcptFilter_0
0x180012b63  mov     [rbp+60h], eax
0x180012b66  jmp     short loc_180012B6F
0x180012b68  mov     dword ptr [rbp+60h], 0
0x180012b6f  mov     eax, [rbp+60h]
0x180012b72  add     rsp, 20h
0x180012b76  pop     rbp
0x180012b77  retn
0x180012b79  push    rbp
0x180012b7b  sub     rsp, 20h
0x180012b7f  mov     rbp, rdx
0x180012b82  mov     rax, [rcx]
0x180012b85  mov     edx, [rax]
0x180012b87  mov     [rbp+0C8h], rcx
0x180012b8e  mov     [rbp+68h], edx
0x180012b91  mov     eax, [rbp+68h]
0x180012b94  cmp     eax, 0E06D7363h
0x180012b99  jnz     short loc_180012BAF
0x180012b9b  mov     rdx, [rbp+0C8h]
0x180012ba2  mov     ecx, [rbp+68h]
0x180012ba5  call    _XcptFilter_0
0x180012baa  mov     [rbp+70h], eax
0x180012bad  jmp     short loc_180012BB6
0x180012baf  mov     dword ptr [rbp+70h], 0
0x180012bb6  mov     eax, [rbp+70h]
0x180012bb9  add     rsp, 20h
0x180012bbd  pop     rbp
0x180012bbe  retn
0x180012bc0  push    rbp
0x180012bc2  sub     rsp, 20h
0x180012bc6  mov     rbp, rdx
0x180012bc9  mov     rax, [rcx]
0x180012bcc  mov     edx, [rax]
0x180012bce  mov     [rbp+0D0h], rcx
0x180012bd5  mov     [rbp+78h], edx
0x180012bd8  mov     eax, [rbp+78h]
0x180012bdb  cmp     eax, 0E06D7363h
0x180012be0  jnz     short loc_180012BF9
0x180012be2  mov     rdx, [rbp+0D0h]
0x180012be9  mov     ecx, [rbp+78h]
0x180012bec  call    _XcptFilter_0
0x180012bf1  mov     [rbp+80h], eax
0x180012bf7  jmp     short loc_180012C03
0x180012bf9  mov     dword ptr [rbp+80h], 0
0x180012c03  mov     eax, [rbp+80h]
0x180012c09  add     rsp, 20h
0x180012c0d  pop     rbp
0x180012c0e  retn
0x180012c10  push    rbp
0x180012c12  sub     rsp, 20h
0x180012c16  mov     rbp, rdx
0x180012c19  mov     rax, [rcx]
0x180012c1c  mov     edx, [rax]
0x180012c1e  mov     [rbp+0D8h], rcx
0x180012c25  mov     [rbp+88h], edx
0x180012c2b  mov     eax, [rbp+88h]
0x180012c31  cmp     eax, 0E06D7363h
0x180012c36  jnz     short loc_180012C52
0x180012c38  mov     rdx, [rbp+0D8h]
0x180012c3f  mov     ecx, [rbp+88h]
0x180012c45  call    _XcptFilter_0
0x180012c4a  mov     [rbp+90h], eax
0x180012c50  jmp     short loc_180012C5C
0x180012c52  mov     dword ptr [rbp+90h], 0
0x180012c5c  mov     eax, [rbp+90h]
0x180012c62  add     rsp, 20h
0x180012c66  pop     rbp
0x180012c67  retn
0x180012c69  push    rbp
0x180012c6b  sub     rsp, 20h
0x180012c6f  mov     rbp, rdx
0x180012c72  mov     rax, [rcx]
0x180012c75  mov     edx, [rax]
0x180012c77  mov     [rbp+0E0h], rcx
0x180012c7e  mov     [rbp+98h], edx
0x180012c84  mov     eax, [rbp+98h]
0x180012c8a  cmp     eax, 0E06D7363h
0x180012c8f  jnz     short loc_180012CAB
0x180012c91  mov     rdx, [rbp+0E0h]
0x180012c98  mov     ecx, [rbp+98h]
0x180012c9e  call    _XcptFilter_0
0x180012ca3  mov     [rbp+0A0h], eax
0x180012ca9  jmp     short loc_180012CB5
0x180012cab  mov     dword ptr [rbp+0A0h], 0
0x180012cb5  mov     eax, [rbp+0A0h]
0x180012cbb  add     rsp, 20h
0x180012cbf  pop     rbp
0x180012cc0  retn
0x180012cc2  push    rbp
0x180012cc4  sub     rsp, 20h
0x180012cc8  mov     rbp, rdx
0x180012ccb  cmp     dword ptr [rbp+118h], 1
0x180012cd2  ja      short loc_180012CDE
0x180012cd4  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
