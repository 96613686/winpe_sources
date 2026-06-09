# __DllMainCRTStartup

- ea: `0x180001e54`
- end: `0x180002060`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001e10`

## callees

- `0x180001be0`
- `0x180001e54`
- `0x1800025ae`
- `0x180009dec`
- `0x18000fca0`

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
  if ( (_DWORD)fdwReason || dword_18001B38C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001B390 = 1;
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
            if ( dword_18001B390 )
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
0x180001e54  mov     [rsp+lpvReserved], r8
0x180001e59  mov     [rsp+arg_8], edx
0x180001e5d  mov     [rsp+arg_0], rcx
0x180001e62  push    rbx
0x180001e63  push    rsi
0x180001e64  push    rdi
0x180001e65  sub     rsp, 0F0h
0x180001e6c  mov     edi, edx
0x180001e6e  mov     rsi, rcx
0x180001e71  mov     ebx, 1
0x180001e76  cmp     edx, ebx
0x180001e78  ja      short loc_180001E80
0x180001e7a  mov     cs:__native_dllmain_reason, edx
0x180001e80  test    edx, edx
0x180001e82  jnz     short loc_180001E97
0x180001e84  cmp     cs:dword_18001B38C, edx
0x180001e8a  jnz     short loc_180001E97
0x180001e8c  xor     ebx, ebx
0x180001e8e  mov     [rsp+108h+var_E8], ebx
0x180001e92  jmp     loc_180002044
0x180001e97  lea     eax, [rdx-1]
0x180001e9a  cmp     eax, 1
0x180001e9d  ja      loc_180001F24
0x180001ea3  mov     rax, cs:_pRawDllMain
0x180001eaa  test    rax, rax
0x180001ead  jz      short loc_180001EE5
0x180001eaf  cmp     edx, 1
0x180001eb2  jnz     short loc_180001EBA
0x180001eb4  mov     cs:dword_18001B390, edx
0x180001eba  mov     r8, [rsp+108h+lpvReserved]
0x180001ec2  call    cs:__guard_dispatch_icall_fptr
0x180001ec8  mov     ebx, eax
0x180001eca  mov     [rsp+108h+var_E8], eax
0x180001ece  jmp     short loc_180001EE5
0x180001ed0  xor     ebx, ebx
0x180001ed2  mov     [rsp+108h+var_E8], ebx
0x180001ed6  mov     edi, [rsp+108h+arg_8]
0x180001edd  mov     rsi, [rsp+108h+arg_0]
0x180001ee5  test    ebx, ebx
0x180001ee7  jz      loc_180002044
0x180001eed  mov     r8, [rsp+108h+lpvReserved]
0x180001ef5  mov     edx, edi
0x180001ef7  mov     rcx, rsi
0x180001efa  call    _CRT_INIT
0x180001eff  mov     ebx, eax
0x180001f01  mov     [rsp+108h+var_E8], eax
0x180001f05  jmp     short loc_180001F1C
0x180001f07  xor     ebx, ebx
0x180001f09  mov     [rsp+108h+var_E8], ebx
0x180001f0d  mov     edi, [rsp+108h+arg_8]
0x180001f14  mov     rsi, [rsp+108h+arg_0]
0x180001f1c  test    ebx, ebx
0x180001f1e  jz      loc_180002044
0x180001f24  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001f2c  mov     edx, edi; fdwReason
0x180001f2e  mov     rcx, rsi; hinstDLL
0x180001f31  call    DllMain
0x180001f36  mov     ebx, eax
0x180001f38  mov     [rsp+108h+var_E8], eax
0x180001f3c  jmp     short loc_180001F53
0x180001f3e  xor     ebx, ebx
0x180001f40  mov     [rsp+108h+var_E8], ebx
0x180001f44  mov     edi, [rsp+108h+arg_8]
0x180001f4b  mov     rsi, [rsp+108h+arg_0]
0x180001f53  cmp     edi, 1
0x180001f56  jnz     short loc_180001FCF
0x180001f58  test    ebx, ebx
0x180001f5a  jnz     short loc_180001FCF
0x180001f5c  xor     r8d, r8d; lpvReserved
0x180001f5f  xor     edx, edx; fdwReason
0x180001f61  mov     rcx, rsi; hinstDLL
0x180001f64  call    DllMain
0x180001f69  jmp     short loc_180001F7E
0x180001f6b  mov     edi, [rsp+108h+arg_8]
0x180001f72  mov     rsi, [rsp+108h+arg_0]
0x180001f7a  mov     ebx, [rsp+108h+var_E8]
0x180001f7e  xor     r8d, r8d
0x180001f81  xor     edx, edx
0x180001f83  mov     rcx, rsi
0x180001f86  call    _CRT_INIT
0x180001f8b  jmp     short loc_180001FA0
0x180001f8d  mov     edi, [rsp+108h+arg_8]
0x180001f94  mov     rsi, [rsp+108h+arg_0]
0x180001f9c  mov     ebx, [rsp+108h+var_E8]
0x180001fa0  mov     rax, cs:_pRawDllMain
0x180001fa7  test    rax, rax
0x180001faa  jz      short loc_180001FCF
0x180001fac  xor     r8d, r8d
0x180001faf  xor     edx, edx
0x180001fb1  mov     rcx, rsi
0x180001fb4  call    cs:__guard_dispatch_icall_fptr
0x180001fba  jmp     short loc_180001FCF
0x180001fbc  mov     edi, [rsp+108h+arg_8]
0x180001fc3  mov     rsi, [rsp+108h+arg_0]
0x180001fcb  mov     ebx, [rsp+108h+var_E8]
0x180001fcf  test    edi, edi
0x180001fd1  jz      short loc_180001FD8
0x180001fd3  cmp     edi, 3
0x180001fd6  jnz     short loc_180002044
0x180001fd8  mov     r8, [rsp+108h+lpvReserved]
0x180001fe0  mov     edx, edi
0x180001fe2  mov     rcx, rsi
0x180001fe5  call    _CRT_INIT
0x180001fea  mov     ebx, eax
0x180001fec  mov     [rsp+108h+var_E8], eax
0x180001ff0  jmp     short loc_180002007
0x180001ff2  xor     ebx, ebx
0x180001ff4  mov     [rsp+108h+var_E8], ebx
0x180001ff8  mov     edi, [rsp+108h+arg_8]
0x180001fff  mov     rsi, [rsp+108h+arg_0]
0x180002007  mov     rax, cs:_pRawDllMain
0x18000200e  test    rax, rax
0x180002011  jz      short loc_180002044
0x180002013  cmp     cs:dword_18001B390, 0
0x18000201a  jz      short loc_180002044
0x18000201c  mov     r8, [rsp+108h+lpvReserved]
0x180002024  mov     edx, edi
0x180002026  mov     rcx, rsi
0x180002029  call    cs:__guard_dispatch_icall_fptr
0x18000202f  mov     ebx, eax
0x180002031  mov     [rsp+108h+var_E8], eax
0x180002035  jmp     short loc_180002044
0x180002037  xor     ebx, ebx
0x180002039  mov     [rsp+108h+var_E8], ebx
0x18000203d  mov     edi, [rsp+108h+arg_8]
0x180002044  cmp     edi, 1
0x180002047  ja      short loc_180002053
0x180002049  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002053  mov     eax, ebx
0x180002055  add     rsp, 0F0h
0x18000205c  pop     rdi
0x18000205d  pop     rsi
0x18000205e  pop     rbx
0x18000205f  retn
0x18000fdb2  push    rbp
0x18000fdb4  sub     rsp, 20h
0x18000fdb8  mov     rbp, rdx
0x18000fdbb  mov     rax, [rcx]
0x18000fdbe  mov     edx, [rax]
0x18000fdc0  mov     [rbp+0A8h], rcx
0x18000fdc7  mov     [rbp+28h], edx
0x18000fdca  mov     eax, [rbp+28h]
0x18000fdcd  cmp     eax, 0E06D7363h
0x18000fdd2  jnz     short loc_18000FDE8
0x18000fdd4  mov     rdx, [rbp+0A8h]
0x18000fddb  mov     ecx, [rbp+28h]
0x18000fdde  call    _XcptFilter_0
0x18000fde3  mov     [rbp+30h], eax
0x18000fde6  jmp     short loc_18000FDEF
0x18000fde8  mov     dword ptr [rbp+30h], 0
0x18000fdef  mov     eax, [rbp+30h]
0x18000fdf2  add     rsp, 20h
0x18000fdf6  pop     rbp
0x18000fdf7  retn
0x18000fdf9  push    rbp
0x18000fdfb  sub     rsp, 20h
0x18000fdff  mov     rbp, rdx
0x18000fe02  mov     rax, [rcx]
0x18000fe05  mov     edx, [rax]
0x18000fe07  mov     [rbp+0B0h], rcx
0x18000fe0e  mov     [rbp+38h], edx
0x18000fe11  mov     eax, [rbp+38h]
0x18000fe14  cmp     eax, 0E06D7363h
0x18000fe19  jnz     short loc_18000FE2F
0x18000fe1b  mov     rdx, [rbp+0B0h]
0x18000fe22  mov     ecx, [rbp+38h]
0x18000fe25  call    _XcptFilter_0
0x18000fe2a  mov     [rbp+40h], eax
0x18000fe2d  jmp     short loc_18000FE36
0x18000fe2f  mov     dword ptr [rbp+40h], 0
0x18000fe36  mov     eax, [rbp+40h]
0x18000fe39  add     rsp, 20h
0x18000fe3d  pop     rbp
0x18000fe3e  retn
0x18000fe40  push    rbp
0x18000fe42  sub     rsp, 20h
0x18000fe46  mov     rbp, rdx
0x18000fe49  mov     rax, [rcx]
0x18000fe4c  mov     edx, [rax]
0x18000fe4e  mov     [rbp+0B8h], rcx
0x18000fe55  mov     [rbp+48h], edx
0x18000fe58  mov     eax, [rbp+48h]
0x18000fe5b  cmp     eax, 0E06D7363h
0x18000fe60  jnz     short loc_18000FE76
0x18000fe62  mov     rdx, [rbp+0B8h]
0x18000fe69  mov     ecx, [rbp+48h]
0x18000fe6c  call    _XcptFilter_0
0x18000fe71  mov     [rbp+50h], eax
0x18000fe74  jmp     short loc_18000FE7D
0x18000fe76  mov     dword ptr [rbp+50h], 0
0x18000fe7d  mov     eax, [rbp+50h]
0x18000fe80  add     rsp, 20h
0x18000fe84  pop     rbp
0x18000fe85  retn
0x18000fe87  push    rbp
0x18000fe89  sub     rsp, 20h
0x18000fe8d  mov     rbp, rdx
0x18000fe90  mov     rax, [rcx]
0x18000fe93  mov     edx, [rax]
0x18000fe95  mov     [rbp+0C0h], rcx
0x18000fe9c  mov     [rbp+58h], edx
0x18000fe9f  mov     eax, [rbp+58h]
0x18000fea2  cmp     eax, 0E06D7363h
0x18000fea7  jnz     short loc_18000FEBD
0x18000fea9  mov     rdx, [rbp+0C0h]
0x18000feb0  mov     ecx, [rbp+58h]
0x18000feb3  call    _XcptFilter_0
0x18000feb8  mov     [rbp+60h], eax
0x18000febb  jmp     short loc_18000FEC4
0x18000febd  mov     dword ptr [rbp+60h], 0
0x18000fec4  mov     eax, [rbp+60h]
0x18000fec7  add     rsp, 20h
0x18000fecb  pop     rbp
0x18000fecc  retn
0x18000fece  push    rbp
0x18000fed0  sub     rsp, 20h
0x18000fed4  mov     rbp, rdx
0x18000fed7  mov     rax, [rcx]
0x18000feda  mov     edx, [rax]
0x18000fedc  mov     [rbp+0C8h], rcx
0x18000fee3  mov     [rbp+68h], edx
0x18000fee6  mov     eax, [rbp+68h]
0x18000fee9  cmp     eax, 0E06D7363h
0x18000feee  jnz     short loc_18000FF04
0x18000fef0  mov     rdx, [rbp+0C8h]
0x18000fef7  mov     ecx, [rbp+68h]
0x18000fefa  call    _XcptFilter_0
0x18000feff  mov     [rbp+70h], eax
0x18000ff02  jmp     short loc_18000FF0B
0x18000ff04  mov     dword ptr [rbp+70h], 0
0x18000ff0b  mov     eax, [rbp+70h]
0x18000ff0e  add     rsp, 20h
0x18000ff12  pop     rbp
0x18000ff13  retn
0x18000ff15  push    rbp
0x18000ff17  sub     rsp, 20h
0x18000ff1b  mov     rbp, rdx
0x18000ff1e  mov     rax, [rcx]
0x18000ff21  mov     edx, [rax]
0x18000ff23  mov     [rbp+0D0h], rcx
0x18000ff2a  mov     [rbp+78h], edx
0x18000ff2d  mov     eax, [rbp+78h]
0x18000ff30  cmp     eax, 0E06D7363h
0x18000ff35  jnz     short loc_18000FF4E
0x18000ff37  mov     rdx, [rbp+0D0h]
0x18000ff3e  mov     ecx, [rbp+78h]
0x18000ff41  call    _XcptFilter_0
0x18000ff46  mov     [rbp+80h], eax
0x18000ff4c  jmp     short loc_18000FF58
0x18000ff4e  mov     dword ptr [rbp+80h], 0
0x18000ff58  mov     eax, [rbp+80h]
0x18000ff5e  add     rsp, 20h
0x18000ff62  pop     rbp
0x18000ff63  retn
0x18000ff65  push    rbp
0x18000ff67  sub     rsp, 20h
0x18000ff6b  mov     rbp, rdx
0x18000ff6e  mov     rax, [rcx]
0x18000ff71  mov     edx, [rax]
0x18000ff73  mov     [rbp+0D8h], rcx
0x18000ff7a  mov     [rbp+88h], edx
0x18000ff80  mov     eax, [rbp+88h]
0x18000ff86  cmp     eax, 0E06D7363h
0x18000ff8b  jnz     short loc_18000FFA7
0x18000ff8d  mov     rdx, [rbp+0D8h]
0x18000ff94  mov     ecx, [rbp+88h]
0x18000ff9a  call    _XcptFilter_0
0x18000ff9f  mov     [rbp+90h], eax
0x18000ffa5  jmp     short loc_18000FFB1
0x18000ffa7  mov     dword ptr [rbp+90h], 0
0x18000ffb1  mov     eax, [rbp+90h]
0x18000ffb7  add     rsp, 20h
0x18000ffbb  pop     rbp
0x18000ffbc  retn
0x18000ffbe  push    rbp
0x18000ffc0  sub     rsp, 20h
0x18000ffc4  mov     rbp, rdx
0x18000ffc7  mov     rax, [rcx]
0x18000ffca  mov     edx, [rax]
0x18000ffcc  mov     [rbp+0E0h], rcx
0x18000ffd3  mov     [rbp+98h], edx
0x18000ffd9  mov     eax, [rbp+98h]
0x18000ffdf  cmp     eax, 0E06D7363h
0x18000ffe4  jnz     short loc_180010000
0x18000ffe6  mov     rdx, [rbp+0E0h]
0x18000ffed  mov     ecx, [rbp+98h]
0x18000fff3  call    _XcptFilter_0
0x18000fff8  mov     [rbp+0A0h], eax
0x18000fffe  jmp     short loc_18001000A
0x180010000  mov     dword ptr [rbp+0A0h], 0
0x18001000a  mov     eax, [rbp+0A0h]
0x180010010  add     rsp, 20h
0x180010014  pop     rbp
0x180010015  retn
0x180010017  push    rbp
0x180010019  sub     rsp, 20h
0x18001001d  mov     rbp, rdx
0x180010020  cmp     dword ptr [rbp+118h], 1
0x180010027  ja      short loc_180010033
0x180010029  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
