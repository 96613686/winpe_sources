# BthDevnodeOpenInterfaceHandle

- ea: `0x18004f920`
- end: `0x18004fb64`
- name: `BthDevnodeOpenInterfaceHandle`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004ef68`

## callees

- `0x180001dd0`
- `0x180002954`
- `0x180002960`
- `0x1800029cc`
- `0x18004e82c`
- `0x18004f8f0`
- `0x18004f920`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004faeb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004faeb`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004f9a8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004f9a8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004fa2c`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004faaa`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004fa2c`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004faaa`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18004f9ec`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18004f9ec`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004fb37`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004fb37`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004f968`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004f968`

## pseudocode

```c
__int64 __fastcall BthDevnodeOpenInterfaceHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  void *DeviceInfoList; // rax
  signed int Error; // ebx
  WCHAR *v6; // rdi
  void *v7; // rcx
  HANDLE FileW; // rax
  __int64 v9; // rcx
  size_t Size; // [rsp+40h] [rbp-40h] BYREF
  void *v12; // [rsp+48h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v14[2]; // [rsp+58h] [rbp-28h] BYREF

  *a3 = (HANDLE)-1LL;
  v12 = (void *)-1LL;
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  Error = ResultFromWin32Handle(DeviceInfoList, &v12);
  if ( Error >= 0 )
  {
    if ( (unsigned int)DevObjGetClassDevs(v12, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      memset(v14, 0, sizeof(v14));
      LODWORD(v14[0]) = 32;
      if ( (unsigned int)DevObjEnumDeviceInterfaces(v12, 0, &GUID_BTHPORT_DEVICE_INTERFACE, 0, v14)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        LODWORD(Size) = 0;
        if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v12, v14, 0, 0, &Size, 0)
          && (unsigned int)ResultFromKnownLastError() == -2147024774
          && (_DWORD)Size )
        {
          v6 = (WCHAR *)o_malloc_0((unsigned int)Size);
          Error = v6 == 0 ? 0x8007000E : 0;
          if ( v6 )
          {
            memset_0(v6, 0, (unsigned int)Size);
            v7 = v12;
            *(_DWORD *)v6 = 8;
            if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v7, v14, v6, (unsigned int)Size, 0, 0)
              || (Error = ResultFromKnownLastError(), Error >= 0) )
            {
              hObject = (HANDLE)-1LL;
              FileW = CreateFileW(v6 + 2, 0xC0000000, 3u, 0, 3u, 0, 0);
              Error = ResultFromWin32Handle(FileW, &hObject);
              if ( Error < 0 )
              {
                v9 = (__int64)hObject;
              }
              else
              {
                v9 = -1;
                *a3 = hObject;
              }
              if ( v9 != -1 )
                CloseHandle((HANDLE)v9);
            }
            free(v6);
          }
        }
        else
        {
          Error = -2147418113;
        }
      }
    }
  }
  if ( v12 != (void *)-1LL )
    DevObjDestroyDeviceInfoList(v12);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004f920  mov     [rsp-18h+arg_0], rbx
0x18004f925  mov     [rsp-18h+arg_8], rdi
0x18004f92a  push    rbp
0x18004f92b  push    r13
0x18004f92d  push    r15
0x18004f92f  mov     rbp, rsp
0x18004f932  sub     rsp, 80h
0x18004f939  mov     rax, cs:__security_cookie
0x18004f940  xor     rax, rsp
0x18004f943  mov     [rbp+var_8], rax
0x18004f947  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004f94b  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004f954  mov     [r8], r13
0x18004f957  mov     r15, r8
0x18004f95a  xor     r8d, r8d
0x18004f95d  mov     [rbp+var_38], r13
0x18004f961  xor     r9d, r9d
0x18004f964  xor     edx, edx
0x18004f966  xor     ecx, ecx
0x18004f968  call    cs:__imp_DevObjCreateDeviceInfoList
0x18004f96e  mov     rcx, rax; void *
0x18004f971  lea     rdx, [rbp+var_38]; void **
0x18004f975  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x18004f97a  mov     ebx, eax
0x18004f97c  test    eax, eax
0x18004f97e  js      loc_18004FB2D
0x18004f984  mov     rcx, [rbp+var_38]
0x18004f988  lea     r9d, [r13+13h]
0x18004f98c  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004f995  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x18004f99c  xor     r8d, r8d
0x18004f99f  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004f9a8  call    cs:__imp_DevObjGetClassDevs
0x18004f9ae  test    eax, eax
0x18004f9b0  jnz     short loc_18004F9C1
0x18004f9b2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004f9b7  mov     ebx, eax
0x18004f9b9  test    eax, eax
0x18004f9bb  js      loc_18004FB2D
0x18004f9c1  mov     rcx, [rbp+var_38]
0x18004f9c5  lea     rax, [rbp+var_28]
0x18004f9c9  xorps   xmm0, xmm0
0x18004f9cc  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004f9d1  movups  [rbp+var_28], xmm0
0x18004f9d5  xor     r9d, r9d
0x18004f9d8  mov     dword ptr [rbp+var_28], 20h ; ' '
0x18004f9df  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x18004f9e6  xor     edx, edx
0x18004f9e8  movups  [rbp+var_18], xmm0
0x18004f9ec  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18004f9f2  test    eax, eax
0x18004f9f4  jnz     short loc_18004FA05
0x18004f9f6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004f9fb  mov     ebx, eax
0x18004f9fd  test    eax, eax
0x18004f9ff  js      loc_18004FB2D
0x18004fa05  mov     rcx, [rbp+var_38]
0x18004fa09  lea     rax, [rbp+Size]
0x18004fa0d  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004fa16  lea     rdx, [rbp+var_28]
0x18004fa1a  xor     r9d, r9d
0x18004fa1d  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004fa22  xor     r8d, r8d
0x18004fa25  mov     dword ptr [rbp+Size], 0
0x18004fa2c  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18004fa32  test    eax, eax
0x18004fa34  jnz     loc_18004FB28
0x18004fa3a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004fa3f  cmp     eax, 8007007Ah
0x18004fa44  jnz     loc_18004FB28
0x18004fa4a  cmp     dword ptr [rbp+Size], 0
0x18004fa4e  jbe     loc_18004FB28
0x18004fa54  mov     ecx, dword ptr [rbp+Size]; Size
0x18004fa57  call    _o_malloc_0
0x18004fa5c  mov     rdi, rax
0x18004fa5f  neg     rax
0x18004fa62  sbb     ebx, ebx
0x18004fa64  not     ebx
0x18004fa66  and     ebx, 8007000Eh
0x18004fa6c  test    rdi, rdi
0x18004fa6f  jz      loc_18004FB2D
0x18004fa75  mov     r8d, dword ptr [rbp+Size]; Size
0x18004fa79  xor     edx, edx; Val
0x18004fa7b  mov     rcx, rdi; void *
0x18004fa7e  call    memset_0
0x18004fa83  mov     rcx, [rbp+var_38]
0x18004fa87  lea     rdx, [rbp+var_28]
0x18004fa8b  mov     dword ptr [rdi], 8
0x18004fa91  mov     r8, rdi
0x18004fa94  mov     r9d, dword ptr [rbp+Size]
0x18004fa98  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004faa1  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004faaa  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18004fab0  test    eax, eax
0x18004fab2  jnz     short loc_18004FABF
0x18004fab4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004fab9  mov     ebx, eax
0x18004fabb  test    eax, eax
0x18004fabd  js      short loc_18004FB1E
0x18004fabf  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18004fac8  lea     rcx, [rdi+4]; lpFileName
0x18004facc  mov     r8d, 3; dwShareMode
0x18004fad2  mov     [rsp+80h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004fada  xor     r9d, r9d; lpSecurityAttributes
0x18004fadd  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004fae2  mov     edx, 0C0000000h; dwDesiredAccess
0x18004fae7  mov     [rbp+hObject], r13
0x18004faeb  call    cs:__imp_CreateFileW
0x18004faf1  mov     rcx, rax; void *
0x18004faf4  lea     rdx, [rbp+hObject]; void **
0x18004faf8  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x18004fafd  mov     ebx, eax
0x18004faff  test    eax, eax
0x18004fb01  js      short loc_18004FB0F
0x18004fb03  mov     rax, [rbp+hObject]
0x18004fb07  mov     rcx, r13
0x18004fb0a  mov     [r15], rax
0x18004fb0d  jmp     short loc_18004FB13
0x18004fb0f  mov     rcx, [rbp+hObject]; hObject
0x18004fb13  cmp     rcx, r13
0x18004fb16  jz      short loc_18004FB1E
0x18004fb18  call    cs:__imp_CloseHandle
0x18004fb1e  mov     rcx, rdi; Block
0x18004fb21  call    free
0x18004fb26  jmp     short loc_18004FB2D
0x18004fb28  mov     ebx, 8000FFFFh
0x18004fb2d  cmp     [rbp+var_38], r13
0x18004fb31  jz      short loc_18004FB3D
0x18004fb33  mov     rcx, [rbp+var_38]
0x18004fb37  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18004fb3d  mov     eax, ebx
0x18004fb3f  mov     rcx, [rbp+var_8]
0x18004fb43  xor     rcx, rsp; StackCookie
0x18004fb46  call    __security_check_cookie
0x18004fb4b  lea     r11, [rsp+80h+var_s0]
0x18004fb53  mov     rbx, [r11+20h]
0x18004fb57  mov     rdi, [r11+28h]
0x18004fb5b  mov     rsp, r11
0x18004fb5e  pop     r15
0x18004fb60  pop     r13
0x18004fb62  pop     rbp
0x18004fb63  retn
```
