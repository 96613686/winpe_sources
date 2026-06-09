# Bulk_TransferData_ConfigureBuffer

- ea: `0x140006910`
- end: `0x140006b7e`
- name: `Bulk_TransferData_ConfigureBuffer`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007c88`

## callees

- `0x140005d48`
- `0x140006910`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14000699e`
- `ntoskrnl!IoAllocateMdl` at `0x14000699e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400069b7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400069b7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006a16`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006a16`

## pseudocode

```c
__int64 __fastcall Bulk_TransferData_ConfigureBuffer(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // esi
  int v4; // ecx
  __int64 v5; // rbp
  __int64 v6; // rax
  int v8; // ecx
  __int64 v9; // rax
  PMDL Mdl; // rax
  __int64 v11; // rcx
  PVOID v12; // rax
  int v13; // r9d
  int v14; // edx
  __int64 v15; // r10
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // edx

  v1 = *(_QWORD *)(a1 + 48);
  v2 = 0;
  if ( *(_WORD *)(v1 + 2) == 56 )
  {
LABEL_2:
    v4 = *(_DWORD *)(a1 + 76);
    v5 = *(_QWORD *)(a1 + 56);
    if ( v4 == 2 || (v8 = v4 - 1) == 0 )
    {
      v6 = *(_QWORD *)(v1 + 40);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 88) = v6;
      }
      else
      {
        v11 = *(_QWORD *)(v1 + 48);
        if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
          v12 = *(PVOID *)(v11 + 24);
        else
          v12 = MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
        *(_QWORD *)(a1 + 88) = v12;
        if ( !v12 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v13 = 39;
LABEL_26:
            v18 = *(unsigned __int8 *)(*(_QWORD *)(v5 + 48) + 143LL);
            LOBYTE(v18) = 2;
            WPP_RECORDER_SF_ddL(
              *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
              v18,
              14,
              v13,
              (__int64)WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids,
              *(_BYTE *)(*(_QWORD *)(v5 + 48) + 143LL),
              *(_DWORD *)(*(_QWORD *)(v5 + 56) + 152LL),
              *(_DWORD *)(v5 + 64));
          }
          return (unsigned int)-1073741670;
        }
      }
    }
    else if ( v8 == 2 )
    {
      v9 = *(_QWORD *)(v1 + 48);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 80) = v9;
        return v2;
      }
      Mdl = IoAllocateMdl(*(PVOID *)(v1 + 40), *(_DWORD *)(a1 + 104), 0, 0, 0);
      *(_QWORD *)(a1 + 80) = Mdl;
      if ( Mdl )
      {
LABEL_11:
        MmBuildMdlForNonPagedPool(*(PMDL *)(a1 + 80));
        return v2;
      }
      if ( (*(_DWORD *)(v1 + 32) & 0x10) != 0 && *(_QWORD *)(v5 + 120) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v14 = *(unsigned __int8 *)(*(_QWORD *)(v5 + 48) + 143LL);
          LOBYTE(v14) = 5;
          WPP_RECORDER_SF_ddL(
            *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
            v14,
            14,
            40,
            (__int64)WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids,
            *(_BYTE *)(*(_QWORD *)(v5 + 48) + 143LL),
            *(_DWORD *)(*(_QWORD *)(v5 + 56) + 152LL),
            *(_DWORD *)(v5 + 64));
        }
        v15 = *(_QWORD *)(v5 + 120);
        v16 = *(unsigned int *)(a1 + 104);
        *(_QWORD *)(a1 + 80) = v15;
        v17 = *(_QWORD *)(v1 + 40);
        *(_QWORD *)v15 = 0;
        *(_DWORD *)(v15 + 40) = v16;
        *(_WORD *)(v15 + 10) = 0;
        *(_WORD *)(v15 + 8) = 8 * ((((unsigned __int64)(v17 & 0xFFF) + v16 + 4095) >> 12) + 6);
        *(_DWORD *)(v15 + 44) = v17 & 0xFFF;
        *(_QWORD *)(v15 + 32) = v17 & 0xFFFFFFFFFFFFF000uLL;
        goto LABEL_11;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 41;
        goto LABEL_26;
      }
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    switch ( *(_WORD *)(v1 + 2) )
    {
      case '9':
      case ':':
        return v2;
      default:
        goto LABEL_2;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140006910  mov     [rsp+arg_8], rbx
0x140006915  mov     [rsp+arg_10], rsi
0x14000691a  push    rdi
0x14000691b  sub     rsp, 40h
0x14000691f  mov     rdi, [rcx+30h]
0x140006923  xor     esi, esi
0x140006925  mov     rbx, rcx
0x140006928  movzx   eax, word ptr [rdi+2]
0x14000692c  cmp     eax, 38h ; '8'
0x14000692f  jz      short def_140006B78; jumptable 0000000140006B78 default case, cases 8-56
0x140006931  add     eax, 0FFFFFFF8h; switch 51 cases
0x140006934  cmp     eax, 32h
0x140006937  jbe     loc_140006B5D
0x14000693d  mov     ecx, [rbx+4Ch]; jumptable 0000000140006B78 default case, cases 8-56
0x140006940  mov     [rsp+48h+arg_0], rbp
0x140006945  mov     rbp, [rbx+38h]
0x140006949  cmp     ecx, 2
0x14000694c  jnz     short loc_140006973
0x14000694e  mov     rax, [rdi+28h]
0x140006952  test    rax, rax
0x140006955  jz      short loc_1400069C5
0x140006957  mov     [rbx+58h], rax
0x14000695b  mov     rbp, [rsp+48h+arg_0]
0x140006960  mov     rbx, [rsp+48h+arg_8]; jumptable 0000000140006B78 cases 57,58
0x140006965  mov     eax, esi
0x140006967  mov     rsi, [rsp+48h+arg_10]
0x14000696c  add     rsp, 40h
0x140006970  pop     rdi
0x140006971  retn
0x140006973  sub     ecx, 1
0x140006976  jz      short loc_14000694E
0x140006978  cmp     ecx, 2
0x14000697b  jnz     short loc_14000695B
0x14000697d  mov     rax, [rdi+30h]
0x140006981  test    rax, rax
0x140006984  jz      short loc_14000698C
0x140006986  mov     [rbx+50h], rax
0x14000698a  jmp     short loc_14000695B
0x14000698c  mov     edx, [rbx+68h]; Length
0x14000698f  xor     r9d, r9d; ChargeQuota
0x140006992  mov     rcx, [rdi+28h]; VirtualAddress
0x140006996  xor     r8d, r8d; SecondaryBuffer
0x140006999  mov     [rsp+48h+Irp], rsi; Irp
0x14000699e  call    cs:__imp_IoAllocateMdl
0x1400069a5  nop     dword ptr [rax+rax+00h]
0x1400069aa  mov     [rbx+50h], rax
0x1400069ae  test    rax, rax
0x1400069b1  jz      short loc_140006A24
0x1400069b3  mov     rcx, [rbx+50h]; MemoryDescriptorList
0x1400069b7  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400069be  nop     dword ptr [rax+rax+00h]
0x1400069c3  jmp     short loc_14000695B
0x1400069c5  mov     rcx, [rdi+30h]; MemoryDescriptorList
0x1400069c9  test    byte ptr [rcx+0Ah], 5
0x1400069cd  jz      short loc_1400069FF
0x1400069cf  mov     rax, [rcx+18h]
0x1400069d3  mov     [rbx+58h], rax
0x1400069d7  test    rax, rax
0x1400069da  jnz     loc_14000695B
0x1400069e0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400069e7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400069ee  jz      loc_140006B53
0x1400069f4  mov     r9d, 27h ; '''
0x1400069fa  jmp     loc_140006B12
0x1400069ff  mov     [rsp+48h+Priority], 40000010h; Priority
0x140006a07  xor     r9d, r9d; RequestedAddress
0x140006a0a  xor     edx, edx; AccessMode
0x140006a0c  mov     dword ptr [rsp+48h+Irp], esi; BugCheckOnFailure
0x140006a10  mov     r8d, 1; CacheType
0x140006a16  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140006a1d  nop     dword ptr [rax+rax+00h]
0x140006a22  jmp     short loc_1400069D3
0x140006a24  mov     eax, [rdi+20h]
0x140006a27  test    al, 10h
0x140006a29  jz      loc_140006AFC
0x140006a2f  cmp     [rbp+78h], rsi
0x140006a33  jz      loc_140006AFC
0x140006a39  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006a40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006a47  jz      short loc_140006A9D
0x140006a49  mov     rax, cs:WPP_GLOBAL_Control
0x140006a50  cmp     [rax+48h], si
0x140006a54  jz      short loc_140006A9D
0x140006a56  mov     rax, [rbp+30h]
0x140006a5a  mov     r9d, 28h ; '('
0x140006a60  mov     rcx, [rbp+38h]
0x140006a64  mov     r8d, 0Eh
0x140006a6a  movzx   edx, byte ptr [rax+8Fh]
0x140006a71  mov     eax, [rbp+40h]
0x140006a74  mov     [rsp+48h+var_10], eax
0x140006a78  mov     eax, [rcx+98h]
0x140006a7e  mov     rcx, [rcx+50h]
0x140006a82  mov     [rsp+48h+var_18], eax
0x140006a86  lea     rax, WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids
0x140006a8d  mov     [rsp+48h+Priority], edx
0x140006a91  mov     dl, 5
0x140006a93  mov     [rsp+48h+Irp], rax
0x140006a98  call    WPP_RECORDER_SF_ddL
0x140006a9d  mov     r10, [rbp+78h]
0x140006aa1  mov     r9d, [rbx+68h]
0x140006aa5  mov     [rbx+50h], r10
0x140006aa9  mov     rdx, [rdi+28h]
0x140006aad  mov     r8d, edx
0x140006ab0  mov     [r10], rsi
0x140006ab3  mov     eax, r8d
0x140006ab6  mov     [r10+28h], r9d
0x140006aba  and     eax, 0FFFh
0x140006abf  lea     rcx, [r9+0FFFh]
0x140006ac6  add     rcx, rax
0x140006ac9  and     rdx, 0FFFFFFFFFFFFF000h
0x140006ad0  shr     rcx, 0Ch
0x140006ad4  xor     eax, eax
0x140006ad6  add     cx, 6
0x140006ada  mov     [r10+0Ah], ax
0x140006adf  shl     cx, 3
0x140006ae3  and     r8d, 0FFFh
0x140006aea  mov     [r10+8], cx
0x140006aef  mov     [r10+2Ch], r8d
0x140006af3  mov     [r10+20h], rdx
0x140006af7  jmp     loc_1400069B3
0x140006afc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006b03  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006b0a  jz      short loc_140006B53
0x140006b0c  mov     r9d, 29h ; ')'
0x140006b12  mov     rax, [rbp+30h]
0x140006b16  mov     r8d, 0Eh
0x140006b1c  mov     rcx, [rbp+38h]
0x140006b20  movzx   edx, byte ptr [rax+8Fh]
0x140006b27  mov     eax, [rbp+40h]
0x140006b2a  mov     [rsp+48h+var_10], eax
0x140006b2e  mov     eax, [rcx+98h]
0x140006b34  mov     rcx, [rcx+50h]
0x140006b38  mov     [rsp+48h+var_18], eax
0x140006b3c  lea     rax, WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids
0x140006b43  mov     [rsp+48h+Priority], edx
0x140006b47  mov     dl, 2
0x140006b49  mov     [rsp+48h+Irp], rax
0x140006b4e  call    WPP_RECORDER_SF_ddL
0x140006b53  mov     esi, 0C000009Ah
0x140006b58  jmp     loc_14000695B
0x140006b5d  lea     rdx, cs:140000000h
0x140006b64  cdqe
0x140006b66  movzx   eax, ds:(byte_140064FFE - 140000000h)[rdx+rax]
0x140006b6e  mov     ecx, ds:(jpt_140006B78 - 140000000h)[rdx+rax*4]
0x140006b75  add     rcx, rdx
0x140006b78  jmp     rcx; switch jump
```
