# BfFsctlGetMappings

- ea: `0x14000fa74`
- end: `0x14000fd98`
- name: `BfFsctlGetMappings`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140025770`

## callees

- `0x140003140`
- `0x140003304`
- `0x140004cc0`
- `0x14000fa74`
- `0x14000ff58`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14000fc3d`
- `ntoskrnl!ExGetPreviousMode` at `0x14000fc3d`
- `ntoskrnl!ProbeForWrite` at `0x14000fc7f`
- `ntoskrnl!ProbeForWrite` at `0x14000fc7f`
- `ntoskrnl!ProbeForRead` at `0x14000fc65`
- `ntoskrnl!ProbeForRead` at `0x14000fc65`
- `ntoskrnl!PsGetCurrentSilo` at `0x14000fac1`
- `ntoskrnl!PsGetCurrentSilo` at `0x14000fac1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd76`
- `ntoskrnl!ExAllocatePool2` at `0x14000fbf2`
- `ntoskrnl!ExAllocatePool2` at `0x14000fca8`
- `ntoskrnl!ExAllocatePool2` at `0x14000fbf2`
- `ntoskrnl!ExAllocatePool2` at `0x14000fca8`
- `ntoskrnl!PsIsHostSilo` at `0x14000fad0`
- `ntoskrnl!PsIsHostSilo` at `0x14000fad0`

## pseudocode

```c
__int64 __fastcall BfFsctlGetMappings(__int64 a1)
{
  char *Pool2; // rsi
  unsigned int v3; // r13d
  _DWORD *v4; // rdi
  __int64 v5; // rax
  SIZE_T v6; // r12
  SIZE_T v7; // r15
  __int64 CurrentSilo; // rax
  int v9; // ebx
  _UNKNOWN **v10; // rdx
  int v11; // r9d
  _UNKNOWN **v12; // rdx
  int v13; // r9d
  KPROCESSOR_MODE PreviousMode; // al
  const void *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  char v19; // [rsp+30h] [rbp-68h]
  char v20; // [rsp+30h] [rbp-68h]
  char v21; // [rsp+38h] [rbp-60h]
  char v22; // [rsp+40h] [rbp-58h]
  unsigned int v23; // [rsp+A8h] [rbp+10h] BYREF
  volatile void *Address; // [rsp+B0h] [rbp+18h]
  volatile void *v25; // [rsp+B8h] [rbp+20h]

  Pool2 = 0;
  v3 = 0;
  v23 = 0;
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(unsigned int *)(v5 + 32);
  v7 = *(unsigned int *)(v5 + 24);
  Address = *(volatile void **)(v5 + 48);
  v25 = *(volatile void **)(v5 + 56);
  CurrentSilo = PsGetCurrentSilo();
  if ( (unsigned __int8)PsIsHostSilo(CurrentSilo) )
  {
    v9 = -1073741637;
    v10 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v11 = 10;
    v19 = 56;
    LOBYTE(v10) = 3;
    goto LABEL_4;
  }
  if ( (unsigned int)v6 < 0x28 )
  {
    v9 = -1073741811;
    v12 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v13 = 11;
    v22 = 40;
    v21 = v6;
    v20 = 63;
    goto LABEL_8;
  }
  if ( (unsigned int)v7 >= 0xC )
  {
    Pool2 = (char *)ExAllocatePool2(256, v6, 1936541250);
    if ( Pool2 )
    {
      PreviousMode = ExGetPreviousMode();
      v15 = (const void *)Address;
      if ( PreviousMode == 1 )
      {
        ProbeForRead(Address, v6, 1u);
        ProbeForWrite(v25, v7, 1u);
      }
      memmove(Pool2, v15, v6);
      v16 = ExAllocatePool2(256, v7, 1936541250);
      v4 = (_DWORD *)v16;
      if ( v16 )
      {
        v9 = 0;
        *(_DWORD *)(v16 + 4) = BfProcessGetMappingsRequest(Pool2 + 8, (unsigned int)v7, v16, &v23);
        v3 = v23;
        *v4 = v23;
        memmove((void *)v25, v4, v7);
        goto LABEL_22;
      }
      v9 = -1073741670;
      v10 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_22;
      v11 = 14;
      v19 = 104;
    }
    else
    {
      v9 = -1073741670;
      v10 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_22;
      v11 = 13;
      v19 = 77;
    }
    LOBYTE(v10) = 2;
LABEL_4:
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      3,
      v11,
      (__int64)WPP_dc550879121a3d6a550fd0f80f21d5de_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\fsctrl.c",
      v19);
    goto LABEL_22;
  }
  v9 = -1073741811;
  v12 = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 12;
    v22 = 12;
    v21 = v7;
    v20 = 69;
LABEL_8:
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_sDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      3,
      v13,
      (__int64)WPP_dc550879121a3d6a550fd0f80f21d5de_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\fsctrl.c",
      v20,
      v21,
      v22);
  }
LABEL_22:
  *(_DWORD *)(a1 + 24) = v9;
  if ( v9 >= 0 )
    v17 = v3;
  else
    v17 = 0;
  *(_QWORD *)(a1 + 32) = v17;
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x736D4642u);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x736D4642u);
  return 4;
}

```

## disassembly

```asm
0x14000fa74  mov     rax, rsp
0x14000fa77  mov     [rax+8], rcx
0x14000fa7b  push    rbx
0x14000fa7c  push    rsi
0x14000fa7d  push    rdi
0x14000fa7e  push    r12
0x14000fa80  push    r13
0x14000fa82  push    r14
0x14000fa84  push    r15
0x14000fa86  sub     rsp, 60h
0x14000fa8a  mov     r14, rcx
0x14000fa8d  xor     esi, esi
0x14000fa8f  xor     r13d, r13d
0x14000fa92  mov     [rax+10h], r13d
0x14000fa96  xor     edi, edi
0x14000fa98  mov     [rsp+98h+var_40], rdi
0x14000fa9d  mov     rax, [rcx+10h]
0x14000faa1  mov     r12d, [rax+20h]
0x14000faa5  mov     r15d, [rax+18h]
0x14000faa9  mov     rcx, [rax+30h]
0x14000faad  mov     [rsp+98h+Address], rcx
0x14000fab5  mov     rax, [rax+38h]
0x14000fab9  mov     [rsp+98h+arg_18], rax
0x14000fac1  call    cs:__imp_PsGetCurrentSilo
0x14000fac8  nop     dword ptr [rax+rax+00h]
0x14000facd  mov     rcx, rax
0x14000fad0  call    cs:__imp_PsIsHostSilo
0x14000fad7  nop     dword ptr [rax+rax+00h]
0x14000fadc  test    al, al
0x14000fade  jz      short loc_14000FB39
0x14000fae0  mov     ebx, 0C00000BBh
0x14000fae5  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000faec  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000faf3  jz      loc_14000FD3D
0x14000faf9  lea     r9d, [rsi+0Ah]
0x14000fafd  mov     dword ptr [rsp+98h+var_68], 38h ; '8'
0x14000fb05  lea     r8d, [rsi+3]
0x14000fb09  mov     dl, r8b
0x14000fb0c  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000fb13  mov     [rsp+98h+var_70], rax
0x14000fb18  lea     rax, WPP_dc550879121a3d6a550fd0f80f21d5de_Traceguids
0x14000fb1f  mov     [rsp+98h+var_78], rax
0x14000fb24  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb2b  mov     rcx, [rcx+40h]
0x14000fb2f  call    WPP_RECORDER_SF_sD
0x14000fb34  jmp     loc_14000FD3D
0x14000fb39  cmp     r12d, 28h ; '('
0x14000fb3d  jnb     short loc_14000FBA8
0x14000fb3f  mov     ebx, 0C000000Dh
0x14000fb44  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000fb4b  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000fb52  jz      loc_14000FD3D
0x14000fb58  mov     r9d, 0Bh
0x14000fb5e  mov     dword ptr [rsp+98h+var_58], 28h ; '('
0x14000fb66  mov     dword ptr [rsp+98h+var_60], r12d
0x14000fb6b  mov     dword ptr [rsp+98h+var_68], 3Fh ; '?'
0x14000fb73  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000fb7a  mov     [rsp+98h+var_70], rax
0x14000fb7f  lea     rax, WPP_dc550879121a3d6a550fd0f80f21d5de_Traceguids
0x14000fb86  mov     [rsp+98h+var_78], rax
0x14000fb8b  mov     r8d, 3
0x14000fb91  mov     dl, 2
0x14000fb93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb9a  mov     rcx, [rcx+40h]
0x14000fb9e  call    WPP_RECORDER_SF_sDdd
0x14000fba3  jmp     loc_14000FD3D
0x14000fba8  mov     ecx, 0Ch
0x14000fbad  cmp     r15d, ecx
0x14000fbb0  jnb     short loc_14000FBE1
0x14000fbb2  mov     ebx, 0C000000Dh
0x14000fbb7  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000fbbe  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000fbc5  jz      loc_14000FD3D
0x14000fbcb  mov     r9d, ecx
0x14000fbce  mov     dword ptr [rsp+98h+var_58], ecx
0x14000fbd2  mov     dword ptr [rsp+98h+var_60], r15d
0x14000fbd7  mov     dword ptr [rsp+98h+var_68], 45h ; 'E'
0x14000fbdf  jmp     short loc_14000FB73
0x14000fbe1  mov     rbx, r12
0x14000fbe4  mov     r8d, 736D4642h
0x14000fbea  mov     rdx, r12
0x14000fbed  mov     ecx, 100h
0x14000fbf2  call    cs:__imp_ExAllocatePool2
0x14000fbf9  nop     dword ptr [rax+rax+00h]
0x14000fbfe  mov     rsi, rax
0x14000fc01  mov     [rsp+98h+var_48], rax
0x14000fc06  test    rax, rax
0x14000fc09  jnz     short loc_14000FC3D
0x14000fc0b  mov     ebx, 0C000009Ah
0x14000fc10  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000fc17  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000fc1e  jz      loc_14000FD3D
0x14000fc24  lea     r9d, [rax+0Dh]
0x14000fc28  mov     dword ptr [rsp+98h+var_68], 4Dh ; 'M'
0x14000fc30  mov     r8d, 3
0x14000fc36  mov     dl, 2
0x14000fc38  jmp     loc_14000FB0C
0x14000fc3d  call    cs:__imp_ExGetPreviousMode
0x14000fc44  nop     dword ptr [rax+rax+00h]
0x14000fc49  mov     r12d, 1
0x14000fc4f  mov     rdi, [rsp+98h+Address]
0x14000fc57  cmp     al, r12b
0x14000fc5a  jnz     short loc_14000FC8B
0x14000fc5c  mov     r8d, r12d; Alignment
0x14000fc5f  mov     rdx, rbx; Length
0x14000fc62  mov     rcx, rdi; Address
0x14000fc65  call    cs:__imp_ProbeForRead
0x14000fc6c  nop     dword ptr [rax+rax+00h]
0x14000fc71  mov     rdx, r15; Length
0x14000fc74  mov     r8d, r12d; Alignment
0x14000fc77  mov     rcx, [rsp+98h+arg_18]; Address
0x14000fc7f  call    cs:__imp_ProbeForWrite
0x14000fc86  nop     dword ptr [rax+rax+00h]
0x14000fc8b  mov     r8, rbx; Size
0x14000fc8e  mov     rdx, rdi; Src
0x14000fc91  mov     rcx, rsi; void *
0x14000fc94  call    memmove
0x14000fc99  nop
0x14000fc9a  mov     r8d, 736D4642h
0x14000fca0  mov     rdx, r15
0x14000fca3  mov     ecx, 100h
0x14000fca8  call    cs:__imp_ExAllocatePool2
0x14000fcaf  nop     dword ptr [rax+rax+00h]
0x14000fcb4  mov     rdi, rax
0x14000fcb7  test    rax, rax
0x14000fcba  jnz     short loc_14000FCE2
0x14000fcbc  mov     ebx, 0C000009Ah
0x14000fcc1  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000fcc8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000fccf  jz      short loc_14000FD3D
0x14000fcd1  lea     r9d, [rax+0Eh]
0x14000fcd5  mov     dword ptr [rsp+98h+var_68], 68h ; 'h'
0x14000fcdd  jmp     loc_14000FC30
0x14000fce2  xor     ebx, ebx
0x14000fce4  lea     rcx, [rsi+8]
0x14000fce8  lea     r9, [rsp+98h+arg_8]
0x14000fcf0  mov     r8, rdi
0x14000fcf3  mov     edx, r15d
0x14000fcf6  call    BfProcessGetMappingsRequest
0x14000fcfb  mov     [rdi+4], eax
0x14000fcfe  mov     r13d, [rsp+98h+arg_8]
0x14000fd06  mov     [rdi], r13d
0x14000fd09  mov     r8, r15; Size
0x14000fd0c  mov     rdx, rdi; Src
0x14000fd0f  mov     rcx, [rsp+98h+arg_18]; void *
0x14000fd17  call    memmove
0x14000fd1c  jmp     short loc_14000FD3D
0x14000fd1e  mov     ebx, 0C0000005h
0x14000fd23  mov     r14, [rsp+98h+arg_0]
0x14000fd2b  mov     rsi, [rsp+98h+var_48]
0x14000fd30  mov     r13d, [rsp+98h+arg_8]
0x14000fd38  mov     rdi, [rsp+98h+var_40]
0x14000fd3d  mov     [r14+18h], ebx
0x14000fd41  test    ebx, ebx
0x14000fd43  jns     short loc_14000FD49
0x14000fd45  xor     eax, eax
0x14000fd47  jmp     short loc_14000FD4C
0x14000fd49  mov     eax, r13d
0x14000fd4c  mov     [r14+20h], rax
0x14000fd50  test    rsi, rsi
0x14000fd53  jz      short loc_14000FD69
0x14000fd55  mov     edx, 736D4642h; Tag
0x14000fd5a  mov     rcx, rsi; P
0x14000fd5d  call    cs:__imp_ExFreePoolWithTag
0x14000fd64  nop     dword ptr [rax+rax+00h]
0x14000fd69  test    rdi, rdi
0x14000fd6c  jz      short loc_14000FD82
0x14000fd6e  mov     edx, 736D4642h; Tag
0x14000fd73  mov     rcx, rdi; P
0x14000fd76  call    cs:__imp_ExFreePoolWithTag
0x14000fd7d  nop     dword ptr [rax+rax+00h]
0x14000fd82  mov     eax, 4
0x14000fd87  add     rsp, 60h
0x14000fd8b  pop     r15
0x14000fd8d  pop     r14
0x14000fd8f  pop     r13
0x14000fd91  pop     r12
0x14000fd93  pop     rdi
0x14000fd94  pop     rsi
0x14000fd95  pop     rbx
0x14000fd96  retn
```
