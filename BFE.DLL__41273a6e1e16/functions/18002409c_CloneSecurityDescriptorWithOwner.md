# CloneSecurityDescriptorWithOwner

- ea: `0x18002409c`
- end: `0x1800242b8`
- name: `CloneSecurityDescriptorWithOwner`
- size: `540`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800115f0`
- `0x180013f60`

## callees

- `0x18000e7e0`
- `0x1800135ac`
- `0x1800197d0`
- `0x18002409c`
- `0x180024e40`
- `0x180031210`
- `0x18005aa60`
- `0x18008ad6c`

## import_xrefs

- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180024139`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180024276`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180024139`
- `ntdll!RtlSelfRelativeToAbsoluteSD2` at `0x180024276`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18002416b`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18002416b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002418f`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800241c8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002418f`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800241c8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800240f2`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800240f2`

## string_xrefs

- `0x180024292`: `RtlSetOwnerSecurityDescriptor`
- `0x1800242a4`: `CloneSecurityDescriptorWithOwner`

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
        v12 = RtlSetOwnerSecurityDescriptor(v8, qword_1800B6CC0, 0);
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
0x18002409c  push    rbp
0x18002409e  push    rbx
0x18002409f  push    rsi
0x1800240a0  push    rdi
0x1800240a1  push    r13
0x1800240a3  push    r14
0x1800240a5  push    r15
0x1800240a7  mov     rbp, rsp
0x1800240aa  sub     rsp, 50h
0x1800240ae  mov     rax, cs:__security_cookie
0x1800240b5  xor     rax, rsp
0x1800240b8  mov     [rbp+var_8], rax
0x1800240bc  mov     r15, r9
0x1800240bf  mov     dword ptr [rbp+Size], 0
0x1800240c6  mov     r14, r8
0x1800240c9  mov     [rbp+BufferLength], 0
0x1800240d0  mov     rsi, rcx
0x1800240d3  mov     dword ptr [rbp+Size+4], 0
0x1800240da  mov     [rbp+SelfRelativeSD], 0
0x1800240e2  mov     [rbp+var_30], 0
0x1800240ea  mov     [rbp+SelfRelativeSecurityDescriptor], 0
0x1800240f2  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800240f9  nop     dword ptr [rax+rax+00h]
0x1800240fe  mov     dword ptr [rbp+Size], eax
0x180024101  lea     r8, [rbp+SelfRelativeSD]
0x180024105  add     eax, eax
0x180024107  xor     edx, edx; dwFlags
0x180024109  mov     ecx, eax; dwBytes
0x18002410b  mov     dword ptr [rbp+Size+4], eax
0x18002410e  call    WfpMemAlloc
0x180024113  mov     rbx, rax
0x180024116  test    rax, rax
0x180024119  jnz     loc_1800241E1
0x18002411f  mov     rdi, [rbp+SelfRelativeSD]
0x180024123  mov     rdx, rsi; Src
0x180024126  mov     r8d, dword ptr [rbp+Size]; Size
0x18002412a  mov     rcx, rdi; void *
0x18002412d  call    memcpy_0
0x180024132  lea     rdx, [rbp+Size+4]; BufferSize
0x180024136  mov     rcx, rdi; SelfRelativeSD
0x180024139  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x180024140  nop     dword ptr [rax+rax+00h]
0x180024145  mov     r8d, eax
0x180024148  mov     r13d, 80000000h
0x18002414e  test    eax, eax
0x180024150  jnz     loc_180024236
0x180024156  mov     [rbp+var_30], rdi
0x18002415a  mov     [rbp+SelfRelativeSD], rbx
0x18002415e  xor     r8d, r8d; OwnerDefaulted
0x180024161  lea     rdx, qword_1800B6CC0; Owner
0x180024168  mov     rcx, rdi; SecurityDescriptor
0x18002416b  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180024172  nop     dword ptr [rax+rax+00h]
0x180024177  test    eax, eax
0x180024179  js      loc_18002428F
0x18002417f  lea     r8, [rbp+BufferLength]; BufferLength
0x180024183  mov     [rbp+BufferLength], 0
0x18002418a  xor     edx, edx; SelfRelativeSecurityDescriptor
0x18002418c  mov     rcx, rdi; AbsoluteSecurityDescriptor
0x18002418f  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180024196  nop     dword ptr [rax+rax+00h]
0x18002419b  lea     ecx, [rax+r13]
0x18002419f  test    r13d, ecx
0x1800241a2  jz      short loc_18002421B
0x1800241a4  mov     ecx, [rbp+BufferLength]; dwBytes
0x1800241a7  lea     r8, [rbp+SelfRelativeSecurityDescriptor]
0x1800241ab  xor     edx, edx; dwFlags
0x1800241ad  call    WfpMemAlloc
0x1800241b2  mov     rbx, rax
0x1800241b5  test    rax, rax
0x1800241b8  jnz     short loc_1800241E1
0x1800241ba  mov     rsi, [rbp+SelfRelativeSecurityDescriptor]
0x1800241be  lea     r8, [rbp+BufferLength]; BufferLength
0x1800241c2  mov     rdx, rsi; SelfRelativeSecurityDescriptor
0x1800241c5  mov     rcx, rdi; AbsoluteSecurityDescriptor
0x1800241c8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1800241cf  nop     dword ptr [rax+rax+00h]
0x1800241d4  test    eax, eax
0x1800241d6  js      short loc_180024222
0x1800241d8  mov     eax, [rbp+BufferLength]
0x1800241db  mov     [r14], rsi
0x1800241de  mov     [r15], eax
0x1800241e1  lea     rcx, [rbp+var_30]
0x1800241e5  call    WfpMemFree
0x1800241ea  lea     rcx, [rbp+SelfRelativeSD]
0x1800241ee  call    WfpMemFree
0x1800241f3  test    rbx, rbx
0x1800241f6  jnz     loc_18002429B
0x1800241fc  mov     rax, rbx
0x1800241ff  mov     rcx, [rbp+var_8]
0x180024203  xor     rcx, rsp; StackCookie
0x180024206  call    __security_check_cookie
0x18002420b  add     rsp, 50h
0x18002420f  pop     r15
0x180024211  pop     r14
0x180024213  pop     r13
0x180024215  pop     rdi
0x180024216  pop     rsi
0x180024217  pop     rbx
0x180024218  pop     rbp
0x180024219  retn
0x18002421b  cmp     eax, 0C0000023h
0x180024220  jz      short loc_1800241A4
0x180024222  mov     r8d, eax
0x180024225  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x18002422c  call    WfpReportSysErrorAsNtStatus
0x180024231  mov     rbx, rax
0x180024234  jmp     short loc_1800241E1
0x180024236  add     eax, r13d
0x180024239  test    r13d, eax
0x18002423c  jnz     short loc_180024250
0x18002423e  cmp     r8d, 0C0000023h
0x180024245  jz      short loc_180024250
0x180024247  lea     rdx, aRtlselfrelativ; "RtlSelfRelativeToAbsoluteSD2"
0x18002424e  jmp     short loc_18002422C
0x180024250  mov     edx, dword ptr [rbp+Size]; dwBytes
0x180024253  lea     r9, [rbp+var_30]
0x180024257  mov     rcx, rsi; Src
0x18002425a  call    WfpBufferCopy
0x18002425f  mov     rbx, rax
0x180024262  test    rax, rax
0x180024265  jnz     loc_1800241E1
0x18002426b  mov     rdi, [rbp+var_30]
0x18002426f  lea     rdx, [rbp+Size]; BufferSize
0x180024273  mov     rcx, rdi; SelfRelativeSD
0x180024276  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x18002427d  nop     dword ptr [rax+rax+00h]
0x180024282  test    eax, eax
0x180024284  jns     loc_18002415E
0x18002428a  mov     r8d, eax
0x18002428d  jmp     short loc_180024247
0x18002428f  mov     r8d, eax
0x180024292  lea     rdx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor"
0x180024299  jmp     short loc_18002422C
0x18002429b  lea     rcx, [rbp+SelfRelativeSecurityDescriptor]
0x18002429f  call    WfpMemFree
0x1800242a4  lea     rdx, aClonesecurityd; "CloneSecurityDescriptorWithOwner"
0x1800242ab  mov     rcx, rbx
0x1800242ae  call    WfpReportError
0x1800242b3  jmp     loc_1800241FC
```
