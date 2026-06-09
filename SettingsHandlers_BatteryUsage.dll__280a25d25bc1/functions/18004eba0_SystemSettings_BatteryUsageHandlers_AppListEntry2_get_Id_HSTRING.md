# SystemSettings::BatteryUsageHandlers::AppListEntry2::get_Id(HSTRING__ * *)

- ea: `0x18004eba0`
- end: `0x18004ec8b`
- name: `?get_Id@AppListEntry2@BatteryUsageHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `235`
- prototype: `int(SystemSettings::BatteryUsageHandlers::AppListEntry2 *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000a13c`
- `0x18001de40`
- `0x18001e360`
- `0x180021138`
- `0x180021534`
- `0x18004eba0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004ec64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004ec64`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry2::get_Id(
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *this,
        HSTRING *a2,
        __int64 a3)
{
  const WCHAR **v3; // rax
  __int64 v5; // rax
  int v6; // eax
  HSTRING *v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  const WCHAR *v11; // rcx
  __int64 v12; // rdx
  HRESULT String; // eax
  SystemSettings::DataModel *v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = (const WCHAR **)*((_QWORD *)this + 12);
  if ( v3 )
  {
    v11 = *v3;
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    String = WindowsCreateString(v11, v12, a2);
    v8 = String;
    if ( String < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)String,
        (int)v14[0]);
      return v8;
    }
  }
  else
  {
    memset(v14, 0, 24);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 320, a2, a3);
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
           v14,
           L"AppDetails_%ws",
           v5);
    v8 = v6;
    if ( v6 < 0 )
    {
      v9 = 311;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)v6,
        (int)v14[0]);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v14);
      return v8;
    }
    v6 = SystemSettings::DataModel::WindowsCreateString((const WCHAR *)v14[0], (unsigned __int16 *)a2, v7);
    v8 = v6;
    if ( v6 < 0 )
    {
      v9 = 313;
      goto LABEL_6;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18004eba0  mov     r11, rsp
0x18004eba3  mov     [r11+8], rbx
0x18004eba7  mov     [r11+10h], rsi
0x18004ebab  push    rdi
0x18004ebac  sub     rsp, 40h
0x18004ebb0  mov     rax, [rcx+60h]
0x18004ebb4  xor     esi, esi
0x18004ebb6  mov     rdi, rdx
0x18004ebb9  test    rax, rax
0x18004ebbc  jnz     loc_18004EC51
0x18004ebc2  add     rcx, 140h
0x18004ebc9  mov     [r11-28h], rsi
0x18004ebcd  mov     [r11-20h], rsi
0x18004ebd1  mov     [r11-18h], rsi
0x18004ebd5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ebda  mov     r8, rax
0x18004ebdd  lea     rcx, [rsp+48h+var_28]
0x18004ebe2  lea     rdx, aAppdetailsWs; "AppDetails_%ws"
0x18004ebe9  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004ebee  mov     ebx, eax
0x18004ebf0  test    eax, eax
0x18004ebf2  jns     short loc_18004EBFB
0x18004ebf4  mov     edx, 137h
0x18004ebf9  jmp     short loc_18004EC13
0x18004ebfb  mov     rcx, [rsp+48h+var_28]; this
0x18004ec00  mov     rdx, rdi; unsigned __int16 *
0x18004ec03  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004ec08  mov     ebx, eax
0x18004ec0a  test    eax, eax
0x18004ec0c  jns     short loc_18004EC35
0x18004ec0e  mov     edx, 139h; void *
0x18004ec13  mov     rcx, [rsp+48h]; this
0x18004ec18  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ec1f  mov     r9d, eax; char *
0x18004ec22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec27  lea     rcx, [rsp+48h+var_28]
0x18004ec2c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004ec31  mov     eax, ebx
0x18004ec33  jmp     short loc_18004EC41
0x18004ec35  lea     rcx, [rsp+48h+var_28]
0x18004ec3a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004ec3f  xor     eax, eax
0x18004ec41  mov     rbx, [rsp+48h+arg_0]
0x18004ec46  mov     rsi, [rsp+48h+arg_8]
0x18004ec4b  add     rsp, 40h
0x18004ec4f  pop     rdi
0x18004ec50  retn
0x18004ec51  mov     rcx, [rax]; sourceString
0x18004ec54  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ec58  inc     rdx; length
0x18004ec5b  cmp     [rcx+rdx*2], si
0x18004ec5f  jnz     short loc_18004EC58
0x18004ec61  mov     r8, rdi; string
0x18004ec64  call    cs:__imp_WindowsCreateString
0x18004ec6a  mov     ebx, eax
0x18004ec6c  test    eax, eax
0x18004ec6e  jns     short loc_18004EC3F
0x18004ec70  mov     rcx, [rsp+48h]; this
0x18004ec75  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ec7c  mov     r9d, eax; char *
0x18004ec7f  mov     edx, 13Eh; void *
0x18004ec84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec89  jmp     short loc_18004EC31
```
