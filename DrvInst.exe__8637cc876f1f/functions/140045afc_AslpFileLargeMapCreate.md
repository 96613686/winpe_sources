# AslpFileLargeMapCreate

- ea: `0x140045afc`
- end: `0x140045d12`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: `__int64 __fastcall(void ***, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400455e4`

## callees

- `0x14003bf18`
- `0x140045afc`
- `0x140045d18`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140045b43`
- `ntdll!RtlAllocateHeap` at `0x140045b43`
- `ntdll!ZwCreateSection` at `0x140045bb0`
- `ntdll!ZwCreateSection` at `0x140045bb0`
- `ntdll!ZwMapViewOfSection` at `0x140045c33`
- `ntdll!ZwMapViewOfSection` at `0x140045ca7`
- `ntdll!ZwMapViewOfSection` at `0x140045c33`
- `ntdll!ZwMapViewOfSection` at `0x140045ca7`

## string_xrefs

- `0x140045bbc`: `ZwCreateSection failed [%x]`
- `0x140045bc9`: `AslpFileLargeMapCreate`

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
0x140045afc  mov     [rsp-28h+arg_0], rbx
0x140045b01  mov     [rsp-28h+arg_8], rsi
0x140045b06  push    rbp
0x140045b07  push    rdi
0x140045b08  push    r13
0x140045b0a  push    r14
0x140045b0c  push    r15
0x140045b0e  mov     rbp, rsp
0x140045b11  sub     rsp, 80h
0x140045b18  xorps   xmm0, xmm0
0x140045b1b  mov     r15, rcx
0x140045b1e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140045b22  mov     r14, rdx
0x140045b25  mov     edx, 8; Flags
0x140045b2a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140045b2e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140045b32  mov     rcx, gs:60h
0x140045b3b  lea     r8d, [rdx+38h]; Size
0x140045b3f  mov     rcx, [rcx+30h]; HeapHandle
0x140045b43  call    cs:__imp_RtlAllocateHeap
0x140045b49  mov     [rbp+arg_10], rax
0x140045b4d  mov     rbx, rax
0x140045b50  test    rax, rax
0x140045b53  jnz     short loc_140045B5F
0x140045b55  mov     edi, 0C0000017h
0x140045b5a  jmp     loc_140045CE6
0x140045b5f  lea     rcx, [rax+8]; SectionHandle
0x140045b63  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140045b6a  mov     rax, [r14]
0x140045b6d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140045b71  mov     [rsp+80h+FileHandle], rax; FileHandle
0x140045b76  xorps   xmm0, xmm0
0x140045b79  mov     r13d, 2
0x140045b7f  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x140045b87  xor     r9d, r9d; MaximumSize
0x140045b8a  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x140045b8f  mov     edx, 0F0005h; DesiredAccess
0x140045b94  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140045b9c  mov     [rbp+ObjectAttributes.Attributes], 0
0x140045ba3  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140045bab  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140045bb0  call    cs:__imp_ZwCreateSection
0x140045bb6  mov     edi, eax
0x140045bb8  test    eax, eax
0x140045bba  jns     short loc_140045BE3
0x140045bbc  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x140045bc3  mov     r8d, 15Ah
0x140045bc9  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140045bd0  mov     [rsp+80h+SectionPageProtection], eax
0x140045bd4  mov     ecx, 1
0x140045bd9  call    AslLogCallPrintf
0x140045bde  jmp     loc_140045CE6
0x140045be3  mov     rcx, [r14+10h]
0x140045be7  lea     rdx, [rbx+38h]
0x140045beb  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x140045bf0  lea     r8, [rbx+28h]; BaseAddress
0x140045bf4  add     rcx, 0FFFFFFFFFFFFF000h
0x140045bfb  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x140045c03  movzx   eax, cx
0x140045c06  xor     r9d, r9d; ZeroBits
0x140045c09  sub     rcx, rax
0x140045c0c  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x140045c11  mov     [rdx], rcx
0x140045c14  lea     rax, [rbx+30h]
0x140045c18  mov     rcx, [rbx+8]; SectionHandle
0x140045c1c  mov     [rsp+80h+FileHandle], rax; ViewSize
0x140045c21  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x140045c26  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140045c2a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x140045c33  call    cs:__imp_ZwMapViewOfSection
0x140045c39  mov     edi, eax
0x140045c3b  test    eax, eax
0x140045c3d  jns     short loc_140045C51
0x140045c3f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x140045c46  mov     r8d, 176h
0x140045c4c  jmp     loc_140045BC9
0x140045c51  mov     rsi, [r14+10h]
0x140045c55  mov     eax, 20000000h
0x140045c5a  cmp     rsi, rax
0x140045c5d  cmova   rsi, rax
0x140045c61  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x140045c66  lea     rcx, [rbx+18h]
0x140045c6a  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x140045c72  lea     rax, [rbx+20h]
0x140045c76  mov     [rcx], rsi
0x140045c79  lea     r8, [rbx+10h]; BaseAddress
0x140045c7d  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x140045c82  xor     r9d, r9d; ZeroBits
0x140045c85  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x140045c8a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140045c8e  mov     qword ptr [rax], 0
0x140045c95  mov     rcx, [rbx+8]; SectionHandle
0x140045c99  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x140045c9e  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x140045ca7  call    cs:__imp_ZwMapViewOfSection
0x140045cad  mov     edi, eax
0x140045caf  cmp     eax, 0C0000017h
0x140045cb4  jnz     short loc_140045CC2
0x140045cb6  shr     rsi, 1
0x140045cb9  cmp     rsi, 100000h
0x140045cc0  jnb     short loc_140045C61
0x140045cc2  test    eax, eax
0x140045cc4  jns     short loc_140045CD8
0x140045cc6  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x140045ccd  mov     r8d, 1A0h
0x140045cd3  jmp     loc_140045BC9
0x140045cd8  mov     [rbx], r14
0x140045cdb  mov     [r15], rbx
0x140045cde  xor     ebx, ebx
0x140045ce0  mov     [rbp+arg_10], rbx
0x140045ce4  xor     edi, edi
0x140045ce6  test    rbx, rbx
0x140045ce9  jz      short loc_140045CF4
0x140045ceb  lea     rcx, [rbp+arg_10]
0x140045cef  call    AslpFileLargeMapDelete
0x140045cf4  lea     r11, [rsp+80h+var_s0]
0x140045cfc  mov     eax, edi
0x140045cfe  mov     rbx, [r11+30h]
0x140045d02  mov     rsi, [r11+38h]
0x140045d06  mov     rsp, r11
0x140045d09  pop     r15
0x140045d0b  pop     r14
0x140045d0d  pop     r13
0x140045d0f  pop     rdi
0x140045d10  pop     rbp
0x140045d11  retn
```
