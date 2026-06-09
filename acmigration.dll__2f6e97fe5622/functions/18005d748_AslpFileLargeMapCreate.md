# AslpFileLargeMapCreate

- ea: `0x18005d748`
- end: `0x18005d95e`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005d258`

## callees

- `0x1800543c0`
- `0x18005d748`
- `0x18005d964`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18005d78f`
- `ntdll!RtlAllocateHeap` at `0x18005d78f`
- `ntdll!ZwCreateSection` at `0x18005d7fc`
- `ntdll!ZwCreateSection` at `0x18005d7fc`
- `ntdll!ZwMapViewOfSection` at `0x18005d87f`
- `ntdll!ZwMapViewOfSection` at `0x18005d8f3`
- `ntdll!ZwMapViewOfSection` at `0x18005d87f`
- `ntdll!ZwMapViewOfSection` at `0x18005d8f3`

## string_xrefs

- `0x18005d808`: `ZwCreateSection failed [%x]`
- `0x18005d815`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(void ***a1, HANDLE *a2)
{
  void **Heap; // rax
  void **v5; // rbx
  unsigned int v6; // edi
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // rsi
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-60h]
  HANDLE FileHandle; // [rsp+30h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void **v15; // [rsp+C0h] [rbp+40h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v15 = Heap;
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    goto LABEL_15;
  }
  ObjectAttributes.Length = 48;
  FileHandle = *a2;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwCreateSection(Heap + 1, 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwCreateSection failed [%x]";
    v9 = 346;
LABEL_5:
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(1, "AslpFileLargeMapCreate", v9, v8, *(_QWORD *)SectionPageProtection);
    goto LABEL_15;
  }
  v5[7] = (char *)a2[2] - (unsigned __int16)((unsigned __int16)a2[2] - 4096) - 4096;
  v7 = ZwMapViewOfSection(
         v5[1],
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         v5 + 5,
         0,
         0,
         (PLARGE_INTEGER)v5 + 7,
         (PSIZE_T)v5 + 6,
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
  v10 = (unsigned __int64)a2[2];
  if ( v10 > 0x20000000 )
    v10 = 0x20000000;
  do
  {
    v5[3] = (void *)v10;
    v5[4] = 0;
    v7 = ZwMapViewOfSection(
           v5[1],
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           v5 + 2,
           0,
           0,
           (PLARGE_INTEGER)v5 + 4,
           (PSIZE_T)v5 + 3,
           ViewUnmap,
           0x500000u,
           2u);
    v6 = v7;
    if ( v7 != -1073741801 )
      break;
    v10 >>= 1;
  }
  while ( v10 >= 0x100000 );
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v9 = 416;
    goto LABEL_5;
  }
  *v5 = a2;
  *a1 = v5;
  v5 = 0;
  v15 = 0;
  v6 = 0;
LABEL_15:
  if ( v5 )
    AslpFileLargeMapDelete(&v15);
  return v6;
}

```

## disassembly

```asm
0x18005d748  mov     [rsp-28h+arg_0], rbx
0x18005d74d  mov     [rsp-28h+arg_8], rsi
0x18005d752  push    rbp
0x18005d753  push    rdi
0x18005d754  push    r13
0x18005d756  push    r14
0x18005d758  push    r15
0x18005d75a  mov     rbp, rsp
0x18005d75d  sub     rsp, 80h
0x18005d764  xorps   xmm0, xmm0
0x18005d767  mov     r15, rcx
0x18005d76a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18005d76e  mov     r14, rdx
0x18005d771  mov     edx, 8; Flags
0x18005d776  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005d77a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d77e  mov     rcx, gs:60h
0x18005d787  lea     r8d, [rdx+38h]; Size
0x18005d78b  mov     rcx, [rcx+30h]; HeapHandle
0x18005d78f  call    cs:__imp_RtlAllocateHeap
0x18005d795  mov     [rbp+arg_10], rax
0x18005d799  mov     rbx, rax
0x18005d79c  test    rax, rax
0x18005d79f  jnz     short loc_18005D7AB
0x18005d7a1  mov     edi, 0C0000017h
0x18005d7a6  jmp     loc_18005D932
0x18005d7ab  lea     rcx, [rax+8]; SectionHandle
0x18005d7af  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005d7b6  mov     rax, [r14]
0x18005d7b9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005d7bd  mov     [rsp+80h+FileHandle], rax; FileHandle
0x18005d7c2  xorps   xmm0, xmm0
0x18005d7c5  mov     r13d, 2
0x18005d7cb  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x18005d7d3  xor     r9d, r9d; MaximumSize
0x18005d7d6  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18005d7db  mov     edx, 0F0005h; DesiredAccess
0x18005d7e0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18005d7e8  mov     [rbp+ObjectAttributes.Attributes], 0
0x18005d7ef  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18005d7f7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d7fc  call    cs:__imp_ZwCreateSection
0x18005d802  mov     edi, eax
0x18005d804  test    eax, eax
0x18005d806  jns     short loc_18005D82F
0x18005d808  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x18005d80f  mov     r8d, 15Ah
0x18005d815  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x18005d81c  mov     [rsp+80h+SectionPageProtection], eax
0x18005d820  mov     ecx, 1
0x18005d825  call    AslLogCallPrintf
0x18005d82a  jmp     loc_18005D932
0x18005d82f  mov     rcx, [r14+10h]
0x18005d833  lea     rdx, [rbx+38h]
0x18005d837  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18005d83c  lea     r8, [rbx+28h]; BaseAddress
0x18005d840  add     rcx, 0FFFFFFFFFFFFF000h
0x18005d847  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18005d84f  movzx   eax, cx
0x18005d852  xor     r9d, r9d; ZeroBits
0x18005d855  sub     rcx, rax
0x18005d858  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18005d85d  mov     [rdx], rcx
0x18005d860  lea     rax, [rbx+30h]
0x18005d864  mov     rcx, [rbx+8]; SectionHandle
0x18005d868  mov     [rsp+80h+FileHandle], rax; ViewSize
0x18005d86d  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x18005d872  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005d876  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18005d87f  call    cs:__imp_ZwMapViewOfSection
0x18005d885  mov     edi, eax
0x18005d887  test    eax, eax
0x18005d889  jns     short loc_18005D89D
0x18005d88b  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x18005d892  mov     r8d, 176h
0x18005d898  jmp     loc_18005D815
0x18005d89d  mov     rsi, [r14+10h]
0x18005d8a1  mov     eax, 20000000h
0x18005d8a6  cmp     rsi, rax
0x18005d8a9  cmova   rsi, rax
0x18005d8ad  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18005d8b2  lea     rcx, [rbx+18h]
0x18005d8b6  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18005d8be  lea     rax, [rbx+20h]
0x18005d8c2  mov     [rcx], rsi
0x18005d8c5  lea     r8, [rbx+10h]; BaseAddress
0x18005d8c9  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18005d8ce  xor     r9d, r9d; ZeroBits
0x18005d8d1  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18005d8d6  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005d8da  mov     qword ptr [rax], 0
0x18005d8e1  mov     rcx, [rbx+8]; SectionHandle
0x18005d8e5  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18005d8ea  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18005d8f3  call    cs:__imp_ZwMapViewOfSection
0x18005d8f9  mov     edi, eax
0x18005d8fb  cmp     eax, 0C0000017h
0x18005d900  jnz     short loc_18005D90E
0x18005d902  shr     rsi, 1
0x18005d905  cmp     rsi, 100000h
0x18005d90c  jnb     short loc_18005D8AD
0x18005d90e  test    eax, eax
0x18005d910  jns     short loc_18005D924
0x18005d912  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18005d919  mov     r8d, 1A0h
0x18005d91f  jmp     loc_18005D815
0x18005d924  mov     [rbx], r14
0x18005d927  mov     [r15], rbx
0x18005d92a  xor     ebx, ebx
0x18005d92c  mov     [rbp+arg_10], rbx
0x18005d930  xor     edi, edi
0x18005d932  test    rbx, rbx
0x18005d935  jz      short loc_18005D940
0x18005d937  lea     rcx, [rbp+arg_10]
0x18005d93b  call    AslpFileLargeMapDelete
0x18005d940  lea     r11, [rsp+80h+var_s0]
0x18005d948  mov     eax, edi
0x18005d94a  mov     rbx, [r11+30h]
0x18005d94e  mov     rsi, [r11+38h]
0x18005d952  mov     rsp, r11
0x18005d955  pop     r15
0x18005d957  pop     r14
0x18005d959  pop     r13
0x18005d95b  pop     rdi
0x18005d95c  pop     rbp
0x18005d95d  retn
```
