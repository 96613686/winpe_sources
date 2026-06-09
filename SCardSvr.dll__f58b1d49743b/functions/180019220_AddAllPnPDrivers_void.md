# AddAllPnPDrivers(void)

- ea: `0x180019220`
- end: `0x180019436`
- name: `?AddAllPnPDrivers@@YAXXZ`
- size: `534`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011410`

## callees

- `0x1800022b0`
- `0x180019220`
- `0x18002a150`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001933c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001933c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001932b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001932b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001926c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001937a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001926c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001937a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193ef`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001925d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001925d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800193e1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800193e1`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800192ae`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800192ae`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019419`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019419`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800192f3`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180019370`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800192f3`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180019370`

## pseudocode

```c
void AddAllPnPDrivers(void)
{
  __int64 DeviceInfoList; // rax
  __int64 v1; // rsi
  DWORD LastError; // eax
  const unsigned __int8 *v3; // rcx
  DWORD v4; // eax
  const unsigned __int8 *v5; // rcx
  unsigned int v6; // ebp
  __int64 i; // r9
  DWORD v8; // eax
  const unsigned __int8 *v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  DWORD v15; // eax
  const unsigned __int8 *v16; // rcx
  HANDLE v17; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v19[2]; // [rsp+38h] [rbp-50h] BYREF

  LODWORD(dwBytes) = 0;
  memset(v19, 0, sizeof(v19));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v1 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    CalaisError(v3, 0x263u, LastError, 0, 0, 0);
    return;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_SMARTCARD_READER, 0, 18, 0, 0) )
  {
    v4 = GetLastError();
    goto LABEL_19;
  }
  LODWORD(v19[0]) = 32;
  v6 = 0;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v1, 0, &GUID_DEVINTERFACE_SMARTCARD_READER, i, v19); i = v6 )
  {
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v1, v19, 0, 0, &dwBytes, 0) )
    {
      v8 = GetLastError();
      if ( v8 != 122 )
      {
        v10 = v8;
LABEL_9:
        CalaisError(v9, 0x263u, v10, 0, 0, 0);
        goto LABEL_16;
      }
    }
    v11 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v13 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v11);
    v14 = v13;
    if ( !v13 )
    {
      v10 = 14;
      goto LABEL_9;
    }
    *(_DWORD *)v13 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v1, v19, v13, (unsigned int)dwBytes, 0, 0) )
    {
      CalaisAsyncAddReader((unsigned int (*)(const unsigned __int16 *, unsigned int))AddReaderDriver, v14 + 2, 1u);
    }
    else
    {
      v15 = GetLastError();
      CalaisError(v16, 0x263u, v15, 0, 0, 0);
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
LABEL_16:
    ++v6;
  }
  v4 = GetLastError();
  if ( v4 != 259 )
LABEL_19:
    CalaisError(v5, 0x263u, v4, 0, 0, 0);
  DevObjDestroyDeviceInfoList(v1);
}

```

## disassembly

```asm
0x180019220  push    rbx
0x180019222  push    rbp
0x180019223  push    rsi
0x180019224  push    r14
0x180019226  sub     rsp, 68h
0x18001922a  mov     rax, cs:__security_cookie
0x180019231  xor     rax, rsp
0x180019234  mov     [rsp+88h+var_30], rax
0x180019239  xorps   xmm0, xmm0
0x18001923c  xor     r14d, r14d
0x18001923f  xor     r9d, r9d
0x180019242  mov     dword ptr [rsp+88h+dwBytes], r14d
0x180019247  xor     r8d, r8d
0x18001924a  mov     [rsp+88h+var_68], r14
0x18001924f  xor     edx, edx
0x180019251  xor     ecx, ecx
0x180019253  movups  [rsp+88h+var_50], xmm0
0x180019258  movups  [rsp+88h+var_40], xmm0
0x18001925d  call    cs:__imp_DevObjCreateDeviceInfoList
0x180019263  mov     rsi, rax
0x180019266  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001926a  jnz     short loc_180019291
0x18001926c  call    cs:__imp_GetLastError
0x180019272  mov     [rsp+88h+var_60], r14; unsigned __int16 *
0x180019277  xor     r9d, r9d; unsigned __int16 *
0x18001927a  mov     r8d, eax; unsigned int
0x18001927d  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x180019282  mov     edx, 263h; unsigned int
0x180019287  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001928c  jmp     loc_18001941F
0x180019291  mov     [rsp+88h+var_60], r14
0x180019296  lea     rdx, GUID_DEVINTERFACE_SMARTCARD_READER
0x18001929d  mov     r9d, 12h
0x1800192a3  mov     [rsp+88h+var_68], r14
0x1800192a8  xor     r8d, r8d
0x1800192ab  mov     rcx, rsi
0x1800192ae  call    cs:__imp_DevObjGetClassDevs
0x1800192b4  test    eax, eax
0x1800192b6  jnz     short loc_1800192C3
0x1800192b8  call    cs:__imp_GetLastError
0x1800192be  jmp     loc_1800193FC
0x1800192c3  mov     dword ptr [rsp+88h+var_50], 20h ; ' '
0x1800192cb  mov     ebp, r14d
0x1800192ce  xor     r9d, r9d
0x1800192d1  jmp     loc_1800193CB
0x1800192d6  lea     rax, [rsp+88h+dwBytes]
0x1800192db  mov     [rsp+88h+var_60], r14
0x1800192e0  xor     r9d, r9d
0x1800192e3  mov     [rsp+88h+var_68], rax
0x1800192e8  xor     r8d, r8d
0x1800192eb  lea     rdx, [rsp+88h+var_50]
0x1800192f0  mov     rcx, rsi
0x1800192f3  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800192f9  test    eax, eax
0x1800192fb  jnz     short loc_180019327
0x1800192fd  call    cs:__imp_GetLastError
0x180019303  cmp     eax, 7Ah ; 'z'
0x180019306  jz      short loc_180019327
0x180019308  mov     [rsp+88h+var_60], r14; unsigned __int16 *
0x18001930d  mov     r8d, eax; unsigned int
0x180019310  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x180019315  mov     edx, 263h; unsigned int
0x18001931a  xor     r9d, r9d; unsigned __int16 *
0x18001931d  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180019322  jmp     loc_1800193C6
0x180019327  mov     ebx, dword ptr [rsp+88h+dwBytes]
0x18001932b  call    cs:__imp_GetProcessHeap
0x180019331  mov     r8d, ebx; dwBytes
0x180019334  mov     edx, 8; dwFlags
0x180019339  mov     rcx, rax; hHeap
0x18001933c  call    cs:__imp_HeapAlloc
0x180019342  mov     [rsp+88h+var_60], r14
0x180019347  mov     rbx, rax
0x18001934a  mov     [rsp+88h+var_68], r14
0x18001934f  test    rax, rax
0x180019352  jnz     short loc_18001935A
0x180019354  lea     r8d, [rax+0Eh]
0x180019358  jmp     short loc_180019315
0x18001935a  mov     dword ptr [rax], 8
0x180019360  lea     rdx, [rsp+88h+var_50]
0x180019365  mov     r9d, dword ptr [rsp+88h+dwBytes]
0x18001936a  mov     r8, rbx
0x18001936d  mov     rcx, rsi
0x180019370  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180019376  test    eax, eax
0x180019378  jnz     short loc_18001939C
0x18001937a  call    cs:__imp_GetLastError
0x180019380  mov     [rsp+88h+var_60], r14; unsigned __int16 *
0x180019385  xor     r9d, r9d; unsigned __int16 *
0x180019388  mov     r8d, eax; unsigned int
0x18001938b  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x180019390  mov     edx, 263h; unsigned int
0x180019395  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001939a  jmp     short loc_1800193B2
0x18001939c  lea     rdx, [rbx+4]; unsigned __int16 *
0x1800193a0  mov     r8d, 1; unsigned int
0x1800193a6  lea     rcx, ?AddReaderDriver@@YAKPEBGK@Z; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x1800193ad  call    ?CalaisAsyncAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAsyncAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x1800193b2  call    cs:__imp_GetProcessHeap
0x1800193b8  mov     r8, rbx; lpMem
0x1800193bb  xor     edx, edx; dwFlags
0x1800193bd  mov     rcx, rax; hHeap
0x1800193c0  call    cs:__imp_HeapFree
0x1800193c6  inc     ebp
0x1800193c8  mov     r9d, ebp
0x1800193cb  lea     rax, [rsp+88h+var_50]
0x1800193d0  xor     edx, edx
0x1800193d2  lea     r8, GUID_DEVINTERFACE_SMARTCARD_READER
0x1800193d9  mov     [rsp+88h+var_68], rax
0x1800193de  mov     rcx, rsi
0x1800193e1  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800193e7  test    eax, eax
0x1800193e9  jnz     loc_1800192D6
0x1800193ef  call    cs:__imp_GetLastError
0x1800193f5  cmp     eax, 103h
0x1800193fa  jz      short loc_180019416
0x1800193fc  mov     [rsp+88h+var_60], r14; unsigned __int16 *
0x180019401  xor     r9d, r9d; unsigned __int16 *
0x180019404  mov     r8d, eax; unsigned int
0x180019407  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x18001940c  mov     edx, 263h; unsigned int
0x180019411  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180019416  mov     rcx, rsi
0x180019419  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001941f  mov     rcx, [rsp+88h+var_30]
0x180019424  xor     rcx, rsp; StackCookie
0x180019427  call    __security_check_cookie
0x18001942c  add     rsp, 68h
0x180019430  pop     r14
0x180019432  pop     rsi
0x180019433  pop     rbp
0x180019434  pop     rbx
0x180019435  retn
```
