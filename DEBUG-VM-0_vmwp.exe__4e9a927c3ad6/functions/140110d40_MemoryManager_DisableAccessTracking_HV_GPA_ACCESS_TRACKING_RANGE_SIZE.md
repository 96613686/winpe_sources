# MemoryManager::DisableAccessTracking(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE)

- ea: `0x140110d40`
- end: `0x140110e89`
- name: `?DisableAccessTracking@MemoryManager@@UEAAJW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1401071b0`

## callees

- `0x14002dd68`
- `0x140042240`
- `0x1400f2c70`
- `0x140110d40`
- `0x140111070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110db8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110e6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110db8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140110e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110e34`
- `vid!VidGpaAccessTrackingDisable` at `0x140110d9e`
- `vid!VidGpaAccessTrackingDisable` at `0x140110d9e`
- `vid!VidGpaAccessTrackingEnable` at `0x140110e14`
- `vid!VidGpaAccessTrackingEnable` at `0x140110e14`

## pseudocode

```c
__int64 __fastcall MemoryManager::DisableAccessTracking(_QWORD *a1, int a2)
{
  _QWORD *v2; // rsi
  int v5; // eax
  bool v6; // al
  __int64 v7; // rcx
  unsigned int v8; // ebx
  signed int v9; // eax
  signed int LastError; // eax
  _DWORD v12[6]; // [rsp+20h] [rbp-18h] BYREF

  v2 = a1 + 119;
  v12[0] = 0;
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 119));
  v5 = 1;
  if ( a2 != 2 )
    v5 = a2;
  --*((_DWORD *)a1 + v5 + 192);
  v6 = MemoryManager::CheckGetSmallestRegisteredRangeSize(
         (MemoryManager *)a1,
         (enum _HV_GPA_ACCESS_TRACKING_RANGE_SIZE *)v12);
  v7 = a1[2];
  if ( v6 )
  {
    if ( !(unsigned int)VidGpaAccessTrackingEnable(v7, v12[0]) && (unsigned int)VmlIsDebugTraceEnabled(16416) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      VmlDebugTraceWithError(16416, &off_1402C75A0, (unsigned int)LastError);
    }
    v8 = 0;
    *((_DWORD *)v2 + 2) = 0;
    goto LABEL_17;
  }
  if ( !(unsigned int)VidGpaAccessTrackingDisable(v7) )
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402DAC20, v8);
    *((_DWORD *)v2 + 2) = 0;
LABEL_17:
    ReleaseSRWLockExclusive((PSRWLOCK)v2);
    return v8;
  }
  *((_DWORD *)v2 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
  return 0;
}

```

## disassembly

```asm
0x140110d40  mov     [rsp+arg_8], rbx
0x140110d45  mov     [rsp+arg_10], rsi
0x140110d4a  push    rdi
0x140110d4b  sub     rsp, 30h
0x140110d4f  lea     rsi, [rcx+3B8h]
0x140110d56  mov     [rsp+38h+var_18], 0
0x140110d5e  mov     rdi, rcx
0x140110d61  mov     ebx, edx
0x140110d63  mov     rcx, rsi; this
0x140110d66  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140110d6b  mov     eax, 1
0x140110d70  lea     rdx, [rsp+38h+var_18]; enum _HV_GPA_ACCESS_TRACKING_RANGE_SIZE *
0x140110d75  cmp     ebx, 2
0x140110d78  cmovnz  eax, ebx
0x140110d7b  movsxd  rcx, eax
0x140110d7e  mov     eax, [rdi+rcx*4+300h]
0x140110d85  dec     eax
0x140110d87  mov     [rdi+rcx*4+300h], eax
0x140110d8e  mov     rcx, rdi; this
0x140110d91  call    ?CheckGetSmallestRegisteredRangeSize@MemoryManager@@AEBA_NPEAW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@@Z; MemoryManager::CheckGetSmallestRegisteredRangeSize(_HV_GPA_ACCESS_TRACKING_RANGE_SIZE *)
0x140110d96  mov     rcx, [rdi+10h]
0x140110d9a  test    al, al
0x140110d9c  jnz     short loc_140110E10
0x140110d9e  call    cs:__imp_VidGpaAccessTrackingDisable
0x140110da5  nop     dword ptr [rax+rax+00h]
0x140110daa  test    eax, eax
0x140110dac  jz      short loc_140110DCB
0x140110dae  mov     rcx, rsi; SRWLock
0x140110db1  mov     dword ptr [rsi+8], 0
0x140110db8  call    cs:__imp_ReleaseSRWLockExclusive
0x140110dbf  nop     dword ptr [rax+rax+00h]
0x140110dc4  xor     ebx, ebx
0x140110dc6  jmp     loc_140110E76
0x140110dcb  call    cs:__imp_GetLastError
0x140110dd2  nop     dword ptr [rax+rax+00h]
0x140110dd7  mov     ebx, eax
0x140110dd9  test    eax, eax
0x140110ddb  jle     short loc_140110DE6
0x140110ddd  movzx   ebx, ax
0x140110de0  or      ebx, 80070000h
0x140110de6  mov     edi, 4020h
0x140110deb  mov     ecx, edi
0x140110ded  call    VmlIsDebugTraceEnabled
0x140110df2  test    eax, eax
0x140110df4  jz      short loc_140110E07
0x140110df6  mov     r8d, ebx
0x140110df9  lea     rdx, off_1402DAC20; "Failed to disable access tracking for t"...
0x140110e00  mov     ecx, edi
0x140110e02  call    VmlDebugTraceWithError
0x140110e07  mov     dword ptr [rsi+8], 0
0x140110e0e  jmp     short loc_140110E67
0x140110e10  mov     edx, [rsp+38h+var_18]
0x140110e14  call    cs:__imp_VidGpaAccessTrackingEnable
0x140110e1b  nop     dword ptr [rax+rax+00h]
0x140110e20  test    eax, eax
0x140110e22  jnz     short loc_140110E62
0x140110e24  mov     edi, 4020h
0x140110e29  mov     ecx, edi
0x140110e2b  call    VmlIsDebugTraceEnabled
0x140110e30  test    eax, eax
0x140110e32  jz      short loc_140110E62
0x140110e34  call    cs:__imp_GetLastError
0x140110e3b  nop     dword ptr [rax+rax+00h]
0x140110e40  test    eax, eax
0x140110e42  jle     short loc_140110E4C
0x140110e44  movzx   eax, ax
0x140110e47  or      eax, 80070000h
0x140110e4c  mov     r9d, [rsp+38h+var_18]
0x140110e51  lea     rdx, off_1402C75A0; "Failed to change tracking size to %u"
0x140110e58  mov     r8d, eax
0x140110e5b  mov     ecx, edi
0x140110e5d  call    VmlDebugTraceWithError
0x140110e62  xor     ebx, ebx
0x140110e64  mov     [rsi+8], ebx
0x140110e67  mov     rcx, rsi; SRWLock
0x140110e6a  call    cs:__imp_ReleaseSRWLockExclusive
0x140110e71  nop     dword ptr [rax+rax+00h]
0x140110e76  mov     rsi, [rsp+38h+arg_10]
0x140110e7b  mov     eax, ebx
0x140110e7d  mov     rbx, [rsp+38h+arg_8]
0x140110e82  add     rsp, 30h
0x140110e86  pop     rdi
0x140110e87  retn
```
