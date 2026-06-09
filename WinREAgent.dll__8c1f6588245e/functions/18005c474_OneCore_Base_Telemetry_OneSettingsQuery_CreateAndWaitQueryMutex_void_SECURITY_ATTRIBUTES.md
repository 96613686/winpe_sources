# OneCore::Base::Telemetry::OneSettingsQuery::CreateAndWaitQueryMutex(void * *,_SECURITY_ATTRIBUTES *)

- ea: `0x18005c474`
- end: `0x18005c53a`
- name: `?CreateAndWaitQueryMutex@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fd5c`

## callees

- `0x180012864`
- `0x18005c474`
- `0x18006c690`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18005c4e7`
- `KERNEL32!WaitForSingleObject` at `0x18005c4e7`
- `KERNEL32!GetLastError` at `0x18005c50f`
- `KERNEL32!GetLastError` at `0x18005c50f`
- `KERNEL32!CreateMutexW` at `0x18005c4d1`
- `KERNEL32!CreateMutexW` at `0x18005c4d1`

## pseudocode

```c
signed int __fastcall OneCore::Base::Telemetry::OneSettingsQuery::CreateAndWaitQueryMutex(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        void **a2,
        struct _SECURITY_ATTRIBUTES *a3)
{
  signed int result; // eax
  HANDLE MutexW; // rax
  DWORD v6; // eax
  WCHAR Name[264]; // [rsp+30h] [rbp-228h] BYREF

  result = StringCchPrintfW(
             Name,
             0x104u,
             L"%s+%s+%s",
             L"Global\\OneSettingQueryMutex",
             (char *)this + 40,
             (char *)this + 560);
  if ( result >= 0 )
  {
    MutexW = CreateMutexW(0, 0, Name);
    *a2 = MutexW;
    if ( MutexW )
    {
      v6 = WaitForSingleObject(MutexW, 0xEA60u);
      if ( !v6 )
        return 0;
      if ( v6 == 258 )
        return -2147024726;
      if ( v6 != -1 )
        return -2147467259;
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18005c474  push    rbx
0x18005c476  sub     rsp, 250h
0x18005c47d  mov     rax, cs:__security_cookie
0x18005c484  xor     rax, rsp
0x18005c487  mov     [rsp+258h+var_18], rax
0x18005c48f  lea     rax, [rcx+230h]
0x18005c496  mov     rbx, rdx
0x18005c499  add     rcx, 28h ; '('
0x18005c49d  mov     [rsp+258h+var_230], rax
0x18005c4a2  mov     [rsp+258h+var_238], rcx
0x18005c4a7  lea     r9, aGlobalOnesetti; "Global\\OneSettingQueryMutex"
0x18005c4ae  lea     rcx, [rsp+258h+Name]; unsigned __int16 *
0x18005c4b3  mov     edx, 104h; unsigned __int64
0x18005c4b8  lea     r8, aSSS; "%s+%s+%s"
0x18005c4bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005c4c4  test    eax, eax
0x18005c4c6  js      short loc_18005C521
0x18005c4c8  lea     r8, [rsp+258h+Name]; lpName
0x18005c4cd  xor     edx, edx; bInitialOwner
0x18005c4cf  xor     ecx, ecx; lpMutexAttributes
0x18005c4d1  call    cs:__imp_CreateMutexW
0x18005c4d7  mov     [rbx], rax
0x18005c4da  test    rax, rax
0x18005c4dd  jz      short loc_18005C50F
0x18005c4df  mov     edx, 0EA60h; dwMilliseconds
0x18005c4e4  mov     rcx, rax; hHandle
0x18005c4e7  call    cs:__imp_WaitForSingleObject
0x18005c4ed  test    eax, eax
0x18005c4ef  jz      short loc_18005C50B
0x18005c4f1  cmp     eax, 102h
0x18005c4f6  jz      short loc_18005C504
0x18005c4f8  cmp     eax, 0FFFFFFFFh
0x18005c4fb  jz      short loc_18005C50F
0x18005c4fd  mov     eax, 80004005h
0x18005c502  jmp     short loc_18005C521
0x18005c504  mov     eax, 800700AAh
0x18005c509  jmp     short loc_18005C521
0x18005c50b  xor     eax, eax
0x18005c50d  jmp     short loc_18005C521
0x18005c50f  call    cs:__imp_GetLastError
0x18005c515  test    eax, eax
0x18005c517  jle     short loc_18005C521
0x18005c519  movzx   eax, ax
0x18005c51c  or      eax, 80070000h
0x18005c521  mov     rcx, [rsp+258h+var_18]
0x18005c529  xor     rcx, rsp; StackCookie
0x18005c52c  call    __security_check_cookie
0x18005c531  add     rsp, 250h
0x18005c538  pop     rbx
0x18005c539  retn
```
