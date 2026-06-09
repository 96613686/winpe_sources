# GetPropKeyPath(IAudioSessionInfo *,ushort *,unsigned __int64)

- ea: `0x180012e64`
- end: `0x180012f9e`
- name: `?GetPropKeyPath@@YAJPEAUIAudioSessionInfo@@PEAG_K@Z`
- size: `314`
- prototype: `int(struct IAudioSessionInfo *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180012c1c`

## callees

- `0x18000a384`
- `0x18000e6a4`
- `0x180012900`
- `0x180012e64`
- `0x180014710`
- `0x1800273a4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012efa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012f43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012f43`

## string_xrefs

- `0x180012ec0`: `%s\Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180012f50`: `%s\Software\Microsoft\Internet Explorer\LowRegistry`

## pseudocode

```c
__int64 __fastcall GetPropKeyPath(struct IAudioSessionInfo *a1, unsigned __int16 *a2, void *a3)
{
  DWORD v5; // eax
  void *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  int ThreadUserStringSid; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  pv = a3;
  if ( (*(unsigned int (__fastcall **)(struct IAudioSessionInfo *))(*(_QWORD *)a1 + 128LL))(a1)
    && (v5 = (*(__int64 (__fastcall **)(struct IAudioSessionInfo *))(*(_QWORD *)a1 + 136LL))(a1),
        pv = 0,
        TsSessionGetUserSid(v5, (unsigned __int16 **)&pv),
        (v6 = pv) != 0) )
  {
    v7 = StringCbPrintfW(a2, 0x208u, L"%s\\Software\\Microsoft\\Internet Explorer\\LowRegistry", pv);
    v8 = v7;
    if ( v7 >= 0 )
      v8 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v7,
        v13);
    CoTaskMemFree(v6);
    return v8;
  }
  else
  {
    pv = 0;
    ThreadUserStringSid = GetThreadUserStringSid((unsigned __int16 **)&pv);
    v11 = ThreadUserStringSid;
    if ( ThreadUserStringSid >= 0 )
    {
      v12 = StringCbPrintfW(a2, 0x208u, L"%s\\Software\\Microsoft\\Internet Explorer\\LowRegistry", pv);
      v11 = v12;
      if ( v12 >= 0 )
        v11 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v12,
          v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)ThreadUserStringSid,
        v13);
      if ( pv )
        LocalFree(pv);
    }
    return v11;
  }
}

```

## disassembly

```asm
0x180012e64  mov     [rsp+arg_0], rbx
0x180012e69  mov     [rsp+pv], r8
0x180012e6e  push    rdi; int
0x180012e6f  sub     rsp, 20h
0x180012e73  mov     rax, [rcx]
0x180012e76  mov     rdi, rdx
0x180012e79  mov     rbx, rcx
0x180012e7c  mov     rax, [rax+80h]
0x180012e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e88  test    eax, eax
0x180012e8a  jz      short loc_180012F07
0x180012e8c  mov     rax, [rbx]
0x180012e8f  mov     rcx, rbx
0x180012e92  mov     rax, [rax+88h]
0x180012e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e9e  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x180012ea3  mov     [rsp+28h+pv], 0
0x180012eac  mov     ecx, eax; SessionId
0x180012eae  call    ?TsSessionGetUserSid@@YAJKPEAPEAG@Z; TsSessionGetUserSid(ulong,ushort * *)
0x180012eb3  mov     rbx, [rsp+28h+pv]
0x180012eb8  test    rbx, rbx
0x180012ebb  jz      short loc_180012F07
0x180012ebd  mov     r9, rbx
0x180012ec0  lea     r8, aSSoftwareMicro; "%s\\Software\\Microsoft\\Internet Explo"...
0x180012ec7  mov     edx, 208h; unsigned __int64
0x180012ecc  mov     rcx, rdi; unsigned __int16 *
0x180012ecf  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ed4  mov     edi, eax
0x180012ed6  test    eax, eax
0x180012ed8  jns     short loc_180012EF5
0x180012eda  mov     rcx, [rsp+28h]; this
0x180012edf  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012ee6  mov     r9d, eax; char *
0x180012ee9  mov     edx, 0B5h; void *
0x180012eee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ef3  jmp     short loc_180012EF7
0x180012ef5  xor     edi, edi
0x180012ef7  mov     rcx, rbx; pv
0x180012efa  call    cs:__imp_CoTaskMemFree
0x180012f00  mov     eax, edi
0x180012f02  jmp     loc_180012F93
0x180012f07  lea     rcx, [rsp+28h+pv]; unsigned __int16 **
0x180012f0c  mov     [rsp+28h+pv], 0
0x180012f15  call    ?GetThreadUserStringSid@@YAJPEAPEAG@Z; GetThreadUserStringSid(ushort * *)
0x180012f1a  mov     ebx, eax
0x180012f1c  test    eax, eax
0x180012f1e  jns     short loc_180012F4B
0x180012f20  mov     rcx, [rsp+28h]; this
0x180012f25  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012f2c  mov     r9d, eax; char *
0x180012f2f  mov     edx, 0BDh; void *
0x180012f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f39  mov     rcx, [rsp+28h+pv]; hMem
0x180012f3e  test    rcx, rcx
0x180012f41  jz      short loc_180012F91
0x180012f43  call    cs:__imp_LocalFree
0x180012f49  jmp     short loc_180012F91
0x180012f4b  mov     r9, [rsp+28h+pv]
0x180012f50  lea     r8, aSSoftwareMicro; "%s\\Software\\Microsoft\\Internet Explo"...
0x180012f57  mov     edx, 208h; unsigned __int64
0x180012f5c  mov     rcx, rdi; unsigned __int16 *
0x180012f5f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012f64  mov     ebx, eax
0x180012f66  test    eax, eax
0x180012f68  jns     short loc_180012F85
0x180012f6a  mov     rcx, [rsp+28h]; this
0x180012f6f  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012f76  mov     r9d, eax; char *
0x180012f79  mov     edx, 0BFh; void *
0x180012f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f83  jmp     short loc_180012F87
0x180012f85  xor     ebx, ebx
0x180012f87  lea     rcx, [rsp+28h+pv]
0x180012f8c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012f91  mov     eax, ebx
0x180012f93  mov     rbx, [rsp+28h+arg_0]
0x180012f98  add     rsp, 20h
0x180012f9c  pop     rdi
0x180012f9d  retn
```
