# AslpFileLargeMapCreate

- ea: `0x18006ef74`
- end: `0x18006f18a`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: `__int64 __fastcall(void ***, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006ea00`

## callees

- `0x1800197d4`
- `0x18006ef74`
- `0x18006f190`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x18006f028`
- `ntdll!ZwCreateSection` at `0x18006f028`
- `ntdll!RtlAllocateHeap` at `0x18006efbb`
- `ntdll!RtlAllocateHeap` at `0x18006efbb`
- `ntdll!ZwMapViewOfSection` at `0x18006f0ab`
- `ntdll!ZwMapViewOfSection` at `0x18006f11f`
- `ntdll!ZwMapViewOfSection` at `0x18006f0ab`
- `ntdll!ZwMapViewOfSection` at `0x18006f11f`

## string_xrefs

- `0x18006f034`: `ZwCreateSection failed [%x]`
- `0x18006f041`: `AslpFileLargeMapCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AslpFileLargeMapCreate(void ***a1, HANDLE *a2)
{
  void **Heap; // rax
  void **v5; // rbx
  NTSTATUS v6; // edi
  const char *v7; // r9
  int v8; // r8d
  unsigned __int64 v9; // rsi
  NTSTATUS v10; // eax
  HANDLE FileHandle; // [rsp+30h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void **v14; // [rsp+C0h] [rbp+40h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v14 = Heap;
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
  v6 = ZwCreateSection(Heap + 1, 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  if ( v6 < 0 )
  {
    v7 = "ZwCreateSection failed [%x]";
    v8 = 346;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"AslpFileLargeMapCreate", v8, (_DWORD)v7);
    goto LABEL_15;
  }
  v5[7] = (char *)a2[2] - (unsigned __int16)((unsigned __int16)a2[2] - 4096) - 4096;
  v6 = ZwMapViewOfSection(
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
  if ( v6 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v8 = 374;
    goto LABEL_5;
  }
  v9 = (unsigned __int64)a2[2];
  if ( v9 > 0x20000000 )
    v9 = 0x20000000;
  do
  {
    v5[3] = (void *)v9;
    v5[4] = 0;
    v10 = ZwMapViewOfSection(
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
    v6 = v10;
    if ( v10 != -1073741801 )
      break;
    v9 >>= 1;
  }
  while ( v9 >= 0x100000 );
  if ( v10 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v8 = 416;
    goto LABEL_5;
  }
  *v5 = a2;
  *a1 = v5;
  v5 = 0;
  v14 = 0;
  v6 = 0;
LABEL_15:
  if ( v5 )
    AslpFileLargeMapDelete(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006ef74  mov     [rsp-28h+arg_0], rbx
0x18006ef79  mov     [rsp-28h+arg_8], rsi
0x18006ef7e  push    rbp
0x18006ef7f  push    rdi
0x18006ef80  push    r13
0x18006ef82  push    r14
0x18006ef84  push    r15
0x18006ef86  mov     rbp, rsp
0x18006ef89  sub     rsp, 80h
0x18006ef90  xorps   xmm0, xmm0
0x18006ef93  mov     r15, rcx
0x18006ef96  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006ef9a  mov     r14, rdx
0x18006ef9d  mov     edx, 8; Flags
0x18006efa2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006efa6  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006efaa  mov     rcx, gs:60h
0x18006efb3  lea     r8d, [rdx+38h]; Size
0x18006efb7  mov     rcx, [rcx+30h]; HeapHandle
0x18006efbb  call    cs:__imp_RtlAllocateHeap
0x18006efc1  mov     [rbp+arg_10], rax
0x18006efc5  mov     rbx, rax
0x18006efc8  test    rax, rax
0x18006efcb  jnz     short loc_18006EFD7
0x18006efcd  mov     edi, 0C0000017h
0x18006efd2  jmp     loc_18006F15E
0x18006efd7  lea     rcx, [rax+8]; SectionHandle
0x18006efdb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006efe2  mov     rax, [r14]
0x18006efe5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006efe9  mov     [rsp+80h+FileHandle], rax; FileHandle
0x18006efee  xorps   xmm0, xmm0
0x18006eff1  mov     r13d, 2
0x18006eff7  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x18006efff  xor     r9d, r9d; MaximumSize
0x18006f002  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18006f007  mov     edx, 0F0005h; DesiredAccess
0x18006f00c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006f014  mov     [rbp+ObjectAttributes.Attributes], 0
0x18006f01b  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18006f023  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f028  call    cs:__imp_ZwCreateSection
0x18006f02e  mov     edi, eax
0x18006f030  test    eax, eax
0x18006f032  jns     short loc_18006F05B
0x18006f034  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x18006f03b  mov     r8d, 15Ah
0x18006f041  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x18006f048  mov     [rsp+80h+SectionPageProtection], eax
0x18006f04c  mov     ecx, 1
0x18006f051  call    AslLogCallPrintf
0x18006f056  jmp     loc_18006F15E
0x18006f05b  mov     rcx, [r14+10h]
0x18006f05f  lea     rdx, [rbx+38h]
0x18006f063  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18006f068  lea     r8, [rbx+28h]; BaseAddress
0x18006f06c  add     rcx, 0FFFFFFFFFFFFF000h
0x18006f073  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18006f07b  movzx   eax, cx
0x18006f07e  xor     r9d, r9d; ZeroBits
0x18006f081  sub     rcx, rax
0x18006f084  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18006f089  mov     [rdx], rcx
0x18006f08c  lea     rax, [rbx+30h]
0x18006f090  mov     rcx, [rbx+8]; SectionHandle
0x18006f094  mov     [rsp+80h+FileHandle], rax; ViewSize
0x18006f099  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x18006f09e  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006f0a2  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18006f0ab  call    cs:__imp_ZwMapViewOfSection
0x18006f0b1  mov     edi, eax
0x18006f0b3  test    eax, eax
0x18006f0b5  jns     short loc_18006F0C9
0x18006f0b7  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x18006f0be  mov     r8d, 176h
0x18006f0c4  jmp     loc_18006F041
0x18006f0c9  mov     rsi, [r14+10h]
0x18006f0cd  mov     eax, 20000000h
0x18006f0d2  cmp     rsi, rax
0x18006f0d5  cmova   rsi, rax
0x18006f0d9  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18006f0de  lea     rcx, [rbx+18h]
0x18006f0e2  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18006f0ea  lea     rax, [rbx+20h]
0x18006f0ee  mov     [rcx], rsi
0x18006f0f1  lea     r8, [rbx+10h]; BaseAddress
0x18006f0f5  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18006f0fa  xor     r9d, r9d; ZeroBits
0x18006f0fd  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18006f102  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006f106  mov     qword ptr [rax], 0
0x18006f10d  mov     rcx, [rbx+8]; SectionHandle
0x18006f111  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18006f116  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18006f11f  call    cs:__imp_ZwMapViewOfSection
0x18006f125  mov     edi, eax
0x18006f127  cmp     eax, 0C0000017h
0x18006f12c  jnz     short loc_18006F13A
0x18006f12e  shr     rsi, 1
0x18006f131  cmp     rsi, 100000h
0x18006f138  jnb     short loc_18006F0D9
0x18006f13a  test    eax, eax
0x18006f13c  jns     short loc_18006F150
0x18006f13e  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18006f145  mov     r8d, 1A0h
0x18006f14b  jmp     loc_18006F041
0x18006f150  mov     [rbx], r14
0x18006f153  mov     [r15], rbx
0x18006f156  xor     ebx, ebx
0x18006f158  mov     [rbp+arg_10], rbx
0x18006f15c  xor     edi, edi
0x18006f15e  test    rbx, rbx
0x18006f161  jz      short loc_18006F16C
0x18006f163  lea     rcx, [rbp+arg_10]
0x18006f167  call    AslpFileLargeMapDelete
0x18006f16c  lea     r11, [rsp+80h+var_s0]
0x18006f174  mov     eax, edi
0x18006f176  mov     rbx, [r11+30h]
0x18006f17a  mov     rsi, [r11+38h]
0x18006f17e  mov     rsp, r11
0x18006f181  pop     r15
0x18006f183  pop     r14
0x18006f185  pop     r13
0x18006f187  pop     rdi
0x18006f188  pop     rbp
0x18006f189  retn
```
