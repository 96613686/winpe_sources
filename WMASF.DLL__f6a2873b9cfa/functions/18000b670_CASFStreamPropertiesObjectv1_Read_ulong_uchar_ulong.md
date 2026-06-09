# CASFStreamPropertiesObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000b670`
- end: `0x18000bb1f`
- name: `?Read@CASFStreamPropertiesObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1199`
- prototype: `__int64 __fastcall(CASFStreamPropertiesObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000a5e4`
- `0x18000a8b8`
- `0x18000aab4`
- `0x18000abc4`
- `0x18000ac64`
- `0x18000b670`
- `0x18001fe00`
- `0x1800310c0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectv1::Read(
        CASFStreamPropertiesObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  int v8; // edi
  unsigned __int64 v9; // rcx
  unsigned int v10; // r10d
  __int16 v11; // ax
  unsigned __int64 v12; // r10
  void *v13; // rax
  unsigned int v14; // edx
  __int64 v15; // rdi
  void *v16; // rax
  int (__fastcall ***v17)(_QWORD, GUID *, unsigned int *); // rcx
  __int64 v18; // rdi
  __int64 (__fastcall ***v19)(__int64, GUID *, __int64 *); // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  GUID *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  GUID *v29; // rdx
  __int64 v30; // rax
  _BYTE v32[8]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v33; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v34[2]; // [rsp+40h] [rbp-10h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v32, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
    goto LABEL_69;
  }
  if ( a4 )
  {
    if ( !(_DWORD)v4 )
      goto LABEL_67;
    if ( a3 )
    {
      if ( (unsigned int)v4 >= 0x4E )
      {
        CASFStreamPropertiesObjectBase::FreshStart(this);
        *((_OWORD *)this + 3) = *(_OWORD *)a3;
        v9 = *((_QWORD *)a3 + 2);
        *((_QWORD *)this + 8) = v9;
        if ( v9 >= 0x100000000LL )
        {
          v8 = -1072887821;
          goto LABEL_69;
        }
        if ( v4 < v9 )
        {
          *a4 = *((_DWORD *)this + 16);
LABEL_68:
          v8 = -1072887855;
          goto LABEL_69;
        }
        *(_OWORD *)((char *)this + 88) = *(_OWORD *)(a3 + 24);
        *(_OWORD *)((char *)this + 696) = *(_OWORD *)(a3 + 40);
        *((_QWORD *)this + 13) = *((_QWORD *)a3 + 7);
        v10 = *((unsigned __int16 *)a3 + 32);
        *((_WORD *)this + 208) = v10;
        *((_DWORD *)this + 178) = *((_DWORD *)a3 + 17);
        v11 = *((_WORD *)a3 + 36);
        *((_WORD *)this + 92) = v11;
        if ( v11 < 0 )
        {
          *((_DWORD *)this + 40) = 1;
          *((_WORD *)this + 92) = v11 & 0x7FFF;
        }
        v34[0] = 78;
        v8 = -1072887855;
        if ( (unsigned int)CHECK_FOR_SPACE(v34, v10, v4) != -1072887855 )
        {
          v13 = operator new[](v12);
          *((_QWORD *)this + 53) = v13;
          if ( !v13 )
          {
            *((_WORD *)this + 208) = 0;
            goto LABEL_16;
          }
          memcpy_0(v13, a3 + 78, *((unsigned __int16 *)this + 208));
          if ( (unsigned int)CHECK_FOR_SPACE(v34, *((_DWORD *)this + 178), v4) != -1072887855 )
          {
            v15 = *((unsigned __int16 *)this + 208);
            v16 = operator new[](v14);
            *((_QWORD *)this + 90) = v16;
            if ( v16 )
            {
              memcpy_0(v16, &a3[v15 + 78], *((unsigned int *)this + 178));
              v17 = (int (__fastcall ***)(_QWORD, GUID *, unsigned int *))*((_QWORD *)this + 5);
              v18 = v34[0];
              if ( v17 )
              {
                *(_QWORD *)v34 = 0;
                if ( (**v17)(v17, &IID_IASFReadWriteTracker, v34) >= 0 )
                {
                  (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v34 + 72LL))(
                    *(_QWORD *)v34,
                    a3,
                    (unsigned int)v18,
                    (char *)this + 48);
                  if ( *(_QWORD *)v34 )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 16LL))(*(_QWORD *)v34);
                }
              }
              *((GUID *)this + 3) = CLSID_ASFStreamPropertiesObject;
              if ( *((_QWORD *)this + 8) != v18 )
              {
                v8 = -1072887838;
                goto LABEL_69;
              }
              *a4 = v18;
              (*(void (__fastcall **)(CASFStreamPropertiesObjectv1 *, __int64))(*(_QWORD *)this + 248LL))(this, 2);
              (*(void (__fastcall **)(CASFStreamPropertiesObjectv1 *, __int64))(*(_QWORD *)this + 280LL))(this, 2);
              v19 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))*((_QWORD *)this + 5);
              v33 = 0;
              v8 = ASFGetHeaderObject(
                     v19,
                     &CLSID_ASFFilePropertiesObject,
                     (__int64)&IID_IASFFilePropertiesObjectv1,
                     (__int64)&v33);
              if ( v8 >= 0 )
              {
                *(_QWORD *)v34 = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, v34);
                if ( v8 >= 0 )
                  *((_DWORD *)this + 182) = *(_QWORD *)v34 / 0x2710uLL;
                if ( v33 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  v33 = 0;
                }
              }
              v20 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeAcmAudio.Data1;
              if ( !v20 )
                v20 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeAcmAudio.Data4;
              if ( v20 )
              {
                v22 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeIcmVideo.Data1;
                if ( !v22 )
                  v22 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeIcmVideo.Data4;
                if ( v22 )
                {
                  v23 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeJpegJfifVideo.Data1;
                  if ( !v23 )
                    v23 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeJpegJfifVideo.Data4;
                  if ( v23 )
                  {
                    v24 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeDegradableJpeg.Data1;
                    if ( !v24 )
                      v24 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeDegradableJpeg.Data4;
                    if ( v24 )
                    {
                      v25 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeScriptCommand.Data1;
                      if ( !v25 )
                        v25 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeScriptCommand.Data4;
                      if ( v25 )
                      {
                        v27 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeAnsiUrl.Data1;
                        if ( !v27 )
                          v27 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeAnsiUrl.Data4;
                        if ( v27 )
                        {
                          v28 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeArbitraryData.Data1;
                          if ( !v28 )
                            v28 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeArbitraryData.Data4;
                          if ( v28 )
                          {
                            v30 = *((_QWORD *)this + 11) - *(_QWORD *)&CLSID_AsfXStreamTypeFileTransfer.Data1;
                            if ( !v30 )
                              v30 = *((_QWORD *)this + 12) - *(_QWORD *)CLSID_AsfXStreamTypeFileTransfer.Data4;
                            if ( v30 )
                              goto LABEL_69;
                            CAutoCritSec::CAutoCritSec((CAutoCritSec *)v34, *((struct IWMSCriticalSection **)this + 4));
                            v29 = &CLSID_ASFFileTransferMedia;
                          }
                          else
                          {
                            CAutoCritSec::CAutoCritSec((CAutoCritSec *)v34, *((struct IWMSCriticalSection **)this + 4));
                            v29 = &CLSID_ASFDirectShowMedia;
                          }
                          v8 = (*(__int64 (__fastcall **)(CASFStreamPropertiesObjectv1 *, GUID *))(*(_QWORD *)this + 88LL))(
                                 this,
                                 v29);
                          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v34);
LABEL_69:
                          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v32);
                          return (unsigned int)v8;
                        }
                        v26 = &CLSID_ASFCommandURL;
                      }
                      else
                      {
                        v26 = &CLSID_ASFCommandScript;
                      }
                      v21 = CASFStreamPropertiesObjectv1::ConvertScriptProperties(this, v26);
                    }
                    else
                    {
                      v21 = CASFStreamPropertiesObjectv1::ConvertDJpegImageProperties(this);
                    }
                  }
                  else
                  {
                    v21 = CASFStreamPropertiesObjectv1::ConvertJpegImageProperties(this);
                  }
                }
                else
                {
                  v21 = CASFStreamPropertiesObjectv1::ConvertVideoProperties(this);
                }
              }
              else
              {
                v21 = CASFStreamPropertiesObjectv1::ConvertAudioProperties(this);
              }
              v8 = v21;
              goto LABEL_69;
            }
            *((_DWORD *)this + 178) = 0;
LABEL_16:
            v8 = -2147024882;
            goto LABEL_69;
          }
        }
        *a4 = v34[0];
        goto LABEL_69;
      }
LABEL_67:
      *a4 = 78;
      goto LABEL_68;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v32);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b670  mov     [rsp-38h+arg_8], rbx
0x18000b675  push    rbp
0x18000b676  push    rsi
0x18000b677  push    rdi
0x18000b678  push    r12
0x18000b67a  push    r13
0x18000b67c  push    r14
0x18000b67e  push    r15
0x18000b680  mov     rbp, rsp
0x18000b683  sub     rsp, 50h
0x18000b687  mov     rax, cs:__security_cookie
0x18000b68e  xor     rax, rsp
0x18000b691  mov     [rbp+var_8], rax
0x18000b695  mov     r15d, edx
0x18000b698  mov     rbx, rcx
0x18000b69b  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000b69f  mov     rsi, r9
0x18000b6a2  lea     rcx, [rbp+var_20]; this
0x18000b6a6  mov     r14, r8
0x18000b6a9  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000b6ae  xor     r13d, r13d
0x18000b6b1  cmp     [rbx+28h], r13
0x18000b6b5  jnz     short loc_18000B6C1
0x18000b6b7  mov     edi, 0C00D07F6h
0x18000b6bc  jmp     loc_18000BAE0
0x18000b6c1  test    rsi, rsi
0x18000b6c4  jz      loc_18000BAED
0x18000b6ca  mov     edi, 4Eh ; 'N'
0x18000b6cf  test    r15d, r15d
0x18000b6d2  jz      loc_18000BAD9
0x18000b6d8  test    r14, r14
0x18000b6db  jz      loc_18000BAED
0x18000b6e1  cmp     r15d, edi
0x18000b6e4  jb      loc_18000BAD9
0x18000b6ea  mov     rcx, rbx; this
0x18000b6ed  call    ?FreshStart@CASFStreamPropertiesObjectBase@@IEAAXXZ; CASFStreamPropertiesObjectBase::FreshStart(void)
0x18000b6f2  movups  xmm0, xmmword ptr [r14]
0x18000b6f6  lea     r12, [rbx+30h]
0x18000b6fa  mov     rax, 100000000h
0x18000b704  movdqu  xmmword ptr [r12], xmm0
0x18000b70a  mov     rcx, [r14+10h]
0x18000b70e  mov     [rbx+40h], rcx
0x18000b712  cmp     rcx, rax
0x18000b715  jb      short loc_18000B721
0x18000b717  mov     edi, 0C00D07F3h
0x18000b71c  jmp     loc_18000BAE0
0x18000b721  cmp     r15, rcx
0x18000b724  jnb     short loc_18000B730
0x18000b726  mov     eax, [rbx+40h]
0x18000b729  mov     [rsi], eax
0x18000b72b  jmp     loc_18000BADB
0x18000b730  movups  xmm0, xmmword ptr [r14+18h]
0x18000b735  movdqu  xmmword ptr [rbx+58h], xmm0
0x18000b73a  movups  xmm0, xmmword ptr [r14+28h]
0x18000b73f  movdqu  xmmword ptr [rbx+2B8h], xmm0
0x18000b747  mov     rax, [r14+38h]
0x18000b74b  mov     [rbx+68h], rax
0x18000b74f  movzx   r10d, word ptr [r14+40h]
0x18000b754  mov     [rbx+1A0h], r10w
0x18000b75c  mov     eax, [r14+44h]
0x18000b760  mov     [rbx+2C8h], eax
0x18000b766  movzx   eax, word ptr [r14+48h]
0x18000b76b  mov     [rbx+0B8h], ax
0x18000b772  test    ax, ax
0x18000b775  jns     short loc_18000B790
0x18000b777  mov     ecx, 7FFFh
0x18000b77c  mov     dword ptr [rbx+0A0h], 1
0x18000b786  and     ax, cx
0x18000b789  mov     [rbx+0B8h], ax
0x18000b790  mov     edx, r10d; unsigned int
0x18000b793  mov     [rbp+var_10], edi
0x18000b796  mov     r8d, r15d; unsigned int
0x18000b799  lea     rcx, [rbp+var_10]; unsigned int *
0x18000b79d  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000b7a2  mov     edi, 0C00D07D1h
0x18000b7a7  cmp     eax, edi
0x18000b7a9  jz      loc_18000BAD2
0x18000b7af  mov     rcx, r10; unsigned __int64
0x18000b7b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b7b7  mov     [rbx+1A8h], rax
0x18000b7be  test    rax, rax
0x18000b7c1  jnz     short loc_18000B7D5
0x18000b7c3  mov     [rbx+1A0h], r13w
0x18000b7cb  mov     edi, 8007000Eh
0x18000b7d0  jmp     loc_18000BAE0
0x18000b7d5  movzx   r8d, word ptr [rbx+1A0h]; Size
0x18000b7dd  lea     r13, [r14+4Eh]
0x18000b7e1  mov     rdx, r13; Src
0x18000b7e4  mov     rcx, rax; void *
0x18000b7e7  call    memcpy_0
0x18000b7ec  mov     edx, [rbx+2C8h]; unsigned int
0x18000b7f2  lea     rcx, [rbp+var_10]; unsigned int *
0x18000b7f6  mov     r8d, r15d; unsigned int
0x18000b7f9  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000b7fe  cmp     eax, edi
0x18000b800  jz      loc_18000BAD2
0x18000b806  movzx   edi, word ptr [rbx+1A0h]
0x18000b80d  mov     ecx, edx; unsigned __int64
0x18000b80f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b814  xor     r15d, r15d
0x18000b817  mov     [rbx+2D0h], rax
0x18000b81e  test    rax, rax
0x18000b821  jnz     short loc_18000B82C
0x18000b823  mov     [rbx+2C8h], r15d
0x18000b82a  jmp     short loc_18000B7CB
0x18000b82c  mov     r8d, [rbx+2C8h]; Size
0x18000b833  lea     rdx, [rdi+r13]; Src
0x18000b837  mov     rcx, rax; void *
0x18000b83a  call    memcpy_0
0x18000b83f  mov     rcx, [rbx+28h]
0x18000b843  mov     edi, [rbp+var_10]
0x18000b846  test    rcx, rcx
0x18000b849  jz      short loc_18000B897
0x18000b84b  mov     qword ptr [rbp+var_10], r15
0x18000b84f  lea     r8, [rbp+var_10]
0x18000b853  mov     rax, [rcx]
0x18000b856  lea     rdx, IID_IASFReadWriteTracker
0x18000b85d  mov     rax, [rax]
0x18000b860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b865  test    eax, eax
0x18000b867  js      short loc_18000B897
0x18000b869  mov     rcx, qword ptr [rbp+var_10]
0x18000b86d  mov     r9, r12
0x18000b870  mov     r8d, edi
0x18000b873  mov     rdx, r14
0x18000b876  mov     rax, [rcx]
0x18000b879  mov     rax, [rax+48h]
0x18000b87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b882  mov     rcx, qword ptr [rbp+var_10]
0x18000b886  test    rcx, rcx
0x18000b889  jz      short loc_18000B897
0x18000b88b  mov     rax, [rcx]
0x18000b88e  mov     rax, [rax+10h]
0x18000b892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b897  movups  xmm0, xmmword ptr cs:CLSID_ASFStreamPropertiesObject.Data1
0x18000b89e  movdqu  xmmword ptr [r12], xmm0
0x18000b8a4  cmp     [rbx+40h], rdi
0x18000b8a8  jz      short loc_18000B8B4
0x18000b8aa  mov     edi, 0C00D07E2h
0x18000b8af  jmp     loc_18000BAE0
0x18000b8b4  mov     [rsi], edi
0x18000b8b6  mov     rcx, rbx
0x18000b8b9  mov     rax, [rbx]
0x18000b8bc  mov     edi, 2
0x18000b8c1  mov     edx, edi
0x18000b8c3  mov     rax, [rax+0F8h]
0x18000b8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8cf  mov     rax, [rbx]
0x18000b8d2  mov     edx, edi
0x18000b8d4  mov     rcx, rbx
0x18000b8d7  mov     rax, [rax+118h]
0x18000b8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8e3  mov     rcx, [rbx+28h]
0x18000b8e7  lea     r9, [rbp+var_18]
0x18000b8eb  lea     r8, IID_IASFFilePropertiesObjectv1
0x18000b8f2  mov     [rbp+var_18], r15
0x18000b8f6  lea     rdx, CLSID_ASFFilePropertiesObject
0x18000b8fd  call    ASFGetHeaderObject
0x18000b902  mov     edi, eax
0x18000b904  test    eax, eax
0x18000b906  js      short loc_18000B957
0x18000b908  mov     rcx, [rbp+var_18]
0x18000b90c  lea     rdx, [rbp+var_10]
0x18000b910  mov     qword ptr [rbp+var_10], r15
0x18000b914  mov     rax, [rcx]
0x18000b917  mov     rax, [rax+18h]
0x18000b91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b920  mov     edi, eax
0x18000b922  test    eax, eax
0x18000b924  js      short loc_18000B93E
0x18000b926  mov     rax, 346DC5D63886594Bh
0x18000b930  mul     qword ptr [rbp+var_10]
0x18000b934  shr     rdx, 0Bh
0x18000b938  mov     [rbx+2D8h], edx
0x18000b93e  mov     rcx, [rbp+var_18]
0x18000b942  test    rcx, rcx
0x18000b945  jz      short loc_18000B957
0x18000b947  mov     rax, [rcx]
0x18000b94a  mov     rax, [rax+10h]
0x18000b94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b953  mov     [rbp+var_18], r15
0x18000b957  mov     rax, [rbx+58h]
0x18000b95b  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeAcmAudio.Data1
0x18000b962  jnz     short loc_18000B96F
0x18000b964  mov     rax, [rbx+60h]
0x18000b968  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeAcmAudio.Data4
0x18000b96f  test    rax, rax
0x18000b972  jnz     short loc_18000B981
0x18000b974  mov     rcx, rbx; this
0x18000b977  call    ?ConvertAudioProperties@CASFStreamPropertiesObjectv1@@IEAAJXZ; CASFStreamPropertiesObjectv1::ConvertAudioProperties(void)
0x18000b97c  jmp     loc_18000BA4B
0x18000b981  mov     rax, [rbx+58h]
0x18000b985  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeIcmVideo.Data1
0x18000b98c  jnz     short loc_18000B999
0x18000b98e  mov     rax, [rbx+60h]
0x18000b992  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeIcmVideo.Data4
0x18000b999  test    rax, rax
0x18000b99c  jnz     short loc_18000B9AB
0x18000b99e  mov     rcx, rbx; this
0x18000b9a1  call    ?ConvertVideoProperties@CASFStreamPropertiesObjectv1@@IEAAJXZ; CASFStreamPropertiesObjectv1::ConvertVideoProperties(void)
0x18000b9a6  jmp     loc_18000BA4B
0x18000b9ab  mov     rax, [rbx+58h]
0x18000b9af  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeJpegJfifVideo.Data1
0x18000b9b6  jnz     short loc_18000B9C3
0x18000b9b8  mov     rax, [rbx+60h]
0x18000b9bc  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeJpegJfifVideo.Data4
0x18000b9c3  test    rax, rax
0x18000b9c6  jnz     short loc_18000B9D2
0x18000b9c8  mov     rcx, rbx; this
0x18000b9cb  call    ?ConvertJpegImageProperties@CASFStreamPropertiesObjectv1@@IEAAJXZ; CASFStreamPropertiesObjectv1::ConvertJpegImageProperties(void)
0x18000b9d0  jmp     short loc_18000BA4B
0x18000b9d2  mov     rax, [rbx+58h]
0x18000b9d6  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeDegradableJpeg.Data1
0x18000b9dd  jnz     short loc_18000B9EA
0x18000b9df  mov     rax, [rbx+60h]
0x18000b9e3  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeDegradableJpeg.Data4
0x18000b9ea  test    rax, rax
0x18000b9ed  jnz     short loc_18000B9F9
0x18000b9ef  mov     rcx, rbx; this
0x18000b9f2  call    ?ConvertDJpegImageProperties@CASFStreamPropertiesObjectv1@@IEAAJXZ; CASFStreamPropertiesObjectv1::ConvertDJpegImageProperties(void)
0x18000b9f7  jmp     short loc_18000BA4B
0x18000b9f9  mov     rax, [rbx+58h]
0x18000b9fd  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeScriptCommand.Data1
0x18000ba04  jnz     short loc_18000BA11
0x18000ba06  mov     rax, [rbx+60h]
0x18000ba0a  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeScriptCommand.Data4
0x18000ba11  test    rax, rax
0x18000ba14  jnz     short loc_18000BA1F
0x18000ba16  lea     rdx, CLSID_ASFCommandScript
0x18000ba1d  jmp     short loc_18000BA43
0x18000ba1f  mov     rax, [rbx+58h]
0x18000ba23  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeAnsiUrl.Data1
0x18000ba2a  jnz     short loc_18000BA37
0x18000ba2c  mov     rax, [rbx+60h]
0x18000ba30  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeAnsiUrl.Data4
0x18000ba37  test    rax, rax
0x18000ba3a  jnz     short loc_18000BA52
0x18000ba3c  lea     rdx, CLSID_ASFCommandURL; struct _GUID *
0x18000ba43  mov     rcx, rbx; this
0x18000ba46  call    ?ConvertScriptProperties@CASFStreamPropertiesObjectv1@@IEAAJAEBU_GUID@@@Z; CASFStreamPropertiesObjectv1::ConvertScriptProperties(_GUID const &)
0x18000ba4b  mov     edi, eax
0x18000ba4d  jmp     loc_18000BAE0
0x18000ba52  mov     rax, [rbx+58h]
0x18000ba56  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeArbitraryData.Data1
0x18000ba5d  jnz     short loc_18000BA6A
0x18000ba5f  mov     rax, [rbx+60h]
0x18000ba63  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeArbitraryData.Data4
0x18000ba6a  test    rax, rax
0x18000ba6d  jnz     short loc_18000BA85
0x18000ba6f  mov     rdx, [rbx+20h]; struct IWMSCriticalSection *
0x18000ba73  lea     rcx, [rbp+var_10]; this
0x18000ba77  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000ba7c  lea     rdx, CLSID_ASFDirectShowMedia
0x18000ba83  jmp     short loc_18000BAB6
0x18000ba85  mov     rax, [rbx+58h]
0x18000ba89  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeFileTransfer.Data1
0x18000ba90  jnz     short loc_18000BA9D
0x18000ba92  mov     rax, [rbx+60h]
0x18000ba96  sub     rax, qword ptr cs:CLSID_AsfXStreamTypeFileTransfer.Data4
0x18000ba9d  test    rax, rax
0x18000baa0  jnz     short loc_18000BAE0
0x18000baa2  mov     rdx, [rbx+20h]; struct IWMSCriticalSection *
0x18000baa6  lea     rcx, [rbp+var_10]; this
0x18000baaa  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000baaf  lea     rdx, CLSID_ASFFileTransferMedia
0x18000bab6  mov     rax, [rbx]
0x18000bab9  mov     rcx, rbx
0x18000babc  mov     rax, [rax+58h]
0x18000bac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac5  lea     rcx, [rbp+var_10]; this
0x18000bac9  mov     edi, eax
0x18000bacb  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000bad0  jmp     short loc_18000BAE0
0x18000bad2  mov     eax, [rbp+var_10]
0x18000bad5  mov     [rsi], eax
0x18000bad7  jmp     short loc_18000BAE0
0x18000bad9  mov     [rsi], edi
0x18000badb  mov     edi, 0C00D07D1h
0x18000bae0  lea     rcx, [rbp+var_20]; this
0x18000bae4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000bae9  mov     eax, edi
0x18000baeb  jmp     short loc_18000BAFB
0x18000baed  lea     rcx, [rbp+var_20]; this
0x18000baf1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000baf6  mov     eax, 80070057h
0x18000bafb  mov     rcx, [rbp+var_8]
0x18000baff  xor     rcx, rsp; StackCookie
0x18000bb02  call    __security_check_cookie
0x18000bb07  mov     rbx, [rsp+50h+arg_8]
0x18000bb0f  add     rsp, 50h
0x18000bb13  pop     r15
0x18000bb15  pop     r14
0x18000bb17  pop     r13
0x18000bb19  pop     r12
0x18000bb1b  pop     rdi
0x18000bb1c  pop     rsi
0x18000bb1d  pop     rbp
0x18000bb1e  retn
```
