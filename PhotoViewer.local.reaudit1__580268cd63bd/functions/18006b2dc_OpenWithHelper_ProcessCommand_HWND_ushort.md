# OpenWithHelper::ProcessCommand(HWND__ *,ushort)

- ea: `0x18006b2dc`
- end: `0x18006b467`
- name: `?ProcessCommand@OpenWithHelper@@QEAA_NPEAUHWND__@@G@Z`
- size: `395`
- prototype: `bool(OpenWithHelper *__hidden this, HWND, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800080fc`
- `0x18004c870`

## callees

- `0x18000cb74`
- `0x18006b1d8`
- `0x18006b2dc`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18006b3b7`
- `ole32!CoTaskMemFree` at `0x18006b3b7`
- `SHELL32!SHGetItemFromDataObject` at `0x18006b343`
- `SHELL32!SHGetItemFromDataObject` at `0x18006b343`
- `SHELL32!SHOpenWithDialog` at `0x18006b3a4`
- `SHELL32!SHOpenWithDialog` at `0x18006b3a4`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006b419`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18006b419`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b31d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b34f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b37e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b402`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b31d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b34f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b37e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006b402`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall OpenWithHelper::ProcessCommand(OpenWithHelper *this, HWND a2, unsigned __int16 a3)
{
  int v5; // ebx
  int v6; // eax
  int v7; // edx
  HRESULT v8; // eax
  int v9; // edx
  int v10; // eax
  int v11; // edx
  bool v12; // bl
  int v14; // eax
  int v15; // edx
  unsigned __int64 v16; // rbx
  __int64 v17; // rbx
  IDataObject *v18; // rdi
  OPENASINFO poainfo; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF
  void *ppv; // [rsp+88h] [rbp+20h] BYREF

  v5 = a3;
  if ( a3 == *((_DWORD *)this + 36) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 136LL))(*((_QWORD *)this + 20));
    if ( v6 < 0 )
      Base::Throw((Base *)(unsigned int)v6, v7);
    ppv = 0;
    v8 = SHGetItemFromDataObject(
           *((IDataObject **)this + 19),
           DOGIF_DEFAULT,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           &ppv);
    if ( v8 < 0 )
      Base::Throw((Base *)(unsigned int)v8, v9);
    pv = 0;
    v10 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 2147647488LL, &pv);
    if ( v10 < 0 )
      Base::Throw((Base *)(unsigned int)v10, v11);
    poainfo.pcszClass = 0;
    *(_QWORD *)&poainfo.oaifInFlags = 36;
    poainfo.pcszFile = (LPCWSTR)pv;
    v12 = SHOpenWithDialog(a2, &poainfo) >= 0;
    CoTaskMemFree(pv);
    pv = 0;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
    return v12;
  }
  else if ( (unsigned int)a3 < *((_DWORD *)this + 34) || (unsigned int)a3 > *((_DWORD *)this + 35) )
  {
    return 0;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 136LL))(*((_QWORD *)this + 20));
    if ( v14 < 0 )
      Base::Throw((Base *)(unsigned int)v14, v15);
    v16 = (unsigned int)(v5 - *((_DWORD *)this + 34));
    if ( v16 >= *((_QWORD *)this + 14) )
      ATL::BaseAtlThrow(-2147024809);
    _mm_lfence();
    v17 = *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v16);
    v18 = (IDataObject *)*((_QWORD *)this + 19);
    LogSqmOpenData(*(LPCWSTR *)(v17 + 32), v18);
    (*(void (__fastcall **)(_QWORD, IDataObject *))(**(_QWORD **)(v17 + 16) + 64LL))(*(_QWORD *)(v17 + 16), v18);
    return 1;
  }
}

```

## disassembly

```asm
0x18006b2dc  mov     [rsp+arg_8], rbx
0x18006b2e1  push    rsi
0x18006b2e2  push    rdi
0x18006b2e3  push    r14
0x18006b2e5  sub     rsp, 50h
0x18006b2e9  mov     r14, rdx
0x18006b2ec  mov     rsi, rcx
0x18006b2ef  movzx   ebx, r8w
0x18006b2f3  cmp     ebx, [rcx+90h]
0x18006b2f9  jnz     loc_18006B3D6
0x18006b2ff  mov     rcx, [rcx+0A0h]
0x18006b306  mov     rax, [rcx]
0x18006b309  mov     rax, [rax+88h]
0x18006b310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b315  xor     edi, edi
0x18006b317  test    eax, eax
0x18006b319  jns     short loc_18006B323
0x18006b31b  mov     ecx, eax
0x18006b31d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006b323  mov     [rsp+68h+ppv], rdi
0x18006b32b  lea     r9, [rsp+68h+ppv]; ppv
0x18006b333  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18006b33a  xor     edx, edx; dwFlags
0x18006b33c  mov     rcx, [rsi+98h]; pdtobj
0x18006b343  call    cs:__imp_SHGetItemFromDataObject
0x18006b349  test    eax, eax
0x18006b34b  jns     short loc_18006B355
0x18006b34d  mov     ecx, eax
0x18006b34f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006b355  mov     [rsp+68h+pv], rdi
0x18006b35a  mov     rcx, [rsp+68h+ppv]
0x18006b362  mov     rax, [rcx]
0x18006b365  lea     r8, [rsp+68h+pv]
0x18006b36a  mov     edx, 80028000h
0x18006b36f  mov     rax, [rax+28h]
0x18006b373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b378  test    eax, eax
0x18006b37a  jns     short loc_18006B384
0x18006b37c  mov     ecx, eax
0x18006b37e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006b384  mov     [rsp+68h+poainfo.pcszClass], rdi
0x18006b389  mov     qword ptr [rsp+68h+poainfo.oaifInFlags], 24h ; '$'
0x18006b392  mov     rax, [rsp+68h+pv]
0x18006b397  mov     [rsp+68h+poainfo.pcszFile], rax
0x18006b39c  lea     rdx, [rsp+68h+poainfo]; poainfo
0x18006b3a1  mov     rcx, r14; hwndParent
0x18006b3a4  call    cs:__imp_SHOpenWithDialog
0x18006b3aa  mov     ebx, eax
0x18006b3ac  shr     ebx, 1Fh
0x18006b3af  xor     bl, 1
0x18006b3b2  mov     rcx, [rsp+68h+pv]; pv
0x18006b3b7  call    cs:__imp_CoTaskMemFree
0x18006b3bd  mov     [rsp+68h+pv], rdi
0x18006b3c2  lea     rcx, [rsp+68h+ppv]
0x18006b3ca  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006b3cf  mov     al, bl
0x18006b3d1  jmp     loc_18006B459
0x18006b3d6  cmp     ebx, [rcx+88h]
0x18006b3dc  jb      short loc_18006B455
0x18006b3de  cmp     ebx, [rcx+8Ch]
0x18006b3e4  ja      short loc_18006B455
0x18006b3e6  mov     rcx, [rcx+0A0h]
0x18006b3ed  mov     rax, [rcx]
0x18006b3f0  mov     rax, [rax+88h]
0x18006b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3fc  test    eax, eax
0x18006b3fe  jns     short loc_18006B408
0x18006b400  mov     ecx, eax
0x18006b402  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006b408  sub     ebx, [rsi+88h]
0x18006b40e  cmp     rbx, [rsi+70h]
0x18006b412  jb      short loc_18006B41F
0x18006b414  mov     ecx, 80070057h
0x18006b419  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18006b41f  lfence
0x18006b422  mov     rax, [rsi+68h]
0x18006b426  mov     rbx, [rax+rbx*8]
0x18006b42a  mov     rdi, [rsi+98h]
0x18006b431  mov     rdx, rdi; pdo
0x18006b434  mov     rcx, [rbx+20h]; pszPath
0x18006b438  call    LogSqmOpenData
0x18006b43d  mov     rcx, [rbx+10h]
0x18006b441  mov     rax, [rcx]
0x18006b444  mov     rdx, rdi
0x18006b447  mov     rax, [rax+40h]
0x18006b44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b450  nop
0x18006b451  mov     al, 1
0x18006b453  jmp     short loc_18006B459
0x18006b455  jmp     short $+2
0x18006b457  xor     al, al
0x18006b459  mov     rbx, [rsp+68h+arg_8]
0x18006b45e  add     rsp, 50h
0x18006b462  pop     r14
0x18006b464  pop     rdi
0x18006b465  pop     rsi
0x18006b466  retn
```
