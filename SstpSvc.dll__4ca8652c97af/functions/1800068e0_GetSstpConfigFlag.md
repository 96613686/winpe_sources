# GetSstpConfigFlag

- ea: `0x1800068e0`
- end: `0x180006926`
- name: `GetSstpConfigFlag`
- size: `70`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180005280`
- `0x18000a620`
- `0x1800138c0`
- `0x180014170`
- `0x180014490`
- `0x180014840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800068f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800068f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006918`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006918`

## pseudocode

```c
_BOOL8 __fastcall GetSstpConfigFlag(int a1)
{
  BOOL v2; // ebx

  AcquireSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  v2 = (a1 & *((_DWORD *)SstpSvcGlobals + 194)) != 0;
  ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  return v2;
}

```

## disassembly

```asm
0x1800068e0  push    rbx
0x1800068e2  sub     rsp, 20h
0x1800068e6  mov     ebx, ecx
0x1800068e8  mov     rcx, cs:SstpSvcGlobals
0x1800068ef  add     rcx, 300h; SRWLock
0x1800068f6  call    cs:__imp_AcquireSRWLockShared
0x1800068fc  mov     rcx, cs:SstpSvcGlobals
0x180006903  test    [rcx+308h], ebx
0x180006909  mov     ebx, 0
0x18000690e  setnz   bl
0x180006911  add     rcx, 300h; SRWLock
0x180006918  call    cs:__imp_ReleaseSRWLockShared
0x18000691e  mov     eax, ebx
0x180006920  add     rsp, 20h
0x180006924  pop     rbx
0x180006925  retn
```
