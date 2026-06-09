# wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)

- ea: `0x18002a848`
- end: `0x18002a874`
- name: `??1?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cd40`
- `0x180036fbc`
- `0x180036ff2`

## callees

- `0x18002a848`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a859`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18002a848  push    rbx
0x18002a84a  sub     rsp, 20h
0x18002a84e  mov     rbx, rcx
0x18002a851  mov     rcx, [rcx]; pv
0x18002a854  test    rcx, rcx
0x18002a857  jz      short loc_18002A86E
0x18002a859  call    cs:__imp_CoTaskMemFree
0x18002a85f  mov     qword ptr [rbx], 0
0x18002a866  mov     qword ptr [rbx+8], 0
0x18002a86e  add     rsp, 20h
0x18002a872  pop     rbx
0x18002a873  retn
```
