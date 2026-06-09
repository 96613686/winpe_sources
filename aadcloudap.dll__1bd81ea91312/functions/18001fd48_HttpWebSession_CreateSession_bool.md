# HttpWebSession::CreateSession(bool)

- ea: `0x18001fd48`
- end: `0x18001fe34`
- name: `?CreateSession@HttpWebSession@@AEAAJ_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(HttpWebSession *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052c98`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18001fd48`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fda7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fda7`
- `WINHTTP!WinHttpOpen` at `0x18001fd99`
- `WINHTTP!WinHttpOpen` at `0x18001fd99`

## string_xrefs

- `0x18001fd65`: `HttpWebSession::CreateSession`
- `0x18001fd92`: `Windows-AzureAD-Authentication-Provider/1.0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HttpWebSession::CreateSession(HttpWebSession *this)
{
  HINTERNET v1; // rbx
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 dwFlags; // [rsp+20h] [rbp-68h]
  const char *v6[7]; // [rsp+50h] [rbp-38h] BYREF
  signed int v7; // [rsp+98h] [rbp+10h] BYREF

  v7 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v6,
    (int)"httpwebsession.cpp",
    (int)"HttpWebSession::CreateSession",
    (int)&v7);
  v1 = WinHttpOpen(L"Windows-AzureAD-Authentication-Provider/1.0", 4u, 0, 0, 0);
  if ( v1 )
    goto LABEL_6;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v7 = LastError;
  if ( LastError >= 0 )
  {
LABEL_6:
    _InterlockedCompareExchange64((volatile signed __int64 *)&hSession, (signed __int64)v1, 0);
  }
  else
  {
    LODWORD(dwFlags) = LastError;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, dwFlags, "httpwebsession.cpp", 90, "HRESULT", &base);
  }
  v3 = v7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v6);
  return v3;
}

```

## disassembly

```asm
0x18001fd48  mov     rax, rsp
0x18001fd4b  mov     [rax+8], rbx
0x18001fd4f  mov     [rax+10h], dl
0x18001fd52  push    rdi
0x18001fd53  sub     rsp, 80h
0x18001fd5a  mov     dword ptr [rax+10h], 0
0x18001fd61  lea     r9, [rax+10h]
0x18001fd65  lea     r8, aHttpwebsession_0; "HttpWebSession::CreateSession"
0x18001fd6c  lea     rdi, aOnecoreuapDsEx_42+21h; "httpwebsession.cpp"
0x18001fd73  mov     rdx, rdi
0x18001fd76  lea     rcx, [rax-38h]
0x18001fd7a  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18001fd7f  nop
0x18001fd80  mov     dword ptr [rsp+88h+dwFlags], 0; dwFlags
0x18001fd88  xor     r9d, r9d; pszProxyBypassW
0x18001fd8b  xor     r8d, r8d; pszProxyW
0x18001fd8e  lea     edx, [r9+4]; dwAccessType
0x18001fd92  lea     rcx, pszAgentW; "Windows-AzureAD-Authentication-Provider"...
0x18001fd99  call    cs:__imp_WinHttpOpen
0x18001fd9f  mov     rbx, rax
0x18001fda2  test    rax, rax
0x18001fda5  jnz     short loc_18001FE05
0x18001fda7  call    cs:__imp_GetLastError
0x18001fdad  test    eax, eax
0x18001fdaf  jle     short loc_18001FDB9
0x18001fdb1  movzx   eax, ax
0x18001fdb4  or      eax, 80070000h
0x18001fdb9  mov     [rsp+88h+arg_8], eax
0x18001fdc0  test    eax, eax
0x18001fdc2  jns     short loc_18001FE05
0x18001fdc4  lea     rcx, base
0x18001fdcb  mov     [rsp+88h+var_48], rcx
0x18001fdd0  lea     rcx, aHresult; "HRESULT"
0x18001fdd7  mov     [rsp+88h+var_50], rcx
0x18001fddc  mov     [rsp+88h+var_58], 5Ah ; 'Z'
0x18001fde4  mov     [rsp+88h+var_60], rdi
0x18001fde9  mov     dword ptr [rsp+88h+dwFlags], eax
0x18001fded  mov     ecx, 2
0x18001fdf2  mov     r9d, ecx
0x18001fdf5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18001fdfc  xor     edx, edx
0x18001fdfe  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18001fe03  jmp     short loc_18001FE10
0x18001fe05  xor     eax, eax
0x18001fe07  lock cmpxchg cs:hSession, rbx
0x18001fe10  mov     ebx, [rsp+88h+arg_8]
0x18001fe17  lea     rcx, [rsp+88h+var_38]
0x18001fe1c  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18001fe21  mov     eax, ebx
0x18001fe23  mov     rbx, [rsp+88h+arg_0]
0x18001fe2b  add     rsp, 80h
0x18001fe32  pop     rdi
0x18001fe33  retn
```
