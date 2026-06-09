# wil::cloud_store::load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store_load_options,char const *)

- ea: `0x180015598`
- end: `0x18001561a`
- name: `??$load@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z`
- size: `130`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001d208`
- `0x180026db4`

## callees

- `0x180003560`
- `0x18001213c`
- `0x180015598`
- `0x180015a74`
- `0x180019bd8`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(int a1, __int64 a2)
{
  int v4; // r8d
  int v5; // r9d
  _QWORD *v7[3]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v8; // [rsp+58h] [rbp-20h]

  std::string::string(v7, &qword_180033B90);
  wil::cloud_store::load_internal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(a1, a2, v4, v5, (__int64)v7);
  if ( v8 > 0xF )
    std::_Deallocate<16>(v7[0], v8 + 1);
  return a2;
}

```

## disassembly

```asm
0x180015598  mov     [rsp+arg_10], rbx
0x18001559d  push    rdi
0x18001559e  sub     rsp, 70h
0x1800155a2  mov     rax, cs:__security_cookie
0x1800155a9  xor     rax, rsp
0x1800155ac  mov     [rsp+78h+var_18], rax
0x1800155b1  mov     rdi, rdx
0x1800155b4  mov     rbx, rcx
0x1800155b7  mov     [rsp+78h+var_40], rdx
0x1800155bc  lea     rdx, qword_180033B90
0x1800155c3  lea     rcx, [rsp+78h+var_38]
0x1800155c8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800155cd  nop
0x1800155ce  lea     rax, [rsp+78h+var_38]
0x1800155d3  mov     [rsp+78h+var_58], rax
0x1800155d8  mov     rdx, rdi
0x1800155db  mov     rcx, rbx
0x1800155de  call    ??$load_internal@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@W4cloud_store_load_options@1@PEBU?$ItemReference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@Platform@Data@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::load_internal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store_load_options,Windows::Data::Platform::ItemReference<Windows::Data::Accessibility::EyeControl::SyncedSettings> const *,std::string const &)
0x1800155e3  nop
0x1800155e4  mov     rdx, [rsp+78h+var_20]
0x1800155e9  cmp     rdx, 0Fh
0x1800155ed  jbe     short loc_1800155FC
0x1800155ef  inc     rdx
0x1800155f2  mov     rcx, [rsp+78h+var_38]
0x1800155f7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800155fc  mov     rax, rdi
0x1800155ff  mov     rcx, [rsp+78h+var_18]
0x180015604  xor     rcx, rsp; StackCookie
0x180015607  call    __security_check_cookie
0x18001560c  mov     rbx, [rsp+78h+arg_10]
0x180015614  add     rsp, 70h
0x180015618  pop     rdi
0x180015619  retn
```
