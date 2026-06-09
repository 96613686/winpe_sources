# _lambda_1737a0e7fb134fea92332ee7c26f729c_::operator()

- ea: `0x18003fa60`
- end: `0x18003fbc0`
- name: `_lambda_1737a0e7fb134fea92332ee7c26f729c_::operator()`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180047e60`

## callees

- `0x180014fdc`
- `0x18001e208`
- `0x180022dec`
- `0x18003a1e8`
- `0x18003fa60`
- `0x180043dd0`
- `0x1800852fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003faa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003faa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall lambda_1737a0e7fb134fea92332ee7c26f729c_::operator()(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  char TimeMs; // di
  char v9; // si
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v11; // rax
  const unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  const struct ConnectedStorage::SimpleHStringWrapper *v14; // rbx
  ConnectedStorage *v15; // rax
  unsigned __int64 *v16; // r9
  const struct ConnectedStorage::SimpleHStringWrapper *AddressOf; // rbx
  ConnectedStorage *v18; // rax
  unsigned __int64 *v19; // r9
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v22; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v23; // [rsp+88h] [rbp+48h] BYREF

  v22 = 0;
  v23 = 0;
  TimeMs = ConnectedStorage::Timer::GetTimeMs((ConnectedStorage::Timer *)(a1 + 128));
  v9 = *(_BYTE *)(a1 + 120);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 88), 0);
  v11 = (ConnectedStorage *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 96), 0);
  LOBYTE(v12) = v9;
  ConnectedStorage::EventWriteWebAcquireLock(v11, StringRawBuffer, v12, TimeMs, a4, a3, (unsigned int)string[0]);
  switch ( *(_WORD *)(a2 + 48) )
  {
    case 0xC8:
      AddressOf = (const struct ConnectedStorage::SimpleHStringWrapper *)ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v22);
      v18 = (ConnectedStorage *)ConnectedStorage::FromUtf8(string);
      ConnectedStorage::ParseAcquireLockResponse(v18, AddressOf, &v23, v19);
      WindowsDeleteString(string[0]);
      v13 = 4;
      break;
    case 0xC9:
      v14 = (const struct ConnectedStorage::SimpleHStringWrapper *)ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v22);
      v15 = (ConnectedStorage *)ConnectedStorage::FromUtf8(string);
      ConnectedStorage::ParseAcquireLockResponse(v15, v14, &v23, v16);
      WindowsDeleteString(string[0]);
      v13 = 5;
      break;
    case 0x193:
      v13 = 17;
      break;
    default:
      v13 = 6;
      if ( *(_WORD *)(a2 + 48) != 409 )
        v13 = 1;
      break;
  }
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(
    a1,
    v13,
    &v22);
  return WindowsDeleteString(v22);
}

```

## disassembly

```asm
0x18003fa60  mov     [rsp-38h+arg_10], rbx
0x18003fa65  push    rbp
0x18003fa66  push    rsi
0x18003fa67  push    rdi
0x18003fa68  push    r12
0x18003fa6a  push    r13
0x18003fa6c  push    r14
0x18003fa6e  push    r15
0x18003fa70  mov     rbp, rsp
0x18003fa73  sub     rsp, 40h
0x18003fa77  mov     r15d, r9d
0x18003fa7a  mov     r14d, r8d
0x18003fa7d  mov     r12, rdx
0x18003fa80  mov     r13, rcx
0x18003fa83  mov     [rbp+arg_0], 0
0x18003fa8b  mov     [rbp+arg_8], 0
0x18003fa93  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x18003fa97  call    ?GetTimeMs@Timer@ConnectedStorage@@QEBAIXZ; ConnectedStorage::Timer::GetTimeMs(void)
0x18003fa9c  mov     edi, eax
0x18003fa9e  mov     sil, [r13+78h]
0x18003faa2  xor     edx, edx; length
0x18003faa4  mov     rcx, [r13+58h]; string
0x18003faa8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003faae  mov     rbx, rax
0x18003fab1  xor     edx, edx; length
0x18003fab3  mov     rcx, [r13+60h]; string
0x18003fab7  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fabd  mov     [rsp+40h+var_18], r14d; unsigned int
0x18003fac2  mov     [rsp+40h+var_20], r15d; unsigned int
0x18003fac7  mov     r9d, edi; bool
0x18003faca  mov     r8b, sil; unsigned __int16 *
0x18003facd  mov     rdx, rbx; unsigned __int16 *
0x18003fad0  mov     rcx, rax; this
0x18003fad3  call    ?EventWriteWebAcquireLock@ConnectedStorage@@YAXQEBG0_NIII@Z; ConnectedStorage::EventWriteWebAcquireLock(ushort const * const,ushort const * const,bool,uint,uint,uint)
0x18003fad8  movzx   ecx, word ptr [r12+30h]
0x18003fade  sub     ecx, 0C8h
0x18003fae4  jz      short loc_18003FB50
0x18003fae6  sub     ecx, 1
0x18003fae9  jz      short loc_18003FB11
0x18003faeb  sub     ecx, 0CAh
0x18003faf1  jz      short loc_18003FB0A
0x18003faf3  mov     edx, 6
0x18003faf8  cmp     ecx, edx
0x18003fafa  jz      loc_18003FB8D
0x18003fb00  mov     edx, 1
0x18003fb05  jmp     loc_18003FB8D
0x18003fb0a  mov     edx, 11h
0x18003fb0f  jmp     short loc_18003FB8D
0x18003fb11  lea     rcx, [rbp+arg_0]; this
0x18003fb15  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18003fb1a  mov     rbx, rax
0x18003fb1d  mov     rdx, [r13+40h]
0x18003fb21  add     rdx, 10h
0x18003fb25  lea     rcx, [rbp+string]; string
0x18003fb29  call    ?FromUtf8@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConnectedStorage::FromUtf8(std::string const &)
0x18003fb2e  nop
0x18003fb2f  lea     r8, [rbp+arg_8]; HSTRING *
0x18003fb33  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18003fb36  mov     rcx, rax; this
0x18003fb39  call    ?ParseAcquireLockResponse@ConnectedStorage@@YAXAEBVSimpleHStringWrapper@1@PEAPEAUHSTRING__@@PEA_K@Z; ConnectedStorage::ParseAcquireLockResponse(ConnectedStorage::SimpleHStringWrapper const &,HSTRING__ * *,unsigned __int64 *)
0x18003fb3e  nop
0x18003fb3f  mov     rcx, [rbp+string]; string
0x18003fb43  call    cs:__imp_WindowsDeleteString
0x18003fb49  mov     edx, 5
0x18003fb4e  jmp     short loc_18003FB8D
0x18003fb50  lea     rcx, [rbp+arg_0]; this
0x18003fb54  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18003fb59  mov     rbx, rax
0x18003fb5c  mov     rdx, [r13+40h]
0x18003fb60  add     rdx, 10h
0x18003fb64  lea     rcx, [rbp+string]; string
0x18003fb68  call    ?FromUtf8@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConnectedStorage::FromUtf8(std::string const &)
0x18003fb6d  nop
0x18003fb6e  lea     r8, [rbp+arg_8]; HSTRING *
0x18003fb72  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18003fb75  mov     rcx, rax; this
0x18003fb78  call    ?ParseAcquireLockResponse@ConnectedStorage@@YAXAEBVSimpleHStringWrapper@1@PEAPEAUHSTRING__@@PEA_K@Z; ConnectedStorage::ParseAcquireLockResponse(ConnectedStorage::SimpleHStringWrapper const &,HSTRING__ * *,unsigned __int64 *)
0x18003fb7d  nop
0x18003fb7e  mov     rcx, [rbp+string]; string
0x18003fb82  call    cs:__imp_WindowsDeleteString
0x18003fb88  mov     edx, 4
0x18003fb8d  mov     r9, [rbp+arg_8]
0x18003fb91  lea     r8, [rbp+arg_0]
0x18003fb95  mov     rcx, r13
0x18003fb98  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@_K@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x18003fb9d  nop
0x18003fb9e  mov     rcx, [rbp+arg_0]; string
0x18003fba2  call    cs:__imp_WindowsDeleteString
0x18003fba8  mov     rbx, [rsp+40h+arg_10]
0x18003fbb0  add     rsp, 40h
0x18003fbb4  pop     r15
0x18003fbb6  pop     r14
0x18003fbb8  pop     r13
0x18003fbba  pop     r12
0x18003fbbc  pop     rdi
0x18003fbbd  pop     rsi
0x18003fbbe  pop     rbp
0x18003fbbf  retn
```
