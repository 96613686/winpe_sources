# SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)

- ea: `0x180014710`
- end: `0x180014772`
- name: `?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, struct IInspectable **, struct IInspectable **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013100`
- `0x180028910`
- `0x180029580`

## callees

- `0x180012814`
- `0x1800146a8`
- `0x180014710`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001475f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001475f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::GetResourceStringValue(
        SystemSettings::DataModel *this,
        struct IInspectable **a2,
        struct IInspectable **a3)
{
  HSTRING *v5; // r8
  int ResourceStringById; // ebx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(this, &string, v5);
  if ( ResourceStringById >= 0 )
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a2);
  WindowsDeleteString(string);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x180014710  mov     [rsp+arg_0], rbx
0x180014715  push    rdi
0x180014716  sub     rsp, 20h
0x18001471a  mov     rdi, rdx
0x18001471d  mov     rbx, rcx
0x180014720  mov     qword ptr [rdx], 0
0x180014727  xor     ecx, ecx; string
0x180014729  call    cs:__imp_WindowsDeleteString
0x18001472f  mov     [rsp+28h+string], 0
0x180014738  lea     rdx, [rsp+28h+string]; HSTRING *
0x18001473d  mov     rcx, rbx; this
0x180014740  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180014745  mov     ebx, eax
0x180014747  test    eax, eax
0x180014749  js      short loc_18001475A
0x18001474b  mov     rdx, rdi; struct IInspectable **
0x18001474e  mov     rcx, [rsp+28h+string]; HSTRING
0x180014753  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180014758  mov     ebx, eax
0x18001475a  mov     rcx, [rsp+28h+string]; string
0x18001475f  call    cs:__imp_WindowsDeleteString
0x180014765  mov     eax, ebx
0x180014767  mov     rbx, [rsp+28h+arg_0]
0x18001476c  add     rsp, 20h
0x180014770  pop     rdi
0x180014771  retn
```
