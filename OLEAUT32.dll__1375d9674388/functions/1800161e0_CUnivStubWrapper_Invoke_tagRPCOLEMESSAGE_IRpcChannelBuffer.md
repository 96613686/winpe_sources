# CUnivStubWrapper::Invoke(tagRPCOLEMESSAGE *,IRpcChannelBuffer *)

- ea: `0x1800161e0`
- end: `0x180016497`
- name: `?Invoke@CUnivStubWrapper@@UEAAJPEAUtagRPCOLEMESSAGE@@PEAUIRpcChannelBuffer@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(CUnivStubWrapper *__hidden this, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180011cd4`
- `0x180011fb4`
- `0x180014f04`
- `0x1800161b8`
- `0x1800161e0`
- `0x180032948`
- `0x18004f1b4`
- `0x18008627c`
- `0x1800862ac`
- `0x1800862d4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001624e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001624e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163b0`
- `RPCRT4!CreateStubFromTypeInfo` at `0x1800162e5`
- `RPCRT4!CreateStubFromTypeInfo` at `0x1800162e5`

## string_xrefs

- `0x18001633a`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x180016362`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x1800163f8`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x18001645b`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x180016475`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`

## pseudocode

```c
__int64 __fastcall CUnivStubWrapper::Invoke(
        CUnivStubWrapper *this,
        struct tagRPCOLEMESSAGE *a2,
        struct IRpcChannelBuffer *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v9; // rax
  signed int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  int TypeInfoOfIID; // eax
  int v14; // eax
  struct ITypeInfo *v15; // rcx
  struct ITypeInfo *v16; // rcx
  struct ITypeInfo *v17; // rdi
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v22[8]; // [rsp+28h] [rbp-28h] BYREF
  _BYTE v23[16]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct ITypeInfo *v26; // [rsp+88h] [rbp+38h] BYREF
  __int64 v27; // [rsp+98h] [rbp+48h] BYREF

  if ( (a2->rpcFlags & 0x80000000) == 0 )
  {
    v27 = *((_QWORD *)this + 4);
    v6 = v27;
    if ( v27 )
    {
LABEL_3:
      v7 = (*(__int64 (__fastcall **)(__int64, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))(*(_QWORD *)v6 + 40LL))(
             v6,
             a2,
             a3);
      if ( v7 >= 0 )
        return 0;
      v20 = 654;
      goto LABEL_28;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v24, v9);
    v27 = *((_QWORD *)this + 4);
    if ( v27 )
    {
LABEL_12:
      wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v24);
      v6 = v27;
      goto LABEL_3;
    }
    TokenHandle = 0;
    v10 = SuspendImpersonate(&TokenHandle);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27D,
        (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
        (const char *)(unsigned int)v10,
        (int)TokenHandle);
    }
    else
    {
      v12 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v22,
              &TokenHandle);
      wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v23, v12);
      v26 = 0;
      Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&v26);
      TypeInfoOfIID = GetTypeInfoOfIID((const struct _GUID *)((char *)this + 40), &v26);
      v11 = TypeInfoOfIID;
      if ( TypeInfoOfIID < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x281,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)TypeInfoOfIID,
          (int)TokenHandle);
        v16 = v26;
        if ( v26 )
        {
          v26 = 0;
          ((void (__fastcall *)(struct ITypeInfo *))v16->lpVtbl->Release)(v16);
        }
      }
      else
      {
        v14 = CreateStubFromTypeInfo(v26, (char *)this + 40, *((_QWORD *)this + 2), &v27);
        v11 = v14;
        if ( v14 >= 0 )
        {
          v15 = v26;
          *((_QWORD *)this + 4) = v27;
          if ( v15 )
          {
            v26 = 0;
            ((void (__fastcall *)(struct ITypeInfo *))v15->lpVtbl->Release)(v15);
          }
          wil::details::lambda_call__CUnivStubWrapper::Invoke_::_33_::_lambda_3___::_lambda_call__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v23);
          goto LABEL_12;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x287,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)v14,
          (int)TokenHandle);
        Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&v26);
      }
      wil::details::lambda_call__CUnivStubWrapper::Invoke_::_33_::_lambda_3___::_lambda_call__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v23);
    }
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v24);
    return v11;
  }
  v17 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( !v17 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v18 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v23, v18);
    v17 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    v26 = v17;
    if ( !v17 )
    {
      v19 = CreateRealStub(0, (char *)this + 40, *((_QWORD *)this + 2), &v26);
      v11 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x264,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)v19,
          (int)TokenHandle);
        wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v23);
        return v11;
      }
      v17 = v26;
      *((_QWORD *)this + 3) = v26;
    }
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v23);
  }
  v7 = ((__int64 (__fastcall *)(struct ITypeInfo *, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))v17->lpVtbl->GetFuncDesc)(
         v17,
         a2,
         a3);
  if ( v7 >= 0 )
    return 0;
  v20 = 619;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
    (const char *)(unsigned int)v7,
    (int)TokenHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800161e0  mov     [rsp-28h+arg_0], rbx
0x1800161e5  push    rbp
0x1800161e6  push    rsi
0x1800161e7  push    rdi
0x1800161e8  push    r14
0x1800161ea  push    r15
0x1800161ec  mov     rbp, rsp
0x1800161ef  sub     rsp, 50h
0x1800161f3  cmp     dword ptr [rdx+48h], 0
0x1800161f7  mov     r15, r8
0x1800161fa  mov     rsi, rdx
0x1800161fd  mov     rbx, rcx
0x180016200  jl      loc_18001639E
0x180016206  mov     rax, [rcx+20h]
0x18001620a  mov     [rbp+arg_18], rax
0x18001620e  nop
0x18001620f  mov     rcx, [rbp+arg_18]
0x180016213  test    rcx, rcx
0x180016216  jz      short loc_18001624A
0x180016218  mov     rax, [rcx]
0x18001621b  mov     r8, r15
0x18001621e  mov     rdx, rsi
0x180016221  mov     rax, [rax+28h]
0x180016225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001622a  mov     ebx, eax
0x18001622c  test    eax, eax
0x18001622e  js      loc_180016452
0x180016234  xor     eax, eax
0x180016236  mov     rbx, [rsp+50h+arg_0]
0x18001623e  add     rsp, 50h
0x180016242  pop     r15
0x180016244  pop     r14
0x180016246  pop     rdi
0x180016247  pop     rsi
0x180016248  pop     rbp
0x180016249  retn
0x18001624a  lea     rcx, [rbx+38h]; lpCriticalSection
0x18001624e  call    cs:__imp_EnterCriticalSection
0x180016254  mov     rdx, rbx
0x180016257  lea     rcx, [rbp+arg_8]
0x18001625b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180016260  mov     rdx, rax
0x180016263  lea     rcx, [rbp+var_10]
0x180016267  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x18001626c  mov     rcx, [rbx+20h]
0x180016270  mov     [rbp+arg_18], rcx
0x180016274  test    rcx, rcx
0x180016277  jnz     loc_180016324
0x18001627d  mov     [rbp+TokenHandle], rcx
0x180016281  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180016285  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18001628a  mov     edi, eax
0x18001628c  test    eax, eax
0x18001628e  js      loc_180016336
0x180016294  lea     rdx, [rbp+TokenHandle]
0x180016298  lea     rcx, [rbp+var_28]
0x18001629c  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800162a1  mov     rdx, rax
0x1800162a4  lea     rcx, [rbp+var_20]
0x1800162a8  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x1800162ad  lea     rcx, [rbp+arg_8]
0x1800162b1  mov     [rbp+arg_8], 0
0x1800162b9  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x1800162be  lea     rdx, [rbp+arg_8]; struct ITypeInfo **
0x1800162c2  lea     rcx, [rbx+28h]; struct _GUID *
0x1800162c6  call    ?GetTypeInfoOfIID@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@@Z; GetTypeInfoOfIID(_GUID const &,ITypeInfo * *)
0x1800162cb  mov     edi, eax
0x1800162cd  test    eax, eax
0x1800162cf  js      loc_18001635E
0x1800162d5  mov     r8, [rbx+10h]
0x1800162d9  lea     r9, [rbp+arg_18]
0x1800162dd  mov     rcx, [rbp+arg_8]
0x1800162e1  lea     rdx, [rbx+28h]
0x1800162e5  call    cs:__imp_CreateStubFromTypeInfo
0x1800162eb  mov     edi, eax
0x1800162ed  test    eax, eax
0x1800162ef  js      loc_180016471
0x1800162f5  nop
0x1800162f6  mov     rcx, [rbp+arg_8]
0x1800162fa  mov     rax, [rbp+arg_18]
0x1800162fe  mov     [rbx+20h], rax
0x180016302  test    rcx, rcx
0x180016305  jz      short loc_18001631B
0x180016307  mov     [rbp+arg_8], 0
0x18001630f  mov     rax, [rcx]
0x180016312  mov     rax, [rax+10h]
0x180016316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001631b  lea     rcx, [rbp+var_20]
0x18001631f  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____33____lambda_3______lambda_call__CUnivStubWrapper__Invoke____33____lambda_3___
0x180016324  lea     rcx, [rbp+var_10]
0x180016328  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x18001632d  mov     rcx, [rbp+arg_18]
0x180016331  jmp     loc_180016218
0x180016336  mov     rcx, [rbp+28h]; this
0x18001633a  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180016341  mov     r9d, eax; char *
0x180016344  mov     edx, 27Dh; void *
0x180016349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001634e  lea     rcx, [rbp+var_10]
0x180016352  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180016357  mov     eax, edi
0x180016359  jmp     loc_180016236
0x18001635e  mov     rcx, [rbp+28h]; this
0x180016362  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180016369  mov     r9d, eax; char *
0x18001636c  mov     edx, 281h; void *
0x180016371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016376  mov     rcx, [rbp+arg_8]
0x18001637a  test    rcx, rcx
0x18001637d  jz      short loc_180016393
0x18001637f  mov     [rbp+arg_8], 0
0x180016387  mov     rax, [rcx]
0x18001638a  mov     rax, [rax+10h]
0x18001638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016393  lea     rcx, [rbp+var_20]
0x180016397  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____33____lambda_3______lambda_call__CUnivStubWrapper__Invoke____33____lambda_3___
0x18001639c  jmp     short loc_18001634E
0x18001639e  mov     rdi, [rcx+18h]
0x1800163a2  nop
0x1800163a3  test    rdi, rdi
0x1800163a6  jnz     loc_18001642C
0x1800163ac  add     rcx, 38h ; '8'; lpCriticalSection
0x1800163b0  call    cs:__imp_EnterCriticalSection
0x1800163b6  mov     rdx, rbx
0x1800163b9  lea     rcx, [rbp+arg_8]
0x1800163bd  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800163c2  mov     rdx, rax
0x1800163c5  lea     rcx, [rbp+var_20]
0x1800163c9  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x1800163ce  mov     rdi, [rbx+18h]
0x1800163d2  mov     [rbp+arg_8], rdi
0x1800163d6  test    rdi, rdi
0x1800163d9  jnz     short loc_180016423
0x1800163db  mov     r8, [rbx+10h]
0x1800163df  lea     rdx, [rbx+28h]
0x1800163e3  lea     r9, [rbp+arg_8]
0x1800163e7  xor     ecx, ecx
0x1800163e9  call    CreateRealStub
0x1800163ee  mov     edi, eax
0x1800163f0  test    eax, eax
0x1800163f2  jns     short loc_18001641A
0x1800163f4  mov     rcx, [rbp+28h]; this
0x1800163f8  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x1800163ff  mov     r9d, eax; char *
0x180016402  mov     edx, 264h; void *
0x180016407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001640c  lea     rcx, [rbp+var_20]
0x180016410  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180016415  jmp     loc_180016357
0x18001641a  mov     rdi, [rbp+arg_8]
0x18001641e  nop
0x18001641f  mov     [rbx+18h], rdi
0x180016423  lea     rcx, [rbp+var_20]
0x180016427  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x18001642c  mov     rax, [rdi]
0x18001642f  mov     r8, r15
0x180016432  mov     rdx, rsi
0x180016435  mov     rcx, rdi
0x180016438  mov     rax, [rax+28h]
0x18001643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016441  mov     ebx, eax
0x180016443  test    eax, eax
0x180016445  jns     loc_180016234
0x18001644b  mov     edx, 26Bh
0x180016450  jmp     short loc_180016457
0x180016452  mov     edx, 28Eh; void *
0x180016457  mov     rcx, [rbp+28h]; this
0x18001645b  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180016462  mov     r9d, ebx; char *
0x180016465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001646a  mov     eax, ebx
0x18001646c  jmp     loc_180016236
0x180016471  mov     rcx, [rbp+28h]; this
0x180016475  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x18001647c  mov     r9d, eax; char *
0x18001647f  mov     edx, 287h; void *
0x180016484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016489  lea     rcx, [rbp+arg_8]
0x18001648d  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x180016492  jmp     loc_180016393
```
