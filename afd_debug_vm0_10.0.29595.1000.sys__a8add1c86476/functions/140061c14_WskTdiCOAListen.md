# WskTdiCOAListen

- ea: `0x140061c14`
- end: `0x140061d32`
- name: `WskTdiCOAListen`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063e04`

## callees

- `0x140061c14`
- `0x140062a20`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140061c4d`
- `ntoskrnl!IoAllocateIrp` at `0x140061c4d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061c2d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140061c2d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061c6b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061c6b`
- `ntoskrnl!IofCallDriver` at `0x140061d18`
- `ntoskrnl!IofCallDriver` at `0x140061d18`

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
0x140061c14  mov     [rsp+arg_0], rbx
0x140061c19  mov     [rsp+arg_8], rsi
0x140061c1e  push    rdi
0x140061c1f  sub     rsp, 20h
0x140061c23  mov     rdi, rcx
0x140061c26  lea     rcx, stru_1400877C0; Lookaside
0x140061c2d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140061c34  nop     dword ptr [rax+rax+00h]
0x140061c39  mov     rbx, rax
0x140061c3c  test    rax, rax
0x140061c3f  jz      short loc_140061C77
0x140061c41  mov     rcx, [rdi+0A0h]
0x140061c48  xor     edx, edx; ChargeQuota
0x140061c4a  mov     cl, [rcx+4Ch]; StackSize
0x140061c4d  call    cs:__imp_IoAllocateIrp
0x140061c54  nop     dword ptr [rax+rax+00h]
0x140061c59  mov     rsi, rax
0x140061c5c  test    rax, rax
0x140061c5f  jnz     short loc_140061C97
0x140061c61  mov     rdx, rbx; Entry
0x140061c64  lea     rcx, stru_1400877C0; Lookaside
0x140061c6b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061c72  nop     dword ptr [rax+rax+00h]
0x140061c77  xor     edx, edx
0x140061c79  mov     rcx, rdi
0x140061c7c  call    WskTdiCloseEndpoint
0x140061c81  mov     eax, 0C000009Ah
0x140061c86  mov     rbx, [rsp+28h+arg_0]
0x140061c8b  mov     rsi, [rsp+28h+arg_8]
0x140061c90  add     rsp, 20h
0x140061c94  pop     rdi
0x140061c95  retn
0x140061c97  xor     edx, edx; Val
0x140061c99  mov     r8d, 0C8h; Size
0x140061c9f  mov     rcx, rbx; void *
0x140061ca2  call    memset
0x140061ca7  mov     [rbx], rdi
0x140061caa  lea     rax, [rbx+38h]
0x140061cae  mov     [rbx+30h], rax
0x140061cb2  lea     rcx, WskTdiCOMPCOAListen
0x140061cb9  mov     dword ptr [rbx+28h], 86h
0x140061cc0  mov     rdx, rsi; Irp
0x140061cc3  mov     rax, [rsi+0B8h]
0x140061cca  mov     [rax-10h], rcx
0x140061cce  mov     [rax-8], rbx
0x140061cd2  mov     byte ptr [rax-45h], 0E0h
0x140061cd6  mov     rcx, [rsi+0B8h]
0x140061cdd  mov     word ptr [rcx-48h], 40Fh
0x140061ce3  mov     rax, [rdi+0A0h]
0x140061cea  mov     [rcx-20h], rax
0x140061cee  mov     rax, [rdi+98h]
0x140061cf5  mov     [rcx-18h], rax
0x140061cf9  lea     rax, [rbx+8]
0x140061cfd  mov     [rcx-30h], rax
0x140061d01  mov     qword ptr [rcx-40h], 1
0x140061d09  mov     qword ptr [rcx-38h], 0
0x140061d11  mov     rcx, [rdi+0A0h]; DeviceObject
0x140061d18  call    cs:__imp_IofCallDriver
0x140061d1f  nop     dword ptr [rax+rax+00h]
0x140061d24  xor     ecx, ecx
0x140061d26  test    eax, eax
0x140061d28  cmovs   ecx, eax
0x140061d2b  mov     eax, ecx
0x140061d2d  jmp     loc_140061C86
```
