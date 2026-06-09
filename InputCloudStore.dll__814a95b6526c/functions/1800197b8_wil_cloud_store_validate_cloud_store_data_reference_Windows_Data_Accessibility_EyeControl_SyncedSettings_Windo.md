# wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Accessibility::EyeControl::SyncedSettings>(Windows::Data::Platform::ItemReference<Windows::Data::Accessibility::EyeControl::SyncedSettings> const *)

- ea: `0x1800197b8`
- end: `0x180019854`
- name: `??$validate_cloud_store_data_reference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@Platform@Data@Windows@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001cd78`
- `0x180021c50`

## callees

- `0x180005478`
- `0x1800151f0`
- `0x1800197b8`
- `0x180019c38`
- `0x180019c80`
- `0x180022b44`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        __int64 a2)
{
  _WORD *v4; // rax
  const char *v5; // r9
  __int16 v6; // dx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 )
  {
    v4 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    if ( *v4 == v6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6E7,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
        v5);
    std::wstring::wstring(a1, a2 + 32);
    std::wstring::wstring(a1 + 32, a2);
    wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(a1 + 64);
  }
  else
  {
    std::wstring::wstring(a1, &qword_180033FA8);
    std::wstring::wstring(a1 + 32, &qword_180033FA8);
    wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(a1 + 64);
  }
  return a1;
}

```

## disassembly

```asm
0x1800197b8  mov     [rsp+arg_8], rbx
0x1800197bd  mov     [rsp+arg_0], rcx
0x1800197c2  push    rdi
0x1800197c3  sub     rsp, 30h
0x1800197c7  mov     rdi, rdx
0x1800197ca  mov     rbx, rcx
0x1800197cd  xor     edx, edx
0x1800197cf  test    rdi, rdi
0x1800197d2  jz      short loc_18001980C
0x1800197d4  mov     rcx, rdi
0x1800197d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800197dc  mov     rcx, [rsp+38h]; this
0x1800197e1  cmp     [rax], dx
0x1800197e4  jz      short loc_180019842
0x1800197e6  lea     rdx, [rdi+20h]
0x1800197ea  mov     rcx, rbx
0x1800197ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800197f2  nop
0x1800197f3  lea     rcx, [rbx+20h]
0x1800197f7  mov     rdx, rdi
0x1800197fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800197ff  nop
0x180019800  lea     rcx, [rbx+40h]
0x180019804  call    ??$get_type_name_wide_string@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(void)
0x180019809  nop
0x18001980a  jmp     short loc_180019834
0x18001980c  lea     rdx, qword_180033FA8
0x180019813  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180019818  nop
0x180019819  lea     rcx, [rbx+20h]
0x18001981d  lea     rdx, qword_180033FA8
0x180019824  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180019829  nop
0x18001982a  lea     rcx, [rbx+40h]
0x18001982e  call    ??$get_type_name_wide_string@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(void)
0x180019833  nop
0x180019834  mov     rax, rbx
0x180019837  mov     rbx, [rsp+38h+arg_8]
0x18001983c  add     rsp, 30h
0x180019840  pop     rdi
0x180019841  retn
0x180019842  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180019849  mov     edx, 6E7h; void *
0x18001984e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
