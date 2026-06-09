# SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)

- ea: `0x18001879c`
- end: `0x180018825`
- name: `?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, struct IInspectable **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015510`
- `0x1800171a0`
- `0x180019c60`

## callees

- `0x18001868c`
- `0x18001879c`
- `0x180021a30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018812`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::GetResourceStringValue(
        SystemSettings::DataModel *this,
        const unsigned __int16 *a2,
        struct IInspectable **a3)
{
  HSTRING *v5; // r8
  int ResourceStringById; // ebx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)a2 = 0;
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(this, &string, v5);
  if ( ResourceStringById >= 0 )
  {
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
    if ( ResourceStringById < 0
      || (ResourceStringById = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, HSTRING, const unsigned __int16 *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 144LL))(
                                 SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                                 string,
                                 a2),
          ResourceStringById < 0) )
    {
      *(_QWORD *)a2 = 0;
    }
  }
  WindowsDeleteString(string);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x18001879c  mov     [rsp+arg_0], rbx
0x1800187a1  push    rdi
0x1800187a2  sub     rsp, 20h
0x1800187a6  mov     rdi, rdx
0x1800187a9  mov     rbx, rcx
0x1800187ac  mov     qword ptr [rdx], 0
0x1800187b3  xor     ecx, ecx; string
0x1800187b5  call    cs:__imp_WindowsDeleteString
0x1800187bb  mov     [rsp+28h+string], 0
0x1800187c4  lea     rdx, [rsp+28h+string]; HSTRING *
0x1800187c9  mov     rcx, rbx; this
0x1800187cc  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800187d1  mov     ebx, eax
0x1800187d3  test    eax, eax
0x1800187d5  js      short loc_18001880D
0x1800187d7  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x1800187dc  mov     ebx, eax
0x1800187de  test    eax, eax
0x1800187e0  js      short loc_180018806
0x1800187e2  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x1800187e9  mov     rax, [rcx]
0x1800187ec  mov     r8, rdi
0x1800187ef  mov     rdx, [rsp+28h+string]
0x1800187f4  mov     rax, [rax+90h]
0x1800187fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018800  mov     ebx, eax
0x180018802  test    eax, eax
0x180018804  jns     short loc_18001880D
0x180018806  mov     qword ptr [rdi], 0
0x18001880d  mov     rcx, [rsp+28h+string]; string
0x180018812  call    cs:__imp_WindowsDeleteString
0x180018818  mov     eax, ebx
0x18001881a  mov     rbx, [rsp+28h+arg_0]
0x18001881f  add     rsp, 20h
0x180018823  pop     rdi
0x180018824  retn
```
