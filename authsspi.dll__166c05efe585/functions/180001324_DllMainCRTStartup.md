# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x18000155a`
- `0x1800058e0`
- `0x180008be0`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(SSPI_AUTH_PROVIDER *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int SupportsAuthPersistence; // ebx

  v3 = a2;
  SupportsAuthPersistence = 1;
  if ( (unsigned int)a2 <= 1 )
    _native_dllmain_reason = a2;
  if ( (_DWORD)a2 || dword_18000E0A0 )
  {
    if ( (unsigned int)(a2 - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)a2 == 1 )
        dword_18000E0A4 = 1;
      SupportsAuthPersistence = pRawDllMain(this, a2, a3);
    }
    if ( SupportsAuthPersistence )
    {
      SupportsAuthPersistence = CRT_INIT(this, v3, a3);
      if ( SupportsAuthPersistence )
      {
LABEL_13:
        SupportsAuthPersistence = SSPI_AUTH_PROVIDER::QuerySupportsAuthPersistence(this);
        if ( v3 == 1 && !SupportsAuthPersistence )
        {
          SSPI_AUTH_PROVIDER::QuerySupportsAuthPersistence(this);
          CRT_INIT(this, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(this, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          SupportsAuthPersistence = CRT_INIT(this, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18000E0A4 )
              SupportsAuthPersistence = pRawDllMain(this, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    SupportsAuthPersistence = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return SupportsAuthPersistence;
}

```

## disassembly

```asm
0x180001324  mov     [rsp+arg_10], r8
0x180001329  mov     [rsp+arg_8], edx
0x18000132d  mov     [rsp+arg_0], rcx
0x180001332  push    rbx
0x180001333  push    rsi
0x180001334  push    rdi
0x180001335  sub     rsp, 0F0h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  cmp     edx, ebx
0x180001348  ja      short loc_180001350
0x18000134a  mov     cs:__native_dllmain_reason, edx
0x180001350  test    edx, edx
0x180001352  jnz     short loc_180001367
0x180001354  cmp     cs:dword_18000E0A0, edx
0x18000135a  jnz     short loc_180001367
0x18000135c  xor     ebx, ebx
0x18000135e  mov     [rsp+108h+var_E8], ebx
0x180001362  jmp     loc_180001514
0x180001367  lea     eax, [rdx-1]
0x18000136a  cmp     eax, 1
0x18000136d  ja      loc_1800013F4
0x180001373  mov     rax, cs:_pRawDllMain
0x18000137a  test    rax, rax
0x18000137d  jz      short loc_1800013B5
0x18000137f  cmp     edx, 1
0x180001382  jnz     short loc_18000138A
0x180001384  mov     cs:dword_18000E0A4, edx
0x18000138a  mov     r8, [rsp+108h+arg_10]
0x180001392  call    cs:__guard_dispatch_icall_fptr
0x180001398  mov     ebx, eax
0x18000139a  mov     [rsp+108h+var_E8], eax
0x18000139e  jmp     short loc_1800013B5
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+108h+var_E8], ebx
0x1800013a6  mov     edi, [rsp+108h+arg_8]
0x1800013ad  mov     rsi, [rsp+108h+arg_0]
0x1800013b5  test    ebx, ebx
0x1800013b7  jz      loc_180001514
0x1800013bd  mov     r8, [rsp+108h+arg_10]
0x1800013c5  mov     edx, edi
0x1800013c7  mov     rcx, rsi
0x1800013ca  call    _CRT_INIT
0x1800013cf  mov     ebx, eax
0x1800013d1  mov     [rsp+108h+var_E8], eax
0x1800013d5  jmp     short loc_1800013EC
0x1800013d7  xor     ebx, ebx
0x1800013d9  mov     [rsp+108h+var_E8], ebx
0x1800013dd  mov     edi, [rsp+108h+arg_8]
0x1800013e4  mov     rsi, [rsp+108h+arg_0]
0x1800013ec  test    ebx, ebx
0x1800013ee  jz      loc_180001514
0x1800013f4  mov     r8, [rsp+108h+arg_10]
0x1800013fc  mov     edx, edi
0x1800013fe  mov     rcx, rsi; this
0x180001401  call    ?QuerySupportsAuthPersistence@SSPI_AUTH_PROVIDER@@UEBAHXZ; SSPI_AUTH_PROVIDER::QuerySupportsAuthPersistence(void)
0x180001406  mov     ebx, eax
0x180001408  mov     [rsp+108h+var_E8], eax
0x18000140c  jmp     short loc_180001423
0x18000140e  xor     ebx, ebx
0x180001410  mov     [rsp+108h+var_E8], ebx
0x180001414  mov     edi, [rsp+108h+arg_8]
0x18000141b  mov     rsi, [rsp+108h+arg_0]
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000149F
0x180001428  test    ebx, ebx
0x18000142a  jnz     short loc_18000149F
0x18000142c  xor     r8d, r8d
0x18000142f  xor     edx, edx
0x180001431  mov     rcx, rsi; this
0x180001434  call    ?QuerySupportsAuthPersistence@SSPI_AUTH_PROVIDER@@UEBAHXZ; SSPI_AUTH_PROVIDER::QuerySupportsAuthPersistence(void)
0x180001439  jmp     short loc_18000144E
0x18000143b  mov     edi, [rsp+108h+arg_8]
0x180001442  mov     rsi, [rsp+108h+arg_0]
0x18000144a  mov     ebx, [rsp+108h+var_E8]
0x18000144e  xor     r8d, r8d
0x180001451  xor     edx, edx
0x180001453  mov     rcx, rsi
0x180001456  call    _CRT_INIT
0x18000145b  jmp     short loc_180001470
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  mov     ebx, [rsp+108h+var_E8]
0x180001470  mov     rax, cs:_pRawDllMain
0x180001477  test    rax, rax
0x18000147a  jz      short loc_18000149F
0x18000147c  xor     r8d, r8d
0x18000147f  xor     edx, edx
0x180001481  mov     rcx, rsi
0x180001484  call    cs:__guard_dispatch_icall_fptr
0x18000148a  jmp     short loc_18000149F
0x18000148c  mov     edi, [rsp+108h+arg_8]
0x180001493  mov     rsi, [rsp+108h+arg_0]
0x18000149b  mov     ebx, [rsp+108h+var_E8]
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_180001514
0x1800014a8  mov     r8, [rsp+108h+arg_10]
0x1800014b0  mov     edx, edi
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    _CRT_INIT
0x1800014ba  mov     ebx, eax
0x1800014bc  mov     [rsp+108h+var_E8], eax
0x1800014c0  jmp     short loc_1800014D7
0x1800014c2  xor     ebx, ebx
0x1800014c4  mov     [rsp+108h+var_E8], ebx
0x1800014c8  mov     edi, [rsp+108h+arg_8]
0x1800014cf  mov     rsi, [rsp+108h+arg_0]
0x1800014d7  mov     rax, cs:_pRawDllMain
0x1800014de  test    rax, rax
0x1800014e1  jz      short loc_180001514
0x1800014e3  cmp     cs:dword_18000E0A4, 0
0x1800014ea  jz      short loc_180001514
0x1800014ec  mov     r8, [rsp+108h+arg_10]
0x1800014f4  mov     edx, edi
0x1800014f6  mov     rcx, rsi
0x1800014f9  call    cs:__guard_dispatch_icall_fptr
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_180001514
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  cmp     edi, 1
0x180001517  ja      short loc_180001523
0x180001519  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001523  mov     eax, ebx
0x180001525  add     rsp, 0F0h
0x18000152c  pop     rdi
0x18000152d  pop     rsi
0x18000152e  pop     rbx
0x18000152f  retn
0x180008c50  push    rbp
0x180008c52  sub     rsp, 20h
0x180008c56  mov     rbp, rdx
0x180008c59  mov     rax, [rcx]
0x180008c5c  mov     edx, [rax]
0x180008c5e  mov     [rbp+0A8h], rcx
0x180008c65  mov     [rbp+28h], edx
0x180008c68  mov     eax, [rbp+28h]
0x180008c6b  cmp     eax, 0E06D7363h
0x180008c70  jnz     short loc_180008C86
0x180008c72  mov     rdx, [rbp+0A8h]
0x180008c79  mov     ecx, [rbp+28h]
0x180008c7c  call    _XcptFilter_0
0x180008c81  mov     [rbp+30h], eax
0x180008c84  jmp     short loc_180008C8D
0x180008c86  mov     dword ptr [rbp+30h], 0
0x180008c8d  mov     eax, [rbp+30h]
0x180008c90  add     rsp, 20h
0x180008c94  pop     rbp
0x180008c95  retn
0x180008c97  push    rbp
0x180008c99  sub     rsp, 20h
0x180008c9d  mov     rbp, rdx
0x180008ca0  mov     rax, [rcx]
0x180008ca3  mov     edx, [rax]
0x180008ca5  mov     [rbp+0B0h], rcx
0x180008cac  mov     [rbp+38h], edx
0x180008caf  mov     eax, [rbp+38h]
0x180008cb2  cmp     eax, 0E06D7363h
0x180008cb7  jnz     short loc_180008CCD
0x180008cb9  mov     rdx, [rbp+0B0h]
0x180008cc0  mov     ecx, [rbp+38h]
0x180008cc3  call    _XcptFilter_0
0x180008cc8  mov     [rbp+40h], eax
0x180008ccb  jmp     short loc_180008CD4
0x180008ccd  mov     dword ptr [rbp+40h], 0
0x180008cd4  mov     eax, [rbp+40h]
0x180008cd7  add     rsp, 20h
0x180008cdb  pop     rbp
0x180008cdc  retn
0x180008cde  push    rbp
0x180008ce0  sub     rsp, 20h
0x180008ce4  mov     rbp, rdx
0x180008ce7  mov     rax, [rcx]
0x180008cea  mov     edx, [rax]
0x180008cec  mov     [rbp+0B8h], rcx
0x180008cf3  mov     [rbp+48h], edx
0x180008cf6  mov     eax, [rbp+48h]
0x180008cf9  cmp     eax, 0E06D7363h
0x180008cfe  jnz     short loc_180008D14
0x180008d00  mov     rdx, [rbp+0B8h]
0x180008d07  mov     ecx, [rbp+48h]
0x180008d0a  call    _XcptFilter_0
0x180008d0f  mov     [rbp+50h], eax
0x180008d12  jmp     short loc_180008D1B
0x180008d14  mov     dword ptr [rbp+50h], 0
0x180008d1b  mov     eax, [rbp+50h]
0x180008d1e  add     rsp, 20h
0x180008d22  pop     rbp
0x180008d23  retn
0x180008d25  push    rbp
0x180008d27  sub     rsp, 20h
0x180008d2b  mov     rbp, rdx
0x180008d2e  mov     rax, [rcx]
0x180008d31  mov     edx, [rax]
0x180008d33  mov     [rbp+0C0h], rcx
0x180008d3a  mov     [rbp+58h], edx
0x180008d3d  mov     eax, [rbp+58h]
0x180008d40  cmp     eax, 0E06D7363h
0x180008d45  jnz     short loc_180008D5B
0x180008d47  mov     rdx, [rbp+0C0h]
0x180008d4e  mov     ecx, [rbp+58h]
0x180008d51  call    _XcptFilter_0
0x180008d56  mov     [rbp+60h], eax
0x180008d59  jmp     short loc_180008D62
0x180008d5b  mov     dword ptr [rbp+60h], 0
0x180008d62  mov     eax, [rbp+60h]
0x180008d65  add     rsp, 20h
0x180008d69  pop     rbp
0x180008d6a  retn
0x180008d6c  push    rbp
0x180008d6e  sub     rsp, 20h
0x180008d72  mov     rbp, rdx
0x180008d75  mov     rax, [rcx]
0x180008d78  mov     edx, [rax]
0x180008d7a  mov     [rbp+0C8h], rcx
0x180008d81  mov     [rbp+68h], edx
0x180008d84  mov     eax, [rbp+68h]
0x180008d87  cmp     eax, 0E06D7363h
0x180008d8c  jnz     short loc_180008DA2
0x180008d8e  mov     rdx, [rbp+0C8h]
0x180008d95  mov     ecx, [rbp+68h]
0x180008d98  call    _XcptFilter_0
0x180008d9d  mov     [rbp+70h], eax
0x180008da0  jmp     short loc_180008DA9
0x180008da2  mov     dword ptr [rbp+70h], 0
0x180008da9  mov     eax, [rbp+70h]
0x180008dac  add     rsp, 20h
0x180008db0  pop     rbp
0x180008db1  retn
0x180008db3  push    rbp
0x180008db5  sub     rsp, 20h
0x180008db9  mov     rbp, rdx
0x180008dbc  mov     rax, [rcx]
0x180008dbf  mov     edx, [rax]
0x180008dc1  mov     [rbp+0D0h], rcx
0x180008dc8  mov     [rbp+78h], edx
0x180008dcb  mov     eax, [rbp+78h]
0x180008dce  cmp     eax, 0E06D7363h
0x180008dd3  jnz     short loc_180008DEC
0x180008dd5  mov     rdx, [rbp+0D0h]
0x180008ddc  mov     ecx, [rbp+78h]
0x180008ddf  call    _XcptFilter_0
0x180008de4  mov     [rbp+80h], eax
0x180008dea  jmp     short loc_180008DF6
0x180008dec  mov     dword ptr [rbp+80h], 0
0x180008df6  mov     eax, [rbp+80h]
0x180008dfc  add     rsp, 20h
0x180008e00  pop     rbp
0x180008e01  retn
0x180008e03  push    rbp
0x180008e05  sub     rsp, 20h
0x180008e09  mov     rbp, rdx
0x180008e0c  mov     rax, [rcx]
0x180008e0f  mov     edx, [rax]
0x180008e11  mov     [rbp+0D8h], rcx
0x180008e18  mov     [rbp+88h], edx
0x180008e1e  mov     eax, [rbp+88h]
0x180008e24  cmp     eax, 0E06D7363h
0x180008e29  jnz     short loc_180008E45
0x180008e2b  mov     rdx, [rbp+0D8h]
0x180008e32  mov     ecx, [rbp+88h]
0x180008e38  call    _XcptFilter_0
0x180008e3d  mov     [rbp+90h], eax
0x180008e43  jmp     short loc_180008E4F
0x180008e45  mov     dword ptr [rbp+90h], 0
0x180008e4f  mov     eax, [rbp+90h]
0x180008e55  add     rsp, 20h
0x180008e59  pop     rbp
0x180008e5a  retn
0x180008e5c  push    rbp
0x180008e5e  sub     rsp, 20h
0x180008e62  mov     rbp, rdx
0x180008e65  mov     rax, [rcx]
0x180008e68  mov     edx, [rax]
0x180008e6a  mov     [rbp+0E0h], rcx
0x180008e71  mov     [rbp+98h], edx
0x180008e77  mov     eax, [rbp+98h]
0x180008e7d  cmp     eax, 0E06D7363h
0x180008e82  jnz     short loc_180008E9E
0x180008e84  mov     rdx, [rbp+0E0h]
0x180008e8b  mov     ecx, [rbp+98h]
0x180008e91  call    _XcptFilter_0
0x180008e96  mov     [rbp+0A0h], eax
0x180008e9c  jmp     short loc_180008EA8
0x180008e9e  mov     dword ptr [rbp+0A0h], 0
0x180008ea8  mov     eax, [rbp+0A0h]
0x180008eae  add     rsp, 20h
0x180008eb2  pop     rbp
0x180008eb3  retn
0x180008eb5  push    rbp
0x180008eb7  sub     rsp, 20h
0x180008ebb  mov     rbp, rdx
0x180008ebe  cmp     dword ptr [rbp+118h], 1
0x180008ec5  ja      short loc_180008ED1
0x180008ec7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
