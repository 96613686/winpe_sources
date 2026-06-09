# CMapi2RowFilter::SetValueChunkFromProperty(CMapi2Property *,tagSTAT_CHUNK *)

- ea: `0x180021ff4`
- end: `0x180022351`
- name: `?SetValueChunkFromProperty@CMapi2RowFilter@@AEAAJPEAVCMapi2Property@@PEAUtagSTAT_CHUNK@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(LCID *this, struct CMapi2Property *, struct tagSTAT_CHUNK *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f140`

## callees

- `0x18000306c`
- `0x18000835c`
- `0x180008a9c`
- `0x180014448`
- `0x18001446c`
- `0x180015754`
- `0x180017870`
- `0x18001db68`
- `0x18001e5d8`
- `0x18001e608`
- `0x1800207dc`
- `0x180021dcc`
- `0x180021f94`
- `0x180021ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002213e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002221e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002213e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002221e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221b0`

## pseudocode

```c
__int64 __fastcall CMapi2RowFilter::SetValueChunkFromProperty(
        LCID *this,
        struct CMapi2Property *a2,
        struct tagSTAT_CHUNK *a3)
{
  int v6; // eax
  SIZE_T v7; // r13
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  int v10; // r12d
  __int64 v11; // r13
  const wchar_t *Buffer; // rax
  CLMString *v13; // rax
  unsigned int v14; // r13d
  __int64 i; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 result; // rax
  _DWORD *v19; // rax
  _WORD *v20; // rax
  CMapi2FullPropSpec *v21; // rcx
  LCID v22; // r14d
  CMapi2FullPropSpec *v23; // rcx
  CMapi2FullPropSpec *v24; // rcx
  GUID *PropGuid; // rbx
  __int64 v26; // rdx
  GUID v27; // xmm0
  CMapi2FullPropSpec *v28; // rcx
  GUID v29; // xmm0
  int v30; // r8d
  int v31; // [rsp+20h] [rbp-20h]
  wchar_t *v32; // [rsp+20h] [rbp-20h]
  _QWORD v33[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  _WORD *v35; // [rsp+88h] [rbp+48h] BYREF
  CLMString *v36; // [rsp+98h] [rbp+58h] BYREF

  if ( !a2 || !a3 )
    return 2147500037LL;
  v6 = *((_DWORD *)a2 + 2);
  switch ( v6 )
  {
    case 11:
      v20 = CoTaskMemAlloc(0x18u);
      v35 = v20;
      if ( !v20 )
      {
        v17 = 2980;
        goto LABEL_28;
      }
      *v20 = 11;
      v20[4] = -(*((_DWORD *)a2 + 524) != 0);
      goto LABEL_37;
    case 19:
      v19 = CoTaskMemAlloc(0x18u);
      v35 = v19;
      if ( !v19 )
      {
        v17 = 2962;
        goto LABEL_28;
      }
      *(_WORD *)v19 = 19;
      v19[2] = *((_DWORD *)a2 + 527);
LABEL_37:
      IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(this, &v35);
      wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v35,
        0);
      goto LABEL_38;
    case 31:
      IFilterImpl<CMapi2RowFilter>::SetValueChunk(this, (char *)a2 + 16);
      goto LABEL_38;
    case 64:
      v16 = CoTaskMemAlloc(0x18u);
      v35 = v16;
      if ( !v16 )
      {
        v17 = 2950;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssph\\mapi2\\mapi2rowfilt.cxx",
          (const char *)0x8007000ELL,
          v31);
        wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v35,
          0);
        return 2147942414LL;
      }
      *(_WORD *)v16 = 64;
      v16[1] = *(_QWORD *)((char *)a2 + 2100);
      goto LABEL_37;
  }
  if ( v6 != 4127 )
    return 2147500037LL;
  LODWORD(v35) = *((_DWORD *)a2 + 536);
  v7 = 8LL * (unsigned int)v35;
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    memset_0(v8, 0, v7);
  }
  else
  {
    v10 = -2147024882;
  }
  v33[2] = 0;
  v33[0] = (char *)a2 + 2112;
  v11 = 0;
  v33[1] = (char *)a2 + 2120;
  if ( v10 < 0 )
  {
LABEL_21:
    v14 = (unsigned int)v35;
  }
  else
  {
    while ( *(_QWORD *)CTPtrSListIterator<TLMString<1024,1024,1048576>>::operator++(v33) )
    {
      v36 = *(CLMString **)CTPtrSListIterator<TLMString<1024,1024,1048576>>::GetCurrentValue(v33);
      v32 = (wchar_t *)CoTaskMemAlloc(2LL * (unsigned int)(*((_DWORD *)v36 + 5) + 1));
      if ( !v32 )
        goto LABEL_21;
      Buffer = CLMString::GetBuffer(v36, 0);
      v10 = StringCchCopyW(v32, (unsigned int)(*((_DWORD *)v36 + 5) + 1), Buffer);
      if ( v10 < 0 )
        goto LABEL_21;
      v9[v11] = v32;
      v11 = (unsigned int)(v11 + 1);
    }
    v13 = (CLMString *)CoTaskMemAlloc(0x18u);
    v14 = (unsigned int)v35;
    v36 = v13;
    if ( v13 )
    {
      *(_WORD *)v13 = 4127;
      *((_DWORD *)v13 + 2) = v14;
      *((_QWORD *)v13 + 2) = v9;
      IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(this, &v36);
    }
    else
    {
      v10 = -2147024882;
    }
    wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v36,
      0);
    if ( v10 >= 0 )
      goto LABEL_38;
  }
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
      CoTaskMemFree((LPVOID)v9[i]);
    CoTaskMemFree(v9);
  }
LABEL_38:
  v21 = *(CMapi2FullPropSpec **)a2;
  if ( *(_DWORD *)(*(_QWORD *)a2 + 32LL) )
    v22 = *((_DWORD *)v21 + 9);
  else
    v22 = this[5420];
  if ( (unsigned int)CMapi2FullPropSpec::IsStringProp(v21) )
  {
    CMapi2FullPropSpec::IsStringProp(v23);
    PropGuid = (GUID *)CMapi2FullPropSpec::GetPropGuid(v24);
    CLMString::operator=((__int64)(this + 2070), v26);
    v27 = *PropGuid;
    a3->attribute.psProperty.ulKind = 0;
    a3->attribute.guidPropSet = v27;
    a3->attribute.psProperty.propid = CLMString::GetBuffer((CLMString *)(this + 2070), 0);
  }
  else
  {
    CMapi2FullPropSpec::GetPropId(v23);
    v29 = *CMapi2FullPropSpec::GetPropGuid(v28);
    a3->attribute.psProperty.ulKind = 1;
    LODWORD(a3->attribute.psProperty.propid) = v30;
    a3->attribute.guidPropSet = v29;
  }
  a3->breakType = CHUNK_EOS;
  a3->flags = CHUNK_VALUE;
  result = 0;
  a3->locale = v22;
  return result;
}

```

## disassembly

```asm
0x180021ff4  mov     [rsp-38h+arg_0], rbx
0x180021ff9  push    rbp
0x180021ffa  push    rsi
0x180021ffb  push    rdi
0x180021ffc  push    r12
0x180021ffe  push    r13
0x180022000  push    r14
0x180022002  push    r15
0x180022004  mov     rbp, rsp
0x180022007  sub     rsp, 40h
0x18002200b  mov     rsi, r8
0x18002200e  mov     rdi, rdx
0x180022011  mov     r15, rcx
0x180022014  test    rdx, rdx
0x180022017  jz      loc_180022334
0x18002201d  test    r8, r8
0x180022020  jz      loc_180022334
0x180022026  mov     eax, [rdx+8]
0x180022029  mov     ebx, 0Bh
0x18002202e  cmp     eax, ebx
0x180022030  jz      loc_180022242
0x180022036  mov     ebx, 13h
0x18002203b  cmp     eax, ebx
0x18002203d  jz      loc_180022219
0x180022043  cmp     eax, 1Fh
0x180022046  jz      loc_18002220E
0x18002204c  mov     ebx, 40h ; '@'
0x180022051  cmp     eax, ebx
0x180022053  jz      loc_1800221BB
0x180022059  cmp     eax, 101Fh
0x18002205e  jnz     loc_180022334
0x180022064  mov     eax, [rdx+860h]
0x18002206a  mov     r13d, eax
0x18002206d  mov     dword ptr [rbp+arg_8], eax
0x180022070  shl     r13, 3
0x180022074  mov     rcx, r13; cb
0x180022077  call    cs:__imp_CoTaskMemAlloc
0x18002207d  mov     r14, rax
0x180022080  mov     ebx, 8007000Eh
0x180022085  test    rax, rax
0x180022088  jnz     short loc_18002208F
0x18002208a  mov     r12d, ebx
0x18002208d  jmp     short loc_18002209F
0x18002208f  xor     r12d, r12d
0x180022092  mov     r8, r13; Size
0x180022095  xor     edx, edx; Val
0x180022097  mov     rcx, r14; void *
0x18002209a  call    memset_0
0x18002209f  lea     rax, [rdi+840h]
0x1800220a6  mov     [rbp+var_8], 0
0x1800220ae  mov     [rbp+var_18], rax
0x1800220b2  xor     r13d, r13d
0x1800220b5  lea     rax, [rdi+848h]
0x1800220bc  mov     [rbp+var_10], rax
0x1800220c0  test    r12d, r12d
0x1800220c3  js      loc_180022188
0x1800220c9  lea     rcx, [rbp+var_18]
0x1800220cd  call    ??E?$CTPtrSListIterator@V?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@@QEAAAEAPEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@XZ; CTPtrSListIterator<TLMString<1024,1024,1048576>>::operator++(void)
0x1800220d2  cmp     qword ptr [rax], 0
0x1800220d6  jz      short loc_180022139
0x1800220d8  lea     rcx, [rbp+var_18]
0x1800220dc  call    ?GetCurrentValue@?$CTPtrSListIterator@V?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@@QEAAAEAPEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@XZ; CTPtrSListIterator<TLMString<1024,1024,1048576>>::GetCurrentValue(void)
0x1800220e1  mov     rax, [rax]
0x1800220e4  mov     [rbp+arg_18], rax
0x1800220e8  mov     ecx, [rax+14h]
0x1800220eb  inc     ecx
0x1800220ed  add     rcx, rcx; cb
0x1800220f0  call    cs:__imp_CoTaskMemAlloc
0x1800220f6  mov     [rbp+var_20], rax
0x1800220fa  mov     r12, rax
0x1800220fd  test    rax, rax
0x180022100  jz      loc_180022188
0x180022106  mov     rcx, [rbp+arg_18]; this
0x18002210a  xor     edx, edx; int
0x18002210c  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180022111  mov     rcx, [rbp+arg_18]
0x180022115  mov     r8, rax; wchar_t *
0x180022118  mov     edx, [rcx+14h]
0x18002211b  mov     rcx, r12; wchar_t *
0x18002211e  inc     edx; unsigned __int64
0x180022120  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180022125  mov     r12d, eax
0x180022128  test    eax, eax
0x18002212a  js      short loc_180022188
0x18002212c  mov     rax, [rbp+var_20]
0x180022130  mov     [r14+r13*8], rax
0x180022134  inc     r13d
0x180022137  jmp     short loc_1800220C9
0x180022139  mov     ecx, 18h; cb
0x18002213e  call    cs:__imp_CoTaskMemAlloc
0x180022144  mov     r13d, dword ptr [rbp+arg_8]
0x180022148  mov     [rbp+arg_18], rax
0x18002214c  test    rax, rax
0x18002214f  jz      short loc_18002216F
0x180022151  mov     ecx, 101Fh
0x180022156  lea     rdx, [rbp+arg_18]
0x18002215a  mov     [rax], cx
0x18002215d  mov     rcx, r15
0x180022160  mov     [rax+8], r13d
0x180022164  mov     [rax+10h], r14
0x180022168  call    ?SetValueChunkAsPropvariantAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2DirFilter@@@@IEAAXAEAV?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18002216d  jmp     short loc_180022172
0x18002216f  mov     r12d, ebx
0x180022172  xor     edx, edx
0x180022174  lea     rcx, [rbp+arg_18]
0x180022178  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x18002217d  test    r12d, r12d
0x180022180  jns     loc_180022289
0x180022186  jmp     short loc_18002218C
0x180022188  mov     r13d, dword ptr [rbp+arg_8]
0x18002218c  test    r14, r14
0x18002218f  jz      loc_180022289
0x180022195  xor     ebx, ebx
0x180022197  test    r13d, r13d
0x18002219a  jz      short loc_1800221AD
0x18002219c  mov     rcx, [r14+rbx*8]; pv
0x1800221a0  call    cs:__imp_CoTaskMemFree
0x1800221a6  inc     ebx
0x1800221a8  cmp     ebx, r13d
0x1800221ab  jb      short loc_18002219C
0x1800221ad  mov     rcx, r14; pv
0x1800221b0  call    cs:__imp_CoTaskMemFree
0x1800221b6  jmp     loc_180022289
0x1800221bb  mov     ecx, 18h; cb
0x1800221c0  call    cs:__imp_CoTaskMemAlloc
0x1800221c6  mov     [rbp+arg_8], rax
0x1800221ca  test    rax, rax
0x1800221cd  jnz     short loc_1800221FE
0x1800221cf  mov     edx, 0B86h; void *
0x1800221d4  mov     rcx, [rbp+38h]; this
0x1800221d8  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800221df  mov     ebx, 8007000Eh
0x1800221e4  mov     r9d, ebx; char *
0x1800221e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221ec  xor     edx, edx
0x1800221ee  lea     rcx, [rbp+arg_8]
0x1800221f2  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x1800221f7  mov     eax, ebx
0x1800221f9  jmp     loc_180022339
0x1800221fe  mov     [rax], bx
0x180022201  mov     rcx, [rdi+834h]
0x180022208  mov     [rax+8], rcx
0x18002220c  jmp     short loc_180022272
0x18002220e  add     rdx, 10h
0x180022212  call    ?SetValueChunk@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXAEBVCLMString@@@Z; IFilterImpl<CMapi2RowFilter>::SetValueChunk(CLMString const &)
0x180022217  jmp     short loc_180022289
0x180022219  mov     ecx, 18h; cb
0x18002221e  call    cs:__imp_CoTaskMemAlloc
0x180022224  mov     [rbp+arg_8], rax
0x180022228  test    rax, rax
0x18002222b  jnz     short loc_180022234
0x18002222d  mov     edx, 0B92h
0x180022232  jmp     short loc_1800221D4
0x180022234  mov     [rax], bx
0x180022237  mov     ecx, [rdi+83Ch]
0x18002223d  mov     [rax+8], ecx
0x180022240  jmp     short loc_180022272
0x180022242  mov     ecx, 18h; cb
0x180022247  call    cs:__imp_CoTaskMemAlloc
0x18002224d  mov     [rbp+arg_8], rax
0x180022251  test    rax, rax
0x180022254  jnz     short loc_180022260
0x180022256  mov     edx, 0BA4h
0x18002225b  jmp     loc_1800221D4
0x180022260  mov     [rax], bx
0x180022263  mov     ecx, [rdi+830h]
0x180022269  neg     ecx
0x18002226b  sbb     dx, dx
0x18002226e  mov     [rax+8], dx
0x180022272  lea     rdx, [rbp+arg_8]
0x180022276  mov     rcx, r15
0x180022279  call    ?SetValueChunkAsPropvariantAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2DirFilter@@@@IEAAXAEAV?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18002227e  xor     edx, edx
0x180022280  lea     rcx, [rbp+arg_8]
0x180022284  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x180022289  mov     rcx, [rdi]; this
0x18002228c  cmp     dword ptr [rcx+20h], 0
0x180022290  jz      short loc_180022298
0x180022292  mov     r14d, [rcx+24h]
0x180022296  jmp     short loc_18002229F
0x180022298  mov     r14d, [r15+54B0h]
0x18002229f  call    ?IsStringProp@CMapi2FullPropSpec@@QEBAHXZ; CMapi2FullPropSpec::IsStringProp(void)
0x1800222a4  test    eax, eax
0x1800222a6  jz      short loc_180022301
0x1800222a8  call    ?IsStringProp@CMapi2FullPropSpec@@QEBAHXZ; CMapi2FullPropSpec::IsStringProp(void)
0x1800222ad  test    eax, eax
0x1800222af  jz      short loc_1800222C9
0x1800222b1  mov     rdx, [rcx+18h]
0x1800222b5  test    rdx, rdx
0x1800222b8  jz      short loc_1800222C0
0x1800222ba  mov     rdx, [rdx+10h]
0x1800222be  jmp     short loc_1800222CB
0x1800222c0  mov     rdx, [rcx+8]
0x1800222c4  test    rdx, rdx
0x1800222c7  jnz     short loc_1800222BA
0x1800222c9  xor     edx, edx
0x1800222cb  call    ?GetPropGuid@CMapi2FullPropSpec@@QEBAAEBU_GUID@@XZ; CMapi2FullPropSpec::GetPropGuid(void)
0x1800222d0  lea     rdi, [r15+2058h]
0x1800222d7  mov     rbx, rax
0x1800222da  mov     rcx, rdi
0x1800222dd  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800222e2  movups  xmm0, xmmword ptr [rbx]
0x1800222e5  xor     edx, edx; int
0x1800222e7  mov     dword ptr [rsi+20h], 0
0x1800222ee  mov     rcx, rdi; this
0x1800222f1  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800222f6  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800222fb  mov     [rsi+28h], rax
0x1800222ff  jmp     short loc_180022321
0x180022301  call    ?GetPropId@CMapi2FullPropSpec@@QEBAKXZ; CMapi2FullPropSpec::GetPropId(void)
0x180022306  mov     r8d, eax
0x180022309  call    ?GetPropGuid@CMapi2FullPropSpec@@QEBAAEBU_GUID@@XZ; CMapi2FullPropSpec::GetPropGuid(void)
0x18002230e  movups  xmm0, xmmword ptr [rax]
0x180022311  mov     dword ptr [rsi+20h], 1
0x180022318  mov     [rsi+28h], r8d
0x18002231c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180022321  mov     eax, 2
0x180022326  mov     [rsi+4], eax
0x180022329  mov     [rsi+8], eax
0x18002232c  xor     eax, eax
0x18002232e  mov     [rsi+0Ch], r14d
0x180022332  jmp     short loc_180022339
0x180022334  mov     eax, 80004005h
0x180022339  mov     rbx, [rsp+40h+arg_0]
0x180022341  add     rsp, 40h
0x180022345  pop     r15
0x180022347  pop     r14
0x180022349  pop     r13
0x18002234b  pop     r12
0x18002234d  pop     rdi
0x18002234e  pop     rsi
0x18002234f  pop     rbp
0x180022350  retn
```
