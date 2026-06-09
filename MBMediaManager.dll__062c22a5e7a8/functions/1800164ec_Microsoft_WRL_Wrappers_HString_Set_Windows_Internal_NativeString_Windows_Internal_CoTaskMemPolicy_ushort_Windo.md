# Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800164ec`
- end: `0x180016552`
- name: `??$Set@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z`
- size: `102`
- prototype: `HRESULT __fastcall(HSTRING *string, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a494`
- `0x18001dc70`

## callees

- `0x180005fc0`
- `0x1800164ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001651b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001651b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(
        HSTRING *string,
        const unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdx
  unsigned __int64 v5; // r8

  v2 = *a2;
  if ( v2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    if ( v5 <= 0xFFFFFFFF )
      return Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)string, v2, v5);
    else
      return -2147024362;
  }
  else
  {
    WindowsDeleteString(*string);
    *string = 0;
    return WindowsCreateString(&sourceString, 0, string);
  }
}

```

## disassembly

```asm
0x1800164ec  mov     [rsp+arg_0], rbx
0x1800164f1  push    rdi
0x1800164f2  sub     rsp, 20h
0x1800164f6  mov     rdx, [rdx]; unsigned __int16 *
0x1800164f9  xor     edi, edi
0x1800164fb  mov     rbx, rcx
0x1800164fe  test    rdx, rdx
0x180016501  jnz     short loc_18001652C
0x180016503  mov     rcx, [rcx]; string
0x180016506  call    cs:__imp_WindowsDeleteString
0x18001650c  mov     r8, rbx; string
0x18001650f  mov     [rbx], rdi
0x180016512  xor     edx, edx; length
0x180016514  lea     rcx, sourceString; sourceString
0x18001651b  call    cs:__imp_WindowsCreateString
0x180016521  mov     rbx, [rsp+28h+arg_0]
0x180016526  add     rsp, 20h
0x18001652a  pop     rdi
0x18001652b  retn
0x18001652c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016530  inc     r8; unsigned int
0x180016533  cmp     [rdx+r8*2], di
0x180016538  jnz     short loc_180016530
0x18001653a  mov     eax, 0FFFFFFFFh
0x18001653f  cmp     r8, rax
0x180016542  jbe     short loc_18001654B
0x180016544  mov     eax, 80070216h
0x180016549  jmp     short loc_180016521
0x18001654b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180016550  jmp     short loc_180016521
```
