# FltpCreateFileNameInformation

- ea: `0x180058a30`
- end: `0x180058e6f`
- name: `FltpCreateFileNameInformation`
- size: `1087`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18000d8b0`
- `0x18000eb80`
- `0x180058090`

## callees

- `0x180009f20`
- `0x180013f50`
- `0x1800148b0`
- `0x1800248e0`
- `0x180057fe0`
- `0x180058a30`
- `0x180059220`
- `0x180059470`
- `0x18005a2e0`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180058d59`
- `ntoskrnl!ExFreePoolWithTag` at `0x180058d59`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180058a89`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180058a89`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180058b37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180058b37`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180058d17`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180058d17`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180058bce`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180058bce`

## string_xrefs

- `0x180058afd`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180058c4f`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180058c86`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180058d29`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180058df8`: `FltpCreateFileNameInformationWorker`
- `0x180058e1e`: `FltpCreateFileNameInformationWorker`
- `0x180058e37`: `FltpCreateFileNameInformationWorker`

## pseudocode

```c
__int64 __fastcall FltpCreateFileNameInformation(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  _DWORD *v4; // rax
  _DWORD *v5; // rcx
  int v6; // eax
  int NormalizedFileName; // eax
  int FileNameInformation; // ebp
  __int64 v9; // rsi
  int v10; // eax
  int v12; // eax
  __int64 v13; // rax
  unsigned int OpenedFileName; // r14d
  __int64 v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  __int64 Parameter; // [rsp+40h] [rbp-48h] BYREF
  __int128 v26; // [rsp+48h] [rbp-40h]
  char v27; // [rsp+98h] [rbp+10h] BYREF

  if ( !(unsigned __int8)FltpShouldSwapStacks(18432) )
  {
    v2 = *(_QWORD *)(a1 + 48);
    if ( v2 )
      v3 = *(_QWORD *)(v2 + 16);
    else
      v3 = 0;
    *(_QWORD *)(a1 + 136) = v3;
    *(_QWORD *)(a1 + 144) = _InterlockedExchangeAdd64(&qword_180040350, 0);
    v4 = ExAllocateFromNPagedLookasideList(&stru_18003F340);
    *(_QWORD *)(a1 + 112) = v4;
    v5 = v4;
    if ( v4 )
    {
      v4[4] = 0;
      v4[6] = 0;
      v4[5] = 254;
      *(_OWORD *)v4 = 0;
      *((_WORD *)v4 + 1) = 254;
      *((_QWORD *)v4 + 1) = v4 + 7;
      v6 = (unsigned __int8)*(_DWORD *)(a1 + 108);
      if ( v6 == 1 )
      {
        if ( (byte_180040A43 & 4) != 0 )
          McTemplateU0sp_EtwWriteTransfer(
            v5,
            NameCacheSup_c3791,
            "FltpCreateFileNameInformationWorker",
            *(_QWORD *)(a1 + 64));
        NormalizedFileName = FltpGetNormalizedFileName(a1);
LABEL_9:
        FileNameInformation = NormalizedFileName;
LABEL_10:
        if ( FileNameInformation >= 0 )
        {
          FileNameInformation = FltpAllocateFileNameInformation(a1);
          if ( (int)FltpDbgStatus(
                      (unsigned int)FileNameInformation,
                      "minkernel\\fs\\filtermgr\\filter\\namecachesup.c",
                      3837,
                      0) >= 0 )
            FileNameInformation = 0;
        }
        goto LABEL_13;
      }
      v12 = v6 - 2;
      if ( !v12 )
      {
        if ( (byte_180040A43 & 4) != 0 )
          McTemplateU0sp_EtwWriteTransfer(
            v5,
            NameCacheSup_c3800,
            "FltpCreateFileNameInformationWorker",
            *(_QWORD *)(a1 + 64));
        v13 = *(_QWORD *)(a1 + 48);
        v27 = 0;
        if ( v13 )
        {
          v15 = *(_QWORD *)(a1 + 80);
          v16 = 0;
          if ( v15 )
          {
            v17 = *(_QWORD *)(v15 + 16);
            v16 = *(_QWORD *)(v17 + 16);
            *(_QWORD *)(v17 + 16) = *(_QWORD *)(v13 + 16);
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)(a1 + 48) + 24LL))(
                  *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL),
                  *(_QWORD *)(a1 + 64),
                  *(_QWORD *)(a1 + 80),
                  *(unsigned int *)(a1 + 108),
                  &v27,
                  *(_QWORD *)(a1 + 112));
          OpenedFileName = v18;
          if ( (unsigned __int8)*(_DWORD *)(a1 + 108) == 1 )
          {
            if ( (int)FltpDbgStatus(v18, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 6526, 0) < 0 )
            {
              if ( OpenedFileName != -1073741670 )
              {
                *(_DWORD *)(a1 + 40) |= 0x2000u;
                if ( (*(_DWORD *)(a1 + 40) & 0x4000) != 0 )
                  OpenedFileName = -1071906811;
                else
                  OpenedFileName = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)(a1 + 48) + 24LL))(
                                     *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL),
                                     *(_QWORD *)(a1 + 64),
                                     *(_QWORD *)(a1 + 80),
                                     *(_DWORD *)(a1 + 108) & 0xFFFFFF00 | 2,
                                     &v27,
                                     *(_QWORD *)(a1 + 112));
              }
            }
            else
            {
              *(_DWORD *)(a1 + 40) |= 0x1000u;
            }
          }
          v19 = *(_QWORD *)(a1 + 80);
          if ( v19 )
            *(_QWORD *)(*(_QWORD *)(v19 + 16) + 16LL) = v16;
          if ( (int)FltpDbgStatus(OpenedFileName, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 6583, 0) >= 0 )
          {
            if ( v27 )
              *(_DWORD *)(a1 + 40) |= 2u;
            v20 = *(_QWORD *)(a1 + 24);
            if ( v20 )
              v21 = *(_DWORD *)(v20 + 56);
            else
              v21 = **(_DWORD **)(a1 + 32);
            if ( (v21 & 1) != 0 )
            {
              v22 = *(_QWORD *)(a1 + 24);
              if ( v22 )
                v23 = v22 + 112;
              else
                v23 = *(_QWORD *)(a1 + 32) + 8LL;
              FltpParseShareName(v23, *(_QWORD *)(a1 + 112));
            }
          }
        }
        else
        {
          *(_DWORD *)(a1 + 40) |= 2u;
          OpenedFileName = FltpGetOpenedFileName(a1);
        }
        FileNameInformation = OpenedFileName;
        goto LABEL_10;
      }
      if ( v12 == 1 )
      {
        if ( (byte_180040A43 & 4) != 0 )
          McTemplateU0sp_EtwWriteTransfer(
            v5,
            NameCacheSup_c3810,
            "FltpCreateFileNameInformationWorker",
            *(_QWORD *)(a1 + 64));
        NormalizedFileName = FltpCallShortFileNameHandler(a1);
        goto LABEL_9;
      }
      FileNameInformation = -1073741811;
    }
    else
    {
      FileNameInformation = -1073741670;
    }
LABEL_13:
    v9 = *(_QWORD *)(a1 + 112);
    if ( v9 )
    {
      v10 = *(_DWORD *)(v9 + 16);
      if ( (v10 & 1) != 0 )
      {
        if ( (v10 & 2) != 0 )
        {
          ExFreeToPagedLookasideList(&stru_18003F9C0, *(PVOID *)(v9 + 8));
          *(_DWORD *)(v9 + 16) &= ~2u;
        }
        else
        {
          ExFreePoolWithTag(*(PVOID *)(v9 + 8), 0x346E4D46u);
        }
        *(_DWORD *)(v9 + 16) &= ~1u;
      }
      ExFreeToNPagedLookasideList(&stru_18003F340, *(PVOID *)(a1 + 112));
      *(_QWORD *)(a1 + 112) = 0;
    }
    return (unsigned int)FileNameInformation;
  }
  Parameter = a1;
  v26 = 0;
  v24 = KeExpandKernelStackAndCalloutEx(FltpCreateFileNameInformationCallout, &Parameter, 0x6000u, 0, 0);
  if ( (int)FltpDbgStatus(v24, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 3633, 0) >= 0 )
    return DWORD2(v26);
  if ( v24 == -1073741801 )
    return (unsigned int)-1073741670;
  return v24;
}

```

## disassembly

```asm
0x180058a30  push    rbx
0x180058a32  push    rbp
0x180058a33  push    rdi
0x180058a34  sub     rsp, 70h
0x180058a38  mov     rbx, rcx
0x180058a3b  mov     ecx, 4800h
0x180058a40  call    FltpShouldSwapStacks
0x180058a45  xor     edi, edi
0x180058a47  test    al, al
0x180058a49  jnz     loc_180058CEF
0x180058a4f  mov     rax, [rbx+30h]
0x180058a53  mov     [rsp+88h+arg_0], rsi
0x180058a5b  test    rax, rax
0x180058a5e  jz      loc_180058BB0
0x180058a64  mov     rcx, [rax+10h]
0x180058a68  mov     [rbx+88h], rcx
0x180058a6f  mov     rax, rdi
0x180058a72  lock xadd cs:qword_180040350, rax
0x180058a7b  lea     rcx, stru_18003F340; Lookaside
0x180058a82  mov     [rbx+90h], rax
0x180058a89  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180058a90  nop     dword ptr [rax+rax+00h]
0x180058a95  mov     [rbx+70h], rax
0x180058a99  mov     rcx, rax
0x180058a9c  test    rax, rax
0x180058a9f  jz      loc_180058CE5
0x180058aa5  mov     [rax+10h], edi
0x180058aa8  xorps   xmm0, xmm0
0x180058aab  mov     [rax+18h], edi
0x180058aae  mov     eax, 0FEh
0x180058ab3  mov     [rcx+14h], eax
0x180058ab6  movups  xmmword ptr [rcx], xmm0
0x180058ab9  mov     [rcx+2], ax
0x180058abd  lea     rax, [rcx+1Ch]
0x180058ac1  mov     [rcx+8], rax
0x180058ac5  mov     eax, [rbx+6Ch]
0x180058ac8  movzx   eax, al
0x180058acb  cmp     eax, 1
0x180058ace  jnz     loc_180058B5A
0x180058ad4  test    cs:byte_180040A43, 4
0x180058adb  jnz     loc_180058DF4
0x180058ae1  mov     rcx, rbx
0x180058ae4  call    FltpGetNormalizedFileName
0x180058ae9  mov     ebp, eax
0x180058aeb  test    ebp, ebp
0x180058aed  js      short loc_180058B18
0x180058aef  mov     rcx, rbx
0x180058af2  call    FltpAllocateFileNameInformation
0x180058af7  mov     r8d, 0EFDh
0x180058afd  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180058b04  xor     r9d, r9d
0x180058b07  mov     ecx, eax
0x180058b09  mov     ebp, eax
0x180058b0b  call    FltpDbgStatus
0x180058b10  test    eax, eax
0x180058b12  jns     loc_180058D4D
0x180058b18  mov     rsi, [rbx+70h]
0x180058b1c  test    rsi, rsi
0x180058b1f  jz      short loc_180058B47
0x180058b21  mov     eax, [rsi+10h]
0x180058b24  test    al, 1
0x180058b26  jnz     loc_180058BB8
0x180058b2c  mov     rdx, [rbx+70h]; Entry
0x180058b30  lea     rcx, stru_18003F340; Lookaside
0x180058b37  call    cs:__imp_ExFreeToNPagedLookasideList
0x180058b3e  nop     dword ptr [rax+rax+00h]
0x180058b43  mov     [rbx+70h], rdi
0x180058b47  mov     rsi, [rsp+88h+arg_0]
0x180058b4f  mov     eax, ebp
0x180058b51  add     rsp, 70h
0x180058b55  pop     rdi
0x180058b56  pop     rbp
0x180058b57  pop     rbx
0x180058b58  retn
0x180058b5a  sub     eax, 2
0x180058b5d  jnz     loc_180058DD9
0x180058b63  test    cs:byte_180040A43, 4
0x180058b6a  mov     [rsp+88h+var_20], r14
0x180058b6f  mov     [rsp+88h+var_28], r15
0x180058b74  jnz     loc_180058E33
0x180058b7a  mov     rax, [rbx+30h]
0x180058b7e  lea     r15, [rbx+6Ch]
0x180058b82  mov     [rsp+88h+arg_8], dil
0x180058b8a  test    rax, rax
0x180058b8d  jnz     short loc_180058BE7
0x180058b8f  or      dword ptr [rbx+28h], 2
0x180058b93  mov     rcx, rbx
0x180058b96  call    FltpGetOpenedFileName
0x180058b9b  mov     r14d, eax
0x180058b9e  mov     r15, [rsp+88h+var_28]
0x180058ba3  mov     ebp, r14d
0x180058ba6  mov     r14, [rsp+88h+var_20]
0x180058bab  jmp     loc_180058AEB
0x180058bb0  mov     rcx, rdi
0x180058bb3  jmp     loc_180058A68
0x180058bb8  mov     rcx, [rsi+8]; P
0x180058bbc  test    al, 2
0x180058bbe  jz      loc_180058D54
0x180058bc4  mov     rdx, rcx; Entry
0x180058bc7  lea     rcx, stru_18003F9C0; Lookaside
0x180058bce  call    cs:__imp_ExFreeToPagedLookasideList
0x180058bd5  nop     dword ptr [rax+rax+00h]
0x180058bda  and     dword ptr [rsi+10h], 0FFFFFFFDh
0x180058bde  and     dword ptr [rsi+10h], 0FFFFFFFEh
0x180058be2  jmp     loc_180058B2C
0x180058be7  mov     rcx, [rbx+50h]
0x180058beb  mov     [rsp+88h+arg_10], r12
0x180058bf3  mov     r12, rdi
0x180058bf6  test    rcx, rcx
0x180058bf9  jz      short loc_180058C0B
0x180058bfb  mov     rcx, [rcx+10h]
0x180058bff  mov     rax, [rax+10h]
0x180058c03  mov     r12, [rcx+10h]
0x180058c07  mov     [rcx+10h], rax
0x180058c0b  mov     rcx, [rbx+30h]
0x180058c0f  mov     rdx, [rbx+70h]
0x180058c13  mov     r9d, [rbx+6Ch]
0x180058c17  mov     r8, [rbx+50h]
0x180058c1b  mov     rax, [rcx+18h]
0x180058c1f  mov     rcx, [rcx+10h]
0x180058c23  mov     [rsp+88h+var_60], rdx
0x180058c28  lea     rdx, [rsp+88h+arg_8]
0x180058c30  mov     [rsp+88h+Context], rdx
0x180058c35  mov     rdx, [rbx+40h]
0x180058c39  call    _guard_dispatch_icall
0x180058c3e  mov     ecx, [r15]
0x180058c41  mov     r14d, eax
0x180058c44  cmp     cl, 1
0x180058c47  jnz     short loc_180058C6F
0x180058c49  mov     r8d, 197Eh
0x180058c4f  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180058c56  xor     r9d, r9d
0x180058c59  mov     ecx, eax
0x180058c5b  call    FltpDbgStatus
0x180058c60  test    eax, eax
0x180058c62  js      loc_180058D6A
0x180058c68  or      dword ptr [rbx+28h], 1000h
0x180058c6f  mov     rax, [rbx+50h]
0x180058c73  test    rax, rax
0x180058c76  jz      short loc_180058C80
0x180058c78  mov     rax, [rax+10h]
0x180058c7c  mov     [rax+10h], r12
0x180058c80  mov     r8d, 19B7h
0x180058c86  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180058c8d  xor     r9d, r9d
0x180058c90  mov     ecx, r14d
0x180058c93  call    FltpDbgStatus
0x180058c98  mov     r12, [rsp+88h+arg_10]
0x180058ca0  test    eax, eax
0x180058ca2  js      loc_180058B9E
0x180058ca8  cmp     [rsp+88h+arg_8], dil
0x180058cb0  jz      short loc_180058CB6
0x180058cb2  or      dword ptr [rbx+28h], 2
0x180058cb6  mov     rax, [rbx+18h]
0x180058cba  test    rax, rax
0x180058cbd  jz      loc_180058E4F
0x180058cc3  mov     ecx, [rax+38h]
0x180058cc6  test    cl, 1
0x180058cc9  jz      loc_180058B9E
0x180058ccf  mov     rcx, [rbx+18h]
0x180058cd3  test    rcx, rcx
0x180058cd6  jz      loc_1800793B2
0x180058cdc  add     rcx, 70h ; 'p'
0x180058ce0  jmp     loc_1800793BA
0x180058ce5  mov     ebp, 0C000009Ah
0x180058cea  jmp     loc_180058B18
0x180058cef  xorps   xmm0, xmm0
0x180058cf2  mov     [rsp+88h+Parameter], rbx
0x180058cf7  xor     r9d, r9d; Wait
0x180058cfa  mov     [rsp+88h+Context], rdi; Context
0x180058cff  mov     r8d, 6000h; Size
0x180058d05  lea     rdx, [rsp+88h+Parameter]; Parameter
0x180058d0a  lea     rcx, FltpCreateFileNameInformationCallout; Callout
0x180058d11  movdqu  [rsp+88h+var_40], xmm0
0x180058d17  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x180058d1e  nop     dword ptr [rax+rax+00h]
0x180058d23  mov     r8d, 0E31h
0x180058d29  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180058d30  mov     ecx, eax
0x180058d32  xor     r9d, r9d
0x180058d35  mov     ebx, eax
0x180058d37  call    FltpDbgStatus
0x180058d3c  test    eax, eax
0x180058d3e  js      loc_180058E5A
0x180058d44  mov     eax, dword ptr [rsp+88h+var_40+8]
0x180058d48  jmp     loc_180058B51
0x180058d4d  mov     ebp, edi
0x180058d4f  jmp     loc_180058B18
0x180058d54  mov     edx, 346E4D46h; Tag
0x180058d59  call    cs:__imp_ExFreePoolWithTag
0x180058d60  nop     dword ptr [rax+rax+00h]
0x180058d65  jmp     loc_180058BDE
0x180058d6a  mov     ebp, 0C000009Ah
0x180058d6f  cmp     r14d, ebp
0x180058d72  jz      loc_180058C6F
0x180058d78  or      dword ptr [rbx+28h], 2000h
0x180058d7f  test    dword ptr [rbx+28h], 4000h
0x180058d86  jnz     short loc_180058DCE
0x180058d88  mov     rcx, [rbx+30h]
0x180058d8c  mov     rdx, [rbx+70h]
0x180058d90  mov     r9d, [rbx+6Ch]
0x180058d94  mov     r8, [rbx+50h]
0x180058d98  and     r9d, 0FFFFFF02h
0x180058d9f  mov     rax, [rcx+18h]
0x180058da3  or      r9d, 2
0x180058da7  mov     rcx, [rcx+10h]
0x180058dab  mov     [rsp+88h+var_60], rdx
0x180058db0  lea     rdx, [rsp+88h+arg_8]
0x180058db8  mov     [rsp+88h+Context], rdx
0x180058dbd  mov     rdx, [rbx+40h]
0x180058dc1  call    _guard_dispatch_icall
0x180058dc6  mov     r14d, eax
0x180058dc9  jmp     loc_180058C6F
0x180058dce  mov     r14d, 0C01C0005h
0x180058dd4  jmp     loc_180058C6F
0x180058dd9  cmp     eax, 1
0x180058ddc  jnz     short loc_180058E10
0x180058dde  test    cs:byte_180040A43, 4
0x180058de5  jnz     short loc_180058E1A
0x180058de7  mov     rcx, rbx
0x180058dea  call    FltpCallShortFileNameHandler
0x180058def  jmp     loc_180058AE9
0x180058df4  mov     r9, [rbx+40h]
0x180058df8  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x180058dff  lea     rdx, NameCacheSup_c3791
0x180058e06  call    McTemplateU0sp_EtwWriteTransfer
0x180058e0b  jmp     loc_180058AE1
0x180058e10  mov     ebp, 0C000000Dh
0x180058e15  jmp     loc_180058B18
0x180058e1a  mov     r9, [rbx+40h]
0x180058e1e  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x180058e25  lea     rdx, NameCacheSup_c3810
0x180058e2c  call    McTemplateU0sp_EtwWriteTransfer
0x180058e31  jmp     short loc_180058DE7
0x180058e33  mov     r9, [rbx+40h]
0x180058e37  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x180058e3e  lea     rdx, NameCacheSup_c3800
0x180058e45  call    McTemplateU0sp_EtwWriteTransfer
0x180058e4a  jmp     loc_180058B7A
0x180058e4f  mov     rax, [rbx+20h]
0x180058e53  mov     ecx, [rax]
0x180058e55  jmp     loc_180058CC6
0x180058e5a  cmp     ebx, 0C0000017h
0x180058e60  mov     ebp, 0C000009Ah
0x180058e65  cmovz   ebx, ebp
0x180058e68  mov     eax, ebx
0x180058e6a  jmp     loc_180058B51
0x1800793b2  mov     rcx, [rbx+20h]
0x1800793b6  add     rcx, 8
0x1800793ba  mov     rdx, [rbx+70h]
0x1800793be  call    FltpParseShareName
0x1800793c3  nop
0x1800793c4  jmp     loc_180058B9E
```
