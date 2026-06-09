# WskTdiCOMPAccept

- ea: `0x140061ba0`
- end: `0x140061cb6`
- name: `WskTdiCOMPAccept`
- size: `278`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140061ba0`
- `0x14006280c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140061c15`
- `ntoskrnl!IoFreeIrp` at `0x140061c15`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140061c3b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140061c3b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061bbc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061bbc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061c06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061c06`
- `ntoskrnl!IoAllocateMdl` at `0x140061be8`
- `ntoskrnl!IoAllocateMdl` at `0x140061be8`
- `ntoskrnl!IofCallDriver` at `0x140061ca5`
- `ntoskrnl!IofCallDriver` at `0x140061ca5`

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
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPAcceptAddressQuery;
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
0x140061ba0  push    rbx
0x140061ba2  push    rbp
0x140061ba3  push    rsi
0x140061ba4  push    rdi
0x140061ba5  sub     rsp, 38h
0x140061ba9  cmp     dword ptr [rdx+30h], 0
0x140061bad  mov     rsi, r8
0x140061bb0  mov     rbx, rdx
0x140061bb3  jl      short loc_140061C12
0x140061bb5  lea     rcx, stru_1400877C0; Lookaside
0x140061bbc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140061bc3  nop     dword ptr [rax+rax+00h]
0x140061bc8  mov     rdi, rax
0x140061bcb  test    rax, rax
0x140061bce  jz      short loc_140061C12
0x140061bd0  lea     rcx, [rax+8]; VirtualAddress
0x140061bd4  mov     [rsp+58h+Irp], 0; Irp
0x140061bdd  xor     r9d, r9d; ChargeQuota
0x140061be0  xor     r8d, r8d; SecondaryBuffer
0x140061be3  mov     edx, 8Ah; Length
0x140061be8  call    cs:__imp_IoAllocateMdl
0x140061bef  nop     dword ptr [rax+rax+00h]
0x140061bf4  mov     rbp, rax
0x140061bf7  test    rax, rax
0x140061bfa  jnz     short loc_140061C38
0x140061bfc  mov     rdx, rdi; Entry
0x140061bff  lea     rcx, stru_1400877C0; Lookaside
0x140061c06  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061c0d  nop     dword ptr [rax+rax+00h]
0x140061c12  mov     rcx, rbx; Irp
0x140061c15  call    cs:__imp_IoFreeIrp
0x140061c1c  nop     dword ptr [rax+rax+00h]
0x140061c21  mov     rcx, rsi
0x140061c24  call    WskTdiCloseConnectionAndPopulate
0x140061c29  mov     eax, 0C0000016h
0x140061c2e  add     rsp, 38h
0x140061c32  pop     rdi
0x140061c33  pop     rsi
0x140061c34  pop     rbp
0x140061c35  pop     rbx
0x140061c36  retn
0x140061c38  mov     rcx, rbp; MemoryDescriptorList
0x140061c3b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140061c42  nop     dword ptr [rax+rax+00h]
0x140061c47  mov     [rsi+30h], rdi
0x140061c4b  lea     rcx, WskTdiCOMPAcceptAddressQuery
0x140061c52  mov     rax, [rbx+0B8h]
0x140061c59  mov     rdx, rbx; Irp
0x140061c5c  mov     [rbx+8], rbp
0x140061c60  mov     [rax-10h], rcx
0x140061c64  mov     [rax-8], rsi
0x140061c68  mov     byte ptr [rax-45h], 0E0h
0x140061c6c  mov     rcx, [rbx+0B8h]
0x140061c73  mov     word ptr [rcx-48h], 0C0Fh
0x140061c79  mov     rax, [rsi+0A0h]
0x140061c80  mov     [rcx-20h], rax
0x140061c84  mov     rax, [rsi+98h]
0x140061c8b  mov     [rcx-18h], rax
0x140061c8f  mov     dword ptr [rcx-40h], 3
0x140061c96  mov     qword ptr [rcx-38h], 0
0x140061c9e  mov     rcx, [rsi+0A0h]; DeviceObject
0x140061ca5  call    cs:__imp_IofCallDriver
0x140061cac  nop     dword ptr [rax+rax+00h]
0x140061cb1  jmp     loc_140061C29
```
