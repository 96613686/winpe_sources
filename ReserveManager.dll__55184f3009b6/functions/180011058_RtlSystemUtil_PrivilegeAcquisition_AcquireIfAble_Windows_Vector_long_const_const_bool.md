# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x180011058`
- end: `0x1800117d9`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `1921`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010fe0`

## callees

- `0x180003870`
- `0x180003894`
- `0x180003c84`
- `0x180004164`
- `0x180008140`
- `0x18000f078`
- `0x18000fafc`
- `0x180011058`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x18001152f`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001152f`
- `ntdll!NtSetInformationThread` at `0x180011609`
- `ntdll!NtSetInformationThread` at `0x180011609`
- `ntdll!NtOpenThreadToken` at `0x180011266`
- `ntdll!NtOpenThreadToken` at `0x180011266`
- `ntdll!NtOpenProcessToken` at `0x180011297`
- `ntdll!NtOpenProcessToken` at `0x180011297`
- `ntdll!NtDuplicateToken` at `0x180011468`
- `ntdll!NtDuplicateToken` at `0x180011468`
- `ntdll!NtClose` at `0x1800110ea`
- `ntdll!NtClose` at `0x18001110a`
- `ntdll!NtClose` at `0x1800111c7`
- `ntdll!NtClose` at `0x1800111e7`
- `ntdll!NtClose` at `0x180011315`
- `ntdll!NtClose` at `0x180011335`
- `ntdll!NtClose` at `0x1800113cb`
- `ntdll!NtClose` at `0x1800113eb`
- `ntdll!NtClose` at `0x1800114e1`
- `ntdll!NtClose` at `0x180011501`
- `ntdll!NtClose` at `0x1800115a8`
- `ntdll!NtClose` at `0x1800115c8`
- `ntdll!NtClose` at `0x180011682`
- `ntdll!NtClose` at `0x1800116a2`
- `ntdll!NtClose` at `0x180011704`
- `ntdll!NtClose` at `0x180011724`
- `ntdll!NtClose` at `0x180011791`
- `ntdll!NtClose` at `0x1800117b1`
- `ntdll!NtClose` at `0x1800110ea`
- `ntdll!NtClose` at `0x18001110a`
- `ntdll!NtClose` at `0x1800111c7`
- `ntdll!NtClose` at `0x1800111e7`
- `ntdll!NtClose` at `0x180011315`
- `ntdll!NtClose` at `0x180011335`
- `ntdll!NtClose` at `0x1800113cb`
- `ntdll!NtClose` at `0x1800113eb`
- `ntdll!NtClose` at `0x1800114e1`
- `ntdll!NtClose` at `0x180011501`
- `ntdll!NtClose` at `0x1800115a8`
- `ntdll!NtClose` at `0x1800115c8`
- `ntdll!NtClose` at `0x180011682`
- `ntdll!NtClose` at `0x1800116a2`
- `ntdll!NtClose` at `0x180011704`
- `ntdll!NtClose` at `0x180011724`
- `ntdll!NtClose` at `0x180011791`
- `ntdll!NtClose` at `0x1800117b1`

## string_xrefs

- `0x1800112a7`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001135d`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180011478`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001153f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180011619`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001173e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800112b3`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180011369`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180011483`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18001154a`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180011624`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180011749`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18001175c`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x1800112c8`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`
- `0x180011496`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`
- `0x180011637`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`

## pseudocode

```c
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
  if ( v10 == -1073741700 )
  {
    if ( (((unsigned __int64)Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_129;
    v10 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2Eu, &Handle);
    if ( v10 < 0 )
    {
      v17[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v17[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v17[2] = 660;
      v17[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.G"
               "etInitPointer())";
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
  }
  else
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
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v27[2] = 1;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v27[0] = 12;
  v27[1] = 2;
  ObjectAttributes.SecurityQualityOfService = v27;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
LABEL_129:
    INTERNAL_ERROR_ACTION(-1073741595);
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
0x180011058  mov     rax, rsp
0x18001105b  push    rbp
0x18001105c  push    rsi
0x18001105d  push    rdi
0x18001105e  push    r12
0x180011060  push    r13
0x180011062  push    r14
0x180011064  push    r15
0x180011066  lea     rbp, [rsp-70h]
0x18001106b  sub     rsp, 170h
0x180011072  mov     [rbp+0A0h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001107a  mov     [rax+20h], rbx
0x18001107e  mov     rax, cs:__security_cookie
0x180011085  xor     rax, rsp
0x180011088  mov     [rbp+0A0h+var_40], rax
0x18001108c  mov     r12, r8
0x18001108f  mov     r15, rdx
0x180011092  mov     r14, rcx
0x180011095  xor     r13d, r13d
0x180011098  mov     [rbp+0A0h+TokenHandle], r13
0x18001109c  mov     [rbp+0A0h+Handle], r13
0x1800110a0  mov     [rsp+1A0h+var_170], r13
0x1800110a5  mov     [r8], r13b
0x1800110a8  cmp     [rcx+8], r13b
0x1800110ac  jnz     loc_1800117CE
0x1800110b2  cmp     [rcx], r13
0x1800110b5  jnz     loc_1800117CE
0x1800110bb  lea     r9, [rsp+1A0h+var_170]
0x1800110c0  lea     r8d, [r13+0Ch]
0x1800110c4  mov     rdx, [rdx+8]
0x1800110c8  lea     rcx, [rsp+1A0h+var_168]
0x1800110cd  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x1800110d2  mov     edi, [rax]
0x1800110d4  test    edi, edi
0x1800110d6  jns     short loc_180011146
0x1800110d8  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1800110dc  lea     rax, [rcx-1]
0x1800110e0  lea     ebx, [r13+7]
0x1800110e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800110e8  ja      short loc_1800110FC
0x1800110ea  call    cs:__imp_NtClose
0x1800110f0  test    eax, eax
0x1800110f2  jns     short loc_1800110F8
0x1800110f4  mov     ecx, ebx
0x1800110f6  int     29h; Win8: RtlFailFast(ecx)
0x1800110f8  mov     [rbp+0A0h+Handle], r13
0x1800110fc  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x180011100  lea     rax, [rcx-1]
0x180011104  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011108  ja      short loc_18001111D
0x18001110a  call    cs:__imp_NtClose
0x180011110  test    eax, eax
0x180011112  jns     short loc_180011119
0x180011114  mov     rcx, rbx
0x180011117  int     29h; Win8: RtlFailFast(ecx)
0x180011119  mov     [rbp+0A0h+TokenHandle], r13
0x18001111d  mov     eax, edi
0x18001111f  mov     rcx, [rbp+0A0h+var_40]
0x180011123  xor     rcx, rsp; StackCookie
0x180011126  call    __security_check_cookie
0x18001112b  mov     rbx, [rsp+1A0h+arg_18]
0x180011133  add     rsp, 170h
0x18001113a  pop     r15
0x18001113c  pop     r14
0x18001113e  pop     r13
0x180011140  pop     r12
0x180011142  pop     rdi
0x180011143  pop     rsi
0x180011144  pop     rbp
0x180011145  retn
0x180011146  mov     rcx, [rsp+1A0h+var_170]
0x18001114b  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18001114f  jnb     loc_18001173E
0x180011155  add     rcx, 10h; Size
0x180011159  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001115e  mov     rbx, rax
0x180011161  lea     rdi, [rax+10h]
0x180011165  mov     eax, r13d
0x180011168  xor     ecx, ecx
0x18001116a  mov     dword ptr [rsp+1A0h+var_170+4], ecx
0x18001116e  mov     ecx, 0FFFFFFFFh
0x180011173  cmp     [r15+8], rcx
0x180011177  ja      short loc_18001118F
0x180011179  mov     eax, [r15+8]
0x18001117d  cmp     [r15+8], rax
0x180011181  jz      short loc_18001118A
0x180011183  mov     esi, 0C00000E5h
0x180011188  jmp     short loc_180011194
0x18001118a  mov     esi, r13d
0x18001118d  jmp     short loc_180011194
0x18001118f  mov     esi, 0C0000095h
0x180011194  mov     [rbx], eax
0x180011196  test    esi, esi
0x180011198  jns     short loc_180011201
0x18001119a  mov     rcx, rbx; void *
0x18001119d  test    rdi, rdi
0x1800111a0  jz      short loc_1800111A9
0x1800111a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800111a7  jmp     short loc_1800111B4
0x1800111a9  mov     edx, 10h; unsigned __int64
0x1800111ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800111b3  nop
0x1800111b4  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1800111b8  lea     rax, [rcx-1]
0x1800111bc  mov     ebx, 7
0x1800111c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800111c5  ja      short loc_1800111D9
0x1800111c7  call    cs:__imp_NtClose
0x1800111cd  test    eax, eax
0x1800111cf  jns     short loc_1800111D5
0x1800111d1  mov     ecx, ebx
0x1800111d3  int     29h; Win8: RtlFailFast(ecx)
0x1800111d5  mov     [rbp+0A0h+Handle], r13
0x1800111d9  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1800111dd  lea     rax, [rcx-1]
0x1800111e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800111e5  ja      short loc_1800111FA
0x1800111e7  call    cs:__imp_NtClose
0x1800111ed  test    eax, eax
0x1800111ef  jns     short loc_1800111F6
0x1800111f1  mov     rcx, rbx
0x1800111f4  int     29h; Win8: RtlFailFast(ecx)
0x1800111f6  mov     [rbp+0A0h+TokenHandle], r13
0x1800111fa  mov     eax, esi
0x1800111fc  jmp     loc_18001111F
0x180011201  mov     rdx, r13
0x180011204  cmp     [r15+8], r13
0x180011208  jbe     short loc_18001123C
0x18001120a  mov     rax, [r15]
0x18001120d  movsxd  rax, dword ptr [rax+rdx*4]
0x180011211  mov     dword ptr [rsp+1A0h+var_170], eax
0x180011215  shr     rax, 20h
0x180011219  mov     dword ptr [rsp+1A0h+var_170+4], eax
0x18001121d  lea     rcx, [rdx+rdx*2]
0x180011221  mov     rax, [rsp+1A0h+var_170]
0x180011226  mov     [rbx+rcx*4+4], rax
0x18001122b  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x180011233  inc     rdx
0x180011236  cmp     rdx, [r15+8]
0x18001123a  jb      short loc_18001120A
0x18001123c  mov     rax, [rbp+0A0h+Handle]
0x180011240  inc     rax
0x180011243  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011249  jnz     loc_1800117CE
0x18001124f  lea     r9, [rbp+0A0h+Handle]; TokenHandle
0x180011253  mov     r8b, 1; OpenAsSelf
0x180011256  mov     r15d, 2Eh ; '.'
0x18001125c  mov     edx, r15d; DesiredAccess
0x18001125f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180011266  call    cs:__imp_NtOpenThreadToken
0x18001126c  mov     esi, eax
0x18001126e  cmp     eax, 0C000007Ch
0x180011273  jnz     loc_180011355
0x180011279  mov     rax, [rbp+0A0h+Handle]
0x18001127d  inc     rax
0x180011280  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011286  jnz     loc_1800117CE
0x18001128c  lea     r8, [rbp+0A0h+Handle]; TokenHandle
0x180011290  mov     edx, r15d; DesiredAccess
0x180011293  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180011297  call    cs:__imp_NtOpenProcessToken
0x18001129d  mov     esi, eax
0x18001129f  test    eax, eax
0x1800112a1  jns     loc_18001134D
0x1800112a7  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1800112ae  mov     [rsp+1A0h+var_160], rcx
0x1800112b3  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1800112ba  mov     [rsp+1A0h+var_158], rcx
0x1800112bf  mov     [rsp+1A0h+var_150], 294h
0x1800112c8  lea     rax, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1800112cf  mov     [rsp+1A0h+var_148], rax
0x1800112d4  mov     r8d, esi
0x1800112d7  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800112de  lea     rcx, [rsp+1A0h+var_160]
0x1800112e3  call    RtlReportErrorOrigination
0x1800112e8  mov     rcx, rbx; void *
0x1800112eb  test    rdi, rdi
0x1800112ee  jz      short loc_1800112F7
0x1800112f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800112f5  jmp     short loc_180011302
0x1800112f7  mov     edx, 10h; unsigned __int64
0x1800112fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011301  nop
0x180011302  mov     rcx, [rbp+0A0h+Handle]; Handle
0x180011306  lea     rax, [rcx-1]
0x18001130a  mov     ebx, 7
0x18001130f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011313  ja      short loc_180011327
0x180011315  call    cs:__imp_NtClose
0x18001131b  test    eax, eax
0x18001131d  jns     short loc_180011323
0x18001131f  mov     ecx, ebx
0x180011321  int     29h; Win8: RtlFailFast(ecx)
0x180011323  mov     [rbp+0A0h+Handle], r13
0x180011327  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x18001132b  lea     rax, [rcx-1]
0x18001132f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011333  ja      short loc_180011348
0x180011335  call    cs:__imp_NtClose
0x18001133b  test    eax, eax
0x18001133d  jns     short loc_180011344
0x18001133f  mov     rcx, rbx
0x180011342  int     29h; Win8: RtlFailFast(ecx)
0x180011344  mov     [rbp+0A0h+TokenHandle], r13
0x180011348  jmp     loc_1800111FA
0x18001134d  mov     r15b, r13b
0x180011350  jmp     loc_180011406
0x180011355  test    esi, esi
0x180011357  jns     loc_180011403
0x18001135d  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180011364  mov     [rsp+1A0h+var_140], rcx
0x180011369  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180011370  mov     [rsp+1A0h+var_138], rcx
0x180011375  mov     [rsp+1A0h+var_130], 29Ah
0x18001137e  lea     rax, aStatus; "Status"
0x180011385  mov     [rsp+1A0h+var_128], rax
0x18001138a  mov     r8d, esi
0x18001138d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180011394  lea     rcx, [rsp+1A0h+var_140]
0x180011399  call    RtlReportErrorOrigination
0x18001139e  mov     rcx, rbx; void *
0x1800113a1  test    rdi, rdi
0x1800113a4  jz      short loc_1800113AD
0x1800113a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800113ab  jmp     short loc_1800113B8
0x1800113ad  mov     edx, 10h; unsigned __int64
0x1800113b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800113b7  nop
0x1800113b8  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1800113bc  lea     rax, [rcx-1]
0x1800113c0  mov     ebx, 7
0x1800113c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800113c9  ja      short loc_1800113DD
0x1800113cb  call    cs:__imp_NtClose
0x1800113d1  test    eax, eax
0x1800113d3  jns     short loc_1800113D9
0x1800113d5  mov     ecx, ebx
0x1800113d7  int     29h; Win8: RtlFailFast(ecx)
0x1800113d9  mov     [rbp+0A0h+Handle], r13
0x1800113dd  mov     rcx, [rbp+0A0h+TokenHandle]; Handle
0x1800113e1  lea     rax, [rcx-1]
0x1800113e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800113e9  ja      short loc_1800113FE
0x1800113eb  call    cs:__imp_NtClose
0x1800113f1  test    eax, eax
0x1800113f3  jns     short loc_1800113FA
0x1800113f5  mov     rcx, rbx
0x1800113f8  int     29h; Win8: RtlFailFast(ecx)
0x1800113fa  mov     [rbp+0A0h+TokenHandle], r13
0x1800113fe  jmp     loc_1800111FA
0x180011403  mov     r15b, 1
0x180011406  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18001140e  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], r13
0x180011412  mov     [rbp+0A0h+var_48], 1
0x180011419  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r13
0x18001141d  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x180011421  mov     [rbp+0A0h+ObjectAttributes.SecurityDescriptor], r13
0x180011425  mov     [rbp+0A0h+var_50], 0Ch
0x18001142c  mov     ecx, 2
0x180011431  mov     [rbp+0A0h+var_4C], ecx
0x180011434  lea     rax, [rbp+0A0h+var_50]
0x180011438  mov     [rbp+0A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18001143c  mov     rax, [rbp+0A0h+TokenHandle]
0x180011440  dec     rax
0x180011443  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011447  jbe     loc_1800117CE
0x18001144d  lea     rax, [rbp+0A0h+TokenHandle]
0x180011451  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x180011456  mov     [rsp+1A0h+TokenType], ecx; TokenType
0x18001145a  xor     r9d, r9d; EffectiveOnly
0x18001145d  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x180011461  lea     edx, [rcx+2Ah]; DesiredAccess
0x180011464  mov     rcx, [rbp+0A0h+Handle]; ExistingTokenHandle
0x180011468  call    cs:__imp_NtDuplicateToken
0x18001146e  mov     esi, eax
0x180011470  test    eax, eax
0x180011472  jns     loc_180011519
0x180011478  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001147f  mov     [rbp+0A0h+var_120], rcx
0x180011483  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18001148a  mov     [rbp+0A0h+var_118], rcx
0x18001148e  mov     [rbp+0A0h+var_110], 2AEh
0x180011496  lea     rax, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x18001149d  mov     [rbp+0A0h+var_108], rax
0x1800114a1  mov     r8d, esi
0x1800114a4  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800114ab  lea     rcx, [rbp+0A0h+var_120]
0x1800114af  call    RtlReportErrorOrigination
0x1800114b4  mov     rcx, rbx; void *
0x1800114b7  test    rdi, rdi
0x1800114ba  jz      short loc_1800114C3
0x1800114bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800114c1  jmp     short loc_1800114CE
0x1800114c3  mov     edx, 10h; unsigned __int64
0x1800114c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800114cd  nop
0x1800114ce  mov     rcx, [rbp+0A0h+Handle]; Handle
0x1800114d2  lea     rax, [rcx-1]
0x1800114d6  mov     ebx, 7
0x1800114db  cmp     rax, 0FFFFFFFFFFFFFFFDh
  ... truncated ...
```
