# Disk_UninstallVolumesByHandle

- ea: `0x14001a2dc`
- end: `0x14001a432`
- name: `Disk_UninstallVolumesByHandle`
- size: `342`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140019e18`
- `0x14001a24c`
- `0x14001b8c4`

## callees

- `0x14001a2dc`
- `0x14001a438`
- `0x14001a4b4`
- `0x14001a530`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001a409`
- `KERNEL32!SetLastError` at `0x14001a409`
- `KERNEL32!GetLastError` at `0x14001a3bf`
- `KERNEL32!GetLastError` at `0x14001a3de`
- `KERNEL32!GetLastError` at `0x14001a3fd`
- `KERNEL32!GetLastError` at `0x14001a3bf`
- `KERNEL32!GetLastError` at `0x14001a3de`
- `KERNEL32!GetLastError` at `0x14001a3fd`
- `KERNEL32!DeviceIoControl` at `0x14001a33e`
- `KERNEL32!DeviceIoControl` at `0x14001a33e`

## pseudocode

```c
__int64 __fastcall Disk_UninstallVolumesByHandle(void *a1)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  unsigned int v3; // ebx
  int v4; // r8d
  int v5; // r8d
  DWORD LastError; // r14d
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v10; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v12; // [rsp+48h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp-20h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h] BYREF
  int v15; // [rsp+60h] [rbp-10h]

  v1 = 0;
  v2 = 0;
  v14 = 0;
  v15 = 0;
  v11 = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  v3 = DeviceIoControl(a1, 0x2D1080u, 0, 0, &v14, 0xCu, 0, 0);
  if ( v3 )
  {
    v3 = Disk_UninstallVolumesByHandle_InitializeUninstallVolumes(
           HIDWORD(v14),
           1,
           v4,
           (unsigned int)&v11,
           (__int64)&v13);
    if ( v3 )
    {
      v3 = Disk_UninstallVolumesByHandle_InitializeUninstallVolumes(
             HIDWORD(v14),
             0,
             v5,
             (unsigned int)&v10,
             (__int64)&v12);
      if ( v3 )
      {
        v3 = Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes(v11, v13);
        if ( v3 )
          v3 = Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes(v10, v12) != 0;
        else
          v2 = v12;
        goto LABEL_9;
      }
      v2 = v12;
    }
    v1 = v13;
  }
LABEL_9:
  LastError = GetLastError();
  if ( v2 )
  {
    v7 = Disk_UninstallVolumesByHandle_AbortUninstallVolumes(v10, v2);
    if ( v3 )
    {
      v3 = v7;
      LastError = GetLastError();
    }
  }
  if ( v1 )
  {
    v8 = Disk_UninstallVolumesByHandle_AbortUninstallVolumes(v11, v1);
    if ( v3 )
    {
      v3 = v8;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x14001a2dc  mov     r11, rsp
0x14001a2df  mov     [r11+10h], rbx
0x14001a2e3  mov     [r11+18h], rsi
0x14001a2e7  push    rbp
0x14001a2e8  push    rdi
0x14001a2e9  push    r14
0x14001a2eb  mov     rbp, rsp
0x14001a2ee  sub     rsp, 70h
0x14001a2f2  mov     rax, cs:__security_cookie
0x14001a2f9  xor     rax, rsp
0x14001a2fc  mov     [rbp+var_8], rax
0x14001a300  xor     eax, eax
0x14001a302  xor     edi, edi
0x14001a304  mov     [r11-50h], rax
0x14001a308  xor     esi, esi
0x14001a30a  mov     [r11-58h], rax
0x14001a30e  xor     r9d, r9d; nInBufferSize
0x14001a311  mov     [rbp+var_18], rax
0x14001a315  xor     r8d, r8d; lpInBuffer
0x14001a318  mov     [rbp+var_10], eax
0x14001a31b  mov     edx, 2D1080h; dwIoControlCode
0x14001a320  mov     [rbp+var_2C], eax
0x14001a323  mov     [rbp+var_30], eax
0x14001a326  lea     rax, [rbp+var_18]
0x14001a32a  mov     [rsp+70h+nOutBufferSize], 0Ch; nOutBufferSize
0x14001a332  mov     [r11-68h], rax
0x14001a336  mov     [rbp+var_20], rdi
0x14001a33a  mov     [rbp+var_28], rsi
0x14001a33e  call    cs:__imp_DeviceIoControl
0x14001a344  mov     ebx, eax
0x14001a346  test    eax, eax
0x14001a348  jz      short loc_14001A3BF
0x14001a34a  mov     ecx, dword ptr [rbp+var_18+4]
0x14001a34d  lea     rax, [rbp+var_20]
0x14001a351  lea     r14d, [rdi+1]
0x14001a355  mov     [rsp+70h+var_50], rax
0x14001a35a  mov     edx, r14d
0x14001a35d  lea     r9, [rbp+var_2C]
0x14001a361  call    Disk_UninstallVolumesByHandle_InitializeUninstallVolumes
0x14001a366  mov     ebx, eax
0x14001a368  test    eax, eax
0x14001a36a  jz      short loc_14001A3BB
0x14001a36c  mov     ecx, dword ptr [rbp+var_18+4]
0x14001a36f  lea     rax, [rbp+var_28]
0x14001a373  lea     r9, [rbp+var_30]
0x14001a377  mov     [rsp+70h+var_50], rax
0x14001a37c  xor     edx, edx
0x14001a37e  call    Disk_UninstallVolumesByHandle_InitializeUninstallVolumes
0x14001a383  mov     ebx, eax
0x14001a385  test    eax, eax
0x14001a387  jz      short loc_14001A3B7
0x14001a389  mov     rdx, [rbp+var_20]
0x14001a38d  mov     ecx, [rbp+var_2C]
0x14001a390  call    Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes
0x14001a395  mov     ebx, eax
0x14001a397  test    eax, eax
0x14001a399  jz      short loc_14001A3B1
0x14001a39b  mov     rdx, [rbp+var_28]
0x14001a39f  mov     ecx, [rbp+var_30]
0x14001a3a2  call    Disk_UninstallVolumesByHandle_FinalizeUninstallVolumes
0x14001a3a7  test    eax, eax
0x14001a3a9  mov     ebx, eax
0x14001a3ab  cmovnz  ebx, r14d
0x14001a3af  jmp     short loc_14001A3BF
0x14001a3b1  mov     rsi, [rbp+var_28]
0x14001a3b5  jmp     short loc_14001A3BF
0x14001a3b7  mov     rsi, [rbp+var_28]
0x14001a3bb  mov     rdi, [rbp+var_20]
0x14001a3bf  call    cs:__imp_GetLastError
0x14001a3c5  mov     r14d, eax
0x14001a3c8  test    rsi, rsi
0x14001a3cb  jz      short loc_14001A3E7
0x14001a3cd  mov     ecx, [rbp+var_30]
0x14001a3d0  mov     rdx, rsi
0x14001a3d3  call    Disk_UninstallVolumesByHandle_AbortUninstallVolumes
0x14001a3d8  test    ebx, ebx
0x14001a3da  jz      short loc_14001A3E7
0x14001a3dc  mov     ebx, eax
0x14001a3de  call    cs:__imp_GetLastError
0x14001a3e4  mov     r14d, eax
0x14001a3e7  test    rdi, rdi
0x14001a3ea  jz      short loc_14001A406
0x14001a3ec  mov     ecx, [rbp+var_2C]
0x14001a3ef  mov     rdx, rdi
0x14001a3f2  call    Disk_UninstallVolumesByHandle_AbortUninstallVolumes
0x14001a3f7  test    ebx, ebx
0x14001a3f9  jz      short loc_14001A406
0x14001a3fb  mov     ebx, eax
0x14001a3fd  call    cs:__imp_GetLastError
0x14001a403  mov     r14d, eax
0x14001a406  mov     ecx, r14d; dwErrCode
0x14001a409  call    cs:__imp_SetLastError
0x14001a40f  mov     eax, ebx
0x14001a411  mov     rcx, [rbp+var_8]
0x14001a415  xor     rcx, rsp; StackCookie
0x14001a418  call    __security_check_cookie
0x14001a41d  lea     r11, [rsp+70h+var_s0]
0x14001a422  mov     rbx, [r11+28h]
0x14001a426  mov     rsi, [r11+30h]
0x14001a42a  mov     rsp, r11
0x14001a42d  pop     r14
0x14001a42f  pop     rdi
0x14001a430  pop     rbp
0x14001a431  retn
```
