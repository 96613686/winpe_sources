# ipx::mtf::CMtfSuggestionClient::RequestLatticeSuggestion(int,IMtfLattice *,_MTF_QUERY_PROP *,ushort *)

- ea: `0x18001a150`
- end: `0x18001a446`
- name: `?RequestLatticeSuggestion@CMtfSuggestionClient@mtf@ipx@@UEAAJHPEAUIMtfLattice@@PEAU_MTF_QUERY_PROP@@PEAG@Z`
- size: `758`
- prototype: `__int64 __usercall@<rax>(ipx::mtf::CMtfSuggestionClient *__hidden this@<rcx>, int@<edx>, struct IMtfLattice *@<r8>, struct _MTF_QUERY_PROP *@<r9>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180019a28`
- `0x18001a150`
- `0x18001d1f4`
- `0x18001dbb4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a1e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a41e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a1e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a41e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a1ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a1ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a175`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RequestLatticeSuggestion(
        ipx::mtf::CMtfSuggestionClient *this,
        int a2,
        struct IMtfLattice *a3,
        struct _MTF_QUERY_PROP *a4,
        unsigned __int16 *a5)
{
  int v9; // ebx
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  ipx::mtf::CMtfSuggestionClient *v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  struct IMtfSuggestionInputQuery *v16; // rdi
  int v17; // eax
  unsigned int v18; // r14d
  struct IMtfPropertyBag *v19; // rcx
  int v20; // eax
  unsigned int v21; // esi
  struct IMtfPropertyBag *v22; // rcx
  struct IMtfPropertyBag *v23; // rcx
  unsigned int v24; // [rsp+20h] [rbp-68h]
  unsigned int v25; // [rsp+20h] [rbp-68h]
  unsigned int v26; // [rsp+20h] [rbp-68h]
  struct IMtfPropertyBag *v27; // [rsp+50h] [rbp-38h] BYREF
  struct IMtfSuggestionInputQuery *v28[3]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v30; // [rsp+90h] [rbp+8h] BYREF

  v9 = *((_DWORD *)this + 50);
  if ( v9 == GetCurrentThreadId() )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v28[1] = (ipx::mtf::CMtfSuggestionClient *)((char *)this + 64);
    if ( a4 )
    {
      v30 = 13;
      v28[0] = 0;
      try
      {
        v13 = ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(v12, a2 != 0, a4, 0, 0, a3, 0, v28, &v30);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v27 = 0;
          v16 = v28[0];
          v17 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(this, v30, 0, 0, 0, 0, 0, v28[0], &v27);
          v18 = v17;
          if ( v17 >= 0 )
          {
            *a5 = *((_WORD *)this + 102);
            v20 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(this, *((_WORD *)this + 102), v27);
            v21 = v20;
            if ( v20 >= 0 )
            {
              v23 = v27;
              if ( v27 )
              {
                v27 = 0;
                (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v23 + 16LL))(v23);
              }
              if ( v16 )
                (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v16 + 16LL))(v16);
              if ( v11 )
                LeaveCriticalSection(v11);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x434,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                (const char *)(unsigned int)v20,
                v26);
              v22 = v27;
              if ( v27 )
              {
                v27 = 0;
                (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v22 + 16LL))(v22);
              }
              if ( v16 )
                (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v16 + 16LL))(v16);
              if ( v11 )
                LeaveCriticalSection(v11);
              result = v21;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x430,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              (const char *)(unsigned int)v17,
              v26);
            v19 = v27;
            if ( v27 )
            {
              v27 = 0;
              (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v19 + 16LL))(v19);
            }
            if ( v16 )
              (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v16 + 16LL))(v16);
            if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
            result = v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x427,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v13,
            v25);
          if ( v28[0] )
            (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
          if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
          result = v14;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x439,
                               (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41B,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)0x80070057LL,
        v24);
      if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v24);
    return 2147549454LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001a150  mov     [rsp+arg_8], rbx
0x18001a155  mov     [rsp+arg_10], rsi
0x18001a15a  push    rdi
0x18001a15b  push    r14
0x18001a15d  push    r15
0x18001a15f  sub     rsp, 70h
0x18001a163  mov     rdi, r9
0x18001a166  mov     r14, r8
0x18001a169  mov     r15d, edx
0x18001a16c  mov     rsi, rcx
0x18001a16f  mov     ebx, [rcx+0C8h]
0x18001a175  call    cs:__imp_GetCurrentThreadId
0x18001a17b  cmp     ebx, eax
0x18001a17d  jz      short loc_18001A1A7
0x18001a17f  mov     rcx, [rsp+88h]; this
0x18001a187  mov     ebx, 8001010Eh
0x18001a18c  mov     r9d, ebx; char *
0x18001a18f  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a196  mov     edx, 417h; void *
0x18001a19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1a0  mov     eax, ebx
0x18001a1a2  jmp     loc_18001A42F
0x18001a1a7  lea     rbx, [rsi+40h]
0x18001a1ab  mov     rcx, rbx; lpCriticalSection
0x18001a1ae  call    cs:__imp_EnterCriticalSection
0x18001a1b4  mov     [rsp+88h+var_28], rbx
0x18001a1b9  test    rdi, rdi
0x18001a1bc  jnz     short loc_18001A1F5
0x18001a1be  mov     rcx, [rsp+88h]; this
0x18001a1c6  mov     edi, 80070057h
0x18001a1cb  mov     r9d, edi; char *
0x18001a1ce  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a1d5  mov     edx, 41Bh; void *
0x18001a1da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1df  nop
0x18001a1e0  test    rbx, rbx
0x18001a1e3  jz      short loc_18001A1EE
0x18001a1e5  mov     rcx, rbx; lpCriticalSection
0x18001a1e8  call    cs:__imp_LeaveCriticalSection
0x18001a1ee  mov     eax, edi
0x18001a1f0  jmp     loc_18001A42F
0x18001a1f5  mov     [rsp+88h+arg_0], 0Dh
0x18001a200  mov     [rsp+88h+var_30], 0
0x18001a209  test    r15d, r15d
0x18001a20c  setnz   dl; bool
0x18001a20f  lea     rax, [rsp+88h+arg_0]
0x18001a217  mov     [rsp+88h+var_48], rax; unsigned int *
0x18001a21c  lea     rax, [rsp+88h+var_30]
0x18001a221  mov     [rsp+88h+var_50], rax; struct IMtfSuggestionInputQuery **
0x18001a226  mov     [rsp+88h+var_58], 0; struct IMtfPropertyBag *
0x18001a22f  mov     [rsp+88h+var_60], r14; struct IMtfLattice *
0x18001a234  mov     [rsp+88h+var_68], 0; int
0x18001a23c  xor     r9d, r9d; unsigned __int8 *
0x18001a23f  mov     r8, rdi; struct _MTF_QUERY_PROP *
0x18001a242  call    ?_CreateSuggestionInputQuery@CMtfSuggestionClient@mtf@ipx@@IEAAJ_NPEBU_MTF_QUERY_PROP@@PEAEKPEAUIMtfLattice@@PEAUIMtfPropertyBag@@PEAPEAUIMtfSuggestionInputQuery@@PEAK@Z; ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(bool,_MTF_QUERY_PROP const *,uchar *,ulong,IMtfLattice *,IMtfPropertyBag *,IMtfSuggestionInputQuery * *,ulong *)
0x18001a247  mov     edi, eax
0x18001a249  test    eax, eax
0x18001a24b  jns     short loc_18001A296
0x18001a24d  mov     rcx, [rsp+88h]; this
0x18001a255  mov     r9d, eax; char *
0x18001a258  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a25f  mov     edx, 427h; void *
0x18001a264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a269  nop
0x18001a26a  mov     rcx, [rsp+88h+var_30]
0x18001a26f  test    rcx, rcx
0x18001a272  jz      short loc_18001A281
0x18001a274  mov     rax, [rcx]
0x18001a277  mov     rax, [rax+10h]
0x18001a27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a280  nop
0x18001a281  test    rbx, rbx
0x18001a284  jz      short loc_18001A28F
0x18001a286  mov     rcx, rbx; lpCriticalSection
0x18001a289  call    cs:__imp_LeaveCriticalSection
0x18001a28f  mov     eax, edi
0x18001a291  jmp     loc_18001A42F
0x18001a296  mov     [rsp+88h+var_38], 0
0x18001a29f  lea     rax, [rsp+88h+var_38]
0x18001a2a4  mov     [rsp+88h+var_48], rax; struct IMtfPropertyBag **
0x18001a2a9  mov     rdi, [rsp+88h+var_30]
0x18001a2ae  mov     [rsp+88h+var_50], rdi; struct IMtfSuggestionInputQuery *
0x18001a2b3  mov     [rsp+88h+var_58], 0; struct IMtfSuggestionContextProperty *
0x18001a2bc  mov     [rsp+88h+var_60], 0; struct IMtfSuggestionCandidatePrimitive *
0x18001a2c5  mov     [rsp+88h+var_68], 0; int
0x18001a2cd  xor     r9d, r9d; unsigned __int8 *
0x18001a2d0  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x18001a2d3  mov     edx, [rsp+88h+arg_0]; unsigned int
0x18001a2da  mov     rcx, rsi; this
0x18001a2dd  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x18001a2e2  mov     r14d, eax
0x18001a2e5  test    eax, eax
0x18001a2e7  jns     short loc_18001A351
0x18001a2e9  mov     rcx, [rsp+88h]; this
0x18001a2f1  mov     r9d, eax; char *
0x18001a2f4  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a2fb  mov     edx, 430h; void *
0x18001a300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a305  nop
0x18001a306  mov     rcx, [rsp+88h+var_38]
0x18001a30b  test    rcx, rcx
0x18001a30e  jz      short loc_18001A326
0x18001a310  mov     [rsp+88h+var_38], 0
0x18001a319  mov     rax, [rcx]
0x18001a31c  mov     rax, [rax+10h]
0x18001a320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a325  nop
0x18001a326  test    rdi, rdi
0x18001a329  jz      short loc_18001A33B
0x18001a32b  mov     rax, [rdi]
0x18001a32e  mov     rcx, rdi
0x18001a331  mov     rax, [rax+10h]
0x18001a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a33a  nop
0x18001a33b  test    rbx, rbx
0x18001a33e  jz      short loc_18001A349
0x18001a340  mov     rcx, rbx; lpCriticalSection
0x18001a343  call    cs:__imp_LeaveCriticalSection
0x18001a349  mov     eax, r14d
0x18001a34c  jmp     loc_18001A42F
0x18001a351  movzx   ecx, word ptr [rsi+0CCh]
0x18001a358  mov     rax, [rsp+88h+arg_20]
0x18001a360  mov     [rax], cx
0x18001a363  mov     r8, [rsp+88h+var_38]; struct IMtfPropertyBag *
0x18001a368  movzx   edx, word ptr [rsi+0CCh]; unsigned __int16
0x18001a36f  mov     rcx, rsi; this
0x18001a372  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x18001a377  mov     esi, eax
0x18001a379  test    eax, eax
0x18001a37b  jns     short loc_18001A3E1
0x18001a37d  mov     rcx, [rsp+88h]; this
0x18001a385  mov     r9d, eax; char *
0x18001a388  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001a38f  mov     edx, 434h; void *
0x18001a394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a399  nop
0x18001a39a  mov     rcx, [rsp+88h+var_38]
0x18001a39f  test    rcx, rcx
0x18001a3a2  jz      short loc_18001A3BA
0x18001a3a4  mov     [rsp+88h+var_38], 0
0x18001a3ad  mov     rax, [rcx]
0x18001a3b0  mov     rax, [rax+10h]
0x18001a3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b9  nop
0x18001a3ba  test    rdi, rdi
0x18001a3bd  jz      short loc_18001A3CF
0x18001a3bf  mov     rax, [rdi]
0x18001a3c2  mov     rcx, rdi
0x18001a3c5  mov     rax, [rax+10h]
0x18001a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3ce  nop
0x18001a3cf  test    rbx, rbx
0x18001a3d2  jz      short loc_18001A3DD
0x18001a3d4  mov     rcx, rbx; lpCriticalSection
0x18001a3d7  call    cs:__imp_LeaveCriticalSection
0x18001a3dd  mov     eax, esi
0x18001a3df  jmp     short loc_18001A42F
0x18001a3e1  mov     rcx, [rsp+88h+var_38]
0x18001a3e6  test    rcx, rcx
0x18001a3e9  jz      short loc_18001A401
0x18001a3eb  mov     [rsp+88h+var_38], 0
0x18001a3f4  mov     rax, [rcx]
0x18001a3f7  mov     rax, [rax+10h]
0x18001a3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a400  nop
0x18001a401  test    rdi, rdi
0x18001a404  jz      short loc_18001A416
0x18001a406  mov     rax, [rdi]
0x18001a409  mov     rcx, rdi
0x18001a40c  mov     rax, [rax+10h]
0x18001a410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a415  nop
0x18001a416  test    rbx, rbx
0x18001a419  jz      short loc_18001A424
0x18001a41b  mov     rcx, rbx; lpCriticalSection
0x18001a41e  call    cs:__imp_LeaveCriticalSection
0x18001a424  xor     eax, eax
0x18001a426  jmp     short loc_18001A42F
0x18001a428  mov     eax, [rsp+88h+arg_0]
0x18001a42f  lea     r11, [rsp+88h+var_18]
0x18001a434  mov     rbx, [r11+28h]
0x18001a438  mov     rsi, [r11+30h]
0x18001a43c  mov     rsp, r11
0x18001a43f  pop     r15
0x18001a441  pop     r14
0x18001a443  pop     rdi
0x18001a444  retn
```
