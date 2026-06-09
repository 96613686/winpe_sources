# ShieldProvider::ForceFieldShield::UpdateForceFieldProviders(Shield_ForceFieldProviderAction,Shield_ForceFieldProviderInfo *)

- ea: `0x1800c18cc`
- end: `0x1800c1a0b`
- name: `?UpdateForceFieldProviders@ForceFieldShield@ShieldProvider@@AEAAJW4Shield_ForceFieldProviderAction@@PEAUShield_ForceFieldProviderInfo@@@Z`
- size: `319`
- prototype: `int __high(enum Shield_ForceFieldProviderAction, struct Shield_ForceFieldProviderInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800bfab8`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18002e0d0`
- `0x18002e1b8`
- `0x1800bebd8`
- `0x1800c18cc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c191f`
- `ole32!CoTaskMemFree` at `0x1800c192c`
- `ole32!CoTaskMemFree` at `0x1800c1939`
- `ole32!CoTaskMemFree` at `0x1800c1942`
- `ole32!CoTaskMemFree` at `0x1800c191f`
- `ole32!CoTaskMemFree` at `0x1800c192c`
- `ole32!CoTaskMemFree` at `0x1800c1939`
- `ole32!CoTaskMemFree` at `0x1800c1942`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::UpdateForceFieldProviders(__int64 a1, int a2, __int64 a3)
{
  LPVOID *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _BYTE v13[16]; // [rsp+20h] [rbp-38h] BYREF
  char v14; // [rsp+30h] [rbp-28h]
  struct Shield_ForceFieldProviderInfo *v15; // [rsp+60h] [rbp+8h] BYREF

  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v13,
    a1 + 56);
  v6 = *(LPVOID **)(a1 + 96);
  v14 = 1;
  while ( v6 != *(LPVOID **)(a1 + 104) )
  {
    v7 = *v6;
    v8 = *(_QWORD *)*v6 - *(_QWORD *)a3;
    if ( !v8 )
      v8 = v7[1] - *(_QWORD *)(a3 + 8);
    if ( v8 )
    {
      ++v6;
    }
    else
    {
      CoTaskMemFree((LPVOID)v7[2]);
      CoTaskMemFree(*((LPVOID *)*v6 + 3));
      CoTaskMemFree(*((LPVOID *)*v6 + 4));
      CoTaskMemFree(*v6);
      std::_Copy_memmove<Shield_ForceFieldProviderInfo * *,Shield_ForceFieldProviderInfo * *>(v6 + 1);
      *(_QWORD *)(a1 + 104) -= 8LL;
    }
  }
  if ( a2 != 2 )
  {
    v15 = 0;
    v9 = ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(
           (struct Shield_ForceFieldProviderInfo *)a3,
           &v15);
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 57;
        goto LABEL_17;
      }
    }
    else
    {
      v9 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(
             a1 + 96,
             &v15);
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 56;
LABEL_17:
          WPP_SF_d(v10[2], v11, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)v9);
        }
      }
    }
  }
  v14 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v13);
  return 0;
}

```

## disassembly

```asm
0x1800c18cc  mov     [rsp+arg_8], rbx
0x1800c18d1  mov     [rsp+arg_10], rbp
0x1800c18d6  push    rsi
0x1800c18d7  push    rdi
0x1800c18d8  push    r14
0x1800c18da  sub     rsp, 40h
0x1800c18de  mov     ebp, edx
0x1800c18e0  mov     rdi, rcx
0x1800c18e3  lea     rdx, [rcx+38h]
0x1800c18e7  mov     rsi, r8
0x1800c18ea  lea     rcx, [rsp+58h+var_38]
0x1800c18ef  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c18f4  mov     rbx, [rdi+60h]
0x1800c18f8  mov     [rsp+58h+var_28], 1
0x1800c18fd  cmp     rbx, [rdi+68h]
0x1800c1901  jz      short loc_1800C1965
0x1800c1903  mov     rcx, [rbx]
0x1800c1906  mov     rax, [rcx]
0x1800c1909  sub     rax, [rsi]
0x1800c190c  jnz     short loc_1800C1916
0x1800c190e  mov     rax, [rcx+8]
0x1800c1912  sub     rax, [rsi+8]
0x1800c1916  test    rax, rax
0x1800c1919  jnz     short loc_1800C195F
0x1800c191b  mov     rcx, [rcx+10h]; pv
0x1800c191f  call    cs:__imp_CoTaskMemFree
0x1800c1925  mov     rcx, [rbx]
0x1800c1928  mov     rcx, [rcx+18h]; pv
0x1800c192c  call    cs:__imp_CoTaskMemFree
0x1800c1932  mov     rcx, [rbx]
0x1800c1935  mov     rcx, [rcx+20h]; pv
0x1800c1939  call    cs:__imp_CoTaskMemFree
0x1800c193f  mov     rcx, [rbx]; pv
0x1800c1942  call    cs:__imp_CoTaskMemFree
0x1800c1948  mov     rdx, [rdi+68h]
0x1800c194c  lea     rcx, [rbx+8]; Src
0x1800c1950  mov     r8, rbx
0x1800c1953  call    ??$_Copy_memmove@PEAPEAUShield_ForceFieldProviderInfo@@PEAPEAU1@@std@@YAPEAPEAUShield_ForceFieldProviderInfo@@PEAPEAU1@00@Z; std::_Copy_memmove<Shield_ForceFieldProviderInfo * *,Shield_ForceFieldProviderInfo * *>(Shield_ForceFieldProviderInfo * *,Shield_ForceFieldProviderInfo * *,Shield_ForceFieldProviderInfo * *)
0x1800c1958  add     qword ptr [rdi+68h], 0FFFFFFFFFFFFFFF8h
0x1800c195d  jmp     short loc_1800C18FD
0x1800c195f  add     rbx, 8
0x1800c1963  jmp     short loc_1800C18FD
0x1800c1965  cmp     ebp, 2
0x1800c1968  jz      short loc_1800C19E7
0x1800c196a  lea     rdx, [rsp+58h+arg_0]; struct Shield_ForceFieldProviderInfo **
0x1800c196f  mov     [rsp+58h+arg_0], 0
0x1800c1978  mov     rcx, rsi; struct Shield_ForceFieldProviderInfo *
0x1800c197b  call    ?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)
0x1800c1980  test    eax, eax
0x1800c1982  js      short loc_1800C19B6
0x1800c1984  lea     rdx, [rsp+58h+arg_0]
0x1800c1989  lea     rcx, [rdi+60h]
0x1800c198d  call    ??$HrStdPushBack@V?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@CommonUtil@@YAJAEAV?$CStdVector@_KV?$allocator@_K@std@@@0@AEB_K@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> &,unsigned __int64 const &)
0x1800c1992  test    eax, eax
0x1800c1994  jns     short loc_1800C19E7
0x1800c1996  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c199d  lea     rdx, WPP_GLOBAL_Control
0x1800c19a4  cmp     rcx, rdx
0x1800c19a7  jz      short loc_1800C19E7
0x1800c19a9  test    byte ptr [rcx+1Ch], 1
0x1800c19ad  jz      short loc_1800C19E7
0x1800c19af  mov     edx, 38h ; '8'
0x1800c19b4  jmp     short loc_1800C19D4
0x1800c19b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c19bd  lea     rdx, WPP_GLOBAL_Control
0x1800c19c4  cmp     rcx, rdx
0x1800c19c7  jz      short loc_1800C19E7
0x1800c19c9  test    byte ptr [rcx+1Ch], 1
0x1800c19cd  jz      short loc_1800C19E7
0x1800c19cf  mov     edx, 39h ; '9'
0x1800c19d4  mov     rcx, [rcx+10h]
0x1800c19d8  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c19df  mov     r9d, eax
0x1800c19e2  call    WPP_SF_d
0x1800c19e7  lea     rcx, [rsp+58h+var_38]
0x1800c19ec  mov     [rsp+58h+var_28], 0
0x1800c19f1  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c19f6  mov     rbx, [rsp+58h+arg_8]
0x1800c19fb  xor     eax, eax
0x1800c19fd  mov     rbp, [rsp+58h+arg_10]
0x1800c1a02  add     rsp, 40h
0x1800c1a06  pop     r14
0x1800c1a08  pop     rdi
0x1800c1a09  pop     rsi
0x1800c1a0a  retn
```
