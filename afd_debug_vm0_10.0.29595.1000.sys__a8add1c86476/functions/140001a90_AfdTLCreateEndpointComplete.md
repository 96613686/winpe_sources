# AfdTLCreateEndpointComplete

- ea: `0x140001a90`
- end: `0x140001bac`
- name: `AfdTLCreateEndpointComplete`
- size: `284`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b920`

## callees

- `0x140001a90`
- `0x140001bb4`
- `0x140001d60`
- `0x14000f390`
- `0x14000f980`
- `0x140010670`
- `0x1400153d0`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140001ae4`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140001ae4`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140001b76`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140001b76`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140001b56`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140001b56`
- `ntoskrnl!IofCompleteRequest` at `0x140001b9b`
- `ntoskrnl!IofCompleteRequest` at `0x140001b9b`

## pseudocode

```c
void __fastcall AfdTLCreateEndpointComplete(PIRP Irp, NTSTATUS a2, __int64 a3, __int64 a4)
{
  PVOID FsContext; // rbx
  __int64 v7; // rcx
  __int64 Compartment; // rax
  struct _ERESOURCE *v9; // rcx
  unsigned int v10; // [rsp+38h] [rbp+10h] BYREF

  FsContext = Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( a2 >= 0 )
  {
    *((_DWORD *)FsContext + 64) = 1;
    *((_QWORD *)FsContext + 2) = a3;
    *((_QWORD *)FsContext + 3) = a4;
    *((_BYTE *)FsContext + 2) = 2;
    v10 = 0;
    if ( (int)AfdQueryCompartmentId(FsContext, &v10, a3) >= 0 )
    {
      ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
      Compartment = AfdGetCompartment(v10);
      v9 = AfdGlobalData;
      *((_QWORD *)FsContext + 11) = Compartment;
      ExReleaseResourceAndLeaveCriticalRegion(v9);
    }
  }
  else
  {
    AfdTlDereferenceTransport(*((_QWORD *)FsContext + 34));
    *((_QWORD *)FsContext + 34) = 0;
    AfdDereferenceEndpoint(FsContext);
  }
  v7 = *((_QWORD *)FsContext + 5);
  if ( v7 )
  {
    ObDereferenceSecurityDescriptor(v7, 1);
    *((_QWORD *)FsContext + 5) = 0;
  }
  _InterlockedExchange((volatile __int32 *)FsContext + 92, 0);
  Irp->IoStatus.Status = a2;
  if ( (unsigned __int8)AfdTLCompleteRequest(Irp) )
  {
    AfdCompleteTLEndpCreate(FsContext, Irp);
    IofCompleteRequest(Irp, AfdPriorityBoost);
  }
}

```

## disassembly

```asm
0x140001a90  mov     [rsp+arg_0], rbx
0x140001a95  mov     [rsp+arg_10], rsi
0x140001a9a  push    rdi
0x140001a9b  sub     rsp, 20h
0x140001a9f  mov     rax, [rcx+0B8h]
0x140001aa6  mov     esi, edx
0x140001aa8  mov     rdi, rcx
0x140001aab  mov     r10, [rax+30h]
0x140001aaf  mov     rbx, [r10+18h]
0x140001ab3  test    edx, edx
0x140001ab5  jns     short loc_140001B20
0x140001ab7  mov     rcx, [rbx+110h]
0x140001abe  call    AfdTlDereferenceTransport
0x140001ac3  mov     rcx, rbx
0x140001ac6  mov     qword ptr [rbx+110h], 0
0x140001ad1  call    AfdDereferenceEndpoint
0x140001ad6  mov     rcx, [rbx+28h]
0x140001ada  test    rcx, rcx
0x140001add  jz      short loc_140001AF8
0x140001adf  mov     edx, 1
0x140001ae4  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140001aeb  nop     dword ptr [rax+rax+00h]
0x140001af0  mov     qword ptr [rbx+28h], 0
0x140001af8  xor     eax, eax
0x140001afa  mov     rcx, rdi
0x140001afd  xchg    eax, [rbx+170h]
0x140001b03  mov     [rdi+30h], esi
0x140001b06  call    AfdTLCompleteRequest
0x140001b0b  test    al, al
0x140001b0d  jnz     short loc_140001B87
0x140001b0f  mov     rbx, [rsp+28h+arg_0]
0x140001b14  mov     rsi, [rsp+28h+arg_10]
0x140001b19  add     rsp, 20h
0x140001b1d  pop     rdi
0x140001b1e  retn
0x140001b20  lea     rdx, [rsp+28h+arg_8]
0x140001b25  mov     dword ptr [rbx+100h], 1
0x140001b2f  mov     rcx, rbx
0x140001b32  mov     [rbx+10h], r8
0x140001b36  mov     [rbx+18h], r9
0x140001b3a  mov     byte ptr [rbx+2], 2
0x140001b3e  mov     [rsp+28h+arg_8], 0
0x140001b46  call    AfdQueryCompartmentId
0x140001b4b  test    eax, eax
0x140001b4d  js      short loc_140001AD6
0x140001b4f  mov     rcx, cs:AfdGlobalData; Resource
0x140001b56  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140001b5d  nop     dword ptr [rax+rax+00h]
0x140001b62  mov     ecx, [rsp+28h+arg_8]
0x140001b66  call    AfdGetCompartment
0x140001b6b  mov     rcx, cs:AfdGlobalData; Resource
0x140001b72  mov     [rbx+58h], rax
0x140001b76  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140001b7d  nop     dword ptr [rax+rax+00h]
0x140001b82  jmp     loc_140001AD6
0x140001b87  mov     rdx, rdi
0x140001b8a  mov     rcx, rbx
0x140001b8d  call    AfdCompleteTLEndpCreate
0x140001b92  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140001b98  mov     rcx, rdi; Irp
0x140001b9b  call    cs:__imp_IofCompleteRequest
0x140001ba2  nop     dword ptr [rax+rax+00h]
0x140001ba7  jmp     loc_140001B0F
```
