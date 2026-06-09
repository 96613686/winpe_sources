# ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(int *)

- ea: `0x180079d48`
- end: `0x180079ee9`
- name: `?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAH@Z`
- size: `417`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180078840`
- `0x180078ddc`
- `0x18007913c`
- `0x180079a00`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x180078768`
- `0x180079d48`
- `0x180079ef0`
- `0x1800ce8f8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180079df1`
- `ole32!CoTaskMemFree` at `0x180079dfb`
- `ole32!CoTaskMemFree` at `0x180079e05`
- `ole32!CoTaskMemFree` at `0x180079e0f`
- `ole32!CoTaskMemFree` at `0x180079e19`
- `ole32!CoTaskMemFree` at `0x180079e22`
- `ole32!CoTaskMemFree` at `0x180079e37`
- `ole32!CoTaskMemFree` at `0x180079e41`
- `ole32!CoTaskMemFree` at `0x180079e4b`
- `ole32!CoTaskMemFree` at `0x180079e55`
- `ole32!CoTaskMemFree` at `0x180079e5f`
- `ole32!CoTaskMemFree` at `0x180079e68`
- `ole32!CoTaskMemFree` at `0x180079e9d`
- `ole32!CoTaskMemFree` at `0x180079ea7`
- `ole32!CoTaskMemFree` at `0x180079eb1`
- `ole32!CoTaskMemFree` at `0x180079ebb`
- `ole32!CoTaskMemFree` at `0x180079ec5`
- `ole32!CoTaskMemFree` at `0x180079ece`
- `ole32!CoTaskMemFree` at `0x180079df1`
- `ole32!CoTaskMemFree` at `0x180079dfb`
- `ole32!CoTaskMemFree` at `0x180079e05`
- `ole32!CoTaskMemFree` at `0x180079e0f`
- `ole32!CoTaskMemFree` at `0x180079e19`
- `ole32!CoTaskMemFree` at `0x180079e22`
- `ole32!CoTaskMemFree` at `0x180079e37`
- `ole32!CoTaskMemFree` at `0x180079e41`
- `ole32!CoTaskMemFree` at `0x180079e4b`
- `ole32!CoTaskMemFree` at `0x180079e55`
- `ole32!CoTaskMemFree` at `0x180079e5f`
- `ole32!CoTaskMemFree` at `0x180079e68`
- `ole32!CoTaskMemFree` at `0x180079e9d`
- `ole32!CoTaskMemFree` at `0x180079ea7`
- `ole32!CoTaskMemFree` at `0x180079eb1`
- `ole32!CoTaskMemFree` at `0x180079ebb`
- `ole32!CoTaskMemFree` at `0x180079ec5`
- `ole32!CoTaskMemFree` at `0x180079ece`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(
        struct Shield_CloudBackupProviderInfo **this,
        int *a2)
{
  int refreshed; // ebp
  struct Shield_CloudBackupProviderInfo *v5; // r8
  LPVOID *v6; // rbx
  LPVOID *v7; // rdi
  LPVOID *v8; // rax
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v11 = 0x100000080LL;
  pv = 0;
  refreshed = ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(
                (ShieldProvider::DataProtectionShield *)this,
                (struct PillarStatus *)&v11,
                (wchar_t *)&pv);
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
    if ( !ShieldProvider::DataProtectionShield::IsEqual((struct Shield_CloudBackupProviderInfo *)pv, this[6]) )
    {
      v7 = (LPVOID *)this[6];
      if ( v6 )
      {
        if ( v7 )
        {
          CoTaskMemFree(v7[3]);
          CoTaskMemFree(v7[4]);
          CoTaskMemFree(v7[5]);
          CoTaskMemFree(v7[6]);
          CoTaskMemFree(v7[7]);
          CoTaskMemFree(v7);
        }
        v8 = v6;
        v6 = 0;
        this[6] = (struct Shield_CloudBackupProviderInfo *)v8;
      }
      else if ( v7 )
      {
        CoTaskMemFree(v7[3]);
        CoTaskMemFree(v7[4]);
        CoTaskMemFree(v7[5]);
        CoTaskMemFree(v7[6]);
        CoTaskMemFree(v7[7]);
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
    CoTaskMemFree(v6[3]);
    CoTaskMemFree(v6[4]);
    CoTaskMemFree(v6[5]);
    CoTaskMemFree(v6[6]);
    CoTaskMemFree(v6[7]);
    CoTaskMemFree(v6);
  }
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x180079d48  mov     rax, rsp
0x180079d4b  mov     [rax+8], rbx
0x180079d4f  mov     [rax+20h], rbp
0x180079d53  push    rsi
0x180079d54  push    rdi
0x180079d55  push    r14
0x180079d57  sub     rsp, 40h
0x180079d5b  mov     r14, rdx
0x180079d5e  mov     dword ptr [rdx], 0
0x180079d64  lea     rdx, [rax+10h]; struct PillarStatus *
0x180079d68  mov     dword ptr [rax+10h], 80h
0x180079d6f  lea     r8, [rax+18h]; struct Shield_CloudBackupProviderInfo **
0x180079d73  mov     dword ptr [rax+14h], 1
0x180079d7a  mov     rsi, rcx
0x180079d7d  mov     qword ptr [rax+18h], 0
0x180079d85  call    ?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAUPillarStatus@@PEAPEAUShield_CloudBackupProviderInfo@@@Z; ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(PillarStatus *,Shield_CloudBackupProviderInfo * *)
0x180079d8a  mov     ebp, eax
0x180079d8c  test    eax, eax
0x180079d8e  js      loc_180079E8F
0x180079d94  lea     rdx, [rsi+38h]
0x180079d98  lea     rcx, [rsp+58h+var_38]
0x180079d9d  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180079da2  mov     r8, [rsp+58h+arg_8]
0x180079da7  mov     rdx, [rsi+28h]
0x180079dab  mov     rcx, r8
0x180079dae  call    ?IsEqualPillarStatus@ShieldProvider@@YA_NUPillarStatus@@0@Z; ShieldProvider::IsEqualPillarStatus(PillarStatus,PillarStatus)
0x180079db3  test    al, al
0x180079db5  jnz     short loc_180079DC2
0x180079db7  mov     [rsi+28h], r8
0x180079dbb  mov     dword ptr [r14], 1
0x180079dc2  mov     rbx, [rsp+58h+pv]
0x180079dc7  mov     rdx, [rsi+30h]; struct Shield_CloudBackupProviderInfo *
0x180079dcb  mov     rcx, rbx; struct Shield_CloudBackupProviderInfo *
0x180079dce  call    ?IsEqual@DataProtectionShield@ShieldProvider@@CA_NPEAUShield_CloudBackupProviderInfo@@0@Z; ShieldProvider::DataProtectionShield::IsEqual(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo *)
0x180079dd3  test    al, al
0x180079dd5  jnz     loc_180079E7E
0x180079ddb  mov     rdi, [rsi+30h]
0x180079ddf  test    rbx, rbx
0x180079de2  jnz     short loc_180079E2E
0x180079de4  test    rdi, rdi
0x180079de7  jz      loc_180079E77
0x180079ded  mov     rcx, [rdi+18h]; pv
0x180079df1  call    cs:__imp_CoTaskMemFree
0x180079df7  mov     rcx, [rdi+20h]; pv
0x180079dfb  call    cs:__imp_CoTaskMemFree
0x180079e01  mov     rcx, [rdi+28h]; pv
0x180079e05  call    cs:__imp_CoTaskMemFree
0x180079e0b  mov     rcx, [rdi+30h]; pv
0x180079e0f  call    cs:__imp_CoTaskMemFree
0x180079e15  mov     rcx, [rdi+38h]; pv
0x180079e19  call    cs:__imp_CoTaskMemFree
0x180079e1f  mov     rcx, rdi; pv
0x180079e22  call    cs:__imp_CoTaskMemFree
0x180079e28  mov     [rsi+30h], rbx
0x180079e2c  jmp     short loc_180079E77
0x180079e2e  test    rdi, rdi
0x180079e31  jz      short loc_180079E6E
0x180079e33  mov     rcx, [rdi+18h]; pv
0x180079e37  call    cs:__imp_CoTaskMemFree
0x180079e3d  mov     rcx, [rdi+20h]; pv
0x180079e41  call    cs:__imp_CoTaskMemFree
0x180079e47  mov     rcx, [rdi+28h]; pv
0x180079e4b  call    cs:__imp_CoTaskMemFree
0x180079e51  mov     rcx, [rdi+30h]; pv
0x180079e55  call    cs:__imp_CoTaskMemFree
0x180079e5b  mov     rcx, [rdi+38h]; pv
0x180079e5f  call    cs:__imp_CoTaskMemFree
0x180079e65  mov     rcx, rdi; pv
0x180079e68  call    cs:__imp_CoTaskMemFree
0x180079e6e  mov     rax, rbx
0x180079e71  xor     ebx, ebx
0x180079e73  mov     [rsi+30h], rax
0x180079e77  mov     dword ptr [r14], 1
0x180079e7e  lea     rcx, [rsp+58h+var_38]
0x180079e83  mov     [rsp+58h+var_28], 0
0x180079e88  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180079e8d  jmp     short loc_180079E94
0x180079e8f  mov     rbx, [rsp+58h+pv]
0x180079e94  test    rbx, rbx
0x180079e97  jz      short loc_180079ED4
0x180079e99  mov     rcx, [rbx+18h]; pv
0x180079e9d  call    cs:__imp_CoTaskMemFree
0x180079ea3  mov     rcx, [rbx+20h]; pv
0x180079ea7  call    cs:__imp_CoTaskMemFree
0x180079ead  mov     rcx, [rbx+28h]; pv
0x180079eb1  call    cs:__imp_CoTaskMemFree
0x180079eb7  mov     rcx, [rbx+30h]; pv
0x180079ebb  call    cs:__imp_CoTaskMemFree
0x180079ec1  mov     rcx, [rbx+38h]; pv
0x180079ec5  call    cs:__imp_CoTaskMemFree
0x180079ecb  mov     rcx, rbx; pv
0x180079ece  call    cs:__imp_CoTaskMemFree
0x180079ed4  mov     rbx, [rsp+58h+arg_0]
0x180079ed9  mov     eax, ebp
0x180079edb  mov     rbp, [rsp+58h+arg_18]
0x180079ee0  add     rsp, 40h
0x180079ee4  pop     r14
0x180079ee6  pop     rdi
0x180079ee7  pop     rsi
0x180079ee8  retn
```
