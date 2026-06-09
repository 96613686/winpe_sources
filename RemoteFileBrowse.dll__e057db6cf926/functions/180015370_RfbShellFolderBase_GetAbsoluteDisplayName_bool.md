# RfbShellFolderBase::GetAbsoluteDisplayName(bool)

- ea: `0x180015370`
- end: `0x18001547c`
- name: `?GetAbsoluteDisplayName@RfbShellFolderBase@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `268`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800053f0`
- `0x180007150`
- `0x18000b0ec`
- `0x180015370`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001541f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001541f`
- `SHELL32!SHCreateItemFromIDList` at `0x1800153a4`
- `SHELL32!SHCreateItemFromIDList` at `0x1800153a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall RfbShellFolderBase::GetAbsoluteDisplayName(__int64 a1, _QWORD *a2, char a3)
{
  __int64 *v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rax
  int v9; // eax
  _WORD *v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  __int64 *v17; // [rsp+68h] [rbp+20h] BYREF

  v17 = 0;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>((__int64 *)&v17);
  v7 = SHCreateItemFromIDList(*(LPCITEMIDLIST *)(a1 + 56), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4DA,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v7,
      v14);
  pv = 0;
  v8 = *v17;
  pv = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, LPVOID *))(v8 + 40))(v17, a3 != 0 ? 0x80028000 : 0, &pv);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4DE,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v9,
      v14);
  v10 = pv;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 0;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  std::wstring::_Construct<1,unsigned short const *>(a2, v10, v11);
  if ( pv )
    CoTaskMemFree(pv);
  v12 = (__int64)v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return a2;
}

```

## disassembly

```asm
0x180015370  mov     [rsp+arg_8], rbx
0x180015375  push    rbp
0x180015376  push    rsi
0x180015377  push    rdi
0x180015378  sub     rsp, 30h
0x18001537c  mov     sil, r8b
0x18001537f  mov     rdi, rdx
0x180015382  mov     rbx, rcx
0x180015385  xor     ebp, ebp
0x180015387  mov     [rsp+48h+arg_18], rbp
0x18001538c  lea     rcx, [rsp+48h+arg_18]
0x180015391  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x180015396  mov     r8, rax; ppv
0x180015399  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800153a0  mov     rcx, [rbx+38h]; pidl
0x1800153a4  call    cs:__imp_SHCreateItemFromIDList
0x1800153aa  mov     rcx, [rsp+48h]; this
0x1800153af  test    eax, eax
0x1800153b1  js      loc_180015467
0x1800153b7  mov     [rsp+48h+pv], rbp
0x1800153bc  mov     rcx, [rsp+48h+arg_18]
0x1800153c1  mov     rax, [rcx]
0x1800153c4  mov     [rsp+48h+pv], rbp
0x1800153c9  neg     sil
0x1800153cc  sbb     edx, edx
0x1800153ce  and     edx, 80028000h
0x1800153d4  lea     r8, [rsp+48h+pv]
0x1800153d9  mov     rax, [rax+28h]
0x1800153dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e2  mov     rcx, [rsp+48h]; this
0x1800153e7  test    eax, eax
0x1800153e9  js      short loc_180015452
0x1800153eb  mov     rdx, [rsp+48h+pv]
0x1800153f0  xorps   xmm0, xmm0
0x1800153f3  movups  xmmword ptr [rdi], xmm0
0x1800153f6  mov     [rdi+10h], rbp
0x1800153fa  mov     [rdi+18h], rbp
0x1800153fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015402  inc     r8
0x180015405  cmp     [rdx+r8*2], bp
0x18001540a  jnz     short loc_180015402
0x18001540c  mov     rcx, rdi
0x18001540f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015414  nop
0x180015415  mov     rcx, [rsp+48h+pv]; pv
0x18001541a  test    rcx, rcx
0x18001541d  jz      short loc_180015426
0x18001541f  call    cs:__imp_CoTaskMemFree
0x180015425  nop
0x180015426  mov     rcx, [rsp+48h+arg_18]
0x18001542b  test    rcx, rcx
0x18001542e  jz      short loc_180015442
0x180015430  mov     [rsp+48h+arg_18], rbp
0x180015435  mov     rax, [rcx]
0x180015438  mov     rax, [rax+10h]
0x18001543c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015441  nop
0x180015442  mov     rax, rdi
0x180015445  mov     rbx, [rsp+48h+arg_8]
0x18001544a  add     rsp, 30h
0x18001544e  pop     rdi
0x18001544f  pop     rsi
0x180015450  pop     rbp
0x180015451  retn
0x180015452  mov     r9d, eax; char *
0x180015455  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x18001545c  mov     edx, 4DEh; void *
0x180015461  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015467  mov     r9d, eax; char *
0x18001546a  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180015471  mov     edx, 4DAh; void *
0x180015476  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
