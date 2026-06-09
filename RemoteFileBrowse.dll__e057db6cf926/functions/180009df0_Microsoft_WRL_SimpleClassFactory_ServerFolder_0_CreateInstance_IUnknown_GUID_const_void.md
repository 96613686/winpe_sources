# Microsoft::WRL::SimpleClassFactory<ServerFolder,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009df0`
- end: `0x180009ece`
- name: `?CreateInstance@?$SimpleClassFactory@VServerFolder@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800020d0`
- `0x180006f70`
- `0x180009df0`
- `0x18000acc0`
- `0x180016328`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e14`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e14`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<ServerFolder,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD *); // rbx
  ServerFolder *v8; // rax
  int v9; // edi
  ServerFolder *v10; // rbx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD *); // rbx
  __int64 (__fastcall ***v12)(_QWORD, __int64, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  v7 = 0;
  v12 = 0;
  v8 = (ServerFolder *)operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
  {
    v10 = ServerFolder::ServerFolder(v8);
    v9 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<ServerFolder,RfbShellFolderBase,1>,IDelegateFolder>::QueryInterface(
           v10,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v12);
    if ( v10 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(v10);
    if ( v9 >= 0 )
    {
      v11 = v12;
      v9 = (**v12)(v12, a3, a4);
      if ( v11 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v11)[2])(v11);
      return (unsigned int)v9;
    }
    v7 = v12;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v7 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v7)[2])(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009df0  push    rbx
0x180009df2  push    rbp
0x180009df3  push    rsi
0x180009df4  push    rdi
0x180009df5  sub     rsp, 28h
0x180009df9  mov     rsi, r9
0x180009dfc  mov     rbp, r8
0x180009dff  mov     qword ptr [r9], 0
0x180009e06  test    rdx, rdx
0x180009e09  jz      short loc_180009E21
0x180009e0b  xor     edx, edx
0x180009e0d  mov     ebx, 80040110h
0x180009e12  mov     ecx, ebx
0x180009e14  call    cs:__imp_RoOriginateError
0x180009e1a  mov     eax, ebx
0x180009e1c  jmp     loc_180009EC5
0x180009e21  xor     ebx, ebx
0x180009e23  mov     [rsp+48h+arg_8], rbx
0x180009e28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e2f  mov     ecx, 80h; unsigned __int64
0x180009e34  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e39  test    rax, rax
0x180009e3c  jnz     short loc_180009E45
0x180009e3e  mov     edi, 8007000Eh
0x180009e43  jmp     short loc_180009E7C
0x180009e45  mov     rcx, rax; this
0x180009e48  call    ??0ServerFolder@@QEAA@XZ; ServerFolder::ServerFolder(void)
0x180009e4d  mov     rbx, rax
0x180009e50  lea     r8, [rsp+48h+arg_8]
0x180009e55  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009e5c  mov     rcx, rax
0x180009e5f  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VServerFolder@@VRfbShellFolderBase@@$00@23@UIDelegateFolder@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<ServerFolder,RfbShellFolderBase,1>,IDelegateFolder>::QueryInterface(_GUID const &,void * *)
0x180009e64  mov     edi, eax
0x180009e66  test    rbx, rbx
0x180009e69  jz      short loc_180009E73
0x180009e6b  mov     rcx, rbx
0x180009e6e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VDiskFolder@@VRfbShellFolderBase@@$00@23@UIResolveShellLink@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(void)
0x180009e73  test    edi, edi
0x180009e75  jns     short loc_180009E93
0x180009e77  mov     rbx, [rsp+48h+arg_8]
0x180009e7c  test    rbx, rbx
0x180009e7f  jz      short loc_180009E91
0x180009e81  mov     rdx, [rbx]
0x180009e84  mov     rcx, rbx
0x180009e87  mov     rax, [rdx+10h]
0x180009e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e90  nop
0x180009e91  jmp     short loc_180009EC3
0x180009e93  mov     rbx, [rsp+48h+arg_8]
0x180009e98  mov     rax, [rbx]
0x180009e9b  mov     r8, rsi
0x180009e9e  mov     rdx, rbp
0x180009ea1  mov     rcx, rbx
0x180009ea4  mov     rax, [rax]
0x180009ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eac  mov     edi, eax
0x180009eae  test    rbx, rbx
0x180009eb1  jz      short loc_180009EC3
0x180009eb3  mov     rdx, [rbx]
0x180009eb6  mov     rcx, rbx
0x180009eb9  mov     rax, [rdx+10h]
0x180009ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ec2  nop
0x180009ec3  mov     eax, edi
0x180009ec5  add     rsp, 28h
0x180009ec9  pop     rdi
0x180009eca  pop     rsi
0x180009ecb  pop     rbp
0x180009ecc  pop     rbx
0x180009ecd  retn
```
