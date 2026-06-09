# __DllMainCRTStartup

- ea: `0x180008b14`
- end: `0x180008d20`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008ad0`

## callees

- `0x1800088a0`
- `0x180008b14`
- `0x180008fe6`
- `0x1800091b8`
- `0x18001bd30`

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
  if ( (_DWORD)fdwReason || dword_18002D240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002D244 = 1;
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
            if ( dword_18002D244 )
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
0x180008b14  mov     [rsp+lpvReserved], r8
0x180008b19  mov     [rsp+arg_8], edx
0x180008b1d  mov     [rsp+arg_0], rcx
0x180008b22  push    rbx
0x180008b23  push    rsi
0x180008b24  push    rdi
0x180008b25  sub     rsp, 0F0h
0x180008b2c  mov     edi, edx
0x180008b2e  mov     rsi, rcx
0x180008b31  mov     ebx, 1
0x180008b36  cmp     edx, ebx
0x180008b38  ja      short loc_180008B40
0x180008b3a  mov     cs:__native_dllmain_reason, edx
0x180008b40  test    edx, edx
0x180008b42  jnz     short loc_180008B57
0x180008b44  cmp     cs:dword_18002D240, edx
0x180008b4a  jnz     short loc_180008B57
0x180008b4c  xor     ebx, ebx
0x180008b4e  mov     [rsp+108h+var_E8], ebx
0x180008b52  jmp     loc_180008D04
0x180008b57  lea     eax, [rdx-1]
0x180008b5a  cmp     eax, 1
0x180008b5d  ja      loc_180008BE4
0x180008b63  mov     rax, cs:_pRawDllMain
0x180008b6a  test    rax, rax
0x180008b6d  jz      short loc_180008BA5
0x180008b6f  cmp     edx, 1
0x180008b72  jnz     short loc_180008B7A
0x180008b74  mov     cs:dword_18002D244, edx
0x180008b7a  mov     r8, [rsp+108h+lpvReserved]
0x180008b82  call    cs:__guard_dispatch_icall_fptr
0x180008b88  mov     ebx, eax
0x180008b8a  mov     [rsp+108h+var_E8], eax
0x180008b8e  jmp     short loc_180008BA5
0x180008b90  xor     ebx, ebx
0x180008b92  mov     [rsp+108h+var_E8], ebx
0x180008b96  mov     edi, [rsp+108h+arg_8]
0x180008b9d  mov     rsi, [rsp+108h+arg_0]
0x180008ba5  test    ebx, ebx
0x180008ba7  jz      loc_180008D04
0x180008bad  mov     r8, [rsp+108h+lpvReserved]
0x180008bb5  mov     edx, edi
0x180008bb7  mov     rcx, rsi
0x180008bba  call    _CRT_INIT
0x180008bbf  mov     ebx, eax
0x180008bc1  mov     [rsp+108h+var_E8], eax
0x180008bc5  jmp     short loc_180008BDC
0x180008bc7  xor     ebx, ebx
0x180008bc9  mov     [rsp+108h+var_E8], ebx
0x180008bcd  mov     edi, [rsp+108h+arg_8]
0x180008bd4  mov     rsi, [rsp+108h+arg_0]
0x180008bdc  test    ebx, ebx
0x180008bde  jz      loc_180008D04
0x180008be4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180008bec  mov     edx, edi; fdwReason
0x180008bee  mov     rcx, rsi; hinstDLL
0x180008bf1  call    DllMain
0x180008bf6  mov     ebx, eax
0x180008bf8  mov     [rsp+108h+var_E8], eax
0x180008bfc  jmp     short loc_180008C13
0x180008bfe  xor     ebx, ebx
0x180008c00  mov     [rsp+108h+var_E8], ebx
0x180008c04  mov     edi, [rsp+108h+arg_8]
0x180008c0b  mov     rsi, [rsp+108h+arg_0]
0x180008c13  cmp     edi, 1
0x180008c16  jnz     short loc_180008C8F
0x180008c18  test    ebx, ebx
0x180008c1a  jnz     short loc_180008C8F
0x180008c1c  xor     r8d, r8d; lpvReserved
0x180008c1f  xor     edx, edx; fdwReason
0x180008c21  mov     rcx, rsi; hinstDLL
0x180008c24  call    DllMain
0x180008c29  jmp     short loc_180008C3E
0x180008c2b  mov     edi, [rsp+108h+arg_8]
0x180008c32  mov     rsi, [rsp+108h+arg_0]
0x180008c3a  mov     ebx, [rsp+108h+var_E8]
0x180008c3e  xor     r8d, r8d
0x180008c41  xor     edx, edx
0x180008c43  mov     rcx, rsi
0x180008c46  call    _CRT_INIT
0x180008c4b  jmp     short loc_180008C60
0x180008c4d  mov     edi, [rsp+108h+arg_8]
0x180008c54  mov     rsi, [rsp+108h+arg_0]
0x180008c5c  mov     ebx, [rsp+108h+var_E8]
0x180008c60  mov     rax, cs:_pRawDllMain
0x180008c67  test    rax, rax
0x180008c6a  jz      short loc_180008C8F
0x180008c6c  xor     r8d, r8d
0x180008c6f  xor     edx, edx
0x180008c71  mov     rcx, rsi
0x180008c74  call    cs:__guard_dispatch_icall_fptr
0x180008c7a  jmp     short loc_180008C8F
0x180008c7c  mov     edi, [rsp+108h+arg_8]
0x180008c83  mov     rsi, [rsp+108h+arg_0]
0x180008c8b  mov     ebx, [rsp+108h+var_E8]
0x180008c8f  test    edi, edi
0x180008c91  jz      short loc_180008C98
0x180008c93  cmp     edi, 3
0x180008c96  jnz     short loc_180008D04
0x180008c98  mov     r8, [rsp+108h+lpvReserved]
0x180008ca0  mov     edx, edi
0x180008ca2  mov     rcx, rsi
0x180008ca5  call    _CRT_INIT
0x180008caa  mov     ebx, eax
0x180008cac  mov     [rsp+108h+var_E8], eax
0x180008cb0  jmp     short loc_180008CC7
0x180008cb2  xor     ebx, ebx
0x180008cb4  mov     [rsp+108h+var_E8], ebx
0x180008cb8  mov     edi, [rsp+108h+arg_8]
0x180008cbf  mov     rsi, [rsp+108h+arg_0]
0x180008cc7  mov     rax, cs:_pRawDllMain
0x180008cce  test    rax, rax
0x180008cd1  jz      short loc_180008D04
0x180008cd3  cmp     cs:dword_18002D244, 0
0x180008cda  jz      short loc_180008D04
0x180008cdc  mov     r8, [rsp+108h+lpvReserved]
0x180008ce4  mov     edx, edi
0x180008ce6  mov     rcx, rsi
0x180008ce9  call    cs:__guard_dispatch_icall_fptr
0x180008cef  mov     ebx, eax
0x180008cf1  mov     [rsp+108h+var_E8], eax
0x180008cf5  jmp     short loc_180008D04
0x180008cf7  xor     ebx, ebx
0x180008cf9  mov     [rsp+108h+var_E8], ebx
0x180008cfd  mov     edi, [rsp+108h+arg_8]
0x180008d04  cmp     edi, 1
0x180008d07  ja      short loc_180008D13
0x180008d09  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180008d13  mov     eax, ebx
0x180008d15  add     rsp, 0F0h
0x180008d1c  pop     rdi
0x180008d1d  pop     rsi
0x180008d1e  pop     rbx
0x180008d1f  retn
0x18001bed8  push    rbp
0x18001beda  sub     rsp, 20h
0x18001bede  mov     rbp, rdx
0x18001bee1  mov     rax, [rcx]
0x18001bee4  mov     edx, [rax]
0x18001bee6  mov     [rbp+0A8h], rcx
0x18001beed  mov     [rbp+28h], edx
0x18001bef0  mov     eax, [rbp+28h]
0x18001bef3  cmp     eax, 0E06D7363h
0x18001bef8  jnz     short loc_18001BF0E
0x18001befa  mov     rdx, [rbp+0A8h]
0x18001bf01  mov     ecx, [rbp+28h]
0x18001bf04  call    _XcptFilter_0
0x18001bf09  mov     [rbp+30h], eax
0x18001bf0c  jmp     short loc_18001BF15
0x18001bf0e  mov     dword ptr [rbp+30h], 0
0x18001bf15  mov     eax, [rbp+30h]
0x18001bf18  add     rsp, 20h
0x18001bf1c  pop     rbp
0x18001bf1d  retn
0x18001bf1f  push    rbp
0x18001bf21  sub     rsp, 20h
0x18001bf25  mov     rbp, rdx
0x18001bf28  mov     rax, [rcx]
0x18001bf2b  mov     edx, [rax]
0x18001bf2d  mov     [rbp+0B0h], rcx
0x18001bf34  mov     [rbp+38h], edx
0x18001bf37  mov     eax, [rbp+38h]
0x18001bf3a  cmp     eax, 0E06D7363h
0x18001bf3f  jnz     short loc_18001BF55
0x18001bf41  mov     rdx, [rbp+0B0h]
0x18001bf48  mov     ecx, [rbp+38h]
0x18001bf4b  call    _XcptFilter_0
0x18001bf50  mov     [rbp+40h], eax
0x18001bf53  jmp     short loc_18001BF5C
0x18001bf55  mov     dword ptr [rbp+40h], 0
0x18001bf5c  mov     eax, [rbp+40h]
0x18001bf5f  add     rsp, 20h
0x18001bf63  pop     rbp
0x18001bf64  retn
0x18001bf66  push    rbp
0x18001bf68  sub     rsp, 20h
0x18001bf6c  mov     rbp, rdx
0x18001bf6f  mov     rax, [rcx]
0x18001bf72  mov     edx, [rax]
0x18001bf74  mov     [rbp+0B8h], rcx
0x18001bf7b  mov     [rbp+48h], edx
0x18001bf7e  mov     eax, [rbp+48h]
0x18001bf81  cmp     eax, 0E06D7363h
0x18001bf86  jnz     short loc_18001BF9C
0x18001bf88  mov     rdx, [rbp+0B8h]
0x18001bf8f  mov     ecx, [rbp+48h]
0x18001bf92  call    _XcptFilter_0
0x18001bf97  mov     [rbp+50h], eax
0x18001bf9a  jmp     short loc_18001BFA3
0x18001bf9c  mov     dword ptr [rbp+50h], 0
0x18001bfa3  mov     eax, [rbp+50h]
0x18001bfa6  add     rsp, 20h
0x18001bfaa  pop     rbp
0x18001bfab  retn
0x18001bfad  push    rbp
0x18001bfaf  sub     rsp, 20h
0x18001bfb3  mov     rbp, rdx
0x18001bfb6  mov     rax, [rcx]
0x18001bfb9  mov     edx, [rax]
0x18001bfbb  mov     [rbp+0C0h], rcx
0x18001bfc2  mov     [rbp+58h], edx
0x18001bfc5  mov     eax, [rbp+58h]
0x18001bfc8  cmp     eax, 0E06D7363h
0x18001bfcd  jnz     short loc_18001BFE3
0x18001bfcf  mov     rdx, [rbp+0C0h]
0x18001bfd6  mov     ecx, [rbp+58h]
0x18001bfd9  call    _XcptFilter_0
0x18001bfde  mov     [rbp+60h], eax
0x18001bfe1  jmp     short loc_18001BFEA
0x18001bfe3  mov     dword ptr [rbp+60h], 0
0x18001bfea  mov     eax, [rbp+60h]
0x18001bfed  add     rsp, 20h
0x18001bff1  pop     rbp
0x18001bff2  retn
0x18001bff4  push    rbp
0x18001bff6  sub     rsp, 20h
0x18001bffa  mov     rbp, rdx
0x18001bffd  mov     rax, [rcx]
0x18001c000  mov     edx, [rax]
0x18001c002  mov     [rbp+0C8h], rcx
0x18001c009  mov     [rbp+68h], edx
0x18001c00c  mov     eax, [rbp+68h]
0x18001c00f  cmp     eax, 0E06D7363h
0x18001c014  jnz     short loc_18001C02A
0x18001c016  mov     rdx, [rbp+0C8h]
0x18001c01d  mov     ecx, [rbp+68h]
0x18001c020  call    _XcptFilter_0
0x18001c025  mov     [rbp+70h], eax
0x18001c028  jmp     short loc_18001C031
0x18001c02a  mov     dword ptr [rbp+70h], 0
0x18001c031  mov     eax, [rbp+70h]
0x18001c034  add     rsp, 20h
0x18001c038  pop     rbp
0x18001c039  retn
0x18001c03b  push    rbp
0x18001c03d  sub     rsp, 20h
0x18001c041  mov     rbp, rdx
0x18001c044  mov     rax, [rcx]
0x18001c047  mov     edx, [rax]
0x18001c049  mov     [rbp+0D0h], rcx
0x18001c050  mov     [rbp+78h], edx
0x18001c053  mov     eax, [rbp+78h]
0x18001c056  cmp     eax, 0E06D7363h
0x18001c05b  jnz     short loc_18001C074
0x18001c05d  mov     rdx, [rbp+0D0h]
0x18001c064  mov     ecx, [rbp+78h]
0x18001c067  call    _XcptFilter_0
0x18001c06c  mov     [rbp+80h], eax
0x18001c072  jmp     short loc_18001C07E
0x18001c074  mov     dword ptr [rbp+80h], 0
0x18001c07e  mov     eax, [rbp+80h]
0x18001c084  add     rsp, 20h
0x18001c088  pop     rbp
0x18001c089  retn
0x18001c08b  push    rbp
0x18001c08d  sub     rsp, 20h
0x18001c091  mov     rbp, rdx
0x18001c094  mov     rax, [rcx]
0x18001c097  mov     edx, [rax]
0x18001c099  mov     [rbp+0D8h], rcx
0x18001c0a0  mov     [rbp+88h], edx
0x18001c0a6  mov     eax, [rbp+88h]
0x18001c0ac  cmp     eax, 0E06D7363h
0x18001c0b1  jnz     short loc_18001C0CD
0x18001c0b3  mov     rdx, [rbp+0D8h]
0x18001c0ba  mov     ecx, [rbp+88h]
0x18001c0c0  call    _XcptFilter_0
0x18001c0c5  mov     [rbp+90h], eax
0x18001c0cb  jmp     short loc_18001C0D7
0x18001c0cd  mov     dword ptr [rbp+90h], 0
0x18001c0d7  mov     eax, [rbp+90h]
0x18001c0dd  add     rsp, 20h
0x18001c0e1  pop     rbp
0x18001c0e2  retn
0x18001c0e4  push    rbp
0x18001c0e6  sub     rsp, 20h
0x18001c0ea  mov     rbp, rdx
0x18001c0ed  mov     rax, [rcx]
0x18001c0f0  mov     edx, [rax]
0x18001c0f2  mov     [rbp+0E0h], rcx
0x18001c0f9  mov     [rbp+98h], edx
0x18001c0ff  mov     eax, [rbp+98h]
0x18001c105  cmp     eax, 0E06D7363h
0x18001c10a  jnz     short loc_18001C126
0x18001c10c  mov     rdx, [rbp+0E0h]
0x18001c113  mov     ecx, [rbp+98h]
0x18001c119  call    _XcptFilter_0
0x18001c11e  mov     [rbp+0A0h], eax
0x18001c124  jmp     short loc_18001C130
0x18001c126  mov     dword ptr [rbp+0A0h], 0
0x18001c130  mov     eax, [rbp+0A0h]
0x18001c136  add     rsp, 20h
0x18001c13a  pop     rbp
0x18001c13b  retn
0x18001c13d  push    rbp
0x18001c13f  sub     rsp, 20h
0x18001c143  mov     rbp, rdx
0x18001c146  cmp     dword ptr [rbp+118h], 1
0x18001c14d  ja      short loc_18001C159
0x18001c14f  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
