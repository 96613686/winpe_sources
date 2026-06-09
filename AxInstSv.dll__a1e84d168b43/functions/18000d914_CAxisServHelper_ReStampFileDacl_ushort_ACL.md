# CAxisServHelper::ReStampFileDacl(ushort *,_ACL *)

- ea: `0x18000d914`
- end: `0x18000d979`
- name: `?ReStampFileDacl@CAxisServHelper@@QEAAJPEAGPEAU_ACL@@@Z`
- size: `101`
- prototype: `int(CAxisServHelper *__hidden this, unsigned __int16 *, struct _ACL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005ee0`
- `0x18000a2fc`

## callees

- `0x18000725c`
- `0x18000d914`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d938`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d938`

## string_xrefs

- `0x18000d95a`: `Failed to Stamp DACL. Error 0x%x`

## pseudocode

```c
__int64 __fastcall CAxisServHelper::ReStampFileDacl(CAxisServHelper *this, unsigned __int16 *a2, struct _ACL *pDacl)
{
  unsigned int v3; // ebx
  signed int v4; // eax
  PSID psidGroup; // [rsp+20h] [rbp-28h]

  v3 = 0;
  v4 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    else
      v3 = v4;
    LODWORD(psidGroup) = v3;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Failed to Stamp DACL. Error 0x%x", psidGroup);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d914  push    rbx
0x18000d916  sub     rsp, 40h
0x18000d91a  xor     ebx, ebx
0x18000d91c  mov     rcx, rdx; pObjectName
0x18000d91f  mov     [rsp+48h+pSacl], rbx; pSacl
0x18000d924  xor     r9d, r9d; psidOwner
0x18000d927  mov     [rsp+48h+pDacl], r8; pDacl
0x18000d92c  mov     [rsp+48h+psidGroup], rbx; psidGroup
0x18000d931  lea     edx, [rbx+1]; ObjectType
0x18000d934  lea     r8d, [rbx+4]; SecurityInfo
0x18000d938  call    cs:__imp_SetNamedSecurityInfoW
0x18000d93e  test    eax, eax
0x18000d940  jz      short loc_18000D971
0x18000d942  jg      short loc_18000D948
0x18000d944  mov     ebx, eax
0x18000d946  jmp     short loc_18000D951
0x18000d948  movzx   ebx, ax
0x18000d94b  or      ebx, 80070000h
0x18000d951  mov     edx, 8; unsigned int
0x18000d956  mov     dword ptr [rsp+48h+psidGroup], ebx
0x18000d95a  lea     r9, aFailedToStampD; "Failed to Stamp DACL. Error 0x%x"
0x18000d961  lea     rcx, qword_180021AD8; this
0x18000d968  lea     r8d, [rdx-6]; unsigned __int8
0x18000d96c  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000d971  mov     eax, ebx
0x18000d973  add     rsp, 40h
0x18000d977  pop     rbx
0x18000d978  retn
```
