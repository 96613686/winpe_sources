# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)

- ea: `0x180022d74`
- end: `0x180022f29`
- name: `?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z`
- size: `437`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022b34`
- `0x180023214`
- `0x1800234fc`
- `0x180025e24`

## callees

- `0x180001790`
- `0x180022d74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022e3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022e3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ec5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ec5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022efe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022ea9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022ea9`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180022dd6`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180022dd6`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022e10`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022e76`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022e10`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180022e76`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
        Microsoft::Bluetooth::Services::BthServ *this,
        _QWORD *a2,
        void **a3)
{
  unsigned int v3; // esi
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // r14
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  HANDLE v15; // rax
  DWORD v16; // ecx
  SIZE_T dwBytes; // [rsp+40h] [rbp-48h] BYREF
  _OWORD v19[2]; // [rsp+48h] [rbp-40h] BYREF

  v3 = 0;
  if ( this )
  {
    while ( 1 )
    {
      v6 = *(unsigned int *)this;
      v7 = *((_QWORD *)this + 1);
      memset(v19, 0, sizeof(v19));
      LODWORD(v19[0]) = 32;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v7, 0, &GUID_BTHPORT_DEVICE_INTERFACE, v6, v19) )
        break;
      v8 = *((_QWORD *)this + 1);
      ++*(_DWORD *)this;
      LODWORD(dwBytes) = 0;
      DevObjGetDeviceInterfaceDetail(v8, v19, 0, 0, &dwBytes, 0);
      if ( GetLastError() == 122 )
      {
        v9 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
        v12 = v11;
        if ( !v11 )
        {
          v16 = 14;
          goto LABEL_14;
        }
        *(_DWORD *)v11 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(
                             *((_QWORD *)this + 1),
                             v19,
                             v11,
                             (unsigned int)dwBytes,
                             &dwBytes,
                             0) )
        {
          FileW = CreateFileW(v12 + 2, 0xC0000000, 3u, 0, 3u, 0, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            *a2 = FileW;
            v3 = 1;
          }
        }
        LastError = GetLastError();
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v12);
        SetLastError(LastError);
      }
      if ( v3 )
        return v3;
    }
    v16 = 259;
  }
  else
  {
    v16 = 6;
  }
LABEL_14:
  SetLastError(v16);
  return v3;
}

```

## disassembly

```asm
0x180022d74  mov     [rsp+arg_10], rbx
0x180022d79  mov     [rsp+arg_18], rsi
0x180022d7e  push    rdi
0x180022d7f  push    r14
0x180022d81  push    r15
0x180022d83  sub     rsp, 70h
0x180022d87  mov     rax, cs:__security_cookie
0x180022d8e  xor     rax, rsp
0x180022d91  mov     [rsp+88h+var_20], rax
0x180022d96  xor     esi, esi
0x180022d98  mov     r15, rdx
0x180022d9b  mov     rdi, rcx
0x180022d9e  test    rcx, rcx
0x180022da1  jz      loc_180022EF9
0x180022da7  mov     r9d, [rdi]
0x180022daa  lea     rax, [rsp+88h+var_40]
0x180022daf  mov     rcx, [rdi+8]
0x180022db3  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x180022dba  xorps   xmm0, xmm0
0x180022dbd  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180022dc2  movups  [rsp+88h+var_40], xmm0
0x180022dc7  xor     edx, edx
0x180022dc9  mov     dword ptr [rsp+88h+var_40], 20h ; ' '
0x180022dd1  movups  [rsp+88h+var_30], xmm0
0x180022dd6  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180022ddc  test    eax, eax
0x180022dde  jz      loc_180022EF2
0x180022de4  mov     rcx, [rdi+8]
0x180022de8  lea     rax, [rsp+88h+dwBytes]
0x180022ded  inc     dword ptr [rdi]
0x180022def  lea     rdx, [rsp+88h+var_40]
0x180022df4  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], 0
0x180022dfd  xor     r9d, r9d
0x180022e00  xor     r8d, r8d
0x180022e03  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180022e08  mov     dword ptr [rsp+88h+dwBytes], 0
0x180022e10  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180022e16  call    cs:__imp_GetLastError
0x180022e1c  cmp     eax, 7Ah ; 'z'
0x180022e1f  jnz     loc_180022EE1
0x180022e25  mov     ebx, dword ptr [rsp+88h+dwBytes]
0x180022e29  call    cs:__imp_GetProcessHeap
0x180022e2f  mov     r8d, ebx; dwBytes
0x180022e32  mov     edx, 8; dwFlags
0x180022e37  mov     rcx, rax; hHeap
0x180022e3a  call    cs:__imp_HeapAlloc
0x180022e40  mov     r14, rax
0x180022e43  test    rax, rax
0x180022e46  jz      loc_180022EEB
0x180022e4c  mov     dword ptr [rax], 8
0x180022e52  lea     rdx, [rsp+88h+var_40]
0x180022e57  mov     r9d, dword ptr [rsp+88h+dwBytes]
0x180022e5c  lea     rax, [rsp+88h+dwBytes]
0x180022e61  mov     rcx, [rdi+8]
0x180022e65  mov     r8, r14
0x180022e68  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], 0
0x180022e71  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180022e76  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180022e7c  test    eax, eax
0x180022e7e  jz      short loc_180022EBD
0x180022e80  xor     r9d, r9d; lpSecurityAttributes
0x180022e83  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180022e8c  lea     rcx, [r14+4]; lpFileName
0x180022e90  mov     [rsp+88h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180022e98  mov     edx, 0C0000000h; dwDesiredAccess
0x180022e9d  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180022ea5  lea     r8d, [r9+3]; dwShareMode
0x180022ea9  call    cs:__imp_CreateFileW
0x180022eaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022eb3  jz      short loc_180022EBD
0x180022eb5  mov     [r15], rax
0x180022eb8  mov     esi, 1
0x180022ebd  call    cs:__imp_GetLastError
0x180022ec3  mov     ebx, eax
0x180022ec5  call    cs:__imp_GetProcessHeap
0x180022ecb  mov     r8, r14; lpMem
0x180022ece  xor     edx, edx; dwFlags
0x180022ed0  mov     rcx, rax; hHeap
0x180022ed3  call    cs:__imp_HeapFree
0x180022ed9  mov     ecx, ebx; dwErrCode
0x180022edb  call    cs:__imp_SetLastError
0x180022ee1  test    esi, esi
0x180022ee3  jz      loc_180022DA7
0x180022ee9  jmp     short loc_180022F04
0x180022eeb  mov     ecx, 0Eh
0x180022ef0  jmp     short loc_180022EFE
0x180022ef2  mov     ecx, 103h
0x180022ef7  jmp     short loc_180022EFE
0x180022ef9  mov     ecx, 6; dwErrCode
0x180022efe  call    cs:__imp_SetLastError
0x180022f04  mov     eax, esi
0x180022f06  mov     rcx, [rsp+88h+var_20]
0x180022f0b  xor     rcx, rsp; StackCookie
0x180022f0e  call    __security_check_cookie
0x180022f13  lea     r11, [rsp+88h+var_18]
0x180022f18  mov     rbx, [r11+30h]
0x180022f1c  mov     rsi, [r11+38h]
0x180022f20  mov     rsp, r11
0x180022f23  pop     r15
0x180022f25  pop     r14
0x180022f27  pop     rdi
0x180022f28  retn
```
