# PowerGrid::ShouldSendNewForecast(void)

- ea: `0x180031200`
- end: `0x180031373`
- name: `?ShouldSendNewForecast@PowerGrid@@YA_NXZ`
- size: `371`
- prototype: `bool __fastcall(PowerGrid *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fa90`

## callees

- `0x1800268ef`
- `0x18002dcd4`
- `0x180031200`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003132d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003132d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031233`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031233`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031297`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031297`

## string_xrefs

- `0x1800312b4`: `onecore\base\sustainability\tasks\deferredcharging\dll\helpers.cpp`

## pseudocode

```c
bool __fastcall PowerGrid::ShouldSendNewForecast(PowerGrid *this)
{
  unsigned __int64 v1; // rbx
  int PersistedRegistryLocationW; // eax
  signed int v3; // edi
  DWORD dwLowDateTime; // ecx
  DWORD dwHighDateTime; // eax
  LSTATUS ValueW; // eax
  struct _FILETIME pvData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[88]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  pvData = SystemTimeAsFileTime;
  v1 = *(_QWORD *)&SystemTimeAsFileTime + 2376000000000LL;
  v9 = 0;
  memset_0(SubKey, 0, 0xAAu);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"COAWOSRoot",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\COAWOS\\PowerGrid",
                                 SubKey,
                                 170);
  v3 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW > 0 )
    v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\helpers.cpp",
      (const char *)(unsigned int)v3,
      0);
LABEL_5:
    dwLowDateTime = v9;
    dwHighDateTime = HIDWORD(v9);
    goto LABEL_6;
  }
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ForecastExpiration", 0x48u, 0, &pvData, &pcbData);
  v3 = ValueW;
  if ( ValueW > 0 )
    v3 = (unsigned __int16)ValueW | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_5;
  dwHighDateTime = pvData.dwHighDateTime;
  dwLowDateTime = pvData.dwLowDateTime;
LABEL_6:
  pvData = (struct _FILETIME)__PAIR64__(dwHighDateTime, dwLowDateTime);
  return v3 < 0 || *(_QWORD *)&pvData <= v1;
}

```

## disassembly

```asm
0x180031200  mov     [rsp-8+arg_0], rbx
0x180031205  mov     [rsp-8+arg_8], rdi
0x18003120a  push    rbp
0x18003120b  lea     rbp, [rsp-20h]
0x180031210  sub     rsp, 120h
0x180031217  mov     rax, cs:__security_cookie
0x18003121e  xor     rax, rsp
0x180031221  mov     [rbp+20h+var_10], rax
0x180031225  lea     rcx, [rsp+120h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003122a  mov     qword ptr [rsp+120h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180031233  call    cs:__imp_GetSystemTimeAsFileTime
0x180031239  mov     eax, [rsp+120h+SystemTimeAsFileTime.dwHighDateTime]
0x18003123d  lea     rcx, [rsp+120h+SubKey]; void *
0x180031242  mov     dword ptr [rsp+120h+var_E0+4], eax
0x180031246  mov     edi, 0AAh
0x18003124b  mov     eax, [rsp+120h+SystemTimeAsFileTime.dwLowDateTime]
0x18003124f  mov     r8d, edi; Size
0x180031252  mov     dword ptr [rsp+120h+var_E0], eax
0x180031256  xor     edx, edx; Val
0x180031258  mov     rbx, [rsp+120h+var_E0]
0x18003125d  mov     rax, 22934A2D000h
0x180031267  add     rbx, rax
0x18003126a  mov     [rsp+120h+var_D8], 0
0x180031273  call    memset_0
0x180031278  mov     r9d, edi
0x18003127b  mov     [rsp+120h+pdwType], 0; int
0x180031284  lea     r8, [rsp+120h+SubKey]
0x180031289  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180031290  lea     rcx, aCoawosroot; "COAWOSRoot"
0x180031297  call    cs:__imp_GetPersistedRegistryLocationW
0x18003129d  mov     edi, eax
0x18003129f  test    eax, eax
0x1800312a1  jle     short loc_1800312AC
0x1800312a3  movzx   edi, ax
0x1800312a6  or      edi, 80070000h
0x1800312ac  test    edi, edi
0x1800312ae  jns     short loc_1800312E6
0x1800312b0  mov     rcx, [rbp+28h]; this
0x1800312b4  lea     r8, aOnecoreBaseSus; "onecore\\base\\sustainability\\tasks\\d"...
0x1800312bb  mov     r9d, edi; char *
0x1800312be  mov     edx, 22h ; '"'; void *
0x1800312c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312c8  mov     ecx, dword ptr [rsp+120h+var_D8]
0x1800312cc  mov     eax, dword ptr [rsp+120h+var_D8+4]
0x1800312d0  mov     dword ptr [rsp+120h+var_E0+4], eax
0x1800312d4  mov     dword ptr [rsp+120h+var_E0], ecx
0x1800312d8  test    edi, edi
0x1800312da  js      short loc_180031350
0x1800312dc  cmp     [rsp+120h+var_E0], rbx
0x1800312e1  setbe   al
0x1800312e4  jmp     short loc_180031352
0x1800312e6  lea     rax, [rsp+120h+var_D0]
0x1800312eb  mov     [rsp+120h+var_E0], 0
0x1800312f4  mov     [rsp+120h+pcbData], rax; pcbData
0x1800312f9  lea     r8, Value; "ForecastExpiration"
0x180031300  lea     rax, [rsp+120h+var_E0]
0x180031305  mov     [rsp+120h+var_D0], 8
0x18003130d  mov     [rsp+120h+pvData], rax; pvData
0x180031312  lea     rdx, [rsp+120h+SubKey]; lpSubKey
0x180031317  mov     r9d, 48h ; 'H'; dwFlags
0x18003131d  mov     [rsp+120h+pdwType], 0; pdwType
0x180031326  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003132d  call    cs:__imp_RegGetValueW
0x180031333  mov     edi, eax
0x180031335  test    eax, eax
0x180031337  jle     short loc_180031342
0x180031339  movzx   edi, ax
0x18003133c  or      edi, 80070000h
0x180031342  test    edi, edi
0x180031344  js      short loc_1800312C8
0x180031346  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x18003134a  mov     ecx, dword ptr [rsp+120h+var_E0]
0x18003134e  jmp     short loc_1800312D0
0x180031350  mov     al, 1
0x180031352  mov     rcx, [rbp+20h+var_10]
0x180031356  xor     rcx, rsp; StackCookie
0x180031359  call    __security_check_cookie
0x18003135e  lea     r11, [rsp+120h+var_s0]
0x180031366  mov     rbx, [r11+10h]
0x18003136a  mov     rdi, [r11+18h]
0x18003136e  mov     rsp, r11
0x180031371  pop     rbp
0x180031372  retn
```
