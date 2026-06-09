# RfbFileDialogEvents::OnFolderChanging(IFileDialog *,IShellItem *)

- ea: `0x18000c720`
- end: `0x18000c967`
- name: `?OnFolderChanging@RfbFileDialogEvents@@UEAAJPEAUIFileDialog@@PEAUIShellItem@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(RfbFileDialogEvents *__hidden this, struct IFileDialog *, struct IShellItem *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000798c`
- `0x18000c720`
- `0x18000c970`
- `0x180017434`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c94d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c94d`
- `USER32!MessageBoxW` at `0x18000c917`
- `USER32!MessageBoxW` at `0x18000c917`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RfbFileDialogEvents::OnFolderChanging(
        RfbFileDialogEvents *this,
        struct IFileDialog *a2,
        struct IShellItem *a3)
{
  int v4; // r14d
  wchar_t *v5; // rbx
  const wchar_t *v6; // rdx
  char v7; // si
  bool v8; // di
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  const WCHAR *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  wchar_t *String1; // [rsp+20h] [rbp-20h] BYREF
  __int64 v21; // [rsp+28h] [rbp-18h] BYREF
  HWND hWnd[2]; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v24; // [rsp+88h] [rbp+48h] BYREF

  String1 = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, wchar_t **))a3->lpVtbl->GetDisplayName)(
         a3,
         2147794944LL,
         &String1);
  v5 = String1;
  if ( v4 >= 0 )
  {
    v6 = (const wchar_t *)&RemoteFileBrowseClient::rfbRoot;
    if ( (unsigned __int64)qword_1800236B8 > 7 )
      v6 = RemoteFileBrowseClient::rfbRoot;
    if ( !wcsncmp_0(String1, v6, (unsigned int)MaxCount) )
    {
      v7 = 1;
      v24 = 0;
      if ( ((int (__fastcall *)(struct IFileDialog *, _QWORD **))a2->lpVtbl->GetCurrentSelection)(a2, &v24) < 0 )
      {
        v8 = 1;
      }
      else
      {
        v8 = 0;
        pv = 0;
        v9 = *v24;
        pv = 0;
        if ( (*(int (__fastcall **)(_QWORD *, __int64, LPVOID *))(v9 + 40))(v24, 2147647488LL, &pv) >= 0 )
          v8 = OnTheSameServer(String1, (const unsigned __int16 *)pv);
        if ( pv )
          CoTaskMemFree(pv);
      }
      v10 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
      }
      v5 = String1;
    }
    else
    {
      v7 = 0;
      v8 = 0;
    }
    if ( wcsncmp_0(v5, L"Network", 7u) && wcsncmp_0(v5, L"\\\\", 2u) && (!v7 || !v8) )
    {
      v21 = 0;
      hWnd[0] = 0;
      if ( ((__int64 (__fastcall *)(struct IFileDialog *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_00000114_0000_0000_c000_000000000046,
             &v21) >= 0
        && (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v21 + 24LL))(v21, hWnd) >= 0 )
      {
        if ( !v7 || (v12 = !v8, v13 = 121, !v12) )
          v13 = 115;
        LODWORD(pv) = 100;
        v14 = std::map<int,std::wstring>::operator[](v11, &pv);
        v16 = (const WCHAR *)v14;
        if ( *(_QWORD *)(v14 + 24) > 7u )
          v16 = *(const WCHAR **)v14;
        LODWORD(v24) = v13;
        v17 = std::map<int,std::wstring>::operator[](v15, &v24);
        if ( *(_QWORD *)(v17 + 24) > 7u )
          v17 = *(_QWORD *)v17;
        MessageBoxW(hWnd[0], (LPCWSTR)v17, v16, 0x30u);
      }
      v4 = 1;
      v18 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v5 = String1;
    }
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c720  mov     [rsp-28h+arg_0], rbx
0x18000c725  push    rbp
0x18000c726  push    rsi
0x18000c727  push    rdi
0x18000c728  push    r14
0x18000c72a  push    r15
0x18000c72c  mov     rbp, rsp
0x18000c72f  sub     rsp, 40h
0x18000c733  mov     rcx, r8
0x18000c736  mov     r15, rdx
0x18000c739  mov     [rbp+String1], 0
0x18000c741  mov     rax, [r8]
0x18000c744  lea     r8, [rbp+String1]
0x18000c748  mov     edx, 8004C000h
0x18000c74d  mov     rax, [rax+28h]
0x18000c751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c756  mov     r14d, eax
0x18000c759  mov     rbx, [rbp+String1]
0x18000c75d  test    eax, eax
0x18000c75f  js      loc_18000C945
0x18000c765  lea     rdx, ?rfbRoot@RemoteFileBrowseClient@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const RemoteFileBrowseClient::rfbRoot
0x18000c76c  cmp     cs:qword_1800236B8, 7
0x18000c774  cmova   rdx, cs:?rfbRoot@RemoteFileBrowseClient@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; String2
0x18000c77c  mov     r8d, cs:MaxCount; MaxCount
0x18000c783  mov     rcx, rbx; String1
0x18000c786  call    wcsncmp_0
0x18000c78b  test    eax, eax
0x18000c78d  jnz     loc_18000C82D
0x18000c793  mov     sil, 1
0x18000c796  mov     [rbp+arg_18], 0
0x18000c79e  mov     rax, [r15]
0x18000c7a1  lea     rdx, [rbp+arg_18]
0x18000c7a5  mov     rcx, r15
0x18000c7a8  mov     rax, [rax+70h]
0x18000c7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b1  test    eax, eax
0x18000c7b3  js      short loc_18000C806
0x18000c7b5  xor     dil, dil
0x18000c7b8  mov     [rbp+pv], 0
0x18000c7c0  mov     rcx, [rbp+arg_18]
0x18000c7c4  mov     rax, [rcx]
0x18000c7c7  mov     [rbp+pv], 0
0x18000c7cf  lea     r8, [rbp+pv]
0x18000c7d3  mov     edx, 80028000h
0x18000c7d8  mov     rax, [rax+28h]
0x18000c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e1  test    eax, eax
0x18000c7e3  js      short loc_18000C7F5
0x18000c7e5  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18000c7e9  mov     rcx, [rbp+String1]; unsigned __int16 *
0x18000c7ed  call    ?OnTheSameServer@@YA_NPEBG0@Z; OnTheSameServer(ushort const *,ushort const *)
0x18000c7f2  mov     dil, al
0x18000c7f5  mov     rcx, [rbp+pv]; pv
0x18000c7f9  test    rcx, rcx
0x18000c7fc  jz      short loc_18000C809
0x18000c7fe  call    cs:__imp_CoTaskMemFree
0x18000c804  jmp     short loc_18000C809
0x18000c806  mov     dil, 1
0x18000c809  mov     rcx, [rbp+arg_18]
0x18000c80d  test    rcx, rcx
0x18000c810  jz      short loc_18000C827
0x18000c812  mov     [rbp+arg_18], 0
0x18000c81a  mov     rax, [rcx]
0x18000c81d  mov     rax, [rax+10h]
0x18000c821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c826  nop
0x18000c827  mov     rbx, [rbp+String1]
0x18000c82b  jmp     short loc_18000C833
0x18000c82d  xor     sil, sil
0x18000c830  xor     dil, dil
0x18000c833  mov     r8d, 7; MaxCount
0x18000c839  lea     rdx, aNetwork; "Network"
0x18000c840  mov     rcx, rbx; String1
0x18000c843  call    wcsncmp_0
0x18000c848  test    eax, eax
0x18000c84a  jz      loc_18000C945
0x18000c850  mov     r8d, 2; MaxCount
0x18000c856  lea     rdx, String2; "\\\\"
0x18000c85d  mov     rcx, rbx; String1
0x18000c860  call    wcsncmp_0
0x18000c865  test    eax, eax
0x18000c867  jz      loc_18000C945
0x18000c86d  test    sil, sil
0x18000c870  jz      short loc_18000C87B
0x18000c872  test    dil, dil
0x18000c875  jnz     loc_18000C945
0x18000c87b  mov     [rbp+var_18], 0
0x18000c883  mov     [rbp+hWnd], 0
0x18000c88b  mov     rax, [r15]
0x18000c88e  lea     r8, [rbp+var_18]
0x18000c892  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x18000c899  mov     rcx, r15
0x18000c89c  mov     rax, [rax]
0x18000c89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a4  test    eax, eax
0x18000c8a6  js      short loc_18000C91D
0x18000c8a8  mov     rcx, [rbp+var_18]
0x18000c8ac  mov     rax, [rcx]
0x18000c8af  lea     rdx, [rbp+hWnd]
0x18000c8b3  mov     rax, [rax+18h]
0x18000c8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8bc  test    eax, eax
0x18000c8be  js      short loc_18000C91D
0x18000c8c0  test    sil, sil
0x18000c8c3  jz      short loc_18000C8CF
0x18000c8c5  test    dil, dil
0x18000c8c8  mov     edi, 79h ; 'y'
0x18000c8cd  jz      short loc_18000C8D4
0x18000c8cf  mov     edi, 73h ; 's'
0x18000c8d4  mov     dword ptr [rbp+pv], 64h ; 'd'
0x18000c8db  lea     rdx, [rbp+pv]
0x18000c8df  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000c8e4  mov     rbx, rax
0x18000c8e7  cmp     qword ptr [rax+18h], 7
0x18000c8ec  jbe     short loc_18000C8F1
0x18000c8ee  mov     rbx, [rax]
0x18000c8f1  mov     dword ptr [rbp+arg_18], edi
0x18000c8f4  lea     rdx, [rbp+arg_18]
0x18000c8f8  call    ??A?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAH@Z; std::map<int,std::wstring>::operator[](int &&)
0x18000c8fd  cmp     qword ptr [rax+18h], 7
0x18000c902  jbe     short loc_18000C907
0x18000c904  mov     rax, [rax]
0x18000c907  mov     r9d, 30h ; '0'; uType
0x18000c90d  mov     r8, rbx; lpCaption
0x18000c910  mov     rdx, rax; lpText
0x18000c913  mov     rcx, [rbp+hWnd]; hWnd
0x18000c917  call    cs:__imp_MessageBoxW
0x18000c91d  mov     r14d, 1
0x18000c923  mov     rcx, [rbp+var_18]
0x18000c927  test    rcx, rcx
0x18000c92a  jz      short loc_18000C941
0x18000c92c  mov     [rbp+var_18], 0
0x18000c934  mov     rax, [rcx]
0x18000c937  mov     rax, [rax+10h]
0x18000c93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c940  nop
0x18000c941  mov     rbx, [rbp+String1]
0x18000c945  test    rbx, rbx
0x18000c948  jz      short loc_18000C953
0x18000c94a  mov     rcx, rbx; pv
0x18000c94d  call    cs:__imp_CoTaskMemFree
0x18000c953  mov     eax, r14d
0x18000c956  mov     rbx, [rsp+40h+arg_0]
0x18000c95b  add     rsp, 40h
0x18000c95f  pop     r15
0x18000c961  pop     r14
0x18000c963  pop     rdi
0x18000c964  pop     rsi
0x18000c965  pop     rbp
0x18000c966  retn
```
