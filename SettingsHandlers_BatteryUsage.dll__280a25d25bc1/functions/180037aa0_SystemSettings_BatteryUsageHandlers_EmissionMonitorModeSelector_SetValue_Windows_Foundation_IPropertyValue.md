# SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180037aa0`
- end: `0x180037b8f`
- name: `?SetValue@EmissionMonitorModeSelector@BatteryUsageHandlers@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `239`
- prototype: `int(SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a13c`
- `0x180037aa0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180037b33`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x180037b33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037b14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037b14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::SetValue(
        SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const WCHAR *StringRawBuffer; // rbp
  __int64 v8; // rbx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = 0;
    while ( StrCmpLogicalW(
              *((PCWSTR *)&SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::_sc_rgridpModeValues
              + 2 * v8),
              StringRawBuffer) )
    {
      if ( (unsigned __int64)++v8 >= 2 )
      {
        v6 = -2147467259;
        goto LABEL_8;
      }
    }
    *((_DWORD *)this + 76) = *((_DWORD *)&SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::_sc_rgridpModeValues
                             + 4 * v8
                             + 2);
    (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *, SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *))(*(_QWORD *)this + 192LL))(
      this,
      this);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\emissionmonitormodeselector.cpp",
      (const char *)(unsigned int)v5,
      v10);
  }
LABEL_8:
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x180037aa0  mov     [rsp+arg_0], rbx
0x180037aa5  mov     [rsp+arg_10], rbp
0x180037aaa  push    rsi
0x180037aab  push    rdi
0x180037aac  push    r14; int
0x180037aae  sub     rsp, 20h
0x180037ab2  mov     rdi, rdx
0x180037ab5  mov     rsi, rcx
0x180037ab8  mov     [rsp+38h+string], 0
0x180037ac1  mov     rax, [rdx]
0x180037ac4  mov     rbx, [rax+98h]
0x180037acb  xor     ecx, ecx; string
0x180037acd  call    cs:__imp_WindowsDeleteString
0x180037ad3  mov     [rsp+38h+string], 0
0x180037adc  lea     rdx, [rsp+38h+string]
0x180037ae1  mov     rcx, rdi
0x180037ae4  mov     rax, rbx
0x180037ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aec  mov     ebx, eax
0x180037aee  test    eax, eax
0x180037af0  jns     short loc_180037B0D
0x180037af2  mov     rcx, [rsp+38h]; this
0x180037af7  mov     r9d, eax; char *
0x180037afa  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\coresettinghandlers"...
0x180037b01  mov     edx, 7Dh ; '}'; void *
0x180037b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b0b  jmp     short loc_180037B6F
0x180037b0d  xor     edx, edx; length
0x180037b0f  mov     rcx, [rsp+38h+string]; string
0x180037b14  call    cs:__imp_WindowsGetStringRawBuffer
0x180037b1a  mov     rbp, rax
0x180037b1d  xor     ebx, ebx
0x180037b1f  lea     r14, ?_sc_rgridpModeValues@EmissionMonitorModeSelector@BatteryUsageHandlers@SystemSettings@@0QBUMODE_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::MODE_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::_sc_rgridpModeValues
0x180037b26  mov     rdi, rbx
0x180037b29  add     rdi, rdi
0x180037b2c  mov     rdx, rbp; psz2
0x180037b2f  mov     rcx, [r14+rdi*8]; psz1
0x180037b33  call    cs:__imp_StrCmpLogicalW
0x180037b39  test    eax, eax
0x180037b3b  jz      short loc_180037B4D
0x180037b3d  inc     rbx
0x180037b40  cmp     rbx, 2
0x180037b44  jb      short loc_180037B26
0x180037b46  mov     ebx, 80004005h
0x180037b4b  jmp     short loc_180037B6F
0x180037b4d  mov     eax, [r14+rdi*8+8]
0x180037b52  mov     [rsi+130h], eax
0x180037b58  mov     rax, [rsi]
0x180037b5b  mov     rdx, rsi
0x180037b5e  mov     rcx, rsi
0x180037b61  mov     rax, [rax+0C0h]
0x180037b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b6d  xor     ebx, ebx
0x180037b6f  mov     rcx, [rsp+38h+string]; string
0x180037b74  call    cs:__imp_WindowsDeleteString
0x180037b7a  mov     eax, ebx
0x180037b7c  mov     rbx, [rsp+38h+arg_0]
0x180037b81  mov     rbp, [rsp+38h+arg_10]
0x180037b86  add     rsp, 20h
0x180037b8a  pop     r14
0x180037b8c  pop     rdi
0x180037b8d  pop     rsi
0x180037b8e  retn
```
