# AfdMdlReadComplete

- ea: `0x140055c5c`
- end: `0x140055d6e`
- name: `AfdMdlReadComplete`
- size: `274`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *Object, struct _MDL *, LARGE_INTEGER *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400404a0`
- `0x1400406dc`
- `0x140041038`
- `0x1400557d0`
- `0x140055b60`

## callees

- `0x140055c5c`
- `0x1400940b0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140055ca0`
- `ntoskrnl!IoAllocateIrp` at `0x140055ca0`
- `ntoskrnl!FsRtlMdlReadComplete` at `0x140055c72`
- `ntoskrnl!FsRtlMdlReadComplete` at `0x140055c72`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055c8c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055c8c`
- `ntoskrnl!ObfReferenceObject` at `0x140055cfd`
- `ntoskrnl!ObfReferenceObject` at `0x140055cfd`
- `ntoskrnl!IofCallDriver` at `0x140055d4f`
- `ntoskrnl!IofCallDriver` at `0x140055d4f`

## pseudocode

```c
__int64 __fastcall AfdMdlReadComplete(struct _FILE_OBJECT *Object, struct _MDL *a2, LARGE_INTEGER *a3)
{
  PDEVICE_OBJECT RelatedDeviceObject; // rbp
  PIRP Irp; // rax
  IRP *v9; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  ULONG v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _IO_STACK_LOCATION *v14; // rax

  if ( (unsigned __int8)FsRtlMdlReadComplete() )
    return 0;
  RelatedDeviceObject = IoGetRelatedDeviceObject(Object);
  Irp = IoAllocateIrp(RelatedDeviceObject->StackSize, 0);
  v9 = Irp;
  if ( !Irp )
    return 3221225626LL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->MdlAddress = a2;
  *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 1539;
  CurrentStackLocation[-1].Parameters.Read.Length = 0;
  if ( a2 )
  {
    v11 = 0;
    do
    {
      v11 += a2->ByteCount;
      CurrentStackLocation[-1].Parameters.Read.Length = v11;
      a2 = a2->Next;
    }
    while ( a2 );
  }
  CurrentStackLocation[-1].Parameters.Read.ByteOffset = *a3;
  CurrentStackLocation[-1].Parameters.Create.Options = 0;
  ObfReferenceObject(Object);
  CurrentStackLocation[-1].FileObject = Object;
  CurrentStackLocation[-1].DeviceObject = RelatedDeviceObject;
  v14 = v9->Tail.Overlay.CurrentStackLocation;
  v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartMdlReadComplete;
  v14[-1].Context = Object;
  v14[-1].Control = -32;
  if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
    WPP_SF_qqi(&AfdRestartMdlReadComplete, v12, v13, Object, v9, a3->QuadPart);
  IofCallDriver(RelatedDeviceObject, v9);
  return 259;
}

```

## disassembly

```asm
0x140055c5c  push    rbx
0x140055c5e  push    rbp
0x140055c5f  push    rsi
0x140055c60  push    rdi
0x140055c61  push    r14
0x140055c63  push    r15
0x140055c65  sub     rsp, 38h
0x140055c69  mov     r15, r8
0x140055c6c  mov     r14, rdx
0x140055c6f  mov     rsi, rcx
0x140055c72  call    cs:__imp_FsRtlMdlReadComplete
0x140055c79  nop     dword ptr [rax+rax+00h]
0x140055c7e  test    al, al
0x140055c80  jz      short loc_140055C89
0x140055c82  xor     eax, eax
0x140055c84  jmp     loc_140055D60
0x140055c89  mov     rcx, rsi; FileObject
0x140055c8c  call    cs:__imp_IoGetRelatedDeviceObject
0x140055c93  nop     dword ptr [rax+rax+00h]
0x140055c98  xor     edx, edx; ChargeQuota
0x140055c9a  mov     rbp, rax
0x140055c9d  mov     cl, [rax+4Ch]; StackSize
0x140055ca0  call    cs:__imp_IoAllocateIrp
0x140055ca7  nop     dword ptr [rax+rax+00h]
0x140055cac  mov     rbx, rax
0x140055caf  test    rax, rax
0x140055cb2  jnz     short loc_140055CBE
0x140055cb4  mov     eax, 0C000009Ah
0x140055cb9  jmp     loc_140055D60
0x140055cbe  mov     rdi, [rax+0B8h]
0x140055cc5  mov     [rax+8], r14
0x140055cc9  mov     word ptr [rdi-48h], 603h
0x140055ccf  mov     dword ptr [rdi-40h], 0
0x140055cd6  test    r14, r14
0x140055cd9  jz      short loc_140055CEC
0x140055cdb  xor     ecx, ecx
0x140055cdd  add     ecx, [r14+28h]
0x140055ce1  mov     [rdi-40h], ecx
0x140055ce4  mov     r14, [r14]
0x140055ce7  test    r14, r14
0x140055cea  jnz     short loc_140055CDD
0x140055cec  mov     rax, [r15]
0x140055cef  mov     rcx, rsi; Object
0x140055cf2  mov     [rdi-30h], rax
0x140055cf6  mov     dword ptr [rdi-38h], 0
0x140055cfd  call    cs:__imp_ObfReferenceObject
0x140055d04  nop     dword ptr [rax+rax+00h]
0x140055d09  mov     [rdi-18h], rsi
0x140055d0d  lea     rcx, AfdRestartMdlReadComplete
0x140055d14  mov     [rdi-20h], rbp
0x140055d18  mov     rax, [rbx+0B8h]
0x140055d1f  mov     [rax-10h], rcx
0x140055d23  mov     [rax-8], rsi
0x140055d27  mov     byte ptr [rax-45h], 0E0h
0x140055d2b  test    byte ptr cs:xmmword_1400875E0+2, 4
0x140055d32  jz      short loc_140055D49
0x140055d34  mov     rax, [r15]
0x140055d37  mov     r9, rsi
0x140055d3a  mov     [rsp+68h+var_40], rax
0x140055d3f  mov     [rsp+68h+var_48], rbx
0x140055d44  call    WPP_SF_qqi
0x140055d49  mov     rdx, rbx; Irp
0x140055d4c  mov     rcx, rbp; DeviceObject
0x140055d4f  call    cs:__imp_IofCallDriver
0x140055d56  nop     dword ptr [rax+rax+00h]
0x140055d5b  mov     eax, 103h
0x140055d60  add     rsp, 38h
0x140055d64  pop     r15
0x140055d66  pop     r14
0x140055d68  pop     rdi
0x140055d69  pop     rsi
0x140055d6a  pop     rbp
0x140055d6b  pop     rbx
0x140055d6c  retn
```
