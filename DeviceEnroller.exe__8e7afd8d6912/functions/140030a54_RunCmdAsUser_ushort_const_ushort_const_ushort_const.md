# RunCmdAsUser(ushort const *,ushort const *,ushort const *)

- ea: `0x140030a54`
- end: `0x1400310be`
- name: `?RunCmdAsUser@@YAJPEBG00@Z`
- size: `1642`
- prototype: `__int64 __fastcall(char *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140033dd0`

## callees

- `0x1400095b4`
- `0x14001ea48`
- `0x14001ef20`
- `0x14001ef94`
- `0x14002e088`
- `0x140030a54`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f43`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030f57`
- `OLEAUT32!__imp_SysAllocString` at `0x140030d60`
- `OLEAUT32!__imp_SysAllocString` at `0x140030d60`
- `OLEAUT32!__imp_VariantInit` at `0x140030d37`
- `OLEAUT32!__imp_VariantInit` at `0x140030d4c`
- `OLEAUT32!__imp_VariantInit` at `0x140030e79`
- `OLEAUT32!__imp_VariantInit` at `0x140030d37`
- `OLEAUT32!__imp_VariantInit` at `0x140030d4c`
- `OLEAUT32!__imp_VariantInit` at `0x140030e79`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140030f2b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140030f2b`

## pseudocode

```c
__int64 __fastcall RunCmdAsUser(char *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  struct ITaskDefinition *v7; // rbx
  int v8; // eax
  int v9; // edi
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  struct ITaskFolder *v13; // rdi
  struct ITaskFolderVtbl *lpVtbl; // r14
  __int128 v15; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v17; // xmm10
  IRecordInfo *v18; // xmm11_8
  BSTR v19; // rax
  __int128 v20; // xmm6
  IRecordInfo *v21; // xmm7_8
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  unsigned int v24; // esi
  __int64 v25; // r14
  __int64 (__fastcall *v26)(__int64, VARIANTARG *, __int64); // rsi
  char *v27; // rsi
  HRESULT (__stdcall *DeleteTask)(ITaskFolder *, BSTR, LONG); // rsi
  _QWORD *v29; // rdx
  int v30; // [rsp+28h] [rbp-E0h]
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  struct ITaskFolder *v33; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-98h] BYREF
  __int64 v35; // [rsp+78h] [rbp-90h] BYREF
  struct ITaskDefinition *v36; // [rsp+80h] [rbp-88h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h]
  __int64 v38; // [rsp+90h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v40; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v42; // [rsp+E8h] [rbp-20h]
  VARIANTARG v43; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v44; // [rsp+108h] [rbp+0h]
  IRecordInfo *v45; // [rsp+118h] [rbp+10h]
  __int128 v46; // [rsp+128h] [rbp+20h]
  IRecordInfo *v47; // [rsp+138h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]
  char *v49; // [rsp+1C8h] [rbp+C0h] BYREF
  DWORD dwProcessId; // [rsp+1E0h] [rbp+D8h] BYREF

  v49 = a1;
  v36 = 0;
  v33 = 0;
  v4 = CreateTaskForUser((const unsigned __int16 *)a1, &v36, &v33, a2, a3);
  v5 = v4;
  LODWORD(v49) = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4,
      v30);
    if ( v33 )
      ((void (__fastcall *)(struct ITaskFolder *))v33->lpVtbl->Release)(v33);
    if ( v36 )
      ((void (__fastcall *)(struct ITaskDefinition *))v36->lpVtbl->Release)(v36);
    return v5;
  }
  v31 = 0;
  v7 = v36;
  v8 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v36->lpVtbl->get_Triggers)(v36, &v31);
  v9 = v8;
  LODWORD(v49) = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEFA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v8,
      v30);
LABEL_9:
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v33 )
      ((void (__fastcall *)(struct ITaskFolder *))v33->lpVtbl->Release)(v33);
    if ( v7 )
      ((void (__fastcall *)(struct ITaskDefinition *))v7->lpVtbl->Release)(v7);
    return (unsigned int)v9;
  }
  v32 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v31 + 80LL))(v31, 9, &v32);
  v9 = v10;
  LODWORD(v49) = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEFE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v10,
      v30);
LABEL_18:
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    goto LABEL_9;
  }
  v34 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v32)(v32, &IID_ILogonTrigger, &v34);
  v9 = v11;
  LODWORD(v49) = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF02,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v11,
      v30);
LABEL_22:
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    goto LABEL_18;
  }
  v35 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 80LL))(v34, &v35);
  LODWORD(v49) = v9;
  if ( v9 < 0 )
  {
    v12 = 3846;
    goto LABEL_26;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 96LL))(v35, 0);
  LODWORD(v49) = v9;
  if ( v9 < 0 )
  {
    v12 = 3849;
    goto LABEL_26;
  }
  v9 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64))v7->lpVtbl->put_Triggers)(v7, v31);
  LODWORD(v49) = v9;
  if ( v9 < 0 )
  {
    v12 = 3852;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v9,
      v30);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_22;
  }
  v37 = 0;
  v13 = v33;
  lpVtbl = v33->lpVtbl;
  VariantInit(&pvarg);
  v15 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v43);
  v17 = *(_OWORD *)&v43.vt;
  v18 = v43.pRecInfo;
  v19 = SysAllocString(a3);
  if ( !v19 && a3 )
    _com_issue_error(-2147024882);
  LOWORD(v41) = 8;
  *((_QWORD *)&v41 + 1) = v19;
  v20 = v41;
  v21 = v42;
  v22 = _bstr_t::_bstr_t((_bstr_t *)&v36, L"Run a Cmd as the User");
  if ( *(_QWORD *)v22 )
    v23 = **(_QWORD **)v22;
  else
    v23 = 0;
  v44 = v15;
  v45 = pRecInfo;
  v46 = v17;
  v47 = v18;
  *(_OWORD *)&v40.vt = v20;
  v40.pRecInfo = v21;
  LODWORD(v49) = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct ITaskDefinition *, __int64))lpVtbl->RegisterTaskDefinition)(
                   v13,
                   v23,
                   v7,
                   6);
  _bstr_t::~_bstr_t((_bstr_t *)&v36);
  _variant_t::~_variant_t((_variant_t *)&v41);
  _variant_t::~_variant_t((_variant_t *)&v43);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v24 = (unsigned int)v49;
  if ( (int)v49 >= 0 )
  {
    v38 = 0;
    v25 = v37;
    v26 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v37 + 104LL);
    VariantInit(&pvarg);
    v40 = pvarg;
    LODWORD(v49) = v26(v25, &v40, 2);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    v24 = (unsigned int)v49;
    if ( (int)v49 >= 0 )
    {
      dwProcessId = 0;
      LODWORD(v49) = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v38 + 112LL))(v38, &dwProcessId);
      if ( (int)v49 >= 0 )
      {
        v27 = (char *)OpenProcess(0x101000u, 0, dwProcessId);
        if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          WaitForSingleObject(v27, 0xFFFFFFFF);
          CloseHandle(v27);
        }
      }
      LODWORD(v49) = 0;
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v37 + 128LL))(v37, &v49);
      v24 = (unsigned int)v49;
      if ( (_DWORD)v49 != 267011 )
      {
        DeleteTask = v13->lpVtbl->DeleteTask;
        v29 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v36, L"Run a Cmd as the User");
        if ( v29 )
          v29 = (_QWORD *)*v29;
        ((void (__fastcall *)(struct ITaskFolder *, _QWORD *, _QWORD))DeleteTask)(v13, v29, 0);
        _bstr_t::~_bstr_t((_bstr_t *)&v36);
        v24 = (unsigned int)v49;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF21,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v49,
        0);
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF18,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v49,
      (int)&v40);
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v13 )
    ((void (__fastcall *)(struct ITaskFolder *))v13->lpVtbl->Release)(v13);
  if ( v7 )
    ((void (__fastcall *)(struct ITaskDefinition *))v7->lpVtbl->Release)(v7);
  return v24;
}

```

## disassembly

```asm
0x140030a54  mov     rax, rsp
0x140030a57  mov     [rax+10h], rbx
0x140030a5b  mov     [rax+18h], rsi
0x140030a5f  mov     [rax+8], rcx
0x140030a63  push    rbp
0x140030a64  push    rdi
0x140030a65  push    r14
0x140030a67  lea     rbp, [rax-0B8h]
0x140030a6e  sub     rsp, 1A0h
0x140030a75  movaps  xmmword ptr [rax-28h], xmm6
0x140030a79  movaps  xmmword ptr [rax-38h], xmm7
0x140030a7d  movaps  xmmword ptr [rax-48h], xmm8
0x140030a82  movaps  xmmword ptr [rax-58h], xmm9
0x140030a87  movaps  xmmword ptr [rax-68h], xmm10
0x140030a8c  movaps  xmmword ptr [rax-78h], xmm11
0x140030a91  mov     rsi, r8
0x140030a94  mov     [rsp+1B0h+var_138], 0
0x140030a9d  mov     [rsp+1B0h+var_150], 0
0x140030aa6  mov     [rsp+1B0h+var_190], r8; int
0x140030aab  mov     r9, rdx; unsigned __int16 *
0x140030aae  lea     r8, [rsp+1B0h+var_150]; struct ITaskFolder **
0x140030ab3  lea     rdx, [rsp+1B0h+var_138]; struct ITaskDefinition **
0x140030ab8  call    ?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z; CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)
0x140030abd  mov     ebx, eax
0x140030abf  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030ac5  test    eax, eax
0x140030ac7  jns     short loc_140030B17
0x140030ac9  mov     rcx, [rbp+0B8h]; this
0x140030ad0  mov     r9d, eax; char *
0x140030ad3  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030ada  mov     edx, 0EF6h; void *
0x140030adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030ae4  mov     rcx, [rsp+1B0h+var_150]
0x140030ae9  test    rcx, rcx
0x140030aec  jz      short loc_140030AFA
0x140030aee  mov     rax, [rcx]
0x140030af1  mov     rax, [rax+10h]
0x140030af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030afa  mov     rcx, [rsp+1B0h+var_138]
0x140030aff  test    rcx, rcx
0x140030b02  jz      short loc_140030B10
0x140030b04  mov     rax, [rcx]
0x140030b07  mov     rax, [rax+10h]
0x140030b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b10  mov     eax, ebx
0x140030b12  jmp     loc_14003107D
0x140030b17  mov     [rsp+1B0h+var_160], 0
0x140030b20  mov     rbx, [rsp+1B0h+var_138]
0x140030b25  mov     rax, [rbx]
0x140030b28  lea     rdx, [rsp+1B0h+var_160]
0x140030b2d  mov     rcx, rbx
0x140030b30  mov     rax, [rax+48h]
0x140030b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b39  mov     edi, eax
0x140030b3b  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030b41  test    eax, eax
0x140030b43  jns     short loc_140030BA7
0x140030b45  mov     rcx, [rbp+0B8h]; this
0x140030b4c  mov     r9d, eax; char *
0x140030b4f  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030b56  mov     edx, 0EFAh; void *
0x140030b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030b60  mov     rcx, [rsp+1B0h+var_160]
0x140030b65  test    rcx, rcx
0x140030b68  jz      short loc_140030B76
0x140030b6a  mov     rax, [rcx]
0x140030b6d  mov     rax, [rax+10h]
0x140030b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b76  mov     rcx, [rsp+1B0h+var_150]
0x140030b7b  test    rcx, rcx
0x140030b7e  jz      short loc_140030B8C
0x140030b80  mov     rax, [rcx]
0x140030b83  mov     rax, [rax+10h]
0x140030b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b8c  test    rbx, rbx
0x140030b8f  jz      short loc_140030BA0
0x140030b91  mov     rax, [rbx]
0x140030b94  mov     rcx, rbx
0x140030b97  mov     rax, [rax+10h]
0x140030b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ba0  mov     eax, edi
0x140030ba2  jmp     loc_14003107D
0x140030ba7  mov     [rsp+1B0h+var_158], 0
0x140030bb0  mov     rcx, [rsp+1B0h+var_160]
0x140030bb5  mov     rax, [rcx]
0x140030bb8  lea     r8, [rsp+1B0h+var_158]
0x140030bbd  mov     edx, 9
0x140030bc2  mov     rax, [rax+50h]
0x140030bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030bcb  mov     edi, eax
0x140030bcd  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030bd3  test    eax, eax
0x140030bd5  jns     short loc_140030C11
0x140030bd7  mov     rcx, [rbp+0B8h]; this
0x140030bde  mov     r9d, eax; char *
0x140030be1  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030be8  mov     edx, 0EFEh; void *
0x140030bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030bf2  mov     rcx, [rsp+1B0h+var_158]
0x140030bf7  test    rcx, rcx
0x140030bfa  jz      loc_140030B60
0x140030c00  mov     rax, [rcx]
0x140030c03  mov     rax, [rax+10h]
0x140030c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c0c  jmp     loc_140030B60
0x140030c11  mov     [rsp+1B0h+var_148], 0
0x140030c1a  mov     rcx, [rsp+1B0h+var_158]
0x140030c1f  mov     rax, [rcx]
0x140030c22  lea     r8, [rsp+1B0h+var_148]
0x140030c27  lea     rdx, IID_ILogonTrigger
0x140030c2e  mov     rax, [rax]
0x140030c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c36  mov     edi, eax
0x140030c38  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030c3e  test    eax, eax
0x140030c40  jns     short loc_140030C78
0x140030c42  mov     rcx, [rbp+0B8h]; this
0x140030c49  mov     r9d, eax; char *
0x140030c4c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030c53  mov     edx, 0F02h; void *
0x140030c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030c5d  mov     rcx, [rsp+1B0h+var_148]
0x140030c62  test    rcx, rcx
0x140030c65  jz      short loc_140030BF2
0x140030c67  mov     rax, [rcx]
0x140030c6a  mov     rax, [rax+10h]
0x140030c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c73  jmp     loc_140030BF2
0x140030c78  mov     [rsp+1B0h+var_140], 0
0x140030c81  mov     rcx, [rsp+1B0h+var_148]
0x140030c86  mov     rax, [rcx]
0x140030c89  lea     rdx, [rsp+1B0h+var_140]
0x140030c8e  mov     rax, [rax+50h]
0x140030c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c97  mov     edi, eax
0x140030c99  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030c9f  test    eax, eax
0x140030ca1  jns     short loc_140030CD6
0x140030ca3  mov     edx, 0F06h; void *
0x140030ca8  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030caf  mov     r9d, edi; char *
0x140030cb2  mov     rcx, [rbp+0B8h]; this
0x140030cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030cbe  mov     rcx, [rsp+1B0h+var_140]
0x140030cc3  test    rcx, rcx
0x140030cc6  jz      short loc_140030C5D
0x140030cc8  mov     rax, [rcx]
0x140030ccb  mov     rax, [rax+10h]
0x140030ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030cd4  jmp     short loc_140030C5D
0x140030cd6  mov     rcx, [rsp+1B0h+var_140]
0x140030cdb  mov     rax, [rcx]
0x140030cde  xor     edx, edx
0x140030ce0  mov     rax, [rax+60h]
0x140030ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ce9  mov     edi, eax
0x140030ceb  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030cf1  test    eax, eax
0x140030cf3  jns     short loc_140030CFC
0x140030cf5  mov     edx, 0F09h
0x140030cfa  jmp     short loc_140030CA8
0x140030cfc  mov     rax, [rbx]
0x140030cff  mov     rdx, [rsp+1B0h+var_160]
0x140030d04  mov     rcx, rbx
0x140030d07  mov     rax, [rax+50h]
0x140030d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030d10  mov     edi, eax
0x140030d12  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030d18  test    eax, eax
0x140030d1a  jns     short loc_140030D23
0x140030d1c  mov     edx, 0F0Ch
0x140030d21  jmp     short loc_140030CA8
0x140030d23  mov     [rbp+0B0h+var_130], 0
0x140030d2b  mov     rdi, [rsp+1B0h+var_150]
0x140030d30  mov     r14, [rdi]
0x140030d33  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x140030d37  call    cs:__imp_VariantInit
0x140030d3d  movups  xmm8, xmmword ptr [rbp+0B0h+pvarg]
0x140030d42  movsd   xmm9, qword ptr [rbp+0B0h+pvarg+10h]
0x140030d48  lea     rcx, [rbp+0B0h+var_C8]; pvarg
0x140030d4c  call    cs:__imp_VariantInit
0x140030d52  movups  xmm10, xmmword ptr [rbp+0B0h+var_C8]
0x140030d57  movsd   xmm11, qword ptr [rbp+0B0h+var_C8+10h]
0x140030d5d  mov     rcx, rsi; psz
0x140030d60  call    cs:__imp_SysAllocString
0x140030d66  test    rax, rax
0x140030d69  jnz     short loc_140030D74
0x140030d6b  test    rsi, rsi
0x140030d6e  jnz     loc_1400310B3
0x140030d74  mov     ecx, 8
0x140030d79  mov     word ptr [rbp+0B0h+var_E0], cx
0x140030d7d  mov     qword ptr [rbp+0B0h+var_E0+8], rax
0x140030d81  movups  xmm6, [rbp+0B0h+var_E0]
0x140030d85  movsd   xmm7, [rbp+0B0h+var_D0]
0x140030d8a  lea     rdx, aRunACmdAsTheUs; "Run a Cmd as the User"
0x140030d91  lea     rcx, [rsp+1B0h+var_138]; this
0x140030d96  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140030d9b  mov     rcx, [rax]
0x140030d9e  test    rcx, rcx
0x140030da1  jz      short loc_140030DA8
0x140030da3  mov     rdx, [rcx]
0x140030da6  jmp     short loc_140030DAA
0x140030da8  xor     edx, edx
0x140030daa  movaps  [rbp+0B0h+var_B0], xmm8
0x140030daf  movsd   [rbp+0B0h+var_A0], xmm9
0x140030db5  movaps  [rbp+0B0h+var_90], xmm10
0x140030dba  movsd   [rbp+0B0h+var_80], xmm11
0x140030dc0  movaps  xmmword ptr [rbp+0B0h+var_100], xmm6
0x140030dc4  movsd   [rbp+0B0h+var_F0], xmm7
0x140030dc9  lea     rax, [rbp+0B0h+var_130]
0x140030dcd  mov     [rsp+1B0h+var_170], rax
0x140030dd2  lea     rax, [rbp+0B0h+var_B0]
0x140030dd6  mov     [rsp+1B0h+var_178], rax
0x140030ddb  mov     dword ptr [rsp+1B0h+var_180], 3
0x140030de3  lea     rax, [rbp+0B0h+var_90]
0x140030de7  mov     qword ptr [rsp+1B0h+var_188], rax
0x140030dec  lea     rax, [rbp+0B0h+var_100]
0x140030df0  mov     [rsp+1B0h+var_190], rax; int
0x140030df5  mov     r9d, 6
0x140030dfb  mov     r8, rbx
0x140030dfe  mov     rcx, rdi
0x140030e01  mov     rax, [r14+88h]
0x140030e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e0d  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030e13  lea     rcx, [rsp+1B0h+var_138]; this
0x140030e18  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140030e1d  lea     rcx, [rbp+0B0h+var_E0]; this
0x140030e21  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140030e26  lea     rcx, [rbp+0B0h+var_C8]; this
0x140030e2a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140030e2f  lea     rcx, [rbp+0B0h+pvarg]; this
0x140030e33  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140030e38  mov     esi, dword ptr [rbp+0B0h+arg_0]
0x140030e3e  test    esi, esi
0x140030e40  jns     short loc_140030E62
0x140030e42  mov     rcx, [rbp+0B8h]; this
0x140030e49  mov     r9d, esi; char *
0x140030e4c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030e53  mov     edx, 0F18h; void *
0x140030e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030e5d  jmp     loc_140030FE6
0x140030e62  mov     [rbp+0B0h+var_128], 0
0x140030e6a  mov     r14, [rbp+0B0h+var_130]
0x140030e6e  mov     rax, [r14]
0x140030e71  mov     rsi, [rax+68h]
0x140030e75  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x140030e79  call    cs:__imp_VariantInit
0x140030e7f  movups  xmm0, xmmword ptr [rbp+0B0h+pvarg]
0x140030e83  movaps  xmmword ptr [rbp+0B0h+var_100], xmm0
0x140030e87  movsd   xmm1, qword ptr [rbp+0B0h+pvarg+10h]
0x140030e8c  movsd   [rbp+0B0h+var_F0], xmm1
0x140030e91  lea     rax, [rbp+0B0h+var_128]
0x140030e95  mov     qword ptr [rsp+1B0h+var_188], rax
0x140030e9a  mov     [rsp+1B0h+var_190], 0; int
0x140030ea3  xor     r9d, r9d
0x140030ea6  lea     r8d, [r9+2]
0x140030eaa  lea     rdx, [rbp+0B0h+var_100]
0x140030eae  mov     rcx, r14
0x140030eb1  mov     rax, rsi
0x140030eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030eb9  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030ebf  lea     rcx, [rbp+0B0h+pvarg]; this
0x140030ec3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140030ec8  mov     esi, dword ptr [rbp+0B0h+arg_0]
0x140030ece  test    esi, esi
0x140030ed0  jns     short loc_140030EF2
0x140030ed2  mov     rcx, [rbp+0B8h]; this
0x140030ed9  mov     r9d, esi; char *
0x140030edc  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030ee3  mov     edx, 0F21h; void *
0x140030ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030eed  jmp     loc_140030FD1
0x140030ef2  mov     [rbp+0B0h+dwProcessId], 0
0x140030efc  mov     rcx, [rbp+0B0h+var_128]
0x140030f00  mov     rax, [rcx]
0x140030f03  lea     rdx, [rbp+0B0h+dwProcessId]
0x140030f0a  mov     rax, [rax+70h]
0x140030f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030f13  mov     dword ptr [rbp+0B0h+arg_0], eax
0x140030f19  test    eax, eax
0x140030f1b  js      short loc_140030F5E
0x140030f1d  mov     r8d, [rbp+0B0h+dwProcessId]; dwProcessId
0x140030f24  xor     edx, edx; bInheritHandle
0x140030f26  mov     ecx, 101000h; dwDesiredAccess
0x140030f2b  call    cs:__imp_OpenProcess
0x140030f31  mov     rsi, rax
0x140030f34  dec     rax
0x140030f37  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140030f3b  ja      short loc_140030F4A
0x140030f3d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140030f40  mov     rcx, rsi; hHandle
0x140030f43  call    cs:__imp_WaitForSingleObject
0x140030f49  nop
0x140030f4a  lea     rax, [rsi-1]
0x140030f4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140030f52  ja      short loc_140030F5E
0x140030f54  mov     rcx, rsi; hObject
0x140030f57  call    cs:__imp_CloseHandle
0x140030f5d  nop
0x140030f5e  mov     dword ptr [rbp+0B0h+arg_0], 0
  ... truncated ...
```
