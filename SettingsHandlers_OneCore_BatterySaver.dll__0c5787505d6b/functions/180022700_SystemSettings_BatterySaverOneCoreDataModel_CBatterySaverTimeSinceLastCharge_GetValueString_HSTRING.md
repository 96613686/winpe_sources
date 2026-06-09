# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverTimeSinceLastCharge::GetValueString(HSTRING__ * *)

- ea: `0x180022700`
- end: `0x18002274a`
- name: `?GetValueString@CBatterySaverTimeSinceLastCharge@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverTimeSinceLastCharge *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800280c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002273c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002273c`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverTimeSinceLastCharge::GetValueString(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverTimeSinceLastCharge *this,
        HSTRING *a2)
{
  HSTRING v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  Microsoft::WRL::Wrappers::HString::Set(&v4, L"[Placeholder]:99", 0x10u);
  *a2 = v4;
  v4 = 0;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180022700  push    rbx
0x180022702  sub     rsp, 20h
0x180022706  mov     rbx, rdx
0x180022709  mov     [rsp+28h+arg_10], 0
0x180022712  lea     rdx, aPlaceholder99; "[Placeholder]:99"
0x180022719  mov     r8d, 10h; unsigned int
0x18002271f  lea     rcx, [rsp+28h+arg_10]; this
0x180022724  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180022729  mov     rax, [rsp+28h+arg_10]
0x18002272e  xor     ecx, ecx; string
0x180022730  mov     [rbx], rax
0x180022733  mov     [rsp+28h+arg_10], 0
0x18002273c  call    cs:__imp_WindowsDeleteString
0x180022742  xor     eax, eax
0x180022744  add     rsp, 20h
0x180022748  pop     rbx
0x180022749  retn
```
