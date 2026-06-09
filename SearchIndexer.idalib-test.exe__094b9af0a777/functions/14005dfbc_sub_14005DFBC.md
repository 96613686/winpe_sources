# sub_14005DFBC

- ea: `0x14005dfbc`
- end: `0x14005e26b`
- name: `sub_14005DFBC`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000eec4`

## callees

- `0x14000e7b8`
- `0x14000fcac`
- `0x140016848`
- `0x140036018`
- `0x140036f74`
- `0x14003c744`
- `0x14003d520`
- `0x1400579a0`
- `0x14005dfbc`
- `0x14005ea60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e1f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e1f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005e23c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005e139`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005e139`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14005e193`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14005e193`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14005e0c9`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14005e0c9`
- `DEVOBJ!DevObjGetClassDevs` at `0x14005e07a`
- `DEVOBJ!DevObjGetClassDevs` at `0x14005e07a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14005e21a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14005e21a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14005e03f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14005e03f`

## pseudocode

```c
__int64 __fastcall sub_14005DFBC(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  __int64 v3; // rax
  int v4; // esi
  char *v5; // r13
  __int64 DeviceInfoList; // rax
  __int64 v7; // rbx
  unsigned int v8; // r15d
  unsigned int *v9; // rdi
  int v10; // eax
  HANDLE FileW; // rax
  char *v12; // r12
  __int64 v13; // r13
  __int64 v14; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-59h] BYREF
  __int64 v17; // [rsp+48h] [rbp-51h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-49h] BYREF
  __int64 v19; // [rsp+58h] [rbp-41h] BYREF
  unsigned int *v20; // [rsp+60h] [rbp-39h] BYREF
  HANDLE hDevice; // [rsp+68h] [rbp-31h] BYREF
  __int64 v22; // [rsp+70h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-21h]
  __int64 OutBuffer; // [rsp+80h] [rbp-19h] BYREF
  int v25; // [rsp+88h] [rbp-11h]
  _OWORD v26[2]; // [rsp+90h] [rbp-9h] BYREF

  v23 = a2;
  v2 = 0;
  hObject = 0;
  v3 = sub_14000E7B8();
  v4 = sub_14000FCAC(v3, &hObject);
  v5 = (char *)hObject;
  if ( v4 >= 0 )
  {
    v20 = 0;
    if ( (int)sub_140036018(hObject) < 0 )
    {
      v4 = 0;
    }
    else
    {
      v17 = -1;
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v4 = sub_14000FCAC(DeviceInfoList, &v17);
      v7 = v17;
      if ( v4 >= 0 )
      {
        v4 = (unsigned int)DevObjGetClassDevs(v17, qword_1400BE6D0, 0, 18, 0, 0) ? 0 : sub_140016848();
        v8 = 0;
        if ( v4 >= 0 )
        {
          v9 = v20;
          while ( 1 )
          {
            memset(v26, 0, sizeof(v26));
            LODWORD(v26[0]) = 32;
            if ( (unsigned int)DevObjEnumDeviceInterfaces(v7, 0, qword_1400BE6D0, v8, v26) )
              break;
            v10 = sub_140016848();
            v4 = v10;
            if ( v10 == -2147024637 )
            {
              v4 = 0;
              goto LABEL_30;
            }
            if ( v10 >= 0 )
              break;
LABEL_27:
            ++v8;
            if ( v4 < 0 )
              goto LABEL_30;
          }
          v19 = 0;
          v4 = sub_140036F74(v26, v7, &v19);
          if ( v4 < 0 )
          {
LABEL_26:
            sub_14003C744(&v19);
            goto LABEL_27;
          }
          hDevice = 0;
          v22 = v19 + 4;
          FileW = CreateFileW((LPCWSTR)(v19 + 4), 0, 1u, 0, 3u, 0, 0);
          v4 = sub_14000FCAC(FileW, &hDevice);
          v12 = (char *)hDevice;
          if ( v4 < 0 )
          {
LABEL_24:
            if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v12);
            goto LABEL_26;
          }
          OutBuffer = 0;
          v25 = 0;
          BytesReturned = 0;
          if ( DeviceIoControl(hDevice, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
          {
            v4 = 0;
          }
          else
          {
            v4 = sub_140016848();
            if ( v4 < 0 )
            {
LABEL_23:
              v2 = 0;
              goto LABEL_24;
            }
          }
          v13 = v22;
          v14 = v23;
          do
          {
            if ( v2 >= *v9 )
              break;
            if ( v9[6 * v2 + 2] == HIDWORD(OutBuffer) )
              v4 = sub_14005EA60(v14, v13);
            ++v2;
          }
          while ( v4 >= 0 );
          v7 = v17;
          v5 = (char *)hObject;
          goto LABEL_23;
        }
      }
LABEL_30:
      DevObjDestroyDeviceInfoList(v7);
    }
    sub_14003D520(&v20);
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14005dfbc  mov     [rsp-8+arg_10], rbx
0x14005dfc1  push    rbp
0x14005dfc2  push    rsi
0x14005dfc3  push    rdi
0x14005dfc4  push    r12
0x14005dfc6  push    r13
0x14005dfc8  push    r14
0x14005dfca  push    r15
0x14005dfcc  lea     rbp, [rsp-27h]
0x14005dfd1  sub     rsp, 0C0h
0x14005dfd8  mov     rax, cs:__security_cookie
0x14005dfdf  xor     rax, rsp
0x14005dfe2  mov     [rbp+57h+var_40], rax
0x14005dfe6  mov     [rbp+57h+var_78], rdx
0x14005dfea  xor     r14d, r14d
0x14005dfed  mov     [rbp+57h+hObject], r14
0x14005dff1  call    sub_14000E7B8
0x14005dff6  lea     rdx, [rbp+57h+hObject]
0x14005dffa  mov     rcx, rax
0x14005dffd  call    sub_14000FCAC
0x14005e002  mov     esi, eax
0x14005e004  mov     r13, [rbp+57h+hObject]
0x14005e008  test    eax, eax
0x14005e00a  js      loc_14005E22F
0x14005e010  mov     [rbp+57h+var_90], r14
0x14005e014  lea     rdx, [rbp+57h+var_90]
0x14005e018  mov     rcx, r13; hDevice
0x14005e01b  call    sub_140036018
0x14005e020  test    eax, eax
0x14005e022  js      loc_14005E222
0x14005e028  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFFh
0x14005e030  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r14
0x14005e035  xor     r9d, r9d
0x14005e038  xor     r8d, r8d
0x14005e03b  xor     edx, edx
0x14005e03d  xor     ecx, ecx
0x14005e03f  call    cs:DevObjCreateDeviceInfoList
0x14005e045  lea     rdx, [rbp+57h+var_A8]
0x14005e049  mov     rcx, rax
0x14005e04c  call    sub_14000FCAC
0x14005e051  mov     esi, eax
0x14005e053  mov     rbx, [rbp+57h+var_A8]
0x14005e057  test    eax, eax
0x14005e059  js      loc_14005E217
0x14005e05f  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r14
0x14005e064  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r14
0x14005e069  lea     r9d, [r14+12h]
0x14005e06d  xor     r8d, r8d
0x14005e070  lea     rdx, qword_1400BE6D0
0x14005e077  mov     rcx, rbx
0x14005e07a  call    cs:DevObjGetClassDevs
0x14005e080  test    eax, eax
0x14005e082  jz      short loc_14005E089
0x14005e084  mov     esi, r14d
0x14005e087  jmp     short loc_14005E090
0x14005e089  call    sub_140016848
0x14005e08e  mov     esi, eax
0x14005e090  mov     r15d, r14d
0x14005e093  test    esi, esi
0x14005e095  js      loc_14005E217
0x14005e09b  mov     rdi, [rbp+57h+var_90]
0x14005e09f  xorps   xmm0, xmm0
0x14005e0a2  movups  [rbp+57h+var_60], xmm0
0x14005e0a6  movups  [rbp+57h+var_50], xmm0
0x14005e0aa  mov     dword ptr [rbp+57h+var_60], 20h ; ' '
0x14005e0b1  lea     rax, [rbp+57h+var_60]
0x14005e0b5  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x14005e0ba  mov     r9d, r15d
0x14005e0bd  lea     r8, qword_1400BE6D0
0x14005e0c4  xor     edx, edx
0x14005e0c6  mov     rcx, rbx
0x14005e0c9  call    cs:DevObjEnumDeviceInterfaces
0x14005e0cf  test    eax, eax
0x14005e0d1  jnz     short loc_14005E0ED
0x14005e0d3  call    sub_140016848
0x14005e0d8  mov     esi, eax
0x14005e0da  cmp     eax, 80070103h
0x14005e0df  jz      loc_14005E214
0x14005e0e5  test    eax, eax
0x14005e0e7  js      loc_14005E207
0x14005e0ed  mov     [rbp+57h+var_98], r14
0x14005e0f1  lea     r8, [rbp+57h+var_98]
0x14005e0f5  mov     rdx, rbx
0x14005e0f8  lea     rcx, [rbp+57h+var_60]
0x14005e0fc  call    sub_140036F74
0x14005e101  mov     esi, eax
0x14005e103  test    eax, eax
0x14005e105  js      loc_14005E1FE
0x14005e10b  mov     [rbp+57h+hDevice], r14
0x14005e10f  mov     rax, [rbp+57h+var_98]
0x14005e113  add     rax, 4
0x14005e117  mov     [rbp+57h+var_80], rax
0x14005e11b  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x14005e120  mov     [rsp+0F0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x14005e125  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x14005e12d  xor     r9d, r9d; lpSecurityAttributes
0x14005e130  xor     edx, edx; dwDesiredAccess
0x14005e132  lea     r8d, [r9+1]; dwShareMode
0x14005e136  mov     rcx, rax; lpFileName
0x14005e139  call    cs:CreateFileW
0x14005e13f  lea     rdx, [rbp+57h+hDevice]
0x14005e143  mov     rcx, rax
0x14005e146  call    sub_14000FCAC
0x14005e14b  mov     esi, eax
0x14005e14d  mov     r12, [rbp+57h+hDevice]
0x14005e151  test    eax, eax
0x14005e153  js      loc_14005E1E9
0x14005e159  xor     eax, eax
0x14005e15b  mov     [rbp+57h+OutBuffer], rax
0x14005e15f  mov     [rbp+57h+var_68], eax
0x14005e162  mov     [rbp+57h+BytesReturned], r14d
0x14005e166  mov     [rsp+0F0h+lpOverlapped], r14; lpOverlapped
0x14005e16b  lea     rax, [rbp+57h+BytesReturned]
0x14005e16f  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x14005e174  mov     [rsp+0F0h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x14005e17c  lea     rax, [rbp+57h+OutBuffer]
0x14005e180  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; lpOutBuffer
0x14005e185  xor     r9d, r9d; nInBufferSize
0x14005e188  xor     r8d, r8d; lpInBuffer
0x14005e18b  mov     edx, 2D1080h; dwIoControlCode
0x14005e190  mov     rcx, r12; hDevice
0x14005e193  call    cs:DeviceIoControl
0x14005e199  test    eax, eax
0x14005e19b  jz      short loc_14005E1A2
0x14005e19d  mov     esi, r14d
0x14005e1a0  jmp     short loc_14005E1AD
0x14005e1a2  call    sub_140016848
0x14005e1a7  mov     esi, eax
0x14005e1a9  test    eax, eax
0x14005e1ab  js      short loc_14005E1E6
0x14005e1ad  mov     r13, [rbp+57h+var_80]
0x14005e1b1  mov     rbx, [rbp+57h+var_78]
0x14005e1b5  cmp     r14d, [rdi]
0x14005e1b8  jnb     short loc_14005E1DE
0x14005e1ba  mov     eax, r14d
0x14005e1bd  lea     rcx, [rax+rax*2]
0x14005e1c1  mov     eax, dword ptr [rbp+57h+OutBuffer+4]
0x14005e1c4  cmp     [rdi+rcx*8+8], eax
0x14005e1c8  jnz     short loc_14005E1D7
0x14005e1ca  mov     rdx, r13
0x14005e1cd  mov     rcx, rbx
0x14005e1d0  call    sub_14005EA60
0x14005e1d5  mov     esi, eax
0x14005e1d7  inc     r14d
0x14005e1da  test    esi, esi
0x14005e1dc  jns     short loc_14005E1B5
0x14005e1de  mov     rbx, [rbp+57h+var_A8]
0x14005e1e2  mov     r13, [rbp+57h+hObject]
0x14005e1e6  xor     r14d, r14d
0x14005e1e9  lea     rax, [r12-1]
0x14005e1ee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005e1f2  ja      short loc_14005E1FE
0x14005e1f4  mov     rcx, r12; hObject
0x14005e1f7  call    cs:CloseHandle
0x14005e1fd  nop
0x14005e1fe  lea     rcx, [rbp+57h+var_98]
0x14005e202  call    sub_14003C744
0x14005e207  inc     r15d
0x14005e20a  test    esi, esi
0x14005e20c  jns     loc_14005E09F
0x14005e212  jmp     short loc_14005E217
0x14005e214  mov     esi, r14d
0x14005e217  mov     rcx, rbx
0x14005e21a  call    cs:DevObjDestroyDeviceInfoList
0x14005e220  jmp     short loc_14005E225
0x14005e222  mov     esi, r14d
0x14005e225  lea     rcx, [rbp+57h+var_90]
0x14005e229  call    sub_14003D520
0x14005e22e  nop
0x14005e22f  lea     rax, [r13-1]
0x14005e233  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005e237  ja      short loc_14005E242
0x14005e239  mov     rcx, r13; hObject
0x14005e23c  call    cs:CloseHandle
0x14005e242  mov     eax, esi
0x14005e244  mov     rcx, [rbp+57h+var_40]
0x14005e248  xor     rcx, rsp; StackCookie
0x14005e24b  call    __security_check_cookie
0x14005e250  mov     rbx, [rsp+0F0h+arg_10]
0x14005e258  add     rsp, 0C0h
0x14005e25f  pop     r15
0x14005e261  pop     r14
0x14005e263  pop     r13
0x14005e265  pop     r12
0x14005e267  pop     rdi
0x14005e268  pop     rsi
0x14005e269  pop     rbp
0x14005e26a  retn
```
