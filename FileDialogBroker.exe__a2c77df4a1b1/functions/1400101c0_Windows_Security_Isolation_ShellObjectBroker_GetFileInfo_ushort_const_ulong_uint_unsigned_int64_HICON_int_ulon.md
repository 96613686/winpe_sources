# Windows::Security::Isolation::ShellObjectBroker::GetFileInfo(ushort const *,ulong,uint,unsigned __int64 *,HICON__ * *,int *,ulong *,ushort * *,ushort * *)

- ea: `0x1400101c0`
- end: `0x140010383`
- name: `?GetFileInfo@ShellObjectBroker@Isolation@Security@Windows@@UEAAJPEBGKIPEA_KPEAPEAUHICON__@@PEAHPEAKPEAPEAG5@Z`
- size: `451`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::ShellObjectBroker *this, const unsigned __int16 *, DWORD, UINT, unsigned __int64 *, HICON *, int *, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140001c80`
- `0x1400028a8`
- `0x140005084`
- `0x14000fdec`
- `0x14000fed4`
- `0x1400101c0`
- `0x140010498`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1400102be`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1400102be`

## string_xrefs

- `0x140010238`: `onecoreuap\ds\security\isolation\broker\lib\shellobjectbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::ShellObjectBroker::GetFileInfo(
        Windows::Security::Isolation::ShellObjectBroker *this,
        const unsigned __int16 *a2,
        DWORD a3,
        UINT a4,
        unsigned __int64 *a5,
        HICON *a6,
        int *a7,
        unsigned int *a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10)
{
  __int64 v11; // rdx
  void *v13; // rdx
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned __int16 *v16; // rax
  void *v17; // rdx
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned __int16 *v20; // rax
  UINT uFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwFileAttributes[2]; // [rsp+30h] [rbp-D0h] BYREF
  UINT v23; // [rsp+38h] [rbp-C8h]
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v23 = a4;
  dwFileAttributes[0] = a3;
  if ( !a5 )
  {
    v11 = 125;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\shellobjectbroker.cpp",
      (const char *)0x80004003LL,
      uFlags);
    return 2147500035LL;
  }
  if ( !a6 )
  {
    v11 = 126;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v11 = 127;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v11 = 128;
    goto LABEL_3;
  }
  if ( !a9 )
  {
    v11 = 129;
    goto LABEL_3;
  }
  if ( !a10 )
  {
    v11 = 130;
    goto LABEL_3;
  }
  memset_0(&psfi, 0, sizeof(psfi));
  psfi.iIcon = *a7;
  *a5 = SHGetFileInfoW(a2, dwFileAttributes[0], &psfi, 0x2B8u, v23);
  *a6 = psfi.hIcon;
  *a7 = psfi.iIcon;
  *a8 = psfi.dwAttributes;
  *a9 = 0;
  *a10 = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    dwFileAttributes,
    psfi.szDisplayName);
  v16 = *(unsigned __int16 **)dwFileAttributes;
  if ( !*(_QWORD *)dwFileAttributes )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v13, v14, v15);
  *(_QWORD *)dwFileAttributes = 0;
  *a9 = v16;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwFileAttributes);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    dwFileAttributes,
    psfi.szTypeName);
  v20 = *(unsigned __int16 **)dwFileAttributes;
  if ( !*(_QWORD *)dwFileAttributes )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v17, v18, v19);
  *(_QWORD *)dwFileAttributes = 0;
  *a10 = v20;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(dwFileAttributes);
  return 0;
}

```

## disassembly

```asm
0x1400101c0  mov     [rsp-8+arg_0], rbx
0x1400101c5  push    rbp
0x1400101c6  push    rsi
0x1400101c7  push    rdi
0x1400101c8  push    r12
0x1400101ca  push    r13
0x1400101cc  push    r14
0x1400101ce  push    r15
0x1400101d0  lea     rbp, [rsp-210h]
0x1400101d8  sub     rsp, 310h
0x1400101df  mov     rax, cs:__security_cookie
0x1400101e6  xor     rax, rsp
0x1400101e9  mov     [rbp+240h+var_40], rax
0x1400101f0  mov     r12, [rbp+240h+arg_20]
0x1400101f7  mov     r13, rdx
0x1400101fa  mov     r14, [rbp+240h+arg_28]
0x140010201  mov     rsi, [rbp+240h+arg_30]
0x140010208  mov     r15, [rbp+240h+arg_38]
0x14001020f  mov     rdi, [rbp+240h+arg_40]
0x140010216  mov     rbx, [rbp+240h+arg_48]
0x14001021d  mov     [rsp+340h+var_308], r9d
0x140010222  mov     [rsp+340h+dwFileAttributes], r8d
0x140010227  test    r12, r12
0x14001022a  jnz     short loc_140010253
0x14001022c  lea     edx, [r12+7Dh]; void *
0x140010231  mov     rcx, [rbp+248h]; this
0x140010238  lea     r8, aOnecoreuapDsSe_4; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001023f  mov     ebx, 80004003h
0x140010244  mov     r9d, ebx; char *
0x140010247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001024c  mov     eax, ebx
0x14001024e  jmp     loc_14001034D
0x140010253  test    r14, r14
0x140010256  jnz     short loc_14001025E
0x140010258  lea     edx, [r14+7Eh]
0x14001025c  jmp     short loc_140010231
0x14001025e  test    rsi, rsi
0x140010261  jnz     short loc_140010268
0x140010263  lea     edx, [rsi+7Fh]
0x140010266  jmp     short loc_140010231
0x140010268  test    r15, r15
0x14001026b  jnz     short loc_140010274
0x14001026d  mov     edx, 80h
0x140010272  jmp     short loc_140010231
0x140010274  test    rdi, rdi
0x140010277  jnz     short loc_140010280
0x140010279  mov     edx, 81h
0x14001027e  jmp     short loc_140010231
0x140010280  test    rbx, rbx
0x140010283  jnz     short loc_14001028C
0x140010285  mov     edx, 82h
0x14001028a  jmp     short loc_140010231
0x14001028c  xor     edx, edx; Val
0x14001028e  lea     rcx, [rsp+340h+psfi]; void *
0x140010293  mov     r8d, 2B8h; Size
0x140010299  call    memset_0
0x14001029e  mov     eax, [rsi]
0x1400102a0  lea     r8, [rsp+340h+psfi]; psfi
0x1400102a5  mov     edx, [rsp+340h+dwFileAttributes]; dwFileAttributes
0x1400102a9  mov     r9d, 2B8h; cbFileInfo
0x1400102af  mov     [rsp+340h+psfi.iIcon], eax
0x1400102b3  mov     rcx, r13; pszPath
0x1400102b6  mov     eax, [rsp+340h+var_308]
0x1400102ba  mov     [rsp+340h+uFlags], eax; uFlags
0x1400102be  call    cs:__imp_SHGetFileInfoW
0x1400102c4  mov     [r12], rax
0x1400102c8  lea     rdx, [rsp+340h+psfi.szDisplayName]
0x1400102cd  mov     rax, [rsp+340h+psfi.hIcon]
0x1400102d2  lea     rcx, [rsp+340h+dwFileAttributes]
0x1400102d7  mov     [r14], rax
0x1400102da  mov     eax, [rsp+340h+psfi.iIcon]
0x1400102de  mov     [rsi], eax
0x1400102e0  xor     esi, esi
0x1400102e2  mov     eax, [rsp+340h+psfi.dwAttributes]
0x1400102e6  mov     [r15], eax
0x1400102e9  mov     [rdi], rsi
0x1400102ec  mov     [rbx], rsi
0x1400102ef  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400102f4  mov     rax, qword ptr [rsp+340h+dwFileAttributes]
0x1400102f9  mov     rcx, [rbp+248h]; this
0x140010300  test    rax, rax
0x140010303  jz      short loc_14001037D
0x140010305  lea     rcx, [rsp+340h+dwFileAttributes]
0x14001030a  mov     qword ptr [rsp+340h+dwFileAttributes], rsi
0x14001030f  mov     [rdi], rax
0x140010312  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010317  lea     rdx, [rbp+240h+psfi.szTypeName]
0x14001031e  lea     rcx, [rsp+340h+dwFileAttributes]
0x140010323  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140010328  mov     rax, qword ptr [rsp+340h+dwFileAttributes]
0x14001032d  mov     rcx, [rbp+248h]; this
0x140010334  test    rax, rax
0x140010337  jz      short loc_140010377
0x140010339  lea     rcx, [rsp+340h+dwFileAttributes]
0x14001033e  mov     qword ptr [rsp+340h+dwFileAttributes], rsi
0x140010343  mov     [rbx], rax
0x140010346  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14001034b  xor     eax, eax
0x14001034d  mov     rcx, [rbp+240h+var_40]
0x140010354  xor     rcx, rsp; StackCookie
0x140010357  call    __security_check_cookie
0x14001035c  mov     rbx, [rsp+340h+arg_0]
0x140010364  add     rsp, 310h
0x14001036b  pop     r15
0x14001036d  pop     r14
0x14001036f  pop     r13
0x140010371  pop     r12
0x140010373  pop     rdi
0x140010374  pop     rsi
0x140010375  pop     rbp
0x140010376  retn
0x140010377  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14001037d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
