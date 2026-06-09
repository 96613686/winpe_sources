# CTSContentManager::ReplaceSection_(SECTION_BUFFER *,SECTION_BUFFER *)

- ea: `0x1800306f8`
- end: `0x18003098a`
- name: `?ReplaceSection_@CTSContentManager@@AEAAJPEAUSECTION_BUFFER@@0@Z`
- size: `658`
- prototype: `__int64 __fastcall(CTSContentManager *__hidden this, struct SECTION_BUFFER *, struct SECTION_BUFFER *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18002fbb0`

## callees

- `0x180001048`
- `0x18002e424`
- `0x18002efd0`
- `0x18002f394`
- `0x1800305a4`
- `0x180030668`
- `0x1800306f8`
- `0x180030c68`
- `0x180030d08`
- `0x180030e00`

## pseudocode

```c
__int64 __fastcall CTSContentManager::ReplaceSection_(
        CTSContentManager *this,
        struct SECTION_BUFFER *a2,
        struct SECTION_BUFFER *a3)
{
  unsigned int v3; // eax
  char v5; // r9
  int NewInitializedTSProgram; // edi
  int v7; // esi
  unsigned int v10; // r12d
  unsigned int v11; // eax
  __int64 v12; // rdx
  CTSProgram *v13; // rbx
  unsigned int v14; // esi
  unsigned int v15; // eax
  __int64 v16; // rdx
  CTSProgram *v17; // rbx
  unsigned int i; // esi
  __int64 v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // rdx
  CTSProgram *v22; // rbx
  _QWORD v24[2]; // [rsp+20h] [rbp-28h] BYREF
  int v25; // [rsp+30h] [rbp-18h]
  int v26; // [rsp+34h] [rbp-14h]
  int v27; // [rsp+38h] [rbp-10h]
  int v28; // [rsp+3Ch] [rbp-Ch]
  CTSProgram *v29; // [rsp+90h] [rbp+48h] BYREF

  v3 = *(unsigned __int16 *)((char *)a3 + 9);
  v5 = *(_WORD *)((char *)a3 + 9);
  v29 = 0;
  NewInitializedTSProgram = 0;
  v7 = 0;
  v10 = (int)((((v5 & 0xF) << 8) | (v3 >> 8)) - 9) / 4;
  if ( v10 )
  {
    while ( 1 )
    {
      v11 = *(unsigned __int16 *)((char *)a3 + (unsigned int)(4 * v7) + 16);
      v12 = (v11 >> 8) | ((unsigned __int8)v11 << 8);
      if ( (_DWORD)v12 )
      {
        NewInitializedTSProgram = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Remove(
                                    (char *)this + 224,
                                    v12,
                                    &v29);
        if ( NewInitializedTSProgram >= 0 )
        {
          v13 = v29;
          NewInitializedTSProgram = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Store(
                                      (char *)this + 648,
                                      v29,
                                      *((unsigned int *)v29 + 6));
          if ( NewInitializedTSProgram < 0 )
            break;
        }
      }
      if ( ++v7 >= v10 )
        goto LABEL_6;
    }
LABEL_13:
    CTSProgram::Shutdown(v13);
    if ( v13 )
    {
      CTSProgram::~CTSProgram(v13);
      operator delete(v13);
    }
  }
  else
  {
LABEL_6:
    v14 = 0;
    v10 = ((HIBYTE(*(unsigned __int16 *)((char *)a2 + 9)) | ((*(_WORD *)((_BYTE *)a2 + 9) & 0xF) << 8)) - 9) / 4;
    if ( v10 )
    {
      do
      {
        v15 = *((unsigned __int16 *)a2 + 2 * v14 + 8);
        v16 = (v15 >> 8) | ((unsigned __int8)v15 << 8);
        if ( (_DWORD)v16 )
        {
          if ( (int)TGenericMap<unsigned __int64,unsigned long,0,5,19>::Remove((char *)this + 648, v16, &v29) >= 0 )
          {
            v13 = v29;
            NewInitializedTSProgram = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Store(
                                        (char *)this + 224,
                                        v29,
                                        *((unsigned int *)v29 + 6));
            if ( NewInitializedTSProgram < 0 )
              goto LABEL_13;
          }
          else
          {
            NewInitializedTSProgram = 0;
          }
        }
        ++v14;
      }
      while ( v14 < v10 );
    }
  }
  while ( *((CTSContentManager **)this + 127) != (CTSContentManager *)((char *)this + 1016) )
  {
    TGenericMap<unsigned __int64,unsigned long,0,5,19>::RemoveFirst((char *)this + 648, &v29);
    v17 = v29;
    v26 = 512;
    v24[0] = 0;
    v24[1] = 0;
    v28 = 0;
    v25 = *((_DWORD *)v29 + 16);
    v27 = *((_DWORD *)v29 + 6);
    CTSContentManager::StreamExpiredEvent(this, (struct SINGULAR_STREAM *)v24);
    CTSProgram::Shutdown(v17);
    CTSProgram::~CTSProgram(v17);
    operator delete(v17);
  }
  for ( i = 0; NewInitializedTSProgram >= 0 && i < v10; ++i )
  {
    v20 = *((unsigned __int16 *)a2 + 2 * i + 8);
    v21 = (v20 >> 8) | ((unsigned __int8)v20 << 8);
    if ( (_DWORD)v21 )
    {
      NewInitializedTSProgram = TGenericMap<unsigned __int64,unsigned long,1,10,19>::Find((char *)this + 224, v21, &v29);
      if ( NewInitializedTSProgram < 0 )
      {
        v19 = 4 * i;
        NewInitializedTSProgram = CTSContentManager::GetNewInitializedTSProgram_(
                                    this,
                                    HIBYTE(*(unsigned __int16 *)((char *)a2 + v19 + 16))
                                  | ((unsigned __int8)*(_WORD *)((char *)a2 + v19 + 16) << 8),
                                    HIBYTE(*(unsigned __int16 *)((char *)a2 + v19 + 18))
                                  | ((unsigned __int8)(*(_WORD *)((_BYTE *)a2 + v19 + 18) & 0x1F) << 8),
                                    &v29);
        if ( NewInitializedTSProgram < 0 )
          return (unsigned int)NewInitializedTSProgram;
        v22 = v29;
        NewInitializedTSProgram = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Store(
                                    (char *)this + 224,
                                    v29,
                                    *((unsigned int *)v29 + 6));
        if ( NewInitializedTSProgram < 0 )
        {
          CTSProgram::Shutdown(v22);
          if ( v22 )
          {
            CTSProgram::~CTSProgram(v22);
            operator delete(v22);
          }
          return (unsigned int)NewInitializedTSProgram;
        }
      }
    }
  }
  return (unsigned int)NewInitializedTSProgram;
}

```

## disassembly

```asm
0x1800306f8  push    rbp
0x1800306fa  push    rbx
0x1800306fb  push    rsi
0x1800306fc  push    rdi
0x1800306fd  push    r12
0x1800306ff  push    r13
0x180030701  push    r14
0x180030703  push    r15
0x180030705  mov     rbp, rsp
0x180030708  sub     rsp, 48h
0x18003070c  movzx   eax, word ptr [r8+9]
0x180030711  mov     r13, rdx
0x180030714  mov     r9d, eax
0x180030717  mov     [rbp+arg_0], 0
0x18003071f  shr     eax, 8
0x180030722  and     r9d, 0Fh
0x180030726  shl     r9d, 8
0x18003072a  xor     edi, edi
0x18003072c  or      eax, r9d
0x18003072f  xor     esi, esi
0x180030731  sub     eax, 9
0x180030734  mov     r15, r8
0x180030737  cdq
0x180030738  mov     r14, rcx
0x18003073b  and     edx, 3
0x18003073e  add     eax, edx
0x180030740  sar     eax, 2
0x180030743  mov     r12d, eax
0x180030746  test    eax, eax
0x180030748  jz      short loc_1800307A2
0x18003074a  lea     eax, ds:0[rsi*4]
0x180030751  movzx   eax, word ptr [rax+r15+10h]
0x180030757  movzx   edx, al
0x18003075a  shl     edx, 8
0x18003075d  shr     eax, 8
0x180030760  or      edx, eax
0x180030762  jz      short loc_18003079B
0x180030764  lea     rcx, [r14+0E0h]
0x18003076b  lea     r8, [rbp+arg_0]
0x18003076f  call    ?Remove@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Remove(ulong,unsigned __int64 *)
0x180030774  mov     edi, eax
0x180030776  test    eax, eax
0x180030778  js      short loc_18003079B
0x18003077a  mov     rbx, [rbp+arg_0]
0x18003077e  lea     rcx, [r14+288h]
0x180030785  mov     rdx, rbx
0x180030788  mov     r8d, [rbx+18h]
0x18003078c  call    ?Store@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJ_KK@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Store(unsigned __int64,ulong)
0x180030791  mov     edi, eax
0x180030793  test    eax, eax
0x180030795  js      loc_180030821
0x18003079b  inc     esi
0x18003079d  cmp     esi, r12d
0x1800307a0  jb      short loc_18003074A
0x1800307a2  movzx   ecx, word ptr [r13+9]
0x1800307a7  xor     esi, esi
0x1800307a9  mov     eax, ecx
0x1800307ab  shr     ecx, 8
0x1800307ae  and     eax, 0Fh
0x1800307b1  shl     eax, 8
0x1800307b4  or      eax, ecx
0x1800307b6  sub     eax, 9
0x1800307b9  cdq
0x1800307ba  and     edx, 3
0x1800307bd  add     eax, edx
0x1800307bf  sar     eax, 2
0x1800307c2  mov     r12d, eax
0x1800307c5  test    eax, eax
0x1800307c7  jz      short loc_180030843
0x1800307c9  lea     eax, ds:0[rsi*4]
0x1800307d0  movzx   eax, word ptr [rax+r13+10h]
0x1800307d6  movzx   edx, al
0x1800307d9  shl     edx, 8
0x1800307dc  shr     eax, 8
0x1800307df  or      edx, eax
0x1800307e1  jz      short loc_180030818
0x1800307e3  lea     rcx, [r14+288h]
0x1800307ea  lea     r8, [rbp+arg_0]
0x1800307ee  call    ?Remove@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Remove(ulong,unsigned __int64 *)
0x1800307f3  test    eax, eax
0x1800307f5  jns     short loc_1800307FB
0x1800307f7  xor     edi, edi
0x1800307f9  jmp     short loc_180030818
0x1800307fb  mov     rbx, [rbp+arg_0]
0x1800307ff  lea     rcx, [r14+0E0h]
0x180030806  mov     rdx, rbx
0x180030809  mov     r8d, [rbx+18h]
0x18003080d  call    ?Store@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJ_KK@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Store(unsigned __int64,ulong)
0x180030812  mov     edi, eax
0x180030814  test    eax, eax
0x180030816  js      short loc_180030821
0x180030818  inc     esi
0x18003081a  cmp     esi, r12d
0x18003081d  jb      short loc_1800307C9
0x18003081f  jmp     short loc_180030843
0x180030821  mov     rcx, rbx; this
0x180030824  call    ?Shutdown@CTSProgram@@QEAAJXZ; CTSProgram::Shutdown(void)
0x180030829  test    rbx, rbx
0x18003082c  jz      short loc_180030843
0x18003082e  mov     rcx, rbx; this
0x180030831  call    ??1CTSProgram@@QEAA@XZ; CTSProgram::~CTSProgram(void)
0x180030836  mov     edx, 3B8h; unsigned __int64
0x18003083b  mov     rcx, rbx; void *
0x18003083e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030843  lea     rsi, [r14+3F8h]
0x18003084a  cmp     [rsi], rsi
0x18003084d  jz      short loc_1800308AE
0x18003084f  lea     rdx, [rbp+arg_0]
0x180030853  lea     rcx, [r14+288h]
0x18003085a  call    ?RemoveFirst@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::RemoveFirst(unsigned __int64 *)
0x18003085f  mov     rbx, [rbp+arg_0]
0x180030863  lea     rdx, [rbp+var_28]; struct SINGULAR_STREAM *
0x180030867  xor     eax, eax
0x180030869  mov     [rbp+var_14], 200h
0x180030870  mov     [rbp+var_28], rax
0x180030874  mov     rcx, r14; this
0x180030877  mov     [rbp+var_20], rax
0x18003087b  mov     [rbp+var_C], eax
0x18003087e  mov     eax, [rbx+40h]
0x180030881  mov     [rbp+var_18], eax
0x180030884  mov     eax, [rbx+18h]
0x180030887  mov     [rbp+var_10], eax
0x18003088a  call    ?StreamExpiredEvent@CTSContentManager@@AEAAXPEAUSINGULAR_STREAM@@@Z; CTSContentManager::StreamExpiredEvent(SINGULAR_STREAM *)
0x18003088f  mov     rcx, rbx; this
0x180030892  call    ?Shutdown@CTSProgram@@QEAAJXZ; CTSProgram::Shutdown(void)
0x180030897  mov     rcx, rbx; this
0x18003089a  call    ??1CTSProgram@@QEAA@XZ; CTSProgram::~CTSProgram(void)
0x18003089f  mov     edx, 3B8h; unsigned __int64
0x1800308a4  mov     rcx, rbx; void *
0x1800308a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800308ac  jmp     short loc_18003084A
0x1800308ae  xor     esi, esi
0x1800308b0  jmp     loc_18003094B
0x1800308b5  cmp     esi, r12d
0x1800308b8  jnb     loc_180030977
0x1800308be  lea     eax, ds:0[rsi*4]
0x1800308c5  mov     ebx, eax
0x1800308c7  movzx   eax, word ptr [rax+r13+10h]
0x1800308cd  movzx   edx, al
0x1800308d0  shl     edx, 8
0x1800308d3  shr     eax, 8
0x1800308d6  or      edx, eax
0x1800308d8  jz      short loc_180030949
0x1800308da  lea     r15, [r14+0E0h]
0x1800308e1  mov     rcx, r15
0x1800308e4  lea     r8, [rbp+arg_0]
0x1800308e8  call    ?Find@?$TGenericMap@_KK$00$09$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,1,10,19>::Find(ulong,unsigned __int64 *)
0x1800308ed  mov     edi, eax
0x1800308ef  test    eax, eax
0x1800308f1  jns     short loc_180030949
0x1800308f3  movzx   r9d, word ptr [rbx+r13+10h]
0x1800308f9  mov     rcx, r14; this
0x1800308fc  movzx   eax, word ptr [rbx+r13+12h]
0x180030902  movzx   edx, r9b
0x180030906  mov     r8d, eax
0x180030909  and     r8d, 1Fh
0x18003090d  shr     r9d, 8
0x180030911  shl     edx, 8
0x180030914  shl     r8d, 8
0x180030918  or      edx, r9d; unsigned int
0x18003091b  shr     eax, 8
0x18003091e  lea     r9, [rbp+arg_0]; struct CTSProgram **
0x180030922  or      r8d, eax; unsigned int
0x180030925  call    ?GetNewInitializedTSProgram_@CTSContentManager@@AEAAJKKPEAPEAVCTSProgram@@@Z; CTSContentManager::GetNewInitializedTSProgram_(ulong,ulong,CTSProgram * *)
0x18003092a  mov     edi, eax
0x18003092c  test    eax, eax
0x18003092e  js      short loc_180030977
0x180030930  mov     rbx, [rbp+arg_0]
0x180030934  mov     rcx, r15
0x180030937  mov     rdx, rbx
0x18003093a  mov     r8d, [rbx+18h]
0x18003093e  call    ?Store@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJ_KK@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Store(unsigned __int64,ulong)
0x180030943  mov     edi, eax
0x180030945  test    eax, eax
0x180030947  js      short loc_180030955
0x180030949  inc     esi
0x18003094b  test    edi, edi
0x18003094d  jns     loc_1800308B5
0x180030953  jmp     short loc_180030977
0x180030955  mov     rcx, rbx; this
0x180030958  call    ?Shutdown@CTSProgram@@QEAAJXZ; CTSProgram::Shutdown(void)
0x18003095d  test    rbx, rbx
0x180030960  jz      short loc_180030977
0x180030962  mov     rcx, rbx; this
0x180030965  call    ??1CTSProgram@@QEAA@XZ; CTSProgram::~CTSProgram(void)
0x18003096a  mov     edx, 3B8h; unsigned __int64
0x18003096f  mov     rcx, rbx; void *
0x180030972  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030977  mov     eax, edi
0x180030979  add     rsp, 48h
0x18003097d  pop     r15
0x18003097f  pop     r14
0x180030981  pop     r13
0x180030983  pop     r12
0x180030985  pop     rdi
0x180030986  pop     rsi
0x180030987  pop     rbx
0x180030988  pop     rbp
0x180030989  retn
```
