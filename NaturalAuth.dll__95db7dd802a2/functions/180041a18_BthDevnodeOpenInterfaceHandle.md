# BthDevnodeOpenInterfaceHandle

- ea: `0x180041a18`
- end: `0x180041c4e`
- name: `BthDevnodeOpenInterfaceHandle`
- size: `566`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180033fa0`
- `0x180035760`
- `0x180037080`

## callees

- `0x180004170`
- `0x1800050c8`
- `0x1800050d4`
- `0x180005140`
- `0x180037044`
- `0x1800419e8`
- `0x180041a18`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041bd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041bd5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041b20`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041b98`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041b20`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041b98`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041ae2`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041ae2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041a60`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041a60`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041aa0`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041aa0`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180041c21`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180041c21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthDevnodeOpenInterfaceHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  void *DeviceInfoList; // rax
  signed int v5; // ebx
  int ClassDevs; // eax
  int v7; // eax
  int DeviceInterfaceDetail; // eax
  WCHAR *v9; // rdi
  __int64 v10; // r9
  void *v11; // rcx
  int v12; // eax
  HANDLE FileW; // rax
  __int64 v14; // rcx
  size_t Size; // [rsp+40h] [rbp-40h] BYREF
  void *v17; // [rsp+48h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v19[2]; // [rsp+58h] [rbp-28h] BYREF

  *a3 = (HANDLE)-1LL;
  v17 = (void *)-1LL;
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = ResultFromWin32Handle(DeviceInfoList, &v17);
  if ( v5 >= 0 )
  {
    ClassDevs = DevObjGetClassDevs(v17, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0);
    v5 = ResultFromWin32Bool(ClassDevs);
    if ( v5 >= 0 )
    {
      memset(v19, 0, sizeof(v19));
      LODWORD(v19[0]) = 32;
      v7 = DevObjEnumDeviceInterfaces(v17, 0, &GUID_BTHPORT_DEVICE_INTERFACE, 0, v19);
      v5 = ResultFromWin32Bool(v7);
      if ( v5 >= 0 )
      {
        LODWORD(Size) = 0;
        DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(v17, v19, 0, 0, &Size, 0);
        if ( (unsigned int)ResultFromWin32Bool(DeviceInterfaceDetail) == -2147024774 && (_DWORD)Size )
        {
          v9 = (WCHAR *)o_malloc_0((unsigned int)Size);
          v5 = v9 == 0 ? 0x8007000E : 0;
          if ( v9 )
          {
            memset_0(v9, 0, (unsigned int)Size);
            v10 = (unsigned int)Size;
            v11 = v17;
            *(_DWORD *)v9 = 8;
            v12 = DevObjGetDeviceInterfaceDetail(v11, v19, v9, v10, 0, 0);
            v5 = ResultFromWin32Bool(v12);
            if ( v5 >= 0 )
            {
              hObject = (HANDLE)-1LL;
              FileW = CreateFileW(v9 + 2, 0xC0000000, 3u, 0, 3u, 0, 0);
              v5 = ResultFromWin32Handle(FileW, &hObject);
              if ( v5 < 0 )
              {
                v14 = (__int64)hObject;
              }
              else
              {
                v14 = -1;
                *a3 = hObject;
              }
              if ( v14 != -1 )
                CloseHandle((HANDLE)v14);
            }
            free(v9);
          }
        }
        else
        {
          v5 = -2147418113;
        }
      }
    }
  }
  if ( v17 != (void *)-1LL )
    DevObjDestroyDeviceInfoList(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180041a18  mov     [rsp-18h+arg_0], rbx
0x180041a1d  mov     [rsp-18h+arg_8], rdi
0x180041a22  push    rbp
0x180041a23  push    r13
0x180041a25  push    r15
0x180041a27  mov     rbp, rsp
0x180041a2a  sub     rsp, 80h
0x180041a31  mov     rax, cs:__security_cookie
0x180041a38  xor     rax, rsp
0x180041a3b  mov     [rbp+var_8], rax
0x180041a3f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180041a43  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x180041a4c  mov     [r8], r13
0x180041a4f  mov     r15, r8
0x180041a52  xor     r8d, r8d
0x180041a55  mov     [rbp+var_38], r13
0x180041a59  xor     r9d, r9d
0x180041a5c  xor     edx, edx
0x180041a5e  xor     ecx, ecx
0x180041a60  call    cs:__imp_DevObjCreateDeviceInfoList
0x180041a66  mov     rcx, rax; void *
0x180041a69  lea     rdx, [rbp+var_38]; void **
0x180041a6d  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180041a72  mov     ebx, eax
0x180041a74  test    eax, eax
0x180041a76  js      loc_180041C17
0x180041a7c  mov     rcx, [rbp+var_38]
0x180041a80  lea     r9d, [r13+13h]
0x180041a84  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x180041a8d  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x180041a94  xor     r8d, r8d
0x180041a97  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x180041aa0  call    cs:__imp_DevObjGetClassDevs
0x180041aa6  mov     ecx, eax; int
0x180041aa8  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180041aad  mov     ebx, eax
0x180041aaf  test    eax, eax
0x180041ab1  js      loc_180041C17
0x180041ab7  mov     rcx, [rbp+var_38]
0x180041abb  lea     rax, [rbp+var_28]
0x180041abf  xorps   xmm0, xmm0
0x180041ac2  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180041ac7  movups  [rbp+var_28], xmm0
0x180041acb  xor     r9d, r9d
0x180041ace  mov     dword ptr [rbp+var_28], 20h ; ' '
0x180041ad5  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x180041adc  xor     edx, edx
0x180041ade  movups  [rbp+var_18], xmm0
0x180041ae2  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180041ae8  mov     ecx, eax; int
0x180041aea  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180041aef  mov     ebx, eax
0x180041af1  test    eax, eax
0x180041af3  js      loc_180041C17
0x180041af9  mov     rcx, [rbp+var_38]
0x180041afd  lea     rax, [rbp+Size]
0x180041b01  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x180041b0a  lea     rdx, [rbp+var_28]
0x180041b0e  xor     r9d, r9d
0x180041b11  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180041b16  xor     r8d, r8d
0x180041b19  mov     dword ptr [rbp+Size], 0
0x180041b20  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180041b26  mov     ecx, eax; int
0x180041b28  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180041b2d  cmp     eax, 8007007Ah
0x180041b32  jnz     loc_180041C12
0x180041b38  cmp     dword ptr [rbp+Size], 0
0x180041b3c  jbe     loc_180041C12
0x180041b42  mov     ecx, dword ptr [rbp+Size]; Size
0x180041b45  call    _o_malloc_0
0x180041b4a  mov     rdi, rax
0x180041b4d  neg     rax
0x180041b50  sbb     ebx, ebx
0x180041b52  not     ebx
0x180041b54  and     ebx, 8007000Eh
0x180041b5a  test    rdi, rdi
0x180041b5d  jz      loc_180041C17
0x180041b63  mov     r8d, dword ptr [rbp+Size]; Size
0x180041b67  xor     edx, edx; Val
0x180041b69  mov     rcx, rdi; void *
0x180041b6c  call    memset_0
0x180041b71  mov     r9d, dword ptr [rbp+Size]
0x180041b75  lea     rdx, [rbp+var_28]
0x180041b79  mov     rcx, [rbp+var_38]
0x180041b7d  mov     r8, rdi
0x180041b80  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x180041b89  mov     dword ptr [rdi], 8
0x180041b8f  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x180041b98  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180041b9e  mov     ecx, eax; int
0x180041ba0  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180041ba5  mov     ebx, eax
0x180041ba7  test    eax, eax
0x180041ba9  js      short loc_180041C08
0x180041bab  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180041bb4  lea     r8d, [r13+4]; dwShareMode
0x180041bb8  mov     [rsp+80h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180041bc0  lea     rcx, [rdi+4]; lpFileName
0x180041bc4  xor     r9d, r9d; lpSecurityAttributes
0x180041bc7  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x180041bcc  mov     edx, 0C0000000h; dwDesiredAccess
0x180041bd1  mov     [rbp+hObject], r13
0x180041bd5  call    cs:__imp_CreateFileW
0x180041bdb  mov     rcx, rax; void *
0x180041bde  lea     rdx, [rbp+hObject]; void **
0x180041be2  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180041be7  mov     ebx, eax
0x180041be9  test    eax, eax
0x180041beb  js      short loc_180041BF9
0x180041bed  mov     rax, [rbp+hObject]
0x180041bf1  mov     rcx, r13
0x180041bf4  mov     [r15], rax
0x180041bf7  jmp     short loc_180041BFD
0x180041bf9  mov     rcx, [rbp+hObject]; hObject
0x180041bfd  cmp     rcx, r13
0x180041c00  jz      short loc_180041C08
0x180041c02  call    cs:__imp_CloseHandle
0x180041c08  mov     rcx, rdi; Block
0x180041c0b  call    free
0x180041c10  jmp     short loc_180041C17
0x180041c12  mov     ebx, 8000FFFFh
0x180041c17  cmp     [rbp+var_38], r13
0x180041c1b  jz      short loc_180041C27
0x180041c1d  mov     rcx, [rbp+var_38]
0x180041c21  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180041c27  mov     eax, ebx
0x180041c29  mov     rcx, [rbp+var_8]
0x180041c2d  xor     rcx, rsp; StackCookie
0x180041c30  call    __security_check_cookie
0x180041c35  lea     r11, [rsp+80h+var_s0]
0x180041c3d  mov     rbx, [r11+20h]
0x180041c41  mov     rdi, [r11+28h]
0x180041c45  mov     rsp, r11
0x180041c48  pop     r15
0x180041c4a  pop     r13
0x180041c4c  pop     rbp
0x180041c4d  retn
```
