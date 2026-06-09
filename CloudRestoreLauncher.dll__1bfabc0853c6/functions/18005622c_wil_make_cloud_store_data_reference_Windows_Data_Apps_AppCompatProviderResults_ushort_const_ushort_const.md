# wil::make_cloud_store_data_reference<Windows::Data::Apps::AppCompatProviderResults>(ushort const *,ushort const *)

- ea: `0x18005622c`
- end: `0x1800562ff`
- name: `??$make_cloud_store_data_reference@UAppCompatProviderResults@Apps@Data@Windows@@@wil@@YA?AU?$ItemReference@UAppCompatProviderResults@Apps@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180060990`
- `0x180064870`

## callees

- `0x18000c6e0`
- `0x1800156b0`
- `0x18001d5fc`
- `0x180031774`
- `0x18005622c`

## import_xrefs

- `OLE32!StringFromGUID2` at `0x1800562a4`
- `OLE32!StringFromGUID2` at `0x1800562a4`
- `OLE32!CoCreateGuid` at `0x18005628e`
- `OLE32!CoCreateGuid` at `0x18005628e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::make_cloud_store_data_reference<Windows::Data::Apps::AppCompatProviderResults>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  OLECHAR *v8; // rdx
  __int64 v9; // rax
  GUID pguid; // [rsp+40h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-78h] BYREF

  std::wstring::wstring(a1);
  std::wstring::wstring(v5 + 32);
  if ( v6 )
  {
    v7 = std::_WChar_traits<unsigned short>::length(v6);
  }
  else
  {
    pguid = 0;
    CoCreateGuid(&pguid);
    StringFromGUID2(&pguid, sz, 40);
    v7 = std::_WChar_traits<unsigned short>::length(sz);
    v8 = sz;
  }
  std::wstring::_Assign<unsigned short>(a1, v8, v7);
  if ( a3 )
  {
    v9 = std::_WChar_traits<unsigned short>::length(a3);
    std::wstring::_Assign<unsigned short>(a1 + 32, a3, v9);
  }
  return a1;
}

```

## disassembly

```asm
0x18005622c  push    rbx
0x18005622e  push    rsi
0x18005622f  push    rdi
0x180056230  sub     rsp, 0B0h
0x180056237  mov     rax, cs:__security_cookie
0x18005623e  xor     rax, rsp
0x180056241  mov     [rsp+0C8h+var_28], rax
0x180056249  mov     rdi, r8
0x18005624c  mov     rbx, rcx
0x18005624f  mov     [rsp+0C8h+var_98], rcx
0x180056254  mov     [rsp+0C8h+var_A8], 0
0x18005625c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056261  add     rcx, 20h ; ' '
0x180056265  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005626a  mov     [rsp+0C8h+var_A8], 1
0x180056272  test    rdx, rdx
0x180056275  jz      short loc_180056281
0x180056277  mov     rcx, rdx
0x18005627a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005627f  jmp     short loc_1800562B9
0x180056281  xorps   xmm0, xmm0
0x180056284  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x180056289  lea     rcx, [rsp+0C8h+pguid]; pguid
0x18005628e  call    cs:__imp_CoCreateGuid
0x180056294  mov     r8d, 28h ; '('; cchMax
0x18005629a  lea     rdx, [rsp+0C8h+sz]; lpsz
0x18005629f  lea     rcx, [rsp+0C8h+pguid]; rguid
0x1800562a4  call    cs:__imp_StringFromGUID2
0x1800562aa  lea     rcx, [rsp+0C8h+sz]
0x1800562af  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800562b4  lea     rdx, [rsp+0C8h+sz]
0x1800562b9  mov     r8, rax
0x1800562bc  mov     rcx, rbx
0x1800562bf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800562c4  test    rdi, rdi
0x1800562c7  jz      short loc_1800562E0
0x1800562c9  mov     rcx, rdi
0x1800562cc  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800562d1  mov     r8, rax
0x1800562d4  mov     rdx, rdi
0x1800562d7  lea     rcx, [rbx+20h]
0x1800562db  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800562e0  mov     rax, rbx
0x1800562e3  mov     rcx, [rsp+0C8h+var_28]
0x1800562eb  xor     rcx, rsp; StackCookie
0x1800562ee  call    __security_check_cookie
0x1800562f3  add     rsp, 0B0h
0x1800562fa  pop     rdi
0x1800562fb  pop     rsi
0x1800562fc  pop     rbx
0x1800562fd  retn
```
