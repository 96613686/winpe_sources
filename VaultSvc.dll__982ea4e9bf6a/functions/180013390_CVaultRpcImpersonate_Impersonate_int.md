# CVaultRpcImpersonate::Impersonate(int)

- ea: `0x180013390`
- end: `0x1800135c0`
- name: `?Impersonate@CVaultRpcImpersonate@@QEAAKH@Z`
- size: `560`
- prototype: `__int64 __fastcall(CVaultRpcImpersonate *this, int)`
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012470`
- `0x180012ae0`
- `0x1800151d0`
- `0x180015e30`
- `0x18001eda0`
- `0x180026a80`
- `0x180029690`
- `0x18002f5e0`
- `0x180034460`
- `0x180045df0`
- `0x180046040`
- `0x180046920`
- `0x180046d90`
- `0x180047610`
- `0x180047890`
- `0x180047e90`
- `0x180048140`
- `0x1800483f0`

## callees

- `0x18000eb30`
- `0x180013390`
- `0x180015620`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134ba`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180013476`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180013476`
- `RPCRT4!RpcImpersonateClient` at `0x1800133e1`
- `RPCRT4!RpcImpersonateClient` at `0x1800133e1`
- `ntdll!NtQueryInformationToken` at `0x180013429`
- `ntdll!NtQueryInformationToken` at `0x180013429`
- `ntdll!NtOpenThreadToken` at `0x1800133ca`
- `ntdll!NtOpenThreadToken` at `0x1800133ca`
- `ntdll!RtlNtStatusToDosError` at `0x18001353c`
- `ntdll!RtlNtStatusToDosError` at `0x18001353c`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CVaultRpcImpersonate::Impersonate(CVaultRpcImpersonate *this, int a2)
{
  unsigned int v4; // eax
  ULONG v5; // esi
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  DWORD LastError; // eax
  int v10; // [rsp+30h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  ReturnLength = 0;
  TokenInformation = 0;
  v10 = 0;
  hObject = 0;
  if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &hObject) >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
    CloseHandle(hObject);
  }
  else
  {
    v4 = RpcImpersonateClient(0);
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, v4);
LABEL_28:
      CVaultRpcImpersonate::UnImpersonate(this);
      return v5;
    }
    *(_BYTE *)this = 1;
  }
  if ( !a2 )
    return 0;
  ReturnLength = 4;
  TokenInformation = 0;
  v6 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids,
        (unsigned int)v6);
    v5 = RtlNtStatusToDosError(v7);
  }
  else
  {
    if ( !TokenInformation )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
      return 0;
    }
    if ( (unsigned int)CheckTokenCapability(0, VaultGlobals::g_PrivAppSID, &v10) )
    {
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
        CVaultIntegrityLevel::Elevate((CVaultRpcImpersonate *)((char *)this + 8));
      }
      return 0;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, LastError);
  }
  if ( v5 )
    goto LABEL_28;
  return v5;
}

```

## disassembly

```asm
0x180013390  mov     rax, rsp
0x180013393  mov     [rax+8], rbx
0x180013397  mov     [rax+10h], rbp
0x18001339b  push    rsi
0x18001339c  push    rdi
0x18001339d  push    r14
0x18001339f  sub     rsp, 40h
0x1800133a3  xor     ebp, ebp
0x1800133a5  lea     r9, [rax-20h]; TokenHandle
0x1800133a9  mov     ebx, edx
0x1800133ab  mov     [rax+20h], ebp
0x1800133ae  mov     rdi, rcx
0x1800133b1  mov     [rax+18h], ebp
0x1800133b4  mov     edx, 8; DesiredAccess
0x1800133b9  mov     [rax-28h], ebp
0x1800133bc  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800133c3  mov     [rax-20h], rbp
0x1800133c7  mov     r8b, 1; OpenAsSelf
0x1800133ca  call    cs:__imp_NtOpenThreadToken
0x1800133d0  lea     r14, WPP_GLOBAL_Control
0x1800133d7  test    eax, eax
0x1800133d9  jns     loc_1800134A3
0x1800133df  xor     ecx, ecx; BindingHandle
0x1800133e1  call    cs:__imp_RpcImpersonateClient
0x1800133e7  mov     esi, eax
0x1800133e9  test    eax, eax
0x1800133eb  jnz     loc_1800134DC
0x1800133f1  mov     byte ptr [rdi], 1
0x1800133f4  test    ebx, ebx
0x1800133f6  jz      loc_18001348E
0x1800133fc  lea     rax, [rsp+58h+arg_18]
0x180013401  mov     [rsp+58h+arg_18], 4
0x180013409  mov     r9d, 4; TokenInformationLength
0x18001340f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180013414  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180013419  mov     [rsp+58h+TokenInformation], ebp
0x18001341d  mov     edx, 1Dh; TokenInformationClass
0x180013422  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180013429  call    cs:__imp_NtQueryInformationToken
0x18001342f  mov     ebx, eax
0x180013431  test    eax, eax
0x180013433  js      loc_180013510
0x180013439  cmp     [rsp+58h+TokenInformation], ebp
0x18001343d  jnz     short loc_180013468
0x18001343f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013446  cmp     rcx, r14
0x180013449  jz      short loc_18001348E
0x18001344b  test    byte ptr [rcx+1Ch], 8
0x18001344f  jz      short loc_18001348E
0x180013451  mov     rcx, [rcx+10h]
0x180013455  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18001345c  mov     edx, 18h
0x180013461  call    WPP_SF_
0x180013466  jmp     short loc_18001348E
0x180013468  mov     rdx, cs:?g_PrivAppSID@VaultGlobals@@3PEAXEA; void * VaultGlobals::g_PrivAppSID
0x18001346f  lea     r8, [rsp+58h+var_28]
0x180013474  xor     ecx, ecx
0x180013476  call    cs:__imp_CheckTokenCapability
0x18001347c  test    eax, eax
0x18001347e  jz      loc_180013546
0x180013484  cmp     [rsp+58h+var_28], ebp
0x180013488  jnz     loc_18001358B
0x18001348e  mov     eax, ebp
0x180013490  mov     rbx, [rsp+58h+arg_0]
0x180013495  mov     rbp, [rsp+58h+arg_8]
0x18001349a  add     rsp, 40h
0x18001349e  pop     r14
0x1800134a0  pop     rdi
0x1800134a1  pop     rsi
0x1800134a2  retn
0x1800134a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134aa  cmp     rcx, r14
0x1800134ad  jz      short loc_1800134B5
0x1800134af  test    byte ptr [rcx+1Ch], 8
0x1800134b3  jnz     short loc_1800134C5
0x1800134b5  mov     rcx, [rsp+58h+hObject]; hObject
0x1800134ba  call    cs:__imp_CloseHandle
0x1800134c0  jmp     loc_1800133F4
0x1800134c5  mov     rcx, [rcx+10h]
0x1800134c9  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x1800134d0  mov     edx, 15h
0x1800134d5  call    WPP_SF_
0x1800134da  jmp     short loc_1800134B5
0x1800134dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134e3  cmp     rcx, r14
0x1800134e6  jz      loc_18001357C
0x1800134ec  test    byte ptr [rcx+1Ch], 2
0x1800134f0  jz      loc_18001357C
0x1800134f6  mov     rcx, [rcx+10h]
0x1800134fa  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180013501  mov     edx, 16h
0x180013506  mov     r9d, eax
0x180013509  call    WPP_SF_d
0x18001350e  jmp     short loc_18001357C
0x180013510  mov     rcx, cs:WPP_GLOBAL_Control
0x180013517  cmp     rcx, r14
0x18001351a  jz      short loc_18001353A
0x18001351c  test    byte ptr [rcx+1Ch], 2
0x180013520  jz      short loc_18001353A
0x180013522  mov     rcx, [rcx+10h]
0x180013526  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18001352d  mov     edx, 17h
0x180013532  mov     r9d, ebx
0x180013535  call    WPP_SF_d
0x18001353a  mov     ecx, ebx; Status
0x18001353c  call    cs:__imp_RtlNtStatusToDosError
0x180013542  mov     esi, eax
0x180013544  jmp     short loc_180013578
0x180013546  call    cs:__imp_GetLastError
0x18001354c  mov     esi, eax
0x18001354e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013555  cmp     rcx, r14
0x180013558  jz      short loc_180013578
0x18001355a  test    byte ptr [rcx+1Ch], 2
0x18001355e  jz      short loc_180013578
0x180013560  mov     rcx, [rcx+10h]
0x180013564  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18001356b  mov     edx, 19h
0x180013570  mov     r9d, eax
0x180013573  call    WPP_SF_d
0x180013578  test    esi, esi
0x18001357a  jz      short loc_180013584
0x18001357c  mov     rcx, rdi; this
0x18001357f  call    ?UnImpersonate@CVaultRpcImpersonate@@QEAAXXZ; CVaultRpcImpersonate::UnImpersonate(void)
0x180013584  mov     eax, esi
0x180013586  jmp     loc_180013490
0x18001358b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013592  cmp     rcx, r14
0x180013595  jz      short loc_1800135B2
0x180013597  test    byte ptr [rcx+1Ch], 8
0x18001359b  jz      short loc_1800135B2
0x18001359d  mov     rcx, [rcx+10h]
0x1800135a1  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x1800135a8  mov     edx, 1Ah
0x1800135ad  call    WPP_SF_
0x1800135b2  lea     rcx, [rdi+8]; this
0x1800135b6  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x1800135bb  jmp     loc_18001348E
```
