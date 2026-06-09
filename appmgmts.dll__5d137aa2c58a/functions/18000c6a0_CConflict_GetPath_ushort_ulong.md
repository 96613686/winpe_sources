# CConflict::GetPath(ushort *,ulong *)

- ea: `0x18000c6a0`
- end: `0x18000c787`
- name: `?GetPath@CConflict@@UEAAJPEAGPEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(CConflict *this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800016d0`
- `0x1800061a0`
- `0x180008f58`
- `0x18000c6a0`
- `0x180012fbc`

## pseudocode

```c
__int64 __fastcall CConflict::GetPath(CConflict *this, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v5; // r9
  unsigned int RsopEntryType; // edi
  int v7; // ebx
  int v10; // [rsp+30h] [rbp-88h]
  unsigned __int16 v11[40]; // [rsp+40h] [rbp-78h] BYREF

  if ( *a3 < 0xB6 )
  {
    *a3 = 182;
    return 1;
  }
  else
  {
    v5 = *((_QWORD *)this + 5);
    if ( *(_DWORD *)(v5 + 304) )
    {
      RsopEntryType = 2;
      v7 = 0;
    }
    else
    {
      v7 = 1;
      if ( *(_DWORD *)(v5 + 296) )
        RsopEntryType = *(_DWORD *)(*(_QWORD *)(v5 + 16) + 308LL) != 0 ? 3 : 1;
      else
        RsopEntryType = CAppInfo::GetRsopEntryType(*((CAppInfo **)this + 5));
    }
    GuidToString((struct _GUID *)(v5 + 24), v11);
    v10 = v7;
    return (unsigned int)StringCchPrintfW(
                           a2,
                           *a3,
                           L"RSOP_ApplicationManagementPolicySetting.EntryType=%d,id=\"%s\",ApplicationId=\"%s\",precedence=%d",
                           RsopEntryType,
                           v11,
                           v11,
                           v10);
  }
}

```

## disassembly

```asm
0x18000c6a0  mov     [rsp+arg_18], rbx
0x18000c6a5  push    rbp
0x18000c6a6  push    rsi
0x18000c6a7  push    rdi
0x18000c6a8  sub     rsp, 0A0h
0x18000c6af  mov     rax, cs:__security_cookie
0x18000c6b6  xor     rax, rsp
0x18000c6b9  mov     [rsp+0B8h+var_28], rax
0x18000c6c1  mov     eax, 0B6h
0x18000c6c6  mov     rsi, r8
0x18000c6c9  mov     rbp, rdx
0x18000c6cc  cmp     [r8], eax
0x18000c6cf  jb      loc_18000C75A
0x18000c6d5  mov     r9, [rcx+28h]
0x18000c6d9  cmp     dword ptr [r9+130h], 0
0x18000c6e1  jz      short loc_18000C6EC
0x18000c6e3  mov     edi, 2
0x18000c6e8  xor     ebx, ebx
0x18000c6ea  jmp     short loc_18000C71C
0x18000c6ec  cmp     dword ptr [r9+128h], 0
0x18000c6f4  mov     ebx, 1
0x18000c6f9  jz      short loc_18000C712
0x18000c6fb  mov     rax, [r9+10h]
0x18000c6ff  lea     edi, [rbx+1]
0x18000c702  mov     ecx, [rax+134h]
0x18000c708  neg     ecx
0x18000c70a  sbb     eax, eax
0x18000c70c  and     edi, eax
0x18000c70e  add     edi, ebx
0x18000c710  jmp     short loc_18000C71C
0x18000c712  mov     rcx, r9; this
0x18000c715  call    ?GetRsopEntryType@CAppInfo@@QEAAJXZ; CAppInfo::GetRsopEntryType(void)
0x18000c71a  mov     edi, eax
0x18000c71c  lea     rcx, [r9+18h]; struct _GUID *
0x18000c720  lea     rdx, [rsp+0B8h+var_78]; unsigned __int16 *
0x18000c725  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000c72a  mov     edx, [rsi]; unsigned __int64
0x18000c72c  lea     rax, [rsp+0B8h+var_78]
0x18000c731  mov     [rsp+0B8h+var_88], ebx
0x18000c735  lea     r8, aRsopApplicatio; "RSOP_ApplicationManagementPolicySetting"...
0x18000c73c  mov     [rsp+0B8h+var_90], rax
0x18000c741  mov     r9d, edi
0x18000c744  lea     rax, [rsp+0B8h+var_78]
0x18000c749  mov     rcx, rbp; unsigned __int16 *
0x18000c74c  mov     [rsp+0B8h+var_98], rax
0x18000c751  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c756  mov     ebx, eax
0x18000c758  jmp     short loc_18000C762
0x18000c75a  mov     [r8], eax
0x18000c75d  mov     ebx, 1
0x18000c762  mov     eax, ebx
0x18000c764  mov     rcx, [rsp+0B8h+var_28]
0x18000c76c  xor     rcx, rsp; StackCookie
0x18000c76f  call    __security_check_cookie
0x18000c774  mov     rbx, [rsp+0B8h+arg_18]
0x18000c77c  add     rsp, 0A0h
0x18000c783  pop     rdi
0x18000c784  pop     rsi
0x18000c785  pop     rbp
0x18000c786  retn
```
