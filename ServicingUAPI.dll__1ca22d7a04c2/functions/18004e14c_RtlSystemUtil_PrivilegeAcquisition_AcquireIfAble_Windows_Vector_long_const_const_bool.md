# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x18004e14c`
- end: `0x18004e958`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `2060`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e0d4`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x1800062ac`
- `0x1800062b8`
- `0x18000aedc`
- `0x180047e6c`
- `0x1800497c0`
- `0x18004e14c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18004e75e`
- `ntdll!NtSetInformationThread` at `0x18004e75e`
- `ntdll!NtOpenThreadToken` at `0x18004e373`
- `ntdll!NtOpenThreadToken` at `0x18004e373`
- `ntdll!NtClose` at `0x18004e1de`
- `ntdll!NtClose` at `0x18004e204`
- `ntdll!NtClose` at `0x18004e2c8`
- `ntdll!NtClose` at `0x18004e2ee`
- `ntdll!NtClose` at `0x18004e42e`
- `ntdll!NtClose` at `0x18004e454`
- `ntdll!NtClose` at `0x18004e4f0`
- `ntdll!NtClose` at `0x18004e516`
- `ntdll!NtClose` at `0x18004e618`
- `ntdll!NtClose` at `0x18004e63e`
- `ntdll!NtClose` at `0x18004e6f1`
- `ntdll!NtClose` at `0x18004e717`
- `ntdll!NtClose` at `0x18004e7dd`
- `ntdll!NtClose` at `0x18004e803`
- `ntdll!NtClose` at `0x18004e86b`
- `ntdll!NtClose` at `0x18004e891`
- `ntdll!NtClose` at `0x18004e904`
- `ntdll!NtClose` at `0x18004e92a`
- `ntdll!NtClose` at `0x18004e1de`
- `ntdll!NtClose` at `0x18004e204`
- `ntdll!NtClose` at `0x18004e2c8`
- `ntdll!NtClose` at `0x18004e2ee`
- `ntdll!NtClose` at `0x18004e42e`
- `ntdll!NtClose` at `0x18004e454`
- `ntdll!NtClose` at `0x18004e4f0`
- `ntdll!NtClose` at `0x18004e516`
- `ntdll!NtClose` at `0x18004e618`
- `ntdll!NtClose` at `0x18004e63e`
- `ntdll!NtClose` at `0x18004e6f1`
- `ntdll!NtClose` at `0x18004e717`
- `ntdll!NtClose` at `0x18004e7dd`
- `ntdll!NtClose` at `0x18004e803`
- `ntdll!NtClose` at `0x18004e86b`
- `ntdll!NtClose` at `0x18004e891`
- `ntdll!NtClose` at `0x18004e904`
- `ntdll!NtClose` at `0x18004e92a`
- `ntdll!NtDuplicateToken` at `0x18004e599`
- `ntdll!NtDuplicateToken` at `0x18004e599`
- `ntdll!NtOpenProcessToken` at `0x18004e3aa`
- `ntdll!NtOpenProcessToken` at `0x18004e3aa`
- `ntdll!NtAdjustPrivilegesToken` at `0x18004e672`
- `ntdll!NtAdjustPrivilegesToken` at `0x18004e672`

## string_xrefs

- `0x18004e3c0`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e482`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e5af`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e688`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e774`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e8b1`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004e8cf`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x18004e3cc`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e48e`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e5ba`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e693`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e77f`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e8bc`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18004e792`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`
- `0x18004e3e1`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x18004e5cd`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`

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
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
        operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
    JUMPOUT(0x18004E957LL);
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
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
      operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
        operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
    operator delete((void *)0xFFFFFFFFFFFFFFF0LL);
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
0x18004e14c  mov     rax, rsp
0x18004e14f  push    rbp
0x18004e150  push    rsi
0x18004e151  push    rdi
0x18004e152  push    r12
0x18004e154  push    r13
0x18004e156  push    r14
0x18004e158  push    r15
0x18004e15a  lea     rbp, [rsp-70h]
0x18004e15f  sub     rsp, 170h
0x18004e166  mov     [rbp+0A0h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18004e16e  mov     [rax+20h], rbx
0x18004e172  mov     rax, cs:__security_cookie
0x18004e179  xor     rax, rsp
0x18004e17c  mov     [rbp+0A0h+var_40], rax
0x18004e180  mov     r12, r8
0x18004e183  mov     r15, rdx
0x18004e186  mov     r14, rcx
0x18004e189  xor     r13d, r13d
0x18004e18c  mov     [rbp+0A0h+TokenHandle], r13
0x18004e190  mov     [rbp+0A0h+Handle], r13
0x18004e194  mov     [rsp+1A0h+var_170], r13
0x18004e199  mov     [r8], r13b
0x18004e19c  cmp     [rcx+8], r13b
0x18004e1a0  jnz     loc_18004E94D
0x18004e1a6  cmp     [rcx], r13
0x18004e1a9  jnz     loc_18004E94D
0x18004e1af  lea     r9, [rsp+1A0h+var_170]
0x18004e1b4  lea     r8d, [r13+0Ch]
0x18004e1b8  mov     rdx, [rdx+8]
0x18004e1bc  lea     rcx, [rsp+1A0h+var_168]
0x18004e1c1  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x18004e1c6  mov     edi, [rax]
0x18004e1c8  test    edi, edi
0x18004e1ca  jns     short loc_18004E247
0x18004e1cc  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18004e1d0  lea     rax, [rcx-1]
0x18004e1d4  lea     ebx, [r13+7]
0x18004e1d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e1dc  ja      short loc_18004E1F6
0x18004e1de  call    cs:__imp_NtClose
0x18004e1e5  nop     dword ptr [rax+rax+00h]
0x18004e1ea  test    eax, eax
0x18004e1ec  jns     short loc_18004E1F2
0x18004e1ee  mov     ecx, ebx
0x18004e1f0  int     29h; Win8: RtlFailFast(ecx)
0x18004e1f2  mov     [rbp+0A0h+Handle], r13
0x18004e1f6  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x18004e1fa  lea     rax, [rcx-1]
0x18004e1fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e202  ja      short loc_18004E21D
0x18004e204  call    cs:__imp_NtClose
0x18004e20b  nop     dword ptr [rax+rax+00h]
0x18004e210  test    eax, eax
0x18004e212  jns     short loc_18004E219
0x18004e214  mov     rcx, rbx
0x18004e217  int     29h; Win8: RtlFailFast(ecx)
0x18004e219  mov     [rbp+0A0h+TokenHandle], r13
0x18004e21d  mov     eax, edi
0x18004e21f  mov     rcx, [rbp+0A0h+var_40]
0x18004e223  xor     rcx, rsp; StackCookie
0x18004e226  call    __security_check_cookie
0x18004e22b  mov     rbx, [rsp+1A0h+arg_18]
0x18004e233  add     rsp, 170h
0x18004e23a  pop     r15
0x18004e23c  pop     r14
0x18004e23e  pop     r13
0x18004e240  pop     r12
0x18004e242  pop     rdi
0x18004e243  pop     rsi
0x18004e244  pop     rbp
0x18004e245  retn
0x18004e247  mov     rcx, [rsp+1A0h+var_170]
0x18004e24c  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18004e250  jnb     loc_18004E8B1
0x18004e256  add     rcx, 10h; Size
0x18004e25a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e25f  mov     rbx, rax
0x18004e262  lea     rdi, [rax+10h]
0x18004e266  mov     eax, r13d
0x18004e269  xor     ecx, ecx
0x18004e26b  mov     dword ptr [rsp+1A0h+var_170+4], ecx
0x18004e26f  mov     ecx, 0FFFFFFFFh
0x18004e274  cmp     [r15+8], rcx
0x18004e278  ja      short loc_18004E290
0x18004e27a  mov     eax, [r15+8]
0x18004e27e  cmp     [r15+8], rax
0x18004e282  jz      short loc_18004E28B
0x18004e284  mov     esi, 0C00000E5h
0x18004e289  jmp     short loc_18004E295
0x18004e28b  mov     esi, r13d
0x18004e28e  jmp     short loc_18004E295
0x18004e290  mov     esi, 0C0000095h
0x18004e295  mov     [rbx], eax
0x18004e297  test    esi, esi
0x18004e299  jns     short loc_18004E30E
0x18004e29b  mov     rcx, rbx; Block
0x18004e29e  test    rdi, rdi
0x18004e2a1  jz      short loc_18004E2AA
0x18004e2a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e2a8  jmp     short loc_18004E2B5
0x18004e2aa  mov     edx, 10h
0x18004e2af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e2b4  nop
0x18004e2b5  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18004e2b9  lea     rax, [rcx-1]
0x18004e2bd  mov     ebx, 7
0x18004e2c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e2c6  ja      short loc_18004E2E0
0x18004e2c8  call    cs:__imp_NtClose
0x18004e2cf  nop     dword ptr [rax+rax+00h]
0x18004e2d4  test    eax, eax
0x18004e2d6  jns     short loc_18004E2DC
0x18004e2d8  mov     ecx, ebx
0x18004e2da  int     29h; Win8: RtlFailFast(ecx)
0x18004e2dc  mov     [rbp+0A0h+Handle], r13
0x18004e2e0  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x18004e2e4  lea     rax, [rcx-1]
0x18004e2e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e2ec  ja      short loc_18004E307
0x18004e2ee  call    cs:__imp_NtClose
0x18004e2f5  nop     dword ptr [rax+rax+00h]
0x18004e2fa  test    eax, eax
0x18004e2fc  jns     short loc_18004E303
0x18004e2fe  mov     rcx, rbx
0x18004e301  int     29h; Win8: RtlFailFast(ecx)
0x18004e303  mov     [rbp+0A0h+TokenHandle], r13
0x18004e307  mov     eax, esi
0x18004e309  jmp     loc_18004E21F
0x18004e30e  mov     rdx, r13
0x18004e311  cmp     [r15+8], r13
0x18004e315  jbe     short loc_18004E349
0x18004e317  mov     rax, [r15]
0x18004e31a  movsxd  rax, dword ptr [rax+rdx*4]
0x18004e31e  mov     dword ptr [rsp+1A0h+var_170], eax
0x18004e322  shr     rax, 20h
0x18004e326  mov     dword ptr [rsp+1A0h+var_170+4], eax
0x18004e32a  lea     rcx, [rdx+rdx*2]
0x18004e32e  mov     rax, [rsp+1A0h+var_170]
0x18004e333  mov     [rbx+rcx*4+4], rax
0x18004e338  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x18004e340  inc     rdx
0x18004e343  cmp     rdx, [r15+8]
0x18004e347  jb      short loc_18004E317
0x18004e349  mov     rax, [rbp+0A0h+Handle]
0x18004e34d  inc     rax
0x18004e350  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004e356  jnz     loc_18004E94D
0x18004e35c  lea     r9, [rbp+0A0h+Handle]; TokenHandle
0x18004e360  mov     r8b, 1; OpenAsSelf
0x18004e363  mov     r15d, 2Eh ; '.'
0x18004e369  mov     edx, r15d; DesiredAccess
0x18004e36c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004e373  call    cs:__imp_NtOpenThreadToken
0x18004e37a  nop     dword ptr [rax+rax+00h]
0x18004e37f  mov     esi, eax
0x18004e381  cmp     eax, 0C000007Ch
0x18004e386  jnz     loc_18004E47A
0x18004e38c  mov     rax, [rbp+0A0h+Handle]
0x18004e390  inc     rax
0x18004e393  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004e399  jnz     loc_18004E94D
0x18004e39f  lea     r8, [rbp+0A0h+Handle]; TokenHandle
0x18004e3a3  mov     edx, r15d; DesiredAccess
0x18004e3a6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004e3aa  call    cs:__imp_NtOpenProcessToken
0x18004e3b1  nop     dword ptr [rax+rax+00h]
0x18004e3b6  mov     esi, eax
0x18004e3b8  test    eax, eax
0x18004e3ba  jns     loc_18004E472
0x18004e3c0  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004e3c7  mov     [rsp+1A0h+var_160], rcx
0x18004e3cc  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18004e3d3  mov     [rsp+1A0h+var_158], rcx
0x18004e3d8  mov     [rsp+1A0h+var_150], 294h
0x18004e3e1  lea     rax, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18004e3e8  mov     [rsp+1A0h+var_148], rax
0x18004e3ed  mov     r8d, esi
0x18004e3f0  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004e3f7  lea     rcx, [rsp+1A0h+var_160]
0x18004e3fc  call    RtlReportErrorOrigination
0x18004e401  mov     rcx, rbx; Block
0x18004e404  test    rdi, rdi
0x18004e407  jz      short loc_18004E410
0x18004e409  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e40e  jmp     short loc_18004E41B
0x18004e410  mov     edx, 10h
0x18004e415  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e41a  nop
0x18004e41b  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18004e41f  lea     rax, [rcx-1]
0x18004e423  mov     ebx, 7
0x18004e428  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e42c  ja      short loc_18004E446
0x18004e42e  call    cs:__imp_NtClose
0x18004e435  nop     dword ptr [rax+rax+00h]
0x18004e43a  test    eax, eax
0x18004e43c  jns     short loc_18004E442
0x18004e43e  mov     ecx, ebx
0x18004e440  int     29h; Win8: RtlFailFast(ecx)
0x18004e442  mov     [rbp+0A0h+Handle], r13
0x18004e446  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x18004e44a  lea     rax, [rcx-1]
0x18004e44e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e452  ja      short loc_18004E46D
0x18004e454  call    cs:__imp_NtClose
0x18004e45b  nop     dword ptr [rax+rax+00h]
0x18004e460  test    eax, eax
0x18004e462  jns     short loc_18004E469
0x18004e464  mov     rcx, rbx
0x18004e467  int     29h; Win8: RtlFailFast(ecx)
0x18004e469  mov     [rbp+0A0h+TokenHandle], r13
0x18004e46d  jmp     loc_18004E307
0x18004e472  mov     r15b, r13b
0x18004e475  jmp     loc_18004E537
0x18004e47a  test    esi, esi
0x18004e47c  jns     loc_18004E534
0x18004e482  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004e489  mov     [rsp+1A0h+var_140], rcx
0x18004e48e  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18004e495  mov     [rsp+1A0h+var_138], rcx
0x18004e49a  mov     [rsp+1A0h+var_130], 29Ah
0x18004e4a3  lea     rax, aStatus; "Status"
0x18004e4aa  mov     [rsp+1A0h+var_128], rax
0x18004e4af  mov     r8d, esi
0x18004e4b2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004e4b9  lea     rcx, [rsp+1A0h+var_140]
0x18004e4be  call    RtlReportErrorOrigination
0x18004e4c3  mov     rcx, rbx; Block
0x18004e4c6  test    rdi, rdi
0x18004e4c9  jz      short loc_18004E4D2
0x18004e4cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e4d0  jmp     short loc_18004E4DD
0x18004e4d2  mov     edx, 10h
0x18004e4d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e4dc  nop
0x18004e4dd  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18004e4e1  lea     rax, [rcx-1]
0x18004e4e5  mov     ebx, 7
0x18004e4ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e4ee  ja      short loc_18004E508
0x18004e4f0  call    cs:__imp_NtClose
0x18004e4f7  nop     dword ptr [rax+rax+00h]
0x18004e4fc  test    eax, eax
0x18004e4fe  jns     short loc_18004E504
0x18004e500  mov     ecx, ebx
0x18004e502  int     29h; Win8: RtlFailFast(ecx)
0x18004e504  mov     [rbp+0A0h+Handle], r13
0x18004e508  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x18004e50c  lea     rax, [rcx-1]
0x18004e510  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e514  ja      short loc_18004E52F
0x18004e516  call    cs:__imp_NtClose
0x18004e51d  nop     dword ptr [rax+rax+00h]
0x18004e522  test    eax, eax
0x18004e524  jns     short loc_18004E52B
0x18004e526  mov     rcx, rbx
0x18004e529  int     29h; Win8: RtlFailFast(ecx)
0x18004e52b  mov     [rbp+0A0h+TokenHandle], r13
0x18004e52f  jmp     loc_18004E307
0x18004e534  mov     r15b, 1
0x18004e537  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18004e53f  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], r13
0x18004e543  mov     [rbp+0A0h+var_48], 1
0x18004e54a  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r13
0x18004e54e  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x18004e552  mov     [rbp+0A0h+ObjectAttributes.SecurityDescriptor], r13
0x18004e556  mov     [rbp+0A0h+var_50], 0Ch
0x18004e55d  mov     ecx, 2
0x18004e562  mov     [rbp+0A0h+var_4C], ecx
0x18004e565  lea     rax, [rbp+0A0h+var_50]
0x18004e569  mov     [rbp+0A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18004e56d  mov     rax, [rbp+0A0h+TokenHandle]
0x18004e571  dec     rax
0x18004e574  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004e578  jbe     loc_18004E94D
0x18004e57e  lea     rax, [rbp+0A0h+TokenHandle]
0x18004e582  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x18004e587  mov     [rsp+1A0h+TokenType], ecx; TokenType
0x18004e58b  xor     r9d, r9d; EffectiveOnly
0x18004e58e  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x18004e592  lea     edx, [rcx+2Ah]; DesiredAccess
0x18004e595  mov     rcx, [rbp+0A0h+Handle]; ExistingTokenHandle
0x18004e599  call    cs:__imp_NtDuplicateToken
0x18004e5a0  nop     dword ptr [rax+rax+00h]
0x18004e5a5  mov     esi, eax
0x18004e5a7  test    eax, eax
0x18004e5a9  jns     loc_18004E65C
0x18004e5af  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004e5b6  mov     [rbp+0A0h+var_120], rcx
0x18004e5ba  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18004e5c1  mov     [rbp+0A0h+var_118], rcx
0x18004e5c5  mov     [rbp+0A0h+var_110], 2AEh
0x18004e5cd  lea     rax, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x18004e5d4  mov     [rbp+0A0h+var_108], rax
0x18004e5d8  mov     r8d, esi
0x18004e5db  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004e5e2  lea     rcx, [rbp+0A0h+var_120]
0x18004e5e6  call    RtlReportErrorOrigination
0x18004e5eb  mov     rcx, rbx; Block
  ... truncated ...
```
