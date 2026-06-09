# CMapiPropertyManager::GetMapiFpsPropVals(CTPtrSList<CMapi2FullPropSpec const> &,CTPtrSListContainer<MapiFpsPropVal> &)

- ea: `0x18001e2e8`
- end: `0x18001e5d1`
- name: `?GetMapiFpsPropVals@CMapiPropertyManager@@QEAAJAEAV?$CTPtrSList@$$CBVCMapi2FullPropSpec@@@@AEAV?$CTPtrSListContainer@UMapiFpsPropVal@@@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct _SPropValue **this, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800212cc`

## callees

- `0x180002300`
- `0x180002780`
- `0x18000da40`
- `0x18000fd58`
- `0x180017894`
- `0x180018640`
- `0x180018898`
- `0x180018a9c`
- `0x18001e1bc`
- `0x18001e2e8`
- `0x18001e64c`
- `0x18001f4bc`
- `0x18001f7c0`
- `0x18002b764`
- `0x18002b784`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateBuffer` at `0x18001e3d9`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateBuffer` at `0x18001e3d9`

## string_xrefs

- `0x18001e568`: `GetMapiFpsPropVals could not create MapiFpsPropVal`
- `0x18001e551`: `onecoreuap\base\appmodel\Search\common\include\tpslist.hxx`

## pseudocode

```c
__int64 __fastcall CMapiPropertyManager::GetMapiFpsPropVals(struct _SPropValue **this, __int64 a2, __int64 a3)
{
  int inited; // ebx
  int v8; // eax
  _DWORD **v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 CurrentValue; // rax
  _WORD *v13; // rdx
  struct _SPropValue *v14; // rcx
  int v15; // ecx
  int Props; // eax
  __int64 v17; // r8
  unsigned int v18; // edi
  unsigned int v19; // r15d
  struct _SPropValue *v20; // r14
  __int64 *v21; // rbx
  struct CSingleLink *v22; // rax
  __int64 *v23; // rax
  struct CSingleLink *v24; // rax
  int v25; // [rsp+20h] [rbp-50h]
  struct _SPropTagArray *v26; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-38h] BYREF
  struct _SPropTagArray *Src; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v29[3]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_GetMapiFpsPropVals_Start,
      a3,
      1,
      v29);
  Src = 0;
  inited = CMapiPropertyManager::InitOrdered(this, a2, &Src);
  if ( inited < 0 )
  {
    CLogger::Error(inited, L"GetMapiFpsPropVals could not InitOrdered");
    return (unsigned int)inited;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v26 = Src;
    v8 = CMapiPropertyManager::InitFiltered((CMapiPropertyManager *)this, Src);
    inited = v8;
    if ( v8 < 0 )
    {
      CLogger::Error(v8, L"GetMapiFpsPropVals could not InitFiltered");
      CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v26);
      return (unsigned int)inited;
    }
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v26);
  }
  else
  {
    this[3] = (struct _SPropValue *)Src;
    Src = 0;
  }
  v9 = (_DWORD **)(this + 4);
  inited = MAPIAllocateBuffer((unsigned int)(4 * *((_DWORD *)this + 20) + 4), this + 4);
  if ( inited < 0 )
  {
    CLogger::Error(inited, L"GetMapiFpsPropVals could not allocate space for properties to fetch");
    return (unsigned int)inited;
  }
  **v9 = 0;
  v11 = 0;
  v29[0] = this + 6;
  v29[1] = this + 7;
  v29[2] = 0;
  while ( *(_QWORD *)CTPtrSListIterator<CMapi2FullPropSpec>::operator++(v29, v10, v11) )
  {
    CurrentValue = CTPtrSListIterator<CMapi2FullPropSpec>::GetCurrentValue(v29);
    v13 = *(_WORD **)CurrentValue;
    if ( *(_QWORD *)(*(_QWORD *)CurrentValue + 8LL) )
    {
      v14 = this[3];
      if ( (unsigned int)v11 < v14->ulPropTag
        && (v15 = *(&v14->dwAlignPad + (unsigned int)v11), (v15 & 0xFFFF0000) != 0) )
      {
        v10 = v15 ^ (unsigned int)(unsigned __int16)(*v13 ^ v15);
      }
      else
      {
        v10 = 1;
      }
      v11 = (unsigned int)(v11 + 1);
    }
    else
    {
      v10 = *(unsigned int *)v13;
    }
    (*v9)[++**v9] = v10;
  }
  v27 = 0;
  Props = CMapiPropertyManager::GetProps((CMapiPropertyManager *)this, &v27, this + 5);
  v18 = Props;
  if ( Props >= 0 )
  {
    v19 = 0;
    v20 = this[5];
    while ( v19 < v27 )
    {
      v21 = (__int64 *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v26 = (struct _SPropTagArray *)v21;
      if ( !v21 )
      {
        v18 = -2147024882;
        CLogger::Error(-2147024882, L"GetMapiFpsPropVals could not create MapiFpsPropVal");
        TPointer<CMapi2PropTag>::~TPointer<CMapi2PropTag>(&v26);
        break;
      }
      v22 = CLnkList::GetAt((CLnkList *)(this + 7), v19);
      if ( v22 )
        v23 = (__int64 *)((char *)v22 + 8);
      else
        v23 = &`CTPtrSList<CMapi2FullPropSpec>::GetLinkValue'::`2'::pNULL;
      *v21 = *v23;
      v21[1] = (__int64)v20;
      if ( v20->ulPropTag == 1 )
        v20->ulPropTag = 10;
      v24 = (struct CSingleLink *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v29[0] = v24;
      if ( !v24 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13D,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\tpslist.hxx",
          (const char *)0x8007000ELL,
          v25);
      *(_QWORD *)v24 = 0;
      *((_QWORD *)v24 + 1) = 0;
      *((_QWORD *)v24 + 1) = v21;
      CLnkList::InsertAfter((CLnkList *)(a3 + 8), *(struct CSingleLink **)(a3 + 24), v24);
      v26 = 0;
      TPointer<CMapi2PropTag>::~TPointer<CMapi2PropTag>(&v26);
      ++v19;
      ++v20;
    }
    if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_Search_ProtocolHandlers_Context,
        MSSearchTraceId_GetMapiFpsPropVals_Stop,
        v17,
        1,
        v29);
  }
  else
  {
    CLogger::Error(Props, L"GetMapiFpsPropVals could not GetProps");
  }
  return v18;
}

```

## disassembly

```asm
0x18001e2e8  mov     [rsp-38h+arg_18], rbx
0x18001e2ed  push    rbp
0x18001e2ee  push    rsi
0x18001e2ef  push    rdi
0x18001e2f0  push    r12
0x18001e2f2  push    r13
0x18001e2f4  push    r14
0x18001e2f6  push    r15
0x18001e2f8  mov     rbp, rsp
0x18001e2fb  sub     rsp, 70h
0x18001e2ff  mov     rax, cs:__security_cookie
0x18001e306  xor     rax, rsp
0x18001e309  mov     [rbp+var_10], rax
0x18001e30d  mov     r13, r8
0x18001e310  mov     rbx, rdx
0x18001e313  mov     rsi, rcx
0x18001e316  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x18001e31d  jz      short loc_18001E341
0x18001e31f  lea     rax, [rbp+var_28]
0x18001e323  mov     qword ptr [rsp+70h+var_50], rax
0x18001e328  mov     r9d, 1
0x18001e32e  lea     rdx, MSSearchTraceId_GetMapiFpsPropVals_Start
0x18001e335  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18001e33c  call    McGenEventWrite_EventWriteTransfer
0x18001e341  xor     r12d, r12d
0x18001e344  mov     [rbp+Src], r12
0x18001e348  lea     r8, [rbp+Src]
0x18001e34c  mov     rdx, rbx
0x18001e34f  mov     rcx, rsi
0x18001e352  call    ?InitOrdered@CMapiPropertyManager@@AEAAJAEAV?$CTPtrSList@$$CBVCMapi2FullPropSpec@@@@PEAPEAU_SPropTagArray@@@Z; CMapiPropertyManager::InitOrdered(CTPtrSList<CMapi2FullPropSpec const> &,_SPropTagArray * *)
0x18001e357  mov     ebx, eax
0x18001e359  test    eax, eax
0x18001e35b  jns     short loc_18001E372
0x18001e35d  lea     rdx, aGetmapifpsprop_1; "GetMapiFpsPropVals could not InitOrdere"...
0x18001e364  mov     ecx, ebx; int
0x18001e366  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001e36b  mov     eax, ebx
0x18001e36d  jmp     loc_18001E5AD
0x18001e372  cmp     [rsi+8], r12d
0x18001e376  jz      short loc_18001E3B3
0x18001e378  mov     rdx, [rbp+Src]; Src
0x18001e37c  mov     [rbp+var_40], rdx
0x18001e380  mov     rcx, rsi; this
0x18001e383  call    ?InitFiltered@CMapiPropertyManager@@AEAAJPEAU_SPropTagArray@@@Z; CMapiPropertyManager::InitFiltered(_SPropTagArray *)
0x18001e388  mov     ebx, eax
0x18001e38a  test    eax, eax
0x18001e38c  jns     short loc_18001E3A8
0x18001e38e  lea     rdx, aGetmapifpsprop_0; "GetMapiFpsPropVals could not InitFilter"...
0x18001e395  mov     ecx, eax; int
0x18001e397  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001e39c  nop
0x18001e39d  lea     rcx, [rbp+var_40]; this
0x18001e3a1  call    ??1CMapiBuffer@@QEAA@XZ; CMapiBuffer::~CMapiBuffer(void)
0x18001e3a6  jmp     short loc_18001E36B
0x18001e3a8  lea     rcx, [rbp+var_40]; this
0x18001e3ac  call    ??1CMapiBuffer@@QEAA@XZ; CMapiBuffer::~CMapiBuffer(void)
0x18001e3b1  jmp     short loc_18001E3BF
0x18001e3b3  mov     rax, [rbp+Src]
0x18001e3b7  mov     [rsi+18h], rax
0x18001e3bb  mov     [rbp+Src], r12
0x18001e3bf  lea     rdi, [rsi+30h]
0x18001e3c3  lea     r14, [rdi+8]
0x18001e3c7  lea     r15, [rsi+20h]
0x18001e3cb  mov     ecx, [r14+18h]
0x18001e3cf  lea     ecx, ds:4[rcx*4]
0x18001e3d6  mov     rdx, r15
0x18001e3d9  call    cs:__imp_MAPIAllocateBuffer
0x18001e3df  mov     ebx, eax
0x18001e3e1  test    eax, eax
0x18001e3e3  jns     short loc_18001E3F1
0x18001e3e5  lea     rdx, aGetmapifpsprop_2; "GetMapiFpsPropVals could not allocate s"...
0x18001e3ec  jmp     loc_18001E364
0x18001e3f1  mov     rax, [r15]
0x18001e3f4  mov     [rax], r12d
0x18001e3f7  mov     r8d, r12d
0x18001e3fa  mov     [rbp+var_28], rdi
0x18001e3fe  mov     [rbp+var_20], r14
0x18001e402  mov     [rbp+var_18], r12
0x18001e406  jmp     short loc_18001E457
0x18001e408  lea     rcx, [rbp+var_28]
0x18001e40c  call    ?GetCurrentValue@?$CTPtrSListIterator@VCMapi2FullPropSpec@@@@QEAAAEAPEAVCMapi2FullPropSpec@@XZ; CTPtrSListIterator<CMapi2FullPropSpec>::GetCurrentValue(void)
0x18001e411  mov     rdx, [rax]
0x18001e414  cmp     [rdx+8], r12
0x18001e418  jz      short loc_18001E447
0x18001e41a  mov     rcx, [rsi+18h]
0x18001e41e  cmp     r8d, [rcx]
0x18001e421  jnb     short loc_18001E43D
0x18001e423  mov     eax, r8d
0x18001e426  mov     ecx, [rcx+rax*4+4]
0x18001e42a  test    ecx, 0FFFF0000h
0x18001e430  jz      short loc_18001E43D
0x18001e432  mov     eax, ecx
0x18001e434  xor     eax, [rdx]
0x18001e436  movzx   edx, ax
0x18001e439  xor     edx, ecx
0x18001e43b  jmp     short loc_18001E442
0x18001e43d  mov     edx, 1
0x18001e442  inc     r8d
0x18001e445  jmp     short loc_18001E449
0x18001e447  mov     edx, [rdx]
0x18001e449  mov     rcx, [r15]
0x18001e44c  mov     eax, [rcx]
0x18001e44e  mov     [rcx+rax*4+4], edx
0x18001e452  mov     rax, [r15]
0x18001e455  inc     dword ptr [rax]
0x18001e457  lea     rcx, [rbp+var_28]
0x18001e45b  call    ??E?$CTPtrSListIterator@VCMapi2FullPropSpec@@@@QEAAAEAPEAVCMapi2FullPropSpec@@XZ; CTPtrSListIterator<CMapi2FullPropSpec>::operator++(void)
0x18001e460  cmp     [rax], r12
0x18001e463  jnz     short loc_18001E408
0x18001e465  mov     [rbp+var_38], r12d
0x18001e469  lea     r8, [rsi+28h]; struct _SPropValue **
0x18001e46d  lea     rdx, [rbp+var_38]; unsigned int *
0x18001e471  mov     rcx, rsi; this
0x18001e474  call    ?GetProps@CMapiPropertyManager@@AEAAJAEAKAEAPEAU_SPropValue@@@Z; CMapiPropertyManager::GetProps(ulong &,_SPropValue * &)
0x18001e479  mov     edi, eax
0x18001e47b  test    eax, eax
0x18001e47d  jns     short loc_18001E492
0x18001e47f  lea     rdx, aGetmapifpsprop_3; "GetMapiFpsPropVals could not GetProps"
0x18001e486  mov     ecx, eax; int
0x18001e488  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001e48d  jmp     loc_18001E5AB
0x18001e492  mov     r15d, r12d
0x18001e495  mov     r14, [rsi+28h]
0x18001e499  cmp     r15d, [rbp+var_38]
0x18001e49d  jnb     loc_18001E580
0x18001e4a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e4aa  mov     ecx, 10h; unsigned __int64
0x18001e4af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e4b4  mov     rbx, rax
0x18001e4b7  mov     [rbp+var_40], rax
0x18001e4bb  test    rax, rax
0x18001e4be  jz      loc_18001E563
0x18001e4c4  lea     rcx, [rsi+38h]; this
0x18001e4c8  mov     edx, r15d; unsigned int
0x18001e4cb  call    ?GetAt@CLnkList@@QEBAPEAVCSingleLink@@I@Z; CLnkList::GetAt(uint)
0x18001e4d0  test    rax, rax
0x18001e4d3  jnz     short loc_18001E4DE
0x18001e4d5  lea     rax, ?pNULL@?1??GetLinkValue@?$CTPtrSList@VCMapi2FullPropSpec@@@@KAAEAPEAVCMapi2FullPropSpec@@PEAVCSingleLink@@@Z@4PEAV3@EA; CMapi2FullPropSpec * `CTPtrSList<CMapi2FullPropSpec>::GetLinkValue(CSingleLink *)'::`2'::pNULL
0x18001e4dc  jmp     short loc_18001E4E2
0x18001e4de  add     rax, 8
0x18001e4e2  mov     rax, [rax]
0x18001e4e5  mov     [rbx], rax
0x18001e4e8  mov     [rbx+8], r14
0x18001e4ec  cmp     dword ptr [r14], 1
0x18001e4f0  jnz     short loc_18001E4F9
0x18001e4f2  mov     dword ptr [r14], 0Ah
0x18001e4f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e500  mov     ecx, 10h; unsigned __int64
0x18001e505  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e50a  mov     [rbp+var_28], rax
0x18001e50e  test    rax, rax
0x18001e511  jz      short loc_18001E547
0x18001e513  mov     [rax], r12
0x18001e516  mov     [rax+8], r12
0x18001e51a  lea     rcx, [r13+8]; this
0x18001e51e  mov     [rax+8], rbx
0x18001e522  mov     r8, rax; struct CSingleLink *
0x18001e525  mov     rdx, [rcx+10h]; struct CSingleLink *
0x18001e529  call    ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x18001e52e  mov     [rbp+var_40], r12
0x18001e532  lea     rcx, [rbp+var_40]
0x18001e536  call    ??1?$TPointer@VCMapi2PropTag@@@@QEAA@XZ; TPointer<CMapi2PropTag>::~TPointer<CMapi2PropTag>(void)
0x18001e53b  inc     r15d
0x18001e53e  add     r14, 18h
0x18001e542  jmp     loc_18001E499
0x18001e547  mov     rcx, [rbp+38h]; this
0x18001e54b  mov     r9d, 8007000Eh; char *
0x18001e551  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18001e558  mov     edx, 13Dh; void *
0x18001e55d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e563  mov     edi, 8007000Eh
0x18001e568  lea     rdx, aGetmapifpsprop; "GetMapiFpsPropVals could not create Map"...
0x18001e56f  mov     ecx, edi; int
0x18001e571  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001e576  nop
0x18001e577  lea     rcx, [rbp+var_40]
0x18001e57b  call    ??1?$TPointer@VCMapi2PropTag@@@@QEAA@XZ; TPointer<CMapi2PropTag>::~TPointer<CMapi2PropTag>(void)
0x18001e580  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x18001e587  jz      short loc_18001E5AB
0x18001e589  lea     rax, [rbp+var_28]
0x18001e58d  mov     qword ptr [rsp+70h+var_50], rax
0x18001e592  mov     r9d, 1
0x18001e598  lea     rdx, MSSearchTraceId_GetMapiFpsPropVals_Stop
0x18001e59f  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18001e5a6  call    McGenEventWrite_EventWriteTransfer
0x18001e5ab  mov     eax, edi
0x18001e5ad  mov     rcx, [rbp+var_10]
0x18001e5b1  xor     rcx, rsp; StackCookie
0x18001e5b4  call    __security_check_cookie
0x18001e5b9  mov     rbx, [rsp+70h+arg_18]
0x18001e5c1  add     rsp, 70h
0x18001e5c5  pop     r15
0x18001e5c7  pop     r14
0x18001e5c9  pop     r13
0x18001e5cb  pop     r12
0x18001e5cd  pop     rdi
0x18001e5ce  pop     rsi
0x18001e5cf  pop     rbp
0x18001e5d0  retn
```
