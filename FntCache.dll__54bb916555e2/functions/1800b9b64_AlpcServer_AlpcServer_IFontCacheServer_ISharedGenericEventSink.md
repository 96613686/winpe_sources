# AlpcServer::AlpcServer(IFontCacheServer *,ISharedGenericEventSink *)

- ea: `0x1800b9b64`
- end: `0x1800b9e0b`
- name: `??0AlpcServer@@QEAA@PEAUIFontCacheServer@@PEAUISharedGenericEventSink@@@Z`
- size: `679`
- prototype: `AlpcServer *__fastcall(AlpcServer *__hidden this, struct IFontCacheServer *, struct ISharedGenericEventSink *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b05b8`

## callees

- `0x180004810`
- `0x18000cd54`
- `0x1800217ac`
- `0x18002faf0`
- `0x18008bc90`
- `0x18009d72c`
- `0x1800a1558`
- `0x1800a2a08`
- `0x1800a4ca0`
- `0x1800a5658`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800b9aac`
- `0x1800b9b64`
- `0x1800b9e14`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b9db9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b9db9`
- `ntdll!NtAlpcCreatePort` at `0x1800b9d52`
- `ntdll!NtAlpcCreatePort` at `0x1800b9d52`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800b9cbe`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800b9cbe`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800b9ca2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800b9ca2`

## string_xrefs

- `0x1800b9ccc`: `\BaseNamedObjects\FontCachePort`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
AlpcServer *__fastcall AlpcServer::AlpcServer(
        AlpcServer *this,
        struct IFontCacheServer *a2,
        struct ISharedGenericEventSink *a3)
{
  PACL *FontCachePortDacl; // rbx
  unsigned int v7; // eax
  HANDLE v8; // rax
  _BYTE v10[8]; // [rsp+30h] [rbp-D0h] BYREF
  PACL *v11; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  void *v13; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v14[7]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v17[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v18; // [rsp+CCh] [rbp-34h]
  __int64 v19; // [rsp+D0h] [rbp-30h]
  int v20; // [rsp+100h] [rbp+0h]

  v14[6] = this;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 4) = _InterlockedIncrement((volatile signed __int32 *)&EventLogger::lastObjectId_);
  *((_QWORD *)this + 3) = 1919906915;
  EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(this, g_stateTag);
  *(_QWORD *)this = &AlpcServer::`vftable';
  ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>((char *)this + 32, a2);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct ISharedGenericEventSink *))(*(_QWORD *)a3 + 8LL))(a3);
  *((_QWORD *)this + 7) = 0;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 64);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 88);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>((char *)this + 112);
  *((_WORD *)this + 68) = 0;
  *((_QWORD *)this + 18) = 0;
  v11 = 0;
  (***((void (__fastcall ****)(_QWORD, GUID *, PACL **))this + 4))(
    *((_QWORD *)this + 4),
    &GUID_0437ac3f_95f7_449c_843a_2ac83aafd09b,
    &v11);
  if ( !v11 )
  {
    Exception::Exception((Exception *)v10, -2147467262, 0);
    LogAndThrow<OSException>(v10, 18769, 212);
  }
  *((_QWORD *)this + 5) = v11;
  FontCachePortDacl = (PACL *)CreateFontCachePortDacl();
  v11 = FontCachePortDacl;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, *FontCachePortDacl, 0) )
  {
    goto LABEL_11;
  }
  NtUnicodeString::NtUnicodeString((NtUnicodeString *)v15, L"\\BaseNamedObjects\\FontCachePort");
  v14[0] = 48;
  v14[3] = 0;
  v14[1] = 0;
  v14[2] = v15;
  v14[4] = pSecurityDescriptor;
  v14[5] = 0;
  memset_0(v17, 0, 0x48u);
  v17[0] = 720896;
  v20 = 4093;
  v17[1] = 12;
  v17[2] = 2;
  v18 = 257;
  v19 = 0x7FFF;
  v13 = 0;
  v7 = NtAlpcCreatePort(&v13, v14, v17);
  if ( v7 )
  {
    Exception::Exception((Exception *)v10, v7 | 0x10000000, v7);
    EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<OSException>(this, v10, 1668312161, 376);
  }
  NtHandle::Attach((AlpcServer *)((char *)this + 56), v13);
  ThreadId = 0;
  v8 = CreateThread(0, 0, AlpcServer::ThreadProc, this, 0, &ThreadId);
  Win32Handle::Attach((AlpcServer *)((char *)this + 144), v8);
  if ( !*((_QWORD *)this + 18) )
LABEL_11:
    OSException::ThrowLastError();
  ScopedPtr<Acl>::~ScopedPtr<Acl>(&v11);
  return this;
}

```

## disassembly

```asm
0x1800b9b64  mov     [rsp-8+arg_10], rbx
0x1800b9b69  mov     [rsp-8+arg_18], rsi
0x1800b9b6e  push    rbp
0x1800b9b6f  push    rdi
0x1800b9b70  push    r12
0x1800b9b72  push    r14
0x1800b9b74  push    r15
0x1800b9b76  lea     rbp, [rsp-20h]
0x1800b9b7b  sub     rsp, 120h
0x1800b9b82  mov     rax, cs:__security_cookie
0x1800b9b89  xor     rax, rsp
0x1800b9b8c  mov     [rbp+40h+var_30], rax
0x1800b9b90  mov     rsi, r8
0x1800b9b93  mov     rbx, rdx
0x1800b9b96  mov     rdi, rcx
0x1800b9b99  mov     [rbp+40h+var_C0], rcx
0x1800b9b9d  xor     r12d, r12d
0x1800b9ba0  mov     [rcx+8], r12d
0x1800b9ba4  lea     eax, [r12+1]
0x1800b9ba9  lock xadd cs:?lastObjectId_@EventLogger@@0IA, eax; uint EventLogger::lastObjectId_
0x1800b9bb1  inc     eax
0x1800b9bb3  mov     [rcx+10h], eax
0x1800b9bb6  mov     r8d, 726F7463h
0x1800b9bbc  mov     [rcx+18h], r8
0x1800b9bc0  mov     rdx, cs:?g_stateTag@@3VEventTag@@B; EventTag const g_stateTag
0x1800b9bc7  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(EventTag,EventTag)
0x1800b9bcc  nop
0x1800b9bcd  lea     rax, ??_7AlpcServer@@6B@; const AlpcServer::`vftable'
0x1800b9bd4  mov     [rdi], rax
0x1800b9bd7  mov     rdx, rbx
0x1800b9bda  lea     rcx, [rdi+20h]
0x1800b9bde  call    ??0?$ComPtr@VServerSideFontFaceContext@@@@QEAA@PEAVServerSideFontFaceContext@@@Z; ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>(ServerSideFontFaceContext *)
0x1800b9be3  nop
0x1800b9be4  mov     [rdi+28h], r12
0x1800b9be8  mov     [rdi+30h], rsi
0x1800b9bec  test    rsi, rsi
0x1800b9bef  jz      short loc_1800B9C01
0x1800b9bf1  mov     rax, [rsi]
0x1800b9bf4  mov     rcx, rsi
0x1800b9bf7  mov     rax, [rax+8]
0x1800b9bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c00  nop
0x1800b9c01  mov     [rdi+38h], r12
0x1800b9c05  lea     rcx, [rdi+40h]; void *
0x1800b9c09  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x1800b9c0e  nop
0x1800b9c0f  lea     rcx, [rdi+58h]; void *
0x1800b9c13  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x1800b9c18  nop
0x1800b9c19  lea     rcx, [rdi+70h]; void *
0x1800b9c1d  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x1800b9c22  nop
0x1800b9c23  mov     [rdi+88h], r12w
0x1800b9c2b  lea     rsi, [rdi+90h]
0x1800b9c32  mov     [rsi], r12
0x1800b9c35  mov     [rsp+140h+var_108], r12
0x1800b9c3a  mov     rcx, [rdi+20h]
0x1800b9c3e  mov     rax, [rcx]
0x1800b9c41  lea     r8, [rsp+140h+var_108]
0x1800b9c46  lea     rdx, _GUID_0437ac3f_95f7_449c_843a_2ac83aafd09b
0x1800b9c4d  mov     rax, [rax]
0x1800b9c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c55  nop
0x1800b9c56  mov     rax, [rsp+140h+var_108]
0x1800b9c5b  test    rax, rax
0x1800b9c5e  jnz     short loc_1800B9C88
0x1800b9c60  xor     r8d, r8d; unsigned int
0x1800b9c63  mov     edx, 80004002h; int
0x1800b9c68  lea     rcx, [rsp+140h+var_110]; this
0x1800b9c6d  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800b9c72  mov     edx, 4951h
0x1800b9c77  mov     r8d, 0D4h
0x1800b9c7d  lea     rcx, [rsp+140h+var_110]
0x1800b9c82  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x1800b9c88  mov     [rdi+28h], rax
0x1800b9c8c  call    ?CreateFontCachePortDacl@@YAPEAVAcl@@XZ; CreateFontCachePortDacl(void)
0x1800b9c91  mov     rbx, rax
0x1800b9c94  mov     [rsp+140h+var_108], rax
0x1800b9c99  mov     edx, 1; dwRevision
0x1800b9c9e  lea     rcx, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b9ca2  call    cs:__imp_InitializeSecurityDescriptor
0x1800b9ca8  test    eax, eax
0x1800b9caa  jz      loc_1800B9E05
0x1800b9cb0  xor     r9d, r9d; bDaclDefaulted
0x1800b9cb3  mov     r8, [rbx]; pDacl
0x1800b9cb6  lea     edx, [r9+1]; bDaclPresent
0x1800b9cba  lea     rcx, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b9cbe  call    cs:__imp_SetSecurityDescriptorDacl
0x1800b9cc4  test    eax, eax
0x1800b9cc6  jz      loc_1800B9E05
0x1800b9ccc  lea     rdx, ?FontCacheServerAlpcPortName@@3QB_WB; "\\BaseNamedObjects\\FontCachePort"
0x1800b9cd3  lea     rcx, [rbp+40h+var_B8]; this
0x1800b9cd7  call    ??0NtUnicodeString@@QEAA@QEB_W@Z; NtUnicodeString::NtUnicodeString(wchar_t const * const)
0x1800b9cdc  mov     [rsp+140h+var_F0], 30h ; '0'
0x1800b9ce5  mov     [rsp+140h+var_D8], r12
0x1800b9cea  mov     [rsp+140h+var_E8], r12
0x1800b9cef  lea     rax, [rbp+40h+var_B8]
0x1800b9cf3  mov     [rsp+140h+var_E0], rax
0x1800b9cf8  lea     rax, [rbp+40h+pSecurityDescriptor]
0x1800b9cfc  mov     [rsp+140h+var_D0], rax
0x1800b9d01  mov     [rsp+140h+var_C8], r12
0x1800b9d06  xor     edx, edx; Val
0x1800b9d08  lea     r8d, [rdx+48h]; Size
0x1800b9d0c  lea     rcx, [rbp+40h+var_80]; void *
0x1800b9d10  call    memset_0
0x1800b9d15  mov     [rbp+40h+var_80], 0B0000h
0x1800b9d1c  mov     [rbp+40h+var_40], 0FFDh
0x1800b9d23  mov     [rbp+40h+var_7C], 0Ch
0x1800b9d2a  mov     [rbp+40h+var_78], 2
0x1800b9d31  mov     [rbp+40h+var_74], 101h
0x1800b9d37  mov     [rbp+40h+var_70], 7FFFh
0x1800b9d3f  mov     [rsp+140h+var_F8], r12
0x1800b9d44  lea     r8, [rbp+40h+var_80]
0x1800b9d48  lea     rdx, [rsp+140h+var_F0]
0x1800b9d4d  lea     rcx, [rsp+140h+var_F8]
0x1800b9d52  call    cs:__imp_NtAlpcCreatePort
0x1800b9d58  test    eax, eax
0x1800b9d5a  jz      short loc_1800B9D89
0x1800b9d5c  mov     edx, eax
0x1800b9d5e  bts     edx, 1Ch; int
0x1800b9d62  mov     r8d, eax; unsigned int
0x1800b9d65  lea     rcx, [rsp+140h+var_110]; this
0x1800b9d6a  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800b9d6f  mov     r8d, 63706C61h
0x1800b9d75  mov     r9d, 178h
0x1800b9d7b  lea     rdx, [rsp+140h+var_110]
0x1800b9d80  mov     rcx, rdi
0x1800b9d83  call    ??$LogAndThrow@VOSException@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXAEBVOSException@@VEventTag@@I@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x1800b9d89  mov     rdx, [rsp+140h+var_F8]; void *
0x1800b9d8e  lea     rcx, [rdi+38h]; this
0x1800b9d92  call    ?Attach@NtHandle@@QEAAXPEAX@Z; NtHandle::Attach(void *)
0x1800b9d97  mov     [rsp+140h+ThreadId], r12d
0x1800b9d9c  lea     rax, [rsp+140h+ThreadId]
0x1800b9da1  mov     [rsp+140h+lpThreadId], rax; lpThreadId
0x1800b9da6  mov     [rsp+140h+dwCreationFlags], r12d; dwCreationFlags
0x1800b9dab  mov     r9, rdi; lpParameter
0x1800b9dae  lea     r8, ?ThreadProc@AlpcServer@@CAKPEAX@Z; lpStartAddress
0x1800b9db5  xor     edx, edx; dwStackSize
0x1800b9db7  xor     ecx, ecx; lpThreadAttributes
0x1800b9db9  call    cs:__imp_CreateThread
0x1800b9dbf  mov     rdx, rax; void *
0x1800b9dc2  mov     rcx, rsi; this
0x1800b9dc5  call    ?Attach@Win32Handle@@QEAAXPEAX@Z; Win32Handle::Attach(void *)
0x1800b9dca  cmp     [rsi], r12
0x1800b9dcd  jz      short loc_1800B9E05
0x1800b9dcf  lea     rcx, [rsp+140h+var_108]
0x1800b9dd4  call    ??1?$ScopedPtr@VAcl@@@@QEAA@XZ; ScopedPtr<Acl>::~ScopedPtr<Acl>(void)
0x1800b9dd9  nop
0x1800b9dda  mov     rax, rdi
0x1800b9ddd  mov     rcx, [rbp+40h+var_30]
0x1800b9de1  xor     rcx, rsp; StackCookie
0x1800b9de4  call    __security_check_cookie
0x1800b9de9  lea     r11, [rsp+140h+var_20]
0x1800b9df1  mov     rbx, [r11+40h]
0x1800b9df5  mov     rsi, [r11+48h]
0x1800b9df9  mov     rsp, r11
0x1800b9dfc  pop     r15
0x1800b9dfe  pop     r14
0x1800b9e00  pop     r12
0x1800b9e02  pop     rdi
0x1800b9e03  pop     rbp
0x1800b9e04  retn
0x1800b9e05  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
