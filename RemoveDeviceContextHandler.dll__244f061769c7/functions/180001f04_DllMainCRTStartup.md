# __DllMainCRTStartup

- ea: `0x180001f04`
- end: `0x180002110`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ec0`

## callees

- `0x180001c90`
- `0x180001f04`
- `0x180002681`
- `0x18000c41c`
- `0x18000c9d0`

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
  if ( (_DWORD)fdwReason || dword_180014320 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014324 = 1;
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
            if ( dword_180014324 )
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
0x180001f04  mov     [rsp+lpvReserved], r8
0x180001f09  mov     [rsp+arg_8], edx
0x180001f0d  mov     [rsp+arg_0], rcx
0x180001f12  push    rbx
0x180001f13  push    rsi
0x180001f14  push    rdi
0x180001f15  sub     rsp, 0F0h
0x180001f1c  mov     edi, edx
0x180001f1e  mov     rsi, rcx
0x180001f21  mov     ebx, 1
0x180001f26  cmp     edx, ebx
0x180001f28  ja      short loc_180001F30
0x180001f2a  mov     cs:__native_dllmain_reason, edx
0x180001f30  test    edx, edx
0x180001f32  jnz     short loc_180001F47
0x180001f34  cmp     cs:dword_180014320, edx
0x180001f3a  jnz     short loc_180001F47
0x180001f3c  xor     ebx, ebx
0x180001f3e  mov     [rsp+108h+var_E8], ebx
0x180001f42  jmp     loc_1800020F4
0x180001f47  lea     eax, [rdx-1]
0x180001f4a  cmp     eax, 1
0x180001f4d  ja      loc_180001FD4
0x180001f53  mov     rax, cs:_pRawDllMain
0x180001f5a  test    rax, rax
0x180001f5d  jz      short loc_180001F95
0x180001f5f  cmp     edx, 1
0x180001f62  jnz     short loc_180001F6A
0x180001f64  mov     cs:dword_180014324, edx
0x180001f6a  mov     r8, [rsp+108h+lpvReserved]
0x180001f72  call    cs:__guard_dispatch_icall_fptr
0x180001f78  mov     ebx, eax
0x180001f7a  mov     [rsp+108h+var_E8], eax
0x180001f7e  jmp     short loc_180001F95
0x180001f80  xor     ebx, ebx
0x180001f82  mov     [rsp+108h+var_E8], ebx
0x180001f86  mov     edi, [rsp+108h+arg_8]
0x180001f8d  mov     rsi, [rsp+108h+arg_0]
0x180001f95  test    ebx, ebx
0x180001f97  jz      loc_1800020F4
0x180001f9d  mov     r8, [rsp+108h+lpvReserved]
0x180001fa5  mov     edx, edi
0x180001fa7  mov     rcx, rsi
0x180001faa  call    _CRT_INIT
0x180001faf  mov     ebx, eax
0x180001fb1  mov     [rsp+108h+var_E8], eax
0x180001fb5  jmp     short loc_180001FCC
0x180001fb7  xor     ebx, ebx
0x180001fb9  mov     [rsp+108h+var_E8], ebx
0x180001fbd  mov     edi, [rsp+108h+arg_8]
0x180001fc4  mov     rsi, [rsp+108h+arg_0]
0x180001fcc  test    ebx, ebx
0x180001fce  jz      loc_1800020F4
0x180001fd4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001fdc  mov     edx, edi; fdwReason
0x180001fde  mov     rcx, rsi; hinstDLL
0x180001fe1  call    DllMain
0x180001fe6  mov     ebx, eax
0x180001fe8  mov     [rsp+108h+var_E8], eax
0x180001fec  jmp     short loc_180002003
0x180001fee  xor     ebx, ebx
0x180001ff0  mov     [rsp+108h+var_E8], ebx
0x180001ff4  mov     edi, [rsp+108h+arg_8]
0x180001ffb  mov     rsi, [rsp+108h+arg_0]
0x180002003  cmp     edi, 1
0x180002006  jnz     short loc_18000207F
0x180002008  test    ebx, ebx
0x18000200a  jnz     short loc_18000207F
0x18000200c  xor     r8d, r8d; lpvReserved
0x18000200f  xor     edx, edx; fdwReason
0x180002011  mov     rcx, rsi; hinstDLL
0x180002014  call    DllMain
0x180002019  jmp     short loc_18000202E
0x18000201b  mov     edi, [rsp+108h+arg_8]
0x180002022  mov     rsi, [rsp+108h+arg_0]
0x18000202a  mov     ebx, [rsp+108h+var_E8]
0x18000202e  xor     r8d, r8d
0x180002031  xor     edx, edx
0x180002033  mov     rcx, rsi
0x180002036  call    _CRT_INIT
0x18000203b  jmp     short loc_180002050
0x18000203d  mov     edi, [rsp+108h+arg_8]
0x180002044  mov     rsi, [rsp+108h+arg_0]
0x18000204c  mov     ebx, [rsp+108h+var_E8]
0x180002050  mov     rax, cs:_pRawDllMain
0x180002057  test    rax, rax
0x18000205a  jz      short loc_18000207F
0x18000205c  xor     r8d, r8d
0x18000205f  xor     edx, edx
0x180002061  mov     rcx, rsi
0x180002064  call    cs:__guard_dispatch_icall_fptr
0x18000206a  jmp     short loc_18000207F
0x18000206c  mov     edi, [rsp+108h+arg_8]
0x180002073  mov     rsi, [rsp+108h+arg_0]
0x18000207b  mov     ebx, [rsp+108h+var_E8]
0x18000207f  test    edi, edi
0x180002081  jz      short loc_180002088
0x180002083  cmp     edi, 3
0x180002086  jnz     short loc_1800020F4
0x180002088  mov     r8, [rsp+108h+lpvReserved]
0x180002090  mov     edx, edi
0x180002092  mov     rcx, rsi
0x180002095  call    _CRT_INIT
0x18000209a  mov     ebx, eax
0x18000209c  mov     [rsp+108h+var_E8], eax
0x1800020a0  jmp     short loc_1800020B7
0x1800020a2  xor     ebx, ebx
0x1800020a4  mov     [rsp+108h+var_E8], ebx
0x1800020a8  mov     edi, [rsp+108h+arg_8]
0x1800020af  mov     rsi, [rsp+108h+arg_0]
0x1800020b7  mov     rax, cs:_pRawDllMain
0x1800020be  test    rax, rax
0x1800020c1  jz      short loc_1800020F4
0x1800020c3  cmp     cs:dword_180014324, 0
0x1800020ca  jz      short loc_1800020F4
0x1800020cc  mov     r8, [rsp+108h+lpvReserved]
0x1800020d4  mov     edx, edi
0x1800020d6  mov     rcx, rsi
0x1800020d9  call    cs:__guard_dispatch_icall_fptr
0x1800020df  mov     ebx, eax
0x1800020e1  mov     [rsp+108h+var_E8], eax
0x1800020e5  jmp     short loc_1800020F4
0x1800020e7  xor     ebx, ebx
0x1800020e9  mov     [rsp+108h+var_E8], ebx
0x1800020ed  mov     edi, [rsp+108h+arg_8]
0x1800020f4  cmp     edi, 1
0x1800020f7  ja      short loc_180002103
0x1800020f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002103  mov     eax, ebx
0x180002105  add     rsp, 0F0h
0x18000210c  pop     rdi
0x18000210d  pop     rsi
0x18000210e  pop     rbx
0x18000210f  retn
0x18000caa0  push    rbp
0x18000caa2  sub     rsp, 20h
0x18000caa6  mov     rbp, rdx
0x18000caa9  mov     rax, [rcx]
0x18000caac  mov     edx, [rax]
0x18000caae  mov     [rbp+0A8h], rcx
0x18000cab5  mov     [rbp+28h], edx
0x18000cab8  mov     eax, [rbp+28h]
0x18000cabb  cmp     eax, 0E06D7363h
0x18000cac0  jnz     short loc_18000CAD6
0x18000cac2  mov     rdx, [rbp+0A8h]
0x18000cac9  mov     ecx, [rbp+28h]
0x18000cacc  call    _XcptFilter_0
0x18000cad1  mov     [rbp+30h], eax
0x18000cad4  jmp     short loc_18000CADD
0x18000cad6  mov     dword ptr [rbp+30h], 0
0x18000cadd  mov     eax, [rbp+30h]
0x18000cae0  add     rsp, 20h
0x18000cae4  pop     rbp
0x18000cae5  retn
0x18000cae7  push    rbp
0x18000cae9  sub     rsp, 20h
0x18000caed  mov     rbp, rdx
0x18000caf0  mov     rax, [rcx]
0x18000caf3  mov     edx, [rax]
0x18000caf5  mov     [rbp+0B0h], rcx
0x18000cafc  mov     [rbp+38h], edx
0x18000caff  mov     eax, [rbp+38h]
0x18000cb02  cmp     eax, 0E06D7363h
0x18000cb07  jnz     short loc_18000CB1D
0x18000cb09  mov     rdx, [rbp+0B0h]
0x18000cb10  mov     ecx, [rbp+38h]
0x18000cb13  call    _XcptFilter_0
0x18000cb18  mov     [rbp+40h], eax
0x18000cb1b  jmp     short loc_18000CB24
0x18000cb1d  mov     dword ptr [rbp+40h], 0
0x18000cb24  mov     eax, [rbp+40h]
0x18000cb27  add     rsp, 20h
0x18000cb2b  pop     rbp
0x18000cb2c  retn
0x18000cb2e  push    rbp
0x18000cb30  sub     rsp, 20h
0x18000cb34  mov     rbp, rdx
0x18000cb37  mov     rax, [rcx]
0x18000cb3a  mov     edx, [rax]
0x18000cb3c  mov     [rbp+0B8h], rcx
0x18000cb43  mov     [rbp+48h], edx
0x18000cb46  mov     eax, [rbp+48h]
0x18000cb49  cmp     eax, 0E06D7363h
0x18000cb4e  jnz     short loc_18000CB64
0x18000cb50  mov     rdx, [rbp+0B8h]
0x18000cb57  mov     ecx, [rbp+48h]
0x18000cb5a  call    _XcptFilter_0
0x18000cb5f  mov     [rbp+50h], eax
0x18000cb62  jmp     short loc_18000CB6B
0x18000cb64  mov     dword ptr [rbp+50h], 0
0x18000cb6b  mov     eax, [rbp+50h]
0x18000cb6e  add     rsp, 20h
0x18000cb72  pop     rbp
0x18000cb73  retn
0x18000cb75  push    rbp
0x18000cb77  sub     rsp, 20h
0x18000cb7b  mov     rbp, rdx
0x18000cb7e  mov     rax, [rcx]
0x18000cb81  mov     edx, [rax]
0x18000cb83  mov     [rbp+0C0h], rcx
0x18000cb8a  mov     [rbp+58h], edx
0x18000cb8d  mov     eax, [rbp+58h]
0x18000cb90  cmp     eax, 0E06D7363h
0x18000cb95  jnz     short loc_18000CBAB
0x18000cb97  mov     rdx, [rbp+0C0h]
0x18000cb9e  mov     ecx, [rbp+58h]
0x18000cba1  call    _XcptFilter_0
0x18000cba6  mov     [rbp+60h], eax
0x18000cba9  jmp     short loc_18000CBB2
0x18000cbab  mov     dword ptr [rbp+60h], 0
0x18000cbb2  mov     eax, [rbp+60h]
0x18000cbb5  add     rsp, 20h
0x18000cbb9  pop     rbp
0x18000cbba  retn
0x18000cbbc  push    rbp
0x18000cbbe  sub     rsp, 20h
0x18000cbc2  mov     rbp, rdx
0x18000cbc5  mov     rax, [rcx]
0x18000cbc8  mov     edx, [rax]
0x18000cbca  mov     [rbp+0C8h], rcx
0x18000cbd1  mov     [rbp+68h], edx
0x18000cbd4  mov     eax, [rbp+68h]
0x18000cbd7  cmp     eax, 0E06D7363h
0x18000cbdc  jnz     short loc_18000CBF2
0x18000cbde  mov     rdx, [rbp+0C8h]
0x18000cbe5  mov     ecx, [rbp+68h]
0x18000cbe8  call    _XcptFilter_0
0x18000cbed  mov     [rbp+70h], eax
0x18000cbf0  jmp     short loc_18000CBF9
0x18000cbf2  mov     dword ptr [rbp+70h], 0
0x18000cbf9  mov     eax, [rbp+70h]
0x18000cbfc  add     rsp, 20h
0x18000cc00  pop     rbp
0x18000cc01  retn
0x18000cc03  push    rbp
0x18000cc05  sub     rsp, 20h
0x18000cc09  mov     rbp, rdx
0x18000cc0c  mov     rax, [rcx]
0x18000cc0f  mov     edx, [rax]
0x18000cc11  mov     [rbp+0D0h], rcx
0x18000cc18  mov     [rbp+78h], edx
0x18000cc1b  mov     eax, [rbp+78h]
0x18000cc1e  cmp     eax, 0E06D7363h
0x18000cc23  jnz     short loc_18000CC3C
0x18000cc25  mov     rdx, [rbp+0D0h]
0x18000cc2c  mov     ecx, [rbp+78h]
0x18000cc2f  call    _XcptFilter_0
0x18000cc34  mov     [rbp+80h], eax
0x18000cc3a  jmp     short loc_18000CC46
0x18000cc3c  mov     dword ptr [rbp+80h], 0
0x18000cc46  mov     eax, [rbp+80h]
0x18000cc4c  add     rsp, 20h
0x18000cc50  pop     rbp
0x18000cc51  retn
0x18000cc53  push    rbp
0x18000cc55  sub     rsp, 20h
0x18000cc59  mov     rbp, rdx
0x18000cc5c  mov     rax, [rcx]
0x18000cc5f  mov     edx, [rax]
0x18000cc61  mov     [rbp+0D8h], rcx
0x18000cc68  mov     [rbp+88h], edx
0x18000cc6e  mov     eax, [rbp+88h]
0x18000cc74  cmp     eax, 0E06D7363h
0x18000cc79  jnz     short loc_18000CC95
0x18000cc7b  mov     rdx, [rbp+0D8h]
0x18000cc82  mov     ecx, [rbp+88h]
0x18000cc88  call    _XcptFilter_0
0x18000cc8d  mov     [rbp+90h], eax
0x18000cc93  jmp     short loc_18000CC9F
0x18000cc95  mov     dword ptr [rbp+90h], 0
0x18000cc9f  mov     eax, [rbp+90h]
0x18000cca5  add     rsp, 20h
0x18000cca9  pop     rbp
0x18000ccaa  retn
0x18000ccac  push    rbp
0x18000ccae  sub     rsp, 20h
0x18000ccb2  mov     rbp, rdx
0x18000ccb5  mov     rax, [rcx]
0x18000ccb8  mov     edx, [rax]
0x18000ccba  mov     [rbp+0E0h], rcx
0x18000ccc1  mov     [rbp+98h], edx
0x18000ccc7  mov     eax, [rbp+98h]
0x18000cccd  cmp     eax, 0E06D7363h
0x18000ccd2  jnz     short loc_18000CCEE
0x18000ccd4  mov     rdx, [rbp+0E0h]
0x18000ccdb  mov     ecx, [rbp+98h]
0x18000cce1  call    _XcptFilter_0
0x18000cce6  mov     [rbp+0A0h], eax
0x18000ccec  jmp     short loc_18000CCF8
0x18000ccee  mov     dword ptr [rbp+0A0h], 0
0x18000ccf8  mov     eax, [rbp+0A0h]
0x18000ccfe  add     rsp, 20h
0x18000cd02  pop     rbp
0x18000cd03  retn
0x18000cd05  push    rbp
0x18000cd07  sub     rsp, 20h
0x18000cd0b  mov     rbp, rdx
0x18000cd0e  cmp     dword ptr [rbp+118h], 1
0x18000cd15  ja      short loc_18000CD21
0x18000cd17  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
