# OSGetTextServicesManagerStatics

- ea: `0x18004b834`
- end: `0x18004b8b2`
- name: `OSGetTextServicesManagerStatics`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004bf88`

## callees

- `0x180048d5c`
- `0x18004b834`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b892`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b86c`

## string_xrefs

- `0x18004b865`: `Windows.UI.Text.Core.CoreTextServicesManager`

## pseudocode

```c
__int64 __fastcall OSGetTextServicesManagerStatics(__int64 a1)
{
  unsigned int ActivationFactory; // ebx
  HSTRING v3; // rbx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.UI.Text.Core.CoreTextServicesManager", 0x2Cu, &string);
  if ( !ActivationFactory )
  {
    v3 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    ActivationFactory = RoGetActivationFactory(v3, &GUID_1520a388_e2cf_4d65_aeb9_b32d86fe39b9, a1);
  }
  WindowsDeleteString(string);
  return ActivationFactory;
}

```

## disassembly

```asm
0x18004b834  mov     [rsp+arg_0], rbx
0x18004b839  push    rdi
0x18004b83a  sub     rsp, 20h
0x18004b83e  mov     rdi, rcx
0x18004b841  mov     [rsp+28h+string], 0
0x18004b84a  xor     ecx, ecx; string
0x18004b84c  call    cs:__imp_WindowsDeleteString
0x18004b852  lea     r8, [rsp+28h+string]; string
0x18004b857  mov     [rsp+28h+string], 0
0x18004b860  mov     edx, 2Ch ; ','; length
0x18004b865  lea     rcx, ?RuntimeClass_Windows_UI_Text_Core_CoreTextServicesManager@@3QBGB; "Windows.UI.Text.Core.CoreTextServicesMa"...
0x18004b86c  call    cs:__imp_WindowsCreateString
0x18004b872  mov     ebx, eax
0x18004b874  test    eax, eax
0x18004b876  jnz     short loc_18004B89A
0x18004b878  mov     rbx, [rsp+28h+string]
0x18004b87d  mov     rcx, rdi
0x18004b880  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b885  mov     r8, rdi
0x18004b888  lea     rdx, _GUID_1520a388_e2cf_4d65_aeb9_b32d86fe39b9
0x18004b88f  mov     rcx, rbx
0x18004b892  call    cs:__imp_RoGetActivationFactory
0x18004b898  mov     ebx, eax
0x18004b89a  mov     rcx, [rsp+28h+string]; string
0x18004b89f  call    cs:__imp_WindowsDeleteString
0x18004b8a5  mov     eax, ebx
0x18004b8a7  mov     rbx, [rsp+28h+arg_0]
0x18004b8ac  add     rsp, 20h
0x18004b8b0  pop     rdi
0x18004b8b1  retn
```
