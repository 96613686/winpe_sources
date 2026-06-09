# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::Next(ulong,ushort * *,ulong *)

- ea: `0x180089e00`
- end: `0x180089ec0`
- name: `?Next@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@UEAAJKPEAPEAGPEAK@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180022e88`
- `0x18004b2dc`
- `0x180089e00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e7f`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Next(
        __int64 a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4)
{
  void **v5; // rdi
  unsigned int v8; // r15d
  void **v9; // rsi
  int v10; // ebp
  __int64 v11; // rbx
  void *v12; // rcx
  __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  if ( a4 )
    *a4 = 0;
  v8 = 0;
  v9 = a3;
  v10 = 0;
  v11 = *(_QWORD *)(a1 + 24);
  v14 = v11;
  while ( v11 != *(_QWORD *)(a1 + 8) && v8 < a2 )
  {
    v10 = Windows::CopyFromPairWstringToLpolestr::copy(v9, v11 + 32);
    if ( v10 < 0 )
    {
      while ( v5 < v9 )
      {
        v12 = *v5++;
        CoTaskMemFree(v12);
      }
      goto LABEL_15;
    }
    ++v9;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(&v14);
    v11 = v14;
    ++v8;
  }
  if ( a4 )
    *a4 = v8;
  if ( v8 < a2 )
  {
    *v9 = 0;
    v10 = 1;
  }
LABEL_15:
  *(_QWORD *)(a1 + 24) = v11;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180089e00  push    rbx
0x180089e02  push    rbp
0x180089e03  push    rsi
0x180089e04  push    rdi
0x180089e05  push    r12
0x180089e07  push    r13
0x180089e09  push    r14
0x180089e0b  push    r15
0x180089e0d  sub     rsp, 28h
0x180089e11  mov     r14, r9
0x180089e14  mov     rdi, r8
0x180089e17  mov     r12d, edx
0x180089e1a  mov     r13, rcx
0x180089e1d  test    r9, r9
0x180089e20  jz      short loc_180089E29
0x180089e22  mov     dword ptr [r9], 0
0x180089e29  xor     r15d, r15d
0x180089e2c  mov     rsi, rdi
0x180089e2f  xor     ebp, ebp
0x180089e31  mov     rbx, [rcx+18h]
0x180089e35  mov     [rsp+68h+arg_10], rbx
0x180089e3d  cmp     rbx, [r13+8]
0x180089e41  jz      short loc_180089E90
0x180089e43  cmp     r15d, r12d
0x180089e46  jnb     short loc_180089E8C
0x180089e48  lea     rdx, [rbx+20h]
0x180089e4c  mov     rcx, rsi
0x180089e4f  call    ?copy@CopyFromPairWstringToLpolestr@Windows@@SAJPEAPEAGPEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@Z; Windows::CopyFromPairWstringToLpolestr::copy(ushort * *,std::pair<std::wstring const,std::wstring> const *)
0x180089e54  mov     ebp, eax
0x180089e56  test    eax, eax
0x180089e58  js      short loc_180089E85
0x180089e5a  lea     rcx, [rsp+68h+arg_10]
0x180089e62  add     rsi, 8
0x180089e66  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUEventRegistrationToken@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(void)
0x180089e6b  mov     rbx, [rsp+68h+arg_10]
0x180089e73  inc     r15d
0x180089e76  jmp     short loc_180089E3D
0x180089e78  mov     rcx, [rdi]; pv
0x180089e7b  add     rdi, 8
0x180089e7f  call    cs:__imp_CoTaskMemFree
0x180089e85  cmp     rdi, rsi
0x180089e88  jb      short loc_180089E78
0x180089e8a  jmp     short loc_180089EA9
0x180089e8c  test    ebp, ebp
0x180089e8e  js      short loc_180089EA9
0x180089e90  test    r14, r14
0x180089e93  jz      short loc_180089E98
0x180089e95  mov     [r14], r15d
0x180089e98  cmp     r15d, r12d
0x180089e9b  jnb     short loc_180089EA9
0x180089e9d  mov     qword ptr [rsi], 0
0x180089ea4  mov     ebp, 1
0x180089ea9  mov     [r13+18h], rbx
0x180089ead  mov     eax, ebp
0x180089eaf  add     rsp, 28h
0x180089eb3  pop     r15
0x180089eb5  pop     r14
0x180089eb7  pop     r13
0x180089eb9  pop     r12
0x180089ebb  pop     rdi
0x180089ebc  pop     rsi
0x180089ebd  pop     rbp
0x180089ebe  pop     rbx
0x180089ebf  retn
```
