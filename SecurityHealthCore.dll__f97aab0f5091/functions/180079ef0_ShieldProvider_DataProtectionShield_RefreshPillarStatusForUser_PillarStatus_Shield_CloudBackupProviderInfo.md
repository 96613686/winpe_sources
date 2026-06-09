# ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(PillarStatus *,Shield_CloudBackupProviderInfo * *)

- ea: `0x180079ef0`
- end: `0x18007a415`
- name: `?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAUPillarStatus@@PEAPEAUShield_CloudBackupProviderInfo@@@Z`
- size: `1317`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, struct PillarStatus *, struct Shield_CloudBackupProviderInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x180079d48`

## callees

- `0x180001a1c`
- `0x180001de8`
- `0x180002244`
- `0x18000d7fc`
- `0x1800775dc`
- `0x180077d34`
- `0x180077ff4`
- `0x180079ef0`
- `0x18007a680`
- `0x18007a78c`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007a15b`
- `ole32!CoTaskMemFree` at `0x18007a165`
- `ole32!CoTaskMemFree` at `0x18007a16f`
- `ole32!CoTaskMemFree` at `0x18007a179`
- `ole32!CoTaskMemFree` at `0x18007a183`
- `ole32!CoTaskMemFree` at `0x18007a18c`
- `ole32!CoTaskMemFree` at `0x18007a1d9`
- `ole32!CoTaskMemFree` at `0x18007a1e3`
- `ole32!CoTaskMemFree` at `0x18007a1ed`
- `ole32!CoTaskMemFree` at `0x18007a1f7`
- `ole32!CoTaskMemFree` at `0x18007a201`
- `ole32!CoTaskMemFree` at `0x18007a20a`
- `ole32!CoTaskMemFree` at `0x18007a261`
- `ole32!CoTaskMemFree` at `0x18007a26b`
- `ole32!CoTaskMemFree` at `0x18007a275`
- `ole32!CoTaskMemFree` at `0x18007a27f`
- `ole32!CoTaskMemFree` at `0x18007a289`
- `ole32!CoTaskMemFree` at `0x18007a292`
- `ole32!CoTaskMemFree` at `0x18007a339`
- `ole32!CoTaskMemFree` at `0x18007a348`
- `ole32!CoTaskMemFree` at `0x18007a357`
- `ole32!CoTaskMemFree` at `0x18007a366`
- `ole32!CoTaskMemFree` at `0x18007a375`
- `ole32!CoTaskMemFree` at `0x18007a388`
- `ole32!CoTaskMemFree` at `0x18007a3c4`
- `ole32!CoTaskMemFree` at `0x18007a3ce`
- `ole32!CoTaskMemFree` at `0x18007a3d8`
- `ole32!CoTaskMemFree` at `0x18007a3e2`
- `ole32!CoTaskMemFree` at `0x18007a3ec`
- `ole32!CoTaskMemFree` at `0x18007a3f5`
- `ole32!CoTaskMemFree` at `0x18007a15b`
- `ole32!CoTaskMemFree` at `0x18007a165`
- `ole32!CoTaskMemFree` at `0x18007a16f`
- `ole32!CoTaskMemFree` at `0x18007a179`
- `ole32!CoTaskMemFree` at `0x18007a183`
- `ole32!CoTaskMemFree` at `0x18007a18c`
- `ole32!CoTaskMemFree` at `0x18007a1d9`
- `ole32!CoTaskMemFree` at `0x18007a1e3`
- `ole32!CoTaskMemFree` at `0x18007a1ed`
- `ole32!CoTaskMemFree` at `0x18007a1f7`
- `ole32!CoTaskMemFree` at `0x18007a201`
- `ole32!CoTaskMemFree` at `0x18007a20a`
- `ole32!CoTaskMemFree` at `0x18007a261`
- `ole32!CoTaskMemFree` at `0x18007a26b`
- `ole32!CoTaskMemFree` at `0x18007a275`
- `ole32!CoTaskMemFree` at `0x18007a27f`
- `ole32!CoTaskMemFree` at `0x18007a289`
- `ole32!CoTaskMemFree` at `0x18007a292`
- `ole32!CoTaskMemFree` at `0x18007a339`
- `ole32!CoTaskMemFree` at `0x18007a348`
- `ole32!CoTaskMemFree` at `0x18007a357`
- `ole32!CoTaskMemFree` at `0x18007a366`
- `ole32!CoTaskMemFree` at `0x18007a375`
- `ole32!CoTaskMemFree` at `0x18007a388`
- `ole32!CoTaskMemFree` at `0x18007a3c4`
- `ole32!CoTaskMemFree` at `0x18007a3ce`
- `ole32!CoTaskMemFree` at `0x18007a3d8`
- `ole32!CoTaskMemFree` at `0x18007a3e2`
- `ole32!CoTaskMemFree` at `0x18007a3ec`
- `ole32!CoTaskMemFree` at `0x18007a3f5`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(
        ShieldProvider::DataProtectionShield *this,
        struct PillarStatus *a2,
        wchar_t *a3)
{
  struct PillarStatus *v3; // r12
  struct Shield_CloudBackupProviderInfo **v4; // r13
  LPVOID *v6; // rdi
  int IsWscServiceRunning; // esi
  int v8; // r14d
  __int64 v9; // rax
  int v10; // r15d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  unsigned int v15; // eax
  char *v16; // r13
  const struct _GUID *v17; // rdx
  int v18; // eax
  int v19; // ecx
  __int64 v20; // r8
  int v21; // r9d
  __int64 v22; // r12
  LPVOID *v23; // rax
  unsigned int v25; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v26; // [rsp+38h] [rbp-28h] BYREF
  int v27; // [rsp+40h] [rbp-20h]
  __int64 v28; // [rsp+48h] [rbp-18h] BYREF
  struct Shield_CloudBackupProviderInfo *v29; // [rsp+50h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-8h] BYREF
  const wchar_t *v32; // [rsp+B0h] [rbp+50h] BYREF
  int v33; // [rsp+B8h] [rbp+58h] BYREF

  v32 = a3;
  *(_QWORD *)a2 = 0;
  v3 = a2;
  *(_QWORD *)a3 = 0;
  v4 = (struct Shield_CloudBackupProviderInfo **)a3;
  v29 = 0;
  LOBYTE(v33) = 0;
  v6 = 0;
  IsWscServiceRunning = ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(this, (bool *)&v33);
  if ( IsWscServiceRunning < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)IsWscServiceRunning);
    return (unsigned int)IsWscServiceRunning;
  }
  if ( !(_BYTE)v33 )
  {
    v8 = 128;
LABEL_51:
    v10 = 1;
    goto LABEL_52;
  }
  if ( *((_BYTE *)this + 160) )
  {
    v8 = 130;
    goto LABEL_51;
  }
  if ( !*((_BYTE *)this + 162) )
  {
    v8 = 131;
    goto LABEL_51;
  }
  v9 = *(_QWORD *)this;
  v25 = 0;
  pv = 0;
  IsWscServiceRunning = (*(__int64 (__fastcall **)(ShieldProvider::DataProtectionShield *, unsigned int *, LPVOID *))(v9 + 64))(
                          this,
                          &v25,
                          &pv);
  if ( IsWscServiceRunning < 0 )
    return (unsigned int)IsWscServiceRunning;
  if ( !v25 )
  {
    if ( !*((_BYTE *)this + 161) )
    {
      v8 = 131;
      v10 = 1;
      goto LABEL_48;
    }
    v33 = 0;
    LODWORD(v32) = 0;
    IsWscServiceRunning = ShieldProvider::DataProtectionShield::GetIsWarningStateDismissedForUser(
                            this,
                            &GUID_NULL,
                            132,
                            &v32,
                            &v33);
    if ( IsWscServiceRunning >= 0 )
    {
      v8 = 129;
      v10 = 2;
      if ( !(_DWORD)v32 )
      {
        v10 = 4;
        v8 = 132;
        if ( (unsigned int)dword_18012F2B8 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
          {
            v32 = L"DataProtection_CloudBackupProviderSetupRequired";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v11,
              (unsigned int)&word_180121F5E,
              v12,
              v13,
              (__int64)&v32);
          }
        }
      }
      goto LABEL_47;
    }
    return (unsigned int)IsWscServiceRunning;
  }
  ShieldProvider::DataProtectionShield::RevokeSetupRequiredWarningStateIfApplicable(this);
  v14 = 0;
  v33 = 0;
  v15 = v25;
  v10 = 2;
  v27 = 0;
  v8 = 129;
  if ( !v25 )
    goto LABEL_44;
  while ( IsWscServiceRunning >= 0 )
  {
    v16 = (char *)pv + 80 * v14;
    v17 = (const struct _GUID *)(v16 + 4);
    if ( (unsigned int)(*((_DWORD *)v16 + 17) - 2) <= 1 )
    {
      LODWORD(v28) = 0;
      LODWORD(v26) = 0;
      IsWscServiceRunning = ShieldProvider::DataProtectionShield::GetIsWarningStateDismissedForUser(
                              this,
                              v17,
                              133,
                              &v26,
                              &v28);
      if ( IsWscServiceRunning >= 0 && !(_DWORD)v26 )
      {
        if ( *((_DWORD *)v16 + 16) == 1 )
        {
          v33 = 1;
          v10 = 4;
          v8 = 133;
          if ( v6 )
          {
            CoTaskMemFree(v6[3]);
            CoTaskMemFree(v6[4]);
            CoTaskMemFree(v6[5]);
            CoTaskMemFree(v6[6]);
            CoTaskMemFree(v6[7]);
            CoTaskMemFree(v6);
            v29 = 0;
          }
          goto LABEL_38;
        }
        if ( *((_DWORD *)v16 + 16) == 2 && v33 != 1 )
        {
          v33 = 2;
          v10 = 4;
          v8 = 133;
          if ( v6 )
          {
            CoTaskMemFree(v6[3]);
            CoTaskMemFree(v6[4]);
            CoTaskMemFree(v6[5]);
            CoTaskMemFree(v6[6]);
            CoTaskMemFree(v6[7]);
            CoTaskMemFree(v6);
            v29 = 0;
          }
          goto LABEL_38;
        }
        if ( *((_DWORD *)v16 + 16) == 3 && (unsigned int)(v33 - 1) > 1 )
        {
          v33 = 3;
          v10 = 4;
          v8 = 133;
          if ( v6 )
          {
            CoTaskMemFree(v6[3]);
            CoTaskMemFree(v6[4]);
            CoTaskMemFree(v6[5]);
            CoTaskMemFree(v6[6]);
            CoTaskMemFree(v6[7]);
            CoTaskMemFree(v6);
            v29 = 0;
          }
LABEL_38:
          v18 = ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(
                  (struct Shield_CloudBackupProviderInfo *)v16,
                  &v29);
          v6 = (LPVOID *)v29;
          IsWscServiceRunning = v18;
        }
        if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
        {
          v28 = v20;
          v26 = L"DataProtection_DataRestoreRequired";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v19,
            (unsigned int)&unk_180121F18,
            v20,
            v21,
            (__int64)&v26,
            (__int64)&v28);
        }
      }
    }
    else
    {
      ShieldProvider::DataProtectionShield::RevokeRestoreRequiredWarningStateIfApplicable(this, v17);
    }
    v15 = v25;
    v14 = (unsigned int)(v27 + 1);
    v27 = v14;
    if ( (unsigned int)v14 >= v25 )
      break;
  }
  v4 = (struct Shield_CloudBackupProviderInfo **)v32;
LABEL_44:
  v22 = 0;
  if ( v15 )
  {
    do
    {
      CoTaskMemFree(*((LPVOID *)pv + 10 * v22 + 3));
      CoTaskMemFree(*((LPVOID *)pv + 10 * v22 + 4));
      CoTaskMemFree(*((LPVOID *)pv + 10 * v22 + 5));
      CoTaskMemFree(*((LPVOID *)pv + 10 * v22 + 6));
      CoTaskMemFree(*((LPVOID *)pv + 10 * v22 + 7));
      v22 = (unsigned int)(v22 + 1);
    }
    while ( (unsigned int)v22 < v25 );
  }
  CoTaskMemFree(pv);
LABEL_47:
  v3 = a2;
LABEL_48:
  if ( IsWscServiceRunning < 0 )
  {
LABEL_54:
    if ( v6 )
    {
      CoTaskMemFree(v6[3]);
      CoTaskMemFree(v6[4]);
      CoTaskMemFree(v6[5]);
      CoTaskMemFree(v6[6]);
      CoTaskMemFree(v6[7]);
      CoTaskMemFree(v6);
    }
  }
  else
  {
LABEL_52:
    *(_DWORD *)v3 = v8;
    *((_DWORD *)v3 + 1) = v10;
    if ( v6 )
    {
      v23 = v6;
      v6 = 0;
      *v4 = (struct Shield_CloudBackupProviderInfo *)v23;
      goto LABEL_54;
    }
  }
  return (unsigned int)IsWscServiceRunning;
}

```

## disassembly

```asm
0x180079ef0  mov     [rsp-38h+arg_0], rbx
0x180079ef5  mov     [rsp-38h+arg_10], r8
0x180079efa  mov     [rsp-38h+arg_8], rdx
0x180079eff  push    rbp
0x180079f00  push    rsi
0x180079f01  push    rdi
0x180079f02  push    r12
0x180079f04  push    r13
0x180079f06  push    r14
0x180079f08  push    r15
0x180079f0a  mov     rbp, rsp
0x180079f0d  sub     rsp, 60h
0x180079f11  xor     r14d, r14d
0x180079f14  xor     eax, eax
0x180079f16  mov     [rdx], rax
0x180079f19  mov     r12, rdx
0x180079f1c  lea     rdx, [rbp+arg_18]; bool *
0x180079f20  mov     [r8], r14
0x180079f23  mov     r13, r8
0x180079f26  mov     [rbp+var_10], r14
0x180079f2a  mov     rbx, rcx
0x180079f2d  mov     byte ptr [rbp+arg_18], r14b
0x180079f31  mov     edi, r14d
0x180079f34  call    ?GetIsWscServiceRunning@DataProtectionShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(bool *)
0x180079f39  mov     esi, eax
0x180079f3b  test    eax, eax
0x180079f3d  jns     short loc_180079F7C
0x180079f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f46  lea     rax, WPP_GLOBAL_Control
0x180079f4d  cmp     rcx, rax
0x180079f50  jz      loc_18007A3FB
0x180079f56  test    byte ptr [rcx+1Ch], 1
0x180079f5a  jz      loc_18007A3FB
0x180079f60  mov     rcx, [rcx+10h]
0x180079f64  lea     edx, [r14+52h]
0x180079f68  mov     r9d, esi
0x180079f6b  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079f72  call    WPP_SF_d
0x180079f77  jmp     loc_18007A3FB
0x180079f7c  cmp     byte ptr [rbp+arg_18], r14b
0x180079f80  jnz     short loc_180079F8D
0x180079f82  mov     r14d, 80h
0x180079f88  jmp     loc_18007A39E
0x180079f8d  cmp     [rbx+0A0h], r14b
0x180079f94  jz      short loc_180079FA1
0x180079f96  mov     r14d, 82h
0x180079f9c  jmp     loc_18007A39E
0x180079fa1  cmp     [rbx+0A2h], r14b
0x180079fa8  jz      loc_18007A398
0x180079fae  mov     rax, [rbx]
0x180079fb1  lea     r8, [rbp+pv]
0x180079fb5  lea     rdx, [rbp+var_30]
0x180079fb9  mov     [rbp+var_30], r14d
0x180079fbd  mov     rcx, rbx
0x180079fc0  mov     [rbp+pv], r14
0x180079fc4  mov     rax, [rax+40h]
0x180079fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079fcd  mov     esi, eax
0x180079fcf  test    eax, eax
0x180079fd1  js      loc_18007A3FB
0x180079fd7  cmp     [rbp+var_30], r14d
0x180079fdb  jnz     loc_18007A0A2
0x180079fe1  cmp     [rbx+0A1h], r14b
0x180079fe8  jz      loc_18007A091
0x180079fee  lea     rax, [rbp+arg_18]
0x180079ff2  mov     [rbp+arg_18], r14d
0x180079ff6  lea     r9, [rbp+arg_10]
0x180079ffa  mov     [rsp+60h+var_40], rax
0x180079fff  mov     r8d, 84h
0x18007a005  mov     dword ptr [rbp+arg_10], r14d
0x18007a009  lea     rdx, GUID_NULL
0x18007a010  mov     rcx, rbx
0x18007a013  call    ?GetIsWarningStateDismissedForUser@DataProtectionShield@ShieldProvider@@AEAAJAEBU_GUID@@W4PillarStatusFlag@@PEAH2@Z; ShieldProvider::DataProtectionShield::GetIsWarningStateDismissedForUser(_GUID const &,PillarStatusFlag,int *,int *)
0x18007a018  mov     esi, eax
0x18007a01a  test    eax, eax
0x18007a01c  js      loc_18007A3FB
0x18007a022  mov     r14d, 81h
0x18007a028  lea     r15d, [r14-7Fh]
0x18007a02c  cmp     dword ptr [rbp+arg_10], edi
0x18007a02f  jnz     loc_18007A38E
0x18007a035  mov     eax, cs:dword_18012F2B8
0x18007a03b  lea     r15d, [r14-7Dh]
0x18007a03f  mov     r14d, 84h
0x18007a045  cmp     eax, 5
0x18007a048  jbe     loc_18007A38E
0x18007a04e  mov     rdx, 400000000000h
0x18007a058  lea     rcx, dword_18012F2B8
0x18007a05f  call    _tlgKeywordOn
0x18007a064  test    al, al
0x18007a066  jz      loc_18007A38E
0x18007a06c  lea     rax, aDataprotection_5; "DataProtection_CloudBackupProviderSetup"...
0x18007a073  mov     [rbp+arg_10], rax
0x18007a077  lea     rdx, word_180121F5E
0x18007a07e  lea     rax, [rbp+arg_10]
0x18007a082  mov     [rsp+60h+var_40], rax
0x18007a087  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a08c  jmp     loc_18007A38E
0x18007a091  mov     r14d, 83h
0x18007a097  mov     r15d, 1
0x18007a09d  jmp     loc_18007A392
0x18007a0a2  mov     rcx, rbx; this
0x18007a0a5  call    ?RevokeSetupRequiredWarningStateIfApplicable@DataProtectionShield@ShieldProvider@@AEAAJXZ; ShieldProvider::DataProtectionShield::RevokeSetupRequiredWarningStateIfApplicable(void)
0x18007a0aa  xor     eax, eax
0x18007a0ac  mov     r12d, 2
0x18007a0b2  xor     ecx, ecx
0x18007a0b4  mov     [rbp+arg_18], eax
0x18007a0b7  mov     eax, [rbp+var_30]
0x18007a0ba  mov     r15d, r12d
0x18007a0bd  mov     [rbp+var_20], ecx
0x18007a0c0  lea     r14d, [r12+7Fh]
0x18007a0c5  test    eax, eax
0x18007a0c7  jz      loc_18007A322
0x18007a0cd  test    esi, esi
0x18007a0cf  js      loc_18007A31E
0x18007a0d5  lea     r13, [rcx+rcx*4]
0x18007a0d9  mov     rcx, rbx; this
0x18007a0dc  shl     r13, 4
0x18007a0e0  add     r13, [rbp+pv]
0x18007a0e4  mov     eax, [r13+44h]
0x18007a0e8  lea     rdx, [r13+4]; struct _GUID *
0x18007a0ec  sub     eax, r12d
0x18007a0ef  cmp     eax, 1
0x18007a0f2  jbe     short loc_18007A0FE
0x18007a0f4  call    ?RevokeRestoreRequiredWarningStateIfApplicable@DataProtectionShield@ShieldProvider@@AEAAJAEBU_GUID@@@Z; ShieldProvider::DataProtectionShield::RevokeRestoreRequiredWarningStateIfApplicable(_GUID const &)
0x18007a0f9  jmp     loc_18007A30B
0x18007a0fe  lea     rax, [rbp+var_18]
0x18007a102  mov     dword ptr [rbp+var_18], 0
0x18007a109  lea     r9, [rbp+var_28]
0x18007a10d  mov     [rsp+60h+var_40], rax
0x18007a112  mov     r8d, 85h
0x18007a118  mov     dword ptr [rbp+var_28], 0
0x18007a11f  call    ?GetIsWarningStateDismissedForUser@DataProtectionShield@ShieldProvider@@AEAAJAEBU_GUID@@W4PillarStatusFlag@@PEAH2@Z; ShieldProvider::DataProtectionShield::GetIsWarningStateDismissedForUser(_GUID const &,PillarStatusFlag,int *,int *)
0x18007a124  mov     esi, eax
0x18007a126  test    eax, eax
0x18007a128  js      loc_18007A30B
0x18007a12e  cmp     dword ptr [rbp+var_28], 0
0x18007a132  jnz     loc_18007A30B
0x18007a138  cmp     dword ptr [r13+40h], 1
0x18007a13d  jnz     short loc_18007A1B2
0x18007a13f  mov     [rbp+arg_18], 1
0x18007a146  mov     r15d, 4
0x18007a14c  mov     r14d, 85h
0x18007a152  test    rdi, rdi
0x18007a155  jz      short loc_18007A19A
0x18007a157  mov     rcx, [rdi+18h]; pv
0x18007a15b  call    cs:__imp_CoTaskMemFree
0x18007a161  mov     rcx, [rdi+20h]; pv
0x18007a165  call    cs:__imp_CoTaskMemFree
0x18007a16b  mov     rcx, [rdi+28h]; pv
0x18007a16f  call    cs:__imp_CoTaskMemFree
0x18007a175  mov     rcx, [rdi+30h]; pv
0x18007a179  call    cs:__imp_CoTaskMemFree
0x18007a17f  mov     rcx, [rdi+38h]; pv
0x18007a183  call    cs:__imp_CoTaskMemFree
0x18007a189  mov     rcx, rdi; pv
0x18007a18c  call    cs:__imp_CoTaskMemFree
0x18007a192  mov     [rbp+var_10], 0
0x18007a19a  lea     rdx, [rbp+var_10]; struct Shield_CloudBackupProviderInfo **
0x18007a19e  mov     rcx, r13; struct Shield_CloudBackupProviderInfo *
0x18007a1a1  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x18007a1a6  lea     r8, aOnedriveBusine; "OneDrive Business"
0x18007a1ad  jmp     loc_18007A2B3
0x18007a1b2  mov     eax, [rbp+arg_18]
0x18007a1b5  cmp     [r13+40h], r12d
0x18007a1b9  jnz     short loc_18007A230
0x18007a1bb  cmp     eax, 1
0x18007a1be  jz      short loc_18007A230
0x18007a1c0  mov     [rbp+arg_18], r12d
0x18007a1c4  mov     r15d, 4
0x18007a1ca  mov     r14d, 85h
0x18007a1d0  test    rdi, rdi
0x18007a1d3  jz      short loc_18007A218
0x18007a1d5  mov     rcx, [rdi+18h]; pv
0x18007a1d9  call    cs:__imp_CoTaskMemFree
0x18007a1df  mov     rcx, [rdi+20h]; pv
0x18007a1e3  call    cs:__imp_CoTaskMemFree
0x18007a1e9  mov     rcx, [rdi+28h]; pv
0x18007a1ed  call    cs:__imp_CoTaskMemFree
0x18007a1f3  mov     rcx, [rdi+30h]; pv
0x18007a1f7  call    cs:__imp_CoTaskMemFree
0x18007a1fd  mov     rcx, [rdi+38h]; pv
0x18007a201  call    cs:__imp_CoTaskMemFree
0x18007a207  mov     rcx, rdi; pv
0x18007a20a  call    cs:__imp_CoTaskMemFree
0x18007a210  mov     [rbp+var_10], 0
0x18007a218  lea     rdx, [rbp+var_10]; struct Shield_CloudBackupProviderInfo **
0x18007a21c  mov     rcx, r13; struct Shield_CloudBackupProviderInfo *
0x18007a21f  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x18007a224  lea     r8, aOnedriveConsum; "OneDrive Consumer"
0x18007a22b  jmp     loc_18007A2B3
0x18007a230  cmp     dword ptr [r13+40h], 3
0x18007a235  lea     r8, aUnknown_1; "Unknown"
0x18007a23c  jnz     short loc_18007A2B9
0x18007a23e  dec     eax
0x18007a240  cmp     eax, 1
0x18007a243  jbe     short loc_18007A2B9
0x18007a245  mov     [rbp+arg_18], 3
0x18007a24c  mov     r15d, 4
0x18007a252  mov     r14d, 85h
0x18007a258  test    rdi, rdi
0x18007a25b  jz      short loc_18007A2A0
0x18007a25d  mov     rcx, [rdi+18h]; pv
0x18007a261  call    cs:__imp_CoTaskMemFree
0x18007a267  mov     rcx, [rdi+20h]; pv
0x18007a26b  call    cs:__imp_CoTaskMemFree
0x18007a271  mov     rcx, [rdi+28h]; pv
0x18007a275  call    cs:__imp_CoTaskMemFree
0x18007a27b  mov     rcx, [rdi+30h]; pv
0x18007a27f  call    cs:__imp_CoTaskMemFree
0x18007a285  mov     rcx, [rdi+38h]; pv
0x18007a289  call    cs:__imp_CoTaskMemFree
0x18007a28f  mov     rcx, rdi; pv
0x18007a292  call    cs:__imp_CoTaskMemFree
0x18007a298  mov     [rbp+var_10], 0
0x18007a2a0  lea     rdx, [rbp+var_10]; struct Shield_CloudBackupProviderInfo **
0x18007a2a4  mov     rcx, r13; struct Shield_CloudBackupProviderInfo *
0x18007a2a7  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x18007a2ac  lea     r8, aThirdParty; "Third Party"
0x18007a2b3  mov     rdi, [rbp+var_10]
0x18007a2b7  mov     esi, eax
0x18007a2b9  mov     eax, cs:dword_18012F2B8
0x18007a2bf  cmp     eax, 5
0x18007a2c2  jbe     short loc_18007A30B
0x18007a2c4  mov     rdx, 400000000000h
0x18007a2ce  lea     rcx, dword_18012F2B8
0x18007a2d5  call    _tlgKeywordOn
0x18007a2da  test    al, al
0x18007a2dc  jz      short loc_18007A30B
0x18007a2de  lea     rax, aDataprotection_0; "DataProtection_DataRestoreRequired"
0x18007a2e5  mov     [rbp+var_18], r8
0x18007a2e9  mov     [rbp+var_28], rax
0x18007a2ed  lea     rdx, unk_180121F18
0x18007a2f4  lea     rax, [rbp+var_18]
0x18007a2f8  mov     [rsp+60h+var_38], rax
0x18007a2fd  lea     rax, [rbp+var_28]
0x18007a301  mov     [rsp+60h+var_40], rax
0x18007a306  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18007a30b  mov     ecx, [rbp+var_20]
0x18007a30e  mov     eax, [rbp+var_30]
0x18007a311  inc     ecx
0x18007a313  mov     [rbp+var_20], ecx
0x18007a316  cmp     ecx, eax
0x18007a318  jb      loc_18007A0CD
0x18007a31e  mov     r13, [rbp+arg_10]
0x18007a322  xor     r12d, r12d
0x18007a325  test    eax, eax
0x18007a327  jz      short loc_18007A384
0x18007a329  mov     rcx, [rbp+pv]
0x18007a32d  lea     rbx, [r12+r12*4]
0x18007a331  add     rbx, rbx
0x18007a334  mov     rcx, [rcx+rbx*8+18h]; pv
0x18007a339  call    cs:__imp_CoTaskMemFree
0x18007a33f  mov     rcx, [rbp+pv]
0x18007a343  mov     rcx, [rcx+rbx*8+20h]; pv
0x18007a348  call    cs:__imp_CoTaskMemFree
0x18007a34e  mov     rcx, [rbp+pv]
0x18007a352  mov     rcx, [rcx+rbx*8+28h]; pv
0x18007a357  call    cs:__imp_CoTaskMemFree
0x18007a35d  mov     rcx, [rbp+pv]
0x18007a361  mov     rcx, [rcx+rbx*8+30h]; pv
0x18007a366  call    cs:__imp_CoTaskMemFree
0x18007a36c  mov     rcx, [rbp+pv]
0x18007a370  mov     rcx, [rcx+rbx*8+38h]; pv
0x18007a375  call    cs:__imp_CoTaskMemFree
0x18007a37b  inc     r12d
0x18007a37e  cmp     r12d, [rbp+var_30]
0x18007a382  jb      short loc_18007A329
0x18007a384  mov     rcx, [rbp+pv]; pv
0x18007a388  call    cs:__imp_CoTaskMemFree
0x18007a38e  mov     r12, [rbp+arg_8]
0x18007a392  test    esi, esi
0x18007a394  js      short loc_18007A3BB
0x18007a396  jmp     short loc_18007A3A4
0x18007a398  mov     r14d, 83h
0x18007a39e  mov     r15d, 1
0x18007a3a4  mov     [r12], r14d
0x18007a3a8  mov     [r12+4], r15d
0x18007a3ad  test    rdi, rdi
0x18007a3b0  jz      short loc_18007A3FB
0x18007a3b2  mov     rax, rdi
0x18007a3b5  xor     edi, edi
0x18007a3b7  mov     [r13+0], rax
0x18007a3bb  test    rdi, rdi
0x18007a3be  jz      short loc_18007A3FB
0x18007a3c0  mov     rcx, [rdi+18h]; pv
0x18007a3c4  call    cs:__imp_CoTaskMemFree
0x18007a3ca  mov     rcx, [rdi+20h]; pv
0x18007a3ce  call    cs:__imp_CoTaskMemFree
0x18007a3d4  mov     rcx, [rdi+28h]; pv
0x18007a3d8  call    cs:__imp_CoTaskMemFree
0x18007a3de  mov     rcx, [rdi+30h]; pv
0x18007a3e2  call    cs:__imp_CoTaskMemFree
0x18007a3e8  mov     rcx, [rdi+38h]; pv
0x18007a3ec  call    cs:__imp_CoTaskMemFree
0x18007a3f2  mov     rcx, rdi; pv
0x18007a3f5  call    cs:__imp_CoTaskMemFree
0x18007a3fb  mov     rbx, [rsp+60h+arg_0]
0x18007a403  mov     eax, esi
0x18007a405  add     rsp, 60h
0x18007a409  pop     r15
  ... truncated ...
```
