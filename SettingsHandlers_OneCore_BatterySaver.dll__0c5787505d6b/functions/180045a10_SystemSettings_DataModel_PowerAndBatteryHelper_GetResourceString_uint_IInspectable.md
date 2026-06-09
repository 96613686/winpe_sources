# SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uint,IInspectable * *)

- ea: `0x180045a10`
- end: `0x180045a79`
- name: `?GetResourceString@PowerAndBatteryHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(UINT uID, struct IInspectable **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003db80`

## callees

- `0x18001d140`
- `0x18004597c`
- `0x180045a10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(
        UINT uID,
        struct IInspectable **a2)
{
  int ResourceString; // ebx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  ResourceString = SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uID, &string);
  if ( ResourceString >= 0 )
    ResourceString = SystemSettings::DataModel::PropValueHelper::CreateString(string, a2);
  WindowsDeleteString(string);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x180045a10  mov     [rsp+arg_0], rbx
0x180045a15  push    rdi
0x180045a16  sub     rsp, 20h
0x180045a1a  mov     rdi, rdx
0x180045a1d  mov     ebx, ecx
0x180045a1f  mov     qword ptr [rdx], 0
0x180045a26  mov     [rsp+28h+string], 0
0x180045a2f  xor     ecx, ecx; string
0x180045a31  call    cs:__imp_WindowsDeleteString
0x180045a37  mov     [rsp+28h+string], 0
0x180045a40  lea     rdx, [rsp+28h+string]; string
0x180045a45  mov     ecx, ebx; uID
0x180045a47  call    ?GetResourceString@PowerAndBatteryHelper@DataModel@SystemSettings@@SAJIPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uint,HSTRING__ * *)
0x180045a4c  mov     ebx, eax
0x180045a4e  test    eax, eax
0x180045a50  js      short loc_180045A61
0x180045a52  mov     rdx, rdi; struct IInspectable **
0x180045a55  mov     rcx, [rsp+28h+string]; HSTRING
0x180045a5a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180045a5f  mov     ebx, eax
0x180045a61  mov     rcx, [rsp+28h+string]; string
0x180045a66  call    cs:__imp_WindowsDeleteString
0x180045a6c  mov     eax, ebx
0x180045a6e  mov     rbx, [rsp+28h+arg_0]
0x180045a73  add     rsp, 20h
0x180045a77  pop     rdi
0x180045a78  retn
```
