# __DllMainCRTStartup

- ea: `0x180004be4`
- end: `0x180004df0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004ba0`

## callees

- `0x180004830`
- `0x180004970`
- `0x180004be4`
- `0x180004df6`
- `0x180006140`

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
  if ( (_DWORD)fdwReason || dword_1800090A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090A4 = 1;
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
            if ( dword_1800090A4 )
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
0x180004be4  mov     [rsp+lpvReserved], r8
0x180004be9  mov     [rsp+arg_8], edx
0x180004bed  mov     [rsp+arg_0], rcx
0x180004bf2  push    rbx
0x180004bf3  push    rsi
0x180004bf4  push    rdi
0x180004bf5  sub     rsp, 0F0h
0x180004bfc  mov     edi, edx
0x180004bfe  mov     rsi, rcx
0x180004c01  mov     ebx, 1
0x180004c06  cmp     edx, ebx
0x180004c08  ja      short loc_180004C10
0x180004c0a  mov     cs:__native_dllmain_reason, edx
0x180004c10  test    edx, edx
0x180004c12  jnz     short loc_180004C27
0x180004c14  cmp     cs:dword_1800090A0, edx
0x180004c1a  jnz     short loc_180004C27
0x180004c1c  xor     ebx, ebx
0x180004c1e  mov     [rsp+108h+var_E8], ebx
0x180004c22  jmp     loc_180004DD4
0x180004c27  lea     eax, [rdx-1]
0x180004c2a  cmp     eax, 1
0x180004c2d  ja      loc_180004CB4
0x180004c33  mov     rax, cs:_pRawDllMain
0x180004c3a  test    rax, rax
0x180004c3d  jz      short loc_180004C75
0x180004c3f  cmp     edx, 1
0x180004c42  jnz     short loc_180004C4A
0x180004c44  mov     cs:dword_1800090A4, edx
0x180004c4a  mov     r8, [rsp+108h+lpvReserved]
0x180004c52  call    cs:__guard_dispatch_icall_fptr
0x180004c58  mov     ebx, eax
0x180004c5a  mov     [rsp+108h+var_E8], eax
0x180004c5e  jmp     short loc_180004C75
0x180004c60  xor     ebx, ebx
0x180004c62  mov     [rsp+108h+var_E8], ebx
0x180004c66  mov     edi, [rsp+108h+arg_8]
0x180004c6d  mov     rsi, [rsp+108h+arg_0]
0x180004c75  test    ebx, ebx
0x180004c77  jz      loc_180004DD4
0x180004c7d  mov     r8, [rsp+108h+lpvReserved]
0x180004c85  mov     edx, edi
0x180004c87  mov     rcx, rsi
0x180004c8a  call    _CRT_INIT
0x180004c8f  mov     ebx, eax
0x180004c91  mov     [rsp+108h+var_E8], eax
0x180004c95  jmp     short loc_180004CAC
0x180004c97  xor     ebx, ebx
0x180004c99  mov     [rsp+108h+var_E8], ebx
0x180004c9d  mov     edi, [rsp+108h+arg_8]
0x180004ca4  mov     rsi, [rsp+108h+arg_0]
0x180004cac  test    ebx, ebx
0x180004cae  jz      loc_180004DD4
0x180004cb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180004cbc  mov     edx, edi; fdwReason
0x180004cbe  mov     rcx, rsi; hinstDLL
0x180004cc1  call    DllMain
0x180004cc6  mov     ebx, eax
0x180004cc8  mov     [rsp+108h+var_E8], eax
0x180004ccc  jmp     short loc_180004CE3
0x180004cce  xor     ebx, ebx
0x180004cd0  mov     [rsp+108h+var_E8], ebx
0x180004cd4  mov     edi, [rsp+108h+arg_8]
0x180004cdb  mov     rsi, [rsp+108h+arg_0]
0x180004ce3  cmp     edi, 1
0x180004ce6  jnz     short loc_180004D5F
0x180004ce8  test    ebx, ebx
0x180004cea  jnz     short loc_180004D5F
0x180004cec  xor     r8d, r8d; lpvReserved
0x180004cef  xor     edx, edx; fdwReason
0x180004cf1  mov     rcx, rsi; hinstDLL
0x180004cf4  call    DllMain
0x180004cf9  jmp     short loc_180004D0E
0x180004cfb  mov     edi, [rsp+108h+arg_8]
0x180004d02  mov     rsi, [rsp+108h+arg_0]
0x180004d0a  mov     ebx, [rsp+108h+var_E8]
0x180004d0e  xor     r8d, r8d
0x180004d11  xor     edx, edx
0x180004d13  mov     rcx, rsi
0x180004d16  call    _CRT_INIT
0x180004d1b  jmp     short loc_180004D30
0x180004d1d  mov     edi, [rsp+108h+arg_8]
0x180004d24  mov     rsi, [rsp+108h+arg_0]
0x180004d2c  mov     ebx, [rsp+108h+var_E8]
0x180004d30  mov     rax, cs:_pRawDllMain
0x180004d37  test    rax, rax
0x180004d3a  jz      short loc_180004D5F
0x180004d3c  xor     r8d, r8d
0x180004d3f  xor     edx, edx
0x180004d41  mov     rcx, rsi
0x180004d44  call    cs:__guard_dispatch_icall_fptr
0x180004d4a  jmp     short loc_180004D5F
0x180004d4c  mov     edi, [rsp+108h+arg_8]
0x180004d53  mov     rsi, [rsp+108h+arg_0]
0x180004d5b  mov     ebx, [rsp+108h+var_E8]
0x180004d5f  test    edi, edi
0x180004d61  jz      short loc_180004D68
0x180004d63  cmp     edi, 3
0x180004d66  jnz     short loc_180004DD4
0x180004d68  mov     r8, [rsp+108h+lpvReserved]
0x180004d70  mov     edx, edi
0x180004d72  mov     rcx, rsi
0x180004d75  call    _CRT_INIT
0x180004d7a  mov     ebx, eax
0x180004d7c  mov     [rsp+108h+var_E8], eax
0x180004d80  jmp     short loc_180004D97
0x180004d82  xor     ebx, ebx
0x180004d84  mov     [rsp+108h+var_E8], ebx
0x180004d88  mov     edi, [rsp+108h+arg_8]
0x180004d8f  mov     rsi, [rsp+108h+arg_0]
0x180004d97  mov     rax, cs:_pRawDllMain
0x180004d9e  test    rax, rax
0x180004da1  jz      short loc_180004DD4
0x180004da3  cmp     cs:dword_1800090A4, 0
0x180004daa  jz      short loc_180004DD4
0x180004dac  mov     r8, [rsp+108h+lpvReserved]
0x180004db4  mov     edx, edi
0x180004db6  mov     rcx, rsi
0x180004db9  call    cs:__guard_dispatch_icall_fptr
0x180004dbf  mov     ebx, eax
0x180004dc1  mov     [rsp+108h+var_E8], eax
0x180004dc5  jmp     short loc_180004DD4
0x180004dc7  xor     ebx, ebx
0x180004dc9  mov     [rsp+108h+var_E8], ebx
0x180004dcd  mov     edi, [rsp+108h+arg_8]
0x180004dd4  cmp     edi, 1
0x180004dd7  ja      short loc_180004DE3
0x180004dd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180004de3  mov     eax, ebx
0x180004de5  add     rsp, 0F0h
0x180004dec  pop     rdi
0x180004ded  pop     rsi
0x180004dee  pop     rbx
0x180004def  retn
0x180006180  push    rbp
0x180006182  sub     rsp, 20h
0x180006186  mov     rbp, rdx
0x180006189  mov     rax, [rcx]
0x18000618c  mov     edx, [rax]
0x18000618e  mov     [rbp+0A8h], rcx
0x180006195  mov     [rbp+28h], edx
0x180006198  mov     eax, [rbp+28h]
0x18000619b  cmp     eax, 0E06D7363h
0x1800061a0  jnz     short loc_1800061B6
0x1800061a2  mov     rdx, [rbp+0A8h]
0x1800061a9  mov     ecx, [rbp+28h]
0x1800061ac  call    _XcptFilter_0
0x1800061b1  mov     [rbp+30h], eax
0x1800061b4  jmp     short loc_1800061BD
0x1800061b6  mov     dword ptr [rbp+30h], 0
0x1800061bd  mov     eax, [rbp+30h]
0x1800061c0  add     rsp, 20h
0x1800061c4  pop     rbp
0x1800061c5  retn
0x1800061c7  push    rbp
0x1800061c9  sub     rsp, 20h
0x1800061cd  mov     rbp, rdx
0x1800061d0  mov     rax, [rcx]
0x1800061d3  mov     edx, [rax]
0x1800061d5  mov     [rbp+0B0h], rcx
0x1800061dc  mov     [rbp+38h], edx
0x1800061df  mov     eax, [rbp+38h]
0x1800061e2  cmp     eax, 0E06D7363h
0x1800061e7  jnz     short loc_1800061FD
0x1800061e9  mov     rdx, [rbp+0B0h]
0x1800061f0  mov     ecx, [rbp+38h]
0x1800061f3  call    _XcptFilter_0
0x1800061f8  mov     [rbp+40h], eax
0x1800061fb  jmp     short loc_180006204
0x1800061fd  mov     dword ptr [rbp+40h], 0
0x180006204  mov     eax, [rbp+40h]
0x180006207  add     rsp, 20h
0x18000620b  pop     rbp
0x18000620c  retn
0x18000620e  push    rbp
0x180006210  sub     rsp, 20h
0x180006214  mov     rbp, rdx
0x180006217  mov     rax, [rcx]
0x18000621a  mov     edx, [rax]
0x18000621c  mov     [rbp+0B8h], rcx
0x180006223  mov     [rbp+48h], edx
0x180006226  mov     eax, [rbp+48h]
0x180006229  cmp     eax, 0E06D7363h
0x18000622e  jnz     short loc_180006244
0x180006230  mov     rdx, [rbp+0B8h]
0x180006237  mov     ecx, [rbp+48h]
0x18000623a  call    _XcptFilter_0
0x18000623f  mov     [rbp+50h], eax
0x180006242  jmp     short loc_18000624B
0x180006244  mov     dword ptr [rbp+50h], 0
0x18000624b  mov     eax, [rbp+50h]
0x18000624e  add     rsp, 20h
0x180006252  pop     rbp
0x180006253  retn
0x180006255  push    rbp
0x180006257  sub     rsp, 20h
0x18000625b  mov     rbp, rdx
0x18000625e  mov     rax, [rcx]
0x180006261  mov     edx, [rax]
0x180006263  mov     [rbp+0C0h], rcx
0x18000626a  mov     [rbp+58h], edx
0x18000626d  mov     eax, [rbp+58h]
0x180006270  cmp     eax, 0E06D7363h
0x180006275  jnz     short loc_18000628B
0x180006277  mov     rdx, [rbp+0C0h]
0x18000627e  mov     ecx, [rbp+58h]
0x180006281  call    _XcptFilter_0
0x180006286  mov     [rbp+60h], eax
0x180006289  jmp     short loc_180006292
0x18000628b  mov     dword ptr [rbp+60h], 0
0x180006292  mov     eax, [rbp+60h]
0x180006295  add     rsp, 20h
0x180006299  pop     rbp
0x18000629a  retn
0x18000629c  push    rbp
0x18000629e  sub     rsp, 20h
0x1800062a2  mov     rbp, rdx
0x1800062a5  mov     rax, [rcx]
0x1800062a8  mov     edx, [rax]
0x1800062aa  mov     [rbp+0C8h], rcx
0x1800062b1  mov     [rbp+68h], edx
0x1800062b4  mov     eax, [rbp+68h]
0x1800062b7  cmp     eax, 0E06D7363h
0x1800062bc  jnz     short loc_1800062D2
0x1800062be  mov     rdx, [rbp+0C8h]
0x1800062c5  mov     ecx, [rbp+68h]
0x1800062c8  call    _XcptFilter_0
0x1800062cd  mov     [rbp+70h], eax
0x1800062d0  jmp     short loc_1800062D9
0x1800062d2  mov     dword ptr [rbp+70h], 0
0x1800062d9  mov     eax, [rbp+70h]
0x1800062dc  add     rsp, 20h
0x1800062e0  pop     rbp
0x1800062e1  retn
0x1800062e3  push    rbp
0x1800062e5  sub     rsp, 20h
0x1800062e9  mov     rbp, rdx
0x1800062ec  mov     rax, [rcx]
0x1800062ef  mov     edx, [rax]
0x1800062f1  mov     [rbp+0D0h], rcx
0x1800062f8  mov     [rbp+78h], edx
0x1800062fb  mov     eax, [rbp+78h]
0x1800062fe  cmp     eax, 0E06D7363h
0x180006303  jnz     short loc_18000631C
0x180006305  mov     rdx, [rbp+0D0h]
0x18000630c  mov     ecx, [rbp+78h]
0x18000630f  call    _XcptFilter_0
0x180006314  mov     [rbp+80h], eax
0x18000631a  jmp     short loc_180006326
0x18000631c  mov     dword ptr [rbp+80h], 0
0x180006326  mov     eax, [rbp+80h]
0x18000632c  add     rsp, 20h
0x180006330  pop     rbp
0x180006331  retn
0x180006333  push    rbp
0x180006335  sub     rsp, 20h
0x180006339  mov     rbp, rdx
0x18000633c  mov     rax, [rcx]
0x18000633f  mov     edx, [rax]
0x180006341  mov     [rbp+0D8h], rcx
0x180006348  mov     [rbp+88h], edx
0x18000634e  mov     eax, [rbp+88h]
0x180006354  cmp     eax, 0E06D7363h
0x180006359  jnz     short loc_180006375
0x18000635b  mov     rdx, [rbp+0D8h]
0x180006362  mov     ecx, [rbp+88h]
0x180006368  call    _XcptFilter_0
0x18000636d  mov     [rbp+90h], eax
0x180006373  jmp     short loc_18000637F
0x180006375  mov     dword ptr [rbp+90h], 0
0x18000637f  mov     eax, [rbp+90h]
0x180006385  add     rsp, 20h
0x180006389  pop     rbp
0x18000638a  retn
0x18000638c  push    rbp
0x18000638e  sub     rsp, 20h
0x180006392  mov     rbp, rdx
0x180006395  mov     rax, [rcx]
0x180006398  mov     edx, [rax]
0x18000639a  mov     [rbp+0E0h], rcx
0x1800063a1  mov     [rbp+98h], edx
0x1800063a7  mov     eax, [rbp+98h]
0x1800063ad  cmp     eax, 0E06D7363h
0x1800063b2  jnz     short loc_1800063CE
0x1800063b4  mov     rdx, [rbp+0E0h]
0x1800063bb  mov     ecx, [rbp+98h]
0x1800063c1  call    _XcptFilter_0
0x1800063c6  mov     [rbp+0A0h], eax
0x1800063cc  jmp     short loc_1800063D8
0x1800063ce  mov     dword ptr [rbp+0A0h], 0
0x1800063d8  mov     eax, [rbp+0A0h]
0x1800063de  add     rsp, 20h
0x1800063e2  pop     rbp
0x1800063e3  retn
0x1800063e5  push    rbp
0x1800063e7  sub     rsp, 20h
0x1800063eb  mov     rbp, rdx
0x1800063ee  cmp     dword ptr [rbp+118h], 1
0x1800063f5  ja      short loc_180006401
0x1800063f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
