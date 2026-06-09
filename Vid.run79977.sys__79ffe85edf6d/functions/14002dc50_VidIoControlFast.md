# VidIoControlFast

- ea: `0x14002dc50`
- end: `0x14002e171`
- name: `VidIoControlFast`
- size: `1313`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x14000477c`
- `0x1400100c0`
- `0x140012bc0`
- `0x140021c60`
- `0x14002dc50`
- `0x140031c08`
- `0x140031f8c`
- `0x1400321a4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14002deb0`
- `ntoskrnl!EtwWriteTransfer` at `0x14002deb0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002dec8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002dec8`
- `HAL!KeQueryPerformanceCounter` at `0x14002dccc`
- `HAL!KeQueryPerformanceCounter` at `0x14002dffc`
- `HAL!KeQueryPerformanceCounter` at `0x14002e0f0`
- `HAL!KeQueryPerformanceCounter` at `0x14002dccc`
- `HAL!KeQueryPerformanceCounter` at `0x14002dffc`
- `HAL!KeQueryPerformanceCounter` at `0x14002e0f0`

## pseudocode

```c
char __fastcall VidIoControlFast(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        __int64 a8)
{
  __int64 v11; // rdi
  LARGE_INTEGER v12; // rcx
  unsigned __int16 v13; // r14
  unsigned __int64 v14; // rdi
  int v15; // edx
  int v16; // ebx
  __int64 v17; // rbx
  __int64 v18; // rax
  int Next; // eax
  unsigned __int64 v20; // rax
  int v21; // eax
  unsigned __int64 v22; // rax
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+78h] [rbp-88h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  void *v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+ACh] [rbp-54h]
  const char *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  const char *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  int *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  int *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  _DWORD *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int64 v48; // [rsp+110h] [rbp+10h]
  _DWORD v49[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  int *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]

  PerformanceFrequency.QuadPart = 0;
  v23 = 0;
  v24 = a5;
  v30 = 0;
  if ( (a7 & 3) != 3 )
    return 0;
  v11 = *(_QWORD *)(a1 + 24);
  *(LARGE_INTEGER *)&v30 = KeQueryPerformanceCounter(0);
  v13 = (a7 >> 2) & 0x3FF;
  v14 = v11 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v14 )
  {
    if ( *(_DWORD *)v14 != 544176197 )
    {
      if ( *(_DWORD *)v14 != 1853125200 )
      {
        v16 = -1073741816;
        goto LABEL_23;
      }
      v15 = *(_DWORD *)(v14 + 48);
      if ( v15 != 1 && a7 != 2232784 )
      {
        v16 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2
          && (qword_140065120 & 0x100) != 0
          && (qword_140065128 & 0x100) == qword_140065128 )
        {
          v37 = 31;
          v36 = "VidIoControlPartitionIsAllowed";
          v39 = 41;
          v38 = "onecore\\vm\\vid\\sys\\driver\\vidiocontrol.c";
          v49[1] = 0;
          v40 = &v25;
          v27 = v15;
          v42 = &v26;
          v25 = 8089;
          v44 = v14 + 656;
          v41 = 4;
          v46 = v49;
          v48 = *(_QWORD *)(v14 + 128);
          v49[0] = *(unsigned __int16 *)(v14 + 120);
          v28 = *(_QWORD *)(v14 + 648);
          v50 = &v28;
          v52 = &v27;
          UserData.Ptr = (ULONGLONG)off_140065118;
          *(_DWORD *)&EventDescriptor.Level = 2;
          v26 = -1073741811;
          v43 = 4;
          v45 = 16;
          v47 = 2;
          v51 = 8;
          v53 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 256;
          UserData.Size = *(unsigned __int16 *)off_140065118;
          v33 = &unk_14005C6C0;
          UserData.Reserved = 2;
          v34 = 110;
          v35 = 1;
          LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
        }
        goto LABEL_47;
      }
      v17 = *(_QWORD *)(v14 + 10240);
      if ( v17 != PsGetCurrentProcess() && a7 != 2232419 && a7 != 2232563 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_9b7999e5d274371e1b0cbda42c5f46a6_Traceguids);
        }
        v16 = -1073741790;
        goto LABEL_47;
      }
      v18 = *(_QWORD *)(v14 + 16) & 0x8000LL;
      if ( a7 == 2232551 )
      {
        if ( v18 )
        {
          v16 = -1073741790;
LABEL_23:
          *(_DWORD *)a8 = v16;
          goto LABEL_24;
        }
        if ( !*(_BYTE *)(v14 + 832) )
        {
          v16 = -1073741811;
          goto LABEL_33;
        }
        Next = VidDispatchInterfaceHandleAndGetNext((int)v14 + 832, a4, (_DWORD)a3, a6, (__int64)&v23);
      }
      else if ( v18 )
      {
        Next = VidExoFastIoControlPartition(v14, a3, a6, a7, (__int64)&v23);
      }
      else
      {
        Next = VidIoControlFastPartition(v14, a3, a6, a7, (__int64)&v23);
      }
      v16 = Next;
LABEL_33:
      if ( v13 < 0xD4u )
      {
        *((LARGE_INTEGER *)&v30 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
        v20 = 1000000LL * (*((_QWORD *)&v30 + 1) - (_QWORD)v30) / PerformanceFrequency.QuadPart;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v14 + 1528)
                                                          + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 292)));
        _InterlockedAdd64(
          (volatile signed __int64 *)(*(_QWORD *)(v14 + 1528) + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 293)),
          v20);
      }
      goto LABEL_47;
    }
    v23 = 0;
    if ( a7 != 2228227 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_a76ff6e5b5ee3bbc086e8bc9b11ca330_Traceguids);
      }
      v16 = -1073741822;
      goto LABEL_45;
    }
    v21 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))VidIoControlFastDriver)(
            (LARGE_INTEGER)v12.QuadPart,
            a3,
            a4,
            a5,
            a6,
            2228227,
            &v23);
  }
  else
  {
    v21 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))VidIoControlFastDriver)(
            (LARGE_INTEGER)v12.QuadPart,
            a3,
            a4,
            a5,
            a6,
            a7,
            &v23);
  }
  v16 = v21;
LABEL_45:
  if ( v13 < 0x2Au )
  {
    *((LARGE_INTEGER *)&v30 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
    v22 = 1000000LL * (*((_QWORD *)&v30 + 1) - (_QWORD)v30) / PerformanceFrequency.QuadPart;
    _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45)
                                                      + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 47)));
    _InterlockedAdd64(
      (volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 48)),
      v22);
  }
LABEL_47:
  *(_DWORD *)a8 = v16;
  if ( v16 >= 0 && v16 != 258 )
  {
    *(_QWORD *)(a8 + 8) = v23;
    return 1;
  }
LABEL_24:
  *(_QWORD *)(a8 + 8) = v16;
  return 1;
}

```

## disassembly

```asm
0x14002dc50  push    rbp
0x14002dc52  push    rbx
0x14002dc53  push    rsi
0x14002dc54  push    r12
0x14002dc56  push    r13
0x14002dc58  push    r15
0x14002dc5a  lea     rbp, [rsp-58h]
0x14002dc5f  sub     rsp, 158h
0x14002dc66  mov     rax, cs:__security_cookie
0x14002dc6d  xor     rax, rsp
0x14002dc70  mov     [rbp+80h+var_40], rax
0x14002dc74  mov     esi, [rbp+80h+arg_30]
0x14002dc7a  xor     eax, eax
0x14002dc7c  mov     rbx, [rbp+80h+arg_20]
0x14002dc83  xorps   xmm0, xmm0
0x14002dc86  mov     r15, [rbp+80h+arg_38]
0x14002dc8d  mov     r13d, r9d
0x14002dc90  mov     qword ptr [rbp+80h+PerformanceFrequency], rax
0x14002dc94  mov     r12, r8
0x14002dc97  mov     [rsp+180h+var_140], rax
0x14002dc9c  mov     eax, esi
0x14002dc9e  and     eax, 3
0x14002dca1  mov     [rsp+180h+var_138], rbx
0x14002dca6  movups  [rsp+180h+var_108], xmm0
0x14002dcab  cmp     al, 3
0x14002dcad  jz      short loc_14002DCB6
0x14002dcaf  xor     al, al
0x14002dcb1  jmp     loc_14002DF5F
0x14002dcb6  mov     [rsp+180h+arg_8], rdi
0x14002dcbe  mov     rdi, [rcx+18h]
0x14002dcc2  xor     ecx, ecx; PerformanceFrequency
0x14002dcc4  mov     [rsp+180h+var_30], r14
0x14002dccc  call    cs:__imp_KeQueryPerformanceCounter
0x14002dcd3  nop     dword ptr [rax+rax+00h]
0x14002dcd8  mov     r14d, esi
0x14002dcdb  mov     qword ptr [rsp+180h+var_108], rax
0x14002dce0  shr     r14d, 2
0x14002dce4  mov     eax, 3FFh
0x14002dce9  and     r14w, ax
0x14002dced  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14002dcf1  jz      loc_14002E0BD
0x14002dcf7  mov     eax, [rdi]
0x14002dcf9  cmp     eax, 206F7845h
0x14002dcfe  jz      loc_14002E059
0x14002dd04  cmp     eax, 6E747250h
0x14002dd09  jnz     loc_14002E04F
0x14002dd0f  mov     edx, [rdi+30h]
0x14002dd12  cmp     edx, 1
0x14002dd15  jz      loc_14002DEC1
0x14002dd1b  cmp     esi, 2211D0h
0x14002dd21  jz      loc_14002DEC1
0x14002dd27  mov     eax, cs:dword_140065110
0x14002dd2d  mov     ebx, 0C000000Dh
0x14002dd32  cmp     eax, 2
0x14002dd35  jbe     loc_14002E14C
0x14002dd3b  mov     rcx, cs:qword_140065128
0x14002dd42  mov     rax, cs:qword_140065120
0x14002dd49  bt      rax, 8
0x14002dd4e  jnb     loc_14002E14C
0x14002dd54  mov     rax, rcx
0x14002dd57  and     eax, 100h
0x14002dd5c  cmp     rax, rcx
0x14002dd5f  jnz     loc_14002E14C
0x14002dd65  lea     rax, aVidiocontrolpa; "VidIoControlPartitionIsAllowed"
0x14002dd6c  mov     [rbp+80h+var_C8], 1Fh
0x14002dd74  mov     [rbp+80h+var_D0], rax
0x14002dd78  xor     ecx, ecx
0x14002dd7a  lea     rax, aOnecoreVmVidSy_31; "onecore\\vm\\vid\\sys\\driver\\vidiocon"...
0x14002dd81  mov     [rbp+80h+var_B8], 29h ; ')'
0x14002dd89  mov     [rbp+80h+var_C0], rax
0x14002dd8d  mov     [rbp+80h+var_64], ecx
0x14002dd90  lea     rax, [rsp+180h+var_130]
0x14002dd95  mov     [rbp+80h+var_B0], rax
0x14002dd99  xor     r9d, r9d; RelatedActivityId
0x14002dd9c  mov     [rsp+180h+var_128], edx
0x14002dda0  lea     rax, [rsp+180h+var_12C]
0x14002dda5  mov     [rbp+80h+var_A0], rax
0x14002dda9  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x14002ddae  mov     [rsp+180h+var_130], 1F99h
0x14002ddb6  lea     rax, [rdi+290h]
0x14002ddbd  mov     [rbp+80h+var_90], rax
0x14002ddc1  xor     r8d, r8d; ActivityId
0x14002ddc4  mov     [rbp+80h+var_A8], 4
0x14002ddcc  lea     rax, [rbp+80h+var_68]
0x14002ddd0  mov     [rbp+80h+var_80], rax
0x14002ddd4  mov     rax, [rdi+80h]
0x14002dddb  mov     [rbp+80h+var_70], rax
0x14002dddf  movzx   eax, word ptr [rdi+78h]
0x14002dde3  mov     [rbp+80h+var_68], eax
0x14002dde6  mov     rax, [rdi+288h]
0x14002dded  mov     [rsp+180h+var_120], rax
0x14002ddf2  lea     rax, [rsp+180h+var_120]
0x14002ddf7  mov     [rbp+80h+var_60], rax
0x14002ddfb  lea     rax, [rsp+180h+var_128]
0x14002de00  mov     [rbp+80h+var_50], rax
0x14002de04  mov     rax, cs:qword_14005C6B6
0x14002de0b  movzx   ecx, ax
0x14002de0e  mov     rax, cs:off_140065118
0x14002de15  mov     [rbp+80h+var_F0.Ptr], rax
0x14002de19  mov     dword ptr [rsp+180h+EventDescriptor.Level], ecx
0x14002de1d  lea     rcx, _TraceLoggingMetadata
0x14002de24  mov     [rsp+180h+var_12C], ebx
0x14002de28  mov     [rbp+80h+var_98], 4
0x14002de30  mov     [rbp+80h+var_88], 10h
0x14002de38  mov     [rbp+80h+var_78], 2
0x14002de40  mov     [rbp+80h+var_58], 8
0x14002de48  mov     [rbp+80h+var_48], 4
0x14002de50  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x14002de58  mov     [rsp+180h+EventDescriptor.Keyword], 100h
0x14002de61  movzx   eax, word ptr [rax]
0x14002de64  mov     [rbp+80h+var_F0.Size], eax
0x14002de67  lea     rax, unk_14005C6C0
0x14002de6e  mov     [rbp+80h+var_E0], rax
0x14002de72  lea     rax, _TraceLoggingMetadataEnd
0x14002de79  sub     eax, ecx
0x14002de7b  mov     dword ptr [rbp+80h+var_F0.0Ch], 2
0x14002de82  mov     [rbp+80h+var_D8], 6Eh ; 'n'
0x14002de89  mov     [rbp+80h+var_D4], 1
0x14002de90  mov     dword ptr [rsp+180h+var_138], eax
0x14002de94  mov     eax, dword ptr [rsp+180h+var_138]
0x14002de98  mov     rcx, cs:RegHandle; RegHandle
0x14002de9f  lea     rax, [rbp+80h+var_F0]
0x14002dea3  mov     [rsp+180h+UserData], rax; UserData
0x14002dea8  mov     [rsp+180h+UserDataCount], 0Bh; UserDataCount
0x14002deb0  call    cs:__imp_EtwWriteTransfer
0x14002deb7  nop     dword ptr [rax+rax+00h]
0x14002debc  jmp     loc_14002E14C
0x14002dec1  mov     rbx, [rdi+2800h]
0x14002dec8  call    cs:__imp_PsGetCurrentProcess
0x14002decf  nop     dword ptr [rax+rax+00h]
0x14002ded4  cmp     rbx, rax
0x14002ded7  jz      short loc_14002DF28
0x14002ded9  cmp     esi, 221063h
0x14002dedf  jz      short loc_14002DF28
0x14002dee1  cmp     esi, 2210F3h
0x14002dee7  jz      short loc_14002DF28
0x14002dee9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002def0  lea     rax, WPP_GLOBAL_Control
0x14002def7  cmp     rcx, rax
0x14002defa  jz      short loc_14002DF1E
0x14002defc  mov     eax, [rcx+2Ch]
0x14002deff  test    al, 2
0x14002df01  jz      short loc_14002DF1E
0x14002df03  cmp     byte ptr [rcx+29h], 2
0x14002df07  jb      short loc_14002DF1E
0x14002df09  mov     rcx, [rcx+18h]
0x14002df0d  lea     r8, WPP_9b7999e5d274371e1b0cbda42c5f46a6_Traceguids
0x14002df14  mov     edx, 0Dh
0x14002df19  call    WPP_SF_
0x14002df1e  mov     ebx, 0C0000022h
0x14002df23  jmp     loc_14002E14C
0x14002df28  mov     rax, [rdi+10h]
0x14002df2c  and     eax, 8000h
0x14002df31  cmp     esi, 2210E7h
0x14002df37  jnz     short loc_14002DFB0
0x14002df39  test    rax, rax
0x14002df3c  jz      short loc_14002DF7D
0x14002df3e  mov     ebx, 0C0000022h
0x14002df43  mov     [r15], ebx
0x14002df46  movsxd  rax, ebx
0x14002df49  mov     [r15+8], rax
0x14002df4d  mov     rdi, [rsp+180h+arg_8]
0x14002df55  mov     al, 1
0x14002df57  mov     r14, [rsp+180h+var_30]
0x14002df5f  mov     rcx, [rbp+80h+var_40]
0x14002df63  xor     rcx, rsp; StackCookie
0x14002df66  call    __security_check_cookie
0x14002df6b  add     rsp, 158h
0x14002df72  pop     r15
0x14002df74  pop     r13
0x14002df76  pop     r12
0x14002df78  pop     rsi
0x14002df79  pop     rbx
0x14002df7a  pop     rbp
0x14002df7b  retn
0x14002df7d  lea     rcx, [rdi+340h]
0x14002df84  movzx   eax, byte ptr [rcx]
0x14002df87  test    al, al
0x14002df89  jnz     short loc_14002DF92
0x14002df8b  mov     ebx, 0C000000Dh
0x14002df90  jmp     short loc_14002DFE9
0x14002df92  mov     r9d, [rbp+80h+arg_28]
0x14002df99  lea     rax, [rsp+180h+var_140]
0x14002df9e  mov     r8, r12
0x14002dfa1  mov     qword ptr [rsp+180h+UserDataCount], rax
0x14002dfa6  mov     edx, r13d
0x14002dfa9  call    VidDispatchInterfaceHandleAndGetNext
0x14002dfae  jmp     short loc_14002DFE7
0x14002dfb0  mov     r9, [rsp+180h+var_138]
0x14002dfb5  test    rax, rax
0x14002dfb8  lea     rax, [rsp+180h+var_140]
0x14002dfbd  mov     r8d, r13d
0x14002dfc0  mov     [rsp+180h+var_150], rax; __int64
0x14002dfc5  mov     rdx, r12; Src
0x14002dfc8  mov     eax, [rbp+80h+arg_28]
0x14002dfce  mov     rcx, rdi; int
0x14002dfd1  mov     dword ptr [rsp+180h+UserData], esi; int
0x14002dfd5  mov     [rsp+180h+UserDataCount], eax; int
0x14002dfd9  jz      short loc_14002DFE2
0x14002dfdb  call    VidExoFastIoControlPartition
0x14002dfe0  jmp     short loc_14002DFE7
0x14002dfe2  call    VidIoControlFastPartition
0x14002dfe7  mov     ebx, eax
0x14002dfe9  mov     eax, 0D4h
0x14002dfee  cmp     r14w, ax
0x14002dff2  jnb     loc_14002E14C
0x14002dff8  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x14002dffc  call    cs:__imp_KeQueryPerformanceCounter
0x14002e003  nop     dword ptr [rax+rax+00h]
0x14002e008  mov     qword ptr [rbp+80h+var_108+8], rax
0x14002e00c  sub     rax, qword ptr [rsp+180h+var_108]
0x14002e011  mov     rcx, [rdi+5F8h]
0x14002e018  imul    rax, 0F4240h
0x14002e01f  movzx   r8d, r14w
0x14002e023  cqo
0x14002e025  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x14002e029  lea     edx, ds:124h[r8*2]
0x14002e031  lock inc qword ptr [rcx+rdx*8]
0x14002e036  mov     rcx, [rdi+5F8h]
0x14002e03d  lea     edx, ds:125h[r8*2]
0x14002e045  lock add [rcx+rdx*8], rax
0x14002e04a  jmp     loc_14002E14C
0x14002e04f  mov     ebx, 0C0000008h
0x14002e054  jmp     loc_14002DF43
0x14002e059  mov     [rsp+180h+var_140], 0
0x14002e062  cmp     esi, 220003h
0x14002e068  jz      short loc_14002E0A9
0x14002e06a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e071  lea     rax, WPP_GLOBAL_Control
0x14002e078  cmp     rcx, rax
0x14002e07b  jz      short loc_14002E0A2
0x14002e07d  mov     eax, [rcx+2Ch]
0x14002e080  test    al, 1
0x14002e082  jz      short loc_14002E0A2
0x14002e084  cmp     byte ptr [rcx+29h], 3
0x14002e088  jb      short loc_14002E0A2
0x14002e08a  mov     rcx, [rcx+18h]
0x14002e08e  lea     r8, WPP_a76ff6e5b5ee3bbc086e8bc9b11ca330_Traceguids
0x14002e095  mov     edx, 0Ch
0x14002e09a  mov     r9d, esi
0x14002e09d  call    WPP_SF_d
0x14002e0a2  mov     ebx, 0C0000002h
0x14002e0a7  jmp     short loc_14002E0E5
0x14002e0a9  lea     rax, [rsp+180h+var_140]
0x14002e0ae  mov     [rsp+180h+var_150], rax
0x14002e0b3  mov     dword ptr [rsp+180h+UserData], 220003h
0x14002e0bb  jmp     short loc_14002E0CB
0x14002e0bd  lea     rax, [rsp+180h+var_140]
0x14002e0c2  mov     [rsp+180h+var_150], rax
0x14002e0c7  mov     dword ptr [rsp+180h+UserData], esi
0x14002e0cb  mov     eax, [rbp+80h+arg_28]
0x14002e0d1  mov     r9, rbx
0x14002e0d4  mov     r8d, r13d
0x14002e0d7  mov     [rsp+180h+UserDataCount], eax
0x14002e0db  mov     rdx, r12
0x14002e0de  call    VidIoControlFastDriver
0x14002e0e3  mov     ebx, eax
0x14002e0e5  cmp     r14w, 2Ah ; '*'
0x14002e0ea  jnb     short loc_14002E14C
0x14002e0ec  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x14002e0f0  call    cs:__imp_KeQueryPerformanceCounter
0x14002e0f7  nop     dword ptr [rax+rax+00h]
0x14002e0fc  mov     rcx, cs:VidDeviceExtension
0x14002e103  mov     qword ptr [rbp+80h+var_108+8], rax
0x14002e107  sub     rax, qword ptr [rsp+180h+var_108]
0x14002e10c  imul    rax, 0F4240h
0x14002e113  movzx   r9d, r14w
0x14002e117  cqo
0x14002e119  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x14002e11d  mov     rdx, [rcx+168h]
0x14002e124  lea     r8d, ds:2Fh[r9*2]
0x14002e12c  lock inc qword ptr [rdx+r8*8]
0x14002e131  mov     rcx, cs:VidDeviceExtension
0x14002e138  lea     r8d, ds:30h[r9*2]
0x14002e140  mov     rdx, [rcx+168h]
0x14002e147  lock add [rdx+r8*8], rax
0x14002e14c  mov     [r15], ebx
0x14002e14f  test    ebx, ebx
0x14002e151  js      loc_14002DF46
0x14002e157  cmp     ebx, 102h
0x14002e15d  jz      loc_14002DF46
0x14002e163  mov     rcx, [rsp+180h+var_140]
0x14002e168  mov     [r15+8], rcx
0x14002e16c  jmp     loc_14002DF4D
```
