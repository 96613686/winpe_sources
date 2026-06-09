# BthEnumRemoveProtocol

- ea: `0x14001ec38`
- end: `0x14001f04d`
- name: `BthEnumRemoveProtocol`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001e1e0`

## callees

- `0x140001214`
- `0x140001328`
- `0x1400013e8`
- `0x1400016fc`
- `0x140003428`
- `0x14000359c`
- `0x140007e40`
- `0x14001e034`
- `0x14001e160`
- `0x14001ec38`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001edd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001edd9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001edef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001edef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ef87`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f003`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ef87`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f003`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ef93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f00f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ef93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f00f`
- `ntoskrnl!RtlStringFromGUID` at `0x14001ed5a`
- `ntoskrnl!RtlStringFromGUID` at `0x14001ed5a`
- `ntoskrnl!IoDeleteDevice` at `0x14001efb1`
- `ntoskrnl!IoDeleteDevice` at `0x14001efb1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f02f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f02f`
- `ntoskrnl!RtlRbRemoveNode` at `0x14001ef6e`
- `ntoskrnl!RtlRbRemoveNode` at `0x14001ef6e`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001efc3`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001efc3`
- `ntoskrnl!ExFreePool` at `0x14001f01e`
- `ntoskrnl!ExFreePool` at `0x14001f01e`
- `ntoskrnl!ExAllocatePool2` at `0x14001ec75`
- `ntoskrnl!ExAllocatePool2` at `0x14001ec75`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ed45`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ed45`

## pseudocode

```c
void __fastcall BthEnumRemoveProtocol(__int64 a1, __int64 a2, const GUID *a3)
{
  __int64 v4; // rbx
  __int64 v5; // r13
  __int64 Pool2; // rax
  int v7; // edx
  _QWORD *v8; // r15
  __int64 v9; // rsi
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r9d
  int v13; // r8d
  int v14; // edx
  __int64 v15; // rbx
  int v16; // esi
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rax
  int v21; // edx
  char v22; // bp
  int v23; // [rsp+20h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF

  DestinationString = 0;
  if ( a2 )
    v4 = *(_QWORD *)(a2 + 8);
  else
    v4 = 0;
  v5 = *(_QWORD *)(a1 + 64);
  Pool2 = ExAllocatePool2(256, 2928, 1330467906);
  v8 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    v9 = Pool2 + 24;
    v23 = v4;
    v10 = RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(Pool2 + 24), 0x1Au, L"%04X%08X", WORD2(v4));
    if ( v10 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, 0);
      v10 = RtlStringFromGUID(a3 + 1, &DestinationString);
      if ( v10 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_SS(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v13,
            23,
            v4,
            (__int64)DestinationString.Buffer,
            v9);
        v8[7] = DestinationString.Buffer;
        memmove(v8 + 130, a3, 0x730u);
        KeEnterCriticalRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 152));
        v15 = *(_QWORD *)(v5 + 136);
        if ( (*(_BYTE *)(v5 + 144) & 1) != 0 && v15 )
          v15 ^= v5 + 136;
        v16 = *(_BYTE *)(v5 + 144) & 1;
        if ( !v15 )
          goto LABEL_46;
        do
        {
          v17 = BthEnumChildCompare((__int64)v8, v15);
          if ( v17 >= 0 )
          {
            if ( v17 <= 0 )
              break;
            v20 = *(_QWORD *)(v15 + 8);
          }
          else
          {
            v20 = *(_QWORD *)v15;
          }
          if ( v16 && v20 )
            v15 ^= v20;
          else
            v15 = v20;
        }
        while ( v15 );
        if ( v15 )
        {
          v21 = *(_DWORD *)(v15 + 96);
          v22 = 0;
          if ( v21 )
          {
            if ( v21 == 1 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_q(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v21,
                  4,
                  26,
                  (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
                  *(_QWORD *)(v15 - 64));
              *(_DWORD *)(v15 + 96) = 2;
            }
            else if ( v21 == 3 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_q(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v21,
                  4,
                  27,
                  (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
                  *(_QWORD *)(v15 - 64));
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              WPP_RECORDER_SF_dq(WPP_GLOBAL_Control->DeviceExtension, v21, v18, v19, v23, v21, *(_QWORD *)(v15 - 64));
            }
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_q(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                4,
                25,
                (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
                *(_QWORD *)(v15 - 64));
            *(_DWORD *)(v15 + 96) = 3;
            RtlRbRemoveNode(v5 + 136, v15);
            --*(_DWORD *)(v5 + 252);
            v22 = 1;
          }
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 152));
          KeLeaveCriticalRegion();
          if ( v22 )
          {
            BthEnumDestroyPdoExt(v15 - 80);
            IoDeleteDevice(*(PDEVICE_OBJECT *)(v15 - 64));
          }
          IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v5 + 16), BusRelations);
        }
        else
        {
LABEL_46:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              4,
              24,
              (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 152));
          KeLeaveCriticalRegion();
        }
        goto LABEL_49;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = 22;
        goto LABEL_10;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 21;
LABEL_10:
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        4,
        v12,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
        v10);
    }
LABEL_49:
    ExFreePool(v8);
    goto LABEL_50;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      4,
      20,
      (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
      -1073741670);
LABEL_50:
  RtlFreeUnicodeString(&DestinationString);
}

```

## disassembly

```asm
0x14001ec38  push    rbx
0x14001ec3a  push    rbp
0x14001ec3b  push    rsi
0x14001ec3c  push    rdi
0x14001ec3d  push    r12
0x14001ec3f  push    r13
0x14001ec41  push    r14
0x14001ec43  push    r15
0x14001ec45  sub     rsp, 58h
0x14001ec49  xorps   xmm0, xmm0
0x14001ec4c  mov     rbp, r8
0x14001ec4f  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14001ec54  test    rdx, rdx
0x14001ec57  jnz     short loc_14001EC5D
0x14001ec59  xor     ebx, ebx
0x14001ec5b  jmp     short loc_14001EC61
0x14001ec5d  mov     rbx, [rdx+8]
0x14001ec61  mov     r13, [rcx+40h]
0x14001ec65  mov     edx, 0B70h
0x14001ec6a  mov     ecx, 100h
0x14001ec6f  mov     r8d, 4F4D5442h
0x14001ec75  call    cs:__imp_ExAllocatePool2
0x14001ec7c  nop     dword ptr [rax+rax+00h]
0x14001ec81  mov     r15, rax
0x14001ec84  test    rax, rax
0x14001ec87  jnz     short loc_14001ECCE
0x14001ec89  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001ec90  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ec97  jz      loc_14001F02A
0x14001ec9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eca4  lea     r9d, [rax+14h]
0x14001eca8  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001ecaf  mov     dword ptr [rsp+98h+var_70], 0C000009Ah
0x14001ecb7  lea     r8d, [r15+4]
0x14001ecbb  mov     [rsp+98h+var_78], rax
0x14001ecc0  mov     rcx, [rcx+40h]
0x14001ecc4  call    WPP_RECORDER_SF_d
0x14001ecc9  jmp     loc_14001F02A
0x14001ecce  lea     rsi, [rax+18h]
0x14001ecd2  mov     dword ptr [rsp+98h+var_78], ebx
0x14001ecd6  mov     rax, rbx
0x14001ecd9  lea     r8, a04x08x; "%04X%08X"
0x14001ece0  shr     rax, 20h
0x14001ece4  mov     edx, 1Ah; cbDest
0x14001ece9  movzx   r9d, ax
0x14001eced  mov     rcx, rsi; pszDest
0x14001ecf0  call    RtlStringCbPrintfW
0x14001ecf5  test    eax, eax
0x14001ecf7  jns     short loc_14001ED3E
0x14001ecf9  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001ed00  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ed07  jz      loc_14001F01B
0x14001ed0d  mov     r9d, 15h
0x14001ed13  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed1a  mov     r8d, 4
0x14001ed20  mov     dword ptr [rsp+98h+var_70], eax
0x14001ed24  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001ed2b  mov     [rsp+98h+var_78], rax
0x14001ed30  mov     rcx, [rcx+40h]
0x14001ed34  call    WPP_RECORDER_SF_d
0x14001ed39  jmp     loc_14001F01B
0x14001ed3e  xor     edx, edx; SourceString
0x14001ed40  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14001ed45  call    cs:__imp_RtlInitUnicodeString
0x14001ed4c  nop     dword ptr [rax+rax+00h]
0x14001ed51  lea     rcx, [rbp+10h]; Guid
0x14001ed55  lea     rdx, [rsp+98h+DestinationString]; GuidString
0x14001ed5a  call    cs:__imp_RtlStringFromGUID
0x14001ed61  nop     dword ptr [rax+rax+00h]
0x14001ed66  test    eax, eax
0x14001ed68  jns     short loc_14001ED86
0x14001ed6a  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001ed71  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ed78  jz      loc_14001F01B
0x14001ed7e  mov     r9d, 16h
0x14001ed84  jmp     short loc_14001ED13
0x14001ed86  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001ed8d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ed94  jz      short loc_14001EDBB
0x14001ed96  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed9d  mov     r9d, 17h
0x14001eda3  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14001eda8  mov     [rsp+98h+var_68], rsi
0x14001edad  mov     [rsp+98h+var_70], rax
0x14001edb2  mov     rcx, [rcx+40h]
0x14001edb6  call    WPP_RECORDER_SF_SS
0x14001edbb  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14001edc0  lea     rcx, [r15+410h]; void *
0x14001edc7  mov     rdx, rbp; Src
0x14001edca  mov     [r15+38h], rax
0x14001edce  mov     r8d, 730h; Size
0x14001edd4  call    memmove
0x14001edd9  call    cs:__imp_KeEnterCriticalRegion
0x14001ede0  nop     dword ptr [rax+rax+00h]
0x14001ede5  lea     r12, [r13+98h]
0x14001edec  mov     rcx, r12; FastMutex
0x14001edef  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001edf6  nop     dword ptr [rax+rax+00h]
0x14001edfb  lea     r14, [r13+88h]
0x14001ee02  test    byte ptr [r14+8], 1
0x14001ee07  mov     rbx, [r14]
0x14001ee0a  jz      short loc_14001EE14
0x14001ee0c  test    rbx, rbx
0x14001ee0f  jz      short loc_14001EE14
0x14001ee11  xor     rbx, r14
0x14001ee14  movzx   esi, byte ptr [r14+8]
0x14001ee19  and     esi, 1
0x14001ee1c  test    rbx, rbx
0x14001ee1f  jz      loc_14001EFD1
0x14001ee25  mov     rdx, rbx
0x14001ee28  mov     rcx, r15
0x14001ee2b  call    BthEnumChildCompare
0x14001ee30  test    eax, eax
0x14001ee32  jns     short loc_14001EE39
0x14001ee34  mov     rax, [rbx]
0x14001ee37  jmp     short loc_14001EE3F
0x14001ee39  jle     short loc_14001EE55
0x14001ee3b  mov     rax, [rbx+8]
0x14001ee3f  test    esi, esi
0x14001ee41  jz      short loc_14001EE4D
0x14001ee43  test    rax, rax
0x14001ee46  jz      short loc_14001EE4D
0x14001ee48  xor     rbx, rax
0x14001ee4b  jmp     short loc_14001EE50
0x14001ee4d  mov     rbx, rax
0x14001ee50  test    rbx, rbx
0x14001ee53  jnz     short loc_14001EE25
0x14001ee55  test    rbx, rbx
0x14001ee58  jz      loc_14001EFD1
0x14001ee5e  mov     edx, [rbx+60h]
0x14001ee61  xor     bpl, bpl
0x14001ee64  mov     ecx, edx
0x14001ee66  test    edx, edx
0x14001ee68  jz      loc_14001EF29
0x14001ee6e  sub     ecx, 1
0x14001ee71  jz      short loc_14001EEE8
0x14001ee73  cmp     ecx, 2
0x14001ee76  jz      short loc_14001EEA7
0x14001ee78  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ee7f  jz      loc_14001EF84
0x14001ee85  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee8c  mov     rax, [rbx-40h]
0x14001ee90  mov     [rsp+98h+var_68], rax
0x14001ee95  mov     dword ptr [rsp+98h+var_70], edx
0x14001ee99  mov     rcx, [rcx+40h]
0x14001ee9d  call    WPP_RECORDER_SF_dq
0x14001eea2  jmp     loc_14001EF84
0x14001eea7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001eeae  jz      loc_14001EF84
0x14001eeb4  mov     rax, [rbx-40h]
0x14001eeb8  mov     r9d, 1Bh
0x14001eebe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eec5  mov     [rsp+98h+var_70], rax
0x14001eeca  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001eed1  mov     [rsp+98h+var_78], rax
0x14001eed6  lea     r8d, [r9-17h]
0x14001eeda  mov     rcx, [rcx+40h]
0x14001eede  call    WPP_RECORDER_SF_q
0x14001eee3  jmp     loc_14001EF84
0x14001eee8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001eeef  jz      short loc_14001EF20
0x14001eef1  mov     rax, [rbx-40h]
0x14001eef5  mov     r9d, 1Ah
0x14001eefb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef02  mov     [rsp+98h+var_70], rax
0x14001ef07  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001ef0e  mov     [rsp+98h+var_78], rax
0x14001ef13  lea     r8d, [r9-16h]
0x14001ef17  mov     rcx, [rcx+40h]
0x14001ef1b  call    WPP_RECORDER_SF_q
0x14001ef20  mov     dword ptr [rbx+60h], 2
0x14001ef27  jmp     short loc_14001EF84
0x14001ef29  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001ef30  jz      short loc_14001EF61
0x14001ef32  mov     rax, [rbx-40h]
0x14001ef36  mov     r9d, 19h
0x14001ef3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef43  mov     [rsp+98h+var_70], rax
0x14001ef48  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001ef4f  mov     [rsp+98h+var_78], rax
0x14001ef54  lea     r8d, [r9-15h]
0x14001ef58  mov     rcx, [rcx+40h]
0x14001ef5c  call    WPP_RECORDER_SF_q
0x14001ef61  mov     rdx, rbx
0x14001ef64  mov     dword ptr [rbx+60h], 3
0x14001ef6b  mov     rcx, r14
0x14001ef6e  call    cs:__imp_RtlRbRemoveNode
0x14001ef75  nop     dword ptr [rax+rax+00h]
0x14001ef7a  dec     dword ptr [r13+0FCh]
0x14001ef81  mov     bpl, 1
0x14001ef84  mov     rcx, r12; FastMutex
0x14001ef87  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ef8e  nop     dword ptr [rax+rax+00h]
0x14001ef93  call    cs:__imp_KeLeaveCriticalRegion
0x14001ef9a  nop     dword ptr [rax+rax+00h]
0x14001ef9f  test    bpl, bpl
0x14001efa2  jz      short loc_14001EFBD
0x14001efa4  lea     rcx, [rbx-50h]
0x14001efa8  call    BthEnumDestroyPdoExt
0x14001efad  mov     rcx, [rbx-40h]; DeviceObject
0x14001efb1  call    cs:__imp_IoDeleteDevice
0x14001efb8  nop     dword ptr [rax+rax+00h]
0x14001efbd  mov     rcx, [r13+10h]; DeviceObject
0x14001efc1  xor     edx, edx; Type
0x14001efc3  call    cs:__imp_IoInvalidateDeviceRelations
0x14001efca  nop     dword ptr [rax+rax+00h]
0x14001efcf  jmp     short loc_14001F01B
0x14001efd1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001efd8  jz      short loc_14001F000
0x14001efda  mov     rcx, cs:WPP_GLOBAL_Control
0x14001efe1  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001efe8  mov     r9d, 18h
0x14001efee  mov     [rsp+98h+var_78], rax
0x14001eff3  mov     rcx, [rcx+40h]
0x14001eff7  lea     r8d, [r9-14h]
0x14001effb  call    WPP_RECORDER_SF_
0x14001f000  mov     rcx, r12; FastMutex
0x14001f003  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f00a  nop     dword ptr [rax+rax+00h]
0x14001f00f  call    cs:__imp_KeLeaveCriticalRegion
0x14001f016  nop     dword ptr [rax+rax+00h]
0x14001f01b  mov     rcx, r15; P
0x14001f01e  call    cs:__imp_ExFreePool
0x14001f025  nop     dword ptr [rax+rax+00h]
0x14001f02a  lea     rcx, [rsp+98h+DestinationString]; UnicodeString
0x14001f02f  call    cs:__imp_RtlFreeUnicodeString
0x14001f036  nop     dword ptr [rax+rax+00h]
0x14001f03b  add     rsp, 58h
0x14001f03f  pop     r15
0x14001f041  pop     r14
0x14001f043  pop     r13
0x14001f045  pop     r12
0x14001f047  pop     rdi
0x14001f048  pop     rsi
0x14001f049  pop     rbp
0x14001f04a  pop     rbx
0x14001f04b  retn
```
