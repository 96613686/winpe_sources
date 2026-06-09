# MediaObjectInfo::GetText(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18000ada0`
- end: `0x18000aeeb`
- name: `?GetText@MediaObjectInfo@@UEBAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c50`
- `0x18000ada0`
- `0x18000b418`
- `0x18000b448`
- `0x18000b7d4`
- `0x18000b938`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae8a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000aebc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae8a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000aebc`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x18000ae63`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x18000ae63`

## pseudocode

```c
__int64 __fastcall MediaObjectInfo::GetText(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  void *v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF

  if ( !a2 )
  {
    Log_HREvent_0(-2147024809);
    Log_AssertionEvent_0(v5, v4, 267);
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 2147942487LL;
  }
  if ( *((_DWORD *)a1 + 20) != 1 && *((_DWORD *)a1 + 20) != 6 )
  {
    Log_AssertionEvent_0(a1, a2, 269);
    if ( *((_DWORD *)a1 + 20) != 1 && *((_DWORD *)a1 + 20) != 6 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *a1;
  v12 = 0;
  v11 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 64))(a1, &v12);
  v9 = v8;
  if ( v8 >= 0
    && (tlx::auto_xxx<char *,void (*)(char *),&void tlx::_delete_array<char>(char *),0>::reset(&v11, 0),
        v8 = ReadStreamContent(v12, &v11, 0xFFFFFFFFLL),
        v9 = v8,
        v8 >= 0) )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            a2,
                            v11) )
    {
      if ( v11 )
        operator delete[](v11);
      v9 = 0;
      goto LABEL_18;
    }
    v9 = -2147024882;
    v10 = -2147024882;
  }
  else
  {
    v10 = v8;
  }
  Log_HREvent_0(v10);
  if ( v11 )
    operator delete[](v11);
LABEL_18:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return v9;
}

```

## disassembly

```asm
0x18000ada0  mov     [rsp-8+arg_10], rbx
0x18000ada5  mov     [rsp-8+arg_18], rdi
0x18000adaa  push    rbp
0x18000adab  mov     rbp, rsp
0x18000adae  sub     rsp, 50h
0x18000adb2  mov     rax, cs:__security_cookie
0x18000adb9  xor     rax, rsp
0x18000adbc  mov     [rbp+var_10], rax
0x18000adc0  mov     rdi, rdx
0x18000adc3  mov     rbx, rcx
0x18000adc6  test    rdx, rdx
0x18000adc9  jnz     short loc_18000ADF3
0x18000adcb  mov     ebx, 10Bh
0x18000add0  mov     edi, 80070057h
0x18000add5  mov     r9d, ebx
0x18000add8  mov     ecx, edi; int
0x18000adda  call    Log_HREvent_0
0x18000addf  mov     r8d, ebx
0x18000ade2  call    Log_AssertionEvent_0
0x18000ade7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000adec  mov     eax, edi
0x18000adee  jmp     loc_18000AECF
0x18000adf3  cmp     dword ptr [rcx+50h], 1
0x18000adf7  jz      short loc_18000AE1B
0x18000adf9  cmp     dword ptr [rcx+50h], 6
0x18000adfd  jz      short loc_18000AE1B
0x18000adff  mov     r8d, 10Dh
0x18000ae05  call    Log_AssertionEvent_0
0x18000ae0a  cmp     dword ptr [rbx+50h], 1
0x18000ae0e  jz      short loc_18000AE1B
0x18000ae10  cmp     dword ptr [rbx+50h], 6
0x18000ae14  jz      short loc_18000AE1B
0x18000ae16  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ae1b  mov     rax, [rbx]
0x18000ae1e  lea     rdx, [rbp+var_18]
0x18000ae22  mov     rcx, rbx
0x18000ae25  mov     [rbp+var_18], 0
0x18000ae2d  mov     [rbp+var_20], 0
0x18000ae35  mov     rax, [rax+40h]
0x18000ae39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3e  mov     ebx, eax
0x18000ae40  test    eax, eax
0x18000ae42  jns     short loc_18000AE4C
0x18000ae44  mov     r9d, 112h
0x18000ae4a  jmp     short loc_18000AE75
0x18000ae4c  xor     edx, edx
0x18000ae4e  lea     rcx, [rbp+var_20]
0x18000ae52  call    ?reset@?$auto_xxx@PEADP6AXPEAD@Z$1??$_delete_array@D@tlx@@YAX0@Z$0A@@tlx@@QEAAXPEAD@Z; tlx::auto_xxx<char *,void (*)(char *),&tlx::_delete_array<char>(char *),0>::reset(char *)
0x18000ae57  mov     rcx, [rbp+var_18]
0x18000ae5b  lea     rdx, [rbp+var_20]
0x18000ae5f  or      r8d, 0FFFFFFFFh
0x18000ae63  call    cs:__imp_ReadStreamContent
0x18000ae69  mov     ebx, eax
0x18000ae6b  test    eax, eax
0x18000ae6d  jns     short loc_18000AE92
0x18000ae6f  mov     r9d, 116h
0x18000ae75  mov     edx, 1
0x18000ae7a  mov     ecx, eax; int
0x18000ae7c  call    Log_HREvent_0
0x18000ae81  mov     rcx, [rbp+var_20]
0x18000ae85  test    rcx, rcx
0x18000ae88  jz      short loc_18000AEC4
0x18000ae8a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae90  jmp     short loc_18000AEC4
0x18000ae92  mov     rdx, [rbp+var_20]
0x18000ae96  mov     rcx, rdi
0x18000ae99  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000ae9e  test    al, al
0x18000aea0  jnz     short loc_18000AEB3
0x18000aea2  mov     ebx, 8007000Eh
0x18000aea7  xor     edx, edx
0x18000aea9  mov     ecx, ebx
0x18000aeab  mov     r9d, 119h
0x18000aeb1  jmp     short loc_18000AE7C
0x18000aeb3  mov     rcx, [rbp+var_20]
0x18000aeb7  test    rcx, rcx
0x18000aeba  jz      short loc_18000AEC2
0x18000aebc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000aec2  xor     ebx, ebx
0x18000aec4  lea     rcx, [rbp+var_18]
0x18000aec8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000aecd  mov     eax, ebx
0x18000aecf  mov     rcx, [rbp+var_10]
0x18000aed3  xor     rcx, rsp; StackCookie
0x18000aed6  call    __security_check_cookie
0x18000aedb  mov     rbx, [rsp+50h+arg_10]
0x18000aee0  mov     rdi, [rsp+50h+arg_18]
0x18000aee5  add     rsp, 50h
0x18000aee9  pop     rbp
0x18000aeea  retn
```
