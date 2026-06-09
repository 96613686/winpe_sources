# ipx::mtf::CMtfSuggestionClient::DeleteLatticeHistory(ushort,IMtfPrimitive *)

- ea: `0x180016750`
- end: `0x180016a00`
- name: `?DeleteLatticeHistory@CMtfSuggestionClient@mtf@ipx@@UEAAJGPEAUIMtfPrimitive@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, unsigned __int16, struct IMtfPrimitive *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180014848`
- `0x180016750`
- `0x180019a28`
- `0x18001d1f4`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016877`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001696a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800169d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016877`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001696a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800169d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016782`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016782`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::DeleteLatticeHistory(
        ipx::mtf::CMtfSuggestionClient *this,
        unsigned __int16 a2,
        struct IMtfPrimitive *a3)
{
  unsigned __int64 v4; // r15
  struct IMtfPropertyBag *v6; // rbx
  int v8; // eax
  unsigned int v9; // esi
  struct IMtfSuggestionCandidatePrimitive *v10; // rcx
  int RequestBag; // eax
  unsigned int v12; // esi
  struct IMtfPropertyBag *v13; // rcx
  struct IMtfSuggestionCandidatePrimitive *v14; // rcx
  unsigned int v15; // edi
  struct IMtfPropertyBag *v16; // rcx
  struct IMtfSuggestionCandidatePrimitive *v17; // rcx
  unsigned int v18; // [rsp+20h] [rbp-98h]
  unsigned int v19; // [rsp+20h] [rbp-98h]
  struct IMtfSuggestionCandidatePrimitive *v20; // [rsp+50h] [rbp-68h] BYREF
  struct IMtfPropertyBag *v21[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v22; // [rsp+68h] [rbp-50h] BYREF
  __int64 v23; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v4 = a2;
  v6 = (ipx::mtf::CMtfSuggestionClient *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v21[1] = v6;
  if ( a3 )
  {
    if ( v4 < *((_QWORD *)this + 24) )
    {
      v20 = 0;
      v8 = (**(__int64 (__fastcall ***)(struct IMtfPrimitive *, GUID *, struct IMtfSuggestionCandidatePrimitive **))a3)(
             a3,
             &GUID_92445657_1419_4aaa_a92f_486ab29470c0,
             &v20);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v22 = 0;
        v23 = 0;
        v22 = *(_OWORD *)*(_QWORD *)std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](
                                      (__int64)this + 160,
                                      v4);
        WORD2(v23) = v4;
        v21[0] = 0;
        RequestBag = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
                       this,
                       0x11u,
                       (const struct MTFCORE_SIMPLEPARAM *)&v22,
                       0,
                       0,
                       v20,
                       0,
                       0,
                       v21);
        v12 = RequestBag;
        if ( RequestBag >= 0 )
        {
          v15 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(this, *((_WORD *)this + 102), v21[0]);
          v16 = v21[0];
          if ( v21[0] )
          {
            v21[0] = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *, _QWORD))(*(_QWORD *)v16 + 16LL))(v16, *(_QWORD *)v16);
          }
          v17 = v20;
          v20 = 0;
          if ( v17 )
            (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v17 + 16LL))(v17);
          if ( v6 )
            LeaveCriticalSection((LPCRITICAL_SECTION)v6);
          return v15;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4CD,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)RequestBag,
            v19);
          v13 = v21[0];
          if ( v21[0] )
          {
            v21[0] = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v14 = v20;
          v20 = 0;
          if ( v14 )
            (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v6 )
            LeaveCriticalSection((LPCRITICAL_SECTION)v6);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C0,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v8,
          v18);
        v10 = v20;
        v20 = 0;
        if ( v10 )
          (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v6 )
          LeaveCriticalSection((LPCRITICAL_SECTION)v6);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BD,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)0x80070057LL,
        v18);
      if ( v6 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v6);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BC,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x80070057LL,
      v18);
    if ( v6 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180016750  push    rbx
0x180016752  push    rsi
0x180016753  push    rdi
0x180016754  push    r14
0x180016756  push    r15
0x180016758  sub     rsp, 90h
0x18001675f  mov     rax, cs:__security_cookie
0x180016766  xor     rax, rsp
0x180016769  mov     [rsp+0B8h+var_38], rax
0x180016771  mov     rsi, r8
0x180016774  movzx   r15d, dx
0x180016778  mov     rdi, rcx
0x18001677b  lea     rbx, [rcx+40h]
0x18001677f  mov     rcx, rbx; lpCriticalSection
0x180016782  call    cs:__imp_EnterCriticalSection
0x180016788  mov     [rsp+0B8h+var_58], rbx
0x18001678d  test    rsi, rsi
0x180016790  jnz     short loc_1800167C9
0x180016792  mov     rcx, [rsp+0B8h]; this
0x18001679a  mov     edi, 80070057h
0x18001679f  mov     r9d, edi; char *
0x1800167a2  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x1800167a9  mov     edx, 4BCh; void *
0x1800167ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167b3  nop
0x1800167b4  test    rbx, rbx
0x1800167b7  jz      short loc_1800167C2
0x1800167b9  mov     rcx, rbx; lpCriticalSection
0x1800167bc  call    cs:__imp_LeaveCriticalSection
0x1800167c2  mov     eax, edi
0x1800167c4  jmp     loc_1800169E0
0x1800167c9  cmp     r15, [rdi+0C0h]
0x1800167d0  jb      short loc_180016809
0x1800167d2  mov     rcx, [rsp+0B8h]; this
0x1800167da  mov     edi, 80070057h
0x1800167df  mov     r9d, edi; char *
0x1800167e2  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x1800167e9  mov     edx, 4BDh; void *
0x1800167ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167f3  nop
0x1800167f4  test    rbx, rbx
0x1800167f7  jz      short loc_180016802
0x1800167f9  mov     rcx, rbx; lpCriticalSection
0x1800167fc  call    cs:__imp_LeaveCriticalSection
0x180016802  mov     eax, edi
0x180016804  jmp     loc_1800169E0
0x180016809  mov     [rsp+0B8h+var_68], 0
0x180016812  mov     rax, [rsi]
0x180016815  lea     r8, [rsp+0B8h+var_68]
0x18001681a  lea     rdx, _GUID_92445657_1419_4aaa_a92f_486ab29470c0
0x180016821  mov     rcx, rsi
0x180016824  mov     rax, [rax]
0x180016827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682c  mov     esi, eax
0x18001682e  test    eax, eax
0x180016830  jns     short loc_180016884
0x180016832  mov     rcx, [rsp+0B8h]; this
0x18001683a  mov     r9d, eax; char *
0x18001683d  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016844  mov     edx, 4C0h; void *
0x180016849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001684e  nop
0x18001684f  mov     rcx, [rsp+0B8h+var_68]
0x180016854  mov     [rsp+0B8h+var_68], 0
0x18001685d  test    rcx, rcx
0x180016860  jz      short loc_18001686F
0x180016862  mov     rax, [rcx]
0x180016865  mov     rax, [rax+10h]
0x180016869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001686e  nop
0x18001686f  test    rbx, rbx
0x180016872  jz      short loc_18001687D
0x180016874  mov     rcx, rbx; lpCriticalSection
0x180016877  call    cs:__imp_LeaveCriticalSection
0x18001687d  mov     eax, esi
0x18001687f  jmp     loc_1800169E0
0x180016884  xorps   xmm0, xmm0
0x180016887  xor     eax, eax
0x180016889  movups  [rsp+0B8h+var_50], xmm0
0x18001688e  mov     [rsp+0B8h+var_40], rax
0x180016893  lea     rcx, [rdi+0A0h]
0x18001689a  mov     rdx, r15
0x18001689d  call    ??A?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@1@_K@Z; std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](unsigned __int64)
0x1800168a2  mov     rax, [rax]
0x1800168a5  movups  xmm0, xmmword ptr [rax]
0x1800168a8  movdqu  [rsp+0B8h+var_50], xmm0
0x1800168ae  mov     word ptr [rsp+0B8h+var_40+4], r15w
0x1800168b4  mov     [rsp+0B8h+var_60], 0
0x1800168bd  mov     rax, [rsp+0B8h+var_68]
0x1800168c2  lea     rcx, [rsp+0B8h+var_60]
0x1800168c7  mov     [rsp+0B8h+var_78], rcx; struct IMtfPropertyBag **
0x1800168cc  mov     [rsp+0B8h+var_80], 0; struct IMtfSuggestionInputQuery *
0x1800168d5  mov     [rsp+0B8h+var_88], 0; struct IMtfSuggestionContextProperty *
0x1800168de  mov     [rsp+0B8h+var_90], rax; struct IMtfSuggestionCandidatePrimitive *
0x1800168e3  mov     [rsp+0B8h+var_98], 0; int
0x1800168eb  xor     r9d, r9d; unsigned __int8 *
0x1800168ee  lea     r8, [rsp+0B8h+var_50]; struct MTFCORE_SIMPLEPARAM *
0x1800168f3  lea     edx, [r9+11h]; unsigned int
0x1800168f7  mov     rcx, rdi; this
0x1800168fa  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x1800168ff  mov     esi, eax
0x180016901  test    eax, eax
0x180016903  jns     short loc_180016974
0x180016905  mov     rcx, [rsp+0B8h]; this
0x18001690d  mov     r9d, eax; char *
0x180016910  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016917  mov     edx, 4CDh; void *
0x18001691c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016921  nop
0x180016922  mov     rcx, [rsp+0B8h+var_60]
0x180016927  test    rcx, rcx
0x18001692a  jz      short loc_180016942
0x18001692c  mov     [rsp+0B8h+var_60], 0
0x180016935  mov     rax, [rcx]
0x180016938  mov     rax, [rax+10h]
0x18001693c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016941  nop
0x180016942  mov     rcx, [rsp+0B8h+var_68]
0x180016947  mov     [rsp+0B8h+var_68], 0
0x180016950  test    rcx, rcx
0x180016953  jz      short loc_180016962
0x180016955  mov     rax, [rcx]
0x180016958  mov     rax, [rax+10h]
0x18001695c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016961  nop
0x180016962  test    rbx, rbx
0x180016965  jz      short loc_180016970
0x180016967  mov     rcx, rbx; lpCriticalSection
0x18001696a  call    cs:__imp_LeaveCriticalSection
0x180016970  mov     eax, esi
0x180016972  jmp     short loc_1800169E0
0x180016974  mov     r8, [rsp+0B8h+var_60]; struct IMtfPropertyBag *
0x180016979  movzx   edx, word ptr [rdi+0CCh]; unsigned __int16
0x180016980  mov     rcx, rdi; this
0x180016983  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x180016988  mov     edi, eax
0x18001698a  mov     rcx, [rsp+0B8h+var_60]
0x18001698f  test    rcx, rcx
0x180016992  jz      short loc_1800169AA
0x180016994  mov     [rsp+0B8h+var_60], 0
0x18001699d  mov     rdx, [rcx]
0x1800169a0  mov     rax, [rdx+10h]
0x1800169a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a9  nop
0x1800169aa  mov     rcx, [rsp+0B8h+var_68]
0x1800169af  mov     [rsp+0B8h+var_68], 0
0x1800169b8  test    rcx, rcx
0x1800169bb  jz      short loc_1800169CA
0x1800169bd  mov     rax, [rcx]
0x1800169c0  mov     rax, [rax+10h]
0x1800169c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169c9  nop
0x1800169ca  test    rbx, rbx
0x1800169cd  jz      short loc_1800169D8
0x1800169cf  mov     rcx, rbx; lpCriticalSection
0x1800169d2  call    cs:__imp_LeaveCriticalSection
0x1800169d8  mov     eax, edi
0x1800169da  jmp     short loc_1800169E0
0x1800169dc  mov     eax, dword ptr [rsp+0B8h+var_68]
0x1800169e0  mov     rcx, [rsp+0B8h+var_38]
0x1800169e8  xor     rcx, rsp; StackCookie
0x1800169eb  call    __security_check_cookie
0x1800169f0  add     rsp, 90h
0x1800169f7  pop     r15
0x1800169f9  pop     r14
0x1800169fb  pop     rdi
0x1800169fc  pop     rsi
0x1800169fd  pop     rbx
0x1800169fe  retn
```
