# SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetPluginSubKeyName(void)

- ea: `0x18008cd84`
- end: `0x18008ce15`
- name: `?GetPluginSubKeyName@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAPEBGXZ`
- size: `145`
- prototype: `const unsigned __int16 *__fastcall(SystemSettings::StorageSenseHandlers::CStorageCleanupItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18008c930`

## callees

- `0x180043f48`
- `0x18008cd84`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cdc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cdfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cdc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cdfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008cdee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008cdee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCWSTR __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetPluginSubKeyName(
        SystemSettings::StorageSenseHandlers::CStorageCleanupItem *this)
{
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, _QWORD, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rbx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  if ( !IsDesktopSKU() )
    return &word_180106450;
  string = 0;
  v3 = *((_QWORD *)this + 40);
  v4 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v4(v3, *((_QWORD *)this + 39), &string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  WindowsDeleteString(string);
  return StringRawBuffer;
}

```

## disassembly

```asm
0x18008cd84  mov     [rsp+arg_0], rbx
0x18008cd89  mov     [rsp+arg_10], rsi
0x18008cd8e  push    rdi
0x18008cd8f  sub     rsp, 20h
0x18008cd93  mov     rsi, rcx
0x18008cd96  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x18008cd9b  test    al, al
0x18008cd9d  jnz     short loc_18008CDA8
0x18008cd9f  lea     rax, word_180106450
0x18008cda6  jmp     short loc_18008CE05
0x18008cda8  mov     [rsp+28h+string], 0
0x18008cdb1  mov     rdi, [rsi+140h]
0x18008cdb8  mov     rax, [rdi]
0x18008cdbb  mov     rbx, [rax+38h]
0x18008cdbf  xor     ecx, ecx; string
0x18008cdc1  call    cs:__imp_WindowsDeleteString
0x18008cdc7  mov     [rsp+28h+string], 0
0x18008cdd0  lea     r8, [rsp+28h+string]
0x18008cdd5  mov     rdx, [rsi+138h]
0x18008cddc  mov     rcx, rdi
0x18008cddf  mov     rax, rbx
0x18008cde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cde7  xor     edx, edx; length
0x18008cde9  mov     rcx, [rsp+28h+string]; string
0x18008cdee  call    cs:__imp_WindowsGetStringRawBuffer
0x18008cdf4  mov     rbx, rax
0x18008cdf7  mov     rcx, [rsp+28h+string]; string
0x18008cdfc  call    cs:__imp_WindowsDeleteString
0x18008ce02  mov     rax, rbx
0x18008ce05  mov     rbx, [rsp+28h+arg_0]
0x18008ce0a  mov     rsi, [rsp+28h+arg_10]
0x18008ce0f  add     rsp, 20h
0x18008ce13  pop     rdi
0x18008ce14  retn
```
