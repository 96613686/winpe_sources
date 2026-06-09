# to_string(_GUID)

- ea: `0x140034fb8`
- end: `0x140035078`
- name: `?to_string@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U_GUID@@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140034e80`

## callees

- `0x1400030a0`
- `0x140005f10`
- `0x1400198c4`
- `0x140034fb8`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x14003503d`
- `RPCRT4!RpcStringFreeW` at `0x14003503d`
- `RPCRT4!UuidToStringW` at `0x140034fff`
- `RPCRT4!UuidToStringW` at `0x140034fff`

## string_xrefs

- `0x140035011`: `onecoreuap\base\appmodel\Search\common\include\guid.h`
- `0x14003504f`: `onecoreuap\base\appmodel\Search\common\include\guid.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall to_string(unsigned __int16 *a1, UUID *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  RPC_WSTR String[3]; // [rsp+28h] [rbp-40h] BYREF
  UUID v7; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  String[1] = (RPC_WSTR)-2LL;
  String[2] = a1;
  v7 = *a2;
  String[0] = 0;
  v3 = UuidToStringW(&v7, String);
  if ( v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\guid.h",
      (const char *)v3,
      0);
  std::wstring::wstring((__int64)a1, (__int64)String[0]);
  v4 = RpcStringFreeW(String);
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\guid.h",
      (const char *)v4,
      1);
  return a1;
}

```

## disassembly

```asm
0x140034fb8  mov     r11, rsp
0x140034fbb  push    rbx
0x140034fbc  sub     rsp, 60h
0x140034fc0  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x140034fc8  mov     rax, cs:__security_cookie
0x140034fcf  xor     rax, rsp
0x140034fd2  mov     [rsp+68h+var_18], rax
0x140034fd7  mov     rbx, rcx
0x140034fda  mov     [r11-30h], rcx
0x140034fde  movups  xmm0, xmmword ptr [rdx]
0x140034fe1  movdqu  [rsp+68h+var_28], xmm0
0x140034fe7  mov     [rsp+68h+var_48], 0; int
0x140034fef  mov     qword ptr [r11-40h], 0
0x140034ff7  lea     rdx, [r11-40h]; StringUuid
0x140034ffb  lea     rcx, [r11-28h]; Uuid
0x140034fff  call    cs:__imp_UuidToStringW
0x140035005  test    eax, eax
0x140035007  jz      short loc_140035023
0x140035009  mov     rcx, [rsp+68h]; this
0x14003500e  mov     r9d, eax; char *
0x140035011  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140035018  mov     edx, 1Fh; void *
0x14003501d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140035023  mov     rdx, [rsp+68h+String]
0x140035028  mov     rcx, rbx
0x14003502b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140035030  mov     [rsp+68h+var_48], 1; int
0x140035038  lea     rcx, [rsp+68h+String]; String
0x14003503d  call    cs:__imp_RpcStringFreeW
0x140035043  test    eax, eax
0x140035045  jz      short loc_140035061
0x140035047  mov     rcx, [rsp+68h]; this
0x14003504c  mov     r9d, eax; char *
0x14003504f  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140035056  mov     edx, 28h ; '('; void *
0x14003505b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140035061  mov     rax, rbx
0x140035064  mov     rcx, [rsp+68h+var_18]
0x140035069  xor     rcx, rsp; StackCookie
0x14003506c  call    __security_check_cookie
0x140035071  add     rsp, 60h
0x140035075  pop     rbx
0x140035076  retn
```
