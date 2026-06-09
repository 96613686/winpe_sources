# BfsCleanupBcdStore

- ea: `0x140003d30`
- end: `0x14000407a`
- name: `BfsCleanupBcdStore`
- size: `842`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001bc8`

## callees

- `0x140003d30`
- `0x140004828`
- `0x140004a60`
- `0x140004e20`
- `0x140004e98`
- `0x140004f9c`
- `0x14000636c`
- `0x1400064c0`
- `0x140006cd8`
- `0x140007e20`
- `0x140008104`
- `0x140008400`
- `0x14000e578`
- `0x14000e5c8`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x1400140c4`
- `0x14001a8c4`
- `0x14001ac80`
- `0x14001bb00`
- `0x140026650`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140004043`
- `KERNEL32!SetLastError` at `0x140004043`
- `ntdll!RtlNtStatusToDosError` at `0x14000403b`
- `ntdll!RtlNtStatusToDosError` at `0x14000403b`

## string_xrefs

- `0x140003e47`: `Attempting to enumerate objects`
- `0x140003f16`: `Failed to delete duplicate winloads. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfsCleanupBcdStore(unsigned int a1)
{
  int v2; // esi
  char v3; // r13
  NTSTATUS Object; // edi
  int v5; // eax
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r14d
  __int64 v12; // rsi
  __int64 v13; // r12
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  ULONG v18; // eax
  unsigned int v20; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+60h] [rbp-20h] BYREF

  v20 = 0;
  v21 = 0;
  Handle = 0;
  v2 = a1 & 0x10000;
  v24 = 0;
  BfspLogInitialize((a1 & 8) == 0 ? 3 : 0);
  BfspLogMessage(2, L"BfsCleanupBcdStore flags(0x%x)", a1);
  v3 = a1 | 4;
  Object = BfspInitializeGlobalState(0);
  if ( Object >= 0 )
  {
    v5 = BfspCleanupRecoveryStore();
    if ( v5 < 0 )
      BfspLogMessage(3, L"Failed to cleanup recovery store. Status = [%x]", (unsigned int)v5);
    v7 = BiOpenStoreWithHash(0, 0, v6, &v21);
    v8 = v21;
    Object = v7;
    if ( v7 >= 0 )
    {
      Object = BcdOpenObject(v21, &GUID_CURRENT_BOOT_ENTRY, &Handle);
      if ( Object >= 0 )
      {
        Object = BcdQueryObject((__int64)Handle, v9, v10, (__int64)&v24);
        if ( Object >= 0 )
        {
          if ( v2 )
          {
            v23 = 0;
            BfspLogMessage(2, L"Attempting to enumerate objects");
            v21 = 0x1020000300000001LL;
            Object = BfspEnumerateObjects(v8, &v21, &v20, &v23);
            if ( Object >= 0 )
            {
              v11 = v20;
              BfspLogMessage(2, L"Allocated %lu objects.", v20);
              v12 = 0;
              if ( v11 )
              {
                v13 = v23;
                do
                {
                  if ( *(_OWORD *)(v13 + 24 * v12) == v24 )
                    BfspLogMessage(2, L"Skipping current entry");
                  else
                    Object = BfspRemoveInvalidBcdEntry(v8);
                  v12 = (unsigned int)(v12 + 1);
                }
                while ( (unsigned int)v12 < v11 );
              }
            }
            else
            {
              BfspLogMessage(4, L"Failed to enumerate objects");
            }
          }
          v14 = BfspRemoveDuplicateEntries(v8, &v24);
          if ( v14 < 0 )
            BfspLogMessage(2, L"Failed to delete duplicate winloads. Status = [%x]", (unsigned int)v14);
          BfspLogMessage(2, L"Reducing duplicate resume entries.");
          v15 = BfspReduceDuplicateObjects(
                  v8,
                  (unsigned int)CompareElementListResume,
                  3,
                  270532612,
                  (__int64)ReferenceElementListResume);
          if ( v15 < 0
            || (BfspLogMessage(2, L"Reducing duplicate winre entries."),
                v15 = BfspReduceDuplicateObjects(
                        v8,
                        (unsigned int)CompareElementListRecovery,
                        6,
                        270532611,
                        (__int64)&ReferenceElementListRecovery),
                v15 < 0) )
          {
            BfspLogMessage(
              2,
              L"Failed to reduce duplicate resume and recovery objects. Status = [%x]",
              (unsigned int)v15);
          }
          v16 = BfspCleanupAdditionalOptions(v8);
          if ( v16 < 0 )
            BfspLogMessage(2, L"Failed to cleanup ramdisk options. Status = [%x]", (unsigned int)v16);
          if ( (v3 & 0x20) != 0 )
            BfspCleanupNtldrSettings(v8);
          BfspCleanupDebuggerSettings(v8);
          BfspCleanupHypervisorSettings(v8);
          v17 = BcdFlushStore(v8);
          if ( v17 < 0 )
            BfspLogMessage(3, L"Failed to flush the BCD to disk. Status = [%x]", (unsigned int)v17);
        }
      }
      if ( Handle )
        BcdCloseObject(Handle);
    }
    if ( v8 )
      BcdCloseStore(v8);
    BfspDestroyGlobalState();
  }
  BfspLogDestroy();
  if ( Object >= 0 )
    return 1;
  v18 = RtlNtStatusToDosError(Object);
  SetLastError(v18);
  return 0;
}

```

## disassembly

```asm
0x140003d30  mov     [rsp-28h+arg_8], rbx
0x140003d35  mov     [rsp-28h+arg_10], rsi
0x140003d3a  push    rbp
0x140003d3b  push    rdi
0x140003d3c  push    r12
0x140003d3e  push    r13
0x140003d40  push    r14
0x140003d42  mov     rbp, rsp
0x140003d45  sub     rsp, 80h
0x140003d4c  mov     rax, cs:__security_cookie
0x140003d53  xor     rax, rsp
0x140003d56  mov     [rbp+var_10], rax
0x140003d5a  mov     esi, ecx
0x140003d5c  mov     [rbp+var_3C], 0
0x140003d63  mov     eax, ecx
0x140003d65  mov     [rbp+var_38], 0
0x140003d6d  mov     r13d, ecx
0x140003d70  mov     [rbp+Handle], 0
0x140003d78  and     esi, 10000h
0x140003d7e  xorps   xmm0, xmm0
0x140003d81  movups  [rbp+var_20], xmm0
0x140003d85  setnz   r14b
0x140003d89  and     al, 8
0x140003d8b  neg     al
0x140003d8d  mov     [rbp+var_40], r14b
0x140003d91  sbb     ecx, ecx
0x140003d93  not     ecx
0x140003d95  and     ecx, 3
0x140003d98  call    BfspLogInitialize
0x140003d9d  mov     r12d, 2
0x140003da3  lea     rdx, aBfscleanupbcds; "BfsCleanupBcdStore flags(0x%x)"
0x140003daa  mov     ecx, r12d
0x140003dad  mov     r8d, r13d
0x140003db0  call    BfspLogMessage
0x140003db5  or      r13d, 4
0x140003db9  xor     r9d, r9d
0x140003dbc  mov     edx, r13d
0x140003dbf  xor     r8d, r8d
0x140003dc2  xor     ecx, ecx; Src
0x140003dc4  call    BfspInitializeGlobalState
0x140003dc9  mov     edi, eax
0x140003dcb  test    eax, eax
0x140003dcd  js      loc_140004030
0x140003dd3  call    BfspCleanupRecoveryStore
0x140003dd8  test    eax, eax
0x140003dda  jns     short loc_140003DF0
0x140003ddc  mov     r8d, eax
0x140003ddf  lea     rdx, aFailedToCleanu_0; "Failed to cleanup recovery store. Statu"...
0x140003de6  lea     ecx, [r12+1]
0x140003deb  call    BfspLogMessage
0x140003df0  lea     r9, [rbp+var_38]
0x140003df4  xor     edx, edx
0x140003df6  xor     ecx, ecx
0x140003df8  call    BiOpenStoreWithHash
0x140003dfd  mov     rbx, [rbp+var_38]
0x140003e01  mov     edi, eax
0x140003e03  test    eax, eax
0x140003e05  js      loc_14000401E
0x140003e0b  lea     r8, [rbp+Handle]
0x140003e0f  mov     rcx, rbx
0x140003e12  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x140003e19  call    BcdOpenObject
0x140003e1e  mov     edi, eax
0x140003e20  test    eax, eax
0x140003e22  js      loc_14000400E
0x140003e28  mov     rcx, [rbp+Handle]
0x140003e2c  lea     r9, [rbp+var_20]
0x140003e30  call    BcdQueryObject
0x140003e35  mov     edi, eax
0x140003e37  test    eax, eax
0x140003e39  js      loc_14000400E
0x140003e3f  test    esi, esi
0x140003e41  jz      loc_140003F03
0x140003e47  lea     rdx, aAttemptingToEn; "Attempting to enumerate objects"
0x140003e4e  mov     [rbp+var_28], 0
0x140003e56  mov     ecx, r12d
0x140003e59  call    BfspLogMessage
0x140003e5e  lea     r9, [rbp+var_28]
0x140003e62  mov     dword ptr [rbp+var_38], 1
0x140003e69  lea     r8, [rbp+var_3C]
0x140003e6d  mov     dword ptr [rbp+var_38+4], 10200003h
0x140003e74  lea     rdx, [rbp+var_38]
0x140003e78  mov     rcx, rbx
0x140003e7b  call    BfspEnumerateObjects
0x140003e80  mov     edi, eax
0x140003e82  test    eax, eax
0x140003e84  jns     short loc_140003E99
0x140003e86  lea     rdx, aFailedToEnumer; "Failed to enumerate objects"
0x140003e8d  mov     ecx, 4
0x140003e92  call    BfspLogMessage
0x140003e97  jmp     short loc_140003F03
0x140003e99  mov     r14d, [rbp+var_3C]
0x140003e9d  lea     rdx, aAllocatedLuObj; "Allocated %lu objects."
0x140003ea4  mov     r8d, r14d
0x140003ea7  mov     ecx, r12d
0x140003eaa  call    BfspLogMessage
0x140003eaf  xor     esi, esi
0x140003eb1  test    r14d, r14d
0x140003eb4  jz      short loc_140003EFF
0x140003eb6  mov     r12, [rbp+var_28]
0x140003eba  lea     rcx, [rsi+rsi*2]
0x140003ebe  lea     rdx, [r12+rcx*8]
0x140003ec2  mov     rax, [rdx]
0x140003ec5  cmp     rax, qword ptr [rbp+var_20]
0x140003ec9  jnz     short loc_140003EE8
0x140003ecb  mov     rax, [rdx+8]
0x140003ecf  cmp     rax, qword ptr [rbp+var_20+8]
0x140003ed3  jnz     short loc_140003EE8
0x140003ed5  lea     rdx, aSkippingCurren; "Skipping current entry"
0x140003edc  mov     ecx, 2
0x140003ee1  call    BfspLogMessage
0x140003ee6  jmp     short loc_140003EF2
0x140003ee8  mov     rcx, rbx
0x140003eeb  call    BfspRemoveInvalidBcdEntry
0x140003ef0  mov     edi, eax
0x140003ef2  inc     esi
0x140003ef4  cmp     esi, r14d
0x140003ef7  jb      short loc_140003EBA
0x140003ef9  mov     r12d, 2
0x140003eff  mov     r14b, [rbp+var_40]
0x140003f03  lea     rdx, [rbp+var_20]
0x140003f07  mov     rcx, rbx
0x140003f0a  call    BfspRemoveDuplicateEntries
0x140003f0f  test    eax, eax
0x140003f11  jns     short loc_140003F25
0x140003f13  mov     r8d, eax
0x140003f16  lea     rdx, aFailedToDelete_4; "Failed to delete duplicate winloads. St"...
0x140003f1d  mov     ecx, r12d
0x140003f20  call    BfspLogMessage
0x140003f25  lea     rdx, aReducingDuplic_0; "Reducing duplicate resume entries."
0x140003f2c  mov     ecx, r12d
0x140003f2f  call    BfspLogMessage
0x140003f34  lea     rax, ReferenceElementListResume
0x140003f3b  mov     [rsp+80h+var_50], r14b
0x140003f40  mov     esi, 3
0x140003f45  mov     [rsp+80h+var_60], rax
0x140003f4a  mov     r8d, esi
0x140003f4d  lea     rdx, CompareElementListResume
0x140003f54  mov     r9d, 10200004h
0x140003f5a  mov     rcx, rbx
0x140003f5d  call    BfspReduceDuplicateObjects
0x140003f62  test    eax, eax
0x140003f64  js      short loc_140003FA3
0x140003f66  lea     rdx, aReducingDuplic; "Reducing duplicate winre entries."
0x140003f6d  mov     ecx, r12d
0x140003f70  call    BfspLogMessage
0x140003f75  lea     rax, ReferenceElementListRecovery
0x140003f7c  mov     [rsp+80h+var_50], r14b
0x140003f81  mov     r9d, 10200003h
0x140003f87  mov     [rsp+80h+var_60], rax
0x140003f8c  lea     r8d, [rsi+3]
0x140003f90  mov     rcx, rbx
0x140003f93  lea     rdx, CompareElementListRecovery
0x140003f9a  call    BfspReduceDuplicateObjects
0x140003f9f  test    eax, eax
0x140003fa1  jns     short loc_140003FB5
0x140003fa3  mov     r8d, eax
0x140003fa6  lea     rdx, aFailedToReduce; "Failed to reduce duplicate resume and r"...
0x140003fad  mov     ecx, r12d
0x140003fb0  call    BfspLogMessage
0x140003fb5  mov     rcx, rbx
0x140003fb8  call    BfspCleanupAdditionalOptions
0x140003fbd  test    eax, eax
0x140003fbf  jns     short loc_140003FD3
0x140003fc1  mov     r8d, eax
0x140003fc4  lea     rdx, aFailedToCleanu_1; "Failed to cleanup ramdisk options. Stat"...
0x140003fcb  mov     ecx, r12d
0x140003fce  call    BfspLogMessage
0x140003fd3  test    r13b, 20h
0x140003fd7  jz      short loc_140003FE1
0x140003fd9  mov     rcx, rbx
0x140003fdc  call    BfspCleanupNtldrSettings
0x140003fe1  mov     rcx, rbx
0x140003fe4  call    BfspCleanupDebuggerSettings
0x140003fe9  mov     rcx, rbx
0x140003fec  call    BfspCleanupHypervisorSettings
0x140003ff1  mov     rcx, rbx
0x140003ff4  call    BcdFlushStore
0x140003ff9  test    eax, eax
0x140003ffb  jns     short loc_14000400E
0x140003ffd  mov     r8d, eax
0x140004000  lea     rdx, aFailedToFlushT; "Failed to flush the BCD to disk. Status"...
0x140004007  mov     ecx, esi
0x140004009  call    BfspLogMessage
0x14000400e  cmp     [rbp+Handle], 0
0x140004013  jz      short loc_14000401E
0x140004015  mov     rcx, [rbp+Handle]; Handle
0x140004019  call    BcdCloseObject
0x14000401e  test    rbx, rbx
0x140004021  jz      short loc_14000402B
0x140004023  mov     rcx, rbx
0x140004026  call    BcdCloseStore
0x14000402b  call    BfspDestroyGlobalState
0x140004030  call    BfspLogDestroy
0x140004035  test    edi, edi
0x140004037  jns     short loc_14000404D
0x140004039  mov     ecx, edi; Status
0x14000403b  call    cs:__imp_RtlNtStatusToDosError
0x140004041  mov     ecx, eax; dwErrCode
0x140004043  call    cs:__imp_SetLastError
0x140004049  xor     eax, eax
0x14000404b  jmp     short loc_140004052
0x14000404d  mov     eax, 1
0x140004052  mov     rcx, [rbp+var_10]
0x140004056  xor     rcx, rsp; StackCookie
0x140004059  call    __security_check_cookie
0x14000405e  lea     r11, [rsp+80h+var_s0]
0x140004066  mov     rbx, [r11+38h]
0x14000406a  mov     rsi, [r11+40h]
0x14000406e  mov     rsp, r11
0x140004071  pop     r14
0x140004073  pop     r13
0x140004075  pop     r12
0x140004077  pop     rdi
0x140004078  pop     rbp
0x140004079  retn
```
