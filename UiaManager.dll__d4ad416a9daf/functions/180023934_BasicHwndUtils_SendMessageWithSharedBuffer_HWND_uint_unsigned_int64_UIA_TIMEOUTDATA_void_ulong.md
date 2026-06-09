# BasicHwndUtils::SendMessageWithSharedBuffer(HWND__ *,uint,unsigned __int64,UIA_TIMEOUTDATA &,void *,ulong)

- ea: `0x180023934`
- end: `0x180023a88`
- name: `?SendMessageWithSharedBuffer@BasicHwndUtils@@SAJPEAUHWND__@@I_KAEAUUIA_TIMEOUTDATA@@PEAXK@Z`
- size: `340`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, struct UIA_TIMEOUTDATA *@<r9>, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180023828`

## callees

- `0x180006edc`
- `0x180023934`
- `0x180023d0c`
- `0x180024f38`
- `0x18007c468`
- `0x180080c98`
- `0x180080d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a39`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180023a2f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180023a2f`

## string_xrefs

- `0x180023984`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800239d5`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800239f8`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023a57`: `onecore\windows\accessibletech\common\sharedblock.cpp`
- `0x180023a45`: `Attempting to use un-Allocated SharedBlock`

## pseudocode

```c
__int64 __fastcall BasicHwndUtils::SendMessageWithSharedBuffer(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        struct UIA_TIMEOUTDATA *a4,
        void *lpBuffer)
{
  int v8; // eax
  unsigned int LastError; // ebx
  LPCVOID v10; // rbx
  int v11; // eax
  const char *v12; // r9
  int v13; // edi
  int lpNumberOfBytesRead; // [rsp+20h] [rbp-30h]
  int lpNumberOfBytesReada; // [rsp+20h] [rbp-30h]
  char *v17; // [rsp+28h] [rbp-28h]
  LPCVOID lpBaseAddress; // [rsp+30h] [rbp-20h] BYREF
  SIZE_T nSize; // [rsp+38h] [rbp-18h]
  HANDLE hProcess; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v22; // [rsp+80h] [rbp+30h] BYREF

  v22 = a3;
  lpBaseAddress = 0;
  LODWORD(nSize) = 4000;
  hProcess = 0;
  v8 = SharedBlock::SharedAlloc((SharedBlock *)&lpBaseAddress, a1);
  LastError = v8;
  if ( v8 >= 0 )
  {
    v10 = lpBaseAddress;
    v22 = 0;
    v11 = BasicHwndUtils::UIASendMessageTimeout(a4, a1, a2, 0x7D0u, (__int64)lpBaseAddress, &v22);
    v13 = v11;
    if ( v11 >= 0 )
    {
      if ( v22 )
      {
        if ( v10 && hProcess )
        {
          if ( !ReadProcessMemory(hProcess, v10, lpBuffer, (unsigned int)nSize, 0) )
            GetLastError();
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x47,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\sharedblock.cpp",
            (const char *)0x80004005LL,
            (int)"Attempting to use un-Allocated SharedBlock",
            v17);
        }
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x357,
                      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
                      v12);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x356,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        (const char *)(unsigned int)v11,
        lpNumberOfBytesReada);
      LastError = v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
      (const char *)(unsigned int)v8,
      lpNumberOfBytesRead);
  }
  SharedBlock::SharedFree((SharedBlock *)&lpBaseAddress);
  return LastError;
}

```

## disassembly

```asm
0x180023934  mov     [rsp-18h+arg_0], rbx
0x180023939  mov     [rsp-18h+arg_8], rsi
0x18002393e  mov     [rsp-18h+arg_10], r8
0x180023943  push    rbp
0x180023944  push    rdi
0x180023945  push    r14
0x180023947  mov     rbp, rsp
0x18002394a  sub     rsp, 50h
0x18002394e  mov     r14d, edx
0x180023951  mov     [rbp+lpBaseAddress], 0
0x180023959  mov     rdx, rcx; HWND
0x18002395c  mov     dword ptr [rbp+nSize], 0FA0h
0x180023963  mov     rdi, rcx
0x180023966  mov     [rbp+hProcess], 0
0x18002396e  lea     rcx, [rbp+lpBaseAddress]; this
0x180023972  mov     rsi, r9
0x180023975  call    ?SharedAlloc@SharedBlock@@QEAAJPEAUHWND__@@@Z; SharedBlock::SharedAlloc(HWND__ *)
0x18002397a  mov     ebx, eax
0x18002397c  test    eax, eax
0x18002397e  jns     short loc_18002399D
0x180023980  mov     rcx, [rbp+18h]; this
0x180023984  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18002398b  mov     r9d, eax; char *
0x18002398e  mov     edx, 353h; void *
0x180023993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023998  jmp     loc_180023A6A
0x18002399d  mov     rbx, [rbp+lpBaseAddress]
0x1800239a1  lea     rax, [rbp+arg_10]
0x1800239a5  mov     [rsp+50h+var_28], rax; char *
0x1800239aa  mov     r9d, 7D0h; unsigned __int64
0x1800239b0  mov     r8d, r14d; unsigned int
0x1800239b3  mov     [rsp+50h+lpNumberOfBytesRead], rbx; int
0x1800239b8  mov     rdx, rdi; HWND
0x1800239bb  mov     [rbp+arg_10], 0
0x1800239c3  mov     rcx, rsi; struct UIA_TIMEOUTDATA *
0x1800239c6  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800239cb  mov     edi, eax
0x1800239cd  test    eax, eax
0x1800239cf  jns     short loc_1800239ED
0x1800239d1  mov     rcx, [rbp+18h]; this
0x1800239d5  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x1800239dc  mov     r9d, eax; char *
0x1800239df  mov     edx, 356h; void *
0x1800239e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239e9  mov     ebx, edi
0x1800239eb  jmp     short loc_180023A6A
0x1800239ed  cmp     [rbp+arg_10], 0
0x1800239f2  jnz     short loc_180023A0D
0x1800239f4  mov     rcx, [rbp+18h]; this
0x1800239f8  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x1800239ff  mov     edx, 357h; void *
0x180023a04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023a09  mov     ebx, eax
0x180023a0b  jmp     short loc_180023A6A
0x180023a0d  test    rbx, rbx
0x180023a10  jz      short loc_180023A41
0x180023a12  mov     rcx, [rbp+hProcess]; hProcess
0x180023a16  test    rcx, rcx
0x180023a19  jz      short loc_180023A41
0x180023a1b  mov     r9d, dword ptr [rbp+nSize]; nSize
0x180023a1f  mov     rdx, rbx; lpBaseAddress
0x180023a22  mov     r8, [rbp+lpBuffer]; lpBuffer
0x180023a26  mov     [rsp+50h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180023a2f  call    cs:__imp_ReadProcessMemory
0x180023a35  test    eax, eax
0x180023a37  jnz     short loc_180023A68
0x180023a39  call    cs:__imp_GetLastError
0x180023a3f  jmp     short loc_180023A68
0x180023a41  mov     rcx, [rbp+18h]; this
0x180023a45  lea     rax, aAttemptingToUs; "Attempting to use un-Allocated SharedBl"...
0x180023a4c  mov     r9d, 80004005h; char *
0x180023a52  mov     [rsp+50h+lpNumberOfBytesRead], rax; int
0x180023a57  lea     r8, aOnecoreWindows_17; "onecore\\windows\\accessibletech\\commo"...
0x180023a5e  mov     edx, 47h ; 'G'; void *
0x180023a63  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023a68  xor     ebx, ebx
0x180023a6a  lea     rcx, [rbp+lpBaseAddress]; this
0x180023a6e  call    ?SharedFree@SharedBlock@@QEAAXXZ; SharedBlock::SharedFree(void)
0x180023a73  mov     rsi, [rsp+50h+arg_8]
0x180023a78  mov     eax, ebx
0x180023a7a  mov     rbx, [rsp+50h+arg_0]
0x180023a7f  add     rsp, 50h
0x180023a83  pop     r14
0x180023a85  pop     rdi
0x180023a86  pop     rbp
0x180023a87  retn
```
