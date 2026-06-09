# BthEnumWmi

- ea: `0x14001db10`
- end: `0x14001db9b`
- name: `BthEnumWmi`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001db10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001db86`
- `ntoskrnl!IofCompleteRequest` at `0x14001db86`
- `ntoskrnl!IofCallDriver` at `0x14001db65`
- `ntoskrnl!IofCallDriver` at `0x14001db65`

## pseudocode

```c
__int64 __fastcall BthEnumWmi(__int64 a1, IRP *a2)
{
  PDEVICE_OBJECT *v2; // rcx
  int v4; // edx
  unsigned __int64 v5; // rax
  __int64 v6; // r9
  unsigned int Status; // ebx

  v2 = *(PDEVICE_OBJECT **)(a1 + 64);
  v4 = *(_DWORD *)v2;
  if ( *(_DWORD *)v2 == 542065744
    || (v5 = (unsigned int)(v4 - 1329877060), (unsigned int)v5 <= 0x34)
    && (v6 = 0x10000000010001LL, _bittest64(&v6, v5))
    || v4 == 1146115192
    || v4 == 1146111096 )
  {
    Status = a2->IoStatus.Status;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return (unsigned int)IofCallDriver(v2[3], a2);
  }
  return Status;
}

```

## disassembly

```asm
0x14001db10  push    rbx
0x14001db12  sub     rsp, 20h
0x14001db16  mov     rcx, [rcx+40h]
0x14001db1a  mov     r8, rdx
0x14001db1d  mov     edx, [rcx]
0x14001db1f  cmp     edx, 204F4450h
0x14001db25  jz      short loc_14001DB75
0x14001db27  lea     eax, [rdx-4F445044h]
0x14001db2d  cmp     eax, 34h ; '4'
0x14001db30  ja      short loc_14001DB42
0x14001db32  mov     r9, 10000000010001h
0x14001db3c  bt      r9, rax
0x14001db40  jb      short loc_14001DB75
0x14001db42  cmp     edx, 44505478h
0x14001db48  jz      short loc_14001DB75
0x14001db4a  cmp     edx, 44504478h
0x14001db50  jz      short loc_14001DB75
0x14001db52  inc     byte ptr [r8+43h]
0x14001db56  mov     rdx, r8; Irp
0x14001db59  add     qword ptr [r8+0B8h], 48h ; 'H'
0x14001db61  mov     rcx, [rcx+18h]; DeviceObject
0x14001db65  call    cs:__imp_IofCallDriver
0x14001db6c  nop     dword ptr [rax+rax+00h]
0x14001db71  mov     ebx, eax
0x14001db73  jmp     short loc_14001DB92
0x14001db75  mov     ebx, [r8+30h]
0x14001db79  xor     edx, edx; PriorityBoost
0x14001db7b  mov     rcx, r8; Irp
0x14001db7e  mov     qword ptr [r8+38h], 0
0x14001db86  call    cs:__imp_IofCompleteRequest
0x14001db8d  nop     dword ptr [rax+rax+00h]
0x14001db92  mov     eax, ebx
0x14001db94  add     rsp, 20h
0x14001db98  pop     rbx
0x14001db99  retn
```
