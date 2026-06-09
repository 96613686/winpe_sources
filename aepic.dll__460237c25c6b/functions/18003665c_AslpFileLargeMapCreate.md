# AslpFileLargeMapCreate

- ea: `0x18003665c`
- end: `0x180036872`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800360e8`

## callees

- `0x1800295dc`
- `0x18003665c`
- `0x180036878`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x180036710`
- `ntdll!ZwCreateSection` at `0x180036710`
- `ntdll!RtlAllocateHeap` at `0x1800366a3`
- `ntdll!RtlAllocateHeap` at `0x1800366a3`
- `ntdll!ZwMapViewOfSection` at `0x180036793`
- `ntdll!ZwMapViewOfSection` at `0x180036807`
- `ntdll!ZwMapViewOfSection` at `0x180036793`
- `ntdll!ZwMapViewOfSection` at `0x180036807`

## string_xrefs

- `0x18003671c`: `ZwCreateSection failed [%x]`
- `0x180036729`: `AslpFileLargeMapCreate`

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
0x18003665c  mov     [rsp-28h+arg_0], rbx
0x180036661  mov     [rsp-28h+arg_8], rsi
0x180036666  push    rbp
0x180036667  push    rdi
0x180036668  push    r13
0x18003666a  push    r14
0x18003666c  push    r15
0x18003666e  mov     rbp, rsp
0x180036671  sub     rsp, 80h
0x180036678  xorps   xmm0, xmm0
0x18003667b  mov     r15, rcx
0x18003667e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180036682  mov     r14, rdx
0x180036685  mov     edx, 8; Flags
0x18003668a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003668e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180036692  mov     rcx, gs:60h
0x18003669b  lea     r8d, [rdx+38h]; Size
0x18003669f  mov     rcx, [rcx+30h]; HeapHandle
0x1800366a3  call    cs:__imp_RtlAllocateHeap
0x1800366a9  mov     [rbp+arg_10], rax
0x1800366ad  mov     rbx, rax
0x1800366b0  test    rax, rax
0x1800366b3  jnz     short loc_1800366BF
0x1800366b5  mov     edi, 0C0000017h
0x1800366ba  jmp     loc_180036846
0x1800366bf  lea     rcx, [rax+8]; SectionHandle
0x1800366c3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800366ca  mov     rax, [r14]
0x1800366cd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800366d1  mov     [rsp+80h+FileHandle], rax; FileHandle
0x1800366d6  xorps   xmm0, xmm0
0x1800366d9  mov     r13d, 2
0x1800366df  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x1800366e7  xor     r9d, r9d; MaximumSize
0x1800366ea  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x1800366ef  mov     edx, 0F0005h; DesiredAccess
0x1800366f4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800366fc  mov     [rbp+ObjectAttributes.Attributes], 0
0x180036703  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18003670b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180036710  call    cs:__imp_ZwCreateSection
0x180036716  mov     edi, eax
0x180036718  test    eax, eax
0x18003671a  jns     short loc_180036743
0x18003671c  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x180036723  mov     r8d, 15Ah
0x180036729  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x180036730  mov     [rsp+80h+SectionPageProtection], eax
0x180036734  mov     ecx, 1
0x180036739  call    AslLogCallPrintf
0x18003673e  jmp     loc_180036846
0x180036743  mov     rcx, [r14+10h]
0x180036747  lea     rdx, [rbx+38h]
0x18003674b  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180036750  lea     r8, [rbx+28h]; BaseAddress
0x180036754  add     rcx, 0FFFFFFFFFFFFF000h
0x18003675b  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180036763  movzx   eax, cx
0x180036766  xor     r9d, r9d; ZeroBits
0x180036769  sub     rcx, rax
0x18003676c  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180036771  mov     [rdx], rcx
0x180036774  lea     rax, [rbx+30h]
0x180036778  mov     rcx, [rbx+8]; SectionHandle
0x18003677c  mov     [rsp+80h+FileHandle], rax; ViewSize
0x180036781  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x180036786  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18003678a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180036793  call    cs:__imp_ZwMapViewOfSection
0x180036799  mov     edi, eax
0x18003679b  test    eax, eax
0x18003679d  jns     short loc_1800367B1
0x18003679f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x1800367a6  mov     r8d, 176h
0x1800367ac  jmp     loc_180036729
0x1800367b1  mov     rsi, [r14+10h]
0x1800367b5  mov     eax, 20000000h
0x1800367ba  cmp     rsi, rax
0x1800367bd  cmova   rsi, rax
0x1800367c1  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1800367c6  lea     rcx, [rbx+18h]
0x1800367ca  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x1800367d2  lea     rax, [rbx+20h]
0x1800367d6  mov     [rcx], rsi
0x1800367d9  lea     r8, [rbx+10h]; BaseAddress
0x1800367dd  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x1800367e2  xor     r9d, r9d; ZeroBits
0x1800367e5  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x1800367ea  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800367ee  mov     qword ptr [rax], 0
0x1800367f5  mov     rcx, [rbx+8]; SectionHandle
0x1800367f9  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x1800367fe  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180036807  call    cs:__imp_ZwMapViewOfSection
0x18003680d  mov     edi, eax
0x18003680f  cmp     eax, 0C0000017h
0x180036814  jnz     short loc_180036822
0x180036816  shr     rsi, 1
0x180036819  cmp     rsi, 100000h
0x180036820  jnb     short loc_1800367C1
0x180036822  test    eax, eax
0x180036824  jns     short loc_180036838
0x180036826  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18003682d  mov     r8d, 1A0h
0x180036833  jmp     loc_180036729
0x180036838  mov     [rbx], r14
0x18003683b  mov     [r15], rbx
0x18003683e  xor     ebx, ebx
0x180036840  mov     [rbp+arg_10], rbx
0x180036844  xor     edi, edi
0x180036846  test    rbx, rbx
0x180036849  jz      short loc_180036854
0x18003684b  lea     rcx, [rbp+arg_10]
0x18003684f  call    AslpFileLargeMapDelete
0x180036854  lea     r11, [rsp+80h+var_s0]
0x18003685c  mov     eax, edi
0x18003685e  mov     rbx, [r11+30h]
0x180036862  mov     rsi, [r11+38h]
0x180036866  mov     rsp, r11
0x180036869  pop     r15
0x18003686b  pop     r14
0x18003686d  pop     r13
0x18003686f  pop     rdi
0x180036870  pop     rbp
0x180036871  retn
```
