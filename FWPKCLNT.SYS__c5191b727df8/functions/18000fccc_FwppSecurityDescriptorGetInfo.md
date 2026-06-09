# FwppSecurityDescriptorGetInfo

- ea: `0x18000fccc`
- end: `0x18000fe24`
- name: `FwppSecurityDescriptorGetInfo`
- size: `344`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PACL *Dacl, PACL *Sacl)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e560`
- `0x18000f110`
- `0x180053530`
- `0x180053c00`
- `0x180053ed0`
- `0x180054c20`
- `0x180056130`
- `0x180056640`
- `0x180056f20`
- `0x180057280`
- `0x180057760`
- `0x180057a70`
- `0x180058dc0`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x18000fccc`
- `0x1800203c0`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x18000fdc7`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x18000fdc7`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x18000fd83`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x18000fd83`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x18000fd4f`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x18000fd4f`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x18000fd1d`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x18000fd1d`

## string_xrefs

- `0x18000fd2d`: `RtlGetOwnerSecurityDescriptor`
- `0x18000fd5f`: `RtlGetGroupSecurityDescriptor`
- `0x18000fd93`: `RtlGetDaclSecurityDescriptor`
- `0x18000fdd7`: `RtlGetSaclSecurityDescriptor`
- `0x18000fdee`: `FwppSecurityDescriptorGetInfo`

## pseudocode

```c
__int64 __fastcall FwppSecurityDescriptorGetInfo(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        char a2,
        PSID *a3,
        PSID *a4,
        PACL *Dacl,
        PACL *Sacl)
{
  NTSTATUS OwnerSecurityDescriptor; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned __int8 OwnerDefaulted; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int8 DaclPresent[7]; // [rsp+21h] [rbp-37h] BYREF

  OwnerDefaulted = 0;
  DaclPresent[0] = 0;
  if ( (a2 & 1) != 0 )
  {
    if ( a3 )
    {
      OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, a3, &OwnerDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
      {
        v11 = "RtlGetOwnerSecurityDescriptor";
        goto LABEL_19;
      }
    }
  }
  if ( (a2 & 2) != 0 )
  {
    if ( a4 )
    {
      OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, a4, &OwnerDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
      {
        v11 = "RtlGetGroupSecurityDescriptor";
        goto LABEL_19;
      }
    }
  }
  if ( (a2 & 4) != 0 && Dacl )
  {
    OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, Dacl, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
    {
      v11 = "RtlGetDaclSecurityDescriptor";
      goto LABEL_19;
    }
    if ( !DaclPresent[0] )
      *Dacl = 0;
  }
  v12 = 0;
  if ( (a2 & 8) == 0 || !Sacl )
    return v12;
  OwnerSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, DaclPresent, Sacl, &OwnerDefaulted);
  if ( OwnerSecurityDescriptor < 0 )
  {
    v11 = "RtlGetSaclSecurityDescriptor";
LABEL_19:
    v13 = WfpReportSysErrorAsNtStatus(v10, (int)v11, OwnerSecurityDescriptor);
    v12 = v13;
    if ( v13 )
      WfpReportError(v13, (int)"FwppSecurityDescriptorGetInfo");
    return v12;
  }
  if ( !DaclPresent[0] )
    *Sacl = 0;
  return v12;
}

```

## disassembly

```asm
0x18000fccc  push    rbx
0x18000fcce  push    rbp
0x18000fccf  push    rsi
0x18000fcd0  push    rdi
0x18000fcd1  push    r14
0x18000fcd3  sub     rsp, 30h
0x18000fcd7  mov     rax, cs:__security_cookie
0x18000fcde  xor     rax, rsp
0x18000fce1  mov     [rsp+58h+var_30], rax
0x18000fce6  mov     rbx, [rsp+58h+Dacl]
0x18000fcee  mov     r14, r9
0x18000fcf1  mov     rsi, [rsp+58h+Sacl]
0x18000fcf9  mov     rax, r8
0x18000fcfc  mov     [rsp+58h+OwnerDefaulted], 0
0x18000fd01  mov     edi, edx
0x18000fd03  mov     [rsp+58h+DaclPresent], 0
0x18000fd08  mov     rbp, rcx
0x18000fd0b  test    dl, 1
0x18000fd0e  jz      short loc_18000FD39
0x18000fd10  test    rax, rax
0x18000fd13  jz      short loc_18000FD39
0x18000fd15  lea     r8, [rsp+58h+OwnerDefaulted]; OwnerDefaulted
0x18000fd1a  mov     rdx, rax; Owner
0x18000fd1d  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18000fd24  nop     dword ptr [rax+rax+00h]
0x18000fd29  test    eax, eax
0x18000fd2b  jns     short loc_18000FD39
0x18000fd2d  lea     rdx, aRtlgetownersec; "RtlGetOwnerSecurityDescriptor"
0x18000fd34  jmp     loc_18000FDDE
0x18000fd39  test    dil, 2
0x18000fd3d  jz      short loc_18000FD68
0x18000fd3f  test    r14, r14
0x18000fd42  jz      short loc_18000FD68
0x18000fd44  lea     r8, [rsp+58h+OwnerDefaulted]; GroupDefaulted
0x18000fd49  mov     rdx, r14; Group
0x18000fd4c  mov     rcx, rbp; SecurityDescriptor
0x18000fd4f  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18000fd56  nop     dword ptr [rax+rax+00h]
0x18000fd5b  test    eax, eax
0x18000fd5d  jns     short loc_18000FD68
0x18000fd5f  lea     rdx, aRtlgetgroupsec; "RtlGetGroupSecurityDescriptor"
0x18000fd66  jmp     short loc_18000FDDE
0x18000fd68  test    dil, 4
0x18000fd6c  jz      short loc_18000FDAA
0x18000fd6e  test    rbx, rbx
0x18000fd71  jz      short loc_18000FDAA
0x18000fd73  lea     r9, [rsp+58h+OwnerDefaulted]; DaclDefaulted
0x18000fd78  mov     r8, rbx; Dacl
0x18000fd7b  lea     rdx, [rsp+58h+DaclPresent]; DaclPresent
0x18000fd80  mov     rcx, rbp; SecurityDescriptor
0x18000fd83  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18000fd8a  nop     dword ptr [rax+rax+00h]
0x18000fd8f  test    eax, eax
0x18000fd91  jns     short loc_18000FD9C
0x18000fd93  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x18000fd9a  jmp     short loc_18000FDDE
0x18000fd9c  cmp     [rsp+58h+DaclPresent], 0
0x18000fda1  jnz     short loc_18000FDAA
0x18000fda3  mov     qword ptr [rbx], 0
0x18000fdaa  xor     ebx, ebx
0x18000fdac  test    dil, 8
0x18000fdb0  jz      short loc_18000FE08
0x18000fdb2  test    rsi, rsi
0x18000fdb5  jz      short loc_18000FE08
0x18000fdb7  lea     r9, [rsp+58h+OwnerDefaulted]; SaclDefaulted
0x18000fdbc  mov     r8, rsi; Sacl
0x18000fdbf  lea     rdx, [rsp+58h+DaclPresent]; SaclPresent
0x18000fdc4  mov     rcx, rbp; SecurityDescriptor
0x18000fdc7  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18000fdce  nop     dword ptr [rax+rax+00h]
0x18000fdd3  test    eax, eax
0x18000fdd5  jns     short loc_18000FDFF
0x18000fdd7  lea     rdx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor"
0x18000fdde  mov     r8d, eax
0x18000fde1  call    WfpReportSysErrorAsNtStatus
0x18000fde6  mov     rbx, rax
0x18000fde9  test    rax, rax
0x18000fdec  jz      short loc_18000FE08
0x18000fdee  lea     rdx, aFwppsecurityde; "FwppSecurityDescriptorGetInfo"
0x18000fdf5  mov     rcx, rax
0x18000fdf8  call    WfpReportError
0x18000fdfd  jmp     short loc_18000FE08
0x18000fdff  cmp     [rsp+58h+DaclPresent], bl
0x18000fe03  jnz     short loc_18000FE08
0x18000fe05  mov     [rsi], rbx
0x18000fe08  mov     rax, rbx
0x18000fe0b  mov     rcx, [rsp+58h+var_30]
0x18000fe10  xor     rcx, rsp; StackCookie
0x18000fe13  call    __security_check_cookie
0x18000fe18  add     rsp, 30h
0x18000fe1c  pop     r14
0x18000fe1e  pop     rdi
0x18000fe1f  pop     rsi
0x18000fe20  pop     rbp
0x18000fe21  pop     rbx
0x18000fe22  retn
```
