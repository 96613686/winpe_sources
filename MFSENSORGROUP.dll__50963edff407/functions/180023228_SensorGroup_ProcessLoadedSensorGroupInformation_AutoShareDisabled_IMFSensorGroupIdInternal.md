# SensorGroup::ProcessLoadedSensorGroupInformation_AutoShareDisabled(IMFSensorGroupIdInternal *)

- ea: `0x180023228`
- end: `0x1800236e4`
- name: `?ProcessLoadedSensorGroupInformation_AutoShareDisabled@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFSensorGroupIdInternal *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011a94`

## callees

- `0x180005fa0`
- `0x180023228`
- `0x1800236ec`
- `0x1800243b0`
- `0x18002464c`
- `0x180024680`
- `0x180034d04`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180023394`
- `MFPlat!MFCreateAttributes` at `0x180023394`
- `MFPlat!MFInitAttributesFromBlob` at `0x180023552`
- `MFPlat!MFInitAttributesFromBlob` at `0x180023552`

## pseudocode

```c
__int64 __fastcall SensorGroup::ProcessLoadedSensorGroupInformation_AutoShareDisabled(
        SensorGroup *this,
        struct IMFSensorGroupIdInternal *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  IMFAttributes **v7; // r14
  __int64 v8; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rdx
  rsize_t DestinationSize; // [rsp+60h] [rbp-19h] BYREF
  __int64 v14; // [rsp+68h] [rbp-11h] BYREF
  void *Source; // [rsp+70h] [rbp-9h] BYREF
  UINT8 *pBuf; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int8 *v17; // [rsp+80h] [rbp+7h] BYREF
  __int64 v18; // [rsp+88h] [rbp+Fh] BYREF
  unsigned __int16 *v19; // [rsp+90h] [rbp+17h] BYREF
  void *Destination; // [rsp+98h] [rbp+1Fh] BYREF
  rsize_t SourceSize; // [rsp+E8h] [rbp+6Fh] BYREF
  UINT cbBufSize; // [rsp+F0h] [rbp+77h] BYREF
  int v23; // [rsp+F8h] [rbp+7Fh] BYREF

  v17 = 0;
  v23 = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  Source = 0;
  LODWORD(SourceSize) = 0;
  pBuf = 0;
  cbBufSize = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        204,
        &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        this,
        -2147024809);
    goto LABEL_29;
  }
  v4 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a2 + 192LL))(
         a2,
         3,
         0,
         &v18,
         0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_29;
    v10 = 205;
    goto LABEL_28;
  }
  v4 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)a2 + 192LL))(
         a2,
         14,
         0,
         &v19,
         0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_29;
    v10 = 206;
    goto LABEL_28;
  }
  v4 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, unsigned __int8 **, int *))(*(_QWORD *)a2 + 192LL))(
         a2,
         6,
         0,
         &v17,
         &v23);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, void **, rsize_t *))(*(_QWORD *)a2 + 192LL))(
           a2,
           9,
           0,
           &Source,
           &SourceSize);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 208;
      goto LABEL_28;
    }
    v4 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, UINT8 **, UINT *))(*(_QWORD *)a2 + 192LL))(
           a2,
           5,
           0,
           &pBuf,
           &cbBufSize);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 209;
      goto LABEL_28;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v12 = L"<null>";
      if ( v19 )
        v12 = v19;
      WPP_SF_qqSqDqDqD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_DWORD)v12,
        v6,
        (_DWORD)this,
        v18,
        (__int64)v12,
        (char)v17,
        v23,
        (char)Source,
        SourceSize,
        (char)pBuf,
        cbBufSize);
    }
    v7 = (IMFAttributes **)((char *)this + 72);
    v8 = *((_QWORD *)this + 9);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *v7 = 0;
    }
    v4 = MFCreateAttributes((IMFAttributes **)this + 9, 1u);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 211;
      goto LABEL_28;
    }
    if ( pBuf )
    {
      if ( cbBufSize )
      {
        v4 = MFInitAttributesFromBlob(*v7, pBuf, cbBufSize);
        v5 = v4;
        if ( v4 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_29;
          v10 = 212;
          goto LABEL_28;
        }
      }
    }
    v4 = SensorGroup::BuildDeviceListFromAttributeBlob(
           this,
           a2,
           v19,
           (const struct _GUID *)this + 14,
           *(_DWORD *)(v18 + 84),
           v17,
           v23,
           (unsigned int *)this + 47);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 213;
      goto LABEL_28;
    }
    ComSmartPtr<IMFSensorProfileCollection>::operator=((__int64 *)this + 48);
    v4 = MFCreateSensorProfileCollection((char *)this + 384);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 214;
      goto LABEL_28;
    }
    v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 48))(
           *((_QWORD *)this + 48),
           &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3,
           &v14);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v10 = 215;
      goto LABEL_28;
    }
    if ( Source && (_DWORD)SourceSize )
    {
      Destination = 0;
      LODWORD(DestinationSize) = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **, rsize_t *))(*(_QWORD *)v14 + 88LL))(
             v14,
             (unsigned int)SourceSize,
             &Destination,
             &DestinationSize);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_29;
        v10 = 216;
        goto LABEL_28;
      }
      memcpy_s(Destination, (unsigned int)DestinationSize, Source, (unsigned int)SourceSize);
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 96LL))(v14);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 217;
          goto LABEL_28;
        }
        goto LABEL_29;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 160LL))(v14, 0x40000000);
    }
    if ( (unsigned __int8)byte_18008D62D < 8u )
      goto LABEL_18;
    v11 = 219;
    goto LABEL_59;
  }
  if ( g_wppLevels )
  {
    v10 = 207;
LABEL_28:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v4);
  }
LABEL_29:
  if ( !byte_18008D62D )
    goto LABEL_18;
  v11 = 218;
LABEL_59:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v5);
LABEL_18:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v5;
}

```

## disassembly

```asm
0x180023228  push    rbp
0x18002322a  push    rbx
0x18002322b  push    rsi
0x18002322c  push    rdi
0x18002322d  push    r12
0x18002322f  push    r14
0x180023231  push    r15
0x180023233  lea     rbp, [rsp-27h]
0x180023238  sub     rsp, 0A0h
0x18002323f  xor     r15d, r15d
0x180023242  lea     r12, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180023249  mov     [rbp+57h+var_50], r15
0x18002324d  mov     rsi, rdx
0x180023250  mov     [rbp+57h+arg_18], r15d
0x180023254  mov     rdi, rcx
0x180023257  mov     [rbp+57h+var_68], r15
0x18002325b  mov     [rbp+57h+var_48], r15
0x18002325f  mov     [rbp+57h+var_40], r15
0x180023263  mov     [rbp+57h+Source], r15
0x180023267  mov     dword ptr [rbp+57h+SourceSize], r15d
0x18002326b  mov     [rbp+57h+pBuf], r15
0x18002326f  mov     [rbp+57h+cbBufSize], r15d
0x180023273  test    rdx, rdx
0x180023276  jz      loc_180023582
0x18002327c  mov     rax, [rdx]
0x18002327f  lea     r9, [rbp+57h+var_48]
0x180023283  xor     r8d, r8d
0x180023286  mov     qword ptr [rsp+0D0h+var_B0], r15
0x18002328b  lea     edx, [r15+3]
0x18002328f  mov     rcx, rsi
0x180023292  mov     rax, [rax+0C0h]
0x180023299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002329e  mov     ebx, eax
0x1800232a0  test    eax, eax
0x1800232a2  js      loc_18002359E
0x1800232a8  mov     rax, [rsi]
0x1800232ab  lea     r9, [rbp+57h+var_40]
0x1800232af  xor     r8d, r8d
0x1800232b2  mov     qword ptr [rsp+0D0h+var_B0], r15
0x1800232b7  lea     edx, [r15+0Eh]
0x1800232bb  mov     rcx, rsi
0x1800232be  mov     rax, [rax+0C0h]
0x1800232c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232ca  mov     ebx, eax
0x1800232cc  test    eax, eax
0x1800232ce  js      loc_1800235B1
0x1800232d4  mov     rax, [rsi]
0x1800232d7  lea     rcx, [rbp+57h+arg_18]
0x1800232db  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x1800232e0  lea     r9, [rbp+57h+var_50]
0x1800232e4  xor     r8d, r8d
0x1800232e7  lea     edx, [r15+6]
0x1800232eb  mov     rcx, rsi
0x1800232ee  mov     rax, [rax+0C0h]
0x1800232f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232fa  mov     ebx, eax
0x1800232fc  test    eax, eax
0x1800232fe  js      loc_180023490
0x180023304  mov     rax, [rsi]
0x180023307  lea     rcx, [rbp+57h+SourceSize]
0x18002330b  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180023310  lea     r9, [rbp+57h+Source]
0x180023314  xor     r8d, r8d
0x180023317  lea     edx, [r15+9]
0x18002331b  mov     rcx, rsi
0x18002331e  mov     rax, [rax+0C0h]
0x180023325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002332a  mov     ebx, eax
0x18002332c  test    eax, eax
0x18002332e  js      loc_1800235C8
0x180023334  mov     rax, [rsi]
0x180023337  lea     rcx, [rbp+57h+cbBufSize]
0x18002333b  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180023340  lea     r9, [rbp+57h+pBuf]
0x180023344  xor     r8d, r8d
0x180023347  lea     edx, [r15+5]
0x18002334b  mov     rcx, rsi
0x18002334e  mov     rax, [rax+0C0h]
0x180023355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002335a  mov     ebx, eax
0x18002335c  test    eax, eax
0x18002335e  js      loc_1800235DF
0x180023364  cmp     cs:byte_18008D62D, 8
0x18002336b  jnb     loc_1800235F6
0x180023371  lea     r14, [rdi+48h]
0x180023375  mov     rcx, [r14]
0x180023378  test    rcx, rcx
0x18002337b  jz      short loc_18002338C
0x18002337d  mov     rax, [rcx]
0x180023380  mov     rax, [rax+10h]
0x180023384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023389  mov     [r14], r15
0x18002338c  mov     edx, 1; cInitialSize
0x180023391  mov     rcx, r14; ppMFAttributes
0x180023394  call    cs:__imp_MFCreateAttributes
0x18002339a  mov     ebx, eax
0x18002339c  test    eax, eax
0x18002339e  js      loc_180023661
0x1800233a4  mov     rdx, [rbp+57h+pBuf]; pBuf
0x1800233a8  test    rdx, rdx
0x1800233ab  jnz     loc_180023542
0x1800233b1  mov     r8, [rbp+57h+var_40]; unsigned __int16 *
0x1800233b5  lea     rax, [rdi+0BCh]
0x1800233bc  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x1800233c1  lea     r9, [rdi+0E0h]; struct _GUID *
0x1800233c8  mov     eax, [rbp+57h+arg_18]
0x1800233cb  mov     rdx, rsi; struct IMFSensorGroupIdInternal *
0x1800233ce  mov     [rsp+0D0h+var_A0], eax; int
0x1800233d2  mov     rax, [rbp+57h+var_50]
0x1800233d6  mov     [rsp+0D0h+var_A8], rax; unsigned __int8 *
0x1800233db  mov     rax, [rbp+57h+var_48]
0x1800233df  mov     ecx, [rax+54h]
0x1800233e2  mov     [rsp+0D0h+var_B0], ecx; int
0x1800233e6  mov     rcx, rdi; this
0x1800233e9  call    ?BuildDeviceListFromAttributeBlob@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@PEBGAEBU_GUID@@JPEBEJPEAK@Z; SensorGroup::BuildDeviceListFromAttributeBlob(IMFSensorGroupIdInternal *,ushort const *,_GUID const &,long,uchar const *,long,ulong *)
0x1800233ee  mov     ebx, eax
0x1800233f0  test    eax, eax
0x1800233f2  js      loc_180023572
0x1800233f8  lea     rsi, [rdi+180h]
0x1800233ff  mov     rcx, rsi
0x180023402  call    ??4?$ComSmartPtr@UIMFSensorProfileCollection@@@@QEAAPEAUIMFSensorProfileCollection@@PEAU1@@Z; ComSmartPtr<IMFSensorProfileCollection>::operator=(IMFSensorProfileCollection *)
0x180023407  mov     rcx, rsi
0x18002340a  call    MFCreateSensorProfileCollection
0x18002340f  mov     ebx, eax
0x180023411  test    eax, eax
0x180023413  js      loc_180023678
0x180023419  mov     rcx, [rsi]
0x18002341c  lea     r8, [rbp+57h+var_68]
0x180023420  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180023427  mov     rax, [rcx]
0x18002342a  mov     rax, [rax]
0x18002342d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023432  mov     ebx, eax
0x180023434  test    eax, eax
0x180023436  js      loc_18002368F
0x18002343c  cmp     [rbp+57h+Source], r15
0x180023440  jnz     short loc_1800234A4
0x180023442  mov     rcx, [rbp+57h+var_68]
0x180023446  mov     edx, 40000000h
0x18002344b  mov     rax, [rcx]
0x18002344e  mov     rax, [rax+0A0h]
0x180023455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002345a  cmp     cs:byte_18008D62D, 8
0x180023461  jnb     loc_1800236BD
0x180023467  mov     rcx, [rbp+57h+var_68]
0x18002346b  test    rcx, rcx
0x18002346e  jz      short loc_18002347C
0x180023470  mov     rax, [rcx]
0x180023473  mov     rax, [rax+10h]
0x180023477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002347c  mov     eax, ebx
0x18002347e  add     rsp, 0A0h
0x180023485  pop     r15
0x180023487  pop     r14
0x180023489  pop     r12
0x18002348b  pop     rdi
0x18002348c  pop     rsi
0x18002348d  pop     rbx
0x18002348e  pop     rbp
0x18002348f  retn
0x180023490  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023497  jb      loc_18002352B
0x18002349d  mov     edx, 0CFh
0x1800234a2  jmp     short loc_180023511
0x1800234a4  mov     edx, dword ptr [rbp+57h+SourceSize]
0x1800234a7  test    edx, edx
0x1800234a9  jz      short loc_180023442
0x1800234ab  mov     rcx, [rbp+57h+var_68]
0x1800234af  lea     r9, [rbp+57h+DestinationSize]
0x1800234b3  mov     [rbp+57h+Destination], r15
0x1800234b7  lea     r8, [rbp+57h+Destination]
0x1800234bb  mov     dword ptr [rbp+57h+DestinationSize], r15d
0x1800234bf  mov     rax, [rcx]
0x1800234c2  mov     rax, [rax+58h]
0x1800234c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234cb  mov     ebx, eax
0x1800234cd  test    eax, eax
0x1800234cf  js      loc_1800236A6
0x1800234d5  mov     r9d, dword ptr [rbp+57h+SourceSize]; SourceSize
0x1800234d9  mov     edx, dword ptr [rbp+57h+DestinationSize]; DestinationSize
0x1800234dc  mov     r8, [rbp+57h+Source]; Source
0x1800234e0  mov     rcx, [rbp+57h+Destination]; Destination
0x1800234e4  call    memcpy_s
0x1800234e9  mov     rcx, [rbp+57h+var_68]
0x1800234ed  mov     rax, [rcx]
0x1800234f0  mov     rax, [rax+60h]
0x1800234f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f9  mov     ebx, eax
0x1800234fb  test    eax, eax
0x1800234fd  jns     loc_18002345A
0x180023503  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002350a  jb      short loc_18002352B
0x18002350c  mov     edx, 0D9h
0x180023511  mov     [rsp+0D0h+var_B0], eax
0x180023515  mov     rcx, cs:WPP_GLOBAL_Control
0x18002351c  mov     r9, rdi
0x18002351f  mov     r8, r12
0x180023522  mov     rcx, [rcx+10h]
0x180023526  call    WPP_SF_qD
0x18002352b  cmp     cs:byte_18008D62D, 1
0x180023532  jb      loc_180023467
0x180023538  mov     edx, 0DAh
0x18002353d  jmp     loc_1800236C2
0x180023542  mov     r8d, [rbp+57h+cbBufSize]; cbBufSize
0x180023546  test    r8d, r8d
0x180023549  jz      loc_1800233B1
0x18002354f  mov     rcx, [r14]; pAttributes
0x180023552  call    cs:__imp_MFInitAttributesFromBlob
0x180023558  mov     ebx, eax
0x18002355a  test    eax, eax
0x18002355c  jns     loc_1800233B1
0x180023562  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023569  jb      short loc_18002352B
0x18002356b  mov     edx, 0D4h
0x180023570  jmp     short loc_180023511
0x180023572  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023579  jb      short loc_18002352B
0x18002357b  mov     edx, 0D5h
0x180023580  jmp     short loc_180023511
0x180023582  mov     ebx, 80070057h
0x180023587  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002358e  jb      short loc_18002352B
0x180023590  mov     edx, 0CCh
0x180023595  mov     [rsp+0D0h+var_B0], ebx
0x180023599  jmp     loc_180023515
0x18002359e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800235a5  jb      short loc_18002352B
0x1800235a7  mov     edx, 0CDh
0x1800235ac  jmp     loc_180023511
0x1800235b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800235b8  jb      loc_18002352B
0x1800235be  mov     edx, 0CEh
0x1800235c3  jmp     loc_180023511
0x1800235c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800235cf  jb      loc_18002352B
0x1800235d5  mov     edx, 0D0h
0x1800235da  jmp     loc_180023511
0x1800235df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800235e6  jb      loc_18002352B
0x1800235ec  mov     edx, 0D1h
0x1800235f1  jmp     loc_180023511
0x1800235f6  mov     rax, [rbp+57h+var_40]
0x1800235fa  lea     rdx, aNull_0; "<null>"
0x180023601  mov     rcx, [rbp+57h+var_50]
0x180023605  test    rax, rax
0x180023608  mov     r9, rdi
0x18002360b  cmovnz  rdx, rax
0x18002360f  mov     eax, [rbp+57h+cbBufSize]
0x180023612  mov     [rsp+0D0h+var_78], eax
0x180023616  mov     rax, [rbp+57h+pBuf]
0x18002361a  mov     [rsp+0D0h+var_80], rax
0x18002361f  mov     eax, dword ptr [rbp+57h+SourceSize]
0x180023622  mov     [rsp+0D0h+var_88], eax
0x180023626  mov     rax, [rbp+57h+Source]
0x18002362a  mov     [rsp+0D0h+var_90], rax
0x18002362f  mov     eax, [rbp+57h+arg_18]
0x180023632  mov     dword ptr [rsp+0D0h+var_98], eax
0x180023636  mov     rax, [rbp+57h+var_48]
0x18002363a  mov     qword ptr [rsp+0D0h+var_A0], rcx
0x18002363f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023646  mov     [rsp+0D0h+var_A8], rdx
0x18002364b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180023650  mov     rcx, [rcx+0D8h]
0x180023657  call    WPP_SF_qqSqDqDqD
0x18002365c  jmp     loc_180023371
0x180023661  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023668  jb      loc_18002352B
0x18002366e  mov     edx, 0D3h
0x180023673  jmp     loc_180023511
0x180023678  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002367f  jb      loc_18002352B
0x180023685  mov     edx, 0D6h
0x18002368a  jmp     loc_180023511
0x18002368f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023696  jb      loc_18002352B
0x18002369c  mov     edx, 0D7h
0x1800236a1  jmp     loc_180023511
0x1800236a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800236ad  jb      loc_18002352B
0x1800236b3  mov     edx, 0D8h
0x1800236b8  jmp     loc_180023511
0x1800236bd  mov     edx, 0DBh
0x1800236c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236c9  mov     r9, rdi
0x1800236cc  mov     r8, r12
0x1800236cf  mov     [rsp+0D0h+var_B0], ebx
0x1800236d3  mov     rcx, [rcx+0D8h]
0x1800236da  call    WPP_SF_qD
0x1800236df  jmp     loc_180023467
```
