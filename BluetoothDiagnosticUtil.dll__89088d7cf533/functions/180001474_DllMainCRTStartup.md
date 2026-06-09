# __DllMainCRTStartup

- ea: `0x180001474`
- end: `0x180001680`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001430`

## callees

- `0x180001200`
- `0x180001474`
- `0x180001819`
- `0x18000878c`
- `0x180009d00`

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
  if ( (_DWORD)fdwReason || dword_1800101C4 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800101C8 = 1;
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
            if ( dword_1800101C8 )
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
0x180001474  mov     [rsp+lpvReserved], r8
0x180001479  mov     [rsp+arg_8], edx
0x18000147d  mov     [rsp+arg_0], rcx
0x180001482  push    rbx
0x180001483  push    rsi
0x180001484  push    rdi
0x180001485  sub     rsp, 0F0h
0x18000148c  mov     edi, edx
0x18000148e  mov     rsi, rcx
0x180001491  mov     ebx, 1
0x180001496  cmp     edx, ebx
0x180001498  ja      short loc_1800014A0
0x18000149a  mov     cs:__native_dllmain_reason, edx
0x1800014a0  test    edx, edx
0x1800014a2  jnz     short loc_1800014B7
0x1800014a4  cmp     cs:dword_1800101C4, edx
0x1800014aa  jnz     short loc_1800014B7
0x1800014ac  xor     ebx, ebx
0x1800014ae  mov     [rsp+108h+var_E8], ebx
0x1800014b2  jmp     loc_180001664
0x1800014b7  lea     eax, [rdx-1]
0x1800014ba  cmp     eax, 1
0x1800014bd  ja      loc_180001544
0x1800014c3  mov     rax, cs:_pRawDllMain
0x1800014ca  test    rax, rax
0x1800014cd  jz      short loc_180001505
0x1800014cf  cmp     edx, 1
0x1800014d2  jnz     short loc_1800014DA
0x1800014d4  mov     cs:dword_1800101C8, edx
0x1800014da  mov     r8, [rsp+108h+lpvReserved]
0x1800014e2  call    cs:__guard_dispatch_icall_fptr
0x1800014e8  mov     ebx, eax
0x1800014ea  mov     [rsp+108h+var_E8], eax
0x1800014ee  jmp     short loc_180001505
0x1800014f0  xor     ebx, ebx
0x1800014f2  mov     [rsp+108h+var_E8], ebx
0x1800014f6  mov     edi, [rsp+108h+arg_8]
0x1800014fd  mov     rsi, [rsp+108h+arg_0]
0x180001505  test    ebx, ebx
0x180001507  jz      loc_180001664
0x18000150d  mov     r8, [rsp+108h+lpvReserved]
0x180001515  mov     edx, edi
0x180001517  mov     rcx, rsi
0x18000151a  call    _CRT_INIT
0x18000151f  mov     ebx, eax
0x180001521  mov     [rsp+108h+var_E8], eax
0x180001525  jmp     short loc_18000153C
0x180001527  xor     ebx, ebx
0x180001529  mov     [rsp+108h+var_E8], ebx
0x18000152d  mov     edi, [rsp+108h+arg_8]
0x180001534  mov     rsi, [rsp+108h+arg_0]
0x18000153c  test    ebx, ebx
0x18000153e  jz      loc_180001664
0x180001544  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000154c  mov     edx, edi; fdwReason
0x18000154e  mov     rcx, rsi; hinstDLL
0x180001551  call    DllMain
0x180001556  mov     ebx, eax
0x180001558  mov     [rsp+108h+var_E8], eax
0x18000155c  jmp     short loc_180001573
0x18000155e  xor     ebx, ebx
0x180001560  mov     [rsp+108h+var_E8], ebx
0x180001564  mov     edi, [rsp+108h+arg_8]
0x18000156b  mov     rsi, [rsp+108h+arg_0]
0x180001573  cmp     edi, 1
0x180001576  jnz     short loc_1800015EF
0x180001578  test    ebx, ebx
0x18000157a  jnz     short loc_1800015EF
0x18000157c  xor     r8d, r8d; lpvReserved
0x18000157f  xor     edx, edx; fdwReason
0x180001581  mov     rcx, rsi; hinstDLL
0x180001584  call    DllMain
0x180001589  jmp     short loc_18000159E
0x18000158b  mov     edi, [rsp+108h+arg_8]
0x180001592  mov     rsi, [rsp+108h+arg_0]
0x18000159a  mov     ebx, [rsp+108h+var_E8]
0x18000159e  xor     r8d, r8d
0x1800015a1  xor     edx, edx
0x1800015a3  mov     rcx, rsi
0x1800015a6  call    _CRT_INIT
0x1800015ab  jmp     short loc_1800015C0
0x1800015ad  mov     edi, [rsp+108h+arg_8]
0x1800015b4  mov     rsi, [rsp+108h+arg_0]
0x1800015bc  mov     ebx, [rsp+108h+var_E8]
0x1800015c0  mov     rax, cs:_pRawDllMain
0x1800015c7  test    rax, rax
0x1800015ca  jz      short loc_1800015EF
0x1800015cc  xor     r8d, r8d
0x1800015cf  xor     edx, edx
0x1800015d1  mov     rcx, rsi
0x1800015d4  call    cs:__guard_dispatch_icall_fptr
0x1800015da  jmp     short loc_1800015EF
0x1800015dc  mov     edi, [rsp+108h+arg_8]
0x1800015e3  mov     rsi, [rsp+108h+arg_0]
0x1800015eb  mov     ebx, [rsp+108h+var_E8]
0x1800015ef  test    edi, edi
0x1800015f1  jz      short loc_1800015F8
0x1800015f3  cmp     edi, 3
0x1800015f6  jnz     short loc_180001664
0x1800015f8  mov     r8, [rsp+108h+lpvReserved]
0x180001600  mov     edx, edi
0x180001602  mov     rcx, rsi
0x180001605  call    _CRT_INIT
0x18000160a  mov     ebx, eax
0x18000160c  mov     [rsp+108h+var_E8], eax
0x180001610  jmp     short loc_180001627
0x180001612  xor     ebx, ebx
0x180001614  mov     [rsp+108h+var_E8], ebx
0x180001618  mov     edi, [rsp+108h+arg_8]
0x18000161f  mov     rsi, [rsp+108h+arg_0]
0x180001627  mov     rax, cs:_pRawDllMain
0x18000162e  test    rax, rax
0x180001631  jz      short loc_180001664
0x180001633  cmp     cs:dword_1800101C8, 0
0x18000163a  jz      short loc_180001664
0x18000163c  mov     r8, [rsp+108h+lpvReserved]
0x180001644  mov     edx, edi
0x180001646  mov     rcx, rsi
0x180001649  call    cs:__guard_dispatch_icall_fptr
0x18000164f  mov     ebx, eax
0x180001651  mov     [rsp+108h+var_E8], eax
0x180001655  jmp     short loc_180001664
0x180001657  xor     ebx, ebx
0x180001659  mov     [rsp+108h+var_E8], ebx
0x18000165d  mov     edi, [rsp+108h+arg_8]
0x180001664  cmp     edi, 1
0x180001667  ja      short loc_180001673
0x180001669  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001673  mov     eax, ebx
0x180001675  add     rsp, 0F0h
0x18000167c  pop     rdi
0x18000167d  pop     rsi
0x18000167e  pop     rbx
0x18000167f  retn
0x180009da3  push    rbp
0x180009da5  sub     rsp, 20h
0x180009da9  mov     rbp, rdx
0x180009dac  mov     rax, [rcx]
0x180009daf  mov     edx, [rax]
0x180009db1  mov     [rbp+0A8h], rcx
0x180009db8  mov     [rbp+28h], edx
0x180009dbb  mov     eax, [rbp+28h]
0x180009dbe  cmp     eax, 0E06D7363h
0x180009dc3  jnz     short loc_180009DD9
0x180009dc5  mov     rdx, [rbp+0A8h]
0x180009dcc  mov     ecx, [rbp+28h]
0x180009dcf  call    _XcptFilter_0
0x180009dd4  mov     [rbp+30h], eax
0x180009dd7  jmp     short loc_180009DE0
0x180009dd9  mov     dword ptr [rbp+30h], 0
0x180009de0  mov     eax, [rbp+30h]
0x180009de3  add     rsp, 20h
0x180009de7  pop     rbp
0x180009de8  retn
0x180009dea  push    rbp
0x180009dec  sub     rsp, 20h
0x180009df0  mov     rbp, rdx
0x180009df3  mov     rax, [rcx]
0x180009df6  mov     edx, [rax]
0x180009df8  mov     [rbp+0B0h], rcx
0x180009dff  mov     [rbp+38h], edx
0x180009e02  mov     eax, [rbp+38h]
0x180009e05  cmp     eax, 0E06D7363h
0x180009e0a  jnz     short loc_180009E20
0x180009e0c  mov     rdx, [rbp+0B0h]
0x180009e13  mov     ecx, [rbp+38h]
0x180009e16  call    _XcptFilter_0
0x180009e1b  mov     [rbp+40h], eax
0x180009e1e  jmp     short loc_180009E27
0x180009e20  mov     dword ptr [rbp+40h], 0
0x180009e27  mov     eax, [rbp+40h]
0x180009e2a  add     rsp, 20h
0x180009e2e  pop     rbp
0x180009e2f  retn
0x180009e31  push    rbp
0x180009e33  sub     rsp, 20h
0x180009e37  mov     rbp, rdx
0x180009e3a  mov     rax, [rcx]
0x180009e3d  mov     edx, [rax]
0x180009e3f  mov     [rbp+0B8h], rcx
0x180009e46  mov     [rbp+48h], edx
0x180009e49  mov     eax, [rbp+48h]
0x180009e4c  cmp     eax, 0E06D7363h
0x180009e51  jnz     short loc_180009E67
0x180009e53  mov     rdx, [rbp+0B8h]
0x180009e5a  mov     ecx, [rbp+48h]
0x180009e5d  call    _XcptFilter_0
0x180009e62  mov     [rbp+50h], eax
0x180009e65  jmp     short loc_180009E6E
0x180009e67  mov     dword ptr [rbp+50h], 0
0x180009e6e  mov     eax, [rbp+50h]
0x180009e71  add     rsp, 20h
0x180009e75  pop     rbp
0x180009e76  retn
0x180009e78  push    rbp
0x180009e7a  sub     rsp, 20h
0x180009e7e  mov     rbp, rdx
0x180009e81  mov     rax, [rcx]
0x180009e84  mov     edx, [rax]
0x180009e86  mov     [rbp+0C0h], rcx
0x180009e8d  mov     [rbp+58h], edx
0x180009e90  mov     eax, [rbp+58h]
0x180009e93  cmp     eax, 0E06D7363h
0x180009e98  jnz     short loc_180009EAE
0x180009e9a  mov     rdx, [rbp+0C0h]
0x180009ea1  mov     ecx, [rbp+58h]
0x180009ea4  call    _XcptFilter_0
0x180009ea9  mov     [rbp+60h], eax
0x180009eac  jmp     short loc_180009EB5
0x180009eae  mov     dword ptr [rbp+60h], 0
0x180009eb5  mov     eax, [rbp+60h]
0x180009eb8  add     rsp, 20h
0x180009ebc  pop     rbp
0x180009ebd  retn
0x180009ebf  push    rbp
0x180009ec1  sub     rsp, 20h
0x180009ec5  mov     rbp, rdx
0x180009ec8  mov     rax, [rcx]
0x180009ecb  mov     edx, [rax]
0x180009ecd  mov     [rbp+0C8h], rcx
0x180009ed4  mov     [rbp+68h], edx
0x180009ed7  mov     eax, [rbp+68h]
0x180009eda  cmp     eax, 0E06D7363h
0x180009edf  jnz     short loc_180009EF5
0x180009ee1  mov     rdx, [rbp+0C8h]
0x180009ee8  mov     ecx, [rbp+68h]
0x180009eeb  call    _XcptFilter_0
0x180009ef0  mov     [rbp+70h], eax
0x180009ef3  jmp     short loc_180009EFC
0x180009ef5  mov     dword ptr [rbp+70h], 0
0x180009efc  mov     eax, [rbp+70h]
0x180009eff  add     rsp, 20h
0x180009f03  pop     rbp
0x180009f04  retn
0x180009f06  push    rbp
0x180009f08  sub     rsp, 20h
0x180009f0c  mov     rbp, rdx
0x180009f0f  mov     rax, [rcx]
0x180009f12  mov     edx, [rax]
0x180009f14  mov     [rbp+0D0h], rcx
0x180009f1b  mov     [rbp+78h], edx
0x180009f1e  mov     eax, [rbp+78h]
0x180009f21  cmp     eax, 0E06D7363h
0x180009f26  jnz     short loc_180009F3F
0x180009f28  mov     rdx, [rbp+0D0h]
0x180009f2f  mov     ecx, [rbp+78h]
0x180009f32  call    _XcptFilter_0
0x180009f37  mov     [rbp+80h], eax
0x180009f3d  jmp     short loc_180009F49
0x180009f3f  mov     dword ptr [rbp+80h], 0
0x180009f49  mov     eax, [rbp+80h]
0x180009f4f  add     rsp, 20h
0x180009f53  pop     rbp
0x180009f54  retn
0x180009f56  push    rbp
0x180009f58  sub     rsp, 20h
0x180009f5c  mov     rbp, rdx
0x180009f5f  mov     rax, [rcx]
0x180009f62  mov     edx, [rax]
0x180009f64  mov     [rbp+0D8h], rcx
0x180009f6b  mov     [rbp+88h], edx
0x180009f71  mov     eax, [rbp+88h]
0x180009f77  cmp     eax, 0E06D7363h
0x180009f7c  jnz     short loc_180009F98
0x180009f7e  mov     rdx, [rbp+0D8h]
0x180009f85  mov     ecx, [rbp+88h]
0x180009f8b  call    _XcptFilter_0
0x180009f90  mov     [rbp+90h], eax
0x180009f96  jmp     short loc_180009FA2
0x180009f98  mov     dword ptr [rbp+90h], 0
0x180009fa2  mov     eax, [rbp+90h]
0x180009fa8  add     rsp, 20h
0x180009fac  pop     rbp
0x180009fad  retn
0x180009faf  push    rbp
0x180009fb1  sub     rsp, 20h
0x180009fb5  mov     rbp, rdx
0x180009fb8  mov     rax, [rcx]
0x180009fbb  mov     edx, [rax]
0x180009fbd  mov     [rbp+0E0h], rcx
0x180009fc4  mov     [rbp+98h], edx
0x180009fca  mov     eax, [rbp+98h]
0x180009fd0  cmp     eax, 0E06D7363h
0x180009fd5  jnz     short loc_180009FF1
0x180009fd7  mov     rdx, [rbp+0E0h]
0x180009fde  mov     ecx, [rbp+98h]
0x180009fe4  call    _XcptFilter_0
0x180009fe9  mov     [rbp+0A0h], eax
0x180009fef  jmp     short loc_180009FFB
0x180009ff1  mov     dword ptr [rbp+0A0h], 0
0x180009ffb  mov     eax, [rbp+0A0h]
0x18000a001  add     rsp, 20h
0x18000a005  pop     rbp
0x18000a006  retn
0x18000a008  push    rbp
0x18000a00a  sub     rsp, 20h
0x18000a00e  mov     rbp, rdx
0x18000a011  cmp     dword ptr [rbp+118h], 1
0x18000a018  ja      short loc_18000A024
0x18000a01a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
