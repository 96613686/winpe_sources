# ConnectedStorage::UploadingContext::ContainerUploaded(ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::SimpleHStringWrapper,bool)

- ea: `0x180061e60`
- end: `0x180061ee4`
- name: `?ContainerUploaded@UploadingContext@ConnectedStorage@@MEBAXVSimpleHStringWrapper@2@0_N@Z`
- size: `132`
- prototype: `void __high(struct ConnectedStorage::SimpleHStringWrapper, struct ConnectedStorage::SimpleHStringWrapper, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011b94`
- `0x180060ed4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ec9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall ConnectedStorage::UploadingContext::ContainerUploaded(__int64 a1, HSTRING *a2, HSTRING *a3, char a4)
{
  HRESULT result; // eax
  HSTRING v9; // [rsp+20h] [rbp-38h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-30h] BYREF
  char v11; // [rsp+30h] [rbp-28h]

  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v9, a2);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a3);
  v11 = a4;
  ConnectedStorage::HasExecuteQueue_ConnectedStorage::UploadingContext_::Enqueue__lambda_633925c69c1080328a11dabbc2abc5b1___(
    a1 + 8,
    &v9);
  WindowsDeleteString(*a2);
  *a2 = 0;
  result = WindowsDeleteString(*a3);
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180061e60  mov     r11, rsp
0x180061e63  mov     [r11+20h], rbx
0x180061e67  mov     [r11+18h], r8
0x180061e6b  mov     [r11+10h], rdx
0x180061e6f  push    rsi
0x180061e70  push    rdi
0x180061e71  push    r14
0x180061e73  sub     rsp, 40h
0x180061e77  mov     dil, r9b
0x180061e7a  mov     r14, r8
0x180061e7d  mov     rsi, rdx
0x180061e80  mov     rbx, rcx
0x180061e83  lea     rax, [r11-38h]
0x180061e87  mov     [r11+8], rax
0x180061e8b  lea     rcx, [r11-38h]; newString
0x180061e8f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180061e94  nop
0x180061e95  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x180061e98  lea     rcx, [rsp+58h+newString]; newString
0x180061e9d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180061ea2  mov     [rsp+58h+var_28], dil
0x180061ea7  lea     rcx, [rbx+8]
0x180061eab  lea     rdx, [rsp+58h+var_38]
0x180061eb0  call    ConnectedStorage__HasExecuteQueue_ConnectedStorage__UploadingContext___Enqueue__lambda_633925c69c1080328a11dabbc2abc5b1___
0x180061eb5  nop
0x180061eb6  mov     rcx, [rsi]; string
0x180061eb9  call    cs:__imp_WindowsDeleteString
0x180061ebf  mov     qword ptr [rsi], 0
0x180061ec6  mov     rcx, [r14]; string
0x180061ec9  call    cs:__imp_WindowsDeleteString
0x180061ecf  mov     qword ptr [r14], 0
0x180061ed6  mov     rbx, [rsp+58h+arg_18]
0x180061edb  add     rsp, 40h
0x180061edf  pop     r14
0x180061ee1  pop     rdi
0x180061ee2  pop     rsi
0x180061ee3  retn
```
