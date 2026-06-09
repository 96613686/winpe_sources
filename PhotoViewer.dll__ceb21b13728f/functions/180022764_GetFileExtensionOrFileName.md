# GetFileExtensionOrFileName

- ea: `0x180022764`
- end: `0x18002291c`
- name: `GetFileExtensionOrFileName`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180039ec8`

## callees

- `0x18000cb74`
- `0x180022764`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800227de`
- `ole32!CoTaskMemFree` at `0x18002281e`
- `ole32!CoTaskMemFree` at `0x1800227de`
- `ole32!CoTaskMemFree` at `0x18002281e`
- `SHELL32!SHCreateItemFromIDList` at `0x18002280b`
- `SHELL32!SHCreateItemFromIDList` at `0x18002280b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002286e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800228e1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002286e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800228e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GetFileExtensionOrFileName(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // ebx
  int v5; // edx
  void *v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // edx
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  __int64 v11; // [rsp+58h] [rbp+28h] BYREF
  void *ppv; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  ppv = 0;
  v11 = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)a1 + 24LL))(
         a1,
         0,
         &BHID_SFUIObject,
         &GUID_000214f9_0000_0000_c000_000000000046,
         &v11) < 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))a1)(
           a1,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           &ppv);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  else
  {
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v11 + 32LL))(v11, &pv);
    if ( v4 < 0 )
    {
      CoTaskMemFree(pv);
      pv = 0;
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v11);
      goto LABEL_11;
    }
    v6 = pv;
    if ( pv )
    {
      v4 = SHCreateItemFromIDList((LPCITEMIDLIST)pv, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v6 = pv;
    }
    else
    {
      v4 = -2147467259;
    }
    CoTaskMemFree(v6);
    pv = 0;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v11);
  }
  if ( v4 < 0 )
  {
LABEL_11:
    Base::Throw((Base *)(unsigned int)v4, v5);
    __debugbreak();
  }
  v7 = 0;
  v13 = 0;
  if ( ppv )
  {
    (**(void (__fastcall ***)(void *, GUID *, __int64 *))ppv)(ppv, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v13);
    v7 = v13;
  }
  if ( !v7
    || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, _QWORD *))(*(_QWORD *)v7 + 136LL))(v7, &PKEY_ItemType, a2) < 0 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD *))(*(_QWORD *)ppv + 40LL))(ppv, 2147581953LL, a2);
    if ( v8 < 0 )
      Base::Throw((Base *)(unsigned int)v8, v9);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180022764  push    rbp
0x180022766  push    rbx
0x180022767  push    rdi
0x180022768  mov     rbp, rsp
0x18002276b  sub     rsp, 30h
0x18002276f  mov     rdi, rdx
0x180022772  mov     rbx, rcx
0x180022775  mov     qword ptr [rdx], 0
0x18002277c  mov     [rbp+ppv], 0
0x180022784  mov     [rbp+arg_8], 0
0x18002278c  mov     rax, [rcx]
0x18002278f  lea     rcx, [rbp+arg_8]
0x180022793  mov     [rsp+30h+var_10], rcx
0x180022798  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x18002279f  lea     r8, BHID_SFUIObject
0x1800227a6  xor     edx, edx
0x1800227a8  mov     rcx, rbx
0x1800227ab  mov     rax, [rax+18h]
0x1800227af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227b4  test    eax, eax
0x1800227b6  js      short loc_180022837
0x1800227b8  mov     [rbp+pv], 0
0x1800227c0  mov     rcx, [rbp+arg_8]
0x1800227c4  mov     rax, [rcx]
0x1800227c7  lea     rdx, [rbp+pv]
0x1800227cb  mov     rax, [rax+20h]
0x1800227cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d4  mov     ebx, eax
0x1800227d6  test    eax, eax
0x1800227d8  jns     short loc_1800227F7
0x1800227da  mov     rcx, [rbp+pv]; pv
0x1800227de  call    cs:__imp_CoTaskMemFree
0x1800227e4  mov     [rbp+pv], 0
0x1800227ec  lea     rcx, [rbp+arg_8]
0x1800227f0  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800227f5  jmp     short loc_18002286C
0x1800227f7  mov     rcx, [rbp+pv]; pv
0x1800227fb  test    rcx, rcx
0x1800227fe  jz      short loc_180022819
0x180022800  lea     r8, [rbp+ppv]; ppv
0x180022804  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002280b  call    cs:__imp_SHCreateItemFromIDList
0x180022811  mov     ebx, eax
0x180022813  mov     rcx, [rbp+pv]
0x180022817  jmp     short loc_18002281E
0x180022819  mov     ebx, 80004005h
0x18002281e  call    cs:__imp_CoTaskMemFree
0x180022824  mov     [rbp+pv], 0
0x18002282c  lea     rcx, [rbp+arg_8]
0x180022830  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180022835  jmp     short loc_180022868
0x180022837  mov     rax, [rbx]
0x18002283a  lea     r8, [rbp+ppv]
0x18002283e  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180022845  mov     rcx, rbx
0x180022848  mov     rax, [rax]
0x18002284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022850  mov     ebx, eax
0x180022852  mov     rcx, [rbp+arg_8]
0x180022856  test    rcx, rcx
0x180022859  jz      short loc_180022868
0x18002285b  mov     rax, [rcx]
0x18002285e  mov     rax, [rax+10h]
0x180022862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022867  nop
0x180022868  test    ebx, ebx
0x18002286a  jns     short loc_180022875
0x18002286c  mov     ecx, ebx
0x18002286e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180022874  int     3; Trap to Debugger
0x180022875  mov     r9, [rbp+ppv]
0x180022879  xor     ecx, ecx
0x18002287b  mov     [rbp+arg_18], rcx
0x18002287f  test    r9, r9
0x180022882  jz      short loc_1800228A1
0x180022884  mov     rax, [r9]
0x180022887  lea     r8, [rbp+arg_18]
0x18002288b  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180022892  mov     rcx, r9
0x180022895  mov     rax, [rax]
0x180022898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002289d  mov     rcx, [rbp+arg_18]
0x1800228a1  test    rcx, rcx
0x1800228a4  jz      short loc_1800228C3
0x1800228a6  mov     rax, [rcx]
0x1800228a9  mov     r8, rdi
0x1800228ac  lea     rdx, PKEY_ItemType
0x1800228b3  mov     rax, [rax+88h]
0x1800228ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228bf  test    eax, eax
0x1800228c1  jns     short loc_1800228E8
0x1800228c3  mov     rcx, [rbp+ppv]
0x1800228c7  mov     rax, [rcx]
0x1800228ca  mov     r8, rdi
0x1800228cd  mov     edx, 80018001h
0x1800228d2  mov     rax, [rax+28h]
0x1800228d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228db  test    eax, eax
0x1800228dd  jns     short loc_1800228E8
0x1800228df  mov     ecx, eax
0x1800228e1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800228e7  nop
0x1800228e8  mov     rcx, [rbp+arg_18]
0x1800228ec  test    rcx, rcx
0x1800228ef  jz      short loc_1800228FE
0x1800228f1  mov     rax, [rcx]
0x1800228f4  mov     rax, [rax+10h]
0x1800228f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228fd  nop
0x1800228fe  mov     rcx, [rbp+ppv]
0x180022902  test    rcx, rcx
0x180022905  jz      short loc_180022914
0x180022907  mov     rax, [rcx]
0x18002290a  mov     rax, [rax+10h]
0x18002290e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022913  nop
0x180022914  add     rsp, 30h
0x180022918  pop     rdi
0x180022919  pop     rbx
0x18002291a  pop     rbp
0x18002291b  retn
```
