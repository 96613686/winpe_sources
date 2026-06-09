# VfsAcquireForSectionSync

- ea: `0x14000e18c`
- end: `0x14000e374`
- name: `VfsAcquireForSectionSync`
- size: `488`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400010e0`

## callees

- `0x14000aefc`
- `0x14000b11c`
- `0x14000e18c`
- `0x14000e37c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e2de`
- `ntoskrnl!ZwClose` at `0x14000e344`
- `ntoskrnl!ZwClose` at `0x14001541b`
- `ntoskrnl!ZwClose` at `0x14000e2de`
- `ntoskrnl!ZwClose` at `0x14000e344`
- `ntoskrnl!ZwClose` at `0x14001541b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e324`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400153f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e324`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400153f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e318`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400153e6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e318`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400153e6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e283`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e283`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e270`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e270`

## string_xrefs

- `0x14000e21f`: `VfsAcquireForSectionSync() - Failed to delay copy file. Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsAcquireForSectionSync(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  __int64 v2; // r8
  unsigned int v4; // esi
  char v5; // r13
  char v6; // r14
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Length; // r12d
  int v12; // eax
  NTSTATUS Section; // ebx
  __int64 v14; // rbx
  void *v15; // rcx
  __int64 v18; // [rsp+80h] [rbp+18h]

  v2 = a2;
  v4 = 1;
  v5 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(a2 + 32);
  v8 = *(_QWORD *)(v7 + 24);
  v18 = v8;
  v9 = *(_QWORD *)(v7 + 32);
  Iopb = Data->Iopb;
  Length = Iopb->Parameters.Read.Length;
  if ( (*(_DWORD *)(v9 + 4) & 4) != 0 )
  {
    if ( Length != 1 )
    {
LABEL_14:
      Section = VfsRedirectIo(Data);
      goto LABEL_15;
    }
    if ( (Iopb->Parameters.AcquireForSectionSynchronization.PageProtection & 0x44) != 0 )
    {
      v12 = VfsDelayedCopy((__int64)Data, v8, v9);
      Section = v12;
      if ( v12 < 0 )
      {
        LogWrite(
          1,
          0,
          L"VfsAcquireForSectionSync() - Failed to delay copy file. Status: 0x%08X",
          (unsigned int)v12,
          0,
          v9);
        goto LABEL_15;
      }
      v8 = v18;
      v2 = a2;
    }
  }
  if ( Length != 1 || **(_QWORD **)(*(_QWORD *)(v2 + 32) + 40LL) )
    goto LABEL_14;
  if ( (*(_DWORD *)(v9 + 4) & 4) != 0 )
  {
    v14 = *(_QWORD *)(v8 + 120);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v14 + 56), 1u);
    v5 = 1;
  }
  Section = VfsCreateSection(*(HANDLE *)((-(__int64)((*(_DWORD *)(v9 + 4) & 4) != 0) & 0xFFFFFFFFFFFFFFE8uLL) + v9 + 80));
  if ( Section >= 0 )
  {
    v6 = 1;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 88), 0, 0) )
    {
      ZwClose(0);
      v6 = 0;
    }
    goto LABEL_14;
  }
LABEL_15:
  if ( v5 )
  {
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v18 + 120) + 56LL));
    KeLeaveCriticalRegion();
  }
  if ( Section < 0 )
  {
    if ( v6 )
    {
      v15 = (void *)_InterlockedExchange64((volatile __int64 *)(v9 + 88), 0);
      if ( v15 )
        ZwClose(v15);
    }
    Data->IoStatus.Status = Section;
    Data->IoStatus.Information = 0;
    return 4;
  }
  return v4;
}

```

## disassembly

```asm
0x14000e18c  mov     rax, rsp
0x14000e18f  mov     [rax+10h], rdx
0x14000e193  mov     [rax+8], rcx
0x14000e197  push    rbx
0x14000e198  push    rsi
0x14000e199  push    rdi
0x14000e19a  push    r12
0x14000e19c  push    r13
0x14000e19e  push    r14
0x14000e1a0  push    r15
0x14000e1a2  sub     rsp, 30h
0x14000e1a6  mov     r8, rdx
0x14000e1a9  mov     r15, rcx
0x14000e1ac  mov     esi, 1
0x14000e1b1  mov     dword ptr [rax-44h], 0
0x14000e1b8  xor     r13b, r13b
0x14000e1bb  mov     [rax-47h], r13b
0x14000e1bf  xor     r14b, r14b
0x14000e1c2  mov     [rax-48h], r14b
0x14000e1c6  mov     rax, [rdx+20h]
0x14000e1ca  mov     rdx, [rax+18h]
0x14000e1ce  mov     [rsp+68h+arg_10], rdx
0x14000e1d6  mov     [rsp+68h+arg_18], rdx
0x14000e1de  mov     rdi, [rax+20h]
0x14000e1e2  mov     [rsp+68h+var_40], rdi
0x14000e1e7  mov     rax, [rcx+10h]
0x14000e1eb  mov     r12d, [rax+18h]
0x14000e1ef  mov     ecx, [rax+1Ch]
0x14000e1f2  mov     eax, [rdi+4]
0x14000e1f5  test    al, 4
0x14000e1f7  jz      short loc_14000E241
0x14000e1f9  cmp     r12d, esi
0x14000e1fc  jnz     loc_14000E2F2
0x14000e202  test    cl, 44h
0x14000e205  jz      short loc_14000E241
0x14000e207  mov     r8, rdi
0x14000e20a  mov     rcx, r15
0x14000e20d  call    VfsDelayedCopy
0x14000e212  mov     ebx, eax
0x14000e214  mov     [rsp+68h+var_44], eax
0x14000e218  test    eax, eax
0x14000e21a  jns     short loc_14000E234
0x14000e21c  mov     r9d, eax
0x14000e21f  lea     r8, aVfsacquirefors; "VfsAcquireForSectionSync() - Failed to "...
0x14000e226  xor     edx, edx
0x14000e228  mov     ecx, esi
0x14000e22a  call    LogWrite
0x14000e22f  jmp     loc_14000E303
0x14000e234  mov     rdx, [rsp+68h+arg_10]
0x14000e23c  mov     r8, [rsp+68h+Handle]
0x14000e241  cmp     r12d, esi
0x14000e244  jnz     loc_14000E2F2
0x14000e24a  mov     rax, [r8+20h]
0x14000e24e  mov     rcx, [rax+28h]
0x14000e252  cmp     qword ptr [rcx], 0
0x14000e256  jnz     loc_14000E2F2
0x14000e25c  mov     [rsp+68h+Handle], 0
0x14000e265  mov     eax, [rdi+4]
0x14000e268  test    al, 4
0x14000e26a  jz      short loc_14000E297
0x14000e26c  mov     rbx, [rdx+78h]
0x14000e270  call    cs:__imp_KeEnterCriticalRegion
0x14000e277  nop     dword ptr [rax+rax+00h]
0x14000e27c  mov     dl, sil; Wait
0x14000e27f  lea     rcx, [rbx+38h]; Resource
0x14000e283  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000e28a  nop     dword ptr [rax+rax+00h]
0x14000e28f  mov     r13b, sil
0x14000e292  mov     [rsp+68h+var_47], sil
0x14000e297  mov     eax, [rdi+4]
0x14000e29a  and     eax, 4
0x14000e29d  setnz   dl
0x14000e2a0  neg     eax
0x14000e2a2  sbb     rcx, rcx
0x14000e2a5  and     rcx, 0FFFFFFFFFFFFFFE8h
0x14000e2a9  lea     r8, [rsp+68h+Handle]
0x14000e2ae  mov     rcx, [rcx+rdi+50h]; FileHandle
0x14000e2b3  call    VfsCreateSection
0x14000e2b8  mov     ebx, eax
0x14000e2ba  mov     [rsp+68h+var_44], eax
0x14000e2be  test    eax, eax
0x14000e2c0  js      short loc_14000E303
0x14000e2c2  mov     r14b, sil
0x14000e2c5  mov     [rsp+68h+var_48], sil
0x14000e2ca  mov     rcx, [rsp+68h+Handle]
0x14000e2cf  xor     eax, eax
0x14000e2d1  lock cmpxchg [rdi+58h], rcx
0x14000e2d7  jz      short loc_14000E2F2
0x14000e2d9  mov     rcx, [rsp+68h+Handle]; Handle
0x14000e2de  call    cs:__imp_ZwClose
0x14000e2e5  nop     dword ptr [rax+rax+00h]
0x14000e2ea  xor     r14b, r14b
0x14000e2ed  mov     [rsp+68h+var_48], r14b
0x14000e2f2  mov     rdx, rdi
0x14000e2f5  mov     rcx, r15; Data
0x14000e2f8  call    VfsRedirectIo
0x14000e2fd  mov     ebx, eax
0x14000e2ff  mov     [rsp+68h+var_44], eax
0x14000e303  test    r13b, r13b
0x14000e306  jz      short loc_14000E330
0x14000e308  mov     rcx, [rsp+68h+arg_10]
0x14000e310  mov     rcx, [rcx+78h]
0x14000e314  add     rcx, 38h ; '8'; Resource
0x14000e318  call    cs:__imp_ExReleaseResourceLite
0x14000e31f  nop     dword ptr [rax+rax+00h]
0x14000e324  call    cs:__imp_KeLeaveCriticalRegion
0x14000e32b  nop     dword ptr [rax+rax+00h]
0x14000e330  test    ebx, ebx
0x14000e332  jns     short loc_14000E361
0x14000e334  test    r14b, r14b
0x14000e337  jz      short loc_14000E350
0x14000e339  xor     ecx, ecx
0x14000e33b  xchg    rcx, [rdi+58h]; Handle
0x14000e33f  test    rcx, rcx
0x14000e342  jz      short loc_14000E350
0x14000e344  call    cs:__imp_ZwClose
0x14000e34b  nop     dword ptr [rax+rax+00h]
0x14000e350  mov     [r15+18h], ebx
0x14000e354  mov     qword ptr [r15+20h], 0
0x14000e35c  mov     esi, 4
0x14000e361  mov     eax, esi
0x14000e363  add     rsp, 30h
0x14000e367  pop     r15
0x14000e369  pop     r14
0x14000e36b  pop     r13
0x14000e36d  pop     r12
0x14000e36f  pop     rdi
0x14000e370  pop     rsi
0x14000e371  pop     rbx
0x14000e372  retn
0x1400153c7  push    rbx
0x1400153c9  push    rbp
0x1400153ca  sub     rsp, 28h
0x1400153ce  mov     rbp, rdx
0x1400153d1  cmp     byte ptr [rbp+21h], 0
0x1400153d5  jz      short loc_1400153FF
0x1400153d7  mov     rax, [rbp+88h]
0x1400153de  mov     rcx, [rax+78h]
0x1400153e2  add     rcx, 38h ; '8'; Resource
0x1400153e6  call    cs:__imp_ExReleaseResourceLite
0x1400153ed  nop     dword ptr [rax+rax+00h]
0x1400153f2  call    cs:__imp_KeLeaveCriticalRegion
0x1400153f9  nop     dword ptr [rax+rax+00h]
0x1400153fe  nop
0x1400153ff  mov     ebx, [rbp+24h]
0x140015402  test    ebx, ebx
0x140015404  jns     short loc_140015437
0x140015406  cmp     byte ptr [rbp+20h], 0
0x14001540a  jz      short loc_140015428
0x14001540c  mov     rax, [rbp+28h]
0x140015410  xor     ecx, ecx
0x140015412  xchg    rcx, [rax+58h]; Handle
0x140015416  test    rcx, rcx
0x140015419  jz      short loc_140015428
0x14001541b  call    cs:__imp_ZwClose
0x140015422  nop     dword ptr [rax+rax+00h]
0x140015427  nop
0x140015428  mov     rax, [rbp+70h]
0x14001542c  mov     [rax+18h], ebx
0x14001542f  mov     qword ptr [rax+20h], 0
0x140015437  add     rsp, 28h
0x14001543b  pop     rbp
0x14001543c  pop     rbx
0x14001543d  retn
```
