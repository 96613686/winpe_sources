# CInterceptor_IWbemSyncProvider::Helper_DeleteClassAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x140037d60`
- end: `0x140038043`
- name: `?Helper_DeleteClassAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `739`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, int@<edx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140036f10`

## callees

- `0x14000a530`
- `0x14000c190`
- `0x1400234b8`
- `0x140037d60`
- `0x14003c6e0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140037fea`
- `wbemcomn!GetMemLogObject` at `0x140037fea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037ff5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037ff5`
- `OLEAUT32!__imp_SysAllocString` at `0x140037dad`
- `OLEAUT32!__imp_SysAllocString` at `0x140037dad`
- `OLEAUT32!__imp_SysFreeString` at `0x140037fc5`
- `OLEAUT32!__imp_SysFreeString` at `0x140037fc5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140037ec5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140037f3a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140037ec5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140037f3a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037f1f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037f83`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037f1f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037f83`

## string_xrefs

- `0x140037fa2`: `DeleteClassAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_DeleteClassAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  OLECHAR *v11; // r14
  struct IWbemContext *v12; // r10
  unsigned __int64 v13; // rsi
  struct IWbemObjectSink *v14; // rdi
  int v15; // ebx
  int v16; // eax
  char *v17; // rcx
  bool v18; // zf
  void (__fastcall *v19)(char *); // rax
  int v20; // esi
  struct IWbemClassObject *v21; // r8
  unsigned __int16 *v22; // r9
  unsigned int v23; // esi
  struct IWbemServices *v24; // r15
  unsigned int v25; // esi
  CMemoryLog *MemLogObject; // rax
  _QWORD v28[9]; // [rsp+50h] [rbp-48h] BYREF

  v28[0] = 0;
  if ( !a5 || ((int (__fastcall *)(struct IWbemContext *, _QWORD *))a5->lpVtbl->Clone)(a5, v28) >= 0 )
  {
    v11 = SysAllocString(a3);
    if ( v11 )
    {
      v12 = (struct IWbemContext *)operator new(0xB0u);
      a5 = v12;
      v13 = (unsigned __int64)this + 232;
      if ( v12 )
        v14 = (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_DeleteClassAsync::CInterceptor_IWbemSyncObjectSink_DeleteClassAsync(
                                          (__int64)v12,
                                          v13 & -(__int64)(this != 0),
                                          a4 & 0xFFFFFDFF,
                                          (__int64)v11,
                                          (__int64)this,
                                          (__int64)a6,
                                          (__int64)this,
                                          v13 & -(__int64)(this != 0));
      else
        v14 = 0;
      if ( v14 )
      {
        ((void (__fastcall *)(struct IWbemObjectSink *))v14->lpVtbl->AddRef)(v14);
        v15 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))v14->lpVtbl[2].QueryInterface)(v14);
        if ( v15 < 0 )
          goto LABEL_26;
        a5 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 48LL))((char *)this + 232);
        v16 = (*(__int64 (__fastcall **)(char *, struct IWbemObjectSink *, struct IWbemContext **))(*(_QWORD *)v13 + 64LL))(
                (char *)this + 232,
                v14 + 2,
                &a5);
        v17 = (char *)this + 232;
        v18 = v16 == 0;
        v19 = *(void (__fastcall **)(char *))(*(_QWORD *)v13 + 56LL);
        if ( !v18 )
        {
          v19(v17);
          v15 = -2147217402;
LABEL_25:
          CInterceptor_IWbemSyncProvider::SetStatus(this, L"DeleteClassAsync", v21, v22, v15, v14);
          goto LABEL_26;
        }
        v19(v17);
        v20 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
        if ( a2 && CoImpersonateClient() < 0 )
          goto LABEL_12;
        v23 = a4 & v20;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 18);
        ++*((_QWORD *)this + 82);
        v24 = a7;
        v15 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, struct IWbemObjectSink *))a7->lpVtbl->DeleteClassAsync)(
                a7,
                v11,
                v23,
                v28[0],
                v14);
        CoRevertToSelf();
        if ( v15 == -2147217355 || v15 == -2147217400 )
        {
          if ( a2 && CoImpersonateClient() < 0 )
          {
LABEL_12:
            v15 = -2147217405;
            goto LABEL_22;
          }
          v25 = v23 & 0xFFFFFF7F;
          if ( ProviderSubSystem_Globals::s_SharedCounters )
            ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 18);
          ++*((_QWORD *)this + 82);
          v15 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, struct IWbemObjectSink *))v24->lpVtbl->DeleteClassAsync)(
                  v24,
                  v11,
                  v25,
                  v28[0],
                  v14);
          CoRevertToSelf();
        }
LABEL_22:
        if ( v15 < 0 )
          goto LABEL_25;
LABEL_26:
        ((void (__fastcall *)(struct IWbemObjectSink *))v14->lpVtbl->Release)(v14);
        goto LABEL_29;
      }
      SysFreeString(v11);
    }
  }
  v15 = -2147217402;
LABEL_29:
  if ( v28[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
  if ( v15 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140037d60  push    rbx
0x140037d62  push    rbp
0x140037d63  push    rsi
0x140037d64  push    rdi
0x140037d65  push    r12
0x140037d67  push    r14
0x140037d69  push    r15
0x140037d6b  sub     rsp, 60h
0x140037d6f  mov     r15d, r9d
0x140037d72  mov     rbx, r8
0x140037d75  mov     r12d, edx
0x140037d78  mov     rbp, rcx
0x140037d7b  mov     [rsp+98h+var_48], 0
0x140037d84  mov     rcx, [rsp+98h+arg_20]
0x140037d8c  test    rcx, rcx
0x140037d8f  jz      short loc_140037DAA
0x140037d91  mov     rax, [rcx]
0x140037d94  lea     rdx, [rsp+98h+var_48]
0x140037d99  mov     rax, [rax+18h]
0x140037d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037da2  test    eax, eax
0x140037da4  js      loc_140037FCB
0x140037daa  mov     rcx, rbx; psz
0x140037dad  call    cs:__imp_SysAllocString
0x140037db3  mov     r14, rax
0x140037db6  test    rax, rax
0x140037db9  jz      loc_140037FCB
0x140037dbf  mov     ecx, 0B0h; dwBytes
0x140037dc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140037dc9  mov     r10, rax
0x140037dcc  mov     [rsp+98h+arg_20], rax
0x140037dd4  lea     rsi, [rbp+0E8h]
0x140037ddb  test    rax, rax
0x140037dde  jz      short loc_140037E20
0x140037de0  mov     rcx, rbp
0x140037de3  neg     rcx
0x140037de6  sbb     rdx, rdx
0x140037de9  and     rdx, rsi
0x140037dec  mov     r8d, r15d
0x140037def  btr     r8d, 9
0x140037df4  mov     [rsp+98h+var_60], rdx
0x140037df9  mov     [rsp+98h+var_68], rbp
0x140037dfe  mov     rax, [rsp+98h+arg_28]
0x140037e06  mov     [rsp+98h+var_70], rax
0x140037e0b  mov     qword ptr [rsp+98h+var_78], rbp
0x140037e10  mov     r9, r14
0x140037e13  mov     rcx, r10
0x140037e16  call    ??0CInterceptor_IWbemSyncObjectSink_DeleteClassAsync@@QEAA@AEAVWmiAllocator@@JPEAGPEAVCInterceptor_IWbemSyncProvider@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CInterceptor_IWbemSyncObjectSink_DeleteClassAsync::CInterceptor_IWbemSyncObjectSink_DeleteClassAsync(WmiAllocator &,long,ushort *,CInterceptor_IWbemSyncProvider *,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x140037e1b  mov     rdi, rax
0x140037e1e  jmp     short loc_140037E22
0x140037e20  xor     edi, edi
0x140037e22  test    rdi, rdi
0x140037e25  jz      loc_140037FC2
0x140037e2b  mov     rax, [rdi]
0x140037e2e  mov     rcx, rdi
0x140037e31  mov     rax, [rax+8]
0x140037e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e3a  mov     rax, [rdi]
0x140037e3d  mov     rcx, rdi
0x140037e40  mov     rax, [rax+50h]
0x140037e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e49  mov     ebx, eax
0x140037e4b  test    eax, eax
0x140037e4d  js      loc_140037FB1
0x140037e53  mov     [rsp+98h+arg_20], 0
0x140037e5f  mov     rax, [rsi]
0x140037e62  mov     rcx, rsi
0x140037e65  mov     rax, [rax+30h]
0x140037e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e6e  mov     rax, [rsi]
0x140037e71  lea     rdx, [rdi+10h]
0x140037e75  lea     r8, [rsp+98h+arg_20]
0x140037e7d  mov     rcx, rsi
0x140037e80  mov     rax, [rax+40h]
0x140037e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e89  mov     rdx, [rsi]
0x140037e8c  mov     r8, [rdx+38h]
0x140037e90  mov     rcx, rsi
0x140037e93  test    eax, eax
0x140037e95  mov     rax, r8
0x140037e98  jnz     loc_140037F8F
0x140037e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ea3  mov     rax, [rbp+258h]
0x140037eaa  mov     ecx, [rax+6CCh]
0x140037eb0  neg     ecx
0x140037eb2  sbb     esi, esi
0x140037eb4  and     esi, 80h
0x140037eba  add     esi, 0FFFFFD7Fh
0x140037ec0  test    r12d, r12d
0x140037ec3  jz      short loc_140037ED9
0x140037ec5  call    cs:__imp_CoImpersonateClient
0x140037ecb  test    eax, eax
0x140037ecd  jns     short loc_140037ED9
0x140037ecf  mov     ebx, 80041003h
0x140037ed4  jmp     loc_140037F89
0x140037ed9  and     esi, r15d
0x140037edc  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140037ee3  test    rax, rax
0x140037ee6  jz      short loc_140037EEF
0x140037ee8  inc     qword ptr [rax+90h]
0x140037eef  inc     qword ptr [rbp+290h]
0x140037ef6  mov     r15, [rsp+98h+arg_30]
0x140037efe  mov     rax, [r15]
0x140037f01  mov     qword ptr [rsp+98h+var_78], rdi
0x140037f06  mov     r9, [rsp+98h+var_48]
0x140037f0b  mov     r8d, esi
0x140037f0e  mov     rdx, r14
0x140037f11  mov     rcx, r15
0x140037f14  mov     rax, [rax+58h]
0x140037f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037f1d  mov     ebx, eax
0x140037f1f  call    cs:__imp_CoRevertToSelf
0x140037f25  cmp     ebx, 80041035h
0x140037f2b  jz      short loc_140037F35
0x140037f2d  cmp     ebx, 80041008h
0x140037f33  jnz     short loc_140037F89
0x140037f35  test    r12d, r12d
0x140037f38  jz      short loc_140037F44
0x140037f3a  call    cs:__imp_CoImpersonateClient
0x140037f40  test    eax, eax
0x140037f42  js      short loc_140037ECF
0x140037f44  btr     esi, 7
0x140037f48  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140037f4f  test    rax, rax
0x140037f52  jz      short loc_140037F5B
0x140037f54  inc     qword ptr [rax+90h]
0x140037f5b  inc     qword ptr [rbp+290h]
0x140037f62  mov     rax, [r15]
0x140037f65  mov     qword ptr [rsp+98h+var_78], rdi
0x140037f6a  mov     r9, [rsp+98h+var_48]
0x140037f6f  mov     r8d, esi
0x140037f72  mov     rdx, r14
0x140037f75  mov     rcx, r15
0x140037f78  mov     rax, [rax+58h]
0x140037f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037f81  mov     ebx, eax
0x140037f83  call    cs:__imp_CoRevertToSelf
0x140037f89  test    ebx, ebx
0x140037f8b  jns     short loc_140037FB1
0x140037f8d  jmp     short loc_140037F99
0x140037f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037f94  mov     ebx, 80041006h
0x140037f99  mov     [rsp+98h+var_70], rdi; struct IWbemObjectSink *
0x140037f9e  mov     [rsp+98h+var_78], ebx; int
0x140037fa2  lea     rdx, aDeleteclassasy; "DeleteClassAsync"
0x140037fa9  mov     rcx, rbp; this
0x140037fac  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x140037fb1  mov     rax, [rdi]
0x140037fb4  mov     rcx, rdi
0x140037fb7  mov     rax, [rax+10h]
0x140037fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037fc0  jmp     short loc_140037FD0
0x140037fc2  mov     rcx, r14; bstrString
0x140037fc5  call    cs:__imp_SysFreeString
0x140037fcb  mov     ebx, 80041006h
0x140037fd0  mov     rcx, [rsp+98h+var_48]
0x140037fd5  test    rcx, rcx
0x140037fd8  jz      short loc_140037FE6
0x140037fda  mov     rax, [rcx]
0x140037fdd  mov     rax, [rax+10h]
0x140037fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037fe6  test    ebx, ebx
0x140037fe8  jns     short loc_140037FFB
0x140037fea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140037ff0  mov     edx, ebx
0x140037ff2  mov     rcx, rax
0x140037ff5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140037ffb  lea     rax, WPP_GLOBAL_Control
0x140038002  mov     rcx, cs:WPP_GLOBAL_Control
0x140038009  cmp     rcx, rax
0x14003800c  jz      short loc_140038032
0x14003800e  test    byte ptr [rcx+1Ch], 4
0x140038012  jz      short loc_140038032
0x140038014  cmp     byte ptr [rcx+19h], 2
0x140038018  jb      short loc_140038032
0x14003801a  mov     edx, 5Dh ; ']'
0x14003801f  mov     r9d, ebx
0x140038022  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140038029  mov     rcx, [rcx+10h]
0x14003802d  call    WPP_SF_d
0x140038032  mov     eax, ebx
0x140038034  add     rsp, 60h
0x140038038  pop     r15
0x14003803a  pop     r14
0x14003803c  pop     r12
0x14003803e  pop     rdi
0x14003803f  pop     rsi
0x140038040  pop     rbp
0x140038041  pop     rbx
0x140038042  retn
```
