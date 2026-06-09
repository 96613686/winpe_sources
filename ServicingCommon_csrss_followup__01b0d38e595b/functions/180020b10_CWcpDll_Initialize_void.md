# CWcpDll::Initialize(void)

- ea: `0x180020b10`
- end: `0x180020c20`
- name: `?Initialize@CWcpDll@@UEAAJXZ`
- size: `272`
- prototype: `__int64 __fastcall(CWcpDll *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020b10`
- `0x1800211f0`
- `0x18002d2b0`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020b6a`
- `KERNEL32!GetLastError` at `0x180020b6a`
- `KERNEL32!GetEnvironmentVariableW` at `0x180020b5a`
- `KERNEL32!GetEnvironmentVariableW` at `0x180020b5a`
- `ntdll!RtlRaiseStatus` at `0x180020b8f`
- `ntdll!RtlRaiseStatus` at `0x180020b8f`

## string_xrefs

- `0x180020ba5`: `onecore\base\wcp\wcpstub\cwcpdll.cpp`
- `0x180020bb1`: `CWcpDll::Initialize`
- `0x180020b7d`: `wcp.dll`
- `0x180020b53`: `wcp_dll`

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
    goto LABEL_10;
  }
  LastError = GetLastError();
  if ( LastError == 203 )
  {
    v3 = L"wcp.dll";
LABEL_10:
    v5 = (*(__int64 (__fastcall **)(CWcpDll *, WCHAR *))(*(_QWORD *)this + 16LL))(this, v3);
    v6 = 0;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  if ( !LastError )
    RtlRaiseStatus(-1073741595);
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
0x180020b10  push    rbx
0x180020b12  sub     rsp, 270h
0x180020b19  mov     rax, cs:__security_cookie
0x180020b20  xor     rax, rsp
0x180020b23  mov     [rsp+278h+var_18], rax
0x180020b2b  mov     rbx, rcx
0x180020b2e  mov     [rsp+278h+var_238], 0
0x180020b36  lea     rcx, [rsp+278h+Buffer]; void *
0x180020b3b  xor     edx, edx; Val
0x180020b3d  mov     r8d, 208h; Size
0x180020b43  call    memset
0x180020b48  mov     r8d, 104h; nSize
0x180020b4e  lea     rdx, [rsp+278h+Buffer]; lpBuffer
0x180020b53  lea     rcx, Name; "wcp_dll"
0x180020b5a  call    cs:__imp_GetEnvironmentVariableW
0x180020b61  nop     dword ptr [rax+rax+00h]
0x180020b66  test    eax, eax
0x180020b68  jnz     short loc_180020BE9
0x180020b6a  call    cs:__imp_GetLastError
0x180020b71  nop     dword ptr [rax+rax+00h]
0x180020b76  cmp     eax, 0CBh
0x180020b7b  jnz     short loc_180020B86
0x180020b7d  lea     rdx, aWcpDll; "wcp.dll"
0x180020b84  jmp     short loc_180020BEE
0x180020b86  test    eax, eax
0x180020b88  jnz     short loc_180020B9C
0x180020b8a  mov     ecx, 0C00000E5h; Status
0x180020b8f  call    cs:__imp_RtlRaiseStatus
0x180020b96  nop     dword ptr [rax+rax+00h]
0x180020b9b  int     3; Trap to Debugger
0x180020b9c  mov     [rsp+278h+var_248], 36h ; '6'
0x180020ba5  lea     rcx, aOnecoreBaseWcp_17; "onecore\\base\\wcp\\wcpstub\\cwcpdll.cp"...
0x180020bac  mov     [rsp+278h+var_258], rcx
0x180020bb1  lea     rcx, aCwcpdllInitial; "CWcpDll::Initialize"
0x180020bb8  mov     [rsp+278h+var_250], rcx
0x180020bbd  lea     rcx, aDwlasterror; "dwLastError"
0x180020bc4  mov     [rsp+278h+var_240], rcx
0x180020bc9  test    eax, eax
0x180020bcb  jle     short loc_180020BD5
0x180020bcd  movzx   eax, ax
0x180020bd0  or      eax, 80070000h
0x180020bd5  mov     r8d, eax
0x180020bd8  lea     rdx, [rsp+278h+var_258]
0x180020bdd  lea     rcx, [rsp+278h+var_238]
0x180020be2  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180020be7  jmp     short loc_180020C06
0x180020be9  lea     rdx, [rsp+278h+Buffer]
0x180020bee  mov     rax, [rbx]
0x180020bf1  mov     rcx, rbx
0x180020bf4  mov     rax, [rax+10h]
0x180020bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bfd  xor     ecx, ecx
0x180020bff  test    eax, eax
0x180020c01  cmovs   ecx, eax
0x180020c04  mov     eax, ecx
0x180020c06  mov     rcx, [rsp+278h+var_18]
0x180020c0e  xor     rcx, rsp; StackCookie
0x180020c11  call    __security_check_cookie
0x180020c16  add     rsp, 270h
0x180020c1d  pop     rbx
0x180020c1e  retn
```
