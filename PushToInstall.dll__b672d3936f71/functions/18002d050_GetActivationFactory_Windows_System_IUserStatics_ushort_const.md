# GetActivationFactory<Windows::System::IUserStatics>(ushort const *)

- ea: `0x18002d050`
- end: `0x18002d10e`
- name: `??$GetActivationFactory@UIUserStatics@System@Windows@@@@YA?AV?$ComPtr@UIUserStatics@System@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `190`
- prototype: `const WCHAR *__fastcall(const WCHAR *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002fc74`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002ce54`
- `0x18002d050`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0cf`

## string_xrefs

- `0x18002d0fc`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const WCHAR *__fastcall GetActivationFactory<Windows::System::IUserStatics>(
        const WCHAR *a1,
        __int64 a2,
        unsigned int a3)
{
  PVOID Reserved1; // rdi
  __int64 v5; // rcx
  int ActivationFactory; // eax
  const WCHAR *v8[2]; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v9; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8[1] = a1;
  v8[0] = L"Windows.System.User";
  *(_QWORD *)a1 = 0;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v9, v8, a3)[1].Reserved.Reserved1;
  v5 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    *(_QWORD *)a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  ActivationFactory = RoGetActivationFactory(Reserved1, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x18002d050  mov     r11, rsp
0x18002d053  mov     [r11+10h], rbx
0x18002d057  push    rdi
0x18002d058  sub     rsp, 60h
0x18002d05c  mov     rax, cs:__security_cookie
0x18002d063  xor     rax, rsp
0x18002d066  mov     [rsp+68h+var_10], rax
0x18002d06b  mov     rbx, rcx
0x18002d06e  mov     [r11-38h], rcx
0x18002d072  mov     [rsp+68h+var_48], 0
0x18002d07a  lea     rax, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18002d081  mov     [r11-40h], rax
0x18002d085  mov     qword ptr [rcx], 0
0x18002d08c  mov     [rsp+68h+var_48], 1; int
0x18002d094  lea     rdx, [r11-40h]
0x18002d098  lea     rcx, [r11-30h]
0x18002d09c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002d0a1  nop
0x18002d0a2  mov     rdi, [rax+18h]
0x18002d0a6  mov     rcx, [rbx]
0x18002d0a9  test    rcx, rcx
0x18002d0ac  jz      short loc_18002D0C2
0x18002d0ae  mov     qword ptr [rbx], 0
0x18002d0b5  mov     rax, [rcx]
0x18002d0b8  mov     rax, [rax+10h]
0x18002d0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0c1  nop
0x18002d0c2  mov     r8, rbx
0x18002d0c5  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x18002d0cc  mov     rcx, rdi
0x18002d0cf  call    cs:__imp_RoGetActivationFactory
0x18002d0d5  mov     rcx, [rsp+68h]; this
0x18002d0da  test    eax, eax
0x18002d0dc  js      short loc_18002D0F9
0x18002d0de  mov     rax, rbx
0x18002d0e1  mov     rcx, [rsp+68h+var_10]
0x18002d0e6  xor     rcx, rsp; StackCookie
0x18002d0e9  call    __security_check_cookie
0x18002d0ee  mov     rbx, [rsp+68h+arg_8]
0x18002d0f3  add     rsp, 60h
0x18002d0f7  pop     rdi
0x18002d0f8  retn
0x18002d0f9  mov     r9d, eax; char *
0x18002d0fc  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d103  mov     edx, 10h; void *
0x18002d108  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
