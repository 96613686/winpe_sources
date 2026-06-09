# ConnectedStorage::IsRunningOnConsole(void)

- ea: `0x180085038`
- end: `0x1800851db`
- name: `?IsRunningOnConsole@ConnectedStorage@@YA_NXZ`
- size: `419`
- prototype: `bool __fastcall(ConnectedStorage *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f8dc`
- `0x18002b0b0`
- `0x18002bb94`
- `0x18002c408`
- `0x18002ca10`
- `0x180043208`

## callees

- `0x180003c70`
- `0x18002a6a8`
- `0x180085038`
- `0x18008e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085111`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085111`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800850a1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800850a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085101`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall ConnectedStorage::IsRunningOnConsole(ConnectedStorage *this)
{
  __int64 v1; // rdi
  int (__fastcall *v2)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  bool v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]

  v12 = 0;
  v11 = 0;
  string = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Profile.AnalyticsInfo",
    0x25u,
    0x24u);
  if ( (int)RoGetActivationFactory(v14, &GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305, &v12) < 0
    || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 48LL))(v12, &v11) < 0
    || (v1 = v11,
        v2 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 48LL),
        WindowsDeleteString(string),
        string = 0,
        v2(v1, &string) < 0) )
  {
    WindowsDeleteString(string);
    string = 0;
    v8 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return 0;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v4 = (unsigned int)_o__wcsicmp(L"Windows.Xbox", StringRawBuffer) == 0;
    WindowsDeleteString(string);
    string = 0;
    v5 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v4;
  }
}

```

## disassembly

```asm
0x180085038  mov     [rsp-8+arg_0], rbx
0x18008503d  mov     [rsp-8+arg_8], rdi
0x180085042  push    rbp
0x180085043  mov     rbp, rsp
0x180085046  sub     rsp, 60h
0x18008504a  mov     rax, cs:__security_cookie
0x180085051  xor     rax, rsp
0x180085054  mov     [rbp+var_8], rax
0x180085058  mov     [rbp+var_30], 0
0x180085060  mov     [rbp+var_38], 0
0x180085068  mov     [rbp+string], 0
0x180085070  mov     [rbp+var_10], 0
0x180085078  mov     r9d, 24h ; '$'; unsigned int
0x18008507e  lea     r8d, [r9+1]; unsigned int
0x180085082  lea     rdx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QBGB; "Windows.System.Profile.AnalyticsInfo"
0x180085089  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008508d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085092  lea     r8, [rbp+var_30]
0x180085096  lea     rdx, _GUID_1d5ee066_188d_5ba9_4387_acaeb0e7e305
0x18008509d  mov     rcx, [rbp+var_10]
0x1800850a1  call    cs:__imp_RoGetActivationFactory
0x1800850a7  test    eax, eax
0x1800850a9  js      loc_18008516F
0x1800850af  mov     rcx, [rbp+var_30]
0x1800850b3  mov     rax, [rcx]
0x1800850b6  lea     rdx, [rbp+var_38]
0x1800850ba  mov     rax, [rax+30h]
0x1800850be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850c3  test    eax, eax
0x1800850c5  js      loc_18008516F
0x1800850cb  mov     rdi, [rbp+var_38]
0x1800850cf  mov     rax, [rdi]
0x1800850d2  mov     rbx, [rax+30h]
0x1800850d6  mov     rcx, [rbp+string]; string
0x1800850da  call    cs:__imp_WindowsDeleteString
0x1800850e0  mov     [rbp+string], 0
0x1800850e8  lea     rdx, [rbp+string]
0x1800850ec  mov     rcx, rdi
0x1800850ef  mov     rax, rbx
0x1800850f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850f7  test    eax, eax
0x1800850f9  js      short loc_18008516F
0x1800850fb  xor     edx, edx; length
0x1800850fd  mov     rcx, [rbp+string]; string
0x180085101  call    cs:__imp_WindowsGetStringRawBuffer
0x180085107  mov     rdx, rax
0x18008510a  lea     rcx, aWindowsXbox; "Windows.Xbox"
0x180085111  call    cs:__imp__o__wcsicmp
0x180085117  nop
0x180085118  test    eax, eax
0x18008511a  setz    bl
0x18008511d  mov     rcx, [rbp+string]; string
0x180085121  call    cs:__imp_WindowsDeleteString
0x180085127  mov     [rbp+string], 0
0x18008512f  mov     rcx, [rbp+var_38]
0x180085133  test    rcx, rcx
0x180085136  jz      short loc_18008514D
0x180085138  mov     [rbp+var_38], 0
0x180085140  mov     rax, [rcx]
0x180085143  mov     rax, [rax+10h]
0x180085147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008514c  nop
0x18008514d  mov     rcx, [rbp+var_30]
0x180085151  test    rcx, rcx
0x180085154  jz      short loc_18008516B
0x180085156  mov     [rbp+var_30], 0
0x18008515e  mov     rdx, [rcx]
0x180085161  mov     rax, [rdx+10h]
0x180085165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008516a  nop
0x18008516b  mov     al, bl
0x18008516d  jmp     short loc_1800851BF
0x18008516f  mov     rcx, [rbp+string]; string
0x180085173  call    cs:__imp_WindowsDeleteString
0x180085179  mov     [rbp+string], 0
0x180085181  mov     rcx, [rbp+var_38]
0x180085185  test    rcx, rcx
0x180085188  jz      short loc_18008519F
0x18008518a  mov     [rbp+var_38], 0
0x180085192  mov     rax, [rcx]
0x180085195  mov     rax, [rax+10h]
0x180085199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008519e  nop
0x18008519f  mov     rcx, [rbp+var_30]
0x1800851a3  test    rcx, rcx
0x1800851a6  jz      short loc_1800851BD
0x1800851a8  mov     [rbp+var_30], 0
0x1800851b0  mov     rax, [rcx]
0x1800851b3  mov     rax, [rax+10h]
0x1800851b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800851bc  nop
0x1800851bd  xor     al, al
0x1800851bf  mov     rcx, [rbp+var_8]
0x1800851c3  xor     rcx, rsp; StackCookie
0x1800851c6  call    __security_check_cookie
0x1800851cb  mov     rbx, [rsp+60h+arg_0]
0x1800851d0  mov     rdi, [rsp+60h+arg_8]
0x1800851d5  add     rsp, 60h
0x1800851d9  pop     rbp
0x1800851da  retn
```
