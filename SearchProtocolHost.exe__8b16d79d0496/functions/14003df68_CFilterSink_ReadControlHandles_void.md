# CFilterSink::ReadControlHandles(void)

- ea: `0x14003df68`
- end: `0x14003e107`
- name: `?ReadControlHandles@CFilterSink@@QEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(CFilterSink *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x140005240`
- `0x14000e97c`
- `0x1400317a8`
- `0x140037ca8`
- `0x14003cc34`
- `0x14003dd60`
- `0x14003df68`
- `0x14004a0c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14003e04d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14003e0c9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14003e04d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14003e0c9`

## string_xrefs

- `0x14003dfa4`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003e001`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003e037`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003e07d`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003e0b3`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFilterSink::ReadControlHandles(CFilterSink *this)
{
  int Buffer; // eax
  int WStr; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v8; // [rsp+28h] [rbp-39h] BYREF
  wchar_t *v9[3]; // [rsp+30h] [rbp-31h] BYREF
  void **v10; // [rsp+48h] [rbp-19h] BYREF
  __int16 *v11; // [rsp+50h] [rbp-11h]
  __int64 v12; // [rsp+58h] [rbp-9h]
  __int16 v13; // [rsp+60h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v9[1] = (wchar_t *)-2LL;
  Buffer = CFilterSink::ReadBuffer(this);
  if ( Buffer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x607,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)(unsigned int)Buffer,
      v8);
  v9[0] = 0;
  v8 = 0;
  v11 = &v13;
  v12 = 33;
  v13 = 0;
  v10 = &TLMString<32,32,1024>::`vftable';
  WStr = CFilterSink::GetWStr(this, v9, &v8);
  if ( WStr < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)(unsigned int)WStr,
      v8);
  CLMString::Assign((CLMString *)&v10, v9[0], 0, v8);
  if ( !HIDWORD(v12) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x613,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)0x80070057LL,
      v8);
  v4 = _o__wtoi(v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &g_hGthr,
    v4);
  v5 = CFilterSink::GetWStr(this, v9, &v8);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)(unsigned int)v5,
      v8);
  CLMString::Assign((CLMString *)&v10, v9[0], 0, v8);
  if ( !HIDWORD(v12) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x620,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)0x80070057LL,
      v8);
  v6 = _o__wtoi(v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &g_hPHBackoffCtrlEv,
    v6);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(&v10);
  return 0;
}

```

## disassembly

```asm
0x14003df68  mov     rax, rsp
0x14003df6b  push    rbp
0x14003df6c  lea     rbp, [rax-5Fh]
0x14003df70  sub     rsp, 0B0h
0x14003df77  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x14003df7f  mov     [rax+10h], rbx
0x14003df83  mov     rax, cs:__security_cookie
0x14003df8a  xor     rax, rsp
0x14003df8d  mov     [rbp+57h+var_10], rax
0x14003df91  mov     rbx, rcx
0x14003df94  call    ?ReadBuffer@CFilterSink@@AEAAJXZ; CFilterSink::ReadBuffer(void)
0x14003df99  mov     rcx, [rbp+5Fh]; this
0x14003df9d  test    eax, eax
0x14003df9f  jns     short loc_14003DFB6
0x14003dfa1  mov     r9d, eax; char *
0x14003dfa4  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003dfab  mov     edx, 607h; void *
0x14003dfb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003dfb6  mov     [rbp+57h+var_88], 0
0x14003dfbe  mov     [rbp+57h+var_90], 0
0x14003dfc5  lea     rax, [rbp+57h+var_58]
0x14003dfc9  mov     [rbp+57h+var_68], rax
0x14003dfcd  mov     [rbp+57h+var_60], 21h ; '!'
0x14003dfd5  xor     eax, eax
0x14003dfd7  mov     [rbp+57h+var_58], ax
0x14003dfdb  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x14003dfe2  mov     [rbp+57h+var_70], rax
0x14003dfe6  lea     r8, [rbp+57h+var_90]; unsigned int *
0x14003dfea  lea     rdx, [rbp+57h+var_88]; wchar_t **
0x14003dfee  mov     rcx, rbx; this
0x14003dff1  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003dff6  mov     rcx, [rbp+5Fh]; this
0x14003dffa  test    eax, eax
0x14003dffc  jns     short loc_14003E013
0x14003dffe  mov     r9d, eax; char *
0x14003e001  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003e008  mov     edx, 60Eh; void *
0x14003e00d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003e013  mov     r9d, [rbp+57h+var_90]; unsigned int
0x14003e017  xor     r8d, r8d; unsigned int
0x14003e01a  mov     rdx, [rbp+57h+var_88]; wchar_t *
0x14003e01e  lea     rcx, [rbp+57h+var_70]; this
0x14003e022  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x14003e027  cmp     dword ptr [rbp+57h+var_60+4], 0
0x14003e02b  jnz     short loc_14003E049
0x14003e02d  mov     rcx, [rbp+5Fh]; this
0x14003e031  mov     r9d, 80070057h; char *
0x14003e037  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003e03e  mov     edx, 613h; void *
0x14003e043  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003e049  mov     rcx, [rbp+57h+var_68]
0x14003e04d  call    cs:__imp__o__wtoi
0x14003e053  movsxd  rdx, eax
0x14003e056  lea     rcx, ?g_hGthr@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hGthr
0x14003e05d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14003e062  lea     r8, [rbp+57h+var_90]; unsigned int *
0x14003e066  lea     rdx, [rbp+57h+var_88]; wchar_t **
0x14003e06a  mov     rcx, rbx; this
0x14003e06d  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003e072  mov     rcx, [rbp+5Fh]; this
0x14003e076  test    eax, eax
0x14003e078  jns     short loc_14003E08F
0x14003e07a  mov     r9d, eax; char *
0x14003e07d  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003e084  mov     edx, 61Bh; void *
0x14003e089  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003e08f  mov     r9d, [rbp+57h+var_90]; unsigned int
0x14003e093  xor     r8d, r8d; unsigned int
0x14003e096  mov     rdx, [rbp+57h+var_88]; wchar_t *
0x14003e09a  lea     rcx, [rbp+57h+var_70]; this
0x14003e09e  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x14003e0a3  cmp     dword ptr [rbp+57h+var_60+4], 0
0x14003e0a7  jnz     short loc_14003E0C5
0x14003e0a9  mov     rcx, [rbp+5Fh]; this
0x14003e0ad  mov     r9d, 80070057h; char *
0x14003e0b3  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003e0ba  mov     edx, 620h; void *
0x14003e0bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003e0c5  mov     rcx, [rbp+57h+var_68]
0x14003e0c9  call    cs:__imp__o__wtoi
0x14003e0cf  movsxd  rdx, eax
0x14003e0d2  lea     rcx, ?g_hPHBackoffCtrlEv@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hPHBackoffCtrlEv
0x14003e0d9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14003e0de  nop
0x14003e0df  lea     rcx, [rbp+57h+var_70]
0x14003e0e3  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x14003e0e8  xor     eax, eax
0x14003e0ea  mov     rcx, [rbp+57h+var_10]
0x14003e0ee  xor     rcx, rsp; StackCookie
0x14003e0f1  call    __security_check_cookie
0x14003e0f6  mov     rbx, [rsp+0B0h+arg_8]
0x14003e0fe  add     rsp, 0B0h
0x14003e105  pop     rbp
0x14003e106  retn
```
