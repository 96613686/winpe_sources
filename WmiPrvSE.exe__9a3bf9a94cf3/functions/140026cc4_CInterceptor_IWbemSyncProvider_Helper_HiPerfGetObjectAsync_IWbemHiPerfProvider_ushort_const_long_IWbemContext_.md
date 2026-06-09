# CInterceptor_IWbemSyncProvider::Helper_HiPerfGetObjectAsync(IWbemHiPerfProvider *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140026cc4`
- end: `0x14002731f`
- name: `?Helper_HiPerfGetObjectAsync@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemHiPerfProvider@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1627`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemHiPerfProvider *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000b7d0`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x1400234b8`
- `0x140026cc4`
- `0x140027328`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140026e8b`
- `wbemcomn!GetMemLogObject` at `0x1400270c9`
- `wbemcomn!GetMemLogObject` at `0x1400271db`
- `wbemcomn!GetMemLogObject` at `0x140027225`
- `wbemcomn!GetMemLogObject` at `0x140026e8b`
- `wbemcomn!GetMemLogObject` at `0x1400270c9`
- `wbemcomn!GetMemLogObject` at `0x1400271db`
- `wbemcomn!GetMemLogObject` at `0x140027225`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140026e97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400270d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400271e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027235`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140026e97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400270d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400271e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027235`
- `OLEAUT32!__imp_SysAllocString` at `0x140026d4d`
- `OLEAUT32!__imp_SysAllocString` at `0x140026d4d`
- `OLEAUT32!__imp_SysFreeString` at `0x140026ef6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002710e`
- `OLEAUT32!__imp_SysFreeString` at `0x140026ef6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002710e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140026d1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140026d1e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026e1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026e7a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026fb9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026fd9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026e1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026e7a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026fb9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140026fd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_HiPerfGetObjectAsync(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemHiPerfProvider *a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6)
{
  OLECHAR *v8; // r12
  HRESULT v9; // edi
  LPVOID v10; // rbx
  BSTR v11; // rax
  OLECHAR *v12; // r13
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // rdi
  int v15; // r15d
  __int64 v16; // r14
  __int64 v17; // rsi
  CMemoryLog *v18; // rax
  CMemoryLog *v20; // rax
  __int64 v21; // rsi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v23; // rax
  __int64 v24; // [rsp+58h] [rbp-59h] BYREF
  __int64 v25; // [rsp+60h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-49h] BYREF
  __int64 v27; // [rsp+70h] [rbp-41h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-39h] BYREF
  __int64 v29; // [rsp+80h] [rbp-31h] BYREF
  _QWORD v30[14]; // [rsp+88h] [rbp-29h] BYREF
  int v33; // [rsp+120h] [rbp+6Fh] BYREF

  v33 = a4;
  v24 = 0;
  ppv = 0;
  v8 = 0;
  v9 = CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, &ppv);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned __int16 *const))(*(_QWORD *)ppv + 24LL))(ppv, 4, a3);
    if ( v9 >= 0 )
    {
      v33 = 0;
      v9 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 168LL))(ppv, &v33, 0);
      if ( v9 >= 0 )
      {
        v8 = (OLECHAR *)operator new(saturated_mul((unsigned int)++v33, 2u));
        if ( v8 )
          v9 = (*(__int64 (__fastcall **)(LPVOID, int *, OLECHAR *))(*(_QWORD *)ppv + 168LL))(ppv, &v33, v8);
        else
          v9 = -2147217402;
      }
    }
  }
  v10 = ppv;
  v30[2] = ppv;
  v30[0] = v8;
  v30[1] = 0;
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v9);
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((__int64)v30);
    if ( v10 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v9;
  }
  v28 = 0;
  v11 = SysAllocString(v8);
  v12 = v11;
  if ( !v11 )
  {
    v23 = GetMemLogObject();
    v9 = -2147217402;
    CMemoryLog::Write(v23, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749894LL);
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((__int64)v30);
    if ( v10 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v9;
  }
  v30[3] = v11;
  v13 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), _QWORD))(**((_QWORD **)this + 52) + 48LL))(
          *((_QWORD *)this + 52),
          v11,
          0,
          0,
          &v28,
          0);
  v14 = v28;
  v30[4] = v28;
  if ( v13 >= 0 )
  {
    v29 = 0;
    v15 = (**v28)(v28, &IID__IWmiObject, &v29);
    v16 = v29;
    v30[5] = v29;
    if ( v15 >= 0 )
    {
      v25 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *const, __int64 *))(*(_QWORD *)v29 + 736LL))(
              v29,
              0,
              a3,
              &v25);
      v21 = v25;
      v27 = v25;
      if ( v15 >= 0 )
        v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(v25, &IID_IWbemClassObject, &v24);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v17 = v24;
    v30[6] = v24;
    if ( v15 >= 0 )
    {
      v15 = ((__int64 (__fastcall *)(struct IWbemHiPerfProvider *, _QWORD, __int64, __int64 *, _DWORD, struct IWbemContext *))a2->lpVtbl->GetObjects)(
              a2,
              *((_QWORD *)this + 52),
              1,
              &v24,
              0,
              a5);
      CoRevertToSelf();
      if ( v15 >= 0 )
      {
        if ( v24 )
        {
          ((void (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))a6->lpVtbl->Indicate)(a6, 1, &v24);
LABEL_14:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              83,
              WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
              (unsigned int)v15);
          }
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v14 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
          SysFreeString(v12);
          if ( v8 )
            operator delete(v8);
          if ( v10 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
          return (unsigned int)v15;
        }
        goto LABEL_12;
      }
      if ( v15 == -2147217372 || v15 == -2147217323 || v15 == -2147467263 || v15 == -2147217396 )
      {
LABEL_12:
        v27 = 0;
        v15 = ((__int64 (__fastcall *)(struct IWbemHiPerfProvider *, _QWORD, _QWORD, __int64 *))a2->lpVtbl->CreateRefresher)(
                a2,
                *((_QWORD *)this + 52),
                0,
                &v27);
        CoRevertToSelf();
        if ( v15 >= 0 )
        {
          v25 = 0;
          v33 = 0;
          v15 = ((__int64 (__fastcall *)(struct IWbemHiPerfProvider *, _QWORD, __int64, __int64, _DWORD, struct IWbemContext *, __int64 *, int *))a2->lpVtbl->CreateRefreshableObject)(
                  a2,
                  *((_QWORD *)this + 52),
                  v24,
                  v27,
                  0,
                  a5,
                  &v25,
                  &v33);
          CoRevertToSelf();
          if ( v15 >= 0 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, 0);
            CoRevertToSelf();
            if ( v15 >= 0 )
              ((void (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))a6->lpVtbl->Indicate)(a6, 1, &v25);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v15 >= 0 )
            goto LABEL_14;
        }
      }
    }
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, v15);
    goto LABEL_14;
  }
  v20 = GetMemLogObject();
  CMemoryLog::Write(v20, -2147217392);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749904LL);
  }
  if ( v14 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
  SysFreeString(v12);
  if ( v8 )
    operator delete(v8);
  if ( v10 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  return 2147749904LL;
}

```

## disassembly

```asm
0x140026cc4  mov     rax, rsp
0x140026cc7  mov     [rax+18h], rbx
0x140026ccb  mov     [rax+20h], r9d
0x140026ccf  mov     [rax+10h], rdx
0x140026cd3  mov     [rax+8], rcx
0x140026cd7  push    rbp
0x140026cd8  push    rsi
0x140026cd9  push    rdi
0x140026cda  push    r12
0x140026cdc  push    r13
0x140026cde  push    r14
0x140026ce0  push    r15
0x140026ce2  lea     rbp, [rax-4Fh]
0x140026ce6  sub     rsp, 0C0h
0x140026ced  mov     rsi, r8
0x140026cf0  mov     r14, rcx
0x140026cf3  xor     r15d, r15d
0x140026cf6  mov     [rbp+47h+var_A0], r15
0x140026cfa  mov     [rbp+47h+var_90], r15
0x140026cfe  mov     r12d, r15d
0x140026d01  lea     rax, [rbp+47h+var_90]
0x140026d05  mov     [rsp+0F0h+ppv], rax; ppv
0x140026d0a  lea     r9, IID_IWbemPath; riid
0x140026d11  xor     edx, edx; pUnkOuter
0x140026d13  lea     r8d, [r15+1]; dwClsContext
0x140026d17  lea     rcx, CLSID_WbemDefPath; rclsid
0x140026d1e  call    cs:__imp_CoCreateInstance
0x140026d24  mov     edi, eax
0x140026d26  test    eax, eax
0x140026d28  jns     loc_14002702D
0x140026d2e  mov     rbx, [rbp+47h+var_90]
0x140026d32  mov     [rbp+47h+var_60], rbx
0x140026d36  mov     [rbp+47h+var_70], r12
0x140026d3a  mov     [rbp+47h+var_68], r15
0x140026d3e  test    edi, edi
0x140026d40  js      loc_1400271DB
0x140026d46  mov     [rbp+47h+var_80], r15
0x140026d4a  mov     rcx, r12; psz
0x140026d4d  call    cs:__imp_SysAllocString
0x140026d53  mov     r13, rax
0x140026d56  test    rax, rax
0x140026d59  jz      loc_140027225
0x140026d5f  mov     [rbp+47h+var_58], rax
0x140026d63  mov     rcx, [r14+1A0h]
0x140026d6a  mov     rax, [rcx]
0x140026d6d  mov     [rsp+0F0h+var_C8], r15
0x140026d72  lea     rdx, [rbp+47h+var_80]
0x140026d76  mov     [rsp+0F0h+ppv], rdx
0x140026d7b  xor     r9d, r9d
0x140026d7e  xor     r8d, r8d
0x140026d81  mov     rdx, r13
0x140026d84  mov     rax, [rax+30h]
0x140026d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026d8d  mov     rdi, [rbp+47h+var_80]
0x140026d91  mov     [rbp+47h+var_50], rdi
0x140026d95  test    eax, eax
0x140026d97  js      loc_1400270C9
0x140026d9d  mov     [rbp+47h+var_78], r15
0x140026da1  mov     rax, [rdi]
0x140026da4  lea     r8, [rbp+47h+var_78]
0x140026da8  lea     rdx, IID__IWmiObject
0x140026daf  mov     rcx, rdi
0x140026db2  mov     rax, [rax]
0x140026db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026dba  mov     r15d, eax
0x140026dbd  mov     r14, [rbp+47h+var_78]
0x140026dc1  mov     [rbp+47h+var_48], r14
0x140026dc5  test    eax, eax
0x140026dc7  jns     loc_14002713A
0x140026dcd  mov     rsi, [rbp+47h+var_A0]
0x140026dd1  mov     [rbp+47h+var_40], rsi
0x140026dd5  test    r15d, r15d
0x140026dd8  js      loc_140026E8B
0x140026dde  mov     r10, [rbp+47h+arg_8]
0x140026de2  mov     rax, [r10]
0x140026de5  mov     rcx, [rbp+47h+arg_20]
0x140026de9  mov     [rsp+0F0h+var_C8], rcx
0x140026dee  mov     dword ptr [rsp+0F0h+ppv], 0
0x140026df6  lea     r9, [rbp+47h+var_A0]
0x140026dfa  mov     r8d, 1
0x140026e00  mov     rcx, [rbp+47h+arg_0]
0x140026e04  mov     rdx, [rcx+1A0h]
0x140026e0b  mov     rcx, r10
0x140026e0e  mov     rax, [rax+40h]
0x140026e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e17  mov     r15d, eax
0x140026e1a  call    cs:__imp_CoRevertToSelf
0x140026e20  test    r15d, r15d
0x140026e23  jns     loc_1400272E8
0x140026e29  cmp     r15d, 80041024h
0x140026e30  jz      short loc_140026E4D
0x140026e32  cmp     r15d, 80041055h
0x140026e39  jz      short loc_140026E4D
0x140026e3b  cmp     r15d, 80004001h
0x140026e42  jz      short loc_140026E4D
0x140026e44  cmp     r15d, 8004100Ch
0x140026e4b  jnz     short loc_140026E8B
0x140026e4d  mov     [rbp+47h+var_88], 0
0x140026e55  mov     rcx, [rbp+47h+arg_8]
0x140026e59  mov     rax, [rcx]
0x140026e5c  lea     r9, [rbp+47h+var_88]
0x140026e60  xor     r8d, r8d
0x140026e63  mov     rdx, [rbp+47h+arg_0]
0x140026e67  mov     rdx, [rdx+1A0h]
0x140026e6e  mov     rax, [rax+20h]
0x140026e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e77  mov     r15d, eax
0x140026e7a  call    cs:__imp_CoRevertToSelf
0x140026e80  xor     edx, edx
0x140026e82  test    r15d, r15d
0x140026e85  jns     loc_140026F6A
0x140026e8b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140026e91  mov     edx, r15d
0x140026e94  mov     rcx, rax
0x140026e97  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140026e9d  lea     rax, WPP_GLOBAL_Control
0x140026ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140026eab  cmp     rcx, rax
0x140026eae  jnz     loc_140026F39
0x140026eb4  test    rsi, rsi
0x140026eb7  jz      short loc_140026EC9
0x140026eb9  mov     rax, [rsi]
0x140026ebc  mov     rcx, rsi
0x140026ebf  mov     rax, [rax+10h]
0x140026ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ec8  nop
0x140026ec9  test    r14, r14
0x140026ecc  jz      short loc_140026EDE
0x140026ece  mov     rax, [r14]
0x140026ed1  mov     rcx, r14
0x140026ed4  mov     rax, [rax+10h]
0x140026ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026edd  nop
0x140026ede  test    rdi, rdi
0x140026ee1  jz      short loc_140026EF3
0x140026ee3  mov     rax, [rdi]
0x140026ee6  mov     rcx, rdi
0x140026ee9  mov     rax, [rax+10h]
0x140026eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ef2  nop
0x140026ef3  mov     rcx, r13; bstrString
0x140026ef6  call    cs:__imp_SysFreeString
0x140026efc  nop
0x140026efd  test    r12, r12
0x140026f00  jnz     loc_140027311
0x140026f06  test    rbx, rbx
0x140026f09  jz      short loc_140026F1B
0x140026f0b  mov     rax, [rbx]
0x140026f0e  mov     rcx, rbx
0x140026f11  mov     rax, [rax+10h]
0x140026f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f1a  nop
0x140026f1b  mov     eax, r15d
0x140026f1e  mov     rbx, [rsp+0F0h+arg_10]
0x140026f26  add     rsp, 0C0h
0x140026f2d  pop     r15
0x140026f2f  pop     r14
0x140026f31  pop     r13
0x140026f33  pop     r12
0x140026f35  pop     rdi
0x140026f36  pop     rsi
0x140026f37  pop     rbp
0x140026f38  retn
0x140026f39  test    byte ptr [rcx+1Ch], 4
0x140026f3d  jz      loc_140026EB4
0x140026f43  cmp     byte ptr [rcx+19h], 2
0x140026f47  jb      loc_140026EB4
0x140026f4d  mov     edx, 53h ; 'S'
0x140026f52  mov     r9d, r15d
0x140026f55  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140026f5c  mov     rcx, [rcx+10h]
0x140026f60  call    WPP_SF_d
0x140026f65  jmp     loc_140026EB4
0x140026f6a  mov     [rbp+47h+var_98], rdx
0x140026f6e  mov     [rbp+47h+arg_18], edx
0x140026f71  mov     r10, [rbp+47h+arg_8]
0x140026f75  mov     rax, [r10]
0x140026f78  lea     rcx, [rbp+47h+arg_18]
0x140026f7c  mov     [rsp+38h], rcx
0x140026f81  lea     rcx, [rbp+47h+var_98]
0x140026f85  mov     [rsp+0F0h+var_C0], rcx
0x140026f8a  mov     rcx, [rbp+47h+arg_20]
0x140026f8e  mov     [rsp+0F0h+var_C8], rcx
0x140026f93  mov     dword ptr [rsp+0F0h+ppv], edx
0x140026f97  mov     r9, [rbp+47h+var_88]
0x140026f9b  mov     r8, [rbp+47h+var_A0]
0x140026f9f  mov     rcx, [rbp+47h+arg_0]
0x140026fa3  mov     rdx, [rcx+1A0h]
0x140026faa  mov     rcx, r10
0x140026fad  mov     rax, [rax+28h]
0x140026fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fb6  mov     r15d, eax
0x140026fb9  call    cs:__imp_CoRevertToSelf
0x140026fbf  test    r15d, r15d
0x140026fc2  js      short loc_140026FF4
0x140026fc4  mov     rcx, [rbp+47h+var_88]
0x140026fc8  mov     rax, [rcx]
0x140026fcb  xor     edx, edx
0x140026fcd  mov     rax, [rax+18h]
0x140026fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fd6  mov     r15d, eax
0x140026fd9  call    cs:__imp_CoRevertToSelf
0x140026fdf  test    r15d, r15d
0x140026fe2  jns     short loc_140027012
0x140026fe4  mov     rcx, [rbp+47h+var_98]
0x140026fe8  mov     rax, [rcx]
0x140026feb  mov     rax, [rax+10h]
0x140026fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026ff4  mov     rcx, [rbp+47h+var_88]
0x140026ff8  mov     rax, [rcx]
0x140026ffb  mov     rax, [rax+10h]
0x140026fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027004  test    r15d, r15d
0x140027007  jns     loc_140026E9D
0x14002700d  jmp     loc_140026E8B
0x140027012  mov     rcx, [rbp+47h+arg_28]
0x140027016  mov     rax, [rcx]
0x140027019  lea     r8, [rbp+47h+var_98]
0x14002701d  mov     edx, 1
0x140027022  mov     rax, [rax+18h]
0x140027026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002702b  jmp     short loc_140026FE4
0x14002702d  mov     rcx, [rbp+47h+var_90]
0x140027031  mov     rax, [rcx]
0x140027034  mov     r8, rsi
0x140027037  mov     edx, 4
0x14002703c  mov     rax, [rax+18h]
0x140027040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027045  mov     edi, eax
0x140027047  test    eax, eax
0x140027049  js      loc_140026D2E
0x14002704f  mov     [rbp+47h+arg_18], r15d
0x140027053  mov     rcx, [rbp+47h+var_90]
0x140027057  mov     rax, [rcx]
0x14002705a  xor     r8d, r8d
0x14002705d  lea     rdx, [rbp+47h+arg_18]
0x140027061  mov     rax, [rax+0A8h]
0x140027068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002706d  mov     edi, eax
0x14002706f  test    eax, eax
0x140027071  js      loc_140026D2E
0x140027077  mov     eax, [rbp+47h+arg_18]
0x14002707a  inc     eax
0x14002707c  mov     [rbp+47h+arg_18], eax
0x14002707f  mov     ecx, eax
0x140027081  mov     eax, 2
0x140027086  mul     rcx
0x140027089  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140027090  cmovb   rax, rcx
0x140027094  mov     rcx, rax; dwBytes
0x140027097  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002709c  mov     r12, rax
0x14002709f  test    rax, rax
0x1400270a2  jz      loc_1400271D1
0x1400270a8  mov     rcx, [rbp+47h+var_90]
0x1400270ac  mov     rdx, [rcx]
0x1400270af  mov     rax, [rdx+0A8h]
0x1400270b6  mov     r8, r12
0x1400270b9  lea     rdx, [rbp+47h+arg_18]
0x1400270bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270c2  mov     edi, eax
0x1400270c4  jmp     loc_140026D2E
0x1400270c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400270cf  mov     esi, 80041010h
0x1400270d4  mov     edx, esi
0x1400270d6  mov     rcx, rax
0x1400270d9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400270df  lea     rax, WPP_GLOBAL_Control
0x1400270e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270ed  cmp     rcx, rax
0x1400270f0  jnz     loc_140027286
0x1400270f6  test    rdi, rdi
0x1400270f9  jz      short loc_14002710B
0x1400270fb  mov     rax, [rdi]
0x1400270fe  mov     rcx, rdi
0x140027101  mov     rax, [rax+10h]
0x140027105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002710a  nop
0x14002710b  mov     rcx, r13; bstrString
0x14002710e  call    cs:__imp_SysFreeString
0x140027114  nop
0x140027115  test    r12, r12
0x140027118  jnz     loc_1400272BA
0x14002711e  test    rbx, rbx
0x140027121  jz      short loc_140027133
0x140027123  mov     rcx, [rbx]
0x140027126  mov     rax, [rcx+10h]
0x14002712a  mov     rcx, rbx
0x14002712d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027132  nop
0x140027133  mov     eax, esi
0x140027135  jmp     loc_140026F1E
0x14002713a  mov     [rbp+47h+var_98], 0
0x140027142  mov     rax, [r14]
0x140027145  lea     r9, [rbp+47h+var_98]
0x140027149  mov     r8, rsi
0x14002714c  xor     edx, edx
0x14002714e  mov     rcx, r14
0x140027151  mov     rax, [rax+2E0h]
0x140027158  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
