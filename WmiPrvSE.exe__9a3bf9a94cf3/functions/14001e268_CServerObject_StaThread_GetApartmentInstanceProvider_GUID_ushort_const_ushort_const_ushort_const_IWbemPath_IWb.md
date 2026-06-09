# CServerObject_StaThread::GetApartmentInstanceProvider(_GUID *,ushort const *,ushort const *,ushort const *,IWbemPath *,IWbemServices *,long,IWbemContext *,ushort const *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x14001e268`
- end: `0x14001e562`
- name: `?GetApartmentInstanceProvider@CServerObject_StaThread@@QEAAJPEAU_GUID@@PEBG11PEAUIWbemPath@@PEAUIWbemServices@@JPEAUIWbemContext@@1AEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `762`
- prototype: `__int64 __usercall@<rax>(CServerObject_StaThread *__hidden this@<rcx>, struct _GUID *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct IWbemPath *, struct IWbemServices *, int, struct IWbemContext *, const unsigned __int16 *, struct CServerObject_ProviderRegistrationV1 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001d55c`

## callees

- `0x14000a530`
- `0x14001cbf4`
- `0x14001e268`
- `0x14001e568`
- `0x14001e5d0`
- `0x14001e688`
- `0x14001e910`
- `0x140020740`
- `0x1400234b8`
- `0x140028708`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001e2e7`
- `wbemcomn!GetMemLogObject` at `0x14001e511`
- `wbemcomn!GetMemLogObject` at `0x14001e2e7`
- `wbemcomn!GetMemLogObject` at `0x14001e511`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e2f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e521`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e2f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e521`
- `OLEAUT32!__imp_SysAllocString` at `0x14001e2a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14001e4fb`
- `OLEAUT32!__imp_SysAllocString` at `0x14001e2a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14001e4fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_StaThread::GetApartmentInstanceProvider(
        CServerObject_StaThread *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWbemPath *a6,
        IUnknown *a7,
        int a8,
        IUnknown *a9,
        unsigned __int16 *a10,
        struct CServerObject_ProviderRegistrationV1 *a11)
{
  BSTR v14; // rax
  const unsigned __int16 *v15; // r12
  int v16; // ebx
  CMemoryLog *v17; // rax
  int v18; // r15d
  StaTask_Create *v19; // rax
  const unsigned __int16 *v20; // r9
  StaTask_Create *v21; // rsi
  struct IWbemServices *v22; // r13
  _QWORD *v23; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  BSTR v27; // rax
  CMemoryLog *MemLogObject; // rax
  StaTask_Create *v29; // [rsp+A0h] [rbp+8h] BYREF
  struct _GUID *v30; // [rsp+A8h] [rbp+10h]

  v30 = a2;
  *((_QWORD *)this + 52) = a2;
  if ( a3 )
  {
    v27 = SysAllocString(a3);
    *((_QWORD *)this + 53) = v27;
    if ( !v27 )
    {
      MemLogObject = GetMemLogObject();
      v16 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = 18;
        v26 = 2147749894LL;
        goto LABEL_26;
      }
      return (unsigned int)v16;
    }
  }
  if ( !a4 || (v14 = SysAllocString(a4), (*((_QWORD *)this + 54) = v14) != 0) )
  {
    v15 = a10;
    v16 = CServerObject_StaThread::SetScope(this, a10);
    if ( v16 < 0 )
      goto LABEL_6;
    v16 = CServerObject_StaThread::SetNamespace(this, a5);
    if ( v16 < 0 )
      goto LABEL_6;
    v16 = CServerObject_StaThread::SetNamespacePath(this, a6);
    if ( v16 < 0 )
      goto LABEL_6;
    v18 = a8;
    *((_DWORD *)this + 100) = a8;
    v19 = (StaTask_Create *)operator new(0x80u);
    v29 = v19;
    if ( v19 )
      v21 = StaTask_Create::StaTask_Create(v19, *((struct WmiAllocator **)this + 49), this, v20);
    else
      v21 = 0;
    if ( v21 )
    {
      (*(void (__fastcall **)(StaTask_Create *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( (*(unsigned int (__fastcall **)(StaTask_Create *))(*(_QWORD *)v21 + 24LL))(v21) )
        goto LABEL_20;
      v22 = (struct IWbemServices *)a7;
      v16 = StaTask_Create::MarshalContext((LPSTREAM *)v21, a9, a7);
      if ( v16 < 0 )
        goto LABEL_16;
      LODWORD(v29) = 0;
      if ( (*(unsigned int (__fastcall **)(char *, StaTask_Create **, StaTask_Create *))(*((_QWORD *)this + 8) + 96LL))(
             (char *)this + 64,
             &v29,
             v21)
        || (LODWORD(v29) = -1,
            (*(unsigned int (__fastcall **)(StaTask_Create *, StaTask_Create **))(*(_QWORD *)v21 + 72LL))(v21, &v29)) )
      {
LABEL_20:
        v16 = -2147217402;
      }
      else
      {
        v16 = *((_DWORD *)v21 + 20);
        if ( v16 >= 0 )
        {
          v16 = StaTask_Create::UnMarshalOutgoing(v21);
          if ( v16 >= 0 )
            v16 = CServerObject_StaThread::InitializeProvider(
                    this,
                    v30,
                    a3,
                    a4,
                    a5,
                    a6,
                    v22,
                    v18,
                    (struct IWbemContext *)a9,
                    v15,
                    a11);
        }
      }
LABEL_16:
      (*(void (__fastcall **)(StaTask_Create *))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v16 >= 0 )
        goto LABEL_17;
      goto LABEL_6;
    }
  }
  v16 = -2147217402;
LABEL_6:
  v17 = GetMemLogObject();
  CMemoryLog::Write(v17, v16);
LABEL_17:
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = 19;
    v26 = (unsigned int)v16;
LABEL_26:
    WPP_SF_d(v23[2], v25, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, v26);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14001e268  mov     [rsp+arg_10], rbx
0x14001e26d  mov     [rsp+arg_8], rdx
0x14001e272  push    rbp
0x14001e273  push    rsi
0x14001e274  push    rdi
0x14001e275  push    r12
0x14001e277  push    r13
0x14001e279  push    r14
0x14001e27b  push    r15
0x14001e27d  sub     rsp, 60h
0x14001e281  mov     rbp, r9
0x14001e284  mov     r14, r8
0x14001e287  mov     rdi, rcx
0x14001e28a  mov     [rcx+1A0h], rdx
0x14001e291  test    r8, r8
0x14001e294  jnz     loc_14001E4F8
0x14001e29a  test    rbp, rbp
0x14001e29d  jz      short loc_14001E2B8
0x14001e29f  mov     rcx, rbp; psz
0x14001e2a2  call    cs:__imp_SysAllocString
0x14001e2a8  mov     [rdi+1B0h], rax
0x14001e2af  test    rax, rax
0x14001e2b2  jz      loc_14001E4EE
0x14001e2b8  mov     r12, [rsp+98h+arg_48]
0x14001e2c0  mov     rdx, r12; unsigned __int16 *
0x14001e2c3  mov     rcx, rdi; this
0x14001e2c6  call    ?SetScope@CServerObject_StaThread@@QEAAJPEBG@Z; CServerObject_StaThread::SetScope(ushort const *)
0x14001e2cb  mov     ebx, eax
0x14001e2cd  test    eax, eax
0x14001e2cf  js      short loc_14001E2E7
0x14001e2d1  mov     rdx, [rsp+98h+arg_20]; unsigned __int16 *
0x14001e2d9  mov     rcx, rdi; this
0x14001e2dc  call    ?SetNamespace@CServerObject_StaThread@@QEAAJPEBG@Z; CServerObject_StaThread::SetNamespace(ushort const *)
0x14001e2e1  mov     ebx, eax
0x14001e2e3  test    eax, eax
0x14001e2e5  jns     short loc_14001E2FD
0x14001e2e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001e2ed  mov     edx, ebx
0x14001e2ef  mov     rcx, rax
0x14001e2f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001e2f8  jmp     loc_14001E410
0x14001e2fd  mov     rdx, [rsp+98h+arg_28]; struct IWbemPath *
0x14001e305  mov     rcx, rdi; this
0x14001e308  call    ?SetNamespacePath@CServerObject_StaThread@@QEAAJPEAUIWbemPath@@@Z; CServerObject_StaThread::SetNamespacePath(IWbemPath *)
0x14001e30d  mov     ebx, eax
0x14001e30f  test    eax, eax
0x14001e311  js      short loc_14001E2E7
0x14001e313  mov     r15d, [rsp+98h+arg_38]
0x14001e31b  mov     [rdi+190h], r15d
0x14001e322  mov     ecx, 80h; dwBytes
0x14001e327  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001e32c  mov     [rsp+98h+arg_0], rax
0x14001e334  test    rax, rax
0x14001e337  jz      loc_14001E441
0x14001e33d  mov     r8, rdi; struct CServerObject_StaThread *
0x14001e340  mov     rdx, [rdi+188h]; struct WmiAllocator *
0x14001e347  mov     rcx, rax; this
0x14001e34a  call    ??0StaTask_Create@@QEAA@AEAVWmiAllocator@@AEAVCServerObject_StaThread@@PEBG2@Z; StaTask_Create::StaTask_Create(WmiAllocator &,CServerObject_StaThread &,ushort const *,ushort const *)
0x14001e34f  mov     rsi, rax
0x14001e352  test    rsi, rsi
0x14001e355  jz      loc_14001E4EE
0x14001e35b  mov     rax, [rsi]
0x14001e35e  mov     rcx, rsi
0x14001e361  mov     rax, [rax+8]
0x14001e365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e36a  mov     rax, [rsi]
0x14001e36d  mov     rcx, rsi
0x14001e370  mov     rax, [rax+18h]
0x14001e374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e379  test    eax, eax
0x14001e37b  jnz     loc_14001E448
0x14001e381  mov     r13, [rsp+98h+arg_30]
0x14001e389  mov     r8, r13; struct IWbemServices *
0x14001e38c  mov     rdx, [rsp+98h+arg_40]; struct IWbemContext *
0x14001e394  mov     rcx, rsi; this
0x14001e397  call    ?MarshalContext@StaTask_Create@@QEAAJPEAUIWbemContext@@PEAUIWbemServices@@@Z; StaTask_Create::MarshalContext(IWbemContext *,IWbemServices *)
0x14001e39c  mov     ebx, eax
0x14001e39e  test    eax, eax
0x14001e3a0  js      short loc_14001E3F9
0x14001e3a2  lea     rcx, [rdi+40h]
0x14001e3a6  mov     dword ptr [rsp+98h+arg_0], 0
0x14001e3b1  mov     rax, [rcx]
0x14001e3b4  mov     r8, rsi
0x14001e3b7  lea     rdx, [rsp+98h+arg_0]
0x14001e3bf  mov     rax, [rax+60h]
0x14001e3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e3c8  test    eax, eax
0x14001e3ca  jnz     short loc_14001E448
0x14001e3cc  mov     dword ptr [rsp+98h+arg_0], 0FFFFFFFFh
0x14001e3d7  mov     rax, [rsi]
0x14001e3da  lea     rdx, [rsp+98h+arg_0]
0x14001e3e2  mov     rcx, rsi
0x14001e3e5  mov     rax, [rax+48h]
0x14001e3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e3ee  test    eax, eax
0x14001e3f0  jnz     short loc_14001E448
0x14001e3f2  mov     ebx, [rsi+50h]
0x14001e3f5  test    ebx, ebx
0x14001e3f7  jns     short loc_14001E44F
0x14001e3f9  mov     rax, [rsi]
0x14001e3fc  mov     rcx, rsi
0x14001e3ff  mov     rax, [rax+10h]
0x14001e403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e408  test    ebx, ebx
0x14001e40a  js      loc_14001E2E7
0x14001e410  lea     rax, WPP_GLOBAL_Control
0x14001e417  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e41e  cmp     rcx, rax
0x14001e421  jnz     loc_14001E4BD
0x14001e427  mov     eax, ebx
0x14001e429  mov     rbx, [rsp+98h+arg_10]
0x14001e431  add     rsp, 60h
0x14001e435  pop     r15
0x14001e437  pop     r14
0x14001e439  pop     r13
0x14001e43b  pop     r12
0x14001e43d  pop     rdi
0x14001e43e  pop     rsi
0x14001e43f  pop     rbp
0x14001e440  retn
0x14001e441  xor     esi, esi
0x14001e443  jmp     loc_14001E352
0x14001e448  mov     ebx, 80041006h
0x14001e44d  jmp     short loc_14001E3F9
0x14001e44f  mov     rcx, rsi; this
0x14001e452  call    ?UnMarshalOutgoing@StaTask_Create@@QEAAJXZ; StaTask_Create::UnMarshalOutgoing(void)
0x14001e457  mov     ebx, eax
0x14001e459  test    eax, eax
0x14001e45b  js      short loc_14001E3F9
0x14001e45d  mov     rax, [rsp+98h+arg_50]
0x14001e465  mov     [rsp+98h+var_48], rax; struct CServerObject_ProviderRegistrationV1 *
0x14001e46a  mov     [rsp+98h+var_50], r12; unsigned __int16 *
0x14001e46f  mov     rax, [rsp+98h+arg_40]
0x14001e477  mov     [rsp+98h+var_58], rax; struct IWbemContext *
0x14001e47c  mov     [rsp+98h+var_60], r15d; int
0x14001e481  mov     [rsp+98h+var_68], r13; struct IWbemServices *
0x14001e486  mov     rax, [rsp+98h+arg_28]
0x14001e48e  mov     [rsp+98h+var_70], rax; struct IWbemPath *
0x14001e493  mov     rax, [rsp+98h+arg_20]
0x14001e49b  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x14001e4a0  mov     r9, rbp; unsigned __int16 *
0x14001e4a3  mov     r8, r14; unsigned __int16 *
0x14001e4a6  mov     rdx, [rsp+98h+arg_8]; struct _GUID *
0x14001e4ae  mov     rcx, rdi; this
0x14001e4b1  call    ?InitializeProvider@CServerObject_StaThread@@QEAAJPEAU_GUID@@PEBG11PEAUIWbemPath@@PEAUIWbemServices@@JPEAUIWbemContext@@1AEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_StaThread::InitializeProvider(_GUID *,ushort const *,ushort const *,ushort const *,IWbemPath *,IWbemServices *,long,IWbemContext *,ushort const *,CServerObject_ProviderRegistrationV1 &)
0x14001e4b6  mov     ebx, eax
0x14001e4b8  jmp     loc_14001E3F9
0x14001e4bd  test    byte ptr [rcx+1Ch], 4
0x14001e4c1  jz      loc_14001E427
0x14001e4c7  cmp     byte ptr [rcx+19h], 2
0x14001e4cb  jb      loc_14001E427
0x14001e4d1  mov     edx, 13h
0x14001e4d6  mov     r9d, ebx
0x14001e4d9  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14001e4e0  mov     rcx, [rcx+10h]
0x14001e4e4  call    WPP_SF_d
0x14001e4e9  jmp     loc_14001E427
0x14001e4ee  mov     ebx, 80041006h
0x14001e4f3  jmp     loc_14001E2E7
0x14001e4f8  mov     rcx, r14; psz
0x14001e4fb  call    cs:__imp_SysAllocString
0x14001e501  mov     [rdi+1A8h], rax
0x14001e508  test    rax, rax
0x14001e50b  jnz     loc_14001E29A
0x14001e511  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001e517  mov     ebx, 80041006h
0x14001e51c  mov     edx, ebx
0x14001e51e  mov     rcx, rax
0x14001e521  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001e527  lea     rax, WPP_GLOBAL_Control
0x14001e52e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e535  cmp     rcx, rax
0x14001e538  jz      loc_14001E427
0x14001e53e  test    byte ptr [rcx+1Ch], 4
0x14001e542  jz      loc_14001E427
0x14001e548  cmp     byte ptr [rcx+19h], 2
0x14001e54c  jb      loc_14001E427
0x14001e552  mov     edx, 12h
0x14001e557  mov     r9d, 80041006h
0x14001e55d  jmp     loc_14001E4D9
```
