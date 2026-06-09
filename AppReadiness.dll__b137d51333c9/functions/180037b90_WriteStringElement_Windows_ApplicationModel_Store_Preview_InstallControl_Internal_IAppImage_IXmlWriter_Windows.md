# WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)

- ea: `0x180037b90`
- end: `0x180037c19`
- name: `??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall *)(__int64, HSTRING *), __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001f0dc`
- `0x180073a54`

## callees

- `0x180037b90`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037be3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037be3`

## pseudocode

```c
__int64 __fastcall WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, HSTRING *),
        __int64 a4)
{
  int v8; // ebx
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64, _QWORD, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v8 = a3(a2, &string);
  if ( v8 >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, PCWSTR))(*(_QWORD *)a1 + 104LL);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = v9(a1, 0, a4, 0, StringRawBuffer);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037b90  push    rbx
0x180037b92  push    rbp
0x180037b93  push    rsi
0x180037b94  push    rdi
0x180037b95  sub     rsp, 38h
0x180037b99  mov     rbp, r9
0x180037b9c  mov     rdi, r8
0x180037b9f  mov     rbx, rdx
0x180037ba2  mov     rsi, rcx
0x180037ba5  mov     [rsp+58h+string], 0
0x180037bae  xor     ecx, ecx; string
0x180037bb0  call    cs:__imp_WindowsDeleteString
0x180037bb6  mov     [rsp+58h+string], 0
0x180037bbf  lea     rdx, [rsp+58h+string]
0x180037bc4  mov     rcx, rbx
0x180037bc7  mov     rax, rdi
0x180037bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bcf  mov     ebx, eax
0x180037bd1  test    eax, eax
0x180037bd3  js      short loc_180037C03
0x180037bd5  mov     rax, [rsi]
0x180037bd8  mov     rbx, [rax+68h]
0x180037bdc  xor     edx, edx; length
0x180037bde  mov     rcx, [rsp+58h+string]; string
0x180037be3  call    cs:__imp_WindowsGetStringRawBuffer
0x180037be9  mov     [rsp+58h+var_38], rax
0x180037bee  xor     r9d, r9d
0x180037bf1  mov     r8, rbp
0x180037bf4  xor     edx, edx
0x180037bf6  mov     rcx, rsi
0x180037bf9  mov     rax, rbx
0x180037bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c01  mov     ebx, eax
0x180037c03  mov     rcx, [rsp+58h+string]; string
0x180037c08  call    cs:__imp_WindowsDeleteString
0x180037c0e  mov     eax, ebx
0x180037c10  add     rsp, 38h
0x180037c14  pop     rdi
0x180037c15  pop     rsi
0x180037c16  pop     rbp
0x180037c17  pop     rbx
0x180037c18  retn
```
