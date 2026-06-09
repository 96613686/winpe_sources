# CClCerts::get_Item(tagVARIANT,tagVARIANT *)

- ea: `0x18004d9b0`
- end: `0x18004deb4`
- name: `?get_Item@CClCerts@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `1284`
- prototype: `int(CClCerts *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a38`
- `0x180006ed4`
- `0x180023d86`
- `0x180023dd0`
- `0x18003537c`
- `0x1800406b0`
- `0x18004ad4c`
- `0x18004ca64`
- `0x18004d9b0`
- `0x180060bd4`
- `0x180061b54`
- `0x180061d44`
- `0x180061e10`
- `0x1800621bc`
- `0x180064010`

## import_xrefs

- `msvcrt!strchr` at `0x18004dc59`
- `msvcrt!strchr` at `0x18004dc59`
- `msvcrt!strcpy_s` at `0x18004dc4e`
- `msvcrt!strcpy_s` at `0x18004dc4e`
- `OLEAUT32!__imp_VariantInit` at `0x18004da14`
- `OLEAUT32!__imp_VariantInit` at `0x18004da31`
- `OLEAUT32!__imp_VariantInit` at `0x18004da14`
- `OLEAUT32!__imp_VariantInit` at `0x18004da31`
- `OLEAUT32!__imp_VariantClear` at `0x18004de78`
- `OLEAUT32!__imp_VariantClear` at `0x18004de78`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004dd25`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004dd25`
- `KERNEL32!GetACP` at `0x18004dab3`
- `KERNEL32!GetACP` at `0x18004dab3`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004de0f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004de0f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004dbd5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004dbd5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004dc1b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004dc1b`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004dbc7`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004dbc7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004dc01`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004dc01`

## pseudocode

```c
__int64 __fastcall CClCerts::get_Item(CRequest **this, struct tagVARIANT *p_pvarg, struct tagVARIANT *a3)
{
  __int64 v6; // r13
  int Variables; // ebx
  VARTYPE vt; // di
  CRequest *v10; // r15
  __int64 v11; // rax
  UINT ACP; // r9d
  unsigned int v13; // r14d
  __int64 i; // rdi
  __int64 v15; // rax
  const char *v16; // rcx
  int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // eax
  const CHAR *Ptr; // r15
  char *v22; // rdi
  __int64 v23; // rdx
  __int64 j; // rsi
  char *v25; // rax
  const char *v26; // r8
  __int64 v27; // rdi
  int v28; // eax
  UINT v29; // r8d
  const char *v30; // rdx
  struct CLinkElem *Elem; // rax
  __int64 lVal; // rax
  void (__fastcall ***v33)(_QWORD, GUID *, ULONG *); // rcx
  CRequest *v34; // rcx
  CClCert *v35; // rax
  struct IUnknown *v36; // rdx
  void (*v37)(void); // r8
  CClCert *v38; // rax
  unsigned __int16 *v39; // [rsp+20h] [rbp-E0h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v41[48]; // [rsp+40h] [rbp-C0h] BYREF
  void *v42; // [rsp+70h] [rbp-90h] BYREF
  char v43; // [rsp+78h] [rbp-88h] BYREF
  int v44; // [rsp+178h] [rbp+78h]
  unsigned __int8 v45[256]; // [rsp+180h] [rbp+80h] BYREF

  v6 = 0;
  if ( (int)CRequest::CheckForTombstone(this[7]) < 0 )
    return 2147500037LL;
  v44 = 0;
  v42 = &v43;
  VariantInit(a3);
  Variables = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  switch ( p_pvarg->vt )
  {
    case 8u:
      vt = 8;
LABEL_11:
      v10 = this[7];
      v11 = *((_QWORD *)v10 + 7);
      if ( (*(_BYTE *)(v11 + 320) & 8) != 0 )
      {
        ACP = *(_DWORD *)(*(_QWORD *)(v11 + 56) + 164LL);
        if ( !ACP )
          ACP = GetACP();
        Variables = CRequest::LoadVariables(v10, 5u, *(char **)(*((_QWORD *)this[7] + 7) + 48LL), ACP);
        if ( Variables < 0 )
          goto LABEL_80;
        *(_DWORD *)(*((_QWORD *)this[7] + 7) + 320LL) &= ~8u;
      }
      if ( vt > 0x10u )
      {
        if ( vt != 17 && vt != 18 && vt != 19 && (unsigned int)vt - 20 >= 2 )
        {
LABEL_55:
          ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x66u, 0);
          Variables = -2147467259;
          goto LABEL_80;
        }
      }
      else if ( vt != 16 && vt != 2 )
      {
        if ( vt == 3 )
          goto LABEL_57;
        if ( vt != 4 && vt != 5 )
        {
          if ( vt != 8 )
          {
            if ( vt == 10 && p_pvarg->lVal == -2147352572 )
            {
              v13 = 1;
              for ( i = *(_QWORD *)(*((_QWORD *)this[7] + 7) + 80LL); i; i = *(_QWORD *)(i + 32) )
              {
                v15 = *(_QWORD *)(i + 72);
                if ( v15 )
                {
                  v16 = *(const char **)(v15 + 104);
                  v17 = *(_DWORD *)(i + 16);
                  if ( v16 )
                    v18 = URLEncodeLen(v16);
                  else
                    v18 = 1;
                  v19 = v18 + v17;
                  if ( v18 + v17 < v18 || (v20 = v19 + 1, v19 + 1 < v19) || (v13 += v20, v13 < v20) )
                  {
                    Variables = -2147024362;
                    goto LABEL_80;
                  }
                  Variables = 0;
                }
              }
              memset_0(v45, 0, sizeof(v45));
              BUFFER::BUFFER((BUFFER *)v41, v45, 0x100u);
              if ( !BUFFER::Resize((BUFFER *)v41, v13) )
                goto LABEL_37;
              Ptr = (const CHAR *)BUFFER::QueryPtr((BUFFER *)v41);
              v22 = (char *)Ptr;
              v23 = *((_QWORD *)this[7] + 7);
              for ( j = *(_QWORD *)(v23 + 80); j; j = *(_QWORD *)(j + 32) )
              {
                v6 = *(_QWORD *)(j + 72);
                if ( v6 )
                {
                  strcpy_s(v22, (rsize_t)&Ptr[v13 - (_QWORD)v22], *(const char **)(j + 8));
                  v25 = strchr(v22, 0);
                  *v25 = 61;
                  v22 = v25 + 1;
                  v26 = *(const char **)(v6 + 104);
                  v6 = 0;
                  if ( v26 )
                    v22 = URLEncode(v25 + 1, (int)(v13 + (_DWORD)Ptr - (_DWORD)v22), v26);
                  else
                    *v22 = 0;
                  if ( *(_QWORD *)(j + 32) )
                    *v22++ = 59;
                }
              }
              *v22 = v6;
              v39 = (unsigned __int16 *)v6;
              if ( (int)SysAllocStringFromSz(Ptr, v23, &v39, 0) >= 0 )
              {
                a3->llVal = (LONGLONG)v39;
                a3->vt = 8;
              }
              else
              {
LABEL_37:
                ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
                Variables = -2147024882;
              }
              BUFFER::~BUFFER((BUFFER *)v41);
              goto LABEL_80;
            }
            goto LABEL_55;
          }
LABEL_57:
          a3->vt = 9;
          a3->llVal = 0;
          if ( vt == 8 )
          {
            v27 = -1;
            v28 = CWCharToMBCS::Init((CWCharToMBCS *)&v42, p_pvarg->bstrVal, 0, -1);
            Variables = v28;
            if ( v28 >= 0 )
            {
              v30 = (const char *)v42;
            }
            else
            {
              if ( v28 == -2147024882 )
              {
                v29 = 100;
LABEL_79:
                ExceptionId(&IID_IRequestDictionary, 0x1964u, v29, 0);
                goto LABEL_80;
              }
              Variables = 0;
              v30 = Str1;
            }
            do
              ++v27;
            while ( v30[v27] );
            Elem = CHashTable::FindElem((CHashTable *)(*((_QWORD *)this[7] + 7) + 64LL), v30, v27);
          }
          else
          {
            lVal = p_pvarg->lVal;
            if ( (int)lVal < 1 || (int)lVal > *((_DWORD *)this + 8) || !*((_DWORD *)this + 8) )
            {
              Variables = -2147467259;
              v29 = 105;
              goto LABEL_79;
            }
            _mm_lfence();
            Elem = (struct CLinkElem *)*((_QWORD *)this[5] + lVal - 1);
          }
          if ( Elem )
          {
            v33 = (void (__fastcall ***)(_QWORD, GUID *, ULONG *))*((_QWORD *)Elem + 9);
            if ( v33 )
            {
              (**v33)(v33, &IID_IRequestDictionary, (ULONG *)&a3->cyVal);
              goto LABEL_80;
            }
          }
          v34 = this[13];
          if ( !v34 )
          {
            v35 = (CClCert *)ALLOC_CACHE_HANDLER::Alloc(CClCert::sm_pach);
            if ( v35 )
            {
              v38 = CClCert::CClCert(v35, v36, v37);
              this[13] = v38;
              v34 = v38;
              if ( v38 )
                goto LABEL_75;
            }
            else
            {
              this[13] = 0;
            }
            Variables = -2147024882;
            goto LABEL_80;
          }
LABEL_75:
          Variables = (**(__int64 (__fastcall ***)(CRequest *, GUID *, ULONG *))v34)(
                        v34,
                        &IID_IRequestDictionary,
                        (ULONG *)&a3->cyVal);
          goto LABEL_80;
        }
      }
      Variables = VariantChangeType(p_pvarg, p_pvarg, 0, 3u);
      if ( Variables < 0 )
        goto LABEL_80;
      goto LABEL_57;
    case 2u:
      vt = 2;
      goto LABEL_11;
    case 3u:
      vt = 3;
      goto LABEL_11;
  }
  if ( (int)VariantResolveDispatch(&pvarg, p_pvarg, &IID_IRequestDictionary, 0x1964u) >= 0 )
  {
    vt = pvarg.vt;
    p_pvarg = &pvarg;
    goto LABEL_11;
  }
LABEL_80:
  VariantClear(&pvarg);
  CWCharToMBCS::~CWCharToMBCS((CWCharToMBCS *)&v42);
  return (unsigned int)Variables;
}

```

## disassembly

```asm
0x18004d9b0  mov     [rsp-8+arg_18], rbx
0x18004d9b5  push    rbp
0x18004d9b6  push    rsi
0x18004d9b7  push    rdi
0x18004d9b8  push    r12
0x18004d9ba  push    r13
0x18004d9bc  push    r14
0x18004d9be  push    r15
0x18004d9c0  lea     rbp, [rsp-190h]
0x18004d9c8  sub     rsp, 290h
0x18004d9cf  mov     rax, cs:__security_cookie
0x18004d9d6  xor     rax, rsp
0x18004d9d9  mov     [rbp+1C0h+var_40], rax
0x18004d9e0  mov     rsi, rcx
0x18004d9e3  mov     r12, r8
0x18004d9e6  mov     rcx, [rcx+38h]; this
0x18004d9ea  mov     r14, rdx
0x18004d9ed  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004d9f2  xor     r13d, r13d
0x18004d9f5  test    eax, eax
0x18004d9f7  jns     short loc_18004DA03
0x18004d9f9  mov     eax, 80004005h
0x18004d9fe  jmp     loc_18004DE8A
0x18004da03  lea     rax, [rsp+2C0h+var_248]
0x18004da08  mov     [rbp+1C0h+var_148], r13d
0x18004da0c  mov     rcx, r12; pvarg
0x18004da0f  mov     [rsp+2C0h+var_250], rax
0x18004da14  call    cs:__imp_VariantInit
0x18004da1a  xorps   xmm0, xmm0
0x18004da1d  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x18004da22  xor     eax, eax
0x18004da24  mov     ebx, r13d
0x18004da27  movups  xmmword ptr [rsp+2C0h+pvarg], xmm0
0x18004da2c  mov     qword ptr [rsp+2C0h+pvarg+10h], rax
0x18004da31  call    cs:__imp_VariantInit
0x18004da37  mov     ecx, 3
0x18004da3c  lea     edx, [rcx+5]
0x18004da3f  lea     eax, [rcx-1]
0x18004da42  cmp     [r14], dx
0x18004da46  jz      short loc_18004DA90
0x18004da48  cmp     [r14], ax
0x18004da4c  jz      short loc_18004DA8B
0x18004da4e  cmp     [r14], cx
0x18004da52  jz      short loc_18004DA87
0x18004da54  mov     r9d, 1964h; unsigned int
0x18004da5a  lea     r8, IID_IRequestDictionary; struct _GUID *
0x18004da61  mov     rdx, r14; pvargSrc
0x18004da64  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x18004da69  call    ?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z; VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)
0x18004da6e  test    eax, eax
0x18004da70  js      loc_18004DE73
0x18004da76  movzx   edi, word ptr [rsp+2C0h+pvarg]
0x18004da7b  lea     r14, [rsp+2C0h+pvarg]
0x18004da80  mov     edx, 8
0x18004da85  jmp     short loc_18004DA93
0x18004da87  mov     edi, ecx
0x18004da89  jmp     short loc_18004DA93
0x18004da8b  movzx   edi, ax
0x18004da8e  jmp     short loc_18004DA93
0x18004da90  movzx   edi, dx
0x18004da93  mov     r15, [rsi+38h]
0x18004da97  mov     rax, [r15+38h]
0x18004da9b  test    [rax+140h], dl
0x18004daa1  jz      short loc_18004DAEE
0x18004daa3  mov     rax, [rax+38h]
0x18004daa7  mov     r9d, [rax+0A4h]
0x18004daae  test    r9d, r9d
0x18004dab1  jnz     short loc_18004DABC
0x18004dab3  call    cs:__imp_GetACP
0x18004dab9  mov     r9d, eax
0x18004dabc  mov     rax, [rsi+38h]
0x18004dac0  mov     edx, 5
0x18004dac5  mov     rcx, r15
0x18004dac8  mov     r8, [rax+38h]
0x18004dacc  mov     r8, [r8+30h]
0x18004dad0  call    ?LoadVariables@CRequest@@AEAAJW4CollectionType@@PEADI@Z; CRequest::LoadVariables(CollectionType,char *,uint)
0x18004dad5  mov     ebx, eax
0x18004dad7  test    eax, eax
0x18004dad9  js      loc_18004DE73
0x18004dadf  mov     rcx, [rsi+38h]
0x18004dae3  mov     rdx, [rcx+38h]
0x18004dae7  and     dword ptr [rdx+140h], 0FFFFFFF7h
0x18004daee  movzx   r15d, di
0x18004daf2  cmp     di, 10h
0x18004daf6  ja      loc_18004DCD8
0x18004dafc  jz      loc_18004DD16
0x18004db02  mov     eax, r15d
0x18004db05  sub     eax, 2
0x18004db08  jz      loc_18004DD16
0x18004db0e  sub     eax, 1
0x18004db11  jz      loc_18004DD35
0x18004db17  sub     eax, 1
0x18004db1a  jz      loc_18004DD16
0x18004db20  sub     eax, 1
0x18004db23  jz      loc_18004DD16
0x18004db29  sub     eax, 3
0x18004db2c  jz      loc_18004DD35
0x18004db32  cmp     eax, 2
0x18004db35  jnz     loc_18004DCF4
0x18004db3b  cmp     dword ptr [r14+8], 80020004h
0x18004db43  jnz     loc_18004DCF4
0x18004db49  lea     r14d, [rax-1]
0x18004db4d  mov     rax, [rsi+38h]
0x18004db51  mov     rcx, [rax+38h]
0x18004db55  mov     rdi, [rcx+50h]
0x18004db59  jmp     short loc_18004DB9D
0x18004db5b  mov     rax, [rdi+48h]
0x18004db5f  test    rax, rax
0x18004db62  jz      short loc_18004DB99
0x18004db64  mov     rcx, [rax+68h]; char *
0x18004db68  mov     ebx, [rdi+10h]
0x18004db6b  test    rcx, rcx
0x18004db6e  jz      short loc_18004DB77
0x18004db70  call    ?URLEncodeLen@@YA_KPEBD@Z; URLEncodeLen(char const *)
0x18004db75  jmp     short loc_18004DB7C
0x18004db77  mov     eax, 1
0x18004db7c  lea     ecx, [rax+rbx]
0x18004db7f  cmp     ecx, eax
0x18004db81  jb      loc_18004DC0C
0x18004db87  lea     eax, [rcx+1]
0x18004db8a  cmp     eax, ecx
0x18004db8c  jb      short loc_18004DC0C
0x18004db8e  add     r14d, eax
0x18004db91  cmp     r14d, eax
0x18004db94  jb      short loc_18004DC0C
0x18004db96  mov     ebx, r13d
0x18004db99  mov     rdi, [rdi+20h]
0x18004db9d  test    rdi, rdi
0x18004dba0  jnz     short loc_18004DB5B
0x18004dba2  mov     edi, 100h
0x18004dba7  lea     rcx, [rbp+1C0h+var_140]; void *
0x18004dbae  mov     r8d, edi; Size
0x18004dbb1  xor     edx, edx; Val
0x18004dbb3  call    memset_0
0x18004dbb8  mov     r8d, edi
0x18004dbbb  lea     rdx, [rbp+1C0h+var_140]
0x18004dbc2  lea     rcx, [rsp+2C0h+var_280]
0x18004dbc7  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18004dbcd  mov     edx, r14d
0x18004dbd0  lea     rcx, [rsp+2C0h+var_280]
0x18004dbd5  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004dbdb  test    al, al
0x18004dbdd  jnz     short loc_18004DC16
0x18004dbdf  xor     r9d, r9d; int
0x18004dbe2  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004dbe9  mov     edx, 1964h; unsigned int
0x18004dbee  lea     r8d, [r9+64h]; unsigned int
0x18004dbf2  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004dbf7  mov     ebx, 8007000Eh
0x18004dbfc  lea     rcx, [rsp+2C0h+var_280]
0x18004dc01  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004dc07  jmp     loc_18004DE73
0x18004dc0c  mov     ebx, 80070216h
0x18004dc11  jmp     loc_18004DE73
0x18004dc16  lea     rcx, [rsp+2C0h+var_280]
0x18004dc1b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004dc21  mov     rcx, [rsi+38h]
0x18004dc25  mov     r15, rax
0x18004dc28  mov     rdi, rax
0x18004dc2b  mov     rdx, [rcx+38h]
0x18004dc2f  mov     rsi, [rdx+50h]
0x18004dc33  jmp     short loc_18004DC9D
0x18004dc35  mov     r13, [rsi+48h]
0x18004dc39  test    r13, r13
0x18004dc3c  jz      short loc_18004DC99
0x18004dc3e  mov     r8, [rsi+8]; Source
0x18004dc42  mov     rcx, rdi; Destination
0x18004dc45  mov     edx, r14d
0x18004dc48  sub     rdx, rdi
0x18004dc4b  add     rdx, r15; SizeInBytes
0x18004dc4e  call    cs:__imp_strcpy_s
0x18004dc54  xor     edx, edx; Val
0x18004dc56  mov     rcx, rdi; Str
0x18004dc59  call    cs:__imp_strchr
0x18004dc5f  mov     byte ptr [rax], 3Dh ; '='
0x18004dc62  lea     rdi, [rax+1]
0x18004dc66  mov     r8, [r13+68h]; char *
0x18004dc6a  xor     r13d, r13d
0x18004dc6d  test    r8, r8
0x18004dc70  jz      short loc_18004DC8A
0x18004dc72  mov     eax, r15d
0x18004dc75  mov     rcx, rdi; char *
0x18004dc78  sub     eax, edi
0x18004dc7a  add     eax, r14d
0x18004dc7d  movsxd  rdx, eax; unsigned __int64
0x18004dc80  call    ?URLEncode@@YAPEADPEAD_KPEBD@Z; URLEncode(char *,unsigned __int64,char const *)
0x18004dc85  mov     rdi, rax
0x18004dc88  jmp     short loc_18004DC8D
0x18004dc8a  mov     [rdi], r13b
0x18004dc8d  cmp     [rsi+20h], r13
0x18004dc91  jz      short loc_18004DC99
0x18004dc93  mov     byte ptr [rdi], 3Bh ; ';'
0x18004dc96  inc     rdi
0x18004dc99  mov     rsi, [rsi+20h]
0x18004dc9d  test    rsi, rsi
0x18004dca0  jnz     short loc_18004DC35
0x18004dca2  xor     r9d, r9d; unsigned int
0x18004dca5  mov     [rdi], r13b
0x18004dca8  lea     r8, [rsp+2C0h+var_2A0]; unsigned __int16 **
0x18004dcad  mov     [rsp+2C0h+var_2A0], r13
0x18004dcb2  mov     rcx, r15; lpMultiByteStr
0x18004dcb5  call    ?SysAllocStringFromSz@@YAJPEADKPEAPEAGI@Z; SysAllocStringFromSz(char *,ulong,ushort * *,uint)
0x18004dcba  test    eax, eax
0x18004dcbc  js      loc_18004DBDF
0x18004dcc2  mov     rax, [rsp+2C0h+var_2A0]
0x18004dcc7  mov     [r12+8], rax
0x18004dccc  mov     word ptr [r12], 8
0x18004dcd3  jmp     loc_18004DBFC
0x18004dcd8  mov     eax, r15d
0x18004dcdb  sub     eax, 11h
0x18004dcde  jz      short loc_18004DD16
0x18004dce0  sub     eax, 1
0x18004dce3  jz      short loc_18004DD16
0x18004dce5  sub     eax, 1
0x18004dce8  jz      short loc_18004DD16
0x18004dcea  sub     eax, 1
0x18004dced  jz      short loc_18004DD16
0x18004dcef  cmp     eax, 1
0x18004dcf2  jz      short loc_18004DD16
0x18004dcf4  xor     r9d, r9d; int
0x18004dcf7  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004dcfe  mov     edx, 1964h; unsigned int
0x18004dd03  lea     r8d, [r9+66h]; unsigned int
0x18004dd07  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004dd0c  mov     ebx, 80004005h
0x18004dd11  jmp     loc_18004DE73
0x18004dd16  mov     r9d, 3; vt
0x18004dd1c  xor     r8d, r8d; wFlags
0x18004dd1f  mov     rdx, r14; pvarSrc
0x18004dd22  mov     rcx, r14; pvargDest
0x18004dd25  call    cs:__imp_VariantChangeType
0x18004dd2b  mov     ebx, eax
0x18004dd2d  test    eax, eax
0x18004dd2f  js      loc_18004DE73
0x18004dd35  mov     eax, 8
0x18004dd3a  mov     word ptr [r12], 9
0x18004dd41  mov     [r12+8], r13
0x18004dd46  cmp     r15d, eax
0x18004dd49  jnz     short loc_18004DDA9
0x18004dd4b  mov     rdx, [r14+8]; unsigned __int16 *
0x18004dd4f  lea     rcx, [rsp+2C0h+var_250]; this
0x18004dd54  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004dd58  xor     r8d, r8d; unsigned int
0x18004dd5b  mov     r9d, edi; int
0x18004dd5e  call    ?Init@CWCharToMBCS@@QEAAJPEBGIH@Z; CWCharToMBCS::Init(ushort const *,uint,int)
0x18004dd63  mov     ebx, eax
0x18004dd65  test    eax, eax
0x18004dd67  jns     short loc_18004DD85
0x18004dd69  cmp     eax, 8007000Eh
0x18004dd6e  jnz     short loc_18004DD79
0x18004dd70  lea     r8d, [rdi+65h]
0x18004dd74  jmp     loc_18004DE5F
0x18004dd79  mov     ebx, r13d
0x18004dd7c  lea     rdx, Str1
0x18004dd83  jmp     short loc_18004DD8A
0x18004dd85  mov     rdx, [rsp+2C0h+var_250]; void *
0x18004dd8a  mov     rax, [rsi+38h]
0x18004dd8e  mov     rcx, [rax+38h]
0x18004dd92  add     rcx, 40h ; '@'; this
0x18004dd96  inc     rdi
0x18004dd99  cmp     [rdx+rdi], r13b
0x18004dd9d  jnz     short loc_18004DD96
0x18004dd9f  mov     r8d, edi; int
0x18004dda2  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x18004dda7  jmp     short loc_18004DDD8
0x18004dda9  movsxd  rax, dword ptr [r14+8]
0x18004ddad  cmp     eax, 1
0x18004ddb0  jl      loc_18004DE54
0x18004ddb6  cmp     eax, [rsi+20h]
0x18004ddb9  jg      loc_18004DE54
0x18004ddbf  cmp     [rsi+20h], r13d
0x18004ddc3  jz      loc_18004DE54
0x18004ddc9  lfence
0x18004ddcc  mov     rcx, rax
0x18004ddcf  mov     rax, [rsi+28h]
0x18004ddd3  mov     rax, [rax+rcx*8-8]
0x18004ddd8  test    rax, rax
0x18004dddb  jz      short loc_18004DDFF
0x18004dddd  mov     rcx, [rax+48h]
0x18004dde1  test    rcx, rcx
0x18004dde4  jz      short loc_18004DDFF
0x18004dde6  mov     rax, [rcx]
0x18004dde9  lea     r8, [r12+8]
0x18004ddee  lea     rdx, IID_IRequestDictionary
0x18004ddf5  mov     rax, [rax]
0x18004ddf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddfd  jmp     short loc_18004DE73
0x18004ddff  mov     rcx, [rsi+68h]
0x18004de03  test    rcx, rcx
0x18004de06  jnz     short loc_18004DE2E
0x18004de08  mov     rcx, cs:?sm_pach@CClCert@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CClCert::sm_pach
0x18004de0f  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004de15  test    rax, rax
0x18004de18  jz      short loc_18004DE49
0x18004de1a  mov     rcx, rax; this
0x18004de1d  call    ??0CClCert@@QEAA@PEAUIUnknown@@P6AXXZ@Z; CClCert::CClCert(IUnknown *,void (*)(void))
0x18004de22  mov     [rsi+68h], rax
0x18004de26  mov     rcx, rax
0x18004de29  test    rax, rax
0x18004de2c  jz      short loc_18004DE4D
  ... truncated ...
```
