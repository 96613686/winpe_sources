# AslpFileLargeMapCreate

- ea: `0x140036b30`
- end: `0x140036da1`
- name: `AslpFileLargeMapCreate`
- size: `625`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140036604`

## callees

- `0x14000451d`
- `0x14000452f`
- `0x140004541`
- `0x140036b30`
- `0x140036da8`
- `0x14003e364`
- `0x14005498c`

## string_xrefs

- `0x140036be0`: `ZwCreateSection failed [%x]`
- `0x140036bef`: `AslpFileLargeMapCreate`
- `0x140036c99`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(__int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  HANDLE v10; // rax
  unsigned __int64 v11; // rsi
  HANDLE v12; // rax
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-49h]
  HANDLE FileHandle; // [rsp+30h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int64 v17; // [rsp+E0h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = AslAlloc((__int64)a1, 80, 1);
  v17 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = -1073741801;
    goto LABEL_20;
  }
  ObjectAttributes.Length = 48;
  FileHandle = *(HANDLE *)a2;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwCreateSection_0((PHANDLE)(v4 + 8), 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwCreateSection failed [%x]";
    v9 = 346;
LABEL_5:
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(1, "AslpFileLargeMapCreate", v9, v8, *(_QWORD *)SectionPageProtection);
    goto LABEL_20;
  }
  *(_QWORD *)(v5 + 64) = *(_QWORD *)(a2 + 16) - 4096LL - (unsigned __int16)(*(_QWORD *)(a2 + 16) - 4096);
  v7 = ZwMapViewOfSection_0(
         *(HANDLE *)(v5 + 8),
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (PVOID *)(v5 + 48),
         0,
         0,
         (PLARGE_INTEGER)(v5 + 64),
         (PSIZE_T)(v5 + 56),
         ViewUnmap,
         0x500000u,
         2u);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v9 = 374;
    goto LABEL_5;
  }
  v10 = MmSecureVirtualMemory_0(*(PVOID *)(v5 + 48), *(_QWORD *)(v5 + 56), 2u);
  *(_QWORD *)(v5 + 72) = v10;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "AslpFileLargeMapCreate", 381, "MmSecureVirtualMemory failed to secure the end view");
LABEL_10:
    v6 = -1073741823;
    goto LABEL_20;
  }
  v11 = *(_QWORD *)(a2 + 16);
  if ( v11 > 0x20000000 )
    v11 = 0x20000000;
  do
  {
    *(_QWORD *)(v5 + 24) = v11;
    *(_QWORD *)(v5 + 32) = 0;
    v7 = ZwMapViewOfSection_0(
           *(HANDLE *)(v5 + 8),
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (PVOID *)(v5 + 16),
           0,
           0,
           (PLARGE_INTEGER)(v5 + 32),
           (PSIZE_T)(v5 + 24),
           ViewUnmap,
           0x500000u,
           2u);
    v6 = v7;
    if ( v7 != -1073741801 )
      break;
    v11 >>= 1;
  }
  while ( v11 >= 0x100000 );
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v9 = 416;
    goto LABEL_5;
  }
  v12 = MmSecureVirtualMemory_0(*(PVOID *)(v5 + 16), *(_QWORD *)(v5 + 24), 2u);
  *(_QWORD *)(v5 + 40) = v12;
  if ( !v12 )
  {
    AslLogCallPrintf(1, "AslpFileLargeMapCreate", 423, "MmSecureVirtualMemory failed to secure the start view");
    goto LABEL_10;
  }
  *(_QWORD *)v5 = a2;
  *a1 = v5;
  v5 = 0;
  v17 = 0;
  v6 = 0;
LABEL_20:
  if ( v5 )
    AslpFileLargeMapDelete(&v17);
  return v6;
}

```

## disassembly

```asm
0x140036b30  push    rbp
0x140036b32  push    rbx
0x140036b33  push    rsi
0x140036b34  push    rdi
0x140036b35  push    r12
0x140036b37  push    r13
0x140036b39  push    r14
0x140036b3b  push    r15
0x140036b3d  lea     rbp, [rsp-1Fh]
0x140036b42  sub     rsp, 88h
0x140036b49  xorps   xmm0, xmm0
0x140036b4c  mov     esi, 1
0x140036b51  mov     r14, rdx
0x140036b54  mov     r8d, esi
0x140036b57  mov     r13, rcx
0x140036b5a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140036b5e  lea     edx, [rsi+4Fh]
0x140036b61  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140036b65  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140036b69  call    AslAlloc
0x140036b6e  mov     [rbp+57h+arg_10], rax
0x140036b72  mov     rdi, rax
0x140036b75  test    rax, rax
0x140036b78  jnz     short loc_140036B84
0x140036b7a  mov     ebx, 0C0000017h
0x140036b7f  jmp     loc_140036D7C
0x140036b84  lea     rcx, [rax+8]; SectionHandle
0x140036b88  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140036b8f  mov     rax, [r14]
0x140036b92  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140036b96  mov     [rsp+0C0h+FileHandle], rax; FileHandle
0x140036b9b  xorps   xmm0, xmm0
0x140036b9e  mov     r15d, 2
0x140036ba4  mov     [rsp+0C0h+AllocationAttributes], 8000000h; AllocationAttributes
0x140036bac  xor     r9d, r9d; MaximumSize
0x140036baf  mov     [rsp+0C0h+SectionPageProtection], r15d; SectionPageProtection
0x140036bb4  mov     edx, 0F0005h; DesiredAccess
0x140036bb9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140036bc1  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140036bc8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140036bd0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140036bd5  call    ZwCreateSection_0
0x140036bda  mov     ebx, eax
0x140036bdc  test    eax, eax
0x140036bde  jns     short loc_140036C04
0x140036be0  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x140036be7  mov     r8d, 15Ah
0x140036bed  mov     ecx, esi
0x140036bef  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140036bf6  mov     [rsp+0C0h+SectionPageProtection], eax
0x140036bfa  call    AslLogCallPrintf
0x140036bff  jmp     loc_140036D7C
0x140036c04  mov     rcx, [r14+10h]
0x140036c08  lea     rdx, [rdi+40h]
0x140036c0c  mov     [rsp+0C0h+Win32Protect], r15d; Win32Protect
0x140036c11  lea     r8, [rdi+30h]; BaseAddress
0x140036c15  add     rcx, 0FFFFFFFFFFFFF000h
0x140036c1c  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140036c24  movzx   eax, cx
0x140036c27  xor     r9d, r9d; ZeroBits
0x140036c2a  sub     rcx, rax
0x140036c2d  mov     [rsp+0C0h+InheritDisposition], r15d; InheritDisposition
0x140036c32  mov     [rdx], rcx
0x140036c35  lea     rax, [rdi+38h]
0x140036c39  mov     rcx, [rdi+8]; SectionHandle
0x140036c3d  mov     [rsp+0C0h+FileHandle], rax; ViewSize
0x140036c42  mov     qword ptr [rsp+0C0h+AllocationAttributes], rdx; SectionOffset
0x140036c47  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140036c4b  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140036c54  call    ZwMapViewOfSection_0
0x140036c59  mov     ebx, eax
0x140036c5b  test    eax, eax
0x140036c5d  jns     short loc_140036C71
0x140036c5f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x140036c66  mov     r8d, 176h
0x140036c6c  jmp     loc_140036BED
0x140036c71  mov     rdx, [rdi+38h]; Size
0x140036c75  mov     r8d, r15d; ProbeMode
0x140036c78  mov     rcx, [rdi+30h]; Address
0x140036c7c  call    MmSecureVirtualMemory_0
0x140036c81  mov     [rdi+48h], rax
0x140036c85  test    rax, rax
0x140036c88  jnz     short loc_140036CAF
0x140036c8a  lea     r9, aMmsecurevirtua; "MmSecureVirtualMemory failed to secure "...
0x140036c91  mov     r8d, 17Dh
0x140036c97  mov     ecx, esi
0x140036c99  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140036ca0  call    AslLogCallPrintf
0x140036ca5  mov     ebx, 0C0000001h
0x140036caa  jmp     loc_140036D7C
0x140036caf  mov     rsi, [r14+10h]
0x140036cb3  mov     eax, 20000000h
0x140036cb8  cmp     rsi, rax
0x140036cbb  cmova   rsi, rax
0x140036cbf  mov     ecx, 2
0x140036cc4  lea     rax, [rdi+20h]
0x140036cc8  mov     [rsp+0C0h+Win32Protect], ecx; Win32Protect
0x140036ccc  lea     r15, [rdi+18h]
0x140036cd0  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140036cd8  lea     r8, [rdi+10h]; BaseAddress
0x140036cdc  mov     [rsp+0C0h+InheritDisposition], ecx; InheritDisposition
0x140036ce0  xor     r9d, r9d; ZeroBits
0x140036ce3  mov     [r15], rsi
0x140036ce6  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140036cea  mov     [rsp+0C0h+FileHandle], r15; ViewSize
0x140036cef  mov     qword ptr [rax], 0
0x140036cf6  mov     rcx, [rdi+8]; SectionHandle
0x140036cfa  mov     qword ptr [rsp+0C0h+AllocationAttributes], rax; SectionOffset
0x140036cff  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140036d08  call    ZwMapViewOfSection_0
0x140036d0d  mov     ebx, eax
0x140036d0f  cmp     eax, 0C0000017h
0x140036d14  jnz     short loc_140036D22
0x140036d16  shr     rsi, 1
0x140036d19  cmp     rsi, 100000h
0x140036d20  jnb     short loc_140036CBF
0x140036d22  test    eax, eax
0x140036d24  jns     short loc_140036D3D
0x140036d26  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x140036d2d  mov     r8d, 1A0h
0x140036d33  mov     ecx, 1
0x140036d38  jmp     loc_140036BEF
0x140036d3d  mov     rdx, [r15]; Size
0x140036d40  mov     r8d, 2; ProbeMode
0x140036d46  mov     rcx, [rdi+10h]; Address
0x140036d4a  call    MmSecureVirtualMemory_0
0x140036d4f  mov     [rdi+28h], rax
0x140036d53  test    rax, rax
0x140036d56  jnz     short loc_140036D6D
0x140036d58  lea     r9, aMmsecurevirtua_0; "MmSecureVirtualMemory failed to secure "...
0x140036d5f  mov     r8d, 1A7h
0x140036d65  lea     ecx, [rax+1]
0x140036d68  jmp     loc_140036C99
0x140036d6d  mov     [rdi], r14
0x140036d70  mov     [r13+0], rdi
0x140036d74  xor     edi, edi
0x140036d76  mov     [rbp+57h+arg_10], rdi
0x140036d7a  xor     ebx, ebx
0x140036d7c  test    rdi, rdi
0x140036d7f  jz      short loc_140036D8A
0x140036d81  lea     rcx, [rbp+57h+arg_10]
0x140036d85  call    AslpFileLargeMapDelete
0x140036d8a  mov     eax, ebx
0x140036d8c  add     rsp, 88h
0x140036d93  pop     r15
0x140036d95  pop     r14
0x140036d97  pop     r13
0x140036d99  pop     r12
0x140036d9b  pop     rdi
0x140036d9c  pop     rsi
0x140036d9d  pop     rbx
0x140036d9e  pop     rbp
0x140036d9f  retn
```
