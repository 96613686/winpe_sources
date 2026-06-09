# ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(int *)

- ea: `0x1800c0e30`
- end: `0x1800c0f8d`
- name: `?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAH@Z`
- size: `349`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bfab8`
- `0x1800bfd74`
- `0x1800c0374`
- `0x1800c0b00`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x1800bfa08`
- `0x1800c0e30`
- `0x1800c0f94`
- `0x1800ce8f8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c0ed1`
- `ole32!CoTaskMemFree` at `0x1800c0edb`
- `ole32!CoTaskMemFree` at `0x1800c0ee5`
- `ole32!CoTaskMemFree` at `0x1800c0eee`
- `ole32!CoTaskMemFree` at `0x1800c0f03`
- `ole32!CoTaskMemFree` at `0x1800c0f0d`
- `ole32!CoTaskMemFree` at `0x1800c0f17`
- `ole32!CoTaskMemFree` at `0x1800c0f20`
- `ole32!CoTaskMemFree` at `0x1800c0f55`
- `ole32!CoTaskMemFree` at `0x1800c0f5f`
- `ole32!CoTaskMemFree` at `0x1800c0f69`
- `ole32!CoTaskMemFree` at `0x1800c0f72`
- `ole32!CoTaskMemFree` at `0x1800c0ed1`
- `ole32!CoTaskMemFree` at `0x1800c0edb`
- `ole32!CoTaskMemFree` at `0x1800c0ee5`
- `ole32!CoTaskMemFree` at `0x1800c0eee`
- `ole32!CoTaskMemFree` at `0x1800c0f03`
- `ole32!CoTaskMemFree` at `0x1800c0f0d`
- `ole32!CoTaskMemFree` at `0x1800c0f17`
- `ole32!CoTaskMemFree` at `0x1800c0f20`
- `ole32!CoTaskMemFree` at `0x1800c0f55`
- `ole32!CoTaskMemFree` at `0x1800c0f5f`
- `ole32!CoTaskMemFree` at `0x1800c0f69`
- `ole32!CoTaskMemFree` at `0x1800c0f72`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(
        struct Shield_ForceFieldProviderInfo **this,
        int *a2)
{
  int refreshed; // ebp
  struct Shield_ForceFieldProviderInfo *v5; // r8
  LPVOID *v6; // rbx
  LPVOID *v7; // rdi
  LPVOID *v8; // rax
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v11 = 0x10000008ALL;
  pv = 0;
  refreshed = ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(
                (ShieldProvider::ForceFieldShield *)this,
                (struct PillarStatus *)&v11,
                (struct Shield_ForceFieldProviderInfo **)&pv);
  if ( refreshed < 0 )
  {
    v6 = (LPVOID *)pv;
  }
  else
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v10,
      this + 7);
    if ( !(unsigned __int8)ShieldProvider::IsEqualPillarStatus(v11, this[5]) )
    {
      this[5] = v5;
      *a2 = 1;
    }
    v6 = (LPVOID *)pv;
    if ( !ShieldProvider::ForceFieldShield::IsEqual((struct Shield_ForceFieldProviderInfo *)pv, this[6]) )
    {
      v7 = (LPVOID *)this[6];
      if ( v6 )
      {
        if ( v7 )
        {
          CoTaskMemFree(v7[2]);
          CoTaskMemFree(v7[3]);
          CoTaskMemFree(v7[4]);
          CoTaskMemFree(v7);
        }
        v8 = v6;
        v6 = 0;
        this[6] = (struct Shield_ForceFieldProviderInfo *)v8;
      }
      else if ( v7 )
      {
        CoTaskMemFree(v7[2]);
        CoTaskMemFree(v7[3]);
        CoTaskMemFree(v7[4]);
        CoTaskMemFree(v7);
        this[6] = 0;
      }
      *a2 = 1;
    }
    v10[16] = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v10);
  }
  if ( v6 )
  {
    CoTaskMemFree(v6[2]);
    CoTaskMemFree(v6[3]);
    CoTaskMemFree(v6[4]);
    CoTaskMemFree(v6);
  }
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x1800c0e30  mov     rax, rsp
0x1800c0e33  mov     [rax+8], rbx
0x1800c0e37  mov     [rax+20h], rbp
0x1800c0e3b  push    rsi
0x1800c0e3c  push    rdi
0x1800c0e3d  push    r14
0x1800c0e3f  sub     rsp, 40h
0x1800c0e43  mov     r14, rdx
0x1800c0e46  mov     dword ptr [rdx], 0
0x1800c0e4c  lea     rdx, [rax+10h]; struct PillarStatus *
0x1800c0e50  mov     dword ptr [rax+10h], 8Ah
0x1800c0e57  lea     r8, [rax+18h]; struct Shield_ForceFieldProviderInfo **
0x1800c0e5b  mov     dword ptr [rax+14h], 1
0x1800c0e62  mov     rsi, rcx
0x1800c0e65  mov     qword ptr [rax+18h], 0
0x1800c0e6d  call    ?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAUPillarStatus@@PEAPEAUShield_ForceFieldProviderInfo@@@Z; ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(PillarStatus *,Shield_ForceFieldProviderInfo * *)
0x1800c0e72  mov     ebp, eax
0x1800c0e74  test    eax, eax
0x1800c0e76  js      loc_1800C0F47
0x1800c0e7c  lea     rdx, [rsi+38h]
0x1800c0e80  lea     rcx, [rsp+58h+var_38]
0x1800c0e85  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c0e8a  mov     r8, [rsp+58h+arg_8]
0x1800c0e8f  mov     rdx, [rsi+28h]
0x1800c0e93  mov     rcx, r8
0x1800c0e96  call    ?IsEqualPillarStatus@ShieldProvider@@YA_NUPillarStatus@@0@Z; ShieldProvider::IsEqualPillarStatus(PillarStatus,PillarStatus)
0x1800c0e9b  test    al, al
0x1800c0e9d  jnz     short loc_1800C0EAA
0x1800c0e9f  mov     [rsi+28h], r8
0x1800c0ea3  mov     dword ptr [r14], 1
0x1800c0eaa  mov     rbx, [rsp+58h+pv]
0x1800c0eaf  mov     rdx, [rsi+30h]; struct Shield_ForceFieldProviderInfo *
0x1800c0eb3  mov     rcx, rbx; struct Shield_ForceFieldProviderInfo *
0x1800c0eb6  call    ?IsEqual@ForceFieldShield@ShieldProvider@@CA_NPEAUShield_ForceFieldProviderInfo@@0@Z; ShieldProvider::ForceFieldShield::IsEqual(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo *)
0x1800c0ebb  test    al, al
0x1800c0ebd  jnz     short loc_1800C0F36
0x1800c0ebf  mov     rdi, [rsi+30h]
0x1800c0ec3  test    rbx, rbx
0x1800c0ec6  jnz     short loc_1800C0EFA
0x1800c0ec8  test    rdi, rdi
0x1800c0ecb  jz      short loc_1800C0F2F
0x1800c0ecd  mov     rcx, [rdi+10h]; pv
0x1800c0ed1  call    cs:__imp_CoTaskMemFree
0x1800c0ed7  mov     rcx, [rdi+18h]; pv
0x1800c0edb  call    cs:__imp_CoTaskMemFree
0x1800c0ee1  mov     rcx, [rdi+20h]; pv
0x1800c0ee5  call    cs:__imp_CoTaskMemFree
0x1800c0eeb  mov     rcx, rdi; pv
0x1800c0eee  call    cs:__imp_CoTaskMemFree
0x1800c0ef4  mov     [rsi+30h], rbx
0x1800c0ef8  jmp     short loc_1800C0F2F
0x1800c0efa  test    rdi, rdi
0x1800c0efd  jz      short loc_1800C0F26
0x1800c0eff  mov     rcx, [rdi+10h]; pv
0x1800c0f03  call    cs:__imp_CoTaskMemFree
0x1800c0f09  mov     rcx, [rdi+18h]; pv
0x1800c0f0d  call    cs:__imp_CoTaskMemFree
0x1800c0f13  mov     rcx, [rdi+20h]; pv
0x1800c0f17  call    cs:__imp_CoTaskMemFree
0x1800c0f1d  mov     rcx, rdi; pv
0x1800c0f20  call    cs:__imp_CoTaskMemFree
0x1800c0f26  mov     rax, rbx
0x1800c0f29  xor     ebx, ebx
0x1800c0f2b  mov     [rsi+30h], rax
0x1800c0f2f  mov     dword ptr [r14], 1
0x1800c0f36  lea     rcx, [rsp+58h+var_38]
0x1800c0f3b  mov     [rsp+58h+var_28], 0
0x1800c0f40  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c0f45  jmp     short loc_1800C0F4C
0x1800c0f47  mov     rbx, [rsp+58h+pv]
0x1800c0f4c  test    rbx, rbx
0x1800c0f4f  jz      short loc_1800C0F78
0x1800c0f51  mov     rcx, [rbx+10h]; pv
0x1800c0f55  call    cs:__imp_CoTaskMemFree
0x1800c0f5b  mov     rcx, [rbx+18h]; pv
0x1800c0f5f  call    cs:__imp_CoTaskMemFree
0x1800c0f65  mov     rcx, [rbx+20h]; pv
0x1800c0f69  call    cs:__imp_CoTaskMemFree
0x1800c0f6f  mov     rcx, rbx; pv
0x1800c0f72  call    cs:__imp_CoTaskMemFree
0x1800c0f78  mov     rbx, [rsp+58h+arg_0]
0x1800c0f7d  mov     eax, ebp
0x1800c0f7f  mov     rbp, [rsp+58h+arg_18]
0x1800c0f84  add     rsp, 40h
0x1800c0f88  pop     r14
0x1800c0f8a  pop     rdi
0x1800c0f8b  pop     rsi
0x1800c0f8c  retn
```
