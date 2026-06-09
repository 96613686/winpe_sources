# CServerVariables::get_Item(tagVARIANT,tagVARIANT *)

- ea: `0x18004f030`
- end: `0x18004f60a`
- name: `?get_Item@CServerVariables@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `1498`
- prototype: `int(CServerVariables *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callees

- `0x18001894c`
- `0x180023d86`
- `0x180023d92`
- `0x180023dd0`
- `0x1800406b0`
- `0x18004ad4c`
- `0x18004bc10`
- `0x18004c154`
- `0x18004f030`
- `0x18005a164`
- `0x18005a26c`
- `0x18005a300`
- `0x180060bd4`
- `0x180061b54`
- `0x1800621bc`
- `0x180064010`

## import_xrefs

- `USER32!CharUpperA` at `0x18004f340`
- `USER32!CharUpperA` at `0x18004f340`
- `OLEAUT32!__imp_VariantInit` at `0x18004f0fa`
- `OLEAUT32!__imp_VariantInit` at `0x18004f114`
- `OLEAUT32!__imp_VariantInit` at `0x18004f0fa`
- `OLEAUT32!__imp_VariantInit` at `0x18004f114`
- `OLEAUT32!__imp_VariantClear` at `0x18004f5c4`
- `OLEAUT32!__imp_VariantClear` at `0x18004f5c4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004f208`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004f208`
- `KERNEL32!HeapAlloc` at `0x18004f28e`
- `KERNEL32!HeapAlloc` at `0x18004f28e`
- `KERNEL32!GetACP` at `0x18004f088`
- `KERNEL32!GetACP` at `0x18004f230`
- `KERNEL32!GetACP` at `0x18004f088`
- `KERNEL32!GetACP` at `0x18004f230`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004f517`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004f517`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004f0cd`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004f478`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004f0cd`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004f478`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004f4a2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004f4a2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f0dc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f0ec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f4b5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f4c5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f0dc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f0ec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f4b5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004f4c5`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004f0c2`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004f0c2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004f5cf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004f5cf`

## pseudocode

```c
__int64 __fastcall CServerVariables::get_Item(CRequest **this, struct tagVARIANT *p_pvarg, struct tagVARIANT *a3)
{
  HRESULT v7; // ebx
  VARTYPE vt; // di
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // r13
  UINT v10; // r8d
  UINT ACP; // r15d
  const unsigned __int16 *bstrVal; // rdx
  int v13; // eax
  UINT v14; // r8d
  __int64 lVal; // rdi
  _QWORD *v16; // rax
  CRequest *v17; // rcx
  CRequest *v18; // rdx
  LPSTR v19; // rdi
  const char *v20; // r12
  int v21; // esi
  int v22; // r10d
  int v23; // eax
  int v24; // eax
  char *v25; // rax
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, LPSTR, unsigned __int16 *, unsigned int *); // rax
  __int64 v28; // rcx
  unsigned __int16 *v29; // r12
  int v30; // eax
  unsigned int v31; // eax
  char *v32; // r8
  CStringList *v33; // rax
  struct IUnknown *v34; // rdx
  void (*v35)(void); // r8
  CStringList *v36; // rax
  __int64 v37; // r8
  CStringList *v38; // rdi
  int v39; // eax
  unsigned int Size; // [rsp+30h] [rbp-D0h] BYREF
  int v41; // [rsp+34h] [rbp-CCh] BYREF
  char *Ptr; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v43; // [rsp+40h] [rbp-C0h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v45[48]; // [rsp+60h] [rbp-A0h] BYREF
  LPSTR lpsz; // [rsp+90h] [rbp-70h] BYREF
  char v47; // [rsp+98h] [rbp-68h] BYREF
  int v48; // [rsp+198h] [rbp+98h]
  unsigned __int8 v49[128]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v50[32]; // [rsp+220h] [rbp+120h] BYREF

  if ( (int)CRequest::CheckForTombstone(this[5]) < 0 )
    return 2147500037LL;
  GetACP();
  v48 = 0;
  lpsz = &v47;
  memset_0(v49, 0, sizeof(v49));
  BUFFER::BUFFER((BUFFER *)v45, v49, 0x80u);
  Size = BUFFER::QuerySize((BUFFER *)v45);
  Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v45);
  v43 = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v45);
  VariantInit(a3);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  switch ( p_pvarg->vt )
  {
    case 8u:
      vt = 8;
LABEL_11:
      a3->vt = 9;
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
      a3->llVal = 0;
      if ( vt > 0x10u )
      {
        if ( vt != 17 && vt != 18 && vt != 19 && (unsigned int)vt - 20 >= 2 )
          goto LABEL_27;
      }
      else if ( vt != 16 && vt != 2 )
      {
        if ( vt == 3 )
          goto LABEL_29;
        if ( vt != 4 && vt != 5 )
        {
          if ( vt != 8 )
          {
            if ( vt == 10 && p_pvarg->lVal == -2147352572 )
            {
              v10 = 104;
LABEL_21:
              ExceptionId(&IID_IRequestDictionary, 0x1964u, v10, 0);
LABEL_22:
              v7 = -2147467259;
              goto LABEL_84;
            }
LABEL_27:
            v10 = 102;
            goto LABEL_21;
          }
LABEL_29:
          ACP = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[5] + 7) + 56LL) + 164LL);
          if ( !ACP )
            ACP = GetACP();
          if ( vt == 8 )
          {
            bstrVal = p_pvarg->bstrVal;
          }
          else
          {
            lVal = p_pvarg->lVal;
            if ( !this[11] )
            {
              v16 = HeapAlloc(g_hDenaliHeap, 0, 0x30u);
              if ( !v16 )
              {
                this[11] = 0;
                goto LABEL_44;
              }
              v16[2] = 0;
              *v16 = &CServVarsIterator::`vftable';
              v16[3] = 0;
              v16[4] = 0;
              v16[5] = 0;
              *((_DWORD *)v16 + 2) = 1;
              v17 = this[5];
              this[11] = (CRequest *)v16;
              v7 = CServVarsIterator::Init(
                     (CServVarsIterator *)v16,
                     *(struct CIsapiReqInfo **)(*((_QWORD *)v17 + 7) + 48LL));
              if ( v7 < 0 )
                goto LABEL_84;
            }
            if ( (int)lVal < 1 || (v18 = this[11], (int)lVal > *((_DWORD *)v18 + 10)) || !*((_DWORD *)v18 + 10) )
            {
              v7 = -2147467259;
              v14 = 105;
              goto LABEL_83;
            }
            bstrVal = *(const unsigned __int16 **)(*((_QWORD *)v18 + 2) + 8 * lVal - 8);
          }
          v13 = CWCharToMBCS::Init((CWCharToMBCS *)&lpsz, bstrVal, ACP, -1);
          v7 = v13;
          if ( v13 >= 0 )
          {
            v19 = CharUpperA(lpsz);
          }
          else
          {
            if ( v13 == -2147024882 )
            {
              v14 = 100;
LABEL_83:
              ExceptionId(&IID_IRequestDictionary, 0x1964u, v14, 0);
              goto LABEL_84;
            }
            v19 = (LPSTR)Str1;
            v7 = 0;
          }
          v20 = lpsz;
          if ( !strncmp_0(lpsz, "UNICODE_", 7u) )
            goto LABEL_80;
          v21 = 0;
          v41 = 32;
          v22 = 0;
          if ( (_DWORD)g_sUNICODEVars != -1 )
          {
            do
            {
              v23 = v48 ? v48 - 1 : 0;
              if ( v23 < *((_DWORD *)&g_sUNICODEVars + 4 * v22) )
                break;
              if ( v48 )
                v24 = v48 - 1;
              else
                v24 = 0;
              if ( v24 == *((_DWORD *)&g_sUNICODEVars + 4 * v22)
                && !strcmp(v20, (const char *)*(&g_sUNICODEVars + 2 * v22 + 1)) )
              {
                v21 = 1;
                v25 = strcpyExA(v50, &v41, "UNICODE_");
                strcpyExA(v25, &v41, v20);
                v19 = v50;
                break;
              }
              ++v22;
            }
            while ( *((_DWORD *)&g_sUNICODEVars + 4 * v22) != -1 );
          }
          v26 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this[5] + 7) + 48LL) + 8LL);
          v27 = *(__int64 (__fastcall **)(__int64, LPSTR, unsigned __int16 *, unsigned int *))(v26 + 160);
          v28 = *(_QWORD *)(v26 + 8);
          if ( v21 )
          {
            v29 = v43;
            v30 = v27(v28, v19, v43, &Size);
          }
          else
          {
            v30 = v27(v28, v19, (unsigned __int16 *)Ptr, &Size);
            v29 = v43;
          }
          if ( v30 )
          {
LABEL_73:
            v33 = (CStringList *)ALLOC_CACHE_HANDLER::Alloc(CStringList::sm_pach);
            if ( v33 )
            {
              v36 = CStringList::CStringList(v33, v34, v35);
              v38 = v36;
              if ( v36 )
              {
                if ( v21 )
                  v39 = CStringList::AddValue(v36, v29, v37);
                else
                  v39 = CStringList::AddValue(v36, Ptr, v37, ACP);
                v7 = v39;
                if ( v39 >= 0 )
                {
                  (**(void (__fastcall ***)(CStringList *, GUID *, union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *))v38)(
                    v38,
                    &IID_IDispatch,
                    p_llVal);
                  (*(void (__fastcall **)(CStringList *))(*(_QWORD *)v38 + 16LL))(v38);
                }
                goto LABEL_84;
              }
            }
            goto LABEL_44;
          }
          v31 = BUFFER::QuerySize((BUFFER *)v45);
          if ( Size <= v31 )
          {
LABEL_80:
            if ( (int)CRequestData::GetEmptyStringList(*((CRequestData **)this[5] + 7), (struct IDispatch **)p_llVal) >= 0 )
              goto LABEL_84;
            goto LABEL_22;
          }
          if ( Size > 0x19000 )
          {
            v10 = 107;
            goto LABEL_21;
          }
          if ( BUFFER::Resize((BUFFER *)v45, Size) )
          {
            Ptr = (char *)BUFFER::QueryPtr((BUFFER *)v45);
            v29 = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v45);
            if ( v21 )
              v32 = (char *)v29;
            else
              v32 = Ptr;
            if ( (*(unsigned int (__fastcall **)(_QWORD, LPSTR, char *, unsigned int *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this[5] + 7) + 48LL) + 8LL)
                                                                                       + 160LL))(
                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this[5] + 7) + 48LL) + 8LL) + 8LL),
                   v19,
                   v32,
                   &Size) )
            {
              goto LABEL_73;
            }
            goto LABEL_80;
          }
LABEL_44:
          ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
          v7 = -2147024882;
          goto LABEL_84;
        }
      }
      v7 = VariantChangeType(p_pvarg, p_pvarg, 0, 3u);
      if ( v7 < 0 )
        goto LABEL_84;
      goto LABEL_29;
    case 2u:
      vt = 2;
      goto LABEL_11;
    case 3u:
      vt = 3;
      goto LABEL_11;
  }
  v7 = 0;
  if ( (int)VariantResolveDispatch(&pvarg, p_pvarg, &IID_IRequestDictionary, 0x1964u) >= 0 )
  {
    vt = pvarg.vt;
    p_pvarg = &pvarg;
    goto LABEL_11;
  }
LABEL_84:
  VariantClear(&pvarg);
  BUFFER::~BUFFER((BUFFER *)v45);
  CWCharToMBCS::~CWCharToMBCS((CWCharToMBCS *)&lpsz);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f030  mov     [rsp-8+arg_18], rbx
0x18004f035  push    rbp
0x18004f036  push    rsi
0x18004f037  push    rdi
0x18004f038  push    r12
0x18004f03a  push    r13
0x18004f03c  push    r14
0x18004f03e  push    r15
0x18004f040  lea     rbp, [rsp-150h]
0x18004f048  sub     rsp, 250h
0x18004f04f  mov     rax, cs:__security_cookie
0x18004f056  xor     rax, rsp
0x18004f059  mov     [rbp+180h+var_40], rax
0x18004f060  mov     r14, rcx
0x18004f063  mov     r15, r8
0x18004f066  mov     rcx, [rcx+28h]; this
0x18004f06a  mov     rsi, rdx
0x18004f06d  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004f072  xor     r12d, r12d
0x18004f075  test    eax, eax
0x18004f077  jns     short loc_18004F083
0x18004f079  mov     eax, 80004005h
0x18004f07e  jmp     loc_18004F5E0
0x18004f083  mov     [rsp+280h+var_250], r12d
0x18004f088  call    cs:__imp_GetACP
0x18004f08e  lea     rax, [rbp+180h+var_1E8]
0x18004f092  mov     [rbp+180h+var_E8], r12d
0x18004f099  mov     ebx, 80h
0x18004f09e  mov     [rbp+180h+lpsz], rax
0x18004f0a2  mov     r8d, ebx; Size
0x18004f0a5  lea     rcx, [rbp+180h+var_E0]; void *
0x18004f0ac  xor     edx, edx; Val
0x18004f0ae  call    memset_0
0x18004f0b3  mov     r8d, ebx
0x18004f0b6  lea     rdx, [rbp+180h+var_E0]
0x18004f0bd  lea     rcx, [rsp+280h+var_220]
0x18004f0c2  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18004f0c8  lea     rcx, [rsp+280h+var_220]
0x18004f0cd  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18004f0d3  lea     rcx, [rsp+280h+var_220]
0x18004f0d8  mov     [rsp+280h+var_250], eax
0x18004f0dc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004f0e2  lea     rcx, [rsp+280h+var_220]
0x18004f0e7  mov     [rsp+280h+var_248], rax
0x18004f0ec  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004f0f2  mov     rcx, r15; pvarg
0x18004f0f5  mov     [rsp+280h+var_240], rax
0x18004f0fa  call    cs:__imp_VariantInit
0x18004f100  xorps   xmm0, xmm0
0x18004f103  lea     rcx, [rsp+280h+pvarg]; pvarg
0x18004f108  xor     eax, eax
0x18004f10a  movups  xmmword ptr [rsp+280h+pvarg], xmm0
0x18004f10f  mov     qword ptr [rsp+280h+pvarg+10h], rax
0x18004f114  call    cs:__imp_VariantInit
0x18004f11a  lea     eax, [rbx-78h]
0x18004f11d  lea     edx, [rbx-7Dh]
0x18004f120  lea     ecx, [rbx-7Eh]
0x18004f123  cmp     [rsi], ax
0x18004f126  jz      short loc_18004F174
0x18004f128  cmp     [rsi], cx
0x18004f12b  jz      short loc_18004F16F
0x18004f12d  cmp     [rsi], dx
0x18004f130  jz      short loc_18004F16B
0x18004f132  mov     r9d, 1964h; unsigned int
0x18004f138  lea     r8, IID_IRequestDictionary; struct _GUID *
0x18004f13f  mov     rdx, rsi; pvargSrc
0x18004f142  lea     rcx, [rsp+280h+pvarg]; pvarg
0x18004f147  mov     ebx, r12d
0x18004f14a  call    ?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z; VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)
0x18004f14f  test    eax, eax
0x18004f151  js      loc_18004F5BF
0x18004f157  movzx   edi, word ptr [rsp+280h+pvarg]
0x18004f15c  lea     rsi, [rsp+280h+pvarg]
0x18004f161  mov     ecx, 2
0x18004f166  lea     edx, [rcx+1]
0x18004f169  jmp     short loc_18004F177
0x18004f16b  mov     edi, edx
0x18004f16d  jmp     short loc_18004F177
0x18004f16f  movzx   edi, cx
0x18004f172  jmp     short loc_18004F177
0x18004f174  movzx   edi, ax
0x18004f177  mov     word ptr [r15], 9
0x18004f17d  lea     r13, [r15+8]
0x18004f181  mov     [r13+0], r12
0x18004f185  cmp     di, 10h
0x18004f189  ja      short loc_18004F1D8
0x18004f18b  jz      short loc_18004F1FC
0x18004f18d  movzx   eax, di
0x18004f190  sub     eax, ecx
0x18004f192  jz      short loc_18004F1FC
0x18004f194  sub     eax, 1
0x18004f197  jz      short loc_18004F218
0x18004f199  sub     eax, 1
0x18004f19c  jz      short loc_18004F1FC
0x18004f19e  sub     eax, 1
0x18004f1a1  jz      short loc_18004F1FC
0x18004f1a3  sub     eax, edx
0x18004f1a5  jz      short loc_18004F218
0x18004f1a7  cmp     eax, ecx
0x18004f1a9  jnz     short loc_18004F1F4
0x18004f1ab  cmp     dword ptr [rsi+8], 80020004h
0x18004f1b2  jnz     short loc_18004F1F4
0x18004f1b4  mov     r8d, 68h ; 'h'; unsigned int
0x18004f1ba  xor     r9d, r9d; int
0x18004f1bd  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004f1c4  mov     edx, 1964h; unsigned int
0x18004f1c9  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004f1ce  mov     ebx, 80004005h
0x18004f1d3  jmp     loc_18004F5BF
0x18004f1d8  movzx   eax, di
0x18004f1db  sub     eax, 11h
0x18004f1de  jz      short loc_18004F1FC
0x18004f1e0  sub     eax, 1
0x18004f1e3  jz      short loc_18004F1FC
0x18004f1e5  sub     eax, 1
0x18004f1e8  jz      short loc_18004F1FC
0x18004f1ea  sub     eax, 1
0x18004f1ed  jz      short loc_18004F1FC
0x18004f1ef  cmp     eax, 1
0x18004f1f2  jz      short loc_18004F1FC
0x18004f1f4  mov     r8d, 66h ; 'f'
0x18004f1fa  jmp     short loc_18004F1BA
0x18004f1fc  mov     r9d, edx; vt
0x18004f1ff  xor     r8d, r8d; wFlags
0x18004f202  mov     rdx, rsi; pvarSrc
0x18004f205  mov     rcx, rsi; pvargDest
0x18004f208  call    cs:__imp_VariantChangeType
0x18004f20e  mov     ebx, eax
0x18004f210  test    eax, eax
0x18004f212  js      loc_18004F5BF
0x18004f218  mov     rax, [r14+28h]
0x18004f21c  mov     rcx, [rax+38h]
0x18004f220  mov     rax, [rcx+38h]
0x18004f224  mov     r15d, [rax+0A4h]
0x18004f22b  test    r15d, r15d
0x18004f22e  jnz     short loc_18004F239
0x18004f230  call    cs:__imp_GetACP
0x18004f236  mov     r15d, eax
0x18004f239  mov     eax, 8
0x18004f23e  cmp     di, ax
0x18004f241  jnz     short loc_18004F277
0x18004f243  mov     rdx, [rsi+8]; unsigned __int16 *
0x18004f247  mov     r8d, r15d; unsigned int
0x18004f24a  lea     rcx, [rbp+180h+lpsz]; this
0x18004f24e  or      r9d, 0FFFFFFFFh; int
0x18004f252  call    ?Init@CWCharToMBCS@@QEAAJPEBGIH@Z; CWCharToMBCS::Init(ushort const *,uint,int)
0x18004f257  mov     ebx, eax
0x18004f259  test    eax, eax
0x18004f25b  jns     loc_18004F33C
0x18004f261  cmp     eax, 8007000Eh
0x18004f266  jnz     loc_18004F330
0x18004f26c  mov     r8d, 64h ; 'd'
0x18004f272  jmp     loc_18004F5AB
0x18004f277  movsxd  rdi, dword ptr [rsi+8]
0x18004f27b  cmp     [r14+58h], r12
0x18004f27f  jnz     short loc_18004F2DC
0x18004f281  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18004f288  xor     edx, edx; dwFlags
0x18004f28a  lea     r8d, [rdx+30h]; dwBytes
0x18004f28e  call    cs:__imp_HeapAlloc
0x18004f294  test    rax, rax
0x18004f297  jz      short loc_18004F30A
0x18004f299  mov     [rax+10h], r12
0x18004f29d  lea     rcx, ??_7CServVarsIterator@@6B@; const CServVarsIterator::`vftable'
0x18004f2a4  mov     [rax], rcx
0x18004f2a7  mov     [rax+18h], r12
0x18004f2ab  mov     [rax+20h], r12
0x18004f2af  mov     [rax+28h], r12
0x18004f2b3  mov     dword ptr [rax+8], 1
0x18004f2ba  mov     rcx, [r14+28h]
0x18004f2be  mov     [r14+58h], rax
0x18004f2c2  mov     rdx, [rcx+38h]
0x18004f2c6  mov     rcx, rax; this
0x18004f2c9  mov     rdx, [rdx+30h]; struct CIsapiReqInfo *
0x18004f2cd  call    ?Init@CServVarsIterator@@QEAAJPEAVCIsapiReqInfo@@@Z; CServVarsIterator::Init(CIsapiReqInfo *)
0x18004f2d2  mov     ebx, eax
0x18004f2d4  test    eax, eax
0x18004f2d6  js      loc_18004F5BF
0x18004f2dc  cmp     edi, 1
0x18004f2df  jl      loc_18004F5A0
0x18004f2e5  mov     rdx, [r14+58h]
0x18004f2e9  cmp     edi, [rdx+28h]
0x18004f2ec  jg      loc_18004F5A0
0x18004f2f2  cmp     [rdx+28h], r12d
0x18004f2f6  jz      loc_18004F5A0
0x18004f2fc  mov     rdx, [rdx+10h]
0x18004f300  mov     rdx, [rdx+rdi*8-8]
0x18004f305  jmp     loc_18004F247
0x18004f30a  mov     [r14+58h], r12
0x18004f30e  xor     r9d, r9d; int
0x18004f311  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004f318  mov     edx, 1964h; unsigned int
0x18004f31d  lea     r8d, [r9+64h]; unsigned int
0x18004f321  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004f326  mov     ebx, 8007000Eh
0x18004f32b  jmp     loc_18004F5BF
0x18004f330  lea     rdi, Str1
0x18004f337  mov     ebx, r12d
0x18004f33a  jmp     short loc_18004F349
0x18004f33c  mov     rcx, [rbp+180h+lpsz]; lpsz
0x18004f340  call    cs:__imp_CharUpperA
0x18004f346  mov     rdi, rax
0x18004f349  mov     r12, [rbp+180h+lpsz]
0x18004f34d  lea     rdx, aUnicode; "UNICODE_"
0x18004f354  mov     rcx, r12; Str1
0x18004f357  mov     r8d, 7; MaxCount
0x18004f35d  call    strncmp_0
0x18004f362  test    eax, eax
0x18004f364  jz      loc_18004F587
0x18004f36a  xor     esi, esi
0x18004f36c  mov     [rsp+280h+var_24C], 20h ; ' '
0x18004f374  xor     r10d, r10d
0x18004f377  cmp     cs:?g_sUNICODEVars@@3PAU_unnamed_type_g_sUNICODEVars_@@A, 0FFFFFFFFh; _unnamed_type_g_sUNICODEVars_ near * g_sUNICODEVars
0x18004f37e  jz      loc_18004F426
0x18004f384  mov     r8d, [rbp+180h+var_E8]
0x18004f38b  lea     r11, ?g_sUNICODEVars@@3PAU_unnamed_type_g_sUNICODEVars_@@A; _unnamed_type_g_sUNICODEVars_ near * g_sUNICODEVars
0x18004f392  test    r8d, r8d
0x18004f395  jz      short loc_18004F39D
0x18004f397  lea     eax, [r8-1]
0x18004f39b  jmp     short loc_18004F39F
0x18004f39d  xor     eax, eax
0x18004f39f  movsxd  rcx, r10d
0x18004f3a2  add     rcx, rcx
0x18004f3a5  cmp     eax, [r11+rcx*8]
0x18004f3a9  jl      short loc_18004F426
0x18004f3ab  test    r8d, r8d
0x18004f3ae  jz      short loc_18004F3B6
0x18004f3b0  lea     eax, [r8-1]
0x18004f3b4  jmp     short loc_18004F3B8
0x18004f3b6  xor     eax, eax
0x18004f3b8  cmp     eax, [r11+rcx*8]
0x18004f3bc  jnz     short loc_18004F3E0
0x18004f3be  mov     r9, [r11+rcx*8+8]
0x18004f3c3  mov     rax, r12
0x18004f3c6  sub     r9, r12
0x18004f3c9  movzx   edx, byte ptr [rax]
0x18004f3cc  movzx   ecx, byte ptr [rax+r9]
0x18004f3d1  sub     edx, ecx
0x18004f3d3  jnz     short loc_18004F3DC
0x18004f3d5  inc     rax
0x18004f3d8  test    ecx, ecx
0x18004f3da  jnz     short loc_18004F3C9
0x18004f3dc  test    edx, edx
0x18004f3de  jz      short loc_18004F3F2
0x18004f3e0  inc     r10d
0x18004f3e3  movsxd  rax, r10d
0x18004f3e6  add     rax, rax
0x18004f3e9  cmp     dword ptr [r11+rax*8], 0FFFFFFFFh
0x18004f3ee  jnz     short loc_18004F392
0x18004f3f0  jmp     short loc_18004F426
0x18004f3f2  lea     r8, aUnicode; "UNICODE_"
0x18004f3f9  mov     esi, 1
0x18004f3fe  lea     rdx, [rsp+280h+var_24C]; int *
0x18004f403  lea     rcx, [rbp+180h+var_60]; char *
0x18004f40a  call    ?strcpyExA@@YAPEADPEADPEAHPEBD@Z; strcpyExA(char *,int *,char const *)
0x18004f40f  mov     r8, r12; char *
0x18004f412  lea     rdx, [rsp+280h+var_24C]; int *
0x18004f417  mov     rcx, rax; char *
0x18004f41a  call    ?strcpyExA@@YAPEADPEADPEAHPEBD@Z; strcpyExA(char *,int *,char const *)
0x18004f41f  lea     rdi, [rbp+180h+var_60]
0x18004f426  mov     rax, [r14+28h]
0x18004f42a  lea     r9, [rsp+280h+var_250]
0x18004f42f  mov     rdx, rdi
0x18004f432  mov     rax, [rax+38h]
0x18004f436  mov     rax, [rax+30h]
0x18004f43a  mov     rcx, [rax+8]
0x18004f43e  mov     rax, [rcx+0A0h]
0x18004f445  mov     rcx, [rcx+8]
0x18004f449  test    esi, esi
0x18004f44b  jz      short loc_18004F45C
0x18004f44d  mov     r12, [rsp+280h+var_240]
0x18004f452  mov     r8, r12
0x18004f455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f45a  jmp     short loc_18004F46B
0x18004f45c  mov     r8, [rsp+280h+var_248]
0x18004f461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f466  mov     r12, [rsp+280h+var_240]
0x18004f46b  test    eax, eax
0x18004f46d  jnz     loc_18004F510
0x18004f473  lea     rcx, [rsp+280h+var_220]
0x18004f478  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18004f47e  mov     edx, [rsp+280h+var_250]
0x18004f482  cmp     edx, eax
0x18004f484  jbe     loc_18004F587
0x18004f48a  cmp     edx, 19000h
0x18004f490  jbe     short loc_18004F49D
0x18004f492  mov     r8d, 6Bh ; 'k'
0x18004f498  jmp     loc_18004F1BA
0x18004f49d  lea     rcx, [rsp+280h+var_220]
0x18004f4a2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004f4a8  test    al, al
0x18004f4aa  jz      loc_18004F30E
0x18004f4b0  lea     rcx, [rsp+280h+var_220]
0x18004f4b5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004f4bb  lea     rcx, [rsp+280h+var_220]
0x18004f4c0  mov     [rsp+280h+var_248], rax
0x18004f4c5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004f4cb  mov     rcx, [r14+28h]
0x18004f4cf  mov     r12, rax
0x18004f4d2  lea     r9, [rsp+280h+var_250]
  ... truncated ...
```
