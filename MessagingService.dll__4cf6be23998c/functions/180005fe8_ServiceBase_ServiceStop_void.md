# ServiceBase::ServiceStop(void)

- ea: `0x180005fe8`
- end: `0x18000617f`
- name: `?ServiceStop@ServiceBase@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(ServiceBase *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005d98`
- `0x180006190`

## callees

- `0x180005fe8`
- `0x180006548`
- `0x180006764`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613d`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000614e`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000614e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000610c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000610c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060ee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000611d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000611d`

## pseudocode

```c
void __fastcall ServiceBase::ServiceStop(ServiceBase *this, __int64 a2, __int64 a3)
{
  const wchar_t *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  void *v8; // rcx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v10[16]; // [rsp+58h] [rbp-30h] BYREF
  const wchar_t *v11; // [rsp+68h] [rbp-20h]
  int v12; // [rsp+70h] [rbp-18h]
  int v13; // [rsp+74h] [rbp-14h]

  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 8) != 0 )
  {
    v4 = (const wchar_t *)((char *)this + 8);
    if ( this == (ServiceBase *)-8LL )
    {
      v4 = L"NULL";
      v6 = 10;
    }
    else
    {
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v6 = (unsigned int)(2 * v5 + 2);
    }
    v11 = v4;
    v12 = v6;
    v13 = 0;
    McGenEventWrite_EventWriteTransfer(v6, ServiceBaseServiceShuttingDown, a3, 2, v10);
  }
  if ( *((_DWORD *)this + 31) )
  {
    (*(void (__fastcall **)(ServiceBase *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 33));
    if ( *((_DWORD *)this + 33) )
    {
      v7 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 88LL))(this);
      if ( v7 )
      {
        hKey = 0;
        RegCreateKeyExW(HKEY_CURRENT_USER, v7, 0, 0, 1u, 0x20019u, 0, &hKey, 0);
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        (*(void (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
      }
    }
  }
  v8 = (void *)*((_QWORD *)this + 11);
  if ( v8 )
  {
    if ( !UnregisterWaitEx(v8, 0) && GetLastError() != 997 )
    {
      *((_DWORD *)this + 27) = GetLastError();
      GetLastError();
    }
    *((_QWORD *)this + 11) = 0;
  }
  CoFreeUnusedLibrariesEx(0x7530u, 0);
  ServiceBase::_UpdateStatus(this, 1u);
}

```

## disassembly

```asm
0x180005fe8  mov     [rsp+arg_8], rbx
0x180005fed  push    rdi
0x180005fee  sub     rsp, 80h
0x180005ff5  mov     rax, cs:__security_cookie
0x180005ffc  xor     rax, rsp
0x180005fff  mov     [rsp+88h+var_10], rax
0x180006004  xor     edi, edi
0x180006006  mov     rbx, rcx
0x180006009  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 8
0x180006010  jz      short loc_180006066
0x180006012  lea     rax, [rcx+8]
0x180006016  test    rax, rax
0x180006019  jz      short loc_180006031
0x18000601b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000601f  inc     rcx
0x180006022  cmp     [rax+rcx*2], di
0x180006026  jnz     short loc_18000601F
0x180006028  lea     ecx, ds:2[rcx*2]
0x18000602f  jmp     short loc_18000603D
0x180006031  lea     rax, aNull; "NULL"
0x180006038  mov     ecx, 0Ah
0x18000603d  mov     [rsp+88h+var_20], rax
0x180006042  lea     rdx, ServiceBaseServiceShuttingDown
0x180006049  lea     rax, [rsp+88h+var_30]
0x18000604e  mov     [rsp+88h+var_18], ecx
0x180006052  mov     r9d, 2
0x180006058  mov     qword ptr [rsp+88h+dwOptions], rax
0x18000605d  mov     [rsp+88h+var_14], edi
0x180006061  call    McGenEventWrite_EventWriteTransfer
0x180006066  cmp     [rbx+7Ch], edi
0x180006069  jz      loc_180006112
0x18000606f  mov     rax, [rbx]
0x180006072  mov     rcx, rbx
0x180006075  mov     edx, [rbx+84h]
0x18000607b  mov     rax, [rax+10h]
0x18000607f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006084  cmp     [rbx+84h], edi
0x18000608a  jz      loc_180006112
0x180006090  mov     rax, [rbx]
0x180006093  mov     rcx, rbx
0x180006096  mov     rax, [rax+58h]
0x18000609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609f  test    rax, rax
0x1800060a2  jnz     short loc_1800060B5
0x1800060a4  mov     rax, [rbx]
0x1800060a7  mov     rcx, rbx
0x1800060aa  mov     rax, [rax+40h]
0x1800060ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b3  jmp     short loc_180006112
0x1800060b5  mov     [rsp+88h+lpdwDisposition], rdi; lpdwDisposition
0x1800060ba  lea     rcx, [rsp+88h+hKey]
0x1800060bf  mov     [rsp+88h+phkResult], rcx; phkResult
0x1800060c4  xor     r9d, r9d; lpClass
0x1800060c7  mov     [rsp+88h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800060cc  xor     r8d, r8d; Reserved
0x1800060cf  mov     [rsp+88h+samDesired], 20019h; samDesired
0x1800060d7  mov     rdx, rax; lpSubKey
0x1800060da  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800060e1  mov     [rsp+88h+dwOptions], 1; dwOptions
0x1800060e9  mov     [rsp+88h+hKey], rdi
0x1800060ee  call    cs:__imp_RegCreateKeyExW
0x1800060f4  test    eax, eax
0x1800060f6  jle     short loc_180006102
0x1800060f8  movzx   eax, ax
0x1800060fb  or      eax, 80070000h
0x180006100  test    eax, eax
0x180006102  mov     rcx, [rsp+88h+hKey]; hKey
0x180006107  test    rcx, rcx
0x18000610a  jz      short loc_180006112
0x18000610c  call    cs:__imp_RegCloseKey
0x180006112  mov     rcx, [rbx+58h]; WaitHandle
0x180006116  test    rcx, rcx
0x180006119  jz      short loc_180006147
0x18000611b  xor     edx, edx; CompletionEvent
0x18000611d  call    cs:__imp_UnregisterWaitEx
0x180006123  test    eax, eax
0x180006125  jnz     short loc_180006143
0x180006127  call    cs:__imp_GetLastError
0x18000612d  cmp     eax, 3E5h
0x180006132  jz      short loc_180006143
0x180006134  call    cs:__imp_GetLastError
0x18000613a  mov     [rbx+6Ch], eax
0x18000613d  call    cs:__imp_GetLastError
0x180006143  mov     [rbx+58h], rdi
0x180006147  xor     edx, edx; dwReserved
0x180006149  mov     ecx, 7530h; dwUnloadDelay
0x18000614e  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180006154  mov     edx, 1; unsigned int
0x180006159  mov     rcx, rbx; this
0x18000615c  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x180006161  mov     rcx, [rsp+88h+var_10]
0x180006166  xor     rcx, rsp; StackCookie
0x180006169  call    __security_check_cookie
0x18000616e  mov     rbx, [rsp+88h+arg_8]
0x180006176  add     rsp, 80h
0x18000617d  pop     rdi
0x18000617e  retn
```
