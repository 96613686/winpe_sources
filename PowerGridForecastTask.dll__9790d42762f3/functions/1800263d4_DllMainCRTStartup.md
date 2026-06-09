# __DllMainCRTStartup

- ea: `0x1800263d4`
- end: `0x1800265e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180026390`

## callees

- `0x180026160`
- `0x1800263d4`
- `0x180026943`
- `0x180030a98`
- `0x180035150`

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
  if ( (_DWORD)fdwReason || dword_180046884 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180046888 = 1;
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
            if ( dword_180046888 )
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
0x1800263d4  mov     [rsp+lpvReserved], r8
0x1800263d9  mov     [rsp+arg_8], edx
0x1800263dd  mov     [rsp+arg_0], rcx
0x1800263e2  push    rbx
0x1800263e3  push    rsi
0x1800263e4  push    rdi
0x1800263e5  sub     rsp, 0F0h
0x1800263ec  mov     edi, edx
0x1800263ee  mov     rsi, rcx
0x1800263f1  mov     ebx, 1
0x1800263f6  cmp     edx, ebx
0x1800263f8  ja      short loc_180026400
0x1800263fa  mov     cs:__native_dllmain_reason, edx
0x180026400  test    edx, edx
0x180026402  jnz     short loc_180026417
0x180026404  cmp     cs:dword_180046884, edx
0x18002640a  jnz     short loc_180026417
0x18002640c  xor     ebx, ebx
0x18002640e  mov     [rsp+108h+var_E8], ebx
0x180026412  jmp     loc_1800265C4
0x180026417  lea     eax, [rdx-1]
0x18002641a  cmp     eax, 1
0x18002641d  ja      loc_1800264A4
0x180026423  mov     rax, cs:_pRawDllMain
0x18002642a  test    rax, rax
0x18002642d  jz      short loc_180026465
0x18002642f  cmp     edx, 1
0x180026432  jnz     short loc_18002643A
0x180026434  mov     cs:dword_180046888, edx
0x18002643a  mov     r8, [rsp+108h+lpvReserved]
0x180026442  call    cs:__guard_dispatch_icall_fptr
0x180026448  mov     ebx, eax
0x18002644a  mov     [rsp+108h+var_E8], eax
0x18002644e  jmp     short loc_180026465
0x180026450  xor     ebx, ebx
0x180026452  mov     [rsp+108h+var_E8], ebx
0x180026456  mov     edi, [rsp+108h+arg_8]
0x18002645d  mov     rsi, [rsp+108h+arg_0]
0x180026465  test    ebx, ebx
0x180026467  jz      loc_1800265C4
0x18002646d  mov     r8, [rsp+108h+lpvReserved]
0x180026475  mov     edx, edi
0x180026477  mov     rcx, rsi
0x18002647a  call    _CRT_INIT
0x18002647f  mov     ebx, eax
0x180026481  mov     [rsp+108h+var_E8], eax
0x180026485  jmp     short loc_18002649C
0x180026487  xor     ebx, ebx
0x180026489  mov     [rsp+108h+var_E8], ebx
0x18002648d  mov     edi, [rsp+108h+arg_8]
0x180026494  mov     rsi, [rsp+108h+arg_0]
0x18002649c  test    ebx, ebx
0x18002649e  jz      loc_1800265C4
0x1800264a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800264ac  mov     edx, edi; fdwReason
0x1800264ae  mov     rcx, rsi; hinstDLL
0x1800264b1  call    DllMain
0x1800264b6  mov     ebx, eax
0x1800264b8  mov     [rsp+108h+var_E8], eax
0x1800264bc  jmp     short loc_1800264D3
0x1800264be  xor     ebx, ebx
0x1800264c0  mov     [rsp+108h+var_E8], ebx
0x1800264c4  mov     edi, [rsp+108h+arg_8]
0x1800264cb  mov     rsi, [rsp+108h+arg_0]
0x1800264d3  cmp     edi, 1
0x1800264d6  jnz     short loc_18002654F
0x1800264d8  test    ebx, ebx
0x1800264da  jnz     short loc_18002654F
0x1800264dc  xor     r8d, r8d; lpvReserved
0x1800264df  xor     edx, edx; fdwReason
0x1800264e1  mov     rcx, rsi; hinstDLL
0x1800264e4  call    DllMain
0x1800264e9  jmp     short loc_1800264FE
0x1800264eb  mov     edi, [rsp+108h+arg_8]
0x1800264f2  mov     rsi, [rsp+108h+arg_0]
0x1800264fa  mov     ebx, [rsp+108h+var_E8]
0x1800264fe  xor     r8d, r8d
0x180026501  xor     edx, edx
0x180026503  mov     rcx, rsi
0x180026506  call    _CRT_INIT
0x18002650b  jmp     short loc_180026520
0x18002650d  mov     edi, [rsp+108h+arg_8]
0x180026514  mov     rsi, [rsp+108h+arg_0]
0x18002651c  mov     ebx, [rsp+108h+var_E8]
0x180026520  mov     rax, cs:_pRawDllMain
0x180026527  test    rax, rax
0x18002652a  jz      short loc_18002654F
0x18002652c  xor     r8d, r8d
0x18002652f  xor     edx, edx
0x180026531  mov     rcx, rsi
0x180026534  call    cs:__guard_dispatch_icall_fptr
0x18002653a  jmp     short loc_18002654F
0x18002653c  mov     edi, [rsp+108h+arg_8]
0x180026543  mov     rsi, [rsp+108h+arg_0]
0x18002654b  mov     ebx, [rsp+108h+var_E8]
0x18002654f  test    edi, edi
0x180026551  jz      short loc_180026558
0x180026553  cmp     edi, 3
0x180026556  jnz     short loc_1800265C4
0x180026558  mov     r8, [rsp+108h+lpvReserved]
0x180026560  mov     edx, edi
0x180026562  mov     rcx, rsi
0x180026565  call    _CRT_INIT
0x18002656a  mov     ebx, eax
0x18002656c  mov     [rsp+108h+var_E8], eax
0x180026570  jmp     short loc_180026587
0x180026572  xor     ebx, ebx
0x180026574  mov     [rsp+108h+var_E8], ebx
0x180026578  mov     edi, [rsp+108h+arg_8]
0x18002657f  mov     rsi, [rsp+108h+arg_0]
0x180026587  mov     rax, cs:_pRawDllMain
0x18002658e  test    rax, rax
0x180026591  jz      short loc_1800265C4
0x180026593  cmp     cs:dword_180046888, 0
0x18002659a  jz      short loc_1800265C4
0x18002659c  mov     r8, [rsp+108h+lpvReserved]
0x1800265a4  mov     edx, edi
0x1800265a6  mov     rcx, rsi
0x1800265a9  call    cs:__guard_dispatch_icall_fptr
0x1800265af  mov     ebx, eax
0x1800265b1  mov     [rsp+108h+var_E8], eax
0x1800265b5  jmp     short loc_1800265C4
0x1800265b7  xor     ebx, ebx
0x1800265b9  mov     [rsp+108h+var_E8], ebx
0x1800265bd  mov     edi, [rsp+108h+arg_8]
0x1800265c4  cmp     edi, 1
0x1800265c7  ja      short loc_1800265D3
0x1800265c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800265d3  mov     eax, ebx
0x1800265d5  add     rsp, 0F0h
0x1800265dc  pop     rdi
0x1800265dd  pop     rsi
0x1800265de  pop     rbx
0x1800265df  retn
0x180035c31  push    rbp
0x180035c33  sub     rsp, 20h
0x180035c37  mov     rbp, rdx
0x180035c3a  mov     rax, [rcx]
0x180035c3d  mov     edx, [rax]
0x180035c3f  mov     [rbp+0A8h], rcx
0x180035c46  mov     [rbp+28h], edx
0x180035c49  mov     eax, [rbp+28h]
0x180035c4c  cmp     eax, 0E06D7363h
0x180035c51  jnz     short loc_180035C67
0x180035c53  mov     rdx, [rbp+0A8h]
0x180035c5a  mov     ecx, [rbp+28h]
0x180035c5d  call    _XcptFilter_0
0x180035c62  mov     [rbp+30h], eax
0x180035c65  jmp     short loc_180035C6E
0x180035c67  mov     dword ptr [rbp+30h], 0
0x180035c6e  mov     eax, [rbp+30h]
0x180035c71  add     rsp, 20h
0x180035c75  pop     rbp
0x180035c76  retn
0x180035c78  push    rbp
0x180035c7a  sub     rsp, 20h
0x180035c7e  mov     rbp, rdx
0x180035c81  mov     rax, [rcx]
0x180035c84  mov     edx, [rax]
0x180035c86  mov     [rbp+0B0h], rcx
0x180035c8d  mov     [rbp+38h], edx
0x180035c90  mov     eax, [rbp+38h]
0x180035c93  cmp     eax, 0E06D7363h
0x180035c98  jnz     short loc_180035CAE
0x180035c9a  mov     rdx, [rbp+0B0h]
0x180035ca1  mov     ecx, [rbp+38h]
0x180035ca4  call    _XcptFilter_0
0x180035ca9  mov     [rbp+40h], eax
0x180035cac  jmp     short loc_180035CB5
0x180035cae  mov     dword ptr [rbp+40h], 0
0x180035cb5  mov     eax, [rbp+40h]
0x180035cb8  add     rsp, 20h
0x180035cbc  pop     rbp
0x180035cbd  retn
0x180035cbf  push    rbp
0x180035cc1  sub     rsp, 20h
0x180035cc5  mov     rbp, rdx
0x180035cc8  mov     rax, [rcx]
0x180035ccb  mov     edx, [rax]
0x180035ccd  mov     [rbp+0B8h], rcx
0x180035cd4  mov     [rbp+48h], edx
0x180035cd7  mov     eax, [rbp+48h]
0x180035cda  cmp     eax, 0E06D7363h
0x180035cdf  jnz     short loc_180035CF5
0x180035ce1  mov     rdx, [rbp+0B8h]
0x180035ce8  mov     ecx, [rbp+48h]
0x180035ceb  call    _XcptFilter_0
0x180035cf0  mov     [rbp+50h], eax
0x180035cf3  jmp     short loc_180035CFC
0x180035cf5  mov     dword ptr [rbp+50h], 0
0x180035cfc  mov     eax, [rbp+50h]
0x180035cff  add     rsp, 20h
0x180035d03  pop     rbp
0x180035d04  retn
0x180035d06  push    rbp
0x180035d08  sub     rsp, 20h
0x180035d0c  mov     rbp, rdx
0x180035d0f  mov     rax, [rcx]
0x180035d12  mov     edx, [rax]
0x180035d14  mov     [rbp+0C0h], rcx
0x180035d1b  mov     [rbp+58h], edx
0x180035d1e  mov     eax, [rbp+58h]
0x180035d21  cmp     eax, 0E06D7363h
0x180035d26  jnz     short loc_180035D3C
0x180035d28  mov     rdx, [rbp+0C0h]
0x180035d2f  mov     ecx, [rbp+58h]
0x180035d32  call    _XcptFilter_0
0x180035d37  mov     [rbp+60h], eax
0x180035d3a  jmp     short loc_180035D43
0x180035d3c  mov     dword ptr [rbp+60h], 0
0x180035d43  mov     eax, [rbp+60h]
0x180035d46  add     rsp, 20h
0x180035d4a  pop     rbp
0x180035d4b  retn
0x180035d4d  push    rbp
0x180035d4f  sub     rsp, 20h
0x180035d53  mov     rbp, rdx
0x180035d56  mov     rax, [rcx]
0x180035d59  mov     edx, [rax]
0x180035d5b  mov     [rbp+0C8h], rcx
0x180035d62  mov     [rbp+68h], edx
0x180035d65  mov     eax, [rbp+68h]
0x180035d68  cmp     eax, 0E06D7363h
0x180035d6d  jnz     short loc_180035D83
0x180035d6f  mov     rdx, [rbp+0C8h]
0x180035d76  mov     ecx, [rbp+68h]
0x180035d79  call    _XcptFilter_0
0x180035d7e  mov     [rbp+70h], eax
0x180035d81  jmp     short loc_180035D8A
0x180035d83  mov     dword ptr [rbp+70h], 0
0x180035d8a  mov     eax, [rbp+70h]
0x180035d8d  add     rsp, 20h
0x180035d91  pop     rbp
0x180035d92  retn
0x180035d94  push    rbp
0x180035d96  sub     rsp, 20h
0x180035d9a  mov     rbp, rdx
0x180035d9d  mov     rax, [rcx]
0x180035da0  mov     edx, [rax]
0x180035da2  mov     [rbp+0D0h], rcx
0x180035da9  mov     [rbp+78h], edx
0x180035dac  mov     eax, [rbp+78h]
0x180035daf  cmp     eax, 0E06D7363h
0x180035db4  jnz     short loc_180035DCD
0x180035db6  mov     rdx, [rbp+0D0h]
0x180035dbd  mov     ecx, [rbp+78h]
0x180035dc0  call    _XcptFilter_0
0x180035dc5  mov     [rbp+80h], eax
0x180035dcb  jmp     short loc_180035DD7
0x180035dcd  mov     dword ptr [rbp+80h], 0
0x180035dd7  mov     eax, [rbp+80h]
0x180035ddd  add     rsp, 20h
0x180035de1  pop     rbp
0x180035de2  retn
0x180035de4  push    rbp
0x180035de6  sub     rsp, 20h
0x180035dea  mov     rbp, rdx
0x180035ded  mov     rax, [rcx]
0x180035df0  mov     edx, [rax]
0x180035df2  mov     [rbp+0D8h], rcx
0x180035df9  mov     [rbp+88h], edx
0x180035dff  mov     eax, [rbp+88h]
0x180035e05  cmp     eax, 0E06D7363h
0x180035e0a  jnz     short loc_180035E26
0x180035e0c  mov     rdx, [rbp+0D8h]
0x180035e13  mov     ecx, [rbp+88h]
0x180035e19  call    _XcptFilter_0
0x180035e1e  mov     [rbp+90h], eax
0x180035e24  jmp     short loc_180035E30
0x180035e26  mov     dword ptr [rbp+90h], 0
0x180035e30  mov     eax, [rbp+90h]
0x180035e36  add     rsp, 20h
0x180035e3a  pop     rbp
0x180035e3b  retn
0x180035e3d  push    rbp
0x180035e3f  sub     rsp, 20h
0x180035e43  mov     rbp, rdx
0x180035e46  mov     rax, [rcx]
0x180035e49  mov     edx, [rax]
0x180035e4b  mov     [rbp+0E0h], rcx
0x180035e52  mov     [rbp+98h], edx
0x180035e58  mov     eax, [rbp+98h]
0x180035e5e  cmp     eax, 0E06D7363h
0x180035e63  jnz     short loc_180035E7F
0x180035e65  mov     rdx, [rbp+0E0h]
0x180035e6c  mov     ecx, [rbp+98h]
0x180035e72  call    _XcptFilter_0
0x180035e77  mov     [rbp+0A0h], eax
0x180035e7d  jmp     short loc_180035E89
0x180035e7f  mov     dword ptr [rbp+0A0h], 0
0x180035e89  mov     eax, [rbp+0A0h]
0x180035e8f  add     rsp, 20h
0x180035e93  pop     rbp
0x180035e94  retn
0x180035e96  push    rbp
0x180035e98  sub     rsp, 20h
0x180035e9c  mov     rbp, rdx
0x180035e9f  cmp     dword ptr [rbp+118h], 1
0x180035ea6  ja      short loc_180035EB2
0x180035ea8  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
