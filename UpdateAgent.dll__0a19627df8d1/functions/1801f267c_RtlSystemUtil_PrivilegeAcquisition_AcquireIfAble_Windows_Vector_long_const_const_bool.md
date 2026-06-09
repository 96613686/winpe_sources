# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x1801f267c`
- end: `0x1801f2e88`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `2060`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801f2604`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x1800061d4`
- `0x1800692fc`
- `0x1800addf4`
- `0x1801efdc0`
- `0x1801f267c`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x1801f2ba2`
- `ntdll!NtAdjustPrivilegesToken` at `0x1801f2ba2`
- `ntdll!NtOpenProcessToken` at `0x1801f28da`
- `ntdll!NtOpenProcessToken` at `0x1801f28da`
- `ntdll!NtDuplicateToken` at `0x1801f2ac9`
- `ntdll!NtDuplicateToken` at `0x1801f2ac9`
- `ntdll!NtOpenThreadToken` at `0x1801f28a3`
- `ntdll!NtOpenThreadToken` at `0x1801f28a3`
- `ntdll!NtClose` at `0x1801f270e`
- `ntdll!NtClose` at `0x1801f2734`
- `ntdll!NtClose` at `0x1801f27f8`
- `ntdll!NtClose` at `0x1801f281e`
- `ntdll!NtClose` at `0x1801f295e`
- `ntdll!NtClose` at `0x1801f2984`
- `ntdll!NtClose` at `0x1801f2a20`
- `ntdll!NtClose` at `0x1801f2a46`
- `ntdll!NtClose` at `0x1801f2b48`
- `ntdll!NtClose` at `0x1801f2b6e`
- `ntdll!NtClose` at `0x1801f2c21`
- `ntdll!NtClose` at `0x1801f2c47`
- `ntdll!NtClose` at `0x1801f2d0d`
- `ntdll!NtClose` at `0x1801f2d33`
- `ntdll!NtClose` at `0x1801f2d9b`
- `ntdll!NtClose` at `0x1801f2dc1`
- `ntdll!NtClose` at `0x1801f2e34`
- `ntdll!NtClose` at `0x1801f2e5a`
- `ntdll!NtClose` at `0x1801f270e`
- `ntdll!NtClose` at `0x1801f2734`
- `ntdll!NtClose` at `0x1801f27f8`
- `ntdll!NtClose` at `0x1801f281e`
- `ntdll!NtClose` at `0x1801f295e`
- `ntdll!NtClose` at `0x1801f2984`
- `ntdll!NtClose` at `0x1801f2a20`
- `ntdll!NtClose` at `0x1801f2a46`
- `ntdll!NtClose` at `0x1801f2b48`
- `ntdll!NtClose` at `0x1801f2b6e`
- `ntdll!NtClose` at `0x1801f2c21`
- `ntdll!NtClose` at `0x1801f2c47`
- `ntdll!NtClose` at `0x1801f2d0d`
- `ntdll!NtClose` at `0x1801f2d33`
- `ntdll!NtClose` at `0x1801f2d9b`
- `ntdll!NtClose` at `0x1801f2dc1`
- `ntdll!NtClose` at `0x1801f2e34`
- `ntdll!NtClose` at `0x1801f2e5a`
- `ntdll!NtSetInformationThread` at `0x1801f2c8e`
- `ntdll!NtSetInformationThread` at `0x1801f2c8e`

## string_xrefs

- `0x1801f28f0`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f29b2`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f2adf`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f2bb8`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f2ca4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f2de1`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f28fc`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f29be`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f2aea`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f2bc3`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f2caf`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f2dec`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1801f2afd`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`
- `0x1801f2911`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x1801f2dff`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x1801f2cc2`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  int v6; // edi
  struct _TOKEN_PRIVILEGES *v8; // rbx
  __int64 v9; // rax
  NTSTATUS v10; // esi
  unsigned __int64 i; // rdx
  __int64 v12; // rcx
  char v13; // r15
  HANDLE v14; // rcx
  unsigned __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v20[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v21[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v22[5]; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE ThreadInformation; // [rsp+108h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+140h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+148h] [rbp+48h] BYREF
  _DWORD v27[4]; // [rsp+150h] [rbp+50h] BYREF

  v22[4] = -2;
  TokenHandle = 0;
  Handle = 0;
  v15 = 0;
  *a3 = 0;
  if ( *(_BYTE *)(a1 + 8) || *(_QWORD *)a1 )
    goto LABEL_129;
  v6 = *(_DWORD *)BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(v16, a2[1], 12, &v15);
  if ( v6 < 0 )
  {
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return (unsigned int)v6;
  }
  if ( v15 >= 0xFFFFFFFFFFFFFFEFuLL )
  {
    v22[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v22[2] = 632;
    v22[3] = "TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)";
    RtlReportErrorOrigination(v22, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return 3221225495LL;
  }
  v8 = (struct _TOKEN_PRIVILEGES *)operator new(v15 + 16);
  LODWORD(v9) = 0;
  HIDWORD(v15) = 0;
  if ( a2[1] > 0xFFFFFFFF )
  {
    v10 = -1073741675;
  }
  else
  {
    v9 = *((unsigned int *)a2 + 2);
    if ( a2[1] == v9 )
      v10 = 0;
    else
      v10 = -1073741595;
  }
  v8->PrivilegeCount = v9;
  if ( v10 < 0 )
  {
    if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
    else
      operator delete(v8);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return (unsigned int)v10;
  }
  for ( i = 0; i < a2[1]; ++i )
  {
    LODWORD(v15) = *(_DWORD *)(*a2 + 4 * i);
    v15 = (int)v15;
    v12 = i;
    v8->Privileges[v12].Luid = (LUID)(int)v15;
    v8->Privileges[v12].Attributes = 2;
  }
  if ( (((unsigned __int64)Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_129;
  v10 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2Eu, 1u, &Handle);
  if ( v10 != -1073741700 )
  {
    if ( v10 < 0 )
    {
      v18[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v18[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v18[2] = 666;
      v18[3] = "Status";
      RtlReportErrorOrigination(v18, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
      if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
        operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
      else
        operator delete(v8);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(TokenHandle) < 0 )
          __fastfail(7u);
        TokenHandle = 0;
      }
      return (unsigned int)v10;
    }
    v13 = 1;
    goto LABEL_65;
  }
  if ( (((unsigned __int64)Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_129:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801F2E87LL);
  }
  v10 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2Eu, &Handle);
  if ( v10 < 0 )
  {
    v17[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v17[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v17[2] = 660;
    v17[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())";
    RtlReportErrorOrigination(v17, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
    if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
    else
      operator delete(v8);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return (unsigned int)v10;
  }
  v13 = 0;
LABEL_65:
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v27[2] = 1;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v27[0] = 12;
  v27[1] = 2;
  ObjectAttributes.SecurityQualityOfService = v27;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    goto LABEL_129;
  v10 = NtDuplicateToken(Handle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &TokenHandle);
  if ( v10 < 0 )
  {
    v19[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v19[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v19[2] = 686;
    v19[3] = "NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())";
    RtlReportErrorOrigination(v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
    if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
    else
      operator delete(v8);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return (unsigned int)v10;
  }
  v10 = NtAdjustPrivilegesToken(TokenHandle, 0, v8, 0, 0, 0);
  if ( v10 < 0 )
  {
    v20[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v20[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v20[2] = 697;
    v20[3] = "Status";
    RtlReportErrorOrigination(v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
    if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
    else
      operator delete(v8);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(Handle) < 0 )
        __fastfail(7u);
      Handle = 0;
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return (unsigned int)v10;
  }
  if ( v10 != 262 )
  {
    ThreadInformation = TokenHandle;
    v10 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v10 < 0 )
    {
      v21[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v21[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v21[2] = 718;
      v21[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))";
      RtlReportErrorOrigination(v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
      if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
        operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
      else
        operator delete(v8);
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(Handle) < 0 )
          __fastfail(7u);
        Handle = 0;
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(TokenHandle) < 0 )
          __fastfail(7u);
        TokenHandle = 0;
      }
      return (unsigned int)v10;
    }
    *(_BYTE *)(a1 + 8) = 1;
    *a3 = 1;
    if ( v13 )
    {
      v14 = Handle;
      Handle = *(HANDLE *)a1;
      *(_QWORD *)a1 = v14;
    }
  }
  if ( v8 == (struct _TOKEN_PRIVILEGES *)-16LL )
    operator delete((void *)0xFFFFFFFFFFFFFFF0LL, (const struct std::nothrow_t *)0x10);
  else
    operator delete(v8);
  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(Handle) < 0 )
      __fastfail(7u);
    Handle = 0;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(TokenHandle) < 0 )
      __fastfail(7u);
    TokenHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801f267c  mov     rax, rsp
0x1801f267f  push    rbp
0x1801f2680  push    rsi
0x1801f2681  push    rdi
0x1801f2682  push    r12
0x1801f2684  push    r13
0x1801f2686  push    r14
0x1801f2688  push    r15
0x1801f268a  lea     rbp, [rsp-70h]
0x1801f268f  sub     rsp, 170h
0x1801f2696  mov     [rbp+0A0h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1801f269e  mov     [rax+20h], rbx
0x1801f26a2  mov     rax, cs:__security_cookie
0x1801f26a9  xor     rax, rsp
0x1801f26ac  mov     [rbp+0A0h+var_40], rax
0x1801f26b0  mov     r12, r8
0x1801f26b3  mov     r15, rdx
0x1801f26b6  mov     r14, rcx
0x1801f26b9  xor     r13d, r13d
0x1801f26bc  mov     [rbp+0A0h+TokenHandle], r13
0x1801f26c0  mov     [rbp+0A0h+Handle], r13
0x1801f26c4  mov     [rsp+1A0h+var_170], r13
0x1801f26c9  mov     [r8], r13b
0x1801f26cc  cmp     [rcx+8], r13b
0x1801f26d0  jnz     loc_1801F2E7D
0x1801f26d6  cmp     [rcx], r13
0x1801f26d9  jnz     loc_1801F2E7D
0x1801f26df  lea     r9, [rsp+1A0h+var_170]
0x1801f26e4  lea     r8d, [r13+0Ch]
0x1801f26e8  mov     rdx, [rdx+8]
0x1801f26ec  lea     rcx, [rsp+1A0h+var_168]
0x1801f26f1  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x1801f26f6  mov     edi, [rax]
0x1801f26f8  test    edi, edi
0x1801f26fa  jns     short loc_1801F2777
0x1801f26fc  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1801f2700  lea     rax, [rcx-1]
0x1801f2704  lea     ebx, [r13+7]
0x1801f2708  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f270c  ja      short loc_1801F2726
0x1801f270e  call    cs:__imp_NtClose
0x1801f2715  nop     dword ptr [rax+rax+00h]
0x1801f271a  test    eax, eax
0x1801f271c  jns     short loc_1801F2722
0x1801f271e  mov     ecx, ebx
0x1801f2720  int     29h; Win8: RtlFailFast(ecx)
0x1801f2722  mov     [rbp+0A0h+Handle], r13
0x1801f2726  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1801f272a  lea     rax, [rcx-1]
0x1801f272e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f2732  ja      short loc_1801F274D
0x1801f2734  call    cs:__imp_NtClose
0x1801f273b  nop     dword ptr [rax+rax+00h]
0x1801f2740  test    eax, eax
0x1801f2742  jns     short loc_1801F2749
0x1801f2744  mov     rcx, rbx
0x1801f2747  int     29h; Win8: RtlFailFast(ecx)
0x1801f2749  mov     [rbp+0A0h+TokenHandle], r13
0x1801f274d  mov     eax, edi
0x1801f274f  mov     rcx, [rbp+0A0h+var_40]
0x1801f2753  xor     rcx, rsp; StackCookie
0x1801f2756  call    __security_check_cookie
0x1801f275b  mov     rbx, [rsp+1A0h+arg_18]
0x1801f2763  add     rsp, 170h
0x1801f276a  pop     r15
0x1801f276c  pop     r14
0x1801f276e  pop     r13
0x1801f2770  pop     r12
0x1801f2772  pop     rdi
0x1801f2773  pop     rsi
0x1801f2774  pop     rbp
0x1801f2775  retn
0x1801f2777  mov     rcx, [rsp+1A0h+var_170]
0x1801f277c  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x1801f2780  jnb     loc_1801F2DE1
0x1801f2786  add     rcx, 10h; Size
0x1801f278a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801f278f  mov     rbx, rax
0x1801f2792  lea     rdi, [rax+10h]
0x1801f2796  mov     eax, r13d
0x1801f2799  xor     ecx, ecx
0x1801f279b  mov     dword ptr [rsp+1A0h+var_170+4], ecx
0x1801f279f  mov     ecx, 0FFFFFFFFh
0x1801f27a4  cmp     [r15+8], rcx
0x1801f27a8  ja      short loc_1801F27C0
0x1801f27aa  mov     eax, [r15+8]
0x1801f27ae  cmp     [r15+8], rax
0x1801f27b2  jz      short loc_1801F27BB
0x1801f27b4  mov     esi, 0C00000E5h
0x1801f27b9  jmp     short loc_1801F27C5
0x1801f27bb  mov     esi, r13d
0x1801f27be  jmp     short loc_1801F27C5
0x1801f27c0  mov     esi, 0C0000095h
0x1801f27c5  mov     [rbx], eax
0x1801f27c7  test    esi, esi
0x1801f27c9  jns     short loc_1801F283E
0x1801f27cb  mov     rcx, rbx; void *
0x1801f27ce  test    rdi, rdi
0x1801f27d1  jz      short loc_1801F27DA
0x1801f27d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f27d8  jmp     short loc_1801F27E5
0x1801f27da  mov     edx, 10h; struct std::nothrow_t *
0x1801f27df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801f27e4  nop
0x1801f27e5  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1801f27e9  lea     rax, [rcx-1]
0x1801f27ed  mov     ebx, 7
0x1801f27f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f27f6  ja      short loc_1801F2810
0x1801f27f8  call    cs:__imp_NtClose
0x1801f27ff  nop     dword ptr [rax+rax+00h]
0x1801f2804  test    eax, eax
0x1801f2806  jns     short loc_1801F280C
0x1801f2808  mov     ecx, ebx
0x1801f280a  int     29h; Win8: RtlFailFast(ecx)
0x1801f280c  mov     [rbp+0A0h+Handle], r13
0x1801f2810  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1801f2814  lea     rax, [rcx-1]
0x1801f2818  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f281c  ja      short loc_1801F2837
0x1801f281e  call    cs:__imp_NtClose
0x1801f2825  nop     dword ptr [rax+rax+00h]
0x1801f282a  test    eax, eax
0x1801f282c  jns     short loc_1801F2833
0x1801f282e  mov     rcx, rbx
0x1801f2831  int     29h; Win8: RtlFailFast(ecx)
0x1801f2833  mov     [rbp+0A0h+TokenHandle], r13
0x1801f2837  mov     eax, esi
0x1801f2839  jmp     loc_1801F274F
0x1801f283e  mov     rdx, r13
0x1801f2841  cmp     [r15+8], r13
0x1801f2845  jbe     short loc_1801F2879
0x1801f2847  mov     rax, [r15]
0x1801f284a  movsxd  rax, dword ptr [rax+rdx*4]
0x1801f284e  mov     dword ptr [rsp+1A0h+var_170], eax
0x1801f2852  shr     rax, 20h
0x1801f2856  mov     dword ptr [rsp+1A0h+var_170+4], eax
0x1801f285a  lea     rcx, [rdx+rdx*2]
0x1801f285e  mov     rax, [rsp+1A0h+var_170]
0x1801f2863  mov     [rbx+rcx*4+4], rax
0x1801f2868  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x1801f2870  inc     rdx
0x1801f2873  cmp     rdx, [r15+8]
0x1801f2877  jb      short loc_1801F2847
0x1801f2879  mov     rax, [rbp+0A0h+Handle]
0x1801f287d  inc     rax
0x1801f2880  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801f2886  jnz     loc_1801F2E7D
0x1801f288c  lea     r9, [rbp+0A0h+Handle]; TokenHandle
0x1801f2890  mov     r8b, 1; OpenAsSelf
0x1801f2893  mov     r15d, 2Eh ; '.'
0x1801f2899  mov     edx, r15d; DesiredAccess
0x1801f289c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1801f28a3  call    cs:__imp_NtOpenThreadToken
0x1801f28aa  nop     dword ptr [rax+rax+00h]
0x1801f28af  mov     esi, eax
0x1801f28b1  cmp     eax, 0C000007Ch
0x1801f28b6  jnz     loc_1801F29AA
0x1801f28bc  mov     rax, [rbp+0A0h+Handle]
0x1801f28c0  inc     rax
0x1801f28c3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801f28c9  jnz     loc_1801F2E7D
0x1801f28cf  lea     r8, [rbp+0A0h+Handle]; TokenHandle
0x1801f28d3  mov     edx, r15d; DesiredAccess
0x1801f28d6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1801f28da  call    cs:__imp_NtOpenProcessToken
0x1801f28e1  nop     dword ptr [rax+rax+00h]
0x1801f28e6  mov     esi, eax
0x1801f28e8  test    eax, eax
0x1801f28ea  jns     loc_1801F29A2
0x1801f28f0  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f28f7  mov     [rsp+1A0h+var_160], rcx
0x1801f28fc  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1801f2903  mov     [rsp+1A0h+var_158], rcx
0x1801f2908  mov     [rsp+1A0h+var_150], 294h
0x1801f2911  lea     rax, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1801f2918  mov     [rsp+1A0h+var_148], rax
0x1801f291d  mov     r8d, esi
0x1801f2920  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f2927  lea     rcx, [rsp+1A0h+var_160]
0x1801f292c  call    RtlReportErrorOrigination
0x1801f2931  mov     rcx, rbx; void *
0x1801f2934  test    rdi, rdi
0x1801f2937  jz      short loc_1801F2940
0x1801f2939  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f293e  jmp     short loc_1801F294B
0x1801f2940  mov     edx, 10h; struct std::nothrow_t *
0x1801f2945  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801f294a  nop
0x1801f294b  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1801f294f  lea     rax, [rcx-1]
0x1801f2953  mov     ebx, 7
0x1801f2958  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f295c  ja      short loc_1801F2976
0x1801f295e  call    cs:__imp_NtClose
0x1801f2965  nop     dword ptr [rax+rax+00h]
0x1801f296a  test    eax, eax
0x1801f296c  jns     short loc_1801F2972
0x1801f296e  mov     ecx, ebx
0x1801f2970  int     29h; Win8: RtlFailFast(ecx)
0x1801f2972  mov     [rbp+0A0h+Handle], r13
0x1801f2976  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1801f297a  lea     rax, [rcx-1]
0x1801f297e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f2982  ja      short loc_1801F299D
0x1801f2984  call    cs:__imp_NtClose
0x1801f298b  nop     dword ptr [rax+rax+00h]
0x1801f2990  test    eax, eax
0x1801f2992  jns     short loc_1801F2999
0x1801f2994  mov     rcx, rbx
0x1801f2997  int     29h; Win8: RtlFailFast(ecx)
0x1801f2999  mov     [rbp+0A0h+TokenHandle], r13
0x1801f299d  jmp     loc_1801F2837
0x1801f29a2  mov     r15b, r13b
0x1801f29a5  jmp     loc_1801F2A67
0x1801f29aa  test    esi, esi
0x1801f29ac  jns     loc_1801F2A64
0x1801f29b2  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f29b9  mov     [rsp+1A0h+var_140], rcx
0x1801f29be  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1801f29c5  mov     [rsp+1A0h+var_138], rcx
0x1801f29ca  mov     [rsp+1A0h+var_130], 29Ah
0x1801f29d3  lea     rax, aStatus; "Status"
0x1801f29da  mov     [rsp+1A0h+var_128], rax
0x1801f29df  mov     r8d, esi
0x1801f29e2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f29e9  lea     rcx, [rsp+1A0h+var_140]
0x1801f29ee  call    RtlReportErrorOrigination
0x1801f29f3  mov     rcx, rbx; void *
0x1801f29f6  test    rdi, rdi
0x1801f29f9  jz      short loc_1801F2A02
0x1801f29fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f2a00  jmp     short loc_1801F2A0D
0x1801f2a02  mov     edx, 10h; struct std::nothrow_t *
0x1801f2a07  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801f2a0c  nop
0x1801f2a0d  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1801f2a11  lea     rax, [rcx-1]
0x1801f2a15  mov     ebx, 7
0x1801f2a1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f2a1e  ja      short loc_1801F2A38
0x1801f2a20  call    cs:__imp_NtClose
0x1801f2a27  nop     dword ptr [rax+rax+00h]
0x1801f2a2c  test    eax, eax
0x1801f2a2e  jns     short loc_1801F2A34
0x1801f2a30  mov     ecx, ebx
0x1801f2a32  int     29h; Win8: RtlFailFast(ecx)
0x1801f2a34  mov     [rbp+0A0h+Handle], r13
0x1801f2a38  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1801f2a3c  lea     rax, [rcx-1]
0x1801f2a40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f2a44  ja      short loc_1801F2A5F
0x1801f2a46  call    cs:__imp_NtClose
0x1801f2a4d  nop     dword ptr [rax+rax+00h]
0x1801f2a52  test    eax, eax
0x1801f2a54  jns     short loc_1801F2A5B
0x1801f2a56  mov     rcx, rbx
0x1801f2a59  int     29h; Win8: RtlFailFast(ecx)
0x1801f2a5b  mov     [rbp+0A0h+TokenHandle], r13
0x1801f2a5f  jmp     loc_1801F2837
0x1801f2a64  mov     r15b, 1
0x1801f2a67  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1801f2a6f  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], r13
0x1801f2a73  mov     [rbp+0A0h+var_48], 1
0x1801f2a7a  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r13
0x1801f2a7e  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x1801f2a82  mov     [rbp+0A0h+ObjectAttributes.SecurityDescriptor], r13
0x1801f2a86  mov     [rbp+0A0h+var_50], 0Ch
0x1801f2a8d  mov     ecx, 2
0x1801f2a92  mov     [rbp+0A0h+var_4C], ecx
0x1801f2a95  lea     rax, [rbp+0A0h+var_50]
0x1801f2a99  mov     [rbp+0A0h+ObjectAttributes.SecurityQualityOfService], rax
0x1801f2a9d  mov     rax, [rbp+0A0h+TokenHandle]
0x1801f2aa1  dec     rax
0x1801f2aa4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f2aa8  jbe     loc_1801F2E7D
0x1801f2aae  lea     rax, [rbp+0A0h+TokenHandle]
0x1801f2ab2  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x1801f2ab7  mov     [rsp+1A0h+TokenType], ecx; TokenType
0x1801f2abb  xor     r9d, r9d; EffectiveOnly
0x1801f2abe  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1801f2ac2  lea     edx, [rcx+2Ah]; DesiredAccess
0x1801f2ac5  mov     rcx, [rbp+0A0h+Handle]; ExistingTokenHandle
0x1801f2ac9  call    cs:__imp_NtDuplicateToken
0x1801f2ad0  nop     dword ptr [rax+rax+00h]
0x1801f2ad5  mov     esi, eax
0x1801f2ad7  test    eax, eax
0x1801f2ad9  jns     loc_1801F2B8C
0x1801f2adf  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f2ae6  mov     [rbp+0A0h+var_120], rcx
0x1801f2aea  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1801f2af1  mov     [rbp+0A0h+var_118], rcx
0x1801f2af5  mov     [rbp+0A0h+var_110], 2AEh
0x1801f2afd  lea     rax, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x1801f2b04  mov     [rbp+0A0h+var_108], rax
0x1801f2b08  mov     r8d, esi
0x1801f2b0b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f2b12  lea     rcx, [rbp+0A0h+var_120]
0x1801f2b16  call    RtlReportErrorOrigination
0x1801f2b1b  mov     rcx, rbx; void *
  ... truncated ...
```
