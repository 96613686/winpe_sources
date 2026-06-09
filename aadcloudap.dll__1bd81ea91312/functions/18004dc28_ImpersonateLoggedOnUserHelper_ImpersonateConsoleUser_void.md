# ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser(void)

- ea: `0x18004dc28`
- end: `0x18004dd4e`
- name: `?ImpersonateConsoleUser@ImpersonateLoggedOnUserHelper@@QEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(ImpersonateLoggedOnUserHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18004dc28`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcdc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd1e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18004dc75`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18004dc75`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18004dcd2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18004dcd2`

## string_xrefs

- `0x18004dc49`: `ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser(ImpersonateLoggedOnUserHelper *this)
{
  ULONG active; // eax
  signed int LastError; // eax
  unsigned int v4; // ebx
  signed int v6; // [rsp+20h] [rbp-68h]
  int v7; // [rsp+30h] [rbp-58h]
  const char *v8[6]; // [rsp+50h] [rbp-38h] BYREF
  int v9; // [rsp+90h] [rbp+8h] BYREF

  v9 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v8,
    (int)"unimpersonatehelper.cpp",
    (int)"ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser",
    (int)&v9);
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  active = WTSGetActiveConsoleSessionId();
  if ( active == -1 )
  {
    LastError = -2147187380;
    v9 = -2147187380;
    v7 = 138;
  }
  else
  {
    if ( WTSQueryUserToken(active, (PHANDLE)this + 1) )
      goto LABEL_9;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = LastError;
    if ( LastError >= 0 )
    {
LABEL_9:
      *(_DWORD *)this = ImpersonateLoggedOnUser(*((HANDLE *)this + 1));
      goto LABEL_10;
    }
    v7 = 143;
  }
  v6 = LastError;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v6, "unimpersonatehelper.cpp", v7, "HRESULT", &base);
LABEL_10:
  v4 = v9;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v8);
  return v4;
}

```

## disassembly

```asm
0x18004dc28  mov     rax, rsp
0x18004dc2b  mov     [rax+10h], rbx
0x18004dc2f  mov     [rax+18h], rbp
0x18004dc33  push    rdi
0x18004dc34  sub     rsp, 80h
0x18004dc3b  mov     rdi, rcx
0x18004dc3e  mov     dword ptr [rax+8], 0
0x18004dc45  lea     r9, [rax+8]
0x18004dc49  lea     r8, aImpersonatelog; "ImpersonateLoggedOnUserHelper::Imperson"...
0x18004dc50  lea     rbp, aOnecoreuapDsEx_27+21h; "unimpersonatehelper.cpp"
0x18004dc57  mov     rdx, rbp
0x18004dc5a  lea     rcx, [rax-38h]
0x18004dc5e  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004dc63  nop
0x18004dc64  mov     dword ptr [rdi], 0
0x18004dc6a  lea     rbx, [rdi+8]
0x18004dc6e  mov     qword ptr [rbx], 0
0x18004dc75  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18004dc7b  cmp     eax, 0FFFFFFFFh
0x18004dc7e  jnz     short loc_18004DCCD
0x18004dc80  mov     eax, 8004854Ch
0x18004dc85  mov     [rsp+88h+arg_0], eax
0x18004dc8c  lea     rcx, base
0x18004dc93  mov     [rsp+88h+var_48], rcx
0x18004dc98  lea     rcx, aHresult; "HRESULT"
0x18004dc9f  mov     [rsp+88h+var_50], rcx
0x18004dca4  mov     [rsp+88h+var_58], 8Ah
0x18004dcac  mov     [rsp+88h+var_60], rbp
0x18004dcb1  mov     [rsp+88h+var_68], eax
0x18004dcb5  mov     ecx, 2
0x18004dcba  mov     r9d, ecx
0x18004dcbd  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004dcc4  xor     edx, edx
0x18004dcc6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004dccb  jmp     short loc_18004DD26
0x18004dccd  mov     rdx, rbx; phToken
0x18004dcd0  mov     ecx, eax; SessionId
0x18004dcd2  call    cs:__imp_WTSQueryUserToken
0x18004dcd8  test    eax, eax
0x18004dcda  jnz     short loc_18004DD1B
0x18004dcdc  call    cs:__imp_GetLastError
0x18004dce2  test    eax, eax
0x18004dce4  jle     short loc_18004DCEE
0x18004dce6  movzx   eax, ax
0x18004dce9  or      eax, 80070000h
0x18004dcee  mov     [rsp+88h+arg_0], eax
0x18004dcf5  test    eax, eax
0x18004dcf7  jns     short loc_18004DD1B
0x18004dcf9  lea     rcx, base
0x18004dd00  mov     [rsp+88h+var_48], rcx
0x18004dd05  lea     rcx, aHresult; "HRESULT"
0x18004dd0c  mov     [rsp+88h+var_50], rcx
0x18004dd11  mov     [rsp+88h+var_58], 8Fh
0x18004dd19  jmp     short loc_18004DCAC
0x18004dd1b  mov     rcx, [rbx]; hToken
0x18004dd1e  call    cs:__imp_ImpersonateLoggedOnUser
0x18004dd24  mov     [rdi], eax
0x18004dd26  mov     ebx, [rsp+88h+arg_0]
0x18004dd2d  lea     rcx, [rsp+88h+var_38]
0x18004dd32  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004dd37  mov     eax, ebx
0x18004dd39  lea     r11, [rsp+88h+var_8]
0x18004dd41  mov     rbx, [r11+18h]
0x18004dd45  mov     rbp, [r11+20h]
0x18004dd49  mov     rsp, r11
0x18004dd4c  pop     rdi
0x18004dd4d  retn
```
