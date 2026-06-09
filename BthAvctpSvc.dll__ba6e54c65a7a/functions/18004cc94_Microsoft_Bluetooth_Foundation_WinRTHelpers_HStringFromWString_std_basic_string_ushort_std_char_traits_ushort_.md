# Microsoft::Bluetooth::Foundation::WinRTHelpers::HStringFromWString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004cc94`
- end: `0x18004cd2d`
- name: `?HStringFromWString@WinRTHelpers@Foundation@Bluetooth@Microsoft@@SAPEAUHSTRING__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004e244`

## callees

- `0x18000e0c0`
- `0x180019c68`
- `0x18001f11c`
- `0x18004cc94`
- `0x18004dd68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cd19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cd19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING __fastcall Microsoft::Bluetooth::Foundation::WinRTHelpers::HStringFromWString(__int64 a1)
{
  __int64 v1; // rax
  const unsigned __int16 *v2; // rbx
  unsigned __int64 v3; // rcx
  HRESULT v4; // eax
  UINT32 v5; // r8d
  const unsigned __int16 *v6; // rdx
  HSTRING v7; // rbx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  HSTRING v12; // [rsp+38h] [rbp+10h] BYREF

  v12 = 0;
  v1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v2 = (const unsigned __int16 *)v1;
  if ( !v1 )
  {
    v5 = 0;
    v6 = &String1;
    goto LABEL_7;
  }
  v11 = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(v1 + 2 * v3) );
  v4 = ULongLongToUInt(v3, &v11);
  if ( v4 >= 0 )
  {
    v5 = v11;
    v6 = v2;
LABEL_7:
    v4 = Microsoft::WRL::Wrappers::HString::Set(&v12, v6, v5);
  }
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\winrthelpers.h",
      (const char *)(unsigned int)v4,
      v9);
  v7 = v12;
  v12 = 0;
  WindowsDeleteString(0);
  return v7;
}

```

## disassembly

```asm
0x18004cc94  mov     [rsp+arg_10], rbx
0x18004cc99  push    rdi; int
0x18004cc9a  sub     rsp, 20h
0x18004cc9e  xor     edi, edi
0x18004cca0  mov     [rsp+28h+arg_8], rdi
0x18004cca5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ccaa  mov     rbx, rax
0x18004ccad  test    rax, rax
0x18004ccb0  jz      short loc_18004CCDB
0x18004ccb2  mov     [rsp+28h+arg_0], edi
0x18004ccb6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ccba  inc     rcx; unsigned __int64
0x18004ccbd  cmp     [rax+rcx*2], di
0x18004ccc1  jnz     short loc_18004CCBA
0x18004ccc3  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x18004ccc8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004cccd  test    eax, eax
0x18004cccf  js      short loc_18004CCEF
0x18004ccd1  mov     r8d, [rsp+28h+arg_0]
0x18004ccd6  mov     rdx, rbx
0x18004ccd9  jmp     short loc_18004CCE5
0x18004ccdb  xor     r8d, r8d; unsigned int
0x18004ccde  lea     rdx, String1; unsigned __int16 *
0x18004cce5  lea     rcx, [rsp+28h+arg_8]; this
0x18004ccea  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18004ccef  mov     rcx, [rsp+28h]; this
0x18004ccf4  test    eax, eax
0x18004ccf6  jns     short loc_18004CD0D
0x18004ccf8  mov     r9d, eax; char *
0x18004ccfb  lea     r8, aOnecorePrivate_2; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18004cd02  mov     edx, 166h; void *
0x18004cd07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cd0d  mov     rbx, [rsp+28h+arg_8]
0x18004cd12  mov     [rsp+28h+arg_8], rdi
0x18004cd17  xor     ecx, ecx; string
0x18004cd19  call    cs:__imp_WindowsDeleteString
0x18004cd1f  mov     rax, rbx
0x18004cd22  mov     rbx, [rsp+28h+arg_10]
0x18004cd27  add     rsp, 20h
0x18004cd2b  pop     rdi
0x18004cd2c  retn
```
