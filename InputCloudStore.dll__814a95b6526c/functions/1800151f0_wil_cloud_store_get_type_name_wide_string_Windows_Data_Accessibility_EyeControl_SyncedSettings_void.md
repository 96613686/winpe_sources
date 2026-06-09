# wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(void)

- ea: `0x1800151f0`
- end: `0x180015263`
- name: `??$get_type_name_wide_string@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800197b8`

## callees

- `0x180003560`
- `0x18001213c`
- `0x1800151f0`
- `0x180019bd8`
- `0x180022b24`
- `0x180026170`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::get_type_name_wide_string<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1)
{
  __int64 v2; // rax
  _QWORD *v4[3]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v5; // [rsp+58h] [rbp-20h]

  v2 = std::_String_val<std::_Simple_types<char>>::_Myptr(qword_180046260);
  std::string::string(v4, v2);
  wil::cloud_store::widen_string(a1, v4);
  if ( v5 > 0xF )
    std::_Deallocate<16>(v4[0], v5 + 1);
  return a1;
}

```

## disassembly

```asm
0x1800151f0  push    rbx
0x1800151f2  sub     rsp, 70h
0x1800151f6  mov     rax, cs:__security_cookie
0x1800151fd  xor     rax, rsp
0x180015200  mov     [rsp+78h+var_18], rax
0x180015205  mov     rbx, rcx
0x180015208  mov     [rsp+78h+var_48], rcx
0x18001520d  lea     rcx, qword_180046260
0x180015214  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180015219  mov     rdx, rax
0x18001521c  lea     rcx, [rsp+78h+var_38]
0x180015221  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015226  nop
0x180015227  lea     rdx, [rsp+78h+var_38]
0x18001522c  mov     rcx, rbx
0x18001522f  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180015234  nop
0x180015235  mov     rdx, [rsp+78h+var_20]
0x18001523a  cmp     rdx, 0Fh
0x18001523e  jbe     short loc_18001524D
0x180015240  inc     rdx
0x180015243  mov     rcx, [rsp+78h+var_38]
0x180015248  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001524d  mov     rax, rbx
0x180015250  mov     rcx, [rsp+78h+var_18]
0x180015255  xor     rcx, rsp; StackCookie
0x180015258  call    __security_check_cookie
0x18001525d  add     rsp, 70h
0x180015261  pop     rbx
0x180015262  retn
```
