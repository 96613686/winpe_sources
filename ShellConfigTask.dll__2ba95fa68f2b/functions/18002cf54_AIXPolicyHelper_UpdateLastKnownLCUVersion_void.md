# AIXPolicyHelper::UpdateLastKnownLCUVersion(void)

- ea: `0x18002cf54`
- end: `0x18002d045`
- name: `?UpdateLastKnownLCUVersion@AIXPolicyHelper@@YAXXZ`
- size: `241`
- prototype: `void __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x180002590`
- `0x180013890`
- `0x18001a154`
- `0x18002065c`
- `0x1800233ec`
- `0x18002cf54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cffe`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cfd9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cfd9`

## string_xrefs

- `0x18002cf84`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`
- `0x18002d033`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AIXPolicyHelper::UpdateLastKnownLCUVersion(AIXPolicyHelper *this)
{
  _QWORD *v1; // rax
  __int64 v2; // rdx
  DWORD cbData; // edx
  int v4; // eax
  int lpData; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  _QWORD Data[4]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  AIXPolicyHelper::GetCurrentLCUVersion((__int64)Data);
  hKey = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
              &hKey) < 0 )
    goto LABEL_10;
  if ( Data[3] <= 7u )
  {
    v1 = Data;
    goto LABEL_4;
  }
  v1 = (_QWORD *)Data[0];
  if ( Data[0] )
  {
LABEL_4:
    v2 = -1;
    do
      ++v2;
    while ( *((_WORD *)v1 + v2) );
    cbData = 2 * v2 + 2;
    goto LABEL_7;
  }
  cbData = 0;
LABEL_7:
  v4 = RegSetKeyValueW(hKey, 0, L"LastKnownLCUVersion", 1u, v1, cbData);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      lpData);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(Data);
}

```

## disassembly

```asm
0x18002cf54  push    rbx
0x18002cf56  sub     rsp, 60h
0x18002cf5a  mov     rax, cs:__security_cookie
0x18002cf61  xor     rax, rsp
0x18002cf64  mov     [rsp+68h+var_10], rax
0x18002cf69  lea     rcx, [rsp+68h+Data]
0x18002cf6e  call    ?GetCurrentLCUVersion@AIXPolicyHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AIXPolicyHelper::GetCurrentLCUVersion(void)
0x18002cf73  nop
0x18002cf74  xor     ebx, ebx
0x18002cf76  mov     [rsp+68h+hKey], rbx
0x18002cf7b  lea     r9d, [rbx+1]
0x18002cf7f  lea     r8, [rsp+68h+hKey]; phkResult
0x18002cf84  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002cf8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cf92  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002cf97  test    eax, eax
0x18002cf99  js      short loc_18002CFF4
0x18002cf9b  mov     rcx, [rsp+68h+hKey]; hKey
0x18002cfa0  cmp     [rsp+68h+var_18], 7
0x18002cfa6  ja      short loc_18002D022
0x18002cfa8  lea     rax, [rsp+68h+Data]
0x18002cfad  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002cfb1  inc     rdx
0x18002cfb4  cmp     [rax+rdx*2], bx
0x18002cfb8  jnz     short loc_18002CFB1
0x18002cfba  lea     edx, ds:2[rdx*2]
0x18002cfc1  mov     [rsp+68h+cbData], edx; cbData
0x18002cfc5  mov     [rsp+68h+lpData], rax; int
0x18002cfca  mov     r9d, 1; dwType
0x18002cfd0  lea     r8, aLastknownlcuve; "LastKnownLCUVersion"
0x18002cfd7  xor     edx, edx; lpSubKey
0x18002cfd9  call    cs:__imp_RegSetKeyValueW
0x18002cfdf  test    eax, eax
0x18002cfe1  jle     short loc_18002CFEB
0x18002cfe3  movzx   eax, ax
0x18002cfe6  or      eax, 80070000h
0x18002cfeb  mov     rcx, [rsp+68h]; this
0x18002cff0  test    eax, eax
0x18002cff2  js      short loc_18002D030
0x18002cff4  mov     rcx, [rsp+68h+hKey]; hKey
0x18002cff9  test    rcx, rcx
0x18002cffc  jz      short loc_18002D005
0x18002cffe  call    cs:__imp_RegCloseKey
0x18002d004  nop
0x18002d005  lea     rcx, [rsp+68h+Data]
0x18002d00a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d00f  mov     rcx, [rsp+68h+var_10]
0x18002d014  xor     rcx, rsp; StackCookie
0x18002d017  call    __security_check_cookie
0x18002d01c  add     rsp, 60h
0x18002d020  pop     rbx
0x18002d021  retn
0x18002d022  mov     rax, [rsp+68h+Data]
0x18002d027  test    rax, rax
0x18002d02a  jnz     short loc_18002CFAD
0x18002d02c  mov     edx, ebx
0x18002d02e  jmp     short loc_18002CFC1
0x18002d030  mov     r9d, eax; char *
0x18002d033  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002d03a  mov     edx, 1CBEh; void *
0x18002d03f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
