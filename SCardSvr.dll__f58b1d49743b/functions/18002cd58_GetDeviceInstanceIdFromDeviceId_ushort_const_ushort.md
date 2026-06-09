# GetDeviceInstanceIdFromDeviceId(ushort const *,ushort * *)

- ea: `0x18002cd58`
- end: `0x18002d0b8`
- name: `?GetDeviceInstanceIdFromDeviceId@@YAKPEBGPEAPEAG@Z`
- size: `864`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002c850`

## callees

- `0x1800022b0`
- `0x180014dc0`
- `0x1800195fc`
- `0x18002cd58`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cea2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cf94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cea2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cf94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d05e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002cdb7`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002cdb7`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002cf3c`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002cfe8`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002cf3c`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002cfe8`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002ce31`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002ce31`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002cdf9`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002cdf9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002ce5d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002cedc`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002ce5d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18002cedc`
- `KERNEL32!lstrcmpiW` at `0x18002cf0c`
- `KERNEL32!lstrcmpiW` at `0x18002cf0c`

## pseudocode

```c
__int64 __fastcall GetDeviceInstanceIdFromDeviceId(LPCWSTR lpString1, const unsigned __int16 **a2)
{
  __int64 DeviceInfoList; // rax
  __int64 v5; // rbx
  DWORD LastError; // eax
  const unsigned __int8 *v7; // rcx
  DWORD v8; // ebx
  unsigned int i; // r15d
  DWORD v10; // eax
  const unsigned __int8 *v11; // rcx
  unsigned int v12; // edi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int8 *v15; // rcx
  const unsigned __int16 *v16; // r14
  DWORD v17; // eax
  const unsigned __int8 *v18; // rcx
  DWORD v19; // eax
  const unsigned __int8 *v20; // rcx
  DWORD v21; // edi
  SIZE_T v22; // rdi
  HANDLE v23; // rax
  const unsigned __int8 *v24; // rcx
  const unsigned __int16 *v25; // rdi
  const unsigned __int8 *v26; // rcx
  unsigned int v28; // [rsp+30h] [rbp-59h] BYREF
  _DWORD dwBytes[3]; // [rsp+34h] [rbp-55h] BYREF
  const unsigned __int16 *v30; // [rsp+40h] [rbp-49h]
  unsigned __int16 *v31; // [rsp+48h] [rbp-41h]
  _OWORD v32[2]; // [rsp+50h] [rbp-39h] BYREF
  _OWORD v33[3]; // [rsp+70h] [rbp-19h] BYREF

  memset(v33, 0, sizeof(v33));
  v30 = 0;
  v28 = 0;
  memset(v32, 0, sizeof(v32));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = DeviceInfoList;
  *(_QWORD *)&dwBytes[1] = DeviceInfoList;
  if ( DeviceInfoList == -1
    || !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_SMARTCARD_READER, 0, 18, 0, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
  }
  else
  {
    LODWORD(v33[0]) = 48;
    LODWORD(v32[0]) = 32;
    for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v5, 0, &GUID_DEVINTERFACE_SMARTCARD_READER, i, v32); ++i )
    {
      dwBytes[0] = 0;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v5, v32, 0, 0, dwBytes, 0) || (v10 = GetLastError(), v10 == 122) )
      {
        v12 = dwBytes[0];
        ProcessHeap = GetProcessHeap();
        v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v12);
        v16 = v14;
        v31 = v14;
        if ( !v14 )
        {
          v8 = 14;
          CalaisError(v15, 0x263u, 0xEu, 0, 0, 0);
          goto LABEL_26;
        }
        *(_DWORD *)v14 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v5, v32, v14, dwBytes[0], 0, v33) )
        {
          if ( !lstrcmpiW(lpString1, v16 + 2) )
          {
            if ( !(unsigned int)DevObjGetDeviceInstanceId(v5, v33, 0, 0, &v28) )
            {
              v19 = GetLastError();
              v21 = v19;
              if ( v19 != 122 )
              {
                CalaisError(v20, 0x263u, v19, 0, 0, 0);
                ConstStringHeapFree(v16);
                v8 = v21;
                goto LABEL_26;
              }
            }
            v22 = 2LL * v28;
            v23 = GetProcessHeap();
            v25 = (const unsigned __int16 *)HeapAlloc(v23, 8u, v22);
            v30 = v25;
            if ( !v25 )
            {
              v8 = 14;
              CalaisError(v24, 0x263u, 0xEu, 0, 0, 0);
              ConstStringHeapFree(v16);
              goto LABEL_26;
            }
            if ( !(unsigned int)DevObjGetDeviceInstanceId(v5, v33, v25, v28, &v28) )
            {
              v8 = GetLastError();
              CalaisError(v26, 0x263u, v8, 0, 0, 0);
              ConstStringHeapFree(v16);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&dwBytes[1]);
              ConstStringHeapFree(v25);
              return v8;
            }
            v8 = 0;
            ConstStringHeapFree(v16);
            *a2 = v25;
            goto LABEL_26;
          }
        }
        else
        {
          v17 = GetLastError();
          CalaisError(v18, 0x263u, v17, 0, 0, 0);
        }
        ConstStringHeapFree(v16);
      }
      else
      {
        CalaisError(v11, 0x263u, v10, 0, 0, 0);
      }
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 259 )
      goto LABEL_26;
  }
  CalaisError(v7, 0x263u, LastError, 0, 0, 0);
LABEL_26:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&dwBytes[1]);
  return v8;
}

```

## disassembly

```asm
0x18002cd58  mov     [rsp-8+arg_10], rbx
0x18002cd5d  push    rbp
0x18002cd5e  push    rsi
0x18002cd5f  push    rdi
0x18002cd60  push    r12
0x18002cd62  push    r13
0x18002cd64  push    r14
0x18002cd66  push    r15
0x18002cd68  lea     rbp, [rsp-27h]
0x18002cd6d  sub     rsp, 0B0h
0x18002cd74  mov     rax, cs:__security_cookie
0x18002cd7b  xor     rax, rsp
0x18002cd7e  mov     [rbp+57h+var_40], rax
0x18002cd82  mov     r13, rdx
0x18002cd85  mov     r12, rcx
0x18002cd88  xorps   xmm0, xmm0
0x18002cd8b  movups  [rbp+57h+var_70], xmm0
0x18002cd8f  movups  [rbp+57h+var_60], xmm0
0x18002cd93  movups  [rbp+57h+var_50], xmm0
0x18002cd97  xor     edi, edi
0x18002cd99  mov     [rbp+57h+var_A0], rdi
0x18002cd9d  mov     [rbp+57h+var_B0], edi
0x18002cda0  movups  [rbp+57h+var_90], xmm0
0x18002cda4  movups  [rbp+57h+var_80], xmm0
0x18002cda8  mov     [rsp+0E0h+var_C0], rdi
0x18002cdad  xor     r9d, r9d
0x18002cdb0  xor     r8d, r8d
0x18002cdb3  xor     edx, edx
0x18002cdb5  xor     ecx, ecx
0x18002cdb7  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002cdbd  mov     rbx, rax
0x18002cdc0  mov     qword ptr [rbp+57h+dwBytes+4], rax
0x18002cdc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cdc8  jnz     short loc_18002CDDC
0x18002cdca  call    cs:__imp_GetLastError
0x18002cdd0  mov     ebx, eax
0x18002cdd2  mov     edx, 263h
0x18002cdd7  jmp     loc_18002D06F
0x18002cddc  mov     [rsp+0E0h+var_B8], rdi
0x18002cde1  mov     [rsp+0E0h+var_C0], rdi
0x18002cde6  mov     r9d, 12h
0x18002cdec  xor     r8d, r8d
0x18002cdef  lea     rdx, GUID_DEVINTERFACE_SMARTCARD_READER
0x18002cdf6  mov     rcx, rbx
0x18002cdf9  call    cs:__imp_DevObjGetClassDevs
0x18002cdff  test    eax, eax
0x18002ce01  jz      short loc_18002CDCA
0x18002ce03  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x18002ce0a  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x18002ce11  mov     r15d, edi
0x18002ce14  mov     esi, 263h
0x18002ce19  lea     rax, [rbp+57h+var_90]
0x18002ce1d  mov     [rsp+0E0h+var_C0], rax
0x18002ce22  mov     r9d, r15d
0x18002ce25  lea     r8, GUID_DEVINTERFACE_SMARTCARD_READER
0x18002ce2c  xor     edx, edx
0x18002ce2e  mov     rcx, rbx
0x18002ce31  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18002ce37  test    eax, eax
0x18002ce39  jz      loc_18002D05E
0x18002ce3f  mov     dword ptr [rbp+57h+dwBytes], edi
0x18002ce42  mov     [rsp+0E0h+var_B8], rdi
0x18002ce47  lea     rax, [rbp+57h+dwBytes]
0x18002ce4b  mov     [rsp+0E0h+var_C0], rax
0x18002ce50  xor     r9d, r9d
0x18002ce53  xor     r8d, r8d
0x18002ce56  lea     rdx, [rbp+57h+var_90]
0x18002ce5a  mov     rcx, rbx
0x18002ce5d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18002ce63  test    eax, eax
0x18002ce65  jnz     short loc_18002CE8E
0x18002ce67  call    cs:__imp_GetLastError
0x18002ce6d  cmp     eax, 7Ah ; 'z'
0x18002ce70  jz      short loc_18002CE8E
0x18002ce72  mov     [rsp+0E0h+var_B8], rdi; unsigned __int16 *
0x18002ce77  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x18002ce7c  xor     r9d, r9d; unsigned __int16 *
0x18002ce7f  mov     r8d, eax; unsigned int
0x18002ce82  mov     edx, esi; unsigned int
0x18002ce84  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002ce89  jmp     loc_18002CF1E
0x18002ce8e  mov     edi, dword ptr [rbp+57h+dwBytes]
0x18002ce91  call    cs:__imp_GetProcessHeap
0x18002ce97  mov     r8d, edi; dwBytes
0x18002ce9a  mov     edx, 8; dwFlags
0x18002ce9f  mov     rcx, rax; hHeap
0x18002cea2  call    cs:__imp_HeapAlloc
0x18002cea8  mov     r14, rax
0x18002ceab  mov     [rbp+57h+var_98], rax
0x18002ceaf  xor     edi, edi
0x18002ceb1  test    rax, rax
0x18002ceb4  jz      loc_18002D040
0x18002ceba  mov     dword ptr [rax], 8
0x18002cec0  lea     rax, [rbp+57h+var_70]
0x18002cec4  mov     [rsp+0E0h+var_B8], rax
0x18002cec9  mov     [rsp+0E0h+var_C0], rdi
0x18002cece  mov     r9d, dword ptr [rbp+57h+dwBytes]
0x18002ced2  mov     r8, r14
0x18002ced5  lea     rdx, [rbp+57h+var_90]
0x18002ced9  mov     rcx, rbx
0x18002cedc  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18002cee2  test    eax, eax
0x18002cee4  jnz     short loc_18002CF05
0x18002cee6  call    cs:__imp_GetLastError
0x18002ceec  mov     [rsp+0E0h+var_B8], rdi; unsigned __int16 *
0x18002cef1  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x18002cef6  xor     r9d, r9d; unsigned __int16 *
0x18002cef9  mov     r8d, eax; unsigned int
0x18002cefc  mov     edx, esi; unsigned int
0x18002cefe  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002cf03  jmp     short loc_18002CF16
0x18002cf05  lea     rdx, [r14+4]; lpString2
0x18002cf09  mov     rcx, r12; lpString1
0x18002cf0c  call    cs:__imp_lstrcmpiW
0x18002cf12  test    eax, eax
0x18002cf14  jz      short loc_18002CF26
0x18002cf16  mov     rcx, r14; unsigned __int16 *
0x18002cf19  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002cf1e  inc     r15d
0x18002cf21  jmp     loc_18002CE19
0x18002cf26  lea     rax, [rbp+57h+var_B0]
0x18002cf2a  mov     [rsp+0E0h+var_C0], rax
0x18002cf2f  xor     r9d, r9d
0x18002cf32  xor     r8d, r8d
0x18002cf35  lea     rdx, [rbp+57h+var_70]
0x18002cf39  mov     rcx, rbx
0x18002cf3c  call    cs:__imp_DevObjGetDeviceInstanceId
0x18002cf42  test    eax, eax
0x18002cf44  jnz     short loc_18002CF7D
0x18002cf46  call    cs:__imp_GetLastError
0x18002cf4c  mov     edi, eax
0x18002cf4e  cmp     eax, 7Ah ; 'z'
0x18002cf51  jz      short loc_18002CF7D
0x18002cf53  xor     r15d, r15d
0x18002cf56  mov     [rsp+0E0h+var_B8], r15; unsigned __int16 *
0x18002cf5b  mov     [rsp+0E0h+var_C0], r15; unsigned __int16 *
0x18002cf60  xor     r9d, r9d; unsigned __int16 *
0x18002cf63  mov     r8d, eax; unsigned int
0x18002cf66  mov     edx, esi; unsigned int
0x18002cf68  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002cf6d  nop
0x18002cf6e  mov     rcx, r14; unsigned __int16 *
0x18002cf71  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002cf76  mov     ebx, edi
0x18002cf78  jmp     loc_18002D085
0x18002cf7d  mov     edi, [rbp+57h+var_B0]
0x18002cf80  add     rdi, rdi
0x18002cf83  call    cs:__imp_GetProcessHeap
0x18002cf89  mov     r8, rdi; dwBytes
0x18002cf8c  mov     edx, 8; dwFlags
0x18002cf91  mov     rcx, rax; hHeap
0x18002cf94  call    cs:__imp_HeapAlloc
0x18002cf9a  mov     rdi, rax
0x18002cf9d  mov     [rbp+57h+var_A0], rax
0x18002cfa1  xor     r15d, r15d
0x18002cfa4  test    rax, rax
0x18002cfa7  jnz     short loc_18002CFD1
0x18002cfa9  mov     [rsp+0E0h+var_B8], r15; unsigned __int16 *
0x18002cfae  mov     [rsp+0E0h+var_C0], r15; unsigned __int16 *
0x18002cfb3  xor     r9d, r9d; unsigned __int16 *
0x18002cfb6  lea     ebx, [rax+0Eh]
0x18002cfb9  mov     r8d, ebx; unsigned int
0x18002cfbc  mov     edx, esi; unsigned int
0x18002cfbe  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002cfc3  nop
0x18002cfc4  mov     rcx, r14; unsigned __int16 *
0x18002cfc7  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002cfcc  jmp     loc_18002D085
0x18002cfd1  lea     rax, [rbp+57h+var_B0]
0x18002cfd5  mov     [rsp+0E0h+var_C0], rax
0x18002cfda  mov     r9d, [rbp+57h+var_B0]
0x18002cfde  mov     r8, rdi
0x18002cfe1  lea     rdx, [rbp+57h+var_70]
0x18002cfe5  mov     rcx, rbx
0x18002cfe8  call    cs:__imp_DevObjGetDeviceInstanceId
0x18002cfee  test    eax, eax
0x18002cff0  jnz     short loc_18002D02F
0x18002cff2  call    cs:__imp_GetLastError
0x18002cff8  mov     ebx, eax
0x18002cffa  mov     [rsp+0E0h+var_B8], r15; unsigned __int16 *
0x18002cfff  mov     [rsp+0E0h+var_C0], r15; unsigned __int16 *
0x18002d004  xor     r9d, r9d; unsigned __int16 *
0x18002d007  mov     r8d, eax; unsigned int
0x18002d00a  mov     edx, esi; unsigned int
0x18002d00c  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d011  nop
0x18002d012  mov     rcx, r14; unsigned __int16 *
0x18002d015  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002d01a  nop
0x18002d01b  lea     rcx, [rbp+57h+dwBytes+4]
0x18002d01f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18002d024  nop
0x18002d025  mov     rcx, rdi; unsigned __int16 *
0x18002d028  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002d02d  jmp     short loc_18002D08F
0x18002d02f  mov     ebx, r15d
0x18002d032  mov     rcx, r14; unsigned __int16 *
0x18002d035  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002d03a  mov     [r13+0], rdi
0x18002d03e  jmp     short loc_18002D085
0x18002d040  mov     [rsp+0E0h+var_B8], rdi; unsigned __int16 *
0x18002d045  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x18002d04a  xor     r9d, r9d; unsigned __int16 *
0x18002d04d  lea     ebx, [r9+0Eh]
0x18002d051  mov     r8d, ebx; unsigned int
0x18002d054  mov     edx, esi; unsigned int
0x18002d056  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d05b  nop
0x18002d05c  jmp     short loc_18002D085
0x18002d05e  call    cs:__imp_GetLastError
0x18002d064  mov     ebx, eax
0x18002d066  cmp     eax, 103h
0x18002d06b  jz      short loc_18002D085
0x18002d06d  mov     edx, esi; unsigned int
0x18002d06f  mov     [rsp+0E0h+var_B8], rdi; unsigned __int16 *
0x18002d074  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x18002d079  xor     r9d, r9d; unsigned __int16 *
0x18002d07c  mov     r8d, eax; unsigned int
0x18002d07f  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d084  nop
0x18002d085  lea     rcx, [rbp+57h+dwBytes+4]
0x18002d089  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18002d08e  nop
0x18002d08f  mov     eax, ebx
0x18002d091  mov     rcx, [rbp+57h+var_40]
0x18002d095  xor     rcx, rsp; StackCookie
0x18002d098  call    __security_check_cookie
0x18002d09d  mov     rbx, [rsp+0E0h+arg_10]
0x18002d0a5  add     rsp, 0B0h
0x18002d0ac  pop     r15
0x18002d0ae  pop     r14
0x18002d0b0  pop     r13
0x18002d0b2  pop     r12
0x18002d0b4  pop     rdi
0x18002d0b5  pop     rsi
0x18002d0b6  pop     rbp
0x18002d0b7  retn
```
