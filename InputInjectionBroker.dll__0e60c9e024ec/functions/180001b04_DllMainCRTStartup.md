# __DllMainCRTStartup

- ea: `0x180001b04`
- end: `0x180001d10`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ac0`

## callees

- `0x180001890`
- `0x180001b04`
- `0x180001efe`
- `0x180009238`
- `0x1800114d0`

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
  if ( (_DWORD)fdwReason || dword_1800223FC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180022400 = 1;
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
            if ( dword_180022400 )
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
0x180001b04  mov     [rsp+lpvReserved], r8
0x180001b09  mov     [rsp+arg_8], edx
0x180001b0d  mov     [rsp+arg_0], rcx
0x180001b12  push    rbx
0x180001b13  push    rsi
0x180001b14  push    rdi
0x180001b15  sub     rsp, 0F0h
0x180001b1c  mov     edi, edx
0x180001b1e  mov     rsi, rcx
0x180001b21  mov     ebx, 1
0x180001b26  cmp     edx, ebx
0x180001b28  ja      short loc_180001B30
0x180001b2a  mov     cs:__native_dllmain_reason, edx
0x180001b30  test    edx, edx
0x180001b32  jnz     short loc_180001B47
0x180001b34  cmp     cs:dword_1800223FC, edx
0x180001b3a  jnz     short loc_180001B47
0x180001b3c  xor     ebx, ebx
0x180001b3e  mov     [rsp+108h+var_E8], ebx
0x180001b42  jmp     loc_180001CF4
0x180001b47  lea     eax, [rdx-1]
0x180001b4a  cmp     eax, 1
0x180001b4d  ja      loc_180001BD4
0x180001b53  mov     rax, cs:_pRawDllMain
0x180001b5a  test    rax, rax
0x180001b5d  jz      short loc_180001B95
0x180001b5f  cmp     edx, 1
0x180001b62  jnz     short loc_180001B6A
0x180001b64  mov     cs:dword_180022400, edx
0x180001b6a  mov     r8, [rsp+108h+lpvReserved]
0x180001b72  call    cs:__guard_dispatch_icall_fptr
0x180001b78  mov     ebx, eax
0x180001b7a  mov     [rsp+108h+var_E8], eax
0x180001b7e  jmp     short loc_180001B95
0x180001b80  xor     ebx, ebx
0x180001b82  mov     [rsp+108h+var_E8], ebx
0x180001b86  mov     edi, [rsp+108h+arg_8]
0x180001b8d  mov     rsi, [rsp+108h+arg_0]
0x180001b95  test    ebx, ebx
0x180001b97  jz      loc_180001CF4
0x180001b9d  mov     r8, [rsp+108h+lpvReserved]
0x180001ba5  mov     edx, edi
0x180001ba7  mov     rcx, rsi
0x180001baa  call    _CRT_INIT
0x180001baf  mov     ebx, eax
0x180001bb1  mov     [rsp+108h+var_E8], eax
0x180001bb5  jmp     short loc_180001BCC
0x180001bb7  xor     ebx, ebx
0x180001bb9  mov     [rsp+108h+var_E8], ebx
0x180001bbd  mov     edi, [rsp+108h+arg_8]
0x180001bc4  mov     rsi, [rsp+108h+arg_0]
0x180001bcc  test    ebx, ebx
0x180001bce  jz      loc_180001CF4
0x180001bd4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001bdc  mov     edx, edi; fdwReason
0x180001bde  mov     rcx, rsi; hinstDLL
0x180001be1  call    DllMain
0x180001be6  mov     ebx, eax
0x180001be8  mov     [rsp+108h+var_E8], eax
0x180001bec  jmp     short loc_180001C03
0x180001bee  xor     ebx, ebx
0x180001bf0  mov     [rsp+108h+var_E8], ebx
0x180001bf4  mov     edi, [rsp+108h+arg_8]
0x180001bfb  mov     rsi, [rsp+108h+arg_0]
0x180001c03  cmp     edi, 1
0x180001c06  jnz     short loc_180001C7F
0x180001c08  test    ebx, ebx
0x180001c0a  jnz     short loc_180001C7F
0x180001c0c  xor     r8d, r8d; lpvReserved
0x180001c0f  xor     edx, edx; fdwReason
0x180001c11  mov     rcx, rsi; hinstDLL
0x180001c14  call    DllMain
0x180001c19  jmp     short loc_180001C2E
0x180001c1b  mov     edi, [rsp+108h+arg_8]
0x180001c22  mov     rsi, [rsp+108h+arg_0]
0x180001c2a  mov     ebx, [rsp+108h+var_E8]
0x180001c2e  xor     r8d, r8d
0x180001c31  xor     edx, edx
0x180001c33  mov     rcx, rsi
0x180001c36  call    _CRT_INIT
0x180001c3b  jmp     short loc_180001C50
0x180001c3d  mov     edi, [rsp+108h+arg_8]
0x180001c44  mov     rsi, [rsp+108h+arg_0]
0x180001c4c  mov     ebx, [rsp+108h+var_E8]
0x180001c50  mov     rax, cs:_pRawDllMain
0x180001c57  test    rax, rax
0x180001c5a  jz      short loc_180001C7F
0x180001c5c  xor     r8d, r8d
0x180001c5f  xor     edx, edx
0x180001c61  mov     rcx, rsi
0x180001c64  call    cs:__guard_dispatch_icall_fptr
0x180001c6a  jmp     short loc_180001C7F
0x180001c6c  mov     edi, [rsp+108h+arg_8]
0x180001c73  mov     rsi, [rsp+108h+arg_0]
0x180001c7b  mov     ebx, [rsp+108h+var_E8]
0x180001c7f  test    edi, edi
0x180001c81  jz      short loc_180001C88
0x180001c83  cmp     edi, 3
0x180001c86  jnz     short loc_180001CF4
0x180001c88  mov     r8, [rsp+108h+lpvReserved]
0x180001c90  mov     edx, edi
0x180001c92  mov     rcx, rsi
0x180001c95  call    _CRT_INIT
0x180001c9a  mov     ebx, eax
0x180001c9c  mov     [rsp+108h+var_E8], eax
0x180001ca0  jmp     short loc_180001CB7
0x180001ca2  xor     ebx, ebx
0x180001ca4  mov     [rsp+108h+var_E8], ebx
0x180001ca8  mov     edi, [rsp+108h+arg_8]
0x180001caf  mov     rsi, [rsp+108h+arg_0]
0x180001cb7  mov     rax, cs:_pRawDllMain
0x180001cbe  test    rax, rax
0x180001cc1  jz      short loc_180001CF4
0x180001cc3  cmp     cs:dword_180022400, 0
0x180001cca  jz      short loc_180001CF4
0x180001ccc  mov     r8, [rsp+108h+lpvReserved]
0x180001cd4  mov     edx, edi
0x180001cd6  mov     rcx, rsi
0x180001cd9  call    cs:__guard_dispatch_icall_fptr
0x180001cdf  mov     ebx, eax
0x180001ce1  mov     [rsp+108h+var_E8], eax
0x180001ce5  jmp     short loc_180001CF4
0x180001ce7  xor     ebx, ebx
0x180001ce9  mov     [rsp+108h+var_E8], ebx
0x180001ced  mov     edi, [rsp+108h+arg_8]
0x180001cf4  cmp     edi, 1
0x180001cf7  ja      short loc_180001D03
0x180001cf9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001d03  mov     eax, ebx
0x180001d05  add     rsp, 0F0h
0x180001d0c  pop     rdi
0x180001d0d  pop     rsi
0x180001d0e  pop     rbx
0x180001d0f  retn
0x180011573  push    rbp
0x180011575  sub     rsp, 20h
0x180011579  mov     rbp, rdx
0x18001157c  mov     rax, [rcx]
0x18001157f  mov     edx, [rax]
0x180011581  mov     [rbp+0A8h], rcx
0x180011588  mov     [rbp+28h], edx
0x18001158b  mov     eax, [rbp+28h]
0x18001158e  cmp     eax, 0E06D7363h
0x180011593  jnz     short loc_1800115A9
0x180011595  mov     rdx, [rbp+0A8h]
0x18001159c  mov     ecx, [rbp+28h]
0x18001159f  call    _XcptFilter_0
0x1800115a4  mov     [rbp+30h], eax
0x1800115a7  jmp     short loc_1800115B0
0x1800115a9  mov     dword ptr [rbp+30h], 0
0x1800115b0  mov     eax, [rbp+30h]
0x1800115b3  add     rsp, 20h
0x1800115b7  pop     rbp
0x1800115b8  retn
0x1800115ba  push    rbp
0x1800115bc  sub     rsp, 20h
0x1800115c0  mov     rbp, rdx
0x1800115c3  mov     rax, [rcx]
0x1800115c6  mov     edx, [rax]
0x1800115c8  mov     [rbp+0B0h], rcx
0x1800115cf  mov     [rbp+38h], edx
0x1800115d2  mov     eax, [rbp+38h]
0x1800115d5  cmp     eax, 0E06D7363h
0x1800115da  jnz     short loc_1800115F0
0x1800115dc  mov     rdx, [rbp+0B0h]
0x1800115e3  mov     ecx, [rbp+38h]
0x1800115e6  call    _XcptFilter_0
0x1800115eb  mov     [rbp+40h], eax
0x1800115ee  jmp     short loc_1800115F7
0x1800115f0  mov     dword ptr [rbp+40h], 0
0x1800115f7  mov     eax, [rbp+40h]
0x1800115fa  add     rsp, 20h
0x1800115fe  pop     rbp
0x1800115ff  retn
0x180011601  push    rbp
0x180011603  sub     rsp, 20h
0x180011607  mov     rbp, rdx
0x18001160a  mov     rax, [rcx]
0x18001160d  mov     edx, [rax]
0x18001160f  mov     [rbp+0B8h], rcx
0x180011616  mov     [rbp+48h], edx
0x180011619  mov     eax, [rbp+48h]
0x18001161c  cmp     eax, 0E06D7363h
0x180011621  jnz     short loc_180011637
0x180011623  mov     rdx, [rbp+0B8h]
0x18001162a  mov     ecx, [rbp+48h]
0x18001162d  call    _XcptFilter_0
0x180011632  mov     [rbp+50h], eax
0x180011635  jmp     short loc_18001163E
0x180011637  mov     dword ptr [rbp+50h], 0
0x18001163e  mov     eax, [rbp+50h]
0x180011641  add     rsp, 20h
0x180011645  pop     rbp
0x180011646  retn
0x180011648  push    rbp
0x18001164a  sub     rsp, 20h
0x18001164e  mov     rbp, rdx
0x180011651  mov     rax, [rcx]
0x180011654  mov     edx, [rax]
0x180011656  mov     [rbp+0C0h], rcx
0x18001165d  mov     [rbp+58h], edx
0x180011660  mov     eax, [rbp+58h]
0x180011663  cmp     eax, 0E06D7363h
0x180011668  jnz     short loc_18001167E
0x18001166a  mov     rdx, [rbp+0C0h]
0x180011671  mov     ecx, [rbp+58h]
0x180011674  call    _XcptFilter_0
0x180011679  mov     [rbp+60h], eax
0x18001167c  jmp     short loc_180011685
0x18001167e  mov     dword ptr [rbp+60h], 0
0x180011685  mov     eax, [rbp+60h]
0x180011688  add     rsp, 20h
0x18001168c  pop     rbp
0x18001168d  retn
0x18001168f  push    rbp
0x180011691  sub     rsp, 20h
0x180011695  mov     rbp, rdx
0x180011698  mov     rax, [rcx]
0x18001169b  mov     edx, [rax]
0x18001169d  mov     [rbp+0C8h], rcx
0x1800116a4  mov     [rbp+68h], edx
0x1800116a7  mov     eax, [rbp+68h]
0x1800116aa  cmp     eax, 0E06D7363h
0x1800116af  jnz     short loc_1800116C5
0x1800116b1  mov     rdx, [rbp+0C8h]
0x1800116b8  mov     ecx, [rbp+68h]
0x1800116bb  call    _XcptFilter_0
0x1800116c0  mov     [rbp+70h], eax
0x1800116c3  jmp     short loc_1800116CC
0x1800116c5  mov     dword ptr [rbp+70h], 0
0x1800116cc  mov     eax, [rbp+70h]
0x1800116cf  add     rsp, 20h
0x1800116d3  pop     rbp
0x1800116d4  retn
0x1800116d6  push    rbp
0x1800116d8  sub     rsp, 20h
0x1800116dc  mov     rbp, rdx
0x1800116df  mov     rax, [rcx]
0x1800116e2  mov     edx, [rax]
0x1800116e4  mov     [rbp+0D0h], rcx
0x1800116eb  mov     [rbp+78h], edx
0x1800116ee  mov     eax, [rbp+78h]
0x1800116f1  cmp     eax, 0E06D7363h
0x1800116f6  jnz     short loc_18001170F
0x1800116f8  mov     rdx, [rbp+0D0h]
0x1800116ff  mov     ecx, [rbp+78h]
0x180011702  call    _XcptFilter_0
0x180011707  mov     [rbp+80h], eax
0x18001170d  jmp     short loc_180011719
0x18001170f  mov     dword ptr [rbp+80h], 0
0x180011719  mov     eax, [rbp+80h]
0x18001171f  add     rsp, 20h
0x180011723  pop     rbp
0x180011724  retn
0x180011726  push    rbp
0x180011728  sub     rsp, 20h
0x18001172c  mov     rbp, rdx
0x18001172f  mov     rax, [rcx]
0x180011732  mov     edx, [rax]
0x180011734  mov     [rbp+0D8h], rcx
0x18001173b  mov     [rbp+88h], edx
0x180011741  mov     eax, [rbp+88h]
0x180011747  cmp     eax, 0E06D7363h
0x18001174c  jnz     short loc_180011768
0x18001174e  mov     rdx, [rbp+0D8h]
0x180011755  mov     ecx, [rbp+88h]
0x18001175b  call    _XcptFilter_0
0x180011760  mov     [rbp+90h], eax
0x180011766  jmp     short loc_180011772
0x180011768  mov     dword ptr [rbp+90h], 0
0x180011772  mov     eax, [rbp+90h]
0x180011778  add     rsp, 20h
0x18001177c  pop     rbp
0x18001177d  retn
0x18001177f  push    rbp
0x180011781  sub     rsp, 20h
0x180011785  mov     rbp, rdx
0x180011788  mov     rax, [rcx]
0x18001178b  mov     edx, [rax]
0x18001178d  mov     [rbp+0E0h], rcx
0x180011794  mov     [rbp+98h], edx
0x18001179a  mov     eax, [rbp+98h]
0x1800117a0  cmp     eax, 0E06D7363h
0x1800117a5  jnz     short loc_1800117C1
0x1800117a7  mov     rdx, [rbp+0E0h]
0x1800117ae  mov     ecx, [rbp+98h]
0x1800117b4  call    _XcptFilter_0
0x1800117b9  mov     [rbp+0A0h], eax
0x1800117bf  jmp     short loc_1800117CB
0x1800117c1  mov     dword ptr [rbp+0A0h], 0
0x1800117cb  mov     eax, [rbp+0A0h]
0x1800117d1  add     rsp, 20h
0x1800117d5  pop     rbp
0x1800117d6  retn
0x1800117d8  push    rbp
0x1800117da  sub     rsp, 20h
0x1800117de  mov     rbp, rdx
0x1800117e1  cmp     dword ptr [rbp+118h], 1
0x1800117e8  ja      short loc_1800117F4
0x1800117ea  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
