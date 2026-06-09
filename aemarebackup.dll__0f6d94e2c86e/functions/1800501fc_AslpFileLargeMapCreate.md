# AslpFileLargeMapCreate

- ea: `0x1800501fc`
- end: `0x180050412`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004fd0c`

## callees

- `0x18004c020`
- `0x1800501fc`
- `0x180050418`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x180050333`
- `ntdll!ZwMapViewOfSection` at `0x1800503a7`
- `ntdll!ZwMapViewOfSection` at `0x180050333`
- `ntdll!ZwMapViewOfSection` at `0x1800503a7`
- `ntdll!RtlAllocateHeap` at `0x180050243`
- `ntdll!RtlAllocateHeap` at `0x180050243`
- `ntdll!ZwCreateSection` at `0x1800502b0`
- `ntdll!ZwCreateSection` at `0x1800502b0`

## string_xrefs

- `0x1800502bc`: `ZwCreateSection failed [%x]`
- `0x1800502c9`: `AslpFileLargeMapCreate`

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
0x1800501fc  mov     [rsp-28h+arg_0], rbx
0x180050201  mov     [rsp-28h+arg_8], rsi
0x180050206  push    rbp
0x180050207  push    rdi
0x180050208  push    r13
0x18005020a  push    r14
0x18005020c  push    r15
0x18005020e  mov     rbp, rsp
0x180050211  sub     rsp, 80h
0x180050218  xorps   xmm0, xmm0
0x18005021b  mov     r15, rcx
0x18005021e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180050222  mov     r14, rdx
0x180050225  mov     edx, 8; Flags
0x18005022a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005022e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180050232  mov     rcx, gs:60h
0x18005023b  lea     r8d, [rdx+38h]; Size
0x18005023f  mov     rcx, [rcx+30h]; HeapHandle
0x180050243  call    cs:__imp_RtlAllocateHeap
0x180050249  mov     [rbp+arg_10], rax
0x18005024d  mov     rbx, rax
0x180050250  test    rax, rax
0x180050253  jnz     short loc_18005025F
0x180050255  mov     edi, 0C0000017h
0x18005025a  jmp     loc_1800503E6
0x18005025f  lea     rcx, [rax+8]; SectionHandle
0x180050263  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005026a  mov     rax, [r14]
0x18005026d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180050271  mov     [rsp+80h+FileHandle], rax; FileHandle
0x180050276  xorps   xmm0, xmm0
0x180050279  mov     r13d, 2
0x18005027f  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x180050287  xor     r9d, r9d; MaximumSize
0x18005028a  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18005028f  mov     edx, 0F0005h; DesiredAccess
0x180050294  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18005029c  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800502a3  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800502ab  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800502b0  call    cs:__imp_ZwCreateSection
0x1800502b6  mov     edi, eax
0x1800502b8  test    eax, eax
0x1800502ba  jns     short loc_1800502E3
0x1800502bc  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x1800502c3  mov     r8d, 15Ah
0x1800502c9  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x1800502d0  mov     [rsp+80h+SectionPageProtection], eax
0x1800502d4  mov     ecx, 1
0x1800502d9  call    AslLogCallPrintf
0x1800502de  jmp     loc_1800503E6
0x1800502e3  mov     rcx, [r14+10h]
0x1800502e7  lea     rdx, [rbx+38h]
0x1800502eb  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1800502f0  lea     r8, [rbx+28h]; BaseAddress
0x1800502f4  add     rcx, 0FFFFFFFFFFFFF000h
0x1800502fb  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180050303  movzx   eax, cx
0x180050306  xor     r9d, r9d; ZeroBits
0x180050309  sub     rcx, rax
0x18005030c  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180050311  mov     [rdx], rcx
0x180050314  lea     rax, [rbx+30h]
0x180050318  mov     rcx, [rbx+8]; SectionHandle
0x18005031c  mov     [rsp+80h+FileHandle], rax; ViewSize
0x180050321  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x180050326  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005032a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180050333  call    cs:__imp_ZwMapViewOfSection
0x180050339  mov     edi, eax
0x18005033b  test    eax, eax
0x18005033d  jns     short loc_180050351
0x18005033f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x180050346  mov     r8d, 176h
0x18005034c  jmp     loc_1800502C9
0x180050351  mov     rsi, [r14+10h]
0x180050355  mov     eax, 20000000h
0x18005035a  cmp     rsi, rax
0x18005035d  cmova   rsi, rax
0x180050361  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180050366  lea     rcx, [rbx+18h]
0x18005036a  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180050372  lea     rax, [rbx+20h]
0x180050376  mov     [rcx], rsi
0x180050379  lea     r8, [rbx+10h]; BaseAddress
0x18005037d  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180050382  xor     r9d, r9d; ZeroBits
0x180050385  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18005038a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005038e  mov     qword ptr [rax], 0
0x180050395  mov     rcx, [rbx+8]; SectionHandle
0x180050399  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18005039e  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1800503a7  call    cs:__imp_ZwMapViewOfSection
0x1800503ad  mov     edi, eax
0x1800503af  cmp     eax, 0C0000017h
0x1800503b4  jnz     short loc_1800503C2
0x1800503b6  shr     rsi, 1
0x1800503b9  cmp     rsi, 100000h
0x1800503c0  jnb     short loc_180050361
0x1800503c2  test    eax, eax
0x1800503c4  jns     short loc_1800503D8
0x1800503c6  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x1800503cd  mov     r8d, 1A0h
0x1800503d3  jmp     loc_1800502C9
0x1800503d8  mov     [rbx], r14
0x1800503db  mov     [r15], rbx
0x1800503de  xor     ebx, ebx
0x1800503e0  mov     [rbp+arg_10], rbx
0x1800503e4  xor     edi, edi
0x1800503e6  test    rbx, rbx
0x1800503e9  jz      short loc_1800503F4
0x1800503eb  lea     rcx, [rbp+arg_10]
0x1800503ef  call    AslpFileLargeMapDelete
0x1800503f4  lea     r11, [rsp+80h+var_s0]
0x1800503fc  mov     eax, edi
0x1800503fe  mov     rbx, [r11+30h]
0x180050402  mov     rsi, [r11+38h]
0x180050406  mov     rsp, r11
0x180050409  pop     r15
0x18005040b  pop     r14
0x18005040d  pop     r13
0x18005040f  pop     rdi
0x180050410  pop     rbp
0x180050411  retn
```
