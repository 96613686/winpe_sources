# CDPComActivityStore::InitializeForStoreInfo(CDPComActivityStoreInfo *)

- ea: `0x180047ad0`
- end: `0x180047bd1`
- name: `?InitializeForStoreInfo@CDPComActivityStore@@UEAAJPEAUCDPComActivityStoreInfo@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(CDPComActivityStore *__hidden this, struct CDPComActivityStoreInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003678`
- `0x18000b328`
- `0x180014aa0`
- `0x18001e798`
- `0x180023b70`
- `0x180047ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047b19`
- `cdp!CDPCreateActivityStoreInfoInternal` at `0x180047b42`
- `cdp!CDPCreateActivityStoreInfoInternal` at `0x180047b42`
- `cdp!CDPGetActivityStoreForStoreInfoInternal` at `0x180047b9f`
- `cdp!CDPGetActivityStoreForStoreInfoInternal` at `0x180047b9f`

## string_xrefs

- `0x180047b55`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::InitializeForStoreInfo(
        RTL_SRWLOCK *this,
        struct CDPComActivityStoreInfo *a2,
        __int64 a3,
        __int64 a4)
{
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-30h]
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v19; // [rsp+78h] [rbp+28h] BYREF
  int v20; // [rsp+80h] [rbp+30h] BYREF
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF

  if ( a2 )
  {
    v7 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    v16 = v7;
    v21 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    LOBYTE(v8) = *((_DWORD *)a2 + 2) != 0;
    v9 = CDPCreateActivityStoreInfoInternal(*(_QWORD *)a2, v8, &v21);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v17[1] = this + 2;
      v17[0] = 0;
      v14 = CDPGetActivityStoreForStoreInfoInternal(v21, v17);
      cdp::detail::address_of<ICDPActivityStore>::~address_of<ICDPActivityStore>(v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v9,
        v15);
      v19 = v10;
      v20 = 53;
      Log<long &,char const (&)[27],int>(v12, v11, &v19, v13, &v20);
      v14 = v19;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
    return v14;
  }
  else
  {
    v19 = -2147024809;
    v20 = 49;
    Log<long &,char const (&)[27],int>((__int64)this, 0, &v19, a4, &v20);
    return v19;
  }
}

```

## disassembly

```asm
0x180047ad0  mov     [rsp-18h+arg_0], rbx
0x180047ad5  push    rbp
0x180047ad6  push    rsi
0x180047ad7  push    rdi
0x180047ad8  mov     rbp, rsp
0x180047adb  sub     rsp, 50h
0x180047adf  mov     rdi, rdx
0x180047ae2  mov     rsi, rcx
0x180047ae5  test    rdx, rdx
0x180047ae8  jnz     short loc_180047B12
0x180047aea  mov     [rbp+arg_8], 80070057h
0x180047af1  mov     [rbp+arg_10], 31h ; '1'
0x180047af8  lea     rax, [rbp+arg_10]
0x180047afc  mov     qword ptr [rsp+50h+var_30], rax
0x180047b01  lea     r8, [rbp+arg_8]
0x180047b05  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180047b0a  mov     eax, [rbp+arg_8]
0x180047b0d  jmp     loc_180047BC4
0x180047b12  lea     rbx, [rcx+20h]
0x180047b16  mov     rcx, rbx; SRWLock
0x180047b19  call    cs:__imp_AcquireSRWLockExclusive
0x180047b1f  mov     [rbp+var_20], rbx
0x180047b23  mov     [rbp+arg_18], 0
0x180047b2b  lea     rcx, [rbp+arg_18]
0x180047b2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047b34  cmp     dword ptr [rdi+8], 0
0x180047b38  setnz   dl
0x180047b3b  lea     r8, [rbp+arg_18]
0x180047b3f  mov     rcx, [rdi]
0x180047b42  call    cs:__imp_CDPCreateActivityStoreInfoInternal
0x180047b48  mov     ebx, eax
0x180047b4a  test    eax, eax
0x180047b4c  jns     short loc_180047B87
0x180047b4e  mov     rcx, [rbp+18h]; this
0x180047b52  mov     r9d, eax; char *
0x180047b55  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180047b5c  mov     edx, 376h; void *
0x180047b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047b66  mov     [rbp+arg_8], ebx
0x180047b69  mov     [rbp+arg_10], 35h ; '5'
0x180047b70  lea     rax, [rbp+arg_10]
0x180047b74  mov     qword ptr [rsp+50h+var_30], rax
0x180047b79  lea     r8, [rbp+arg_8]
0x180047b7d  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180047b82  mov     ebx, [rbp+arg_8]
0x180047b85  jmp     short loc_180047BB0
0x180047b87  lea     rax, [rsi+10h]
0x180047b8b  mov     [rbp+var_10], rax
0x180047b8f  mov     [rbp+var_18], 0
0x180047b97  lea     rdx, [rbp+var_18]
0x180047b9b  mov     rcx, [rbp+arg_18]
0x180047b9f  call    cs:__imp_CDPGetActivityStoreForStoreInfoInternal
0x180047ba5  mov     ebx, eax
0x180047ba7  lea     rcx, [rbp+var_18]
0x180047bab  call    ??1?$address_of@VICDPActivityStore@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityStore>::~address_of<ICDPActivityStore>(void)
0x180047bb0  lea     rcx, [rbp+arg_18]
0x180047bb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047bb9  lea     rcx, [rbp+var_20]
0x180047bbd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180047bc2  mov     eax, ebx
0x180047bc4  mov     rbx, [rsp+50h+arg_0]
0x180047bc9  add     rsp, 50h
0x180047bcd  pop     rdi
0x180047bce  pop     rsi
0x180047bcf  pop     rbp
0x180047bd0  retn
```
