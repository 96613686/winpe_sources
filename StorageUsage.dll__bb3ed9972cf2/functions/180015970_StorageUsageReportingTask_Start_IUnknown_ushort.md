# StorageUsageReportingTask::Start(IUnknown *,ushort *)

- ea: `0x180015970`
- end: `0x180015a7e`
- name: `?Start@StorageUsageReportingTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `270`
- prototype: `__int64 __fastcall(StorageUsageReportingTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015970`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800159cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800159cb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180015a37`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180015a37`

## pseudocode

```c
__int64 __fastcall StorageUsageReportingTask::Start(
        StorageUsageReportingTask *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  signed int v4; // ebx
  HANDLE EventW; // rax
  __int64 v6; // rcx
  HANDLE Thread; // rax
  signed int LastError; // eax
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v4 = -2147418113;
  v10 = 0;
  if ( a2 )
  {
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
           &v10);
    if ( v4 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 3) = EventW;
      if ( !EventW )
        goto LABEL_8;
      *((_QWORD *)this + 5) = EventW;
      *((_QWORD *)this + 4) = v10;
      if ( *((StorageUsageReportingTask **)this + 6) != this )
      {
        (*(void (__fastcall **)(StorageUsageReportingTask *))(*(_QWORD *)this + 8LL))(this);
        v6 = *((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = this;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      Thread = CreateThread(0, 0, StorageUsageReportingTask::CollectStorageUsage, (char *)this + 32, 0, 0);
      *((_QWORD *)this + 2) = Thread;
      if ( !Thread )
      {
LABEL_8:
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015970  mov     r11, rsp
0x180015973  mov     [r11+8], rbx
0x180015977  mov     [r11+18h], rsi
0x18001597b  push    rdi
0x18001597c  sub     rsp, 30h
0x180015980  mov     r9, rdx
0x180015983  mov     rdi, rcx
0x180015986  mov     ebx, 8000FFFFh
0x18001598b  mov     qword ptr [r11+10h], 0
0x180015993  test    rdx, rdx
0x180015996  jz      loc_180015A6C
0x18001599c  mov     rax, [rdx]
0x18001599f  lea     r8, [r11+10h]
0x1800159a3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800159aa  mov     rcx, r9
0x1800159ad  mov     rax, [rax]
0x1800159b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b5  mov     ebx, eax
0x1800159b7  test    eax, eax
0x1800159b9  js      loc_180015A6C
0x1800159bf  xor     r9d, r9d; lpName
0x1800159c2  xor     r8d, r8d; bInitialState
0x1800159c5  lea     edx, [r9+1]; bManualReset
0x1800159c9  xor     ecx, ecx; lpEventAttributes
0x1800159cb  call    cs:__imp_CreateEventW
0x1800159d1  mov     [rdi+18h], rax
0x1800159d5  test    rax, rax
0x1800159d8  jz      short loc_180015A46
0x1800159da  mov     [rdi+28h], rax
0x1800159de  mov     rax, [rsp+38h+arg_8]
0x1800159e3  mov     [rdi+20h], rax
0x1800159e7  cmp     [rdi+30h], rdi
0x1800159eb  jz      short loc_180015A17
0x1800159ed  mov     rax, [rdi]
0x1800159f0  mov     rcx, rdi
0x1800159f3  mov     rax, [rax+8]
0x1800159f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159fc  nop
0x1800159fd  mov     rcx, [rdi+30h]
0x180015a01  mov     [rdi+30h], rdi
0x180015a05  test    rcx, rcx
0x180015a08  jz      short loc_180015A17
0x180015a0a  mov     rax, [rcx]
0x180015a0d  mov     rax, [rax+10h]
0x180015a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a16  nop
0x180015a17  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180015a20  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180015a28  lea     r9, [rdi+20h]; lpParameter
0x180015a2c  lea     r8, ?CollectStorageUsage@StorageUsageReportingTask@@CAKPEAX@Z; lpStartAddress
0x180015a33  xor     edx, edx; dwStackSize
0x180015a35  xor     ecx, ecx; lpThreadAttributes
0x180015a37  call    cs:__imp_CreateThread
0x180015a3d  mov     [rdi+10h], rax
0x180015a41  test    rax, rax
0x180015a44  jnz     short loc_180015A6C
0x180015a46  call    cs:__imp_GetLastError
0x180015a4c  test    eax, eax
0x180015a4e  mov     ebx, eax
0x180015a50  jle     short loc_180015A5B
0x180015a52  movzx   ebx, ax
0x180015a55  or      ebx, 80070000h
0x180015a5b  mov     rcx, [rsp+38h+arg_8]
0x180015a60  mov     rax, [rcx]
0x180015a63  mov     rax, [rax+10h]
0x180015a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6c  mov     eax, ebx
0x180015a6e  mov     rbx, [rsp+38h+arg_0]
0x180015a73  mov     rsi, [rsp+38h+arg_10]
0x180015a78  add     rsp, 30h
0x180015a7c  pop     rdi
0x180015a7d  retn
```
