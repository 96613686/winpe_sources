# ATL::AtlGetDacl(ushort const *,_SE_OBJECT_TYPE,ATL::CDacl *)

- ea: `0x180030650`
- end: `0x18003070a`
- name: `?AtlGetDacl@ATL@@YA_NPEBGW4_SE_OBJECT_TYPE@@PEAVCDacl@1@@Z`
- size: `186`
- prototype: `bool(const unsigned __int16 *, enum _SE_OBJECT_TYPE, struct ATL::CDacl *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002da4c`

## callees

- `0x180030260`
- `0x180030650`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800306f9`
- `KERNEL32!LocalFree` at `0x1800306f9`
- `KERNEL32!SetLastError` at `0x1800306af`
- `KERNEL32!SetLastError` at `0x1800306af`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800306a3`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800306a3`

## pseudocode

```c
bool __fastcall ATL::AtlGetDacl(const unsigned __int16 *a1, enum _SE_OBJECT_TYPE a2, struct ATL::CDacl *a3)
{
  DWORD NamedSecurityInfoW; // eax
  struct _ACL *v6; // rdi
  struct _ACL *v7; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF

  if ( !a1 || !a3 )
    return 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &v7, 0, &hMem);
  if ( NamedSecurityInfoW )
  {
    SetLastError(NamedSecurityInfoW);
    return 0;
  }
  v6 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(struct ATL::CDacl *))(*(_QWORD *)a3 + 16LL))(a3);
    ATL::CDacl::Copy(a3, v6);
  }
  LocalFree(hMem);
  return v7 != 0;
}

```

## disassembly

```asm
0x180030650  mov     r11, rsp
0x180030653  mov     [r11+10h], rbx
0x180030657  push    rdi
0x180030658  sub     rsp, 60h
0x18003065c  mov     rax, cs:__security_cookie
0x180030663  xor     rax, rsp
0x180030666  mov     [rsp+68h+var_18], rax
0x18003066b  mov     rbx, r8
0x18003066e  test    rcx, rcx
0x180030671  jz      short loc_1800306B5
0x180030673  test    rbx, rbx
0x180030676  jz      short loc_1800306B5
0x180030678  lea     rax, [r11-20h]
0x18003067c  xor     r9d, r9d; ppsidOwner
0x18003067f  mov     [r11-30h], rax
0x180030683  lea     rax, [r11-28h]
0x180030687  mov     qword ptr [r11-38h], 0
0x18003068f  mov     [r11-40h], rax
0x180030693  lea     edx, [r9+1]; ObjectType
0x180030697  mov     qword ptr [r11-48h], 0
0x18003069f  lea     r8d, [r9+4]; SecurityInfo
0x1800306a3  call    cs:__imp_GetNamedSecurityInfoW
0x1800306a9  test    eax, eax
0x1800306ab  jz      short loc_1800306CF
0x1800306ad  mov     ecx, eax; dwErrCode
0x1800306af  call    cs:__imp_SetLastError
0x1800306b5  xor     al, al
0x1800306b7  mov     rcx, [rsp+68h+var_18]
0x1800306bc  xor     rcx, rsp; StackCookie
0x1800306bf  call    __security_check_cookie
0x1800306c4  mov     rbx, [rsp+68h+arg_8]
0x1800306c9  add     rsp, 60h
0x1800306cd  pop     rdi
0x1800306ce  retn
0x1800306cf  mov     rdi, [rsp+68h+var_28]
0x1800306d4  test    rdi, rdi
0x1800306d7  jz      short loc_1800306F4
0x1800306d9  mov     rax, [rbx]
0x1800306dc  mov     rcx, rbx
0x1800306df  mov     rax, [rax+10h]
0x1800306e3  call    cs:__guard_dispatch_icall_fptr
0x1800306e9  mov     rdx, rdi; struct _ACL *
0x1800306ec  mov     rcx, rbx; this
0x1800306ef  call    ?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z; ATL::CDacl::Copy(_ACL const &)
0x1800306f4  mov     rcx, [rsp+68h+hMem]; hMem
0x1800306f9  call    cs:__imp_LocalFree
0x1800306ff  cmp     [rsp+68h+var_28], 0
0x180030705  setnz   al
0x180030708  jmp     short loc_1800306B7
```
