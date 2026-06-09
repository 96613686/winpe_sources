# AfdTransmitPackets32

- ea: `0x140058458`
- end: `0x140058a98`
- name: `AfdTransmitPackets32`
- size: `1600`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, _BYTE *, _BYTE *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140057940`

## callees

- `0x14002fd5c`
- `0x14003f8b8`
- `0x14003fc3c`
- `0x1400445b8`
- `0x140058458`
- `0x1400726a0`
- `0x1400726d0`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x14005883e`
- `ntoskrnl!IoQueryFileInformation` at `0x14005883e`
- `ntoskrnl!ProbeForRead` at `0x140058628`
- `ntoskrnl!ProbeForRead` at `0x140058628`
- `ntoskrnl!ObfReferenceObject` at `0x140058748`
- `ntoskrnl!ObfReferenceObject` at `0x140058748`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058519`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058519`
- `ntoskrnl!IoFileObjectType` at `0x140058767`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005878d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005878d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058a60`
- `ntoskrnl!ExAllocatePool2` at `0x14005864e`
- `ntoskrnl!ExAllocatePool2` at `0x14005864e`

## pseudocode

```c
__int64 __fastcall AfdTransmitPackets32(__int64 a1, __int64 a2, __int64 *a3, _BYTE *a4, _BYTE *a5, unsigned int *a6)
{
  __int64 *v6; // r12
  __int64 v8; // rdi
  int *Pool2; // r15
  __int64 v10; // rsi
  char v11; // cl
  void *v12; // rdx
  __int64 TpInfo; // rax
  size_t v14; // r8
  unsigned int v15; // r9d
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  void *v18; // r10
  void *v19; // r11
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // r14
  int v23; // edx
  unsigned int v24; // r8d
  __int64 v25; // rax
  void *v26; // r13
  _QWORD *v27; // r11
  KPROCESSOR_MODE v28; // r9
  NTSTATUS v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned int v32; // ecx
  unsigned int v33; // r10d
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // r11
  unsigned int v36; // r8d
  unsigned int v37; // edx
  NTSTATUS v39; // [rsp+30h] [rbp-E8h]
  unsigned int v40; // [rsp+34h] [rbp-E4h]
  PVOID i; // [rsp+58h] [rbp-C0h]
  ULONG ReturnedLength; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int64 v45; // [rsp+68h] [rbp-B0h]
  void *v46; // [rsp+70h] [rbp-A8h]
  PVOID Object; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+80h] [rbp-98h]
  __int64 v49; // [rsp+88h] [rbp-90h]
  int *v50; // [rsp+90h] [rbp-88h]
  unsigned int *v51; // [rsp+98h] [rbp-80h]
  __int64 *v52; // [rsp+A0h] [rbp-78h]
  __int128 Address; // [rsp+A8h] [rbp-70h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-50h]

  v6 = a3;
  v48 = a1;
  v52 = a3;
  v51 = a6;
  v39 = 0;
  v8 = 0;
  v49 = 0;
  Address = 0;
  Pool2 = 0;
  v50 = 0;
  *a5 = 0;
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( *(_DWORD *)(a2 + 16) < 0x10u )
  {
    v39 = -1073741811;
    goto LABEL_85;
  }
  v46 = 0;
  v11 = *(_BYTE *)(a1 + 64);
  if ( v11 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  v12 = *(void **)(a2 + 32);
  if ( v11 )
    RtlCopyFromUser(&Address, v12, 0x10u);
  else
    RtlCopyVolatileMemory(&Address, v12, 0x10u);
  if ( (HIDWORD(Address) & 0xFFFFFFC8) != 0
    || (BYTE12(Address) & 0x30) == 0x30
    || *(_WORD *)v10 == 0xAFD1 && (BYTE12(Address) & 3) != 0 )
  {
    v39 = -1073741811;
  }
  else
  {
    if ( (_DWORD)Address && (unsigned int)(DWORD1(Address) - 1) <= 0xAAAAAA9 )
    {
      if ( (BYTE12(Address) & 0x30) == 0 )
        HIDWORD(Address) |= AfdDefaultTransmitWorker;
      if ( (*(_DWORD *)(v10 + 8) & 0x100) != 0 )
        TpInfo = AfdTliGetTpInfo(DWORD1(Address));
      else
        TpInfo = AfdTdiGetTpInfo(DWORD1(Address));
      v8 = TpInfo;
      v49 = TpInfo;
      if ( !TpInfo )
      {
        v39 = -1073741670;
        goto LABEL_85;
      }
      *(_DWORD *)(TpInfo + 76) = 0;
      *(_DWORD *)(TpInfo + 92) = DWORD2(Address);
      if ( DWORD2(Address) )
        *a5 = 1;
      else
        *(_DWORD *)(TpInfo + 92) = AfdTransmitIoLength;
      if ( *(_BYTE *)(a1 + 64) )
        ProbeForRead((volatile void *)(unsigned int)Address, 24LL * DWORD1(Address), 4u);
      Pool2 = (int *)ExAllocatePool2(97, 24LL * DWORD1(Address), 1180984897);
      v50 = Pool2;
      if ( !Pool2 )
      {
        v39 = -1073741670;
        goto LABEL_85;
      }
      v14 = 24LL * DWORD1(Address);
      if ( *(_BYTE *)(a1 + 64) )
        RtlCopyFromUser(Pool2, (void *)(unsigned int)Address, v14);
      else
        RtlCopyVolatileMemory(Pool2, (const void *)(unsigned int)Address, v14);
      v15 = 0;
      v40 = 0;
      v16 = 0;
      v45 = 0;
      *(_DWORD *)(v8 + 80) = 0;
      v17 = 0;
      v18 = 0;
      v46 = 0;
      v19 = 0;
      for ( i = 0; ; v19 = i )
      {
        v20 = *(unsigned int *)(v8 + 76);
        if ( (unsigned int)v20 >= DWORD1(Address) )
        {
          *(_DWORD *)(v48 + 128) = HIDWORD(Address);
          *v51 = v17;
          v6 = a3;
          goto LABEL_85;
        }
        v21 = 3 * v20;
        v22 = *(_QWORD *)(v8 + 64);
        v23 = Pool2[6 * v20];
        *(_DWORD *)(v22 + 24 * v20) = v23;
        if ( (v23 & 0xFFFFFFF8) != 0 || (v23 & 3) == 3 || (v23 & 3) == 0 )
        {
          v39 = -1073741811;
          v6 = a3;
          goto LABEL_85;
        }
        v24 = Pool2[6 * *(unsigned int *)(v8 + 76) + 1];
        *(_DWORD *)(v22 + 24 * v20 + 4) = v24;
        v25 = *(unsigned int *)(v8 + 76);
        if ( (v23 & 2) != 0 )
        {
          v26 = (void *)Pool2[6 * v25 + 4];
          if ( v18 && v26 == v18 )
          {
            ObfReferenceObject(v19);
            v27 = i;
          }
          else
          {
            v28 = *(_BYTE *)(v48 + 64);
            Object = 0;
            v29 = ObReferenceObjectByHandle(v26, 1u, (POBJECT_TYPE)IoFileObjectType, v28, &Object, 0);
            v27 = Object;
            i = Object;
            v39 = v29;
            if ( v29 < 0 )
            {
              *a4 = 1;
              v6 = a3;
              goto LABEL_85;
            }
          }
          *(_QWORD *)(v22 + 8 * v21 + 16) = v27;
          v30 = *(unsigned int *)(v8 + 76);
          *(_DWORD *)(v8 + 76) = v30 + 1;
          *(_QWORD *)(v22 + 8 * v21 + 8) = *(_QWORD *)&Pool2[6 * v30 + 2];
          --*(_DWORD *)(v8 + 76);
          if ( (v27[10] & 2) != 0 && !*(_QWORD *)(v22 + 8 * v21 + 8) )
            *(_QWORD *)(v22 + 8 * v21 + 8) = v27[13];
          v24 = *(_DWORD *)(v22 + 8 * v21 + 4);
          if ( v24 )
          {
            if ( *(__int64 *)(v22 + 8 * v21 + 8) < 0 )
            {
              ++*(_DWORD *)(v8 + 76);
              v39 = -1073741811;
              *a4 = 1;
              v6 = a3;
              goto LABEL_85;
            }
          }
          else
          {
            FileInformation = 0;
            v55 = 0;
            ReturnedLength = 0;
            v39 = IoQueryFileInformation(
                    *(PFILE_OBJECT *)(v22 + 8 * v21 + 16),
                    FileStandardInformation,
                    0x18u,
                    &FileInformation,
                    &ReturnedLength);
            if ( v39 < 0 )
            {
              ++*(_DWORD *)(v8 + 76);
              *a4 = 1;
              v6 = a3;
              goto LABEL_85;
            }
            v31 = *(_QWORD *)(v22 + 8 * v21 + 8);
            if ( v31 < 0
              || v31 > *((__int64 *)&FileInformation + 1)
              || (v24 = DWORD2(FileInformation) - v31, *((_QWORD *)&FileInformation + 1) - v31 > 0x7FFFFFFF) )
            {
              ++*(_DWORD *)(v8 + 76);
              v39 = -1073741811;
              *a4 = 1;
              v6 = a3;
              goto LABEL_85;
            }
            *(_DWORD *)(v22 + 8 * v21 + 4) = v24;
          }
          v46 = v26;
          v23 = *(_DWORD *)(v22 + 8 * v21);
          v16 = v45;
        }
        else
        {
          *(_QWORD *)(v22 + 8 * v21 + 8) = (unsigned int)Pool2[6 * v25 + 2];
          if ( v24 <= AfdTPacketsCopyThreshold )
          {
            v32 = v40;
            if ( v15 && (v15 += v24, v15 <= AfdTPacketsCopyThreshold) && v15 + v40 <= *(_DWORD *)(v8 + 92) )
              *(_DWORD *)(v22 + 8 * v21 - 24) |= 0x40000000u;
            else
              v15 = v24;
            if ( (v23 & 4) == 0 )
              goto LABEL_67;
            goto LABEL_58;
          }
        }
        v32 = v40;
LABEL_58:
        v15 = 0;
        if ( (v23 & 4) != 0 )
        {
          v40 = 0;
          goto LABEL_68;
        }
LABEL_67:
        v40 = (v24 + v32) % *(_DWORD *)(v8 + 92);
LABEL_68:
        v33 = *(_DWORD *)(v8 + 80);
        if ( v33 != -1 )
        {
          v34 = v24 + v16;
          v35 = *(unsigned int *)(v8 + 92);
          v36 = v16 / (unsigned int)v35 + v33;
          v37 = (unsigned int)v34 % *(_DWORD *)(v8 + 92);
          v16 = v37;
          v45 = (unsigned int)v34 % v35;
          if ( v34 <= v35 )
          {
            if ( v17 < v37 )
              v17 = v37;
          }
          else
          {
            v17 = v35;
          }
          if ( v36 < v33 || v36 == -1 )
          {
            *(_DWORD *)(v8 + 80) = -1;
          }
          else
          {
            *(_DWORD *)(v8 + 80) = v36;
            if ( (*(_DWORD *)(v22 + 8 * v21) & 4) != 0 && (v37 || !*(_DWORD *)(v22 + 8 * v21 + 4)) )
            {
              *(_DWORD *)(v8 + 80) = v36 + 1;
              v16 = 0;
              v45 = 0;
            }
          }
        }
        ++*(_DWORD *)(v8 + 76);
        v18 = v46;
      }
    }
    v39 = -1073741811;
  }
LABEL_85:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x46646641u);
  *v6 = v8;
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x140058458  mov     r11, rsp
0x14005845b  push    rbx
0x14005845c  push    rsi
0x14005845d  push    rdi
0x14005845e  push    r12
0x140058460  push    r13
0x140058462  push    r14
0x140058464  push    r15
0x140058466  sub     rsp, 0E0h
0x14005846d  mov     rax, cs:__security_cookie
0x140058474  xor     rax, rsp
0x140058477  mov     [rsp+118h+var_48], rax
0x14005847f  mov     [rsp+118h+var_C8], r9
0x140058484  mov     r12, r8
0x140058487  mov     [rsp+118h+var_D8], r8
0x14005848c  mov     r13, rcx
0x14005848f  mov     [rsp+118h+var_98], rcx
0x140058497  mov     [rsp+118h+var_78], r8
0x14005849f  mov     r14, [rsp+118h+arg_20]
0x1400584a7  mov     rax, [rsp+118h+arg_28]
0x1400584af  mov     [rsp+118h+var_80], rax
0x1400584b7  xor     ebx, ebx
0x1400584b9  mov     [rsp+118h+var_E8], ebx
0x1400584bd  mov     edi, ebx
0x1400584bf  mov     [r11-90h], rbx
0x1400584c6  xorps   xmm0, xmm0
0x1400584c9  movups  xmmword ptr [r11-70h], xmm0
0x1400584ce  mov     r15d, ebx
0x1400584d1  mov     [r11-88h], rbx
0x1400584d8  mov     [r14], bl
0x1400584db  mov     rax, [rdx+30h]
0x1400584df  mov     rsi, [rax+18h]
0x1400584e3  lea     r8d, [rbx+10h]
0x1400584e7  cmp     [rdx+10h], r8d
0x1400584eb  jnb     short loc_1400584FA
0x1400584ed  mov     [rsp+118h+var_E8], 0C000000Dh
0x1400584f5  jmp     loc_140058A53
0x1400584fa  mov     [rsp+118h+var_C0], rbx
0x1400584ff  mov     [rsp+118h+var_A8], rbx
0x140058504  mov     [rsp+118h+var_E0], ebx
0x140058508  mov     [rsp+118h+var_DC], ebx
0x14005850c  mov     cl, [rcx+40h]
0x14005850f  test    cl, cl
0x140058511  jz      short loc_140058526
0x140058513  test    byte ptr [rdx+20h], 3
0x140058517  jz      short loc_140058526
0x140058519  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140058520  nop     dword ptr [rax+rax+00h]
0x140058525  int     3; Trap to Debugger
0x140058526  mov     rdx, [rdx+20h]; Src
0x14005852a  test    cl, cl
0x14005852c  lea     rcx, [rsp+118h+Address]; void *
0x140058534  jz      short loc_14005853D
0x140058536  call    RtlCopyFromUser
0x14005853b  jmp     short loc_140058542
0x14005853d  call    RtlCopyVolatileMemory
0x140058542  mov     ecx, [rsp+118h+var_64]
0x140058549  test    ecx, 0FFFFFFC8h
0x14005854f  jnz     loc_140058A31
0x140058555  mov     edx, ecx
0x140058557  and     edx, 30h
0x14005855a  cmp     edx, 30h ; '0'
0x14005855d  jz      loc_140058A31
0x140058563  mov     eax, 0AFD1h
0x140058568  cmp     [rsi], ax
0x14005856b  jnz     short loc_140058576
0x14005856d  test    cl, 3
0x140058570  jnz     loc_140058A31
0x140058576  cmp     dword ptr [rsp+118h+Address], ebx
0x14005857d  jz      loc_140058A27
0x140058583  mov     eax, dword ptr [rsp+118h+Address+4]
0x14005858a  dec     eax
0x14005858c  cmp     eax, 0AAAAAA9h
0x140058591  ja      loc_140058A27
0x140058597  test    edx, edx
0x140058599  jnz     short loc_1400585A8
0x14005859b  or      ecx, cs:AfdDefaultTransmitWorker
0x1400585a1  mov     [rsp+118h+var_64], ecx
0x1400585a8  mov     eax, [rsi+8]
0x1400585ab  mov     ecx, dword ptr [rsp+118h+Address+4]
0x1400585b2  bt      eax, 8
0x1400585b6  jnb     short loc_1400585BF
0x1400585b8  call    AfdTliGetTpInfo
0x1400585bd  jmp     short loc_1400585C4
0x1400585bf  call    AfdTdiGetTpInfo
0x1400585c4  mov     rdi, rax
0x1400585c7  mov     [rsp+118h+var_90], rax
0x1400585cf  test    rax, rax
0x1400585d2  jnz     short loc_1400585E1
0x1400585d4  mov     [rsp+118h+var_E8], 0C000009Ah
0x1400585dc  jmp     loc_140058A53
0x1400585e1  mov     [rdi+4Ch], ebx
0x1400585e4  mov     eax, [rsp+118h+var_68]
0x1400585eb  mov     [rdi+5Ch], eax
0x1400585ee  cmp     [rsp+118h+var_68], ebx
0x1400585f5  jnz     short loc_140058602
0x1400585f7  mov     eax, cs:AfdTransmitIoLength
0x1400585fd  mov     [rdi+5Ch], eax
0x140058600  jmp     short loc_140058606
0x140058602  mov     byte ptr [r14], 1
0x140058606  cmp     [r13+40h], bl
0x14005860a  jz      short loc_140058634
0x14005860c  mov     eax, dword ptr [rsp+118h+Address+4]
0x140058613  lea     rdx, [rax+rax*2]
0x140058617  shl     rdx, 3; Length
0x14005861b  mov     ecx, dword ptr [rsp+118h+Address]; Address
0x140058622  mov     r8d, 4; Alignment
0x140058628  call    cs:__imp_ProbeForRead
0x14005862f  nop     dword ptr [rax+rax+00h]
0x140058634  mov     eax, dword ptr [rsp+118h+Address+4]
0x14005863b  lea     rdx, [rax+rax*2]
0x14005863f  shl     rdx, 3
0x140058643  mov     ecx, 61h ; 'a'
0x140058648  mov     r8d, 46646641h
0x14005864e  call    cs:__imp_ExAllocatePool2
0x140058655  nop     dword ptr [rax+rax+00h]
0x14005865a  mov     r15, rax
0x14005865d  mov     [rsp+118h+var_88], rax
0x140058665  test    rax, rax
0x140058668  jnz     short loc_140058677
0x14005866a  mov     [rsp+118h+var_E8], 0C000009Ah
0x140058672  jmp     loc_140058A53
0x140058677  mov     edx, dword ptr [rsp+118h+Address]; Src
0x14005867e  mov     eax, dword ptr [rsp+118h+Address+4]
0x140058685  lea     r8, [rax+rax*2]
0x140058689  shl     r8, 3; Size
0x14005868d  mov     rcx, r15; void *
0x140058690  cmp     [r13+40h], bl
0x140058694  jz      short loc_14005869D
0x140058696  call    RtlCopyFromUser
0x14005869b  jmp     short loc_1400586A2
0x14005869d  call    RtlCopyVolatileMemory
0x1400586a2  mov     r9d, ebx
0x1400586a5  mov     [rsp+118h+var_E0], ebx
0x1400586a9  mov     [rsp+118h+var_E4], ebx
0x1400586ad  mov     r13d, ebx
0x1400586b0  mov     [rsp+118h+var_B0], r13
0x1400586b5  mov     [rsp+118h+var_DC], ebx
0x1400586b9  mov     [rdi+50h], ebx
0x1400586bc  mov     r12d, ebx
0x1400586bf  mov     [rsp+118h+var_D0], ebx
0x1400586c3  mov     r10, rbx
0x1400586c6  mov     [rsp+118h+var_A8], rbx
0x1400586cb  mov     r11, rbx
0x1400586ce  mov     [rsp+118h+var_C0], rbx
0x1400586d3  mov     eax, [rdi+4Ch]
0x1400586d6  cmp     eax, dword ptr [rsp+118h+Address+4]
0x1400586dd  jnb     loc_140058A00
0x1400586e3  lea     rsi, [rax+rax*2]
0x1400586e7  mov     r14, [rdi+40h]
0x1400586eb  mov     edx, [r15+rsi*8]
0x1400586ef  mov     [r14+rsi*8], edx
0x1400586f3  test    edx, 0FFFFFFF8h
0x1400586f9  jnz     loc_1400589F1
0x1400586ff  mov     eax, edx
0x140058701  and     eax, 3
0x140058704  cmp     eax, 3
0x140058707  jz      loc_1400589F1
0x14005870d  test    eax, eax
0x14005870f  jz      loc_1400589F1
0x140058715  mov     eax, [rdi+4Ch]
0x140058718  lea     rcx, [rax+rax*2]
0x14005871c  mov     r8d, [r15+rcx*8+4]
0x140058721  mov     [r14+rsi*8+4], r8d
0x140058726  mov     eax, [rdi+4Ch]
0x140058729  lea     rcx, [rax+rax*2]
0x14005872d  test    dl, 2
0x140058730  jz      loc_1400588FA
0x140058736  movsxd  r13, dword ptr [r15+rcx*8+10h]
0x14005873b  test    r10, r10
0x14005873e  jz      short loc_14005875B
0x140058740  cmp     r13, r10
0x140058743  jnz     short loc_14005875B
0x140058745  mov     rcx, r11; Object
0x140058748  call    cs:__imp_ObfReferenceObject
0x14005874f  nop     dword ptr [rax+rax+00h]
0x140058754  mov     r11, [rsp+118h+var_C0]
0x140058759  jmp     short loc_1400587C1
0x14005875b  mov     rax, [rsp+118h+var_98]
0x140058763  mov     r9b, [rax+40h]; AccessMode
0x140058767  mov     rax, cs:__imp_IoFileObjectType
0x14005876e  mov     r8, [rax]; ObjectType
0x140058771  mov     [rsp+118h+var_A0], rbx
0x140058776  mov     [rsp+118h+HandleInformation], rbx; HandleInformation
0x14005877b  lea     rax, [rsp+118h+var_A0]
0x140058780  mov     [rsp+118h+Object], rax; Object
0x140058785  mov     edx, 1; DesiredAccess
0x14005878a  mov     rcx, r13; Handle
0x14005878d  call    cs:__imp_ObReferenceObjectByHandle
0x140058794  nop     dword ptr [rax+rax+00h]
0x140058799  mov     r11, [rsp+118h+var_A0]
0x14005879e  mov     [rsp+118h+var_C0], r11
0x1400587a3  mov     [rsp+118h+var_E8], eax
0x1400587a7  mov     eax, [rsp+118h+var_E8]
0x1400587ab  test    eax, eax
0x1400587ad  jns     short loc_1400587C1
0x1400587af  mov     rax, [rsp+118h+var_C8]
0x1400587b4  mov     byte ptr [rax], 1
0x1400587b7  mov     r12, [rsp+118h+var_D8]
0x1400587bc  jmp     loc_140058A53
0x1400587c1  mov     [r14+rsi*8+10h], r11
0x1400587c6  mov     ecx, [rdi+4Ch]
0x1400587c9  lea     eax, [rcx+1]
0x1400587cc  mov     [rdi+4Ch], eax
0x1400587cf  lea     rcx, [rcx+rcx*2]
0x1400587d3  mov     rax, [r15+rcx*8+8]
0x1400587d8  mov     [r14+rsi*8+8], rax
0x1400587dd  dec     dword ptr [rdi+4Ch]
0x1400587e0  mov     eax, [r11+50h]
0x1400587e4  test    al, 2
0x1400587e6  jz      short loc_1400587F8
0x1400587e8  cmp     [r14+rsi*8+8], rbx
0x1400587ed  jnz     short loc_1400587F8
0x1400587ef  mov     rax, [r11+68h]
0x1400587f3  mov     [r14+rsi*8+8], rax
0x1400587f8  mov     r8d, [r14+rsi*8+4]
0x1400587fd  test    r8d, r8d
0x140058800  jnz     loc_1400588B2
0x140058806  xorps   xmm0, xmm0
0x140058809  xor     eax, eax
0x14005880b  movups  [rsp+118h+FileInformation], xmm0
0x140058813  mov     [rsp+118h+var_50], rax
0x14005881b  mov     [rsp+118h+ReturnedLength], ebx
0x14005881f  lea     rax, [rsp+118h+ReturnedLength]
0x140058824  mov     [rsp+118h+Object], rax; ReturnedLength
0x140058829  lea     r9, [rsp+118h+FileInformation]; FileInformation
0x140058831  lea     edx, [r8+5]; FileInformationClass
0x140058835  lea     r8d, [rdx+13h]; Length
0x140058839  mov     rcx, [r14+rsi*8+10h]; FileObject
0x14005883e  call    cs:__imp_IoQueryFileInformation
0x140058845  nop     dword ptr [rax+rax+00h]
0x14005884a  mov     [rsp+118h+var_E8], eax
0x14005884e  mov     eax, [rsp+118h+var_E8]
0x140058852  test    eax, eax
0x140058854  jns     short loc_14005886B
0x140058856  inc     dword ptr [rdi+4Ch]
0x140058859  mov     rax, [rsp+118h+var_C8]
0x14005885e  mov     byte ptr [rax], 1
0x140058861  mov     r12, [rsp+118h+var_D8]
0x140058866  jmp     loc_140058A53
0x14005886b  mov     rax, [r14+rsi*8+8]
0x140058870  test    rax, rax
0x140058873  js      short loc_140058895
0x140058875  mov     r8, qword ptr [rsp+118h+FileInformation+8]
0x14005887d  cmp     rax, r8
0x140058880  jg      short loc_140058895
0x140058882  sub     r8, rax
0x140058885  cmp     r8, 7FFFFFFFh
0x14005888c  jg      short loc_140058895
0x14005888e  mov     [r14+rsi*8+4], r8d
0x140058893  jmp     short loc_1400588D6
0x140058895  inc     dword ptr [rdi+4Ch]
0x140058898  mov     [rsp+118h+var_E8], 0C000000Dh
0x1400588a0  mov     rax, [rsp+118h+var_C8]
0x1400588a5  mov     byte ptr [rax], 1
0x1400588a8  mov     r12, [rsp+118h+var_D8]
0x1400588ad  jmp     loc_140058A53
0x1400588b2  cmp     [r14+rsi*8+8], rbx
0x1400588b7  jge     short loc_1400588D6
0x1400588b9  inc     dword ptr [rdi+4Ch]
0x1400588bc  mov     [rsp+118h+var_E8], 0C000000Dh
0x1400588c4  mov     rax, [rsp+118h+var_C8]
0x1400588c9  mov     byte ptr [rax], 1
0x1400588cc  mov     r12, [rsp+118h+var_D8]
0x1400588d1  jmp     loc_140058A53
0x1400588d6  mov     [rsp+118h+var_A8], r13
0x1400588db  mov     edx, [r14+rsi*8]
0x1400588df  mov     r13, [rsp+118h+var_B0]
0x1400588e4  mov     ecx, [rsp+118h+var_E4]
0x1400588e8  mov     r9d, ebx
0x1400588eb  mov     [rsp+118h+var_E0], ebx
0x1400588ef  test    dl, 4
0x1400588f2  jz      short loc_140058944
0x1400588f4  mov     [rsp+118h+var_E4], ebx
0x1400588f8  jmp     short loc_140058951
0x1400588fa  mov     eax, [r15+rcx*8+8]
0x1400588ff  mov     [r14+rsi*8+8], rax
0x140058904  mov     eax, cs:AfdTPacketsCopyThreshold
0x14005890a  cmp     r8d, eax
0x14005890d  ja      short loc_1400588E4
0x14005890f  mov     ecx, [rsp+118h+var_E4]
0x140058913  test    r9d, r9d
0x140058916  jz      short loc_140058937
0x140058918  add     r9d, r8d
0x14005891b  mov     [rsp+118h+var_E0], r9d
0x140058920  cmp     r9d, eax
0x140058923  ja      short loc_140058937
0x140058925  lea     eax, [r9+rcx]
0x140058929  cmp     eax, [rdi+5Ch]
0x14005892c  ja      short loc_140058937
0x14005892e  bts     dword ptr [r14+rsi*8-18h], 1Eh
0x140058935  jmp     short loc_14005893F
0x140058937  mov     r9d, r8d
0x14005893a  mov     [rsp+118h+var_E0], r8d
0x14005893f  test    dl, 4
0x140058942  jnz     short loc_1400588E8
0x140058944  lea     eax, [r8+rcx]
0x140058948  xor     edx, edx
0x14005894a  div     dword ptr [rdi+5Ch]
0x14005894d  mov     [rsp+118h+var_E4], edx
  ... truncated ...
```
