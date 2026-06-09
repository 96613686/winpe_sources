# ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(uint,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x180029824`
- end: `0x1800298c4`
- name: `??0LocalUserInfo@UserManager@ConnectedStorage@@QEAA@IAEBVSimpleHStringWrapper@2@0@Z`
- size: `160`
- prototype: `HSTRING *__fastcall(HSTRING *this, unsigned int, const struct ConnectedStorage::SimpleHStringWrapper *, const struct ConnectedStorage::SimpleHStringWrapper *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002b5b0`
- `0x18002da8c`

## callees

- `0x180003c70`
- `0x180011b94`
- `0x180011c0c`
- `0x180012ed8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002987d`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002987d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(
        HSTRING *this,
        unsigned int a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3,
        const struct ConnectedStorage::SimpleHStringWrapper *a4)
{
  HSTRING string[2]; // [rsp+20h] [rbp-58h] BYREF
  WCHAR sourceString[16]; // [rsp+30h] [rbp-48h] BYREF

  string[1] = (HSTRING)this;
  *(_DWORD *)this = a2;
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(this + 1, a4);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(this + 2, a3);
  this[3] = 0;
  _o__ultow_s(a2, sourceString, 15);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, sourceString);
  ConnectedStorage::SimpleHStringWrapper::operator=(this + 3);
  WindowsDeleteString(string[0]);
  return this;
}

```

## disassembly

```asm
0x180029824  push    rbx
0x180029826  push    rsi
0x180029827  push    rdi
0x180029828  sub     rsp, 60h
0x18002982c  mov     rax, cs:__security_cookie
0x180029833  xor     rax, rsp
0x180029836  mov     [rsp+78h+var_28], rax
0x18002983b  mov     rbx, r8
0x18002983e  mov     edi, edx
0x180029840  mov     rsi, rcx
0x180029843  mov     [rsp+78h+var_50], rcx
0x180029848  mov     [rcx], edx
0x18002984a  add     rcx, 8; newString
0x18002984e  mov     rdx, r9; struct ConnectedStorage::SimpleHStringWrapper *
0x180029851  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180029856  nop
0x180029857  lea     rcx, [rsi+10h]; newString
0x18002985b  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18002985e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180029863  nop
0x180029864  mov     qword ptr [rsi+18h], 0
0x18002986c  mov     r9d, 0Ah
0x180029872  lea     r8d, [r9+5]
0x180029876  lea     rdx, [rsp+78h+sourceString]
0x18002987b  mov     ecx, edi
0x18002987d  call    cs:__imp__o__ultow_s
0x180029883  lea     rdx, [rsp+78h+sourceString]; sourceString
0x180029888  lea     rcx, [rsp+78h+string]; string
0x18002988d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180029892  nop
0x180029893  mov     rdx, rax
0x180029896  lea     rcx, [rsi+18h]; newString
0x18002989a  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002989f  nop
0x1800298a0  mov     rcx, [rsp+78h+string]; string
0x1800298a5  call    cs:__imp_WindowsDeleteString
0x1800298ab  nop
0x1800298ac  mov     rax, rsi
0x1800298af  mov     rcx, [rsp+78h+var_28]
0x1800298b4  xor     rcx, rsp; StackCookie
0x1800298b7  call    __security_check_cookie
0x1800298bc  add     rsp, 60h
0x1800298c0  pop     rdi
0x1800298c1  pop     rsi
0x1800298c2  pop     rbx
0x1800298c3  retn
```
