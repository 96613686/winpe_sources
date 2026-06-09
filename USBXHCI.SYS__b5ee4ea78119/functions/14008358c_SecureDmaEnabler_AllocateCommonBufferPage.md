# SecureDmaEnabler_AllocateCommonBufferPage

- ea: `0x14008358c`
- end: `0x140083898`
- name: `SecureDmaEnabler_AllocateCommonBufferPage`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002c5b0`
- `0x14003b238`
- `0x140040164`

## callees

- `0x14001ad0c`
- `0x1400599b0`
- `0x14008358c`
- `0x140083aa8`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140083790`
- `ntoskrnl!IoAllocateMdl` at `0x140083790`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008376e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140083845`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008376e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140083845`
- `ntoskrnl!IoFreeMdl` at `0x1400837f5`
- `ntoskrnl!IoFreeMdl` at `0x1400837f5`

## pseudocode

```c
__int64 __fastcall SecureDmaEnabler_AllocateCommonBufferPage(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  _QWORD *v7; // r15
  ULONG v8; // esi
  int v9; // edx
  int v10; // ebx
  __int64 v11; // rax
  _QWORD *v12; // rdi
  unsigned __int64 v13; // r9
  _QWORD *v14; // rbx
  __int16 v15; // r10
  _QWORD *v16; // rdx
  struct _MDL *Mdl; // rax
  int v18; // edx
  struct _MDL *v19; // rcx
  __int128 v21; // [rsp+40h] [rbp-40h] BYREF
  __int128 v22; // [rsp+50h] [rbp-30h]
  __int128 v23; // [rsp+60h] [rbp-20h]
  __int64 *v24; // [rsp+70h] [rbp-10h]
  PVOID VirtualAddress; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+50h] BYREF
  _QWORD *v27; // [rsp+D8h] [rbp+58h]

  v27 = a4;
  v24 = 0;
  VirtualAddress = 0;
  v26 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v21) = -1;
    else
      LODWORD(v21) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v21) = 56;
  }
  v7 = a5;
  *((_QWORD *)&v22 + 1) = 0x100000001LL;
  v24 = off_14006C338;
  *(_QWORD *)&v23 = *a1;
  *((_QWORD *)&v21 + 1) = SecureDmaEnabler_WdfEvtCommonBufferPageCleanupCallback;
  *((_QWORD *)&v23 + 1) = (a2 & -(__int64)(a5 != 0)) + 128;
  v8 = 4096;
  if ( a3 > 0x1000 )
    v8 = a3;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64, _QWORD, __int64 *, PVOID *))(WdfFunctions_01033 + 1536))(
          WdfDriverGlobals,
          &v21,
          512,
          1229146200,
          v8,
          &v26,
          &VirtualAddress);
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 72LL),
        v9,
        18,
        20,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
        v10);
    }
LABEL_19:
    if ( v26 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 1664))(WdfDriverGlobals);
    return (unsigned int)v10;
  }
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          v26,
          off_14006C338);
  v12 = (_QWORD *)v11;
  *(_QWORD *)(v11 + 16) = v26;
  *(_QWORD *)(v11 + 24) = a1;
  *(_QWORD *)(v11 + 88) = 0;
  if ( a3 > 0x1000 )
  {
    Mdl = IoAllocateMdl(VirtualAddress, v8, 0, 0, 0);
    v12[11] = Mdl;
    if ( !Mdl )
    {
      v10 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1[1] + 72LL),
          v18,
          18,
          21,
          (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
          154);
      }
      goto LABEL_16;
    }
    MmBuildMdlForNonPagedPool(Mdl);
    v16 = (_QWORD *)v12[11];
  }
  else
  {
    v13 = (unsigned __int64)VirtualAddress;
    v14 = (_QWORD *)(v11 + 32);
    v15 = (__int16)VirtualAddress;
    *(_QWORD *)(v11 + 32) = 0;
    *(_WORD *)(v11 + 42) = 0;
    *(_DWORD *)(v11 + 72) = v8;
    *(_QWORD *)(v11 + 64) = v13 & 0xFFFFFFFFFFFFF000uLL;
    *(_DWORD *)(v11 + 76) = v15 & 0xFFF;
    *(_WORD *)(v11 + 40) = 8 * (((v8 + (unsigned __int64)(v15 & 0xFFF) + 4095) >> 12) + 6);
    MmBuildMdlForNonPagedPool((PMDL)(v11 + 32));
    v16 = v14;
  }
  v10 = SecureDmaEnabler_MapMemory((__int64)a1, v16, v8, (__int64)(v12 + 12));
  if ( v10 < 0 )
  {
LABEL_16:
    if ( v12 )
    {
      v19 = (struct _MDL *)v12[11];
      if ( v19 )
        IoFreeMdl(v19);
    }
    goto LABEL_19;
  }
  *v12 = VirtualAddress;
  v12[1] = v12[12];
  *v27 = v12;
  if ( v7 )
    *v7 = v12 + 16;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14008358c  mov     [rsp-38h+arg_8], rbx
0x140083591  mov     [rsp-38h+arg_18], r9
0x140083596  push    rbp
0x140083597  push    rsi
0x140083598  push    rdi
0x140083599  push    r12
0x14008359b  push    r13
0x14008359d  push    r14
0x14008359f  push    r15
0x1400835a1  mov     rbp, rsp
0x1400835a4  sub     rsp, 80h
0x1400835ab  xorps   xmm0, xmm0
0x1400835ae  xor     eax, eax
0x1400835b0  mov     r14, rcx
0x1400835b3  mov     [rbp+var_10], rax
0x1400835b7  xor     ecx, ecx
0x1400835b9  mov     r12, r8
0x1400835bc  cmp     cs:WdfClientVersionHigherThanFramework, cl
0x1400835c2  mov     [rbp+VirtualAddress], rcx
0x1400835c6  mov     [rbp+arg_10], rcx
0x1400835ca  movups  [rbp+var_40], xmm0
0x1400835ce  movups  [rbp+var_30], xmm0
0x1400835d2  movups  [rbp+var_20], xmm0
0x1400835d6  jz      short loc_1400835FC
0x1400835d8  cmp     cs:WdfStructureCount, 26h ; '&'
0x1400835df  jbe     short loc_1400835F3
0x1400835e1  mov     rax, cs:WdfStructures
0x1400835e8  mov     ecx, [rax+130h]
0x1400835ee  mov     dword ptr [rbp+var_40], ecx
0x1400835f1  jmp     short loc_140083603
0x1400835f3  mov     dword ptr [rbp+var_40], 0FFFFFFFFh
0x1400835fa  jmp     short loc_140083603
0x1400835fc  mov     dword ptr [rbp+var_40], 38h ; '8'
0x140083603  mov     r15, [rbp+arg_20]
0x140083607  mov     eax, 1
0x14008360c  mov     dword ptr [rbp+var_30+8], eax
0x14008360f  mov     dword ptr [rbp+var_30+0Ch], eax
0x140083612  mov     rax, cs:off_14006C338
0x140083619  mov     [rbp+var_10], rax
0x14008361d  mov     rax, r15
0x140083620  neg     rax
0x140083623  mov     rax, [r14]
0x140083626  sbb     rcx, rcx
0x140083629  mov     qword ptr [rbp+var_20], rax
0x14008362d  lea     rax, SecureDmaEnabler_WdfEvtCommonBufferPageCleanupCallback
0x140083634  and     rcx, rdx
0x140083637  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14008363b  mov     qword ptr [rbp+var_40+8], rax
0x14008363f  mov     eax, 1000h
0x140083644  mov     qword ptr [rbp+var_20+8], rcx
0x140083648  mov     esi, eax
0x14008364a  cmp     r12, rax
0x14008364d  jbe     short loc_140083652
0x14008364f  mov     esi, r12d
0x140083652  mov     rax, cs:WdfFunctions_01033
0x140083659  lea     rcx, [rbp+VirtualAddress]
0x14008365d  mov     [rsp+80h+var_50], rcx
0x140083662  lea     rdx, [rbp+var_40]
0x140083666  lea     rcx, [rbp+arg_10]
0x14008366a  mov     r13d, esi
0x14008366d  mov     [rsp+80h+var_58], rcx
0x140083672  mov     r9d, 49434858h
0x140083678  mov     rcx, cs:WdfDriverGlobals
0x14008367f  mov     r8d, 200h
0x140083685  mov     rax, [rax+600h]
0x14008368c  mov     [rsp+80h+Irp], r13
0x140083691  call    _guard_dispatch_icall
0x140083696  mov     ebx, eax
0x140083698  test    eax, eax
0x14008369a  jns     short loc_1400836DE
0x14008369c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400836a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400836aa  jz      loc_140083801
0x1400836b0  mov     rcx, [r14+8]
0x1400836b4  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x1400836bb  mov     r9d, 14h
0x1400836c1  mov     dword ptr [rsp+80h+var_58], ebx
0x1400836c5  mov     dl, 2
0x1400836c7  mov     [rsp+80h+Irp], rax
0x1400836cc  mov     rcx, [rcx+48h]
0x1400836d0  lea     r8d, [r9-2]
0x1400836d4  call    WPP_RECORDER_SF_d
0x1400836d9  jmp     loc_140083801
0x1400836de  mov     rax, cs:WdfFunctions_01033
0x1400836e5  mov     r8, cs:off_14006C338
0x1400836ec  mov     rdx, [rbp+arg_10]
0x1400836f0  mov     rcx, cs:WdfDriverGlobals
0x1400836f7  mov     rax, [rax+650h]
0x1400836fe  call    _guard_dispatch_icall
0x140083703  mov     rcx, [rbp+arg_10]
0x140083707  xor     r8d, r8d; SecondaryBuffer
0x14008370a  mov     rdi, rax
0x14008370d  mov     [rax+10h], rcx
0x140083711  mov     [rax+18h], r14
0x140083715  mov     [rax+58h], r8
0x140083719  cmp     r12, 1000h
0x140083720  ja      short loc_140083782
0x140083722  mov     r9, [rbp+VirtualAddress]
0x140083726  lea     rbx, [rax+20h]
0x14008372a  mov     r10d, r9d
0x14008372d  mov     [rbx], r8
0x140083730  mov     edx, 0FFFh
0x140083735  mov     [rbx+0Ah], r8w
0x14008373a  mov     eax, r10d
0x14008373d  mov     [rbx+28h], esi
0x140083740  and     rax, rdx
0x140083743  and     r9, 0FFFFFFFFFFFFF000h
0x14008374a  add     rax, rdx
0x14008374d  mov     [rbx+20h], r9
0x140083751  add     rax, r13
0x140083754  and     r10d, edx
0x140083757  shr     rax, 0Ch
0x14008375b  mov     rcx, rbx; MemoryDescriptorList
0x14008375e  add     ax, 6
0x140083762  mov     [rbx+2Ch], r10d
0x140083766  shl     ax, 3
0x14008376a  mov     [rbx+8], ax
0x14008376e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140083775  nop     dword ptr [rax+rax+00h]
0x14008377a  mov     rdx, rbx
0x14008377d  jmp     loc_140083855
0x140083782  mov     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140083786  xor     r9d, r9d; ChargeQuota
0x140083789  mov     edx, esi; Length
0x14008378b  mov     [rsp+80h+Irp], r8; Irp
0x140083790  call    cs:__imp_IoAllocateMdl
0x140083797  nop     dword ptr [rax+rax+00h]
0x14008379c  mov     [rdi+58h], rax
0x1400837a0  test    rax, rax
0x1400837a3  jnz     loc_140083842
0x1400837a9  mov     ebx, 0C000009Ah
0x1400837ae  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400837b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400837bc  jz      short loc_1400837E7
0x1400837be  mov     rcx, [r14+8]
0x1400837c2  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x1400837c9  mov     r9d, 15h
0x1400837cf  mov     dword ptr [rsp+80h+var_58], ebx
0x1400837d3  mov     dl, 2
0x1400837d5  mov     [rsp+80h+Irp], rax
0x1400837da  mov     rcx, [rcx+48h]
0x1400837de  lea     r8d, [r9-3]
0x1400837e2  call    WPP_RECORDER_SF_d
0x1400837e7  test    rdi, rdi
0x1400837ea  jz      short loc_140083801
0x1400837ec  mov     rcx, [rdi+58h]; Mdl
0x1400837f0  test    rcx, rcx
0x1400837f3  jz      short loc_140083801
0x1400837f5  call    cs:__imp_IoFreeMdl
0x1400837fc  nop     dword ptr [rax+rax+00h]
0x140083801  mov     rdx, [rbp+arg_10]
0x140083805  test    rdx, rdx
0x140083808  jz      short loc_140083824
0x14008380a  mov     rax, cs:WdfFunctions_01033
0x140083811  mov     rcx, cs:WdfDriverGlobals
0x140083818  mov     rax, [rax+680h]
0x14008381f  call    _guard_dispatch_icall
0x140083824  mov     eax, ebx
0x140083826  mov     rbx, [rsp+80h+arg_8]
0x14008382e  add     rsp, 80h
0x140083835  pop     r15
0x140083837  pop     r14
0x140083839  pop     r13
0x14008383b  pop     r12
0x14008383d  pop     rdi
0x14008383e  pop     rsi
0x14008383f  pop     rbp
0x140083840  retn
0x140083842  mov     rcx, rax; MemoryDescriptorList
0x140083845  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14008384c  nop     dword ptr [rax+rax+00h]
0x140083851  mov     rdx, [rdi+58h]
0x140083855  lea     r12, [rdi+60h]
0x140083859  mov     r8d, esi
0x14008385c  mov     r9, r12
0x14008385f  mov     rcx, r14
0x140083862  call    SecureDmaEnabler_MapMemory
0x140083867  mov     ebx, eax
0x140083869  test    eax, eax
0x14008386b  js      loc_1400837E7
0x140083871  mov     rax, [rbp+VirtualAddress]
0x140083875  mov     [rdi], rax
0x140083878  mov     rax, [r12]
0x14008387c  mov     [rdi+8], rax
0x140083880  mov     rax, [rbp+arg_18]
0x140083884  mov     [rax], rdi
0x140083887  test    r15, r15
0x14008388a  jz      short loc_140083824
0x14008388c  lea     rax, [rdi+80h]
0x140083893  mov     [r15], rax
0x140083896  jmp     short loc_140083824
```
