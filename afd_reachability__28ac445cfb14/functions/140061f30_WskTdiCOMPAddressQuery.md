# WskTdiCOMPAddressQuery

- ea: `0x140061f30`
- end: `0x140062005`
- name: `WskTdiCOMPAddressQuery`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x140005b60`
- `0x140061f30`
- `0x140072800`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140061f67`
- `ntoskrnl!IoFreeIrp` at `0x140061f67`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061fca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061fca`
- `ntoskrnl!IoFreeMdl` at `0x140061f54`
- `ntoskrnl!IoFreeMdl` at `0x140061f54`
- `ntoskrnl!IofCompleteRequest` at `0x140061fe6`
- `ntoskrnl!IofCompleteRequest` at `0x140061fe6`

## pseudocode

```c
__int64 __fastcall WskTdiCOMPAddressQuery(__int64 a1, IRP *a2, IRP *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned __int16 v6; // bp
  unsigned __int16 *QuadPart; // r14
  int Status; // r15d
  UCHAR v9; // al
  PUNICODE_STRING FileName; // rcx
  __int64 v11; // r8

  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  v6 = 0;
  QuadPart = (unsigned __int16 *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  IoFreeMdl(a2->MdlAddress);
  Status = a2->IoStatus.Status;
  IoFreeIrp(a2);
  if ( Status >= 0 )
  {
    v9 = SOCKADDR_SIZE(*(_WORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 184));
    FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
    v6 = v9;
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 40) + 16LL) & 0x10) != 0 )
      IN6ADDR_SETV4MAPPED(FileName, QuadPart + 11, 0, QuadPart[10]);
    else
      memmove(FileName, QuadPart + 9, v9);
  }
  ExFreeToNPagedLookasideList(&stru_1400877C0, QuadPart);
  a3->IoStatus.Information = v6;
  a3->IoStatus.Status = Status;
  IofCompleteRequest(a3, 2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140061f30  push    rbx
0x140061f32  push    rbp
0x140061f33  push    rsi
0x140061f34  push    rdi
0x140061f35  push    r14
0x140061f37  push    r15
0x140061f39  sub     rsp, 28h
0x140061f3d  mov     rsi, [r8+0B8h]
0x140061f44  mov     rdi, r8
0x140061f47  mov     rcx, [rdx+8]; Mdl
0x140061f4b  mov     rbx, rdx
0x140061f4e  xor     ebp, ebp
0x140061f50  mov     r14, [rsi+18h]
0x140061f54  call    cs:__imp_IoFreeMdl
0x140061f5b  nop     dword ptr [rax+rax+00h]
0x140061f60  mov     r15d, [rbx+30h]
0x140061f64  mov     rcx, rbx; Irp
0x140061f67  call    cs:__imp_IoFreeIrp
0x140061f6e  nop     dword ptr [rax+rax+00h]
0x140061f73  test    r15d, r15d
0x140061f76  js      short loc_140061FC0
0x140061f78  mov     r8, [rsi+8]
0x140061f7c  movzx   ecx, word ptr [r8+0B8h]; af
0x140061f84  call    SOCKADDR_SIZE
0x140061f89  mov     rcx, [rsi+10h]; void *
0x140061f8d  movzx   edx, al
0x140061f90  mov     rax, [r8+28h]
0x140061f94  movzx   ebp, dx
0x140061f97  mov     r8d, [rax+10h]
0x140061f9b  test    r8b, 10h
0x140061f9f  jnz     short loc_140061FAF
0x140061fa1  mov     r8d, edx; Size
0x140061fa4  lea     rdx, [r14+12h]; Src
0x140061fa8  call    memmove
0x140061fad  jmp     short loc_140061FC0
0x140061faf  movzx   r9d, word ptr [r14+14h]
0x140061fb4  lea     rdx, [r14+16h]
0x140061fb8  xor     r8d, r8d
0x140061fbb  call    IN6ADDR_SETV4MAPPED
0x140061fc0  mov     rdx, r14; Entry
0x140061fc3  lea     rcx, stru_1400877C0; Lookaside
0x140061fca  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061fd1  nop     dword ptr [rax+rax+00h]
0x140061fd6  movzx   eax, bp
0x140061fd9  mov     dl, 2; PriorityBoost
0x140061fdb  mov     rcx, rdi; Irp
0x140061fde  mov     [rdi+38h], rax
0x140061fe2  mov     [rdi+30h], r15d
0x140061fe6  call    cs:__imp_IofCompleteRequest
0x140061fed  nop     dword ptr [rax+rax+00h]
0x140061ff2  mov     eax, 0C0000016h
0x140061ff7  add     rsp, 28h
0x140061ffb  pop     r15
0x140061ffd  pop     r14
0x140061fff  pop     rdi
0x140062000  pop     rsi
0x140062001  pop     rbp
0x140062002  pop     rbx
0x140062003  retn
```
