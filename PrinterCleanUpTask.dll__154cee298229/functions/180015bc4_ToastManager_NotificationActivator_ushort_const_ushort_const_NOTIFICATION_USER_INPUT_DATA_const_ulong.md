# ToastManager::NotificationActivator(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180015bc4`
- end: `0x180015cce`
- name: `?NotificationActivator@ToastManager@@SAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `266`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180006b80`

## callees

- `0x180002020`
- `0x1800085e8`
- `0x180009a78`
- `0x18000aeb4`
- `0x18000f0d0`
- `0x18000f26c`
- `0x18000f88c`
- `0x1800158c8`
- `0x180015bc4`
- `0x180015e3c`

## string_xrefs

- `0x180015c38`: `PrintJobCleanupTask`

## pseudocode

```c
__int64 __fastcall ToastManager::NotificationActivator(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct NOTIFICATION_USER_INPUT_DATA *a3)
{
  int v3; // eax
  __int64 v4; // r8
  int v5; // r9d
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  PrintJobCleanUpUtil *v10; // rax
  const unsigned __int16 *v11; // rdx
  _BYTE v13[16]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v14; // [rsp+48h] [rbp-60h]
  _BYTE v15[16]; // [rsp+58h] [rbp-50h] BYREF
  __int64 v16; // [rsp+68h] [rbp-40h]
  _BYTE v17[32]; // [rsp+78h] [rbp-30h] BYREF

  std::wstring::wstring(v13, a2);
  std::_WChar_traits<unsigned short>::length(L"/");
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = std::_Traits_find<std::char_traits<unsigned short>>(v3, v14, v4, v5, v4);
  v7 = v6;
  if ( v6 != -1 )
  {
    std::wstring::substr(v13, v15, 0, v6);
    std::_WChar_traits<unsigned short>::length(L"PrintJobCleanupTask");
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v8, v16) )
    {
      v9 = std::wstring::substr(v13, v17, v7 + 1, -1);
      v10 = (PrintJobCleanUpUtil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
      PrintJobCleanUpUtil::Activate(v10, v11);
      std::wstring::_Tidy_deallocate(v17);
    }
    std::wstring::_Tidy_deallocate(v15);
  }
  std::wstring::_Tidy_deallocate(v13);
  return 0;
}

```

## disassembly

```asm
0x180015bc4  push    rbx
0x180015bc6  sub     rsp, 0A0h
0x180015bcd  mov     rax, cs:__security_cookie
0x180015bd4  xor     rax, rsp
0x180015bd7  mov     [rsp+0A8h+var_10], rax
0x180015bdf  lea     rcx, [rsp+0A8h+var_70]
0x180015be4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015be9  nop
0x180015bea  lea     rcx, asc_18001A270; "/"
0x180015bf1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015bf6  mov     r8, rax
0x180015bf9  lea     rcx, [rsp+0A8h+var_70]
0x180015bfe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015c03  mov     rcx, rax
0x180015c06  mov     [rsp+0A8h+var_88], r8
0x180015c0b  mov     rdx, [rsp+0A8h+var_60]
0x180015c10  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180015c15  mov     rbx, rax
0x180015c18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015c1c  jz      loc_180015CA2
0x180015c22  mov     r9, rax
0x180015c25  xor     r8d, r8d
0x180015c28  lea     rdx, [rsp+0A8h+var_50]
0x180015c2d  lea     rcx, [rsp+0A8h+var_70]
0x180015c32  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180015c37  nop
0x180015c38  lea     r8, aPrintjobcleanu; "PrintJobCleanupTask"
0x180015c3f  mov     rcx, r8
0x180015c42  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015c47  mov     r9, rax
0x180015c4a  lea     rcx, [rsp+0A8h+var_50]
0x180015c4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015c54  mov     rcx, rax
0x180015c57  mov     rdx, [rsp+0A8h+var_40]
0x180015c5c  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180015c61  test    al, al
0x180015c63  jz      short loc_180015C97
0x180015c65  lea     r8, [rbx+1]
0x180015c69  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015c6d  lea     rdx, [rsp+0A8h+var_30]
0x180015c72  lea     rcx, [rsp+0A8h+var_70]
0x180015c77  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180015c7c  mov     rcx, rax
0x180015c7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015c84  mov     rcx, rax; this
0x180015c87  call    ?Activate@PrintJobCleanUpUtil@@YAJPEBG@Z; PrintJobCleanUpUtil::Activate(ushort const *)
0x180015c8c  lea     rcx, [rsp+0A8h+var_30]
0x180015c91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015c96  nop
0x180015c97  lea     rcx, [rsp+0A8h+var_50]
0x180015c9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ca1  nop
0x180015ca2  lea     rcx, [rsp+0A8h+var_70]
0x180015ca7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015cac  xor     eax, eax
0x180015cae  jmp     short loc_180015CB4
0x180015cb0  mov     eax, [rsp+0A8h+var_78]
0x180015cb4  mov     rcx, [rsp+0A8h+var_10]
0x180015cbc  xor     rcx, rsp; StackCookie
0x180015cbf  call    __security_check_cookie
0x180015cc4  add     rsp, 0A0h
0x180015ccb  pop     rbx
0x180015ccc  retn
```
