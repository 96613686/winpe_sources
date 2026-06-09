# Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(void)

- ea: `0x18001ecc8`
- end: `0x18001ed48`
- name: `?CleanupLocalMutex@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019484`
- `0x18001f2c8`

## callees

- `0x18000d280`
- `0x18000e300`
- `0x180010400`
- `0x180013b00`
- `0x18001ecc8`
- `0x18002031c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ed0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ed0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001ecfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001ecfa`

## pseudocode

```c
void __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(
        Windows::Security::Authentication::Web::CWebAuthOperation *this)
{
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > *p_m_MutexHandle; // rdi
  void *m_ptr; // rcx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v5; // eax
  const char *v6; // r8
  void *retaddr; // [rsp+28h] [rbp+0h]

  p_m_MutexHandle = &this->m_MutexHandle;
  m_ptr = this->m_MutexHandle.m_ptr;
  if ( m_ptr )
  {
    wil::details::ReleaseMutex(m_ptr);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      p_m_MutexHandle,
      0);
  }
  if ( !WindowsIsStringEmpty(this->m_MutexRegValue._hstring) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(this->m_MutexRegValue._hstring, 0);
    v5 = _DeleteInternetMutexFromRegistry(StringRawBuffer);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, 0x25Fu, v6, v5);
    Windows::Internal::String::Release(&this->m_MutexRegValue);
  }
}

```

## disassembly

```asm
0x18001ecc8  mov     [rsp+arg_0], rbx
0x18001eccd  push    rdi
0x18001ecce  sub     rsp, 20h
0x18001ecd2  lea     rdi, [this+108h]
0x18001ecd9  mov     rbx, this
0x18001ecdc  mov     this, [rdi]; mutex
0x18001ecdf  test    this, this
0x18001ece2  jz      short loc_18001ECF3
0x18001ece4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001ece9  xor     edx, edx; ptr
0x18001eceb  mov     this, rdi; this
0x18001ecee  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ecf3  mov     this, [rbx+110h]; string
0x18001ecfa  call    cs:__imp_WindowsIsStringEmpty
0x18001ed00  test    eax, eax
0x18001ed02  jnz     short loc_18001ED3D
0x18001ed04  mov     this, [rbx+110h]; string
0x18001ed0b  xor     edx, edx; length
0x18001ed0d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ed13  mov     this, rax; regValue
0x18001ed16  call    ?_DeleteInternetMutexFromRegistry@@YAJPEBG@Z; _DeleteInternetMutexFromRegistry(ushort const *)
0x18001ed1b  test    eax, eax
0x18001ed1d  jns     short loc_18001ED31
0x18001ed1f  mov     this, [rsp+28h]; callerReturnAddress
0x18001ed24  mov     r9d, eax; callerReturnAddress
0x18001ed27  mov     edx, 25Fh; lineNumber
0x18001ed2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ed31  lea     this, [rbx+110h]; this
0x18001ed38  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x18001ed3d  mov     rbx, [rsp+28h+arg_0]
0x18001ed42  add     rsp, 20h
0x18001ed46  pop     rdi
0x18001ed47  retn
```
