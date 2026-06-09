# wil::make_cloud_store_data_reference<Windows::Data::Shell::FocusSessionActiveTheme>(ushort const *,ushort const *)

- ea: `0x180011ce8`
- end: `0x180011d95`
- name: `??$make_cloud_store_data_reference@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@YA?AU?$ItemReference@UFocusSessionActiveTheme@Shell@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012b98`

## callees

- `0x180003980`
- `0x180007e7c`
- `0x180010a74`
- `0x180011ce8`
- `0x180012578`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180011d42`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180011d42`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011d58`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::make_cloud_store_data_reference<Windows::Data::Shell::FocusSessionActiveTheme>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r9
  __int64 v5; // rax
  OLECHAR *v6; // r9
  OLECHAR *v7; // rdx
  GUID pguid; // [rsp+40h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-68h] BYREF

  Windows::Data::Platform::ItemReference<Windows::Data::Shell::FocusSessionActiveTheme>::ItemReference<Windows::Data::Shell::FocusSessionActiveTheme>(
    a1,
    a2,
    a3,
    a2,
    0);
  if ( v4 )
  {
    v5 = std::_WChar_traits<unsigned short>::length(v4);
    v7 = v6;
  }
  else
  {
    pguid = 0;
    CoCreateGuid(&pguid);
    StringFromGUID2(&pguid, sz, 40);
    v5 = std::_WChar_traits<unsigned short>::length(sz);
    v7 = sz;
  }
  std::wstring::_Assign<unsigned short>(a1, v7, v5);
  return a1;
}

```

## disassembly

```asm
0x180011ce8  push    rbx
0x180011cea  sub     rsp, 0B0h
0x180011cf1  mov     rax, cs:__security_cookie
0x180011cf8  xor     rax, rsp
0x180011cfb  mov     [rsp+0B8h+var_18], rax
0x180011d03  mov     r9, rdx
0x180011d06  mov     rbx, rcx
0x180011d09  mov     [rsp+0B8h+var_88], rcx
0x180011d0e  mov     [rsp+0B8h+var_98], 0
0x180011d16  call    ??0?$ItemReference@UFocusSessionActiveTheme@Shell@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Shell::FocusSessionActiveTheme>::ItemReference<Windows::Data::Shell::FocusSessionActiveTheme>(void)
0x180011d1b  mov     [rsp+0B8h+var_98], 1
0x180011d23  test    r9, r9
0x180011d26  jz      short loc_180011D35
0x180011d28  mov     rcx, r9
0x180011d2b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180011d30  mov     rdx, r9
0x180011d33  jmp     short loc_180011D6D
0x180011d35  xorps   xmm0, xmm0
0x180011d38  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x180011d3d  lea     rcx, [rsp+0B8h+pguid]; pguid
0x180011d42  call    cs:__imp_CoCreateGuid
0x180011d48  mov     r8d, 28h ; '('; cchMax
0x180011d4e  lea     rdx, [rsp+0B8h+sz]; lpsz
0x180011d53  lea     rcx, [rsp+0B8h+pguid]; rguid
0x180011d58  call    cs:__imp_StringFromGUID2
0x180011d5e  lea     rcx, [rsp+0B8h+sz]
0x180011d63  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180011d68  lea     rdx, [rsp+0B8h+sz]
0x180011d6d  mov     r8, rax
0x180011d70  mov     rcx, rbx
0x180011d73  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180011d78  mov     rax, rbx
0x180011d7b  mov     rcx, [rsp+0B8h+var_18]
0x180011d83  xor     rcx, rsp; StackCookie
0x180011d86  call    __security_check_cookie
0x180011d8b  add     rsp, 0B0h
0x180011d92  pop     rbx
0x180011d93  retn
```
