# CUserVaultMgr::CreateOrReinitBuiltinVault(void *)

- ea: `0x18003c784`
- end: `0x18003c940`
- name: `?CreateOrReinitBuiltinVault@CUserVaultMgr@@AEAAKPEAX@Z`
- size: `444`
- prototype: `__int64 __fastcall(wchar_t **this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18000cd28`

## callees

- `0x180001008`
- `0x180003140`
- `0x18003577c`
- `0x18003b7d8`
- `0x18003b920`
- `0x18003b9ac`
- `0x18003c4e0`
- `0x18003c784`
- `0x18003cb08`
- `0x18003cc10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c818`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c809`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c809`
- `LSASRV!LsaILookupUserAccountType` at `0x18003c87e`
- `LSASRV!LsaILookupUserAccountType` at `0x18003c87e`
- `ntdll!RtlNtStatusToDosError` at `0x18003c88c`
- `ntdll!RtlNtStatusToDosError` at `0x18003c88c`

## string_xrefs

- `0x18003c83b`: `create`

## pseudocode

```c
__int64 __fastcall CUserVaultMgr::CreateOrReinitBuiltinVault(wchar_t **this, void *a2)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax
  const wchar_t *v7; // r9
  NTSTATUS v8; // eax
  unsigned int v9; // edi
  unsigned int BuiltinVault; // ebx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-18h] BYREF
  int v16; // [rsp+50h] [rbp-10h]
  unsigned int v17; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v18; // [rsp+A0h] [rbp+40h] BYREF
  int *AccountTypeString; // [rsp+A8h] [rbp+48h] BYREF

  lpFileName = 0;
  v16 = 0;
  v14 = 0;
  if ( !*((_BYTE *)this + 70) )
  {
    v4 = BuildVaultPath(this[6], &Vault_DefaultVault_ID, (unsigned __int16 **)&lpFileName);
    if ( v4 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v14);
      return v4;
    }
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x2000080u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandle(FileW);
      *((_BYTE *)this + 70) = 1;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v7 = L"reinit";
    if ( !*((_BYTE *)this + 70) )
      v7 = L"create";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v7);
  }
  if ( *((_BYTE *)this + 70) )
  {
    v17 = 0;
    v8 = LsaILookupUserAccountType(a2, &v17);
    v9 = v8;
    if ( v8 >= 0 )
    {
      BuiltinVault = CUserVaultMgr::ReinitBuiltinVault((CUserVaultMgr *)this);
      if ( (unsigned int)dword_18005F088 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005F088) )
      {
        v18 = BuiltinVault;
        AccountTypeString = (int *)GetAccountTypeString(v17);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v11,
          (__int64)byte_180054C31,
          v12,
          v13,
          &AccountTypeString,
          (__int64)&v18);
      }
    }
    else
    {
      BuiltinVault = RtlNtStatusToDosError(v8);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v9);
    }
  }
  else
  {
    BuiltinVault = CUserVaultMgr::CreateBuiltinVault((CUserVaultMgr *)this);
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v14);
  return BuiltinVault;
}

```

## disassembly

```asm
0x18003c784  push    rbp
0x18003c786  push    rbx
0x18003c787  push    rsi
0x18003c788  push    rdi
0x18003c789  push    r15
0x18003c78b  mov     rbp, rsp
0x18003c78e  sub     rsp, 60h
0x18003c792  mov     rsi, rdx
0x18003c795  mov     rbx, rcx
0x18003c798  mov     [rbp+lpFileName], 0
0x18003c7a0  mov     [rbp+var_10], 0
0x18003c7a7  mov     [rbp+var_20], 0
0x18003c7af  cmp     byte ptr [rcx+46h], 0
0x18003c7b3  jnz     short loc_18003C822
0x18003c7b5  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x18003c7b9  lea     rdx, Vault_DefaultVault_ID; struct _GUID *
0x18003c7c0  mov     rcx, [rcx+30h]; Source
0x18003c7c4  call    ?BuildVaultPath@@YAKPEBGPEBU_GUID@@PEAPEAG@Z; BuildVaultPath(ushort const *,_GUID const *,ushort * *)
0x18003c7c9  mov     edi, eax
0x18003c7cb  test    eax, eax
0x18003c7cd  jz      short loc_18003C7E0
0x18003c7cf  lea     rcx, [rbp+var_20]
0x18003c7d3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003c7d8  nop
0x18003c7d9  mov     eax, edi
0x18003c7db  jmp     loc_18003C935
0x18003c7e0  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18003c7e9  mov     [rsp+60h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18003c7f1  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c7f9  xor     r9d, r9d; lpSecurityAttributes
0x18003c7fc  mov     edx, 80000000h; dwDesiredAccess
0x18003c801  lea     r8d, [r9+1]; dwShareMode
0x18003c805  mov     rcx, [rbp+lpFileName]; lpFileName
0x18003c809  call    cs:__imp_CreateFileW
0x18003c80f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c813  jz      short loc_18003C822
0x18003c815  mov     rcx, rax; hObject
0x18003c818  call    cs:__imp_CloseHandle
0x18003c81e  mov     byte ptr [rbx+46h], 1
0x18003c822  lea     r15, WPP_GLOBAL_Control
0x18003c829  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c830  cmp     rcx, r15
0x18003c833  jz      short loc_18003C866
0x18003c835  test    byte ptr [rcx+1Ch], 8
0x18003c839  jz      short loc_18003C866
0x18003c83b  lea     rax, aCreate; "create"
0x18003c842  lea     r9, aReinit; "reinit"
0x18003c849  cmp     byte ptr [rbx+46h], 0
0x18003c84d  cmovz   r9, rax
0x18003c851  mov     edx, 33h ; '3'
0x18003c856  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18003c85d  mov     rcx, [rcx+10h]
0x18003c861  call    WPP_SF_S
0x18003c866  cmp     byte ptr [rbx+46h], 0
0x18003c86a  jz      loc_18003C91F
0x18003c870  mov     [rbp+arg_0], 0
0x18003c877  lea     rdx, [rbp+arg_0]
0x18003c87b  mov     rcx, rsi
0x18003c87e  call    cs:__imp_LsaILookupUserAccountType
0x18003c884  mov     edi, eax
0x18003c886  test    eax, eax
0x18003c888  jns     short loc_18003C8CB
0x18003c88a  mov     ecx, eax; Status
0x18003c88c  call    cs:__imp_RtlNtStatusToDosError
0x18003c892  mov     ebx, eax
0x18003c894  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c89b  cmp     rcx, r15
0x18003c89e  jz      short loc_18003C8BF
0x18003c8a0  test    byte ptr [rcx+1Ch], 2
0x18003c8a4  jz      short loc_18003C8BF
0x18003c8a6  mov     edx, 34h ; '4'
0x18003c8ab  mov     r9d, edi
0x18003c8ae  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18003c8b5  mov     rcx, [rcx+10h]
0x18003c8b9  call    WPP_SF_d
0x18003c8be  nop
0x18003c8bf  lea     rcx, [rbp+var_20]
0x18003c8c3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003c8c8  nop
0x18003c8c9  jmp     short loc_18003C933
0x18003c8cb  mov     rcx, rbx; this
0x18003c8ce  call    ?ReinitBuiltinVault@CUserVaultMgr@@AEAAKXZ; CUserVaultMgr::ReinitBuiltinVault(void)
0x18003c8d3  mov     ebx, eax
0x18003c8d5  mov     ecx, cs:dword_18005F088
0x18003c8db  cmp     ecx, 5
0x18003c8de  jbe     short loc_18003C929
0x18003c8e0  lea     rcx, dword_18005F088
0x18003c8e7  call    _tlgKeywordOn
0x18003c8ec  test    al, al
0x18003c8ee  jz      short loc_18003C929
0x18003c8f0  mov     [rbp+arg_10], ebx
0x18003c8f3  mov     ecx, [rbp+arg_0]
0x18003c8f6  call    ?GetAccountTypeString@@YAPEBGW4_LSA_USER_ACCOUNT_TYPE@@@Z; GetAccountTypeString(_LSA_USER_ACCOUNT_TYPE)
0x18003c8fb  mov     [rbp+arg_18], rax
0x18003c8ff  lea     rax, [rbp+arg_10]
0x18003c903  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax
0x18003c908  lea     rax, [rbp+arg_18]
0x18003c90c  mov     qword ptr [rsp+60h+dwCreationDisposition], rax
0x18003c911  lea     rdx, byte_180054C31
0x18003c918  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003c91d  jmp     short loc_18003C929
0x18003c91f  mov     rcx, rbx; this
0x18003c922  call    ?CreateBuiltinVault@CUserVaultMgr@@AEAAKXZ; CUserVaultMgr::CreateBuiltinVault(void)
0x18003c927  mov     ebx, eax
0x18003c929  lea     rcx, [rbp+var_20]
0x18003c92d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003c932  nop
0x18003c933  mov     eax, ebx
0x18003c935  add     rsp, 60h
0x18003c939  pop     r15
0x18003c93b  pop     rdi
0x18003c93c  pop     rsi
0x18003c93d  pop     rbx
0x18003c93e  pop     rbp
0x18003c93f  retn
```
