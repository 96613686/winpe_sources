# CloneSecurityDescriptorWithOwner

- ea: `0x1800219c4`
- end: `0x180021bbb`
- name: `CloneSecurityDescriptorWithOwner`
- size: `503`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010ba0`
- `0x180013480`

## callees

- `0x18000e000`
- `0x180012b54`
- `0x180018b74`
- `0x1800219c4`
- `0x180022730`
- `0x18002f724`
- `0x180058b30`
- `0x180087dcc`

## import_xrefs

- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180021a5b`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180021b7f`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180021a5b`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180021b7f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180021a87`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180021a87`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180021aa5`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180021ad8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180021aa5`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180021ad8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180021a1a`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180021a1a`

## string_xrefs

- `0x180021b95`: `RtlSetOwnerSecurityDescriptor`
- `0x180021ba7`: `CloneSecurityDescriptorWithOwner`

## pseudocode

```c
__int64 __fastcall CloneSecurityDescriptorWithOwner(void *Src, __int64 a2, PSECURITY_DESCRIPTOR *a3, ULONG *a4)
{
  __int64 v7; // rbx
  PSECURITY_DESCRIPTOR v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  ULONG v14; // eax
  const char *v16; // rdx
  NTSTATUS v17; // eax
  PSECURITY_DESCRIPTOR v18; // [rsp+20h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSD; // [rsp+28h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  ULONG BufferLength; // [rsp+38h] [rbp-18h] BYREF
  ULONG Size; // [rsp+3Ch] [rbp-14h] BYREF
  ULONG Size_4; // [rsp+40h] [rbp-10h] BYREF

  BufferLength = 0;
  SelfRelativeSD = 0;
  v18 = 0;
  SelfRelativeSecurityDescriptor = 0;
  Size = RtlLengthSecurityDescriptor(Src);
  Size_4 = 2 * Size;
  v7 = WfpMemAlloc(2 * Size, 0);
  if ( !v7 )
  {
    v8 = SelfRelativeSD;
    memcpy_0(SelfRelativeSD, Src, Size);
    v9 = RtlSelfRelativeToAbsoluteSD2(SelfRelativeSD, &Size_4);
    v11 = v9;
    if ( !v9 )
    {
      v18 = SelfRelativeSD;
      SelfRelativeSD = 0;
      goto LABEL_4;
    }
    if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -1073741789 )
    {
LABEL_17:
      v16 = "RtlSelfRelativeToAbsoluteSD2";
LABEL_14:
      v7 = WfpReportSysErrorAsNtStatus(v10, v16, v11);
      goto LABEL_9;
    }
    v7 = WfpBufferCopy(Src, Size);
    if ( !v7 )
    {
      v8 = v18;
      v17 = RtlSelfRelativeToAbsoluteSD2(v18, &Size);
      if ( v17 >= 0 )
      {
LABEL_4:
        v12 = RtlSetOwnerSecurityDescriptor(v8, qword_1800B3C40, 0);
        if ( v12 < 0 )
        {
          v11 = (unsigned int)v12;
          v16 = "RtlSetOwnerSecurityDescriptor";
        }
        else
        {
          BufferLength = 0;
          v13 = RtlAbsoluteToSelfRelativeSD(v8, 0, &BufferLength);
          v10 = v13 + 0x80000000;
          if ( (v10 & 0x80000000) != 0 || v13 == -1073741789 )
          {
            v7 = WfpMemAlloc(BufferLength, 0);
            if ( v7 )
              goto LABEL_9;
            v13 = RtlAbsoluteToSelfRelativeSD(v8, SelfRelativeSecurityDescriptor, &BufferLength);
            if ( v13 >= 0 )
            {
              v14 = BufferLength;
              *a3 = SelfRelativeSecurityDescriptor;
              *a4 = v14;
              goto LABEL_9;
            }
          }
          v11 = (unsigned int)v13;
          v16 = "RtlAbsoluteToSelfRelativeSD";
        }
        goto LABEL_14;
      }
      v11 = (unsigned int)v17;
      goto LABEL_17;
    }
  }
LABEL_9:
  WfpMemFree(&v18);
  WfpMemFree(&SelfRelativeSD);
  if ( v7 )
  {
    WfpMemFree(&SelfRelativeSecurityDescriptor);
    WfpReportError(v7, "CloneSecurityDescriptorWithOwner");
  }
  return v7;
}

```

## disassembly

```asm
0x1800219c4  push    rbp
0x1800219c6  push    rbx
0x1800219c7  push    rsi
0x1800219c8  push    rdi
0x1800219c9  push    r13
0x1800219cb  push    r14
0x1800219cd  push    r15
0x1800219cf  mov     rbp, rsp
0x1800219d2  sub     rsp, 50h
0x1800219d6  mov     rax, cs:__security_cookie
0x1800219dd  xor     rax, rsp
0x1800219e0  mov     [rbp+var_8], rax
0x1800219e4  mov     r15, r9
0x1800219e7  mov     dword ptr [rbp+Size], 0
0x1800219ee  mov     r14, r8
0x1800219f1  mov     [rbp+BufferLength], 0
0x1800219f8  mov     rsi, rcx
0x1800219fb  mov     dword ptr [rbp+Size+4], 0
0x180021a02  mov     [rbp+SelfRelativeSD], 0
0x180021a0a  mov     [rbp+var_30], 0
0x180021a12  mov     [rbp+SelfRelativeSecurityDescriptor], 0
0x180021a1a  call    cs:__imp_RtlLengthSecurityDescriptor
0x180021a20  mov     dword ptr [rbp+Size], eax
0x180021a23  lea     r8, [rbp+SelfRelativeSD]
0x180021a27  add     eax, eax
0x180021a29  xor     edx, edx; dwFlags
0x180021a2b  mov     ecx, eax; dwBytes
0x180021a2d  mov     dword ptr [rbp+Size+4], eax
0x180021a30  call    WfpMemAlloc
0x180021a35  mov     rbx, rax
0x180021a38  test    rax, rax
0x180021a3b  jnz     loc_180021AEB
0x180021a41  mov     rdi, [rbp+SelfRelativeSD]
0x180021a45  mov     rdx, rsi; Src
0x180021a48  mov     r8d, dword ptr [rbp+Size]; Size
0x180021a4c  mov     rcx, rdi; void *
0x180021a4f  call    memcpy_0
0x180021a54  lea     rdx, [rbp+Size+4]; BufferSize
0x180021a58  mov     rcx, rdi; SelfRelativeSD
0x180021a5b  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x180021a61  mov     r8d, eax
0x180021a64  mov     r13d, 80000000h
0x180021a6a  test    eax, eax
0x180021a6c  jnz     loc_180021B3F
0x180021a72  mov     [rbp+var_30], rdi
0x180021a76  mov     [rbp+SelfRelativeSD], rbx
0x180021a7a  xor     r8d, r8d; OwnerDefaulted
0x180021a7d  lea     rdx, qword_1800B3C40; Owner
0x180021a84  mov     rcx, rdi; SecurityDescriptor
0x180021a87  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180021a8d  test    eax, eax
0x180021a8f  js      loc_180021B92
0x180021a95  lea     r8, [rbp+BufferLength]; BufferLength
0x180021a99  mov     [rbp+BufferLength], 0
0x180021aa0  xor     edx, edx; SelfRelativeSecurityDescriptor
0x180021aa2  mov     rcx, rdi; AbsoluteSecurityDescriptor
0x180021aa5  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180021aab  lea     ecx, [rax+r13]
0x180021aaf  test    r13d, ecx
0x180021ab2  jz      short loc_180021B24
0x180021ab4  mov     ecx, [rbp+BufferLength]; dwBytes
0x180021ab7  lea     r8, [rbp+SelfRelativeSecurityDescriptor]
0x180021abb  xor     edx, edx; dwFlags
0x180021abd  call    WfpMemAlloc
0x180021ac2  mov     rbx, rax
0x180021ac5  test    rax, rax
0x180021ac8  jnz     short loc_180021AEB
0x180021aca  mov     rsi, [rbp+SelfRelativeSecurityDescriptor]
0x180021ace  lea     r8, [rbp+BufferLength]; BufferLength
0x180021ad2  mov     rdx, rsi; SelfRelativeSecurityDescriptor
0x180021ad5  mov     rcx, rdi; AbsoluteSecurityDescriptor
0x180021ad8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180021ade  test    eax, eax
0x180021ae0  js      short loc_180021B2B
0x180021ae2  mov     eax, [rbp+BufferLength]
0x180021ae5  mov     [r14], rsi
0x180021ae8  mov     [r15], eax
0x180021aeb  lea     rcx, [rbp+var_30]
0x180021aef  call    WfpMemFree
0x180021af4  lea     rcx, [rbp+SelfRelativeSD]
0x180021af8  call    WfpMemFree
0x180021afd  test    rbx, rbx
0x180021b00  jnz     loc_180021B9E
0x180021b06  mov     rax, rbx
0x180021b09  mov     rcx, [rbp+var_8]
0x180021b0d  xor     rcx, rsp; StackCookie
0x180021b10  call    __security_check_cookie
0x180021b15  add     rsp, 50h
0x180021b19  pop     r15
0x180021b1b  pop     r14
0x180021b1d  pop     r13
0x180021b1f  pop     rdi
0x180021b20  pop     rsi
0x180021b21  pop     rbx
0x180021b22  pop     rbp
0x180021b23  retn
0x180021b24  cmp     eax, 0C0000023h
0x180021b29  jz      short loc_180021AB4
0x180021b2b  mov     r8d, eax
0x180021b2e  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x180021b35  call    WfpReportSysErrorAsNtStatus
0x180021b3a  mov     rbx, rax
0x180021b3d  jmp     short loc_180021AEB
0x180021b3f  add     eax, r13d
0x180021b42  test    r13d, eax
0x180021b45  jnz     short loc_180021B59
0x180021b47  cmp     r8d, 0C0000023h
0x180021b4e  jz      short loc_180021B59
0x180021b50  lea     rdx, aRtlselfrelativ; "RtlSelfRelativeToAbsoluteSD2"
0x180021b57  jmp     short loc_180021B35
0x180021b59  mov     edx, dword ptr [rbp+Size]; dwBytes
0x180021b5c  lea     r9, [rbp+var_30]
0x180021b60  mov     rcx, rsi; Src
0x180021b63  call    WfpBufferCopy
0x180021b68  mov     rbx, rax
0x180021b6b  test    rax, rax
0x180021b6e  jnz     loc_180021AEB
0x180021b74  mov     rdi, [rbp+var_30]
0x180021b78  lea     rdx, [rbp+Size]; BufferSize
0x180021b7c  mov     rcx, rdi; SelfRelativeSD
0x180021b7f  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x180021b85  test    eax, eax
0x180021b87  jns     loc_180021A7A
0x180021b8d  mov     r8d, eax
0x180021b90  jmp     short loc_180021B50
0x180021b92  mov     r8d, eax
0x180021b95  lea     rdx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor"
0x180021b9c  jmp     short loc_180021B35
0x180021b9e  lea     rcx, [rbp+SelfRelativeSecurityDescriptor]
0x180021ba2  call    WfpMemFree
0x180021ba7  lea     rdx, aClonesecurityd; "CloneSecurityDescriptorWithOwner"
0x180021bae  mov     rcx, rbx
0x180021bb1  call    WfpReportError
0x180021bb6  jmp     loc_180021B06
```
