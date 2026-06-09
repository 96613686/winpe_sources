# VidIoControlPreProcess

- ea: `0x140033bc0`
- end: `0x14003406a`
- name: `VidIoControlPreProcess`
- size: `1194`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007880`

## callees

- `0x1400100c0`
- `0x140021c60`
- `0x140023e54`
- `0x140033bc0`
- `0x140035708`
- `0x14003782c`
- `0x140038040`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003403b`
- `ntoskrnl!IofCompleteRequest` at `0x14003403b`
- `ntoskrnl!EtwWriteTransfer` at `0x140033e2c`
- `ntoskrnl!EtwWriteTransfer` at `0x140033e2c`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033e44`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033e44`
- `HAL!KeQueryPerformanceCounter` at `0x140033c4a`
- `HAL!KeQueryPerformanceCounter` at `0x140033f02`
- `HAL!KeQueryPerformanceCounter` at `0x140033fc7`
- `HAL!KeQueryPerformanceCounter` at `0x140033c4a`
- `HAL!KeQueryPerformanceCounter` at `0x140033f02`
- `HAL!KeQueryPerformanceCounter` at `0x140033fc7`

## pseudocode

```c
__int64 __fastcall VidIoControlPreProcess(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  wchar_t *v3; // rax
  unsigned int LowPart; // esi
  unsigned int v6; // ebx
  unsigned int Options; // r12d
  struct _IRP *MasterIrp; // r13
  unsigned int Length; // ebx
  __int64 v10; // rdi
  int v11; // edx
  int v12; // ecx
  unsigned __int16 v13; // r15
  unsigned __int64 v14; // rdi
  int v15; // edx
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned __int64 v18; // rax
  unsigned int v19; // eax
  unsigned __int64 v20; // rax
  unsigned int pullResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-ACh] BYREF
  NTSTRSAFE_PWSTR pszDest; // [rsp+58h] [rbp-A8h]
  int v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+88h] [rbp-78h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  void *v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+BCh] [rbp-44h]
  const char *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  const char *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  unsigned int *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  int *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  _DWORD *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  __int64 v47; // [rsp+120h] [rbp+20h]
  _DWORD v48[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  int *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  pullResult = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( (LowPart & 3) != 0 )
  {
    v6 = -1073741808;
LABEL_36:
    a2->IoStatus.Information = pullResult;
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
    return v6;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options )
    MasterIrp = a2->AssociatedIrp.MasterIrp;
  else
    MasterIrp = 0;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v23 = Length;
  if ( Length )
    v3 = (wchar_t *)a2->AssociatedIrp.MasterIrp;
  pszDest = v3;
  *(_QWORD *)v25 = CurrentStackLocation->FileObject;
  v29 = 0;
  PerformanceFrequency.QuadPart = 0;
  v10 = *(_QWORD *)(*(_QWORD *)v25 + 24LL);
  *(LARGE_INTEGER *)&v29 = KeQueryPerformanceCounter(0);
  v13 = (LowPart >> 2) & 0x3FF;
  v14 = v10 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( !v14 )
  {
    v19 = VidIoControlDriver(
            (_DWORD)VidDeviceExtension,
            v25[0],
            (_DWORD)MasterIrp,
            Options,
            (__int64)pszDest,
            Length,
            LowPart,
            (__int64)&pullResult);
LABEL_33:
    v6 = v19;
    if ( v13 < 0x2Au )
    {
      *((LARGE_INTEGER *)&v29 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
      v20 = 1000000LL * (*((_QWORD *)&v29 + 1) - (_QWORD)v29) / PerformanceFrequency.QuadPart;
      _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45)
                                                        + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 47)));
      _InterlockedAdd64(
        (volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 48)),
        v20);
    }
    goto LABEL_35;
  }
  if ( *(_DWORD *)v14 == 544176197 )
  {
    v19 = VidExoIoControlDriver(
            v12,
            v11,
            (_DWORD)MasterIrp,
            Options,
            (__int64)pszDest,
            Length,
            LowPart,
            (__int64)&pullResult);
    goto LABEL_33;
  }
  if ( *(_DWORD *)v14 != 1853125200 )
  {
    v6 = -1073741816;
    goto LABEL_36;
  }
  v15 = *(_DWORD *)(v14 + 48);
  if ( v15 == 1 || LowPart == 2232784 )
  {
    v16 = *(_QWORD *)(v14 + 10240);
    if ( v16 == PsGetCurrentProcess() || LowPart == 2232419 || LowPart == 2232563 )
    {
      if ( (*(_DWORD *)(v14 + 16) & 0x8000LL) != 0 )
        v17 = VidExoIoControlPartition(
                v14,
                (int)a2,
                v25[0],
                (int)MasterIrp,
                Options,
                pszDest,
                v23,
                LowPart,
                (ULONGLONG)&pullResult);
      else
        v17 = VidIoControlPartition(
                (_QWORD *)v14,
                (__int64)a2,
                *(__int64 *)v25,
                MasterIrp,
                Options,
                pszDest,
                v23,
                LowPart,
                &pullResult);
      v6 = v17;
      if ( v13 < 0xD4u )
      {
        *((LARGE_INTEGER *)&v29 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
        v18 = 1000000LL * (*((_QWORD *)&v29 + 1) - (_QWORD)v29) / PerformanceFrequency.QuadPart;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v14 + 1528)
                                                          + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 292)));
        _InterlockedAdd64(
          (volatile signed __int64 *)(*(_QWORD *)(v14 + 1528) + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 293)),
          v18);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_9b7999e5d274371e1b0cbda42c5f46a6_Traceguids);
      }
      v6 = -1073741790;
    }
  }
  else
  {
    v6 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2
      && (qword_140065120 & 0x100) != 0
      && (qword_140065128 & 0x100) == qword_140065128 )
    {
      v36 = 31;
      v35 = "VidIoControlPartitionIsAllowed";
      v38 = 41;
      v37 = "onecore\\vm\\vid\\sys\\driver\\vidiocontrol.c";
      v48[1] = 0;
      v39 = &v23;
      v25[0] = v15;
      v41 = &v26;
      v23 = 8089;
      v43 = v14 + 656;
      v40 = 4;
      v45 = v48;
      v47 = *(_QWORD *)(v14 + 128);
      v48[0] = *(unsigned __int16 *)(v14 + 120);
      v27 = *(_QWORD *)(v14 + 648);
      v49 = &v27;
      v51 = v25;
      UserData.Ptr = (ULONGLONG)off_140065118;
      *(_DWORD *)&EventDescriptor.Level = 2;
      v26 = -1073741811;
      v42 = 4;
      v44 = 16;
      v46 = 2;
      v50 = 8;
      v52 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 256;
      UserData.Size = *(unsigned __int16 *)off_140065118;
      v32 = &unk_14005C6C0;
      UserData.Reserved = 2;
      v33 = 110;
      v34 = 1;
      LODWORD(pszDest) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
    }
  }
LABEL_35:
  if ( v6 != 259 )
    goto LABEL_36;
  return v6;
}

```

## disassembly

```asm
0x140033bc0  push    rbp
0x140033bc2  push    rbx
0x140033bc3  push    rsi
0x140033bc4  push    rdi
0x140033bc5  push    r12
0x140033bc7  push    r13
0x140033bc9  push    r14
0x140033bcb  push    r15
0x140033bcd  lea     rbp, [rsp-68h]
0x140033bd2  sub     rsp, 168h
0x140033bd9  mov     rax, cs:__security_cookie
0x140033be0  xor     rax, rsp
0x140033be3  mov     [rbp+0A0h+var_50], rax
0x140033be7  mov     rcx, [rdx+0B8h]
0x140033bee  xor     eax, eax
0x140033bf0  mov     dword ptr [rsp+1A0h+var_150], eax
0x140033bf4  mov     r14, rdx
0x140033bf7  mov     esi, [rcx+18h]
0x140033bfa  test    sil, 3
0x140033bfe  jz      short loc_140033C0A
0x140033c00  mov     ebx, 0C0000010h
0x140033c05  jmp     loc_14003402A
0x140033c0a  mov     r12d, [rcx+10h]
0x140033c0e  test    r12d, r12d
0x140033c11  jz      short loc_140033C19
0x140033c13  mov     r13, [rdx+18h]
0x140033c17  jmp     short loc_140033C1C
0x140033c19  mov     r13, rax
0x140033c1c  mov     ebx, [rcx+8]
0x140033c1f  mov     dword ptr [rsp+1A0h+var_150+4], ebx
0x140033c23  test    ebx, ebx
0x140033c25  jz      short loc_140033C2B
0x140033c27  mov     rax, [rdx+18h]
0x140033c2b  mov     [rsp+1A0h+pszDest], rax
0x140033c30  xorps   xmm0, xmm0
0x140033c33  mov     rax, [rcx+30h]
0x140033c37  xor     ecx, ecx; PerformanceFrequency
0x140033c39  mov     qword ptr [rsp+1A0h+var_140], rax
0x140033c3e  movups  [rbp+0A0h+var_118], xmm0
0x140033c42  mov     qword ptr [rbp+0A0h+PerformanceFrequency], rcx
0x140033c46  mov     rdi, [rax+18h]
0x140033c4a  call    cs:__imp_KeQueryPerformanceCounter
0x140033c51  nop     dword ptr [rax+rax+00h]
0x140033c56  mov     r15d, esi
0x140033c59  mov     qword ptr [rbp+0A0h+var_118], rax
0x140033c5d  shr     r15d, 2
0x140033c61  mov     eax, 3FFh
0x140033c66  and     r15w, ax
0x140033c6a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140033c6e  jz      loc_140033F87
0x140033c74  mov     eax, [rdi]
0x140033c76  cmp     eax, 206F7845h
0x140033c7b  jz      loc_140033F5E
0x140033c81  cmp     eax, 6E747250h
0x140033c86  jnz     loc_140033F54
0x140033c8c  mov     edx, [rdi+30h]
0x140033c8f  cmp     edx, 1
0x140033c92  jz      loc_140033E3D
0x140033c98  cmp     esi, 2211D0h
0x140033c9e  jz      loc_140033E3D
0x140033ca4  mov     eax, cs:dword_140065110
0x140033caa  mov     ebx, 0C000000Dh
0x140033caf  cmp     eax, 2
0x140033cb2  jbe     loc_140034022
0x140033cb8  mov     rcx, cs:qword_140065128
0x140033cbf  mov     rax, cs:qword_140065120
0x140033cc6  bt      rax, 8
0x140033ccb  jnb     loc_140034022
0x140033cd1  mov     rax, rcx
0x140033cd4  and     eax, 100h
0x140033cd9  cmp     rax, rcx
0x140033cdc  jnz     loc_140034022
0x140033ce2  lea     rax, aVidiocontrolpa; "VidIoControlPartitionIsAllowed"
0x140033ce9  mov     [rbp+0A0h+var_D8], 1Fh
0x140033cf1  mov     [rbp+0A0h+var_E0], rax
0x140033cf5  xor     ecx, ecx
0x140033cf7  lea     rax, aOnecoreVmVidSy_31; "onecore\\vm\\vid\\sys\\driver\\vidiocon"...
0x140033cfe  mov     [rbp+0A0h+var_C8], 29h ; ')'
0x140033d06  mov     [rbp+0A0h+var_D0], rax
0x140033d0a  mov     [rbp+0A0h+var_74], ecx
0x140033d0d  lea     rax, [rsp+1A0h+var_150+4]
0x140033d12  mov     [rbp+0A0h+var_C0], rax
0x140033d16  xor     r9d, r9d; RelatedActivityId
0x140033d19  mov     [rsp+1A0h+var_140], edx
0x140033d1d  lea     rax, [rsp+1A0h+var_138]
0x140033d22  mov     [rbp+0A0h+var_B0], rax
0x140033d26  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140033d2b  mov     dword ptr [rsp+1A0h+var_150+4], 1F99h
0x140033d33  lea     rax, [rdi+290h]
0x140033d3a  mov     [rbp+0A0h+var_A0], rax
0x140033d3e  xor     r8d, r8d; ActivityId
0x140033d41  mov     [rbp+0A0h+var_B8], 4
0x140033d49  lea     rax, [rbp+0A0h+var_78]
0x140033d4d  mov     [rbp+0A0h+var_90], rax
0x140033d51  mov     rax, [rdi+80h]
0x140033d58  mov     [rbp+0A0h+var_80], rax
0x140033d5c  movzx   eax, word ptr [rdi+78h]
0x140033d60  mov     [rbp+0A0h+var_78], eax
0x140033d63  mov     rax, [rdi+288h]
0x140033d6a  mov     [rsp+1A0h+var_130], rax
0x140033d6f  lea     rax, [rsp+1A0h+var_130]
0x140033d74  mov     [rbp+0A0h+var_70], rax
0x140033d78  lea     rax, [rsp+1A0h+var_140]
0x140033d7d  mov     [rbp+0A0h+var_60], rax
0x140033d81  mov     rax, cs:qword_14005C6B6
0x140033d88  movzx   ecx, ax
0x140033d8b  mov     rax, cs:off_140065118
0x140033d92  mov     [rbp+0A0h+var_100.Ptr], rax
0x140033d96  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], ecx
0x140033d9a  lea     rcx, _TraceLoggingMetadata
0x140033da1  mov     [rsp+1A0h+var_138], ebx
0x140033da5  mov     [rbp+0A0h+var_A8], 4
0x140033dad  mov     [rbp+0A0h+var_98], 10h
0x140033db5  mov     [rbp+0A0h+var_88], 2
0x140033dbd  mov     [rbp+0A0h+var_68], 8
0x140033dc5  mov     [rbp+0A0h+var_58], 4
0x140033dcd  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], 0B000000h
0x140033dd5  mov     [rbp+0A0h+EventDescriptor.Keyword], 100h
0x140033ddd  movzx   eax, word ptr [rax]
0x140033de0  mov     [rbp+0A0h+var_100.Size], eax
0x140033de3  lea     rax, unk_14005C6C0
0x140033dea  mov     [rbp+0A0h+var_F0], rax
0x140033dee  lea     rax, _TraceLoggingMetadataEnd
0x140033df5  sub     eax, ecx
0x140033df7  mov     dword ptr [rbp+0A0h+var_100.0Ch], 2
0x140033dfe  mov     [rbp+0A0h+var_E8], 6Eh ; 'n'
0x140033e05  mov     [rbp+0A0h+var_E4], 1
0x140033e0c  mov     dword ptr [rsp+1A0h+pszDest], eax
0x140033e10  mov     eax, dword ptr [rsp+1A0h+pszDest]
0x140033e14  mov     rcx, cs:RegHandle; RegHandle
0x140033e1b  lea     rax, [rbp+0A0h+var_100]
0x140033e1f  mov     [rsp+1A0h+UserData], rax; UserData
0x140033e24  mov     [rsp+1A0h+UserDataCount], 0Bh; UserDataCount
0x140033e2c  call    cs:__imp_EtwWriteTransfer
0x140033e33  nop     dword ptr [rax+rax+00h]
0x140033e38  jmp     loc_140034022
0x140033e3d  mov     rbx, [rdi+2800h]
0x140033e44  call    cs:__imp_PsGetCurrentProcess
0x140033e4b  nop     dword ptr [rax+rax+00h]
0x140033e50  cmp     rbx, rax
0x140033e53  jz      short loc_140033EA4
0x140033e55  cmp     esi, 221063h
0x140033e5b  jz      short loc_140033EA4
0x140033e5d  cmp     esi, 2210F3h
0x140033e63  jz      short loc_140033EA4
0x140033e65  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e6c  lea     rax, WPP_GLOBAL_Control
0x140033e73  cmp     rcx, rax
0x140033e76  jz      short loc_140033E9A
0x140033e78  mov     eax, [rcx+2Ch]
0x140033e7b  test    al, 2
0x140033e7d  jz      short loc_140033E9A
0x140033e7f  cmp     byte ptr [rcx+29h], 2
0x140033e83  jb      short loc_140033E9A
0x140033e85  mov     rcx, [rcx+18h]
0x140033e89  lea     r8, WPP_9b7999e5d274371e1b0cbda42c5f46a6_Traceguids
0x140033e90  mov     edx, 0Dh
0x140033e95  call    WPP_SF_
0x140033e9a  mov     ebx, 0C0000022h
0x140033e9f  jmp     loc_140034022
0x140033ea4  mov     eax, [rdi+10h]
0x140033ea7  mov     r9, r13; int
0x140033eaa  mov     r8, qword ptr [rsp+1A0h+var_140]; int
0x140033eaf  bt      rax, 0Fh
0x140033eb4  lea     rax, [rsp+1A0h+var_150]
0x140033eb9  mov     rdx, r14; int
0x140033ebc  mov     [rsp+1A0h+pullResult], rax; pullResult
0x140033ec1  mov     rcx, rdi; int
0x140033ec4  mov     eax, dword ptr [rsp+1A0h+var_150+4]
0x140033ec8  mov     [rsp+1A0h+var_168], esi; int
0x140033ecc  mov     [rsp+1A0h+var_170], eax; int
0x140033ed0  mov     rax, [rsp+1A0h+pszDest]
0x140033ed5  mov     [rsp+1A0h+UserData], rax; pszDest
0x140033eda  mov     [rsp+1A0h+UserDataCount], r12d; int
0x140033edf  jnb     short loc_140033EE8
0x140033ee1  call    VidExoIoControlPartition
0x140033ee6  jmp     short loc_140033EED
0x140033ee8  call    VidIoControlPartition
0x140033eed  mov     ebx, eax
0x140033eef  mov     eax, 0D4h
0x140033ef4  cmp     r15w, ax
0x140033ef8  jnb     loc_140034022
0x140033efe  lea     rcx, [rbp+0A0h+PerformanceFrequency]; PerformanceFrequency
0x140033f02  call    cs:__imp_KeQueryPerformanceCounter
0x140033f09  nop     dword ptr [rax+rax+00h]
0x140033f0e  mov     qword ptr [rbp+0A0h+var_118+8], rax
0x140033f12  sub     rax, qword ptr [rbp+0A0h+var_118]
0x140033f16  mov     rcx, [rdi+5F8h]
0x140033f1d  imul    rax, 0F4240h
0x140033f24  movzx   r8d, r15w
0x140033f28  cqo
0x140033f2a  idiv    qword ptr [rbp+0A0h+PerformanceFrequency]
0x140033f2e  lea     edx, ds:124h[r8*2]
0x140033f36  lock inc qword ptr [rcx+rdx*8]
0x140033f3b  mov     rcx, [rdi+5F8h]
0x140033f42  lea     edx, ds:125h[r8*2]
0x140033f4a  lock add [rcx+rdx*8], rax
0x140033f4f  jmp     loc_140034022
0x140033f54  mov     ebx, 0C0000008h
0x140033f59  jmp     loc_14003402A
0x140033f5e  lea     rax, [rsp+1A0h+var_150]
0x140033f63  mov     r9d, r12d
0x140033f66  mov     qword ptr [rsp+1A0h+var_168], rax
0x140033f6b  mov     r8, r13
0x140033f6e  mov     rax, [rsp+1A0h+pszDest]
0x140033f73  mov     [rsp+1A0h+var_170], esi
0x140033f77  mov     dword ptr [rsp+1A0h+UserData], ebx
0x140033f7b  mov     qword ptr [rsp+1A0h+UserDataCount], rax
0x140033f80  call    VidExoIoControlDriver
0x140033f85  jmp     short loc_140033FBA
0x140033f87  mov     rdx, qword ptr [rsp+1A0h+var_140]
0x140033f8c  lea     rax, [rsp+1A0h+var_150]
0x140033f91  mov     rcx, cs:VidDeviceExtension
0x140033f98  mov     r9d, r12d
0x140033f9b  mov     qword ptr [rsp+1A0h+var_168], rax
0x140033fa0  mov     r8, r13
0x140033fa3  mov     rax, [rsp+1A0h+pszDest]
0x140033fa8  mov     [rsp+1A0h+var_170], esi
0x140033fac  mov     dword ptr [rsp+1A0h+UserData], ebx
0x140033fb0  mov     qword ptr [rsp+1A0h+UserDataCount], rax
0x140033fb5  call    VidIoControlDriver
0x140033fba  mov     ebx, eax
0x140033fbc  cmp     r15w, 2Ah ; '*'
0x140033fc1  jnb     short loc_140034022
0x140033fc3  lea     rcx, [rbp+0A0h+PerformanceFrequency]; PerformanceFrequency
0x140033fc7  call    cs:__imp_KeQueryPerformanceCounter
0x140033fce  nop     dword ptr [rax+rax+00h]
0x140033fd3  mov     rcx, cs:VidDeviceExtension
0x140033fda  mov     qword ptr [rbp+0A0h+var_118+8], rax
0x140033fde  sub     rax, qword ptr [rbp+0A0h+var_118]
0x140033fe2  imul    rax, 0F4240h
0x140033fe9  movzx   r9d, r15w
0x140033fed  cqo
0x140033fef  idiv    qword ptr [rbp+0A0h+PerformanceFrequency]
0x140033ff3  mov     rdx, [rcx+168h]
0x140033ffa  lea     r8d, ds:2Fh[r9*2]
0x140034002  lock inc qword ptr [rdx+r8*8]
0x140034007  mov     rcx, cs:VidDeviceExtension
0x14003400e  lea     r8d, ds:30h[r9*2]
0x140034016  mov     rdx, [rcx+168h]
0x14003401d  lock add [rdx+r8*8], rax
0x140034022  cmp     ebx, 103h
0x140034028  jz      short loc_140034047
0x14003402a  mov     edx, dword ptr [rsp+1A0h+var_150]
0x14003402e  mov     rcx, r14; Irp
0x140034031  mov     [r14+38h], rdx
0x140034035  xor     edx, edx; PriorityBoost
0x140034037  mov     [r14+30h], ebx
0x14003403b  call    cs:__imp_IofCompleteRequest
0x140034042  nop     dword ptr [rax+rax+00h]
0x140034047  mov     eax, ebx
0x140034049  mov     rcx, [rbp+0A0h+var_50]
0x14003404d  xor     rcx, rsp; StackCookie
0x140034050  call    __security_check_cookie
0x140034055  add     rsp, 168h
0x14003405c  pop     r15
0x14003405e  pop     r14
0x140034060  pop     r13
0x140034062  pop     r12
0x140034064  pop     rdi
0x140034065  pop     rsi
0x140034066  pop     rbx
0x140034067  pop     rbp
0x140034068  retn
```
