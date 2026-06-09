# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x18006c43c`
- end: `0x18006c876`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c3a8`

## callees

- `0x180017f34`
- `0x180018df0`
- `0x180019328`
- `0x18001f840`
- `0x1800217cc`
- `0x180026dc0`
- `0x180026e00`
- `0x180026e18`
- `0x18002d2b0`
- `0x180047884`
- `0x18006c43c`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x18006c6fb`
- `ntdll!NtAdjustPrivilegesToken` at `0x18006c6fb`
- `ntdll!NtOpenProcessToken` at `0x18006c595`
- `ntdll!NtOpenProcessToken` at `0x18006c595`
- `ntdll!NtDuplicateToken` at `0x18006c6a0`
- `ntdll!NtDuplicateToken` at `0x18006c6a0`
- `ntdll!NtOpenThreadToken` at `0x18006c568`
- `ntdll!NtOpenThreadToken` at `0x18006c568`
- `ntdll!NtSetInformationThread` at `0x18006c763`
- `ntdll!NtSetInformationThread` at `0x18006c763`
- `ntdll!RtlRaiseStatus` at `0x18006c869`
- `ntdll!RtlRaiseStatus` at `0x18006c869`

## string_xrefs

- `0x18006c5a5`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c60f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c6b0`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c70d`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c773`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c816`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c5bf`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c62b`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c6c9`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c727`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c78a`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c830`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c829`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x18006c5cb`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x18006c6d5`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`
- `0x18006c795`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`

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
  __int64 v17; // rdx
  __int64 v18; // r8
  void **v19; // rax
  NTSTATUS v20; // eax
  _QWORD *v21; // rdx
  int v22; // esi
  char v23; // r14
  void **NewTokenHandle; // rax
  NTSTATUS v25; // edx
  HANDLE v26; // rcx
  _QWORD v28[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v29[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v33[4]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE ThreadInformation; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  int v36; // [rsp+128h] [rbp+28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+130h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v39[4]; // [rsp+140h] [rbp+40h] BYREF

  *a3 = 0;
  v36 = 0;
  TokenHandle = 0;
  ExistingTokenHandle = 0;
  ThreadInformation = 0;
  if ( *(_BYTE *)(a1 + 8) || *(_QWORD *)a1 )
    RtlRaiseStatus(-1073741595);
  v6 = BUCL::Rtl::Multiply<unsigned __int64>(a2[1], 12, &ThreadInformation);
  if ( v6 < 0 )
    goto LABEL_39;
  if ( (unsigned __int64)ThreadInformation >= 0xFFFFFFFFFFFFFFEFuLL
    || (v7 = (struct _TOKEN_PRIVILEGES *)operator new((size_t)ThreadInformation + 16), (v8 = v7) == 0) )
  {
    v33[2] = 632;
    v33[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v33[3] = "TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)";
    v33[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v36,
           v33);
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
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                           &ExistingTokenHandle,
                           i);
  v16 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2Eu, 1u, InitPointer);
  v18 = (unsigned int)v16;
  if ( v16 == -1073741700 )
  {
    v19 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                     &ExistingTokenHandle,
                     v17);
    v20 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2Eu, v19);
    if ( v20 < 0 )
    {
      v28[2] = 660;
      v28[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v21 = v28;
      v28[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v28[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.G"
               "etInitPointer())";
LABEL_16:
      v18 = (unsigned int)v20;
LABEL_17:
      v22 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v36,
              v21,
              v18);
      if ( v9 )
        operator delete(v8);
      else
        operator delete(v8, (const struct std::nothrow_t *)0x10);
      v6 = v22;
      goto LABEL_39;
    }
    v23 = 0;
  }
  else
  {
    if ( v16 < 0 )
    {
      v29[2] = 666;
      v29[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v29[3] = "Status";
      v29[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v21 = v29;
      goto LABEL_17;
    }
    v23 = 1;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = v39;
  v39[2] = 1;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v39[0] = 12;
  v39[1] = 2;
  NewTokenHandle = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                              &TokenHandle,
                              v17);
  v20 = NtDuplicateToken(ExistingTokenHandle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, NewTokenHandle);
  if ( v20 < 0 )
  {
    v30[2] = 686;
    v30[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v21 = v30;
    v30[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v30[3] = "NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())";
    goto LABEL_16;
  }
  v25 = NtAdjustPrivilegesToken(TokenHandle, 0, v8, 0, 0, 0);
  if ( v25 < 0 )
  {
    v31[2] = 697;
    v31[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v31[3] = "Status";
    v18 = (unsigned int)v25;
    v31[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v21 = v31;
    goto LABEL_17;
  }
  if ( v25 != 262 )
  {
    ThreadInformation = TokenHandle;
    v20 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v20 < 0 )
    {
      v32[2] = 718;
      v32[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v21 = v32;
      v32[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v32[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))";
      goto LABEL_16;
    }
    *(_BYTE *)(a1 + 8) = 1;
    *a3 = 1;
    if ( v23 )
    {
      v26 = ExistingTokenHandle;
      ExistingTokenHandle = *(HANDLE *)a1;
      *(_QWORD *)a1 = v26;
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
0x18006c43c  mov     [rsp-8+arg_18], rbx
0x18006c441  push    rbp
0x18006c442  push    rsi
0x18006c443  push    rdi
0x18006c444  push    r12
0x18006c446  push    r13
0x18006c448  push    r14
0x18006c44a  push    r15
0x18006c44c  lea     rbp, [rsp-60h]
0x18006c451  sub     rsp, 160h
0x18006c458  mov     rax, cs:__security_cookie
0x18006c45f  xor     rax, rsp
0x18006c462  mov     [rbp+90h+var_40], rax
0x18006c466  xor     r13d, r13d
0x18006c469  mov     r12, r8
0x18006c46c  mov     [r8], r13b
0x18006c46f  mov     r14, rdx
0x18006c472  mov     rsi, rcx
0x18006c475  mov     [rbp+90h+var_68], r13d
0x18006c479  mov     [rbp+90h+TokenHandle], r13
0x18006c47d  mov     [rbp+90h+ExistingTokenHandle], r13
0x18006c481  mov     [rbp+90h+ThreadInformation], r13
0x18006c485  cmp     [rcx+8], r13b
0x18006c489  jnz     loc_18006C864
0x18006c48f  cmp     [rcx], r13
0x18006c492  jnz     loc_18006C864
0x18006c498  mov     rcx, [r14+8]
0x18006c49c  lea     r8, [rbp+90h+ThreadInformation]
0x18006c4a0  lea     edx, [r13+0Ch]
0x18006c4a4  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18006c4a9  mov     ebx, eax
0x18006c4ab  test    eax, eax
0x18006c4ad  js      loc_18006C84E
0x18006c4b3  mov     rcx, [rbp+90h+ThreadInformation]
0x18006c4b7  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18006c4bb  jnb     loc_18006C816
0x18006c4c1  add     rcx, 10h; Size
0x18006c4c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c4ca  mov     rbx, rax
0x18006c4cd  test    rax, rax
0x18006c4d0  jz      loc_18006C816
0x18006c4d6  mov     rcx, [r14+8]
0x18006c4da  lea     rdi, [rax+10h]
0x18006c4de  mov     rdx, rax
0x18006c4e1  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x18006c4e6  mov     r15d, eax
0x18006c4e9  test    eax, eax
0x18006c4eb  jns     short loc_18006C50E
0x18006c4ed  mov     rcx, rdx; void *
0x18006c4f0  test    rdi, rdi
0x18006c4f3  jz      short loc_18006C4FC
0x18006c4f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c4fa  jmp     short loc_18006C506
0x18006c4fc  mov     edx, 10h; struct std::nothrow_t *
0x18006c501  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c506  mov     ebx, r15d
0x18006c509  jmp     loc_18006C84E
0x18006c50e  mov     rdx, r13
0x18006c511  cmp     [r14+8], r13
0x18006c515  jbe     short loc_18006C546
0x18006c517  mov     rax, [r14]
0x18006c51a  lea     rcx, [rdx+rdx*2]
0x18006c51e  movsxd  rax, dword ptr [rax+rdx*4]
0x18006c522  inc     rdx
0x18006c525  mov     dword ptr [rbp+90h+ThreadInformation], eax
0x18006c528  shr     rax, 20h
0x18006c52c  mov     dword ptr [rbp+90h+ThreadInformation+4], eax
0x18006c52f  mov     rax, [rbp+90h+ThreadInformation]
0x18006c533  mov     [rbx+rcx*4+4], rax
0x18006c538  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x18006c540  cmp     rdx, [r14+8]
0x18006c544  jb      short loc_18006C517
0x18006c546  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c54a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c54f  mov     r14d, 2Eh ; '.'
0x18006c555  mov     r15, 0FFFFFFFFFFFFFFFEh
0x18006c55c  mov     edx, r14d; DesiredAccess
0x18006c55f  mov     rcx, r15; ThreadHandle
0x18006c562  mov     r9, rax; TokenHandle
0x18006c565  mov     r8b, 1; OpenAsSelf
0x18006c568  call    cs:__imp_NtOpenThreadToken
0x18006c56f  nop     dword ptr [rax+rax+00h]
0x18006c574  mov     r8d, eax
0x18006c577  cmp     eax, 0C000007Ch
0x18006c57c  jnz     loc_18006C60A
0x18006c582  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c586  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c58b  mov     r8, rax; TokenHandle
0x18006c58e  mov     edx, r14d; DesiredAccess
0x18006c591  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006c595  call    cs:__imp_NtOpenProcessToken
0x18006c59c  nop     dword ptr [rax+rax+00h]
0x18006c5a1  test    eax, eax
0x18006c5a3  jns     short loc_18006C605
0x18006c5a5  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c5ac  mov     [rsp+190h+var_150], 294h
0x18006c5b5  mov     [rsp+190h+var_160], rcx
0x18006c5ba  lea     rdx, [rsp+190h+var_160]
0x18006c5bf  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c5c6  mov     [rsp+190h+var_158], rcx
0x18006c5cb  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18006c5d2  mov     [rsp+190h+var_148], rcx
0x18006c5d7  mov     r8d, eax
0x18006c5da  lea     rcx, [rbp+90h+var_68]
0x18006c5de  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006c5e3  mov     esi, eax
0x18006c5e5  mov     rcx, rbx; void *
0x18006c5e8  test    rdi, rdi
0x18006c5eb  jz      short loc_18006C5F4
0x18006c5ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c5f2  jmp     short loc_18006C5FE
0x18006c5f4  mov     edx, 10h; struct std::nothrow_t *
0x18006c5f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c5fe  mov     ebx, esi
0x18006c600  jmp     loc_18006C84E
0x18006c605  mov     r14b, r13b
0x18006c608  jmp     short loc_18006C646
0x18006c60a  test    r8d, r8d
0x18006c60d  jns     short loc_18006C643
0x18006c60f  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c616  mov     [rsp+190h+var_130], 29Ah
0x18006c61f  mov     [rsp+190h+var_140], rcx
0x18006c624  lea     rax, aStatus; "Status"
0x18006c62b  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c632  mov     [rsp+190h+var_128], rax
0x18006c637  mov     [rsp+190h+var_138], rcx
0x18006c63c  lea     rdx, [rsp+190h+var_140]
0x18006c641  jmp     short loc_18006C5DA
0x18006c643  mov     r14b, 1
0x18006c646  lea     rax, [rbp+90h+var_50]
0x18006c64a  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18006c652  lea     rcx, [rbp+90h+TokenHandle]
0x18006c656  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x18006c65a  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], r13
0x18006c65e  mov     [rbp+90h+var_48], 1
0x18006c665  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x18006c669  mov     [rbp+90h+ObjectAttributes.ObjectName], r13
0x18006c66d  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r13
0x18006c671  mov     [rbp+90h+var_50], 0Ch
0x18006c678  mov     [rbp+90h+var_4C], 2
0x18006c67f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c684  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x18006c688  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18006c68c  xor     r9d, r9d; EffectiveOnly
0x18006c68f  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x18006c694  mov     [rsp+190h+TokenType], 2; TokenType
0x18006c69c  lea     edx, [r9+2Ch]; DesiredAccess
0x18006c6a0  call    cs:__imp_NtDuplicateToken
0x18006c6a7  nop     dword ptr [rax+rax+00h]
0x18006c6ac  test    eax, eax
0x18006c6ae  jns     short loc_18006C6E5
0x18006c6b0  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c6b7  mov     [rbp+90h+var_110], 2AEh
0x18006c6bf  mov     [rsp+190h+var_120], rcx
0x18006c6c4  lea     rdx, [rsp+190h+var_120]
0x18006c6c9  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c6d0  mov     [rsp+190h+var_118], rcx
0x18006c6d5  lea     rcx, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x18006c6dc  mov     [rbp+90h+var_108], rcx
0x18006c6e0  jmp     loc_18006C5D7
0x18006c6e5  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x18006c6e9  xor     r9d, r9d; BufferLength
0x18006c6ec  mov     [rsp+190h+NewTokenHandle], r13; ReturnLength
0x18006c6f1  mov     r8, rbx; NewState
0x18006c6f4  xor     edx, edx; DisableAllPrivileges
0x18006c6f6  mov     qword ptr [rsp+190h+TokenType], r13; PreviousState
0x18006c6fb  call    cs:__imp_NtAdjustPrivilegesToken
0x18006c702  nop     dword ptr [rax+rax+00h]
0x18006c707  mov     edx, eax
0x18006c709  test    eax, eax
0x18006c70b  jns     short loc_18006C742
0x18006c70d  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c714  mov     [rbp+90h+var_F0], 2B9h
0x18006c71c  mov     [rbp+90h+var_100], rcx
0x18006c720  lea     rax, aStatus; "Status"
0x18006c727  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c72e  mov     [rbp+90h+var_E8], rax
0x18006c732  mov     r8d, edx
0x18006c735  mov     [rbp+90h+var_F8], rcx
0x18006c739  lea     rdx, [rbp+90h+var_100]
0x18006c73d  jmp     loc_18006C5DA
0x18006c742  cmp     edx, 106h
0x18006c748  jz      short loc_18006C7C1
0x18006c74a  mov     rax, [rbp+90h+TokenHandle]
0x18006c74e  lea     r8, [rbp+90h+ThreadInformation]; ThreadInformation
0x18006c752  mov     r9d, 8; ThreadInformationLength
0x18006c758  mov     [rbp+90h+ThreadInformation], rax
0x18006c75c  mov     rcx, r15; ThreadHandle
0x18006c75f  lea     edx, [r9-3]; ThreadInformationClass
0x18006c763  call    cs:__imp_NtSetInformationThread
0x18006c76a  nop     dword ptr [rax+rax+00h]
0x18006c76f  test    eax, eax
0x18006c771  jns     short loc_18006C7A5
0x18006c773  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c77a  mov     [rbp+90h+var_D0], 2CEh
0x18006c782  mov     [rbp+90h+var_E0], rcx
0x18006c786  lea     rdx, [rbp+90h+var_E0]
0x18006c78a  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c791  mov     [rbp+90h+var_D8], rcx
0x18006c795  lea     rcx, aNtsetinformati_0; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x18006c79c  mov     [rbp+90h+var_C8], rcx
0x18006c7a0  jmp     loc_18006C5D7
0x18006c7a5  mov     byte ptr [rsi+8], 1
0x18006c7a9  mov     byte ptr [r12], 1
0x18006c7ae  test    r14b, r14b
0x18006c7b1  jz      short loc_18006C7C1
0x18006c7b3  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c7b7  mov     rax, [rsi]
0x18006c7ba  mov     [rbp+90h+ExistingTokenHandle], rax
0x18006c7be  mov     [rsi], rcx
0x18006c7c1  mov     rcx, rbx; void *
0x18006c7c4  test    rdi, rdi
0x18006c7c7  jz      short loc_18006C7D0
0x18006c7c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c7ce  jmp     short loc_18006C7DA
0x18006c7d0  mov     edx, 10h; struct std::nothrow_t *
0x18006c7d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c7da  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c7de  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c7e3  lea     rcx, [rbp+90h+TokenHandle]
0x18006c7e7  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c7ec  xor     eax, eax
0x18006c7ee  mov     rcx, [rbp+90h+var_40]
0x18006c7f2  xor     rcx, rsp; StackCookie
0x18006c7f5  call    __security_check_cookie
0x18006c7fa  mov     rbx, [rsp+190h+arg_18]
0x18006c802  add     rsp, 160h
0x18006c809  pop     r15
0x18006c80b  pop     r14
0x18006c80d  pop     r13
0x18006c80f  pop     r12
0x18006c811  pop     rdi
0x18006c812  pop     rsi
0x18006c813  pop     rbp
0x18006c814  retn
0x18006c816  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c81d  mov     [rbp+90h+var_B0], 278h
0x18006c825  mov     [rbp+90h+var_C0], rcx
0x18006c829  lea     rax, aTokenprivilege; "TokenPrivileges.AllocateWithExtraBytes("...
0x18006c830  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c837  mov     [rbp+90h+var_A8], rax
0x18006c83b  mov     [rbp+90h+var_B8], rcx
0x18006c83f  lea     rdx, [rbp+90h+var_C0]
0x18006c843  lea     rcx, [rbp+90h+var_68]
0x18006c847  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006c84c  mov     ebx, eax
0x18006c84e  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c852  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c857  lea     rcx, [rbp+90h+TokenHandle]
0x18006c85b  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c860  mov     eax, ebx
0x18006c862  jmp     short loc_18006C7EE
0x18006c864  mov     ecx, 0C00000E5h; Status
0x18006c869  call    cs:__imp_RtlRaiseStatus
0x18006c870  nop     dword ptr [rax+rax+00h]
0x18006c875  int     3; Trap to Debugger
```
