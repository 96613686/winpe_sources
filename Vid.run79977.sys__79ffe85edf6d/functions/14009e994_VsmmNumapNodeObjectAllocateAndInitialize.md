# VsmmNumapNodeObjectAllocateAndInitialize

- ea: `0x14009e994`
- end: `0x14009eaf5`
- name: `VsmmNumapNodeObjectAllocateAndInitialize`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14009f2d4`

## callees

- `0x140021800`
- `0x1400386a0`
- `0x140076e34`
- `0x14009e054`
- `0x14009e994`
- `0x14009eafc`
- `0x1400f04a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009ead9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009ead9`
- `ntoskrnl!ExAllocatePool2` at `0x14009e9f8`
- `ntoskrnl!ExAllocatePool2` at `0x14009e9f8`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009ea85`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009ea85`

## pseudocode

```c
__int64 __fastcall VsmmNumapNodeObjectAllocateAndInitialize(__int64 a1, unsigned __int8 a2, __int64 a3)
{
  __int64 v3; // rsi
  int i; // edi
  NTSTATUS WorkspaceSize; // ebx
  __int64 Pool2; // rax
  __int64 v8; // rdi
  __int64 j; // rbx
  _BYTE v11[12]; // [rsp+8Ch] [rbp+14h] BYREF

  v3 = a2;
  *(_QWORD *)&v11[4] = 0;
  for ( i = 1; i < 3; ++i )
  {
    WorkspaceSize = VmCompressGetWorkspaceSize(i != 1, (ULONG *)&v11[4 * i], a3);
    if ( WorkspaceSize < 0 )
      return (unsigned int)WorkspaceSize;
  }
  Pool2 = ExAllocatePool2(64, 432, 1833788502);
  v8 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1634563406;
    *(_BYTE *)(Pool2 + 4) = v3;
    VidStatisticsDataInitialize(Pool2 + 72);
    for ( j = 1; j != 3; ++j )
      ExInitializeLookasideListEx(
        (PLOOKASIDE_LIST_EX)(v8 + 224 + 96 * (j - 1)),
        0,
        0,
        PagedPool,
        0,
        *(unsigned int *)&v11[4 * j],
        0x6D4D6456u,
        0);
    WorkspaceSize = VidStatisticsDataSetup((PFAST_MUTEX)(v8 + 72));
    if ( WorkspaceSize < 0 || (WorkspaceSize = VsmmNumapBackingSetup(v8), WorkspaceSize < 0) )
    {
      VsmmNumapNodeObjectTeardown(v8);
      ExFreePoolWithTag((PVOID)v8, 0x6D4D6456u);
    }
    else
    {
      WorkspaceSize = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 264) + 8 * v3) = v8;
    }
  }
  else
  {
    WorkspaceSize = -1073741670;
    VidTraceErrorInternal0("VsmmNumapNodeObjectAllocateAndInitialize", "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c", 2082);
  }
  return (unsigned int)WorkspaceSize;
}

```

## disassembly

```asm
0x14009e994  mov     rax, rsp
0x14009e997  push    rbx
0x14009e998  push    rbp
0x14009e999  push    rsi
0x14009e99a  push    rdi
0x14009e99b  push    r14
0x14009e99d  push    r15
0x14009e99f  sub     rsp, 48h
0x14009e9a3  movzx   esi, dl
0x14009e9a6  mov     r14, rcx
0x14009e9a9  mov     qword ptr [rax+18h], 0
0x14009e9b1  mov     edi, 1
0x14009e9b6  cmp     edi, 3
0x14009e9b9  jge     short loc_14009E9E8
0x14009e9bb  xor     ecx, ecx
0x14009e9bd  lea     eax, [rdi-1]
0x14009e9c0  movsxd  rdx, eax
0x14009e9c3  cmp     edi, 1
0x14009e9c6  lea     rax, [rsp+78h+arg_C+4]
0x14009e9ce  setnz   cl
0x14009e9d1  lea     rdx, [rax+rdx*4]
0x14009e9d5  call    VmCompressGetWorkspaceSize
0x14009e9da  mov     ebx, eax
0x14009e9dc  test    eax, eax
0x14009e9de  js      loc_14009EAE5
0x14009e9e4  inc     edi
0x14009e9e6  jmp     short loc_14009E9B6
0x14009e9e8  mov     edx, 1B0h
0x14009e9ed  mov     ecx, 40h ; '@'
0x14009e9f2  mov     r8d, 6D4D6456h
0x14009e9f8  call    cs:__imp_ExAllocatePool2
0x14009e9ff  nop     dword ptr [rax+rax+00h]
0x14009ea04  mov     rdi, rax
0x14009ea07  test    rax, rax
0x14009ea0a  jnz     short loc_14009EA2F
0x14009ea0c  mov     ebx, 0C000009Ah
0x14009ea11  mov     r8d, 822h
0x14009ea17  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009ea1e  lea     rcx, aVsmmnumapnodeo_0; "VsmmNumapNodeObjectAllocateAndInitializ"...
0x14009ea25  call    VidTraceErrorInternal0
0x14009ea2a  jmp     loc_14009EAE5
0x14009ea2f  lea     rcx, [rax+48h]
0x14009ea33  mov     dword ptr [rax], 616D754Eh
0x14009ea39  mov     [rax+4], sil
0x14009ea3d  call    VidStatisticsDataInitialize
0x14009ea42  lea     r15, [rdi+0E0h]
0x14009ea49  mov     ebx, 1
0x14009ea4e  mov     edx, dword ptr [rsp+rbx*4+78h+arg_C]
0x14009ea55  lea     rcx, [rbx-1]
0x14009ea59  xor     eax, eax
0x14009ea5b  lea     rcx, [rcx+rcx*2]
0x14009ea5f  mov     [rsp+78h+Depth], ax; Depth
0x14009ea64  xor     r8d, r8d; Free
0x14009ea67  shl     rcx, 5
0x14009ea6b  mov     [rsp+78h+Tag], 6D4D6456h; Tag
0x14009ea73  add     rcx, r15; Lookaside
0x14009ea76  mov     [rsp+78h+Size], rdx; Size
0x14009ea7b  lea     r9d, [rax+1]; PoolType
0x14009ea7f  xor     edx, edx; Allocate
0x14009ea81  mov     [rsp+78h+Flags], eax; Flags
0x14009ea85  call    cs:__imp_ExInitializeLookasideListEx
0x14009ea8c  nop     dword ptr [rax+rax+00h]
0x14009ea91  inc     rbx
0x14009ea94  cmp     rbx, 3
0x14009ea98  jnz     short loc_14009EA4E
0x14009ea9a  lea     edx, [rbx+0Ah]
0x14009ea9d  lea     rcx, [rdi+48h]; FastMutex
0x14009eaa1  call    VidStatisticsDataSetup
0x14009eaa6  mov     ebx, eax
0x14009eaa8  test    eax, eax
0x14009eaaa  js      short loc_14009EAC9
0x14009eaac  mov     rcx, rdi
0x14009eaaf  call    VsmmNumapBackingSetup
0x14009eab4  mov     ebx, eax
0x14009eab6  test    eax, eax
0x14009eab8  js      short loc_14009EAC9
0x14009eaba  mov     rax, [r14+108h]
0x14009eac1  xor     ebx, ebx
0x14009eac3  mov     [rax+rsi*8], rdi
0x14009eac7  jmp     short loc_14009EAE5
0x14009eac9  mov     rcx, rdi
0x14009eacc  call    VsmmNumapNodeObjectTeardown
0x14009ead1  mov     edx, 6D4D6456h; Tag
0x14009ead6  mov     rcx, rdi; P
0x14009ead9  call    cs:__imp_ExFreePoolWithTag
0x14009eae0  nop     dword ptr [rax+rax+00h]
0x14009eae5  mov     eax, ebx
0x14009eae7  add     rsp, 48h
0x14009eaeb  pop     r15
0x14009eaed  pop     r14
0x14009eaef  pop     rdi
0x14009eaf0  pop     rsi
0x14009eaf1  pop     rbp
0x14009eaf2  pop     rbx
0x14009eaf3  retn
```
