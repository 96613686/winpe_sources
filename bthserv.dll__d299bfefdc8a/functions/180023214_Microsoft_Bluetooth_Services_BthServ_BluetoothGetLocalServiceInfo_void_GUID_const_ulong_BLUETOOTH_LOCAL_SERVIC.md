# Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO *)

- ea: `0x180023214`
- end: `0x1800234f5`
- name: `?BluetoothGetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEAU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _GUID *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023214`
- `0x1800237e8`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180022d74`
- `0x180023158`
- `0x180023214`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002339c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800234b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002339c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800234b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800234c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800234c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002342c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002342c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023490`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002329c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002329c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800233cd`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800233cd`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800233fc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800233fc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180023440`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180023440`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3,
        __int64 a4)
{
  unsigned int v5; // r12d
  int v6; // eax
  _WORD *v7; // rbx
  unsigned int v8; // esi
  char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  _WORD *v15; // rcx
  _WORD *v16; // rax
  char *v17; // rcx
  _WORD *v18; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // rdi
  __int64 DeviceInfoList; // rax
  void **v22; // r8
  DWORD LastError; // ebx
  void *v24; // rdx
  Microsoft::Bluetooth::Services::BthServ *v25; // r14
  HANDLE v26; // rax
  int v27; // ebx
  unsigned int LocalServiceInfo; // eax
  void *v29; // rdx
  void **v30; // r8
  HANDLE v31; // rax
  struct _BLUETOOTH_LOCAL_SERVICE_INFO *lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+64h] [rbp-9Ch]
  __int64 v38; // [rsp+68h] [rbp-98h]
  char v39; // [rsp+70h] [rbp-90h] BYREF
  char v40; // [rsp+270h] [rbp+170h] BYREF

  v5 = (unsigned int)a3;
  if ( this )
  {
    v36 = (int)a3;
    BytesReturned[0] = 0;
    OutBuffer = SerialPortServiceClass_UUID;
    if ( DeviceIoControl(this, 0x411048u, &OutBuffer, 0x14u, &OutBuffer, 0x422u, BytesReturned, 0) )
    {
      v6 = v37;
      v7 = (_WORD *)(a4 + 16);
      *(_DWORD *)a4 = v37;
      v8 = 0;
      if ( v6 )
      {
        v9 = &v40;
        v10 = 2147483646;
        *(_QWORD *)(a4 + 8) = v38;
        v11 = 256;
        v12 = 2147483646;
        v13 = 256;
        do
        {
          if ( !v12 )
            break;
          if ( !*(_WORD *)v9 )
            break;
          *v7 = *(_WORD *)v9;
          v9 += 2;
          ++v7;
          --v12;
          --v13;
        }
        while ( v13 );
        v14 = v13 == 0;
        v15 = v7 - 1;
        v16 = (_WORD *)(a4 + 528);
        if ( !v14 )
          v15 = v7;
        *v15 = 0;
        v17 = &v39;
        do
        {
          if ( !v10 )
            break;
          if ( !*(_WORD *)v17 )
            break;
          *v16 = *(_WORD *)v17;
          v17 += 2;
          ++v16;
          --v10;
          --v11;
        }
        while ( v11 );
        v18 = v16 - 1;
        if ( v11 )
          v18 = v16;
        *v18 = 0;
      }
      else
      {
        *(_QWORD *)(a4 + 8) = 0;
        memset_0((void *)(a4 + 528), 0, 0x200u);
        memset_0((void *)(a4 + 16), 0, 0x200u);
      }
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    *(_QWORD *)BytesReturned = 0;
    v8 = 20;
    ProcessHeap = GetProcessHeap();
    v20 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v20 )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v20[1] = DeviceInfoList;
      if ( DeviceInfoList == -1 )
      {
        v31 = GetProcessHeap();
        HeapFree(v31, 0, v20);
      }
      else
      {
        if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
        {
          if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                               (Microsoft::Bluetooth::Services::BthServ *)v20,
                               BytesReturned,
                               v22) )
          {
            v25 = (Microsoft::Bluetooth::Services::BthServ *)v20;
          }
          else
          {
            LastError = GetLastError();
            Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
              (Microsoft::Bluetooth::Services::BthServ *)v20,
              v24);
            v25 = 0;
            SetLastError(LastError);
          }
        }
        else
        {
          v25 = 0;
          DevObjDestroyDeviceInfoList(v20[1]);
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v20);
        }
        if ( v25 )
        {
          v27 = 0;
          do
          {
            LocalServiceInfo = Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
                                 *(Microsoft::Bluetooth::Services::BthServ **)BytesReturned,
                                 (void *)&SerialPortServiceClass_UUID,
                                 (const struct _GUID *)v5,
                                 a4,
                                 lpOutBuffer);
            v8 = LocalServiceInfo;
            if ( !LocalServiceInfo || LocalServiceInfo == 234 )
              v27 = 1;
            CloseHandle(*(HANDLE *)BytesReturned);
          }
          while ( !v27
               && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v25, BytesReturned, v30) );
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v25, v29);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180023214  mov     [rsp-8+arg_8], rbx
0x180023219  push    rbp
0x18002321a  push    rsi
0x18002321b  push    rdi
0x18002321c  push    r12
0x18002321e  push    r13
0x180023220  push    r14
0x180023222  push    r15
0x180023224  lea     rbp, [rsp-390h]
0x18002322c  sub     rsp, 490h
0x180023233  mov     rax, cs:__security_cookie
0x18002323a  xor     rax, rsp
0x18002323d  mov     [rbp+3C0h+var_40], rax
0x180023244  xor     r13d, r13d
0x180023247  mov     r15, r9
0x18002324a  mov     r12d, r8d
0x18002324d  test    rcx, rcx
0x180023250  jz      loc_180023392
0x180023256  movups  xmm0, xmmword ptr cs:SerialPortServiceClass_UUID.Data1
0x18002325d  mov     [rsp+4C0h+lpOverlapped], r13; lpOverlapped
0x180023262  lea     rax, [rsp+4C0h+BytesReturned]
0x180023267  mov     [rsp+4C0h+lpBytesReturned], rax; lpBytesReturned
0x18002326c  lea     r9d, [r13+14h]; nInBufferSize
0x180023270  lea     rax, [rsp+4C0h+OutBuffer]
0x180023275  mov     [rsp+4C0h+var_460], r8d
0x18002327a  mov     [rsp+4C0h+nOutBufferSize], 422h; nOutBufferSize
0x180023282  lea     r8, [rsp+4C0h+OutBuffer]; lpInBuffer
0x180023287  mov     edx, 411048h; dwIoControlCode
0x18002328c  mov     [rsp+4C0h+lpOutBuffer], rax; lpOutBuffer
0x180023291  mov     [rsp+4C0h+BytesReturned], r13d
0x180023296  movdqu  [rsp+4C0h+OutBuffer], xmm0
0x18002329c  call    cs:__imp_DeviceIoControl
0x1800232a2  test    eax, eax
0x1800232a4  jz      loc_180023385
0x1800232aa  mov     eax, [rsp+4C0h+var_45C]
0x1800232ae  lea     rbx, [r15+10h]
0x1800232b2  mov     [r15], eax
0x1800232b5  mov     esi, r13d
0x1800232b8  test    eax, eax
0x1800232ba  jz      loc_180023357
0x1800232c0  mov     rax, [rsp+4C0h+var_458]
0x1800232c5  lea     r9, [rbp+3C0h+var_250]
0x1800232cc  mov     r8d, 7FFFFFFEh
0x1800232d2  mov     [r15+8], rax
0x1800232d6  mov     edx, 100h
0x1800232db  mov     ecx, r8d
0x1800232de  mov     eax, edx
0x1800232e0  test    rcx, rcx
0x1800232e3  jz      short loc_180023304
0x1800232e5  movzx   r10d, word ptr [r9]
0x1800232e9  test    r10w, r10w
0x1800232ed  jz      short loc_180023304
0x1800232ef  mov     [rbx], r10w
0x1800232f3  add     r9, 2
0x1800232f7  add     rbx, 2
0x1800232fb  dec     rcx
0x1800232fe  sub     rax, 1
0x180023302  jnz     short loc_1800232E0
0x180023304  test    rax, rax
0x180023307  lea     rcx, [rbx-2]
0x18002330b  lea     rax, [r15+210h]
0x180023312  cmovnz  rcx, rbx
0x180023316  mov     [rcx], r13w
0x18002331a  lea     rcx, [rsp+4C0h+var_450]
0x18002331f  test    r8, r8
0x180023322  jz      short loc_180023343
0x180023324  movzx   r9d, word ptr [rcx]
0x180023328  test    r9w, r9w
0x18002332c  jz      short loc_180023343
0x18002332e  mov     [rax], r9w
0x180023332  add     rcx, 2
0x180023336  add     rax, 2
0x18002333a  dec     r8
0x18002333d  sub     rdx, 1
0x180023341  jnz     short loc_18002331F
0x180023343  test    rdx, rdx
0x180023346  lea     rcx, [rax-2]
0x18002334a  cmovnz  rcx, rax
0x18002334e  mov     [rcx], r13w
0x180023352  jmp     loc_1800234C9
0x180023357  xor     eax, eax
0x180023359  lea     rcx, [r15+210h]; void *
0x180023360  mov     edi, 200h
0x180023365  mov     [r15+8], rax
0x180023369  mov     r8d, edi; Size
0x18002336c  xor     edx, edx; Val
0x18002336e  call    memset_0
0x180023373  mov     r8d, edi; Size
0x180023376  xor     edx, edx; Val
0x180023378  mov     rcx, rbx; void *
0x18002337b  call    memset_0
0x180023380  jmp     loc_1800234C9
0x180023385  call    cs:__imp_GetLastError
0x18002338b  mov     esi, eax
0x18002338d  jmp     loc_1800234C9
0x180023392  mov     qword ptr [rsp+4C0h+BytesReturned], r13
0x180023397  mov     esi, 14h
0x18002339c  call    cs:__imp_GetProcessHeap
0x1800233a2  mov     rcx, rax; hHeap
0x1800233a5  lea     edx, [rsi-0Ch]; dwFlags
0x1800233a8  lea     r8d, [rsi-4]; dwBytes
0x1800233ac  call    cs:__imp_HeapAlloc
0x1800233b2  mov     rdi, rax
0x1800233b5  test    rax, rax
0x1800233b8  jz      loc_1800234C9
0x1800233be  xor     r9d, r9d
0x1800233c1  mov     [rsp+4C0h+lpOutBuffer], r13
0x1800233c6  xor     r8d, r8d
0x1800233c9  xor     edx, edx
0x1800233cb  xor     ecx, ecx
0x1800233cd  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800233d3  mov     [rdi+8], rax
0x1800233d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800233db  jz      loc_1800234B5
0x1800233e1  mov     qword ptr [rsp+4C0h+nOutBufferSize], r13
0x1800233e6  lea     r9d, [rsi-2]
0x1800233ea  xor     r8d, r8d
0x1800233ed  mov     [rsp+4C0h+lpOutBuffer], r13; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x1800233f2  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800233f9  mov     rcx, rax
0x1800233fc  call    cs:__imp_DevObjGetClassDevs
0x180023402  test    eax, eax
0x180023404  jz      short loc_180023439
0x180023406  lea     rdx, [rsp+4C0h+BytesReturned]; void *
0x18002340b  mov     rcx, rdi; this
0x18002340e  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180023413  test    eax, eax
0x180023415  jnz     short loc_180023434
0x180023417  call    cs:__imp_GetLastError
0x18002341d  mov     rcx, rdi; this
0x180023420  mov     ebx, eax
0x180023422  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180023427  mov     ecx, ebx; dwErrCode
0x180023429  mov     r14, r13
0x18002342c  call    cs:__imp_SetLastError
0x180023432  jmp     short loc_18002345A
0x180023434  mov     r14, rdi
0x180023437  jmp     short loc_18002345A
0x180023439  mov     rcx, [rdi+8]
0x18002343d  mov     r14, r13
0x180023440  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180023446  call    cs:__imp_GetProcessHeap
0x18002344c  mov     r8, rdi; lpMem
0x18002344f  xor     edx, edx; dwFlags
0x180023451  mov     rcx, rax; hHeap
0x180023454  call    cs:__imp_HeapFree
0x18002345a  test    r14, r14
0x18002345d  jz      short loc_1800234C9
0x18002345f  mov     ebx, r13d
0x180023462  mov     rcx, qword ptr [rsp+4C0h+BytesReturned]; this
0x180023467  lea     rdx, SerialPortServiceClass_UUID; void *
0x18002346e  mov     r9, r15; unsigned int
0x180023471  mov     r8d, r12d; struct _GUID *
0x180023474  call    ?BluetoothGetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEAU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO *)
0x180023479  mov     esi, eax
0x18002347b  test    eax, eax
0x18002347d  jz      short loc_180023486
0x18002347f  cmp     eax, 0EAh
0x180023484  jnz     short loc_18002348B
0x180023486  mov     ebx, 1
0x18002348b  mov     rcx, qword ptr [rsp+4C0h+BytesReturned]; hObject
0x180023490  call    cs:__imp_CloseHandle
0x180023496  test    ebx, ebx
0x180023498  jnz     short loc_1800234AB
0x18002349a  lea     rdx, [rsp+4C0h+BytesReturned]; void *
0x18002349f  mov     rcx, r14; this
0x1800234a2  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800234a7  test    eax, eax
0x1800234a9  jnz     short loc_180023462
0x1800234ab  mov     rcx, r14; this
0x1800234ae  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x1800234b3  jmp     short loc_1800234C9
0x1800234b5  call    cs:__imp_GetProcessHeap
0x1800234bb  mov     r8, rdi; lpMem
0x1800234be  xor     edx, edx; dwFlags
0x1800234c0  mov     rcx, rax; hHeap
0x1800234c3  call    cs:__imp_HeapFree
0x1800234c9  mov     eax, esi
0x1800234cb  mov     rcx, [rbp+3C0h+var_40]
0x1800234d2  xor     rcx, rsp; StackCookie
0x1800234d5  call    __security_check_cookie
0x1800234da  mov     rbx, [rsp+4C0h+arg_8]
0x1800234e2  add     rsp, 490h
0x1800234e9  pop     r15
0x1800234eb  pop     r14
0x1800234ed  pop     r13
0x1800234ef  pop     r12
0x1800234f1  pop     rdi
0x1800234f2  pop     rsi
0x1800234f3  pop     rbp
0x1800234f4  retn
```
