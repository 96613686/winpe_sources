# ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>>::`vector deleting destructor'(uint)

- ea: `0x140008fb0`
- end: `0x140008fe0`
- name: `??_E?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140008564`
- `0x140008fb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008fcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008fcc`

## pseudocode

```c
void *__fastcall ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::~CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140008fb0  mov     [rsp+arg_0], rbx
0x140008fb5  push    rdi
0x140008fb6  sub     rsp, 20h
0x140008fba  mov     ebx, edx
0x140008fbc  mov     rdi, rcx
0x140008fbf  call    ??1?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@UEAA@XZ; ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::~CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>(void)
0x140008fc4  test    bl, 1
0x140008fc7  jz      short loc_140008FD2
0x140008fc9  mov     rcx, rdi
0x140008fcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008fd2  mov     rbx, [rsp+28h+arg_0]
0x140008fd7  mov     rax, rdi
0x140008fda  add     rsp, 20h
0x140008fde  pop     rdi
0x140008fdf  retn
```
