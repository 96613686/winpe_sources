# ServiceMain(ulong,ushort * * const)

- ea: `0x180016400`
- end: `0x18001649c`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `156`
- prototype: `void __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180016044`
- `0x180016400`
- `0x1800164a4`
- `0x180042c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180016414`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180016414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016479`

## string_xrefs

- `0x180016409`: `RecommendedTroubleshootingServiceMutexName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **const a2)
{
  unsigned int v3; // ecx
  signed int LastError; // eax
  void **v5; // [rsp+20h] [rbp-18h] BYREF
  HANDLE MutexW; // [rsp+28h] [rbp-10h]

  MutexW = CreateMutexW(0, 0, L"RecommendedTroubleshootingServiceMutexName");
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::Close(&g_serviceLock);
  qword_18007D0F0 = MutexW;
  v5 = &Microsoft::WRL::Wrappers::Mutex::`vftable';
  MutexW = 0;
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::Close(&v5);
  if ( qword_18007D0F0 )
  {
    ServiceMainInternal(v3, a2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    MitigationExecutionContext::DispatchEvent(4, (unsigned int)LastError);
  }
}

```

## disassembly

```asm
0x180016400  push    rbx
0x180016402  sub     rsp, 30h
0x180016406  mov     rbx, rdx
0x180016409  lea     r8, Name; "RecommendedTroubleshootingServiceMutexN"...
0x180016410  xor     edx, edx; bInitialOwner
0x180016412  xor     ecx, ecx; lpMutexAttributes
0x180016414  call    cs:__imp_CreateMutexW
0x18001641a  mov     [rsp+38h+var_10], rax
0x18001641f  lea     rcx, ?g_serviceLock@@3VMutex@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::Mutex g_serviceLock
0x180016426  lea     rax, ??_7Mutex@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::Mutex::`vftable'
0x18001642d  mov     [rsp+38h+var_18], rax
0x180016432  call    ?Close@?$HandleT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::Close(void)
0x180016437  mov     rax, [rsp+38h+var_10]
0x18001643c  lea     rcx, [rsp+38h+var_18]
0x180016441  mov     cs:qword_18007D0F0, rax
0x180016448  lea     rax, ??_7Mutex@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::Mutex::`vftable'
0x18001644f  mov     [rsp+38h+var_18], rax
0x180016454  mov     [rsp+38h+var_10], 0
0x18001645d  call    ?Close@?$HandleT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::Close(void)
0x180016462  cmp     cs:qword_18007D0F0, 0
0x18001646a  jz      short loc_180016479
0x18001646c  mov     rdx, rbx; unsigned __int16 **
0x18001646f  add     rsp, 30h
0x180016473  pop     rbx
0x180016474  jmp     ?ServiceMainInternal@@YAJKQEAPEAG@Z; ServiceMainInternal(ulong,ushort * * const)
0x180016479  call    cs:__imp_GetLastError
0x18001647f  test    eax, eax
0x180016481  jle     short loc_18001648B
0x180016483  movzx   eax, ax
0x180016486  or      eax, 80070000h
0x18001648b  mov     edx, eax
0x18001648d  mov     ecx, 4
0x180016492  add     rsp, 30h
0x180016496  pop     rbx
0x180016497  jmp     ?DispatchEvent@MitigationExecutionContext@@SAXW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(MitigationError,long)
```
