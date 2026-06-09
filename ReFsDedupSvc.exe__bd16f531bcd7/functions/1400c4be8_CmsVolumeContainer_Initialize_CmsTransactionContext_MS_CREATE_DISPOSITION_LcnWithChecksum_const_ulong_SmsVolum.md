# CmsVolumeContainer::Initialize(CmsTransactionContext *,_MS_CREATE_DISPOSITION,LcnWithChecksum * * const,ulong,_SmsVolumeContainerKsrContext *)

- ea: `0x1400c4be8`
- end: `0x1400c546c`
- name: `?Initialize@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@QEAPEAULcnWithChecksum@@KPEAU_SmsVolumeContainerKsrContext@@@Z`
- size: `2180`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1400939c8`

## callees

- `0x140004870`
- `0x140004be0`
- `0x140004f44`
- `0x1400057e0`
- `0x1400057f8`
- `0x14004ead4`
- `0x14007e34c`
- `0x14007fe5c`
- `0x14008ae6c`
- `0x140090fb0`
- `0x1400a2a8c`
- `0x1400a76d0`
- `0x1400a8eb4`
- `0x1400aa2ac`
- `0x1400af8e8`
- `0x1400bcc9c`
- `0x1400bd694`
- `0x1400bdb0c`
- `0x1400be2f0`
- `0x1400bf8c0`
- `0x1400c1b30`
- `0x1400c4be8`
- `0x1400c960c`

## import_xrefs

- `ntdll!RtlCreateHashTableEx` at `0x1400c4cdd`
- `ntdll!RtlCreateHashTableEx` at `0x1400c4cdd`
- `ntdll!DbgPrintEx` at `0x1400c51ba`
- `ntdll!DbgPrintEx` at `0x1400c53a3`
- `ntdll!DbgPrintEx` at `0x1400c51ba`
- `ntdll!DbgPrintEx` at `0x1400c53a3`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c513c`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c5187`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c5366`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c513c`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c5187`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400c5366`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CmsVolumeContainer::Initialize(
        __int64 a1,
        struct CmsTransactionContext *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        struct _SmsVolumeContainerKsrContext *a6)
{
  char v6; // bl
  struct CmsTransactionContext *v9; // rdx
  unsigned int DefaultMaxReservedContainerCount; // eax
  CmsVolume **v11; // r12
  void *v12; // rax
  int updated; // r14d
  unsigned __int64 v14; // rcx
  void *v15; // rax
  const struct SmsInternalPropertyDef *PropertyDef; // r13
  __int64 v17; // rcx
  CmsFailoverBPlusTable *PoolWithTagImpl; // rax
  struct CmsBPlusTable *v19; // r8
  struct CmsBPlusTable *v20; // r9
  int result; // eax
  __int64 v22; // rdi
  int v23; // ebx
  struct LcnWithChecksum *v24; // r8
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  struct CmsBPlusTable *v27; // rax
  struct SmsPage *v28; // rdi
  __int64 i; // r9
  __int64 v30; // r9
  __int64 v31; // r10
  CmsFailoverBPlusTable *v32; // rax
  struct SmsPage *v33; // r8
  CmsVolume *v34; // r13
  unsigned int v35; // r9d
  unsigned int v36; // ebx
  int v37; // eax
  bool v38; // zf
  struct CmsBPlusTable *v39; // r13
  int v40; // eax
  unsigned int v41; // ebx
  struct CmsBPlusTable *v42; // rdi
  __int64 v43; // rcx
  __int64 v44; // r14
  unsigned int v45; // r13d
  int v46; // ecx
  unsigned __int64 v47; // rdi
  void *v48; // rbx
  const struct std::nothrow_t *v49; // rdx
  int v50; // eax
  CmsVolume *v51; // rax
  char *v52; // rax
  char v53; // cl
  int v54; // [rsp+28h] [rbp-D8h]
  struct CmsBPlusTable *v55; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v56; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v57[2]; // [rsp+50h] [rbp-B0h] BYREF
  CmsFailoverBPlusTable *v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v59; // [rsp+68h] [rbp-98h]
  __int128 v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  struct _SmsVolumeContainerKsrContext *v63; // [rsp+90h] [rbp-70h]
  _QWORD v64[2]; // [rsp+98h] [rbp-68h]
  struct SmsPage *v65[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-48h]
  __int64 v67; // [rsp+C8h] [rbp-38h]
  _BYTE v68[208]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v69[16]; // [rsp+1A0h] [rbp+A0h] BYREF

  v57[0] = a4;
  v6 = a3;
  v56 = a3;
  v63 = a6;
  v55 = 0;
  v60 = 0;
  v64[0] = 11;
  v64[1] = 12;
  `vector constructor iterator'(v69, 0x40u, 2u, (void *(*)(void *))_RANGE_TUPLE::_RANGE_TUPLE);
  DefaultMaxReservedContainerCount = *(_DWORD *)(a1 + 328);
  v11 = (CmsVolume **)(a1 + 8);
  if ( !DefaultMaxReservedContainerCount )
  {
    DefaultMaxReservedContainerCount = CmsVolume::GetDefaultMaxReservedContainerCount(*v11, v9);
    *(_DWORD *)(a1 + 328) = DefaultMaxReservedContainerCount;
  }
  *(_DWORD *)(a1 + 464) = 0;
  v12 = operator new[](saturated_mul(DefaultMaxReservedContainerCount, 8u));
  *(_QWORD *)(a1 + 456) = v12;
  memset_0(v12, 0, 8LL * *(unsigned int *)(a1 + 328));
  if ( !(unsigned __int8)RtlCreateHashTableEx(a1 + 48, 0x10000, 0, 0) )
    return -1073741670;
  v14 = (*((__int64 *)*v11 + 7) >> *((_DWORD *)*v11 + 20)) + 1;
  *(_QWORD *)(a1 + 24) = v14;
  v15 = operator new[](saturated_mul(v14, 8u));
  *(_QWORD *)(a1 + 32) = v15;
  memset_0(v15, 0, 8LL * *(_QWORD *)(a1 + 24));
  PropertyDef = CmsSchemaTable::GetPropertyDef(*(CmsSchemaTable **)(*((_QWORD *)a2 + 1) + 3272LL), 0xE0C0u);
  PoolWithTagImpl = (CmsFailoverBPlusTable *)MsAllocatePoolWithTagImpl(v17, 112, 1651790669);
  v58 = PoolWithTagImpl;
  if ( PoolWithTagImpl )
    PoolWithTagImpl = CmsFailoverBPlusTable::CmsFailoverBPlusTable(PoolWithTagImpl, PropertyDef, v19, v20);
  *(_QWORD *)(a1 + 16) = PoolWithTagImpl;
  if ( !PoolWithTagImpl )
    return -1073741670;
  v22 = 0;
  v23 = v6 & 1;
  do
  {
    v24 = *(struct LcnWithChecksum **)(v57[0] + 8 * v22);
    if ( v23 )
    {
      v25 = 4;
      if ( *((_DWORD *)*v11 + 16) != 12 )
        v25 = 1;
      v26 = (unsigned __int64)(unsigned int)v22 << 6;
      *(_QWORD *)((char *)v69 + v26) = *(_QWORD *)v24;
      *(_QWORD *)((char *)&v69[1] + v26) = v25;
      *(_OWORD *)((char *)&v69[2] + v26) = 0;
      *(_OWORD *)((char *)&v69[4] + v26) = 0;
      *(_OWORD *)((char *)&v69[6] + v26) = 0;
    }
    result = CmsTableFactory::ProduceBTableObject(
               a2,
               PropertyDef,
               v24,
               0,
               *((_DWORD *)*v11 + 809) >> *((_DWORD *)*v11 + 16),
               0,
               &v55);
    if ( result < 0 )
      return result;
    v27 = v55;
    *((_WORD *)v55 + 104) = *(unsigned __int8 *)(*((_QWORD *)a2 + 1) + 88LL);
    *((_BYTE *)v27 + 14) |= 0xC0u;
    *((_BYTE *)v27 + 15) |= 0x40u;
    *((_QWORD *)&v60 + v22) = v27;
    v22 = (unsigned int)(v22 + 1);
  }
  while ( (unsigned int)v22 < 2 );
  v28 = 0;
  for ( i = 0; i != 2; i = v31 + v30 )
  {
    v57[0] = 0;
    v57[1] = v64[i];
    CmsFailoverBPlusTable::AddTable(*(_QWORD *)(a1 + 16), *((_QWORD *)&v60 + i), v57);
  }
  updated = CmsFailoverBPlusTable::InitializeTables(*(_QWORD *)(a1 + 16), a2, v56);
  if ( updated >= 0 )
  {
    if ( v23 )
    {
      memset_0((void *)(a1 + 80), 0, 0xC0u);
      *(_QWORD *)(a1 + 72) = 1;
      *(_QWORD *)(a1 + 80) = (1LL << (61 - *((_BYTE *)*v11 + 80))) - 256;
      *(_DWORD *)(a1 + 112) = 8;
      updated = CmsFailoverBPlusTable::UpdateDataWithRoot(
                  *(CmsFailoverBPlusTable **)(a1 + 16),
                  a2,
                  (const void *)(a1 + 72),
                  0xC8u,
                  0,
                  0);
      if ( updated < 0 )
        return updated;
LABEL_63:
      v51 = *v11;
      if ( (*((_BYTE *)*v11 + 3284) & 2) != 0 )
        goto LABEL_67;
      if ( !*(_DWORD *)(a1 + 160) )
      {
        *(_DWORD *)(a1 + 160) = 1;
        *(_BYTE *)(a1 + 720) |= 2u;
      }
      if ( (*((_BYTE *)v51 + 3284) & 2) != 0 )
      {
LABEL_67:
        v52 = (char *)(a1 + 720);
      }
      else
      {
        v52 = (char *)(a1 + 720);
        if ( *(_DWORD *)(a1 + 192) )
        {
          v53 = *(_BYTE *)(a1 + 720);
        }
        else
        {
          *(_DWORD *)(a1 + 192) = 432000;
          *v52 |= 2u;
          v53 = *v52;
        }
        if ( !*(_DWORD *)(a1 + 196) )
        {
          *(_DWORD *)(a1 + 196) = 20;
          v52 = (char *)(a1 + 720);
          v53 |= 2u;
          *(_BYTE *)(a1 + 720) = v53;
        }
        if ( !*(_DWORD *)(a1 + 200) )
        {
          *(_DWORD *)(a1 + 200) = 600;
          *v52 = v53 | 2;
        }
      }
      *v52 |= 1u;
      return updated;
    }
    v58 = 0;
    v56 = 0;
    *(_OWORD *)v65 = 0;
    v66 = 0;
    v67 = 0;
    updated = CmsFailoverBPlusTable::PinDataWithRoot(*(_QWORD *)(a1 + 16), a2, 0, &v58, &v56, v65);
    if ( updated >= 0 )
    {
      v32 = v58;
      *(_OWORD *)(a1 + 72) = *(_OWORD *)v58;
      *(_OWORD *)(a1 + 88) = *((_OWORD *)v32 + 1);
      *(_OWORD *)(a1 + 104) = *((_OWORD *)v32 + 2);
      *(_OWORD *)(a1 + 120) = *((_OWORD *)v32 + 3);
      *(_OWORD *)(a1 + 136) = *((_OWORD *)v32 + 4);
      *(_OWORD *)(a1 + 152) = *((_OWORD *)v32 + 5);
      *(_OWORD *)(a1 + 168) = *((_OWORD *)v32 + 6);
      *(_OWORD *)(a1 + 184) = *((_OWORD *)v32 + 7);
      *(_OWORD *)(a1 + 200) = *((_OWORD *)v32 + 8);
      *(_OWORD *)(a1 + 216) = *((_OWORD *)v32 + 9);
      *(_OWORD *)(a1 + 232) = *((_OWORD *)v32 + 10);
      *(_OWORD *)(a1 + 248) = *((_OWORD *)v32 + 11);
      *(_QWORD *)(a1 + 264) = *((_QWORD *)v32 + 24);
    }
    v33 = v65[0];
    if ( !v65[0] )
    {
LABEL_40:
      if ( updated < 0 )
        return updated;
      v39 = 0;
      v57[0] = 0;
      v40 = *(_DWORD *)(a1 + 104);
      if ( v40 )
      {
        v41 = v40 + 1;
        v59 = (unsigned int)(v40 + 1);
        v42 = (struct CmsBPlusTable *)operator new[](saturated_mul(v59, 0x18u));
        v55 = v42;
        `vector constructor iterator'(v42, 0x18u, v41, (void *(*)(void *))_SmsStorageTierRange::_SmsStorageTierRange);
        *(_QWORD *)(a1 + 288) = v42;
        v43 = (unsigned int)(*(_DWORD *)(a1 + 104) + 1);
        *(_DWORD *)(a1 + 336) = v43;
        memset_0(v42, 0, 24 * v43);
      }
      if ( byte_140220070 )
      {
        v55 = 0;
        RtlQueryPerformanceCounter(&v55);
        v39 = v55;
        v57[0] = v55;
      }
      if ( v63 )
      {
        updated = CmsVolumeContainer::RestoreContext((CmsVolumeContainer *)a1, v63);
        if ( updated >= 0 )
        {
          *(_BYTE *)(a1 + 274) = 1;
          if ( byte_140220070 )
          {
            v55 = 0;
            RtlQueryPerformanceCounter(&v55);
            DbgPrintEx(
              0x65u,
              0,
              "[KSR] Container context restored in %lld ms.\n\n",
              1000 * (v55 - v39) / MsQpcFrequency);
          }
        }
      }
      if ( !*(_BYTE *)(a1 + 274) )
      {
        CmsContainerCursor::CmsContainerCursor((CmsContainerCursor *)v68);
        v60 = 0;
        v61 = 0;
        v62 = 0;
        while ( 1 )
        {
          LOBYTE(v54) = 0;
          v50 = CmsTable::Enumerate(*(_QWORD *)(a1 + 16), a2, v68, &v60, 261, v54);
          updated = v50;
          if ( v50 < 0 )
            break;
          v44 = v62;
          if ( (*(_BYTE *)(v62 + 20) & 8) == 0 )
          {
            v45 = 16 * *(_DWORD *)(a1 + 380);
            while ( 1 )
            {
              v46 = *((_DWORD *)*v11 + 20);
              if ( *(_QWORD *)(v44 + v45 + 80) >> v46 < *(_QWORD *)(a1 + 24) )
                break;
              *(_DWORD *)(*((_QWORD *)a2 + 1) + 3284LL) |= 0x80000000;
              v47 = *(_QWORD *)(a1 + 24) + (*((__int64 *)*v11 + 7) >> *((_DWORD *)*v11 + 20));
              v48 = operator new[](saturated_mul(v47, 8u));
              memset_0(v48, 0, 8 * v47);
              memcpy_0(v48, *(const void **)(a1 + 32), 8LL * *(_QWORD *)(a1 + 24));
              operator delete(*(void **)(a1 + 32), v49);
              *(_QWORD *)(a1 + 32) = v48;
              *(_QWORD *)(a1 + 24) = v47;
            }
            *(_QWORD *)(*(_QWORD *)(a1 + 32)
                      + 8LL * (*(_QWORD *)((unsigned int)(16 * *(_DWORD *)(a1 + 380)) + v44 + 80) >> v46)) = *(_QWORD *)v44;
            v39 = (struct CmsBPlusTable *)v57[0];
            if ( (*(_DWORD *)(v44 + 20) & 0x40) != 0 )
            {
              updated = CmsVolumeContainer::AddReservedContainer(
                          (CmsVolumeContainer *)a1,
                          a2,
                          (const struct _RANGE *)(v44 + (unsigned int)(16 * *(_DWORD *)(a1 + 380)) + 80LL),
                          0,
                          (*(_DWORD *)(v44 + 20) & 0x400) != 0);
              if ( updated < 0 )
                goto LABEL_57;
            }
          }
        }
        if ( v50 != -1073741197 )
        {
LABEL_57:
          CmsTableCursorBase::~CmsTableCursorBase((CmsTableCursorBase *)v68);
          return updated;
        }
        CmsTableCursorBase::CleanCursorAfterEnumerate((CmsTableCursorBase *)v68, a2);
        updated = 0;
        CmsTableCursorBase::~CmsTableCursorBase((CmsTableCursorBase *)v68);
      }
      if ( byte_140220070 )
      {
        v57[0] = 0;
        RtlQueryPerformanceCounter(v57);
        DbgPrintEx(
          0x65u,
          0,
          "[KSR context restored = %d] Container context restored in %lld ms.\n\n",
          *(unsigned __int8 *)(a1 + 274),
          1000LL * (v57[0] - (_QWORD)v39) / MsQpcFrequency);
      }
      goto LABEL_63;
    }
    v34 = (CmsVolume *)*((_QWORD *)a2 + 1);
    v35 = 3;
    while ( 1 )
    {
      v36 = v35;
      if ( *((_QWORD *)v33 + 38) )
      {
        if ( (v35 & 1) != 0 && *((_DWORD *)v33 + 96) == *((_DWORD *)v33 + 78) )
        {
          v28 = (struct SmsPage *)*((_QWORD *)v33 + 38);
          if ( (v35 & 4) == 0 )
            goto LABEL_36;
          v37 = *((_DWORD *)v33 + 79);
          if ( *((_DWORD *)v33 + 97) != v37 )
          {
            v36 = v35 & 0xFFFFFFFB;
            goto LABEL_36;
          }
LABEL_35:
          *((_DWORD *)v33 + 79) = v37 - 1;
LABEL_36:
          v38 = (*((_DWORD *)v33 + 78))-- == 1;
          if ( v38 )
            *((_QWORD *)v33 + 38) = 0;
          goto LABEL_38;
        }
        if ( (v35 & 4) != 0 )
        {
          v37 = *((_DWORD *)v33 + 79);
          if ( *((_DWORD *)v33 + 97) == v37 )
          {
            v28 = (struct SmsPage *)*((_QWORD *)v33 + 38);
            goto LABEL_35;
          }
        }
      }
LABEL_38:
      CmsVolume::UnpinInternal(v34, a2, v33, v35);
      v33 = v28;
      v35 = v36;
      v38 = v28 == 0;
      v28 = 0;
      if ( v38 )
      {
        v65[0] = 0;
        goto LABEL_40;
      }
    }
  }
  return updated;
}

```

## disassembly

```asm
0x1400c4be8  push    rbp
0x1400c4bea  push    rbx
0x1400c4beb  push    rsi
0x1400c4bec  push    rdi
0x1400c4bed  push    r12
0x1400c4bef  push    r13
0x1400c4bf1  push    r14
0x1400c4bf3  push    r15
0x1400c4bf5  lea     rbp, [rsp-138h]
0x1400c4bfd  sub     rsp, 238h
0x1400c4c04  mov     rax, cs:__security_cookie
0x1400c4c0b  xor     rax, rsp
0x1400c4c0e  mov     [rbp+170h+var_50], rax
0x1400c4c15  mov     [rsp+270h+var_220], r9
0x1400c4c1a  mov     ebx, r8d
0x1400c4c1d  mov     [rsp+270h+var_228], ebx
0x1400c4c21  mov     r15, rdx
0x1400c4c24  mov     rsi, rcx
0x1400c4c27  mov     rax, [rbp+170h+arg_28]
0x1400c4c2e  mov     [rbp+170h+var_1E0], rax
0x1400c4c32  mov     [rsp+270h+var_230], 0
0x1400c4c3b  xorps   xmm0, xmm0
0x1400c4c3e  movups  [rsp+270h+var_200], xmm0
0x1400c4c43  mov     [rbp+170h+var_1D8], 0Bh
0x1400c4c4b  mov     [rbp+170h+var_1D0], 0Ch
0x1400c4c53  lea     r9, ??0_RANGE_TUPLE@@QEAA@XZ; void *(*)(void *)
0x1400c4c5a  mov     edx, 40h ; '@'; unsigned __int64
0x1400c4c5f  lea     r8d, [rdx-3Eh]; unsigned __int64
0x1400c4c63  lea     rcx, [rbp+170h+var_D0]; void *
0x1400c4c6a  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400c4c6f  mov     eax, [rsi+148h]
0x1400c4c75  lea     r12, [rsi+8]
0x1400c4c79  test    eax, eax
0x1400c4c7b  jnz     short loc_1400C4C8C
0x1400c4c7d  mov     rcx, [r12]; this
0x1400c4c81  call    ?GetDefaultMaxReservedContainerCount@CmsVolume@@QEAAKPEAVCmsTransactionContext@@@Z; CmsVolume::GetDefaultMaxReservedContainerCount(CmsTransactionContext *)
0x1400c4c86  mov     [rsi+148h], eax
0x1400c4c8c  mov     dword ptr [rsi+1D0h], 0
0x1400c4c96  mov     ecx, eax
0x1400c4c98  mov     edi, 8
0x1400c4c9d  mov     eax, edi
0x1400c4c9f  mul     rcx
0x1400c4ca2  lea     r14, [rdi-9]
0x1400c4ca6  cmovb   rax, r14
0x1400c4caa  mov     rcx, rax; unsigned __int64
0x1400c4cad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400c4cb2  mov     [rsi+1C8h], rax
0x1400c4cb9  mov     r8d, [rsi+148h]
0x1400c4cc0  shl     r8, 3; Size
0x1400c4cc4  xor     edx, edx; Val
0x1400c4cc6  mov     rcx, rax; void *
0x1400c4cc9  call    memset_0
0x1400c4cce  lea     rcx, [rsi+30h]
0x1400c4cd2  xor     r9d, r9d
0x1400c4cd5  xor     r8d, r8d
0x1400c4cd8  mov     edx, 10000h
0x1400c4cdd  call    cs:__imp_RtlCreateHashTableEx
0x1400c4ce4  nop     dword ptr [rax+rax+00h]
0x1400c4ce9  test    al, al
0x1400c4ceb  jnz     short loc_1400C4CF8
0x1400c4ced  mov     r14d, 0C000009Ah
0x1400c4cf3  jmp     loc_1400C5445
0x1400c4cf8  mov     rcx, [r12]
0x1400c4cfc  mov     rax, [rcx+38h]
0x1400c4d00  mov     ecx, [rcx+50h]
0x1400c4d03  sar     rax, cl
0x1400c4d06  lea     rcx, [rax+1]
0x1400c4d0a  mov     [rsi+18h], rcx
0x1400c4d0e  mov     rax, rdi
0x1400c4d11  mul     rcx
0x1400c4d14  cmovb   rax, r14
0x1400c4d18  mov     rcx, rax; unsigned __int64
0x1400c4d1b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400c4d20  mov     [rsi+20h], rax
0x1400c4d24  mov     r8, [rsi+18h]
0x1400c4d28  shl     r8, 3; Size
0x1400c4d2c  xor     edx, edx; Val
0x1400c4d2e  mov     rcx, rax; void *
0x1400c4d31  call    memset_0
0x1400c4d36  mov     rcx, [r15+8]
0x1400c4d3a  mov     edx, 0E0C0h; unsigned int
0x1400c4d3f  mov     rcx, [rcx+0CC8h]; this
0x1400c4d46  call    ?GetPropertyDef@CmsSchemaTable@@QEBAPEBUSmsInternalPropertyDef@@K@Z; CmsSchemaTable::GetPropertyDef(ulong)
0x1400c4d4b  mov     r13, rax
0x1400c4d4e  mov     edx, 70h ; 'p'
0x1400c4d53  mov     r8d, 6274534Dh
0x1400c4d59  call    ?MsAllocatePoolWithTagImpl@@YAPEAXW4_MS_POOL_TYPE@@_KK@Z; MsAllocatePoolWithTagImpl(_MS_POOL_TYPE,unsigned __int64,ulong)
0x1400c4d5e  mov     [rsp+270h+var_210], rax
0x1400c4d63  test    rax, rax
0x1400c4d66  jz      short loc_1400C4D73
0x1400c4d68  mov     rdx, r13; struct SmsInternalPropertyDef *
0x1400c4d6b  mov     rcx, rax; this
0x1400c4d6e  call    ??0CmsFailoverBPlusTable@@QEAA@AEBUSmsInternalPropertyDef@@PEAVCmsBPlusTable@@1@Z; CmsFailoverBPlusTable::CmsFailoverBPlusTable(SmsInternalPropertyDef const &,CmsBPlusTable *,CmsBPlusTable *)
0x1400c4d73  mov     [rsi+10h], rax
0x1400c4d77  test    rax, rax
0x1400c4d7a  jnz     short loc_1400C4D86
0x1400c4d7c  mov     eax, 0C000009Ah
0x1400c4d81  jmp     loc_1400C5448
0x1400c4d86  xor     edi, edi
0x1400c4d88  lea     r10d, [rdi+1]
0x1400c4d8c  and     ebx, r10d
0x1400c4d8f  mov     edx, edi
0x1400c4d91  lea     r14, ds:0[rdi*8]
0x1400c4d99  mov     rax, [rsp+270h+var_220]
0x1400c4d9e  mov     r8, [rax+r14]; struct LcnWithChecksum *
0x1400c4da2  test    ebx, ebx
0x1400c4da4  jz      short loc_1400C4DE9
0x1400c4da6  mov     rax, [r12]
0x1400c4daa  mov     ecx, 4
0x1400c4daf  cmp     dword ptr [rax+40h], 0Ch
0x1400c4db3  cmovnz  rcx, r10
0x1400c4db7  shl     rdx, 6
0x1400c4dbb  mov     rax, [r8]
0x1400c4dbe  mov     [rbp+rdx+170h+var_D0], rax
0x1400c4dc6  mov     [rbp+rdx+170h+var_C8], rcx
0x1400c4dce  xorps   xmm0, xmm0
0x1400c4dd1  movups  [rbp+rdx+170h+var_C0], xmm0
0x1400c4dd9  movups  [rbp+rdx+170h+var_B0], xmm0
0x1400c4de1  movups  [rbp+rdx+170h+var_A0], xmm0
0x1400c4de9  mov     rcx, [r12]
0x1400c4ded  mov     eax, [rcx+0CA4h]
0x1400c4df3  mov     ecx, [rcx+40h]
0x1400c4df6  shr     eax, cl
0x1400c4df8  lea     rcx, [rsp+270h+var_230]
0x1400c4dfd  mov     [rsp+270h+var_240], rcx; struct CmsBPlusTable **
0x1400c4e02  mov     byte ptr [rsp+270h+var_248], 0; unsigned __int8
0x1400c4e07  mov     dword ptr [rsp+270h+var_250], eax; unsigned int
0x1400c4e0b  xor     r9d, r9d; union _LCN_TUPLE *
0x1400c4e0e  mov     rdx, r13; struct SmsInternalPropertyDef *
0x1400c4e11  mov     rcx, r15; struct CmsTransactionContext *
0x1400c4e14  call    ?ProduceBTableObject@CmsTableFactory@@SAJPEAVCmsTransactionContext@@AEBUSmsInternalPropertyDef@@PEAULcnWithChecksum@@PEBT_LCN_TUPLE@@KEPEAPEAVCmsBPlusTable@@@Z; CmsTableFactory::ProduceBTableObject(CmsTransactionContext *,SmsInternalPropertyDef const &,LcnWithChecksum *,_LCN_TUPLE const *,ulong,uchar,CmsBPlusTable * *)
0x1400c4e19  test    eax, eax
0x1400c4e1b  js      loc_1400C5448
0x1400c4e21  mov     rax, [r15+8]
0x1400c4e25  movzx   ecx, byte ptr [rax+58h]
0x1400c4e29  mov     rax, [rsp+270h+var_230]
0x1400c4e2e  mov     [rax+0D0h], cx
0x1400c4e35  or      byte ptr [rax+0Eh], 0C0h
0x1400c4e39  or      byte ptr [rax+0Fh], 40h
0x1400c4e3d  mov     qword ptr [rsp+r14+270h+var_200], rax
0x1400c4e42  mov     r10d, 1
0x1400c4e48  add     edi, r10d
0x1400c4e4b  cmp     edi, 2
0x1400c4e4e  jb      loc_1400C4D8F
0x1400c4e54  xor     edi, edi
0x1400c4e56  mov     r9d, edi
0x1400c4e59  mov     [rsp+270h+var_220], rdi
0x1400c4e5e  mov     rax, [rbp+r9*8+170h+var_1D8]
0x1400c4e63  mov     [rsp+270h+var_218], rax
0x1400c4e68  lea     r8, [rsp+270h+var_220]
0x1400c4e6d  mov     rdx, qword ptr [rsp+r9*8+270h+var_200]
0x1400c4e72  mov     rcx, [rsi+10h]
0x1400c4e76  call    ?AddTable@CmsFailoverBPlusTable@@QEAAJPEAVCmsBPlusTable@@TSmsBigIdentifier@@@Z; CmsFailoverBPlusTable::AddTable(CmsBPlusTable *,SmsBigIdentifier)
0x1400c4e7b  add     r9, r10
0x1400c4e7e  cmp     r9, 2
0x1400c4e82  jnz     short loc_1400C4E59
0x1400c4e84  mov     r8d, [rsp+270h+var_228]
0x1400c4e89  mov     rdx, r15
0x1400c4e8c  mov     rcx, [rsi+10h]
0x1400c4e90  call    ?InitializeTables@CmsFailoverBPlusTable@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@PEAPEAX@Z; CmsFailoverBPlusTable::InitializeTables(CmsTransactionContext *,_MS_CREATE_DISPOSITION,void * *)
0x1400c4e95  mov     r14d, eax
0x1400c4e98  test    eax, eax
0x1400c4e9a  js      loc_1400C5445
0x1400c4ea0  test    ebx, ebx
0x1400c4ea2  jz      short loc_1400C4F11
0x1400c4ea4  lea     rcx, [rsi+50h]; void *
0x1400c4ea8  xor     edx, edx; Val
0x1400c4eaa  mov     r8d, 0C0h; Size
0x1400c4eb0  call    memset_0
0x1400c4eb5  mov     qword ptr [rsi+48h], 1
0x1400c4ebd  mov     rax, [r12]
0x1400c4ec1  mov     ecx, 3Dh ; '='
0x1400c4ec6  sub     ecx, [rax+50h]
0x1400c4ec9  mov     eax, 1
0x1400c4ece  shl     rax, cl
0x1400c4ed1  sub     rax, 100h
0x1400c4ed7  mov     [rsi+50h], rax
0x1400c4edb  mov     dword ptr [rsi+70h], 8
0x1400c4ee2  mov     [rsp+270h+var_248], rdi; struct SmsLookupStack *
0x1400c4ee7  mov     dword ptr [rsp+270h+var_250], edi; unsigned int
0x1400c4eeb  mov     r9d, 0C8h; unsigned int
0x1400c4ef1  lea     r8, [rsi+48h]; void *
0x1400c4ef5  mov     rdx, r15; struct CmsTransactionContext *
0x1400c4ef8  mov     rcx, [rsi+10h]; this
0x1400c4efc  call    ?UpdateDataWithRoot@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEBXKKPEAUSmsLookupStack@@@Z; CmsFailoverBPlusTable::UpdateDataWithRoot(CmsTransactionContext *,void const *,ulong,ulong,SmsLookupStack *)
0x1400c4f01  mov     r14d, eax
0x1400c4f04  test    eax, eax
0x1400c4f06  js      loc_1400C5445
0x1400c4f0c  jmp     loc_1400C53AF
0x1400c4f11  mov     [rsp+270h+var_210], rdi
0x1400c4f16  mov     [rsp+270h+var_228], edi
0x1400c4f1a  xorps   xmm0, xmm0
0x1400c4f1d  xor     eax, eax
0x1400c4f1f  movups  xmmword ptr [rbp+170h+var_1C8], xmm0
0x1400c4f23  movups  [rbp+170h+var_1B8], xmm0
0x1400c4f27  mov     [rbp+170h+var_1A8], rax
0x1400c4f2b  lea     rax, [rbp+170h+var_1C8]
0x1400c4f2f  mov     [rsp+270h+var_248], rax
0x1400c4f34  lea     rax, [rsp+270h+var_228]
0x1400c4f39  mov     qword ptr [rsp+270h+var_250], rax
0x1400c4f3e  lea     r9, [rsp+270h+var_210]
0x1400c4f43  xor     r8d, r8d
0x1400c4f46  mov     rdx, r15
0x1400c4f49  mov     rcx, [rsi+10h]
0x1400c4f4d  call    ?PinDataWithRoot@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@W4_EMS_PIN_FLAGS@@PEAPEAXPEAKPEAUSmsLookupStack@@@Z; CmsFailoverBPlusTable::PinDataWithRoot(CmsTransactionContext *,_EMS_PIN_FLAGS,void * *,ulong *,SmsLookupStack *)
0x1400c4f52  mov     r14d, eax
0x1400c4f55  test    eax, eax
0x1400c4f57  js      loc_1400C4FF3
0x1400c4f5d  mov     rax, [rsp+270h+var_210]
0x1400c4f62  movups  xmm0, xmmword ptr [rax]
0x1400c4f65  movups  xmmword ptr [rsi+48h], xmm0
0x1400c4f69  movups  xmm1, xmmword ptr [rax+10h]
0x1400c4f6d  movups  xmmword ptr [rsi+58h], xmm1
0x1400c4f71  movups  xmm0, xmmword ptr [rax+20h]
0x1400c4f75  movups  xmmword ptr [rsi+68h], xmm0
0x1400c4f79  movups  xmm1, xmmword ptr [rax+30h]
0x1400c4f7d  movups  xmmword ptr [rsi+78h], xmm1
0x1400c4f81  movups  xmm0, xmmword ptr [rax+40h]
0x1400c4f85  movups  xmmword ptr [rsi+88h], xmm0
0x1400c4f8c  movups  xmm1, xmmword ptr [rax+50h]
0x1400c4f90  movups  xmmword ptr [rsi+98h], xmm1
0x1400c4f97  movups  xmm0, xmmword ptr [rax+60h]
0x1400c4f9b  movups  xmmword ptr [rsi+0A8h], xmm0
0x1400c4fa2  movups  xmm1, xmmword ptr [rax+70h]
0x1400c4fa6  movups  xmmword ptr [rsi+0B8h], xmm1
0x1400c4fad  movups  xmm0, xmmword ptr [rax+80h]
0x1400c4fb4  movups  xmmword ptr [rsi+0C8h], xmm0
0x1400c4fbb  movups  xmm1, xmmword ptr [rax+90h]
0x1400c4fc2  movups  xmmword ptr [rsi+0D8h], xmm1
0x1400c4fc9  movups  xmm0, xmmword ptr [rax+0A0h]
0x1400c4fd0  movups  xmmword ptr [rsi+0E8h], xmm0
0x1400c4fd7  movups  xmm1, xmmword ptr [rax+0B0h]
0x1400c4fde  movups  xmmword ptr [rsi+0F8h], xmm1
0x1400c4fe5  mov     rax, [rax+0C0h]
0x1400c4fec  mov     [rsi+108h], rax
0x1400c4ff3  mov     r8, [rbp+170h+var_1C8]; struct SmsPage *
0x1400c4ff7  test    r8, r8
0x1400c4ffa  jz      loc_1400C50A8
0x1400c5000  mov     r13, [r15+8]
0x1400c5004  mov     r9d, 3; unsigned int
0x1400c500a  mov     ebx, r9d
0x1400c500d  mov     rcx, [r8+130h]
0x1400c5014  test    rcx, rcx
0x1400c5017  jz      short loc_1400C5085
0x1400c5019  test    r9b, 1
0x1400c501d  jz      short loc_1400C504E
0x1400c501f  mov     eax, [r8+138h]
0x1400c5026  cmp     [r8+180h], eax
0x1400c502d  jnz     short loc_1400C504E
0x1400c502f  bt      r9d, 2
0x1400c5034  mov     rdi, rcx
0x1400c5037  jnb     short loc_1400C5070
0x1400c5039  mov     eax, [r8+13Ch]
0x1400c5040  cmp     [r8+184h], eax
0x1400c5047  jz      short loc_1400C5067
0x1400c5049  and     ebx, 0FFFFFFFBh
0x1400c504c  jmp     short loc_1400C5070
0x1400c504e  test    r9b, 4
0x1400c5052  jz      short loc_1400C5085
0x1400c5054  mov     eax, [r8+13Ch]
0x1400c505b  cmp     [r8+184h], eax
0x1400c5062  jnz     short loc_1400C5085
0x1400c5064  mov     rdi, rcx
0x1400c5067  dec     eax
0x1400c5069  mov     [r8+13Ch], eax
0x1400c5070  sub     dword ptr [r8+138h], 1
0x1400c5078  jnz     short loc_1400C5085
0x1400c507a  mov     qword ptr [r8+130h], 0
0x1400c5085  mov     rdx, r15; struct CmsTransactionCore *
0x1400c5088  mov     rcx, r13; this
0x1400c508b  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400c5090  mov     r8, rdi
0x1400c5093  mov     r9d, ebx
0x1400c5096  test    rdi, rdi
0x1400c5099  mov     edi, 0
0x1400c509e  jnz     loc_1400C500A
0x1400c50a4  mov     [rbp+170h+var_1C8], rdi
0x1400c50a8  test    r14d, r14d
0x1400c50ab  js      loc_1400C5445
0x1400c50b1  mov     r13, rdi
0x1400c50b4  mov     [rsp+270h+var_220], rdi
0x1400c50b9  mov     eax, [rsi+68h]
0x1400c50bc  test    eax, eax
0x1400c50be  jz      short loc_1400C5129
0x1400c50c0  lea     ebx, [rax+1]
0x1400c50c3  mov     [rsp+270h+var_208], rbx
0x1400c50c8  mov     eax, 18h
0x1400c50cd  mul     rbx
0x1400c50d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400c50d7  cmovb   rax, rcx
0x1400c50db  mov     rcx, rax; unsigned __int64
0x1400c50de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400c50e3  mov     rdi, rax
0x1400c50e6  mov     [rsp+270h+var_230], rax
0x1400c50eb  lea     r9, ??0_SmsStorageTierRange@@QEAA@XZ; void *(*)(void *)
0x1400c50f2  mov     r8d, ebx; unsigned __int64
0x1400c50f5  mov     edx, 18h; unsigned __int64
0x1400c50fa  mov     rcx, rax; void *
0x1400c50fd  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400c5102  nop
  ... truncated ...
```
