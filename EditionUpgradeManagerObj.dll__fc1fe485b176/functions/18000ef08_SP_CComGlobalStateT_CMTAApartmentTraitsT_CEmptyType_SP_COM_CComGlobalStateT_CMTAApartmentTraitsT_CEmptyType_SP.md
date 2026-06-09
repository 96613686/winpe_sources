# SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)

- ea: `0x18000ef08`
- end: `0x18000ef71`
- name: `??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012af4`

## callees

- `0x180001e90`
- `0x18000ee34`
- `0x18000ef08`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef32`

## pseudocode

```c
void __fastcall SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      v3 = (void *)v1[8];
      if ( v3 )
      {
        CloseHandle(v3);
        v1[8] = 0;
      }
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v1 + 3));
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v1 + 1));
      operator delete(v1, 0x48u);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000ef08  mov     [rsp+arg_0], rbx
0x18000ef0d  push    rdi
0x18000ef0e  sub     rsp, 20h
0x18000ef12  mov     rbx, [rcx]
0x18000ef15  mov     rdi, rcx
0x18000ef18  test    rbx, rbx
0x18000ef1b  jz      short loc_18000EF66
0x18000ef1d  or      eax, 0FFFFFFFFh
0x18000ef20  lock xadd [rbx], eax
0x18000ef24  cmp     eax, 1
0x18000ef27  jnz     short loc_18000EF5F
0x18000ef29  mov     rcx, [rbx+40h]; hObject
0x18000ef2d  test    rcx, rcx
0x18000ef30  jz      short loc_18000EF40
0x18000ef32  call    cs:__imp_CloseHandle
0x18000ef38  mov     qword ptr [rbx+40h], 0
0x18000ef40  lea     rcx, [rbx+18h]
0x18000ef44  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18000ef49  lea     rcx, [rbx+8]
0x18000ef4d  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18000ef52  mov     edx, 48h ; 'H'; unsigned __int64
0x18000ef57  mov     rcx, rbx; void *
0x18000ef5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ef5f  mov     qword ptr [rdi], 0
0x18000ef66  mov     rbx, [rsp+28h+arg_0]
0x18000ef6b  add     rsp, 20h
0x18000ef6f  pop     rdi
0x18000ef70  retn
```
