# winrt::Windows::Data::Json::JsonObject::JsonObject(void)

- ea: `0x18002b250`
- end: `0x18002b2c6`
- name: `??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ`
- size: `118`
- prototype: `winrt::Windows::Data::Json::JsonObject *__fastcall(winrt::Windows::Data::Json::JsonObject *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x18002b010`
- `0x18002b170`
- `0x18002b250`

## pseudocode

```c
winrt::Windows::Data::Json::JsonObject *__fastcall winrt::Windows::Data::Json::JsonObject::JsonObject(
        winrt::Windows::Data::Json::JsonObject *this)
{
  void (__fastcall *v3)(__int64, __int64 *); // [rsp+30h] [rbp+8h] BYREF

  v3 = (void (__fastcall *)(__int64, __int64 *))&qword_180059FB8;
  _InterlockedIncrement64(&qword_180059FB8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_63b666b759e740627ed77e2c1fafff5a_::operator()(
      this,
      this,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059FB8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059FB8);
    v3 = (void (__fastcall *)(__int64, __int64 *))_lambda_63b666b759e740627ed77e2c1fafff5a_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      (__int64)this,
      (__int64)this,
      &v3);
  }
  return this;
}

```

## disassembly

```asm
0x18002b250  mov     [rsp+arg_0], rcx
0x18002b255  push    rbx
0x18002b256  sub     rsp, 20h
0x18002b25a  mov     rbx, rcx
0x18002b25d  lea     rax, qword_180059FB8
0x18002b264  mov     [rsp+28h+arg_0], rax
0x18002b269  lock inc cs:qword_180059FB8
0x18002b271  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002b279  jz      short loc_18002B29C
0x18002b27b  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002b282  mov     rdx, rcx
0x18002b285  call    ??R_lambda_63b666b759e740627ed77e2c1fafff5a_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_63b666b759e740627ed77e2c1fafff5a_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18002b28a  nop
0x18002b28b  lock dec cs:qword_180059FB8
0x18002b293  mov     rax, rbx
0x18002b296  add     rsp, 20h
0x18002b29a  pop     rbx
0x18002b29b  retn
0x18002b29c  lock dec cs:qword_180059FB8
0x18002b2a4  lea     rax, ?_lambda_invoker_cdecl_@_lambda_63b666b759e740627ed77e2c1fafff5a_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_63b666b759e740627ed77e2c1fafff5a_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18002b2ab  mov     [rsp+28h+arg_0], rax
0x18002b2b0  lea     r8, [rsp+28h+arg_0]
0x18002b2b5  mov     rdx, rbx
0x18002b2b8  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18002b2bd  mov     rax, rbx
0x18002b2c0  add     rsp, 20h
0x18002b2c4  pop     rbx
0x18002b2c5  retn
```
