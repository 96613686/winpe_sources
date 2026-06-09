# AslpFileLargeMapCreate

- ea: `0x18003eb94`
- end: `0x18003edaa`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: `__int64 __fastcall(void ***, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003e620`

## callees

- `0x18000f114`
- `0x18003eb94`
- `0x18003edb0`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x18003eccb`
- `ntdll!ZwMapViewOfSection` at `0x18003ed3f`
- `ntdll!ZwMapViewOfSection` at `0x18003eccb`
- `ntdll!ZwMapViewOfSection` at `0x18003ed3f`
- `ntdll!ZwCreateSection` at `0x18003ec48`
- `ntdll!ZwCreateSection` at `0x18003ec48`
- `ntdll!RtlAllocateHeap` at `0x18003ebdb`
- `ntdll!RtlAllocateHeap` at `0x18003ebdb`

## string_xrefs

- `0x18003ec54`: `ZwCreateSection failed [%x]`
- `0x18003ec61`: `AslpFileLargeMapCreate`

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
0x18003eb94  mov     [rsp-28h+arg_0], rbx
0x18003eb99  mov     [rsp-28h+arg_8], rsi
0x18003eb9e  push    rbp
0x18003eb9f  push    rdi
0x18003eba0  push    r13
0x18003eba2  push    r14
0x18003eba4  push    r15
0x18003eba6  mov     rbp, rsp
0x18003eba9  sub     rsp, 80h
0x18003ebb0  xorps   xmm0, xmm0
0x18003ebb3  mov     r15, rcx
0x18003ebb6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003ebba  mov     r14, rdx
0x18003ebbd  mov     edx, 8; Flags
0x18003ebc2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003ebc6  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ebca  mov     rcx, gs:60h
0x18003ebd3  lea     r8d, [rdx+38h]; Size
0x18003ebd7  mov     rcx, [rcx+30h]; HeapHandle
0x18003ebdb  call    cs:__imp_RtlAllocateHeap
0x18003ebe1  mov     [rbp+arg_10], rax
0x18003ebe5  mov     rbx, rax
0x18003ebe8  test    rax, rax
0x18003ebeb  jnz     short loc_18003EBF7
0x18003ebed  mov     edi, 0C0000017h
0x18003ebf2  jmp     loc_18003ED7E
0x18003ebf7  lea     rcx, [rax+8]; SectionHandle
0x18003ebfb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003ec02  mov     rax, [r14]
0x18003ec05  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003ec09  mov     [rsp+80h+FileHandle], rax; FileHandle
0x18003ec0e  xorps   xmm0, xmm0
0x18003ec11  mov     r13d, 2
0x18003ec17  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x18003ec1f  xor     r9d, r9d; MaximumSize
0x18003ec22  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18003ec27  mov     edx, 0F0005h; DesiredAccess
0x18003ec2c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003ec34  mov     [rbp+ObjectAttributes.Attributes], 0
0x18003ec3b  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18003ec43  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ec48  call    cs:__imp_ZwCreateSection
0x18003ec4e  mov     edi, eax
0x18003ec50  test    eax, eax
0x18003ec52  jns     short loc_18003EC7B
0x18003ec54  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x18003ec5b  mov     r8d, 15Ah
0x18003ec61  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x18003ec68  mov     [rsp+80h+SectionPageProtection], eax
0x18003ec6c  mov     ecx, 1
0x18003ec71  call    AslLogCallPrintf
0x18003ec76  jmp     loc_18003ED7E
0x18003ec7b  mov     rcx, [r14+10h]
0x18003ec7f  lea     rdx, [rbx+38h]
0x18003ec83  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18003ec88  lea     r8, [rbx+28h]; BaseAddress
0x18003ec8c  add     rcx, 0FFFFFFFFFFFFF000h
0x18003ec93  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18003ec9b  movzx   eax, cx
0x18003ec9e  xor     r9d, r9d; ZeroBits
0x18003eca1  sub     rcx, rax
0x18003eca4  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18003eca9  mov     [rdx], rcx
0x18003ecac  lea     rax, [rbx+30h]
0x18003ecb0  mov     rcx, [rbx+8]; SectionHandle
0x18003ecb4  mov     [rsp+80h+FileHandle], rax; ViewSize
0x18003ecb9  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x18003ecbe  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18003ecc2  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18003eccb  call    cs:__imp_ZwMapViewOfSection
0x18003ecd1  mov     edi, eax
0x18003ecd3  test    eax, eax
0x18003ecd5  jns     short loc_18003ECE9
0x18003ecd7  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x18003ecde  mov     r8d, 176h
0x18003ece4  jmp     loc_18003EC61
0x18003ece9  mov     rsi, [r14+10h]
0x18003eced  mov     eax, 20000000h
0x18003ecf2  cmp     rsi, rax
0x18003ecf5  cmova   rsi, rax
0x18003ecf9  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18003ecfe  lea     rcx, [rbx+18h]
0x18003ed02  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18003ed0a  lea     rax, [rbx+20h]
0x18003ed0e  mov     [rcx], rsi
0x18003ed11  lea     r8, [rbx+10h]; BaseAddress
0x18003ed15  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18003ed1a  xor     r9d, r9d; ZeroBits
0x18003ed1d  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18003ed22  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18003ed26  mov     qword ptr [rax], 0
0x18003ed2d  mov     rcx, [rbx+8]; SectionHandle
0x18003ed31  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18003ed36  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18003ed3f  call    cs:__imp_ZwMapViewOfSection
0x18003ed45  mov     edi, eax
0x18003ed47  cmp     eax, 0C0000017h
0x18003ed4c  jnz     short loc_18003ED5A
0x18003ed4e  shr     rsi, 1
0x18003ed51  cmp     rsi, 100000h
0x18003ed58  jnb     short loc_18003ECF9
0x18003ed5a  test    eax, eax
0x18003ed5c  jns     short loc_18003ED70
0x18003ed5e  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18003ed65  mov     r8d, 1A0h
0x18003ed6b  jmp     loc_18003EC61
0x18003ed70  mov     [rbx], r14
0x18003ed73  mov     [r15], rbx
0x18003ed76  xor     ebx, ebx
0x18003ed78  mov     [rbp+arg_10], rbx
0x18003ed7c  xor     edi, edi
0x18003ed7e  test    rbx, rbx
0x18003ed81  jz      short loc_18003ED8C
0x18003ed83  lea     rcx, [rbp+arg_10]
0x18003ed87  call    AslpFileLargeMapDelete
0x18003ed8c  lea     r11, [rsp+80h+var_s0]
0x18003ed94  mov     eax, edi
0x18003ed96  mov     rbx, [r11+30h]
0x18003ed9a  mov     rsi, [r11+38h]
0x18003ed9e  mov     rsp, r11
0x18003eda1  pop     r15
0x18003eda3  pop     r14
0x18003eda5  pop     r13
0x18003eda7  pop     rdi
0x18003eda8  pop     rbp
0x18003eda9  retn
```
