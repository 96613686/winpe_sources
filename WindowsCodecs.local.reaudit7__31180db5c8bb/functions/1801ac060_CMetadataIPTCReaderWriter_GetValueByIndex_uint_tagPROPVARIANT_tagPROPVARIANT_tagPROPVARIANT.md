# CMetadataIPTCReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1801ac060`
- end: `0x1801ac210`
- name: `?GetValueByIndex@CMetadataIPTCReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `432`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *this, unsigned int, struct tagPROPVARIANT *, PROPVARIANT *, PROPVARIANT *pvarDest)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800319d0`
- `0x18003c670`
- `0x18004e5e0`
- `0x18004f390`
- `0x1800ac94c`
- `0x1800bd9d4`
- `0x1801ac060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ac184`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ac1b3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ac184`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ac1b3`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::GetValueByIndex(
        CMetadataIPTCReaderWriter *this,
        unsigned int a2,
        struct tagPROPVARIANT *a3,
        PROPVARIANT *a4,
        PROPVARIANT *pvarDest)
{
  unsigned int v9; // ebx
  PROPVARIANT *v10; // rsi
  HRESULT v11; // eax
  int v12; // ecx
  unsigned int v13; // r8d
  __int64 v14; // r11
  unsigned __int64 v15; // rdi
  unsigned int v16; // edx
  int v17; // ecx
  unsigned int v18; // r9d
  unsigned int i; // eax
  CMetadataIPTCReaderWriter *v20; // rcx
  char *v22; // [rsp+50h] [rbp+8h] BYREF

  v22 = (char *)this + 40;
  CMTALock::Enter((CMetadataIPTCReaderWriter *)((char *)this + 40));
  if ( a4 && *(_WORD *)a4 || (v10 = pvarDest) != 0 && *(_WORD *)pvarDest || a3 && a3->vt )
  {
    v9 = -2147024809;
  }
  else
  {
    v11 = CMetadataIPTCReaderWriter::EnsureLoadedValues(this);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_9;
    v13 = *((_DWORD *)this + 58);
    if ( v13 )
    {
      v14 = *((_QWORD *)this + 26);
      v15 = 0;
      v16 = 0;
      v17 = 0;
      do
      {
        v18 = *(_DWORD *)(v14 + 40LL * v16 + 32);
        if ( v18 + v17 >= a2 )
        {
          for ( i = 0; i < v18; ++i )
          {
            if ( v17 == a2 )
            {
              v15 = *(_QWORD *)(v14 + 40LL * v16 + 8) + ((unsigned __int64)i << 6);
              break;
            }
            ++v17;
          }
          if ( v15 )
          {
            v11 = CMetadataIPTCReaderWriter::EnsureDataSetLoaded(this, (struct CMetadataIPTCReaderWriter::DataSet *)v15);
            v9 = v11;
            if ( v11 < 0 )
            {
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_40;
LABEL_10:
              v12 = v11;
LABEL_39:
              DoStackCapture(v12);
              goto LABEL_40;
            }
            if ( v10 )
            {
              v11 = *(_QWORD *)(v15 + 56)
                  ? CMetadataIPTCReaderWriter::CreateVectorFromVariants(
                      v20,
                      (struct CMetadataIPTCReaderWriter::DataSet *)v15,
                      v10)
                  : PropVariantCopy(v10, (const PROPVARIANT *)(v15 + 8));
              v9 = v11;
              if ( v11 < 0 )
              {
                if ( !(_DWORD)g_doStackCaptures )
                  goto LABEL_40;
                goto LABEL_10;
              }
            }
            if ( !a4 )
              goto LABEL_40;
            v11 = PropVariantCopy(a4, (const PROPVARIANT *)(v15 + 32));
            v9 = v11;
            if ( v11 >= 0 )
              goto LABEL_40;
LABEL_9:
            if ( (_DWORD)g_doStackCaptures )
              goto LABEL_10;
            goto LABEL_40;
          }
        }
        else
        {
          v17 += v18;
        }
        ++v16;
      }
      while ( v16 < v13 );
    }
    v9 = -2003292352;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
    v12 = v9;
    goto LABEL_39;
  }
LABEL_40:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v22);
  return v9;
}

```

## disassembly

```asm
0x1801ac060  mov     [rsp+arg_8], rbx
0x1801ac065  mov     [rsp+arg_10], rbp
0x1801ac06a  push    rsi
0x1801ac06b  push    rdi
0x1801ac06c  push    r12
0x1801ac06e  push    r14
0x1801ac070  push    r15
0x1801ac072  sub     rsp, 20h
0x1801ac076  mov     rbp, rcx
0x1801ac079  mov     r14, r9
0x1801ac07c  add     rcx, 28h ; '('; this
0x1801ac080  mov     rbx, r8
0x1801ac083  mov     [rsp+48h+arg_0], rcx
0x1801ac088  mov     r15d, edx
0x1801ac08b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1801ac090  xor     r12d, r12d
0x1801ac093  test    r14, r14
0x1801ac096  jz      short loc_1801AC0A8
0x1801ac098  cmp     [r14], r12w
0x1801ac09c  jz      short loc_1801AC0A8
0x1801ac09e  mov     ebx, 80070057h
0x1801ac0a3  jmp     loc_1801AC1DC
0x1801ac0a8  mov     rsi, [rsp+48h+pvarDest]
0x1801ac0ad  test    rsi, rsi
0x1801ac0b0  jz      short loc_1801AC0B8
0x1801ac0b2  cmp     [rsi], r12w
0x1801ac0b6  jnz     short loc_1801AC09E
0x1801ac0b8  test    rbx, rbx
0x1801ac0bb  jz      short loc_1801AC0C3
0x1801ac0bd  cmp     [rbx], r12w
0x1801ac0c1  jnz     short loc_1801AC09E
0x1801ac0c3  mov     rcx, rbp; this
0x1801ac0c6  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x1801ac0cb  mov     ebx, eax
0x1801ac0cd  test    eax, eax
0x1801ac0cf  jns     short loc_1801AC0E5
0x1801ac0d1  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801ac0d8  jz      loc_1801AC1EC
0x1801ac0de  mov     ecx, eax
0x1801ac0e0  jmp     loc_1801AC1E7
0x1801ac0e5  mov     r8d, [rbp+0E8h]
0x1801ac0ec  test    r8d, r8d
0x1801ac0ef  jz      loc_1801AC1D7
0x1801ac0f5  mov     r11, [rbp+0D0h]
0x1801ac0fc  mov     rdi, r12
0x1801ac0ff  mov     edx, r12d
0x1801ac102  mov     ecx, r12d
0x1801ac105  mov     eax, edx
0x1801ac107  lea     r10, [rax+rax*4]
0x1801ac10b  mov     r9d, [r11+r10*8+20h]
0x1801ac110  lea     eax, [r9+rcx]
0x1801ac114  cmp     eax, r15d
0x1801ac117  jnb     short loc_1801AC11D
0x1801ac119  mov     ecx, eax
0x1801ac11b  jmp     short loc_1801AC140
0x1801ac11d  mov     eax, r12d
0x1801ac120  cmp     eax, r9d
0x1801ac123  jnb     short loc_1801AC13B
0x1801ac125  cmp     ecx, r15d
0x1801ac128  jz      short loc_1801AC130
0x1801ac12a  inc     ecx
0x1801ac12c  inc     eax
0x1801ac12e  jmp     short loc_1801AC120
0x1801ac130  mov     edi, eax
0x1801ac132  shl     rdi, 6
0x1801ac136  add     rdi, [r11+r10*8+8]
0x1801ac13b  test    rdi, rdi
0x1801ac13e  jnz     short loc_1801AC150
0x1801ac140  inc     edx
0x1801ac142  cmp     edx, r8d
0x1801ac145  jb      short loc_1801AC105
0x1801ac147  test    rdi, rdi
0x1801ac14a  jz      loc_1801AC1D7
0x1801ac150  mov     rdx, rdi; struct CMetadataIPTCReaderWriter::DataSet *
0x1801ac153  mov     rcx, rbp; this
0x1801ac156  call    ?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z; CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)
0x1801ac15b  mov     ebx, eax
0x1801ac15d  test    eax, eax
0x1801ac15f  jns     short loc_1801AC172
0x1801ac161  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801ac168  jnz     loc_1801AC0DE
0x1801ac16e  test    eax, eax
0x1801ac170  js      short loc_1801AC1EC
0x1801ac172  test    rsi, rsi
0x1801ac175  jz      short loc_1801AC1A7
0x1801ac177  cmp     [rdi+38h], r12
0x1801ac17b  jnz     short loc_1801AC1CA
0x1801ac17d  lea     rdx, [rdi+8]; pvarSrc
0x1801ac181  mov     rcx, rsi; pvarDest
0x1801ac184  call    cs:__imp_PropVariantCopy
0x1801ac18b  nop     dword ptr [rax+rax+00h]
0x1801ac190  mov     ebx, eax
0x1801ac192  test    eax, eax
0x1801ac194  jns     short loc_1801AC1A7
0x1801ac196  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801ac19d  jnz     loc_1801AC0DE
0x1801ac1a3  test    eax, eax
0x1801ac1a5  js      short loc_1801AC1EC
0x1801ac1a7  test    r14, r14
0x1801ac1aa  jz      short loc_1801AC1EC
0x1801ac1ac  lea     rdx, [rdi+20h]; pvarSrc
0x1801ac1b0  mov     rcx, r14; pvarDest
0x1801ac1b3  call    cs:__imp_PropVariantCopy
0x1801ac1ba  nop     dword ptr [rax+rax+00h]
0x1801ac1bf  mov     ebx, eax
0x1801ac1c1  test    eax, eax
0x1801ac1c3  jns     short loc_1801AC1EC
0x1801ac1c5  jmp     loc_1801AC0D1
0x1801ac1ca  mov     r8, rsi; struct tagPROPVARIANT *
0x1801ac1cd  mov     rdx, rdi; struct CMetadataIPTCReaderWriter::DataSet *
0x1801ac1d0  call    ?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)
0x1801ac1d5  jmp     short loc_1801AC190
0x1801ac1d7  mov     ebx, 88982F40h
0x1801ac1dc  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801ac1e3  jz      short loc_1801AC1EC
0x1801ac1e5  mov     ecx, ebx; int
0x1801ac1e7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ac1ec  lea     rcx, [rsp+48h+arg_0]
0x1801ac1f1  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1801ac1f6  mov     rbp, [rsp+48h+arg_10]
0x1801ac1fb  mov     eax, ebx
0x1801ac1fd  mov     rbx, [rsp+48h+arg_8]
0x1801ac202  add     rsp, 20h
0x1801ac206  pop     r15
0x1801ac208  pop     r14
0x1801ac20a  pop     r12
0x1801ac20c  pop     rdi
0x1801ac20d  pop     rsi
0x1801ac20e  retn
```
