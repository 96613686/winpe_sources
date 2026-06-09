# BfspCleanupHypervisorSettings

- ea: `0x18004e30c`
- end: `0x18004e37b`
- name: `BfspCleanupHypervisorSettings`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004d7e4`

## callees

- `0x18004cdd4`
- `0x18004e30c`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18004e36d`
- `bcd!BcdCloseObject` at `0x18004e36d`
- `bcd!BcdOpenObject` at `0x18004e347`
- `bcd!BcdOpenObject` at `0x18004e347`
- `bcd!BcdDeleteElement` at `0x18004e35d`
- `bcd!BcdDeleteElement` at `0x18004e35d`

## pseudocode

```c
__int64 __fastcall BfspCleanupHypervisorSettings(__int64 a1)
{
  int v2; // ebx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  BfspLogMessage(2, L"Cleaning up hypervisor settings.");
  v4 = 0;
  v2 = BcdOpenObject(a1, &GUID_HYPERVISOR_SETTINGS_GROUP, &v4);
  if ( v2 >= 0 )
    BcdDeleteElement(v4, 369098763);
  if ( v4 )
    BcdCloseObject(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004e30c  push    rbx
0x18004e30e  sub     rsp, 20h
0x18004e312  mov     rbx, rcx
0x18004e315  mov     [rsp+28h+arg_8], 0
0x18004e31e  mov     ecx, 2
0x18004e323  lea     rdx, aCleaningUpHype; "Cleaning up hypervisor settings."
0x18004e32a  call    BfspLogMessage
0x18004e32f  lea     r8, [rsp+28h+arg_8]
0x18004e334  mov     [rsp+28h+arg_8], 0
0x18004e33d  lea     rdx, GUID_HYPERVISOR_SETTINGS_GROUP
0x18004e344  mov     rcx, rbx
0x18004e347  call    cs:__imp_BcdOpenObject
0x18004e34d  mov     ebx, eax
0x18004e34f  test    eax, eax
0x18004e351  js      short loc_18004E363
0x18004e353  mov     rcx, [rsp+28h+arg_8]
0x18004e358  mov     edx, 1600000Bh
0x18004e35d  call    cs:__imp_BcdDeleteElement
0x18004e363  mov     rcx, [rsp+28h+arg_8]
0x18004e368  test    rcx, rcx
0x18004e36b  jz      short loc_18004E373
0x18004e36d  call    cs:__imp_BcdCloseObject
0x18004e373  mov     eax, ebx
0x18004e375  add     rsp, 20h
0x18004e379  pop     rbx
0x18004e37a  retn
```
