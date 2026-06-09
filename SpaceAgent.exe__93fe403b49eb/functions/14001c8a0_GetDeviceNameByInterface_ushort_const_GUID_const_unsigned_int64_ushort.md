# GetDeviceNameByInterface(ushort const *,_GUID const *,unsigned __int64 *,ushort *)

- ea: `0x14001c8a0`
- end: `0x14001c9c8`
- name: `?GetDeviceNameByInterface@@YAHPEBGPEBU_GUID@@PEA_KPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(PCWSTR DevicePath, const struct _GUID *, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015bfc`

## callees

- `0x14001c538`
- `0x14001c750`
- `0x14001c8a0`
- `0x14001c9d0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001c91e`
- `KERNEL32!HeapAlloc` at `0x14001c91e`
- `KERNEL32!HeapFree` at `0x14001c989`
- `KERNEL32!HeapFree` at `0x14001c989`
- `KERNEL32!GetProcessHeap` at `0x14001c8ba`
- `KERNEL32!GetProcessHeap` at `0x14001c8ba`
- `KERNEL32!SetLastError` at `0x14001c931`
- `KERNEL32!SetLastError` at `0x14001c9b3`
- `KERNEL32!SetLastError` at `0x14001c931`
- `KERNEL32!SetLastError` at `0x14001c9b3`
- `KERNEL32!GetLastError` at `0x14001c903`
- `KERNEL32!GetLastError` at `0x14001c96a`
- `KERNEL32!GetLastError` at `0x14001c974`
- `KERNEL32!GetLastError` at `0x14001c9a9`
- `KERNEL32!GetLastError` at `0x14001c903`
- `KERNEL32!GetLastError` at `0x14001c96a`
- `KERNEL32!GetLastError` at `0x14001c974`
- `KERNEL32!GetLastError` at `0x14001c9a9`

## pseudocode

```c
__int64 __fastcall GetDeviceNameByInterface(
        PCWSTR DevicePath,
        const struct _GUID *a2,
        unsigned __int64 *a3,
        unsigned __int16 *a4)
{
  const struct _DEVPROPKEY *v7; // rdx
  const struct _GUID *v8; // rcx
  HANDLE ProcessHeap; // r15
  unsigned int DeviceClassString; // ebx
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rcx
  const struct _DEVPROPKEY *v14; // r8
  const struct _GUID *v15; // r9
  DWORD LastError; // edi
  BOOL v17; // eax
  const struct _DEVPROPKEY *v19; // [rsp+20h] [rbp-58h]
  unsigned __int64 v20; // [rsp+88h] [rbp+10h] BYREF

  v20 = (unsigned __int64)a2;
  ProcessHeap = GetProcessHeap();
  if ( *a3 && a4 )
  {
    v7 = 0;
    *a4 = 0;
  }
  if ( !DevicePath )
  {
    DeviceClassString = GetDeviceClassString(v8, v7, a3, a4);
    goto LABEL_16;
  }
  v20 = 0;
  DeviceClassString = GetDeviceInstance(DevicePath, &v20, 0);
  if ( !DeviceClassString )
  {
    v11 = 0;
    if ( GetLastError() != 122 )
      goto LABEL_12;
  }
  v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v20);
  v11 = v12;
  if ( !v12 )
  {
    DeviceClassString = 0;
    SetLastError(8u);
LABEL_16:
    LastError = GetLastError();
    goto LABEL_17;
  }
  DeviceClassString = GetDeviceInstance(DevicePath, &v20, v12);
  if ( DeviceClassString && (DeviceClassString = GetDeviceString(v13, v11, v14, v15, v19, a3, a4)) != 0 )
  {
    LastError = GetLastError();
  }
  else
  {
LABEL_12:
    LastError = GetLastError();
    if ( !v11 )
      goto LABEL_17;
  }
  v17 = HeapFree(ProcessHeap, 0, v11);
  if ( DeviceClassString )
  {
    DeviceClassString = v17;
    LastError = 6;
  }
LABEL_17:
  SetLastError(LastError);
  return DeviceClassString;
}

```

## disassembly

```asm
0x14001c8a0  mov     [rsp+arg_8], rdx
0x14001c8a5  push    rbx
0x14001c8a6  push    rbp
0x14001c8a7  push    rsi
0x14001c8a8  push    rdi
0x14001c8a9  push    r14
0x14001c8ab  push    r15
0x14001c8ad  sub     rsp, 48h
0x14001c8b1  mov     rdi, r9
0x14001c8b4  mov     r14, r8
0x14001c8b7  mov     rbp, rcx
0x14001c8ba  call    cs:__imp_GetProcessHeap
0x14001c8c0  cmp     qword ptr [r14], 0
0x14001c8c4  mov     r15, rax
0x14001c8c7  jbe     short loc_14001C8D3
0x14001c8c9  test    rdi, rdi
0x14001c8cc  jz      short loc_14001C8D3
0x14001c8ce  xor     edx, edx; struct _DEVPROPKEY *
0x14001c8d0  mov     [rdi], dx
0x14001c8d3  test    rbp, rbp
0x14001c8d6  jz      loc_14001C99C
0x14001c8dc  xor     r8d, r8d; unsigned __int16 *
0x14001c8df  mov     [rsp+78h+arg_8], 0
0x14001c8eb  lea     rdx, [rsp+78h+arg_8]; unsigned __int64 *
0x14001c8f3  mov     rcx, rbp; DevicePath
0x14001c8f6  call    ?GetDeviceInstance@@YAHPEBGPEA_KPEAG@Z; GetDeviceInstance(ushort const *,unsigned __int64 *,ushort *)
0x14001c8fb  mov     ebx, eax
0x14001c8fd  test    eax, eax
0x14001c8ff  jnz     short loc_14001C90E
0x14001c901  xor     esi, esi
0x14001c903  call    cs:__imp_GetLastError
0x14001c909  cmp     eax, 7Ah ; 'z'
0x14001c90c  jnz     short loc_14001C974
0x14001c90e  mov     r8, [rsp+78h+arg_8]
0x14001c916  xor     edx, edx; dwFlags
0x14001c918  add     r8, r8; dwBytes
0x14001c91b  mov     rcx, r15; hHeap
0x14001c91e  call    cs:__imp_HeapAlloc
0x14001c924  mov     rsi, rax
0x14001c927  test    rax, rax
0x14001c92a  jnz     short loc_14001C939
0x14001c92c  xor     ebx, ebx
0x14001c92e  lea     ecx, [rax+8]; dwErrCode
0x14001c931  call    cs:__imp_SetLastError
0x14001c937  jmp     short loc_14001C9A9
0x14001c939  mov     r8, rsi; unsigned __int16 *
0x14001c93c  lea     rdx, [rsp+78h+arg_8]; unsigned __int64 *
0x14001c944  mov     rcx, rbp; DevicePath
0x14001c947  call    ?GetDeviceInstance@@YAHPEBGPEA_KPEAG@Z; GetDeviceInstance(ushort const *,unsigned __int64 *,ushort *)
0x14001c94c  mov     ebx, eax
0x14001c94e  test    eax, eax
0x14001c950  jz      short loc_14001C974
0x14001c952  mov     [rsp+78h+var_48], rdi; unsigned __int16 *
0x14001c957  mov     rdx, rsi; unsigned __int16 *
0x14001c95a  mov     [rsp+78h+var_50], r14; unsigned __int64 *
0x14001c95f  call    ?GetDeviceString@@YAHPEBG0PEBU_DEVPROPKEY@@PEBU_GUID@@1PEA_KPEAG@Z; GetDeviceString(ushort const *,ushort const *,_DEVPROPKEY const *,_GUID const *,_DEVPROPKEY const *,unsigned __int64 *,ushort *)
0x14001c964  mov     ebx, eax
0x14001c966  test    eax, eax
0x14001c968  jz      short loc_14001C974
0x14001c96a  call    cs:__imp_GetLastError
0x14001c970  mov     edi, eax
0x14001c972  jmp     short loc_14001C981
0x14001c974  call    cs:__imp_GetLastError
0x14001c97a  mov     edi, eax
0x14001c97c  test    rsi, rsi
0x14001c97f  jz      short loc_14001C9B1
0x14001c981  mov     r8, rsi; lpMem
0x14001c984  xor     edx, edx; dwFlags
0x14001c986  mov     rcx, r15; hHeap
0x14001c989  call    cs:__imp_HeapFree
0x14001c98f  test    ebx, ebx
0x14001c991  jz      short loc_14001C9B1
0x14001c993  mov     ebx, eax
0x14001c995  mov     edi, 6
0x14001c99a  jmp     short loc_14001C9B1
0x14001c99c  mov     r9, rdi; unsigned __int16 *
0x14001c99f  mov     r8, r14; unsigned __int64 *
0x14001c9a2  call    ?GetDeviceClassString@@YAHPEBU_GUID@@PEBU_DEVPROPKEY@@PEA_KPEAG@Z; GetDeviceClassString(_GUID const *,_DEVPROPKEY const *,unsigned __int64 *,ushort *)
0x14001c9a7  mov     ebx, eax
0x14001c9a9  call    cs:__imp_GetLastError
0x14001c9af  mov     edi, eax
0x14001c9b1  mov     ecx, edi; dwErrCode
0x14001c9b3  call    cs:__imp_SetLastError
0x14001c9b9  mov     eax, ebx
0x14001c9bb  add     rsp, 48h
0x14001c9bf  pop     r15
0x14001c9c1  pop     r14
0x14001c9c3  pop     rdi
0x14001c9c4  pop     rsi
0x14001c9c5  pop     rbp
0x14001c9c6  pop     rbx
0x14001c9c7  retn
```
