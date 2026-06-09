# VidVpIoctlStateGet

- ea: `0x1400fa14c`
- end: `0x1400fa3a6`
- name: `VidVpIoctlStateGet`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400321a4`

## callees

- `0x140011518`
- `0x140012bc0`
- `0x140021c60`
- `0x1400347a4`
- `0x1400347d4`
- `0x140079dfc`
- `0x1400fa14c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400fa22f`
- `ntoskrnl!ProbeForWrite` at `0x1400fa22f`
- `ntoskrnl!ProbeForRead` at `0x1400fa211`
- `ntoskrnl!ProbeForRead` at `0x1400fa211`
- `winhvr!WinHvGetVpRegisters` at `0x1400fa2ab`
- `winhvr!WinHvGetVpRegisters` at `0x1400fa2ab`

## pseudocode

```c
__int64 __fastcall VidVpIoctlStateGet(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        char *a4,
        unsigned __int8 a5,
        char *a6)
{
  char v7; // bl
  unsigned __int8 v9; // r15
  int VpRegisters; // edi
  unsigned int v11; // eax
  unsigned __int8 v12; // r12
  __int64 v13; // r8
  char v15; // [rsp+40h] [rbp-308h]
  char *Address; // [rsp+48h] [rbp-300h]
  char *Src; // [rsp+50h] [rbp-2F8h]
  size_t v19; // [rsp+58h] [rbp-2F0h]
  __int64 v20; // [rsp+68h] [rbp-2E0h] BYREF
  size_t v21; // [rsp+70h] [rbp-2D8h]
  _BYTE v22[128]; // [rsp+80h] [rbp-2C8h] BYREF
  _BYTE v23[512]; // [rsp+100h] [rbp-248h] BYREF

  Src = a4;
  v7 = a3;
  Address = a6;
  v20 = 0;
  v15 = 0;
  v9 = a5;
  if ( (unsigned __int8)(a5 - 1) > 0x7Fu || a3 >= 0x800 || (a3 & 0x700) != 0 )
  {
    VpRegisters = -1073741811;
  }
  else
  {
    VidObjectLockAcquireShared(a1);
    v15 = 1;
    VpRegisters = -1073741811;
    v11 = *(_DWORD *)(a1 + 3200);
    if ( v11 <= 0x800 && a2 < v11 )
      VpRegisters = 0;
    if ( VpRegisters >= 0 )
    {
      ProbeForRead(a4, 4LL * a5, 1u);
      ProbeForWrite(a6, 16LL * a5, 1u);
      do
      {
        v12 = 32;
        if ( v9 < 0x20u )
          v12 = v9;
        v21 = 4LL * v12;
        RtlCopyFromUser(v22, Src, v21);
        LOBYTE(v13) = v7;
        VpRegisters = WinHvGetVpRegisters(*(_QWORD *)(a1 + 648), a2, v13, v12, v22, &v20, v23);
        if ( VpRegisters < 0 )
          break;
        v19 = 16LL * v12;
        RtlCopyToUser(Address, v23, v19);
        Src += v21;
        Address += v19;
        v9 -= v12;
      }
      while ( v9 );
    }
  }
  if ( v15 )
    VidObjectLockRelease(a1);
  return (unsigned int)VpRegisters;
}

```

## disassembly

```asm
0x1400fa14c  push    rbx
0x1400fa14e  push    rsi
0x1400fa14f  push    rdi
0x1400fa150  push    r12
0x1400fa152  push    r13
0x1400fa154  push    r14
0x1400fa156  push    r15
0x1400fa158  sub     rsp, 310h
0x1400fa15f  mov     rax, cs:__security_cookie
0x1400fa166  xor     rax, rsp
0x1400fa169  mov     [rsp+348h+var_48], rax
0x1400fa171  mov     r12, r9
0x1400fa174  mov     [rsp+348h+Src], r9
0x1400fa179  mov     ebx, r8d
0x1400fa17c  mov     [rsp+348h+var_304], edx
0x1400fa180  mov     r14, rcx
0x1400fa183  mov     [rsp+348h+var_2E8], rcx
0x1400fa188  mov     rax, [rsp+348h+arg_28]
0x1400fa190  mov     [rsp+348h+Address], rax
0x1400fa195  xor     esi, esi
0x1400fa197  mov     r13b, sil
0x1400fa19a  mov     [rsp+348h+var_2E0], rsi
0x1400fa19f  mov     [rsp+348h+var_308], sil
0x1400fa1a4  movzx   r15d, [rsp+348h+arg_20]
0x1400fa1ad  lea     eax, [r15-1]
0x1400fa1b1  cmp     al, 7Fh
0x1400fa1b3  ja      loc_1400FA32F
0x1400fa1b9  cmp     ebx, 800h
0x1400fa1bf  jnb     loc_1400FA32F
0x1400fa1c5  test    ebx, 700h
0x1400fa1cb  jnz     loc_1400FA32F
0x1400fa1d1  call    VidObjectLockAcquireShared
0x1400fa1d6  mov     [rsp+348h+var_308], 1
0x1400fa1db  mov     edi, 0C000000Dh
0x1400fa1e0  mov     eax, [r14+0C80h]
0x1400fa1e7  cmp     eax, 800h
0x1400fa1ec  ja      short loc_1400FA1F5
0x1400fa1ee  cmp     [rsp+348h+var_304], eax
0x1400fa1f2  cmovb   edi, esi
0x1400fa1f5  test    edi, edi
0x1400fa1f7  js      loc_1400FA334
0x1400fa1fd  mov     rdi, r15
0x1400fa200  lea     rdx, ds:0[r15*4]; Length
0x1400fa208  mov     r8d, 1; Alignment
0x1400fa20e  mov     rcx, r12; Address
0x1400fa211  call    cs:__imp_ProbeForRead
0x1400fa218  nop     dword ptr [rax+rax+00h]
0x1400fa21d  shl     rdi, 4
0x1400fa221  mov     r8d, 1; Alignment
0x1400fa227  mov     rdx, rdi; Length
0x1400fa22a  mov     rcx, [rsp+348h+Address]; Address
0x1400fa22f  call    cs:__imp_ProbeForWrite
0x1400fa236  nop     dword ptr [rax+rax+00h]
0x1400fa23b  nop
0x1400fa23c  mov     r12d, 20h ; ' '
0x1400fa242  movzx   eax, r15b
0x1400fa246  cmp     r15b, r12b
0x1400fa249  cmovb   r12d, eax
0x1400fa24d  movzx   eax, r12b
0x1400fa251  mov     [rsp+348h+var_2F0], rax
0x1400fa256  shl     rax, 2
0x1400fa25a  mov     [rsp+348h+var_2D8], rax
0x1400fa25f  mov     r8, rax; Size
0x1400fa262  mov     rdx, [rsp+348h+Src]; Src
0x1400fa267  lea     rcx, [rsp+348h+var_2C8]; void *
0x1400fa26f  call    RtlCopyFromUser
0x1400fa274  nop
0x1400fa275  movzx   r9d, r12b
0x1400fa279  lea     rax, [rsp+348h+var_248]
0x1400fa281  mov     [rsp+348h+var_318], rax
0x1400fa286  lea     rax, [rsp+348h+var_2E0]
0x1400fa28b  mov     [rsp+348h+var_320], rax
0x1400fa290  lea     rax, [rsp+348h+var_2C8]
0x1400fa298  mov     [rsp+348h+var_328], rax
0x1400fa29d  mov     r8b, bl
0x1400fa2a0  mov     edx, [rsp+348h+var_304]
0x1400fa2a4  mov     rcx, [r14+288h]
0x1400fa2ab  call    cs:__imp_WinHvGetVpRegisters
0x1400fa2b2  nop     dword ptr [rax+rax+00h]
0x1400fa2b7  mov     edi, eax
0x1400fa2b9  test    eax, eax
0x1400fa2bb  js      short loc_1400FA334
0x1400fa2bd  mov     rax, [rsp+348h+var_2F0]
0x1400fa2c2  shl     rax, 4
0x1400fa2c6  mov     [rsp+348h+var_2F0], rax
0x1400fa2cb  mov     r8, rax; Size
0x1400fa2ce  lea     rdx, [rsp+348h+var_248]; Src
0x1400fa2d6  mov     rcx, [rsp+348h+Address]; void *
0x1400fa2db  call    RtlCopyToUser
0x1400fa2e0  nop
0x1400fa2e1  mov     rax, [rsp+348h+Src]
0x1400fa2e6  add     rax, [rsp+348h+var_2D8]
0x1400fa2eb  mov     [rsp+348h+Src], rax
0x1400fa2f0  mov     rax, [rsp+348h+var_2F0]
0x1400fa2f5  add     [rsp+348h+Address], rax
0x1400fa2fa  sub     r15b, r12b
0x1400fa2fd  jnz     loc_1400FA23C
0x1400fa303  jmp     short loc_1400FA334
0x1400fa305  mov     edi, eax
0x1400fa307  mov     r13b, 1
0x1400fa30a  xor     esi, esi
0x1400fa30c  mov     r14, [rsp+348h+var_2E8]
0x1400fa311  jmp     short loc_1400FA334
0x1400fa313  mov     edi, eax
0x1400fa315  mov     r13b, 1
0x1400fa318  xor     esi, esi
0x1400fa31a  mov     r14, [rsp+348h+var_2E8]
0x1400fa31f  jmp     short loc_1400FA334
0x1400fa321  mov     edi, eax
0x1400fa323  mov     r13b, 1
0x1400fa326  xor     esi, esi
0x1400fa328  mov     r14, [rsp+348h+var_2E8]
0x1400fa32d  jmp     short loc_1400FA334
0x1400fa32f  mov     edi, 0C000000Dh
0x1400fa334  cmp     [rsp+348h+var_308], sil
0x1400fa339  jz      short loc_1400FA343
0x1400fa33b  mov     rcx, r14
0x1400fa33e  call    VidObjectLockRelease
0x1400fa343  test    r13b, r13b
0x1400fa346  jz      short loc_1400FA380
0x1400fa348  lea     rax, WPP_GLOBAL_Control
0x1400fa34f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fa356  cmp     rcx, rax
0x1400fa359  jz      short loc_1400FA380
0x1400fa35b  mov     eax, [rcx+2Ch]
0x1400fa35e  test    al, 2
0x1400fa360  jz      short loc_1400FA380
0x1400fa362  cmp     byte ptr [rcx+29h], 2
0x1400fa366  jb      short loc_1400FA380
0x1400fa368  mov     edx, 0Ch
0x1400fa36d  mov     r9d, edi
0x1400fa370  lea     r8, WPP_f3c8146851b33f019037d8521c1ed030_Traceguids
0x1400fa377  mov     rcx, [rcx+18h]
0x1400fa37b  call    WPP_SF_d
0x1400fa380  mov     eax, edi
0x1400fa382  mov     rcx, [rsp+348h+var_48]
0x1400fa38a  xor     rcx, rsp; StackCookie
0x1400fa38d  call    __security_check_cookie
0x1400fa392  add     rsp, 310h
0x1400fa399  pop     r15
0x1400fa39b  pop     r14
0x1400fa39d  pop     r13
0x1400fa39f  pop     r12
0x1400fa3a1  pop     rdi
0x1400fa3a2  pop     rsi
0x1400fa3a3  pop     rbx
0x1400fa3a4  retn
```
