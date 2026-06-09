# VfsMessageRemoveMappings

- ea: `0x140009d44`
- end: `0x140009f8d`
- name: `VfsMessageRemoveMappings`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008650`

## callees

- `0x14000559c`
- `0x140005888`
- `0x1400059e8`
- `0x1400093f0`
- `0x140009b0c`
- `0x140009d44`
- `0x140012828`
- `0x140012880`
- `0x14001295c`
- `0x140012acc`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140009dec`
- `ntoskrnl!RtlLengthSid` at `0x140009dec`

## string_xrefs

- `0x140009e5a`: `VfsMessageRemoveMappings() - Failed to get user context for user: %wZ\n Status: 0x%08X`
- `0x140009f30`: `VfsMessageRemoveMappings() - Failed to get package context for user: %wZ\n PackageId: %wZ\n VersionId: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsMessageRemoveMappings(int a1, int a2)
{
  __int64 v2; // r14
  __int64 v3; // r15
  __int64 v5; // rax
  unsigned int v6; // esi
  __int64 v7; // rax
  struct _UNICODE_STRING *p_GuidString; // rcx
  struct _RTL_AVL_TABLE *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // [rsp+20h] [rbp-B8h]
  PSID Sid; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-90h]
  struct _UNICODE_STRING GuidString; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING v18; // [rsp+60h] [rbp-78h] BYREF
  __int64 v19; // [rsp+70h] [rbp-68h]
  __int64 v20; // [rsp+78h] [rbp-60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-58h] BYREF
  GUID Buffer; // [rsp+90h] [rbp-48h] BYREF
  GUID Guid; // [rsp+A0h] [rbp-38h] BYREF

  v2 = 0;
  v19 = 0;
  v3 = 0;
  v20 = 0;
  Sid = 0;
  Buffer = 0;
  Guid = 0;
  *(_DWORD *)&v18.Length = 0;
  if ( (int)VfsMessageCommonValidate(a1, a2, (unsigned int)&v18, (unsigned int)&Buffer, (__int64)&Sid) < 0 )
    return 3221225485LL;
  if ( Sid )
  {
    RtlLengthSid(Sid);
    *(_QWORD *)&v18.Length = 0;
    v5 = VfsCtxTableElementLookup(&stru_14001F470, Sid);
    *(_QWORD *)&v18.Length = v5;
    if ( v5 )
      v3 = v5;
    v20 = v3;
    v6 = v5 == 0 ? 0xC0000225 : 0;
    v16 = v6;
    if ( !v5 )
    {
      GuidString = 0;
      v7 = ConvertSidToString(Sid, &GuidString);
      LODWORD(v14) = v6;
      LogWrite(1, 0, L"VfsMessageRemoveMappings() - Failed to get user context for user: %wZ\n Status: 0x%08X", v7, v14);
      p_GuidString = &GuidString;
      goto LABEL_8;
    }
    v9 = (struct _RTL_AVL_TABLE *)(v3 + 96);
  }
  else
  {
    v9 = &Table;
  }
  *(_QWORD *)&GuidString.Length = 0;
  v10 = VfsCtxTableElementLookup(v9, &Buffer);
  *(_QWORD *)&GuidString.Length = v10;
  if ( v10 )
    v2 = v10;
  v19 = v2;
  v6 = v10 == 0 ? 0xC0000225 : 0;
  v16 = v6;
  if ( v10 )
  {
    VfsRemoveMappings(v2 + 40);
    goto LABEL_16;
  }
  UnicodeString = 0;
  v18 = 0;
  GuidString = 0;
  v11 = ConvertGuidToString(&Guid, &GuidString);
  v12 = ConvertGuidToString(&Buffer, &v18);
  v13 = ConvertSidToString(Sid, &UnicodeString);
  LogWrite(
    1,
    0,
    L"VfsMessageRemoveMappings() - Failed to get package context for user: %wZ\n"
     " PackageId: %wZ\n"
     " VersionId: %wZ\n"
     " Status: 0x%08X",
    v13,
    v12,
    v11,
    v6);
  FreeSidString(&GuidString);
  FreeSidString(&v18);
  p_GuidString = &UnicodeString;
LABEL_8:
  FreeSidString(p_GuidString);
LABEL_16:
  if ( v2 )
    VfsPkgCtxRelease(v2);
  if ( v3 )
    VfsUserCtxRelease(v3);
  return v6;
}

```

## disassembly

```asm
0x140009d44  mov     r11, rsp
0x140009d47  mov     [r11+18h], rbx
0x140009d4b  mov     [r11+20h], rsi
0x140009d4f  push    rdi
0x140009d50  push    r14
0x140009d52  push    r15
0x140009d54  sub     rsp, 0C0h
0x140009d5b  mov     rax, cs:__security_cookie
0x140009d62  xor     rax, rsp
0x140009d65  mov     [rsp+0D8h+var_28], rax
0x140009d6d  xor     r14d, r14d
0x140009d70  mov     [r11-68h], r14
0x140009d74  xor     r15d, r15d
0x140009d77  mov     [r11-60h], r15
0x140009d7b  mov     [rsp+0D8h+Sid], r14
0x140009d80  xorps   xmm0, xmm0
0x140009d83  movups  xmmword ptr [r11-48h], xmm0
0x140009d88  movups  xmmword ptr [r11-38h], xmm0
0x140009d8d  mov     [r11-78h], r14d
0x140009d91  lea     rax, [rsp+0D8h+Sid]
0x140009d96  mov     [rsp+0D8h+var_B8], rax
0x140009d9b  lea     r9, [r11-48h]
0x140009d9f  lea     r8, [r11-78h]
0x140009da3  call    VfsMessageCommonValidate
0x140009da8  test    eax, eax
0x140009daa  jns     short loc_140009DDB
0x140009dac  mov     eax, 0C000000Dh
0x140009db1  mov     rcx, [rsp+0D8h+var_28]
0x140009db9  xor     rcx, rsp; StackCookie
0x140009dbc  call    __security_check_cookie
0x140009dc1  lea     r11, [rsp+0D8h+var_18]
0x140009dc9  mov     rbx, [r11+30h]
0x140009dcd  mov     rsi, [r11+38h]
0x140009dd1  mov     rsp, r11
0x140009dd4  pop     r15
0x140009dd6  pop     r14
0x140009dd8  pop     rdi
0x140009dd9  retn
0x140009ddb  cmp     [rsp+0D8h+Sid], 0
0x140009de1  jz      loc_140009E80
0x140009de7  mov     rcx, [rsp+0D8h+Sid]; Sid
0x140009dec  call    cs:__imp_RtlLengthSid
0x140009df3  nop     dword ptr [rax+rax+00h]
0x140009df8  mov     qword ptr [rsp+0D8h+var_78.Length], 0
0x140009e01  mov     rdx, [rsp+0D8h+Sid]; Buffer
0x140009e06  lea     rcx, stru_14001F470; Table
0x140009e0d  call    VfsCtxTableElementLookup
0x140009e12  mov     qword ptr [rsp+0D8h+var_78.Length], rax
0x140009e17  test    rax, rax
0x140009e1a  cmovnz  r15, rax
0x140009e1e  mov     [rsp+0D8h+var_60], r15
0x140009e23  mov     rcx, rax
0x140009e26  neg     rcx
0x140009e29  sbb     esi, esi
0x140009e2b  not     esi
0x140009e2d  and     esi, 0C0000225h
0x140009e33  mov     [rsp+0D8h+var_90], esi
0x140009e37  test    rax, rax
0x140009e3a  jnz     short loc_140009E7A
0x140009e3c  xorps   xmm0, xmm0
0x140009e3f  movups  xmmword ptr [rsp+0D8h+GuidString.Length], xmm0
0x140009e44  lea     rdx, [rsp+0D8h+GuidString]; UnicodeString
0x140009e49  mov     rcx, [rsp+0D8h+Sid]; Sid
0x140009e4e  call    ConvertSidToString
0x140009e53  mov     r9, rax
0x140009e56  mov     dword ptr [rsp+0D8h+var_B8], esi
0x140009e5a  lea     r8, aVfsmessageremo; "VfsMessageRemoveMappings() - Failed to "...
0x140009e61  xor     edx, edx
0x140009e63  lea     ecx, [rdx+1]
0x140009e66  call    LogWrite
0x140009e6b  lea     rcx, [rsp+0D8h+GuidString]; UnicodeString
0x140009e70  call    FreeSidString
0x140009e75  jmp     loc_140009F6C
0x140009e7a  lea     rcx, [r15+60h]
0x140009e7e  jmp     short loc_140009E87
0x140009e80  lea     rcx, Table; Table
0x140009e87  mov     qword ptr [rsp+0D8h+GuidString.Length], 0
0x140009e90  lea     rdx, [rsp+0D8h+Buffer]; Buffer
0x140009e98  call    VfsCtxTableElementLookup
0x140009e9d  mov     qword ptr [rsp+0D8h+GuidString.Length], rax
0x140009ea2  test    rax, rax
0x140009ea5  cmovnz  r14, rax
0x140009ea9  mov     [rsp+0D8h+var_68], r14
0x140009eae  mov     rcx, rax
0x140009eb1  neg     rcx
0x140009eb4  sbb     esi, esi
0x140009eb6  not     esi
0x140009eb8  and     esi, 0C0000225h
0x140009ebe  mov     [rsp+0D8h+var_90], esi
0x140009ec2  test    rax, rax
0x140009ec5  jnz     loc_140009F62
0x140009ecb  xorps   xmm0, xmm0
0x140009ece  movups  xmmword ptr [rsp+0D8h+UnicodeString.Length], xmm0
0x140009ed6  xorps   xmm1, xmm1
0x140009ed9  movups  xmmword ptr [rsp+0D8h+var_78.Length], xmm1
0x140009ede  movups  xmmword ptr [rsp+0D8h+GuidString.Length], xmm0
0x140009ee3  lea     rdx, [rsp+0D8h+GuidString]; GuidString
0x140009ee8  lea     rcx, [rsp+0D8h+Guid]; Guid
0x140009ef0  call    ConvertGuidToString
0x140009ef5  mov     rdi, rax
0x140009ef8  lea     rdx, [rsp+0D8h+var_78]; GuidString
0x140009efd  lea     rcx, [rsp+0D8h+Buffer]; Guid
0x140009f05  call    ConvertGuidToString
0x140009f0a  mov     rbx, rax
0x140009f0d  lea     rdx, [rsp+0D8h+UnicodeString]; UnicodeString
0x140009f15  mov     rcx, [rsp+0D8h+Sid]; Sid
0x140009f1a  call    ConvertSidToString
0x140009f1f  mov     r9, rax
0x140009f22  mov     [rsp+0D8h+var_A8], esi
0x140009f26  mov     [rsp+0D8h+var_B0], rdi
0x140009f2b  mov     [rsp+0D8h+var_B8], rbx
0x140009f30  lea     r8, aVfsmessageremo_0; "VfsMessageRemoveMappings() - Failed to "...
0x140009f37  xor     edx, edx
0x140009f39  lea     ecx, [rdx+1]
0x140009f3c  call    LogWrite
0x140009f41  lea     rcx, [rsp+0D8h+GuidString]; UnicodeString
0x140009f46  call    FreeSidString
0x140009f4b  lea     rcx, [rsp+0D8h+var_78]; UnicodeString
0x140009f50  call    FreeSidString
0x140009f55  lea     rcx, [rsp+0D8h+UnicodeString]
0x140009f5d  jmp     loc_140009E70
0x140009f62  lea     rcx, [r14+28h]
0x140009f66  call    VfsRemoveMappings
0x140009f6b  nop
0x140009f6c  test    r14, r14
0x140009f6f  jz      short loc_140009F79
0x140009f71  mov     rcx, r14
0x140009f74  call    VfsPkgCtxRelease
0x140009f79  test    r15, r15
0x140009f7c  jz      short loc_140009F86
0x140009f7e  mov     rcx, r15
0x140009f81  call    VfsUserCtxRelease
0x140009f86  mov     eax, esi
0x140009f88  jmp     loc_140009DB1
0x140014de8  push    rbp
0x140014dea  sub     rsp, 40h
0x140014dee  mov     rbp, rdx
0x140014df1  mov     rcx, [rbp+70h]
0x140014df5  test    rcx, rcx
0x140014df8  jz      short loc_140014E00
0x140014dfa  call    VfsPkgCtxRelease
0x140014dff  nop
0x140014e00  mov     rcx, [rbp+78h]
0x140014e04  test    rcx, rcx
0x140014e07  jz      short loc_140014E0F
0x140014e09  call    VfsUserCtxRelease
0x140014e0e  nop
0x140014e0f  add     rsp, 40h
0x140014e13  pop     rbp
0x140014e14  retn
```
