# CInterceptor_IWbemSyncProvider::InternalEx_FindConsumer(bool,IWbemClassObject *,IWbemUnboundObjectSink * *)

- ea: `0x140038b20`
- end: `0x140038df9`
- name: `?InternalEx_FindConsumer@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIWbemClassObject@@PEAPEAUIWbemUnboundObjectSink@@@Z`
- size: `729`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, bool, struct IWbemClassObject *, struct IWbemUnboundObjectSink **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140037370`
- `0x14003a170`

## callees

- `0x14000a530`
- `0x14001b638`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140035f94`
- `0x140038ab0`
- `0x140038b20`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140038d5d`
- `wbemcomn!GetMemLogObject` at `0x140038d97`
- `wbemcomn!GetMemLogObject` at `0x140038d5d`
- `wbemcomn!GetMemLogObject` at `0x140038d97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038d68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038da7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038d68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038da7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_FindConsumer(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        struct IWbemClassObject *a3,
        struct IWbemUnboundObjectSink **a4)
{
  struct IUnknown *v7; // r8
  int v8; // ebx
  struct IUnknown *v9; // rdx
  const struct _GUID *v10; // r8
  LPVOID v11; // rax
  unsigned __int64 v12; // r14
  CInterceptor_IWbemSyncUnboundObjectSink *v13; // rdi
  int v14; // eax
  char *v15; // rcx
  bool v16; // zf
  void (__fastcall *v17)(char *); // rax
  CMemoryLog *MemLogObject; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  int v24; // [rsp+40h] [rbp-31h]
  struct IUnknown *v25; // [rsp+48h] [rbp-29h]
  int v26; // [rsp+68h] [rbp-9h] BYREF
  int v27[3]; // [rsp+6Ch] [rbp-5h] BYREF
  struct IUnknown *v28; // [rsp+78h] [rbp+7h] BYREF
  struct IUnknown *v29; // [rsp+80h] [rbp+Fh] BYREF
  struct IServerSecurity *v30; // [rsp+88h] [rbp+17h] BYREF
  struct IUnknown *v31; // [rsp+90h] [rbp+1Fh] BYREF
  LPVOID v32; // [rsp+D8h] [rbp+67h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 48);
  if ( v7 )
  {
    *(_QWORD *)&v27[1] = 0;
    v26 = 0;
    v31 = 0;
    v30 = 0;
    v28 = 0;
    LODWORD(v32) = 0;
    v29 = 0;
    v8 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           this,
           a2,
           v7,
           &IID_IWbemEventConsumerProvider,
           7u,
           &v26,
           &v31,
           &v30,
           v27,
           &v28,
           (int *)&v32,
           &v29);
    if ( v8 >= 0 )
    {
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 39);
      ++*((_QWORD *)this + 107);
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, int *))v28->lpVtbl[1].QueryInterface)(
             v28,
             a3,
             &v27[1]);
      CInterceptor_IWbemSyncProvider::End_Interface_Events(this, v9, v10, 7u, v26, v31, v30, v24, v25, (int)v32, v29);
      if ( v8 >= 0 && a4 )
      {
        v11 = operator new(0xC0u);
        v32 = v11;
        v12 = (unsigned __int64)this + 232;
        if ( v11 )
          v13 = (CInterceptor_IWbemSyncUnboundObjectSink *)CInterceptor_IWbemSyncUnboundObjectSink::CInterceptor_IWbemSyncUnboundObjectSink(
                                                             v11,
                                                             *((_QWORD *)this + 54),
                                                             *(_QWORD *)&v27[1],
                                                             v12 & -(__int64)(this != 0),
                                                             *((_QWORD *)this + 75));
        else
          v13 = 0;
        if ( v13 )
        {
          (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 8LL))(v13);
          v8 = CInterceptor_IWbemSyncUnboundObjectSink::Initialize(v13);
          if ( v8 >= 0 )
          {
            v32 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 48LL))((char *)this + 232);
            v14 = (*(__int64 (__fastcall **)(char *, __int64, LPVOID *))(*(_QWORD *)v12 + 64LL))(
                    (char *)this + 232,
                    (__int64)v13 + 32,
                    &v32);
            v15 = (char *)this + 232;
            v16 = v14 == 0;
            v17 = *(void (__fastcall **)(char *))(*(_QWORD *)v12 + 56LL);
            if ( v16 )
            {
              v17(v15);
              *a4 = (struct IWbemUnboundObjectSink *)v13;
              (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 8LL))(v13);
            }
            else
            {
              v17(v15);
              v8 = -2147217402;
            }
          }
          (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        else
        {
          v8 = -2147217402;
        }
      }
    }
    if ( *(_QWORD *)&v27[1] )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v27[1] + 16LL))(*(_QWORD *)&v27[1]);
    if ( v8 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 147;
      v21 = (unsigned int)v8;
LABEL_29:
      WPP_SF_d(v19[2], v20, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v21);
    }
  }
  else
  {
    v22 = GetMemLogObject();
    v8 = -2147217372;
    CMemoryLog::Write(v22, -2147217372);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 148;
      v21 = 2147749924LL;
      goto LABEL_29;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140038b20  mov     r11, rsp
0x140038b23  push    rbp
0x140038b24  push    rbx
0x140038b25  push    rsi
0x140038b26  push    rdi
0x140038b27  push    r14
0x140038b29  push    r15
0x140038b2b  lea     rbp, [r11-5Fh]
0x140038b2f  sub     rsp, 98h
0x140038b36  mov     r15, r9
0x140038b39  mov     rdi, r8
0x140038b3c  mov     rsi, rcx
0x140038b3f  mov     r8, [rcx+180h]; struct IUnknown *
0x140038b46  test    r8, r8
0x140038b49  jz      loc_140038D97
0x140038b4f  mov     qword ptr [rbp+57h+var_5C+4], 0
0x140038b57  mov     [rbp+57h+var_60], 0
0x140038b5e  mov     [rbp+57h+var_38], 0
0x140038b66  mov     [rbp+57h+var_40], 0
0x140038b6e  mov     [rbp+57h+var_50], 0
0x140038b76  mov     dword ptr [rbp+57h+arg_0], 0
0x140038b7d  mov     [rbp+57h+var_48], 0
0x140038b85  lea     rax, [rbp+57h+var_48]
0x140038b89  mov     [r11-70h], rax
0x140038b8d  lea     rax, [rbp+57h+arg_0]
0x140038b91  mov     [r11-78h], rax
0x140038b95  lea     rax, [rbp+57h+var_50]
0x140038b99  mov     [r11-80h], rax
0x140038b9d  lea     rax, [rbp+57h+var_5C]
0x140038ba1  mov     [rsp+0C0h+var_80], rax; struct IUnknown *
0x140038ba6  lea     rax, [rbp+57h+var_40]
0x140038baa  mov     [rsp+0C0h+var_88], rax; int
0x140038baf  lea     rax, [rbp+57h+var_38]
0x140038bb3  mov     [rsp+0C0h+var_90], rax; struct IUnknown **
0x140038bb8  lea     rax, [rbp+57h+var_60]
0x140038bbc  mov     [rsp+0C0h+var_98], rax; int *
0x140038bc1  mov     r14d, 7
0x140038bc7  mov     [rsp+0C0h+var_A0], r14d; unsigned int
0x140038bcc  lea     r9, IID_IWbemEventConsumerProvider; struct _GUID *
0x140038bd3  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x140038bd8  mov     ebx, eax
0x140038bda  test    eax, eax
0x140038bdc  js      loc_140038D44
0x140038be2  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140038be9  test    rax, rax
0x140038bec  jz      short loc_140038BF5
0x140038bee  inc     qword ptr [rax+138h]
0x140038bf5  inc     qword ptr [rsi+358h]
0x140038bfc  mov     rcx, [rbp+57h+var_50]
0x140038c00  mov     rax, [rcx]
0x140038c03  lea     r8, [rbp+57h+var_5C+4]
0x140038c07  mov     rdx, rdi
0x140038c0a  mov     rax, [rax+18h]
0x140038c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038c13  mov     ebx, eax
0x140038c15  mov     rax, [rbp+57h+var_48]
0x140038c19  mov     [rsp+50h], rax; struct IUnknown *
0x140038c1e  mov     eax, dword ptr [rbp+57h+arg_0]
0x140038c21  mov     [rsp+0C0h+var_78], eax; int
0x140038c25  mov     rax, [rbp+57h+var_40]
0x140038c29  mov     [rsp+0C0h+var_90], rax; struct IServerSecurity *
0x140038c2e  mov     rax, [rbp+57h+var_38]
0x140038c32  mov     [rsp+0C0h+var_98], rax; struct IUnknown *
0x140038c37  mov     eax, [rbp+57h+var_60]
0x140038c3a  mov     [rsp+0C0h+var_A0], eax; int
0x140038c3e  mov     r9d, r14d; unsigned int
0x140038c41  mov     rcx, rsi; this
0x140038c44  call    ?End_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface_Events(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x140038c49  test    ebx, ebx
0x140038c4b  js      loc_140038D44
0x140038c51  test    r15, r15
0x140038c54  jz      loc_140038D44
0x140038c5a  mov     ecx, 0C0h; dwBytes
0x140038c5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140038c64  mov     [rbp+57h+arg_0], rax
0x140038c68  lea     r14, [rsi+0E8h]
0x140038c6f  test    rax, rax
0x140038c72  jz      short loc_140038CA4
0x140038c74  mov     rcx, rsi
0x140038c77  neg     rcx
0x140038c7a  sbb     r9, r9
0x140038c7d  and     r9, r14
0x140038c80  mov     rcx, [rsi+258h]
0x140038c87  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x140038c8c  mov     r8, qword ptr [rbp+57h+var_5C+4]
0x140038c90  mov     rdx, [rsi+1B0h]
0x140038c97  mov     rcx, rax
0x140038c9a  call    ??0CInterceptor_IWbemSyncUnboundObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@AEAVCServerObject_ProviderRegistrationV1@@@Z; CInterceptor_IWbemSyncUnboundObjectSink::CInterceptor_IWbemSyncUnboundObjectSink(WmiAllocator &,IUnknown *,WmiContainerController<void *> *,CServerObject_ProviderRegistrationV1 &)
0x140038c9f  mov     rdi, rax
0x140038ca2  jmp     short loc_140038CA6
0x140038ca4  xor     edi, edi
0x140038ca6  test    rdi, rdi
0x140038ca9  jz      loc_140038D3F
0x140038caf  mov     rax, [rdi]
0x140038cb2  mov     rcx, rdi
0x140038cb5  mov     rax, [rax+8]
0x140038cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038cbe  mov     rcx, rdi; this
0x140038cc1  call    ?Initialize@CInterceptor_IWbemSyncUnboundObjectSink@@QEAAJXZ; CInterceptor_IWbemSyncUnboundObjectSink::Initialize(void)
0x140038cc6  mov     ebx, eax
0x140038cc8  test    eax, eax
0x140038cca  js      short loc_140038D2E
0x140038ccc  mov     [rbp+57h+arg_0], 0
0x140038cd4  mov     rax, [r14]
0x140038cd7  mov     rcx, r14
0x140038cda  mov     rax, [rax+30h]
0x140038cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ce3  mov     rax, [r14]
0x140038ce6  lea     rdx, [rdi+20h]
0x140038cea  lea     r8, [rbp+57h+arg_0]
0x140038cee  mov     rcx, r14
0x140038cf1  mov     rax, [rax+40h]
0x140038cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038cfa  mov     rdx, [r14]
0x140038cfd  mov     r8, [rdx+38h]
0x140038d01  mov     rcx, r14
0x140038d04  test    eax, eax
0x140038d06  mov     rax, r8
0x140038d09  jnz     short loc_140038D24
0x140038d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d10  mov     [r15], rdi
0x140038d13  mov     rax, [rdi]
0x140038d16  mov     rcx, rdi
0x140038d19  mov     rax, [rax+8]
0x140038d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d22  jmp     short loc_140038D2E
0x140038d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d29  mov     ebx, 80041006h
0x140038d2e  mov     rax, [rdi]
0x140038d31  mov     rcx, rdi
0x140038d34  mov     rax, [rax+10h]
0x140038d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d3d  jmp     short loc_140038D44
0x140038d3f  mov     ebx, 80041006h
0x140038d44  mov     rcx, qword ptr [rbp+57h+var_5C+4]
0x140038d48  test    rcx, rcx
0x140038d4b  jz      short loc_140038D59
0x140038d4d  mov     rax, [rcx]
0x140038d50  mov     rax, [rax+10h]
0x140038d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038d59  test    ebx, ebx
0x140038d5b  jns     short loc_140038D6E
0x140038d5d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140038d63  mov     edx, ebx
0x140038d65  mov     rcx, rax
0x140038d68  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140038d6e  lea     rax, WPP_GLOBAL_Control
0x140038d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d7c  cmp     rcx, rax
0x140038d7f  jz      short loc_140038DE7
0x140038d81  test    byte ptr [rcx+1Ch], 4
0x140038d85  jz      short loc_140038DE7
0x140038d87  cmp     byte ptr [rcx+19h], 2
0x140038d8b  jb      short loc_140038DE7
0x140038d8d  mov     edx, 93h
0x140038d92  mov     r9d, ebx
0x140038d95  jmp     short loc_140038DD7
0x140038d97  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140038d9d  mov     ebx, 80041024h
0x140038da2  mov     edx, ebx
0x140038da4  mov     rcx, rax
0x140038da7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140038dad  lea     rax, WPP_GLOBAL_Control
0x140038db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140038dbb  cmp     rcx, rax
0x140038dbe  jz      short loc_140038DE7
0x140038dc0  test    byte ptr [rcx+1Ch], 4
0x140038dc4  jz      short loc_140038DE7
0x140038dc6  cmp     byte ptr [rcx+19h], 2
0x140038dca  jb      short loc_140038DE7
0x140038dcc  mov     edx, 94h
0x140038dd1  mov     r9d, 80041024h
0x140038dd7  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140038dde  mov     rcx, [rcx+10h]
0x140038de2  call    WPP_SF_d
0x140038de7  mov     eax, ebx
0x140038de9  add     rsp, 98h
0x140038df0  pop     r15
0x140038df2  pop     r14
0x140038df4  pop     rdi
0x140038df5  pop     rsi
0x140038df6  pop     rbx
0x140038df7  pop     rbp
0x140038df8  retn
```
