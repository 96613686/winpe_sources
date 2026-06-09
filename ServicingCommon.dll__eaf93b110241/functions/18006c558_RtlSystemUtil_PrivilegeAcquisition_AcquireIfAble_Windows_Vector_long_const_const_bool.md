# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x18006c558`
- end: `0x18006c98b`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c4c4`

## callees

- `0x18000e1b4`
- `0x18000ea3c`
- `0x18000f088`
- `0x18001f554`
- `0x18001f5d4`
- `0x18001fd10`
- `0x180022eb0`
- `0x180022ef0`
- `0x180022f08`
- `0x1800293a0`
- `0x180044754`
- `0x18006c558`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x18006c817`
- `ntdll!NtAdjustPrivilegesToken` at `0x18006c817`
- `ntdll!NtOpenProcessToken` at `0x18006c6b1`
- `ntdll!NtOpenProcessToken` at `0x18006c6b1`
- `ntdll!NtDuplicateToken` at `0x18006c7bc`
- `ntdll!NtDuplicateToken` at `0x18006c7bc`
- `ntdll!NtOpenThreadToken` at `0x18006c684`
- `ntdll!NtOpenThreadToken` at `0x18006c684`
- `ntdll!NtSetInformationThread` at `0x18006c87f`
- `ntdll!NtSetInformationThread` at `0x18006c87f`

## string_xrefs

- `0x18006c6c1`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c72b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c7cc`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c829`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c88f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c932`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006c6db`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c747`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c7e5`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c843`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c8a6`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c94c`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006c945`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x18006c6e7`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x18006c8b1`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`
- `0x18006c7f1`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`

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
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18006C98ALL);
  }
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
0x18006c558  mov     [rsp-8+arg_18], rbx
0x18006c55d  push    rbp
0x18006c55e  push    rsi
0x18006c55f  push    rdi
0x18006c560  push    r12
0x18006c562  push    r13
0x18006c564  push    r14
0x18006c566  push    r15
0x18006c568  lea     rbp, [rsp-60h]
0x18006c56d  sub     rsp, 160h
0x18006c574  mov     rax, cs:__security_cookie
0x18006c57b  xor     rax, rsp
0x18006c57e  mov     [rbp+90h+var_40], rax
0x18006c582  xor     r13d, r13d
0x18006c585  mov     r12, r8
0x18006c588  mov     [r8], r13b
0x18006c58b  mov     r14, rdx
0x18006c58e  mov     rsi, rcx
0x18006c591  mov     [rbp+90h+var_68], r13d
0x18006c595  mov     [rbp+90h+TokenHandle], r13
0x18006c599  mov     [rbp+90h+ExistingTokenHandle], r13
0x18006c59d  mov     [rbp+90h+ThreadInformation], r13
0x18006c5a1  cmp     [rcx+8], r13b
0x18006c5a5  jnz     loc_18006C980
0x18006c5ab  cmp     [rcx], r13
0x18006c5ae  jnz     loc_18006C980
0x18006c5b4  mov     rcx, [r14+8]
0x18006c5b8  lea     r8, [rbp+90h+ThreadInformation]
0x18006c5bc  lea     edx, [r13+0Ch]
0x18006c5c0  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18006c5c5  mov     ebx, eax
0x18006c5c7  test    eax, eax
0x18006c5c9  js      loc_18006C96A
0x18006c5cf  mov     rcx, [rbp+90h+ThreadInformation]
0x18006c5d3  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18006c5d7  jnb     loc_18006C932
0x18006c5dd  add     rcx, 10h; Size
0x18006c5e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c5e6  mov     rbx, rax
0x18006c5e9  test    rax, rax
0x18006c5ec  jz      loc_18006C932
0x18006c5f2  mov     rcx, [r14+8]
0x18006c5f6  lea     rdi, [rax+10h]
0x18006c5fa  mov     rdx, rax
0x18006c5fd  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x18006c602  mov     r15d, eax
0x18006c605  test    eax, eax
0x18006c607  jns     short loc_18006C62A
0x18006c609  mov     rcx, rdx; void *
0x18006c60c  test    rdi, rdi
0x18006c60f  jz      short loc_18006C618
0x18006c611  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c616  jmp     short loc_18006C622
0x18006c618  mov     edx, 10h; struct std::nothrow_t *
0x18006c61d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c622  mov     ebx, r15d
0x18006c625  jmp     loc_18006C96A
0x18006c62a  mov     rdx, r13
0x18006c62d  cmp     [r14+8], r13
0x18006c631  jbe     short loc_18006C662
0x18006c633  mov     rax, [r14]
0x18006c636  lea     rcx, [rdx+rdx*2]
0x18006c63a  movsxd  rax, dword ptr [rax+rdx*4]
0x18006c63e  inc     rdx
0x18006c641  mov     dword ptr [rbp+90h+ThreadInformation], eax
0x18006c644  shr     rax, 20h
0x18006c648  mov     dword ptr [rbp+90h+ThreadInformation+4], eax
0x18006c64b  mov     rax, [rbp+90h+ThreadInformation]
0x18006c64f  mov     [rbx+rcx*4+4], rax
0x18006c654  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x18006c65c  cmp     rdx, [r14+8]
0x18006c660  jb      short loc_18006C633
0x18006c662  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c666  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c66b  mov     r14d, 2Eh ; '.'
0x18006c671  mov     r15, 0FFFFFFFFFFFFFFFEh
0x18006c678  mov     edx, r14d; DesiredAccess
0x18006c67b  mov     rcx, r15; ThreadHandle
0x18006c67e  mov     r9, rax; TokenHandle
0x18006c681  mov     r8b, 1; OpenAsSelf
0x18006c684  call    cs:__imp_NtOpenThreadToken
0x18006c68b  nop     dword ptr [rax+rax+00h]
0x18006c690  mov     r8d, eax
0x18006c693  cmp     eax, 0C000007Ch
0x18006c698  jnz     loc_18006C726
0x18006c69e  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c6a2  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c6a7  mov     r8, rax; TokenHandle
0x18006c6aa  mov     edx, r14d; DesiredAccess
0x18006c6ad  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006c6b1  call    cs:__imp_NtOpenProcessToken
0x18006c6b8  nop     dword ptr [rax+rax+00h]
0x18006c6bd  test    eax, eax
0x18006c6bf  jns     short loc_18006C721
0x18006c6c1  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c6c8  mov     [rsp+190h+var_150], 294h
0x18006c6d1  mov     [rsp+190h+var_160], rcx
0x18006c6d6  lea     rdx, [rsp+190h+var_160]
0x18006c6db  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c6e2  mov     [rsp+190h+var_158], rcx
0x18006c6e7  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18006c6ee  mov     [rsp+190h+var_148], rcx
0x18006c6f3  mov     r8d, eax
0x18006c6f6  lea     rcx, [rbp+90h+var_68]
0x18006c6fa  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006c6ff  mov     esi, eax
0x18006c701  mov     rcx, rbx; void *
0x18006c704  test    rdi, rdi
0x18006c707  jz      short loc_18006C710
0x18006c709  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c70e  jmp     short loc_18006C71A
0x18006c710  mov     edx, 10h; struct std::nothrow_t *
0x18006c715  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c71a  mov     ebx, esi
0x18006c71c  jmp     loc_18006C96A
0x18006c721  mov     r14b, r13b
0x18006c724  jmp     short loc_18006C762
0x18006c726  test    r8d, r8d
0x18006c729  jns     short loc_18006C75F
0x18006c72b  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c732  mov     [rsp+190h+var_130], 29Ah
0x18006c73b  mov     [rsp+190h+var_140], rcx
0x18006c740  lea     rax, aStatus; "Status"
0x18006c747  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c74e  mov     [rsp+190h+var_128], rax
0x18006c753  mov     [rsp+190h+var_138], rcx
0x18006c758  lea     rdx, [rsp+190h+var_140]
0x18006c75d  jmp     short loc_18006C6F6
0x18006c75f  mov     r14b, 1
0x18006c762  lea     rax, [rbp+90h+var_50]
0x18006c766  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18006c76e  lea     rcx, [rbp+90h+TokenHandle]
0x18006c772  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x18006c776  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], r13
0x18006c77a  mov     [rbp+90h+var_48], 1
0x18006c781  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x18006c785  mov     [rbp+90h+ObjectAttributes.ObjectName], r13
0x18006c789  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r13
0x18006c78d  mov     [rbp+90h+var_50], 0Ch
0x18006c794  mov     [rbp+90h+var_4C], 2
0x18006c79b  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006c7a0  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x18006c7a4  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18006c7a8  xor     r9d, r9d; EffectiveOnly
0x18006c7ab  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x18006c7b0  mov     [rsp+190h+TokenType], 2; TokenType
0x18006c7b8  lea     edx, [r9+2Ch]; DesiredAccess
0x18006c7bc  call    cs:__imp_NtDuplicateToken
0x18006c7c3  nop     dword ptr [rax+rax+00h]
0x18006c7c8  test    eax, eax
0x18006c7ca  jns     short loc_18006C801
0x18006c7cc  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c7d3  mov     [rbp+90h+var_110], 2AEh
0x18006c7db  mov     [rsp+190h+var_120], rcx
0x18006c7e0  lea     rdx, [rsp+190h+var_120]
0x18006c7e5  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c7ec  mov     [rsp+190h+var_118], rcx
0x18006c7f1  lea     rcx, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x18006c7f8  mov     [rbp+90h+var_108], rcx
0x18006c7fc  jmp     loc_18006C6F3
0x18006c801  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x18006c805  xor     r9d, r9d; BufferLength
0x18006c808  mov     [rsp+190h+NewTokenHandle], r13; ReturnLength
0x18006c80d  mov     r8, rbx; NewState
0x18006c810  xor     edx, edx; DisableAllPrivileges
0x18006c812  mov     qword ptr [rsp+190h+TokenType], r13; PreviousState
0x18006c817  call    cs:__imp_NtAdjustPrivilegesToken
0x18006c81e  nop     dword ptr [rax+rax+00h]
0x18006c823  mov     edx, eax
0x18006c825  test    eax, eax
0x18006c827  jns     short loc_18006C85E
0x18006c829  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c830  mov     [rbp+90h+var_F0], 2B9h
0x18006c838  mov     [rbp+90h+var_100], rcx
0x18006c83c  lea     rax, aStatus; "Status"
0x18006c843  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c84a  mov     [rbp+90h+var_E8], rax
0x18006c84e  mov     r8d, edx
0x18006c851  mov     [rbp+90h+var_F8], rcx
0x18006c855  lea     rdx, [rbp+90h+var_100]
0x18006c859  jmp     loc_18006C6F6
0x18006c85e  cmp     edx, 106h
0x18006c864  jz      short loc_18006C8DD
0x18006c866  mov     rax, [rbp+90h+TokenHandle]
0x18006c86a  lea     r8, [rbp+90h+ThreadInformation]; ThreadInformation
0x18006c86e  mov     r9d, 8; ThreadInformationLength
0x18006c874  mov     [rbp+90h+ThreadInformation], rax
0x18006c878  mov     rcx, r15; ThreadHandle
0x18006c87b  lea     edx, [r9-3]; ThreadInformationClass
0x18006c87f  call    cs:__imp_NtSetInformationThread
0x18006c886  nop     dword ptr [rax+rax+00h]
0x18006c88b  test    eax, eax
0x18006c88d  jns     short loc_18006C8C1
0x18006c88f  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c896  mov     [rbp+90h+var_D0], 2CEh
0x18006c89e  mov     [rbp+90h+var_E0], rcx
0x18006c8a2  lea     rdx, [rbp+90h+var_E0]
0x18006c8a6  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c8ad  mov     [rbp+90h+var_D8], rcx
0x18006c8b1  lea     rcx, aNtsetinformati_0; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x18006c8b8  mov     [rbp+90h+var_C8], rcx
0x18006c8bc  jmp     loc_18006C6F3
0x18006c8c1  mov     byte ptr [rsi+8], 1
0x18006c8c5  mov     byte ptr [r12], 1
0x18006c8ca  test    r14b, r14b
0x18006c8cd  jz      short loc_18006C8DD
0x18006c8cf  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c8d3  mov     rax, [rsi]
0x18006c8d6  mov     [rbp+90h+ExistingTokenHandle], rax
0x18006c8da  mov     [rsi], rcx
0x18006c8dd  mov     rcx, rbx; void *
0x18006c8e0  test    rdi, rdi
0x18006c8e3  jz      short loc_18006C8EC
0x18006c8e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c8ea  jmp     short loc_18006C8F6
0x18006c8ec  mov     edx, 10h; struct std::nothrow_t *
0x18006c8f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006c8f6  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c8fa  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c8ff  lea     rcx, [rbp+90h+TokenHandle]
0x18006c903  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c908  xor     eax, eax
0x18006c90a  mov     rcx, [rbp+90h+var_40]
0x18006c90e  xor     rcx, rsp; StackCookie
0x18006c911  call    __security_check_cookie
0x18006c916  mov     rbx, [rsp+190h+arg_18]
0x18006c91e  add     rsp, 160h
0x18006c925  pop     r15
0x18006c927  pop     r14
0x18006c929  pop     r13
0x18006c92b  pop     r12
0x18006c92d  pop     rdi
0x18006c92e  pop     rsi
0x18006c92f  pop     rbp
0x18006c930  retn
0x18006c932  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006c939  mov     [rbp+90h+var_B0], 278h
0x18006c941  mov     [rbp+90h+var_C0], rcx
0x18006c945  lea     rax, aTokenprivilege; "TokenPrivileges.AllocateWithExtraBytes("...
0x18006c94c  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006c953  mov     [rbp+90h+var_A8], rax
0x18006c957  mov     [rbp+90h+var_B8], rcx
0x18006c95b  lea     rdx, [rbp+90h+var_C0]
0x18006c95f  lea     rcx, [rbp+90h+var_68]
0x18006c963  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006c968  mov     ebx, eax
0x18006c96a  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006c96e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c973  lea     rcx, [rbp+90h+TokenHandle]
0x18006c977  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006c97c  mov     eax, ebx
0x18006c97e  jmp     short loc_18006C90A
0x18006c980  mov     ecx, 0C00000E5h; int
0x18006c985  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
