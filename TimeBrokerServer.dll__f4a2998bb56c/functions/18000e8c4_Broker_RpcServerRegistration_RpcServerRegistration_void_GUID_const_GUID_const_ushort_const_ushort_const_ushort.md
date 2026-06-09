# Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)

- ea: `0x18000e8c4`
- end: `0x18000eb84`
- name: `??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z`
- size: `704`
- prototype: `Broker::RpcServerRegistration *__fastcall(Broker::RpcServerRegistration *this, void *, struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned __int16 *Protseq, const unsigned __int16 *StringSecurityDescriptor, unsigned int, int (*)(void *, void *))`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012028`
- `0x180014224`

## callees

- `0x180003800`
- `0x180003eac`
- `0x18000e8c4`
- `0x180012df4`
- `0x1800132ec`
- `0x180013978`
- `0x180019538`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x18000eb2f`
- `RPCRT4!RpcBindingVectorFree` at `0x18000eb2f`
- `RPCRT4!RpcServerInqBindings` at `0x18000ea88`
- `RPCRT4!RpcServerInqBindings` at `0x18000ea88`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000e982`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000e982`
- `RPCRT4!RpcObjectSetType` at `0x18000e9fb`
- `RPCRT4!RpcObjectSetType` at `0x18000e9fb`
- `RPCRT4!RpcEpRegisterW` at `0x18000eaf5`
- `RPCRT4!RpcEpRegisterW` at `0x18000eaf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb62`

## pseudocode

```c
Broker::RpcServerRegistration *__fastcall Broker::RpcServerRegistration::RpcServerRegistration(
        Broker::RpcServerRegistration *this,
        void *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *Protseq,
        const unsigned __int16 *StringSecurityDescriptor,
        unsigned int a8,
        int (*a9)(void *, void *))
{
  RPC_BINDING_VECTOR **v13; // r14
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned int v18; // esi
  _DWORD *v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // eax
  unsigned int v23; // esi
  void **pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int128 v26; // [rsp+38h] [rbp-28h]
  int v27; // [rsp+48h] [rbp-18h]
  unsigned int v28; // [rsp+50h] [rbp-10h]
  void *SecurityDescriptor; // [rsp+90h] [rbp+30h] BYREF
  Broker::RpcIfRegistration *v30; // [rsp+98h] [rbp+38h]

  *(_QWORD *)this = a2;
  v13 = (RPC_BINDING_VECTOR **)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v30 = (Broker::RpcIfRegistration *)operator new(0x18u);
  v14 = Broker::RpcIfRegistration::RpcIfRegistration(v30, a2, a3, a5, a8, a9);
  *((_QWORD *)this + 1) = v14;
  if ( !v14 )
  {
    *((_QWORD *)&v26 + 1) = 0;
    *(_QWORD *)&v26 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  Broker::StringSecurityDescriptor::StringSecurityDescriptor(&SecurityDescriptor, StringSecurityDescriptor);
  v15 = RpcServerUseProtseqW(Protseq, 0xAu, SecurityDescriptor);
  v16 = v15;
  if ( v15 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v15);
    v26 = 0;
    v27 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v28 = v16;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  if ( a4 )
  {
    v17 = RpcObjectSetType(a4, a3);
    v18 = v17;
    if ( v17 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v17);
      v26 = 0;
      v27 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v28 = v18;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    v19 = operator new[](0x20u);
    *((_QWORD *)this + 3) = v19;
    *v19 = 1;
    *(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = *((_QWORD *)this + 3) + 16LL;
    *(struct _GUID *)*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = *a4;
  }
  v20 = RpcServerInqBindings(v13);
  v21 = v20;
  if ( v20 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v20);
    v26 = 0;
    v27 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v28 = v21;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v22 = RpcEpRegisterW(*(RPC_IF_HANDLE *)this, *v13, *((UUID_VECTOR **)this + 3), 0);
  v23 = v22;
  if ( v22 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v22);
    RpcBindingVectorFree(v13);
    v26 = 0;
    v27 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v28 = v23;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  LocalFree(SecurityDescriptor);
  return this;
}

```

## disassembly

```asm
0x18000e8c4  mov     [rsp-28h+arg_10], rbx
0x18000e8c9  mov     [rsp-28h+arg_18], rsi
0x18000e8ce  push    rbp
0x18000e8cf  push    rdi
0x18000e8d0  push    r12
0x18000e8d2  push    r14
0x18000e8d4  push    r15
0x18000e8d6  mov     rbp, rsp
0x18000e8d9  sub     rsp, 60h
0x18000e8dd  mov     r15, r9
0x18000e8e0  mov     r12, r8
0x18000e8e3  mov     rbx, rdx
0x18000e8e6  mov     rdi, rcx
0x18000e8e9  mov     [rcx], rdx
0x18000e8ec  lea     r14, [rcx+10h]
0x18000e8f0  mov     qword ptr [r14], 0
0x18000e8f7  mov     qword ptr [rcx+18h], 0
0x18000e8ff  mov     ecx, 18h; Size
0x18000e904  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e909  mov     [rbp+arg_8], rax
0x18000e90d  mov     rcx, [rbp+arg_40]
0x18000e911  mov     [rsp+60h+var_38], rcx; int (*)(void *, void *)
0x18000e916  mov     ecx, [rbp+arg_38]
0x18000e919  mov     [rsp+60h+var_40], ecx; unsigned int
0x18000e91d  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x18000e921  mov     r8, r12; struct _GUID *
0x18000e924  mov     rdx, rbx; void *
0x18000e927  mov     rcx, rax; this
0x18000e92a  call    ??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z; Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))
0x18000e92f  nop
0x18000e930  mov     [rdi+8], rax
0x18000e934  test    rax, rax
0x18000e937  jnz     short loc_18000E967
0x18000e939  xorps   xmm0, xmm0
0x18000e93c  movups  [rbp+var_28], xmm0
0x18000e940  lea     rax, aBadAllocation; "bad allocation"
0x18000e947  mov     qword ptr [rbp+var_28], rax
0x18000e94b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e952  mov     [rbp+pExceptionObject], rax
0x18000e956  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000e95d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e961  call    _CxxThrowException_0
0x18000e967  mov     rdx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000e96b  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000e96f  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x18000e974  nop
0x18000e975  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000e979  mov     edx, 0Ah; MaxCalls
0x18000e97e  mov     rcx, [rbp+Protseq]; Protseq
0x18000e982  call    cs:__imp_RpcServerUseProtseqW
0x18000e988  mov     esi, eax
0x18000e98a  test    eax, eax
0x18000e98c  jz      short loc_18000E9E7
0x18000e98e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e995  test    byte ptr [rcx+1Ch], 8
0x18000e999  jz      short loc_18000E9B9
0x18000e99b  cmp     byte ptr [rcx+19h], 2
0x18000e99f  jb      short loc_18000E9B9
0x18000e9a1  mov     edx, 1Bh
0x18000e9a6  mov     r9d, eax
0x18000e9a9  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000e9b0  mov     rcx, [rcx+10h]
0x18000e9b4  call    WPP_SF_d
0x18000e9b9  xorps   xmm0, xmm0
0x18000e9bc  movups  [rbp+var_28], xmm0
0x18000e9c0  mov     ebx, 1
0x18000e9c5  mov     [rbp+var_18], ebx
0x18000e9c8  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000e9cf  mov     [rbp+pExceptionObject], rax
0x18000e9d3  mov     [rbp+var_10], esi
0x18000e9d6  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000e9dd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e9e1  call    _CxxThrowException_0
0x18000e9e7  mov     ebx, 1
0x18000e9ec  test    r15, r15
0x18000e9ef  jz      loc_18000EA85
0x18000e9f5  mov     rdx, r12; TypeUuid
0x18000e9f8  mov     rcx, r15; ObjUuid
0x18000e9fb  call    cs:__imp_RpcObjectSetType
0x18000ea01  mov     esi, eax
0x18000ea03  test    eax, eax
0x18000ea05  jz      short loc_18000EA59
0x18000ea07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea0e  test    byte ptr [rcx+1Ch], 8
0x18000ea12  jz      short loc_18000EA30
0x18000ea14  cmp     byte ptr [rcx+19h], 2
0x18000ea18  jb      short loc_18000EA30
0x18000ea1a  lea     edx, [rbx+1Bh]
0x18000ea1d  mov     r9d, eax
0x18000ea20  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000ea27  mov     rcx, [rcx+10h]
0x18000ea2b  call    WPP_SF_d
0x18000ea30  xorps   xmm0, xmm0
0x18000ea33  movups  [rbp+var_28], xmm0
0x18000ea37  mov     [rbp+var_18], ebx
0x18000ea3a  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ea41  mov     [rbp+pExceptionObject], rax
0x18000ea45  mov     [rbp+var_10], esi
0x18000ea48  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ea4f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ea53  call    _CxxThrowException_0
0x18000ea59  mov     ecx, 20h ; ' '; unsigned __int64
0x18000ea5e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ea63  mov     [rdi+18h], rax
0x18000ea67  mov     [rax], ebx
0x18000ea69  mov     rcx, [rdi+18h]
0x18000ea6d  lea     rax, [rcx+10h]
0x18000ea71  mov     [rcx+8], rax
0x18000ea75  mov     rax, [rdi+18h]
0x18000ea79  mov     rcx, [rax+8]
0x18000ea7d  movups  xmm0, xmmword ptr [r15]
0x18000ea81  movdqu  xmmword ptr [rcx], xmm0
0x18000ea85  mov     rcx, r14; BindingVector
0x18000ea88  call    cs:__imp_RpcServerInqBindings
0x18000ea8e  mov     esi, eax
0x18000ea90  test    eax, eax
0x18000ea92  jz      short loc_18000EAE8
0x18000ea94  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea9b  test    byte ptr [rcx+1Ch], 8
0x18000ea9f  jz      short loc_18000EABF
0x18000eaa1  cmp     byte ptr [rcx+19h], 2
0x18000eaa5  jb      short loc_18000EABF
0x18000eaa7  mov     edx, 1Eh
0x18000eaac  mov     r9d, eax
0x18000eaaf  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000eab6  mov     rcx, [rcx+10h]
0x18000eaba  call    WPP_SF_d
0x18000eabf  xorps   xmm0, xmm0
0x18000eac2  movups  [rbp+var_28], xmm0
0x18000eac6  mov     [rbp+var_18], ebx
0x18000eac9  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ead0  mov     [rbp+pExceptionObject], rax
0x18000ead4  mov     [rbp+var_10], esi
0x18000ead7  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000eade  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000eae2  call    _CxxThrowException_0
0x18000eae8  xor     r9d, r9d; Annotation
0x18000eaeb  mov     r8, [rdi+18h]; UuidVector
0x18000eaef  mov     rdx, [r14]; BindingVector
0x18000eaf2  mov     rcx, [rdi]; IfSpec
0x18000eaf5  call    cs:__imp_RpcEpRegisterW
0x18000eafb  mov     esi, eax
0x18000eafd  test    eax, eax
0x18000eaff  jz      short loc_18000EB5E
0x18000eb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb08  test    byte ptr [rcx+1Ch], 8
0x18000eb0c  jz      short loc_18000EB2C
0x18000eb0e  cmp     byte ptr [rcx+19h], 2
0x18000eb12  jb      short loc_18000EB2C
0x18000eb14  mov     edx, 1Fh
0x18000eb19  mov     r9d, eax
0x18000eb1c  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000eb23  mov     rcx, [rcx+10h]
0x18000eb27  call    WPP_SF_d
0x18000eb2c  mov     rcx, r14; BindingVector
0x18000eb2f  call    cs:__imp_RpcBindingVectorFree
0x18000eb35  xorps   xmm0, xmm0
0x18000eb38  movups  [rbp+var_28], xmm0
0x18000eb3c  mov     [rbp+var_18], ebx
0x18000eb3f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000eb46  mov     [rbp+pExceptionObject], rax
0x18000eb4a  mov     [rbp+var_10], esi
0x18000eb4d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000eb54  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000eb58  call    _CxxThrowException_0
0x18000eb5e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000eb62  call    cs:__imp_LocalFree
0x18000eb68  mov     rax, rdi
0x18000eb6b  lea     r11, [rsp+60h+var_s0]
0x18000eb70  mov     rbx, [r11+40h]
0x18000eb74  mov     rsi, [r11+48h]
0x18000eb78  mov     rsp, r11
0x18000eb7b  pop     r15
0x18000eb7d  pop     r14
0x18000eb7f  pop     r12
0x18000eb81  pop     rdi
0x18000eb82  pop     rbp
0x18000eb83  retn
```
