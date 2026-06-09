# CInterceptor_IWbemSyncProvider::InternalEx_ProvideEvents(bool,IWbemObjectSink *,long)

- ea: `0x14001b75c`
- end: `0x14001ba08`
- name: `?InternalEx_ProvideEvents@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIWbemObjectSink@@J@Z`
- size: `684`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, bool, struct IWbemObjectSink *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001b6e0`
- `0x14003a940`

## callees

- `0x14001b638`
- `0x14001b75c`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001b7d4`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001b8bc`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001b7d4`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001b8bc`
- `wbemcomn!GetMemLogObject` at `0x14001b8f7`
- `wbemcomn!GetMemLogObject` at `0x14001b9be`
- `wbemcomn!GetMemLogObject` at `0x14001b8f7`
- `wbemcomn!GetMemLogObject` at `0x14001b9be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b907`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b9c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b907`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b9c9`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_ProvideEvents(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        struct IWbemObjectSink *a3,
        unsigned int a4)
{
  struct IUnknown *v8; // r8
  int v9; // edi
  CMemoryLog *v11; // rax
  __int64 v12; // rcx
  struct IUnknown *v13; // rdx
  const struct _GUID *v14; // r8
  CMemoryLog *MemLogObject; // rax
  int v16; // [rsp+40h] [rbp-11h]
  struct IUnknown *v17; // [rsp+48h] [rbp-9h]
  int v18; // [rsp+68h] [rbp+17h] BYREF
  int v19[3]; // [rsp+6Ch] [rbp+1Bh] BYREF
  struct IUnknown *v20; // [rsp+78h] [rbp+27h] BYREF
  struct IServerSecurity *v21; // [rsp+80h] [rbp+2Fh] BYREF
  struct IUnknown *v22; // [rsp+88h] [rbp+37h] BYREF
  int v23; // [rsp+B8h] [rbp+67h] BYREF

  if ( *((_QWORD *)this + 44) )
  {
    WmiSetAndCommitObject(
      qword_1400613E8,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a4);
    v8 = (struct IUnknown *)*((_QWORD *)this + 44);
    v18 = 0;
    v22 = 0;
    v21 = 0;
    *(_QWORD *)&v19[1] = 0;
    v23 = 0;
    v20 = 0;
    v9 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           this,
           a2,
           v8,
           &IID_IWbemEventProvider,
           3u,
           &v18,
           &v22,
           &v21,
           v19,
           (struct IUnknown **)&v19[1],
           &v23,
           &v20);
    if ( v9 >= 0 )
    {
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 34);
      v12 = *(_QWORD *)&v19[1];
      ++*((_QWORD *)this + 102);
      v9 = (*(__int64 (__fastcall **)(__int64, struct IWbemObjectSink *, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, a3, a4);
      CInterceptor_IWbemSyncProvider::End_Interface_Events(this, v13, v14, 3u, v18, v22, v21, v16, v17, v23, v20);
    }
    WmiSetAndCommitObject(
      qword_140061458,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a4);
    if ( v9 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v9);
    }
    return (unsigned int)v9;
  }
  else
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2147217372);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749924LL);
    }
    return 2147749924LL;
  }
}

```

## disassembly

```asm
0x14001b75c  mov     r11, rsp
0x14001b75f  mov     [r11+10h], rbx
0x14001b763  mov     [r11+18h], rsi
0x14001b767  push    rbp
0x14001b768  push    rdi
0x14001b769  push    r14
0x14001b76b  lea     rbp, [r11-5Fh]
0x14001b76f  sub     rsp, 90h
0x14001b776  cmp     qword ptr [rcx+160h], 0
0x14001b77e  mov     esi, r9d
0x14001b781  mov     r14, r8
0x14001b784  mov     dil, dl
0x14001b787  mov     rbx, rcx
0x14001b78a  jz      loc_14001B8F7
0x14001b790  mov     rax, [rcx+278h]
0x14001b797  mov     edx, 1
0x14001b79c  mov     r9, [rcx+258h]
0x14001b7a3  mov     r8, [rcx+270h]
0x14001b7aa  mov     dword ptr [rsp+0A0h+var_68], esi
0x14001b7ae  mov     [r11-78h], rax
0x14001b7b2  mov     rax, [rcx+260h]
0x14001b7b9  mov     r9, [r9+40h]
0x14001b7bd  mov     [r11-80h], rax
0x14001b7c1  mov     rax, [rcx+268h]
0x14001b7c8  mov     rcx, cs:qword_1400613E8
0x14001b7cf  mov     qword ptr [rsp+0A0h+var_80], rax
0x14001b7d4  call    cs:__imp_WmiSetAndCommitObject
0x14001b7da  mov     r8, [rbx+160h]; struct IUnknown *
0x14001b7e1  lea     rax, [rbp+57h+var_30]
0x14001b7e5  mov     [rsp+0A0h+var_48], rax; struct IUnknown **
0x14001b7ea  lea     r9, IID_IWbemEventProvider; struct _GUID *
0x14001b7f1  lea     rax, [rbp+57h+arg_0]
0x14001b7f5  mov     [rbp+57h+var_40], 0
0x14001b7fc  mov     [rsp+0A0h+var_50], rax; int *
0x14001b801  mov     dl, dil; bool
0x14001b804  lea     rax, [rbp+57h+var_3C+4]
0x14001b808  mov     [rbp+57h+var_20], 0
0x14001b810  mov     [rsp+0A0h+var_58], rax; struct IUnknown **
0x14001b815  mov     rcx, rbx; this
0x14001b818  lea     rax, [rbp+57h+var_3C]
0x14001b81c  mov     [rbp+57h+var_28], 0
0x14001b824  mov     [rsp+0A0h+var_60], rax; struct IUnknown *
0x14001b829  lea     rax, [rbp+57h+var_28]
0x14001b82d  mov     [rsp+0A0h+var_68], rax; int
0x14001b832  lea     rax, [rbp+57h+var_20]
0x14001b836  mov     [rsp+0A0h+var_70], rax; struct IUnknown **
0x14001b83b  lea     rax, [rbp+57h+var_40]
0x14001b83f  mov     [rsp+0A0h+var_78], rax; int *
0x14001b844  mov     [rsp+0A0h+var_80], 3; unsigned int
0x14001b84c  mov     qword ptr [rbp+57h+var_3C+4], 0
0x14001b854  mov     [rbp+57h+arg_0], 0
0x14001b85b  mov     [rbp+57h+var_30], 0
0x14001b863  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001b868  mov     edi, eax
0x14001b86a  test    eax, eax
0x14001b86c  jns     loc_14001B94E
0x14001b872  mov     rax, [rbx+278h]
0x14001b879  mov     edx, 1
0x14001b87e  mov     r9, [rbx+258h]
0x14001b885  mov     r8, [rbx+270h]
0x14001b88c  mov     rcx, cs:qword_140061458
0x14001b893  mov     dword ptr [rsp+0A0h+var_60], edi
0x14001b897  mov     r9, [r9+40h]
0x14001b89b  mov     dword ptr [rsp+0A0h+var_68], esi
0x14001b89f  mov     [rsp+0A0h+var_70], rax
0x14001b8a4  mov     rax, [rbx+260h]
0x14001b8ab  mov     [rsp+0A0h+var_78], rax
0x14001b8b0  mov     rax, [rbx+268h]
0x14001b8b7  mov     qword ptr [rsp+0A0h+var_80], rax
0x14001b8bc  call    cs:__imp_WmiSetAndCommitObject
0x14001b8c2  test    edi, edi
0x14001b8c4  js      loc_14001B9BE
0x14001b8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8d1  lea     rax, WPP_GLOBAL_Control
0x14001b8d8  cmp     rcx, rax
0x14001b8db  jnz     short loc_14001B928
0x14001b8dd  mov     eax, edi
0x14001b8df  lea     r11, [rsp+0A0h+var_10]
0x14001b8e7  mov     rbx, [r11+28h]
0x14001b8eb  mov     rsi, [r11+30h]
0x14001b8ef  mov     rsp, r11
0x14001b8f2  pop     r14
0x14001b8f4  pop     rdi
0x14001b8f5  pop     rbp
0x14001b8f6  retn
0x14001b8f7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001b8fd  mov     ebx, 80041024h
0x14001b902  mov     rcx, rax
0x14001b905  mov     edx, ebx
0x14001b907  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001b90d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b914  lea     rax, WPP_GLOBAL_Control
0x14001b91b  cmp     rcx, rax
0x14001b91e  jnz     loc_14001B9D4
0x14001b924  mov     eax, ebx
0x14001b926  jmp     short loc_14001B8DF
0x14001b928  test    byte ptr [rcx+1Ch], 4
0x14001b92c  jz      short loc_14001B8DD
0x14001b92e  cmp     byte ptr [rcx+19h], 2
0x14001b932  jb      short loc_14001B8DD
0x14001b934  mov     rcx, [rcx+10h]
0x14001b938  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001b93f  mov     edx, 89h
0x14001b944  mov     r9d, edi
0x14001b947  call    WPP_SF_d
0x14001b94c  jmp     short loc_14001B8DD
0x14001b94e  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14001b955  test    rax, rax
0x14001b958  jnz     short loc_14001B9B5
0x14001b95a  mov     rcx, qword ptr [rbp+57h+var_3C+4]
0x14001b95e  mov     r8d, esi
0x14001b961  inc     qword ptr [rbx+330h]
0x14001b968  mov     rdx, r14
0x14001b96b  mov     rax, [rcx]
0x14001b96e  mov     rax, [rax+18h]
0x14001b972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b977  mov     edi, eax
0x14001b979  mov     r9d, 3; unsigned int
0x14001b97f  mov     rax, [rbp+57h+var_30]
0x14001b983  mov     rcx, rbx; this
0x14001b986  mov     [rsp+0A0h+var_50], rax; struct IUnknown *
0x14001b98b  mov     eax, [rbp+57h+arg_0]
0x14001b98e  mov     dword ptr [rsp+0A0h+var_58], eax; int
0x14001b992  mov     rax, [rbp+57h+var_28]
0x14001b996  mov     [rsp+0A0h+var_70], rax; struct IServerSecurity *
0x14001b99b  mov     rax, [rbp+57h+var_20]
0x14001b99f  mov     [rsp+0A0h+var_78], rax; struct IUnknown *
0x14001b9a4  mov     eax, [rbp+57h+var_40]
0x14001b9a7  mov     [rsp+0A0h+var_80], eax; int
0x14001b9ab  call    ?End_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface_Events(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x14001b9b0  jmp     loc_14001B872
0x14001b9b5  inc     qword ptr [rax+110h]
0x14001b9bc  jmp     short loc_14001B95A
0x14001b9be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001b9c4  mov     rcx, rax
0x14001b9c7  mov     edx, edi
0x14001b9c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001b9cf  jmp     loc_14001B8CA
0x14001b9d4  test    byte ptr [rcx+1Ch], 4
0x14001b9d8  jz      loc_14001B924
0x14001b9de  cmp     byte ptr [rcx+19h], 2
0x14001b9e2  jb      loc_14001B924
0x14001b9e8  mov     rcx, [rcx+10h]
0x14001b9ec  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001b9f3  mov     edx, 8Ah
0x14001b9f8  mov     r9d, 80041024h
0x14001b9fe  call    WPP_SF_d
0x14001ba03  jmp     loc_14001B924
```
