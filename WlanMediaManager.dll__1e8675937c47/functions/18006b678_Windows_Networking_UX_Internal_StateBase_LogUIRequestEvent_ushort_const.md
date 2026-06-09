# Windows::Networking::UX::Internal::StateBase::LogUIRequestEvent(ushort const *)

- ea: `0x18006b678`
- end: `0x18006b76e`
- name: `?LogUIRequestEvent@StateBase@Internal@UX@Networking@Windows@@IEAAXPEBG@Z`
- size: `246`
- prototype: `void(Windows::Networking::UX::Internal::StateBase *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18006ffc0`
- `0x1800701b0`

## callees

- `0x180003ed0`
- `0x18006b678`
- `0x18006c4e4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b700`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b700`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b6c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b74b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b6c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b74b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::StateBase::LogUIRequestEvent(
        Windows::Networking::UX::Internal::StateBase *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *StringRawBuffer; // rbx
  __int128 v8; // xmm0
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+28h] [rbp-40h] BYREF
  __int128 v11; // [rsp+2Ch] [rbp-3Ch]
  int v12; // [rsp+3Ch] [rbp-2Ch]

  string = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2));
  v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v4 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v5(v4, &string) >= 0 )
  {
    v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(Windows::Networking::UX::Internal::StateBase *))(*(_QWORD *)this + 160LL))(this);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 104LL))(*((_QWORD *)this + 2));
    v10 = 13;
    v11 = v8;
    v12 = 71;
    NetworkingTriageScenario::GetConnected::UXModelWiFiUIRequestReceivedEvent(
      (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v10,
      StringRawBuffer,
      v6,
      a2);
  }
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18006b678  mov     [rsp+arg_10], rbx
0x18006b67d  push    rbp
0x18006b67e  push    rsi
0x18006b67f  push    rdi
0x18006b680  sub     rsp, 50h
0x18006b684  mov     rax, cs:__security_cookie
0x18006b68b  xor     rax, rsp
0x18006b68e  mov     [rsp+68h+var_28], rax
0x18006b693  mov     rbp, rdx
0x18006b696  mov     rsi, rcx
0x18006b699  mov     [rsp+68h+string], 0
0x18006b6a2  mov     rcx, [rcx+10h]
0x18006b6a6  mov     rax, [rcx]
0x18006b6a9  mov     rax, [rax+60h]
0x18006b6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6b2  mov     rdi, rax
0x18006b6b5  mov     rcx, [rax]
0x18006b6b8  mov     rbx, [rcx+30h]
0x18006b6bc  mov     rcx, [rsp+68h+string]; string
0x18006b6c1  call    cs:__imp_WindowsDeleteString
0x18006b6c7  mov     [rsp+68h+string], 0
0x18006b6d0  lea     rdx, [rsp+68h+string]
0x18006b6d5  mov     rcx, rdi
0x18006b6d8  mov     rax, rbx
0x18006b6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6e0  test    eax, eax
0x18006b6e2  js      short loc_18006B746
0x18006b6e4  mov     rax, [rsi]
0x18006b6e7  mov     rcx, rsi
0x18006b6ea  mov     rax, [rax+0A0h]
0x18006b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6f6  mov     rdi, rax
0x18006b6f9  xor     edx, edx; length
0x18006b6fb  mov     rcx, [rsp+68h+string]; string
0x18006b700  call    cs:__imp_WindowsGetStringRawBuffer
0x18006b706  mov     rbx, rax
0x18006b709  mov     rcx, [rsi+10h]
0x18006b70d  mov     rdx, [rcx]
0x18006b710  mov     rax, [rdx+68h]
0x18006b714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b719  movups  xmm0, xmmword ptr [rax]
0x18006b71c  mov     [rsp+68h+var_40], 0Dh
0x18006b724  movdqu  [rsp+68h+var_3C], xmm0
0x18006b72a  mov     [rsp+68h+var_2C], 47h ; 'G'
0x18006b732  mov     r9, rbp; unsigned __int16 *
0x18006b735  mov     r8, rdi; unsigned __int16 *
0x18006b738  mov     rdx, rbx; unsigned __int16 *
0x18006b73b  lea     rcx, [rsp+68h+var_40]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18006b740  call    ?UXModelWiFiUIRequestReceivedEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG11@Z; NetworkingTriageScenario::GetConnected::UXModelWiFiUIRequestReceivedEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,ushort const *,ushort const *)
0x18006b745  nop
0x18006b746  mov     rcx, [rsp+68h+string]; string
0x18006b74b  call    cs:__imp_WindowsDeleteString
0x18006b751  mov     rcx, [rsp+68h+var_28]
0x18006b756  xor     rcx, rsp; StackCookie
0x18006b759  call    __security_check_cookie
0x18006b75e  mov     rbx, [rsp+68h+arg_10]
0x18006b766  add     rsp, 50h
0x18006b76a  pop     rdi
0x18006b76b  pop     rsi
0x18006b76c  pop     rbp
0x18006b76d  retn
```
