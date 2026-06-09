# Microsoft::CoreUI::HvSockets::HvSocket::StartAsyncOperation(bool,void *,uint,void *,Microsoft::CoreUI::Support::Win32Event,uint,CFlat::Ref<bool>)

- ea: `0x1800b5364`
- end: `0x1800b5402`
- name: `?StartAsyncOperation@HvSocket@HvSockets@CoreUI@Microsoft@@AEAA_N_NPEAXI1UWin32Event@Support@34@IU?$Ref@_N@CFlat@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(int, int, int, int, LPOVERLAPPED, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800992c0`
- `0x1800b79d4`
- `0x1800b7a84`

## callees

- `0x180007d80`
- `0x1800b5364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b53de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b53de`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b53c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b53c6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b53bb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b53bb`

## pseudocode

```c
bool __fastcall Microsoft::CoreUI::HvSockets::HvSocket::StartAsyncOperation(
        void **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPOVERLAPPED lpOverlapped,
        void *a6,
        unsigned int a7,
        _BYTE *a8)
{
  unsigned int v8; // r10d
  void *v9; // rcx
  void *v10; // rdx
  DWORD v11; // r8d
  BOOL File; // eax
  bool v13; // zf

  v8 = a4;
  LOBYTE(a4) = a2;
  if ( !v8 || a7 >= v8 )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      a1,
      a2,
      a3,
      a4);
  v9 = *a1;
  v10 = (void *)(a3 + a7);
  *(_OWORD *)&lpOverlapped->Internal = 0;
  *(_OWORD *)&lpOverlapped->Offset = 0;
  lpOverlapped->hEvent = a6;
  v11 = v8 - a7;
  if ( (_BYTE)a4 )
    File = ReadFile(v9, v10, v11, 0, lpOverlapped);
  else
    File = WriteFile(v9, v10, v11, 0, lpOverlapped);
  *a8 = File;
  v13 = !File;
  if ( !File )
    v13 = GetLastError() != 997;
  return !v13;
}

```

## disassembly

```asm
0x1800b5364  mov     [rsp+arg_0], rbx
0x1800b5369  push    rdi
0x1800b536a  sub     rsp, 30h
0x1800b536e  mov     r10d, r9d
0x1800b5371  mov     edi, 1
0x1800b5376  mov     r9b, dl
0x1800b5379  cmp     r10d, edi
0x1800b537c  jb      short loc_1800B53FC
0x1800b537e  mov     eax, [rsp+38h+arg_30]
0x1800b5382  cmp     eax, r10d
0x1800b5385  jnb     short loc_1800B53FC
0x1800b5387  mov     rcx, [rcx]; hFile
0x1800b538a  lea     rdx, [r8+rax]; lpBuffer
0x1800b538e  mov     r8, [rsp+38h+arg_20]
0x1800b5393  sub     r10d, eax
0x1800b5396  mov     rax, [rsp+38h+arg_28]
0x1800b539b  xorps   xmm0, xmm0
0x1800b539e  mov     [rsp+38h+lpOverlapped], r8; lpOverlapped
0x1800b53a3  movups  xmmword ptr [r8], xmm0
0x1800b53a7  movups  xmmword ptr [r8+10h], xmm0
0x1800b53ac  mov     [r8+18h], rax
0x1800b53b0  mov     r8d, r10d; nNumberOfBytesToWrite
0x1800b53b3  test    r9b, r9b
0x1800b53b6  jz      short loc_1800B53C3
0x1800b53b8  xor     r9d, r9d; lpNumberOfBytesRead
0x1800b53bb  call    cs:__imp_ReadFile
0x1800b53c1  jmp     short loc_1800B53CC
0x1800b53c3  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800b53c6  call    cs:__imp_WriteFile
0x1800b53cc  test    eax, eax
0x1800b53ce  mov     ebx, eax
0x1800b53d0  mov     rax, [rsp+38h+arg_38]
0x1800b53d5  setnz   cl
0x1800b53d8  mov     [rax], cl
0x1800b53da  test    ebx, ebx
0x1800b53dc  jnz     short loc_1800B53EE
0x1800b53de  call    cs:__imp_GetLastError
0x1800b53e4  cmp     eax, 3E5h
0x1800b53e9  cmovz   ebx, edi
0x1800b53ec  test    ebx, ebx
0x1800b53ee  mov     rbx, [rsp+38h+arg_0]
0x1800b53f3  setnz   al
0x1800b53f6  add     rsp, 30h
0x1800b53fa  pop     rdi
0x1800b53fb  retn
0x1800b53fc  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
```
