# Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)

- ea: `0x180020fc4`
- end: `0x180021284`
- name: `??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z`
- size: `704`
- prototype: `Broker::RpcServerRegistration *__fastcall(Broker::RpcServerRegistration *this, void *, struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned __int16 *Protseq, const unsigned __int16 *StringSecurityDescriptor, unsigned int, int (*)(void *, void *))`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ddf0`
- `0x18001fa54`

## callees

- `0x1800030e0`
- `0x180016090`
- `0x18001cf74`
- `0x18001d39c`
- `0x18001d9ac`
- `0x180020eb4`
- `0x180020fc4`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x180021188`
- `RPCRT4!RpcServerInqBindings` at `0x180021188`
- `RPCRT4!RpcEpRegisterW` at `0x1800211f5`
- `RPCRT4!RpcEpRegisterW` at `0x1800211f5`
- `RPCRT4!RpcBindingVectorFree` at `0x18002122f`
- `RPCRT4!RpcBindingVectorFree` at `0x18002122f`
- `RPCRT4!RpcObjectSetType` at `0x1800210fb`
- `RPCRT4!RpcObjectSetType` at `0x1800210fb`
- `RPCRT4!RpcServerUseProtseqW` at `0x180021082`
- `RPCRT4!RpcServerUseProtseqW` at `0x180021082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021262`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021262`

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
  Broker::RpcIfRegistration *v14; // rax
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
0x180020fc4  mov     [rsp-28h+arg_10], rbx
0x180020fc9  mov     [rsp-28h+arg_18], rsi
0x180020fce  push    rbp
0x180020fcf  push    rdi
0x180020fd0  push    r12
0x180020fd2  push    r14
0x180020fd4  push    r15
0x180020fd6  mov     rbp, rsp
0x180020fd9  sub     rsp, 60h
0x180020fdd  mov     r15, r9
0x180020fe0  mov     r12, r8
0x180020fe3  mov     rbx, rdx
0x180020fe6  mov     rdi, rcx
0x180020fe9  mov     [rcx], rdx
0x180020fec  lea     r14, [rcx+10h]
0x180020ff0  mov     qword ptr [r14], 0
0x180020ff7  mov     qword ptr [rcx+18h], 0
0x180020fff  mov     ecx, 18h; Size
0x180021004  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021009  mov     [rbp+arg_8], rax
0x18002100d  mov     rcx, [rbp+arg_40]
0x180021011  mov     [rsp+60h+var_38], rcx; int (*)(void *, void *)
0x180021016  mov     ecx, [rbp+arg_38]
0x180021019  mov     [rsp+60h+var_40], ecx; unsigned int
0x18002101d  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x180021021  mov     r8, r12; struct _GUID *
0x180021024  mov     rdx, rbx; void *
0x180021027  mov     rcx, rax; this
0x18002102a  call    ??0RpcIfRegistration@Broker@@QEAA@PEAXPEBU_GUID@@PEBGKP6AJ00@Z@Z; Broker::RpcIfRegistration::RpcIfRegistration(void *,_GUID const *,ushort const *,ulong,long (*)(void *,void *))
0x18002102f  nop
0x180021030  mov     [rdi+8], rax
0x180021034  test    rax, rax
0x180021037  jnz     short loc_180021067
0x180021039  xorps   xmm0, xmm0
0x18002103c  movups  [rbp+var_28], xmm0
0x180021040  lea     rax, aBadAllocation; "bad allocation"
0x180021047  mov     qword ptr [rbp+var_28], rax
0x18002104b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180021052  mov     [rbp+pExceptionObject], rax
0x180021056  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002105d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180021061  call    _CxxThrowException_0
0x180021067  mov     rdx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002106b  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002106f  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180021074  nop
0x180021075  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180021079  mov     edx, 0Ah; MaxCalls
0x18002107e  mov     rcx, [rbp+Protseq]; Protseq
0x180021082  call    cs:__imp_RpcServerUseProtseqW
0x180021088  mov     esi, eax
0x18002108a  test    eax, eax
0x18002108c  jz      short loc_1800210E7
0x18002108e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021095  test    byte ptr [rcx+1Ch], 8
0x180021099  jz      short loc_1800210B9
0x18002109b  cmp     byte ptr [rcx+19h], 2
0x18002109f  jb      short loc_1800210B9
0x1800210a1  mov     edx, 1Bh
0x1800210a6  mov     r9d, eax
0x1800210a9  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800210b0  mov     rcx, [rcx+10h]
0x1800210b4  call    WPP_SF_d
0x1800210b9  xorps   xmm0, xmm0
0x1800210bc  movups  [rbp+var_28], xmm0
0x1800210c0  mov     ebx, 1
0x1800210c5  mov     [rbp+var_18], ebx
0x1800210c8  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800210cf  mov     [rbp+pExceptionObject], rax
0x1800210d3  mov     [rbp+var_10], esi
0x1800210d6  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800210dd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800210e1  call    _CxxThrowException_0
0x1800210e7  mov     ebx, 1
0x1800210ec  test    r15, r15
0x1800210ef  jz      loc_180021185
0x1800210f5  mov     rdx, r12; TypeUuid
0x1800210f8  mov     rcx, r15; ObjUuid
0x1800210fb  call    cs:__imp_RpcObjectSetType
0x180021101  mov     esi, eax
0x180021103  test    eax, eax
0x180021105  jz      short loc_180021159
0x180021107  mov     rcx, cs:WPP_GLOBAL_Control
0x18002110e  test    byte ptr [rcx+1Ch], 8
0x180021112  jz      short loc_180021130
0x180021114  cmp     byte ptr [rcx+19h], 2
0x180021118  jb      short loc_180021130
0x18002111a  lea     edx, [rbx+1Bh]
0x18002111d  mov     r9d, eax
0x180021120  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180021127  mov     rcx, [rcx+10h]
0x18002112b  call    WPP_SF_d
0x180021130  xorps   xmm0, xmm0
0x180021133  movups  [rbp+var_28], xmm0
0x180021137  mov     [rbp+var_18], ebx
0x18002113a  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180021141  mov     [rbp+pExceptionObject], rax
0x180021145  mov     [rbp+var_10], esi
0x180021148  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18002114f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180021153  call    _CxxThrowException_0
0x180021159  mov     ecx, 20h ; ' '; unsigned __int64
0x18002115e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180021163  mov     [rdi+18h], rax
0x180021167  mov     [rax], ebx
0x180021169  mov     rcx, [rdi+18h]
0x18002116d  lea     rax, [rcx+10h]
0x180021171  mov     [rcx+8], rax
0x180021175  mov     rax, [rdi+18h]
0x180021179  mov     rcx, [rax+8]
0x18002117d  movups  xmm0, xmmword ptr [r15]
0x180021181  movdqu  xmmword ptr [rcx], xmm0
0x180021185  mov     rcx, r14; BindingVector
0x180021188  call    cs:__imp_RpcServerInqBindings
0x18002118e  mov     esi, eax
0x180021190  test    eax, eax
0x180021192  jz      short loc_1800211E8
0x180021194  mov     rcx, cs:WPP_GLOBAL_Control
0x18002119b  test    byte ptr [rcx+1Ch], 8
0x18002119f  jz      short loc_1800211BF
0x1800211a1  cmp     byte ptr [rcx+19h], 2
0x1800211a5  jb      short loc_1800211BF
0x1800211a7  mov     edx, 1Eh
0x1800211ac  mov     r9d, eax
0x1800211af  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800211b6  mov     rcx, [rcx+10h]
0x1800211ba  call    WPP_SF_d
0x1800211bf  xorps   xmm0, xmm0
0x1800211c2  movups  [rbp+var_28], xmm0
0x1800211c6  mov     [rbp+var_18], ebx
0x1800211c9  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800211d0  mov     [rbp+pExceptionObject], rax
0x1800211d4  mov     [rbp+var_10], esi
0x1800211d7  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800211de  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800211e2  call    _CxxThrowException_0
0x1800211e8  xor     r9d, r9d; Annotation
0x1800211eb  mov     r8, [rdi+18h]; UuidVector
0x1800211ef  mov     rdx, [r14]; BindingVector
0x1800211f2  mov     rcx, [rdi]; IfSpec
0x1800211f5  call    cs:__imp_RpcEpRegisterW
0x1800211fb  mov     esi, eax
0x1800211fd  test    eax, eax
0x1800211ff  jz      short loc_18002125E
0x180021201  mov     rcx, cs:WPP_GLOBAL_Control
0x180021208  test    byte ptr [rcx+1Ch], 8
0x18002120c  jz      short loc_18002122C
0x18002120e  cmp     byte ptr [rcx+19h], 2
0x180021212  jb      short loc_18002122C
0x180021214  mov     edx, 1Fh
0x180021219  mov     r9d, eax
0x18002121c  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180021223  mov     rcx, [rcx+10h]
0x180021227  call    WPP_SF_d
0x18002122c  mov     rcx, r14; BindingVector
0x18002122f  call    cs:__imp_RpcBindingVectorFree
0x180021235  xorps   xmm0, xmm0
0x180021238  movups  [rbp+var_28], xmm0
0x18002123c  mov     [rbp+var_18], ebx
0x18002123f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180021246  mov     [rbp+pExceptionObject], rax
0x18002124a  mov     [rbp+var_10], esi
0x18002124d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180021254  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180021258  call    _CxxThrowException_0
0x18002125e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180021262  call    cs:__imp_LocalFree
0x180021268  mov     rax, rdi
0x18002126b  lea     r11, [rsp+60h+var_s0]
0x180021270  mov     rbx, [r11+40h]
0x180021274  mov     rsi, [r11+48h]
0x180021278  mov     rsp, r11
0x18002127b  pop     r15
0x18002127d  pop     r14
0x18002127f  pop     r12
0x180021281  pop     rdi
0x180021282  pop     rbp
0x180021283  retn
```
