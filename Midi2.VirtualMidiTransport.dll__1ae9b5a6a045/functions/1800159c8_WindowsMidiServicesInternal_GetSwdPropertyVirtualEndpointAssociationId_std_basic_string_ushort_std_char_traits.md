# WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800159c8`
- end: `0x180015ade`
- name: `?GetSwdPropertyVirtualEndpointAssociationId@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `278`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180016740`
- `0x180016bec`
- `0x180017014`
- `0x180017670`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d1ac`
- `0x1800116e0`
- `0x1800117d8`
- `0x180015ae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  winrt::impl *SwdStringProperty; // rax
  __int128 v8; // [rsp+30h] [rbp-69h] BYREF
  __int64 v9; // [rsp+40h] [rbp-59h]
  __int64 v10; // [rsp+48h] [rbp-51h]
  __int128 v11; // [rsp+50h] [rbp-49h] BYREF
  __int64 v12; // [rsp+60h] [rbp-39h]
  __int64 v13; // [rsp+68h] [rbp-31h]
  __int128 *v14; // [rsp+70h] [rbp-29h]
  _BYTE v15[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v16[32]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+27h]
  unsigned __int16 v18[16]; // [rsp+C8h] [rbp+2Fh] BYREF

  v17 = a2;
  v4 = std::wstring::wstring(&v8, a2);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v18, v4);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v11, &S2);
  v14 = &v8;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v8, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 905");
  v5 = std::wstring::wstring(v15, v18);
  SwdStringProperty = WindowsMidiServicesInternal::GetSwdStringProperty((winrt::impl *)v16, v5, (__int64)&v8, &v11);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(a1, SwdStringProperty);
  std::wstring::~wstring(v18);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x1800159c8  mov     [rsp-8+arg_10], rbx
0x1800159cd  mov     [rsp-8+arg_18], rdi
0x1800159d2  push    rbp
0x1800159d3  lea     rbp, [rsp-57h]
0x1800159d8  sub     rsp, 0F0h
0x1800159df  mov     rax, cs:__security_cookie
0x1800159e6  xor     rax, rsp
0x1800159e9  mov     [rbp+57h+var_8], rax
0x1800159ed  mov     rdi, rdx
0x1800159f0  mov     rbx, rcx
0x1800159f3  mov     [rbp+57h+var_30], rcx
0x1800159f7  mov     [rbp+57h+var_30], rdx
0x1800159fb  lea     rcx, [rbp+57h+var_C0]
0x1800159ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015a04  mov     rdx, rax
0x180015a07  lea     rcx, [rbp+57h+var_28]
0x180015a0b  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x180015a10  nop
0x180015a11  lea     rax, [rbp+57h+var_A0]
0x180015a15  mov     [rbp+57h+var_D0], rax
0x180015a19  xorps   xmm0, xmm0
0x180015a1c  movups  [rbp+57h+var_A0], xmm0
0x180015a20  mov     [rbp+57h+var_90], 0
0x180015a28  mov     [rbp+57h+var_88], 0
0x180015a30  xor     r8d, r8d
0x180015a33  lea     rdx, S2
0x180015a3a  lea     rcx, [rbp+57h+var_A0]
0x180015a3e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015a43  nop
0x180015a44  lea     rax, [rbp+57h+var_C0]
0x180015a48  mov     [rbp+57h+var_80], rax
0x180015a4c  xorps   xmm0, xmm0
0x180015a4f  movups  [rbp+57h+var_C0], xmm0
0x180015a53  mov     [rbp+57h+var_B0], 0
0x180015a5b  mov     [rbp+57h+var_A8], 0
0x180015a63  mov     r8d, 2Ah ; '*'
0x180015a69  lea     rdx, a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x180015a70  lea     rcx, [rbp+57h+var_C0]
0x180015a74  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015a79  nop
0x180015a7a  lea     rdx, [rbp+57h+var_28]
0x180015a7e  lea     rcx, [rbp+57h+var_70]
0x180015a82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015a87  nop
0x180015a88  lea     r9, [rbp+57h+var_A0]
0x180015a8c  lea     r8, [rbp+57h+var_C0]
0x180015a90  mov     rdx, rax
0x180015a93  lea     rcx, [rbp+57h+var_50]
0x180015a97  call    ?GetSwdStringProperty@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@00@Z; WindowsMidiServicesInternal::GetSwdStringProperty(std::wstring,std::wstring,std::wstring)
0x180015a9c  mov     rdx, rax
0x180015a9f  mov     rcx, rbx
0x180015aa2  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x180015aa7  nop
0x180015aa8  lea     rcx, [rbp+57h+var_28]
0x180015aac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015ab1  nop
0x180015ab2  mov     rcx, rdi
0x180015ab5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015aba  mov     rax, rbx
0x180015abd  mov     rcx, [rbp+57h+var_8]
0x180015ac1  xor     rcx, rsp; StackCookie
0x180015ac4  call    __security_check_cookie
0x180015ac9  lea     r11, [rsp+0F0h+var_s0]
0x180015ad1  mov     rbx, [r11+20h]
0x180015ad5  mov     rdi, [r11+28h]
0x180015ad9  mov     rsp, r11
0x180015adc  pop     rbp
0x180015add  retn
```
