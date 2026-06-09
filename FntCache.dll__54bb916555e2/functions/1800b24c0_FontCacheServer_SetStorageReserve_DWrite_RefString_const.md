# FontCacheServer::SetStorageReserve(DWrite::RefString const &)

- ea: `0x1800b24c0`
- end: `0x1800b2640`
- name: `?SetStorageReserve@FontCacheServer@@AEAAXAEBVRefString@DWrite@@@Z`
- size: `384`
- prototype: `void __fastcall(FontCacheServer *__hidden this, const struct DWrite::RefString *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a7190`
- `0x1800b2020`

## callees

- `0x18000d7ec`
- `0x18009372c`
- `0x1800b24c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2528`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2622`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b250c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b250c`
- `ntdll!NtSetInformationFile` at `0x1800b25bf`
- `ntdll!NtSetInformationFile` at `0x1800b25bf`

## string_xrefs

- `0x1800b252e`: `open_dir`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall FontCacheServer::SetStorageReserve(FontCacheServer *this, const struct DWrite::RefString *a2)
{
  HANDLE FileW; // rax
  void *v5; // rbx
  __int64 v6; // rbx
  EventTag *v7; // rax
  unsigned int v8; // r9d
  __int64 v9; // r8
  __int64 v10; // rcx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp+7h] BYREF
  int v15; // [rsp+68h] [rbp+17h]
  int v16; // [rsp+6Ch] [rbp+1Bh]
  __int64 v17; // [rsp+70h] [rbp+1Fh]
  _DWORD v18[6]; // [rsp+78h] [rbp+27h] BYREF
  __int64 v19; // [rsp+90h] [rbp+3Fh]
  int FileInformation; // [rsp+C0h] [rbp+6Fh] BYREF

  FileW = CreateFileW((LPCWSTR)(*(_QWORD *)a2 + 8LL), 2u, 1u, 0, 3u, 0x2000000u, 0);
  v5 = 0;
  if ( FileW != (HANDLE)-1LL )
    v5 = FileW;
  if ( v5 )
  {
    FileInformation = 2;
    IoStatusBlock = 0;
    v11 = NtSetInformationFile(v5, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    v12 = *(_QWORD *)a2 + 8LL;
    v18[2] = v11;
    v19 = v12;
    v18[1] = 0;
    v13 = *((unsigned int *)this + 6);
    v18[3] = 0;
    v18[0] = 1;
    v18[4] = 3;
    v18[5] = 0;
    EventLogger::LogGenericEvent(v13, 0x7265767265536346LL, 0x7365725F677473LL, v18, 2);
    CloseHandle(v5);
  }
  else
  {
    v6 = *(_QWORD *)a2 + 8LL;
    GetLastError();
    v7 = EventTag::EventTag((EventTag *)&FileInformation, (const char (*)[9])"open_dir");
    IoStatusBlock.Information = v8;
    v9 = *(_QWORD *)v7;
    v16 = 0;
    v10 = *((unsigned int *)this + 6);
    IoStatusBlock.Pointer = (PVOID)1;
    v15 = 3;
    v17 = v6;
    EventLogger::LogGenericEvent(v10, 0x7265767265536346LL, v9, &IoStatusBlock, 2);
  }
}

```

## disassembly

```asm
0x1800b24c0  mov     rax, rsp
0x1800b24c3  mov     [rax+8], rbx
0x1800b24c7  mov     [rax+18h], rsi
0x1800b24cb  push    rbp
0x1800b24cc  push    rdi
0x1800b24cd  push    r14
0x1800b24cf  lea     rbp, [rax-5Fh]
0x1800b24d3  sub     rsp, 90h
0x1800b24da  xor     r9d, r9d; lpSecurityAttributes
0x1800b24dd  mov     qword ptr [rax-78h], 0
0x1800b24e5  mov     rsi, rcx
0x1800b24e8  mov     dword ptr [rax-80h], 2000000h
0x1800b24ef  mov     rcx, [rdx]
0x1800b24f2  mov     rdi, rdx
0x1800b24f5  add     rcx, 8; lpFileName
0x1800b24f9  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b2501  lea     r14d, [r9+2]
0x1800b2505  mov     edx, r14d; dwDesiredAccess
0x1800b2508  lea     r8d, [r9+1]; dwShareMode
0x1800b250c  call    cs:__imp_CreateFileW
0x1800b2512  xor     ebx, ebx
0x1800b2514  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b2518  cmovnz  rbx, rax
0x1800b251c  test    rbx, rbx
0x1800b251f  jnz     short loc_1800B2597
0x1800b2521  mov     rbx, [rdi]
0x1800b2524  add     rbx, 8
0x1800b2528  call    cs:__imp_GetLastError
0x1800b252e  lea     rdx, aOpenDir; "open_dir"
0x1800b2535  mov     r9d, eax
0x1800b2538  lea     rcx, [rbp+57h+FileInformation]; this
0x1800b253c  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1800b2541  xorps   xmm0, xmm0
0x1800b2544  mov     dword ptr [rbp+57h+IoStatusBlock.Information], r9d
0x1800b2548  movups  [rbp+57h+var_60], xmm0
0x1800b254c  mov     ecx, dword ptr [rbp+57h+var_60+4]
0x1800b254f  lea     r9, [rbp+57h+IoStatusBlock]
0x1800b2553  mov     r8, [rax]
0x1800b2556  mov     rdx, 7265767265536346h
0x1800b2560  mov     dword ptr [rbp+57h+IoStatusBlock+4], ecx
0x1800b2563  mov     ecx, dword ptr [rbp+57h+var_60+0Ch]
0x1800b2566  mov     dword ptr [rbp+57h+IoStatusBlock.Information+4], ecx
0x1800b2569  movups  [rbp+57h+var_60], xmm0
0x1800b256d  mov     ecx, dword ptr [rbp+57h+var_60+4]
0x1800b2570  mov     [rbp+57h+var_3C], ecx
0x1800b2573  mov     ecx, [rsi+18h]
0x1800b2576  mov     dword ptr [rbp+57h+IoStatusBlock], 1
0x1800b257d  mov     [rbp+57h+var_40], 3
0x1800b2584  mov     [rbp+57h+var_38], rbx
0x1800b2588  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14
0x1800b258d  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x1800b2592  jmp     loc_1800B2628
0x1800b2597  xorps   xmm0, xmm0
0x1800b259a  mov     [rbp+57h+FileInformation], r14d
0x1800b259e  mov     r9d, 4; Length
0x1800b25a4  mov     [rsp+0A0h+dwCreationDisposition], 4Ah ; 'J'; FileInformationClass
0x1800b25ac  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800b25b0  mov     rcx, rbx; FileHandle
0x1800b25b3  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800b25b7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800b25bb  movups  [rbp+57h+var_60], xmm0
0x1800b25bf  call    cs:__imp_NtSetInformationFile
0x1800b25c5  mov     ecx, dword ptr [rbp+57h+var_60+4]
0x1800b25c8  lea     r9, [rbp+57h+var_30]
0x1800b25cc  mov     rdx, [rdi]
0x1800b25cf  xorps   xmm0, xmm0
0x1800b25d2  add     rdx, 8
0x1800b25d6  mov     [rbp+57h+var_28], eax
0x1800b25d9  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x1800b25dc  mov     r8, 7365725F677473h
0x1800b25e6  mov     [rbp+57h+var_18], rdx
0x1800b25ea  mov     rdx, 7265767265536346h
0x1800b25f4  mov     [rbp+57h+var_2C], ecx
0x1800b25f7  mov     ecx, [rsi+18h]
0x1800b25fa  mov     [rbp+57h+var_24], eax
0x1800b25fd  movups  [rbp+57h+var_60], xmm0
0x1800b2601  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1800b2604  mov     [rbp+57h+var_30], 1
0x1800b260b  mov     [rbp+57h+var_20], 3
0x1800b2612  mov     [rbp+57h+var_1C], eax
0x1800b2615  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14
0x1800b261a  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x1800b261f  mov     rcx, rbx; hObject
0x1800b2622  call    cs:__imp_CloseHandle
0x1800b2628  lea     r11, [rsp+0A0h+var_10]
0x1800b2630  mov     rbx, [r11+20h]
0x1800b2634  mov     rsi, [r11+30h]
0x1800b2638  mov     rsp, r11
0x1800b263b  pop     r14
0x1800b263d  pop     rdi
0x1800b263e  pop     rbp
0x1800b263f  retn
```
