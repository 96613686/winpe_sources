# ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList(void)

- ea: `0x180077130`
- end: `0x1800771d2`
- name: `?ClearCloudBackupProviderList@DataProtectionShield@ShieldProvider@@AEAAXXZ`
- size: `162`
- prototype: `void __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180076894`
- `0x18007963c`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x180077130`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180077161`
- `ole32!CoTaskMemFree` at `0x18007716e`
- `ole32!CoTaskMemFree` at `0x18007717b`
- `ole32!CoTaskMemFree` at `0x180077188`
- `ole32!CoTaskMemFree` at `0x180077195`
- `ole32!CoTaskMemFree` at `0x18007719e`
- `ole32!CoTaskMemFree` at `0x180077161`
- `ole32!CoTaskMemFree` at `0x18007716e`
- `ole32!CoTaskMemFree` at `0x18007717b`
- `ole32!CoTaskMemFree` at `0x180077188`
- `ole32!CoTaskMemFree` at `0x180077195`
- `ole32!CoTaskMemFree` at `0x18007719e`

## pseudocode

```c
void __fastcall ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList(
        ShieldProvider::DataProtectionShield *this)
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
    CoTaskMemFree(*((LPVOID *)*v2 + 3));
    CoTaskMemFree(*((LPVOID *)*v2 + 4));
    CoTaskMemFree(*((LPVOID *)*v2 + 5));
    CoTaskMemFree(*((LPVOID *)*v2 + 6));
    CoTaskMemFree(*((LPVOID *)*v2 + 7));
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
0x180077130  mov     [rsp+arg_0], rbx
0x180077135  push    rdi
0x180077136  sub     rsp, 40h
0x18007713a  mov     rdi, rcx
0x18007713d  lea     rdx, [rcx+38h]
0x180077141  lea     rcx, [rsp+48h+var_28]
0x180077146  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18007714b  mov     rbx, [rdi+60h]
0x18007714f  mov     [rsp+48h+var_18], 1
0x180077154  cmp     rbx, [rdi+68h]
0x180077158  jz      short loc_1800771AA
0x18007715a  mov     rcx, [rbx]
0x18007715d  mov     rcx, [rcx+18h]; pv
0x180077161  call    cs:__imp_CoTaskMemFree
0x180077167  mov     rcx, [rbx]
0x18007716a  mov     rcx, [rcx+20h]; pv
0x18007716e  call    cs:__imp_CoTaskMemFree
0x180077174  mov     rcx, [rbx]
0x180077177  mov     rcx, [rcx+28h]; pv
0x18007717b  call    cs:__imp_CoTaskMemFree
0x180077181  mov     rcx, [rbx]
0x180077184  mov     rcx, [rcx+30h]; pv
0x180077188  call    cs:__imp_CoTaskMemFree
0x18007718e  mov     rcx, [rbx]
0x180077191  mov     rcx, [rcx+38h]; pv
0x180077195  call    cs:__imp_CoTaskMemFree
0x18007719b  mov     rcx, [rbx]; pv
0x18007719e  call    cs:__imp_CoTaskMemFree
0x1800771a4  add     rbx, 8
0x1800771a8  jmp     short loc_180077154
0x1800771aa  mov     rax, [rdi+60h]
0x1800771ae  cmp     rax, [rdi+68h]
0x1800771b2  jz      short loc_1800771B8
0x1800771b4  mov     [rdi+68h], rax
0x1800771b8  lea     rcx, [rsp+48h+var_28]
0x1800771bd  mov     [rsp+48h+var_18], 0
0x1800771c2  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800771c7  mov     rbx, [rsp+48h+arg_0]
0x1800771cc  add     rsp, 40h
0x1800771d0  pop     rdi
0x1800771d1  retn
```
