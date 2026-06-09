# DeviceFinder::RunQuery(_DEV_OBJECT_TYPE,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ulong,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,void *)

- ea: `0x18005a8f0`
- end: `0x18005a9c8`
- name: `?RunQuery@DeviceFinder@@SAJW4_DEV_OBJECT_TYPE@@PEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@KP6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z44@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017df0`

## callees

- `0x180039cdc`
- `0x18005a8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a99d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a99d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005a987`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005a987`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18005a9ba`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18005a9ba`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18005a94e`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18005a94e`

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
0x18005a8f0  mov     r11, rsp
0x18005a8f3  mov     [r11+20h], r9
0x18005a8f7  mov     [r11+18h], r8d
0x18005a8fb  push    rbx
0x18005a8fc  sub     rsp, 60h
0x18005a900  lea     rax, [r11+20h]
0x18005a904  mov     qword ptr [r11+20h], 0
0x18005a90c  mov     [r11-18h], rax
0x18005a910  xor     r9d, r9d
0x18005a913  mov     rax, [rsp+68h+arg_30]
0x18005a91b  xor     r8d, r8d
0x18005a91e  mov     [r11-20h], rax
0x18005a922  lea     rax, DeviceFinderQuery__lambda_a13cb55ba1c98070f9e9d109b3a1cc12_____QueryResultCallback
0x18005a929  mov     [r11-28h], rax
0x18005a92d  mov     qword ptr [r11-30h], 0
0x18005a935  mov     [rsp+68h+var_38], 0
0x18005a93d  mov     [r11-40h], rdx
0x18005a941  xor     edx, edx
0x18005a943  mov     dword ptr [rsp+68h+lpdwindex], 2
0x18005a94b  lea     ecx, [rdx+1]
0x18005a94e  call    cs:__imp_DevCreateObjectQueryEx
0x18005a954  mov     ebx, eax
0x18005a956  test    eax, eax
0x18005a958  js      short loc_18005A9C0
0x18005a95a  call    IsDispatchMessageWPresent
0x18005a95f  neg     al
0x18005a961  lea     r9, [rsp+68h+pHandles]; pHandles
0x18005a969  lea     rax, [rsp+68h+dwindex]
0x18005a971  mov     r8d, 1; cHandles
0x18005a977  sbb     ecx, ecx
0x18005a979  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x18005a97e  and     ecx, 10h
0x18005a981  or      edx, 0FFFFFFFFh; dwTimeout
0x18005a984  add     ecx, 8; dwFlags
0x18005a987  call    cs:__imp_CoWaitForMultipleHandles
0x18005a98d  mov     ebx, eax
0x18005a98f  test    eax, eax
0x18005a991  js      short loc_18005A9B2
0x18005a993  cmp     [rsp+68h+dwindex], 0
0x18005a99b  jz      short loc_18005A9B2
0x18005a99d  call    cs:__imp_GetLastError
0x18005a9a3  mov     ebx, eax
0x18005a9a5  test    eax, eax
0x18005a9a7  jle     short loc_18005A9B2
0x18005a9a9  movzx   ebx, ax
0x18005a9ac  or      ebx, 80070000h
0x18005a9b2  mov     rcx, [rsp+68h+arg_18]
0x18005a9ba  call    cs:__imp_DevCloseObjectQuery
0x18005a9c0  mov     eax, ebx
0x18005a9c2  add     rsp, 60h
0x18005a9c6  pop     rbx
0x18005a9c7  retn
```
