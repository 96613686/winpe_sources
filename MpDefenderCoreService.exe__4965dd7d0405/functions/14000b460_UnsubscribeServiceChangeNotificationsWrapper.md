# UnsubscribeServiceChangeNotificationsWrapper

- ea: `0x14000b460`
- end: `0x14000b534`
- name: `UnsubscribeServiceChangeNotificationsWrapper`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400f60dc`

## callees

- `0x14000b460`
- `0x14000dc50`
- `0x14003a3c0`
- `0x14003a430`
- `0x140166250`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000b4f1`
- `KERNEL32!FreeLibrary` at `0x14000b4f1`
- `KERNEL32!GetProcAddress` at `0x14000b526`
- `KERNEL32!GetProcAddress` at `0x14000b526`

## string_xrefs

- `0x14000b4fe`: `SecHost.dll`
- `0x14000b51f`: `UnsubscribeServiceChangeNotifications`

## pseudocode

```c
__int64 __fastcall UnsubscribeServiceChangeNotificationsWrapper(__int64 a1)
{
  __int64 (__fastcall *v3)(_QWORD, _QWORD); // rdx
  const wchar_t *v4; // r8
  FARPROC ProcAddress; // rbx

  if ( dword_1401E3BB8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1401E3BB8);
    if ( dword_1401E3BB8 == -1 )
    {
      ProcAddress = 0;
      if ( hLibModule )
      {
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
      if ( (int)CommonUtil::UtilLoadSystemLibrary((CommonUtil *)&hLibModule, (HINSTANCE *)L"SecHost.dll", v4) >= 0 )
        ProcAddress = GetProcAddress(hLibModule, "UnsubscribeServiceChangeNotifications");
      v3 = Microsoft::Applications::Events::NullLogManager::SetLevelFilter;
      if ( ProcAddress )
        v3 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
      qword_1401E3BB0 = (__int64)v3;
      Init_thread_footer(&dword_1401E3BB8);
    }
  }
  return ((__int64 (__fastcall *)(__int64))qword_1401E3BB0)(a1);
}

```

## disassembly

```asm
0x14000b460  mov     [rsp+arg_0], rbx
0x14000b465  push    rdi
0x14000b466  sub     rsp, 20h
0x14000b46a  mov     edx, cs:_tls_index
0x14000b470  mov     rdi, rcx
0x14000b473  mov     rax, gs:58h
0x14000b47c  mov     ecx, 4
0x14000b481  mov     rax, [rax+rdx*8]
0x14000b485  mov     eax, [rcx+rax]
0x14000b488  cmp     cs:dword_1401E3BB8, eax
0x14000b48e  jg      short loc_14000B4CE
0x14000b490  mov     rax, cs:qword_1401E3BB0
0x14000b497  mov     rcx, rdi
0x14000b49a  mov     rbx, [rsp+28h+arg_0]
0x14000b49f  add     rsp, 20h
0x14000b4a3  pop     rdi
0x14000b4a4  jmp     cs:__guard_dispatch_icall_fptr
0x14000b4ab  test    rbx, rbx
0x14000b4ae  lea     rdx, ?SetLevelFilter@NullLogManager@Events@Applications@Microsoft@@UEAAXEAEBV?$set@EU?$less@E@std@@V?$allocator@E@2@@std@@@Z; Microsoft::Applications::Events::NullLogManager::SetLevelFilter(uchar,std::set<uchar> const &)
0x14000b4b5  lea     rcx, dword_1401E3BB8
0x14000b4bc  cmovnz  rdx, rbx
0x14000b4c0  mov     cs:qword_1401E3BB0, rdx
0x14000b4c7  call    _Init_thread_footer
0x14000b4cc  jmp     short loc_14000B490
0x14000b4ce  lea     rcx, dword_1401E3BB8
0x14000b4d5  call    _Init_thread_header
0x14000b4da  cmp     cs:dword_1401E3BB8, 0FFFFFFFFh
0x14000b4e1  jnz     short loc_14000B490
0x14000b4e3  mov     rcx, cs:hLibModule; hLibModule
0x14000b4ea  xor     ebx, ebx
0x14000b4ec  test    rcx, rcx
0x14000b4ef  jz      short loc_14000B4FE
0x14000b4f1  call    cs:__imp_FreeLibrary
0x14000b4f7  mov     cs:hLibModule, rbx
0x14000b4fe  lea     rdx, aSechostDll; "SecHost.dll"
0x14000b505  lea     rcx, hLibModule; this
0x14000b50c  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)
0x14000b511  shr     eax, 1Fh
0x14000b514  test    al, al
0x14000b516  jnz     short loc_14000B4AB
0x14000b518  mov     rcx, cs:hLibModule; hModule
0x14000b51f  lea     rdx, aUnsubscribeser; "UnsubscribeServiceChangeNotifications"
0x14000b526  call    cs:__imp_GetProcAddress
0x14000b52c  mov     rbx, rax
0x14000b52f  jmp     loc_14000B4AB
```
