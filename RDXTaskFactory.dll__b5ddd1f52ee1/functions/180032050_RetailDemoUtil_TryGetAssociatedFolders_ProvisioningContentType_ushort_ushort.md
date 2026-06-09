# RetailDemoUtil::TryGetAssociatedFolders(ProvisioningContentType,ushort * *,ushort * *)

- ea: `0x180032050`
- end: `0x1800322a1`
- name: `?TryGetAssociatedFolders@RetailDemoUtil@@YA_NW4ProvisioningContentType@@PEAPEAG1@Z`
- size: `593`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e8f0`
- `0x18000eab0`
- `0x180010770`
- `0x18002ce20`

## callees

- `0x180003390`
- `0x1800056d5`
- `0x18000b1d4`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180015e6c`
- `0x180017144`
- `0x180022ad8`
- `0x1800305b8`
- `0x180032050`

## import_xrefs

- `SHLWAPI!PathStripPathW` at `0x180032161`
- `SHLWAPI!PathStripPathW` at `0x180032161`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003212f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003212f`

## string_xrefs

- `0x180032250`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall RetailDemoUtil::TryGetAssociatedFolders(int a1, _QWORD *a2, _QWORD *a3)
{
  wchar_t **v6; // rbx
  unsigned __int64 *v7; // rdx
  PWSTR *p_ppszPath; // rcx
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  bool v13; // bl
  int v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  *a3 = 0;
  v17 = 0;
  *(_QWORD *)v15 = 0;
  v6 = &off_18006D0C0;
  do
  {
    if ( a1 != *((_DWORD *)v6 + 2) )
      goto LABEL_14;
    if ( !memcmp_0((char *)v6 + 12, &GUID_NULL, 0x10u) )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v15,
        &v18);
      p_ppszPath = (PWSTR *)&v18;
      goto LABEL_12;
    }
    ppszPath = 0;
    RetailDemoUtil::GetDemoUserToken(&hToken, v7);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)((char *)v6 + 12), 0, hToken, &ppszPath) >= 0 )
    {
      v9 = StringCchCopyW(pszPath, 0x104u, ppszPath);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          (const char *)(unsigned int)v9,
          v15[0]);
      PathStripPathW(pszPath);
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v19);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v15,
        &v19);
      v10 = &v19;
      goto LABEL_10;
    }
    if ( *((_DWORD *)v6 + 2) == 0x20000 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v20);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v15,
        &v20);
      v10 = &v20;
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v10);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    p_ppszPath = &ppszPath;
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(p_ppszPath);
    if ( *(_QWORD *)v15 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v22);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v17,
        &v22);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
    }
LABEL_14:
    v6 += 5;
  }
  while ( v6 != (wchar_t **)&qword_18006D3B8 );
  v11 = *(_QWORD *)v15;
  *(_QWORD *)v15 = 0;
  *a3 = v11;
  v12 = v17;
  v17 = 0;
  *a2 = v12;
  v13 = v12 && *a3;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v15);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  return v13;
}

```

## disassembly

```asm
0x180032050  mov     [rsp-8+arg_0], rbx
0x180032055  push    rbp
0x180032056  push    rsi
0x180032057  push    rdi
0x180032058  push    r14
0x18003205a  push    r15
0x18003205c  lea     rbp, [rsp-180h]
0x180032064  sub     rsp, 280h
0x18003206b  mov     rax, cs:__security_cookie
0x180032072  xor     rax, rsp
0x180032075  mov     [rbp+1A0h+var_30], rax
0x18003207c  mov     rdi, r8
0x18003207f  mov     r14, rdx
0x180032082  mov     r15d, ecx
0x180032085  mov     qword ptr [rdx], 0
0x18003208c  mov     qword ptr [r8], 0
0x180032093  mov     [rsp+2A0h+var_270], 0
0x18003209c  mov     qword ptr [rsp+2A0h+var_280], 0; int
0x1800320a5  lea     rbx, off_18006D0C0; "None"
0x1800320ac  cmp     r15d, [rbx+8]
0x1800320b0  jnz     loc_180032208
0x1800320b6  mov     r8d, 10h; Size
0x1800320bc  lea     rdx, GUID_NULL; Buf2
0x1800320c3  lea     rcx, [rbx+0Ch]; Buf1
0x1800320c7  call    memcmp_0
0x1800320cc  test    eax, eax
0x1800320ce  jnz     short loc_1800320FF
0x1800320d0  mov     rdx, [rbx+20h]
0x1800320d4  test    rdx, rdx
0x1800320d7  jnz     short loc_1800320DC
0x1800320d9  mov     rdx, [rbx]
0x1800320dc  lea     rcx, [rsp+2A0h+var_268]
0x1800320e1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800320e6  lea     rdx, [rsp+2A0h+var_268]
0x1800320eb  lea     rcx, [rsp+2A0h+var_280]
0x1800320f0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800320f5  lea     rcx, [rsp+2A0h+var_268]
0x1800320fa  jmp     loc_1800321D5
0x1800320ff  mov     [rsp+2A0h+ppszPath], 0
0x180032108  lea     rcx, [rsp+2A0h+hToken]
0x18003210d  call    ?GetDemoUserToken@RetailDemoUtil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; RetailDemoUtil::GetDemoUserToken(void)
0x180032112  nop
0x180032113  xor     edx, edx
0x180032115  lea     rcx, [rsp+2A0h+ppszPath]
0x18003211a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003211f  lea     r9, [rsp+2A0h+ppszPath]; ppszPath
0x180032124  mov     r8, [rsp+2A0h+hToken]; hToken
0x180032129  xor     edx, edx; dwFlags
0x18003212b  lea     rcx, [rbx+0Ch]; rfid
0x18003212f  call    cs:__imp_SHGetKnownFolderPath
0x180032135  test    eax, eax
0x180032137  js      short loc_18003218C
0x180032139  mov     r8, [rsp+2A0h+ppszPath]; unsigned __int16 *
0x18003213e  mov     edx, 104h; unsigned __int64
0x180032143  lea     rcx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x180032148  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003214d  mov     rcx, [rbp+1A8h]; this
0x180032154  test    eax, eax
0x180032156  js      loc_18003224D
0x18003215c  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x180032161  call    cs:__imp_PathStripPathW
0x180032167  lea     rdx, [rsp+2A0h+pszPath]
0x18003216c  lea     rcx, [rsp+2A0h+var_260]
0x180032171  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180032176  lea     rdx, [rsp+2A0h+var_260]
0x18003217b  lea     rcx, [rsp+2A0h+var_280]
0x180032180  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180032185  lea     rcx, [rsp+2A0h+var_260]
0x18003218a  jmp     short loc_1800321BF
0x18003218c  cmp     dword ptr [rbx+8], 20000h
0x180032193  jnz     short loc_1800321C5
0x180032195  mov     rdx, [rbx+20h]
0x180032199  test    rdx, rdx
0x18003219c  jnz     short loc_1800321A1
0x18003219e  mov     rdx, [rbx]
0x1800321a1  lea     rcx, [rsp+2A0h+var_258]
0x1800321a6  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800321ab  lea     rdx, [rsp+2A0h+var_258]
0x1800321b0  lea     rcx, [rsp+2A0h+var_280]
0x1800321b5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800321ba  lea     rcx, [rsp+2A0h+var_258]
0x1800321bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800321c4  nop
0x1800321c5  lea     rcx, [rsp+2A0h+hToken]
0x1800321ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800321cf  nop
0x1800321d0  lea     rcx, [rsp+2A0h+ppszPath]
0x1800321d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800321da  cmp     qword ptr [rsp+2A0h+var_280], 0
0x1800321e0  jz      short loc_180032208
0x1800321e2  mov     rdx, [rbx]
0x1800321e5  lea     rcx, [rsp+2A0h+var_248]
0x1800321ea  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800321ef  lea     rdx, [rsp+2A0h+var_248]
0x1800321f4  lea     rcx, [rsp+2A0h+var_270]
0x1800321f9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800321fe  lea     rcx, [rsp+2A0h+var_248]
0x180032203  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032208  add     rbx, 28h ; '('
0x18003220c  lea     rax, qword_18006D3B8
0x180032213  cmp     rbx, rax
0x180032216  jnz     loc_1800320AC
0x18003221c  mov     rax, qword ptr [rsp+2A0h+var_280]
0x180032221  mov     qword ptr [rsp+2A0h+var_280], 0
0x18003222a  mov     [rdi], rax
0x18003222d  mov     rax, [rsp+2A0h+var_270]
0x180032232  mov     [rsp+2A0h+var_270], 0
0x18003223b  mov     [r14], rax
0x18003223e  test    rax, rax
0x180032241  jz      short loc_180032262
0x180032243  cmp     qword ptr [rdi], 0
0x180032247  jz      short loc_180032262
0x180032249  mov     bl, 1
0x18003224b  jmp     short loc_180032264
0x18003224d  mov     r9d, eax; char *
0x180032250  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180032257  mov     edx, 254h; void *
0x18003225c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032262  xor     bl, bl
0x180032264  lea     rcx, [rsp+2A0h+var_280]
0x180032269  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003226e  nop
0x18003226f  lea     rcx, [rsp+2A0h+var_270]
0x180032274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032279  mov     al, bl
0x18003227b  mov     rcx, [rbp+1A0h+var_30]
0x180032282  xor     rcx, rsp; StackCookie
0x180032285  call    __security_check_cookie
0x18003228a  mov     rbx, [rsp+2A0h+arg_0]
0x180032292  add     rsp, 280h
0x180032299  pop     r15
0x18003229b  pop     r14
0x18003229d  pop     rdi
0x18003229e  pop     rsi
0x18003229f  pop     rbp
0x1800322a0  retn
```
