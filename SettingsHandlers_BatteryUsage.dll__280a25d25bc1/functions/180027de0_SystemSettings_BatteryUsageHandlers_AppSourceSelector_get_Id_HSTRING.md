# SystemSettings::BatteryUsageHandlers::AppSourceSelector::get_Id(HSTRING__ * *)

- ea: `0x180027de0`
- end: `0x180027eaf`
- name: `?get_Id@AppSourceSelector@BatteryUsageHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `207`
- prototype: `int(SystemSettings::BatteryUsageHandlers::AppSourceSelector *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x18000a8fc`
- `0x180027de0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x180027e33`
- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x180027e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027e84`

## pseudocode

```c
HRESULT __fastcall SystemSettings::BatteryUsageHandlers::AppSourceSelector::get_Id(
        SystemSettings::BatteryUsageHandlers::AppSourceSelector *this,
        HSTRING *a2)
{
  unsigned __int16 **v4; // rcx
  HRESULT result; // eax
  __int64 v6; // rdx
  unsigned __int16 *v7; // rcx
  _DWORD v8[4]; // [rsp+20h] [rbp-228h] BYREF
  unsigned __int16 v9[256]; // [rsp+30h] [rbp-218h] BYREF

  memset_0(v9, 0, sizeof(v9));
  *a2 = 0;
  v4 = (unsigned __int16 **)*((_QWORD *)this + 12);
  v8[0] = 0;
  if ( v4 )
  {
    v7 = *v4;
    v6 = -1;
    do
      ++v6;
    while ( v7[v6] );
  }
  else
  {
    _o_rand_s(v8);
    result = StringCchPrintfW(v9, 0x100u, L"%u", v8[0]);
    if ( result < 0 )
      return result;
    v6 = -1;
    do
      ++v6;
    while ( v9[v6] );
    v7 = v9;
  }
  return WindowsCreateString(v7, v6, a2);
}

```

## disassembly

```asm
0x180027de0  mov     [rsp+arg_10], rbx
0x180027de5  mov     [rsp+arg_18], rsi
0x180027dea  push    rdi
0x180027deb  sub     rsp, 240h
0x180027df2  mov     rax, cs:__security_cookie
0x180027df9  xor     rax, rsp
0x180027dfc  mov     [rsp+248h+var_18], rax
0x180027e04  mov     rdi, rdx
0x180027e07  mov     rbx, rcx
0x180027e0a  xor     edx, edx; Val
0x180027e0c  lea     rcx, [rsp+248h+var_218]; void *
0x180027e11  mov     r8d, 200h; Size
0x180027e17  call    memset_0
0x180027e1c  xor     esi, esi
0x180027e1e  mov     [rdi], rsi
0x180027e21  mov     rcx, [rbx+60h]
0x180027e25  mov     [rsp+248h+var_228], esi
0x180027e29  test    rcx, rcx
0x180027e2c  jnz     short loc_180027E71
0x180027e2e  lea     rcx, [rsp+248h+var_228]
0x180027e33  call    cs:__imp__o_rand_s
0x180027e39  mov     r9d, [rsp+248h+var_228]
0x180027e3e  lea     r8, aU; "%u"
0x180027e45  mov     edx, 100h; unsigned __int64
0x180027e4a  lea     rcx, [rsp+248h+var_218]; unsigned __int16 *
0x180027e4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027e54  test    eax, eax
0x180027e56  js      short loc_180027E8A
0x180027e58  lea     rax, [rsp+248h+var_218]
0x180027e5d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027e61  inc     rdx
0x180027e64  cmp     [rax+rdx*2], si
0x180027e68  jnz     short loc_180027E61
0x180027e6a  lea     rcx, [rsp+248h+var_218]
0x180027e6f  jmp     short loc_180027E81
0x180027e71  mov     rcx, [rcx]; sourceString
0x180027e74  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027e78  inc     rdx; length
0x180027e7b  cmp     [rcx+rdx*2], si
0x180027e7f  jnz     short loc_180027E78
0x180027e81  mov     r8, rdi; string
0x180027e84  call    cs:__imp_WindowsCreateString
0x180027e8a  mov     rcx, [rsp+248h+var_18]
0x180027e92  xor     rcx, rsp; StackCookie
0x180027e95  call    __security_check_cookie
0x180027e9a  lea     r11, [rsp+248h+var_8]
0x180027ea2  mov     rbx, [r11+20h]
0x180027ea6  mov     rsi, [r11+28h]
0x180027eaa  mov     rsp, r11
0x180027ead  pop     rdi
0x180027eae  retn
```
