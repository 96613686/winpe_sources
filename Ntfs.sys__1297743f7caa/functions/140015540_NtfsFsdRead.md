# NtfsFsdRead

- ea: `0x140015540`
- end: `0x140015b87`
- name: `NtfsFsdRead`
- size: `1607`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140013bb0`
- `0x14001519c`
- `0x1400151d0`
- `0x140015228`
- `0x140015540`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x1400291f0`
- `0x140029d80`
- `0x14002c840`
- `0x140036de4`
- `0x1400592c0`
- `0x140059740`
- `0x14013add0`
- `0x14018a28c`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140015767`
- `ntoskrnl!IoGetStackLimits` at `0x1400159ac`
- `ntoskrnl!IoGetStackLimits` at `0x140015767`
- `ntoskrnl!IoGetStackLimits` at `0x1400159ac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001565a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001597f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001565a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001597f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001590c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001590c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159e5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001568c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001568c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140015619`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140015b44`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140015619`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140015b44`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015708`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015960`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015708`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x140015960`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140015844`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x140015844`
- `HAL!KeQueryPerformanceCounter` at `0x1400156e7`
- `HAL!KeQueryPerformanceCounter` at `0x1400156e7`

## pseudocode

```c
__int64 __fastcall NtfsFsdRead(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  PFILE_OBJECT FileObject; // rax
  int v6; // ecx
  __int64 FsContext; // r15
  unsigned __int8 *FsContext2; // rax
  bool v9; // bl
  __int64 v10; // r13
  BOOLEAN IsOperationSynchronous; // al
  unsigned int v12; // ebx
  __int64 v13; // r9
  _DWORD *v14; // r12
  ULONG_PTR v15; // r14
  __int64 v16; // rdx
  int v17; // edx
  int v18; // edx
  unsigned int v19; // edx
  unsigned int v20; // eax
  __int64 v21; // r9
  __int64 v23; // r8
  __int64 v24; // r9
  void *v25; // rsp
  __int64 v26; // [rsp-30h] [rbp-260h] BYREF
  _DWORD v27[140]; // [rsp+0h] [rbp-230h] BYREF
  int v28; // [rsp+230h] [rbp+0h]
  ULONG_PTR BugCheckParameter2; // [rsp+238h] [rbp+8h] BYREF
  int v30; // [rsp+240h] [rbp+10h] BYREF
  unsigned int v31; // [rsp+244h] [rbp+14h]
  unsigned __int64 LowLimit; // [rsp+248h] [rbp+18h] BYREF
  unsigned __int64 HighLimit; // [rsp+250h] [rbp+20h] BYREF
  _DWORD *v34; // [rsp+258h] [rbp+28h]
  unsigned __int64 v35; // [rsp+260h] [rbp+30h] BYREF
  IRP *v36; // [rsp+268h] [rbp+38h]
  __int64 v37; // [rsp+270h] [rbp+40h]
  _OWORD v38[2]; // [rsp+278h] [rbp+48h] BYREF
  __int64 v39; // [rsp+298h] [rbp+68h]

  memset(v38, 0, sizeof(v38));
  v39 = 0;
  BugCheckParameter2 = 0;
  LOWORD(v31) = 0;
  v30 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v6 = 1;
  FsContext = (__int64)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = (unsigned __int8 *)FileObject->FsContext2;
    if ( FsContext2 )
      v6 = FsContext2[88];
    else
      v6 = 5;
  }
  if ( ((v6 - 2) & 0xFFFFFFFC) != 0 || v6 == 3 )
    FsContext = 0;
  if ( !FsContext )
  {
    v12 = -1073741808;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225488LL, 1835701);
    LOBYTE(a4) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(0, a2, 3221225488LL, a4, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225488LL, 1835702);
    return v12;
  }
  v9 = (*(_DWORD *)(*(_QWORD *)(FsContext + 184) + 4LL) & 4) != 0 && (*(_DWORD *)(FsContext + 200) & 0x10) != 0;
  v10 = NtfsInitializeTopLevelIrp(v38, 2 * (a2->Flags & 2), *(_QWORD *)(FsContext + 192));
  if ( v9 )
  {
    KeEnterCriticalRegion();
    if ( (_OWORD *)v10 == v38 )
      NtfsSetTopLevelWithoutIrpContext(v10);
    v35 = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &v35);
    if ( (unsigned __int64)&v35 - LowLimit <= 0x2000 )
      NtfsPagingFileIoOnNewStack(a2, FsContext);
    else
      NtfsPagingFileIo(a2, FsContext, v23, v24);
    if ( (_OWORD *)v10 == v38 )
      NtfsRestoreTopLevelIrpWithoutContext();
    KeLeaveCriticalRegion();
    return 259;
  }
  IsOperationSynchronous = IoIsOperationSynchronous(a2);
  v12 = NtfsInitializeIrpContextInternal(a2, IsOperationSynchronous, 0, (__int64 *)&BugCheckParameter2);
  if ( v12 == -1073741670
    && IoIsOperationSynchronous(a2)
    && (a2->Flags & 2) != 0
    && a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length <= 0x1000 )
  {
    v25 = alloca(560);
    BugCheckParameter2 = (ULONG_PTR)v27;
    if ( &v26 != (__int64 *)-48LL )
      memset(v27, 0, 0x228u);
    v12 = NtfsInitializeIrpContextInternal(a2, 1, 0, (__int64 *)&BugCheckParameter2);
  }
  if ( (v12 & 0x80000000) != 0 )
  {
    if ( NtfsStatusDebugFlags
      && v12 < 0xFFFFFFED
      && v12 != -1073741802
      && v12 != -1073741807
      && v12 + 2147483643 > 1
      && v12 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v12, 1835736);
    }
    LOBYTE(v13) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(0, a2, v12, v13, (v12 & 0x80000000) == 0);
    return v12;
  }
  v36 = a2;
  v37 = FsContext;
  v14 = 0;
  v34 = 0;
  KeEnterCriticalRegion();
  v15 = BugCheckParameter2;
  v16 = *(_QWORD *)(v10 + 32);
  if ( v16 )
  {
    v17 = *(_DWORD *)(v16 + 436);
    goto LABEL_15;
  }
  *(_DWORD *)(v10 + 4) = 1397118030;
  *(_QWORD *)(v10 + 32) = v15;
  *(_DWORD *)(v15 + 12) |= 0x100000u;
  IoSetTopLevelIrp((PIRP)v10);
  if ( *(_BYTE *)(v10 + 1) )
  {
    v17 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 24) + 32LL) + 436LL);
LABEL_15:
    v18 = *(_DWORD *)(v15 + 432) | v17;
    goto LABEL_16;
  }
  v18 = *(_DWORD *)(v15 + 432);
LABEL_16:
  v19 = v18 & 0xFFFFFBFF;
  *(_DWORD *)(v15 + 432) = v19;
  *(_DWORD *)(v15 + 436) |= v19;
  *(_QWORD *)(v15 + 144) = *(_QWORD *)(v10 + 32);
  if ( *(_BYTE *)(*(_QWORD *)(FsContext + 192) + 10496LL) )
    *(LARGE_INTEGER *)(v15 + 496) = KeQueryPerformanceCounter(0);
  while ( 1 )
  {
    if ( v12 == -1073741432 )
    {
      NtfsCheckpointForLogFileFull(v15);
    }
    else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v12) )
    {
      v30 = 8;
      v31 = v12;
      CcErrorCallbackRoutine(&v30);
    }
    if ( !v15 )
      goto LABEL_36;
    NtfsPreRequestProcessingExtend(v15);
    if ( (*(_BYTE *)(v15 + 33) & 4) == 0 )
    {
      if ( !v14 )
      {
        v14 = &v27[116];
        v34 = &v27[116];
      }
      HighLimit = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&HighLimit - LowLimit <= 0x3000 )
        v20 = NtfsCommonReadOnNewStack(v15, a2, v14, FsContext);
      else
        v20 = NtfsCommonRead(v15, a2, (__int64)v14);
      v28 = v20;
      v12 = v20;
      goto LABEL_36;
    }
    v12 = NtfsCompleteMdl(v15, a2);
    v28 = v12;
    if ( (*(_DWORD *)(FsContext + 512) & 0x1000000) != 0 )
      break;
LABEL_36:
    if ( !v12 || v12 != -1073741608 && v12 != -1073741432 && !(unsigned __int8)CcIsCacheManagerCallbackNeeded(v12) )
      goto LABEL_37;
  }
  v12 = -1073741816;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(v15, 3221225480LL, 1835851);
  LOBYTE(v21) = v36 != 0;
  NtfsExtendedCompleteRequestInternal(v15, a2, 3221225480LL, v21, 0);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225480LL, 1835852);
  v28 = -1073741816;
LABEL_37:
  KeLeaveCriticalRegion();
  return v12;
}

```

## disassembly

```asm
0x140015540  mov     [rsp-8+arg_8], rdx
0x140015545  push    rbp
0x140015546  push    r12
0x140015548  push    r13
0x14001554a  push    r14
0x14001554c  push    r15
0x14001554e  sub     rsp, 0B0h
0x140015555  lea     rbp, [rsp+30h]
0x14001555a  mov     [rbp+0A0h+arg_0], rbx
0x140015561  mov     [rbp+0A0h+arg_10], rsi
0x140015568  mov     rax, cs:__security_cookie
0x14001556f  xor     rax, rbp
0x140015572  mov     [rbp+0A0h+var_30], rax
0x140015576  mov     rsi, rdx
0x140015579  xorps   xmm0, xmm0
0x14001557c  xor     eax, eax
0x14001557e  movups  [rbp+0A0h+var_58], xmm0
0x140015582  movups  [rbp+0A0h+var_48], xmm0
0x140015586  mov     [rbp+0A0h+var_38], rax
0x14001558a  mov     [rbp+0A0h+BugCheckParameter2], rax
0x14001558e  mov     dword ptr [rbp+0A0h+var_90+2], eax
0x140015591  mov     dword ptr [rbp+0A0h+var_90], eax
0x140015594  mov     rax, [rdx+0B8h]
0x14001559b  mov     rax, [rax+30h]
0x14001559f  mov     ecx, 1
0x1400155a4  mov     r15, [rax+18h]
0x1400155a8  test    r15, r15
0x1400155ab  jz      short loc_1400155BE
0x1400155ad  mov     rax, [rax+20h]
0x1400155b1  test    rax, rax
0x1400155b4  jz      loc_140015975
0x1400155ba  movzx   ecx, byte ptr [rax+58h]
0x1400155be  lea     eax, [rcx-2]
0x1400155c1  test    eax, 0FFFFFFFCh
0x1400155c6  jnz     loc_140015B39
0x1400155cc  cmp     ecx, 3
0x1400155cf  jz      loc_140015B39
0x1400155d5  test    r15, r15
0x1400155d8  jz      loc_140015A38
0x1400155de  mov     rax, [r15+0B8h]
0x1400155e5  mov     ecx, [rax+4]
0x1400155e8  test    cl, 4
0x1400155eb  jnz     loc_140015A16
0x1400155f1  xor     bl, bl
0x1400155f3  mov     edx, [rdx+10h]
0x1400155f6  and     edx, 2
0x1400155f9  add     edx, edx
0x1400155fb  mov     r8, [r15+0C0h]
0x140015602  lea     rcx, [rbp+0A0h+var_58]
0x140015606  call    NtfsInitializeTopLevelIrp
0x14001560b  mov     r13, rax
0x14001560e  test    bl, bl
0x140015610  jnz     loc_14001597F
0x140015616  mov     rcx, rsi; Irp
0x140015619  call    cs:__imp_IoIsOperationSynchronous
0x140015620  nop     dword ptr [rax+rax+00h]
0x140015625  lea     r9, [rbp+0A0h+BugCheckParameter2]
0x140015629  xor     r8d, r8d
0x14001562c  mov     dl, al
0x14001562e  mov     rcx, rsi; Irp
0x140015631  call    NtfsInitializeIrpContextInternal
0x140015636  mov     ebx, eax
0x140015638  cmp     eax, 0C000009Ah
0x14001563d  jz      loc_140015B41
0x140015643  test    ebx, ebx
0x140015645  js      loc_140015AD4
0x14001564b  mov     [rbp+0A0h+var_68], rsi
0x14001564f  mov     [rbp+0A0h+var_60], r15
0x140015653  xor     r12d, r12d
0x140015656  mov     [rbp+0A0h+var_78], r12
0x14001565a  call    cs:__imp_KeEnterCriticalRegion
0x140015661  nop     dword ptr [rax+rax+00h]
0x140015666  mov     r14, [rbp+0A0h+BugCheckParameter2]
0x14001566a  mov     rdx, [r13+20h]
0x14001566e  test    rdx, rdx
0x140015671  jnz     loc_140015A0B
0x140015677  mov     dword ptr [r13+4], 5346544Eh
0x14001567f  mov     [r13+20h], r14
0x140015683  bts     dword ptr [r14+0Ch], 14h
0x140015689  mov     rcx, r13; Irp
0x14001568c  call    cs:__imp_IoSetTopLevelIrp
0x140015693  nop     dword ptr [rax+rax+00h]
0x140015698  cmp     [r13+1], r12b
0x14001569c  jz      loc_140015A2C
0x1400156a2  mov     rax, [r13+18h]
0x1400156a6  mov     rcx, [rax+20h]
0x1400156aa  mov     edx, [rcx+1B4h]
0x1400156b0  or      edx, [r14+1B0h]
0x1400156b7  btr     edx, 0Ah
0x1400156bb  mov     [r14+1B0h], edx
0x1400156c2  or      [r14+1B4h], edx
0x1400156c9  mov     rax, [r13+20h]
0x1400156cd  mov     [r14+90h], rax
0x1400156d4  mov     rax, [r15+0C0h]
0x1400156db  mov     cl, [rax+2900h]
0x1400156e1  test    cl, cl
0x1400156e3  jz      short loc_1400156FA
0x1400156e5  xor     ecx, ecx; PerformanceFrequency
0x1400156e7  call    cs:__imp_KeQueryPerformanceCounter
0x1400156ee  nop     dword ptr [rax+rax+00h]
0x1400156f3  mov     [r14+1F0h], rax
0x1400156fa  cmp     ebx, 0C0000188h
0x140015700  jz      loc_14001581F
0x140015706  mov     ecx, ebx
0x140015708  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x14001570f  nop     dword ptr [rax+rax+00h]
0x140015714  test    al, al
0x140015716  jnz     loc_14001582C
0x14001571c  test    r14, r14
0x14001571f  jz      loc_140015862
0x140015725  mov     edx, ebx
0x140015727  mov     rcx, r14
0x14001572a  call    NtfsPreRequestProcessingExtend
0x14001572f  test    byte ptr [r14+21h], 4
0x140015734  jnz     short loc_14001579F
0x140015736  test    r12, r12
0x140015739  jnz     short loc_14001574F
0x14001573b  mov     eax, [rsp+0D0h+var_D0]
0x14001573e  sub     rsp, 60h
0x140015742  lea     r12, [rsp+130h+var_100]
0x140015747  mov     eax, [r12]
0x14001574b  mov     [rbp+0A0h+var_78], r12
0x14001574f  mov     [rbp+0A0h+HighLimit], 0
0x140015757  mov     [rbp+0A0h+LowLimit], 0
0x14001575f  lea     rdx, [rbp+0A0h+HighLimit]; HighLimit
0x140015763  lea     rcx, [rbp+0A0h+LowLimit]; LowLimit
0x140015767  call    cs:__imp_IoGetStackLimits
0x14001576e  nop     dword ptr [rax+rax+00h]
0x140015773  lea     rax, [rbp+0A0h+HighLimit]
0x140015777  sub     rax, [rbp+0A0h+LowLimit]
0x14001577b  mov     r8, r12
0x14001577e  mov     rdx, rsi; int
0x140015781  mov     rcx, r14; int
0x140015784  cmp     rax, 3000h
0x14001578a  jbe     loc_140015855
0x140015790  call    NtfsCommonRead
0x140015795  mov     [rbp+0A0h+var_A0], eax
0x140015798  mov     ebx, eax
0x14001579a  jmp     loc_140015862
0x14001579f  mov     rdx, rsi
0x1400157a2  mov     rcx, r14
0x1400157a5  call    NtfsCompleteMdl
0x1400157aa  mov     ebx, eax
0x1400157ac  mov     [rbp+0A0h+var_A0], eax
0x1400157af  test    dword ptr [r15+200h], 1000000h
0x1400157ba  jz      loc_140015862
0x1400157c0  mov     al, cs:NtfsStatusDebugFlags
0x1400157c6  mov     ebx, 0C0000008h
0x1400157cb  test    al, al
0x1400157cd  jz      short loc_1400157DF
0x1400157cf  mov     r8d, 1C034Bh
0x1400157d5  mov     edx, ebx
0x1400157d7  mov     rcx, r14
0x1400157da  call    NtfsStatusTraceAndDebugInternal
0x1400157df  cmp     [rbp+0A0h+var_68], 0
0x1400157e4  setnz   r9b
0x1400157e8  mov     [rsp+0D0h+var_B0], 0
0x1400157f0  mov     r8d, ebx
0x1400157f3  mov     rdx, rsi
0x1400157f6  mov     rcx, r14
0x1400157f9  call    NtfsExtendedCompleteRequestInternal
0x1400157fe  mov     al, cs:NtfsStatusDebugFlags
0x140015804  test    al, al
0x140015806  jz      short loc_140015817
0x140015808  mov     r8d, 1C034Ch
0x14001580e  mov     edx, ebx
0x140015810  xor     ecx, ecx
0x140015812  call    NtfsStatusTraceAndDebugInternal
0x140015817  mov     [rbp+0A0h+var_A0], ebx
0x14001581a  jmp     loc_14001590C
0x14001581f  mov     rcx, r14
0x140015822  call    NtfsCheckpointForLogFileFull
0x140015827  jmp     loc_14001571C
0x14001582c  mov     [rbp+0A0h+var_90], 0
0x140015834  mov     eax, 8
0x140015839  mov     word ptr [rbp+0A0h+var_90], ax
0x14001583d  mov     dword ptr [rbp+0A0h+var_90+4], ebx
0x140015840  lea     rcx, [rbp+0A0h+var_90]
0x140015844  call    cs:__imp_CcErrorCallbackRoutine
0x14001584b  nop     dword ptr [rax+rax+00h]
0x140015850  jmp     loc_14001571C
0x140015855  mov     r9, r15
0x140015858  call    NtfsCommonReadOnNewStack
0x14001585d  jmp     loc_140015795
0x140015862  jmp     loc_140015908
0x140015867  mov     ebx, eax
0x140015869  mov     al, cs:NtfsStatusDebugFlags
0x14001586f  test    al, al
0x140015871  jz      short loc_1400158C9
0x140015873  test    ebx, ebx
0x140015875  jz      short loc_1400158C9
0x140015877  cmp     ebx, 126h
0x14001587d  jz      short loc_1400158C9
0x14001587f  lea     eax, [rbx-12Ah]
0x140015885  cmp     eax, 1
0x140015888  jbe     short loc_1400158C9
0x14001588a  cmp     ebx, 0FFFFFFEDh
0x14001588d  jnb     short loc_1400158C9
0x14001588f  cmp     ebx, 0C00000D8h
0x140015895  jz      short loc_1400158C9
0x140015897  cmp     ebx, 0C0000016h
0x14001589d  jz      short loc_1400158C9
0x14001589f  cmp     ebx, 0C0000011h
0x1400158a5  jz      short loc_1400158C9
0x1400158a7  lea     eax, [rbx+7FFFFFFBh]
0x1400158ad  cmp     eax, 1
0x1400158b0  jbe     short loc_1400158C9
0x1400158b2  cmp     ebx, 103h
0x1400158b8  jz      short loc_1400158C9
0x1400158ba  mov     r8d, 1C036Ch
0x1400158c0  mov     edx, ebx
0x1400158c2  xor     ecx, ecx
0x1400158c4  call    NtfsStatusTraceAndDebugInternal
0x1400158c9  mov     r14, [rbp+0A0h+BugCheckParameter2]
0x1400158cd  mov     rsi, [rbp+0A0h+arg_8]
0x1400158d4  cmp     ebx, 0C0000123h
0x1400158da  jnz     short loc_1400158ED
0x1400158dc  mov     ebx, 0C0000011h
0x1400158e1  mov     [r14+18h], ebx
0x1400158e5  mov     qword ptr [rsi+38h], 0
0x1400158ed  mov     r8d, ebx
0x1400158f0  mov     rdx, rsi
0x1400158f3  mov     rcx, r14
0x1400158f6  call    NtfsProcessException
0x1400158fb  mov     ebx, eax
0x1400158fd  mov     [rbp+0A0h+var_A0], eax
0x140015900  mov     r15, [rbp+0A0h+var_60]
0x140015904  mov     r12, [rbp+0A0h+var_78]
0x140015908  test    ebx, ebx
0x14001590a  jnz     short loc_140015946
0x14001590c  call    cs:__imp_KeLeaveCriticalRegion
0x140015913  nop     dword ptr [rax+rax+00h]
0x140015918  mov     eax, ebx
0x14001591a  mov     rcx, [rbp+0A0h+var_30]
0x14001591e  xor     rcx, rbp; StackCookie
0x140015921  call    __security_check_cookie
0x140015926  mov     rbx, [rbp+0A0h+arg_0]
0x14001592d  mov     rsi, [rbp+0A0h+arg_10]
0x140015934  lea     rsp, [rbp+80h]
0x14001593b  pop     r15
0x14001593d  pop     r14
0x14001593f  pop     r13
0x140015941  pop     r12
0x140015943  pop     rbp
0x140015944  retn
0x140015946  cmp     ebx, 0C00000D8h
0x14001594c  jz      loc_1400156FA
0x140015952  cmp     ebx, 0C0000188h
0x140015958  jz      loc_1400156FA
0x14001595e  mov     ecx, ebx
0x140015960  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x140015967  nop     dword ptr [rax+rax+00h]
0x14001596c  test    al, al
0x14001596e  jz      short loc_14001590C
0x140015970  jmp     loc_1400156FA
0x140015975  mov     ecx, 5
0x14001597a  jmp     loc_1400155BE
0x14001597f  call    cs:__imp_KeEnterCriticalRegion
0x140015986  nop     dword ptr [rax+rax+00h]
0x14001598b  lea     rax, [rbp+0A0h+var_58]
0x14001598f  cmp     r13, rax
0x140015992  jz      short loc_140015A01
0x140015994  mov     [rbp+0A0h+var_70], 0
0x14001599c  mov     [rbp+0A0h+LowLimit], 0
0x1400159a4  lea     rdx, [rbp+0A0h+var_70]; HighLimit
0x1400159a8  lea     rcx, [rbp+0A0h+LowLimit]; LowLimit
0x1400159ac  call    cs:__imp_IoGetStackLimits
0x1400159b3  nop     dword ptr [rax+rax+00h]
0x1400159b8  lea     rax, [rbp+0A0h+var_70]
0x1400159bc  sub     rax, [rbp+0A0h+LowLimit]
0x1400159c0  mov     rdx, r15; int
0x1400159c3  mov     rcx, rsi; int
0x1400159c6  cmp     rax, 2000h
0x1400159cc  jbe     loc_140015B7D
0x1400159d2  call    NtfsPagingFileIo
0x1400159d7  lea     rax, [rbp+0A0h+var_58]
0x1400159db  cmp     r13, rax
0x1400159de  jnz     short loc_1400159E5
0x1400159e0  call    NtfsRestoreTopLevelIrpWithoutContext
0x1400159e5  call    cs:__imp_KeLeaveCriticalRegion
0x1400159ec  nop     dword ptr [rax+rax+00h]
0x1400159f1  mov     al, cs:NtfsStatusDebugFlags
0x1400159f7  mov     eax, 103h
0x1400159fc  jmp     loc_14001591A
0x140015a01  mov     rcx, r13
0x140015a04  call    NtfsSetTopLevelWithoutIrpContext
0x140015a09  jmp     short loc_140015994
0x140015a0b  mov     edx, [rdx+1B4h]
0x140015a11  jmp     loc_1400156B0
0x140015a16  mov     eax, [r15+0C8h]
0x140015a1d  test    al, 10h
0x140015a1f  jz      loc_1400155F1
0x140015a25  mov     bl, 1
0x140015a27  jmp     loc_1400155F3
0x140015a2c  mov     edx, [r14+1B0h]
0x140015a33  jmp     loc_1400156B7
0x140015a38  mov     al, cs:NtfsStatusDebugFlags
0x140015a3e  mov     ebx, 0C0000010h
0x140015a43  test    al, al
0x140015a45  jz      short loc_140015A56
  ... truncated ...
```
