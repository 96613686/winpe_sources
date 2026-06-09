# NetSetupClose

- ea: `0x180004ec0`
- end: `0x180004f69`
- name: `NetSetupClose`
- size: `169`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fd78`

## callees

- `0x180004ec0`
- `0x180004f70`
- `0x18000f5a0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180004f14`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180004f14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ef2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ef2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ef8`

## pseudocode

```c
void __fastcall NetSetupClose(__int64 a1, __int64 a2)
{
  __int64 *v3; // rax
  DWORD CurrentThreadId; // eax
  bool v5; // zf

  if ( a1 )
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  else
    v3 = qword_18001D4A0;
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McTemplateU0jq_EventWriteTransfer(a1, a2, (__int64)v3, 4);
  NetSetupExecuteInFrame__lambda_06fb40216b468837b8d767c46b73c3b4_(a1);
  AcquireSRWLockExclusive(&g_NetSetupHandleCountLock);
  CurrentThreadId = GetCurrentThreadId();
  v5 = g_NumNetSetupHandles-- == 1;
  dword_180025A68 = CurrentThreadId;
  if ( v5 )
  {
    FreeLibrary(g_NetSetupEngine);
    g_NetSetupEngine = 0;
    g_NetSetupGetEnginePfn = 0;
  }
  dword_180025A68 = 0;
  ReleaseSRWLockExclusive(&g_NetSetupHandleCountLock);
}

```

## disassembly

```asm
0x180004ec0  push    rbx
0x180004ec2  sub     rsp, 30h
0x180004ec6  mov     rbx, rcx
0x180004ec9  test    rcx, rcx
0x180004ecc  jz      short loc_180004F4D
0x180004ece  mov     rax, [rcx]
0x180004ed1  mov     rax, [rax+8]
0x180004ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eda  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x180004ee1  jnz     short loc_180004F56
0x180004ee3  mov     rcx, rbx
0x180004ee6  call    NetSetupExecuteInFrame__lambda_06fb40216b468837b8d767c46b73c3b4___; NetSetupExecuteInFrame__lambda_06fb40216b468837b8d767c46b73c3b4_
0x180004eeb  lea     rcx, ?g_NetSetupHandleCountLock@@3VRtlSrwLock@@A; SRWLock
0x180004ef2  call    cs:__imp_AcquireSRWLockExclusive
0x180004ef8  call    cs:__imp_GetCurrentThreadId
0x180004efe  add     cs:?g_NumNetSetupHandles@@3KA, 0FFFFFFFFh; ulong g_NumNetSetupHandles
0x180004f05  mov     cs:dword_180025A68, eax
0x180004f0b  jnz     short loc_180004F30
0x180004f0d  mov     rcx, cs:?g_NetSetupEngine@@3PEAUHINSTANCE__@@EA; hLibModule
0x180004f14  call    cs:__imp_FreeLibrary
0x180004f1a  mov     cs:?g_NetSetupEngine@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_NetSetupEngine
0x180004f25  mov     cs:?g_NetSetupGetEnginePfn@@3P6APEAVNetSetupImplementation@@KPEAU_NETSETUP_ENVIRONMENT@@@ZEA, 0; NetSetupImplementation * (*g_NetSetupGetEnginePfn)(ulong,_NETSETUP_ENVIRONMENT *)
0x180004f30  lea     rcx, ?g_NetSetupHandleCountLock@@3VRtlSrwLock@@A; RtlSrwLock g_NetSetupHandleCountLock
0x180004f37  mov     cs:dword_180025A68, 0
0x180004f41  add     rsp, 30h
0x180004f45  pop     rbx
0x180004f46  jmp     cs:__imp_ReleaseSRWLockExclusive
0x180004f4d  lea     rax, qword_18001D4A0
0x180004f54  jmp     short loc_180004EDA
0x180004f56  mov     r9d, 4
0x180004f5c  mov     r8, rax
0x180004f5f  call    McTemplateU0jq_EventWriteTransfer
0x180004f64  jmp     loc_180004EE3
```
