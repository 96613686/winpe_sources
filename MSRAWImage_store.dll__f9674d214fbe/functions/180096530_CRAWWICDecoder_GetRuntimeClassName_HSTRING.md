# CRAWWICDecoder::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180096530`
- end: `0x18009654d`
- name: `?GetRuntimeClassName@CRAWWICDecoder@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CRAWWICDecoder *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180096560`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180096546`

## pseudocode

```c
HRESULT __fastcall CRAWWICDecoder::GetRuntimeClassName(CRAWWICDecoder *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"RAWDecoder.CRAWWICDecoder", 0x19u, a2);
}

```

## disassembly

```asm
0x180096530  mov     qword ptr [rdx], 0
0x180096537  lea     rcx, ?RuntimeClass_RAWDecoder_CRAWWICDecoder@@3QBGB; "RAWDecoder.CRAWWICDecoder"
0x18009653e  mov     r8, rdx
0x180096541  mov     edx, 19h
0x180096546  jmp     cs:__imp_WindowsCreateString
```
