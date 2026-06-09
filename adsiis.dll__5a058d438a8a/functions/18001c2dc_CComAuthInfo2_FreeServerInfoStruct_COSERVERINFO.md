# CComAuthInfo2::FreeServerInfoStruct(_COSERVERINFO *)

- ea: `0x18001c2dc`
- end: `0x18001c392`
- name: `?FreeServerInfoStruct@CComAuthInfo2@@SAXPEAU_COSERVERINFO@@@Z`
- size: `182`
- prototype: `void __fastcall(struct _COSERVERINFO *Block)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013430`
- `0x18001a578`
- `0x18001bf94`

## callees

- `0x1800010f0`
- `0x18001c2dc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001c30b`
- `KERNEL32!LocalFree` at `0x18001c331`
- `KERNEL32!LocalFree` at `0x18001c358`
- `KERNEL32!LocalFree` at `0x18001c30b`
- `KERNEL32!LocalFree` at `0x18001c331`
- `KERNEL32!LocalFree` at `0x18001c358`

## pseudocode

```c
void __fastcall CComAuthInfo2::FreeServerInfoStruct(struct _COSERVERINFO *Block)
{
  COAUTHINFO *pAuthInfo; // rax
  void **p_User; // rcx
  void *v4; // rcx
  USHORT *Domain; // rcx
  USHORT *Password; // rcx

  if ( Block )
  {
    pAuthInfo = Block->pAuthInfo;
    if ( pAuthInfo )
    {
      p_User = (void **)&pAuthInfo->pAuthIdentityData->User;
      if ( p_User )
      {
        v4 = *p_User;
        if ( v4 )
        {
          LocalFree(v4);
          Block->pAuthInfo->pAuthIdentityData->User = 0;
        }
        Domain = Block->pAuthInfo->pAuthIdentityData->Domain;
        if ( Domain )
        {
          LocalFree(Domain);
          Block->pAuthInfo->pAuthIdentityData->Domain = 0;
        }
        Password = Block->pAuthInfo->pAuthIdentityData->Password;
        if ( Password )
        {
          LocalFree(Password);
          Block->pAuthInfo->pAuthIdentityData->Password = 0;
        }
        operator delete(Block->pAuthInfo->pAuthIdentityData);
      }
      operator delete(Block->pAuthInfo);
    }
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x18001c2dc  test    rcx, rcx
0x18001c2df  jz      locret_18001C391
0x18001c2e5  push    rbx
0x18001c2e6  sub     rsp, 20h
0x18001c2ea  mov     rax, [rcx+10h]
0x18001c2ee  mov     rbx, rcx
0x18001c2f1  test    rax, rax
0x18001c2f4  jz      loc_18001C384
0x18001c2fa  mov     rcx, [rax+18h]
0x18001c2fe  test    rcx, rcx
0x18001c301  jz      short loc_18001C37B
0x18001c303  mov     rcx, [rcx]; hMem
0x18001c306  test    rcx, rcx
0x18001c309  jz      short loc_18001C320
0x18001c30b  call    cs:__imp_LocalFree
0x18001c311  mov     rax, [rbx+10h]
0x18001c315  mov     rcx, [rax+18h]
0x18001c319  mov     qword ptr [rcx], 0
0x18001c320  mov     rax, [rbx+10h]
0x18001c324  mov     rcx, [rax+18h]
0x18001c328  mov     rcx, [rcx+10h]; hMem
0x18001c32c  test    rcx, rcx
0x18001c32f  jz      short loc_18001C347
0x18001c331  call    cs:__imp_LocalFree
0x18001c337  mov     rax, [rbx+10h]
0x18001c33b  mov     rcx, [rax+18h]
0x18001c33f  mov     qword ptr [rcx+10h], 0
0x18001c347  mov     rax, [rbx+10h]
0x18001c34b  mov     rcx, [rax+18h]
0x18001c34f  mov     rcx, [rcx+20h]; hMem
0x18001c353  test    rcx, rcx
0x18001c356  jz      short loc_18001C36E
0x18001c358  call    cs:__imp_LocalFree
0x18001c35e  mov     rax, [rbx+10h]
0x18001c362  mov     rcx, [rax+18h]
0x18001c366  mov     qword ptr [rcx+20h], 0
0x18001c36e  mov     rcx, [rbx+10h]
0x18001c372  mov     rcx, [rcx+18h]; Block
0x18001c376  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c37b  mov     rcx, [rbx+10h]; Block
0x18001c37f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c384  mov     rcx, rbx; Block
0x18001c387  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c38c  add     rsp, 20h
0x18001c390  pop     rbx
0x18001c391  retn
```
