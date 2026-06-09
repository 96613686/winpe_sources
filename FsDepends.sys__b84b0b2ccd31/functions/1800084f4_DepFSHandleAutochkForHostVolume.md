# DepFSHandleAutochkForHostVolume

- ea: `0x1800084f4`
- end: `0x180008a51`
- name: `DepFSHandleAutochkForHostVolume`
- size: `1373`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180008a60`
- `0x180008c10`
- `0x180008d60`

## callees

- `0x180001020`
- `0x180001064`
- `0x1800010b8`
- `0x1800010fc`
- `0x1800084f4`
- `0x18000eac0`
- `0x18000f73c`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008671`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800088ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008a04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008671`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800088ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008a04`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800088ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800088ee`
- `ntoskrnl!KeInitializeEvent` at `0x1800087f5`
- `ntoskrnl!KeInitializeEvent` at `0x1800087f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800089e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800089e0`
- `ntoskrnl!IofCallDriver` at `0x1800088c4`
- `ntoskrnl!IofCallDriver` at `0x1800088c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008665`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000889f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800089f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008665`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000889f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800089f8`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000883f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000883f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008554`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008602`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008978`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008554`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008602`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008978`
- `ntoskrnl!ObfDereferenceObject` at `0x18000876c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000876c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000853f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800085ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008962`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000853f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800085ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008962`
- `ntoskrnl!KeBugCheckEx` at `0x180008a44`
- `ntoskrnl!KeBugCheckEx` at `0x180008a44`
- `FLTMGR!FltClose` at `0x18000877c`
- `FLTMGR!FltClose` at `0x18000877c`
- `FLTMGR!FltOpenVolume` at `0x1800086c4`
- `FLTMGR!FltOpenVolume` at `0x1800086c4`
- `FLTMGR!FltFlushBuffers` at `0x180008717`
- `FLTMGR!FltFlushBuffers` at `0x180008717`

## pseudocode

```c
__int64 __fastcall DepFSHandleAutochkForHostVolume(__int64 a1, int a2)
{
  NTSTATUS Status; // ebx
  unsigned int v5; // r12d
  char v6; // r15
  _QWORD *v7; // r14
  __int64 v8; // rdi
  NTSTATUS v9; // eax
  __int64 v10; // rdi
  _DWORD *v11; // rcx
  IRP *v12; // rbx
  unsigned int i; // esi
  _QWORD *v14; // r14
  __int64 v15; // rcx
  void *v16; // rcx
  void *VolumeHandle; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-21h] BYREF
  __int128 InputBuffer; // [rsp+68h] [rbp-11h] BYREF
  __int64 v21; // [rsp+78h] [rbp-1h]
  struct _KEVENT Event; // [rsp+80h] [rbp+7h] BYREF
  PVOID P; // [rsp+F0h] [rbp+77h] BYREF
  PFILE_OBJECT VolumeFileObject; // [rsp+F8h] [rbp+7Fh] BYREF

  P = 0;
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  v21 = 0;
  InputBuffer = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  Status = DepFSGenerateDependencyList(0, a1, 0, &P, 1, 0x8000);
  if ( Status < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
      (unsigned int)Status);
  }
  if ( !P )
    goto LABEL_69;
  v5 = 0;
  v6 = 1;
  if ( !*((_DWORD *)P + 1) )
    goto LABEL_60;
  do
  {
    v7 = P;
    if ( !v6 )
    {
      v6 = 1;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&Resource, 1u);
    }
    if ( (v7[2 * v5 + 1] & 1) != 0 )
    {
      v8 = v7[2 * v5 + 2];
      if ( v8 != a1 && (*(_DWORD *)(v8 + 56) & 0x24) == 0 && a2 == 1 && !*(_QWORD *)(v8 + 104) )
      {
        VolumeFileObject = 0;
        VolumeHandle = 0;
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        v6 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids, v8);
        }
        v9 = FltOpenVolume(*(PFLT_INSTANCE *)(v8 + 64), &VolumeHandle, &VolumeFileObject);
        if ( v9 >= 0 )
        {
          Status = FltFlushBuffers(*(PFLT_INSTANCE *)(v8 + 64), VolumeFileObject);
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                19,
                WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
                *(_QWORD *)(v8 + 72),
                Status);
            }
            Status = 0;
          }
          ObfDereferenceObject(VolumeFileObject);
          FltClose(VolumeHandle);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
              *(_QWORD *)(v8 + 72),
              v9);
          }
          Status = 0;
        }
      }
    }
    if ( (v7[2 * v5 + 1] & 2) != 0 )
    {
      v10 = v7[2 * v5 + 2];
      v11 = (_DWORD *)(v10 + 92);
      if ( a2 == 2 )
      {
        if ( (*v11 & 0x200) != 0 )
          goto LABEL_57;
        *v11 |= 0x200u;
      }
      if ( *(_QWORD *)(v10 + 40) != v10 + 40 && (*(_DWORD *)(v10 + 60) & 4) == 0 && (*v11 & 3) == 0 )
      {
        *(_QWORD *)&InputBuffer = *(_QWORD *)(v10 + 104);
        *((_QWORD *)&InputBuffer + 1) = *(_QWORD *)(v10 + 120);
        LODWORD(v21) = a2;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v12 = IoBuildDeviceIoControlRequest(
                0x2D9198u,
                *(PDEVICE_OBJECT *)(v10 + 128),
                &InputBuffer,
                0x18u,
                0,
                0,
                0,
                &Event,
                &IoStatusBlock);
        if ( v12 )
        {
          if ( v6 )
          {
            ExReleaseResourceLite(&Resource);
            KeLeaveCriticalRegion();
            v6 = 0;
          }
          Status = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 128), v12);
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            Status = IoStatusBlock.Status;
          }
          if ( Status < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_Dq(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
                (unsigned int)Status,
                v10);
            }
            if ( (*(_DWORD *)(v10 + 60) & 0x10) != 0 )
              KeBugCheckEx(0x136u, 0, Status, 0, 0);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids, v10);
          }
          Status = -1073741670;
        }
      }
    }
LABEL_57:
    ++v5;
  }
  while ( v5 < *((_DWORD *)P + 1) );
  if ( !v6 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
  }
LABEL_60:
  for ( i = 0; i < *((_DWORD *)P + 1); ++i )
  {
    v14 = P;
    if ( (*((_BYTE *)P + 16 * i + 8) & 1) != 0 )
    {
      v15 = *((_QWORD *)P + 2 * i + 2);
      if ( v15 )
        DereferenceVolumeContext(v15);
    }
    if ( (v14[2 * i + 1] & 2) != 0 )
    {
      v16 = (void *)v14[2 * i + 2];
      if ( v16 )
        DereferenceDependencyContext(v16);
    }
  }
  ExFreePoolWithTag(P, 0x6C447044u);
LABEL_69:
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1800084f4  mov     [rsp-8+arg_8], rbx
0x1800084f9  mov     [rsp-8+arg_0], rcx
0x1800084fe  push    rbp
0x1800084ff  push    rsi
0x180008500  push    rdi
0x180008501  push    r12
0x180008503  push    r13
0x180008505  push    r14
0x180008507  push    r15
0x180008509  lea     rbp, [rsp-27h]
0x18000850e  sub     rsp, 0A0h
0x180008515  xorps   xmm0, xmm0
0x180008518  mov     [rbp+57h+P], 0
0x180008520  xor     eax, eax
0x180008522  xorps   xmm1, xmm1
0x180008525  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180008529  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18000852d  mov     r13d, edx
0x180008530  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x180008534  mov     [rbp+57h+var_58], rax
0x180008538  mov     rbx, rcx
0x18000853b  movups  [rbp+57h+InputBuffer], xmm0
0x18000853f  call    cs:__imp_KeEnterCriticalRegion
0x180008546  nop     dword ptr [rax+rax+00h]
0x18000854b  mov     dl, 1; Wait
0x18000854d  lea     rcx, Resource; Resource
0x180008554  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000855b  nop     dword ptr [rax+rax+00h]
0x180008560  lea     r9, [rbp+57h+P]
0x180008564  mov     [rsp+0D0h+OutputBufferLength], 8000h
0x18000856c  xor     r8d, r8d
0x18000856f  mov     byte ptr [rsp+0D0h+OutputBuffer], 1
0x180008574  mov     rdx, rbx
0x180008577  xor     ecx, ecx
0x180008579  call    DepFSGenerateDependencyList
0x18000857e  mov     ebx, eax
0x180008580  lea     rax, WPP_GLOBAL_Control
0x180008587  test    ebx, ebx
0x180008589  jns     short loc_1800085BD
0x18000858b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008592  cmp     rcx, rax
0x180008595  jz      short loc_1800085BD
0x180008597  mov     edx, [rcx+2Ch]
0x18000859a  test    dl, 1
0x18000859d  jz      short loc_1800085BD
0x18000859f  cmp     byte ptr [rcx+29h], 2
0x1800085a3  jb      short loc_1800085BD
0x1800085a5  mov     rcx, [rcx+18h]
0x1800085a9  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x1800085b0  mov     edx, 10h
0x1800085b5  mov     r9d, ebx
0x1800085b8  call    WPP_SF_D
0x1800085bd  mov     rax, [rbp+57h+P]
0x1800085c1  test    rax, rax
0x1800085c4  jz      loc_1800089F1
0x1800085ca  xor     r12d, r12d
0x1800085cd  mov     r15b, 1
0x1800085d0  cmp     [rax+4], r12d
0x1800085d4  jbe     loc_180008984
0x1800085da  mov     r14, [rbp+57h+P]
0x1800085de  mov     esi, r12d
0x1800085e1  add     rsi, rsi
0x1800085e4  test    r15b, r15b
0x1800085e7  jnz     short loc_18000860E
0x1800085e9  mov     r15b, 1
0x1800085ec  call    cs:__imp_KeEnterCriticalRegion
0x1800085f3  nop     dword ptr [rax+rax+00h]
0x1800085f8  mov     dl, r15b; Wait
0x1800085fb  lea     rcx, Resource; Resource
0x180008602  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008609  nop     dword ptr [rax+rax+00h]
0x18000860e  test    byte ptr [r14+rsi*8+8], 1
0x180008614  jz      loc_180008788
0x18000861a  mov     rdi, [r14+rsi*8+10h]
0x18000861f  cmp     rdi, [rbp+57h+arg_0]
0x180008623  jz      loc_180008788
0x180008629  mov     eax, [rdi+38h]
0x18000862c  test    al, 24h
0x18000862e  jnz     loc_180008788
0x180008634  cmp     r13d, 1
0x180008638  jnz     loc_180008788
0x18000863e  cmp     qword ptr [rdi+68h], 0
0x180008643  jnz     loc_180008788
0x180008649  mov     [rbp+57h+VolumeFileObject], 0
0x180008651  mov     [rbp+57h+VolumeHandle], 0
0x180008659  test    r15b, r15b
0x18000865c  jz      short loc_180008680
0x18000865e  lea     rcx, Resource; Resource
0x180008665  call    cs:__imp_ExReleaseResourceLite
0x18000866c  nop     dword ptr [rax+rax+00h]
0x180008671  call    cs:__imp_KeLeaveCriticalRegion
0x180008678  nop     dword ptr [rax+rax+00h]
0x18000867d  xor     r15b, r15b
0x180008680  mov     rcx, cs:WPP_GLOBAL_Control
0x180008687  lea     rbx, WPP_GLOBAL_Control
0x18000868e  cmp     rcx, rbx
0x180008691  jz      short loc_1800086B8
0x180008693  mov     eax, [rcx+2Ch]
0x180008696  test    al, 4
0x180008698  jz      short loc_1800086B8
0x18000869a  cmp     byte ptr [rcx+29h], 4
0x18000869e  jb      short loc_1800086B8
0x1800086a0  mov     rcx, [rcx+18h]
0x1800086a4  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x1800086ab  mov     edx, 11h
0x1800086b0  mov     r9, rdi
0x1800086b3  call    WPP_SF_q
0x1800086b8  mov     rcx, [rdi+40h]; Instance
0x1800086bc  lea     r8, [rbp+57h+VolumeFileObject]; VolumeFileObject
0x1800086c0  lea     rdx, [rbp+57h+VolumeHandle]; VolumeHandle
0x1800086c4  call    cs:__imp_FltOpenVolume
0x1800086cb  nop     dword ptr [rax+rax+00h]
0x1800086d0  test    eax, eax
0x1800086d2  jns     short loc_18000870F
0x1800086d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086db  cmp     rcx, rbx
0x1800086de  jz      short loc_18000870B
0x1800086e0  mov     edx, [rcx+2Ch]
0x1800086e3  test    dl, 4
0x1800086e6  jz      short loc_18000870B
0x1800086e8  cmp     byte ptr [rcx+29h], 4
0x1800086ec  jb      short loc_18000870B
0x1800086ee  mov     r9, [rdi+48h]
0x1800086f2  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x1800086f9  mov     rcx, [rcx+18h]
0x1800086fd  mov     edx, 12h
0x180008702  mov     dword ptr [rsp+0D0h+OutputBuffer], eax
0x180008706  call    WPP_SF_qD
0x18000870b  xor     ebx, ebx
0x18000870d  jmp     short loc_180008788
0x18000870f  mov     rdx, [rbp+57h+VolumeFileObject]; FileObject
0x180008713  mov     rcx, [rdi+40h]; Instance
0x180008717  call    cs:__imp_FltFlushBuffers
0x18000871e  nop     dword ptr [rax+rax+00h]
0x180008723  mov     ebx, eax
0x180008725  test    eax, eax
0x180008727  jns     short loc_180008768
0x180008729  mov     rcx, cs:WPP_GLOBAL_Control
0x180008730  lea     rax, WPP_GLOBAL_Control
0x180008737  cmp     rcx, rax
0x18000873a  jz      short loc_180008766
0x18000873c  mov     eax, [rcx+2Ch]
0x18000873f  test    al, 4
0x180008741  jz      short loc_180008766
0x180008743  cmp     byte ptr [rcx+29h], 4
0x180008747  jb      short loc_180008766
0x180008749  mov     r9, [rdi+48h]
0x18000874d  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008754  mov     rcx, [rcx+18h]
0x180008758  mov     edx, 13h
0x18000875d  mov     dword ptr [rsp+0D0h+OutputBuffer], ebx
0x180008761  call    WPP_SF_qD
0x180008766  xor     ebx, ebx
0x180008768  mov     rcx, [rbp+57h+VolumeFileObject]; Object
0x18000876c  call    cs:__imp_ObfDereferenceObject
0x180008773  nop     dword ptr [rax+rax+00h]
0x180008778  mov     rcx, [rbp+57h+VolumeHandle]; FileHandle
0x18000877c  call    cs:__imp_FltClose
0x180008783  nop     dword ptr [rax+rax+00h]
0x180008788  test    byte ptr [r14+rsi*8+8], 2
0x18000878e  jz      loc_180008949
0x180008794  mov     rdi, [r14+rsi*8+10h]
0x180008799  lea     rcx, [rdi+5Ch]
0x18000879d  cmp     r13d, 2
0x1800087a1  jnz     short loc_1800087B6
0x1800087a3  mov     eax, [rcx]
0x1800087a5  mov     edx, 200h
0x1800087aa  test    edx, eax
0x1800087ac  jnz     loc_180008949
0x1800087b2  or      eax, edx
0x1800087b4  mov     [rcx], eax
0x1800087b6  lea     rax, [rdi+28h]
0x1800087ba  cmp     [rax], rax
0x1800087bd  jz      loc_180008949
0x1800087c3  mov     eax, [rdi+3Ch]
0x1800087c6  test    al, 4
0x1800087c8  jnz     loc_180008949
0x1800087ce  mov     eax, [rcx]
0x1800087d0  test    al, 3
0x1800087d2  jnz     loc_180008949
0x1800087d8  mov     rax, [rdi+68h]
0x1800087dc  lea     rcx, [rbp+57h+Event]; Event
0x1800087e0  mov     qword ptr [rbp+57h+InputBuffer], rax
0x1800087e4  xor     r8d, r8d; State
0x1800087e7  mov     rax, [rdi+78h]
0x1800087eb  xor     edx, edx; Type
0x1800087ed  mov     qword ptr [rbp+57h+InputBuffer+8], rax
0x1800087f1  mov     dword ptr [rbp+57h+var_58], r13d
0x1800087f5  call    cs:__imp_KeInitializeEvent
0x1800087fc  nop     dword ptr [rax+rax+00h]
0x180008801  mov     rdx, [rdi+80h]; DeviceObject
0x180008808  lea     rax, [rbp+57h+var_78]
0x18000880c  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x180008811  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x180008815  lea     rax, [rbp+57h+Event]
0x180008819  mov     r9d, 18h; InputBufferLength
0x18000881f  mov     [rsp+0D0h+var_98], rax; Event
0x180008824  mov     ecx, 2D9198h; IoControlCode
0x180008829  mov     [rsp+0D0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x18000882e  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x180008836  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x18000883f  call    cs:__imp_IoBuildDeviceIoControlRequest
0x180008846  nop     dword ptr [rax+rax+00h]
0x18000884b  mov     rbx, rax
0x18000884e  test    rax, rax
0x180008851  jnz     short loc_180008893
0x180008853  mov     rcx, cs:WPP_GLOBAL_Control
0x18000885a  lea     rax, WPP_GLOBAL_Control
0x180008861  cmp     rcx, rax
0x180008864  jz      short loc_180008889
0x180008866  mov     eax, [rcx+2Ch]
0x180008869  test    al, 1
0x18000886b  jz      short loc_180008889
0x18000886d  cmp     byte ptr [rcx+29h], 2
0x180008871  jb      short loc_180008889
0x180008873  mov     rcx, [rcx+18h]
0x180008877  lea     edx, [rbx+14h]
0x18000887a  mov     r9, rdi
0x18000887d  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008884  call    WPP_SF_q
0x180008889  mov     ebx, 0C000009Ah
0x18000888e  jmp     loc_180008949
0x180008893  test    r15b, r15b
0x180008896  jz      short loc_1800088BA
0x180008898  lea     rcx, Resource; Resource
0x18000889f  call    cs:__imp_ExReleaseResourceLite
0x1800088a6  nop     dword ptr [rax+rax+00h]
0x1800088ab  call    cs:__imp_KeLeaveCriticalRegion
0x1800088b2  nop     dword ptr [rax+rax+00h]
0x1800088b7  xor     r15b, r15b
0x1800088ba  mov     rcx, [rdi+80h]; DeviceObject
0x1800088c1  mov     rdx, rbx; Irp
0x1800088c4  call    cs:__imp_IofCallDriver
0x1800088cb  nop     dword ptr [rax+rax+00h]
0x1800088d0  mov     ebx, eax
0x1800088d2  cmp     eax, 103h
0x1800088d7  jnz     short loc_1800088FD
0x1800088d9  xor     r9d, r9d; Alertable
0x1800088dc  mov     [rsp+0D0h+OutputBuffer], 0; Timeout
0x1800088e5  xor     r8d, r8d; WaitMode
0x1800088e8  lea     rcx, [rbp+57h+Event]; Object
0x1800088ec  xor     edx, edx; WaitReason
0x1800088ee  call    cs:__imp_KeWaitForSingleObject
0x1800088f5  nop     dword ptr [rax+rax+00h]
0x1800088fa  mov     ebx, dword ptr [rbp+57h+var_78]
0x1800088fd  test    ebx, ebx
0x1800088ff  jns     short loc_180008949
0x180008901  mov     rcx, cs:WPP_GLOBAL_Control
0x180008908  lea     rax, WPP_GLOBAL_Control
0x18000890f  cmp     rcx, rax
0x180008912  jz      short loc_18000893E
0x180008914  mov     eax, [rcx+2Ch]
0x180008917  test    al, 1
0x180008919  jz      short loc_18000893E
0x18000891b  cmp     byte ptr [rcx+29h], 2
0x18000891f  jb      short loc_18000893E
0x180008921  mov     rcx, [rcx+18h]
0x180008925  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x18000892c  mov     edx, 15h
0x180008931  mov     [rsp+0D0h+OutputBuffer], rdi
0x180008936  mov     r9d, ebx
0x180008939  call    WPP_SF_Dq
0x18000893e  mov     eax, [rdi+3Ch]
0x180008941  test    al, 10h
0x180008943  jnz     loc_180008A2E
0x180008949  mov     rax, [rbp+57h+P]
0x18000894d  inc     r12d
0x180008950  cmp     r12d, [rax+4]
0x180008954  jb      loc_1800085DA
0x18000895a  test    r15b, r15b
0x18000895d  jnz     short loc_180008984
0x18000895f  mov     r15b, 1
0x180008962  call    cs:__imp_KeEnterCriticalRegion
0x180008969  nop     dword ptr [rax+rax+00h]
0x18000896e  mov     dl, r15b; Wait
0x180008971  lea     rcx, Resource; Resource
0x180008978  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000897f  nop     dword ptr [rax+rax+00h]
0x180008984  mov     rax, [rbp+57h+P]
0x180008988  xor     esi, esi
0x18000898a  cmp     [rax+4], esi
0x18000898d  jbe     short loc_1800089D7
0x18000898f  mov     r14, [rbp+57h+P]
0x180008993  mov     edi, esi
0x180008995  add     rdi, rdi
0x180008998  test    byte ptr [r14+rdi*8+8], 1
0x18000899e  jz      short loc_1800089AF
0x1800089a0  mov     rcx, [r14+rdi*8+10h]
0x1800089a5  test    rcx, rcx
0x1800089a8  jz      short loc_1800089AF
0x1800089aa  call    DereferenceVolumeContext
0x1800089af  test    byte ptr [r14+rdi*8+8], 2
0x1800089b5  jz      short loc_1800089CC
0x1800089b7  mov     rcx, [r14+rdi*8+10h]; P
0x1800089bc  test    rcx, rcx
0x1800089bf  jz      short loc_1800089CC
0x1800089c1  xor     r8d, r8d
0x1800089c4  mov     dl, r15b
0x1800089c7  call    DereferenceDependencyContext
0x1800089cc  mov     rax, [rbp+57h+P]
  ... truncated ...
```
