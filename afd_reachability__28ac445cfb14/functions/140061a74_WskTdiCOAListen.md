# WskTdiCOAListen

- ea: `0x140061a74`
- end: `0x140061b92`
- name: `WskTdiCOAListen`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063c64`

## callees

- `0x140061a74`
- `0x140062880`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140061aad`
- `ntoskrnl!IoAllocateIrp` at `0x140061aad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061a8d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061a8d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061acb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061acb`
- `ntoskrnl!IofCallDriver` at `0x140061b78`
- `ntoskrnl!IofCallDriver` at `0x140061b78`

## pseudocode

```c
__int64 __fastcall WskTdiCOAListen(__int64 a1)
{
  _QWORD *v2; // rbx
  PIRP Irp; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v6; // rcx
  NTSTATUS v7; // eax
  unsigned int v8; // ecx

  v2 = ExAllocateFromNPagedLookasideList(&stru_1400877C0);
  if ( !v2 )
    goto LABEL_4;
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 160) + 76LL), 0);
  if ( !Irp )
  {
    ExFreeToNPagedLookasideList(&stru_1400877C0, v2);
LABEL_4:
    WskTdiCloseEndpoint(a1, 0);
    return 3221225626LL;
  }
  memset(v2, 0, 0xC8u);
  *v2 = a1;
  v2[6] = v2 + 7;
  *((_DWORD *)v2 + 10) = 134;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)WskTdiCOMPCOAListen;
  CurrentStackLocation[-1].Context = v2;
  CurrentStackLocation[-1].Control = -32;
  v6 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v6[-1].MajorFunction = 1039;
  v6[-1].DeviceObject = *(PDEVICE_OBJECT *)(a1 + 160);
  v6[-1].FileObject = *(PFILE_OBJECT *)(a1 + 152);
  v6[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)(v2 + 1);
  v6[-1].Parameters.WMI.ProviderId = 1;
  v6[-1].Parameters.QueryDirectory.FileName = 0;
  v7 = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 160), Irp);
  v8 = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v8;
}

```

## disassembly

```asm
0x140061a74  mov     [rsp+arg_0], rbx
0x140061a79  mov     [rsp+arg_8], rsi
0x140061a7e  push    rdi
0x140061a7f  sub     rsp, 20h
0x140061a83  mov     rdi, rcx
0x140061a86  lea     rcx, stru_1400877C0; Lookaside
0x140061a8d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140061a94  nop     dword ptr [rax+rax+00h]
0x140061a99  mov     rbx, rax
0x140061a9c  test    rax, rax
0x140061a9f  jz      short loc_140061AD7
0x140061aa1  mov     rcx, [rdi+0A0h]
0x140061aa8  xor     edx, edx; ChargeQuota
0x140061aaa  mov     cl, [rcx+4Ch]; StackSize
0x140061aad  call    cs:__imp_IoAllocateIrp
0x140061ab4  nop     dword ptr [rax+rax+00h]
0x140061ab9  mov     rsi, rax
0x140061abc  test    rax, rax
0x140061abf  jnz     short loc_140061AF7
0x140061ac1  mov     rdx, rbx; Entry
0x140061ac4  lea     rcx, stru_1400877C0; Lookaside
0x140061acb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061ad2  nop     dword ptr [rax+rax+00h]
0x140061ad7  xor     edx, edx
0x140061ad9  mov     rcx, rdi
0x140061adc  call    WskTdiCloseEndpoint
0x140061ae1  mov     eax, 0C000009Ah
0x140061ae6  mov     rbx, [rsp+28h+arg_0]
0x140061aeb  mov     rsi, [rsp+28h+arg_8]
0x140061af0  add     rsp, 20h
0x140061af4  pop     rdi
0x140061af5  retn
0x140061af7  xor     edx, edx; Val
0x140061af9  mov     r8d, 0C8h; Size
0x140061aff  mov     rcx, rbx; void *
0x140061b02  call    memset
0x140061b07  mov     [rbx], rdi
0x140061b0a  lea     rax, [rbx+38h]
0x140061b0e  mov     [rbx+30h], rax
0x140061b12  lea     rcx, WskTdiCOMPCOAListen
0x140061b19  mov     dword ptr [rbx+28h], 86h
0x140061b20  mov     rdx, rsi; Irp
0x140061b23  mov     rax, [rsi+0B8h]
0x140061b2a  mov     [rax-10h], rcx
0x140061b2e  mov     [rax-8], rbx
0x140061b32  mov     byte ptr [rax-45h], 0E0h
0x140061b36  mov     rcx, [rsi+0B8h]
0x140061b3d  mov     word ptr [rcx-48h], 40Fh
0x140061b43  mov     rax, [rdi+0A0h]
0x140061b4a  mov     [rcx-20h], rax
0x140061b4e  mov     rax, [rdi+98h]
0x140061b55  mov     [rcx-18h], rax
0x140061b59  lea     rax, [rbx+8]
0x140061b5d  mov     [rcx-30h], rax
0x140061b61  mov     qword ptr [rcx-40h], 1
0x140061b69  mov     qword ptr [rcx-38h], 0
0x140061b71  mov     rcx, [rdi+0A0h]; DeviceObject
0x140061b78  call    cs:__imp_IofCallDriver
0x140061b7f  nop     dword ptr [rax+rax+00h]
0x140061b84  xor     ecx, ecx
0x140061b86  test    eax, eax
0x140061b88  cmovs   ecx, eax
0x140061b8b  mov     eax, ecx
0x140061b8d  jmp     loc_140061AE6
```
