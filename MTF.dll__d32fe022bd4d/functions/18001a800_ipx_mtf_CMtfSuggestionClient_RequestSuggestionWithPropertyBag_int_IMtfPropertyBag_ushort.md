# ipx::mtf::CMtfSuggestionClient::RequestSuggestionWithPropertyBag(int,IMtfPropertyBag *,ushort *)

- ea: `0x18001a800`
- end: `0x18001aa24`
- name: `?RequestSuggestionWithPropertyBag@CMtfSuggestionClient@mtf@ipx@@UEAAJHPEAUIMtfPropertyBag@@PEAG@Z`
- size: `548`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, int, struct IMtfPropertyBag *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180019a28`
- `0x18001a800`
- `0x18001d1f4`
- `0x18001dbb4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a85c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a85c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a827`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RequestSuggestionWithPropertyBag(
        ipx::mtf::CMtfSuggestionClient *this,
        int a2,
        struct IMtfPropertyBag *a3,
        unsigned __int16 *a4)
{
  int v8; // ebx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  ipx::mtf::CMtfSuggestionClient *v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  struct IMtfSuggestionInputQuery *v14; // rdi
  int v15; // eax
  unsigned int v16; // r14d
  struct IMtfPropertyBag *v17; // rcx
  unsigned int v18; // esi
  struct IMtfPropertyBag *v19; // rcx
  unsigned int v20; // [rsp+20h] [rbp-59h]
  unsigned int v21; // [rsp+20h] [rbp-59h]
  unsigned int v22; // [rsp+20h] [rbp-59h]
  struct IMtfPropertyBag *v23; // [rsp+50h] [rbp-29h] BYREF
  struct IMtfSuggestionInputQuery *v24; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v25[3]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v28; // [rsp+E0h] [rbp+67h] BYREF

  v8 = *((_DWORD *)this + 50);
  if ( v8 == GetCurrentThreadId() )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    v28 = 4;
    v24 = 0;
    v12 = ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(
            v11,
            a2 != 0,
            (const struct _MTF_QUERY_PROP *)v25,
            0,
            0,
            0,
            a3,
            &v24,
            &v28);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v23 = 0;
      v14 = v24;
      v15 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(this, v28, 0, 0, 0, 0, 0, v24, &v23);
      v16 = v15;
      if ( v15 >= 0 )
      {
        *a4 = *((_WORD *)this + 102);
        v18 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(this, *((_WORD *)this + 102), v23);
        v19 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        if ( v14 )
          (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v10 )
          LeaveCriticalSection(v10);
        return v18;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64D,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v15,
          v22);
        v17 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v17 + 16LL))(v17);
        }
        if ( v14 )
          (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x644,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v12,
        v21);
      if ( v24 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v24 + 16LL))(v24);
      if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x634,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v20);
    return 2147549454LL;
  }
}

```

## disassembly

```asm
0x18001a800  push    rbp
0x18001a802  push    rbx
0x18001a803  push    rsi
0x18001a804  push    rdi
0x18001a805  push    r14
0x18001a807  push    r15
0x18001a809  lea     rbp, [rsp-2Fh]
0x18001a80e  sub     rsp, 0A8h
0x18001a815  mov     r15, r9
0x18001a818  mov     rdi, r8
0x18001a81b  mov     r14d, edx
0x18001a81e  mov     rsi, rcx
0x18001a821  mov     ebx, [rcx+0C8h]
0x18001a827  call    cs:__imp_GetCurrentThreadId
0x18001a82d  cmp     ebx, eax
0x18001a82f  jz      short loc_18001A855
0x18001a831  mov     rcx, [rbp+5Fh]; this
0x18001a835  mov     ebx, 8001010Eh
0x18001a83a  mov     r9d, ebx; char *
0x18001a83d  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a844  mov     edx, 634h; void *
0x18001a849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a84e  mov     eax, ebx
0x18001a850  jmp     loc_18001AA14
0x18001a855  lea     rbx, [rsi+40h]
0x18001a859  mov     rcx, rbx; lpCriticalSection
0x18001a85c  call    cs:__imp_EnterCriticalSection
0x18001a862  xorps   xmm0, xmm0
0x18001a865  xor     eax, eax
0x18001a867  movups  [rbp+57h+var_70], xmm0
0x18001a86b  movups  [rbp+57h+var_60], xmm0
0x18001a86f  movups  [rbp+57h+var_50], xmm0
0x18001a873  mov     [rbp+57h+var_40], rax
0x18001a877  mov     [rbp+57h+arg_0], 4
0x18001a87e  mov     [rbp+57h+var_78], rax
0x18001a882  test    r14d, r14d
0x18001a885  setnz   dl; bool
0x18001a888  lea     rax, [rbp+57h+arg_0]
0x18001a88c  mov     [rsp+0D0h+var_90], rax; unsigned int *
0x18001a891  lea     rax, [rbp+57h+var_78]
0x18001a895  mov     [rsp+0D0h+var_98], rax; struct IMtfSuggestionInputQuery **
0x18001a89a  mov     [rsp+0D0h+var_A0], rdi; struct IMtfPropertyBag *
0x18001a89f  mov     [rsp+0D0h+var_A8], 0; struct IMtfLattice *
0x18001a8a8  mov     [rsp+0D0h+var_B0], 0; int
0x18001a8b0  xor     r9d, r9d; unsigned __int8 *
0x18001a8b3  lea     r8, [rbp+57h+var_70]; struct _MTF_QUERY_PROP *
0x18001a8b7  call    ?_CreateSuggestionInputQuery@CMtfSuggestionClient@mtf@ipx@@IEAAJ_NPEBU_MTF_QUERY_PROP@@PEAEKPEAUIMtfLattice@@PEAUIMtfPropertyBag@@PEAPEAUIMtfSuggestionInputQuery@@PEAK@Z; ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(bool,_MTF_QUERY_PROP const *,uchar *,ulong,IMtfLattice *,IMtfPropertyBag *,IMtfSuggestionInputQuery * *,ulong *)
0x18001a8bc  mov     edi, eax
0x18001a8be  test    eax, eax
0x18001a8c0  jns     short loc_18001A906
0x18001a8c2  mov     rcx, [rbp+5Fh]; this
0x18001a8c6  mov     r9d, eax; char *
0x18001a8c9  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a8d0  mov     edx, 644h; void *
0x18001a8d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a8da  nop
0x18001a8db  mov     rcx, [rbp+57h+var_78]
0x18001a8df  test    rcx, rcx
0x18001a8e2  jz      short loc_18001A8F1
0x18001a8e4  mov     rax, [rcx]
0x18001a8e7  mov     rax, [rax+10h]
0x18001a8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f0  nop
0x18001a8f1  test    rbx, rbx
0x18001a8f4  jz      short loc_18001A8FF
0x18001a8f6  mov     rcx, rbx; lpCriticalSection
0x18001a8f9  call    cs:__imp_LeaveCriticalSection
0x18001a8ff  mov     eax, edi
0x18001a901  jmp     loc_18001AA14
0x18001a906  mov     [rbp+57h+var_80], 0
0x18001a90e  lea     rax, [rbp+57h+var_80]
0x18001a912  mov     [rsp+0D0h+var_90], rax; struct IMtfPropertyBag **
0x18001a917  mov     rdi, [rbp+57h+var_78]
0x18001a91b  mov     [rsp+0D0h+var_98], rdi; struct IMtfSuggestionInputQuery *
0x18001a920  mov     [rsp+0D0h+var_A0], 0; struct IMtfSuggestionContextProperty *
0x18001a929  mov     [rsp+0D0h+var_A8], 0; struct IMtfSuggestionCandidatePrimitive *
0x18001a932  mov     [rsp+0D0h+var_B0], 0; int
0x18001a93a  xor     r9d, r9d; unsigned __int8 *
0x18001a93d  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x18001a940  mov     edx, [rbp+57h+arg_0]; unsigned int
0x18001a943  mov     rcx, rsi; this
0x18001a946  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x18001a94b  mov     r14d, eax
0x18001a94e  test    eax, eax
0x18001a950  jns     short loc_18001A9B1
0x18001a952  mov     rcx, [rbp+5Fh]; this
0x18001a956  mov     r9d, eax; char *
0x18001a959  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a960  mov     edx, 64Dh; void *
0x18001a965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a96a  nop
0x18001a96b  mov     rcx, [rbp+57h+var_80]
0x18001a96f  test    rcx, rcx
0x18001a972  jz      short loc_18001A989
0x18001a974  mov     [rbp+57h+var_80], 0
0x18001a97c  mov     rax, [rcx]
0x18001a97f  mov     rax, [rax+10h]
0x18001a983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a988  nop
0x18001a989  test    rdi, rdi
0x18001a98c  jz      short loc_18001A99E
0x18001a98e  mov     rax, [rdi]
0x18001a991  mov     rcx, rdi
0x18001a994  mov     rax, [rax+10h]
0x18001a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99d  nop
0x18001a99e  test    rbx, rbx
0x18001a9a1  jz      short loc_18001A9AC
0x18001a9a3  mov     rcx, rbx; lpCriticalSection
0x18001a9a6  call    cs:__imp_LeaveCriticalSection
0x18001a9ac  mov     eax, r14d
0x18001a9af  jmp     short loc_18001AA14
0x18001a9b1  movzx   eax, word ptr [rsi+0CCh]
0x18001a9b8  mov     [r15], ax
0x18001a9bc  mov     r8, [rbp+57h+var_80]; struct IMtfPropertyBag *
0x18001a9c0  movzx   edx, word ptr [rsi+0CCh]; unsigned __int16
0x18001a9c7  mov     rcx, rsi; this
0x18001a9ca  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x18001a9cf  mov     esi, eax
0x18001a9d1  mov     rcx, [rbp+57h+var_80]
0x18001a9d5  test    rcx, rcx
0x18001a9d8  jz      short loc_18001A9EF
0x18001a9da  mov     [rbp+57h+var_80], 0
0x18001a9e2  mov     rdx, [rcx]
0x18001a9e5  mov     rax, [rdx+10h]
0x18001a9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ee  nop
0x18001a9ef  test    rdi, rdi
0x18001a9f2  jz      short loc_18001AA04
0x18001a9f4  mov     rax, [rdi]
0x18001a9f7  mov     rcx, rdi
0x18001a9fa  mov     rax, [rax+10h]
0x18001a9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa03  nop
0x18001aa04  test    rbx, rbx
0x18001aa07  jz      short loc_18001AA12
0x18001aa09  mov     rcx, rbx; lpCriticalSection
0x18001aa0c  call    cs:__imp_LeaveCriticalSection
0x18001aa12  mov     eax, esi
0x18001aa14  add     rsp, 0A8h
0x18001aa1b  pop     r15
0x18001aa1d  pop     r14
0x18001aa1f  pop     rdi
0x18001aa20  pop     rsi
0x18001aa21  pop     rbx
0x18001aa22  pop     rbp
0x18001aa23  retn
```
