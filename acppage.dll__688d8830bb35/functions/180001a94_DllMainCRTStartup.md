# __DllMainCRTStartup

- ea: `0x180001a94`
- end: `0x180001ca0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001820`
- `0x180001a94`
- `0x180001fae`
- `0x180008738`
- `0x1800162c0`

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
  if ( (_DWORD)fdwReason || dword_180020500 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180020504 = 1;
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
            if ( dword_180020504 )
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
0x180001a94  mov     [rsp+lpvReserved], r8
0x180001a99  mov     [rsp+arg_8], edx
0x180001a9d  mov     [rsp+arg_0], rcx
0x180001aa2  push    rbx
0x180001aa3  push    rsi
0x180001aa4  push    rdi
0x180001aa5  sub     rsp, 0F0h
0x180001aac  mov     edi, edx
0x180001aae  mov     rsi, rcx
0x180001ab1  mov     ebx, 1
0x180001ab6  cmp     edx, ebx
0x180001ab8  ja      short loc_180001AC0
0x180001aba  mov     cs:__native_dllmain_reason, edx
0x180001ac0  test    edx, edx
0x180001ac2  jnz     short loc_180001AD7
0x180001ac4  cmp     cs:dword_180020500, edx
0x180001aca  jnz     short loc_180001AD7
0x180001acc  xor     ebx, ebx
0x180001ace  mov     [rsp+108h+var_E8], ebx
0x180001ad2  jmp     loc_180001C84
0x180001ad7  lea     eax, [rdx-1]
0x180001ada  cmp     eax, 1
0x180001add  ja      loc_180001B64
0x180001ae3  mov     rax, cs:_pRawDllMain
0x180001aea  test    rax, rax
0x180001aed  jz      short loc_180001B25
0x180001aef  cmp     edx, 1
0x180001af2  jnz     short loc_180001AFA
0x180001af4  mov     cs:dword_180020504, edx
0x180001afa  mov     r8, [rsp+108h+lpvReserved]
0x180001b02  call    cs:__guard_dispatch_icall_fptr
0x180001b08  mov     ebx, eax
0x180001b0a  mov     [rsp+108h+var_E8], eax
0x180001b0e  jmp     short loc_180001B25
0x180001b10  xor     ebx, ebx
0x180001b12  mov     [rsp+108h+var_E8], ebx
0x180001b16  mov     edi, [rsp+108h+arg_8]
0x180001b1d  mov     rsi, [rsp+108h+arg_0]
0x180001b25  test    ebx, ebx
0x180001b27  jz      loc_180001C84
0x180001b2d  mov     r8, [rsp+108h+lpvReserved]
0x180001b35  mov     edx, edi
0x180001b37  mov     rcx, rsi
0x180001b3a  call    _CRT_INIT
0x180001b3f  mov     ebx, eax
0x180001b41  mov     [rsp+108h+var_E8], eax
0x180001b45  jmp     short loc_180001B5C
0x180001b47  xor     ebx, ebx
0x180001b49  mov     [rsp+108h+var_E8], ebx
0x180001b4d  mov     edi, [rsp+108h+arg_8]
0x180001b54  mov     rsi, [rsp+108h+arg_0]
0x180001b5c  test    ebx, ebx
0x180001b5e  jz      loc_180001C84
0x180001b64  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001b6c  mov     edx, edi; fdwReason
0x180001b6e  mov     rcx, rsi; hinstDLL
0x180001b71  call    DllMain
0x180001b76  mov     ebx, eax
0x180001b78  mov     [rsp+108h+var_E8], eax
0x180001b7c  jmp     short loc_180001B93
0x180001b7e  xor     ebx, ebx
0x180001b80  mov     [rsp+108h+var_E8], ebx
0x180001b84  mov     edi, [rsp+108h+arg_8]
0x180001b8b  mov     rsi, [rsp+108h+arg_0]
0x180001b93  cmp     edi, 1
0x180001b96  jnz     short loc_180001C0F
0x180001b98  test    ebx, ebx
0x180001b9a  jnz     short loc_180001C0F
0x180001b9c  xor     r8d, r8d; lpvReserved
0x180001b9f  xor     edx, edx; fdwReason
0x180001ba1  mov     rcx, rsi; hinstDLL
0x180001ba4  call    DllMain
0x180001ba9  jmp     short loc_180001BBE
0x180001bab  mov     edi, [rsp+108h+arg_8]
0x180001bb2  mov     rsi, [rsp+108h+arg_0]
0x180001bba  mov     ebx, [rsp+108h+var_E8]
0x180001bbe  xor     r8d, r8d
0x180001bc1  xor     edx, edx
0x180001bc3  mov     rcx, rsi
0x180001bc6  call    _CRT_INIT
0x180001bcb  jmp     short loc_180001BE0
0x180001bcd  mov     edi, [rsp+108h+arg_8]
0x180001bd4  mov     rsi, [rsp+108h+arg_0]
0x180001bdc  mov     ebx, [rsp+108h+var_E8]
0x180001be0  mov     rax, cs:_pRawDllMain
0x180001be7  test    rax, rax
0x180001bea  jz      short loc_180001C0F
0x180001bec  xor     r8d, r8d
0x180001bef  xor     edx, edx
0x180001bf1  mov     rcx, rsi
0x180001bf4  call    cs:__guard_dispatch_icall_fptr
0x180001bfa  jmp     short loc_180001C0F
0x180001bfc  mov     edi, [rsp+108h+arg_8]
0x180001c03  mov     rsi, [rsp+108h+arg_0]
0x180001c0b  mov     ebx, [rsp+108h+var_E8]
0x180001c0f  test    edi, edi
0x180001c11  jz      short loc_180001C18
0x180001c13  cmp     edi, 3
0x180001c16  jnz     short loc_180001C84
0x180001c18  mov     r8, [rsp+108h+lpvReserved]
0x180001c20  mov     edx, edi
0x180001c22  mov     rcx, rsi
0x180001c25  call    _CRT_INIT
0x180001c2a  mov     ebx, eax
0x180001c2c  mov     [rsp+108h+var_E8], eax
0x180001c30  jmp     short loc_180001C47
0x180001c32  xor     ebx, ebx
0x180001c34  mov     [rsp+108h+var_E8], ebx
0x180001c38  mov     edi, [rsp+108h+arg_8]
0x180001c3f  mov     rsi, [rsp+108h+arg_0]
0x180001c47  mov     rax, cs:_pRawDllMain
0x180001c4e  test    rax, rax
0x180001c51  jz      short loc_180001C84
0x180001c53  cmp     cs:dword_180020504, 0
0x180001c5a  jz      short loc_180001C84
0x180001c5c  mov     r8, [rsp+108h+lpvReserved]
0x180001c64  mov     edx, edi
0x180001c66  mov     rcx, rsi
0x180001c69  call    cs:__guard_dispatch_icall_fptr
0x180001c6f  mov     ebx, eax
0x180001c71  mov     [rsp+108h+var_E8], eax
0x180001c75  jmp     short loc_180001C84
0x180001c77  xor     ebx, ebx
0x180001c79  mov     [rsp+108h+var_E8], ebx
0x180001c7d  mov     edi, [rsp+108h+arg_8]
0x180001c84  cmp     edi, 1
0x180001c87  ja      short loc_180001C93
0x180001c89  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001c93  mov     eax, ebx
0x180001c95  add     rsp, 0F0h
0x180001c9c  pop     rdi
0x180001c9d  pop     rsi
0x180001c9e  pop     rbx
0x180001c9f  retn
0x180016390  push    rbp
0x180016392  sub     rsp, 20h
0x180016396  mov     rbp, rdx
0x180016399  mov     rax, [rcx]
0x18001639c  mov     edx, [rax]
0x18001639e  mov     [rbp+0A8h], rcx
0x1800163a5  mov     [rbp+28h], edx
0x1800163a8  mov     eax, [rbp+28h]
0x1800163ab  cmp     eax, 0E06D7363h
0x1800163b0  jnz     short loc_1800163C6
0x1800163b2  mov     rdx, [rbp+0A8h]
0x1800163b9  mov     ecx, [rbp+28h]
0x1800163bc  call    _XcptFilter_0
0x1800163c1  mov     [rbp+30h], eax
0x1800163c4  jmp     short loc_1800163CD
0x1800163c6  mov     dword ptr [rbp+30h], 0
0x1800163cd  mov     eax, [rbp+30h]
0x1800163d0  add     rsp, 20h
0x1800163d4  pop     rbp
0x1800163d5  retn
0x1800163d7  push    rbp
0x1800163d9  sub     rsp, 20h
0x1800163dd  mov     rbp, rdx
0x1800163e0  mov     rax, [rcx]
0x1800163e3  mov     edx, [rax]
0x1800163e5  mov     [rbp+0B0h], rcx
0x1800163ec  mov     [rbp+38h], edx
0x1800163ef  mov     eax, [rbp+38h]
0x1800163f2  cmp     eax, 0E06D7363h
0x1800163f7  jnz     short loc_18001640D
0x1800163f9  mov     rdx, [rbp+0B0h]
0x180016400  mov     ecx, [rbp+38h]
0x180016403  call    _XcptFilter_0
0x180016408  mov     [rbp+40h], eax
0x18001640b  jmp     short loc_180016414
0x18001640d  mov     dword ptr [rbp+40h], 0
0x180016414  mov     eax, [rbp+40h]
0x180016417  add     rsp, 20h
0x18001641b  pop     rbp
0x18001641c  retn
0x18001641e  push    rbp
0x180016420  sub     rsp, 20h
0x180016424  mov     rbp, rdx
0x180016427  mov     rax, [rcx]
0x18001642a  mov     edx, [rax]
0x18001642c  mov     [rbp+0B8h], rcx
0x180016433  mov     [rbp+48h], edx
0x180016436  mov     eax, [rbp+48h]
0x180016439  cmp     eax, 0E06D7363h
0x18001643e  jnz     short loc_180016454
0x180016440  mov     rdx, [rbp+0B8h]
0x180016447  mov     ecx, [rbp+48h]
0x18001644a  call    _XcptFilter_0
0x18001644f  mov     [rbp+50h], eax
0x180016452  jmp     short loc_18001645B
0x180016454  mov     dword ptr [rbp+50h], 0
0x18001645b  mov     eax, [rbp+50h]
0x18001645e  add     rsp, 20h
0x180016462  pop     rbp
0x180016463  retn
0x180016465  push    rbp
0x180016467  sub     rsp, 20h
0x18001646b  mov     rbp, rdx
0x18001646e  mov     rax, [rcx]
0x180016471  mov     edx, [rax]
0x180016473  mov     [rbp+0C0h], rcx
0x18001647a  mov     [rbp+58h], edx
0x18001647d  mov     eax, [rbp+58h]
0x180016480  cmp     eax, 0E06D7363h
0x180016485  jnz     short loc_18001649B
0x180016487  mov     rdx, [rbp+0C0h]
0x18001648e  mov     ecx, [rbp+58h]
0x180016491  call    _XcptFilter_0
0x180016496  mov     [rbp+60h], eax
0x180016499  jmp     short loc_1800164A2
0x18001649b  mov     dword ptr [rbp+60h], 0
0x1800164a2  mov     eax, [rbp+60h]
0x1800164a5  add     rsp, 20h
0x1800164a9  pop     rbp
0x1800164aa  retn
0x1800164ac  push    rbp
0x1800164ae  sub     rsp, 20h
0x1800164b2  mov     rbp, rdx
0x1800164b5  mov     rax, [rcx]
0x1800164b8  mov     edx, [rax]
0x1800164ba  mov     [rbp+0C8h], rcx
0x1800164c1  mov     [rbp+68h], edx
0x1800164c4  mov     eax, [rbp+68h]
0x1800164c7  cmp     eax, 0E06D7363h
0x1800164cc  jnz     short loc_1800164E2
0x1800164ce  mov     rdx, [rbp+0C8h]
0x1800164d5  mov     ecx, [rbp+68h]
0x1800164d8  call    _XcptFilter_0
0x1800164dd  mov     [rbp+70h], eax
0x1800164e0  jmp     short loc_1800164E9
0x1800164e2  mov     dword ptr [rbp+70h], 0
0x1800164e9  mov     eax, [rbp+70h]
0x1800164ec  add     rsp, 20h
0x1800164f0  pop     rbp
0x1800164f1  retn
0x1800164f3  push    rbp
0x1800164f5  sub     rsp, 20h
0x1800164f9  mov     rbp, rdx
0x1800164fc  mov     rax, [rcx]
0x1800164ff  mov     edx, [rax]
0x180016501  mov     [rbp+0D0h], rcx
0x180016508  mov     [rbp+78h], edx
0x18001650b  mov     eax, [rbp+78h]
0x18001650e  cmp     eax, 0E06D7363h
0x180016513  jnz     short loc_18001652C
0x180016515  mov     rdx, [rbp+0D0h]
0x18001651c  mov     ecx, [rbp+78h]
0x18001651f  call    _XcptFilter_0
0x180016524  mov     [rbp+80h], eax
0x18001652a  jmp     short loc_180016536
0x18001652c  mov     dword ptr [rbp+80h], 0
0x180016536  mov     eax, [rbp+80h]
0x18001653c  add     rsp, 20h
0x180016540  pop     rbp
0x180016541  retn
0x180016543  push    rbp
0x180016545  sub     rsp, 20h
0x180016549  mov     rbp, rdx
0x18001654c  mov     rax, [rcx]
0x18001654f  mov     edx, [rax]
0x180016551  mov     [rbp+0D8h], rcx
0x180016558  mov     [rbp+88h], edx
0x18001655e  mov     eax, [rbp+88h]
0x180016564  cmp     eax, 0E06D7363h
0x180016569  jnz     short loc_180016585
0x18001656b  mov     rdx, [rbp+0D8h]
0x180016572  mov     ecx, [rbp+88h]
0x180016578  call    _XcptFilter_0
0x18001657d  mov     [rbp+90h], eax
0x180016583  jmp     short loc_18001658F
0x180016585  mov     dword ptr [rbp+90h], 0
0x18001658f  mov     eax, [rbp+90h]
0x180016595  add     rsp, 20h
0x180016599  pop     rbp
0x18001659a  retn
0x18001659c  push    rbp
0x18001659e  sub     rsp, 20h
0x1800165a2  mov     rbp, rdx
0x1800165a5  mov     rax, [rcx]
0x1800165a8  mov     edx, [rax]
0x1800165aa  mov     [rbp+0E0h], rcx
0x1800165b1  mov     [rbp+98h], edx
0x1800165b7  mov     eax, [rbp+98h]
0x1800165bd  cmp     eax, 0E06D7363h
0x1800165c2  jnz     short loc_1800165DE
0x1800165c4  mov     rdx, [rbp+0E0h]
0x1800165cb  mov     ecx, [rbp+98h]
0x1800165d1  call    _XcptFilter_0
0x1800165d6  mov     [rbp+0A0h], eax
0x1800165dc  jmp     short loc_1800165E8
0x1800165de  mov     dword ptr [rbp+0A0h], 0
0x1800165e8  mov     eax, [rbp+0A0h]
0x1800165ee  add     rsp, 20h
0x1800165f2  pop     rbp
0x1800165f3  retn
0x1800165f5  push    rbp
0x1800165f7  sub     rsp, 20h
0x1800165fb  mov     rbp, rdx
0x1800165fe  cmp     dword ptr [rbp+118h], 1
0x180016605  ja      short loc_180016611
0x180016607  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
