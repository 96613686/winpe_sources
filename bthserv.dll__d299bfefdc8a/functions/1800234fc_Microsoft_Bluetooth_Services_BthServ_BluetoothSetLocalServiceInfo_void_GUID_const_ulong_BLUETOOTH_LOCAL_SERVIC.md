# Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO const *)

- ea: `0x1800234fc`
- end: `0x1800237e1`
- name: `?BluetoothSetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEBU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z`
- size: `741`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _GUID *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800234fc`
- `0x180028b64`

## callees

- `0x180001790`
- `0x180022d74`
- `0x180023158`
- `0x1800234fc`
- `0x180025bd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023698`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023732`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800237a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023732`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800237a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023740`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800237af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023740`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800237af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023703`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002377c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002377c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023663`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023663`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800236b9`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800236b9`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800236e8`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800236e8`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002372c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002372c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3,
        int *a4)
{
  unsigned int v5; // r12d
  _WORD *v7; // rcx
  __int64 v8; // r10
  __int64 v9; // rdx
  Microsoft::Bluetooth::Services::BthServ *v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  Microsoft::Bluetooth::Services::BthServ *v13; // rcx
  unsigned int v14; // edi
  _WORD *v15; // rcx
  Microsoft::Bluetooth::Services::BthServ *v16; // rax
  bool v17; // zf
  HANDLE ProcessHeap; // rax
  _QWORD *v19; // rsi
  __int64 DeviceInfoList; // rax
  void **v21; // r8
  DWORD LastError; // ebx
  void *v23; // rdx
  Microsoft::Bluetooth::Services::BthServ *v24; // r14
  HANDLE v25; // rax
  int v26; // ebx
  unsigned int v27; // eax
  void *v28; // rdx
  void **v29; // r8
  HANDLE v30; // rax
  const struct _BLUETOOTH_LOCAL_SERVICE_INFO *lpOutBuffer; // [rsp+20h] [rbp-E0h]
  HANDLE hDevice[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+64h] [rbp-9Ch]
  __int64 v37; // [rsp+68h] [rbp-98h]
  char v38; // [rsp+70h] [rbp-90h] BYREF
  char v39; // [rsp+270h] [rbp+170h] BYREF

  v5 = (unsigned int)a3;
  if ( this )
  {
    v7 = a4 + 4;
    v36 = *a4;
    v8 = 2147483646;
    v9 = 256;
    v37 = *((_QWORD *)a4 + 1);
    v10 = (Microsoft::Bluetooth::Services::BthServ *)&v39;
    v35 = (unsigned int)a3;
    v11 = 2147483646;
    LODWORD(hDevice[0]) = 0;
    v12 = 256;
    InBuffer = SerialPortServiceClass_UUID;
    do
    {
      if ( !v11 )
        break;
      if ( !*v7 )
        break;
      *(_WORD *)v10 = *v7++;
      v10 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v10 + 2);
      --v11;
      --v12;
    }
    while ( v12 );
    v13 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v10 - 2);
    v14 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v13 = v10;
    *(_WORD *)v13 = 0;
    if ( v12 )
    {
      v15 = a4 + 132;
      v16 = (Microsoft::Bluetooth::Services::BthServ *)&v38;
      do
      {
        if ( !v8 )
          break;
        if ( !*v15 )
          break;
        *(_WORD *)v16 = *v15++;
        v16 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v16 + 2);
        --v8;
        --v9;
      }
      while ( v9 );
      v13 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v16 - 2);
      if ( v9 )
        v13 = v16;
      v9 = -v9;
      v14 = v9 == 0 ? 0x8007007A : 0;
      *(_WORD *)v13 = 0;
    }
    if ( !v36 )
    {
      v17 = v14 == 0;
      if ( (v14 & 0x80000000) != 0 )
      {
LABEL_20:
        if ( v17 )
        {
          v14 = 0;
          if ( !DeviceIoControl(this, 0x41104Cu, &InBuffer, 0x422u, 0, 0, (LPDWORD)hDevice, 0) )
            return GetLastError();
        }
        return v14;
      }
      v14 = Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(
              v13,
              (void *)v9,
              (const struct _GUID *)v35,
              (int)v10);
    }
    v17 = v14 == 0;
    goto LABEL_20;
  }
  hDevice[0] = 0;
  v14 = 20;
  ProcessHeap = GetProcessHeap();
  v19 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( v19 )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v19[1] = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v19);
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
      {
        if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                             (Microsoft::Bluetooth::Services::BthServ *)v19,
                             hDevice,
                             v21) )
        {
          v24 = (Microsoft::Bluetooth::Services::BthServ *)v19;
        }
        else
        {
          LastError = GetLastError();
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
            (Microsoft::Bluetooth::Services::BthServ *)v19,
            v23);
          v24 = 0;
          SetLastError(LastError);
        }
      }
      else
      {
        v24 = 0;
        DevObjDestroyDeviceInfoList(v19[1]);
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v19);
      }
      if ( v24 )
      {
        v26 = 0;
        do
        {
          v27 = Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(
                  (Microsoft::Bluetooth::Services::BthServ *)hDevice[0],
                  (void *)&SerialPortServiceClass_UUID,
                  (const struct _GUID *)v5,
                  (unsigned int)a4,
                  lpOutBuffer);
          v14 = v27;
          if ( !v27 || v27 == 234 )
            v26 = 1;
          CloseHandle(hDevice[0]);
        }
        while ( !v26 && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v24, hDevice, v29) );
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v24, v28);
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1800234fc  mov     [rsp-8+arg_8], rbx
0x180023501  push    rbp
0x180023502  push    rsi
0x180023503  push    rdi
0x180023504  push    r12
0x180023506  push    r13
0x180023508  push    r14
0x18002350a  push    r15
0x18002350c  lea     rbp, [rsp-390h]
0x180023514  sub     rsp, 490h
0x18002351b  mov     rax, cs:__security_cookie
0x180023522  xor     rax, rsp
0x180023525  mov     [rbp+3C0h+var_40], rax
0x18002352c  xor     r13d, r13d
0x18002352f  mov     r15, r9
0x180023532  mov     r12d, r8d
0x180023535  mov     rbx, rcx
0x180023538  test    rcx, rcx
0x18002353b  jz      loc_18002367E
0x180023541  mov     eax, [r9]
0x180023544  lea     rcx, [r9+10h]
0x180023548  movups  xmm0, xmmword ptr cs:SerialPortServiceClass_UUID.Data1
0x18002354f  mov     dword ptr [rsp+4C0h+var_460+4], eax
0x180023553  mov     r10d, 7FFFFFFEh
0x180023559  mov     rax, [r9+8]
0x18002355d  mov     edx, 100h
0x180023562  mov     [rsp+4C0h+var_458], rax
0x180023567  lea     r9, [rbp+3C0h+var_250]
0x18002356e  mov     dword ptr [rsp+4C0h+var_460], r8d
0x180023573  mov     eax, r10d
0x180023576  mov     dword ptr [rsp+4C0h+hDevice], r13d
0x18002357b  mov     r8d, edx
0x18002357e  movdqu  [rsp+4C0h+InBuffer], xmm0
0x180023584  test    rax, rax
0x180023587  jz      short loc_1800235A8
0x180023589  movzx   r11d, word ptr [rcx]
0x18002358d  test    r11w, r11w
0x180023591  jz      short loc_1800235A8
0x180023593  mov     [r9], r11w
0x180023597  add     rcx, 2
0x18002359b  add     r9, 2; int
0x18002359f  dec     rax
0x1800235a2  sub     r8, 1
0x1800235a6  jnz     short loc_180023584
0x1800235a8  mov     rax, r8
0x1800235ab  lea     rcx, [r9-2]
0x1800235af  neg     rax
0x1800235b2  mov     r11d, 8007007Ah
0x1800235b8  sbb     edi, edi
0x1800235ba  not     edi
0x1800235bc  and     edi, r11d
0x1800235bf  test    r8, r8
0x1800235c2  cmovnz  rcx, r9
0x1800235c6  mov     [rcx], r13w
0x1800235ca  jz      short loc_180023615
0x1800235cc  lea     rcx, [r15+210h]
0x1800235d3  lea     rax, [rsp+4C0h+var_450]
0x1800235d8  test    r10, r10
0x1800235db  jz      short loc_1800235FC
0x1800235dd  movzx   r8d, word ptr [rcx]
0x1800235e1  test    r8w, r8w
0x1800235e5  jz      short loc_1800235FC
0x1800235e7  mov     [rax], r8w
0x1800235eb  add     rcx, 2
0x1800235ef  add     rax, 2
0x1800235f3  dec     r10
0x1800235f6  sub     rdx, 1
0x1800235fa  jnz     short loc_1800235D8
0x1800235fc  test    rdx, rdx
0x1800235ff  lea     rcx, [rax-2]
0x180023603  cmovnz  rcx, rax; this
0x180023607  neg     rdx; void *
0x18002360a  sbb     edi, edi
0x18002360c  not     edi
0x18002360e  and     edi, r11d
0x180023611  mov     [rcx], r13w
0x180023615  cmp     dword ptr [rsp+4C0h+var_460+4], r13d
0x18002361a  jnz     short loc_18002362C
0x18002361c  test    edi, edi
0x18002361e  js      short loc_18002362E
0x180023620  mov     r8d, dword ptr [rsp+4C0h+var_460]; struct _GUID *
0x180023625  call    ?BthpRemoveLocalDeviceInstance@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(void *,_GUID const *,int)
0x18002362a  mov     edi, eax
0x18002362c  test    edi, edi
0x18002362e  jnz     loc_1800237B5
0x180023634  mov     [rsp+4C0h+lpOverlapped], r13; lpOverlapped
0x180023639  lea     rax, [rsp+4C0h+hDevice]
0x18002363e  mov     [rsp+4C0h+lpBytesReturned], rax; lpBytesReturned
0x180023643  lea     r8, [rsp+4C0h+InBuffer]; lpInBuffer
0x180023648  mov     [rsp+4C0h+nOutBufferSize], r13d; nOutBufferSize
0x18002364d  mov     r9d, 422h; nInBufferSize
0x180023653  mov     edx, 41104Ch; dwIoControlCode
0x180023658  mov     [rsp+4C0h+lpOutBuffer], r13; lpOutBuffer
0x18002365d  mov     rcx, rbx; hDevice
0x180023660  mov     edi, r13d
0x180023663  call    cs:__imp_DeviceIoControl
0x180023669  test    eax, eax
0x18002366b  jnz     loc_1800237B5
0x180023671  call    cs:__imp_GetLastError
0x180023677  mov     edi, eax
0x180023679  jmp     loc_1800237B5
0x18002367e  mov     [rsp+4C0h+hDevice], r13
0x180023683  mov     edi, 14h
0x180023688  call    cs:__imp_GetProcessHeap
0x18002368e  mov     rcx, rax; hHeap
0x180023691  lea     edx, [rdi-0Ch]; dwFlags
0x180023694  lea     r8d, [rdi-4]; dwBytes
0x180023698  call    cs:__imp_HeapAlloc
0x18002369e  mov     rsi, rax
0x1800236a1  test    rax, rax
0x1800236a4  jz      loc_1800237B5
0x1800236aa  xor     r9d, r9d
0x1800236ad  mov     [rsp+4C0h+lpOutBuffer], r13
0x1800236b2  xor     r8d, r8d
0x1800236b5  xor     edx, edx
0x1800236b7  xor     ecx, ecx
0x1800236b9  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800236bf  mov     [rsi+8], rax
0x1800236c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800236c7  jz      loc_1800237A1
0x1800236cd  mov     qword ptr [rsp+4C0h+nOutBufferSize], r13
0x1800236d2  lea     r9d, [rdi-2]
0x1800236d6  xor     r8d, r8d
0x1800236d9  mov     [rsp+4C0h+lpOutBuffer], r13; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x1800236de  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800236e5  mov     rcx, rax
0x1800236e8  call    cs:__imp_DevObjGetClassDevs
0x1800236ee  test    eax, eax
0x1800236f0  jz      short loc_180023725
0x1800236f2  lea     rdx, [rsp+4C0h+hDevice]; void *
0x1800236f7  mov     rcx, rsi; this
0x1800236fa  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800236ff  test    eax, eax
0x180023701  jnz     short loc_180023720
0x180023703  call    cs:__imp_GetLastError
0x180023709  mov     rcx, rsi; this
0x18002370c  mov     ebx, eax
0x18002370e  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180023713  mov     ecx, ebx; dwErrCode
0x180023715  mov     r14, r13
0x180023718  call    cs:__imp_SetLastError
0x18002371e  jmp     short loc_180023746
0x180023720  mov     r14, rsi
0x180023723  jmp     short loc_180023746
0x180023725  mov     rcx, [rsi+8]
0x180023729  mov     r14, r13
0x18002372c  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180023732  call    cs:__imp_GetProcessHeap
0x180023738  mov     r8, rsi; lpMem
0x18002373b  xor     edx, edx; dwFlags
0x18002373d  mov     rcx, rax; hHeap
0x180023740  call    cs:__imp_HeapFree
0x180023746  test    r14, r14
0x180023749  jz      short loc_1800237B5
0x18002374b  mov     ebx, r13d
0x18002374e  mov     rcx, [rsp+4C0h+hDevice]; this
0x180023753  lea     rdx, SerialPortServiceClass_UUID; void *
0x18002375a  mov     r9, r15; unsigned int
0x18002375d  mov     r8d, r12d; struct _GUID *
0x180023760  call    ?BluetoothSetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEBU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO const *)
0x180023765  mov     edi, eax
0x180023767  test    eax, eax
0x180023769  jz      short loc_180023772
0x18002376b  cmp     eax, 0EAh
0x180023770  jnz     short loc_180023777
0x180023772  mov     ebx, 1
0x180023777  mov     rcx, [rsp+4C0h+hDevice]; hObject
0x18002377c  call    cs:__imp_CloseHandle
0x180023782  test    ebx, ebx
0x180023784  jnz     short loc_180023797
0x180023786  lea     rdx, [rsp+4C0h+hDevice]; void *
0x18002378b  mov     rcx, r14; this
0x18002378e  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180023793  test    eax, eax
0x180023795  jnz     short loc_18002374E
0x180023797  mov     rcx, r14; this
0x18002379a  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x18002379f  jmp     short loc_1800237B5
0x1800237a1  call    cs:__imp_GetProcessHeap
0x1800237a7  mov     r8, rsi; lpMem
0x1800237aa  xor     edx, edx; dwFlags
0x1800237ac  mov     rcx, rax; hHeap
0x1800237af  call    cs:__imp_HeapFree
0x1800237b5  mov     eax, edi
0x1800237b7  mov     rcx, [rbp+3C0h+var_40]
0x1800237be  xor     rcx, rsp; StackCookie
0x1800237c1  call    __security_check_cookie
0x1800237c6  mov     rbx, [rsp+4C0h+arg_8]
0x1800237ce  add     rsp, 490h
0x1800237d5  pop     r15
0x1800237d7  pop     r14
0x1800237d9  pop     r13
0x1800237db  pop     r12
0x1800237dd  pop     rdi
0x1800237de  pop     rsi
0x1800237df  pop     rbp
0x1800237e0  retn
```
