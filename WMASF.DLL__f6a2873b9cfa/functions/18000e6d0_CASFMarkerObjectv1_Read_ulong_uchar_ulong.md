# CASFMarkerObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000e6d0`
- end: `0x18000edcd`
- name: `?Read@CASFMarkerObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1789`
- prototype: `__int64 __fastcall(CASFMarkerObjectv1 *this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001174`
- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000e5c4`
- `0x18000e6d0`
- `0x180027d44`
- `0x18002e900`
- `0x18002ed90`
- `0x180031360`
- `0x18003f294`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectv1::Read(
        CASFMarkerObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  struct IWMSCriticalSection *v6; // rdx
  unsigned int v9; // r15d
  unsigned int v10; // ebx
  __int128 v11; // xmm0
  unsigned __int64 v12; // rcx
  __int128 v13; // xmm0
  __int64 v14; // r12
  unsigned int v15; // edx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // edi
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  unsigned __int8 *v23; // r12
  __int64 v24; // rcx
  unsigned int i; // eax
  CASFMarker *v26; // rax
  CASFMarker *v27; // rax
  CASFMarker *v28; // rdi
  int v29; // r15d
  unsigned int v30; // r8d
  __int64 v31; // r15
  unsigned int v32; // r13d
  unsigned int v33; // r10d
  void *v34; // rax
  void *v35; // r12
  unsigned int v36; // ecx
  __int64 v37; // r13
  unsigned int j; // r15d
  int v39; // r12d
  int (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // rcx
  GUID *v41; // rbx
  unsigned int v43; // [rsp+30h] [rbp-89h] BYREF
  unsigned __int16 v44; // [rsp+34h] [rbp-85h]
  unsigned int v45; // [rsp+38h] [rbp-81h]
  void *Block; // [rsp+40h] [rbp-79h]
  unsigned int v47; // [rsp+48h] [rbp-71h]
  unsigned int v48; // [rsp+4Ch] [rbp-6Dh]
  _BYTE v49[8]; // [rsp+50h] [rbp-69h] BYREF
  GUID *v50; // [rsp+58h] [rbp-61h]
  unsigned __int8 *v51; // [rsp+60h] [rbp-59h]
  __int64 v52; // [rsp+68h] [rbp-51h]
  __int64 v53; // [rsp+70h] [rbp-49h]
  unsigned __int8 *v54; // [rsp+78h] [rbp-41h]
  __int64 v55; // [rsp+80h] [rbp-39h] BYREF
  __int64 v56; // [rsp+88h] [rbp-31h] BYREF
  __int64 v57; // [rsp+90h] [rbp-29h] BYREF
  __int64 v58; // [rsp+98h] [rbp-21h] BYREF
  _WORD v59[2]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int v60; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-11h] BYREF
  int v62; // [rsp+B0h] [rbp-9h]
  __int64 v63; // [rsp+B8h] [rbp-1h] BYREF
  int v64; // [rsp+C0h] [rbp+7h]
  __int128 Buf1; // [rsp+C8h] [rbp+Fh] BYREF

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v54 = a3;
  v48 = v4;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v49, v6);
  v9 = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    v10 = -1072887818;
LABEL_79:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v49);
    return v10;
  }
  if ( a4 )
  {
    if ( !(_DWORD)v4 )
      goto LABEL_77;
    if ( a3 )
    {
      if ( (unsigned int)v4 >= 0x30 )
      {
        (*(void (__fastcall **)(CASFMarkerObjectv1 *))(*(_QWORD *)this + 160LL))(this);
        v11 = *(_OWORD *)a3;
        v50 = (GUID *)((char *)this + 48);
        *((_OWORD *)this + 3) = v11;
        v12 = *((_QWORD *)a3 + 2);
        *((_QWORD *)this + 8) = v12;
        if ( v12 >= 0x100000000LL )
        {
          v10 = -1072887821;
          goto LABEL_79;
        }
        if ( v4 < v12 )
        {
          *a4 = *((_DWORD *)this + 16);
LABEL_78:
          v10 = -1072887855;
          goto LABEL_79;
        }
        v13 = *(_OWORD *)(a3 + 24);
        v43 = 48;
        *(_OWORD *)((char *)this + 444) = v13;
        v47 = *((_DWORD *)a3 + 10);
        *((_WORD *)this + 230) = *((_WORD *)a3 + 22);
        v14 = *((unsigned __int16 *)a3 + 23);
        v15 = *((unsigned __int16 *)a3 + 23);
        *((_WORD *)this + 231) = v14;
        v16 = CHECK_FOR_SPACE(&v43, v15, v4);
        v10 = -1072887855;
        if ( v16 == -1072887855 )
        {
LABEL_12:
          *a4 = v43;
          goto LABEL_79;
        }
        v17 = *((_QWORD *)this + 5);
        v55 = 0;
        v18 = ASFGetRootObject(v17, &CLSID_ASFHeaderObject, &IID_IASFUnknownContainer, &v55);
        if ( v18 < 0 )
        {
          v10 = v18;
          goto LABEL_79;
        }
        v60 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *))(*(_QWORD *)v55 + 24LL))(
                v55,
                &CLSID_ASFStreamPropertiesObject,
                &v60);
        if ( v19 >= 0 )
        {
          while ( 1 )
          {
            if ( v9 >= v60 )
            {
              v23 = &a3[v14 + 48];
              if ( v55 )
              {
                (*(void (**)(void))(*(_QWORD *)v55 + 16LL))();
                v55 = 0;
              }
              v24 = *((_QWORD *)this + 5);
              v61 = 0;
              v62 = 0;
              ASFGetTimeBase(v24, 0, &v61);
              for ( i = 0; ; i = v45 + 1 )
              {
                v45 = i;
                if ( i >= v47 )
                  break;
                v26 = (CASFMarker *)operator new(0x2A8u);
                if ( !v26 )
                  goto LABEL_67;
                v27 = CASFMarker::CASFMarker(v26);
                v28 = v27;
                if ( !v27 )
                  goto LABEL_67;
                v57 = 0;
                v29 = (**(__int64 (__fastcall ***)(CASFMarker *, GUID *, __int64 *))v27)(v27, &IID_IASFMarkerPriv, &v57);
                if ( v29 < 0 )
                  goto LABEL_70;
                v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, CASFMarkerObjectv1 *))(*(_QWORD *)v57 + 24LL))(
                        v57,
                        *((_QWORD *)this + 5),
                        this);
                if ( v57 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                  v57 = 0;
                }
                if ( v29 < 0 )
                  goto LABEL_70;
                if ( (unsigned int)CHECK_FOR_SPACE(&v43, 0x1Eu, v48) == -1072887855 )
                  goto LABEL_69;
                v31 = *(unsigned int *)(v23 + 26);
                if ( (int)v31 + 1 < (unsigned int)v31 || (unsigned int)(v31 + 1) > 0x7FFFFFFF )
                {
LABEL_68:
                  (*(void (__fastcall **)(CASFMarker *))(*(_QWORD *)v28 + 16LL))(v28);
                  v10 = -2147467259;
                  goto LABEL_79;
                }
                v32 = 2 * v31;
                if ( (unsigned int)CHECK_FOR_SPACE(&v43, 2 * (int)v31, v30) == -1072887855 )
                {
LABEL_69:
                  (*(void (__fastcall **)(CASFMarker *))(*(_QWORD *)v28 + 16LL))(v28);
                  goto LABEL_12;
                }
                v53 = *(_QWORD *)v23;
                v52 = *((_QWORD *)v23 + 1);
                v44 = *((_WORD *)v23 + 8);
                v34 = operator new[](saturated_mul(v33, 2u));
                Block = v34;
                if ( !v34 )
                {
LABEL_66:
                  (*(void (__fastcall **)(CASFMarker *))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_67:
                  v10 = -2147024882;
                  goto LABEL_79;
                }
                v51 = v23 + 30;
                memcpy_0(v34, v23 + 30, v32);
                v35 = Block;
                *((_WORD *)Block + v31) = 0;
                if ( v32 + 12 < v32 )
                  goto LABEL_68;
                if ( v44 <= v32 + 12 )
                {
                  Block = &v51[2 * v31];
                }
                else
                {
                  v36 = v44 - v32;
                  Block = &v51[2 * v31 - 12 + v36];
                  v43 = v43 - 12 + v36;
                }
                v29 = (*(__int64 (__fastcall **)(CASFMarker *, _QWORD, void *))(*(_QWORD *)v28 + 88LL))(v28, 0, v35);
                operator delete(v35);
                if ( v29 < 0
                  || (v63 = 0,
                      v64 = 0,
                      ASFTimeToPresTime(&v61, v52, &v63),
                      v29 = (*(__int64 (__fastcall **)(CASFMarker *, __int64 *))(*(_QWORD *)v28 + 32LL))(v28, &v63),
                      v29 < 0) )
                {
LABEL_70:
                  (*(void (__fastcall **)(CASFMarker *))(*(_QWORD *)v28 + 16LL))(v28);
                  v10 = v29;
                  goto LABEL_79;
                }
                v37 = v53;
                for ( j = 0; j < *((_DWORD *)this + 52); ++j )
                {
                  v39 = (*(__int64 (__fastcall **)(CASFMarker *, _QWORD, __int64))(*(_QWORD *)v28 + 56LL))(
                          v28,
                          (unsigned __int16)j,
                          v37);
                  if ( v39 < 0 )
                  {
                    (*(void (__fastcall **)(CASFMarker *))(*(_QWORD *)v28 + 16LL))(v28);
                    v10 = v39;
                    goto LABEL_79;
                  }
                }
                if ( !(unsigned int)CTDynArray<IASFMarker *,20>::Add((char *)this + 216, v28) )
                  goto LABEL_66;
                v23 = (unsigned __int8 *)Block;
              }
              *a4 = v43;
              v40 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
              if ( v40 && (v57 = 0, (**v40)(v40, &IID_IASFReadWriteTracker, &v57) >= 0) )
              {
                v41 = (GUID *)((char *)this + 48);
                (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v57 + 72LL))(
                  v57,
                  v54,
                  *a4,
                  (char *)this + 48);
                if ( v57 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
              }
              else
              {
                v41 = v50;
              }
              *v41 = CLSID_ASFMarkerObject;
              CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v49);
              return 0;
            }
            v56 = 0;
            v58 = 0;
            v19 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, __int64 *))(*(_QWORD *)v55 + 32LL))(
                    v55,
                    &CLSID_ASFStreamPropertiesObject,
                    v9,
                    &v58);
            if ( v19 < 0 )
              break;
            v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v58)(
                    v58,
                    &IID_IASFStreamPropertiesObject,
                    &v56);
            if ( v58 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              v58 = 0;
            }
            if ( v19 < 0 )
              break;
            v59[0] = 0;
            Buf1 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v56 + 304LL))(v56, v59);
            v22 = v56;
            v19 = v21;
            if ( v21 < 0 )
              goto LABEL_34;
            v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v56 + 80LL))(v56, &Buf1);
            if ( v19 < 0
              || (!memcmp_0(&Buf1, &CLSID_ASFAudioMedia, 0x10u)
               || !memcmp_0(&Buf1, &CLSID_ASFVideoMedia, 0x10u)
               || !memcmp_0(&Buf1, &CLSID_ASFImageMedia, 0x10u))
              && (v19 = (*(__int64 (__fastcall **)(CASFMarkerObjectv1 *, _QWORD, __int64))(*(_QWORD *)this + 104LL))(
                          this,
                          v59[0],
                          1),
                  v19 < 0) )
            {
              v22 = v56;
LABEL_34:
              if ( v22 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                v56 = 0;
              }
              break;
            }
            if ( v56 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
            ++v9;
          }
          v20 = v55;
          if ( !v55 )
            goto LABEL_18;
        }
        else
        {
          v20 = v55;
          if ( !v55 )
          {
LABEL_18:
            v10 = v19;
            goto LABEL_79;
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v20);
        v55 = 0;
        goto LABEL_18;
      }
LABEL_77:
      *a4 = 48;
      goto LABEL_78;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v49);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000e6d0  mov     [rsp-8+arg_8], rbx
0x18000e6d5  push    rbp
0x18000e6d6  push    rsi
0x18000e6d7  push    rdi
0x18000e6d8  push    r12
0x18000e6da  push    r13
0x18000e6dc  push    r14
0x18000e6de  push    r15
0x18000e6e0  lea     rbp, [rsp-27h]
0x18000e6e5  sub     rsp, 0E0h
0x18000e6ec  mov     rax, cs:__security_cookie
0x18000e6f3  xor     rax, rsp
0x18000e6f6  mov     [rbp+57h+var_38], rax
0x18000e6fa  mov     ebx, edx
0x18000e6fc  mov     rsi, rcx
0x18000e6ff  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000e703  mov     r14, r9
0x18000e706  lea     rcx, [rbp+57h+var_C0]; this
0x18000e70a  mov     [rbp+57h+var_98], r8
0x18000e70e  mov     r13, r8
0x18000e711  mov     [rbp+57h+var_C4], ebx
0x18000e714  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000e719  xor     r15d, r15d
0x18000e71c  cmp     [rsi+28h], r15
0x18000e720  jnz     short loc_18000E72C
0x18000e722  mov     ebx, 0C00D07F6h
0x18000e727  jmp     loc_18000ED8B
0x18000e72c  test    r14, r14
0x18000e72f  jz      loc_18000ED98
0x18000e735  mov     edi, 30h ; '0'
0x18000e73a  test    ebx, ebx
0x18000e73c  jz      loc_18000ED83
0x18000e742  test    r13, r13
0x18000e745  jz      loc_18000ED98
0x18000e74b  cmp     ebx, edi
0x18000e74d  jb      loc_18000ED83
0x18000e753  mov     rax, [rsi]
0x18000e756  mov     rcx, rsi
0x18000e759  mov     rax, [rax+0A0h]
0x18000e760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e765  movups  xmm0, xmmword ptr [r13+0]
0x18000e76a  lea     rax, [rsi+30h]
0x18000e76e  mov     [rbp+57h+var_B8], rax
0x18000e772  movdqu  xmmword ptr [rax], xmm0
0x18000e776  mov     rcx, [r13+10h]
0x18000e77a  mov     rax, 100000000h
0x18000e784  mov     [rsi+40h], rcx
0x18000e788  cmp     rcx, rax
0x18000e78b  jb      short loc_18000E797
0x18000e78d  mov     ebx, 0C00D07F3h
0x18000e792  jmp     loc_18000ED8B
0x18000e797  cmp     rbx, rcx
0x18000e79a  jnb     short loc_18000E7A7
0x18000e79c  mov     eax, [rsi+40h]
0x18000e79f  mov     [r14], eax
0x18000e7a2  jmp     loc_18000ED86
0x18000e7a7  movups  xmm0, xmmword ptr [r13+18h]
0x18000e7ac  mov     r8d, ebx; unsigned int
0x18000e7af  mov     [rsp+110h+var_E0], edi
0x18000e7b3  lea     rcx, [rsp+110h+var_E0]; unsigned int *
0x18000e7b8  movdqu  xmmword ptr [rsi+1BCh], xmm0
0x18000e7c0  mov     eax, [r13+28h]
0x18000e7c4  mov     [rbp+57h+var_C8], eax
0x18000e7c7  movzx   eax, word ptr [r13+2Ch]
0x18000e7cc  mov     [rsi+1CCh], ax
0x18000e7d3  movzx   r12d, word ptr [r13+2Eh]
0x18000e7d8  mov     edx, r12d; unsigned int
0x18000e7db  mov     [rsi+1CEh], r12w
0x18000e7e3  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000e7e8  mov     ebx, 0C00D07D1h
0x18000e7ed  cmp     eax, ebx
0x18000e7ef  jnz     short loc_18000E7FD
0x18000e7f1  mov     eax, [rsp+110h+var_E0]
0x18000e7f5  mov     [r14], eax
0x18000e7f8  jmp     loc_18000ED8B
0x18000e7fd  mov     rcx, [rsi+28h]
0x18000e801  lea     r9, [rbp+57h+var_90]
0x18000e805  lea     r8, IID_IASFUnknownContainer
0x18000e80c  mov     [rbp+57h+var_90], r15
0x18000e810  lea     rdx, CLSID_ASFHeaderObject
0x18000e817  call    ASFGetRootObject
0x18000e81c  test    eax, eax
0x18000e81e  jns     short loc_18000E827
0x18000e820  mov     ebx, eax
0x18000e822  jmp     loc_18000ED8B
0x18000e827  mov     rcx, [rbp+57h+var_90]
0x18000e82b  lea     r8, [rbp+57h+var_6C]
0x18000e82f  mov     [rbp+57h+var_6C], r15d
0x18000e833  lea     rdx, CLSID_ASFStreamPropertiesObject
0x18000e83a  mov     rax, [rcx]
0x18000e83d  mov     rax, [rax+18h]
0x18000e841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e846  mov     edi, eax
0x18000e848  test    eax, eax
0x18000e84a  jns     short loc_18000E86C
0x18000e84c  mov     rcx, [rbp+57h+var_90]
0x18000e850  test    rcx, rcx
0x18000e853  jz      short loc_18000E865
0x18000e855  mov     rax, [rcx]
0x18000e858  mov     rax, [rax+10h]
0x18000e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e861  mov     [rbp+57h+var_90], r15
0x18000e865  mov     ebx, edi
0x18000e867  jmp     loc_18000ED8B
0x18000e86c  mov     rcx, [rbp+57h+var_90]
0x18000e870  cmp     r15d, [rbp+57h+var_6C]
0x18000e874  jnb     loc_18000EA04
0x18000e87a  mov     [rbp+57h+var_88], 0
0x18000e882  lea     r9, [rbp+57h+var_78]
0x18000e886  mov     [rbp+57h+var_78], 0
0x18000e88e  lea     rdx, CLSID_ASFStreamPropertiesObject
0x18000e895  mov     rax, [rcx]
0x18000e898  mov     r8d, r15d
0x18000e89b  mov     rax, [rax+20h]
0x18000e89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a4  mov     edi, eax
0x18000e8a6  test    eax, eax
0x18000e8a8  js      loc_18000E9DE
0x18000e8ae  mov     rcx, [rbp+57h+var_78]
0x18000e8b2  lea     r8, [rbp+57h+var_88]
0x18000e8b6  lea     rdx, IID_IASFStreamPropertiesObject
0x18000e8bd  mov     rax, [rcx]
0x18000e8c0  mov     rax, [rax]
0x18000e8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8c8  mov     rcx, [rbp+57h+var_78]
0x18000e8cc  mov     edi, eax
0x18000e8ce  test    rcx, rcx
0x18000e8d1  jz      short loc_18000E8E7
0x18000e8d3  mov     rax, [rcx]
0x18000e8d6  mov     rax, [rax+10h]
0x18000e8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8df  mov     [rbp+57h+var_78], 0
0x18000e8e7  test    edi, edi
0x18000e8e9  js      loc_18000E9DE
0x18000e8ef  mov     rcx, [rbp+57h+var_88]
0x18000e8f3  lea     rdx, [rbp+57h+var_70]
0x18000e8f7  xor     eax, eax
0x18000e8f9  xorps   xmm0, xmm0
0x18000e8fc  mov     [rbp+57h+var_70], ax
0x18000e900  movups  [rbp+57h+Buf1], xmm0
0x18000e904  mov     rax, [rcx]
0x18000e907  mov     rax, [rax+130h]
0x18000e90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e913  mov     rcx, [rbp+57h+var_88]
0x18000e917  mov     edi, eax
0x18000e919  test    eax, eax
0x18000e91b  js      loc_18000E9C5
0x18000e921  mov     rax, [rcx]
0x18000e924  lea     rdx, [rbp+57h+Buf1]
0x18000e928  mov     rax, [rax+50h]
0x18000e92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e931  mov     edi, eax
0x18000e933  test    eax, eax
0x18000e935  js      loc_18000E9C1
0x18000e93b  mov     edi, 10h
0x18000e940  lea     rdx, CLSID_ASFAudioMedia; Buf2
0x18000e947  mov     r8d, edi; Size
0x18000e94a  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000e94e  call    memcmp_0
0x18000e953  test    eax, eax
0x18000e955  jz      short loc_18000E985
0x18000e957  mov     r8d, edi; Size
0x18000e95a  lea     rdx, CLSID_ASFVideoMedia; Buf2
0x18000e961  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000e965  call    memcmp_0
0x18000e96a  test    eax, eax
0x18000e96c  jz      short loc_18000E985
0x18000e96e  mov     r8d, edi; Size
0x18000e971  lea     rdx, CLSID_ASFImageMedia; Buf2
0x18000e978  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000e97c  call    memcmp_0
0x18000e981  test    eax, eax
0x18000e983  jnz     short loc_18000E9A4
0x18000e985  mov     rax, [rsi]
0x18000e988  mov     r8d, 1
0x18000e98e  movzx   edx, [rbp+57h+var_70]
0x18000e992  mov     rcx, rsi
0x18000e995  mov     rax, [rax+68h]
0x18000e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e99e  mov     edi, eax
0x18000e9a0  test    eax, eax
0x18000e9a2  js      short loc_18000E9C1
0x18000e9a4  mov     rcx, [rbp+57h+var_88]
0x18000e9a8  test    rcx, rcx
0x18000e9ab  jz      short loc_18000E9B9
0x18000e9ad  mov     rax, [rcx]
0x18000e9b0  mov     rax, [rax+10h]
0x18000e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b9  inc     r15d
0x18000e9bc  jmp     loc_18000E86C
0x18000e9c1  mov     rcx, [rbp+57h+var_88]
0x18000e9c5  test    rcx, rcx
0x18000e9c8  jz      short loc_18000E9DE
0x18000e9ca  mov     rax, [rcx]
0x18000e9cd  mov     rax, [rax+10h]
0x18000e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d6  mov     [rbp+57h+var_88], 0
0x18000e9de  mov     rcx, [rbp+57h+var_90]
0x18000e9e2  test    rcx, rcx
0x18000e9e5  jz      loc_18000E865
0x18000e9eb  mov     rax, [rcx]
0x18000e9ee  mov     rax, [rax+10h]
0x18000e9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9f7  mov     [rbp+57h+var_90], 0
0x18000e9ff  jmp     loc_18000E865
0x18000ea04  add     r12, 30h ; '0'
0x18000ea08  add     r12, r13
0x18000ea0b  test    rcx, rcx
0x18000ea0e  jz      short loc_18000EA24
0x18000ea10  mov     rax, [rcx]
0x18000ea13  mov     rax, [rax+10h]
0x18000ea17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1c  mov     [rbp+57h+var_90], 0
0x18000ea24  mov     rcx, [rsi+28h]
0x18000ea28  lea     r8, [rbp+57h+var_68]
0x18000ea2c  xor     eax, eax
0x18000ea2e  xor     edx, edx
0x18000ea30  mov     [rbp+57h+var_68], rax
0x18000ea34  mov     [rbp+57h+var_60], eax
0x18000ea37  call    ASFGetTimeBase
0x18000ea3c  xor     eax, eax
0x18000ea3e  mov     [rsp+110h+var_D8], eax
0x18000ea42  cmp     eax, [rbp+57h+var_C8]
0x18000ea45  jnb     loc_18000ED00
0x18000ea4b  mov     ecx, 2A8h; Size
0x18000ea50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea55  test    rax, rax
0x18000ea58  jz      loc_18000ECB2
0x18000ea5e  mov     rcx, rax; this
0x18000ea61  call    ??0CASFMarker@@QEAA@XZ; CASFMarker::CASFMarker(void)
0x18000ea66  mov     rdi, rax
0x18000ea69  test    rax, rax
0x18000ea6c  jz      loc_18000ECB2
0x18000ea72  mov     [rbp+57h+var_80], 0
0x18000ea7a  lea     r8, [rbp+57h+var_80]
0x18000ea7e  mov     rax, [rax]
0x18000ea81  lea     rdx, IID_IASFMarkerPriv
0x18000ea88  mov     rcx, rdi
0x18000ea8b  mov     rax, [rax]
0x18000ea8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea93  mov     r15d, eax
0x18000ea96  test    eax, eax
0x18000ea98  js      loc_18000ECE9
0x18000ea9e  mov     rcx, [rbp+57h+var_80]
0x18000eaa2  mov     r8, rsi
0x18000eaa5  mov     rdx, [rsi+28h]
0x18000eaa9  mov     rax, [rcx]
0x18000eaac  mov     rax, [rax+18h]
0x18000eab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab5  mov     rcx, [rbp+57h+var_80]
0x18000eab9  mov     r15d, eax
0x18000eabc  test    rcx, rcx
0x18000eabf  jz      short loc_18000EAD5
0x18000eac1  mov     rax, [rcx]
0x18000eac4  mov     rax, [rax+10h]
0x18000eac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eacd  mov     [rbp+57h+var_80], 0
0x18000ead5  test    r15d, r15d
0x18000ead8  js      loc_18000ECE9
0x18000eade  mov     r8d, [rbp+57h+var_C4]; unsigned int
0x18000eae2  lea     rcx, [rsp+110h+var_E0]; unsigned int *
0x18000eae7  mov     edx, 1Eh; unsigned int
0x18000eaec  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000eaf1  cmp     eax, ebx
0x18000eaf3  jz      loc_18000ECD5
0x18000eaf9  mov     r15d, [r12+1Ah]
0x18000eafe  lea     r10d, [r15+1]
0x18000eb02  cmp     r10d, r15d
0x18000eb05  jb      loc_18000ECBC
0x18000eb0b  cmp     r10d, 7FFFFFFFh
0x18000eb12  ja      loc_18000ECBC
0x18000eb18  lea     r13d, [r15+r15]
0x18000eb1c  mov     edx, r13d; unsigned int
0x18000eb1f  lea     rcx, [rsp+110h+var_E0]; unsigned int *
0x18000eb24  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000eb29  cmp     eax, ebx
0x18000eb2b  jz      loc_18000ECD5
0x18000eb31  mov     rax, [r12]
0x18000eb35  mov     [rbp+57h+var_A0], rax
0x18000eb39  mov     rax, [r12+8]
0x18000eb3e  mov     [rbp+57h+var_A8], rax
0x18000eb42  movzx   eax, word ptr [r12+10h]
0x18000eb48  mov     [rsp+110h+var_DC], ax
0x18000eb4d  mov     eax, 2
0x18000eb52  mov     ecx, r10d
0x18000eb55  mul     rcx
0x18000eb58  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000eb5f  cmovb   rax, rcx
0x18000eb63  mov     rcx, rax; unsigned __int64
0x18000eb66  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000eb6b  mov     [rbp+57h+Block], rax
0x18000eb6f  test    rax, rax
0x18000eb72  jz      loc_18000ECA3
0x18000eb78  lea     rcx, [r12+1Eh]
0x18000eb7d  mov     r8d, r13d; Size
0x18000eb80  mov     [rbp+57h+var_B0], rcx
0x18000eb84  mov     rdx, rcx; Src
0x18000eb87  mov     rcx, rax; void *
0x18000eb8a  call    memcpy_0
0x18000eb8f  mov     r12, [rbp+57h+Block]
  ... truncated ...
```
