# Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b750`
- end: `0x18000b76d`
- name: `?GetRuntimeClassName@PhoneCallActivatedEventArgsImpl@Activation@ApplicationModel@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *__hidden this, HSTRING *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b780`
- `0x18000b790`
- `0x18000b7a0`
- `0x18000b7b0`
- `0x18000b7d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b766`

## pseudocode

```c
HRESULT __fastcall Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::GetRuntimeClassName(
        Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.ApplicationModel.Activation.PhoneCallActivatedEventArgs", 0x3Fu, a2);
}

```

## disassembly

```asm
0x18000b750  mov     qword ptr [rdx], 0
0x18000b757  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Activation_PhoneCallActivatedEventArgs@@3QBGB; "Windows.ApplicationModel.Activation.Pho"...
0x18000b75e  mov     r8, rdx
0x18000b761  mov     edx, 3Fh ; '?'
0x18000b766  jmp     cs:__imp_WindowsCreateString
```
