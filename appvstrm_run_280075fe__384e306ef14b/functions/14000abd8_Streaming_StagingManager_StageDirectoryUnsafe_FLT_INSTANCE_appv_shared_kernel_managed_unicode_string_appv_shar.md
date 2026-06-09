# Streaming::StagingManager::StageDirectoryUnsafe(_FLT_INSTANCE *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)

- ea: `0x14000abd8`
- end: `0x14000ad7a`
- name: `?StageDirectoryUnsafe@StagingManager@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000ad80`
- `0x140012b18`

## callees

- `0x140002864`
- `0x14000a310`
- `0x14000abd8`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000ad14`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad5b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad14`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad5b`
- `FLTMGR!FltClose` at `0x14000acf7`
- `FLTMGR!FltClose` at `0x14000ad3e`
- `FLTMGR!FltClose` at `0x14000acf7`
- `FLTMGR!FltClose` at `0x14000ad3e`

## string_xrefs

- `0x14000ac5d`: `StagingManager::StageDirectoryUnsafe() - Failed to open directory %s, error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StagingManager::StageDirectoryUnsafe(PFLT_INSTANCE Instance, struct _UNICODE_STRING *a2)
{
  struct _UNICODE_STRING *v2; // rsi
  NTSTATUS v4; // edi
  __int64 v5; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  unsigned int v10; // ebx
  __int64 v11; // [rsp+20h] [rbp-40h]
  __int64 v12; // [rsp+28h] [rbp-38h]
  _BYTE v13[8]; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 *v14; // [rsp+48h] [rbp-18h]
  _BYTE v15[8]; // [rsp+50h] [rbp-10h] BYREF
  volatile signed __int32 *v16; // [rsp+58h] [rbp-8h]
  HANDLE FileHandle; // [rsp+88h] [rbp+28h] BYREF
  PVOID Object; // [rsp+90h] [rbp+30h] BYREF

  v2 = a2 + 1;
  Object = 0;
  FileHandle = 0;
  v4 = Streaming::FileOperations::CreateDirectoryInternal(
         *((struct _FLT_FILTER **)Streaming::gStrmFltData + 1),
         Instance,
         a2 + 1,
         0x100198u,
         1u,
         v12,
         (PFILE_OBJECT *)&Object,
         &FileHandle);
  if ( v4 >= 0 )
  {
    v10 = Streaming::StagingManager::StageDirectoryInternal(Instance, (PFILE_OBJECT)Object, 0);
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( Object )
      ObfDereferenceObject(Object);
    return v10;
  }
  else
  {
    v5 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v15, v2);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v13);
    LODWORD(v11) = v4;
    LogWrite(
      4,
      *CurrentActivityID,
      L"StagingManager::StageDirectoryUnsafe() - Failed to open directory %s, error code 0x%08X.",
      v5,
      v11);
    v7 = v14;
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    v8 = v16;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( Object )
      ObfDereferenceObject(Object);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x14000abd8  mov     [rsp-18h+arg_0], rbx
0x14000abdd  push    rbp
0x14000abde  push    rsi
0x14000abdf  push    rdi
0x14000abe0  mov     rbp, rsp
0x14000abe3  sub     rsp, 60h
0x14000abe7  lea     rsi, [rdx+10h]
0x14000abeb  mov     [rbp+Object], 0
0x14000abf3  mov     rdx, rcx
0x14000abf6  mov     [rbp+FileHandle], 0
0x14000abfe  mov     rbx, rcx
0x14000ac01  lea     rax, [rbp+FileHandle]
0x14000ac05  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000ac0c  mov     r9d, 100198h
0x14000ac12  mov     [rsp+60h+var_28], rax
0x14000ac17  mov     r8, rsi
0x14000ac1a  lea     rax, [rbp+Object]
0x14000ac1e  mov     [rsp+60h+var_30], rax
0x14000ac23  mov     rcx, [rcx+8]
0x14000ac27  mov     dword ptr [rsp+60h+var_40], 1
0x14000ac2f  call    ?CreateDirectoryInternal@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KKPEAXAEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::CreateDirectoryInternal(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,ulong,ulong,void *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x14000ac34  mov     edi, eax
0x14000ac36  test    eax, eax
0x14000ac38  jns     loc_14000AD24
0x14000ac3e  mov     rdx, rsi
0x14000ac41  lea     rcx, [rbp+var_10]
0x14000ac45  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000ac4a  lea     rcx, [rbp+var_20]
0x14000ac4e  mov     rbx, [rax]
0x14000ac51  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000ac56  mov     r9, rbx
0x14000ac59  mov     dword ptr [rsp+60h+var_40], edi
0x14000ac5d  lea     r8, aStagingmanager; "StagingManager::StageDirectoryUnsafe() "...
0x14000ac64  mov     ecx, 4
0x14000ac69  mov     rdx, [rax]
0x14000ac6c  call    LogWrite
0x14000ac71  mov     rbx, [rbp+var_18]
0x14000ac75  or      esi, 0FFFFFFFFh
0x14000ac78  test    rbx, rbx
0x14000ac7b  jz      short loc_14000ACB1
0x14000ac7d  mov     eax, esi
0x14000ac7f  lock xadd [rbx+8], eax
0x14000ac84  add     eax, esi
0x14000ac86  jnz     short loc_14000ACB1
0x14000ac88  mov     rax, [rbx]
0x14000ac8b  mov     rcx, rbx
0x14000ac8e  mov     rax, [rax+8]
0x14000ac92  call    _guard_dispatch_icall
0x14000ac97  mov     eax, esi
0x14000ac99  lock xadd [rbx+0Ch], eax
0x14000ac9e  add     eax, esi
0x14000aca0  jnz     short loc_14000ACB1
0x14000aca2  mov     rax, [rbx]
0x14000aca5  mov     rcx, rbx
0x14000aca8  mov     rax, [rax+10h]
0x14000acac  call    _guard_dispatch_icall
0x14000acb1  mov     rbx, [rbp+var_8]
0x14000acb5  test    rbx, rbx
0x14000acb8  jz      short loc_14000ACEE
0x14000acba  mov     eax, esi
0x14000acbc  lock xadd [rbx+8], eax
0x14000acc1  add     eax, esi
0x14000acc3  jnz     short loc_14000ACEE
0x14000acc5  mov     rax, [rbx]
0x14000acc8  mov     rcx, rbx
0x14000accb  mov     rax, [rax+8]
0x14000accf  call    _guard_dispatch_icall
0x14000acd4  mov     eax, esi
0x14000acd6  lock xadd [rbx+0Ch], eax
0x14000acdb  add     eax, esi
0x14000acdd  jnz     short loc_14000ACEE
0x14000acdf  mov     rax, [rbx]
0x14000ace2  mov     rcx, rbx
0x14000ace5  mov     rax, [rax+10h]
0x14000ace9  call    _guard_dispatch_icall
0x14000acee  mov     rcx, [rbp+FileHandle]; FileHandle
0x14000acf2  test    rcx, rcx
0x14000acf5  jz      short loc_14000AD0B
0x14000acf7  call    cs:__imp_FltClose
0x14000acfe  nop     dword ptr [rax+rax+00h]
0x14000ad03  mov     [rbp+FileHandle], 0
0x14000ad0b  mov     rcx, [rbp+Object]; Object
0x14000ad0f  test    rcx, rcx
0x14000ad12  jz      short loc_14000AD20
0x14000ad14  call    cs:__imp_ObfDereferenceObject
0x14000ad1b  nop     dword ptr [rax+rax+00h]
0x14000ad20  mov     eax, edi
0x14000ad22  jmp     short loc_14000AD69
0x14000ad24  mov     rdx, [rbp+Object]; FileObject
0x14000ad28  xor     r8d, r8d; CallbackData
0x14000ad2b  mov     rcx, rbx; Instance
0x14000ad2e  call    ?StageDirectoryInternal@StagingManager@Streaming@@CAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@PEAU_FLT_CALLBACK_DATA@@@Z; Streaming::StagingManager::StageDirectoryInternal(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA *)
0x14000ad33  mov     rcx, [rbp+FileHandle]; FileHandle
0x14000ad37  mov     ebx, eax
0x14000ad39  test    rcx, rcx
0x14000ad3c  jz      short loc_14000AD52
0x14000ad3e  call    cs:__imp_FltClose
0x14000ad45  nop     dword ptr [rax+rax+00h]
0x14000ad4a  mov     [rbp+FileHandle], 0
0x14000ad52  mov     rcx, [rbp+Object]; Object
0x14000ad56  test    rcx, rcx
0x14000ad59  jz      short loc_14000AD67
0x14000ad5b  call    cs:__imp_ObfDereferenceObject
0x14000ad62  nop     dword ptr [rax+rax+00h]
0x14000ad67  mov     eax, ebx
0x14000ad69  mov     rbx, [rsp+60h+arg_0]
0x14000ad71  add     rsp, 60h
0x14000ad75  pop     rdi
0x14000ad76  pop     rsi
0x14000ad77  pop     rbp
0x14000ad78  retn
```
