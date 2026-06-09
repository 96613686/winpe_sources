# ServiceBase::_ServiceMainInner(void)

- ea: `0x180020ab8`
- end: `0x180020c75`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `445`
- prototype: `signed int __fastcall(ServiceBase *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800205e8`

## callees

- `0x18000b654`
- `0x1800207dc`
- `0x180020ab8`
- `0x180020d48`
- `0x180020f2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020aef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b21`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180020c62`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180020c62`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  HANDLE EventW; // rbx
  bool v3; // sf
  __int64 v4; // rcx
  int v5; // ebx
  __int64 *v6; // rdx
  int v7; // eax
  signed int v8; // ecx

  if ( !qword_18002DD10 )
    return -2147467263;
  result = ServiceBase::_CheckServiceShutdownAlready(this);
  if ( result >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW == (HANDLE)xmmword_18002DCB0 )
    {
      EventW = (HANDLE)xmmword_18002DCB0;
    }
    else
    {
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((void **)&xmmword_18002DCB0);
      *(_QWORD *)&xmmword_18002DCB0 = EventW;
    }
    if ( EventW )
      goto LABEL_11;
    result = GetLastError();
    v3 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v3 = result < 0;
    }
    if ( !v3 )
    {
LABEL_11:
      result = ServiceBase::_UpdateStatus((ServiceBase *)&myService, 2u);
      if ( result >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(void *))(myService + 8LL))(&myService);
        if ( v5 < 0 )
        {
          if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
            return v5;
          v6 = ServiceBaseServiceStartingError;
LABEL_15:
          McTemplateU0zq_EventWriteTransfer(v4, v6, &ServiceName, (unsigned int)v5);
          return v5;
        }
        LODWORD(qword_18002DCDC) = 1;
        result = ServiceBase::_UpdateStatus((ServiceBase *)&myService, 4u);
        if ( result >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(void *))(myService + 24LL))(&myService);
          if ( v5 < 0 )
          {
            if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
              return v5;
            v6 = ServiceBaseServiceStartedError;
            goto LABEL_15;
          }
          v7 = (*(__int64 (__fastcall **)(char *, WCHAR *, _QWORD, __int64 (__fastcall *)(), void *, int))(qword_18002DD10 + 192))(
                 (char *)&xmmword_18002DCB0 + 8,
                 &ServiceName,
                 xmmword_18002DCB0,
                 StopCallback,
                 &myService,
                 8);
          v8 = v7;
          if ( v7 > 0 )
            v8 = (unsigned __int16)v7 | 0x80070000;
          if ( v8 >= 0 )
            v8 = 0;
          if ( v8 >= 0 )
          {
            if ( HIDWORD(qword_18002DCDC) )
              (*(void (__fastcall **)(void *, _QWORD))(myService + 32LL))(&myService, (unsigned int)dword_18002DCE4);
            CoFreeUnusedLibrariesEx(0x7530u, 0);
            return 0;
          }
          else
          {
            return v8;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020ab8  mov     [rsp+arg_0], rbx
0x180020abd  push    rdi
0x180020abe  sub     rsp, 40h
0x180020ac2  cmp     cs:qword_18002DD10, 0
0x180020aca  jnz     short loc_180020AD6
0x180020acc  mov     eax, 80004001h
0x180020ad1  jmp     loc_180020C6A
0x180020ad6  call    ?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ; ServiceBase::_CheckServiceShutdownAlready(void)
0x180020adb  test    eax, eax
0x180020add  js      loc_180020C6A
0x180020ae3  xor     r9d, r9d; lpName
0x180020ae6  xor     r8d, r8d; bInitialState
0x180020ae9  xor     ecx, ecx; lpEventAttributes
0x180020aeb  lea     edx, [r9+1]; bManualReset
0x180020aef  call    cs:__imp_CreateEventW
0x180020af5  mov     rbx, rax
0x180020af8  mov     rax, qword ptr cs:xmmword_18002DCB0
0x180020aff  cmp     rbx, rax
0x180020b02  jz      short loc_180020B19
0x180020b04  lea     rcx, xmmword_18002DCB0
0x180020b0b  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180020b10  mov     qword ptr cs:xmmword_18002DCB0, rbx
0x180020b17  jmp     short loc_180020B1C
0x180020b19  mov     rbx, rax
0x180020b1c  test    rbx, rbx
0x180020b1f  jnz     short loc_180020B3B
0x180020b21  call    cs:__imp_GetLastError
0x180020b27  test    eax, eax
0x180020b29  jle     short loc_180020B35
0x180020b2b  movzx   eax, ax
0x180020b2e  or      eax, 80070000h
0x180020b33  test    eax, eax
0x180020b35  js      loc_180020C6A
0x180020b3b  lea     rdi, ?myService@@3VPimIMService@@A; PimIMService myService
0x180020b42  mov     edx, 2; unsigned int
0x180020b47  mov     rcx, rdi; this
0x180020b4a  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x180020b4f  test    eax, eax
0x180020b51  js      loc_180020C6A
0x180020b57  mov     rax, cs:?myService@@3VPimIMService@@A; PimIMService myService
0x180020b5e  mov     rcx, rdi
0x180020b61  mov     rax, [rax+8]
0x180020b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6a  mov     ebx, eax
0x180020b6c  test    eax, eax
0x180020b6e  jns     short loc_180020B96
0x180020b70  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x180020b77  jz      short loc_180020B8F
0x180020b79  lea     rdx, ServiceBaseServiceStartingError
0x180020b80  lea     r8, ServiceName
0x180020b87  mov     r9d, ebx
0x180020b8a  call    McTemplateU0zq_EventWriteTransfer
0x180020b8f  mov     eax, ebx
0x180020b91  jmp     loc_180020C6A
0x180020b96  mov     edx, 4; unsigned int
0x180020b9b  mov     dword ptr cs:qword_18002DCDC, 1
0x180020ba5  mov     rcx, rdi; this
0x180020ba8  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x180020bad  test    eax, eax
0x180020baf  js      loc_180020C6A
0x180020bb5  mov     rax, cs:?myService@@3VPimIMService@@A; PimIMService myService
0x180020bbc  mov     rcx, rdi
0x180020bbf  mov     rax, [rax+18h]
0x180020bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc8  mov     ebx, eax
0x180020bca  test    eax, eax
0x180020bcc  jns     short loc_180020BE0
0x180020bce  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x180020bd5  jz      short loc_180020B8F
0x180020bd7  lea     rdx, ServiceBaseServiceStartedError
0x180020bde  jmp     short loc_180020B80
0x180020be0  mov     rax, cs:qword_18002DD10
0x180020be7  lea     r9, StopCallback
0x180020bee  mov     r8, qword ptr cs:xmmword_18002DCB0
0x180020bf5  lea     rdx, ServiceName
0x180020bfc  mov     [rsp+48h+var_20], 8
0x180020c04  lea     rcx, xmmword_18002DCB0+8
0x180020c0b  mov     [rsp+48h+var_28], rdi
0x180020c10  mov     rax, [rax+0C0h]
0x180020c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c1c  mov     ecx, eax
0x180020c1e  test    eax, eax
0x180020c20  jle     short loc_180020C2B
0x180020c22  movzx   ecx, ax
0x180020c25  or      ecx, 80070000h
0x180020c2b  xor     eax, eax
0x180020c2d  test    ecx, ecx
0x180020c2f  cmovns  ecx, eax
0x180020c32  test    ecx, ecx
0x180020c34  jns     short loc_180020C3A
0x180020c36  mov     eax, ecx
0x180020c38  jmp     short loc_180020C6A
0x180020c3a  cmp     dword ptr cs:qword_18002DCDC+4, eax
0x180020c40  jz      short loc_180020C5B
0x180020c42  mov     rax, cs:?myService@@3VPimIMService@@A; PimIMService myService
0x180020c49  mov     rcx, rdi
0x180020c4c  mov     edx, cs:dword_18002DCE4
0x180020c52  mov     rax, [rax+20h]
0x180020c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c5b  xor     edx, edx; dwReserved
0x180020c5d  mov     ecx, 7530h; dwUnloadDelay
0x180020c62  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180020c68  xor     eax, eax
0x180020c6a  mov     rbx, [rsp+48h+arg_0]
0x180020c6f  add     rsp, 40h
0x180020c73  pop     rdi
0x180020c74  retn
```
