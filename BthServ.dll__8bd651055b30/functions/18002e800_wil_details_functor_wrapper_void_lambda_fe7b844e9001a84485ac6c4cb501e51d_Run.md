# wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run

- ea: `0x18002e800`
- end: `0x18002e8bf`
- name: `wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002c278`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x18002e800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e87f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e860`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e860`

## string_xrefs

- `0x18002e8aa`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run(__int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rcx
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  BytesReturned = 0;
  v2 = **(__int64 ***)v1;
  if ( v2 )
    v3 = *v2;
  else
    v3 = -1;
  if ( !DeviceIoControl(
          (HANDLE)v3,
          0x4111C4u,
          **(LPVOID **)(v1 + 8),
          **(_DWORD **)(v1 + 16),
          0,
          0,
          &BytesReturned,
          **(LPOVERLAPPED **)(v1 + 24))
    && GetLastError() != 997 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    **(_DWORD **)(v1 + 32) = v8;
    v9 = wil::verify_hresult<long>(**(unsigned int **)(v1 + 32), v6, v7);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v9,
      lpOutBuffer);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e800  push    rbx
0x18002e802  sub     rsp, 40h
0x18002e806  mov     rbx, [rcx+8]
0x18002e80a  mov     [rsp+48h+BytesReturned], 0
0x18002e812  mov     rax, [rbx+18h]
0x18002e816  mov     rdx, [rax]
0x18002e819  mov     rax, [rbx+10h]
0x18002e81d  mov     r9d, [rax]; nInBufferSize
0x18002e820  mov     rax, [rbx+8]
0x18002e824  mov     r8, [rax]; lpInBuffer
0x18002e827  mov     rax, [rbx]
0x18002e82a  mov     rcx, [rax]
0x18002e82d  test    rcx, rcx
0x18002e830  jz      short loc_18002E837
0x18002e832  mov     rcx, [rcx]
0x18002e835  jmp     short loc_18002E83B
0x18002e837  or      rcx, 0FFFFFFFFFFFFFFFFh; hDevice
0x18002e83b  mov     [rsp+48h+lpOverlapped], rdx; lpOverlapped
0x18002e840  lea     rax, [rsp+48h+BytesReturned]
0x18002e845  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18002e84a  mov     edx, 4111C4h; dwIoControlCode
0x18002e84f  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x18002e857  mov     [rsp+48h+lpOutBuffer], 0; int
0x18002e860  call    cs:__imp_DeviceIoControl
0x18002e866  test    eax, eax
0x18002e868  jnz     short loc_18002E877
0x18002e86a  call    cs:__imp_GetLastError
0x18002e870  cmp     eax, 3E5h
0x18002e875  jnz     short loc_18002E87F
0x18002e877  xor     eax, eax
0x18002e879  add     rsp, 40h
0x18002e87d  pop     rbx
0x18002e87e  retn
0x18002e87f  call    cs:__imp_GetLastError
0x18002e885  mov     ecx, eax
0x18002e887  test    eax, eax
0x18002e889  jle     short loc_18002E894
0x18002e88b  movzx   ecx, ax
0x18002e88e  or      ecx, 80070000h
0x18002e894  mov     rax, [rbx+20h]
0x18002e898  mov     [rax], ecx
0x18002e89a  mov     rcx, [rbx+20h]
0x18002e89e  mov     ecx, [rcx]
0x18002e8a0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e8a5  mov     rcx, [rsp+48h]; this
0x18002e8aa  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e8b1  mov     r9d, eax; char *
0x18002e8b4  mov     edx, 0D6h; void *
0x18002e8b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
