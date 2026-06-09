# CNetworkItemFactory::CNetworkItemFactory(void)

- ea: `0x180002db0`
- end: `0x180002e6b`
- name: `??0CNetworkItemFactory@@QEAA@XZ`
- size: `187`
- prototype: `CNetworkItemFactory *__fastcall(CNetworkItemFactory *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000312c`

## callees

- `0x180002db0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002e33`
- `KERNEL32!GetLastError` at `0x180002e33`
- `KERNEL32!InitializeCriticalSection` at `0x180002dfc`
- `KERNEL32!InitializeCriticalSection` at `0x180002dfc`
- `KERNEL32!CreateEventW` at `0x180002e0e`
- `KERNEL32!CreateEventW` at `0x180002e0e`
- `KERNEL32!CloseHandle` at `0x180002e4d`
- `KERNEL32!CloseHandle` at `0x180002e4d`
- `SHLWAPI!__imp_SHCreateThread` at `0x180002e29`
- `SHLWAPI!__imp_SHCreateThread` at `0x180002e29`

## pseudocode

```c
CNetworkItemFactory *__fastcall CNetworkItemFactory::CNetworkItemFactory(CNetworkItemFactory *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v4; // sf

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CNetworkItemFactory::`vftable';
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 15) = EventW;
  if ( !SHCreateThread(CNetworkItemFactory::s_FDBackgroundCOMParkingThread, EventW, 0x10u, 0) )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
      v4 = 1;
    if ( v4 )
    {
      CloseHandle(*((HANDLE *)this + 15));
      *((_QWORD *)this + 15) = 0;
    }
  }
  _InterlockedIncrement(&g_cRefThisDll);
  return this;
}

```

## disassembly

```asm
0x180002db0  push    rbx
0x180002db2  sub     rsp, 20h
0x180002db6  lea     rax, ??_7CNetworkItemFactory@@6B@; const CNetworkItemFactory::`vftable'
0x180002dbd  mov     dword ptr [rcx+8], 1
0x180002dc4  mov     [rcx], rax
0x180002dc7  mov     rbx, rcx
0x180002dca  mov     qword ptr [rcx+48h], 0
0x180002dd2  mov     qword ptr [rcx+50h], 0
0x180002dda  mov     qword ptr [rcx+58h], 0
0x180002de2  mov     qword ptr [rcx+80h], 0
0x180002ded  mov     qword ptr [rcx+88h], 0
0x180002df8  add     rcx, 10h; lpCriticalSection
0x180002dfc  call    cs:__imp_InitializeCriticalSection
0x180002e02  xor     r9d, r9d; lpName
0x180002e05  xor     r8d, r8d; bInitialState
0x180002e08  xor     ecx, ecx; lpEventAttributes
0x180002e0a  lea     edx, [r9+1]; bManualReset
0x180002e0e  call    cs:__imp_CreateEventW
0x180002e14  xor     r9d, r9d; pfnCallback
0x180002e17  lea     rcx, ?s_FDBackgroundCOMParkingThread@CNetworkItemFactory@@CAKPEAX@Z; pfnThreadProc
0x180002e1e  mov     rdx, rax; pData
0x180002e21  mov     [rbx+78h], rax
0x180002e25  lea     r8d, [r9+10h]; flags
0x180002e29  call    cs:__imp_SHCreateThread
0x180002e2f  test    eax, eax
0x180002e31  jnz     short loc_180002E5B
0x180002e33  call    cs:__imp_GetLastError
0x180002e39  test    eax, eax
0x180002e3b  jle     short loc_180002E47
0x180002e3d  movzx   eax, ax
0x180002e40  or      eax, 80070000h
0x180002e45  test    eax, eax
0x180002e47  jns     short loc_180002E5B
0x180002e49  mov     rcx, [rbx+78h]; hObject
0x180002e4d  call    cs:__imp_CloseHandle
0x180002e53  mov     qword ptr [rbx+78h], 0
0x180002e5b  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180002e62  mov     rax, rbx
0x180002e65  add     rsp, 20h
0x180002e69  pop     rbx
0x180002e6a  retn
```
