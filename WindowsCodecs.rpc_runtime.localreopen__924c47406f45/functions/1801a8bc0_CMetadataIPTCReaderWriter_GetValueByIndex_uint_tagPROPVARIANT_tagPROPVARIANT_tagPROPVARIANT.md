# CMetadataIPTCReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1801a8bc0`
- end: `0x1801a8d5f`
- name: `?GetValueByIndex@CMetadataIPTCReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `415`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *this, unsigned int, struct tagPROPVARIANT *, PROPVARIANT *, PROPVARIANT *pvarDest)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180022660`
- `0x180023648`
- `0x180032d50`
- `0x1800787a0`
- `0x1800aa990`
- `0x1800bb784`
- `0x1801a8bc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a8ce0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a8d09`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a8ce0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a8d09`

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
  struct tagPROPVARIANT *v10; // rsi
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
  if ( a4 && *(_WORD *)a4 || (v10 = (struct tagPROPVARIANT *)pvarDest) != 0 && *(_WORD *)pvarDest || a3 && a3->vt )
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
                  : PropVariantCopy((PROPVARIANT *)v10, (const PROPVARIANT *)(v15 + 8));
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
0x1801a8bc0  mov     [rsp+arg_8], rbx
0x1801a8bc5  mov     [rsp+arg_10], rbp
0x1801a8bca  push    rsi
0x1801a8bcb  push    rdi
0x1801a8bcc  push    r12
0x1801a8bce  push    r14
0x1801a8bd0  push    r15
0x1801a8bd2  sub     rsp, 20h
0x1801a8bd6  mov     rbp, rcx
0x1801a8bd9  mov     r14, r9
0x1801a8bdc  add     rcx, 28h ; '('; this
0x1801a8be0  mov     rbx, r8
0x1801a8be3  mov     [rsp+48h+arg_0], rcx
0x1801a8be8  mov     r15d, edx
0x1801a8beb  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1801a8bf0  xor     r12d, r12d
0x1801a8bf3  test    r14, r14
0x1801a8bf6  jz      short loc_1801A8C08
0x1801a8bf8  cmp     [r14], r12w
0x1801a8bfc  jz      short loc_1801A8C08
0x1801a8bfe  mov     ebx, 80070057h
0x1801a8c03  jmp     loc_1801A8D2C
0x1801a8c08  mov     rsi, [rsp+48h+pvarDest]
0x1801a8c0d  test    rsi, rsi
0x1801a8c10  jz      short loc_1801A8C18
0x1801a8c12  cmp     [rsi], r12w
0x1801a8c16  jnz     short loc_1801A8BFE
0x1801a8c18  test    rbx, rbx
0x1801a8c1b  jz      short loc_1801A8C23
0x1801a8c1d  cmp     [rbx], r12w
0x1801a8c21  jnz     short loc_1801A8BFE
0x1801a8c23  mov     rcx, rbp; this
0x1801a8c26  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x1801a8c2b  mov     ebx, eax
0x1801a8c2d  test    eax, eax
0x1801a8c2f  jns     short loc_1801A8C45
0x1801a8c31  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801a8c38  jz      loc_1801A8D3C
0x1801a8c3e  mov     ecx, eax
0x1801a8c40  jmp     loc_1801A8D37
0x1801a8c45  mov     r8d, [rbp+0E8h]
0x1801a8c4c  test    r8d, r8d
0x1801a8c4f  jz      loc_1801A8D27
0x1801a8c55  mov     r11, [rbp+0D0h]
0x1801a8c5c  mov     rdi, r12
0x1801a8c5f  mov     edx, r12d
0x1801a8c62  mov     ecx, r12d
0x1801a8c65  mov     eax, edx
0x1801a8c67  lea     r10, [rax+rax*4]
0x1801a8c6b  mov     r9d, [r11+r10*8+20h]
0x1801a8c70  lea     eax, [r9+rcx]
0x1801a8c74  cmp     eax, r15d
0x1801a8c77  jnb     short loc_1801A8C7D
0x1801a8c79  mov     ecx, eax
0x1801a8c7b  jmp     short loc_1801A8CA0
0x1801a8c7d  mov     eax, r12d
0x1801a8c80  cmp     eax, r9d
0x1801a8c83  jnb     short loc_1801A8C9B
0x1801a8c85  cmp     ecx, r15d
0x1801a8c88  jz      short loc_1801A8C90
0x1801a8c8a  inc     ecx
0x1801a8c8c  inc     eax
0x1801a8c8e  jmp     short loc_1801A8C80
0x1801a8c90  mov     edi, eax
0x1801a8c92  shl     rdi, 6
0x1801a8c96  add     rdi, [r11+r10*8+8]
0x1801a8c9b  test    rdi, rdi
0x1801a8c9e  jnz     short loc_1801A8CAC
0x1801a8ca0  inc     edx
0x1801a8ca2  cmp     edx, r8d
0x1801a8ca5  jb      short loc_1801A8C65
0x1801a8ca7  test    rdi, rdi
0x1801a8caa  jz      short loc_1801A8D27
0x1801a8cac  mov     rdx, rdi; struct CMetadataIPTCReaderWriter::DataSet *
0x1801a8caf  mov     rcx, rbp; this
0x1801a8cb2  call    ?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z; CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)
0x1801a8cb7  mov     ebx, eax
0x1801a8cb9  test    eax, eax
0x1801a8cbb  jns     short loc_1801A8CCE
0x1801a8cbd  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801a8cc4  jnz     loc_1801A8C3E
0x1801a8cca  test    eax, eax
0x1801a8ccc  js      short loc_1801A8D3C
0x1801a8cce  test    rsi, rsi
0x1801a8cd1  jz      short loc_1801A8CFD
0x1801a8cd3  cmp     [rdi+38h], r12
0x1801a8cd7  jnz     short loc_1801A8D1A
0x1801a8cd9  lea     rdx, [rdi+8]; pvarSrc
0x1801a8cdd  mov     rcx, rsi; pvarDest
0x1801a8ce0  call    cs:__imp_PropVariantCopy
0x1801a8ce6  mov     ebx, eax
0x1801a8ce8  test    eax, eax
0x1801a8cea  jns     short loc_1801A8CFD
0x1801a8cec  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801a8cf3  jnz     loc_1801A8C3E
0x1801a8cf9  test    eax, eax
0x1801a8cfb  js      short loc_1801A8D3C
0x1801a8cfd  test    r14, r14
0x1801a8d00  jz      short loc_1801A8D3C
0x1801a8d02  lea     rdx, [rdi+20h]; pvarSrc
0x1801a8d06  mov     rcx, r14; pvarDest
0x1801a8d09  call    cs:__imp_PropVariantCopy
0x1801a8d0f  mov     ebx, eax
0x1801a8d11  test    eax, eax
0x1801a8d13  jns     short loc_1801A8D3C
0x1801a8d15  jmp     loc_1801A8C31
0x1801a8d1a  mov     r8, rsi; struct tagPROPVARIANT *
0x1801a8d1d  mov     rdx, rdi; struct CMetadataIPTCReaderWriter::DataSet *
0x1801a8d20  call    ?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)
0x1801a8d25  jmp     short loc_1801A8CE6
0x1801a8d27  mov     ebx, 88982F40h
0x1801a8d2c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1801a8d33  jz      short loc_1801A8D3C
0x1801a8d35  mov     ecx, ebx; int
0x1801a8d37  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a8d3c  lea     rcx, [rsp+48h+arg_0]
0x1801a8d41  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1801a8d46  mov     rbp, [rsp+48h+arg_10]
0x1801a8d4b  mov     eax, ebx
0x1801a8d4d  mov     rbx, [rsp+48h+arg_8]
0x1801a8d52  add     rsp, 20h
0x1801a8d56  pop     r15
0x1801a8d58  pop     r14
0x1801a8d5a  pop     r12
0x1801a8d5c  pop     rdi
0x1801a8d5d  pop     rsi
0x1801a8d5e  retn
```
