# BthEnumQueryEnumeratorInterface

- ea: `0x14001d4fc`
- end: `0x14001d7cf`
- name: `BthEnumQueryEnumeratorInterface`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cf90`

## callees

- `0x14001d4fc`
- `0x14001de14`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14001d51b`
- `ntoskrnl!IoAllocateIrp` at `0x14001d6ab`
- `ntoskrnl!IoAllocateIrp` at `0x14001d51b`
- `ntoskrnl!IoAllocateIrp` at `0x14001d6ab`
- `ntoskrnl!IoFreeIrp` at `0x14001d66f`
- `ntoskrnl!IoFreeIrp` at `0x14001d683`
- `ntoskrnl!IoFreeIrp` at `0x14001d66f`
- `ntoskrnl!IoFreeIrp` at `0x14001d683`
- `ntoskrnl!ExFreePool` at `0x14001d531`
- `ntoskrnl!ExFreePool` at `0x14001d64c`
- `ntoskrnl!ExFreePool` at `0x14001d660`
- `ntoskrnl!ExFreePool` at `0x14001d6c1`
- `ntoskrnl!ExFreePool` at `0x14001d531`
- `ntoskrnl!ExFreePool` at `0x14001d64c`
- `ntoskrnl!ExFreePool` at `0x14001d660`
- `ntoskrnl!ExFreePool` at `0x14001d6c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001d570`
- `ntoskrnl!ExAllocatePool2` at `0x14001d60d`
- `ntoskrnl!ExAllocatePool2` at `0x14001d630`
- `ntoskrnl!ExAllocatePool2` at `0x14001d570`
- `ntoskrnl!ExAllocatePool2` at `0x14001d60d`
- `ntoskrnl!ExAllocatePool2` at `0x14001d630`

## pseudocode

```c
__int64 __fastcall BthEnumQueryEnumeratorInterface(__int64 a1)
{
  __int64 v1; // r15
  PIRP Irp; // rax
  IRP *v4; // rsi
  int v5; // ebx
  IRP *v6; // r14
  __int64 Pool2; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v9; // rbp
  PIRP v11; // rax
  _IO_STACK_LOCATION *v12; // rax
  _IO_STACK_LOCATION *v13; // rax

  v1 = *(_QWORD *)(a1 + 64);
  Irp = IoAllocateIrp(*(_BYTE *)(a1 + 76) + 1, 0);
  v4 = Irp;
  if ( !Irp )
  {
    ExFreePool(0);
    return (unsigned int)-1073741670;
  }
  --Irp->CurrentLocation;
  v6 = 0;
  --Irp->Tail.Overlay.CurrentStackLocation;
  if ( *(_DWORD *)(v1 + 208) == 3 )
  {
    Pool2 = ExAllocatePool2(64, 72, 1330467906);
    if ( !Pool2 )
    {
LABEL_5:
      v5 = -1073741670;
      goto LABEL_13;
    }
    CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
    *(_QWORD *)(Pool2 + 40) = BthEnumEnumerateProtocolOrDevice;
    v9 = 0;
    *(_QWORD *)(Pool2 + 48) = 0;
    *(_QWORD *)(Pool2 + 64) = 0;
    *(_QWORD *)(Pool2 + 32) = a1;
    *(_DWORD *)(Pool2 + 56) = 1;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)&GUID_BTHDDI_ENUMERATOR_INTERFACE;
    CurrentStackLocation[-1].Parameters.Create.Options = 33554504;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = Pool2;
    v4->IoStatus.Status = -1073741637;
    v5 = WaitForLowerDriverToCompleteIrp(*(PDEVICE_OBJECT *)(v1 + 24), v4, 0);
    if ( v5 >= 0 )
    {
      *(_QWORD *)(v1 + 232) = Pool2;
      goto LABEL_13;
    }
LABEL_11:
    ExFreePool((PVOID)Pool2);
    if ( v9 )
      ExFreePool((PVOID)v9);
    goto LABEL_13;
  }
  Pool2 = ExAllocatePool2(64, 72, 1330467906);
  if ( !Pool2 )
    goto LABEL_5;
  v9 = ExAllocatePool2(64, 72, 1330467906);
  if ( !v9 )
  {
LABEL_10:
    v5 = -1073741670;
    goto LABEL_11;
  }
  v11 = IoAllocateIrp(*(_BYTE *)(a1 + 76) + 1, 0);
  v6 = v11;
  if ( !v11 )
  {
    ExFreePool(0);
    goto LABEL_10;
  }
  --v11->CurrentLocation;
  --v11->Tail.Overlay.CurrentStackLocation;
  v12 = v4->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)(Pool2 + 40) = BthEnumEnumerateProtocolOrDevice;
  *(_QWORD *)(Pool2 + 48) = BthEnumEnumerateWWSettings;
  *(_QWORD *)(Pool2 + 64) = BthEnumEnumerateFlags;
  *(_QWORD *)(Pool2 + 32) = a1;
  *(_DWORD *)(Pool2 + 56) = 0;
  v12[-1].Parameters.WMI.ProviderId = (unsigned __int64)&GUID_BTHDDI_ENUMERATOR_INTERFACE;
  *(_WORD *)&v12[-1].MajorFunction = 2075;
  v12[-1].Parameters.Create.Options = 33554504;
  v12[-1].Parameters.Read.ByteOffset.QuadPart = Pool2;
  v12[-1].Parameters.CreatePipe.Parameters = 0;
  v4->IoStatus.Status = -1073741637;
  v5 = WaitForLowerDriverToCompleteIrp(*(PDEVICE_OBJECT *)(v1 + 24), v4, 0);
  if ( v5 < 0 )
    goto LABEL_11;
  *(_QWORD *)(v1 + 232) = Pool2;
  v13 = v6->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)(v9 + 40) = BthEnumEnumerateProtocolOrDevice;
  *(_QWORD *)(v9 + 48) = 0;
  *(_QWORD *)(v9 + 64) = 0;
  *(_QWORD *)(v9 + 32) = a1;
  *(_DWORD *)(v9 + 56) = 2;
  v13[-1].Parameters.CreatePipe.Parameters = 0;
  *(_WORD *)&v13[-1].MajorFunction = 2075;
  v13[-1].Parameters.WMI.ProviderId = (unsigned __int64)&GUID_BTHDDI_ENUMERATOR_INTERFACE;
  v13[-1].Parameters.Create.Options = 33554504;
  v13[-1].Parameters.Read.ByteOffset.QuadPart = v9;
  v6->IoStatus.Status = -1073741637;
  v5 = WaitForLowerDriverToCompleteIrp(*(PDEVICE_OBJECT *)(v1 + 24), v6, 0);
  if ( v5 < 0 )
    goto LABEL_11;
  *(_QWORD *)(v1 + 240) = v9;
LABEL_13:
  IoFreeIrp(v4);
  if ( v6 )
    IoFreeIrp(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001d4fc  push    rbx
0x14001d4fe  push    rbp
0x14001d4ff  push    rsi
0x14001d500  push    rdi
0x14001d501  push    r12
0x14001d503  push    r13
0x14001d505  push    r14
0x14001d507  push    r15
0x14001d509  sub     rsp, 28h
0x14001d50d  mov     r15, [rcx+40h]
0x14001d511  mov     r13, rcx
0x14001d514  mov     cl, [rcx+4Ch]
0x14001d517  xor     edx, edx; ChargeQuota
0x14001d519  inc     cl; StackSize
0x14001d51b  call    cs:__imp_IoAllocateIrp
0x14001d522  nop     dword ptr [rax+rax+00h]
0x14001d527  mov     rsi, rax
0x14001d52a  test    rax, rax
0x14001d52d  jnz     short loc_14001D547
0x14001d52f  xor     ecx, ecx; P
0x14001d531  call    cs:__imp_ExFreePool
0x14001d538  nop     dword ptr [rax+rax+00h]
0x14001d53d  mov     ebx, 0C000009Ah
0x14001d542  jmp     loc_14001D68F
0x14001d547  dec     byte ptr [rax+43h]
0x14001d54a  xor     r14d, r14d
0x14001d54d  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001d555  mov     r8d, 4F4D5442h
0x14001d55b  cmp     dword ptr [r15+0D0h], 3
0x14001d563  jnz     loc_14001D5FD
0x14001d569  lea     edx, [r14+48h]
0x14001d56d  lea     ecx, [rdx-8]
0x14001d570  call    cs:__imp_ExAllocatePool2
0x14001d577  nop     dword ptr [rax+rax+00h]
0x14001d57c  xor     edx, edx
0x14001d57e  mov     rdi, rax
0x14001d581  test    rax, rax
0x14001d584  jnz     short loc_14001D590
0x14001d586  mov     ebx, 0C000009Ah
0x14001d58b  jmp     loc_14001D66C
0x14001d590  mov     rax, [rsi+0B8h]
0x14001d597  lea     rcx, BthEnumEnumerateProtocolOrDevice
0x14001d59e  mov     [rdi+28h], rcx
0x14001d5a2  mov     rbp, rdx
0x14001d5a5  mov     [rdi+30h], rdx
0x14001d5a9  lea     rcx, GUID_BTHDDI_ENUMERATOR_INTERFACE
0x14001d5b0  mov     [rdi+40h], rdx
0x14001d5b4  xor     r8d, r8d
0x14001d5b7  mov     [rdi+20h], r13
0x14001d5bb  mov     dword ptr [rdi+38h], 1
0x14001d5c2  mov     [rax-28h], rdx
0x14001d5c6  mov     rdx, rsi; Irp
0x14001d5c9  mov     word ptr [rax-48h], 81Bh
0x14001d5cf  mov     [rax-40h], rcx
0x14001d5d3  mov     dword ptr [rax-38h], 2000048h
0x14001d5da  mov     [rax-30h], rdi
0x14001d5de  mov     dword ptr [rsi+30h], 0C00000BBh
0x14001d5e5  mov     rcx, [r15+18h]; DeviceObject
0x14001d5e9  call    WaitForLowerDriverToCompleteIrp
0x14001d5ee  mov     ebx, eax
0x14001d5f0  test    eax, eax
0x14001d5f2  js      short loc_14001D649
0x14001d5f4  mov     [r15+0E8h], rdi
0x14001d5fb  jmp     short loc_14001D66C
0x14001d5fd  mov     r12d, 48h ; 'H'
0x14001d603  mov     edx, r12d
0x14001d606  lea     ebx, [r12-8]
0x14001d60b  mov     ecx, ebx
0x14001d60d  call    cs:__imp_ExAllocatePool2
0x14001d614  nop     dword ptr [rax+rax+00h]
0x14001d619  mov     rdi, rax
0x14001d61c  test    rax, rax
0x14001d61f  jz      loc_14001D586
0x14001d625  mov     r8d, 4F4D5442h
0x14001d62b  mov     edx, r12d
0x14001d62e  mov     ecx, ebx
0x14001d630  call    cs:__imp_ExAllocatePool2
0x14001d637  nop     dword ptr [rax+rax+00h]
0x14001d63c  mov     rbp, rax
0x14001d63f  test    rax, rax
0x14001d642  jnz     short loc_14001D6A3
0x14001d644  mov     ebx, 0C000009Ah
0x14001d649  mov     rcx, rdi; P
0x14001d64c  call    cs:__imp_ExFreePool
0x14001d653  nop     dword ptr [rax+rax+00h]
0x14001d658  test    rbp, rbp
0x14001d65b  jz      short loc_14001D66C
0x14001d65d  mov     rcx, rbp; P
0x14001d660  call    cs:__imp_ExFreePool
0x14001d667  nop     dword ptr [rax+rax+00h]
0x14001d66c  mov     rcx, rsi; Irp
0x14001d66f  call    cs:__imp_IoFreeIrp
0x14001d676  nop     dword ptr [rax+rax+00h]
0x14001d67b  test    r14, r14
0x14001d67e  jz      short loc_14001D68F
0x14001d680  mov     rcx, r14; Irp
0x14001d683  call    cs:__imp_IoFreeIrp
0x14001d68a  nop     dword ptr [rax+rax+00h]
0x14001d68f  mov     eax, ebx
0x14001d691  add     rsp, 28h
0x14001d695  pop     r15
0x14001d697  pop     r14
0x14001d699  pop     r13
0x14001d69b  pop     r12
0x14001d69d  pop     rdi
0x14001d69e  pop     rsi
0x14001d69f  pop     rbp
0x14001d6a0  pop     rbx
0x14001d6a1  retn
0x14001d6a3  mov     cl, [r13+4Ch]
0x14001d6a7  xor     edx, edx; ChargeQuota
0x14001d6a9  inc     cl; StackSize
0x14001d6ab  call    cs:__imp_IoAllocateIrp
0x14001d6b2  nop     dword ptr [rax+rax+00h]
0x14001d6b7  mov     r14, rax
0x14001d6ba  test    rax, rax
0x14001d6bd  jnz     short loc_14001D6D2
0x14001d6bf  xor     ecx, ecx; P
0x14001d6c1  call    cs:__imp_ExFreePool
0x14001d6c8  nop     dword ptr [rax+rax+00h]
0x14001d6cd  jmp     loc_14001D644
0x14001d6d2  dec     byte ptr [rax+43h]
0x14001d6d5  lea     rcx, BthEnumEnumerateProtocolOrDevice
0x14001d6dc  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001d6e4  xor     r8d, r8d
0x14001d6e7  mov     rax, [rsi+0B8h]
0x14001d6ee  mov     rdx, rsi; Irp
0x14001d6f1  mov     [rdi+28h], rcx
0x14001d6f5  lea     rcx, BthEnumEnumerateWWSettings
0x14001d6fc  mov     [rdi+30h], rcx
0x14001d700  lea     rcx, BthEnumEnumerateFlags
0x14001d707  mov     [rdi+40h], rcx
0x14001d70b  lea     rcx, GUID_BTHDDI_ENUMERATOR_INTERFACE
0x14001d712  mov     [rdi+20h], r13
0x14001d716  mov     dword ptr [rdi+38h], 0
0x14001d71d  mov     [rax-40h], rcx
0x14001d721  mov     word ptr [rax-48h], 81Bh
0x14001d727  mov     dword ptr [rax-38h], 2000048h
0x14001d72e  mov     [rax-30h], rdi
0x14001d732  mov     qword ptr [rax-28h], 0
0x14001d73a  mov     dword ptr [rsi+30h], 0C00000BBh
0x14001d741  mov     rcx, [r15+18h]; DeviceObject
0x14001d745  call    WaitForLowerDriverToCompleteIrp
0x14001d74a  xor     edx, edx
0x14001d74c  mov     ebx, eax
0x14001d74e  test    eax, eax
0x14001d750  js      loc_14001D649
0x14001d756  mov     [r15+0E8h], rdi
0x14001d75d  lea     rcx, BthEnumEnumerateProtocolOrDevice
0x14001d764  mov     rax, [r14+0B8h]
0x14001d76b  xor     r8d, r8d
0x14001d76e  mov     [rbp+28h], rcx
0x14001d772  lea     rcx, GUID_BTHDDI_ENUMERATOR_INTERFACE
0x14001d779  mov     [rbp+30h], rdx
0x14001d77d  mov     [rbp+40h], rdx
0x14001d781  mov     [rbp+20h], r13
0x14001d785  mov     dword ptr [rbp+38h], 2
0x14001d78c  mov     [rax-28h], rdx
0x14001d790  mov     rdx, r14; Irp
0x14001d793  mov     word ptr [rax-48h], 81Bh
0x14001d799  mov     [rax-40h], rcx
0x14001d79d  mov     dword ptr [rax-38h], 2000048h
0x14001d7a4  mov     [rax-30h], rbp
0x14001d7a8  mov     dword ptr [r14+30h], 0C00000BBh
0x14001d7b0  mov     rcx, [r15+18h]; DeviceObject
0x14001d7b4  call    WaitForLowerDriverToCompleteIrp
0x14001d7b9  mov     ebx, eax
0x14001d7bb  test    eax, eax
0x14001d7bd  js      loc_14001D649
0x14001d7c3  mov     [r15+0F0h], rbp
0x14001d7ca  jmp     loc_14001D66C
```
