# DeviceFinder::RunQuery(_DEV_OBJECT_TYPE,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ulong,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,void *)

- ea: `0x1800109bc`
- end: `0x180010a94`
- name: `?RunQuery@DeviceFinder@@SAJW4_DEV_OBJECT_TYPE@@PEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@KP6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z44@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000977c`

## callees

- `0x1800109bc`
- `0x18002578c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010a53`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a69`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180010a86`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180010a86`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180010a1a`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180010a1a`

## pseudocode

```c
__int64 DeviceFinder::RunQuery(__int64 a1, __int64 a2, DWORD a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7, ...)
{
  int v7; // ebx
  char v8; // al
  signed int LastError; // eax
  DWORD dwindex; // [rsp+80h] [rbp+18h] BYREF
  __int64 v12; // [rsp+88h] [rbp+20h] BYREF
  va_list pHandles; // [rsp+A8h] [rbp+40h] BYREF

  va_start(pHandles, a7);
  dwindex = a3;
  v12 = 0;
  v7 = DevCreateObjectQueryEx(
         1,
         0,
         0,
         0,
         2,
         a2,
         0,
         0,
         DeviceFinderQuery__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___::QueryResultCallback,
         a7,
         &v12);
  if ( v7 >= 0 )
  {
    v8 = IsDispatchMessageWPresent();
    v7 = CoWaitForMultipleHandles(v8 != 0 ? 24 : 8, 0xFFFFFFFF, 1u, (LPHANDLE)pHandles, &dwindex);
    if ( v7 >= 0 )
    {
      if ( dwindex )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    DevCloseObjectQuery(v12);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800109bc  mov     r11, rsp
0x1800109bf  mov     [r11+20h], r9
0x1800109c3  mov     [r11+18h], r8d
0x1800109c7  push    rbx
0x1800109c8  sub     rsp, 60h
0x1800109cc  lea     rax, [r11+20h]
0x1800109d0  mov     qword ptr [r11+20h], 0
0x1800109d8  mov     [r11-18h], rax
0x1800109dc  xor     r9d, r9d
0x1800109df  mov     rax, [rsp+68h+arg_30]
0x1800109e7  xor     r8d, r8d
0x1800109ea  mov     [r11-20h], rax
0x1800109ee  lea     rax, DeviceFinderQuery__lambda_a13cb55ba1c98070f9e9d109b3a1cc12_____QueryResultCallback
0x1800109f5  mov     [r11-28h], rax
0x1800109f9  mov     qword ptr [r11-30h], 0
0x180010a01  mov     [rsp+68h+var_38], 0
0x180010a09  mov     [r11-40h], rdx
0x180010a0d  xor     edx, edx
0x180010a0f  mov     dword ptr [rsp+68h+lpdwindex], 2
0x180010a17  lea     ecx, [rdx+1]
0x180010a1a  call    cs:__imp_DevCreateObjectQueryEx
0x180010a20  mov     ebx, eax
0x180010a22  test    eax, eax
0x180010a24  js      short loc_180010A8C
0x180010a26  call    IsDispatchMessageWPresent
0x180010a2b  neg     al
0x180010a2d  lea     r9, [rsp+68h+pHandles]; pHandles
0x180010a35  lea     rax, [rsp+68h+dwindex]
0x180010a3d  mov     r8d, 1; cHandles
0x180010a43  sbb     ecx, ecx
0x180010a45  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180010a4a  and     ecx, 10h
0x180010a4d  or      edx, 0FFFFFFFFh; dwTimeout
0x180010a50  add     ecx, 8; dwFlags
0x180010a53  call    cs:__imp_CoWaitForMultipleHandles
0x180010a59  mov     ebx, eax
0x180010a5b  test    eax, eax
0x180010a5d  js      short loc_180010A7E
0x180010a5f  cmp     [rsp+68h+dwindex], 0
0x180010a67  jz      short loc_180010A7E
0x180010a69  call    cs:__imp_GetLastError
0x180010a6f  mov     ebx, eax
0x180010a71  test    eax, eax
0x180010a73  jle     short loc_180010A7E
0x180010a75  movzx   ebx, ax
0x180010a78  or      ebx, 80070000h
0x180010a7e  mov     rcx, [rsp+68h+arg_18]
0x180010a86  call    cs:__imp_DevCloseObjectQuery
0x180010a8c  mov     eax, ebx
0x180010a8e  add     rsp, 60h
0x180010a92  pop     rbx
0x180010a93  retn
```
