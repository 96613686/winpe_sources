# CASFStreamSelector::CreateScalableGroups(void)

- ea: `0x1800357c8`
- end: `0x180035bfb`
- name: `?CreateScalableGroups@CASFStreamSelector@@IEAAJXZ`
- size: `1075`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x180031360`
- `0x180033438`
- `0x180033a40`
- `0x180033aac`
- `0x180033d00`
- `0x180033d38`
- `0x180033da0`
- `0x1800357c8`
- `0x180037f08`
- `0x18003f294`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateScalableGroups(CASFStreamSelector *this)
{
  CASFStreamSelector *v1; // r13
  __int64 v2; // rcx
  __int64 result; // rax
  int StreamInfo; // edi
  CASFStreamSelector::MULTI_GROUP *v5; // rbx
  unsigned int v6; // edx
  int v7; // r12d
  unsigned __int16 v8; // si
  char *v9; // r15
  __int64 v10; // rcx
  unsigned __int16 i; // r14
  __int64 v12; // rax
  __int64 v13; // rcx
  CASFStreamSelector::STREAM_GROUP *v14; // rbx
  struct CASFStreamSelector::STREAM_INFO *v15; // rax
  CASFStreamSelector::MULTI_GROUP *v16; // rax
  unsigned __int16 v17; // si
  __int64 v18; // rcx
  CASFStreamSelector::STREAM_GROUP *v19; // rax
  __int64 v20; // rax
  CASFStreamSelector::STREAM_GROUP *v21; // r14
  struct CASFStreamSelector::STREAM_INFO *v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-45h] BYREF
  CASFStreamSelector *v26; // [rsp+38h] [rbp-41h]
  __int64 *v27; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  __int64 v29; // [rsp+50h] [rbp-29h] BYREF
  __int64 v30; // [rsp+58h] [rbp-21h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 v32; // [rsp+64h] [rbp-15h] BYREF
  _WORD v33[2]; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 v34; // [rsp+6Ch] [rbp-Dh] BYREF
  int v35; // [rsp+70h] [rbp-9h] BYREF
  __int128 Buf1; // [rsp+78h] [rbp-1h] BYREF

  v1 = this;
  v26 = this;
  v2 = *((_QWORD *)this + 3);
  v29 = 0;
  result = ASFGetRootObject(v2, &CLSID_ASFHeaderObject, &IID_IASFUnknownContainer, &v29);
  if ( (int)result >= 0 )
  {
    v28 = 0;
    v30 = 0;
    v27 = 0;
    v35 = 0;
    StreamInfo = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v29 + 72LL))(
                   v29,
                   &CLSID_ASFInterStreamDependencyObject,
                   &v28);
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = 0;
    }
    if ( StreamInfo >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 40LL))(v28);
      while ( 1 )
      {
        v5 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v28 + 24LL))(
               v28,
               1,
               &v30,
               &v35) )
        {
          break;
        }
        if ( v27 )
        {
          (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
          v27 = 0;
        }
        StreamInfo = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v30)(
                       v30,
                       &IID_IASFInterStreamDependencyObject,
                       &v27);
        if ( v30 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v30 = 0;
        }
        if ( StreamInfo >= 0 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64 *, unsigned __int16 *))(*v27 + 80))(v27, &v32);
          if ( v32 )
          {
            v7 = 0;
            v8 = 0;
            v9 = (char *)v1 + 64;
            do
            {
              v33[0] = 0;
              v34 = 0;
              v25 = 0;
              (*(void (__fastcall **)(__int64 *, _QWORD, _WORD *, unsigned __int16 *))(*v27 + 88))(v27, v8, v33, &v34);
              StreamInfo = CASFStreamSelector::GetStreamInfo(v10, v9, v33[0], &v25);
              if ( StreamInfo >= 0 )
              {
                for ( i = 0; i < v34; ++i )
                {
                  v31[0] = 0;
                  Buf1 = 0;
                  v12 = *v27;
                  v24 = 0;
                  StreamInfo = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _WORD *, __int128 *))(v12 + 96))(
                                 v27,
                                 v8,
                                 i,
                                 v31,
                                 &Buf1);
                  if ( StreamInfo >= 0 )
                  {
                    StreamInfo = CASFStreamSelector::GetStreamInfo(v13, v9, v31[0], &v24);
                    if ( StreamInfo >= 0 )
                    {
                      v14 = (CASFStreamSelector::STREAM_GROUP *)(CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                   v9,
                                                                   v25)
                                                               + 32);
                      v15 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                        v9,
                                                                        v24);
                      CASFStreamSelector::STREAM_GROUP::Add(v14, v15);
                      if ( memcmp_0(&Buf1, &CLSID_ASFEnhancementNone, 0x10u) )
                        v7 = 1;
                    }
                  }
                }
              }
              ++v8;
            }
            while ( v8 < v32 );
            v1 = v26;
            if ( v7 )
            {
              v16 = (CASFStreamSelector::MULTI_GROUP *)operator new(0xF0u);
              v5 = v16;
              if ( !v16 )
                goto LABEL_36;
              *((_QWORD *)v16 + 1) = 0;
              v17 = 0;
              *((_WORD *)v16 + 12) = 0;
              *((_BYTE *)v16 + 26) = 0;
              *(_QWORD *)v16 = &CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable';
              *((_QWORD *)v16 + 24) = 0;
              *((_QWORD *)v16 + 25) = v16;
              *((_DWORD *)v16 + 52) = 0;
              *((_DWORD *)v16 + 54) = 0;
              *((_DWORD *)v16 + 56) = 0;
              *((_QWORD *)v16 + 29) = 0;
              while ( v17 < v32 )
              {
                v31[0] = 0;
                v33[0] = 0;
                v24 = 0;
                (*(void (__fastcall **)(__int64 *, _QWORD, _WORD *, _WORD *))(*v27 + 88))(v27, v17, v31, v33);
                StreamInfo = CASFStreamSelector::GetStreamInfo(v18, v9, v31[0], &v24);
                if ( StreamInfo >= 0 )
                {
                  v19 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u);
                  if ( !v19 )
                    goto LABEL_37;
                  v20 = CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v19);
                  v21 = (CASFStreamSelector::STREAM_GROUP *)v20;
                  if ( !v20 )
                    goto LABEL_37;
                  CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(v5, v20);
                  v22 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                    v9,
                                                                    v24);
                  CASFStreamSelector::STREAM_GROUP::Add(v21, v22);
                }
                ++v17;
              }
              if ( StreamInfo < 0 )
                break;
              if ( !(unsigned int)CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add((char *)v1 + 288, v5, 0) )
              {
                CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(v5, v23);
LABEL_36:
                v5 = 0;
LABEL_37:
                StreamInfo = -2147024882;
                break;
              }
            }
          }
          else if ( v27 )
          {
            (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
            v27 = 0;
          }
        }
      }
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
        v27 = 0;
      }
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      if ( v5 )
        CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(v5, v6);
    }
    return (unsigned int)StreamInfo;
  }
  return result;
}

```

## disassembly

```asm
0x1800357c8  push    rbp
0x1800357ca  push    rbx
0x1800357cb  push    rsi
0x1800357cc  push    rdi
0x1800357cd  push    r12
0x1800357cf  push    r13
0x1800357d1  push    r14
0x1800357d3  push    r15
0x1800357d5  lea     rbp, [rsp-1Fh]
0x1800357da  sub     rsp, 98h
0x1800357e1  mov     rax, cs:__security_cookie
0x1800357e8  xor     rax, rsp
0x1800357eb  mov     [rbp+57h+var_48], rax
0x1800357ef  mov     r13, rcx
0x1800357f2  mov     [rbp+57h+var_98], rcx
0x1800357f6  mov     rcx, [rcx+18h]
0x1800357fa  lea     r9, [rbp+57h+var_80]
0x1800357fe  xor     r14d, r14d
0x180035801  lea     r8, IID_IASFUnknownContainer
0x180035808  lea     rdx, CLSID_ASFHeaderObject
0x18003580f  mov     [rbp+57h+var_80], r14
0x180035813  call    ASFGetRootObject
0x180035818  test    eax, eax
0x18003581a  js      loc_180035BD6
0x180035820  mov     rcx, [rbp+57h+var_80]
0x180035824  lea     r8, [rbp+57h+var_88]
0x180035828  mov     [rbp+57h+var_88], r14
0x18003582c  lea     rdx, CLSID_ASFInterStreamDependencyObject
0x180035833  mov     [rbp+57h+var_78], r14
0x180035837  mov     [rbp+57h+var_90], r14
0x18003583b  mov     [rbp+57h+var_60], r14d
0x18003583f  mov     rax, [rcx]
0x180035842  mov     rax, [rax+48h]
0x180035846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003584b  mov     rcx, [rbp+57h+var_80]
0x18003584f  mov     edi, eax
0x180035851  test    rcx, rcx
0x180035854  jz      short loc_180035866
0x180035856  mov     rdx, [rcx]
0x180035859  mov     rax, [rdx+10h]
0x18003585d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035862  mov     [rbp+57h+var_80], r14
0x180035866  test    edi, edi
0x180035868  js      loc_180035BD4
0x18003586e  mov     rcx, [rbp+57h+var_88]
0x180035872  mov     rax, [rcx]
0x180035875  mov     rax, [rax+28h]
0x180035879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003587e  mov     rcx, [rbp+57h+var_88]
0x180035882  lea     r9, [rbp+57h+var_60]
0x180035886  lea     r8, [rbp+57h+var_78]
0x18003588a  mov     edx, 1
0x18003588f  mov     rbx, r14
0x180035892  mov     rax, [rcx]
0x180035895  mov     rax, [rax+18h]
0x180035899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003589e  test    eax, eax
0x1800358a0  jnz     loc_180035B95
0x1800358a6  mov     rcx, [rbp+57h+var_90]
0x1800358aa  test    rcx, rcx
0x1800358ad  jz      short loc_1800358BF
0x1800358af  mov     rax, [rcx]
0x1800358b2  mov     rax, [rax+10h]
0x1800358b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bb  mov     [rbp+57h+var_90], r14
0x1800358bf  mov     rcx, [rbp+57h+var_78]
0x1800358c3  lea     r8, [rbp+57h+var_90]
0x1800358c7  lea     rdx, IID_IASFInterStreamDependencyObject
0x1800358ce  mov     rax, [rcx]
0x1800358d1  mov     rax, [rax]
0x1800358d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358d9  mov     rcx, [rbp+57h+var_78]
0x1800358dd  mov     edi, eax
0x1800358df  test    rcx, rcx
0x1800358e2  jz      short loc_1800358F4
0x1800358e4  mov     rax, [rcx]
0x1800358e7  mov     rax, [rax+10h]
0x1800358eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358f0  mov     [rbp+57h+var_78], r14
0x1800358f4  test    edi, edi
0x1800358f6  js      short loc_18003587E
0x1800358f8  mov     rcx, [rbp+57h+var_90]
0x1800358fc  lea     rdx, [rbp+57h+var_6C]
0x180035900  mov     [rbp+57h+var_6C], r14w
0x180035905  mov     rax, [rcx]
0x180035908  mov     rax, [rax+50h]
0x18003590c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035911  cmp     [rbp+57h+var_6C], r14w
0x180035916  jnz     short loc_18003593A
0x180035918  mov     rcx, [rbp+57h+var_90]
0x18003591c  test    rcx, rcx
0x18003591f  jz      loc_18003587E
0x180035925  mov     rax, [rcx]
0x180035928  mov     rax, [rax+10h]
0x18003592c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035931  mov     [rbp+57h+var_90], r14
0x180035935  jmp     loc_18003587E
0x18003593a  mov     r12d, r14d
0x18003593d  mov     esi, r14d
0x180035940  jbe     loc_18003587E
0x180035946  lea     r15, [r13+40h]
0x18003594a  xor     r13d, r13d
0x18003594d  lea     r14d, [r13+1]
0x180035951  mov     rcx, [rbp+57h+var_90]
0x180035955  lea     r9, [rbp+57h+var_64]
0x180035959  mov     [rbp+57h+var_68], r13w
0x18003595e  lea     r8, [rbp+57h+var_68]
0x180035962  mov     [rbp+57h+var_64], r13w
0x180035967  movzx   edx, si
0x18003596a  mov     [rbp+57h+var_9C], r13d
0x18003596e  mov     rax, [rcx]
0x180035971  mov     rax, [rax+58h]
0x180035975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003597a  movzx   r8d, [rbp+57h+var_68]
0x18003597f  lea     r9, [rbp+57h+var_9C]
0x180035983  mov     rdx, r15
0x180035986  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x18003598b  mov     edi, eax
0x18003598d  test    eax, eax
0x18003598f  js      loc_180035A56
0x180035995  mov     r14d, r13d
0x180035998  cmp     r13w, [rbp+57h+var_64]
0x18003599d  jnb     loc_180035A50
0x1800359a3  mov     rcx, [rbp+57h+var_90]
0x1800359a7  lea     rdx, [rbp+57h+Buf1]
0x1800359ab  xorps   xmm0, xmm0
0x1800359ae  mov     [rbp+57h+var_70], r13w
0x1800359b3  movups  [rbp+57h+Buf1], xmm0
0x1800359b7  mov     [rsp+0D0h+var_B0], rdx
0x1800359bc  lea     r9, [rbp+57h+var_70]
0x1800359c0  mov     rax, [rcx]
0x1800359c3  movzx   r8d, r14w
0x1800359c7  movzx   edx, si
0x1800359ca  mov     [rbp+57h+var_A0], r13d
0x1800359ce  mov     rax, [rax+60h]
0x1800359d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359d7  mov     edi, eax
0x1800359d9  test    eax, eax
0x1800359db  js      short loc_180035A3C
0x1800359dd  movzx   r8d, [rbp+57h+var_70]
0x1800359e2  lea     r9, [rbp+57h+var_A0]
0x1800359e6  mov     rdx, r15
0x1800359e9  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x1800359ee  mov     edi, eax
0x1800359f0  test    eax, eax
0x1800359f2  js      short loc_180035A3C
0x1800359f4  mov     edx, [rbp+57h+var_9C]
0x1800359f7  mov     rcx, r15
0x1800359fa  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800359ff  mov     edx, [rbp+57h+var_A0]
0x180035a02  mov     rcx, r15
0x180035a05  lea     rbx, [rax+20h]
0x180035a09  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180035a0e  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x180035a11  mov     rcx, rbx; this
0x180035a14  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x180035a19  mov     r8d, 10h; Size
0x180035a1f  lea     rdx, CLSID_ASFEnhancementNone; Buf2
0x180035a26  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180035a2a  call    memcmp_0
0x180035a2f  test    eax, eax
0x180035a31  mov     eax, 1
0x180035a36  cmovnz  r12d, eax
0x180035a3a  jmp     short loc_180035A41
0x180035a3c  mov     eax, 1
0x180035a41  add     r14w, ax
0x180035a45  cmp     r14w, [rbp+57h+var_64]
0x180035a4a  jb      loc_1800359A3
0x180035a50  mov     r14d, 1
0x180035a56  add     si, r14w
0x180035a5a  cmp     si, [rbp+57h+var_6C]
0x180035a5e  jb      loc_180035951
0x180035a64  mov     r13, [rbp+57h+var_98]
0x180035a68  xor     r14d, r14d
0x180035a6b  test    r12d, r12d
0x180035a6e  jz      loc_18003587E
0x180035a74  mov     ecx, 0F0h; Size
0x180035a79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035a7e  mov     rbx, rax
0x180035a81  test    rax, rax
0x180035a84  jz      loc_180035B8D
0x180035a8a  mov     [rax+8], r14
0x180035a8e  mov     esi, r14d
0x180035a91  xor     eax, eax
0x180035a93  mov     [rbx+18h], ax
0x180035a97  mov     [rbx+1Ah], al
0x180035a9a  lea     rax, ??_7?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@6B@; const CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable'
0x180035aa1  mov     [rbx], rax
0x180035aa4  mov     [rbx+0C0h], r14
0x180035aab  mov     [rbx+0C8h], rbx
0x180035ab2  mov     [rbx+0D0h], r14d
0x180035ab9  mov     [rbx+0D8h], r14d
0x180035ac0  mov     [rbx+0E0h], r14d
0x180035ac7  mov     [rbx+0E8h], r14
0x180035ace  cmp     si, [rbp+57h+var_6C]
0x180035ad2  jnb     loc_180035B67
0x180035ad8  mov     rcx, [rbp+57h+var_90]
0x180035adc  lea     r9, [rbp+57h+var_68]
0x180035ae0  mov     [rbp+57h+var_70], r14w
0x180035ae5  lea     r8, [rbp+57h+var_70]
0x180035ae9  mov     [rbp+57h+var_68], r14w
0x180035aee  movzx   edx, si
0x180035af1  mov     [rbp+57h+var_A0], r14d
0x180035af5  mov     rax, [rcx]
0x180035af8  mov     rax, [rax+58h]
0x180035afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b01  movzx   r8d, [rbp+57h+var_70]
0x180035b06  lea     r9, [rbp+57h+var_A0]
0x180035b0a  mov     rdx, r15
0x180035b0d  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x180035b12  mov     edi, eax
0x180035b14  test    eax, eax
0x180035b16  js      short loc_180035B5F
0x180035b18  mov     ecx, 0F0h; Size
0x180035b1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035b22  test    rax, rax
0x180035b25  jz      short loc_180035B90
0x180035b27  mov     rcx, rax; this
0x180035b2a  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x180035b2f  mov     r14, rax
0x180035b32  test    rax, rax
0x180035b35  jz      loc_180035BF6
0x180035b3b  mov     rdx, rax
0x180035b3e  mov     rcx, rbx
0x180035b41  call    ?Add@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(CASFStreamSelector::STREAM_GROUP *,ulong *)
0x180035b46  mov     edx, [rbp+57h+var_A0]
0x180035b49  mov     rcx, r15
0x180035b4c  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180035b51  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x180035b54  mov     rcx, r14; this
0x180035b57  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x180035b5c  xor     r14d, r14d
0x180035b5f  inc     si
0x180035b62  jmp     loc_180035ACE
0x180035b67  test    edi, edi
0x180035b69  js      short loc_180035B95
0x180035b6b  lea     rcx, [r13+120h]
0x180035b72  xor     r8d, r8d
0x180035b75  mov     rdx, rbx
0x180035b78  call    ?Add@?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUMULTI_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add(CASFStreamSelector::MULTI_GROUP *,ulong *)
0x180035b7d  test    eax, eax
0x180035b7f  jnz     loc_18003587E
0x180035b85  mov     rcx, rbx; this
0x180035b88  call    ??_GMULTI_GROUP@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(uint)
0x180035b8d  mov     rbx, r14
0x180035b90  mov     edi, 8007000Eh
0x180035b95  mov     rcx, [rbp+57h+var_90]
0x180035b99  test    rcx, rcx
0x180035b9c  jz      short loc_180035BAE
0x180035b9e  mov     rax, [rcx]
0x180035ba1  mov     rax, [rax+10h]
0x180035ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035baa  mov     [rbp+57h+var_90], r14
0x180035bae  mov     rcx, [rbp+57h+var_88]
0x180035bb2  test    rcx, rcx
0x180035bb5  jz      short loc_180035BC7
0x180035bb7  mov     rax, [rcx]
0x180035bba  mov     rax, [rax+10h]
0x180035bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bc3  mov     [rbp+57h+var_88], r14
0x180035bc7  test    rbx, rbx
0x180035bca  jz      short loc_180035BD4
0x180035bcc  mov     rcx, rbx; this
0x180035bcf  call    ??_GMULTI_GROUP@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(uint)
0x180035bd4  mov     eax, edi
0x180035bd6  mov     rcx, [rbp+57h+var_48]
0x180035bda  xor     rcx, rsp; StackCookie
0x180035bdd  call    __security_check_cookie
0x180035be2  add     rsp, 98h
0x180035be9  pop     r15
0x180035beb  pop     r14
0x180035bed  pop     r13
0x180035bef  pop     r12
0x180035bf1  pop     rdi
0x180035bf2  pop     rsi
0x180035bf3  pop     rbx
0x180035bf4  pop     rbp
0x180035bf5  retn
0x180035bf6  xor     r14d, r14d
0x180035bf9  jmp     short loc_180035B90
```
