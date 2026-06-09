# RpcpBindRpc

- ea: `0x1800d9bc0`
- end: `0x1800d9e7b`
- name: `RpcpBindRpc`
- size: `699`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d9b50`

## callees

- `0x180004e35`
- `0x180004f86`
- `0x1800d9bc0`
- `0x1800d9e84`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9c5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9ce2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9d4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9c5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9ce2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d9d4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800d9ca8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800d9d0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800d9ca8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800d9d0d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800d9e00`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800d9e00`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800d9de0`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800d9de0`
- `RPCRT4!RpcStringFreeW` at `0x1800d9e0c`
- `RPCRT4!RpcStringFreeW` at `0x1800d9e0c`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(RPC_WSTR NetworkAddr, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  RPC_WSTR v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  unsigned __int16 *v16; // rdi
  __int64 v17; // r11
  unsigned __int64 v18; // r8
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  RPC_STATUS v21; // ebx
  RPC_STATUS v22; // ebx
  int v23; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = NetworkAddr;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !NetworkAddr )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( NetworkAddr[v7] );
  if ( !*NetworkAddr )
    goto LABEL_26;
  if ( *NetworkAddr == 92 )
  {
    if ( NetworkAddr[1] != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)NetworkAddr;
    if ( NetworkAddr == (RPC_WSTR)-4LL )
      goto LABEL_27;
    v5 = NetworkAddr + 2;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = (unsigned __int64)v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !wcsnicmp_0(Buffer, v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( v5[v7 - 1] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(wcsnicmp_0(v13, v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_41;
  }
  if ( (int)RtlStringCopyWorkerW(v14, 14, v15, L"\\PIPE\\") >= 0 )
  {
    v18 = (unsigned int)v17;
    v19 = v16;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
    {
      v20 = (v17 - v18) & ((unsigned __int128)-(__int128)v18 >> 64);
      if ( (int)RtlStringCopyWorkerW(&v16[v20], v17 - v20, v18, L"lsarpc") >= 0 )
      {
        v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v16, 0, &String);
        LocalFree(v16);
        if ( !v21 )
        {
          v22 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v22 )
          {
            *a4 = 0;
            v23 = -1073741534;
            if ( (unsigned int)(v22 - 1706) > 1 )
              v23 = -1073741801;
            v8 = v23;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_41;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v16);
  v8 = -1073741811;
LABEL_41:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x1800d9bc0  mov     [rsp-38h+arg_8], rbx
0x1800d9bc5  push    rbp
0x1800d9bc6  push    rsi
0x1800d9bc7  push    rdi
0x1800d9bc8  push    r12
0x1800d9bca  push    r13
0x1800d9bcc  push    r14
0x1800d9bce  push    r15
0x1800d9bd0  mov     rbp, rsp
0x1800d9bd3  sub     rsp, 70h
0x1800d9bd7  mov     rax, cs:__security_cookie
0x1800d9bde  xor     rax, rsp
0x1800d9be1  mov     [rbp+var_10], rax
0x1800d9be5  xor     r13d, r13d
0x1800d9be8  mov     r12, r9
0x1800d9beb  mov     [rbp+String], r13
0x1800d9bef  mov     rdi, rcx
0x1800d9bf2  mov     [rbp+nSize], r13d
0x1800d9bf6  mov     r14d, r13d
0x1800d9bf9  mov     [r9], r13
0x1800d9bfc  test    rcx, rcx
0x1800d9bff  jz      loc_1800D9D40
0x1800d9c05  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d9c09  inc     rbx
0x1800d9c0c  cmp     [rcx+rbx*2], r13w
0x1800d9c11  jnz     short loc_1800D9C09
0x1800d9c13  cmp     [rcx], r13w
0x1800d9c17  jz      loc_1800D9D40
0x1800d9c1d  mov     esi, 5Ch ; '\'
0x1800d9c22  cmp     [rcx], si
0x1800d9c25  jnz     short loc_1800D9C52
0x1800d9c27  cmp     [rcx+2], si
0x1800d9c2b  jnz     short loc_1800D9C33
0x1800d9c2d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800d9c31  jnz     short loc_1800D9C3D
0x1800d9c33  mov     ebx, 0C0000122h
0x1800d9c38  jmp     loc_1800D9E55
0x1800d9c3d  lea     rax, [rcx+4]
0x1800d9c41  mov     rsi, rdi
0x1800d9c44  test    rax, rax
0x1800d9c47  jz      loc_1800D9D43
0x1800d9c4d  mov     rdi, rax
0x1800d9c50  jmp     short loc_1800D9C91
0x1800d9c52  lea     rdx, ds:6[rbx*2]; uBytes
0x1800d9c5a  xor     ecx, ecx; uFlags
0x1800d9c5c  call    cs:__imp_LocalAlloc
0x1800d9c62  mov     r14, rax
0x1800d9c65  test    rax, rax
0x1800d9c68  jnz     short loc_1800D9C74
0x1800d9c6a  mov     ebx, 0C0000017h
0x1800d9c6f  jmp     loc_1800D9E55
0x1800d9c74  lea     r8, ds:2[rbx*2]; Size
0x1800d9c7c  mov     dword ptr [rax], 5C005Ch
0x1800d9c82  lea     rcx, [rax+4]; void *
0x1800d9c86  mov     rdx, rdi; Src
0x1800d9c89  call    memcpy_0
0x1800d9c8e  mov     rsi, r14
0x1800d9c91  cmp     rbx, 0Fh
0x1800d9c95  ja      short loc_1800D9CCD
0x1800d9c97  lea     r8, [rbp+nSize]; nSize
0x1800d9c9b  mov     [rbp+nSize], 10h
0x1800d9ca2  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800d9ca6  xor     ecx, ecx; NameType
0x1800d9ca8  call    cs:__imp_GetComputerNameExW
0x1800d9cae  test    eax, eax
0x1800d9cb0  jz      short loc_1800D9CCD
0x1800d9cb2  mov     eax, [rbp+nSize]
0x1800d9cb5  cmp     rbx, rax
0x1800d9cb8  jnz     short loc_1800D9CCD
0x1800d9cba  mov     r8, rbx; MaxCount
0x1800d9cbd  lea     rcx, [rbp+Buffer]; String1
0x1800d9cc1  mov     rdx, rdi; String2
0x1800d9cc4  call    _wcsnicmp_0
0x1800d9cc9  test    eax, eax
0x1800d9ccb  jz      short loc_1800D9D40
0x1800d9ccd  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800d9cd3  lea     r15, [rbx-1]
0x1800d9cd7  mov     edx, 20Ah; uBytes
0x1800d9cdc  cmovnz  r15, rbx
0x1800d9ce0  xor     ecx, ecx; uFlags
0x1800d9ce2  call    cs:__imp_LocalAlloc
0x1800d9ce8  mov     rbx, rax
0x1800d9ceb  test    rax, rax
0x1800d9cee  jnz     short loc_1800D9CFA
0x1800d9cf0  mov     ebx, 0C0000017h
0x1800d9cf5  jmp     loc_1800D9E47
0x1800d9cfa  lea     r8, [rbp+nSize]; nSize
0x1800d9cfe  mov     [rbp+nSize], 105h
0x1800d9d05  mov     rdx, rbx; lpBuffer
0x1800d9d08  mov     ecx, 3; NameType
0x1800d9d0d  call    cs:__imp_GetComputerNameExW
0x1800d9d13  test    eax, eax
0x1800d9d15  jz      short loc_1800D9D35
0x1800d9d17  mov     eax, [rbp+nSize]
0x1800d9d1a  cmp     r15, rax
0x1800d9d1d  jnz     short loc_1800D9D35
0x1800d9d1f  mov     r8, r15; MaxCount
0x1800d9d22  mov     rdx, rdi; String2
0x1800d9d25  mov     rcx, rbx; String1
0x1800d9d28  call    _wcsnicmp_0
0x1800d9d2d  neg     eax
0x1800d9d2f  sbb     rcx, rcx
0x1800d9d32  and     rsi, rcx
0x1800d9d35  mov     rcx, rbx; hMem
0x1800d9d38  call    cs:__imp_LocalFree
0x1800d9d3e  jmp     short loc_1800D9D43
0x1800d9d40  mov     rsi, r13
0x1800d9d43  mov     edx, 1Ch; uBytes
0x1800d9d48  xor     ecx, ecx; uFlags
0x1800d9d4a  call    cs:__imp_LocalAlloc
0x1800d9d50  mov     rdi, rax
0x1800d9d53  test    rax, rax
0x1800d9d56  jz      short loc_1800D9CF0
0x1800d9d58  mov     r11d, 0Eh
0x1800d9d5e  lea     r9, aPipe; "\\PIPE\\"
0x1800d9d65  mov     edx, r11d
0x1800d9d68  mov     rcx, rax
0x1800d9d6b  call    RtlStringCopyWorkerW
0x1800d9d70  test    eax, eax
0x1800d9d72  js      loc_1800D9E39
0x1800d9d78  mov     r8d, r11d
0x1800d9d7b  mov     rax, rdi
0x1800d9d7e  cmp     [rax], r13w
0x1800d9d82  jz      short loc_1800D9D8E
0x1800d9d84  add     rax, 2
0x1800d9d88  sub     r8, 1
0x1800d9d8c  jnz     short loc_1800D9D7E
0x1800d9d8e  mov     rcx, r11
0x1800d9d91  mov     rax, r8
0x1800d9d94  sub     rcx, r8
0x1800d9d97  neg     rax
0x1800d9d9a  sbb     rdx, rdx
0x1800d9d9d  and     rdx, rcx
0x1800d9da0  test    r8, r8
0x1800d9da3  jz      loc_1800D9E39
0x1800d9da9  sub     r11, rdx
0x1800d9dac  lea     rcx, [rdi+rdx*2]
0x1800d9db0  mov     rdx, r11
0x1800d9db3  lea     r9, aLsarpc; "lsarpc"
0x1800d9dba  call    RtlStringCopyWorkerW
0x1800d9dbf  test    eax, eax
0x1800d9dc1  js      short loc_1800D9E39
0x1800d9dc3  lea     rax, [rbp+String]
0x1800d9dc7  mov     r9, rdi; Endpoint
0x1800d9dca  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800d9dcf  lea     rdx, ProtSeq; "ncacn_np"
0x1800d9dd6  mov     r8, rsi; NetworkAddr
0x1800d9dd9  mov     [rsp+70h+Options], r13; Options
0x1800d9dde  xor     ecx, ecx; ObjUuid
0x1800d9de0  call    cs:__imp_RpcStringBindingComposeW
0x1800d9de6  mov     rcx, rdi; hMem
0x1800d9de9  mov     ebx, eax
0x1800d9deb  call    cs:__imp_LocalFree
0x1800d9df1  test    ebx, ebx
0x1800d9df3  jnz     loc_1800D9CF0
0x1800d9df9  mov     rcx, [rbp+String]; StringBinding
0x1800d9dfd  mov     rdx, r12; Binding
0x1800d9e00  call    cs:__imp_RpcBindingFromStringBindingW
0x1800d9e06  lea     rcx, [rbp+String]; String
0x1800d9e0a  mov     ebx, eax
0x1800d9e0c  call    cs:__imp_RpcStringFreeW
0x1800d9e12  test    ebx, ebx
0x1800d9e14  jz      short loc_1800D9E34
0x1800d9e16  lea     eax, [rbx-6AAh]
0x1800d9e1c  mov     [r12], r13
0x1800d9e20  mov     ebx, 0C0000017h
0x1800d9e25  cmp     eax, 1
0x1800d9e28  mov     ecx, 0C0000122h
0x1800d9e2d  cmova   ecx, ebx
0x1800d9e30  mov     ebx, ecx
0x1800d9e32  jmp     short loc_1800D9E47
0x1800d9e34  mov     ebx, r13d
0x1800d9e37  jmp     short loc_1800D9E47
0x1800d9e39  mov     rcx, rdi; hMem
0x1800d9e3c  call    cs:__imp_LocalFree
0x1800d9e42  mov     ebx, 0C000000Dh
0x1800d9e47  test    r14, r14
0x1800d9e4a  jz      short loc_1800D9E55
0x1800d9e4c  mov     rcx, r14; hMem
0x1800d9e4f  call    cs:__imp_LocalFree
0x1800d9e55  mov     eax, ebx
0x1800d9e57  mov     rcx, [rbp+var_10]
0x1800d9e5b  xor     rcx, rsp; StackCookie
0x1800d9e5e  call    __security_check_cookie
0x1800d9e63  mov     rbx, [rsp+70h+arg_8]
0x1800d9e6b  add     rsp, 70h
0x1800d9e6f  pop     r15
0x1800d9e71  pop     r14
0x1800d9e73  pop     r13
0x1800d9e75  pop     r12
0x1800d9e77  pop     rdi
0x1800d9e78  pop     rsi
0x1800d9e79  pop     rbp
0x1800d9e7a  retn
```
