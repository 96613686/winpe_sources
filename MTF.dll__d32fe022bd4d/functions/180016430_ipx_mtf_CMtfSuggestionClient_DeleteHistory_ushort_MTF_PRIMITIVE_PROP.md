# ipx::mtf::CMtfSuggestionClient::DeleteHistory(ushort,_MTF_PRIMITIVE_PROP *)

- ea: `0x180016430`
- end: `0x18001674a`
- name: `?DeleteHistory@CMtfSuggestionClient@mtf@ipx@@UEAAJGPEAU_MTF_PRIMITIVE_PROP@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, unsigned __int16, struct _MTF_PRIMITIVE_PROP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180006074`
- `0x180014848`
- `0x180016430`
- `0x180019a28`
- `0x18001d1f4`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001649f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001658f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800165f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016707`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016719`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001649f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001658f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800165f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016707`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016719`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016461`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016461`
- `OLEAUT32!__imp_SysStringLen` at `0x1800164f8`
- `OLEAUT32!__imp_SysStringLen` at `0x18001650a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800164f8`
- `OLEAUT32!__imp_SysStringLen` at `0x18001650a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::DeleteHistory(
        ipx::mtf::CMtfSuggestionClient *this,
        unsigned __int16 a2,
        BSTR *a3)
{
  unsigned __int64 v4; // rbx
  struct IMtfPropertyBag *v6; // rdi
  int Instance; // eax
  unsigned int v9; // r15d
  struct IMtfSuggestionCandidatePrimitive *v10; // rcx
  int v11; // eax
  unsigned int v12; // r14d
  struct IMtfSuggestionCandidatePrimitive *v13; // rcx
  int RequestBag; // eax
  unsigned int v15; // r14d
  struct IMtfPropertyBag *v16; // rcx
  struct IMtfSuggestionCandidatePrimitive *v17; // rcx
  unsigned int v18; // esi
  struct IMtfPropertyBag *v19; // rcx
  struct IMtfSuggestionCandidatePrimitive *v20; // rcx
  int v21; // [rsp+20h] [rbp-98h]
  int v22; // [rsp+20h] [rbp-98h]
  int v23; // [rsp+20h] [rbp-98h]
  struct IMtfSuggestionCandidatePrimitive *v24; // [rsp+50h] [rbp-68h] BYREF
  struct IMtfPropertyBag *v25[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v26; // [rsp+68h] [rbp-50h] BYREF
  __int64 v27; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v4 = a2;
  v6 = (ipx::mtf::CMtfSuggestionClient *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v25[1] = v6;
  if ( v4 < *((_QWORD *)this + 24) )
  {
    v26 = 0;
    v27 = 0;
    v26 = *(_OWORD *)*(_QWORD *)std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](
                                  (__int64)this + 160,
                                  (unsigned int)v4);
    WORD2(v27) = v4;
    if ( a3 && (*(_BYTE *)a3 & 3) == 3 && SysStringLen(a3[1]) && SysStringLen(a3[2]) )
    {
      v24 = 0;
      Instance = Hooked_CoCreateInstance(
                   &CLSID_MtfPrimitive,
                   0,
                   1u,
                   &GUID_92445657_1419_4aaa_a92f_486ab29470c0,
                   (void **)&v24);
      v9 = Instance;
      if ( Instance >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *, BSTR *))(*(_QWORD *)v24 + 32LL))(
                v24,
                a3);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v25[0] = 0;
          RequestBag = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
                         this,
                         6u,
                         (const struct MTFCORE_SIMPLEPARAM *)&v26,
                         0,
                         0,
                         v24,
                         0,
                         0,
                         v25);
          v15 = RequestBag;
          if ( RequestBag >= 0 )
          {
            v18 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(this, *((_WORD *)this + 102), v25[0]);
            v19 = v25[0];
            if ( v25[0] )
            {
              v25[0] = 0;
              (*(void (__fastcall **)(struct IMtfPropertyBag *, _QWORD))(*(_QWORD *)v19 + 16LL))(v19, *(_QWORD *)v19);
            }
            v20 = v24;
            v24 = 0;
            if ( v20 )
              (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v20 + 16LL))(v20);
            if ( v6 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v6);
            return v18;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x319,
              (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
              (const char *)(unsigned int)RequestBag,
              v23);
            v16 = v25[0];
            if ( v25[0] )
            {
              v25[0] = 0;
              (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v17 = v24;
            v24 = 0;
            if ( v17 )
              (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v17 + 16LL))(v17);
            if ( v6 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v6);
            return v15;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30F,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v11,
            v22);
          v13 = v24;
          v24 = 0;
          if ( v13 )
            (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v13 + 16LL))(v13);
          if ( v6 )
            LeaveCriticalSection((LPCRITICAL_SECTION)v6);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)Instance,
          v22);
        v10 = v24;
        v24 = 0;
        if ( v10 )
          (*(void (__fastcall **)(struct IMtfSuggestionCandidatePrimitive *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v6 )
          LeaveCriticalSection((LPCRITICAL_SECTION)v6);
        return v9;
      }
    }
    else
    {
      if ( v6 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v6);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x80070057LL,
      v21);
    if ( v6 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180016430  push    rbx
0x180016432  push    rsi
0x180016433  push    rdi
0x180016434  push    r14
0x180016436  push    r15
0x180016438  sub     rsp, 90h
0x18001643f  mov     rax, cs:__security_cookie
0x180016446  xor     rax, rsp
0x180016449  mov     [rsp+0B8h+var_38], rax
0x180016451  mov     r14, r8
0x180016454  movzx   ebx, dx
0x180016457  mov     rsi, rcx
0x18001645a  lea     rdi, [rcx+40h]
0x18001645e  mov     rcx, rdi; lpCriticalSection
0x180016461  call    cs:__imp_EnterCriticalSection
0x180016467  mov     [rsp+0B8h+var_58], rdi
0x18001646c  mov     edx, ebx
0x18001646e  cmp     rbx, [rsi+0C0h]
0x180016475  jb      short loc_1800164AF
0x180016477  mov     rcx, [rsp+0B8h]; this
0x18001647f  mov     r9d, 80070057h; char *
0x180016485  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001648c  mov     edx, 2F9h; void *
0x180016491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016496  nop
0x180016497  test    rdi, rdi
0x18001649a  jz      short loc_1800164A5
0x18001649c  mov     rcx, rdi; lpCriticalSection
0x18001649f  call    cs:__imp_LeaveCriticalSection
0x1800164a5  mov     eax, 80070057h
0x1800164aa  jmp     loc_18001672A
0x1800164af  xorps   xmm0, xmm0
0x1800164b2  xor     eax, eax
0x1800164b4  movups  [rsp+0B8h+var_50], xmm0
0x1800164b9  mov     [rsp+0B8h+var_40], rax
0x1800164be  lea     rcx, [rsi+0A0h]
0x1800164c5  call    ??A?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@1@_K@Z; std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](unsigned __int64)
0x1800164ca  mov     rax, [rax]
0x1800164cd  movups  xmm0, xmmword ptr [rax]
0x1800164d0  movdqu  [rsp+0B8h+var_50], xmm0
0x1800164d6  mov     word ptr [rsp+0B8h+var_40+4], bx
0x1800164db  xor     ebx, ebx
0x1800164dd  test    r14, r14
0x1800164e0  jz      loc_180016711
0x1800164e6  mov     eax, [r14]
0x1800164e9  and     eax, 3
0x1800164ec  cmp     al, 3
0x1800164ee  jnz     loc_180016711
0x1800164f4  mov     rcx, [r14+8]; pbstr
0x1800164f8  call    cs:__imp_SysStringLen
0x1800164fe  test    eax, eax
0x180016500  jz      loc_180016711
0x180016506  mov     rcx, [r14+10h]; pbstr
0x18001650a  call    cs:__imp_SysStringLen
0x180016510  test    eax, eax
0x180016512  jz      loc_180016711
0x180016518  mov     [rsp+0B8h+var_68], rbx
0x18001651d  lea     rax, [rsp+0B8h+var_68]
0x180016522  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180016527  lea     r9, _GUID_92445657_1419_4aaa_a92f_486ab29470c0
0x18001652e  xor     edx, edx
0x180016530  lea     r8d, [rbx+1]
0x180016534  lea     rcx, CLSID_MtfPrimitive
0x18001653b  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180016542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016547  mov     r15d, eax
0x18001654a  test    eax, eax
0x18001654c  jns     short loc_18001659D
0x18001654e  mov     rcx, [rsp+0B8h]; this
0x180016556  mov     r9d, eax; char *
0x180016559  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016560  mov     edx, 30Eh; void *
0x180016565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001656a  nop
0x18001656b  mov     rcx, [rsp+0B8h+var_68]
0x180016570  mov     [rsp+0B8h+var_68], rbx
0x180016575  test    rcx, rcx
0x180016578  jz      short loc_180016587
0x18001657a  mov     rax, [rcx]
0x18001657d  mov     rax, [rax+10h]
0x180016581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016586  nop
0x180016587  test    rdi, rdi
0x18001658a  jz      short loc_180016595
0x18001658c  mov     rcx, rdi; lpCriticalSection
0x18001658f  call    cs:__imp_LeaveCriticalSection
0x180016595  mov     eax, r15d
0x180016598  jmp     loc_18001672A
0x18001659d  mov     rcx, [rsp+0B8h+var_68]
0x1800165a2  mov     rax, [rcx]
0x1800165a5  mov     rdx, r14
0x1800165a8  mov     rax, [rax+20h]
0x1800165ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b1  mov     r14d, eax
0x1800165b4  test    eax, eax
0x1800165b6  jns     short loc_180016607
0x1800165b8  mov     rcx, [rsp+0B8h]; this
0x1800165c0  mov     r9d, eax; char *
0x1800165c3  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x1800165ca  mov     edx, 30Fh; void *
0x1800165cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165d4  nop
0x1800165d5  mov     rcx, [rsp+0B8h+var_68]
0x1800165da  mov     [rsp+0B8h+var_68], rbx
0x1800165df  test    rcx, rcx
0x1800165e2  jz      short loc_1800165F1
0x1800165e4  mov     rax, [rcx]
0x1800165e7  mov     rax, [rax+10h]
0x1800165eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165f0  nop
0x1800165f1  test    rdi, rdi
0x1800165f4  jz      short loc_1800165FF
0x1800165f6  mov     rcx, rdi; lpCriticalSection
0x1800165f9  call    cs:__imp_LeaveCriticalSection
0x1800165ff  mov     eax, r14d
0x180016602  jmp     loc_18001672A
0x180016607  mov     [rsp+0B8h+var_60], rbx
0x18001660c  mov     rax, [rsp+0B8h+var_68]
0x180016611  lea     rcx, [rsp+0B8h+var_60]
0x180016616  mov     [rsp+0B8h+var_78], rcx; struct IMtfPropertyBag **
0x18001661b  mov     [rsp+0B8h+var_80], rbx; struct IMtfSuggestionInputQuery *
0x180016620  mov     [rsp+0B8h+var_88], rbx; struct IMtfSuggestionContextProperty *
0x180016625  mov     [rsp+0B8h+var_90], rax; struct IMtfSuggestionCandidatePrimitive *
0x18001662a  mov     [rsp+0B8h+var_98], ebx; int
0x18001662e  xor     r9d, r9d; unsigned __int8 *
0x180016631  lea     r8, [rsp+0B8h+var_50]; struct MTFCORE_SIMPLEPARAM *
0x180016636  lea     edx, [r9+6]; unsigned int
0x18001663a  mov     rcx, rsi; this
0x18001663d  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x180016642  mov     r14d, eax
0x180016645  test    eax, eax
0x180016647  jns     short loc_1800166B1
0x180016649  mov     rcx, [rsp+0B8h]; this
0x180016651  mov     r9d, eax; char *
0x180016654  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001665b  mov     edx, 319h; void *
0x180016660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016665  nop
0x180016666  mov     rcx, [rsp+0B8h+var_60]
0x18001666b  test    rcx, rcx
0x18001666e  jz      short loc_180016682
0x180016670  mov     [rsp+0B8h+var_60], rbx
0x180016675  mov     rax, [rcx]
0x180016678  mov     rax, [rax+10h]
0x18001667c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016681  nop
0x180016682  mov     rcx, [rsp+0B8h+var_68]
0x180016687  mov     [rsp+0B8h+var_68], rbx
0x18001668c  test    rcx, rcx
0x18001668f  jz      short loc_18001669E
0x180016691  mov     rax, [rcx]
0x180016694  mov     rax, [rax+10h]
0x180016698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001669d  nop
0x18001669e  test    rdi, rdi
0x1800166a1  jz      short loc_1800166AC
0x1800166a3  mov     rcx, rdi; lpCriticalSection
0x1800166a6  call    cs:__imp_LeaveCriticalSection
0x1800166ac  mov     eax, r14d
0x1800166af  jmp     short loc_18001672A
0x1800166b1  mov     r8, [rsp+0B8h+var_60]; struct IMtfPropertyBag *
0x1800166b6  movzx   edx, word ptr [rsi+0CCh]; unsigned __int16
0x1800166bd  mov     rcx, rsi; this
0x1800166c0  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x1800166c5  mov     esi, eax
0x1800166c7  mov     rcx, [rsp+0B8h+var_60]
0x1800166cc  test    rcx, rcx
0x1800166cf  jz      short loc_1800166E3
0x1800166d1  mov     [rsp+0B8h+var_60], rbx
0x1800166d6  mov     rdx, [rcx]
0x1800166d9  mov     rax, [rdx+10h]
0x1800166dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e2  nop
0x1800166e3  mov     rcx, [rsp+0B8h+var_68]
0x1800166e8  mov     [rsp+0B8h+var_68], rbx
0x1800166ed  test    rcx, rcx
0x1800166f0  jz      short loc_1800166FF
0x1800166f2  mov     rax, [rcx]
0x1800166f5  mov     rax, [rax+10h]
0x1800166f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166fe  nop
0x1800166ff  test    rdi, rdi
0x180016702  jz      short loc_18001670D
0x180016704  mov     rcx, rdi; lpCriticalSection
0x180016707  call    cs:__imp_LeaveCriticalSection
0x18001670d  mov     eax, esi
0x18001670f  jmp     short loc_18001672A
0x180016711  test    rdi, rdi
0x180016714  jz      short loc_18001671F
0x180016716  mov     rcx, rdi; lpCriticalSection
0x180016719  call    cs:__imp_LeaveCriticalSection
0x18001671f  mov     eax, 80070057h
0x180016724  jmp     short loc_18001672A
0x180016726  mov     eax, dword ptr [rsp+0B8h+var_68]
0x18001672a  mov     rcx, [rsp+0B8h+var_38]
0x180016732  xor     rcx, rsp; StackCookie
0x180016735  call    __security_check_cookie
0x18001673a  add     rsp, 90h
0x180016741  pop     r15
0x180016743  pop     r14
0x180016745  pop     rdi
0x180016746  pop     rsi
0x180016747  pop     rbx
0x180016748  retn
```
