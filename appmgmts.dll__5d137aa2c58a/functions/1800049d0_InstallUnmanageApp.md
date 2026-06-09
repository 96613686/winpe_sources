# InstallUnmanageApp

- ea: `0x1800049d0`
- end: `0x180004be8`
- name: `InstallUnmanageApp`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x1800049d0`
- `0x180008fe4`
- `0x18000d524`
- `0x1800131d4`
- `0x18001b1a0`
- `0x18001b4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a56`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004ba7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004ba7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004a2c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004a2c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004bbd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004bbd`

## pseudocode

```c
__int64 __fastcall InstallUnmanageApp(struct CAppInfo **a1, const unsigned __int16 *a2, char a3)
{
  struct CAppInfo *v5; // rcx
  DWORD LastError; // eax
  unsigned int v7; // ebx
  struct CAppInfo **v8; // rdi
  CAppInfo *v9; // rcx
  unsigned int v10; // eax
  struct CAppInfo *v11; // rcx
  struct CAppInfo *v12; // rsi
  CAppInfo *v13; // rcx
  unsigned int v14; // eax
  struct _GUID v16; // [rsp+40h] [rbp-38h] BYREF

  v16 = 0;
  StringToGuid(a2, &v16);
  v5 = *a1;
  if ( *((_DWORD *)*a1 + 99) != 1 && *((_DWORD *)v5 + 74) && !ImpersonateLoggedOnUser(*((HANDLE *)v5 + 33)) )
  {
    if ( *(_DWORD *)&gDebugLevel )
    {
      LastError = GetLastError();
      _DebugMsg(2, 0xBC4u, LastError);
    }
    v7 = GetLastError();
    if ( v7 )
    {
      v8 = a1 + 1;
LABEL_28:
      if ( !a3 )
        DeleteFileW(*((LPCWSTR *)*v8 + 11));
      return v7;
    }
  }
  v8 = a1 + 1;
  v9 = a1[1];
  if ( *(_QWORD *)&v16.Data1 == *((_QWORD *)v9 + 3) && *(_QWORD *)v16.Data4 == *((_QWORD *)v9 + 4) )
  {
    v10 = CAppInfo::Unassign(v9, 33, 1);
    v7 = v10;
    if ( v10 )
      CEvents::Unassign((struct CAppInfo *)((char *)*a1 + 344), v10, *v8);
  }
  else
  {
    v11 = *a1;
    *((_QWORD *)v11 + 13) = *((_QWORD *)*a1 + 12);
    *((_QWORD *)v11 + 12) = *((_QWORD *)v11 + 11);
    while ( 1 )
    {
      v12 = (struct CAppInfo *)*((_QWORD *)*a1 + 12);
      if ( v12 == (struct CAppInfo *)((char *)*a1 + 80) || !v12 )
      {
        v7 = 1168;
        goto LABEL_24;
      }
      if ( *(_QWORD *)&v16.Data1 == *((_QWORD *)v12 + 3) && *(_QWORD *)v16.Data4 == *((_QWORD *)v12 + 4) )
        break;
      *((_QWORD *)*a1 + 12) = *((_QWORD *)v12 + 1);
    }
    v13 = (CAppInfo *)*((_QWORD *)*a1 + 12);
    if ( a3 )
    {
      v7 = CAppInfo::Unassign(v13, 293, 0);
    }
    else
    {
      v14 = CAppInfo::Unassign(v13, 0, 1);
      v7 = v14;
      if ( v14 )
        CEvents::Unassign((struct CAppInfo *)((char *)*a1 + 344), v14, v12);
      CEventsBase::Report(
        (void **)*a1 + 43,
        0x132u,
        0,
        4u,
        *((_QWORD *)*v8 + 5),
        *((_QWORD *)*v8 + 9),
        *((_QWORD *)v12 + 5),
        *((_QWORD *)v12 + 9));
    }
  }
LABEL_24:
  if ( *((_DWORD *)*a1 + 99) != 1 && *((_DWORD *)*a1 + 74) )
    RevertToSelf();
  if ( v7 )
    goto LABEL_28;
  return v7;
}

```

## disassembly

```asm
0x1800049d0  mov     [rsp+arg_10], rbx
0x1800049d5  mov     [rsp+arg_18], rsi
0x1800049da  push    rdi
0x1800049db  push    r14
0x1800049dd  push    r15
0x1800049df  sub     rsp, 60h
0x1800049e3  mov     rax, cs:__security_cookie
0x1800049ea  xor     rax, rsp
0x1800049ed  mov     [rsp+78h+var_28], rax
0x1800049f2  mov     rax, rdx
0x1800049f5  mov     r14, rcx
0x1800049f8  xorps   xmm0, xmm0
0x1800049fb  lea     rdx, [rsp+78h+var_38]; struct _GUID *
0x180004a00  mov     rcx, rax; unsigned __int16 *
0x180004a03  mov     r15b, r8b
0x180004a06  movups  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x180004a0b  call    ?StringToGuid@@YAXPEBGPEAU_GUID@@@Z; StringToGuid(ushort const *,_GUID *)
0x180004a10  mov     rcx, [r14]
0x180004a13  cmp     dword ptr [rcx+18Ch], 1
0x180004a1a  jz      short loc_180004A6B
0x180004a1c  cmp     dword ptr [rcx+128h], 0
0x180004a23  jz      short loc_180004A6B
0x180004a25  mov     rcx, [rcx+108h]; hToken
0x180004a2c  call    cs:__imp_ImpersonateLoggedOnUser
0x180004a32  test    eax, eax
0x180004a34  jnz     short loc_180004A6B
0x180004a36  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180004a3c  jz      short loc_180004A56
0x180004a3e  call    cs:__imp_GetLastError
0x180004a44  mov     edx, 0BC4h; unsigned int
0x180004a49  mov     ecx, 2; unsigned int
0x180004a4e  mov     r8d, eax
0x180004a51  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180004a56  call    cs:__imp_GetLastError
0x180004a5c  mov     ebx, eax
0x180004a5e  test    eax, eax
0x180004a60  jz      short loc_180004A6B
0x180004a62  lea     rdi, [r14+8]
0x180004a66  jmp     loc_180004BB1
0x180004a6b  mov     rax, qword ptr [rsp+78h+var_38.Data1]
0x180004a70  lea     rdi, [r14+8]
0x180004a74  mov     rcx, [rdi]; this
0x180004a77  cmp     rax, [rcx+18h]
0x180004a7b  jnz     short loc_180004AB9
0x180004a7d  mov     rax, qword ptr [rsp+78h+var_38.Data4]
0x180004a82  cmp     rax, [rcx+20h]
0x180004a86  jnz     short loc_180004AB9
0x180004a88  mov     edx, 21h ; '!'; unsigned int
0x180004a8d  lea     r8d, [rdx-20h]; int
0x180004a91  call    ?Unassign@CAppInfo@@QEAAKKH@Z; CAppInfo::Unassign(ulong,int)
0x180004a96  mov     ebx, eax
0x180004a98  test    eax, eax
0x180004a9a  jz      loc_180004B92
0x180004aa0  mov     rcx, [r14]
0x180004aa3  mov     edx, eax; unsigned int
0x180004aa5  mov     r8, [rdi]; struct CAppInfo *
0x180004aa8  add     rcx, 158h; this
0x180004aaf  call    ?Unassign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Unassign(ulong,CAppInfo *)
0x180004ab4  jmp     loc_180004B92
0x180004ab9  mov     rcx, [r14]
0x180004abc  mov     rax, [rcx+60h]
0x180004ac0  mov     [rcx+68h], rax
0x180004ac4  mov     rax, [rcx+58h]
0x180004ac8  mov     [rcx+60h], rax
0x180004acc  mov     rcx, [r14]
0x180004acf  add     rcx, 50h ; 'P'
0x180004ad3  mov     rsi, [rcx+10h]
0x180004ad7  cmp     rsi, rcx
0x180004ada  jz      loc_180004B8D
0x180004ae0  test    rsi, rsi
0x180004ae3  jz      loc_180004B8D
0x180004ae9  mov     rax, qword ptr [rsp+78h+var_38.Data1]
0x180004aee  cmp     rax, [rsi+18h]
0x180004af2  jnz     short loc_180004AFF
0x180004af4  mov     rax, qword ptr [rsp+78h+var_38.Data4]
0x180004af9  cmp     rax, [rsi+20h]
0x180004afd  jz      short loc_180004B09
0x180004aff  mov     rax, [rsi+8]
0x180004b03  mov     [rcx+10h], rax
0x180004b07  jmp     short loc_180004ACC
0x180004b09  mov     rcx, rsi; this
0x180004b0c  test    r15b, r15b
0x180004b0f  jz      short loc_180004B22
0x180004b11  xor     r8d, r8d; int
0x180004b14  mov     edx, 125h; unsigned int
0x180004b19  call    ?Unassign@CAppInfo@@QEAAKKH@Z; CAppInfo::Unassign(ulong,int)
0x180004b1e  mov     ebx, eax
0x180004b20  jmp     short loc_180004B92
0x180004b22  xor     edx, edx; unsigned int
0x180004b24  lea     r8d, [rdx+1]; int
0x180004b28  call    ?Unassign@CAppInfo@@QEAAKKH@Z; CAppInfo::Unassign(ulong,int)
0x180004b2d  mov     ebx, eax
0x180004b2f  test    eax, eax
0x180004b31  jz      short loc_180004B47
0x180004b33  mov     rcx, [r14]
0x180004b36  mov     r8, rsi; struct CAppInfo *
0x180004b39  add     rcx, 158h; this
0x180004b40  mov     edx, eax; unsigned int
0x180004b42  call    ?Unassign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Unassign(ulong,CAppInfo *)
0x180004b47  mov     rdx, [rdi]
0x180004b4a  mov     r9d, 4; unsigned __int16
0x180004b50  mov     rax, [rsi+48h]
0x180004b54  xor     r8d, r8d; int
0x180004b57  mov     rcx, [r14]
0x180004b5a  mov     [rsp+78h+var_40], rax
0x180004b5f  add     rcx, 158h; this
0x180004b66  mov     rax, [rsi+28h]
0x180004b6a  mov     [rsp+78h+var_48], rax
0x180004b6f  mov     rax, [rdx+48h]
0x180004b73  mov     [rsp+78h+var_50], rax
0x180004b78  mov     rax, [rdx+28h]
0x180004b7c  mov     edx, 132h; unsigned int
0x180004b81  mov     [rsp+78h+var_58], rax
0x180004b86  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x180004b8b  jmp     short loc_180004B92
0x180004b8d  mov     ebx, 490h
0x180004b92  mov     rax, [r14]
0x180004b95  cmp     dword ptr [rax+18Ch], 1
0x180004b9c  jz      short loc_180004BAD
0x180004b9e  cmp     dword ptr [rax+128h], 0
0x180004ba5  jz      short loc_180004BAD
0x180004ba7  call    cs:__imp_RevertToSelf
0x180004bad  test    ebx, ebx
0x180004baf  jz      short loc_180004BC3
0x180004bb1  test    r15b, r15b
0x180004bb4  jnz     short loc_180004BC3
0x180004bb6  mov     rcx, [rdi]
0x180004bb9  mov     rcx, [rcx+58h]; lpFileName
0x180004bbd  call    cs:__imp_DeleteFileW
0x180004bc3  mov     eax, ebx
0x180004bc5  mov     rcx, [rsp+78h+var_28]
0x180004bca  xor     rcx, rsp; StackCookie
0x180004bcd  call    __security_check_cookie
0x180004bd2  lea     r11, [rsp+78h+var_18]
0x180004bd7  mov     rbx, [r11+30h]
0x180004bdb  mov     rsi, [r11+38h]
0x180004bdf  mov     rsp, r11
0x180004be2  pop     r15
0x180004be4  pop     r14
0x180004be6  pop     rdi
0x180004be7  retn
```
