# ShieldProvider::ForceFieldShield::ClearForceFieldProviderList(void)

- ea: `0x1800be8dc`
- end: `0x1800be964`
- name: `?ClearForceFieldProviderList@ForceFieldShield@ShieldProvider@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(ShieldProvider::ForceFieldShield *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800be518`
- `0x1800c07bc`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x1800be8dc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800be90d`
- `ole32!CoTaskMemFree` at `0x1800be91a`
- `ole32!CoTaskMemFree` at `0x1800be927`
- `ole32!CoTaskMemFree` at `0x1800be930`
- `ole32!CoTaskMemFree` at `0x1800be90d`
- `ole32!CoTaskMemFree` at `0x1800be91a`
- `ole32!CoTaskMemFree` at `0x1800be927`
- `ole32!CoTaskMemFree` at `0x1800be930`

## pseudocode

```c
void __fastcall ShieldProvider::ForceFieldShield::ClearForceFieldProviderList(ShieldProvider::ForceFieldShield *this)
{
  LPVOID *v2; // rbx
  __int64 v3; // rax
  _BYTE v4[16]; // [rsp+20h] [rbp-28h] BYREF
  char v5; // [rsp+30h] [rbp-18h]

  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v4,
    (char *)this + 56);
  v2 = (LPVOID *)*((_QWORD *)this + 12);
  v5 = 1;
  while ( v2 != *((LPVOID **)this + 13) )
  {
    CoTaskMemFree(*((LPVOID *)*v2 + 2));
    CoTaskMemFree(*((LPVOID *)*v2 + 3));
    CoTaskMemFree(*((LPVOID *)*v2 + 4));
    CoTaskMemFree(*v2++);
  }
  v3 = *((_QWORD *)this + 12);
  if ( v3 != *((_QWORD *)this + 13) )
    *((_QWORD *)this + 13) = v3;
  v5 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v4);
}

```

## disassembly

```asm
0x1800be8dc  mov     [rsp+arg_0], rbx
0x1800be8e1  push    rdi
0x1800be8e2  sub     rsp, 40h
0x1800be8e6  mov     rdi, rcx
0x1800be8e9  lea     rdx, [rcx+38h]
0x1800be8ed  lea     rcx, [rsp+48h+var_28]
0x1800be8f2  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800be8f7  mov     rbx, [rdi+60h]
0x1800be8fb  mov     [rsp+48h+var_18], 1
0x1800be900  cmp     rbx, [rdi+68h]
0x1800be904  jz      short loc_1800BE93C
0x1800be906  mov     rcx, [rbx]
0x1800be909  mov     rcx, [rcx+10h]; pv
0x1800be90d  call    cs:__imp_CoTaskMemFree
0x1800be913  mov     rcx, [rbx]
0x1800be916  mov     rcx, [rcx+18h]; pv
0x1800be91a  call    cs:__imp_CoTaskMemFree
0x1800be920  mov     rcx, [rbx]
0x1800be923  mov     rcx, [rcx+20h]; pv
0x1800be927  call    cs:__imp_CoTaskMemFree
0x1800be92d  mov     rcx, [rbx]; pv
0x1800be930  call    cs:__imp_CoTaskMemFree
0x1800be936  add     rbx, 8
0x1800be93a  jmp     short loc_1800BE900
0x1800be93c  mov     rax, [rdi+60h]
0x1800be940  cmp     rax, [rdi+68h]
0x1800be944  jz      short loc_1800BE94A
0x1800be946  mov     [rdi+68h], rax
0x1800be94a  lea     rcx, [rsp+48h+var_28]
0x1800be94f  mov     [rsp+48h+var_18], 0
0x1800be954  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800be959  mov     rbx, [rsp+48h+arg_0]
0x1800be95e  add     rsp, 40h
0x1800be962  pop     rdi
0x1800be963  retn
```
