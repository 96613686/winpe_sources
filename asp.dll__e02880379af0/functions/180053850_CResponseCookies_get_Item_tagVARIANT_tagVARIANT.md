# CResponseCookies::get_Item(tagVARIANT,tagVARIANT *)

- ea: `0x180053850`
- end: `0x180053dca`
- name: `?get_Item@CResponseCookies@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `1402`
- prototype: `int(CResponseCookies *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180006ed4`
- `0x180007228`
- `0x180023d92`
- `0x180023dd0`
- `0x180039cf0`
- `0x18003a660`
- `0x1800406b0`
- `0x180049238`
- `0x18004a828`
- `0x18004ad4c`
- `0x18004be94`
- `0x18004ca64`
- `0x180051664`
- `0x180053850`
- `0x180060bd4`
- `0x180061b54`
- `0x1800621bc`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180053a2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180053a2f`
- `OLEAUT32!__imp_VariantInit` at `0x180053906`
- `OLEAUT32!__imp_VariantInit` at `0x180053906`
- `OLEAUT32!__imp_VariantClear` at `0x180053aeb`
- `OLEAUT32!__imp_VariantClear` at `0x180053aeb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005397f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005397f`
- `KERNEL32!GetACP` at `0x1800539d3`
- `KERNEL32!GetACP` at `0x180053b3c`
- `KERNEL32!GetACP` at `0x180053d23`
- `KERNEL32!GetACP` at `0x1800539d3`
- `KERNEL32!GetACP` at `0x180053b3c`
- `KERNEL32!GetACP` at `0x180053d23`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180053c7a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180053cf9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180053c7a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180053cf9`

## pseudocode

```c
__int64 __fastcall CResponseCookies::get_Item(CResponse **this, struct tagVARIANT *p_pvarg, struct tagVARIANT *a3)
{
  unsigned int v7; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // r12
  int Variables; // esi
  VARTYPE vt; // bx
  __int64 v11; // rcx
  char *PszCookie; // rax
  CRequest *v13; // rdi
  char *v14; // rsi
  UINT ACP; // eax
  UINT v16; // ebx
  unsigned int v17; // r8d
  GUID *v18; // rcx
  UINT v19; // eax
  __int64 v20; // rbx
  int v21; // eax
  char *v22; // r14
  struct CLinkElem *Elem; // rbx
  int iVal; // edx
  void (__fastcall ***v25)(_QWORD, GUID *, union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *); // rcx
  struct CLinkElem *v26; // rax
  int v27; // r8d
  struct IUnknown *v28; // r9
  CCookie *v29; // r14
  UINT v30; // r8d
  CCookie *v31; // rax
  void (*v32)(void); // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-D0h] BYREF
  char *v34; // [rsp+50h] [rbp-B0h] BYREF
  char v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+158h] [rbp+58h]

  if ( (int)CResponse::CheckForTombstone(this[11]) < 0 )
    return 2147500037LL;
  v36 = 0;
  v34 = &v35;
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[11] + 7) + 48LL) + 52LL) & 0x800) == 0 )
  {
    a3->vt = 9;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
    a3->llVal = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    Variables = 0;
    VariantInit(&pvarg);
    switch ( p_pvarg->vt )
    {
      case 8u:
        vt = 8;
        break;
      case 2u:
        vt = 2;
        break;
      case 3u:
        vt = 3;
        break;
      default:
        if ( (int)VariantResolveDispatch(&pvarg, p_pvarg, &IID_IRequestDictionary, 0x1964u) < 0 )
          goto LABEL_39;
        p_pvarg = &pvarg;
        vt = pvarg.vt;
        if ( pvarg.vt > 0x10u )
        {
          if ( pvarg.vt != 17 && pvarg.vt != 18 && pvarg.vt != 19 && (unsigned int)pvarg.vt - 20 >= 2 )
            goto LABEL_36;
          goto LABEL_11;
        }
        if ( pvarg.vt == 16 )
          goto LABEL_11;
        break;
    }
    if ( vt != 2 )
    {
      if ( vt == 3 )
        goto LABEL_12;
      if ( vt != 4 && vt != 5 )
      {
        if ( vt != 8 )
        {
LABEL_36:
          v17 = 102;
          v18 = &IID_IRequestDictionary;
LABEL_37:
          ExceptionId(v18, 0x1900u, v17, 0);
          goto LABEL_38;
        }
LABEL_12:
        if ( (int)CRequest::CheckForTombstone(this[10]) < 0 )
        {
LABEL_38:
          Variables = -2147467259;
          goto LABEL_39;
        }
        v11 = *((_QWORD *)this[10] + 7);
        if ( (*(_BYTE *)(v11 + 320) & 4) != 0 )
        {
          PszCookie = CIsapiReqInfo::QueryPszCookie(*(CIsapiReqInfo **)(v11 + 48));
          v13 = this[10];
          v14 = PszCookie;
          ACP = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 7) + 56LL) + 164LL);
          if ( !ACP )
            ACP = GetACP();
          Variables = CRequest::LoadVariables(v13, 4u, v14, ACP);
          if ( Variables < 0 )
            goto LABEL_39;
          *(_DWORD *)(*((_QWORD *)this[10] + 7) + 320LL) &= ~4u;
        }
        v7 = -2147024882;
        if ( vt == 8 )
        {
          v16 = 0x4000;
          if ( (g_AspRegistryParams & 0x10000) != 0 )
            v16 = *(_DWORD *)&dword_18007D870;
          if ( SysStringLen(p_pvarg->bstrVal) > v16 )
          {
            ExceptionId(&IID_IResponse, 0x1770u, 0x68u, 0);
            Variables = -2147024809;
            goto LABEL_39;
          }
          v19 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[10] + 7) + 56LL) + 164LL);
          if ( !v19 )
            v19 = GetACP();
          v20 = -1;
          v21 = CWCharToMBCS::Init((CWCharToMBCS *)&v34, p_pvarg->bstrVal, v19, -1);
          Variables = v21;
          if ( v21 >= 0 )
          {
            v22 = v34;
          }
          else
          {
            if ( v21 == -2147024882 )
            {
              ExceptionId(&IID_IResponse, 0x1900u, 0x64u, 0);
              goto LABEL_39;
            }
            Variables = 0;
            v22 = (char *)Str1;
          }
          if ( !strncmp_0(v22, "ASPSESSIONID", 0xCu) )
          {
            v17 = 6011;
LABEL_50:
            v18 = &IID_IResponse;
            goto LABEL_37;
          }
          do
            ++v20;
          while ( v22[v20] );
          Elem = CHashTable::FindElem((CHashTable *)(*((_QWORD *)this[10] + 7) + 64LL), v22, v20);
        }
        else
        {
          if ( vt == 2 )
            iVal = p_pvarg->iVal;
          else
            iVal = p_pvarg->lVal;
          if ( iVal < 1 || iVal > *(_DWORD *)(*((_QWORD *)this[10] + 7) + 784LL) )
            goto LABEL_38;
          v22 = 0;
          _mm_lfence();
          Elem = *(struct CLinkElem **)(*(_QWORD *)(*((_QWORD *)this[10] + 7) + 792LL) + 8LL * iVal - 8);
        }
        if ( Elem )
        {
          v25 = (void (__fastcall ***)(_QWORD, GUID *, union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *))*((_QWORD *)Elem + 8);
          if ( v25 )
          {
            (**v25)(v25, &IID_IWriteCookie, p_llVal);
            goto LABEL_39;
          }
        }
        if ( v22 && !*v22 )
        {
          v17 = 6402;
          goto LABEL_50;
        }
        if ( !Elem )
        {
          v26 = (struct CLinkElem *)ALLOC_CACHE_HANDLER::Alloc(CRequestHit::sm_pach);
          Elem = v26;
          if ( !v26 )
            goto LABEL_78;
          *((_DWORD *)v26 + 10) &= 0xFFFFFFFC;
          *((_QWORD *)v26 + 1) = 0;
          *((_DWORD *)v26 + 4) = 0;
          *((_WORD *)v26 + 10) = 0;
          *((_QWORD *)v26 + 3) = 0;
          *((_QWORD *)v26 + 4) = 0;
          *(_QWORD *)v26 = &CRequestHit::`vftable';
          *((_QWORD *)v26 + 7) = 0;
          *((_QWORD *)v26 + 6) = 0;
          *((_QWORD *)v26 + 8) = 0;
          *((_QWORD *)v26 + 9) = 0;
          if ( (int)CRequestHit::Init(v26, v22, 1) < 0 )
          {
            (**(void (__fastcall ***)(struct CLinkElem *, __int64))Elem)(Elem, 1);
            goto LABEL_78;
          }
          CHashTable::AddElem((CHashTable *)(*((_QWORD *)this[10] + 7) + 64LL), Elem, v27);
        }
        if ( *((_QWORD *)Elem + 8) )
        {
LABEL_75:
          if ( !(unsigned int)CRequestHitsArray::AddRequestHit(
                                (CRequestHitsArray *)(*((_QWORD *)this[10] + 7) + 784LL),
                                Elem) )
            goto LABEL_40;
          (***((void (__fastcall ****)(_QWORD, GUID *, union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *))Elem
             + 8))(
            *((_QWORD *)Elem + 8),
            &IID_IWriteCookie,
            p_llVal);
          goto LABEL_39;
        }
        v29 = (CCookie *)ALLOC_CACHE_HANDLER::Alloc(CCookie::sm_pach);
        if ( v29 )
        {
          v30 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[10] + 7) + 56LL) + 164LL);
          if ( !v30 )
            v30 = GetACP();
          v31 = CCookie::CCookie(v29, *(struct CIsapiReqInfo **)(*((_QWORD *)this[11] + 7) + 48LL), v30, v28, v32);
          *((_QWORD *)Elem + 8) = v31;
          if ( v31 && (int)CCookie::Init(v31) >= 0 )
            goto LABEL_75;
        }
        else
        {
          *((_QWORD *)Elem + 8) = 0;
        }
LABEL_78:
        ExceptionId(&IID_IResponse, 0x1900u, 0x64u, 0);
        Variables = -2147024882;
        goto LABEL_39;
      }
    }
LABEL_11:
    Variables = VariantChangeType(p_pvarg, p_pvarg, 0, 3u);
    if ( Variables >= 0 )
      goto LABEL_12;
LABEL_39:
    VariantClear(&pvarg);
    v7 = Variables;
    goto LABEL_40;
  }
  ExceptionId(&IID_IResponse, 0x1770u, 0x1773u, 0);
  v7 = -2147467259;
LABEL_40:
  CWCharToMBCS::~CWCharToMBCS((CWCharToMBCS *)&v34);
  return v7;
}

```

## disassembly

```asm
0x180053850  mov     [rsp-8+arg_18], rbx
0x180053855  push    rbp
0x180053856  push    rsi
0x180053857  push    rdi
0x180053858  push    r12
0x18005385a  push    r13
0x18005385c  push    r14
0x18005385e  push    r15
0x180053860  lea     rbp, [rsp-70h]
0x180053865  sub     rsp, 170h
0x18005386c  mov     rax, cs:__security_cookie
0x180053873  xor     rax, rsp
0x180053876  mov     [rbp+0A0h+var_40], rax
0x18005387a  mov     r15, rcx
0x18005387d  mov     rbx, r8
0x180053880  mov     rcx, [rcx+58h]; this
0x180053884  mov     r14, rdx
0x180053887  call    ?CheckForTombstone@CResponse@@QEAAJXZ; CResponse::CheckForTombstone(void)
0x18005388c  xor     r13d, r13d
0x18005388f  test    eax, eax
0x180053891  jns     short loc_18005389D
0x180053893  mov     eax, 80004005h
0x180053898  jmp     loc_180053AFF
0x18005389d  mov     [rbp+0A0h+var_48], r13d
0x1800538a1  lea     rax, [rsp+1A0h+var_148]
0x1800538a6  mov     [rsp+1A0h+var_150], rax
0x1800538ab  mov     rax, [r15+58h]
0x1800538af  mov     rcx, [rax+38h]
0x1800538b3  mov     rax, [rcx+30h]
0x1800538b7  test    dword ptr [rax+34h], 800h
0x1800538be  jz      short loc_1800538E2
0x1800538c0  mov     edx, 1770h; unsigned int
0x1800538c5  lea     rcx, IID_IResponse; struct _GUID *
0x1800538cc  xor     r9d, r9d; int
0x1800538cf  lea     r8d, [rdx+3]; unsigned int
0x1800538d3  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x1800538d8  mov     edi, 80004005h
0x1800538dd  jmp     loc_180053AF3
0x1800538e2  xorps   xmm0, xmm0
0x1800538e5  mov     word ptr [rbx], 9
0x1800538ea  xor     eax, eax
0x1800538ec  lea     r12, [rbx+8]
0x1800538f0  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x1800538f5  mov     [r12], r13
0x1800538f9  movups  xmmword ptr [rsp+1A0h+pvarg], xmm0
0x1800538fe  mov     qword ptr [rsp+1A0h+pvarg+10h], rax
0x180053903  mov     esi, r13d
0x180053906  call    cs:__imp_VariantInit
0x18005390c  mov     edi, 3
0x180053911  lea     ecx, [rdi+5]
0x180053914  lea     eax, [rdi-1]
0x180053917  cmp     [r14], cx
0x18005391b  jz      loc_180053A95
0x180053921  cmp     [r14], ax
0x180053925  jz      loc_180053A90
0x18005392b  cmp     [r14], di
0x18005392f  jz      loc_180053A8C
0x180053935  mov     r9d, 1964h; unsigned int
0x18005393b  lea     r8, IID_IRequestDictionary; struct _GUID *
0x180053942  mov     rdx, r14; pvargSrc
0x180053945  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x18005394a  call    ?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z; VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)
0x18005394f  test    eax, eax
0x180053951  js      loc_180053AE6
0x180053957  movzx   eax, word ptr [rsp+1A0h+pvarg]
0x18005395c  lea     r14, [rsp+1A0h+pvarg]
0x180053961  movzx   ebx, ax
0x180053964  cmp     eax, 10h
0x180053967  ja      loc_180053A5D
0x18005396d  jnz     loc_180053A98
0x180053973  mov     r9d, edi; vt
0x180053976  xor     r8d, r8d; wFlags
0x180053979  mov     rdx, r14; pvarSrc
0x18005397c  mov     rcx, r14; pvargDest
0x18005397f  call    cs:__imp_VariantChangeType
0x180053985  mov     esi, eax
0x180053987  test    eax, eax
0x180053989  js      loc_180053AE6
0x18005398f  mov     rcx, [r15+50h]; this
0x180053993  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x180053998  test    eax, eax
0x18005399a  js      loc_180053AE1
0x1800539a0  mov     rax, [r15+50h]
0x1800539a4  mov     rcx, [rax+38h]
0x1800539a8  test    byte ptr [rcx+140h], 4
0x1800539af  jz      short loc_180053A05
0x1800539b1  mov     rcx, [rcx+30h]; this
0x1800539b5  call    ?QueryPszCookie@CIsapiReqInfo@@QEAAPEADXZ; CIsapiReqInfo::QueryPszCookie(void)
0x1800539ba  mov     rdi, [r15+50h]
0x1800539be  mov     rsi, rax
0x1800539c1  mov     rcx, [rdi+38h]
0x1800539c5  mov     rdx, [rcx+38h]
0x1800539c9  mov     eax, [rdx+0A4h]
0x1800539cf  test    eax, eax
0x1800539d1  jnz     short loc_1800539D9
0x1800539d3  call    cs:__imp_GetACP
0x1800539d9  mov     r9d, eax
0x1800539dc  mov     r8, rsi
0x1800539df  mov     edx, 4
0x1800539e4  mov     rcx, rdi
0x1800539e7  call    ?LoadVariables@CRequest@@AEAAJW4CollectionType@@PEADI@Z; CRequest::LoadVariables(CollectionType,char *,uint)
0x1800539ec  mov     esi, eax
0x1800539ee  test    eax, eax
0x1800539f0  js      loc_180053AE6
0x1800539f6  mov     rax, [r15+50h]
0x1800539fa  mov     rcx, [rax+38h]
0x1800539fe  and     dword ptr [rcx+140h], 0FFFFFFFBh
0x180053a05  mov     eax, 8
0x180053a0a  mov     edi, 8007000Eh
0x180053a0f  cmp     bx, ax
0x180053a12  jnz     loc_180053BE2
0x180053a18  test    byte ptr cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A+2, 1; CAspRegistryParams g_AspRegistryParams
0x180053a1f  mov     ebx, 4000h
0x180053a24  mov     rcx, [r14+8]; pbstr
0x180053a28  cmovnz  ebx, cs:dword_18007D870
0x180053a2f  call    cs:__imp_SysStringLen
0x180053a35  cmp     eax, ebx
0x180053a37  jbe     loc_180053B26
0x180053a3d  xor     r9d, r9d; int
0x180053a40  lea     rcx, IID_IResponse; struct _GUID *
0x180053a47  mov     edx, 1770h; unsigned int
0x180053a4c  lea     r8d, [r9+68h]; unsigned int
0x180053a50  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180053a55  lea     esi, [rdi+49h]
0x180053a58  jmp     loc_180053AE6
0x180053a5d  sub     eax, 11h
0x180053a60  jz      loc_180053973
0x180053a66  sub     eax, 1
0x180053a69  jz      loc_180053973
0x180053a6f  sub     eax, 1
0x180053a72  jz      loc_180053973
0x180053a78  sub     eax, 1
0x180053a7b  jz      loc_180053973
0x180053a81  cmp     eax, 1
0x180053a84  jz      loc_180053973
0x180053a8a  jmp     short loc_180053AC7
0x180053a8c  mov     ebx, edi
0x180053a8e  jmp     short loc_180053A98
0x180053a90  movzx   ebx, ax
0x180053a93  jmp     short loc_180053A98
0x180053a95  movzx   ebx, cx
0x180053a98  movzx   eax, bx
0x180053a9b  sub     eax, 2
0x180053a9e  jz      loc_180053973
0x180053aa4  sub     eax, 1
0x180053aa7  jz      loc_18005398F
0x180053aad  sub     eax, 1
0x180053ab0  jz      loc_180053973
0x180053ab6  sub     eax, 1
0x180053ab9  jz      loc_180053973
0x180053abf  cmp     eax, edi
0x180053ac1  jz      loc_18005398F
0x180053ac7  mov     r8d, 66h ; 'f'; unsigned int
0x180053acd  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x180053ad4  mov     edx, 1900h; unsigned int
0x180053ad9  xor     r9d, r9d; int
0x180053adc  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180053ae1  mov     esi, 80004005h
0x180053ae6  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x180053aeb  call    cs:__imp_VariantClear
0x180053af1  mov     edi, esi
0x180053af3  lea     rcx, [rsp+1A0h+var_150]; this
0x180053af8  call    ??1CWCharToMBCS@@QEAA@XZ; CWCharToMBCS::~CWCharToMBCS(void)
0x180053afd  mov     eax, edi
0x180053aff  mov     rcx, [rbp+0A0h+var_40]
0x180053b03  xor     rcx, rsp; StackCookie
0x180053b06  call    __security_check_cookie
0x180053b0b  mov     rbx, [rsp+1A0h+arg_18]
0x180053b13  add     rsp, 170h
0x180053b1a  pop     r15
0x180053b1c  pop     r14
0x180053b1e  pop     r13
0x180053b20  pop     r12
0x180053b22  pop     rdi
0x180053b23  pop     rsi
0x180053b24  pop     rbp
0x180053b25  retn
0x180053b26  mov     rax, [r15+50h]
0x180053b2a  mov     rcx, [rax+38h]
0x180053b2e  mov     rax, [rcx+38h]
0x180053b32  mov     eax, [rax+0A4h]
0x180053b38  test    eax, eax
0x180053b3a  jnz     short loc_180053B42
0x180053b3c  call    cs:__imp_GetACP
0x180053b42  mov     rdx, [r14+8]; unsigned __int16 *
0x180053b46  lea     rcx, [rsp+1A0h+var_150]; this
0x180053b4b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180053b4f  mov     r8d, eax; unsigned int
0x180053b52  mov     r9d, ebx; int
0x180053b55  call    ?Init@CWCharToMBCS@@QEAAJPEBGIH@Z; CWCharToMBCS::Init(ushort const *,uint,int)
0x180053b5a  mov     esi, eax
0x180053b5c  test    eax, eax
0x180053b5e  jns     short loc_180053B8D
0x180053b60  cmp     eax, edi
0x180053b62  jnz     short loc_180053B81
0x180053b64  xor     r9d, r9d; int
0x180053b67  lea     r8d, [rbx+65h]; unsigned int
0x180053b6b  mov     edx, 1900h; unsigned int
0x180053b70  lea     rcx, IID_IResponse; struct _GUID *
0x180053b77  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180053b7c  jmp     loc_180053AE6
0x180053b81  mov     esi, r13d
0x180053b84  lea     r14, Str1
0x180053b8b  jmp     short loc_180053B92
0x180053b8d  mov     r14, [rsp+1A0h+var_150]
0x180053b92  mov     r8d, 0Ch; MaxCount
0x180053b98  lea     rdx, aAspsessionid; "ASPSESSIONID"
0x180053b9f  mov     rcx, r14; Str1
0x180053ba2  call    strncmp_0
0x180053ba7  test    eax, eax
0x180053ba9  jnz     short loc_180053BBD
0x180053bab  mov     r8d, 177Bh
0x180053bb1  lea     rcx, IID_IResponse
0x180053bb8  jmp     loc_180053AD4
0x180053bbd  mov     rax, [r15+50h]
0x180053bc1  mov     rcx, [rax+38h]
0x180053bc5  add     rcx, 40h ; '@'; this
0x180053bc9  inc     rbx
0x180053bcc  cmp     [r14+rbx], r13b
0x180053bd0  jnz     short loc_180053BC9
0x180053bd2  mov     r8d, ebx; int
0x180053bd5  mov     rdx, r14; void *
0x180053bd8  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x180053bdd  mov     rbx, rax
0x180053be0  jmp     short loc_180053C31
0x180053be2  mov     eax, 2
0x180053be7  cmp     bx, ax
0x180053bea  jnz     short loc_180053BF3
0x180053bec  movsx   edx, word ptr [r14+8]
0x180053bf1  jmp     short loc_180053BF7
0x180053bf3  mov     edx, [r14+8]
0x180053bf7  cmp     edx, 1
0x180053bfa  jl      loc_180053AE1
0x180053c00  mov     rax, [r15+50h]
0x180053c04  mov     rcx, [rax+38h]
0x180053c08  cmp     edx, [rcx+310h]
0x180053c0e  jg      loc_180053AE1
0x180053c14  mov     r14, r13
0x180053c17  lfence
0x180053c1a  mov     rax, [r15+50h]
0x180053c1e  movsxd  rcx, edx
0x180053c21  mov     rax, [rax+38h]
0x180053c25  mov     rax, [rax+318h]
0x180053c2c  mov     rbx, [rax+rcx*8-8]
0x180053c31  test    rbx, rbx
0x180053c34  jz      short loc_180053C59
0x180053c36  mov     rcx, [rbx+40h]
0x180053c3a  test    rcx, rcx
0x180053c3d  jz      short loc_180053C59
0x180053c3f  mov     rax, [rcx]
0x180053c42  lea     rdx, IID_IWriteCookie
0x180053c49  mov     r8, r12
0x180053c4c  mov     rax, [rax]
0x180053c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c54  jmp     loc_180053AE6
0x180053c59  test    r14, r14
0x180053c5c  jz      short loc_180053C6E
0x180053c5e  cmp     [r14], r13b
0x180053c61  jnz     short loc_180053C6E
0x180053c63  mov     r8d, 1902h
0x180053c69  jmp     loc_180053BB1
0x180053c6e  test    rbx, rbx
0x180053c71  jnz     short loc_180053CEC
0x180053c73  mov     rcx, cs:?sm_pach@CRequestHit@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CRequestHit::sm_pach
0x180053c7a  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180053c80  mov     rbx, rax
0x180053c83  test    rax, rax
0x180053c86  jz      loc_180053DA5
0x180053c8c  and     dword ptr [rbx+28h], 0FFFFFFFCh
0x180053c90  mov     r8d, 1; int
0x180053c96  mov     [rax+8], r13
0x180053c9a  mov     rdx, r14; Source
0x180053c9d  mov     [rax+10h], r13d
0x180053ca1  mov     rcx, rbx; this
0x180053ca4  mov     [rax+14h], r13w
0x180053ca9  mov     [rax+18h], r13
0x180053cad  mov     [rax+20h], r13
0x180053cb1  lea     rax, ??_7CRequestHit@@6B@; const CRequestHit::`vftable'
0x180053cb8  mov     [rbx], rax
0x180053cbb  mov     [rbx+38h], r13
0x180053cbf  mov     [rbx+30h], r13
0x180053cc3  mov     [rbx+40h], r13
0x180053cc7  mov     [rbx+48h], r13
0x180053ccb  call    ?Init@CRequestHit@@QEAAJPEADH@Z; CRequestHit::Init(char *,int)
0x180053cd0  test    eax, eax
0x180053cd2  js      loc_180053D92
0x180053cd8  mov     rax, [r15+50h]
0x180053cdc  mov     rdx, rbx; struct CLinkElem *
0x180053cdf  mov     rcx, [rax+38h]
0x180053ce3  add     rcx, 40h ; '@'; this
0x180053ce7  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x180053cec  cmp     [rbx+40h], r13
0x180053cf0  jnz     short loc_180053D55
0x180053cf2  mov     rcx, cs:?sm_pach@CCookie@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CCookie::sm_pach
0x180053cf9  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180053cff  mov     r14, rax
0x180053d02  test    rax, rax
0x180053d05  jz      loc_180053DC4
0x180053d0b  mov     rcx, [r15+50h]
0x180053d0f  mov     rdx, [rcx+38h]
  ... truncated ...
```
