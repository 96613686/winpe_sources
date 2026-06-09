# WskTdiCOMPAddressQuery

- ea: `0x1400620d0`
- end: `0x1400621a5`
- name: `WskTdiCOMPAddressQuery`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x140005b60`
- `0x1400620d0`
- `0x140072980`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140062107`
- `ntoskrnl!IoFreeIrp` at `0x140062107`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006216a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006216a`
- `ntoskrnl!IoFreeMdl` at `0x1400620f4`
- `ntoskrnl!IoFreeMdl` at `0x1400620f4`
- `ntoskrnl!IofCompleteRequest` at `0x140062186`
- `ntoskrnl!IofCompleteRequest` at `0x140062186`

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
0x1400620d0  push    rbx
0x1400620d2  push    rbp
0x1400620d3  push    rsi
0x1400620d4  push    rdi
0x1400620d5  push    r14
0x1400620d7  push    r15
0x1400620d9  sub     rsp, 28h
0x1400620dd  mov     rsi, [r8+0B8h]
0x1400620e4  mov     rdi, r8
0x1400620e7  mov     rcx, [rdx+8]; Mdl
0x1400620eb  mov     rbx, rdx
0x1400620ee  xor     ebp, ebp
0x1400620f0  mov     r14, [rsi+18h]
0x1400620f4  call    cs:__imp_IoFreeMdl
0x1400620fb  nop     dword ptr [rax+rax+00h]
0x140062100  mov     r15d, [rbx+30h]
0x140062104  mov     rcx, rbx; Irp
0x140062107  call    cs:__imp_IoFreeIrp
0x14006210e  nop     dword ptr [rax+rax+00h]
0x140062113  test    r15d, r15d
0x140062116  js      short loc_140062160
0x140062118  mov     r8, [rsi+8]
0x14006211c  movzx   ecx, word ptr [r8+0B8h]; af
0x140062124  call    SOCKADDR_SIZE
0x140062129  mov     rcx, [rsi+10h]; void *
0x14006212d  movzx   edx, al
0x140062130  mov     rax, [r8+28h]
0x140062134  movzx   ebp, dx
0x140062137  mov     r8d, [rax+10h]
0x14006213b  test    r8b, 10h
0x14006213f  jnz     short loc_14006214F
0x140062141  mov     r8d, edx; Size
0x140062144  lea     rdx, [r14+12h]; Src
0x140062148  call    memmove
0x14006214d  jmp     short loc_140062160
0x14006214f  movzx   r9d, word ptr [r14+14h]
0x140062154  lea     rdx, [r14+16h]
0x140062158  xor     r8d, r8d
0x14006215b  call    IN6ADDR_SETV4MAPPED
0x140062160  mov     rdx, r14; Entry
0x140062163  lea     rcx, stru_1400877C0; Lookaside
0x14006216a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062171  nop     dword ptr [rax+rax+00h]
0x140062176  movzx   eax, bp
0x140062179  mov     dl, 2; PriorityBoost
0x14006217b  mov     rcx, rdi; Irp
0x14006217e  mov     [rdi+38h], rax
0x140062182  mov     [rdi+30h], r15d
0x140062186  call    cs:__imp_IofCompleteRequest
0x14006218d  nop     dword ptr [rax+rax+00h]
0x140062192  mov     eax, 0C0000016h
0x140062197  add     rsp, 28h
0x14006219b  pop     r15
0x14006219d  pop     r14
0x14006219f  pop     rdi
0x1400621a0  pop     rsi
0x1400621a1  pop     rbp
0x1400621a2  pop     rbx
0x1400621a3  retn
```
