# CDPComActivityStore::GetActivitiesTimeIntersection(CDPComActivityType,CDPComCrossPlatformAppId *,char const *,unsigned __int64,unsigned __int64,ushort,CDPComActivityData * *,ushort *,int)

- ea: `0x180021b90`
- end: `0x180021de8`
- name: `?GetActivitiesTimeIntersection@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEAUCDPComCrossPlatformAppId@@PEBD_K3GPEAPEAUCDPComActivityData@@PEAGH@Z`
- size: `600`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800097d0`
- `0x18000b270`
- `0x18000eb48`
- `0x1800112cc`
- `0x180011450`
- `0x180013908`
- `0x180014cdc`
- `0x180021b3c`
- `0x180021b90`
- `0x180023b70`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021c33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021c33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d47`

## string_xrefs

- `0x180021d91`: `{"text":"Encountered error converting CDPActivity to ComActivityData, returning activities up to this point and abandoning."}`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetActivitiesTimeIntersection(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned __int16 a7,
        _QWORD *a8,
        _WORD *a9,
        int a10)
{
  _QWORD *v13; // r15
  _WORD *v15; // r14
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  int v20; // eax
  int v21; // esi
  LPVOID v22; // rbx
  __int64 v23; // [rsp+60h] [rbp-41h] BYREF
  _QWORD v24[2]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v25; // [rsp+78h] [rbp-29h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v27[10]; // [rsp+90h] [rbp-11h] BYREF
  unsigned int v28; // [rsp+F8h] [rbp+57h]

  v28 = a2;
  v13 = a8;
  if ( !a8 )
  {
    LODWORD(v23) = 2068;
LABEL_3:
    LODWORD(a8) = -2147467261;
LABEL_4:
    Log<long &,char const (&)[27],int>(0, a2, &a8, a4, &v23);
    return (unsigned int)a8;
  }
  v15 = a9;
  if ( !a9 )
  {
    LODWORD(v23) = 2069;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    LODWORD(a8) = -2147024809;
    LODWORD(v23) = 2070;
    goto LABEL_4;
  }
  *a9 = 0;
  *v13 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  v25 = a1 + 32;
  *(_OWORD *)v26 = 0;
  if ( !a3 )
    goto LABEL_14;
  v24[0] = 0;
  v24[1] = v26;
  v16 = CDPCrossPlatformAppIdFromComCrossPlatformAppId(a3, v24);
  cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v24);
  LODWORD(a3) = 0;
  v20 = 0;
  if ( v16 != -2147024809 )
    v20 = v16;
  if ( v20 < 0 )
  {
    LODWORD(a8) = v20;
    LODWORD(v23) = 2088;
    Log<long &,char const (&)[27],int>(v18, v17, &a8, v19, &v23);
    v21 = (int)a8;
  }
  else
  {
LABEL_14:
    std::make_unique<ICDPActivity * [0],0>(&v23, a7);
    LOWORD(a8) = (_WORD)a3;
    v27[0] = &a8;
    v27[1] = &v23;
    v24[0] = v27;
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, std::_Ref_count_base *, __int64, __int64, __int64, __int64, unsigned __int16, _QWORD **, bool))(**(_QWORD **)(a1 + 16) + 72LL))(
            *(_QWORD *)(a1 + 16),
            v28,
            v26[0],
            a4,
            a5,
            a6,
            v23,
            a7,
            &a8,
            a10 != (_DWORD)a3);
    if ( v21 >= 0 && (_WORD)a8 )
    {
      v22 = CoTaskMemAlloc(232LL * (unsigned __int16)a8);
      if ( v22 )
      {
        while ( (unsigned __int16)a3 < (unsigned __int16)a8 )
        {
          v21 = CDPActivityToComActivityData(
                  *(__int64 **)(v23 + 8LL * (unsigned __int16)a3),
                  (__int64)v22 + 232 * (unsigned __int16)a3);
          if ( v21 < 0 )
          {
            Log<>(
              1u,
              "{\"text\":\"Encountered error converting CDPActivity to ComActivityData, returning activities up to this p"
              "oint and abandoning.\"}");
            v21 = 0;
            break;
          }
          LOWORD(a3) = (_WORD)a3 + 1;
        }
        *v13 = v22;
        *v15 = (_WORD)a3;
      }
      else
      {
        v21 = -2147024882;
      }
    }
    ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___::_ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___(v24);
    std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(&v23);
  }
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180021b90  mov     [rsp-8+arg_8], edx
0x180021b94  push    rbp
0x180021b95  push    rbx
0x180021b96  push    rsi
0x180021b97  push    rdi
0x180021b98  push    r12
0x180021b9a  push    r13
0x180021b9c  push    r14
0x180021b9e  push    r15
0x180021ba0  lea     rbp, [rsp-7]
0x180021ba5  sub     rsp, 0A8h
0x180021bac  mov     r12, r9
0x180021baf  mov     rdi, r8
0x180021bb2  mov     r13, rcx
0x180021bb5  mov     r15, [rbp+3Fh+arg_38]
0x180021bbc  xor     ecx, ecx
0x180021bbe  test    r15, r15
0x180021bc1  jnz     short loc_180021BF4
0x180021bc3  mov     dword ptr [rbp+3Fh+var_80], 814h
0x180021bca  mov     dword ptr [rbp+3Fh+arg_38], 80004003h
0x180021bd4  lea     rax, [rbp+3Fh+var_80]
0x180021bd8  mov     [rsp+0E0h+var_C0], rax
0x180021bdd  lea     r8, [rbp+3Fh+arg_38]
0x180021be4  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180021be9  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x180021bef  jmp     loc_180021DD4
0x180021bf4  mov     r14, [rbp+3Fh+arg_40]
0x180021bfb  test    r14, r14
0x180021bfe  jnz     short loc_180021C09
0x180021c00  mov     dword ptr [rbp+3Fh+var_80], 815h
0x180021c07  jmp     short loc_180021BCA
0x180021c09  movzx   esi, [rbp+3Fh+arg_30]
0x180021c0d  test    si, si
0x180021c10  jnz     short loc_180021C25
0x180021c12  mov     dword ptr [rbp+3Fh+arg_38], 80070057h
0x180021c1c  mov     dword ptr [rbp+3Fh+var_80], 816h
0x180021c23  jmp     short loc_180021BD4
0x180021c25  mov     [r14], cx
0x180021c29  mov     [r15], rcx
0x180021c2c  lea     rbx, [r13+20h]
0x180021c30  mov     rcx, rbx; SRWLock
0x180021c33  call    cs:__imp_AcquireSRWLockShared
0x180021c39  mov     [rbp+3Fh+var_68], rbx
0x180021c3d  xorps   xmm0, xmm0
0x180021c40  movdqu  xmmword ptr [rbp+3Fh+var_60], xmm0
0x180021c45  xor     eax, eax
0x180021c47  test    rdi, rdi
0x180021c4a  jz      short loc_180021CAD
0x180021c4c  mov     [rbp+3Fh+var_78], rax
0x180021c50  lea     rax, [rbp+3Fh+var_60]
0x180021c54  mov     [rbp+3Fh+var_70], rax
0x180021c58  lea     rdx, [rbp+3Fh+var_78]
0x180021c5c  mov     rcx, rdi
0x180021c5f  call    CDPCrossPlatformAppIdFromComCrossPlatformAppId
0x180021c64  mov     ebx, eax
0x180021c66  lea     rcx, [rbp+3Fh+var_78]
0x180021c6a  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x180021c6f  xor     edi, edi
0x180021c71  mov     eax, edi
0x180021c73  cmp     ebx, 80070057h
0x180021c79  cmovnz  eax, ebx
0x180021c7c  test    eax, eax
0x180021c7e  jns     short loc_180021CAD
0x180021c80  mov     dword ptr [rbp+3Fh+arg_38], eax
0x180021c86  mov     dword ptr [rbp+3Fh+var_80], 828h
0x180021c8d  lea     rax, [rbp+3Fh+var_80]
0x180021c91  mov     [rsp+0E0h+var_C0], rax
0x180021c96  lea     r8, [rbp+3Fh+arg_38]
0x180021c9d  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180021ca2  mov     esi, dword ptr [rbp+3Fh+arg_38]
0x180021ca8  jmp     loc_180021DBB
0x180021cad  mov     rdx, rsi
0x180021cb0  lea     rcx, [rbp+3Fh+var_80]
0x180021cb4  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x180021cb9  mov     word ptr [rbp+3Fh+arg_38], di
0x180021cc0  lea     rax, [rbp+3Fh+arg_38]
0x180021cc7  mov     [rbp+3Fh+var_50], rax
0x180021ccb  lea     rax, [rbp+3Fh+var_80]
0x180021ccf  mov     [rbp+3Fh+var_48], rax
0x180021cd3  lea     rax, [rbp+3Fh+var_50]
0x180021cd7  mov     [rbp+3Fh+var_78], rax
0x180021cdb  mov     rcx, [r13+10h]
0x180021cdf  mov     r9, [rbp+3Fh+var_80]
0x180021ce3  mov     rax, [rcx]
0x180021ce6  cmp     [rbp+3Fh+arg_48], edi
0x180021cec  setnz   dl
0x180021cef  mov     [rsp+0E0h+var_98], dl
0x180021cf3  lea     rdx, [rbp+3Fh+arg_38]
0x180021cfa  mov     [rsp+0E0h+var_A0], rdx
0x180021cff  mov     [rsp+0E0h+var_A8], si
0x180021d04  mov     [rsp+0E0h+var_B0], r9
0x180021d09  mov     rdx, [rbp+3Fh+arg_28]
0x180021d0d  mov     [rsp+0E0h+var_B8], rdx
0x180021d12  mov     rdx, [rbp+3Fh+arg_20]
0x180021d16  mov     [rsp+0E0h+var_C0], rdx
0x180021d1b  mov     r9, r12
0x180021d1e  mov     r8, [rbp+3Fh+var_60]
0x180021d22  mov     edx, [rbp+3Fh+arg_8]
0x180021d25  mov     rax, [rax+48h]
0x180021d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d2e  mov     esi, eax
0x180021d30  test    eax, eax
0x180021d32  js      short loc_180021DA9
0x180021d34  movzx   eax, word ptr [rbp+3Fh+arg_38]
0x180021d3b  test    ax, ax
0x180021d3e  jz      short loc_180021DA9
0x180021d40  imul    rcx, rax, 0E8h; cb
0x180021d47  call    cs:__imp_CoTaskMemAlloc
0x180021d4d  mov     rbx, rax
0x180021d50  test    rax, rax
0x180021d53  jnz     short loc_180021D5C
0x180021d55  mov     esi, 8007000Eh
0x180021d5a  jmp     short loc_180021DA9
0x180021d5c  mov     r12d, 1
0x180021d62  cmp     di, word ptr [rbp+3Fh+arg_38]
0x180021d69  jnb     short loc_180021DA2
0x180021d6b  movzx   eax, di
0x180021d6e  imul    rdx, rax, 0E8h
0x180021d75  add     rdx, rbx
0x180021d78  mov     rcx, [rbp+3Fh+var_80]
0x180021d7c  mov     rcx, [rcx+rax*8]
0x180021d80  call    CDPActivityToComActivityData
0x180021d85  mov     esi, eax
0x180021d87  test    eax, eax
0x180021d89  js      short loc_180021D91
0x180021d8b  add     di, r12w
0x180021d8f  jmp     short loc_180021D62
0x180021d91  lea     rdx, aTextEncountere; "{\"text\":\"Encountered error convertin"...
0x180021d98  mov     ecx, r12d
0x180021d9b  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180021da0  xor     esi, esi
0x180021da2  mov     [r15], rbx
0x180021da5  mov     [r14], di
0x180021da9  lea     rcx, [rbp+3Fh+var_78]
0x180021dad  call    ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22______ScopeWarden__lambda_f29fb1899365e5d5175cbe739752ae22___
0x180021db2  lea     rcx, [rbp+3Fh+var_80]
0x180021db6  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x180021dbb  mov     rcx, [rbp+3Fh+var_60+8]; this
0x180021dbf  test    rcx, rcx
0x180021dc2  jz      short loc_180021DC9
0x180021dc4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021dc9  lea     rcx, [rbp+3Fh+var_68]
0x180021dcd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180021dd2  mov     eax, esi
0x180021dd4  add     rsp, 0A8h
0x180021ddb  pop     r15
0x180021ddd  pop     r14
0x180021ddf  pop     r13
0x180021de1  pop     r12
0x180021de3  pop     rdi
0x180021de4  pop     rsi
0x180021de5  pop     rbx
0x180021de6  pop     rbp
0x180021de7  retn
```
