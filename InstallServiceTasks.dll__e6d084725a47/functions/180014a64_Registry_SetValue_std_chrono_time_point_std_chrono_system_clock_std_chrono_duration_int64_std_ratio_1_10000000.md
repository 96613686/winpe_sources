# Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)

- ea: `0x180014a64`
- end: `0x180014b3e`
- name: `??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z`
- size: `218`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180017b80`
- `0x180020fe4`
- `0x180027178`

## callees

- `0x180003450`
- `0x180009884`
- `0x18000d370`
- `0x180010150`
- `0x180014a64`
- `0x180018f7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014ace`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014ace`

## string_xrefs

- `0x180014adc`: `onecoreuap\enduser\winstore\installservice\lib\RegHelpers.h`
- `0x180014b29`: `onecoreuap\enduser\winstore\installservice\lib\RegHelpers.h`

## pseudocode

```c
unsigned int __fastcall Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName)
{
  const unsigned __int16 *v6; // rax
  int v7; // eax
  unsigned int v8; // eax
  int lpData; // [rsp+20h] [rbp-B8h]
  unsigned __int16 Data[28]; // [rsp+40h] [rbp-98h] BYREF
  wchar_t Buffer[28]; // [rsp+78h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v6 = (const unsigned __int16 *)time_point_iso8601::time_point_iso8601(Buffer);
  v7 = StringCchCopyW(Data, 0x1Au, v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
      (const char *)(unsigned int)v7,
      lpData);
  v8 = RegSetKeyValueW(hKey, lpSubKey, lpValueName, 1u, Data, 0x34u);
  return wil::details::in1diag3::Throw_IfWin32ErrorMsg(
           retaddr,
           (void *)0x120,
           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
           (const char *)v8,
           (unsigned int)"Subkey : %ws, ValueName :%ws",
           (const char *)lpSubKey,
           lpValueName);
}

```

## disassembly

```asm
0x180014a64  push    rbx
0x180014a66  push    rsi
0x180014a67  push    rdi
0x180014a68  sub     rsp, 0C0h
0x180014a6f  mov     rax, cs:__security_cookie
0x180014a76  xor     rax, rsp
0x180014a79  mov     [rsp+0D8h+var_28], rax
0x180014a81  mov     rbx, rdx
0x180014a84  mov     rsi, rcx
0x180014a87  mov     rdx, r9
0x180014a8a  lea     rcx, [rsp+0D8h+Buffer]; Buffer
0x180014a8f  mov     rdi, r8
0x180014a92  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180014a97  mov     r8, rax; unsigned __int16 *
0x180014a9a  lea     rcx, [rsp+0D8h+Data]; unsigned __int16 *
0x180014a9f  mov     edx, 1Ah; unsigned __int64
0x180014aa4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014aa9  test    eax, eax
0x180014aab  js      short loc_180014B21
0x180014aad  lea     rax, [rsp+0D8h+Data]
0x180014ab2  mov     [rsp+0D8h+cbData], 34h ; '4'; cbData
0x180014aba  mov     r9d, 1; dwType
0x180014ac0  mov     [rsp+0D8h+lpData], rax; lpData
0x180014ac5  mov     r8, rdi; lpValueName
0x180014ac8  mov     rdx, rbx; lpSubKey
0x180014acb  mov     rcx, rsi; hKey
0x180014ace  call    cs:__imp_RegSetKeyValueW
0x180014ad4  mov     rcx, [rsp+0D8h]; this
0x180014adc  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\installs"...
0x180014ae3  mov     r9d, eax; char *
0x180014ae6  mov     [rsp+0D8h+var_A8], rdi
0x180014aeb  lea     rax, aSubkeyWsValuen; "Subkey : %ws, ValueName :%ws"
0x180014af2  mov     qword ptr [rsp+0D8h+cbData], rbx; char *
0x180014af7  mov     edx, 120h; void *
0x180014afc  mov     [rsp+0D8h+lpData], rax; unsigned int
0x180014b01  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180014b06  mov     rcx, [rsp+0D8h+var_28]
0x180014b0e  xor     rcx, rsp; StackCookie
0x180014b11  call    __security_check_cookie
0x180014b16  add     rsp, 0C0h
0x180014b1d  pop     rdi
0x180014b1e  pop     rsi
0x180014b1f  pop     rbx
0x180014b20  retn
0x180014b21  mov     rcx, [rsp+0D8h]; this
0x180014b29  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\installs"...
0x180014b30  mov     r9d, eax; char *
0x180014b33  mov     edx, 34h ; '4'; void *
0x180014b38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
