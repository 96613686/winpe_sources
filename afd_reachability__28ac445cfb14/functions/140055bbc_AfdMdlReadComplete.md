# AfdMdlReadComplete

- ea: `0x140055bbc`
- end: `0x140055cce`
- name: `AfdMdlReadComplete`
- size: `274`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140040480`
- `0x1400406bc`
- `0x140041018`
- `0x140055730`
- `0x140055ac0`

## callees

- `0x140055bbc`
- `0x1400940b0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140055c00`
- `ntoskrnl!IoAllocateIrp` at `0x140055c00`
- `ntoskrnl!FsRtlMdlReadComplete` at `0x140055bd2`
- `ntoskrnl!FsRtlMdlReadComplete` at `0x140055bd2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055bec`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055bec`
- `ntoskrnl!ObfReferenceObject` at `0x140055c5d`
- `ntoskrnl!ObfReferenceObject` at `0x140055c5d`
- `ntoskrnl!IofCallDriver` at `0x140055caf`
- `ntoskrnl!IofCallDriver` at `0x140055caf`

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
0x140055bbc  push    rbx
0x140055bbe  push    rbp
0x140055bbf  push    rsi
0x140055bc0  push    rdi
0x140055bc1  push    r14
0x140055bc3  push    r15
0x140055bc5  sub     rsp, 38h
0x140055bc9  mov     r15, r8
0x140055bcc  mov     r14, rdx
0x140055bcf  mov     rsi, rcx
0x140055bd2  call    cs:__imp_FsRtlMdlReadComplete
0x140055bd9  nop     dword ptr [rax+rax+00h]
0x140055bde  test    al, al
0x140055be0  jz      short loc_140055BE9
0x140055be2  xor     eax, eax
0x140055be4  jmp     loc_140055CC0
0x140055be9  mov     rcx, rsi; FileObject
0x140055bec  call    cs:__imp_IoGetRelatedDeviceObject
0x140055bf3  nop     dword ptr [rax+rax+00h]
0x140055bf8  xor     edx, edx; ChargeQuota
0x140055bfa  mov     rbp, rax
0x140055bfd  mov     cl, [rax+4Ch]; StackSize
0x140055c00  call    cs:__imp_IoAllocateIrp
0x140055c07  nop     dword ptr [rax+rax+00h]
0x140055c0c  mov     rbx, rax
0x140055c0f  test    rax, rax
0x140055c12  jnz     short loc_140055C1E
0x140055c14  mov     eax, 0C000009Ah
0x140055c19  jmp     loc_140055CC0
0x140055c1e  mov     rdi, [rax+0B8h]
0x140055c25  mov     [rax+8], r14
0x140055c29  mov     word ptr [rdi-48h], 603h
0x140055c2f  mov     dword ptr [rdi-40h], 0
0x140055c36  test    r14, r14
0x140055c39  jz      short loc_140055C4C
0x140055c3b  xor     ecx, ecx
0x140055c3d  add     ecx, [r14+28h]
0x140055c41  mov     [rdi-40h], ecx
0x140055c44  mov     r14, [r14]
0x140055c47  test    r14, r14
0x140055c4a  jnz     short loc_140055C3D
0x140055c4c  mov     rax, [r15]
0x140055c4f  mov     rcx, rsi; Object
0x140055c52  mov     [rdi-30h], rax
0x140055c56  mov     dword ptr [rdi-38h], 0
0x140055c5d  call    cs:__imp_ObfReferenceObject
0x140055c64  nop     dword ptr [rax+rax+00h]
0x140055c69  mov     [rdi-18h], rsi
0x140055c6d  lea     rcx, AfdRestartMdlReadComplete
0x140055c74  mov     [rdi-20h], rbp
0x140055c78  mov     rax, [rbx+0B8h]
0x140055c7f  mov     [rax-10h], rcx
0x140055c83  mov     [rax-8], rsi
0x140055c87  mov     byte ptr [rax-45h], 0E0h
0x140055c8b  test    byte ptr cs:xmmword_1400875E0+2, 4
0x140055c92  jz      short loc_140055CA9
0x140055c94  mov     rax, [r15]
0x140055c97  mov     r9, rsi
0x140055c9a  mov     [rsp+68h+var_40], rax
0x140055c9f  mov     [rsp+68h+var_48], rbx
0x140055ca4  call    WPP_SF_qqi
0x140055ca9  mov     rdx, rbx; Irp
0x140055cac  mov     rcx, rbp; DeviceObject
0x140055caf  call    cs:__imp_IofCallDriver
0x140055cb6  nop     dword ptr [rax+rax+00h]
0x140055cbb  mov     eax, 103h
0x140055cc0  add     rsp, 38h
0x140055cc4  pop     r15
0x140055cc6  pop     r14
0x140055cc8  pop     rdi
0x140055cc9  pop     rsi
0x140055cca  pop     rbp
0x140055ccb  pop     rbx
0x140055ccc  retn
```
