# CMetadataIPTCReaderWriter::HrSaveEx(IStream *,ulong,int,int)

- ea: `0x1800bdf20`
- end: `0x1800be295`
- name: `?HrSaveEx@CMetadataIPTCReaderWriter@@UEAAJPEAUIStream@@KHH@Z`
- size: `885`
- prototype: `__int64 __usercall@<rax>(CMetadataIPTCReaderWriter *__hidden this@<rcx>, struct IStream *@<rdx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800319d0`
- `0x18003c670`
- `0x18004e5e0`
- `0x1800542e8`
- `0x180055880`
- `0x180055dbc`
- `0x180087478`
- `0x1800a3f68`
- `0x1800a7120`
- `0x1800bd9d4`
- `0x1800bdf20`
- `0x1800d8c30`
- `0x1800d8e60`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be20e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be20e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be265`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be265`

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
  HRESULT IsDeepMetadataDirty; // eax
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
  __int64 v27; // [rsp+48h] [rbp-8h] BYREF
  ULONG pulResult; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v29; // [rsp+98h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+58h]

  v30 = a4;
  v29 = 0;
  v27 = (__int64)this + 40;
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
                              v17);
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
0x1800bdf20  mov     [rsp-38h+arg_10], rbx
0x1800bdf25  mov     [rsp-38h+arg_18], r9d
0x1800bdf2a  push    rbp
0x1800bdf2b  push    rsi
0x1800bdf2c  push    rdi
0x1800bdf2d  push    r12
0x1800bdf2f  push    r13
0x1800bdf31  push    r14
0x1800bdf33  push    r15
0x1800bdf35  mov     rbp, rsp
0x1800bdf38  sub     rsp, 50h
0x1800bdf3c  xor     ebx, ebx
0x1800bdf3e  mov     rdi, rcx
0x1800bdf41  add     rcx, 28h ; '('; this
0x1800bdf45  mov     [rbp+arg_8], ebx
0x1800bdf48  mov     [rbp+var_8], rcx
0x1800bdf4c  mov     r14d, r9d
0x1800bdf4f  mov     rsi, rdx
0x1800bdf52  mov     [rbp+pulResult], ebx
0x1800bdf55  mov     r12d, ebx
0x1800bdf58  mov     [rbp+var_20], rbx
0x1800bdf5c  mov     qword ptr [rbp+ulSubtrahend], rbx
0x1800bdf60  mov     r13d, ebx
0x1800bdf63  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800bdf68  test    rsi, rsi
0x1800bdf6b  jnz     short loc_1800BDF7E
0x1800bdf6d  mov     ebx, 80070057h
0x1800bdf72  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bdf79  jmp     loc_1800BE24A
0x1800bdf7e  mov     r15d, [rbp+arg_20]
0x1800bdf82  test    r15d, r15d
0x1800bdf85  jz      short loc_1800BDFBC
0x1800bdf87  mov     rax, [rsi]
0x1800bdf8a  xor     r9d, r9d
0x1800bdf8d  mov     edx, [rdi+88h]
0x1800bdf93  xor     r8d, r8d
0x1800bdf96  mov     rcx, rsi
0x1800bdf99  mov     rax, [rax+28h]
0x1800bdf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfa2  mov     ebx, eax
0x1800bdfa4  test    eax, eax
0x1800bdfa6  jns     short loc_1800BDFBC
0x1800bdfa8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bdfaf  jz      loc_1800BE253
0x1800bdfb5  mov     ecx, eax
0x1800bdfb7  jmp     loc_1800BE24E
0x1800bdfbc  lea     rdx, [rbp+pulResult]; int *
0x1800bdfc0  mov     rcx, rdi; this
0x1800bdfc3  call    ?IsDeepMetadataDirty@CMetadataHandler@@IEAAJPEAH@Z; CMetadataHandler::IsDeepMetadataDirty(int *)
0x1800bdfc8  xor     ecx, ecx
0x1800bdfca  mov     ebx, eax
0x1800bdfcc  test    eax, eax
0x1800bdfce  jns     short loc_1800BDFD8
0x1800bdfd0  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800bdfd6  jmp     short loc_1800BDFAF
0x1800bdfd8  mov     eax, [rbp+pulResult]
0x1800bdfdb  or      [rdi+0C8h], eax
0x1800bdfe1  mov     rdx, [rdi+108h]; void *
0x1800bdfe8  test    rdx, rdx
0x1800bdfeb  jz      short loc_1800BE01F
0x1800bdfed  mov     r8d, [rdi+110h]; unsigned int
0x1800bdff4  mov     rcx, rsi; struct IStream *
0x1800bdff7  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800bdffc  xor     r15d, r15d
0x1800bdfff  mov     ebx, eax
0x1800be001  test    eax, eax
0x1800be003  jns     loc_1800BE0E1
0x1800be009  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800be010  jnz     short loc_1800BDFB5
0x1800be012  test    eax, eax
0x1800be014  js      loc_1800BE253
0x1800be01a  jmp     loc_1800BE0E1
0x1800be01f  cmp     [rdi+0C8h], ecx
0x1800be025  jnz     loc_1800BE103
0x1800be02b  cmp     [rdi+78h], rcx
0x1800be02f  jz      loc_1800BE103
0x1800be035  mov     eax, [rdi+80h]
0x1800be03b  sub     eax, [rdi+88h]
0x1800be041  mov     ecx, eax; cb
0x1800be043  mov     r14d, eax
0x1800be046  call    cs:__imp_CoTaskMemAlloc
0x1800be04d  nop     dword ptr [rax+rax+00h]
0x1800be052  xor     r15d, r15d
0x1800be055  mov     r12, rax
0x1800be058  test    rax, rax
0x1800be05b  jnz     short loc_1800BE067
0x1800be05d  mov     ebx, 8007000Eh
0x1800be062  jmp     loc_1800BE243
0x1800be067  mov     rcx, [rdi+78h]
0x1800be06b  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800be06e  mov     edx, [rdi+88h]; union _LARGE_INTEGER
0x1800be074  add     rcx, 10h; this
0x1800be078  xor     r8d, r8d; unsigned int
0x1800be07b  call    ?Seek@CStreamBase@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CStreamBase::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800be080  mov     ebx, eax
0x1800be082  test    eax, eax
0x1800be084  jns     short loc_1800BE092
0x1800be086  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800be08d  jmp     loc_1800BDFAF
0x1800be092  mov     rax, [rdi+78h]
0x1800be096  mov     r8d, r14d; unsigned int
0x1800be099  lea     rdx, [rax+10h]
0x1800be09d  neg     rax
0x1800be0a0  sbb     rcx, rcx
0x1800be0a3  and     rcx, rdx; struct IStream *
0x1800be0a6  mov     rdx, r12; void *
0x1800be0a9  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800be0ae  mov     ebx, eax
0x1800be0b0  test    eax, eax
0x1800be0b2  js      short loc_1800BE086
0x1800be0b4  mov     r8d, r14d; unsigned int
0x1800be0b7  mov     rdx, r12; void *
0x1800be0ba  mov     rcx, rsi; struct IStream *
0x1800be0bd  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800be0c2  mov     ebx, eax
0x1800be0c4  test    eax, eax
0x1800be0c6  jns     short loc_1800BE0DD
0x1800be0c8  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800be0cf  jnz     loc_1800BDFB5
0x1800be0d5  test    eax, eax
0x1800be0d7  js      loc_1800BE253
0x1800be0dd  mov     r14d, [rbp+arg_18]
0x1800be0e1  cmp     [rdi+78h], r15
0x1800be0e5  jz      loc_1800BE253
0x1800be0eb  test    r14d, r14d
0x1800be0ee  jz      loc_1800BE253
0x1800be0f4  xor     edx, edx; int
0x1800be0f6  mov     rcx, rdi; this
0x1800be0f9  call    ?SetShallowMetadataDirty@CMetadataIPTCReaderWriter@@MEAAXH@Z; CMetadataIPTCReaderWriter::SetShallowMetadataDirty(int)
0x1800be0fe  jmp     loc_1800BE253
0x1800be103  cmp     [rdi+0C0h], ecx
0x1800be109  jnz     short loc_1800BE11B
0x1800be10b  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800be111  mov     ebx, 88982F81h
0x1800be116  jmp     loc_1800BE24A
0x1800be11b  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800be11f  mov     rcx, rdi; this
0x1800be122  call    ?GetSize@CMetadataIPTCReaderWriter@@AEAAJPEAK@Z; CMetadataIPTCReaderWriter::GetSize(ulong *)
0x1800be127  mov     ebx, eax
0x1800be129  test    eax, eax
0x1800be12b  js      loc_1800BDFA8
0x1800be131  mov     r14d, [rbp+arg_8]
0x1800be135  test    r15d, r15d
0x1800be138  jz      short loc_1800BE163
0x1800be13a  mov     eax, [rdi+80h]
0x1800be140  sub     eax, [rdi+88h]
0x1800be146  test    al, 3
0x1800be148  jz      short loc_1800BE154
0x1800be14a  mov     ebx, 88982F42h
0x1800be14f  jmp     loc_1800BDF72
0x1800be154  cmp     r14d, eax
0x1800be157  jbe     short loc_1800BE163
0x1800be159  mov     ebx, 88982F52h
0x1800be15e  jmp     loc_1800BDF72
0x1800be163  mov     rcx, rdi; this
0x1800be166  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x1800be16b  xor     r15d, r15d
0x1800be16e  mov     ebx, eax
0x1800be170  test    eax, eax
0x1800be172  js      loc_1800BE086
0x1800be178  mov     rax, [rsi]
0x1800be17b  lea     r9, [rbp+ulSubtrahend]
0x1800be17f  mov     rdx, [rbp+var_20]
0x1800be183  lea     r8d, [r15+1]
0x1800be187  mov     rcx, rsi
0x1800be18a  mov     rax, [rax+28h]
0x1800be18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be193  mov     ebx, eax
0x1800be195  test    eax, eax
0x1800be197  js      loc_1800BE086
0x1800be19d  mov     rdx, rsi; struct IStream *
0x1800be1a0  mov     rcx, rdi; this
0x1800be1a3  call    ?WriteFields@CMetadataIPTCReaderWriter@@EEAAJPEAUIStream@@@Z; CMetadataIPTCReaderWriter::WriteFields(IStream *)
0x1800be1a8  mov     ebx, eax
0x1800be1aa  test    eax, eax
0x1800be1ac  js      loc_1800BE086
0x1800be1b2  mov     rax, [rsi]
0x1800be1b5  lea     r9, [rbp+ulMinuend]
0x1800be1b9  mov     rdx, [rbp+var_20]
0x1800be1bd  lea     r8d, [r15+1]
0x1800be1c1  mov     rcx, rsi
0x1800be1c4  mov     qword ptr [rbp+ulMinuend], r15
0x1800be1c8  mov     [rbp+pulResult], r15d
0x1800be1cc  mov     rax, [rax+28h]
0x1800be1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be1d5  mov     ebx, eax
0x1800be1d7  test    eax, eax
0x1800be1d9  js      loc_1800BE086
0x1800be1df  cmp     [rbp+ulSubtrahend+4], r15d
0x1800be1e3  jnz     short loc_1800BE23E
0x1800be1e5  cmp     [rbp+ulMinuend+4], r15d
0x1800be1e9  jnz     short loc_1800BE23E
0x1800be1eb  mov     edx, [rbp+ulSubtrahend]; ulSubtrahend
0x1800be1ee  lea     r8, [rbp+pulResult]; pulResult
0x1800be1f2  mov     ecx, [rbp+ulMinuend]; ulMinuend
0x1800be1f5  call    ULongSub
0x1800be1fa  mov     ebx, eax
0x1800be1fc  test    eax, eax
0x1800be1fe  js      loc_1800BE086
0x1800be204  sub     r14d, [rbp+pulResult]
0x1800be208  mov     ecx, r14d; cb
0x1800be20b  mov     ebx, r14d
0x1800be20e  call    cs:__imp_CoTaskMemAlloc
0x1800be215  nop     dword ptr [rax+rax+00h]
0x1800be21a  mov     r13, rax
0x1800be21d  test    rax, rax
0x1800be220  jz      loc_1800BE05D
0x1800be226  mov     r8d, ebx; Size
0x1800be229  xor     edx, edx; Val
0x1800be22b  mov     rcx, rax; void *
0x1800be22e  call    memset_0
0x1800be233  mov     r8d, ebx
0x1800be236  mov     rdx, r13
0x1800be239  jmp     loc_1800BE0BA
0x1800be23e  mov     ebx, 80004005h
0x1800be243  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800be24a  jz      short loc_1800BE253
0x1800be24c  mov     ecx, ebx; int
0x1800be24e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800be253  mov     rcx, r12; pv
0x1800be256  call    cs:__imp_CoTaskMemFree
0x1800be25d  nop     dword ptr [rax+rax+00h]
0x1800be262  mov     rcx, r13; pv
0x1800be265  call    cs:__imp_CoTaskMemFree
0x1800be26c  nop     dword ptr [rax+rax+00h]
0x1800be271  lea     rcx, [rbp+var_8]
0x1800be275  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800be27a  mov     eax, ebx
0x1800be27c  mov     rbx, [rsp+50h+arg_10]
0x1800be284  add     rsp, 50h
0x1800be288  pop     r15
0x1800be28a  pop     r14
0x1800be28c  pop     r13
0x1800be28e  pop     r12
0x1800be290  pop     rdi
0x1800be291  pop     rsi
0x1800be292  pop     rbp
0x1800be293  retn
```
