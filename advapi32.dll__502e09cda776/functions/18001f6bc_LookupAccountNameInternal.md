# LookupAccountNameInternal

- ea: `0x18001f6bc`
- end: `0x18001f9cd`
- name: `LookupAccountNameInternal`
- size: `785`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, PSID pDestinationSid@<r8>, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027740`
- `0x180027cb0`

## callees

- `0x18001df64`
- `0x18001e120`
- `0x18001f6bc`
- `0x18001f9d4`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001f826`
- `ntdll!RtlLengthSid` at `0x18001f826`
- `ntdll!RtlCopyUnicodeString` at `0x18001f92d`
- `ntdll!RtlCopyUnicodeString` at `0x18001f92d`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18001f8c0`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18001f8c0`
- `ntdll!RtlInitUnicodeString` at `0x18001f787`
- `ntdll!RtlInitUnicodeString` at `0x18001f95f`
- `ntdll!RtlInitUnicodeString` at `0x18001f787`
- `ntdll!RtlInitUnicodeString` at `0x18001f95f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f8e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f8e8`
- `KERNEL32!LocalFree` at `0x18001f866`
- `KERNEL32!LocalFree` at `0x18001f875`
- `KERNEL32!LocalFree` at `0x18001f978`
- `KERNEL32!LocalFree` at `0x18001f9ab`
- `KERNEL32!LocalFree` at `0x18001f866`
- `KERNEL32!LocalFree` at `0x18001f875`
- `KERNEL32!LocalFree` at `0x18001f978`
- `KERNEL32!LocalFree` at `0x18001f9ab`
- `KERNEL32!BaseSetLastNTError` at `0x18001f84e`
- `KERNEL32!BaseSetLastNTError` at `0x18001f986`
- `KERNEL32!BaseSetLastNTError` at `0x18001f84e`
- `KERNEL32!BaseSetLastNTError` at `0x18001f986`

## pseudocode

```c
__int64 __fastcall LookupAccountNameInternal(
        PCWSTR SourceString,
        PCWSTR a2,
        PSID pDestinationSid,
        DWORD *a4,
        WCHAR *a5,
        ULONG *a6,
        _DWORD *a7,
        int a8)
{
  unsigned int v11; // esi
  struct _UNICODE_STRING *v13; // rcx
  NTSTATUS v14; // eax
  int v15; // ebx
  PSID *v16; // rbx
  __int64 v17; // rax
  ULONG v18; // r9d
  ULONG v19; // eax
  bool v21; // cf
  USHORT v22; // ax
  __int64 v23; // rcx
  ULONG BytesInMultiByteString; // [rsp+50h] [rbp-A1h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-99h] BYREF
  HLOCAL v26; // [rsp+60h] [rbp-91h] BYREF
  int v27; // [rsp+68h] [rbp-89h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp-81h] BYREF
  struct _UNICODE_STRING v29; // [rsp+78h] [rbp-79h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-69h] BYREF
  struct _UNICODE_STRING v31; // [rsp+B8h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-29h] BYREF
  _DWORD v33[4]; // [rsp+D8h] [rbp-19h] BYREF

  v33[2] = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  hMem = 0;
  v11 = 1;
  BytesInMultiByteString = 0;
  v33[0] = 12;
  v13 = 0;
  v33[1] = 2;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  ObjectAttributes.SecurityQualityOfService = v33;
  DestinationString = 0;
  v29 = 0;
  v31 = 0;
  if ( SourceString )
  {
    RtlInitUnicodeString(&v31, SourceString);
    v13 = &v31;
  }
  v14 = LsaOpenPolicy((PLSA_UNICODE_STRING)v13, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v14 < 0 )
  {
    v23 = (unsigned int)v14;
LABEL_19:
    BaseSetLastNTError(v23);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  v27 = 0;
  hMem = 0;
  v26 = 0;
  v15 = LsaICLookupNames_0((__int64)PolicyHandle, 0, 1u, (__int64)&DestinationString, &hMem, &v26, 1, 0, &v27, 0);
  LsaClose(PolicyHandle);
  if ( v15 < 0 )
  {
    if ( v15 == -1073741709 )
    {
      if ( hMem )
        LocalFree(hMem);
      if ( v26 )
        LocalFree(v26);
    }
    v23 = (unsigned int)v15;
    goto LABEL_19;
  }
  v16 = (PSID *)v26;
  v17 = *((int *)v26 + 4);
  if ( a8 )
    BytesInMultiByteString = *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24 * v17) >> 1;
  else
    RtlUnicodeToMultiByteSize(
      &BytesInMultiByteString,
      *(PWCH *)(*((_QWORD *)hMem + 1) + 24 * v17 + 8),
      *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24 * v17));
  v18 = RtlLengthSid(v16[1]);
  v19 = BytesInMultiByteString;
  if ( v18 > *a4 || BytesInMultiByteString + 1 > *a6 )
  {
    *a4 = v18;
    *a6 = v19 + 1;
    BaseSetLastNTError(3221225507LL);
    v11 = 0;
  }
  else
  {
    CopySid(*a4, pDestinationSid, v16[1]);
    v29.Buffer = a5;
    v21 = *a6 < 0x7FFF;
    v29.Length = 0;
    if ( v21 )
      v22 = 2 * *(_WORD *)a6;
    else
      v22 = -2;
    v29.MaximumLength = v22;
    RtlCopyUnicodeString(&v29, (PCUNICODE_STRING)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v16 + 4)));
    v29.Buffer[(unsigned __int64)v29.Length >> 1] = 0;
    *a7 = *(_DWORD *)v16;
    *a6 = BytesInMultiByteString;
  }
  if ( hMem )
    LocalFree(hMem);
  LocalFree(v16);
  return v11;
}

```

## disassembly

```asm
0x18001f6bc  push    rbp
0x18001f6be  push    rbx
0x18001f6bf  push    rsi
0x18001f6c0  push    rdi
0x18001f6c1  push    r12
0x18001f6c3  push    r13
0x18001f6c5  push    r14
0x18001f6c7  push    r15
0x18001f6c9  lea     rbp, [rsp-7]
0x18001f6ce  sub     rsp, 0F8h
0x18001f6d5  mov     rax, cs:__security_cookie
0x18001f6dc  xor     rax, rsp
0x18001f6df  mov     [rbp+3Fh+var_48], rax
0x18001f6e3  mov     r12, [rbp+3Fh+arg_20]
0x18001f6e7  lea     rax, [rbp+3Fh+var_58]
0x18001f6eb  mov     rdi, [rbp+3Fh+arg_28]
0x18001f6ef  xorps   xmm0, xmm0
0x18001f6f2  mov     r13, [rbp+3Fh+arg_30]
0x18001f6f6  mov     r15, r8
0x18001f6f9  xor     r8d, r8d
0x18001f6fc  mov     [rbp+3Fh+var_50], 1
0x18001f703  mov     rbx, rdx
0x18001f706  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18001f70e  mov     rdx, rcx; SourceString
0x18001f711  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], r8
0x18001f715  mov     [rsp+130h+PolicyHandle], r8
0x18001f71a  xorps   xmm1, xmm1
0x18001f71d  mov     [rsp+130h+hMem], r8
0x18001f722  lea     esi, [r8+1]
0x18001f726  mov     [rsp+130h+BytesInMultiByteString], r8d
0x18001f72b  mov     r14, r9
0x18001f72e  mov     [rbp+3Fh+var_58], 0Ch
0x18001f735  mov     ecx, r8d; SystemName
0x18001f738  mov     [rbp+3Fh+var_54], 2
0x18001f73f  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r8
0x18001f743  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r8
0x18001f747  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], r8
0x18001f74b  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], rax
0x18001f74f  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18001f753  movups  xmmword ptr [rbp+3Fh+var_B8.Length], xmm1
0x18001f757  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x18001f75b  test    rdx, rdx
0x18001f75e  jnz     loc_18001F95B
0x18001f764  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x18001f769  mov     r8d, 800h; DesiredAccess
0x18001f76f  lea     rdx, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18001f773  call    LsaOpenPolicy
0x18001f778  test    eax, eax
0x18001f77a  js      loc_18001F974
0x18001f780  mov     rdx, rbx; SourceString
0x18001f783  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18001f787  call    cs:__imp_RtlInitUnicodeString
0x18001f78e  nop     dword ptr [rax+rax+00h]
0x18001f793  xor     ecx, ecx
0x18001f795  lea     rax, [rsp+130h+var_C8]
0x18001f79a  mov     [rsp+130h+var_E8], rcx
0x18001f79f  lea     r9, [rbp+3Fh+DestinationString]
0x18001f7a3  mov     [rsp+130h+var_F0], rax
0x18001f7a8  mov     r8d, esi
0x18001f7ab  mov     [rsp+130h+var_F8], ecx
0x18001f7af  lea     rax, [rsp+130h+var_D0]
0x18001f7b4  mov     [rsp+130h+var_100], esi
0x18001f7b8  xor     edx, edx
0x18001f7ba  mov     [rsp+130h+var_108], rax
0x18001f7bf  lea     rax, [rsp+130h+hMem]
0x18001f7c4  mov     [rsp+130h+var_C8], ecx
0x18001f7c8  mov     [rsp+130h+hMem], rcx
0x18001f7cd  mov     [rsp+130h+var_D0], rcx
0x18001f7d2  mov     rcx, [rsp+130h+PolicyHandle]
0x18001f7d7  mov     [rsp+130h+var_110], rax
0x18001f7dc  call    LsaICLookupNames_0
0x18001f7e1  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x18001f7e6  mov     ebx, eax
0x18001f7e8  call    LsaClose
0x18001f7ed  test    ebx, ebx
0x18001f7ef  js      loc_18001F999
0x18001f7f5  cmp     [rbp+3Fh+arg_38], 0
0x18001f7fc  mov     rbx, [rsp+130h+var_D0]
0x18001f801  movsxd  rax, dword ptr [rbx+10h]
0x18001f805  jz      loc_18001F8A4
0x18001f80b  lea     rdx, [rax+rax*2]
0x18001f80f  mov     rax, [rsp+130h+hMem]
0x18001f814  mov     rcx, [rax+8]
0x18001f818  movzx   eax, word ptr [rcx+rdx*8]
0x18001f81c  shr     eax, 1
0x18001f81e  mov     [rsp+130h+BytesInMultiByteString], eax
0x18001f822  mov     rcx, [rbx+8]; Sid
0x18001f826  call    cs:__imp_RtlLengthSid
0x18001f82d  nop     dword ptr [rax+rax+00h]
0x18001f832  mov     r9d, eax
0x18001f835  mov     eax, [rsp+130h+BytesInMultiByteString]
0x18001f839  cmp     r9d, [r14]
0x18001f83c  jbe     loc_18001F8D1
0x18001f842  inc     eax
0x18001f844  mov     [r14], r9d
0x18001f847  mov     ecx, 0C0000023h
0x18001f84c  mov     [rdi], eax
0x18001f84e  call    cs:__imp_BaseSetLastNTError
0x18001f855  nop     dword ptr [rax+rax+00h]
0x18001f85a  xor     esi, esi
0x18001f85c  mov     rcx, [rsp+130h+hMem]; hMem
0x18001f861  test    rcx, rcx
0x18001f864  jz      short loc_18001F872
0x18001f866  call    cs:__imp_LocalFree
0x18001f86d  nop     dword ptr [rax+rax+00h]
0x18001f872  mov     rcx, rbx; hMem
0x18001f875  call    cs:__imp_LocalFree
0x18001f87c  nop     dword ptr [rax+rax+00h]
0x18001f881  mov     eax, esi
0x18001f883  mov     rcx, [rbp+3Fh+var_48]
0x18001f887  xor     rcx, rsp; StackCookie
0x18001f88a  call    __security_check_cookie
0x18001f88f  add     rsp, 0F8h
0x18001f896  pop     r15
0x18001f898  pop     r14
0x18001f89a  pop     r13
0x18001f89c  pop     r12
0x18001f89e  pop     rdi
0x18001f89f  pop     rsi
0x18001f8a0  pop     rbx
0x18001f8a1  pop     rbp
0x18001f8a2  retn
0x18001f8a4  lea     rcx, [rax+rax*2]
0x18001f8a8  mov     rax, [rsp+130h+hMem]
0x18001f8ad  mov     rdx, [rax+8]
0x18001f8b1  movzx   r8d, word ptr [rdx+rcx*8]; BytesInUnicodeString
0x18001f8b6  mov     rdx, [rdx+rcx*8+8]; UnicodeString
0x18001f8bb  lea     rcx, [rsp+130h+BytesInMultiByteString]; BytesInMultiByteString
0x18001f8c0  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18001f8c7  nop     dword ptr [rax+rax+00h]
0x18001f8cc  jmp     loc_18001F822
0x18001f8d1  lea     r8d, [rax+1]
0x18001f8d5  cmp     r8d, [rdi]
0x18001f8d8  ja      loc_18001F842
0x18001f8de  mov     r8, [rbx+8]; pSourceSid
0x18001f8e2  mov     rdx, r15; pDestinationSid
0x18001f8e5  mov     ecx, [r14]; nDestinationSidLength
0x18001f8e8  call    cs:__imp_CopySid
0x18001f8ef  nop     dword ptr [rax+rax+00h]
0x18001f8f4  xor     eax, eax
0x18001f8f6  mov     [rbp+3Fh+var_B8.Buffer], r12
0x18001f8fa  cmp     dword ptr [rdi], 7FFFh
0x18001f900  mov     [rbp+3Fh+var_B8.Length], ax
0x18001f904  jnb     loc_18001F9C3
0x18001f90a  movzx   eax, word ptr [rdi]
0x18001f90d  add     ax, ax
0x18001f910  mov     [rbp+3Fh+var_B8.MaximumLength], ax
0x18001f914  movsxd  rax, dword ptr [rbx+10h]
0x18001f918  lea     rdx, [rax+rax*2]
0x18001f91c  mov     rax, [rsp+130h+hMem]
0x18001f921  mov     rcx, [rax+8]
0x18001f925  lea     rdx, [rcx+rdx*8]; SourceString
0x18001f929  lea     rcx, [rbp+3Fh+var_B8]; DestinationString
0x18001f92d  call    cs:__imp_RtlCopyUnicodeString
0x18001f934  nop     dword ptr [rax+rax+00h]
0x18001f939  movzx   edx, [rbp+3Fh+var_B8.Length]
0x18001f93d  mov     rax, [rbp+3Fh+var_B8.Buffer]
0x18001f941  shr     rdx, 1
0x18001f944  xor     ecx, ecx
0x18001f946  mov     [rax+rdx*2], cx
0x18001f94a  mov     eax, [rbx]
0x18001f94c  mov     [r13+0], eax
0x18001f950  mov     eax, [rsp+130h+BytesInMultiByteString]
0x18001f954  mov     [rdi], eax
0x18001f956  jmp     loc_18001F85C
0x18001f95b  lea     rcx, [rbp+3Fh+var_78]; DestinationString
0x18001f95f  call    cs:__imp_RtlInitUnicodeString
0x18001f966  nop     dword ptr [rax+rax+00h]
0x18001f96b  lea     rcx, [rbp+3Fh+var_78]
0x18001f96f  jmp     loc_18001F764
0x18001f974  mov     ecx, eax
0x18001f976  jmp     short loc_18001F986
0x18001f978  call    cs:__imp_LocalFree
0x18001f97f  nop     dword ptr [rax+rax+00h]
0x18001f984  mov     ecx, ebx
0x18001f986  call    cs:__imp_BaseSetLastNTError
0x18001f98d  nop     dword ptr [rax+rax+00h]
0x18001f992  xor     eax, eax
0x18001f994  jmp     loc_18001F883
0x18001f999  cmp     ebx, 0C0000073h
0x18001f99f  jnz     short loc_18001F984
0x18001f9a1  mov     rcx, [rsp+130h+hMem]; hMem
0x18001f9a6  test    rcx, rcx
0x18001f9a9  jz      short loc_18001F9B7
0x18001f9ab  call    cs:__imp_LocalFree
0x18001f9b2  nop     dword ptr [rax+rax+00h]
0x18001f9b7  mov     rcx, [rsp+130h+var_D0]; hMem
0x18001f9bc  test    rcx, rcx
0x18001f9bf  jz      short loc_18001F984
0x18001f9c1  jmp     short loc_18001F978
0x18001f9c3  mov     eax, 0FFFEh
0x18001f9c8  jmp     loc_18001F910
```
