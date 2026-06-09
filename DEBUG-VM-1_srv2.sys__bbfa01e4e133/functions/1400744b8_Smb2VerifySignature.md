# Smb2VerifySignature

- ea: `0x1400744b8`
- end: `0x14007484d`
- name: `Smb2VerifySignature`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140073a60`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x1400222ec`
- `0x140022958`
- `0x140038490`
- `0x140038560`
- `0x1400744b8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400746e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400746e1`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x14007457e`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x14007457e`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x1400745ab`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x1400745ab`
- `ksecdd!BCryptDuplicateHash` at `0x140074566`
- `ksecdd!BCryptDuplicateHash` at `0x140074566`
- `ksecdd!BCryptHashData` at `0x1400745f5`
- `ksecdd!BCryptHashData` at `0x1400745f5`
- `ksecdd!BCryptFinishHash` at `0x140074627`
- `ksecdd!BCryptFinishHash` at `0x140074627`
- `ksecdd!BCryptDestroyHash` at `0x14007468a`
- `ksecdd!BCryptDestroyHash` at `0x14007468a`

## pseudocode

```c
__int64 __fastcall Smb2VerifySignature(__int64 a1, void *a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  ULONG v5; // r14d
  __int64 v6; // r13
  struct _MDL *v7; // rdi
  void *v8; // r12
  unsigned int v9; // ebp
  ULONG v10; // ebx
  UCHAR *SigningHashObject; // rax
  UCHAR *v12; // r15
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // ebp
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v19; // rdx
  PDEVICE_OBJECT v20; // r10
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+30h] [rbp-88h] BYREF
  ULONG cbOutput; // [rsp+38h] [rbp-80h]
  void *Buf1; // [rsp+40h] [rbp-78h]
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-70h] BYREF
  __int128 v25; // [rsp+58h] [rbp-60h]

  v2 = *(_QWORD *)(a1 + 304);
  v3 = *(_QWORD *)(a1 + 560);
  v5 = *(_DWORD *)(a1 + 404);
  Buf1 = a2;
  v6 = *(_QWORD *)(v2 + 24);
  v7 = *(struct _MDL **)(v2 + 56);
  v8 = *(void **)(v3 + 112);
  v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 140LL);
  phNewHash = 0;
  *(_OWORD *)pbOutput = 0;
  v25 = 0;
  v10 = *(_DWORD *)(v3 + 120);
  cbOutput = *(_DWORD *)(v3 + 124);
  if ( !v8 )
    __int2c();
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(v10);
  v12 = SigningHashObject;
  if ( !SigningHashObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1);
    }
LABEL_23:
    v13 = -1073741670;
    goto LABEL_17;
  }
  v13 = BCryptDuplicateHash(v8, &phNewHash, SigningHashObject, v10, 0);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v19 = 17;
LABEL_49:
      WPP_SF_qD(AttachedDevice, v19, &WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1, v13);
    }
  }
  else
  {
    if ( !(unsigned __int8)SmbCryptoSigningAlgRequireIV(v9)
      || (LOBYTE(v14) = *(_WORD *)(v6 + 12) == 12,
          v13 = SmbCryptoCalculateAndSetIV(v9, *(_QWORD *)(v6 + 24), 0, v14, phNewHash),
          v13 >= 0) )
    {
      while ( 1 )
      {
        if ( (v7->MdlFlags & 5) != 0 )
          MappedSystemVa = (UCHAR *)v7->MappedSystemVa;
        else
          MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
        ByteCount = v5;
        if ( v5 >= v7->ByteCount )
          ByteCount = v7->ByteCount;
        if ( !MappedSystemVa )
          goto LABEL_23;
        v7 = v7->Next;
        v13 = BCryptHashData(phNewHash, MappedSystemVa, ByteCount, 0);
        if ( v13 < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 19;
            goto LABEL_48;
          }
          goto LABEL_17;
        }
        if ( v7 )
        {
          v5 -= ByteCount;
          if ( v5 )
            continue;
        }
        v13 = BCryptFinishHash(phNewHash, pbOutput, cbOutput, 0);
        if ( v13 < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 20;
            goto LABEL_48;
          }
        }
        else if ( memcmp(Buf1, pbOutput, 0x10u) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1);
          }
          v13 = -1073741790;
        }
        goto LABEL_17;
      }
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v19 = 18;
LABEL_48:
      AttachedDevice = v20->AttachedDevice;
      goto LABEL_49;
    }
  }
LABEL_17:
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v12 )
    Smb2DeallocateSigningHashObject(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400744b8  push    rbx
0x1400744ba  push    rbp
0x1400744bb  push    rsi
0x1400744bc  push    rdi
0x1400744bd  push    r12
0x1400744bf  push    r13
0x1400744c1  push    r14
0x1400744c3  push    r15
0x1400744c5  sub     rsp, 78h
0x1400744c9  mov     rax, cs:__security_cookie
0x1400744d0  xor     rax, rsp
0x1400744d3  mov     [rsp+0B8h+var_50], rax
0x1400744d8  mov     rax, [rcx+130h]
0x1400744df  xorps   xmm0, xmm0
0x1400744e2  mov     r8, [rcx+230h]
0x1400744e9  mov     rsi, rcx
0x1400744ec  mov     r14d, [rcx+194h]
0x1400744f3  mov     [rsp+0B8h+Buf1], rdx
0x1400744f8  mov     r13, [rax+18h]
0x1400744fc  mov     rdi, [rax+38h]
0x140074500  mov     r12, [r8+70h]
0x140074504  mov     rax, [rcx+60h]
0x140074508  mov     rcx, [rax+1F0h]
0x14007450f  mov     ebp, [rcx+8Ch]
0x140074515  mov     [rsp+0B8h+phNewHash], 0
0x14007451e  movups  xmmword ptr [rsp+0B8h+pbOutput], xmm0
0x140074523  movups  [rsp+0B8h+var_60], xmm0
0x140074528  mov     eax, [r8+7Ch]
0x14007452c  mov     ebx, [r8+78h]
0x140074530  mov     [rsp+0B8h+cbOutput], eax
0x140074534  test    r12, r12
0x140074537  jz      loc_1400746F2
0x14007453d  mov     ecx, ebx
0x14007453f  call    Smb2AllocateSigningHashObject
0x140074544  mov     r15, rax
0x140074547  test    rax, rax
0x14007454a  jz      loc_1400746AB
0x140074550  mov     r9d, ebx; cbHashObject
0x140074553  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x14007455b  mov     r8, rax; pbHashObject
0x14007455e  lea     rdx, [rsp+0B8h+phNewHash]; phNewHash
0x140074563  mov     rcx, r12; hHash
0x140074566  call    cs:__imp_BCryptDuplicateHash
0x14007456d  nop     dword ptr [rax+rax+00h]
0x140074572  mov     ebx, eax
0x140074574  test    eax, eax
0x140074576  js      loc_140074723
0x14007457c  mov     ecx, ebp
0x14007457e  call    cs:__imp_SmbCryptoSigningAlgRequireIV
0x140074585  nop     dword ptr [rax+rax+00h]
0x14007458a  test    al, al
0x14007458c  jz      short loc_1400745C1
0x14007458e  cmp     word ptr [r13+0Ch], 0Ch
0x140074594  mov     ecx, ebp
0x140074596  mov     rax, [rsp+0B8h+phNewHash]
0x14007459b  mov     rdx, [r13+18h]
0x14007459f  setz    r9b
0x1400745a3  xor     r8d, r8d
0x1400745a6  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x1400745ab  call    cs:__imp_SmbCryptoCalculateAndSetIV
0x1400745b2  nop     dword ptr [rax+rax+00h]
0x1400745b7  mov     ebx, eax
0x1400745b9  test    eax, eax
0x1400745bb  js      loc_14007475E
0x1400745c1  test    byte ptr [rdi+0Ah], 5
0x1400745c5  jz      loc_1400746C5
0x1400745cb  mov     rax, [rdi+18h]
0x1400745cf  mov     ecx, [rdi+28h]
0x1400745d2  mov     ebp, r14d
0x1400745d5  cmp     r14d, ecx
0x1400745d8  cmovnb  ebp, ecx
0x1400745db  test    rax, rax
0x1400745de  jz      loc_1400746BE
0x1400745e4  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x1400745e9  xor     r9d, r9d; dwFlags
0x1400745ec  mov     rdi, [rdi]
0x1400745ef  mov     r8d, ebp; cbInput
0x1400745f2  mov     rdx, rax; pbInput
0x1400745f5  call    cs:__imp_BCryptHashData
0x1400745fc  nop     dword ptr [rax+rax+00h]
0x140074601  mov     ebx, eax
0x140074603  test    eax, eax
0x140074605  js      loc_140074815
0x14007460b  test    rdi, rdi
0x14007460e  jz      short loc_140074615
0x140074610  sub     r14d, ebp
0x140074613  jnz     short loc_1400745C1
0x140074615  mov     r8d, [rsp+0B8h+cbOutput]; cbOutput
0x14007461a  lea     rdx, [rsp+0B8h+pbOutput]; pbOutput
0x14007461f  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x140074624  xor     r9d, r9d; dwFlags
0x140074627  call    cs:__imp_BCryptFinishHash
0x14007462e  nop     dword ptr [rax+rax+00h]
0x140074633  mov     ebx, eax
0x140074635  test    eax, eax
0x140074637  js      loc_140074791
0x14007463d  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x140074642  lea     rdx, [rsp+0B8h+pbOutput]; Buf2
0x140074647  mov     r8d, 10h; Size
0x14007464d  call    memcmp
0x140074652  test    eax, eax
0x140074654  jnz     loc_1400747C9
0x14007465a  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x14007465f  test    rcx, rcx
0x140074662  jnz     short loc_14007468A
0x140074664  test    r15, r15
0x140074667  jnz     short loc_1400746A1
0x140074669  mov     eax, ebx
0x14007466b  mov     rcx, [rsp+0B8h+var_50]
0x140074670  xor     rcx, rsp; StackCookie
0x140074673  call    __security_check_cookie
0x140074678  add     rsp, 78h
0x14007467c  pop     r15
0x14007467e  pop     r14
0x140074680  pop     r13
0x140074682  pop     r12
0x140074684  pop     rdi
0x140074685  pop     rsi
0x140074686  pop     rbp
0x140074687  pop     rbx
0x140074688  retn
0x14007468a  call    cs:__imp_BCryptDestroyHash
0x140074691  nop     dword ptr [rax+rax+00h]
0x140074696  mov     [rsp+0B8h+phNewHash], 0
0x14007469f  jmp     short loc_140074664
0x1400746a1  mov     rcx, r15
0x1400746a4  call    Smb2DeallocateSigningHashObject
0x1400746a9  jmp     short loc_140074669
0x1400746ab  mov     r10, cs:WPP_GLOBAL_Control
0x1400746b2  lea     rcx, WPP_GLOBAL_Control
0x1400746b9  cmp     r10, rcx
0x1400746bc  jnz     short loc_1400746F9
0x1400746be  mov     ebx, 0C000009Ah
0x1400746c3  jmp     short loc_14007465A
0x1400746c5  xor     r9d, r9d; RequestedAddress
0x1400746c8  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x1400746d0  xor     edx, edx; AccessMode
0x1400746d2  mov     [rsp+0B8h+dwFlags], 0; BugCheckOnFailure
0x1400746da  mov     rcx, rdi; MemoryDescriptorList
0x1400746dd  lea     r8d, [r9+1]; CacheType
0x1400746e1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400746e8  nop     dword ptr [rax+rax+00h]
0x1400746ed  jmp     loc_1400745CF
0x1400746f2  int     2Ch; Windows NT - assertion failure
0x1400746f4  jmp     loc_14007453D
0x1400746f9  mov     ecx, [r10+2Ch]
0x1400746fd  test    cl, 1
0x140074700  jz      short loc_1400746BE
0x140074702  cmp     byte ptr [r10+29h], 1
0x140074707  jb      short loc_1400746BE
0x140074709  mov     rcx, [r10+18h]
0x14007470d  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140074714  mov     edx, 10h
0x140074719  mov     r9, rsi
0x14007471c  call    WPP_SF_q
0x140074721  jmp     short loc_1400746BE
0x140074723  mov     rax, cs:WPP_GLOBAL_Control
0x14007472a  lea     rcx, WPP_GLOBAL_Control
0x140074731  cmp     rax, rcx
0x140074734  jz      loc_14007465A
0x14007473a  mov     edx, [rax+2Ch]
0x14007473d  test    dl, 1
0x140074740  jz      loc_14007465A
0x140074746  cmp     byte ptr [rax+29h], 1
0x14007474a  jb      loc_14007465A
0x140074750  mov     rcx, [rax+18h]
0x140074754  mov     edx, 11h
0x140074759  jmp     loc_1400969DB
0x14007475e  mov     r10, cs:WPP_GLOBAL_Control
0x140074765  lea     rcx, WPP_GLOBAL_Control
0x14007476c  cmp     r10, rcx
0x14007476f  jz      loc_14007465A
0x140074775  mov     eax, [r10+2Ch]
0x140074779  test    al, 1
0x14007477b  jz      loc_14007465A
0x140074781  cmp     byte ptr [r10+29h], 1
0x140074786  jb      loc_14007465A
0x14007478c  jmp     loc_1400969D2
0x140074791  mov     r10, cs:WPP_GLOBAL_Control
0x140074798  lea     rcx, WPP_GLOBAL_Control
0x14007479f  cmp     r10, rcx
0x1400747a2  jz      loc_14007465A
0x1400747a8  mov     eax, [r10+2Ch]
0x1400747ac  test    al, 1
0x1400747ae  jz      loc_14007465A
0x1400747b4  cmp     byte ptr [r10+29h], 1
0x1400747b9  jb      loc_14007465A
0x1400747bf  mov     edx, 14h
0x1400747c4  jmp     loc_1400969D7
0x1400747c9  mov     r10, cs:WPP_GLOBAL_Control
0x1400747d0  lea     rcx, WPP_GLOBAL_Control
0x1400747d7  cmp     r10, rcx
0x1400747da  jz      loc_1400969F4
0x1400747e0  mov     eax, [r10+2Ch]
0x1400747e4  test    al, 1
0x1400747e6  jz      loc_1400969F4
0x1400747ec  cmp     byte ptr [r10+29h], 1
0x1400747f1  jb      loc_1400969F4
0x1400747f7  mov     rcx, [r10+18h]
0x1400747fb  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140074802  mov     edx, 15h
0x140074807  mov     r9, rsi
0x14007480a  call    WPP_SF_q
0x14007480f  nop
0x140074810  jmp     loc_1400969F4
0x140074815  mov     r10, cs:WPP_GLOBAL_Control
0x14007481c  lea     rcx, WPP_GLOBAL_Control
0x140074823  cmp     r10, rcx
0x140074826  jz      loc_14007465A
0x14007482c  mov     eax, [r10+2Ch]
0x140074830  test    al, 1
0x140074832  jz      loc_14007465A
0x140074838  cmp     byte ptr [r10+29h], 1
0x14007483d  jb      loc_14007465A
0x140074843  mov     edx, 13h
0x140074848  jmp     loc_1400969D7
0x1400969d2  mov     edx, 12h
0x1400969d7  mov     rcx, [r10+18h]
0x1400969db  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x1400969e2  mov     [rsp+0B8h+dwFlags], ebx
0x1400969e6  mov     r9, rsi
0x1400969e9  call    WPP_SF_qD
0x1400969ee  nop
0x1400969ef  jmp     loc_14007465A
0x1400969f4  mov     ebx, 0C0000022h
0x1400969f9  jmp     loc_14007465A
```
