# WsCreateLinkedConnection

- ea: `0x180007728`
- end: `0x1800078e4`
- name: `WsCreateLinkedConnection`
- size: `444`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001710`

## callees

- `0x180005a60`
- `0x180007728`
- `0x18000b5c0`
- `0x18000dd94`
- `0x18001e420`
- `0x18002a4ec`
- `0x18002ecc0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800077c4`
- `ntdll!NtFsControlFile` at `0x1800077c4`
- `RPCRT4!RpcImpersonateClient` at `0x180007776`
- `RPCRT4!RpcImpersonateClient` at `0x180007776`
- `RPCRT4!RpcRevertToSelf` at `0x1800077d9`
- `RPCRT4!RpcRevertToSelf` at `0x1800077d9`

## pseudocode

```c
__int64 __fastcall WsCreateLinkedConnection(HANDLE FileHandle, __int64 a2, void *a3)
{
  NTSTATUS Status; // ebx
  RPC_STATUS v6; // eax
  int v7; // r8d
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  RPC_STATUS v10; // eax
  int v11; // r8d
  STRSAFE_LPCWSTR v13; // r11
  size_t v14; // rdx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-69h] BYREF
  int InputBuffer; // [rsp+60h] [rbp-59h] BYREF
  __int64 v17; // [rsp+64h] [rbp-55h]
  NTSTATUS v18; // [rsp+74h] [rbp-45h]
  wchar_t pszDest[60]; // [rsp+78h] [rbp-41h] BYREF

  Status = 0;
  IoStatusBlock.Pointer = 0;
  if ( a2 )
  {
    StringCchCopyW(pszDest, 0x20u, L"\\??\\");
    if ( StringCchCatW(pszDest, 0x20u, v13) < 0 )
      return 2123;
    StringCbLengthW(pszDest, v14, (size_t *)&IoStatusBlock);
    Status = IoStatusBlock.Status;
  }
  v18 = Status;
  InputBuffer = 3;
  v17 = 6;
  v6 = RpcImpersonateClient(0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, (unsigned int)"unknown", 0, v6);
    }
    return 5;
  }
  else
  {
    IoStatusBlock = 0;
    v8 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401D8u, &InputBuffer, Status + 36, a3, 8u);
    if ( v8 >= 0 )
      v8 = IoStatusBlock.Status;
    v9 = WsMapStatus((unsigned int)v8);
    v10 = RpcRevertToSelf();
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, (unsigned int)"unknown", 0, v10);
      }
      __fastfail(7u);
    }
    return v9;
  }
}

```

## disassembly

```asm
0x180007728  mov     [rsp-8+arg_18], rbx
0x18000772d  push    rbp
0x18000772e  push    rsi
0x18000772f  push    rdi
0x180007730  lea     rbp, [rsp-47h]
0x180007735  sub     rsp, 100h
0x18000773c  mov     rax, cs:__security_cookie
0x180007743  xor     rax, rsp
0x180007746  mov     [rbp+57h+var_20], rax
0x18000774a  xor     ebx, ebx
0x18000774c  mov     rsi, r8
0x18000774f  mov     qword ptr [rbp+57h+var_C0], rbx
0x180007753  mov     r11, rdx
0x180007756  mov     rdi, rcx
0x180007759  test    rdx, rdx
0x18000775c  jnz     loc_180007808
0x180007762  xor     ecx, ecx; BindingHandle
0x180007764  mov     [rbp+57h+var_9C], ebx
0x180007767  mov     [rbp+57h+var_B0], 3
0x18000776e  mov     [rbp+57h+var_AC], 6
0x180007776  call    cs:__imp_RpcImpersonateClient
0x18000777c  test    eax, eax
0x18000777e  jnz     loc_18000784E
0x180007784  mov     [rsp+110h+OutputBufferLength], 8; OutputBufferLength
0x18000778c  lea     eax, [rbx+24h]
0x18000778f  mov     [rsp+110h+OutputBuffer], rsi; OutputBuffer
0x180007794  xorps   xmm0, xmm0
0x180007797  mov     [rsp+110h+InputBufferLength], eax; InputBufferLength
0x18000779b  xor     r9d, r9d; ApcContext
0x18000779e  lea     rax, [rbp+57h+var_B0]
0x1800077a2  xor     r8d, r8d; ApcRoutine
0x1800077a5  mov     [rsp+110h+InputBuffer], rax; InputBuffer
0x1800077aa  xor     edx, edx; Event
0x1800077ac  lea     rax, [rbp+57h+var_C0]
0x1800077b0  mov     [rsp+110h+FsControlCode], 1401D8h; FsControlCode
0x1800077b8  mov     rcx, rdi; FileHandle
0x1800077bb  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x1800077c0  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800077c4  call    cs:__imp_NtFsControlFile
0x1800077ca  test    eax, eax
0x1800077cc  cmovns  eax, dword ptr [rbp+57h+var_C0]
0x1800077d0  mov     ecx, eax
0x1800077d2  call    WsMapStatus
0x1800077d7  mov     ebx, eax
0x1800077d9  call    cs:__imp_RpcRevertToSelf
0x1800077df  test    eax, eax
0x1800077e1  jnz     loc_180007898
0x1800077e7  mov     eax, ebx
0x1800077e9  mov     rcx, [rbp+57h+var_20]
0x1800077ed  xor     rcx, rsp; StackCookie
0x1800077f0  call    __security_check_cookie
0x1800077f5  mov     rbx, [rsp+110h+arg_18]
0x1800077fd  add     rsp, 100h
0x180007804  pop     rdi
0x180007805  pop     rsi
0x180007806  pop     rbp
0x180007807  retn
0x180007808  mov     ebx, 20h ; ' '
0x18000780d  lea     r8, asc_18003AA90; "\\??\\"
0x180007814  mov     edx, ebx; cchDest
0x180007816  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18000781a  call    StringCchCopyW
0x18000781f  mov     r8, r11; pszSrc
0x180007822  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180007826  mov     edx, ebx; cchDest
0x180007828  call    StringCchCatW
0x18000782d  test    eax, eax
0x18000782f  jns     short loc_180007838
0x180007831  mov     eax, 84Bh
0x180007836  jmp     short loc_1800077E9
0x180007838  lea     r8, [rbp+57h+var_C0]; pcbLength
0x18000783c  lea     rcx, [rbp+57h+pszDest]; psz
0x180007840  call    StringCbLengthW
0x180007845  mov     rbx, qword ptr [rbp+57h+var_C0]
0x180007849  jmp     loc_180007762
0x18000784e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180007855  lea     rdx, WPP_GLOBAL_Control
0x18000785c  cmp     rcx, rdx
0x18000785f  jz      short loc_18000788E
0x180007861  test    byte ptr [rcx+1Ch], 4
0x180007865  jz      short loc_18000788E
0x180007867  cmp     byte ptr [rcx+19h], 1
0x18000786b  jb      short loc_18000788E
0x18000786d  mov     rcx, [rcx+10h]
0x180007871  lea     r9, aUnknown; "unknown"
0x180007878  mov     [rsp+110h+FsControlCode], eax
0x18000787c  mov     edx, 0Ah
0x180007881  mov     dword ptr [rsp+110h+IoStatusBlock], 0
0x180007889  call    WPP_SF_sdL
0x18000788e  mov     eax, 5
0x180007893  jmp     loc_1800077E9
0x180007898  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000789f  lea     rdx, WPP_GLOBAL_Control
0x1800078a6  cmp     rcx, rdx
0x1800078a9  jz      short loc_1800078D8
0x1800078ab  test    byte ptr [rcx+1Ch], 4
0x1800078af  jz      short loc_1800078D8
0x1800078b1  cmp     byte ptr [rcx+19h], 1
0x1800078b5  jb      short loc_1800078D8
0x1800078b7  mov     rcx, [rcx+10h]
0x1800078bb  lea     r9, aUnknown; "unknown"
0x1800078c2  mov     [rsp+110h+FsControlCode], eax
0x1800078c6  mov     edx, 0Bh
0x1800078cb  mov     dword ptr [rsp+110h+IoStatusBlock], 0
0x1800078d3  call    WPP_SF_sdL
0x1800078d8  mov     ecx, 7
0x1800078dd  int     29h; Win8: RtlFailFast(ecx)
0x1800078df  jmp     loc_1800077E7
```
