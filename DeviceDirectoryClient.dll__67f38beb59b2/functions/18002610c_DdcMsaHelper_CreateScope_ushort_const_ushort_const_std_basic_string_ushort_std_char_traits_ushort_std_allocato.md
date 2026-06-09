# DdcMsaHelper::CreateScope(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002610c`
- end: `0x180026273`
- name: `?CreateScope@DdcMsaHelper@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x1800024c0`
- `0x180004d5c`
- `0x180004db8`
- `0x1800145e0`
- `0x180020cf0`
- `0x180025de8`
- `0x18002610c`

## string_xrefs

- `0x180026191`: `service::`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::CreateScope(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  _WORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v16; // [rsp+0h] [rbp-138h] BYREF
  unsigned int v17; // [rsp+30h] [rbp-108h]
  _BYTE v18[32]; // [rsp+38h] [rbp-100h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-E0h] BYREF
  _BYTE v20[32]; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE v21[32]; // [rsp+98h] [rbp-A0h] BYREF
  _BYTE v22[32]; // [rsp+B8h] [rbp-80h] BYREF
  _BYTE v23[32]; // [rsp+D8h] [rbp-60h] BYREF
  _BYTE v24[32]; // [rsp+F8h] [rbp-40h] BYREF

  v5 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  v6 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  try
  {
    *v6 = 0;
    v7 = std::wstring::wstring(v24, L"MBI_SSL");
    v8 = std::wstring::wstring(v23, L"::");
    v9 = std::wstring::wstring(v22, a1);
    v10 = std::wstring::wstring(v21, L"service::");
    std::wstring::wstring(v20, v11, v10, v9);
    std::wstring::wstring(v19, v12, v20, v8);
    std::wstring::wstring(v18, v13, v19, v7);
    std::wstring::operator=(a3, v18);
    std::wstring::_Tidy_deallocate((__int64)v18);
    std::wstring::_Tidy_deallocate((__int64)v19);
    std::wstring::_Tidy_deallocate((__int64)v20);
    std::wstring::_Tidy_deallocate((__int64)v21);
    std::wstring::_Tidy_deallocate((__int64)v22);
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v24);
  }
  catch ( std::bad_alloc )
  {
    v17 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        (unsigned int)&v16,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
        235,
        (__int64)"CHR(((HRESULT)0x8007000EL))");
    return v17;
  }
  *v6 = 0;
}

```

## disassembly

```asm
0x18002610c  mov     [rsp+arg_8], rbx
0x180026111  mov     [rsp+arg_18], rsi
0x180026116  push    rdi
0x180026117  push    r14
0x180026119  push    r15
0x18002611b  sub     rsp, 120h
0x180026122  mov     rax, cs:__security_cookie
0x180026129  xor     rax, rsp
0x18002612c  mov     [rsp+138h+var_20], rax
0x180026134  mov     r15, r8
0x180026137  mov     r14, rcx
0x18002613a  xor     ebx, ebx
0x18002613c  mov     [r8+10h], rbx
0x180026140  mov     rcx, r8
0x180026143  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026148  mov     rdx, rax
0x18002614b  xor     eax, eax
0x18002614d  mov     [rdx], ax
0x180026150  lea     rdx, aMbiSsl; "MBI_SSL"
0x180026157  lea     rcx, [rsp+138h+var_40]
0x18002615f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026164  mov     rdi, rax
0x180026167  lea     rdx, asc_180041870; "::"
0x18002616e  lea     rcx, [rsp+138h+var_60]
0x180026176  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002617b  mov     rsi, rax
0x18002617e  mov     rdx, r14
0x180026181  lea     rcx, [rsp+138h+var_80]
0x180026189  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002618e  mov     r14, rax
0x180026191  lea     rdx, aService; "service::"
0x180026198  lea     rcx, [rsp+138h+var_A0]
0x1800261a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800261a5  nop
0x1800261a6  mov     r9, r14
0x1800261a9  mov     r8, rax
0x1800261ac  lea     rcx, [rsp+138h+var_C0]
0x1800261b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800261b6  nop
0x1800261b7  mov     r9, rsi
0x1800261ba  lea     r8, [rsp+138h+var_C0]
0x1800261bf  lea     rcx, [rsp+138h+var_E0]
0x1800261c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800261c9  nop
0x1800261ca  mov     r9, rdi
0x1800261cd  lea     r8, [rsp+138h+var_E0]
0x1800261d2  lea     rcx, [rsp+138h+var_100]
0x1800261d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800261dc  lea     rdx, [rsp+138h+var_100]
0x1800261e1  mov     rcx, r15
0x1800261e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800261e9  lea     rcx, [rsp+138h+var_100]
0x1800261ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261f3  nop
0x1800261f4  lea     rcx, [rsp+138h+var_E0]
0x1800261f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261fe  nop
0x1800261ff  lea     rcx, [rsp+138h+var_C0]
0x180026204  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026209  nop
0x18002620a  lea     rcx, [rsp+138h+var_A0]
0x180026212  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026217  nop
0x180026218  lea     rcx, [rsp+138h+var_80]
0x180026220  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026225  nop
0x180026226  lea     rcx, [rsp+138h+var_60]
0x18002622e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026233  nop
0x180026234  lea     rcx, [rsp+138h+var_40]
0x18002623c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026241  nop
0x180026242  jmp     short loc_180026248
0x180026244  mov     ebx, [rsp+138h+var_108]
0x180026248  mov     eax, ebx
0x18002624a  mov     rcx, [rsp+138h+var_20]
0x180026252  xor     rcx, rsp; StackCookie
0x180026255  call    __security_check_cookie
0x18002625a  lea     r11, [rsp+138h+var_18]
0x180026262  mov     rbx, [r11+28h]
0x180026266  mov     rsi, [r11+38h]
0x18002626a  mov     rsp, r11
0x18002626d  pop     r15
0x18002626f  pop     r14
0x180026271  pop     rdi
0x180026272  retn
```
