# CMetadataIPTCReaderWriter::HrSaveEx(IStream *,ulong,int,int)

- ea: `0x1800bbcd0`
- end: `0x1800bc02c`
- name: `?HrSaveEx@CMetadataIPTCReaderWriter@@UEAAJPEAUIStream@@KHH@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(CMetadataIPTCReaderWriter *__hidden this@<rcx>, struct IStream *@<rdx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180022660`
- `0x1800257d0`
- `0x180025d00`
- `0x180032d50`
- `0x180036cb4`
- `0x1800787a0`
- `0x180086fe4`
- `0x1800a116c`
- `0x1800a4d90`
- `0x1800bb784`
- `0x1800bbcd0`
- `0x1800d617c`
- `0x1800d63b0`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbdf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbdf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bc003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bc003`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::HrSaveEx(
        CMetadataIPTCReaderWriter *this,
        struct IStream *a2,
        __int64 a3,
        int a4,
        int a5)
{
  int v6; // r14d
  void *v8; // r12
  void *v9; // r13
  unsigned int v10; // ebx
  bool v11; // zf
  int v12; // r15d
  int IsDeepMetadataDirty; // eax
  bool v14; // zf
  int v15; // ecx
  const void *v16; // rdx
  SIZE_T v17; // r14
  unsigned int v18; // r8d
  const void *v19; // rdx
  unsigned int v20; // r14d
  __int64 v21; // rax
  unsigned int v22; // r14d
  void *v23; // rax
  ULONG ulSubtrahend[2]; // [rsp+38h] [rbp-18h] BYREF
  ULONG ulMinuend[2]; // [rsp+40h] [rbp-10h] BYREF
  char *v27; // [rsp+48h] [rbp-8h] BYREF
  ULONG pulResult; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v29; // [rsp+98h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+58h]

  v30 = a4;
  v29 = 0;
  v27 = (char *)this + 40;
  v6 = a4;
  pulResult = 0;
  v8 = 0;
  *(_QWORD *)ulSubtrahend = 0;
  v9 = 0;
  CMTALock::Enter((CMetadataIPTCReaderWriter *)((char *)this + 40));
  if ( !a2 )
  {
    v10 = -2147024809;
LABEL_3:
    v11 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_49;
  }
  v12 = a5;
  if ( a5 )
  {
    IsDeepMetadataDirty = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                            a2,
                            *((unsigned int *)this + 34),
                            0,
                            0);
    v10 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty < 0 )
      goto LABEL_6;
  }
  IsDeepMetadataDirty = CMetadataHandler::IsDeepMetadataDirty(this, (int *)&pulResult);
  v10 = IsDeepMetadataDirty;
  if ( IsDeepMetadataDirty < 0 )
  {
    v14 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_7;
  }
  *((_DWORD *)this + 50) |= pulResult;
  v16 = (const void *)*((_QWORD *)this + 33);
  if ( v16 )
  {
    IsDeepMetadataDirty = WriteFullBufferToStream(a2, v16, *((_DWORD *)this + 68));
    v10 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_52;
      goto LABEL_8;
    }
    goto LABEL_27;
  }
  if ( *((_DWORD *)this + 50) || !*((_QWORD *)this + 15) )
  {
    if ( !*((_DWORD *)this + 48) )
    {
      v11 = (_DWORD)g_doStackCaptures == 0;
      v10 = -2003292287;
      goto LABEL_49;
    }
    IsDeepMetadataDirty = CMetadataIPTCReaderWriter::GetSize(this, &v29);
    v10 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty < 0 )
    {
LABEL_6:
      v14 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_7;
    }
    v20 = v29;
    if ( v12 )
    {
      if ( ((*((_BYTE *)this + 128) - *((_BYTE *)this + 136)) & 3) != 0 )
      {
        v10 = -2003292350;
        goto LABEL_3;
      }
      if ( v29 > *((_DWORD *)this + 32) - *((_DWORD *)this + 34) )
      {
        v10 = -2003292334;
        goto LABEL_3;
      }
    }
    IsDeepMetadataDirty = CMetadataIPTCReaderWriter::EnsureLoadedValues(this);
    v10 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty >= 0 )
    {
      IsDeepMetadataDirty = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONG *))(*(_QWORD *)a2 + 40LL))(
                              a2,
                              0,
                              1,
                              ulSubtrahend);
      v10 = IsDeepMetadataDirty;
      if ( IsDeepMetadataDirty >= 0 )
      {
        IsDeepMetadataDirty = CMetadataIPTCReaderWriter::WriteFields(this, a2);
        v10 = IsDeepMetadataDirty;
        if ( IsDeepMetadataDirty >= 0 )
        {
          v21 = *(_QWORD *)a2;
          *(_QWORD *)ulMinuend = 0;
          pulResult = 0;
          IsDeepMetadataDirty = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONG *))(v21 + 40))(
                                  a2,
                                  0,
                                  1,
                                  ulMinuend);
          v10 = IsDeepMetadataDirty;
          if ( IsDeepMetadataDirty >= 0 )
          {
            if ( ulSubtrahend[1] || ulMinuend[1] )
            {
              v10 = -2147467259;
              goto LABEL_48;
            }
            IsDeepMetadataDirty = ULongSub(ulMinuend[0], ulSubtrahend[0], &pulResult);
            v10 = IsDeepMetadataDirty;
            if ( IsDeepMetadataDirty >= 0 )
            {
              v22 = v20 - pulResult;
              v23 = CoTaskMemAlloc(v22);
              v9 = v23;
              if ( !v23 )
                goto LABEL_18;
              memset_0(v23, 0, v22);
              v18 = v22;
              v19 = v9;
LABEL_23:
              IsDeepMetadataDirty = WriteFullBufferToStream(a2, v19, v18);
              v10 = IsDeepMetadataDirty;
              if ( IsDeepMetadataDirty < 0 )
              {
                if ( !(_DWORD)g_doStackCaptures )
                  goto LABEL_52;
                goto LABEL_8;
              }
              v6 = v30;
LABEL_27:
              if ( *((_QWORD *)this + 15) && v6 )
                CMetadataIPTCReaderWriter::SetShallowMetadataDirty(this, 0);
              goto LABEL_52;
            }
          }
        }
      }
    }
LABEL_20:
    v14 = (_DWORD)g_doStackCaptures == 0;
LABEL_7:
    if ( v14 )
      goto LABEL_52;
LABEL_8:
    v15 = IsDeepMetadataDirty;
LABEL_51:
    DoStackCapture(v15);
    goto LABEL_52;
  }
  v17 = (unsigned int)(*((_DWORD *)this + 32) - *((_DWORD *)this + 34));
  v8 = CoTaskMemAlloc(v17);
  if ( v8 )
  {
    IsDeepMetadataDirty = CStreamBase::Seek(
                            (CStreamBase *)(*((_QWORD *)this + 15) + 16LL),
                            (union _LARGE_INTEGER)*((unsigned int *)this + 34),
                            0,
                            0);
    v10 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty >= 0 )
    {
      IsDeepMetadataDirty = ReadFullBufferFromStream(
                              (struct IStream *)((*((_QWORD *)this + 15) + 16LL)
                                               & -(__int64)(*((_QWORD *)this + 15) != 0)),
                              v8,
                              (unsigned int)v17);
      v10 = IsDeepMetadataDirty;
      if ( IsDeepMetadataDirty >= 0 )
      {
        v18 = v17;
        v19 = v8;
        goto LABEL_23;
      }
    }
    goto LABEL_20;
  }
LABEL_18:
  v10 = -2147024882;
LABEL_48:
  v11 = (_DWORD)g_doStackCaptures == 0;
LABEL_49:
  if ( !v11 )
  {
    v15 = v10;
    goto LABEL_51;
  }
LABEL_52:
  CoTaskMemFree(v8);
  CoTaskMemFree(v9);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v27);
  return v10;
}

```

## disassembly

```asm
0x1800bbcd0  mov     [rsp-38h+arg_10], rbx
0x1800bbcd5  mov     [rsp-38h+arg_18], r9d
0x1800bbcda  push    rbp
0x1800bbcdb  push    rsi
0x1800bbcdc  push    rdi
0x1800bbcdd  push    r12
0x1800bbcdf  push    r13
0x1800bbce1  push    r14
0x1800bbce3  push    r15
0x1800bbce5  mov     rbp, rsp
0x1800bbce8  sub     rsp, 50h
0x1800bbcec  xor     ebx, ebx
0x1800bbcee  mov     rdi, rcx
0x1800bbcf1  add     rcx, 28h ; '('; this
0x1800bbcf5  mov     [rbp+arg_8], ebx
0x1800bbcf8  mov     [rbp+var_8], rcx
0x1800bbcfc  mov     r14d, r9d
0x1800bbcff  mov     rsi, rdx
0x1800bbd02  mov     [rbp+pulResult], ebx
0x1800bbd05  mov     r12d, ebx
0x1800bbd08  mov     [rbp+var_20], rbx
0x1800bbd0c  mov     qword ptr [rbp+ulSubtrahend], rbx
0x1800bbd10  mov     r13d, ebx
0x1800bbd13  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800bbd18  test    rsi, rsi
0x1800bbd1b  jnz     short loc_1800BBD2E
0x1800bbd1d  mov     ebx, 80070057h
0x1800bbd22  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbd29  jmp     loc_1800BBFEE
0x1800bbd2e  mov     r15d, [rbp+arg_20]
0x1800bbd32  test    r15d, r15d
0x1800bbd35  jz      short loc_1800BBD6C
0x1800bbd37  mov     rax, [rsi]
0x1800bbd3a  xor     r9d, r9d
0x1800bbd3d  mov     edx, [rdi+88h]
0x1800bbd43  xor     r8d, r8d
0x1800bbd46  mov     rcx, rsi
0x1800bbd49  mov     rax, [rax+28h]
0x1800bbd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd52  mov     ebx, eax
0x1800bbd54  test    eax, eax
0x1800bbd56  jns     short loc_1800BBD6C
0x1800bbd58  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbd5f  jz      loc_1800BBFF7
0x1800bbd65  mov     ecx, eax
0x1800bbd67  jmp     loc_1800BBFF2
0x1800bbd6c  lea     rdx, [rbp+pulResult]; int *
0x1800bbd70  mov     rcx, rdi; this
0x1800bbd73  call    ?IsDeepMetadataDirty@CMetadataHandler@@IEAAJPEAH@Z; CMetadataHandler::IsDeepMetadataDirty(int *)
0x1800bbd78  xor     ecx, ecx
0x1800bbd7a  mov     ebx, eax
0x1800bbd7c  test    eax, eax
0x1800bbd7e  jns     short loc_1800BBD88
0x1800bbd80  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800bbd86  jmp     short loc_1800BBD5F
0x1800bbd88  mov     eax, [rbp+pulResult]
0x1800bbd8b  or      [rdi+0C8h], eax
0x1800bbd91  mov     rdx, [rdi+108h]; void *
0x1800bbd98  test    rdx, rdx
0x1800bbd9b  jz      short loc_1800BBDCF
0x1800bbd9d  mov     r8d, [rdi+110h]; unsigned int
0x1800bbda4  mov     rcx, rsi; struct IStream *
0x1800bbda7  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800bbdac  xor     r15d, r15d
0x1800bbdaf  mov     ebx, eax
0x1800bbdb1  test    eax, eax
0x1800bbdb3  jns     loc_1800BBE8B
0x1800bbdb9  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800bbdc0  jnz     short loc_1800BBD65
0x1800bbdc2  test    eax, eax
0x1800bbdc4  js      loc_1800BBFF7
0x1800bbdca  jmp     loc_1800BBE8B
0x1800bbdcf  cmp     [rdi+0C8h], ecx
0x1800bbdd5  jnz     loc_1800BBEAD
0x1800bbddb  cmp     [rdi+78h], rcx
0x1800bbddf  jz      loc_1800BBEAD
0x1800bbde5  mov     eax, [rdi+80h]
0x1800bbdeb  sub     eax, [rdi+88h]
0x1800bbdf1  mov     ecx, eax; cb
0x1800bbdf3  mov     r14d, eax
0x1800bbdf6  call    cs:__imp_CoTaskMemAlloc
0x1800bbdfc  xor     r15d, r15d
0x1800bbdff  mov     r12, rax
0x1800bbe02  test    rax, rax
0x1800bbe05  jnz     short loc_1800BBE11
0x1800bbe07  mov     ebx, 8007000Eh
0x1800bbe0c  jmp     loc_1800BBFE7
0x1800bbe11  mov     rcx, [rdi+78h]
0x1800bbe15  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800bbe18  mov     edx, [rdi+88h]; union _LARGE_INTEGER
0x1800bbe1e  add     rcx, 10h; this
0x1800bbe22  xor     r8d, r8d; unsigned int
0x1800bbe25  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800bbe2a  mov     ebx, eax
0x1800bbe2c  test    eax, eax
0x1800bbe2e  jns     short loc_1800BBE3C
0x1800bbe30  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800bbe37  jmp     loc_1800BBD5F
0x1800bbe3c  mov     rax, [rdi+78h]
0x1800bbe40  mov     r8d, r14d; unsigned int
0x1800bbe43  lea     rdx, [rax+10h]
0x1800bbe47  neg     rax
0x1800bbe4a  sbb     rcx, rcx
0x1800bbe4d  and     rcx, rdx; struct IStream *
0x1800bbe50  mov     rdx, r12; void *
0x1800bbe53  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800bbe58  mov     ebx, eax
0x1800bbe5a  test    eax, eax
0x1800bbe5c  js      short loc_1800BBE30
0x1800bbe5e  mov     r8d, r14d; unsigned int
0x1800bbe61  mov     rdx, r12; void *
0x1800bbe64  mov     rcx, rsi; struct IStream *
0x1800bbe67  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800bbe6c  mov     ebx, eax
0x1800bbe6e  test    eax, eax
0x1800bbe70  jns     short loc_1800BBE87
0x1800bbe72  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800bbe79  jnz     loc_1800BBD65
0x1800bbe7f  test    eax, eax
0x1800bbe81  js      loc_1800BBFF7
0x1800bbe87  mov     r14d, [rbp+arg_18]
0x1800bbe8b  cmp     [rdi+78h], r15
0x1800bbe8f  jz      loc_1800BBFF7
0x1800bbe95  test    r14d, r14d
0x1800bbe98  jz      loc_1800BBFF7
0x1800bbe9e  xor     edx, edx; int
0x1800bbea0  mov     rcx, rdi; this
0x1800bbea3  call    ?SetShallowMetadataDirty@CMetadataIPTCReaderWriter@@MEAAXH@Z; CMetadataIPTCReaderWriter::SetShallowMetadataDirty(int)
0x1800bbea8  jmp     loc_1800BBFF7
0x1800bbead  cmp     [rdi+0C0h], ecx
0x1800bbeb3  jnz     short loc_1800BBEC5
0x1800bbeb5  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800bbebb  mov     ebx, 88982F81h
0x1800bbec0  jmp     loc_1800BBFEE
0x1800bbec5  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800bbec9  mov     rcx, rdi; this
0x1800bbecc  call    ?GetSize@CMetadataIPTCReaderWriter@@AEAAJPEAK@Z; CMetadataIPTCReaderWriter::GetSize(ulong *)
0x1800bbed1  mov     ebx, eax
0x1800bbed3  test    eax, eax
0x1800bbed5  js      loc_1800BBD58
0x1800bbedb  mov     r14d, [rbp+arg_8]
0x1800bbedf  test    r15d, r15d
0x1800bbee2  jz      short loc_1800BBF0D
0x1800bbee4  mov     eax, [rdi+80h]
0x1800bbeea  sub     eax, [rdi+88h]
0x1800bbef0  test    al, 3
0x1800bbef2  jz      short loc_1800BBEFE
0x1800bbef4  mov     ebx, 88982F42h
0x1800bbef9  jmp     loc_1800BBD22
0x1800bbefe  cmp     r14d, eax
0x1800bbf01  jbe     short loc_1800BBF0D
0x1800bbf03  mov     ebx, 88982F52h
0x1800bbf08  jmp     loc_1800BBD22
0x1800bbf0d  mov     rcx, rdi; this
0x1800bbf10  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x1800bbf15  xor     r15d, r15d
0x1800bbf18  mov     ebx, eax
0x1800bbf1a  test    eax, eax
0x1800bbf1c  js      loc_1800BBE30
0x1800bbf22  mov     rax, [rsi]
0x1800bbf25  lea     r9, [rbp+ulSubtrahend]
0x1800bbf29  mov     rdx, [rbp+var_20]
0x1800bbf2d  lea     r8d, [r15+1]
0x1800bbf31  mov     rcx, rsi
0x1800bbf34  mov     rax, [rax+28h]
0x1800bbf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf3d  mov     ebx, eax
0x1800bbf3f  test    eax, eax
0x1800bbf41  js      loc_1800BBE30
0x1800bbf47  mov     rdx, rsi; struct IStream *
0x1800bbf4a  mov     rcx, rdi; this
0x1800bbf4d  call    ?WriteFields@CMetadataIPTCReaderWriter@@EEAAJPEAUIStream@@@Z; CMetadataIPTCReaderWriter::WriteFields(IStream *)
0x1800bbf52  mov     ebx, eax
0x1800bbf54  test    eax, eax
0x1800bbf56  js      loc_1800BBE30
0x1800bbf5c  mov     rax, [rsi]
0x1800bbf5f  lea     r9, [rbp+ulMinuend]
0x1800bbf63  mov     rdx, [rbp+var_20]
0x1800bbf67  lea     r8d, [r15+1]
0x1800bbf6b  mov     rcx, rsi
0x1800bbf6e  mov     qword ptr [rbp+ulMinuend], r15
0x1800bbf72  mov     [rbp+pulResult], r15d
0x1800bbf76  mov     rax, [rax+28h]
0x1800bbf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf7f  mov     ebx, eax
0x1800bbf81  test    eax, eax
0x1800bbf83  js      loc_1800BBE30
0x1800bbf89  cmp     [rbp+ulSubtrahend+4], r15d
0x1800bbf8d  jnz     short loc_1800BBFE2
0x1800bbf8f  cmp     [rbp+ulMinuend+4], r15d
0x1800bbf93  jnz     short loc_1800BBFE2
0x1800bbf95  mov     edx, [rbp+ulSubtrahend]; ulSubtrahend
0x1800bbf98  lea     r8, [rbp+pulResult]; pulResult
0x1800bbf9c  mov     ecx, [rbp+ulMinuend]; ulMinuend
0x1800bbf9f  call    ULongSub
0x1800bbfa4  mov     ebx, eax
0x1800bbfa6  test    eax, eax
0x1800bbfa8  js      loc_1800BBE30
0x1800bbfae  sub     r14d, [rbp+pulResult]
0x1800bbfb2  mov     ecx, r14d; cb
0x1800bbfb5  mov     ebx, r14d
0x1800bbfb8  call    cs:__imp_CoTaskMemAlloc
0x1800bbfbe  mov     r13, rax
0x1800bbfc1  test    rax, rax
0x1800bbfc4  jz      loc_1800BBE07
0x1800bbfca  mov     r8d, ebx; Size
0x1800bbfcd  xor     edx, edx; Val
0x1800bbfcf  mov     rcx, rax; void *
0x1800bbfd2  call    memset_0
0x1800bbfd7  mov     r8d, ebx
0x1800bbfda  mov     rdx, r13
0x1800bbfdd  jmp     loc_1800BBE64
0x1800bbfe2  mov     ebx, 80004005h
0x1800bbfe7  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800bbfee  jz      short loc_1800BBFF7
0x1800bbff0  mov     ecx, ebx; int
0x1800bbff2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bbff7  mov     rcx, r12; pv
0x1800bbffa  call    cs:__imp_CoTaskMemFree
0x1800bc000  mov     rcx, r13; pv
0x1800bc003  call    cs:__imp_CoTaskMemFree
0x1800bc009  lea     rcx, [rbp+var_8]
0x1800bc00d  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800bc012  mov     eax, ebx
0x1800bc014  mov     rbx, [rsp+50h+arg_10]
0x1800bc01c  add     rsp, 50h
0x1800bc020  pop     r15
0x1800bc022  pop     r14
0x1800bc024  pop     r13
0x1800bc026  pop     r12
0x1800bc028  pop     rdi
0x1800bc029  pop     rsi
0x1800bc02a  pop     rbp
0x1800bc02b  retn
```
