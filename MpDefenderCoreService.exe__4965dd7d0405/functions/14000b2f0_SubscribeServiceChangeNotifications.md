# SubscribeServiceChangeNotifications

- ea: `0x14000b2f0`
- end: `0x14000b3fe`
- name: `SubscribeServiceChangeNotifications`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400f60dc`

## callees

- `0x14000b2f0`
- `0x14000dc50`
- `0x14003a3c0`
- `0x14003a430`
- `0x140166250`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000b3bb`
- `KERNEL32!FreeLibrary` at `0x14000b3bb`
- `KERNEL32!GetProcAddress` at `0x14000b3f0`
- `KERNEL32!GetProcAddress` at `0x14000b3f0`

## string_xrefs

- `0x14000b3c8`: `SecHost.dll`
- `0x14000b3e9`: `SubscribeServiceChangeNotifications`

## pseudocode

```c
__int64 __fastcall SubscribeServiceChangeNotifications(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  FARPROC v10; // rdx
  const wchar_t *v11; // r8
  FARPROC ProcAddress; // rbx

  if ( dword_1401E3BA0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1401E3BA0);
    if ( dword_1401E3BA0 == -1 )
    {
      ProcAddress = 0;
      if ( hModule )
      {
        FreeLibrary(hModule);
        hModule = 0;
      }
      if ( (int)CommonUtil::UtilLoadSystemLibrary((CommonUtil *)&hModule, (HINSTANCE *)L"SecHost.dll", v11) >= 0 )
        ProcAddress = GetProcAddress(hModule, "SubscribeServiceChangeNotifications");
      v10 = (FARPROC)&SubscribeServiceChangeNotificationsDownlevel;
      if ( ProcAddress )
        v10 = ProcAddress;
      qword_1401E3B98 = (__int64)v10;
      Init_thread_footer(&dword_1401E3BA0);
    }
  }
  return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, __int64))qword_1401E3B98)(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x14000b2f0  mov     rax, rsp
0x14000b2f3  mov     [rax+8], rbx
0x14000b2f7  mov     [rax+10h], rbp
0x14000b2fb  mov     [rax+18h], rsi
0x14000b2ff  mov     [rax+20h], rdi
0x14000b303  push    r14
0x14000b305  sub     rsp, 30h
0x14000b309  mov     r10d, cs:_tls_index
0x14000b310  mov     r14, rcx
0x14000b313  mov     rax, gs:58h
0x14000b31c  mov     rdi, r9
0x14000b31f  mov     ecx, 4
0x14000b324  mov     rsi, r8
0x14000b327  mov     ebp, edx
0x14000b329  mov     rax, [rax+r10*8]
0x14000b32d  mov     eax, [rcx+rax]
0x14000b330  cmp     cs:dword_1401E3BA0, eax
0x14000b336  jg      short loc_14000B398
0x14000b338  mov     rcx, [rsp+38h+arg_20]
0x14000b33d  mov     r9, rdi
0x14000b340  mov     rax, cs:qword_1401E3B98
0x14000b347  mov     r8, rsi
0x14000b34a  mov     [rsp+38h+var_18], rcx
0x14000b34f  mov     edx, ebp
0x14000b351  mov     rcx, r14
0x14000b354  call    cs:__guard_dispatch_icall_fptr
0x14000b35a  mov     rbx, [rsp+38h+arg_0]
0x14000b35f  mov     rbp, [rsp+38h+arg_8]
0x14000b364  mov     rsi, [rsp+38h+arg_10]
0x14000b369  mov     rdi, [rsp+38h+arg_18]
0x14000b36e  add     rsp, 30h
0x14000b372  pop     r14
0x14000b374  retn
0x14000b375  test    rbx, rbx
0x14000b378  lea     rdx, ?SubscribeServiceChangeNotificationsDownlevel@@YAKPEAUSC_HANDLE__@@W4_SC_EVENT_TYPE@@P6AXKPEAX@Z2PEAPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; SubscribeServiceChangeNotificationsDownlevel(SC_HANDLE__ *,_SC_EVENT_TYPE,void (*)(ulong,void *),void *,_SC_NOTIFICATION_REGISTRATION * *)
0x14000b37f  lea     rcx, dword_1401E3BA0
0x14000b386  cmovnz  rdx, rbx
0x14000b38a  mov     cs:qword_1401E3B98, rdx
0x14000b391  call    _Init_thread_footer
0x14000b396  jmp     short loc_14000B338
0x14000b398  lea     rcx, dword_1401E3BA0
0x14000b39f  call    _Init_thread_header
0x14000b3a4  cmp     cs:dword_1401E3BA0, 0FFFFFFFFh
0x14000b3ab  jnz     short loc_14000B338
0x14000b3ad  mov     rcx, cs:hModule; hLibModule
0x14000b3b4  xor     ebx, ebx
0x14000b3b6  test    rcx, rcx
0x14000b3b9  jz      short loc_14000B3C8
0x14000b3bb  call    cs:__imp_FreeLibrary
0x14000b3c1  mov     cs:hModule, rbx
0x14000b3c8  lea     rdx, aSechostDll; "SecHost.dll"
0x14000b3cf  lea     rcx, hModule; this
0x14000b3d6  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)
0x14000b3db  shr     eax, 1Fh
0x14000b3de  test    al, al
0x14000b3e0  jnz     short loc_14000B375
0x14000b3e2  mov     rcx, cs:hModule; hModule
0x14000b3e9  lea     rdx, ProcName; "SubscribeServiceChangeNotifications"
0x14000b3f0  call    cs:__imp_GetProcAddress
0x14000b3f6  mov     rbx, rax
0x14000b3f9  jmp     loc_14000B375
```
