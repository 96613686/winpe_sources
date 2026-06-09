# __DllMainCRTStartup

- ea: `0x18000fe74`
- end: `0x180010080`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000fe30`

## callees

- `0x18000fc00`
- `0x18000fe74`
- `0x18001028e`
- `0x1800171d4`
- `0x180020ca0`

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
  if ( (_DWORD)fdwReason || dword_18003049C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800304A0 = 1;
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
            if ( dword_1800304A0 )
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
0x18000fe74  mov     [rsp+lpvReserved], r8
0x18000fe79  mov     [rsp+arg_8], edx
0x18000fe7d  mov     [rsp+arg_0], rcx
0x18000fe82  push    rbx
0x18000fe83  push    rsi
0x18000fe84  push    rdi
0x18000fe85  sub     rsp, 0F0h
0x18000fe8c  mov     edi, edx
0x18000fe8e  mov     rsi, rcx
0x18000fe91  mov     ebx, 1
0x18000fe96  cmp     edx, ebx
0x18000fe98  ja      short loc_18000FEA0
0x18000fe9a  mov     cs:__native_dllmain_reason, edx
0x18000fea0  test    edx, edx
0x18000fea2  jnz     short loc_18000FEB7
0x18000fea4  cmp     cs:dword_18003049C, edx
0x18000feaa  jnz     short loc_18000FEB7
0x18000feac  xor     ebx, ebx
0x18000feae  mov     [rsp+108h+var_E8], ebx
0x18000feb2  jmp     loc_180010064
0x18000feb7  lea     eax, [rdx-1]
0x18000feba  cmp     eax, 1
0x18000febd  ja      loc_18000FF44
0x18000fec3  mov     rax, cs:_pRawDllMain
0x18000feca  test    rax, rax
0x18000fecd  jz      short loc_18000FF05
0x18000fecf  cmp     edx, 1
0x18000fed2  jnz     short loc_18000FEDA
0x18000fed4  mov     cs:dword_1800304A0, edx
0x18000feda  mov     r8, [rsp+108h+lpvReserved]
0x18000fee2  call    cs:__guard_dispatch_icall_fptr
0x18000fee8  mov     ebx, eax
0x18000feea  mov     [rsp+108h+var_E8], eax
0x18000feee  jmp     short loc_18000FF05
0x18000fef0  xor     ebx, ebx
0x18000fef2  mov     [rsp+108h+var_E8], ebx
0x18000fef6  mov     edi, [rsp+108h+arg_8]
0x18000fefd  mov     rsi, [rsp+108h+arg_0]
0x18000ff05  test    ebx, ebx
0x18000ff07  jz      loc_180010064
0x18000ff0d  mov     r8, [rsp+108h+lpvReserved]
0x18000ff15  mov     edx, edi
0x18000ff17  mov     rcx, rsi
0x18000ff1a  call    _CRT_INIT
0x18000ff1f  mov     ebx, eax
0x18000ff21  mov     [rsp+108h+var_E8], eax
0x18000ff25  jmp     short loc_18000FF3C
0x18000ff27  xor     ebx, ebx
0x18000ff29  mov     [rsp+108h+var_E8], ebx
0x18000ff2d  mov     edi, [rsp+108h+arg_8]
0x18000ff34  mov     rsi, [rsp+108h+arg_0]
0x18000ff3c  test    ebx, ebx
0x18000ff3e  jz      loc_180010064
0x18000ff44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000ff4c  mov     edx, edi; fdwReason
0x18000ff4e  mov     rcx, rsi; hinstDLL
0x18000ff51  call    DllMain
0x18000ff56  mov     ebx, eax
0x18000ff58  mov     [rsp+108h+var_E8], eax
0x18000ff5c  jmp     short loc_18000FF73
0x18000ff5e  xor     ebx, ebx
0x18000ff60  mov     [rsp+108h+var_E8], ebx
0x18000ff64  mov     edi, [rsp+108h+arg_8]
0x18000ff6b  mov     rsi, [rsp+108h+arg_0]
0x18000ff73  cmp     edi, 1
0x18000ff76  jnz     short loc_18000FFEF
0x18000ff78  test    ebx, ebx
0x18000ff7a  jnz     short loc_18000FFEF
0x18000ff7c  xor     r8d, r8d; lpvReserved
0x18000ff7f  xor     edx, edx; fdwReason
0x18000ff81  mov     rcx, rsi; hinstDLL
0x18000ff84  call    DllMain
0x18000ff89  jmp     short loc_18000FF9E
0x18000ff8b  mov     edi, [rsp+108h+arg_8]
0x18000ff92  mov     rsi, [rsp+108h+arg_0]
0x18000ff9a  mov     ebx, [rsp+108h+var_E8]
0x18000ff9e  xor     r8d, r8d
0x18000ffa1  xor     edx, edx
0x18000ffa3  mov     rcx, rsi
0x18000ffa6  call    _CRT_INIT
0x18000ffab  jmp     short loc_18000FFC0
0x18000ffad  mov     edi, [rsp+108h+arg_8]
0x18000ffb4  mov     rsi, [rsp+108h+arg_0]
0x18000ffbc  mov     ebx, [rsp+108h+var_E8]
0x18000ffc0  mov     rax, cs:_pRawDllMain
0x18000ffc7  test    rax, rax
0x18000ffca  jz      short loc_18000FFEF
0x18000ffcc  xor     r8d, r8d
0x18000ffcf  xor     edx, edx
0x18000ffd1  mov     rcx, rsi
0x18000ffd4  call    cs:__guard_dispatch_icall_fptr
0x18000ffda  jmp     short loc_18000FFEF
0x18000ffdc  mov     edi, [rsp+108h+arg_8]
0x18000ffe3  mov     rsi, [rsp+108h+arg_0]
0x18000ffeb  mov     ebx, [rsp+108h+var_E8]
0x18000ffef  test    edi, edi
0x18000fff1  jz      short loc_18000FFF8
0x18000fff3  cmp     edi, 3
0x18000fff6  jnz     short loc_180010064
0x18000fff8  mov     r8, [rsp+108h+lpvReserved]
0x180010000  mov     edx, edi
0x180010002  mov     rcx, rsi
0x180010005  call    _CRT_INIT
0x18001000a  mov     ebx, eax
0x18001000c  mov     [rsp+108h+var_E8], eax
0x180010010  jmp     short loc_180010027
0x180010012  xor     ebx, ebx
0x180010014  mov     [rsp+108h+var_E8], ebx
0x180010018  mov     edi, [rsp+108h+arg_8]
0x18001001f  mov     rsi, [rsp+108h+arg_0]
0x180010027  mov     rax, cs:_pRawDllMain
0x18001002e  test    rax, rax
0x180010031  jz      short loc_180010064
0x180010033  cmp     cs:dword_1800304A0, 0
0x18001003a  jz      short loc_180010064
0x18001003c  mov     r8, [rsp+108h+lpvReserved]
0x180010044  mov     edx, edi
0x180010046  mov     rcx, rsi
0x180010049  call    cs:__guard_dispatch_icall_fptr
0x18001004f  mov     ebx, eax
0x180010051  mov     [rsp+108h+var_E8], eax
0x180010055  jmp     short loc_180010064
0x180010057  xor     ebx, ebx
0x180010059  mov     [rsp+108h+var_E8], ebx
0x18001005d  mov     edi, [rsp+108h+arg_8]
0x180010064  cmp     edi, 1
0x180010067  ja      short loc_180010073
0x180010069  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180010073  mov     eax, ebx
0x180010075  add     rsp, 0F0h
0x18001007c  pop     rdi
0x18001007d  pop     rsi
0x18001007e  pop     rbx
0x18001007f  retn
0x18002105c  push    rbp
0x18002105e  sub     rsp, 20h
0x180021062  mov     rbp, rdx
0x180021065  mov     rax, [rcx]
0x180021068  mov     edx, [rax]
0x18002106a  mov     [rbp+0A8h], rcx
0x180021071  mov     [rbp+28h], edx
0x180021074  mov     eax, [rbp+28h]
0x180021077  cmp     eax, 0E06D7363h
0x18002107c  jnz     short loc_180021092
0x18002107e  mov     rdx, [rbp+0A8h]
0x180021085  mov     ecx, [rbp+28h]
0x180021088  call    _XcptFilter_0
0x18002108d  mov     [rbp+30h], eax
0x180021090  jmp     short loc_180021099
0x180021092  mov     dword ptr [rbp+30h], 0
0x180021099  mov     eax, [rbp+30h]
0x18002109c  add     rsp, 20h
0x1800210a0  pop     rbp
0x1800210a1  retn
0x1800210a3  push    rbp
0x1800210a5  sub     rsp, 20h
0x1800210a9  mov     rbp, rdx
0x1800210ac  mov     rax, [rcx]
0x1800210af  mov     edx, [rax]
0x1800210b1  mov     [rbp+0B0h], rcx
0x1800210b8  mov     [rbp+38h], edx
0x1800210bb  mov     eax, [rbp+38h]
0x1800210be  cmp     eax, 0E06D7363h
0x1800210c3  jnz     short loc_1800210D9
0x1800210c5  mov     rdx, [rbp+0B0h]
0x1800210cc  mov     ecx, [rbp+38h]
0x1800210cf  call    _XcptFilter_0
0x1800210d4  mov     [rbp+40h], eax
0x1800210d7  jmp     short loc_1800210E0
0x1800210d9  mov     dword ptr [rbp+40h], 0
0x1800210e0  mov     eax, [rbp+40h]
0x1800210e3  add     rsp, 20h
0x1800210e7  pop     rbp
0x1800210e8  retn
0x1800210ea  push    rbp
0x1800210ec  sub     rsp, 20h
0x1800210f0  mov     rbp, rdx
0x1800210f3  mov     rax, [rcx]
0x1800210f6  mov     edx, [rax]
0x1800210f8  mov     [rbp+0B8h], rcx
0x1800210ff  mov     [rbp+48h], edx
0x180021102  mov     eax, [rbp+48h]
0x180021105  cmp     eax, 0E06D7363h
0x18002110a  jnz     short loc_180021120
0x18002110c  mov     rdx, [rbp+0B8h]
0x180021113  mov     ecx, [rbp+48h]
0x180021116  call    _XcptFilter_0
0x18002111b  mov     [rbp+50h], eax
0x18002111e  jmp     short loc_180021127
0x180021120  mov     dword ptr [rbp+50h], 0
0x180021127  mov     eax, [rbp+50h]
0x18002112a  add     rsp, 20h
0x18002112e  pop     rbp
0x18002112f  retn
0x180021131  push    rbp
0x180021133  sub     rsp, 20h
0x180021137  mov     rbp, rdx
0x18002113a  mov     rax, [rcx]
0x18002113d  mov     edx, [rax]
0x18002113f  mov     [rbp+0C0h], rcx
0x180021146  mov     [rbp+58h], edx
0x180021149  mov     eax, [rbp+58h]
0x18002114c  cmp     eax, 0E06D7363h
0x180021151  jnz     short loc_180021167
0x180021153  mov     rdx, [rbp+0C0h]
0x18002115a  mov     ecx, [rbp+58h]
0x18002115d  call    _XcptFilter_0
0x180021162  mov     [rbp+60h], eax
0x180021165  jmp     short loc_18002116E
0x180021167  mov     dword ptr [rbp+60h], 0
0x18002116e  mov     eax, [rbp+60h]
0x180021171  add     rsp, 20h
0x180021175  pop     rbp
0x180021176  retn
0x180021178  push    rbp
0x18002117a  sub     rsp, 20h
0x18002117e  mov     rbp, rdx
0x180021181  mov     rax, [rcx]
0x180021184  mov     edx, [rax]
0x180021186  mov     [rbp+0C8h], rcx
0x18002118d  mov     [rbp+68h], edx
0x180021190  mov     eax, [rbp+68h]
0x180021193  cmp     eax, 0E06D7363h
0x180021198  jnz     short loc_1800211AE
0x18002119a  mov     rdx, [rbp+0C8h]
0x1800211a1  mov     ecx, [rbp+68h]
0x1800211a4  call    _XcptFilter_0
0x1800211a9  mov     [rbp+70h], eax
0x1800211ac  jmp     short loc_1800211B5
0x1800211ae  mov     dword ptr [rbp+70h], 0
0x1800211b5  mov     eax, [rbp+70h]
0x1800211b8  add     rsp, 20h
0x1800211bc  pop     rbp
0x1800211bd  retn
0x1800211bf  push    rbp
0x1800211c1  sub     rsp, 20h
0x1800211c5  mov     rbp, rdx
0x1800211c8  mov     rax, [rcx]
0x1800211cb  mov     edx, [rax]
0x1800211cd  mov     [rbp+0D0h], rcx
0x1800211d4  mov     [rbp+78h], edx
0x1800211d7  mov     eax, [rbp+78h]
0x1800211da  cmp     eax, 0E06D7363h
0x1800211df  jnz     short loc_1800211F8
0x1800211e1  mov     rdx, [rbp+0D0h]
0x1800211e8  mov     ecx, [rbp+78h]
0x1800211eb  call    _XcptFilter_0
0x1800211f0  mov     [rbp+80h], eax
0x1800211f6  jmp     short loc_180021202
0x1800211f8  mov     dword ptr [rbp+80h], 0
0x180021202  mov     eax, [rbp+80h]
0x180021208  add     rsp, 20h
0x18002120c  pop     rbp
0x18002120d  retn
0x18002120f  push    rbp
0x180021211  sub     rsp, 20h
0x180021215  mov     rbp, rdx
0x180021218  mov     rax, [rcx]
0x18002121b  mov     edx, [rax]
0x18002121d  mov     [rbp+0D8h], rcx
0x180021224  mov     [rbp+88h], edx
0x18002122a  mov     eax, [rbp+88h]
0x180021230  cmp     eax, 0E06D7363h
0x180021235  jnz     short loc_180021251
0x180021237  mov     rdx, [rbp+0D8h]
0x18002123e  mov     ecx, [rbp+88h]
0x180021244  call    _XcptFilter_0
0x180021249  mov     [rbp+90h], eax
0x18002124f  jmp     short loc_18002125B
0x180021251  mov     dword ptr [rbp+90h], 0
0x18002125b  mov     eax, [rbp+90h]
0x180021261  add     rsp, 20h
0x180021265  pop     rbp
0x180021266  retn
0x180021268  push    rbp
0x18002126a  sub     rsp, 20h
0x18002126e  mov     rbp, rdx
0x180021271  mov     rax, [rcx]
0x180021274  mov     edx, [rax]
0x180021276  mov     [rbp+0E0h], rcx
0x18002127d  mov     [rbp+98h], edx
0x180021283  mov     eax, [rbp+98h]
0x180021289  cmp     eax, 0E06D7363h
0x18002128e  jnz     short loc_1800212AA
0x180021290  mov     rdx, [rbp+0E0h]
0x180021297  mov     ecx, [rbp+98h]
0x18002129d  call    _XcptFilter_0
0x1800212a2  mov     [rbp+0A0h], eax
0x1800212a8  jmp     short loc_1800212B4
0x1800212aa  mov     dword ptr [rbp+0A0h], 0
0x1800212b4  mov     eax, [rbp+0A0h]
0x1800212ba  add     rsp, 20h
0x1800212be  pop     rbp
0x1800212bf  retn
0x1800212c1  push    rbp
0x1800212c3  sub     rsp, 20h
0x1800212c7  mov     rbp, rdx
0x1800212ca  cmp     dword ptr [rbp+118h], 1
0x1800212d1  ja      short loc_1800212DD
0x1800212d3  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
