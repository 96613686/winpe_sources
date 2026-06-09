# CWwanDataExecutor::OnPmProfileUpdate(WWAN_PROFILE_UPDATE_INFO *)

- ea: `0x18002c22c`
- end: `0x18002c79f`
- name: `?OnPmProfileUpdate@CWwanDataExecutor@@QEAAXPEAUWWAN_PROFILE_UPDATE_INFO@@@Z`
- size: `1395`
- prototype: `void __fastcall(CWwanDataExecutor *__hidden this, struct WWAN_PROFILE_UPDATE_INFO *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002cb70`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180017640`
- `0x18002746c`
- `0x18002755c`
- `0x18002c22c`
- `0x18002e8fc`
- `0x1800313d4`
- `0x180031498`
- `0x180031598`
- `0x18003bc04`
- `0x1800736f8`
- `0x18009dd40`
- `0x1800b6ac0`
- `0x1800c8520`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c31f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c31f`
- `WwanPrfl!WwanProfileCleanup` at `0x18002c682`
- `WwanPrfl!WwanProfileCleanup` at `0x18002c772`
- `WwanPrfl!WwanProfileCleanup` at `0x18002c682`
- `WwanPrfl!WwanProfileCleanup` at `0x18002c772`
- `WwanPrfl!WwanProfileInit` at `0x18002c484`
- `WwanPrfl!WwanProfileInit` at `0x18002c484`
- `WwanPrfl!WwanProfileDeinit` at `0x18002c68c`
- `WwanPrfl!WwanProfileDeinit` at `0x18002c68c`

## string_xrefs

- `0x18002c379`: `Op DELETE on Profile {%s} (Modem %s EXEC %d)`
- `0x18002c33b`: `CWwanDataExecutor::OnPmProfileUpdate`
- `0x18002c430`: `CWwanDataExecutor::OnPmProfileUpdate`
- `0x18002c4a9`: `CWwanDataExecutor::OnPmProfileUpdate`
- `0x18002c51a`: `CWwanDataExecutor::OnPmProfileUpdate`
- `0x18002c591`: `CWwanDataExecutor::OnPmProfileUpdate`
- `0x18002c40d`: `CREATE`
- `0x18002c403`: `UPDATE`
- `0x18002c4a0`: `Data Executor is not ready with ICCID %u`
- `0x18002c588`: `failed from CreateProfileIstream [error %u]`
- `0x18002c344`: `no support for WwanProfileUpdateRenamed`

## pseudocode

```c
void __fastcall CWwanDataExecutor::OnPmProfileUpdate(CWwanDataExecutor *this, struct WWAN_PROFILE_UPDATE_INFO *a2)
{
  __int64 v4; // rcx
  unsigned __int16 *v5; // rax
  __int64 v6; // rdx
  _OWORD *v7; // rax
  unsigned __int16 *v8; // rcx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  int v16; // r14d
  int v17; // ecx
  const wchar_t *v18; // r9
  unsigned int v19; // r8d
  unsigned int ExecutorICCID; // eax
  int v21; // ecx
  unsigned int ProfileStruct; // eax
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // eax
  _OWORD *v26; // rax
  unsigned int v27; // edx
  unsigned int v28; // [rsp+70h] [rbp-90h] BYREF
  void *v29; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[3076]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+C84h] [rbp+B84h]
  int v32; // [rsp+CFCh] [rbp+BFCh]
  _BYTE v33[1256]; // [rsp+D08h] [rbp+C08h] BYREF
  int v34; // [rsp+11F0h] [rbp+10F0h]
  int v35; // [rsp+1200h] [rbp+1100h]
  int v36; // [rsp+128Ch] [rbp+118Ch]
  int v37; // [rsp+1620h] [rbp+1520h]
  unsigned __int16 v38[8]; // [rsp+1930h] [rbp+1830h] BYREF
  _BYTE v39[26]; // [rsp+1940h] [rbp+1840h] BYREF
  OLECHAR sz[48]; // [rsp+1960h] [rbp+1860h] BYREF
  unsigned __int16 v41[256]; // [rsp+19C0h] [rbp+18C0h] BYREF

  memset_0(sz, 0, 0x5Eu);
  v4 = 512;
  v29 = 0;
  v5 = v41;
  v28 = 0;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (unsigned __int16 *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  v6 = 4;
  v7 = (_OWORD *)((char *)a2 + 4);
  v8 = v41;
  do
  {
    v9 = v7[1];
    *(_OWORD *)v8 = *v7;
    v10 = v7[2];
    *((_OWORD *)v8 + 1) = v9;
    v11 = v7[3];
    *((_OWORD *)v8 + 2) = v10;
    v12 = v7[4];
    *((_OWORD *)v8 + 3) = v11;
    v13 = v7[5];
    *((_OWORD *)v8 + 4) = v12;
    v14 = v7[6];
    *((_OWORD *)v8 + 5) = v13;
    v15 = v7[7];
    v7 += 8;
    *((_OWORD *)v8 + 6) = v14;
    *((_OWORD *)v8 + 7) = v15;
    v8 += 64;
    --v6;
  }
  while ( v6 );
  v41[255] = 0;
  v16 = 0;
  StringFromGUID2((const GUID *const)((char *)this + 12552), sz, 47);
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != 1 )
    {
      if ( *(_DWORD *)a2 == 3 )
      {
        WwanLog::Info(
          "CWwanDataExecutor::OnPmProfileUpdate",
          (const struct _GUID *)((char *)this + 12536),
          L"Op DELETE on Profile {%s} (Modem %s EXEC %d)",
          v41,
          sz,
          *((_DWORD *)this + 3143));
        WwanNhNotificationDispatcherWithHeader(
          2u,
          0x2Fu,
          (const struct _GUID *)((char *)this + 12536),
          0,
          0,
          0x200u,
          v41);
        if ( (byte_1801528C4 & 0x10) != 0 )
          McTemplateU0jdqz_EventWriteTransfer(
            v17,
            (unsigned int)PMDeleteProfile,
            (_DWORD)this + 12536,
            *((_DWORD *)this + 3142),
            *((_DWORD *)this + 3143),
            (__int64)v41);
        CWwanDataExecutor::DeleteProfileW(this, v41);
      }
      else
      {
        WwanLog::Error("CWwanDataExecutor::OnPmProfileUpdate", 0, L"no support for WwanProfileUpdateRenamed");
      }
      return;
    }
  }
  else
  {
    v16 = 1;
  }
  v18 = L"CREATE";
  if ( !v16 )
    v18 = L"UPDATE";
  WwanLog::Info(
    "CWwanDataExecutor::OnPmProfileUpdate",
    (const struct _GUID *)((char *)this + 12536),
    L"Op %s on Profile {%s} (Modem %s EXEC %d)",
    v18,
    v41,
    sz,
    *((_DWORD *)this + 3143));
  memset(v39, 0, sizeof(v39));
  *(_OWORD *)v38 = 0;
  memset_0(v30, 0, 0x18B0u);
  WwanProfileInit(v30);
  ExecutorICCID = CWwanDataExecutorState::GetExecutorICCID(this, v38, v19);
  if ( ExecutorICCID )
  {
    WwanLog::Info("CWwanDataExecutor::OnPmProfileUpdate", 0, L"Data Executor is not ready with ICCID %u", ExecutorICCID);
    if ( (byte_1801528C4 & 0x10) != 0 )
      McTemplateU0jdqz_EventWriteTransfer(
        v21,
        (unsigned int)CreateUpdateProfileBeforeICCIDArrive,
        (_DWORD)this + 12536,
        *((_DWORD *)this + 3142),
        *((_DWORD *)this + 3143),
        (__int64)v41);
  }
  else
  {
    ProfileStruct = WwanPmGetProfileStruct(v38, v41, v30);
    if ( ProfileStruct )
    {
      WwanLog::Error("CWwanDataExecutor::OnPmProfileUpdate", 0, L"WwanPmGetProfileStruct() failed: %u", ProfileStruct);
      if ( (byte_1801528C4 & 0x20) != 0 )
        McTemplateU0jdqzz_EventWriteTransfer(
          v24,
          v23,
          (_DWORD)this + 12536,
          *((_DWORD *)this + 3142),
          *((_DWORD *)this + 3143),
          (__int64)v38,
          (__int64)v41);
    }
    else
    {
      v25 = CWwanManager::CreateProfileIstream((__int64)v41, 0, &v28, (char **)&v29);
      if ( v25 )
      {
        WwanLog::Error("CWwanDataExecutor::OnPmProfileUpdate", 0, L"failed from CreateProfileIstream [error %u]", v25);
      }
      else
      {
        v26 = v29;
        *((_OWORD *)v29 + 395) = *(_OWORD *)((char *)a2 + 1032);
        v26[396] = *(_OWORD *)((char *)a2 + 1048);
        *((_QWORD *)v26 + 794) = *((_QWORD *)a2 + 133);
        if ( v16 )
        {
          if ( (byte_1801528C4 & 0x10) != 0 )
            McTemplateU0jdqzzqtqqzq_EventWriteTransfer(
              v31,
              (unsigned int)PMAddProfile,
              (_DWORD)this + 12536,
              *((_DWORD *)this + 3142),
              *((_DWORD *)this + 3143),
              (__int64)v41,
              (__int64)v38,
              v32,
              v36 != 0,
              v31,
              v37,
              (__int64)v33,
              v34);
          if ( v36 && !v35 )
          {
            CWwanDataExecutor::AddUserMMSProfile(this, (const struct WWAN_PROFILE *)v30);
            WwanProfileCleanup(v30);
            WwanProfileDeinit(v30);
          }
          v27 = 45;
        }
        else
        {
          if ( (byte_1801528C4 & 0x10) != 0 )
            McTemplateU0jdqzzqtqqzq_EventWriteTransfer(
              v31,
              (unsigned int)PMUpdateProfile,
              (_DWORD)this + 12536,
              *((_DWORD *)this + 3142),
              *((_DWORD *)this + 3143),
              (__int64)v41,
              (__int64)v38,
              v32,
              v36 != 0,
              v31,
              v37,
              (__int64)v33,
              v34);
          CWwanDataExecutor::UpdateProfile(this, (struct WWAN_PROFILE *)v30);
          v27 = 46;
        }
        WwanNhNotificationDispatcherWithHeader(2u, v27, (const struct _GUID *)((char *)this + 12536), 0, 0, v28, v29);
        WwanMemFree(v29);
        v29 = 0;
      }
      WwanProfileCleanup(v30);
    }
  }
}

```

## disassembly

```asm
0x18002c22c  mov     [rsp-8+arg_10], rbx
0x18002c231  mov     [rsp-8+arg_18], rsi
0x18002c236  push    rbp
0x18002c237  push    rdi
0x18002c238  push    r14
0x18002c23a  lea     rbp, [rsp-1AD0h]
0x18002c242  mov     eax, 1BD0h
0x18002c247  call    _alloca_probe
0x18002c24c  sub     rsp, rax
0x18002c24f  mov     rax, cs:__security_cookie
0x18002c256  xor     rax, rsp
0x18002c259  mov     [rbp+1AE0h+var_20], rax
0x18002c260  mov     rdi, rdx
0x18002c263  mov     rbx, rcx
0x18002c266  xor     edx, edx; Val
0x18002c268  lea     rcx, [rbp+1AE0h+sz]; void *
0x18002c26f  lea     r8d, [rdx+5Eh]; Size
0x18002c273  call    memset_0
0x18002c278  mov     ecx, 200h
0x18002c27d  mov     [rsp+1BE0h+var_1B68], 0
0x18002c286  lea     rax, [rbp+1AE0h+var_220]
0x18002c28d  mov     [rsp+1BE0h+var_1B70], 0
0x18002c295  mov     byte ptr [rax], 0
0x18002c298  inc     rax
0x18002c29b  sub     rcx, 1
0x18002c29f  jnz     short loc_18002C295
0x18002c2a1  mov     edx, 4
0x18002c2a6  lea     rax, [rdi+4]
0x18002c2aa  lea     rcx, [rbp+1AE0h+var_220]
0x18002c2b1  lea     r8d, [rdx+7Ch]
0x18002c2b5  movups  xmm0, xmmword ptr [rax]
0x18002c2b8  movups  xmm1, xmmword ptr [rax+10h]
0x18002c2bc  movups  xmmword ptr [rcx], xmm0
0x18002c2bf  movups  xmm0, xmmword ptr [rax+20h]
0x18002c2c3  movups  xmmword ptr [rcx+10h], xmm1
0x18002c2c7  movups  xmm1, xmmword ptr [rax+30h]
0x18002c2cb  movups  xmmword ptr [rcx+20h], xmm0
0x18002c2cf  movups  xmm0, xmmword ptr [rax+40h]
0x18002c2d3  movups  xmmword ptr [rcx+30h], xmm1
0x18002c2d7  movups  xmm1, xmmword ptr [rax+50h]
0x18002c2db  movups  xmmword ptr [rcx+40h], xmm0
0x18002c2df  movups  xmm0, xmmword ptr [rax+60h]
0x18002c2e3  movups  xmmword ptr [rcx+50h], xmm1
0x18002c2e7  movups  xmm1, xmmword ptr [rax+70h]
0x18002c2eb  add     rax, r8
0x18002c2ee  movups  xmmword ptr [rcx+60h], xmm0
0x18002c2f2  movups  xmmword ptr [rcx+70h], xmm1
0x18002c2f6  add     rcx, r8
0x18002c2f9  sub     rdx, 1
0x18002c2fd  jnz     short loc_18002C2B5
0x18002c2ff  lea     esi, [rdx+2Fh]
0x18002c302  xor     eax, eax
0x18002c304  mov     r8d, esi; cchMax
0x18002c307  mov     [rbp+1AE0h+var_22], ax
0x18002c30e  lea     rcx, [rbx+3108h]; rguid
0x18002c315  xor     r14d, r14d
0x18002c318  lea     rdx, [rbp+1AE0h+sz]; lpsz
0x18002c31f  call    cs:__imp_StringFromGUID2
0x18002c325  mov     ecx, [rdi]
0x18002c327  test    ecx, ecx
0x18002c329  jz      loc_18002C3FD
0x18002c32f  sub     ecx, 1
0x18002c332  jz      loc_18002C403
0x18002c338  cmp     ecx, 2
0x18002c33b  lea     rcx, aCwwandataexecu_77; "CWwanDataExecutor::OnPmProfileUpdate"
0x18002c342  jz      short loc_18002C357
0x18002c344  lea     r8, aNoSupportForWw; "no support for WwanProfileUpdateRenamed"
0x18002c34b  xor     edx, edx; struct _GUID *
0x18002c34d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002c352  jmp     loc_18002C778
0x18002c357  mov     eax, [rbx+311Ch]
0x18002c35d  lea     rdi, [rbx+30F8h]
0x18002c364  mov     [rsp+1BE0h+var_1BB8], eax
0x18002c368  lea     r9, [rbp+1AE0h+var_220]
0x18002c36f  lea     rax, [rbp+1AE0h+sz]
0x18002c376  mov     rdx, rdi; struct _GUID *
0x18002c379  lea     r8, aOpDeleteOnProf; "Op DELETE on Profile {%s} (Modem %s EXE"...
0x18002c380  mov     [rsp+1BE0h+var_1BC0], rax
0x18002c385  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002c38a  xor     r9d, r9d; unsigned int
0x18002c38d  lea     rax, [rbp+1AE0h+var_220]
0x18002c394  mov     [rsp+1BE0h+var_1BB0], rax; void *
0x18002c399  mov     r8, rdi; struct _GUID *
0x18002c39c  mov     [rsp+1BE0h+var_1BB8], 200h; unsigned int
0x18002c3a4  mov     edx, esi; unsigned int
0x18002c3a6  mov     [rsp+1BE0h+var_1BC0], r14; void *
0x18002c3ab  lea     ecx, [r9+2]; unsigned int
0x18002c3af  call    ?WwanNhNotificationDispatcherWithHeader@@YAXKKPEBU_GUID@@KPEBXK1@Z; WwanNhNotificationDispatcherWithHeader(ulong,ulong,_GUID const *,ulong,void const *,ulong,void const *)
0x18002c3b4  test    cs:byte_1801528C4, 10h
0x18002c3bb  jz      short loc_18002C3E9
0x18002c3bd  mov     r9d, [rbx+3118h]
0x18002c3c4  lea     rax, [rbp+1AE0h+var_220]
0x18002c3cb  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c3d0  lea     rdx, PMDeleteProfile
0x18002c3d7  mov     eax, [rbx+311Ch]
0x18002c3dd  mov     r8, rdi
0x18002c3e0  mov     dword ptr [rsp+1BE0h+var_1BC0], eax
0x18002c3e4  call    McTemplateU0jdqz_EventWriteTransfer
0x18002c3e9  lea     rdx, [rbp+1AE0h+var_220]; unsigned __int16 *
0x18002c3f0  mov     rcx, rbx; this
0x18002c3f3  call    ?DeleteProfileW@CWwanDataExecutor@@AEAAKPEBG@Z; CWwanDataExecutor::DeleteProfileW(ushort const *)
0x18002c3f8  jmp     loc_18002C778
0x18002c3fd  mov     r14d, 1
0x18002c403  lea     rax, aUpdate; "UPDATE"
0x18002c40a  test    r14d, r14d
0x18002c40d  lea     r9, aCreate; "CREATE"
0x18002c414  cmovz   r9, rax
0x18002c418  lea     rsi, [rbx+30F8h]
0x18002c41f  mov     eax, [rbx+311Ch]
0x18002c425  lea     r8, aOpSOnProfileSM; "Op %s on Profile {%s} (Modem %s EXEC %d"...
0x18002c42c  mov     dword ptr [rsp+1BE0h+var_1BB0], eax
0x18002c430  lea     rcx, aCwwandataexecu_77; "CWwanDataExecutor::OnPmProfileUpdate"
0x18002c437  lea     rax, [rbp+1AE0h+sz]
0x18002c43e  mov     rdx, rsi; struct _GUID *
0x18002c441  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c446  lea     rax, [rbp+1AE0h+var_220]
0x18002c44d  mov     [rsp+1BE0h+var_1BC0], rax
0x18002c452  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002c457  xorps   xmm0, xmm0
0x18002c45a  lea     rcx, [rbp+1AE0h+var_1B60]; void *
0x18002c45e  movups  xmmword ptr [rbp+1AE0h+var_2A0], xmm0
0x18002c465  xor     edx, edx; Val
0x18002c467  mov     r8d, 18B0h; Size
0x18002c46d  movups  xmmword ptr [rbp+1AE0h+var_2A0+0Ah], xmm0
0x18002c474  movups  xmmword ptr [rbp+1AE0h+var_2B0], xmm0
0x18002c47b  call    memset_0
0x18002c480  lea     rcx, [rbp+1AE0h+var_1B60]
0x18002c484  call    cs:__imp_WwanProfileInit
0x18002c48a  lea     rdx, [rbp+1AE0h+var_2B0]; unsigned __int16 *
0x18002c491  mov     rcx, rbx; this
0x18002c494  call    ?GetExecutorICCID@CWwanDataExecutorState@@QEAAKPEAGK@Z; CWwanDataExecutorState::GetExecutorICCID(ushort *,ulong)
0x18002c499  test    eax, eax
0x18002c49b  jz      short loc_18002C4F3
0x18002c49d  mov     r9d, eax
0x18002c4a0  lea     r8, aDataExecutorIs; "Data Executor is not ready with ICCID %"...
0x18002c4a7  xor     edx, edx; struct _GUID *
0x18002c4a9  lea     rcx, aCwwandataexecu_77; "CWwanDataExecutor::OnPmProfileUpdate"
0x18002c4b0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002c4b5  test    cs:byte_1801528C4, 10h
0x18002c4bc  jz      loc_18002C778
0x18002c4c2  mov     r9d, [rbx+3118h]
0x18002c4c9  lea     rax, [rbp+1AE0h+var_220]
0x18002c4d0  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c4d5  lea     rdx, CreateUpdateProfileBeforeICCIDArrive
0x18002c4dc  mov     eax, [rbx+311Ch]
0x18002c4e2  mov     r8, rsi
0x18002c4e5  mov     dword ptr [rsp+1BE0h+var_1BC0], eax
0x18002c4e9  call    McTemplateU0jdqz_EventWriteTransfer
0x18002c4ee  jmp     loc_18002C778
0x18002c4f3  lea     r8, [rbp+1AE0h+var_1B60]
0x18002c4f7  lea     rdx, [rbp+1AE0h+var_220]
0x18002c4fe  lea     rcx, [rbp+1AE0h+var_2B0]
0x18002c505  call    WwanPmGetProfileStruct
0x18002c50a  test    eax, eax
0x18002c50c  jz      short loc_18002C569
0x18002c50e  mov     r9d, eax
0x18002c511  lea     r8, aWwanpmgetprofi_5; "WwanPmGetProfileStruct() failed: %u"
0x18002c518  xor     edx, edx; struct _GUID *
0x18002c51a  lea     rcx, aCwwandataexecu_77; "CWwanDataExecutor::OnPmProfileUpdate"
0x18002c521  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002c526  test    cs:byte_1801528C4, 20h
0x18002c52d  jz      loc_18002C778
0x18002c533  mov     r9d, [rbx+3118h]
0x18002c53a  lea     rax, [rbp+1AE0h+var_220]
0x18002c541  mov     [rsp+1BE0h+var_1BB0], rax
0x18002c546  mov     r8, rsi
0x18002c549  lea     rax, [rbp+1AE0h+var_2B0]
0x18002c550  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c555  mov     eax, [rbx+311Ch]
0x18002c55b  mov     dword ptr [rsp+1BE0h+var_1BC0], eax
0x18002c55f  call    McTemplateU0jdqzz_EventWriteTransfer
0x18002c564  jmp     loc_18002C778
0x18002c569  lea     r9, [rsp+1BE0h+var_1B68]
0x18002c56e  xor     edx, edx
0x18002c570  lea     r8, [rsp+1BE0h+var_1B70]
0x18002c575  lea     rcx, [rbp+1AE0h+var_220]
0x18002c57c  call    ?CreateProfileIstream@CWwanManager@@SAKPEBGW4WWAN_PROFILE_PASSWORD_PROTECTION@@PEAKPEAPEAE@Z; CWwanManager::CreateProfileIstream(ushort const *,WWAN_PROFILE_PASSWORD_PROTECTION,ulong *,uchar * *)
0x18002c581  test    eax, eax
0x18002c583  jz      short loc_18002C5A2
0x18002c585  mov     r9d, eax
0x18002c588  lea     r8, aFailedFromCrea; "failed from CreateProfileIstream [error"...
0x18002c58f  xor     edx, edx; struct _GUID *
0x18002c591  lea     rcx, aCwwandataexecu_77; "CWwanDataExecutor::OnPmProfileUpdate"
0x18002c598  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002c59d  jmp     loc_18002C76E
0x18002c5a2  mov     rax, [rsp+1BE0h+var_1B68]
0x18002c5a7  movups  xmm0, xmmword ptr [rdi+408h]
0x18002c5ae  movups  xmmword ptr [rax+18B0h], xmm0
0x18002c5b5  movups  xmm1, xmmword ptr [rdi+418h]
0x18002c5bc  movups  xmmword ptr [rax+18C0h], xmm1
0x18002c5c3  movsd   xmm0, qword ptr [rdi+428h]
0x18002c5cb  movsd   qword ptr [rax+18D0h], xmm0
0x18002c5d3  test    r14d, r14d
0x18002c5d6  jz      loc_18002C69C
0x18002c5dc  test    cs:byte_1801528C4, 10h
0x18002c5e3  jz      short loc_18002C660
0x18002c5e5  mov     eax, [rbp+1AE0h+var_9F0]
0x18002c5eb  xor     edx, edx
0x18002c5ed  cmp     [rbp+1AE0h+var_954], edx
0x18002c5f3  mov     r8, rsi
0x18002c5f6  mov     ecx, [rbp+1AE0h+var_F5C]
0x18002c5fc  mov     r9d, [rbx+3118h]
0x18002c603  setnz   dl
0x18002c606  mov     [rsp+1BE0h+var_1B80], eax
0x18002c60a  lea     rax, [rbp+1AE0h+var_ED8]
0x18002c611  mov     [rsp+1BE0h+var_1B88], rax
0x18002c616  mov     eax, [rbp+1AE0h+var_5C0]
0x18002c61c  mov     [rsp+1BE0h+var_1B90], eax
0x18002c620  mov     eax, [rbp+1AE0h+var_EE4]
0x18002c626  mov     [rsp+1BE0h+var_1B98], ecx
0x18002c62a  mov     [rsp+1BE0h+var_1BA0], edx
0x18002c62e  lea     rdx, PMAddProfile
0x18002c635  mov     [rsp+1BE0h+var_1BA8], eax
0x18002c639  lea     rax, [rbp+1AE0h+var_2B0]
0x18002c640  mov     [rsp+1BE0h+var_1BB0], rax
0x18002c645  lea     rax, [rbp+1AE0h+var_220]
0x18002c64c  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c651  mov     eax, [rbx+311Ch]
0x18002c657  mov     dword ptr [rsp+1BE0h+var_1BC0], eax
0x18002c65b  call    McTemplateU0jdqzzqtqqzq_EventWriteTransfer
0x18002c660  cmp     [rbp+1AE0h+var_954], 0
0x18002c667  jz      short loc_18002C692
0x18002c669  cmp     [rbp+1AE0h+var_9E0], 0
0x18002c670  jnz     short loc_18002C692
0x18002c672  lea     rdx, [rbp+1AE0h+var_1B60]; struct WWAN_PROFILE *
0x18002c676  mov     rcx, rbx; this
0x18002c679  call    ?AddUserMMSProfile@CWwanDataExecutor@@AEAAXAEBUWWAN_PROFILE@@@Z; CWwanDataExecutor::AddUserMMSProfile(WWAN_PROFILE const &)
0x18002c67e  lea     rcx, [rbp+1AE0h+var_1B60]
0x18002c682  call    cs:__imp_WwanProfileCleanup
0x18002c688  lea     rcx, [rbp+1AE0h+var_1B60]
0x18002c68c  call    cs:__imp_WwanProfileDeinit
0x18002c692  mov     edx, 2Dh ; '-'
0x18002c697  jmp     loc_18002C731
0x18002c69c  test    cs:byte_1801528C4, 10h
0x18002c6a3  jz      short loc_18002C720
0x18002c6a5  mov     eax, [rbp+1AE0h+var_9F0]
0x18002c6ab  xor     edx, edx
0x18002c6ad  cmp     [rbp+1AE0h+var_954], edx
0x18002c6b3  mov     r8, rsi
0x18002c6b6  mov     ecx, [rbp+1AE0h+var_F5C]
0x18002c6bc  mov     r9d, [rbx+3118h]
0x18002c6c3  setnz   dl
0x18002c6c6  mov     [rsp+1BE0h+var_1B80], eax
0x18002c6ca  lea     rax, [rbp+1AE0h+var_ED8]
0x18002c6d1  mov     [rsp+1BE0h+var_1B88], rax
0x18002c6d6  mov     eax, [rbp+1AE0h+var_5C0]
0x18002c6dc  mov     [rsp+1BE0h+var_1B90], eax
0x18002c6e0  mov     eax, [rbp+1AE0h+var_EE4]
0x18002c6e6  mov     [rsp+1BE0h+var_1B98], ecx
0x18002c6ea  mov     [rsp+1BE0h+var_1BA0], edx
0x18002c6ee  lea     rdx, PMUpdateProfile
0x18002c6f5  mov     [rsp+1BE0h+var_1BA8], eax
0x18002c6f9  lea     rax, [rbp+1AE0h+var_2B0]
0x18002c700  mov     [rsp+1BE0h+var_1BB0], rax
0x18002c705  lea     rax, [rbp+1AE0h+var_220]
0x18002c70c  mov     qword ptr [rsp+1BE0h+var_1BB8], rax
0x18002c711  mov     eax, [rbx+311Ch]
0x18002c717  mov     dword ptr [rsp+1BE0h+var_1BC0], eax
0x18002c71b  call    McTemplateU0jdqzzqtqqzq_EventWriteTransfer
0x18002c720  lea     rdx, [rbp+1AE0h+var_1B60]; struct WWAN_PROFILE *
0x18002c724  mov     rcx, rbx; this
0x18002c727  call    ?UpdateProfile@CWwanDataExecutor@@AEAAKAEAUWWAN_PROFILE@@@Z; CWwanDataExecutor::UpdateProfile(WWAN_PROFILE &)
0x18002c72c  mov     edx, 2Eh ; '.'; unsigned int
0x18002c731  mov     rax, [rsp+1BE0h+var_1B68]
0x18002c736  xor     r9d, r9d; unsigned int
0x18002c739  mov     [rsp+1BE0h+var_1BB0], rax; void *
0x18002c73e  mov     r8, rsi; struct _GUID *
0x18002c741  mov     eax, [rsp+1BE0h+var_1B70]
0x18002c745  mov     [rsp+1BE0h+var_1BB8], eax; unsigned int
0x18002c749  lea     ecx, [r9+2]; unsigned int
0x18002c74d  mov     [rsp+1BE0h+var_1BC0], 0; void *
0x18002c756  call    ?WwanNhNotificationDispatcherWithHeader@@YAXKKPEBU_GUID@@KPEBXK1@Z; WwanNhNotificationDispatcherWithHeader(ulong,ulong,_GUID const *,ulong,void const *,ulong,void const *)
0x18002c75b  mov     rcx, [rsp+1BE0h+var_1B68]
0x18002c760  call    WwanMemFree
0x18002c765  mov     [rsp+1BE0h+var_1B68], 0
0x18002c76e  lea     rcx, [rbp+1AE0h+var_1B60]
0x18002c772  call    cs:__imp_WwanProfileCleanup
0x18002c778  mov     rcx, [rbp+1AE0h+var_20]
0x18002c77f  xor     rcx, rsp; StackCookie
0x18002c782  call    __security_check_cookie
0x18002c787  lea     r11, [rsp+1BE0h+var_10]
0x18002c78f  mov     rbx, [r11+30h]
0x18002c793  mov     rsi, [r11+38h]
0x18002c797  mov     rsp, r11
0x18002c79a  pop     r14
0x18002c79c  pop     rdi
0x18002c79d  pop     rbp
0x18002c79e  retn
```
