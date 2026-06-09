# BfspCleanupRecoveryStore

- ea: `0x140004f9c`
- end: `0x1400050f9`
- name: `BfspCleanupRecoveryStore`
- size: `349`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003d30`

## callees

- `0x140004828`
- `0x140004f9c`
- `0x140007e20`
- `0x14000e628`
- `0x14001a8c4`
- `0x14001bb00`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140004ffc`
- `msvcrt!swprintf_s` at `0x140004ffc`
- `ntdll!RtlInitUnicodeString` at `0x14000500c`
- `ntdll!RtlInitUnicodeString` at `0x14000500c`

## string_xrefs

- `0x14000501c`: `Opening recovery store from %ws`
- `0x140005047`: `Failed to open recovery store %ws. Status = [%x]`

## pseudocode

```c
__int64 BfspCleanupRecoveryStore()
{
  __int64 v1; // r8
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // [rsp+40h] [rbp-248h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-240h] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-228h] BYREF

  DestinationString = 0;
  v6 = 0;
  if ( !byte_14003F8F8 )
    return 0;
  swprintf_s(Buffer, 0x104u, L"%s%s", Src, L"\\EFI\\Microsoft\\Recovery\\BCD");
  RtlInitUnicodeString(&DestinationString, Buffer);
  BfspLogMessage(2, L"Opening recovery store from %ws", Buffer);
  v2 = BiOpenStoreWithHash(&DestinationString, 0, v1, &v6);
  v3 = v2;
  if ( v2 >= 0 )
  {
    BfspLogMessage(2, L"Reducing duplicate winre entries.");
    v4 = BfspReduceDuplicateObjects(
           v6,
           (unsigned int)CompareElementListRecovery,
           6,
           270532611,
           (__int64)&ReferenceElementListRecovery);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v5 = BfspCleanupAdditionalOptions(v6);
      v3 = v5;
      if ( v5 < 0 )
        BfspLogMessage(4, L"Failed to cleanup ramdisk options in recovery store. Status = [%x]", (unsigned int)v5);
    }
    else
    {
      BfspLogMessage(4, L"Failed to reduce winre entries in recovery store. Status = [%x]", (unsigned int)v4);
    }
  }
  else
  {
    BfspLogMessage(4, L"Failed to open recovery store %ws. Status = [%x]", Buffer, (unsigned int)v2);
  }
  if ( v6 )
    BcdCloseStore(v6);
  return v3;
}

```

## disassembly

```asm
0x140004f9c  push    rbx
0x140004f9e  sub     rsp, 280h
0x140004fa5  mov     rax, cs:__security_cookie
0x140004fac  xor     rax, rsp
0x140004faf  mov     [rsp+288h+var_18], rax
0x140004fb7  cmp     cs:byte_14003F8F8, 0
0x140004fbe  xorps   xmm0, xmm0
0x140004fc1  movups  xmmword ptr [rsp+288h+DestinationString.Length], xmm0
0x140004fc6  mov     [rsp+288h+var_248], 0
0x140004fcf  jnz     short loc_140004FD8
0x140004fd1  xor     eax, eax
0x140004fd3  jmp     loc_1400050E0
0x140004fd8  mov     r9, cs:Src
0x140004fdf  lea     rax, aEfiMicrosoftRe_0; "\\EFI\\Microsoft\\Recovery\\BCD"
0x140004fe6  lea     r8, aSS_0; "%s%s"
0x140004fed  mov     [rsp+288h+var_268], rax
0x140004ff2  mov     edx, 104h; BufferCount
0x140004ff7  lea     rcx, [rsp+288h+Buffer]; Buffer
0x140004ffc  call    cs:__imp_swprintf_s
0x140005002  lea     rdx, [rsp+288h+Buffer]; SourceString
0x140005007  lea     rcx, [rsp+288h+DestinationString]; DestinationString
0x14000500c  call    cs:__imp_RtlInitUnicodeString
0x140005012  lea     r8, [rsp+288h+Buffer]
0x140005017  mov     ecx, 2
0x14000501c  lea     rdx, aOpeningRecover; "Opening recovery store from %ws"
0x140005023  call    BfspLogMessage
0x140005028  lea     r9, [rsp+288h+var_248]
0x14000502d  xor     edx, edx
0x14000502f  lea     rcx, [rsp+288h+DestinationString]
0x140005034  call    BiOpenStoreWithHash
0x140005039  mov     ebx, eax
0x14000503b  test    eax, eax
0x14000503d  jns     short loc_14000505A
0x14000503f  mov     r9d, eax
0x140005042  lea     r8, [rsp+288h+Buffer]
0x140005047  lea     rdx, aFailedToOpenRe_0; "Failed to open recovery store %ws. Stat"...
0x14000504e  mov     ecx, 4
0x140005053  call    BfspLogMessage
0x140005058  jmp     short loc_1400050CC
0x14000505a  lea     rdx, aReducingDuplic; "Reducing duplicate winre entries."
0x140005061  mov     ecx, 2
0x140005066  call    BfspLogMessage
0x14000506b  mov     rcx, [rsp+288h+var_248]
0x140005070  lea     rax, ReferenceElementListRecovery
0x140005077  mov     [rsp+288h+var_258], 0
0x14000507c  lea     rdx, CompareElementListRecovery
0x140005083  mov     r9d, 10200003h
0x140005089  mov     [rsp+288h+var_268], rax
0x14000508e  mov     r8d, 6
0x140005094  call    BfspReduceDuplicateObjects
0x140005099  mov     ebx, eax
0x14000509b  test    eax, eax
0x14000509d  jns     short loc_1400050A8
0x14000509f  lea     rdx, aFailedToReduce_0; "Failed to reduce winre entries in recov"...
0x1400050a6  jmp     short loc_1400050BF
0x1400050a8  mov     rcx, [rsp+288h+var_248]
0x1400050ad  call    BfspCleanupAdditionalOptions
0x1400050b2  mov     ebx, eax
0x1400050b4  test    eax, eax
0x1400050b6  jns     short loc_1400050CC
0x1400050b8  lea     rdx, aFailedToCleanu; "Failed to cleanup ramdisk options in re"...
0x1400050bf  mov     r8d, eax
0x1400050c2  mov     ecx, 4
0x1400050c7  call    BfspLogMessage
0x1400050cc  cmp     [rsp+288h+var_248], 0
0x1400050d2  jz      short loc_1400050DE
0x1400050d4  mov     rcx, [rsp+288h+var_248]
0x1400050d9  call    BcdCloseStore
0x1400050de  mov     eax, ebx
0x1400050e0  mov     rcx, [rsp+288h+var_18]
0x1400050e8  xor     rcx, rsp; StackCookie
0x1400050eb  call    __security_check_cookie
0x1400050f0  add     rsp, 280h
0x1400050f7  pop     rbx
0x1400050f8  retn
```
