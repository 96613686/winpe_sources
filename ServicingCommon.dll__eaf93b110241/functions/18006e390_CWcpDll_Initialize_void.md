# CWcpDll::Initialize(void)

- ea: `0x18006e390`
- end: `0x18006e49d`
- name: `?Initialize@CWcpDll@@UEAAJXZ`
- size: `269`
- prototype: `__int64 __fastcall(CWcpDll *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f604`
- `0x18001fd10`
- `0x1800293a0`
- `0x18006e390`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006e3ea`
- `KERNEL32!GetLastError` at `0x18006e3ea`
- `KERNEL32!GetEnvironmentVariableW` at `0x18006e3da`
- `KERNEL32!GetEnvironmentVariableW` at `0x18006e3da`

## string_xrefs

- `0x18006e3d3`: `wcp_dll`
- `0x18006e417`: `onecore\base\wcp\wcpstub\cwcpdll.cpp`
- `0x18006e3fd`: `wcp.dll`
- `0x18006e423`: `CWcpDll::Initialize`

## pseudocode

```c
__int64 __fastcall CWcpDll::Initialize(CWcpDll *this)
{
  signed int LastError; // eax
  WCHAR *v3; // rdx
  int v5; // eax
  unsigned int v6; // ecx
  _QWORD v7[4]; // [rsp+20h] [rbp-258h] BYREF
  _DWORD v8[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  v8[0] = 0;
  memset(Buffer, 0, 0x208u);
  if ( GetEnvironmentVariableW(L"wcp_dll", Buffer, 0x104u) )
  {
    v3 = Buffer;
    goto LABEL_9;
  }
  LastError = GetLastError();
  if ( LastError == 203 )
  {
    v3 = L"wcp.dll";
LABEL_9:
    v5 = (*(__int64 (__fastcall **)(CWcpDll *, WCHAR *))(*(_QWORD *)this + 16LL))(this, v3);
    v6 = 0;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  if ( !LastError )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18006E49CLL);
  }
  v7[2] = 54;
  v7[0] = "onecore\\base\\wcp\\wcpstub\\cwcpdll.cpp";
  v7[1] = "CWcpDll::Initialize";
  v7[3] = "dwLastError";
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           v8,
           v7,
           (unsigned int)LastError);
}

```

## disassembly

```asm
0x18006e390  push    rbx
0x18006e392  sub     rsp, 270h
0x18006e399  mov     rax, cs:__security_cookie
0x18006e3a0  xor     rax, rsp
0x18006e3a3  mov     [rsp+278h+var_18], rax
0x18006e3ab  mov     rbx, rcx
0x18006e3ae  mov     [rsp+278h+var_238], 0
0x18006e3b6  lea     rcx, [rsp+278h+Buffer]; void *
0x18006e3bb  xor     edx, edx; Val
0x18006e3bd  mov     r8d, 208h; Size
0x18006e3c3  call    memset
0x18006e3c8  mov     r8d, 104h; nSize
0x18006e3ce  lea     rdx, [rsp+278h+Buffer]; lpBuffer
0x18006e3d3  lea     rcx, aWcpDll_0; "wcp_dll"
0x18006e3da  call    cs:__imp_GetEnvironmentVariableW
0x18006e3e1  nop     dword ptr [rax+rax+00h]
0x18006e3e6  test    eax, eax
0x18006e3e8  jnz     short loc_18006E45B
0x18006e3ea  call    cs:__imp_GetLastError
0x18006e3f1  nop     dword ptr [rax+rax+00h]
0x18006e3f6  cmp     eax, 0CBh
0x18006e3fb  jnz     short loc_18006E406
0x18006e3fd  lea     rdx, aWcpDll; "wcp.dll"
0x18006e404  jmp     short loc_18006E460
0x18006e406  test    eax, eax
0x18006e408  jz      loc_18006E492
0x18006e40e  mov     [rsp+278h+var_248], 36h ; '6'
0x18006e417  lea     rcx, aOnecoreBaseWcp_17; "onecore\\base\\wcp\\wcpstub\\cwcpdll.cp"...
0x18006e41e  mov     [rsp+278h+var_258], rcx
0x18006e423  lea     rcx, aCwcpdllInitial; "CWcpDll::Initialize"
0x18006e42a  mov     [rsp+278h+var_250], rcx
0x18006e42f  lea     rcx, aDwlasterror; "dwLastError"
0x18006e436  mov     [rsp+278h+var_240], rcx
0x18006e43b  test    eax, eax
0x18006e43d  jle     short loc_18006E447
0x18006e43f  movzx   eax, ax
0x18006e442  or      eax, 80070000h
0x18006e447  mov     r8d, eax
0x18006e44a  lea     rdx, [rsp+278h+var_258]
0x18006e44f  lea     rcx, [rsp+278h+var_238]
0x18006e454  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006e459  jmp     short loc_18006E478
0x18006e45b  lea     rdx, [rsp+278h+Buffer]
0x18006e460  mov     rax, [rbx]
0x18006e463  mov     rcx, rbx
0x18006e466  mov     rax, [rax+10h]
0x18006e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e46f  xor     ecx, ecx
0x18006e471  test    eax, eax
0x18006e473  cmovs   ecx, eax
0x18006e476  mov     eax, ecx
0x18006e478  mov     rcx, [rsp+278h+var_18]
0x18006e480  xor     rcx, rsp; StackCookie
0x18006e483  call    __security_check_cookie
0x18006e488  add     rsp, 270h
0x18006e48f  pop     rbx
0x18006e490  retn
0x18006e492  mov     ecx, 0C00000E5h; int
0x18006e497  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
