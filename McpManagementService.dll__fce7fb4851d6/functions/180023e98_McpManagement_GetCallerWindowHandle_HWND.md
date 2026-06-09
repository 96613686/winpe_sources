# McpManagement::GetCallerWindowHandle(HWND__ * *)

- ea: `0x180023e98`
- end: `0x180023f15`
- name: `?GetCallerWindowHandle@McpManagement@@YAJPEAPEAUHWND__@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(McpManagement *__hidden this, HWND *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180022580`
- `0x180022e80`
- `0x180024ca0`

## callees

- `0x180019c08`
- `0x18001b0e8`
- `0x180023e98`
- `0x1800274b8`
- `0x180027804`

## string_xrefs

- `0x180023ee2`: `Failed to get core window handle for calling thread`
- `0x180023eab`: `Could not find active window. Trying core window handle for calling thread...`

## pseudocode

```c
__int64 __fastcall McpManagement::GetCallerWindowHandle(McpManagement *this, HWND *a2)
{
  unsigned int ActiveWindowForCallingThread; // eax
  HWND *v4; // rdx
  const char *v5; // r9
  int CoreWindowHandleForCallingThread; // ebx
  __int64 result; // rax
  const char *v8; // [rsp+28h] [rbp-10h]
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    ActiveWindowForCallingThread = CallerIdentity::GetActiveWindowForCallingThread(this, a2);
    if ( wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0x5D,
           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
           (const char *)ActiveWindowForCallingThread,
           (int)"Could not find active window. Trying core window handle for calling thread...",
           v8) >= 0
      || (CoreWindowHandleForCallingThread = CallerIdentity::GetCoreWindowHandleForCallingThread(this, v4),
          CoreWindowHandleForCallingThread >= 0) )
    {
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
        (const char *)(unsigned int)CoreWindowHandleForCallingThread,
        (int)"Failed to get core window handle for calling thread",
        v9);
      result = (unsigned int)CoreWindowHandleForCallingThread;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x65,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180023e98  push    rbx
0x180023e9a  sub     rsp, 30h
0x180023e9e  mov     rbx, rcx
0x180023ea1  call    ?GetActiveWindowForCallingThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetActiveWindowForCallingThread(HWND__ * *)
0x180023ea6  mov     rcx, [rsp+38h]; this
0x180023eab  lea     rdx, aCouldNotFindAc; "Could not find active window. Trying co"...
0x180023eb2  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180023eb7  mov     r9d, eax; char *
0x180023eba  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023ec1  mov     edx, 5Dh ; ']'; void *
0x180023ec6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023ecb  test    eax, eax
0x180023ecd  jns     short loc_180023F06
0x180023ecf  mov     rcx, rbx; this
0x180023ed2  call    ?GetCoreWindowHandleForCallingThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCallingThread(HWND__ * *)
0x180023ed7  mov     ebx, eax
0x180023ed9  test    eax, eax
0x180023edb  jns     short loc_180023F06
0x180023edd  mov     rcx, [rsp+38h]; this
0x180023ee2  lea     rax, aFailedToGetCor; "Failed to get core window handle for ca"...
0x180023ee9  mov     qword ptr [rsp+38h+var_18], rax; int
0x180023eee  mov     r9d, ebx; char *
0x180023ef1  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023ef8  mov     edx, 60h ; '`'; void *
0x180023efd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023f02  mov     eax, ebx
0x180023f04  jmp     short loc_180023F0E
0x180023f06  xor     eax, eax
0x180023f08  jmp     short loc_180023F0E
0x180023f0a  mov     eax, [rsp+38h+arg_8]
0x180023f0e  add     rsp, 30h
0x180023f12  pop     rbx
0x180023f13  retn
```
