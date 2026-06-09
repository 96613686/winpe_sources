# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x1800234b8`
- end: `0x180023643`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `395`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180022d44`
- `0x1800231b4`
- `0x180023708`

## callees

- `0x180003560`
- `0x180009a54`
- `0x180009ad8`
- `0x180016bc8`
- `0x18001ab20`
- `0x18001ad1c`
- `0x1800232bc`
- `0x180023448`
- `0x1800234b8`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rsi
  bool v5; // zf
  __int64 v6; // rdx
  _BYTE *v7; // rcx
  __int64 result; // rax
  char v9; // [rsp+20h] [rbp-E0h] BYREF
  const char *v10; // [rsp+28h] [rbp-D8h] BYREF
  char v11; // [rsp+30h] [rbp-D0h]
  char *v12; // [rsp+38h] [rbp-C8h]
  const char *v13; // [rsp+40h] [rbp-C0h] BYREF
  char v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  const char *v16; // [rsp+58h] [rbp-A8h] BYREF
  char v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  char v22; // [rsp+B0h] [rbp-50h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_15;
  tson::read_buffer::read_buffer((tson::read_buffer *)v19, *(const char **)(a2 + 24));
  v4 = (_QWORD *)(a1 + 8);
  tson::input_archive::input_archive((tson::input_archive *)&v20, (struct tson::read_buffer *)v19, *(_BYTE *)(a1 + 33));
  if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 24) == 0;
    v10 = "name";
    v11 = 4;
    if ( v5 )
    {
      v12 = (char *)(a1 + 8);
      tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        (__int64)&v20,
        (__int64)&v10);
      if ( *v4 )
        *(_QWORD *)(a1 + 24) = *v4;
    }
    else
    {
      v9 = 0;
      v12 = &v9;
      tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>((tson::input_archive *)&v20);
    }
  }
  v11 = 5;
  v10 = "flags";
  v14 = 6;
  v12 = (char *)(a1 + 120);
  v17 = 3;
  v13 = "errors";
  v15 = a1 + 72;
  v16 = "log";
  v18 = a1 + 96;
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
    (tson *)&v20,
    (__int64)&v16,
    (__int64 *)&v13,
    (__int64 *)&v10);
  v7 = *(_BYTE **)(v20 + 8);
  if ( (unsigned __int64)v7 >= *(_QWORD *)(v20 + 16) )
    goto LABEL_10;
  LOBYTE(v6) = 8;
  if ( *v7 == 8 )
    result = tson::input_archive::consume_expected_marker(&v20, v6, 2147944029LL);
  else
LABEL_10:
    result = tip2::details::shared_data<1,0,0>::deserialize(a1, &v20);
  if ( v21 < 0 || (result = v20, *(_BYTE *)(v20 + 24)) || v22 )
  {
LABEL_15:
    *(_DWORD *)(a1 + 64) |= 0x80000u;
  }
  else
  {
    result = *(unsigned int *)(a2 + 16);
    *(_DWORD *)(a1 + 184) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800234b8  mov     [rsp-8+arg_10], rbx
0x1800234bd  push    rbp
0x1800234be  push    rsi
0x1800234bf  push    rdi
0x1800234c0  lea     rbp, [rsp-30h]
0x1800234c5  sub     rsp, 130h
0x1800234cc  mov     rax, cs:__security_cookie
0x1800234d3  xor     rax, rsp
0x1800234d6  mov     [rbp+40h+var_20], rax
0x1800234da  test    dword ptr [rdx+14h], 1000h
0x1800234e1  mov     rdi, rdx
0x1800234e4  mov     rbx, rcx
0x1800234e7  jz      loc_18002361F
0x1800234ed  mov     rdx, [rdx+18h]; char *
0x1800234f1  lea     rcx, [rsp+140h+var_D0]; this
0x1800234f6  call    ??0read_buffer@tson@@QEAA@PEBD@Z; tson::read_buffer::read_buffer(char const *)
0x1800234fb  lea     rsi, [rbx+8]
0x1800234ff  mov     r8b, [rsi+19h]; unsigned __int8
0x180023503  lea     rdx, [rsp+140h+var_D0]; struct tson::read_buffer *
0x180023508  lea     rcx, [rbp+40h+var_B0]; this
0x18002350c  call    ??0input_archive@tson@@QEAA@AEAVread_buffer@1@E@Z; tson::input_archive::input_archive(tson::read_buffer &,uchar)
0x180023511  test    dword ptr [rbx+14h], 40000h
0x180023518  jz      short loc_180023567
0x18002351a  cmp     qword ptr [rbx+18h], 0
0x18002351f  lea     rax, aName; "name"
0x180023526  mov     [rsp+140h+var_118], rax
0x18002352b  lea     rdx, [rsp+140h+var_118]
0x180023530  mov     [rsp+140h+var_110], 4
0x180023535  lea     rcx, [rbp+40h+var_B0]; this
0x180023539  jnz     short loc_180023553
0x18002353b  mov     [rsp+140h+var_108], rsi
0x180023540  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x180023545  mov     rax, [rsi]
0x180023548  test    rax, rax
0x18002354b  jz      short loc_180023567
0x18002354d  mov     [rbx+18h], rax
0x180023551  jmp     short loc_180023567
0x180023553  lea     rax, [rsp+140h+var_120]
0x180023558  mov     [rsp+140h+var_120], 0
0x18002355d  mov     [rsp+140h+var_108], rax
0x180023562  call    ??$?RV?$nvp@AEAUansistring_skip_tag@tson@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUansistring_skip_tag@tson@@@1@@Z; tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>(tson::nvp<tson::ansistring_skip_tag &> &&)
0x180023567  lea     rax, aFlags; "flags"
0x18002356e  mov     [rsp+140h+var_110], 5
0x180023573  mov     [rsp+140h+var_118], rax
0x180023578  lea     r9, [rsp+140h+var_118]
0x18002357d  lea     rax, [rbx+78h]
0x180023581  mov     [rsp+140h+var_F8], 6
0x180023586  mov     [rsp+140h+var_108], rax
0x18002358b  lea     r8, [rsp+140h+var_100]
0x180023590  lea     rax, aErrors; "errors"
0x180023597  mov     [rsp+140h+var_E0], 3
0x18002359c  mov     [rsp+140h+var_100], rax
0x1800235a1  lea     rdx, [rsp+140h+var_E8]
0x1800235a6  lea     rax, [rbx+48h]
0x1800235aa  mov     [rsp+140h+var_F0], rax
0x1800235af  lea     rcx, [rbp+40h+var_B0]; this
0x1800235b3  lea     rax, aLog; "log"
0x1800235ba  mov     [rsp+140h+var_E8], rax
0x1800235bf  lea     rax, [rbx+60h]
0x1800235c3  mov     [rsp+140h+var_D8], rax
0x1800235c8  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x1800235cd  mov     rax, [rbp+40h+var_B0]
0x1800235d1  mov     rcx, [rax+8]
0x1800235d5  cmp     rcx, [rax+10h]
0x1800235d9  jnb     short loc_1800235F2
0x1800235db  mov     dl, 8
0x1800235dd  cmp     [rcx], dl
0x1800235df  jnz     short loc_1800235F2
0x1800235e1  mov     r8d, 8007065Dh
0x1800235e7  lea     rcx, [rbp+40h+var_B0]
0x1800235eb  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x1800235f0  jmp     short loc_1800235FE
0x1800235f2  lea     rdx, [rbp+40h+var_B0]
0x1800235f6  mov     rcx, rbx
0x1800235f9  call    ?deserialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVinput_archive@tson@@@Z; tip2::details::shared_data<1,0,0>::deserialize(tson::input_archive &)
0x1800235fe  cmp     [rbp+40h+var_A8], 0
0x180023602  jl      short loc_18002361F
0x180023604  mov     rax, [rbp+40h+var_B0]
0x180023608  cmp     byte ptr [rax+18h], 0
0x18002360c  jnz     short loc_18002361F
0x18002360e  cmp     [rbp+40h+var_90], 0
0x180023612  jnz     short loc_18002361F
0x180023614  mov     eax, [rdi+10h]
0x180023617  mov     [rbx+0B8h], eax
0x18002361d  jmp     short loc_180023624
0x18002361f  bts     dword ptr [rbx+40h], 13h
0x180023624  mov     rcx, [rbp+40h+var_20]
0x180023628  xor     rcx, rsp; StackCookie
0x18002362b  call    __security_check_cookie
0x180023630  mov     rbx, [rsp+140h+arg_10]
0x180023638  add     rsp, 130h
0x18002363f  pop     rdi
0x180023640  pop     rsi
0x180023641  pop     rbp
0x180023642  retn
```
