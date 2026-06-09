# WskTdiCOMPAccept

- ea: `0x140061d40`
- end: `0x140061e56`
- name: `WskTdiCOMPAccept`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140061d40`
- `0x1400629ac`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140061db5`
- `ntoskrnl!IoFreeIrp` at `0x140061db5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140061ddb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140061ddb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061d5c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061d5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061da6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061da6`
- `ntoskrnl!IoAllocateMdl` at `0x140061d88`
- `ntoskrnl!IoAllocateMdl` at `0x140061d88`
- `ntoskrnl!IofCallDriver` at `0x140061e45`
- `ntoskrnl!IofCallDriver` at `0x140061e45`

## pseudocode

```c
__int64 __fastcall WskTdiCOMPAccept(__int64 a1, IRP *a2, __int64 a3)
{
  char *v5; // rax
  void *v6; // rdi
  struct _MDL *Mdl; // rax
  struct _MDL *v8; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v11; // rcx

  if ( a2->IoStatus.Status >= 0 )
  {
    v5 = (char *)ExAllocateFromNPagedLookasideList(&stru_1400877C0);
    v6 = v5;
    if ( v5 )
    {
      Mdl = IoAllocateMdl(v5 + 8, 0x8Au, 0, 0, 0);
      v8 = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        *(_QWORD *)(a3 + 48) = v6;
        CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
        a2->MdlAddress = v8;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)WskTdiCOMPAcceptAddressQuery;
        CurrentStackLocation[-1].Context = (PVOID)a3;
        CurrentStackLocation[-1].Control = -32;
        v11 = a2->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v11[-1].MajorFunction = 3087;
        v11[-1].DeviceObject = *(PDEVICE_OBJECT *)(a3 + 160);
        v11[-1].FileObject = *(PFILE_OBJECT *)(a3 + 152);
        v11[-1].Parameters.Read.Length = 3;
        v11[-1].Parameters.QueryDirectory.FileName = 0;
        IofCallDriver(*(PDEVICE_OBJECT *)(a3 + 160), a2);
        return 3221225494LL;
      }
      ExFreeToNPagedLookasideList(&stru_1400877C0, v6);
    }
  }
  IoFreeIrp(a2);
  WskTdiCloseConnectionAndPopulate(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140061d40  push    rbx
0x140061d42  push    rbp
0x140061d43  push    rsi
0x140061d44  push    rdi
0x140061d45  sub     rsp, 38h
0x140061d49  cmp     dword ptr [rdx+30h], 0
0x140061d4d  mov     rsi, r8
0x140061d50  mov     rbx, rdx
0x140061d53  jl      short loc_140061DB2
0x140061d55  lea     rcx, stru_1400877C0; Lookaside
0x140061d5c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140061d63  nop     dword ptr [rax+rax+00h]
0x140061d68  mov     rdi, rax
0x140061d6b  test    rax, rax
0x140061d6e  jz      short loc_140061DB2
0x140061d70  lea     rcx, [rax+8]; VirtualAddress
0x140061d74  mov     [rsp+58h+Irp], 0; Irp
0x140061d7d  xor     r9d, r9d; ChargeQuota
0x140061d80  xor     r8d, r8d; SecondaryBuffer
0x140061d83  mov     edx, 8Ah; Length
0x140061d88  call    cs:__imp_IoAllocateMdl
0x140061d8f  nop     dword ptr [rax+rax+00h]
0x140061d94  mov     rbp, rax
0x140061d97  test    rax, rax
0x140061d9a  jnz     short loc_140061DD8
0x140061d9c  mov     rdx, rdi; Entry
0x140061d9f  lea     rcx, stru_1400877C0; Lookaside
0x140061da6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061dad  nop     dword ptr [rax+rax+00h]
0x140061db2  mov     rcx, rbx; Irp
0x140061db5  call    cs:__imp_IoFreeIrp
0x140061dbc  nop     dword ptr [rax+rax+00h]
0x140061dc1  mov     rcx, rsi
0x140061dc4  call    WskTdiCloseConnectionAndPopulate
0x140061dc9  mov     eax, 0C0000016h
0x140061dce  add     rsp, 38h
0x140061dd2  pop     rdi
0x140061dd3  pop     rsi
0x140061dd4  pop     rbp
0x140061dd5  pop     rbx
0x140061dd6  retn
0x140061dd8  mov     rcx, rbp; MemoryDescriptorList
0x140061ddb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140061de2  nop     dword ptr [rax+rax+00h]
0x140061de7  mov     [rsi+30h], rdi
0x140061deb  lea     rcx, WskTdiCOMPAcceptAddressQuery
0x140061df2  mov     rax, [rbx+0B8h]
0x140061df9  mov     rdx, rbx; Irp
0x140061dfc  mov     [rbx+8], rbp
0x140061e00  mov     [rax-10h], rcx
0x140061e04  mov     [rax-8], rsi
0x140061e08  mov     byte ptr [rax-45h], 0E0h
0x140061e0c  mov     rcx, [rbx+0B8h]
0x140061e13  mov     word ptr [rcx-48h], 0C0Fh
0x140061e19  mov     rax, [rsi+0A0h]
0x140061e20  mov     [rcx-20h], rax
0x140061e24  mov     rax, [rsi+98h]
0x140061e2b  mov     [rcx-18h], rax
0x140061e2f  mov     dword ptr [rcx-40h], 3
0x140061e36  mov     qword ptr [rcx-38h], 0
0x140061e3e  mov     rcx, [rsi+0A0h]; DeviceObject
0x140061e45  call    cs:__imp_IofCallDriver
0x140061e4c  nop     dword ptr [rax+rax+00h]
0x140061e51  jmp     loc_140061DC9
```
