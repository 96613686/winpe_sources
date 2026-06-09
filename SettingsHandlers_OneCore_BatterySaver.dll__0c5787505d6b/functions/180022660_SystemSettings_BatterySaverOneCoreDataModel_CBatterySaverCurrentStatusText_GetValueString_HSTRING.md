# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText::GetValueString(HSTRING__ * *)

- ea: `0x180022660`
- end: `0x1800226f9`
- name: `?GetValueString@CBatterySaverCurrentStatusText@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001dda4`
- `0x180022660`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800226c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800226c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText::GetValueString(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText *this,
        HSTRING *a2)
{
  HRESULT v3; // ebx
  HSTRING v4; // rax
  HSTRING v5; // rcx
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF
  HSTRING v8; // [rsp+48h] [rbp+20h] BYREF

  string = 0;
  v8 = 0;
  v3 = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText::GenerateStatusMessage(this, &v8);
  if ( v3 < 0 )
    goto LABEL_5;
  v4 = string;
  if ( v8 )
  {
    v3 = 0;
    if ( v8 == string )
    {
LABEL_7:
      string = 0;
      *a2 = v4;
      v5 = 0;
      goto LABEL_8;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  v3 = WindowsDuplicateString(v8, &string);
  if ( v3 >= 0 )
  {
    v4 = string;
    goto LABEL_7;
  }
LABEL_5:
  v5 = string;
LABEL_8:
  WindowsDeleteString(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022660  mov     rax, rsp
0x180022663  mov     [rax+8], rbx
0x180022667  push    rdi
0x180022668  sub     rsp, 20h
0x18002266c  mov     rdi, rdx
0x18002266f  mov     qword ptr [rax+18h], 0
0x180022677  mov     qword ptr [rax+20h], 0
0x18002267f  lea     rdx, [rax+20h]; HSTRING *
0x180022683  call    ?GenerateStatusMessage@CBatterySaverCurrentStatusText@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverCurrentStatusText::GenerateStatusMessage(HSTRING__ * *)
0x180022688  mov     ebx, eax
0x18002268a  test    eax, eax
0x18002268c  js      short loc_1800226CC
0x18002268e  mov     rax, [rsp+28h+string]
0x180022693  mov     rcx, [rsp+28h+arg_18]
0x180022698  test    rcx, rcx
0x18002269b  jz      short loc_1800226A4
0x18002269d  xor     ebx, ebx
0x18002269f  cmp     rcx, rax
0x1800226a2  jz      short loc_1800226D8
0x1800226a4  mov     rcx, rax; string
0x1800226a7  call    cs:__imp_WindowsDeleteString
0x1800226ad  mov     [rsp+28h+string], 0
0x1800226b6  lea     rdx, [rsp+28h+string]; newString
0x1800226bb  mov     rcx, [rsp+28h+arg_18]; string
0x1800226c0  call    cs:__imp_WindowsDuplicateString
0x1800226c6  mov     ebx, eax
0x1800226c8  test    eax, eax
0x1800226ca  jns     short loc_1800226D3
0x1800226cc  mov     rcx, [rsp+28h+string]
0x1800226d1  jmp     short loc_1800226E6
0x1800226d3  mov     rax, [rsp+28h+string]
0x1800226d8  mov     [rsp+28h+string], 0
0x1800226e1  mov     [rdi], rax
0x1800226e4  xor     ecx, ecx; string
0x1800226e6  call    cs:__imp_WindowsDeleteString
0x1800226ec  mov     eax, ebx
0x1800226ee  mov     rbx, [rsp+28h+arg_0]
0x1800226f3  add     rsp, 20h
0x1800226f7  pop     rdi
0x1800226f8  retn
```
