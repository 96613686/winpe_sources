# BrowserActivationManager::ActivateBrowserApplication(ushort const *,IInspectable *,ulong *)

- ea: `0x180085364`
- end: `0x180085401`
- name: `?ActivateBrowserApplication@BrowserActivationManager@@YAJPEBGPEAUIInspectable@@PEAK@Z`
- size: `157`
- prototype: `__int64 __fastcall(BrowserActivationManager *__hidden this, struct IInspectable *, struct IInspectable *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x180057684`
- `0x180085364`
- `0x180085578`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800853e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800853e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800853ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800853ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrowserActivationManager::ActivateBrowserApplication(
        BrowserActivationManager *this,
        struct IInspectable *a2,
        DWORD *a3,
        unsigned int *a4)
{
  int BrowserLaunchCommands; // eax
  unsigned int BrowserProcess; // ebx
  PCWSTR StringRawBuffer; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  BrowserLaunchCommands = GetBrowserLaunchCommands((const unsigned __int16 *)this, a2, &string);
  BrowserProcess = BrowserLaunchCommands;
  if ( BrowserLaunchCommands >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    BrowserProcess = CreateBrowserProcess((__int64)this, (__int64)StringRawBuffer, a3);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
      (const char *)(unsigned int)BrowserLaunchCommands,
      v11);
  }
  WindowsDeleteString(string);
  return BrowserProcess;
}

```

## disassembly

```asm
0x180085364  mov     [rsp+arg_0], rbx
0x180085369  mov     [rsp+arg_8], rsi
0x18008536e  push    rdi; int
0x18008536f  sub     rsp, 20h
0x180085373  mov     rsi, r8
0x180085376  mov     rbx, rdx
0x180085379  mov     rdi, rcx
0x18008537c  mov     [rsp+28h+string], 0
0x180085385  xor     ecx, ecx; string
0x180085387  call    cs:__imp_WindowsDeleteString
0x18008538d  mov     [rsp+28h+string], 0
0x180085396  lea     r8, [rsp+28h+string]; HSTRING *
0x18008539b  mov     rdx, rbx; struct IInspectable *
0x18008539e  mov     rcx, rdi; unsigned __int16 *
0x1800853a1  call    ?GetBrowserLaunchCommands@@YAJPEBGPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; GetBrowserLaunchCommands(ushort const *,IInspectable *,HSTRING__ * *)
0x1800853a6  mov     ebx, eax
0x1800853a8  test    eax, eax
0x1800853aa  jns     short loc_1800853C7
0x1800853ac  mov     rcx, [rsp+28h]; this
0x1800853b1  mov     r9d, eax; char *
0x1800853b4  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800853bb  mov     edx, 112h; void *
0x1800853c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800853c5  jmp     short loc_1800853E4
0x1800853c7  xor     edx, edx; length
0x1800853c9  mov     rcx, [rsp+28h+string]; string
0x1800853ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800853d4  mov     r8, rsi
0x1800853d7  mov     rdx, rax
0x1800853da  mov     rcx, rdi
0x1800853dd  call    CreateBrowserProcess
0x1800853e2  mov     ebx, eax
0x1800853e4  mov     rcx, [rsp+28h+string]; string
0x1800853e9  call    cs:__imp_WindowsDeleteString
0x1800853ef  mov     eax, ebx
0x1800853f1  mov     rbx, [rsp+28h+arg_0]
0x1800853f6  mov     rsi, [rsp+28h+arg_8]
0x1800853fb  add     rsp, 20h
0x1800853ff  pop     rdi
0x180085400  retn
```
