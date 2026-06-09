# SystemSettings::BatteryUsageHandlers::AppListEntry::get_Id(HSTRING__ * *)

- ea: `0x18004c840`
- end: `0x18004c92b`
- name: `?get_Id@AppListEntry@BatteryUsageHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `235`
- prototype: `int(SystemSettings::BatteryUsageHandlers::AppListEntry *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000a13c`
- `0x18001de40`
- `0x18001e360`
- `0x180021138`
- `0x180021534`
- `0x18004c840`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004c904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004c904`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry::get_Id(
        SystemSettings::BatteryUsageHandlers::AppListEntry *this,
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
        (void *)0x11C,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
      v9 = 277;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
        (const char *)(unsigned int)v6,
        (int)v14[0]);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v14);
      return v8;
    }
    v6 = SystemSettings::DataModel::WindowsCreateString((const WCHAR *)v14[0], (unsigned __int16 *)a2, v7);
    v8 = v6;
    if ( v6 < 0 )
    {
      v9 = 279;
      goto LABEL_6;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18004c840  mov     r11, rsp
0x18004c843  mov     [r11+8], rbx
0x18004c847  mov     [r11+10h], rsi
0x18004c84b  push    rdi
0x18004c84c  sub     rsp, 40h
0x18004c850  mov     rax, [rcx+60h]
0x18004c854  xor     esi, esi
0x18004c856  mov     rdi, rdx
0x18004c859  test    rax, rax
0x18004c85c  jnz     loc_18004C8F1
0x18004c862  add     rcx, 140h
0x18004c869  mov     [r11-28h], rsi
0x18004c86d  mov     [r11-20h], rsi
0x18004c871  mov     [r11-18h], rsi
0x18004c875  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004c87a  mov     r8, rax
0x18004c87d  lea     rcx, [rsp+48h+var_28]
0x18004c882  lea     rdx, aAppdetailsWs; "AppDetails_%ws"
0x18004c889  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004c88e  mov     ebx, eax
0x18004c890  test    eax, eax
0x18004c892  jns     short loc_18004C89B
0x18004c894  mov     edx, 115h
0x18004c899  jmp     short loc_18004C8B3
0x18004c89b  mov     rcx, [rsp+48h+var_28]; this
0x18004c8a0  mov     rdx, rdi; unsigned __int16 *
0x18004c8a3  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004c8a8  mov     ebx, eax
0x18004c8aa  test    eax, eax
0x18004c8ac  jns     short loc_18004C8D5
0x18004c8ae  mov     edx, 117h; void *
0x18004c8b3  mov     rcx, [rsp+48h]; this
0x18004c8b8  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004c8bf  mov     r9d, eax; char *
0x18004c8c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c8c7  lea     rcx, [rsp+48h+var_28]
0x18004c8cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004c8d1  mov     eax, ebx
0x18004c8d3  jmp     short loc_18004C8E1
0x18004c8d5  lea     rcx, [rsp+48h+var_28]
0x18004c8da  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004c8df  xor     eax, eax
0x18004c8e1  mov     rbx, [rsp+48h+arg_0]
0x18004c8e6  mov     rsi, [rsp+48h+arg_8]
0x18004c8eb  add     rsp, 40h
0x18004c8ef  pop     rdi
0x18004c8f0  retn
0x18004c8f1  mov     rcx, [rax]; sourceString
0x18004c8f4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004c8f8  inc     rdx; length
0x18004c8fb  cmp     [rcx+rdx*2], si
0x18004c8ff  jnz     short loc_18004C8F8
0x18004c901  mov     r8, rdi; string
0x18004c904  call    cs:__imp_WindowsCreateString
0x18004c90a  mov     ebx, eax
0x18004c90c  test    eax, eax
0x18004c90e  jns     short loc_18004C8DF
0x18004c910  mov     rcx, [rsp+48h]; this
0x18004c915  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004c91c  mov     r9d, eax; char *
0x18004c91f  mov     edx, 11Ch; void *
0x18004c924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c929  jmp     short loc_18004C8D1
```
