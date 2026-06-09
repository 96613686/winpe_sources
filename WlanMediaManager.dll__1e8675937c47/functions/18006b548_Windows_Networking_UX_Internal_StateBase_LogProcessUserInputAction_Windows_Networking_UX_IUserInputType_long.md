# Windows::Networking::UX::Internal::StateBase::LogProcessUserInputAction(Windows::Networking::UX::IUserInputType *,long)

- ea: `0x18006b548`
- end: `0x18006b672`
- name: `?LogProcessUserInputAction@StateBase@Internal@UX@Networking@Windows@@IEAAXPEAUIUserInputType@345@J@Z`
- size: `298`
- prototype: `void(Windows::Networking::UX::Internal::StateBase *__hidden this, struct Windows::Networking::UX::IUserInputType *, int)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180070900`
- `0x180070c00`
- `0x180070e80`
- `0x180071060`
- `0x180071360`
- `0x180071550`
- `0x180071840`
- `0x180071af0`

## callees

- `0x180003ed0`
- `0x1800481a4`
- `0x18006b548`
- `0x18006c374`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b64c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b64c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::StateBase::LogProcessUserInputAction(
        Windows::Networking::UX::Internal::StateBase *this,
        struct Windows::Networking::UX::IUserInputType *a2,
        int a3)
{
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *StringRawBuffer; // rbx
  __int128 v11; // xmm0
  unsigned int v12; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  int v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+44h] [rbp-1Ch]
  int v16; // [rsp+54h] [rbp-Ch]

  string = 0;
  v12 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2));
  v7 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v7(v6, &string) >= 0
    && (*(int (__fastcall **)(struct Windows::Networking::UX::IUserInputType *, unsigned int *))(*(_QWORD *)a2 + 48LL))(
         a2,
         &v12) >= 0 )
  {
    v8 = (const unsigned __int16 *)Windows::Networking::UX::Internal::UserInputTypeAsString(v12);
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(Windows::Networking::UX::Internal::StateBase *))(*(_QWORD *)this + 160LL))(this);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 104LL))(*((_QWORD *)this + 2));
    v14 = 13;
    v15 = v11;
    v16 = 71;
    NetworkingTriageScenario::GetConnected::UXModelWiFiProcessUserInputAction(
      (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v14,
      StringRawBuffer,
      v9,
      v8,
      a3);
  }
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18006b548  mov     [rsp-28h+arg_10], rbx
0x18006b54d  push    rbp
0x18006b54e  push    rsi
0x18006b54f  push    rdi
0x18006b550  push    r14
0x18006b552  push    r15
0x18006b554  mov     rbp, rsp
0x18006b557  sub     rsp, 60h
0x18006b55b  mov     rax, cs:__security_cookie
0x18006b562  xor     rax, rsp
0x18006b565  mov     [rbp+var_8], rax
0x18006b569  mov     r15d, r8d
0x18006b56c  mov     rsi, rdx
0x18006b56f  mov     r14, rcx
0x18006b572  mov     [rbp+string], 0
0x18006b57a  mov     [rbp+var_30], 0
0x18006b581  mov     rcx, [rcx+10h]
0x18006b585  mov     rax, [rcx]
0x18006b588  mov     rax, [rax+60h]
0x18006b58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b591  mov     rdi, rax
0x18006b594  mov     rcx, [rax]
0x18006b597  mov     rbx, [rcx+30h]
0x18006b59b  mov     rcx, [rbp+string]; string
0x18006b59f  call    cs:__imp_WindowsDeleteString
0x18006b5a5  mov     [rbp+string], 0
0x18006b5ad  lea     rdx, [rbp+string]
0x18006b5b1  mov     rcx, rdi
0x18006b5b4  mov     rax, rbx
0x18006b5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5bc  test    eax, eax
0x18006b5be  js      loc_18006B648
0x18006b5c4  mov     rax, [rsi]
0x18006b5c7  lea     rdx, [rbp+var_30]
0x18006b5cb  mov     rcx, rsi
0x18006b5ce  mov     rax, [rax+30h]
0x18006b5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5d7  test    eax, eax
0x18006b5d9  js      short loc_18006B648
0x18006b5db  mov     ecx, [rbp+var_30]
0x18006b5de  call    ?UserInputTypeAsString@Internal@UX@Networking@Windows@@YAPEBGW4UserInputType@234@@Z; Windows::Networking::UX::Internal::UserInputTypeAsString(Windows::Networking::UX::UserInputType)
0x18006b5e3  mov     rsi, rax
0x18006b5e6  mov     rcx, [r14]
0x18006b5e9  mov     rax, [rcx+0A0h]
0x18006b5f0  mov     rcx, r14
0x18006b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5f8  mov     rdi, rax
0x18006b5fb  xor     edx, edx; length
0x18006b5fd  mov     rcx, [rbp+string]; string
0x18006b601  call    cs:__imp_WindowsGetStringRawBuffer
0x18006b607  mov     rbx, rax
0x18006b60a  mov     rcx, [r14+10h]
0x18006b60e  mov     rdx, [rcx]
0x18006b611  mov     rax, [rdx+68h]
0x18006b615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b61a  movups  xmm0, xmmword ptr [rax]
0x18006b61d  mov     [rbp+var_20], 0Dh
0x18006b624  movdqu  [rbp+var_1C], xmm0
0x18006b629  mov     [rbp+var_C], 47h ; 'G'
0x18006b630  mov     [rsp+60h+var_40], r15d; int
0x18006b635  mov     r9, rsi; unsigned __int16 *
0x18006b638  mov     r8, rdi; unsigned __int16 *
0x18006b63b  mov     rdx, rbx; unsigned __int16 *
0x18006b63e  lea     rcx, [rbp+var_20]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18006b642  call    ?UXModelWiFiProcessUserInputAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG11J@Z; NetworkingTriageScenario::GetConnected::UXModelWiFiProcessUserInputAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,ushort const *,ushort const *,long)
0x18006b647  nop
0x18006b648  mov     rcx, [rbp+string]; string
0x18006b64c  call    cs:__imp_WindowsDeleteString
0x18006b652  mov     rcx, [rbp+var_8]
0x18006b656  xor     rcx, rsp; StackCookie
0x18006b659  call    __security_check_cookie
0x18006b65e  mov     rbx, [rsp+60h+arg_10]
0x18006b666  add     rsp, 60h
0x18006b66a  pop     r15
0x18006b66c  pop     r14
0x18006b66e  pop     rdi
0x18006b66f  pop     rsi
0x18006b670  pop     rbp
0x18006b671  retn
```
