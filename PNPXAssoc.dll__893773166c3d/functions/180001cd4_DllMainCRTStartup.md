# __DllMainCRTStartup

- ea: `0x180001cd4`
- end: `0x180001ee0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c90`

## callees

- `0x180001a60`
- `0x180001cd4`
- `0x180002368`
- `0x1800090c0`
- `0x180012e40`

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
  if ( (_DWORD)fdwReason || dword_18001A4A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001A4A4 = 1;
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
            if ( dword_18001A4A4 )
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
0x180001cd4  mov     [rsp+lpvReserved], r8
0x180001cd9  mov     [rsp+arg_8], edx
0x180001cdd  mov     [rsp+arg_0], rcx
0x180001ce2  push    rbx
0x180001ce3  push    rsi
0x180001ce4  push    rdi
0x180001ce5  sub     rsp, 0F0h
0x180001cec  mov     edi, edx
0x180001cee  mov     rsi, rcx
0x180001cf1  mov     ebx, 1
0x180001cf6  cmp     edx, ebx
0x180001cf8  ja      short loc_180001D00
0x180001cfa  mov     cs:__native_dllmain_reason, edx
0x180001d00  test    edx, edx
0x180001d02  jnz     short loc_180001D17
0x180001d04  cmp     cs:dword_18001A4A0, edx
0x180001d0a  jnz     short loc_180001D17
0x180001d0c  xor     ebx, ebx
0x180001d0e  mov     [rsp+108h+var_E8], ebx
0x180001d12  jmp     loc_180001EC4
0x180001d17  lea     eax, [rdx-1]
0x180001d1a  cmp     eax, 1
0x180001d1d  ja      loc_180001DA4
0x180001d23  mov     rax, cs:_pRawDllMain
0x180001d2a  test    rax, rax
0x180001d2d  jz      short loc_180001D65
0x180001d2f  cmp     edx, 1
0x180001d32  jnz     short loc_180001D3A
0x180001d34  mov     cs:dword_18001A4A4, edx
0x180001d3a  mov     r8, [rsp+108h+lpvReserved]
0x180001d42  call    cs:__guard_dispatch_icall_fptr
0x180001d48  mov     ebx, eax
0x180001d4a  mov     [rsp+108h+var_E8], eax
0x180001d4e  jmp     short loc_180001D65
0x180001d50  xor     ebx, ebx
0x180001d52  mov     [rsp+108h+var_E8], ebx
0x180001d56  mov     edi, [rsp+108h+arg_8]
0x180001d5d  mov     rsi, [rsp+108h+arg_0]
0x180001d65  test    ebx, ebx
0x180001d67  jz      loc_180001EC4
0x180001d6d  mov     r8, [rsp+108h+lpvReserved]
0x180001d75  mov     edx, edi
0x180001d77  mov     rcx, rsi
0x180001d7a  call    _CRT_INIT
0x180001d7f  mov     ebx, eax
0x180001d81  mov     [rsp+108h+var_E8], eax
0x180001d85  jmp     short loc_180001D9C
0x180001d87  xor     ebx, ebx
0x180001d89  mov     [rsp+108h+var_E8], ebx
0x180001d8d  mov     edi, [rsp+108h+arg_8]
0x180001d94  mov     rsi, [rsp+108h+arg_0]
0x180001d9c  test    ebx, ebx
0x180001d9e  jz      loc_180001EC4
0x180001da4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001dac  mov     edx, edi; fdwReason
0x180001dae  mov     rcx, rsi; hinstDLL
0x180001db1  call    DllMain
0x180001db6  mov     ebx, eax
0x180001db8  mov     [rsp+108h+var_E8], eax
0x180001dbc  jmp     short loc_180001DD3
0x180001dbe  xor     ebx, ebx
0x180001dc0  mov     [rsp+108h+var_E8], ebx
0x180001dc4  mov     edi, [rsp+108h+arg_8]
0x180001dcb  mov     rsi, [rsp+108h+arg_0]
0x180001dd3  cmp     edi, 1
0x180001dd6  jnz     short loc_180001E4F
0x180001dd8  test    ebx, ebx
0x180001dda  jnz     short loc_180001E4F
0x180001ddc  xor     r8d, r8d; lpvReserved
0x180001ddf  xor     edx, edx; fdwReason
0x180001de1  mov     rcx, rsi; hinstDLL
0x180001de4  call    DllMain
0x180001de9  jmp     short loc_180001DFE
0x180001deb  mov     edi, [rsp+108h+arg_8]
0x180001df2  mov     rsi, [rsp+108h+arg_0]
0x180001dfa  mov     ebx, [rsp+108h+var_E8]
0x180001dfe  xor     r8d, r8d
0x180001e01  xor     edx, edx
0x180001e03  mov     rcx, rsi
0x180001e06  call    _CRT_INIT
0x180001e0b  jmp     short loc_180001E20
0x180001e0d  mov     edi, [rsp+108h+arg_8]
0x180001e14  mov     rsi, [rsp+108h+arg_0]
0x180001e1c  mov     ebx, [rsp+108h+var_E8]
0x180001e20  mov     rax, cs:_pRawDllMain
0x180001e27  test    rax, rax
0x180001e2a  jz      short loc_180001E4F
0x180001e2c  xor     r8d, r8d
0x180001e2f  xor     edx, edx
0x180001e31  mov     rcx, rsi
0x180001e34  call    cs:__guard_dispatch_icall_fptr
0x180001e3a  jmp     short loc_180001E4F
0x180001e3c  mov     edi, [rsp+108h+arg_8]
0x180001e43  mov     rsi, [rsp+108h+arg_0]
0x180001e4b  mov     ebx, [rsp+108h+var_E8]
0x180001e4f  test    edi, edi
0x180001e51  jz      short loc_180001E58
0x180001e53  cmp     edi, 3
0x180001e56  jnz     short loc_180001EC4
0x180001e58  mov     r8, [rsp+108h+lpvReserved]
0x180001e60  mov     edx, edi
0x180001e62  mov     rcx, rsi
0x180001e65  call    _CRT_INIT
0x180001e6a  mov     ebx, eax
0x180001e6c  mov     [rsp+108h+var_E8], eax
0x180001e70  jmp     short loc_180001E87
0x180001e72  xor     ebx, ebx
0x180001e74  mov     [rsp+108h+var_E8], ebx
0x180001e78  mov     edi, [rsp+108h+arg_8]
0x180001e7f  mov     rsi, [rsp+108h+arg_0]
0x180001e87  mov     rax, cs:_pRawDllMain
0x180001e8e  test    rax, rax
0x180001e91  jz      short loc_180001EC4
0x180001e93  cmp     cs:dword_18001A4A4, 0
0x180001e9a  jz      short loc_180001EC4
0x180001e9c  mov     r8, [rsp+108h+lpvReserved]
0x180001ea4  mov     edx, edi
0x180001ea6  mov     rcx, rsi
0x180001ea9  call    cs:__guard_dispatch_icall_fptr
0x180001eaf  mov     ebx, eax
0x180001eb1  mov     [rsp+108h+var_E8], eax
0x180001eb5  jmp     short loc_180001EC4
0x180001eb7  xor     ebx, ebx
0x180001eb9  mov     [rsp+108h+var_E8], ebx
0x180001ebd  mov     edi, [rsp+108h+arg_8]
0x180001ec4  cmp     edi, 1
0x180001ec7  ja      short loc_180001ED3
0x180001ec9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ed3  mov     eax, ebx
0x180001ed5  add     rsp, 0F0h
0x180001edc  pop     rdi
0x180001edd  pop     rsi
0x180001ede  pop     rbx
0x180001edf  retn
0x180012f10  push    rbp
0x180012f12  sub     rsp, 20h
0x180012f16  mov     rbp, rdx
0x180012f19  mov     rax, [rcx]
0x180012f1c  mov     edx, [rax]
0x180012f1e  mov     [rbp+0A8h], rcx
0x180012f25  mov     [rbp+28h], edx
0x180012f28  mov     eax, [rbp+28h]
0x180012f2b  cmp     eax, 0E06D7363h
0x180012f30  jnz     short loc_180012F46
0x180012f32  mov     rdx, [rbp+0A8h]
0x180012f39  mov     ecx, [rbp+28h]
0x180012f3c  call    _XcptFilter_0
0x180012f41  mov     [rbp+30h], eax
0x180012f44  jmp     short loc_180012F4D
0x180012f46  mov     dword ptr [rbp+30h], 0
0x180012f4d  mov     eax, [rbp+30h]
0x180012f50  add     rsp, 20h
0x180012f54  pop     rbp
0x180012f55  retn
0x180012f57  push    rbp
0x180012f59  sub     rsp, 20h
0x180012f5d  mov     rbp, rdx
0x180012f60  mov     rax, [rcx]
0x180012f63  mov     edx, [rax]
0x180012f65  mov     [rbp+0B0h], rcx
0x180012f6c  mov     [rbp+38h], edx
0x180012f6f  mov     eax, [rbp+38h]
0x180012f72  cmp     eax, 0E06D7363h
0x180012f77  jnz     short loc_180012F8D
0x180012f79  mov     rdx, [rbp+0B0h]
0x180012f80  mov     ecx, [rbp+38h]
0x180012f83  call    _XcptFilter_0
0x180012f88  mov     [rbp+40h], eax
0x180012f8b  jmp     short loc_180012F94
0x180012f8d  mov     dword ptr [rbp+40h], 0
0x180012f94  mov     eax, [rbp+40h]
0x180012f97  add     rsp, 20h
0x180012f9b  pop     rbp
0x180012f9c  retn
0x180012f9e  push    rbp
0x180012fa0  sub     rsp, 20h
0x180012fa4  mov     rbp, rdx
0x180012fa7  mov     rax, [rcx]
0x180012faa  mov     edx, [rax]
0x180012fac  mov     [rbp+0B8h], rcx
0x180012fb3  mov     [rbp+48h], edx
0x180012fb6  mov     eax, [rbp+48h]
0x180012fb9  cmp     eax, 0E06D7363h
0x180012fbe  jnz     short loc_180012FD4
0x180012fc0  mov     rdx, [rbp+0B8h]
0x180012fc7  mov     ecx, [rbp+48h]
0x180012fca  call    _XcptFilter_0
0x180012fcf  mov     [rbp+50h], eax
0x180012fd2  jmp     short loc_180012FDB
0x180012fd4  mov     dword ptr [rbp+50h], 0
0x180012fdb  mov     eax, [rbp+50h]
0x180012fde  add     rsp, 20h
0x180012fe2  pop     rbp
0x180012fe3  retn
0x180012fe5  push    rbp
0x180012fe7  sub     rsp, 20h
0x180012feb  mov     rbp, rdx
0x180012fee  mov     rax, [rcx]
0x180012ff1  mov     edx, [rax]
0x180012ff3  mov     [rbp+0C0h], rcx
0x180012ffa  mov     [rbp+58h], edx
0x180012ffd  mov     eax, [rbp+58h]
0x180013000  cmp     eax, 0E06D7363h
0x180013005  jnz     short loc_18001301B
0x180013007  mov     rdx, [rbp+0C0h]
0x18001300e  mov     ecx, [rbp+58h]
0x180013011  call    _XcptFilter_0
0x180013016  mov     [rbp+60h], eax
0x180013019  jmp     short loc_180013022
0x18001301b  mov     dword ptr [rbp+60h], 0
0x180013022  mov     eax, [rbp+60h]
0x180013025  add     rsp, 20h
0x180013029  pop     rbp
0x18001302a  retn
0x18001302c  push    rbp
0x18001302e  sub     rsp, 20h
0x180013032  mov     rbp, rdx
0x180013035  mov     rax, [rcx]
0x180013038  mov     edx, [rax]
0x18001303a  mov     [rbp+0C8h], rcx
0x180013041  mov     [rbp+68h], edx
0x180013044  mov     eax, [rbp+68h]
0x180013047  cmp     eax, 0E06D7363h
0x18001304c  jnz     short loc_180013062
0x18001304e  mov     rdx, [rbp+0C8h]
0x180013055  mov     ecx, [rbp+68h]
0x180013058  call    _XcptFilter_0
0x18001305d  mov     [rbp+70h], eax
0x180013060  jmp     short loc_180013069
0x180013062  mov     dword ptr [rbp+70h], 0
0x180013069  mov     eax, [rbp+70h]
0x18001306c  add     rsp, 20h
0x180013070  pop     rbp
0x180013071  retn
0x180013073  push    rbp
0x180013075  sub     rsp, 20h
0x180013079  mov     rbp, rdx
0x18001307c  mov     rax, [rcx]
0x18001307f  mov     edx, [rax]
0x180013081  mov     [rbp+0D0h], rcx
0x180013088  mov     [rbp+78h], edx
0x18001308b  mov     eax, [rbp+78h]
0x18001308e  cmp     eax, 0E06D7363h
0x180013093  jnz     short loc_1800130AC
0x180013095  mov     rdx, [rbp+0D0h]
0x18001309c  mov     ecx, [rbp+78h]
0x18001309f  call    _XcptFilter_0
0x1800130a4  mov     [rbp+80h], eax
0x1800130aa  jmp     short loc_1800130B6
0x1800130ac  mov     dword ptr [rbp+80h], 0
0x1800130b6  mov     eax, [rbp+80h]
0x1800130bc  add     rsp, 20h
0x1800130c0  pop     rbp
0x1800130c1  retn
0x1800130c3  push    rbp
0x1800130c5  sub     rsp, 20h
0x1800130c9  mov     rbp, rdx
0x1800130cc  mov     rax, [rcx]
0x1800130cf  mov     edx, [rax]
0x1800130d1  mov     [rbp+0D8h], rcx
0x1800130d8  mov     [rbp+88h], edx
0x1800130de  mov     eax, [rbp+88h]
0x1800130e4  cmp     eax, 0E06D7363h
0x1800130e9  jnz     short loc_180013105
0x1800130eb  mov     rdx, [rbp+0D8h]
0x1800130f2  mov     ecx, [rbp+88h]
0x1800130f8  call    _XcptFilter_0
0x1800130fd  mov     [rbp+90h], eax
0x180013103  jmp     short loc_18001310F
0x180013105  mov     dword ptr [rbp+90h], 0
0x18001310f  mov     eax, [rbp+90h]
0x180013115  add     rsp, 20h
0x180013119  pop     rbp
0x18001311a  retn
0x18001311c  push    rbp
0x18001311e  sub     rsp, 20h
0x180013122  mov     rbp, rdx
0x180013125  mov     rax, [rcx]
0x180013128  mov     edx, [rax]
0x18001312a  mov     [rbp+0E0h], rcx
0x180013131  mov     [rbp+98h], edx
0x180013137  mov     eax, [rbp+98h]
0x18001313d  cmp     eax, 0E06D7363h
0x180013142  jnz     short loc_18001315E
0x180013144  mov     rdx, [rbp+0E0h]
0x18001314b  mov     ecx, [rbp+98h]
0x180013151  call    _XcptFilter_0
0x180013156  mov     [rbp+0A0h], eax
0x18001315c  jmp     short loc_180013168
0x18001315e  mov     dword ptr [rbp+0A0h], 0
0x180013168  mov     eax, [rbp+0A0h]
0x18001316e  add     rsp, 20h
0x180013172  pop     rbp
0x180013173  retn
0x180013175  push    rbp
0x180013177  sub     rsp, 20h
0x18001317b  mov     rbp, rdx
0x18001317e  cmp     dword ptr [rbp+118h], 1
0x180013185  ja      short loc_180013191
0x180013187  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
