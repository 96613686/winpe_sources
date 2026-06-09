# __DllMainCRTStartup

- ea: `0x1800013a4`
- end: `0x1800015b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x180001130`
- `0x1800013a4`
- `0x1800018e0`
- `0x18000b4b8`
- `0x18001b9c0`

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
  if ( (_DWORD)fdwReason || dword_180025240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180025244 = 1;
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
            if ( dword_180025244 )
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
0x1800013a4  mov     [rsp+lpvReserved], r8
0x1800013a9  mov     [rsp+arg_8], edx
0x1800013ad  mov     [rsp+arg_0], rcx
0x1800013b2  push    rbx
0x1800013b3  push    rsi
0x1800013b4  push    rdi
0x1800013b5  sub     rsp, 0F0h
0x1800013bc  mov     edi, edx
0x1800013be  mov     rsi, rcx
0x1800013c1  mov     ebx, 1
0x1800013c6  cmp     edx, ebx
0x1800013c8  ja      short loc_1800013D0
0x1800013ca  mov     cs:__native_dllmain_reason, edx
0x1800013d0  test    edx, edx
0x1800013d2  jnz     short loc_1800013E7
0x1800013d4  cmp     cs:dword_180025240, edx
0x1800013da  jnz     short loc_1800013E7
0x1800013dc  xor     ebx, ebx
0x1800013de  mov     [rsp+108h+var_E8], ebx
0x1800013e2  jmp     loc_180001594
0x1800013e7  lea     eax, [rdx-1]
0x1800013ea  cmp     eax, 1
0x1800013ed  ja      loc_180001474
0x1800013f3  mov     rax, cs:_pRawDllMain
0x1800013fa  test    rax, rax
0x1800013fd  jz      short loc_180001435
0x1800013ff  cmp     edx, 1
0x180001402  jnz     short loc_18000140A
0x180001404  mov     cs:dword_180025244, edx
0x18000140a  mov     r8, [rsp+108h+lpvReserved]
0x180001412  call    cs:__guard_dispatch_icall_fptr
0x180001418  mov     ebx, eax
0x18000141a  mov     [rsp+108h+var_E8], eax
0x18000141e  jmp     short loc_180001435
0x180001420  xor     ebx, ebx
0x180001422  mov     [rsp+108h+var_E8], ebx
0x180001426  mov     edi, [rsp+108h+arg_8]
0x18000142d  mov     rsi, [rsp+108h+arg_0]
0x180001435  test    ebx, ebx
0x180001437  jz      loc_180001594
0x18000143d  mov     r8, [rsp+108h+lpvReserved]
0x180001445  mov     edx, edi
0x180001447  mov     rcx, rsi
0x18000144a  call    _CRT_INIT
0x18000144f  mov     ebx, eax
0x180001451  mov     [rsp+108h+var_E8], eax
0x180001455  jmp     short loc_18000146C
0x180001457  xor     ebx, ebx
0x180001459  mov     [rsp+108h+var_E8], ebx
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  test    ebx, ebx
0x18000146e  jz      loc_180001594
0x180001474  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000147c  mov     edx, edi; fdwReason
0x18000147e  mov     rcx, rsi; hinstDLL
0x180001481  call    DllMain
0x180001486  mov     ebx, eax
0x180001488  mov     [rsp+108h+var_E8], eax
0x18000148c  jmp     short loc_1800014A3
0x18000148e  xor     ebx, ebx
0x180001490  mov     [rsp+108h+var_E8], ebx
0x180001494  mov     edi, [rsp+108h+arg_8]
0x18000149b  mov     rsi, [rsp+108h+arg_0]
0x1800014a3  cmp     edi, 1
0x1800014a6  jnz     short loc_18000151F
0x1800014a8  test    ebx, ebx
0x1800014aa  jnz     short loc_18000151F
0x1800014ac  xor     r8d, r8d; lpvReserved
0x1800014af  xor     edx, edx; fdwReason
0x1800014b1  mov     rcx, rsi; hinstDLL
0x1800014b4  call    DllMain
0x1800014b9  jmp     short loc_1800014CE
0x1800014bb  mov     edi, [rsp+108h+arg_8]
0x1800014c2  mov     rsi, [rsp+108h+arg_0]
0x1800014ca  mov     ebx, [rsp+108h+var_E8]
0x1800014ce  xor     r8d, r8d
0x1800014d1  xor     edx, edx
0x1800014d3  mov     rcx, rsi
0x1800014d6  call    _CRT_INIT
0x1800014db  jmp     short loc_1800014F0
0x1800014dd  mov     edi, [rsp+108h+arg_8]
0x1800014e4  mov     rsi, [rsp+108h+arg_0]
0x1800014ec  mov     ebx, [rsp+108h+var_E8]
0x1800014f0  mov     rax, cs:_pRawDllMain
0x1800014f7  test    rax, rax
0x1800014fa  jz      short loc_18000151F
0x1800014fc  xor     r8d, r8d
0x1800014ff  xor     edx, edx
0x180001501  mov     rcx, rsi
0x180001504  call    cs:__guard_dispatch_icall_fptr
0x18000150a  jmp     short loc_18000151F
0x18000150c  mov     edi, [rsp+108h+arg_8]
0x180001513  mov     rsi, [rsp+108h+arg_0]
0x18000151b  mov     ebx, [rsp+108h+var_E8]
0x18000151f  test    edi, edi
0x180001521  jz      short loc_180001528
0x180001523  cmp     edi, 3
0x180001526  jnz     short loc_180001594
0x180001528  mov     r8, [rsp+108h+lpvReserved]
0x180001530  mov     edx, edi
0x180001532  mov     rcx, rsi
0x180001535  call    _CRT_INIT
0x18000153a  mov     ebx, eax
0x18000153c  mov     [rsp+108h+var_E8], eax
0x180001540  jmp     short loc_180001557
0x180001542  xor     ebx, ebx
0x180001544  mov     [rsp+108h+var_E8], ebx
0x180001548  mov     edi, [rsp+108h+arg_8]
0x18000154f  mov     rsi, [rsp+108h+arg_0]
0x180001557  mov     rax, cs:_pRawDllMain
0x18000155e  test    rax, rax
0x180001561  jz      short loc_180001594
0x180001563  cmp     cs:dword_180025244, 0
0x18000156a  jz      short loc_180001594
0x18000156c  mov     r8, [rsp+108h+lpvReserved]
0x180001574  mov     edx, edi
0x180001576  mov     rcx, rsi
0x180001579  call    cs:__guard_dispatch_icall_fptr
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_180001594
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  cmp     edi, 1
0x180001597  ja      short loc_1800015A3
0x180001599  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015a3  mov     eax, ebx
0x1800015a5  add     rsp, 0F0h
0x1800015ac  pop     rdi
0x1800015ad  pop     rsi
0x1800015ae  pop     rbx
0x1800015af  retn
0x18001ba90  push    rbp
0x18001ba92  sub     rsp, 20h
0x18001ba96  mov     rbp, rdx
0x18001ba99  mov     rax, [rcx]
0x18001ba9c  mov     edx, [rax]
0x18001ba9e  mov     [rbp+0A8h], rcx
0x18001baa5  mov     [rbp+28h], edx
0x18001baa8  mov     eax, [rbp+28h]
0x18001baab  cmp     eax, 0E06D7363h
0x18001bab0  jnz     short loc_18001BAC6
0x18001bab2  mov     rdx, [rbp+0A8h]
0x18001bab9  mov     ecx, [rbp+28h]
0x18001babc  call    _XcptFilter_0
0x18001bac1  mov     [rbp+30h], eax
0x18001bac4  jmp     short loc_18001BACD
0x18001bac6  mov     dword ptr [rbp+30h], 0
0x18001bacd  mov     eax, [rbp+30h]
0x18001bad0  add     rsp, 20h
0x18001bad4  pop     rbp
0x18001bad5  retn
0x18001bad7  push    rbp
0x18001bad9  sub     rsp, 20h
0x18001badd  mov     rbp, rdx
0x18001bae0  mov     rax, [rcx]
0x18001bae3  mov     edx, [rax]
0x18001bae5  mov     [rbp+0B0h], rcx
0x18001baec  mov     [rbp+38h], edx
0x18001baef  mov     eax, [rbp+38h]
0x18001baf2  cmp     eax, 0E06D7363h
0x18001baf7  jnz     short loc_18001BB0D
0x18001baf9  mov     rdx, [rbp+0B0h]
0x18001bb00  mov     ecx, [rbp+38h]
0x18001bb03  call    _XcptFilter_0
0x18001bb08  mov     [rbp+40h], eax
0x18001bb0b  jmp     short loc_18001BB14
0x18001bb0d  mov     dword ptr [rbp+40h], 0
0x18001bb14  mov     eax, [rbp+40h]
0x18001bb17  add     rsp, 20h
0x18001bb1b  pop     rbp
0x18001bb1c  retn
0x18001bb1e  push    rbp
0x18001bb20  sub     rsp, 20h
0x18001bb24  mov     rbp, rdx
0x18001bb27  mov     rax, [rcx]
0x18001bb2a  mov     edx, [rax]
0x18001bb2c  mov     [rbp+0B8h], rcx
0x18001bb33  mov     [rbp+48h], edx
0x18001bb36  mov     eax, [rbp+48h]
0x18001bb39  cmp     eax, 0E06D7363h
0x18001bb3e  jnz     short loc_18001BB54
0x18001bb40  mov     rdx, [rbp+0B8h]
0x18001bb47  mov     ecx, [rbp+48h]
0x18001bb4a  call    _XcptFilter_0
0x18001bb4f  mov     [rbp+50h], eax
0x18001bb52  jmp     short loc_18001BB5B
0x18001bb54  mov     dword ptr [rbp+50h], 0
0x18001bb5b  mov     eax, [rbp+50h]
0x18001bb5e  add     rsp, 20h
0x18001bb62  pop     rbp
0x18001bb63  retn
0x18001bb65  push    rbp
0x18001bb67  sub     rsp, 20h
0x18001bb6b  mov     rbp, rdx
0x18001bb6e  mov     rax, [rcx]
0x18001bb71  mov     edx, [rax]
0x18001bb73  mov     [rbp+0C0h], rcx
0x18001bb7a  mov     [rbp+58h], edx
0x18001bb7d  mov     eax, [rbp+58h]
0x18001bb80  cmp     eax, 0E06D7363h
0x18001bb85  jnz     short loc_18001BB9B
0x18001bb87  mov     rdx, [rbp+0C0h]
0x18001bb8e  mov     ecx, [rbp+58h]
0x18001bb91  call    _XcptFilter_0
0x18001bb96  mov     [rbp+60h], eax
0x18001bb99  jmp     short loc_18001BBA2
0x18001bb9b  mov     dword ptr [rbp+60h], 0
0x18001bba2  mov     eax, [rbp+60h]
0x18001bba5  add     rsp, 20h
0x18001bba9  pop     rbp
0x18001bbaa  retn
0x18001bbac  push    rbp
0x18001bbae  sub     rsp, 20h
0x18001bbb2  mov     rbp, rdx
0x18001bbb5  mov     rax, [rcx]
0x18001bbb8  mov     edx, [rax]
0x18001bbba  mov     [rbp+0C8h], rcx
0x18001bbc1  mov     [rbp+68h], edx
0x18001bbc4  mov     eax, [rbp+68h]
0x18001bbc7  cmp     eax, 0E06D7363h
0x18001bbcc  jnz     short loc_18001BBE2
0x18001bbce  mov     rdx, [rbp+0C8h]
0x18001bbd5  mov     ecx, [rbp+68h]
0x18001bbd8  call    _XcptFilter_0
0x18001bbdd  mov     [rbp+70h], eax
0x18001bbe0  jmp     short loc_18001BBE9
0x18001bbe2  mov     dword ptr [rbp+70h], 0
0x18001bbe9  mov     eax, [rbp+70h]
0x18001bbec  add     rsp, 20h
0x18001bbf0  pop     rbp
0x18001bbf1  retn
0x18001bbf3  push    rbp
0x18001bbf5  sub     rsp, 20h
0x18001bbf9  mov     rbp, rdx
0x18001bbfc  mov     rax, [rcx]
0x18001bbff  mov     edx, [rax]
0x18001bc01  mov     [rbp+0D0h], rcx
0x18001bc08  mov     [rbp+78h], edx
0x18001bc0b  mov     eax, [rbp+78h]
0x18001bc0e  cmp     eax, 0E06D7363h
0x18001bc13  jnz     short loc_18001BC2C
0x18001bc15  mov     rdx, [rbp+0D0h]
0x18001bc1c  mov     ecx, [rbp+78h]
0x18001bc1f  call    _XcptFilter_0
0x18001bc24  mov     [rbp+80h], eax
0x18001bc2a  jmp     short loc_18001BC36
0x18001bc2c  mov     dword ptr [rbp+80h], 0
0x18001bc36  mov     eax, [rbp+80h]
0x18001bc3c  add     rsp, 20h
0x18001bc40  pop     rbp
0x18001bc41  retn
0x18001bc43  push    rbp
0x18001bc45  sub     rsp, 20h
0x18001bc49  mov     rbp, rdx
0x18001bc4c  mov     rax, [rcx]
0x18001bc4f  mov     edx, [rax]
0x18001bc51  mov     [rbp+0D8h], rcx
0x18001bc58  mov     [rbp+88h], edx
0x18001bc5e  mov     eax, [rbp+88h]
0x18001bc64  cmp     eax, 0E06D7363h
0x18001bc69  jnz     short loc_18001BC85
0x18001bc6b  mov     rdx, [rbp+0D8h]
0x18001bc72  mov     ecx, [rbp+88h]
0x18001bc78  call    _XcptFilter_0
0x18001bc7d  mov     [rbp+90h], eax
0x18001bc83  jmp     short loc_18001BC8F
0x18001bc85  mov     dword ptr [rbp+90h], 0
0x18001bc8f  mov     eax, [rbp+90h]
0x18001bc95  add     rsp, 20h
0x18001bc99  pop     rbp
0x18001bc9a  retn
0x18001bc9c  push    rbp
0x18001bc9e  sub     rsp, 20h
0x18001bca2  mov     rbp, rdx
0x18001bca5  mov     rax, [rcx]
0x18001bca8  mov     edx, [rax]
0x18001bcaa  mov     [rbp+0E0h], rcx
0x18001bcb1  mov     [rbp+98h], edx
0x18001bcb7  mov     eax, [rbp+98h]
0x18001bcbd  cmp     eax, 0E06D7363h
0x18001bcc2  jnz     short loc_18001BCDE
0x18001bcc4  mov     rdx, [rbp+0E0h]
0x18001bccb  mov     ecx, [rbp+98h]
0x18001bcd1  call    _XcptFilter_0
0x18001bcd6  mov     [rbp+0A0h], eax
0x18001bcdc  jmp     short loc_18001BCE8
0x18001bcde  mov     dword ptr [rbp+0A0h], 0
0x18001bce8  mov     eax, [rbp+0A0h]
0x18001bcee  add     rsp, 20h
0x18001bcf2  pop     rbp
0x18001bcf3  retn
0x18001bcf5  push    rbp
0x18001bcf7  sub     rsp, 20h
0x18001bcfb  mov     rbp, rdx
0x18001bcfe  cmp     dword ptr [rbp+118h], 1
0x18001bd05  ja      short loc_18001BD11
0x18001bd07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
