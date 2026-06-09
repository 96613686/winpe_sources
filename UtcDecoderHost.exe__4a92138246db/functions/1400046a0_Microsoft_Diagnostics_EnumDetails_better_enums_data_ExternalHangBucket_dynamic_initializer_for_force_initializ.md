# Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_dynamic_initializer_for___force_initialization__

- ea: `0x1400046a0`
- end: `0x140004733`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400046a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400046e5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400046e5`

## string_xrefs

- `0x1400046cc`: `None,Syscall,Usermgrcli_UMgrQueryUserToken,Netprofm_GetInterfaceHasInternetConnectionProfile,Nsi_NsiRpcRegisterChangeNotificationEx,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 5; ++i )
    {
      v2 = off_140019B10[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019B10[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400046a0  mov     [rsp+arg_0], rbx
0x1400046a5  mov     [rsp+arg_8], rdi
0x1400046aa  push    r14
0x1400046ac  sub     rsp, 20h
0x1400046b0  cmp     cs:?value@?1??_initialized@_data_ExternalHangBucket@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_initialized(void)'::`2'::value
0x1400046b7  jnz     short loc_140004722
0x1400046b9  xor     edi, edi
0x1400046bb  lea     r14, cs:140000000h
0x1400046c2  xor     ebx, ebx
0x1400046c4  mov     rcx, ds:rva off_140019B10[r14+rbx*8]; Str
0x1400046cc  lea     rax, rva ?storage@?1??_name_storage@_data_ExternalHangBucket@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "None,Syscall,Usermgrcli_UMgrQueryUserTo"... ...
0x1400046d3  add     rax, rdi
0x1400046d6  lea     rdx, Control; "= \t\n"
0x1400046dd  mov     rva ?value@?1??_name_array@_data_ExternalHangBucket@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_name_array(void)'::`2'::value ...
0x1400046e5  call    cs:__imp_strcspn
0x1400046eb  mov     rcx, ds:rva off_140019B10[r14+rbx*8]; "None" ...
0x1400046f3  add     rax, rdi
0x1400046f6  mov     byte ptr [rax+r14+264D0h], 0
0x1400046ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004703  inc     rax
0x140004706  cmp     byte ptr [rcx+rax], 0
0x14000470a  jnz     short loc_140004703
0x14000470c  inc     rdi
0x14000470f  inc     rbx
0x140004712  add     rdi, rax
0x140004715  cmp     rbx, 5
0x140004719  jb      short loc_1400046C4
0x14000471b  mov     cs:?value@?1??_initialized@_data_ExternalHangBucket@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ExternalHangBucket::_initialized(void)'::`2'::value
0x140004722  mov     rbx, [rsp+28h+arg_0]
0x140004727  mov     rdi, [rsp+28h+arg_8]
0x14000472c  add     rsp, 20h
0x140004730  pop     r14
0x140004732  retn
```
