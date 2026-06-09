# ShieldProvider::DataProtectionShield::UpdateCloudBackupProviders(Shield_CloudBackupProviderAction,Shield_CloudBackupProviderInfo *)

- ea: `0x18007afdc`
- end: `0x18007b208`
- name: `?UpdateCloudBackupProviders@DataProtectionShield@ShieldProvider@@AEAAJW4Shield_CloudBackupProviderAction@@PEAUShield_CloudBackupProviderInfo@@@Z`
- size: `556`
- prototype: `int __high(enum Shield_CloudBackupProviderAction, struct Shield_CloudBackupProviderInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180078840`

## callees

- `0x180001a1c`
- `0x180001a48`
- `0x180004710`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18002e0d0`
- `0x1800775dc`
- `0x18007afdc`
- `0x1800e3ea4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007b045`
- `ole32!CoTaskMemFree` at `0x18007b052`
- `ole32!CoTaskMemFree` at `0x18007b05f`
- `ole32!CoTaskMemFree` at `0x18007b06c`
- `ole32!CoTaskMemFree` at `0x18007b079`
- `ole32!CoTaskMemFree` at `0x18007b082`
- `ole32!CoTaskMemFree` at `0x18007b045`
- `ole32!CoTaskMemFree` at `0x18007b052`
- `ole32!CoTaskMemFree` at `0x18007b05f`
- `ole32!CoTaskMemFree` at `0x18007b06c`
- `ole32!CoTaskMemFree` at `0x18007b079`
- `ole32!CoTaskMemFree` at `0x18007b082`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::UpdateCloudBackupProviders(__int64 a1, int a2, __int64 a3)
{
  LPVOID *v6; // rbx
  char *v7; // rcx
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  struct Shield_CloudBackupProviderInfo *v12; // [rsp+30h] [rbp-69h] BYREF
  __int64 v13; // [rsp+38h] [rbp-61h] BYREF
  int v14; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-51h] BYREF
  char v16; // [rsp+58h] [rbp-41h]
  char v17[32]; // [rsp+60h] [rbp-39h] BYREF
  struct Shield_CloudBackupProviderInfo **v18; // [rsp+80h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp-11h]
  int *v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  char *v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]
  __int64 *v24; // [rsp+B0h] [rbp+17h]
  __int64 v25; // [rsp+B8h] [rbp+1Fh]

  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v15,
    a1 + 56);
  v6 = *(LPVOID **)(a1 + 96);
  v16 = 1;
  while ( v6 != *(LPVOID **)(a1 + 104) )
  {
    v7 = (char *)*v6;
    if ( *(_QWORD *)((char *)*v6 + 4) == *(_QWORD *)(a3 + 4) && *(_QWORD *)(v7 + 12) == *(_QWORD *)(a3 + 12) )
    {
      CoTaskMemFree(*((LPVOID *)v7 + 3));
      CoTaskMemFree(*((LPVOID *)*v6 + 4));
      CoTaskMemFree(*((LPVOID *)*v6 + 5));
      CoTaskMemFree(*((LPVOID *)*v6 + 6));
      CoTaskMemFree(*((LPVOID *)*v6 + 7));
      CoTaskMemFree(*v6);
      memmove_0(v6, v6 + 1, *(_QWORD *)(a1 + 104) - (_QWORD)(v6 + 1));
      *(_QWORD *)(a1 + 104) -= 8LL;
    }
    else
    {
      ++v6;
    }
  }
  if ( a2 != 2 )
  {
    v12 = 0;
    v8 = ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(
           (struct Shield_CloudBackupProviderInfo *)a3,
           (LPVOID **)&v12);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 68;
        goto LABEL_16;
      }
    }
    else
    {
      v8 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(
             a1 + 96,
             &v12);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 67;
LABEL_16:
          WPP_SF_d(v9[2], v10, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)v8);
        }
      }
    }
  }
  v16 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v15);
  if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
  {
    LODWORD(v13) = *(_DWORD *)(a3 + 72);
    HIDWORD(v13) = *(_DWORD *)(a3 + 68);
    v14 = *(_DWORD *)(a3 + 64);
    v24 = &v13;
    v22 = (char *)&v13 + 4;
    v20 = &v14;
    v18 = &v12;
    LODWORD(v12) = a2;
    v25 = 4;
    v23 = 4;
    v21 = 4;
    v19 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18012F2B8, &unk_180122008, 0, 0, 6, v17, v12, v13, v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18007afdc  mov     [rsp-8+arg_8], rbx
0x18007afe1  push    rbp
0x18007afe2  push    rsi
0x18007afe3  push    rdi
0x18007afe4  push    r14
0x18007afe6  push    r15
0x18007afe8  lea     rbp, [rsp-37h]
0x18007afed  sub     rsp, 0D0h
0x18007aff4  mov     rax, cs:__security_cookie
0x18007affb  xor     rax, rsp
0x18007affe  mov     [rbp+57h+var_30], rax
0x18007b002  mov     r15d, edx
0x18007b005  mov     rsi, rcx
0x18007b008  lea     rdx, [rcx+38h]
0x18007b00c  mov     rdi, r8
0x18007b00f  lea     rcx, [rbp+57h+var_A8]
0x18007b013  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18007b018  mov     rbx, [rsi+60h]
0x18007b01c  mov     [rbp+57h+var_98], 1
0x18007b020  cmp     rbx, [rsi+68h]
0x18007b024  jz      loc_18007B0AE
0x18007b02a  mov     rcx, [rbx]
0x18007b02d  mov     rax, [rcx+4]
0x18007b031  cmp     rax, [rdi+4]
0x18007b035  jnz     short loc_18007B0A5
0x18007b037  mov     rax, [rcx+0Ch]
0x18007b03b  cmp     rax, [rdi+0Ch]
0x18007b03f  jnz     short loc_18007B0A5
0x18007b041  mov     rcx, [rcx+18h]; pv
0x18007b045  call    cs:__imp_CoTaskMemFree
0x18007b04b  mov     rcx, [rbx]
0x18007b04e  mov     rcx, [rcx+20h]; pv
0x18007b052  call    cs:__imp_CoTaskMemFree
0x18007b058  mov     rcx, [rbx]
0x18007b05b  mov     rcx, [rcx+28h]; pv
0x18007b05f  call    cs:__imp_CoTaskMemFree
0x18007b065  mov     rcx, [rbx]
0x18007b068  mov     rcx, [rcx+30h]; pv
0x18007b06c  call    cs:__imp_CoTaskMemFree
0x18007b072  mov     rcx, [rbx]
0x18007b075  mov     rcx, [rcx+38h]; pv
0x18007b079  call    cs:__imp_CoTaskMemFree
0x18007b07f  mov     rcx, [rbx]; pv
0x18007b082  call    cs:__imp_CoTaskMemFree
0x18007b088  mov     r8, [rsi+68h]
0x18007b08c  lea     rdx, [rbx+8]; Src
0x18007b090  sub     r8, rdx; Size
0x18007b093  mov     rcx, rbx; void *
0x18007b096  call    memmove_0
0x18007b09b  add     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFF8h
0x18007b0a0  jmp     loc_18007B020
0x18007b0a5  add     rbx, 8
0x18007b0a9  jmp     loc_18007B020
0x18007b0ae  xor     ebx, ebx
0x18007b0b0  cmp     r15d, 2
0x18007b0b4  jz      short loc_18007B12A
0x18007b0b6  lea     rdx, [rbp+57h+var_C0]; struct Shield_CloudBackupProviderInfo **
0x18007b0ba  mov     [rbp+57h+var_C0], rbx
0x18007b0be  mov     rcx, rdi; struct Shield_CloudBackupProviderInfo *
0x18007b0c1  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x18007b0c6  test    eax, eax
0x18007b0c8  js      short loc_18007B0F9
0x18007b0ca  lea     rdx, [rbp+57h+var_C0]
0x18007b0ce  lea     rcx, [rsi+60h]
0x18007b0d2  call    ??$HrStdPushBack@V?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@CommonUtil@@YAJAEAV?$CStdVector@_KV?$allocator@_K@std@@@0@AEB_K@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> &,unsigned __int64 const &)
0x18007b0d7  test    eax, eax
0x18007b0d9  jns     short loc_18007B12A
0x18007b0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b0e2  lea     rdx, WPP_GLOBAL_Control
0x18007b0e9  cmp     rcx, rdx
0x18007b0ec  jz      short loc_18007B12A
0x18007b0ee  test    byte ptr [rcx+1Ch], 1
0x18007b0f2  jz      short loc_18007B12A
0x18007b0f4  lea     edx, [rbx+43h]
0x18007b0f7  jmp     short loc_18007B117
0x18007b0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b100  lea     rdx, WPP_GLOBAL_Control
0x18007b107  cmp     rcx, rdx
0x18007b10a  jz      short loc_18007B12A
0x18007b10c  test    byte ptr [rcx+1Ch], 1
0x18007b110  jz      short loc_18007B12A
0x18007b112  mov     edx, 44h ; 'D'
0x18007b117  mov     rcx, [rcx+10h]
0x18007b11b  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007b122  mov     r9d, eax
0x18007b125  call    WPP_SF_d
0x18007b12a  lea     rcx, [rbp+57h+var_A8]
0x18007b12e  mov     [rbp+57h+var_98], bl
0x18007b131  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x18007b136  mov     eax, cs:dword_18012F2B8
0x18007b13c  cmp     eax, 5
0x18007b13f  jbe     loc_18007B1E3
0x18007b145  mov     rdx, 400000000000h
0x18007b14f  lea     rcx, dword_18012F2B8
0x18007b156  call    _tlgKeywordOn
0x18007b15b  test    al, al
0x18007b15d  jz      loc_18007B1E3
0x18007b163  mov     eax, [rdi+48h]
0x18007b166  lea     rdx, unk_180122008
0x18007b16d  mov     [rbp+57h+var_B8], eax
0x18007b170  lea     rcx, dword_18012F2B8
0x18007b177  mov     eax, [rdi+44h]
0x18007b17a  xor     r9d, r9d
0x18007b17d  mov     [rbp+57h+var_B4], eax
0x18007b180  xor     r8d, r8d
0x18007b183  mov     eax, [rdi+40h]
0x18007b186  mov     [rbp+57h+var_B0], eax
0x18007b189  lea     rax, [rbp+57h+var_B8]
0x18007b18d  mov     [rbp+57h+var_40], rax
0x18007b191  lea     rax, [rbp+57h+var_B4]
0x18007b195  mov     [rbp+57h+var_50], rax
0x18007b199  lea     rax, [rbp+57h+var_B0]
0x18007b19d  mov     [rbp+57h+var_60], rax
0x18007b1a1  lea     rax, [rbp+57h+var_C0]
0x18007b1a5  mov     [rbp+57h+var_70], rax
0x18007b1a9  lea     rax, [rbp+57h+var_90]
0x18007b1ad  mov     [rsp+0F0h+var_C8], rax
0x18007b1b2  mov     [rsp+0F0h+var_D0], 6
0x18007b1ba  mov     dword ptr [rbp+57h+var_C0], r15d
0x18007b1be  mov     [rbp+57h+var_38], 4
0x18007b1c6  mov     [rbp+57h+var_48], 4
0x18007b1ce  mov     [rbp+57h+var_58], 4
0x18007b1d6  mov     [rbp+57h+var_68], 4
0x18007b1de  call    _tlgWriteTransfer_EventWriteTransfer
0x18007b1e3  xor     eax, eax
0x18007b1e5  mov     rcx, [rbp+57h+var_30]
0x18007b1e9  xor     rcx, rsp; StackCookie
0x18007b1ec  call    __security_check_cookie
0x18007b1f1  mov     rbx, [rsp+0F0h+arg_8]
0x18007b1f9  add     rsp, 0D0h
0x18007b200  pop     r15
0x18007b202  pop     r14
0x18007b204  pop     rdi
0x18007b205  pop     rsi
0x18007b206  pop     rbp
0x18007b207  retn
```
