# ConnectedStorage::Context::ContainerUploaded(ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::SimpleHStringWrapper,bool)

- ea: `0x18005c030`
- end: `0x18005c090`
- name: `?ContainerUploaded@Context@ConnectedStorage@@UEBAXVSimpleHStringWrapper@2@0_N@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180058f80`
- `0x18005a7c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c06b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c07b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c06b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c07b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall ConnectedStorage::Context::ContainerUploaded(__int64 a1, HSTRING *a2, HSTRING *a3, char a4)
{
  __int64 v7; // rax
  HRESULT result; // eax
  __int64 v9; // [rsp+28h] [rbp-30h] BYREF
  char v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = a4;
  v7 = lambda_e523a1bc6b5071a9b755155d5c586746_::_lambda_e523a1bc6b5071a9b755155d5c586746_(&v9, a2, a3, &v10);
  ConnectedStorage::Context::EnqueueOperation__lambda_e523a1bc6b5071a9b755155d5c586746___(a1, v7);
  WindowsDeleteString(*a2);
  *a2 = 0;
  result = WindowsDeleteString(*a3);
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18005c030  mov     rax, rsp
0x18005c033  mov     [rax+20h], r9b
0x18005c037  mov     [rax+18h], r8
0x18005c03b  mov     [rax+10h], rdx
0x18005c03f  push    rbx
0x18005c040  push    rsi
0x18005c041  push    rdi
0x18005c042  sub     rsp, 40h
0x18005c046  mov     rsi, r8
0x18005c049  mov     rdi, rdx
0x18005c04c  mov     rbx, rcx
0x18005c04f  lea     r9, [rax+20h]
0x18005c053  lea     rcx, [rax-30h]
0x18005c057  call    _lambda_e523a1bc6b5071a9b755155d5c586746____lambda_e523a1bc6b5071a9b755155d5c586746_
0x18005c05c  mov     rdx, rax
0x18005c05f  mov     rcx, rbx
0x18005c062  call    ConnectedStorage__Context__EnqueueOperation__lambda_e523a1bc6b5071a9b755155d5c586746___
0x18005c067  nop
0x18005c068  mov     rcx, [rdi]; string
0x18005c06b  call    cs:__imp_WindowsDeleteString
0x18005c071  mov     qword ptr [rdi], 0
0x18005c078  mov     rcx, [rsi]; string
0x18005c07b  call    cs:__imp_WindowsDeleteString
0x18005c081  mov     qword ptr [rsi], 0
0x18005c088  add     rsp, 40h
0x18005c08c  pop     rdi
0x18005c08d  pop     rsi
0x18005c08e  pop     rbx
0x18005c08f  retn
```
