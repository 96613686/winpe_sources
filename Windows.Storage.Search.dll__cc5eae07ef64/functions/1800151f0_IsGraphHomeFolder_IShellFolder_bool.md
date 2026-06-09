# IsGraphHomeFolder(IShellFolder *,bool *)

- ea: `0x1800151f0`
- end: `0x18001537e`
- name: `?IsGraphHomeFolder@@YAJPEAUIShellFolder@@PEA_N@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct IShellFolder *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014b10`
- `0x180014e20`

## callees

- `0x180014498`
- `0x1800151f0`
- `0x180022cf4`
- `0x180045428`
- `0x180063a68`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHGetIDListFromObject` at `0x18001521f`
- `Windows.Storage!SHGetIDListFromObject` at `0x18001521f`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180015297`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180015297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001526f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001526f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015369`

## pseudocode

```c
__int64 __fastcall IsGraphHomeFolder(IUnknown *a1, bool *a2)
{
  HRESULT v3; // ebx
  void *v4; // rcx
  void *v5; // rcx
  __int64 *v7; // rax
  HRESULT v8; // eax
  __int64 *v9; // rax
  const struct _GUID *v10; // r8
  __int64 v11; // rdx
  void *v12; // rcx
  int v13; // [rsp+20h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-18h]
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-10h] BYREF
  char v17; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v19; // [rsp+78h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF

  *a2 = 0;
  pv = 0;
  p_pv = &pv;
  ppidl = 0;
  v17 = 1;
  v3 = SHGetIDListFromObject(a1, &ppidl);
  if ( v17 )
  {
    v4 = *p_pv;
    *p_pv = ppidl;
    if ( v4 )
      CoTaskMemFree(v4);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
      (const char *)(unsigned int)v3,
      v13);
LABEL_6:
    v5 = pv;
    pv = 0;
    if ( v5 )
      CoTaskMemFree(v5);
    return (unsigned int)v3;
  }
  v21 = 0;
  v7 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v21);
  v8 = SHCreateItemFromIDList((LPCITEMIDLIST)pv, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)v7);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
      (const char *)(unsigned int)v8,
      v13);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    goto LABEL_6;
  }
  v14 = 0;
  v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v14);
  v3 = SHSimpleItemFromAttributes(L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}", 0x10u, v10, (void **)v9);
  if ( v3 < 0 )
  {
    v11 = 26;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
      (const char *)(unsigned int)v3,
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    goto LABEL_11;
  }
  v19 = -1;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v21 + 56LL))(v21, v14, 0x10000000, &v19);
  if ( v3 < 0 )
  {
    v11 = 29;
    goto LABEL_14;
  }
  *a2 = v19 == 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  v12 = pv;
  pv = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x1800151f0  mov     [rsp-18h+arg_0], rbx
0x1800151f5  push    rbp
0x1800151f6  push    rsi
0x1800151f7  push    rdi
0x1800151f8  mov     rbp, rsp
0x1800151fb  sub     rsp, 50h
0x1800151ff  mov     rdi, rdx
0x180015202  xor     esi, esi
0x180015204  mov     [rdx], sil
0x180015207  mov     [rbp+pv], rsi
0x18001520b  lea     rax, [rbp+pv]
0x18001520f  mov     [rbp+var_18], rax
0x180015213  mov     [rbp+ppidl], rsi
0x180015217  mov     [rbp+var_8], 1
0x18001521b  lea     rdx, [rbp+ppidl]; ppidl
0x18001521f  call    cs:__imp_SHGetIDListFromObject
0x180015225  mov     ebx, eax
0x180015227  cmp     [rbp+var_8], sil
0x18001522b  jz      short loc_180015246
0x18001522d  mov     r8, [rbp+var_18]
0x180015231  mov     rcx, [r8]; pv
0x180015234  mov     rdx, [rbp+ppidl]
0x180015238  mov     [r8], rdx
0x18001523b  test    rcx, rcx
0x18001523e  jz      short loc_180015246
0x180015240  call    cs:__imp_CoTaskMemFree
0x180015246  test    ebx, ebx
0x180015248  jns     short loc_18001527C
0x18001524a  mov     rcx, [rbp+18h]; this
0x18001524e  mov     r9d, ebx; char *
0x180015251  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180015258  mov     edx, 14h; void *
0x18001525d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015262  mov     rcx, [rbp+pv]; pv
0x180015266  mov     [rbp+pv], rsi
0x18001526a  test    rcx, rcx
0x18001526d  jz      short loc_180015275
0x18001526f  call    cs:__imp_CoTaskMemFree
0x180015275  mov     eax, ebx
0x180015277  jmp     loc_180015371
0x18001527c  mov     [rbp+arg_18], rsi
0x180015280  lea     rcx, [rbp+arg_18]
0x180015284  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x180015289  mov     r8, rax; ppv
0x18001528c  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180015293  mov     rcx, [rbp+pv]; pidl
0x180015297  call    cs:__imp_SHCreateItemFromIDList
0x18001529d  mov     ebx, eax
0x18001529f  test    eax, eax
0x1800152a1  jns     short loc_1800152C6
0x1800152a3  mov     rcx, [rbp+18h]; this
0x1800152a7  mov     r9d, eax; char *
0x1800152aa  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800152b1  mov     edx, 17h; void *
0x1800152b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152bb  lea     rcx, [rbp+arg_18]
0x1800152bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800152c4  jmp     short loc_180015262
0x1800152c6  mov     [rbp+var_20], rsi
0x1800152ca  lea     rcx, [rbp+var_20]
0x1800152ce  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x1800152d3  mov     r9, rax; void **
0x1800152d6  mov     edx, 10h; unsigned int
0x1800152db  lea     rcx, aShellF874310eB; "shell:::{f874310e-b6b7-47dc-bc84-b9e6b3"...
0x1800152e2  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x1800152e7  mov     ebx, eax
0x1800152e9  test    eax, eax
0x1800152eb  jns     short loc_180015310
0x1800152ed  mov     edx, 1Ah; void *
0x1800152f2  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800152f9  mov     r9d, ebx; char *
0x1800152fc  mov     rcx, [rbp+18h]; this
0x180015300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015305  lea     rcx, [rbp+var_20]
0x180015309  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001530e  jmp     short loc_1800152BB
0x180015310  mov     [rbp+arg_8], 0FFFFFFFFh
0x180015317  mov     rcx, [rbp+arg_18]
0x18001531b  mov     rax, [rcx]
0x18001531e  lea     r9, [rbp+arg_8]
0x180015322  mov     r8d, 10000000h
0x180015328  mov     rdx, [rbp+var_20]
0x18001532c  mov     rax, [rax+38h]
0x180015330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015335  mov     ebx, eax
0x180015337  test    eax, eax
0x180015339  jns     short loc_180015342
0x18001533b  mov     edx, 1Dh
0x180015340  jmp     short loc_1800152F2
0x180015342  cmp     [rbp+arg_8], esi
0x180015345  setz    al
0x180015348  mov     [rdi], al
0x18001534a  lea     rcx, [rbp+var_20]
0x18001534e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015353  lea     rcx, [rbp+arg_18]
0x180015357  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001535c  mov     rcx, [rbp+pv]; pv
0x180015360  mov     [rbp+pv], rsi
0x180015364  test    rcx, rcx
0x180015367  jz      short loc_18001536F
0x180015369  call    cs:__imp_CoTaskMemFree
0x18001536f  xor     eax, eax
0x180015371  mov     rbx, [rsp+50h+arg_0]
0x180015376  add     rsp, 50h
0x18001537a  pop     rdi
0x18001537b  pop     rsi
0x18001537c  pop     rbp
0x18001537d  retn
```
