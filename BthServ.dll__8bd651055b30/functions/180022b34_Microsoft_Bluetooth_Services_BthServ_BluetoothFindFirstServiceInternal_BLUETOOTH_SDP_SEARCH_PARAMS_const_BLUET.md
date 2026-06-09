# Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)

- ea: `0x180022b34`
- end: `0x180022d04`
- name: `?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z`
- size: `464`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800237e8`
- `0x1800248ac`
- `0x180024e1c`
- `0x180025e24`

## callees

- `0x180022b34`
- `0x180022d74`
- `0x180023158`
- `0x180024738`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022b99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022b99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022c1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022cea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022c1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022c71`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180022bba`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180022bba`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022be9`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022be9`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180022c2e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180022c2e`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3)
{
  __int64 FirstService; // r15
  DWORD v7; // ecx
  DWORD v8; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rsi
  __int64 DeviceInfoList; // rax
  void **v12; // r8
  __int64 v13; // rcx
  DWORD LastError; // ebx
  void *v15; // rdx
  Microsoft::Bluetooth::Services::BthServ *v16; // rbp
  HANDLE v17; // rax
  DWORD v18; // eax
  void **v19; // r8
  DWORD v20; // eax
  void *v21; // rdx
  HANDLE v22; // rax
  HANDLE hObject; // [rsp+80h] [rbp+8h] BYREF

  FirstService = 0;
  if ( *(_DWORD *)a1 != 32 || *a2 != 1480 )
  {
    v7 = 1306;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v7 = 87;
LABEL_28:
    SetLastError(v7);
    return FirstService;
  }
  if ( *(_QWORD *)(a1 + 16) )
    return Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(a1, a1, a2, a3);
  v8 = 0;
  hObject = 0;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( v10 )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v10[1] = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v10);
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
      {
        if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                             (Microsoft::Bluetooth::Services::BthServ *)v10,
                             &hObject,
                             v12) )
        {
          v16 = (Microsoft::Bluetooth::Services::BthServ *)v10;
        }
        else
        {
          LastError = GetLastError();
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
            (Microsoft::Bluetooth::Services::BthServ *)v10,
            v15);
          v16 = 0;
          SetLastError(LastError);
        }
      }
      else
      {
        v16 = 0;
        DevObjDestroyDeviceInfoList(v10[1]);
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
      }
      if ( v16 )
      {
        do
        {
          FirstService = Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(v13, a1, a2, a3);
          v18 = GetLastError();
          if ( v18 )
            v8 = v18;
          CloseHandle(hObject);
        }
        while ( !FirstService
             && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v16, &hObject, v19) );
        v20 = GetLastError();
        if ( v20 )
          v8 = v20;
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v16, v21);
        if ( FirstService )
        {
          v7 = 0;
          goto LABEL_28;
        }
      }
    }
  }
  if ( !GetLastError() && v8 )
  {
    v7 = v8;
    goto LABEL_28;
  }
  return FirstService;
}

```

## disassembly

```asm
0x180022b34  push    rbx
0x180022b36  push    rbp
0x180022b37  push    rsi
0x180022b38  push    rdi
0x180022b39  push    r12
0x180022b3b  push    r13
0x180022b3d  push    r14
0x180022b3f  push    r15
0x180022b41  sub     rsp, 38h
0x180022b45  xor     r15d, r15d
0x180022b48  mov     r13d, r8d
0x180022b4b  cmp     dword ptr [rcx], 20h ; ' '
0x180022b4e  mov     r12, rdx
0x180022b51  mov     r14, rcx
0x180022b54  jnz     loc_180022CE5
0x180022b5a  cmp     dword ptr [rdx], 5C8h
0x180022b60  jnz     loc_180022CE5
0x180022b66  cmp     [rcx+8], r15
0x180022b6a  jnz     short loc_180022B75
0x180022b6c  lea     ecx, [r15+57h]
0x180022b70  jmp     loc_180022CEA
0x180022b75  cmp     [rcx+10h], r15
0x180022b79  jnz     loc_180022CD2
0x180022b7f  xor     edi, edi
0x180022b81  mov     [rsp+78h+hObject], rdi
0x180022b89  call    cs:__imp_GetProcessHeap
0x180022b8f  mov     rcx, rax; hHeap
0x180022b92  lea     edx, [rdi+8]; dwFlags
0x180022b95  lea     r8d, [rdi+10h]; dwBytes
0x180022b99  call    cs:__imp_HeapAlloc
0x180022b9f  mov     rsi, rax
0x180022ba2  test    rax, rax
0x180022ba5  jz      loc_180022CC0
0x180022bab  xor     r9d, r9d
0x180022bae  mov     [rsp+78h+var_58], rdi
0x180022bb3  xor     r8d, r8d
0x180022bb6  xor     edx, edx
0x180022bb8  xor     ecx, ecx
0x180022bba  call    cs:__imp_DevObjCreateDeviceInfoList
0x180022bc0  mov     [rsi+8], rax
0x180022bc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022bc8  jz      loc_180022CAC
0x180022bce  mov     [rsp+78h+var_50], rdi
0x180022bd3  lea     r9d, [rdi+12h]
0x180022bd7  xor     r8d, r8d
0x180022bda  mov     [rsp+78h+var_58], rdi
0x180022bdf  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x180022be6  mov     rcx, rax
0x180022be9  call    cs:__imp_DevObjGetClassDevs
0x180022bef  test    eax, eax
0x180022bf1  jz      short loc_180022C28
0x180022bf3  lea     rdx, [rsp+78h+hObject]; void *
0x180022bfb  mov     rcx, rsi; this
0x180022bfe  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180022c03  test    eax, eax
0x180022c05  jnz     short loc_180022C23
0x180022c07  call    cs:__imp_GetLastError
0x180022c0d  mov     rcx, rsi; this
0x180022c10  mov     ebx, eax
0x180022c12  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180022c17  mov     ecx, ebx; dwErrCode
0x180022c19  xor     ebp, ebp
0x180022c1b  call    cs:__imp_SetLastError
0x180022c21  jmp     short loc_180022C48
0x180022c23  mov     rbp, rsi
0x180022c26  jmp     short loc_180022C48
0x180022c28  mov     rcx, [rsi+8]
0x180022c2c  xor     ebp, ebp
0x180022c2e  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180022c34  call    cs:__imp_GetProcessHeap
0x180022c3a  mov     r8, rsi; lpMem
0x180022c3d  xor     edx, edx; dwFlags
0x180022c3f  mov     rcx, rax; hHeap
0x180022c42  call    cs:__imp_HeapFree
0x180022c48  test    rbp, rbp
0x180022c4b  jz      short loc_180022CC0
0x180022c4d  mov     r9d, r13d
0x180022c50  mov     r8, r12
0x180022c53  mov     rdx, r14
0x180022c56  call    ?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180022c5b  mov     r15, rax
0x180022c5e  call    cs:__imp_GetLastError
0x180022c64  mov     rcx, [rsp+78h+hObject]; hObject
0x180022c6c  test    eax, eax
0x180022c6e  cmovnz  edi, eax
0x180022c71  call    cs:__imp_CloseHandle
0x180022c77  test    r15, r15
0x180022c7a  jnz     short loc_180022C90
0x180022c7c  lea     rdx, [rsp+78h+hObject]; void *
0x180022c84  mov     rcx, rbp; this
0x180022c87  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180022c8c  test    eax, eax
0x180022c8e  jnz     short loc_180022C4D
0x180022c90  call    cs:__imp_GetLastError
0x180022c96  test    eax, eax
0x180022c98  mov     rcx, rbp; this
0x180022c9b  cmovnz  edi, eax
0x180022c9e  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180022ca3  test    r15, r15
0x180022ca6  jz      short loc_180022CC0
0x180022ca8  xor     ecx, ecx
0x180022caa  jmp     short loc_180022CEA
0x180022cac  call    cs:__imp_GetProcessHeap
0x180022cb2  mov     r8, rsi; lpMem
0x180022cb5  xor     edx, edx; dwFlags
0x180022cb7  mov     rcx, rax; hHeap
0x180022cba  call    cs:__imp_HeapFree
0x180022cc0  call    cs:__imp_GetLastError
0x180022cc6  test    eax, eax
0x180022cc8  jnz     short loc_180022CF0
0x180022cca  test    edi, edi
0x180022ccc  jz      short loc_180022CF0
0x180022cce  mov     ecx, edi
0x180022cd0  jmp     short loc_180022CEA
0x180022cd2  mov     r9d, r13d
0x180022cd5  mov     r8, r12
0x180022cd8  mov     rdx, r14
0x180022cdb  call    ?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180022ce0  mov     r15, rax
0x180022ce3  jmp     short loc_180022CF0
0x180022ce5  mov     ecx, 51Ah; dwErrCode
0x180022cea  call    cs:__imp_SetLastError
0x180022cf0  mov     rax, r15
0x180022cf3  add     rsp, 38h
0x180022cf7  pop     r15
0x180022cf9  pop     r14
0x180022cfb  pop     r13
0x180022cfd  pop     r12
0x180022cff  pop     rdi
0x180022d00  pop     rsi
0x180022d01  pop     rbp
0x180022d02  pop     rbx
0x180022d03  retn
```
