# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180020ad4`
- end: `0x180020c4e`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `378`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001de88`
- `0x18001e4bc`
- `0x180020e54`

## callees

- `0x1800021d0`
- `0x18000c6c0`
- `0x18000c970`
- `0x18000caa0`
- `0x180012218`
- `0x18001eac4`
- `0x18001f600`
- `0x180020a70`
- `0x180020ad4`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
        __int64 a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // xmm1_8
  const char *v11; // [rsp+20h] [rbp-E0h] BYREF
  char v12; // [rsp+28h] [rbp-D8h]
  _BYTE *v13; // [rsp+30h] [rbp-D0h]
  const char *v14; // [rsp+38h] [rbp-C8h] BYREF
  char v15; // [rsp+40h] [rbp-C0h]
  __int128 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  _BYTE v21[160]; // [rsp+80h] [rbp-80h] BYREF

  if ( a3 )
  {
    v6 = (_BYTE *)(a1 + 33);
    tson::output_archive::output_archive((tson::output_archive *)v21, a2, *(_BYTE *)(a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v12 = 7;
      v11 = "version";
      v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(v21, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( !v7 )
          v7 = *(_QWORD *)(a1 + 24);
        string_tag = tson::make_string_tag(&v18, v7);
        v15 = 4;
        v14 = "name";
        v9 = *(_QWORD *)(string_tag + 16);
        v16 = *(_OWORD *)string_tag;
        v17 = v9;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(v21, &v14);
      }
      v12 = 5;
      v11 = "flags";
      v15 = 6;
      v13 = (_BYTE *)(a1 + 120);
      v19 = 3;
      v14 = "errors";
      *(_QWORD *)&v16 = a1 + 72;
      v18 = "log";
      v20 = a1 + 96;
      tson::output_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson::output_archive *)v21);
    }
    tip2::details::shared_data<1,0,0>::serialize(a1, v21, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)v21) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x180020ad4  push    rbp
0x180020ad6  push    rbx
0x180020ad7  push    rsi
0x180020ad8  push    rdi
0x180020ad9  push    r14
0x180020adb  lea     rbp, [rsp-30h]
0x180020ae0  sub     rsp, 130h
0x180020ae7  mov     rax, cs:__security_cookie
0x180020aee  xor     rax, rsp
0x180020af1  mov     [rbp+50h+var_30], rax
0x180020af5  mov     edi, r8d
0x180020af8  mov     r14, rdx
0x180020afb  mov     rbx, rcx
0x180020afe  test    r8d, r8d
0x180020b01  jz      loc_180020C32
0x180020b07  lea     rsi, [rcx+21h]
0x180020b0b  mov     r8b, [rsi]; unsigned __int8
0x180020b0e  lea     rcx, [rbp+50h+var_D0]; this
0x180020b12  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180020b17  test    dil, 4
0x180020b1b  jz      short loc_180020B46
0x180020b1d  cmp     byte ptr [rsi], 0
0x180020b20  jbe     short loc_180020B46
0x180020b22  lea     rax, aVersion; "version"
0x180020b29  mov     [rsp+150h+var_128], 7
0x180020b2e  lea     rdx, [rsp+150h+var_130]
0x180020b33  mov     [rsp+150h+var_130], rax
0x180020b38  lea     rcx, [rbp+50h+var_D0]
0x180020b3c  mov     [rsp+150h+var_120], rsi
0x180020b41  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180020b46  test    dil, 1
0x180020b4a  jz      loc_180020C08
0x180020b50  test    dword ptr [rbx+14h], 40000h
0x180020b57  jz      short loc_180020BA2
0x180020b59  mov     rdx, [rbx+8]
0x180020b5d  test    rdx, rdx
0x180020b60  jnz     short loc_180020B66
0x180020b62  mov     rdx, [rbx+18h]
0x180020b66  lea     rcx, [rsp+150h+var_F0]
0x180020b6b  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x180020b70  lea     rcx, aName; "name"
0x180020b77  mov     [rsp+150h+var_110], 4
0x180020b7c  mov     [rsp+150h+var_118], rcx
0x180020b81  lea     rdx, [rsp+150h+var_118]
0x180020b86  lea     rcx, [rbp+50h+var_D0]
0x180020b8a  movups  xmm0, xmmword ptr [rax]
0x180020b8d  movsd   xmm1, qword ptr [rax+10h]
0x180020b92  movups  [rsp+150h+var_108], xmm0
0x180020b97  movsd   [rsp+150h+var_F8], xmm1
0x180020b9d  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x180020ba2  lea     rax, aFlags; "flags"
0x180020ba9  mov     [rsp+150h+var_128], 5
0x180020bae  mov     [rsp+150h+var_130], rax
0x180020bb3  lea     r9, [rsp+150h+var_130]
0x180020bb8  lea     rax, [rbx+78h]
0x180020bbc  mov     [rsp+150h+var_110], 6
0x180020bc1  mov     [rsp+150h+var_120], rax
0x180020bc6  lea     r8, [rsp+150h+var_118]
0x180020bcb  lea     rax, aErrors; "errors"
0x180020bd2  mov     [rsp+150h+var_E8], 3
0x180020bd7  mov     [rsp+150h+var_118], rax
0x180020bdc  lea     rdx, [rsp+150h+var_F0]
0x180020be1  lea     rax, [rbx+48h]
0x180020be5  mov     qword ptr [rsp+150h+var_108], rax
0x180020bea  lea     rcx, [rbp+50h+var_D0]; this
0x180020bee  lea     rax, aLog; "log"
0x180020bf5  mov     [rsp+150h+var_F0], rax
0x180020bfa  lea     rax, [rbx+60h]
0x180020bfe  mov     [rsp+150h+var_E0], rax
0x180020c03  call    ??$?RV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180020c08  mov     r8d, edi
0x180020c0b  lea     rdx, [rbp+50h+var_D0]
0x180020c0f  mov     rcx, rbx
0x180020c12  call    ?serialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x180020c17  lea     rcx, [rbp+50h+var_D0]; this
0x180020c1b  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180020c20  test    eax, eax
0x180020c22  js      short loc_180020C2D
0x180020c24  mov     rax, [r14+810h]
0x180020c2b  jmp     short loc_180020C34
0x180020c2d  bts     dword ptr [rbx+40h], 14h
0x180020c32  xor     eax, eax
0x180020c34  mov     rcx, [rbp+50h+var_30]
0x180020c38  xor     rcx, rsp; StackCookie
0x180020c3b  call    __security_check_cookie
0x180020c40  add     rsp, 130h
0x180020c47  pop     r14
0x180020c49  pop     rdi
0x180020c4a  pop     rsi
0x180020c4b  pop     rbx
0x180020c4c  pop     rbp
0x180020c4d  retn
```
