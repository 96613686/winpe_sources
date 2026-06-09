# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x14002606c`
- end: `0x140026482`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140025fd8`

## callees

- `0x140001fa0`
- `0x140002310`
- `0x1400025a4`
- `0x140002b10`
- `0x140006950`
- `0x140006b54`
- `0x14000e66c`
- `0x14000ebb4`
- `0x140025dbc`
- `0x140025e1c`
- `0x14002606c`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x140026315`
- `ntdll!NtAdjustPrivilegesToken` at `0x140026315`
- `ntdll!NtOpenProcessToken` at `0x1400261bb`
- `ntdll!NtOpenProcessToken` at `0x1400261bb`
- `ntdll!NtSetInformationThread` at `0x140026377`
- `ntdll!NtSetInformationThread` at `0x140026377`
- `ntdll!NtDuplicateToken` at `0x1400262c0`
- `ntdll!NtDuplicateToken` at `0x1400262c0`
- `ntdll!NtOpenThreadToken` at `0x140026194`
- `ntdll!NtOpenThreadToken` at `0x140026194`

## string_xrefs

- `0x1400261c5`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002622f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400262ca`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026321`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026381`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026423`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400261df`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x14002624b`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1400262e3`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x14002633b`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x140026398`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x14002643d`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x140026436`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x1400261eb`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x1400262ef`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`
- `0x1400263a3`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  int v6; // ebx
  struct _TOKEN_PRIVILEGES *v7; // rax
  struct _TOKEN_PRIVILEGES *v8; // rbx
  struct _TOKEN_PRIVILEGES *v9; // rdi
  void *v10; // rdx
  int v11; // r15d
  unsigned __int64 i; // rdx
  __int64 v13; // rcx
  LUID v14; // rax
  void **InitPointer; // rax
  NTSTATUS v16; // eax
  __int64 v17; // r8
  void **v18; // rax
  NTSTATUS v19; // eax
  _QWORD *v20; // rdx
  int v21; // esi
  char v22; // r14
  void **NewTokenHandle; // rax
  NTSTATUS v24; // edx
  HANDLE v25; // rcx
  _QWORD v27[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v30[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v31[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v32[4]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE ThreadInformation; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  int v35; // [rsp+128h] [rbp+28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+130h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v38[4]; // [rsp+140h] [rbp+40h] BYREF

  *a3 = 0;
  v35 = 0;
  TokenHandle = 0;
  ExistingTokenHandle = 0;
  ThreadInformation = 0;
  if ( *(_BYTE *)(a1 + 8) || *(_QWORD *)a1 )
    INTERNAL_ERROR_ACTION(-1073741595);
  v6 = BUCL::Rtl::Multiply<unsigned __int64>(a2[1], a2, &ThreadInformation);
  if ( v6 < 0 )
    goto LABEL_39;
  if ( (unsigned __int64)ThreadInformation >= 0xFFFFFFFFFFFFFFEFuLL
    || (v7 = (struct _TOKEN_PRIVILEGES *)operator new((size_t)ThreadInformation + 16), (v8 = v7) == 0) )
  {
    v32[2] = 632;
    v32[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v32[3] = "TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)";
    v32[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v6 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           &v35,
           v32,
           3221225495LL);
LABEL_39:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
    return (unsigned int)v6;
  }
  v9 = v7 + 1;
  v11 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(a2[1], v7);
  if ( v11 < 0 )
  {
    if ( v9 )
      operator delete(v10);
    else
      operator delete(v10, (const struct std::nothrow_t *)0x10);
    v6 = v11;
    goto LABEL_39;
  }
  for ( i = 0; i < a2[1]; v8->Privileges[v13].Attributes = 2 )
  {
    v13 = i;
    v14 = (LUID)*(int *)(*a2 + 4 * i++);
    ThreadInformation = (HANDLE)v14;
    v8->Privileges[v13].Luid = v14;
  }
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&ExistingTokenHandle);
  v16 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2Eu, 1u, InitPointer);
  v17 = (unsigned int)v16;
  if ( v16 == -1073741700 )
  {
    v18 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&ExistingTokenHandle);
    v19 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2Eu, v18);
    if ( v19 < 0 )
    {
      v27[2] = 660;
      v27[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v20 = v27;
      v27[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v27[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.G"
               "etInitPointer())";
LABEL_16:
      v17 = (unsigned int)v19;
LABEL_17:
      v21 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
              &v35,
              v20,
              v17);
      if ( v9 )
        operator delete(v8);
      else
        operator delete(v8, (const struct std::nothrow_t *)0x10);
      v6 = v21;
      goto LABEL_39;
    }
    v22 = 0;
  }
  else
  {
    if ( v16 < 0 )
    {
      v28[2] = 666;
      v28[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v28[3] = "Status";
      v28[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v20 = v28;
      goto LABEL_17;
    }
    v22 = 1;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = v38;
  v38[2] = 1;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v38[0] = 12;
  v38[1] = 2;
  NewTokenHandle = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&TokenHandle);
  v19 = NtDuplicateToken(ExistingTokenHandle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, NewTokenHandle);
  if ( v19 < 0 )
  {
    v29[2] = 686;
    v29[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v20 = v29;
    v29[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v29[3] = "NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())";
    goto LABEL_16;
  }
  v24 = NtAdjustPrivilegesToken(TokenHandle, 0, v8, 0, 0, 0);
  if ( v24 < 0 )
  {
    v30[2] = 697;
    v30[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v30[3] = "Status";
    v17 = (unsigned int)v24;
    v30[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v20 = v30;
    goto LABEL_17;
  }
  if ( v24 != 262 )
  {
    ThreadInformation = TokenHandle;
    v19 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v19 < 0 )
    {
      v31[2] = 718;
      v31[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v20 = v31;
      v31[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v31[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))";
      goto LABEL_16;
    }
    *(_BYTE *)(a1 + 8) = 1;
    *a3 = 1;
    if ( v22 )
    {
      v25 = ExistingTokenHandle;
      ExistingTokenHandle = *(HANDLE *)a1;
      *(_QWORD *)a1 = v25;
    }
  }
  if ( v9 )
    operator delete(v8);
  else
    operator delete(v8, (const struct std::nothrow_t *)0x10);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x14002606c  mov     [rsp-8+arg_18], rbx
0x140026071  push    rbp
0x140026072  push    rsi
0x140026073  push    rdi
0x140026074  push    r12
0x140026076  push    r13
0x140026078  push    r14
0x14002607a  push    r15
0x14002607c  lea     rbp, [rsp-60h]
0x140026081  sub     rsp, 160h
0x140026088  mov     rax, cs:__security_cookie
0x14002608f  xor     rax, rsp
0x140026092  mov     [rbp+90h+var_40], rax
0x140026096  xor     r13d, r13d
0x140026099  mov     r12, r8
0x14002609c  mov     [r8], r13b
0x14002609f  mov     r14, rdx
0x1400260a2  mov     rsi, rcx
0x1400260a5  mov     [rbp+90h+var_68], r13d
0x1400260a9  mov     [rbp+90h+TokenHandle], r13
0x1400260ad  mov     [rbp+90h+ExistingTokenHandle], r13
0x1400260b1  mov     [rbp+90h+ThreadInformation], r13
0x1400260b5  cmp     [rcx+8], r13b
0x1400260b9  jnz     loc_140026477
0x1400260bf  cmp     [rcx], r13
0x1400260c2  jnz     loc_140026477
0x1400260c8  mov     rcx, [rdx+8]
0x1400260cc  lea     r8, [rbp+90h+ThreadInformation]
0x1400260d0  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1400260d5  mov     ebx, eax
0x1400260d7  test    eax, eax
0x1400260d9  js      loc_140026461
0x1400260df  mov     rcx, [rbp+90h+ThreadInformation]
0x1400260e3  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x1400260e7  jnb     loc_140026423
0x1400260ed  add     rcx, 10h; Size
0x1400260f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400260f6  mov     rbx, rax
0x1400260f9  test    rax, rax
0x1400260fc  jz      loc_140026423
0x140026102  mov     rcx, [r14+8]
0x140026106  lea     rdi, [rax+10h]
0x14002610a  mov     rdx, rax
0x14002610d  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x140026112  mov     r15d, eax
0x140026115  test    eax, eax
0x140026117  jns     short loc_14002613A
0x140026119  mov     rcx, rdx; void *
0x14002611c  test    rdi, rdi
0x14002611f  jz      short loc_140026128
0x140026121  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140026126  jmp     short loc_140026132
0x140026128  mov     edx, 10h; struct std::nothrow_t *
0x14002612d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140026132  mov     ebx, r15d
0x140026135  jmp     loc_140026461
0x14002613a  mov     rdx, r13
0x14002613d  cmp     [r14+8], r13
0x140026141  jbe     short loc_140026172
0x140026143  mov     rax, [r14]
0x140026146  lea     rcx, [rdx+rdx*2]
0x14002614a  movsxd  rax, dword ptr [rax+rdx*4]
0x14002614e  inc     rdx
0x140026151  mov     dword ptr [rbp+90h+ThreadInformation], eax
0x140026154  shr     rax, 20h
0x140026158  mov     dword ptr [rbp+90h+ThreadInformation+4], eax
0x14002615b  mov     rax, [rbp+90h+ThreadInformation]
0x14002615f  mov     [rbx+rcx*4+4], rax
0x140026164  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x14002616c  cmp     rdx, [r14+8]
0x140026170  jb      short loc_140026143
0x140026172  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x140026176  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x14002617b  mov     r14d, 2Eh ; '.'
0x140026181  mov     r15, 0FFFFFFFFFFFFFFFEh
0x140026188  mov     edx, r14d; DesiredAccess
0x14002618b  mov     rcx, r15; ThreadHandle
0x14002618e  mov     r9, rax; TokenHandle
0x140026191  mov     r8b, 1; OpenAsSelf
0x140026194  call    cs:__imp_NtOpenThreadToken
0x14002619a  mov     r8d, eax
0x14002619d  cmp     eax, 0C000007Ch
0x1400261a2  jnz     loc_14002622A
0x1400261a8  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x1400261ac  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400261b1  mov     r8, rax; TokenHandle
0x1400261b4  mov     edx, r14d; DesiredAccess
0x1400261b7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400261bb  call    cs:__imp_NtOpenProcessToken
0x1400261c1  test    eax, eax
0x1400261c3  jns     short loc_140026225
0x1400261c5  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400261cc  mov     [rsp+190h+var_150], 294h
0x1400261d5  mov     [rsp+190h+var_160], rcx
0x1400261da  lea     rdx, [rsp+190h+var_160]
0x1400261df  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1400261e6  mov     [rsp+190h+var_158], rcx
0x1400261eb  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1400261f2  mov     [rsp+190h+var_148], rcx
0x1400261f7  mov     r8d, eax
0x1400261fa  lea     rcx, [rbp+90h+var_68]
0x1400261fe  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026203  mov     esi, eax
0x140026205  mov     rcx, rbx; void *
0x140026208  test    rdi, rdi
0x14002620b  jz      short loc_140026214
0x14002620d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140026212  jmp     short loc_14002621E
0x140026214  mov     edx, 10h; struct std::nothrow_t *
0x140026219  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002621e  mov     ebx, esi
0x140026220  jmp     loc_140026461
0x140026225  mov     r14b, r13b
0x140026228  jmp     short loc_140026266
0x14002622a  test    r8d, r8d
0x14002622d  jns     short loc_140026263
0x14002622f  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026236  mov     [rsp+190h+var_130], 29Ah
0x14002623f  mov     [rsp+190h+var_140], rcx
0x140026244  lea     rax, aStatus; "Status"
0x14002624b  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x140026252  mov     [rsp+190h+var_128], rax
0x140026257  mov     [rsp+190h+var_138], rcx
0x14002625c  lea     rdx, [rsp+190h+var_140]
0x140026261  jmp     short loc_1400261FA
0x140026263  mov     r14b, 1
0x140026266  lea     rax, [rbp+90h+var_50]
0x14002626a  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140026272  lea     rcx, [rbp+90h+TokenHandle]
0x140026276  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x14002627a  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], r13
0x14002627e  mov     [rbp+90h+var_48], 1
0x140026285  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x140026289  mov     [rbp+90h+ObjectAttributes.ObjectName], r13
0x14002628d  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r13
0x140026291  mov     [rbp+90h+var_50], 0Ch
0x140026298  mov     [rbp+90h+var_4C], 2
0x14002629f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400262a4  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x1400262a8  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1400262ac  xor     r9d, r9d; EffectiveOnly
0x1400262af  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x1400262b4  mov     [rsp+190h+TokenType], 2; TokenType
0x1400262bc  lea     edx, [r9+2Ch]; DesiredAccess
0x1400262c0  call    cs:__imp_NtDuplicateToken
0x1400262c6  test    eax, eax
0x1400262c8  jns     short loc_1400262FF
0x1400262ca  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400262d1  mov     [rbp+90h+var_110], 2AEh
0x1400262d9  mov     [rsp+190h+var_120], rcx
0x1400262de  lea     rdx, [rsp+190h+var_120]
0x1400262e3  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1400262ea  mov     [rsp+190h+var_118], rcx
0x1400262ef  lea     rcx, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x1400262f6  mov     [rbp+90h+var_108], rcx
0x1400262fa  jmp     loc_1400261F7
0x1400262ff  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x140026303  xor     r9d, r9d; BufferLength
0x140026306  mov     [rsp+190h+NewTokenHandle], r13; ReturnLength
0x14002630b  mov     r8, rbx; NewState
0x14002630e  xor     edx, edx; DisableAllPrivileges
0x140026310  mov     qword ptr [rsp+190h+TokenType], r13; PreviousState
0x140026315  call    cs:__imp_NtAdjustPrivilegesToken
0x14002631b  mov     edx, eax
0x14002631d  test    eax, eax
0x14002631f  jns     short loc_140026356
0x140026321  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026328  mov     [rbp+90h+var_F0], 2B9h
0x140026330  mov     [rbp+90h+var_100], rcx
0x140026334  lea     rax, aStatus; "Status"
0x14002633b  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x140026342  mov     [rbp+90h+var_E8], rax
0x140026346  mov     r8d, edx
0x140026349  mov     [rbp+90h+var_F8], rcx
0x14002634d  lea     rdx, [rbp+90h+var_100]
0x140026351  jmp     loc_1400261FA
0x140026356  cmp     edx, 106h
0x14002635c  jz      short loc_1400263CF
0x14002635e  mov     rax, [rbp+90h+TokenHandle]
0x140026362  lea     r8, [rbp+90h+ThreadInformation]; ThreadInformation
0x140026366  mov     r9d, 8; ThreadInformationLength
0x14002636c  mov     [rbp+90h+ThreadInformation], rax
0x140026370  mov     rcx, r15; ThreadHandle
0x140026373  lea     edx, [r9-3]; ThreadInformationClass
0x140026377  call    cs:__imp_NtSetInformationThread
0x14002637d  test    eax, eax
0x14002637f  jns     short loc_1400263B3
0x140026381  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026388  mov     [rbp+90h+var_D0], 2CEh
0x140026390  mov     [rbp+90h+var_E0], rcx
0x140026394  lea     rdx, [rbp+90h+var_E0]
0x140026398  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x14002639f  mov     [rbp+90h+var_D8], rcx
0x1400263a3  lea     rcx, aNtsetinformati_0; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x1400263aa  mov     [rbp+90h+var_C8], rcx
0x1400263ae  jmp     loc_1400261F7
0x1400263b3  mov     byte ptr [rsi+8], 1
0x1400263b7  mov     byte ptr [r12], 1
0x1400263bc  test    r14b, r14b
0x1400263bf  jz      short loc_1400263CF
0x1400263c1  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x1400263c5  mov     rax, [rsi]
0x1400263c8  mov     [rbp+90h+ExistingTokenHandle], rax
0x1400263cc  mov     [rsi], rcx
0x1400263cf  mov     rcx, rbx; void *
0x1400263d2  test    rdi, rdi
0x1400263d5  jz      short loc_1400263DE
0x1400263d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400263dc  jmp     short loc_1400263E8
0x1400263de  mov     edx, 10h; struct std::nothrow_t *
0x1400263e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400263e8  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x1400263ec  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1400263f1  lea     rcx, [rbp+90h+TokenHandle]
0x1400263f5  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1400263fa  xor     eax, eax
0x1400263fc  mov     rcx, [rbp+90h+var_40]
0x140026400  xor     rcx, rsp; StackCookie
0x140026403  call    __security_check_cookie
0x140026408  mov     rbx, [rsp+190h+arg_18]
0x140026410  add     rsp, 160h
0x140026417  pop     r15
0x140026419  pop     r14
0x14002641b  pop     r13
0x14002641d  pop     r12
0x14002641f  pop     rdi
0x140026420  pop     rsi
0x140026421  pop     rbp
0x140026422  retn
0x140026423  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002642a  mov     [rbp+90h+var_B0], 278h
0x140026432  mov     [rbp+90h+var_C0], rcx
0x140026436  lea     rax, aTokenprivilege; "TokenPrivileges.AllocateWithExtraBytes("...
0x14002643d  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x140026444  mov     [rbp+90h+var_A8], rax
0x140026448  mov     [rbp+90h+var_B8], rcx
0x14002644c  lea     rdx, [rbp+90h+var_C0]
0x140026450  lea     rcx, [rbp+90h+var_68]
0x140026454  mov     r8d, 0C0000017h
0x14002645a  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14002645f  mov     ebx, eax
0x140026461  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x140026465  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14002646a  lea     rcx, [rbp+90h+TokenHandle]
0x14002646e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140026473  mov     eax, ebx
0x140026475  jmp     short loc_1400263FC
0x140026477  mov     ecx, 0C00000E5h; int
0x14002647c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
