# StandardCollectorService::DestroySession(_GUID const &)

- ea: `0x180033f50`
- end: `0x18003406b`
- name: `?DestroySession@StandardCollectorService@@UEAAJAEBU_GUID@@@Z`
- size: `283`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180033f50`
- `0x180034078`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180033ff5`
- `KERNEL32!WaitForSingleObject` at `0x180033ff5`
- `KERNEL32!CloseHandle` at `0x180034024`
- `KERNEL32!CloseHandle` at `0x180034024`
- `KERNEL32!GetLastError` at `0x180033fff`
- `KERNEL32!GetLastError` at `0x180033fff`
- `ole32!StringFromGUID2` at `0x180033fb1`
- `ole32!StringFromGUID2` at `0x180033fb1`

## string_xrefs

- `0x180033fd8`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StandardCollectorService::DestroySession(RTL_SRWLOCK *this, struct _GUID *a2)
{
  int v3; // ebx
  DiagHubCommon::LogStream *v4; // rbx
  signed int LastError; // eax
  int pExceptionObject; // [rsp+20h] [rbp-108h] BYREF
  OLECHAR sz[112]; // [rsp+30h] [rbp-F8h] BYREF
  HANDLE hHandle; // [rsp+110h] [rbp-18h] BYREF

  hHandle = 0;
  v3 = StandardCollectorService::RequestDestroySession(this, a2, &hHandle);
  if ( v3 >= 0 )
  {
    v4 = _logger;
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
    {
      _mm_lfence();
      if ( !StringFromGUID2(a2, sz, 39) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      sz[39] = 0;
      sz[78] = 0;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)v4 + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Waiting for session '%s' to be destroyed",
        sz);
    }
    if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
    else
    {
      v3 = 0;
    }
  }
  if ( hHandle )
    CloseHandle(hHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180033f50  mov     r11, rsp
0x180033f53  mov     [r11+18h], rbx
0x180033f57  mov     [r11+20h], rsi
0x180033f5b  push    rdi
0x180033f5c  sub     rsp, 120h
0x180033f63  mov     rax, cs:__security_cookie
0x180033f6a  xor     rax, rsp
0x180033f6d  mov     [rsp+128h+var_10], rax
0x180033f75  mov     rdi, rdx
0x180033f78  xor     esi, esi
0x180033f7a  mov     [r11-18h], rsi
0x180033f7e  lea     r8, [r11-18h]; void **
0x180033f82  call    ?RequestDestroySession@StandardCollectorService@@AEAAJAEBU_GUID@@PEAPEAX@Z; StandardCollectorService::RequestDestroySession(_GUID const &,void * *)
0x180033f87  mov     ebx, eax
0x180033f89  test    eax, eax
0x180033f8b  js      loc_180034017
0x180033f91  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180033f98  mov     rax, [rbx+40h]
0x180033f9c  cmp     [rbx+38h], rax
0x180033fa0  jz      short loc_180033FE8
0x180033fa2  lfence
0x180033fa5  lea     r8d, [rsi+27h]; cchMax
0x180033fa9  lea     rdx, [rsp+128h+sz]; lpsz
0x180033fae  mov     rcx, rdi; rguid
0x180033fb1  call    cs:__imp_StringFromGUID2
0x180033fb7  test    eax, eax
0x180033fb9  jz      loc_180034051
0x180033fbf  mov     [rsp+128h+var_AA], si
0x180033fc4  mov     [rsp+128h+var_5C], si
0x180033fcc  lea     r9, [rsp+128h+sz]
0x180033fd1  lea     r8, aWaitingForSess; "Waiting for session '%s' to be destroye"...
0x180033fd8  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180033fdf  lea     rcx, [rbx+38h]; this
0x180033fe3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180033fe8  or      ebx, 0FFFFFFFFh
0x180033feb  mov     edx, ebx; dwMilliseconds
0x180033fed  mov     rcx, [rsp+128h+hHandle]; hHandle
0x180033ff5  call    cs:__imp_WaitForSingleObject
0x180033ffb  cmp     eax, ebx
0x180033ffd  jnz     short loc_180034015
0x180033fff  call    cs:__imp_GetLastError
0x180034005  movzx   ebx, ax
0x180034008  or      ebx, 80070000h
0x18003400e  test    eax, eax
0x180034010  cmovle  ebx, eax
0x180034013  jmp     short loc_180034017
0x180034015  mov     ebx, esi
0x180034017  mov     rcx, [rsp+128h+hHandle]; hObject
0x18003401f  test    rcx, rcx
0x180034022  jz      short loc_18003402A
0x180034024  call    cs:__imp_CloseHandle
0x18003402a  mov     eax, ebx
0x18003402c  mov     rcx, [rsp+128h+var_10]
0x180034034  xor     rcx, rsp; StackCookie
0x180034037  call    __security_check_cookie
0x18003403c  lea     r11, [rsp+128h+var_8]
0x180034044  mov     rbx, [r11+20h]
0x180034048  mov     rsi, [r11+28h]
0x18003404c  mov     rsp, r11
0x18003404f  pop     rdi
0x180034050  retn
0x180034051  mov     [rsp+128h+pExceptionObject], 8007000Eh
0x180034059  lea     rdx, _TI1J; pThrowInfo
0x180034060  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180034065  call    _CxxThrowException_0
```
