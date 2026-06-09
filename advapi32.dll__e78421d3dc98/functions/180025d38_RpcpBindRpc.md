# RpcpBindRpc

- ea: `0x180025d38`
- end: `0x180025fe4`
- name: `RpcpBindRpc`
- size: `684`
- prototype: `__int64 __fastcall(char *Src, __int64, __int64, RPC_BINDING_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025c50`
- `0x180063730`

## callees

- `0x180025d38`
- `0x180039cb0`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180025e3c`
- `msvcrt!_wcsnicmp` at `0x180025ea1`
- `msvcrt!_wcsnicmp` at `0x180025e3c`
- `msvcrt!_wcsnicmp` at `0x180025ea1`
- `KERNELBASE!LocalAlloc` at `0x180025dd4`
- `KERNELBASE!LocalAlloc` at `0x180025e5b`
- `KERNELBASE!LocalAlloc` at `0x180025ec6`
- `KERNELBASE!LocalAlloc` at `0x180025dd4`
- `KERNELBASE!LocalAlloc` at `0x180025e5b`
- `KERNELBASE!LocalAlloc` at `0x180025ec6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025e20`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025e86`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025e20`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025e86`
- `KERNEL32!LocalFree` at `0x180025eb2`
- `KERNEL32!LocalFree` at `0x180025f1b`
- `KERNEL32!LocalFree` at `0x180025f64`
- `KERNEL32!LocalFree` at `0x180025fb8`
- `KERNEL32!LocalFree` at `0x180025eb2`
- `KERNEL32!LocalFree` at `0x180025f1b`
- `KERNEL32!LocalFree` at `0x180025f64`
- `KERNEL32!LocalFree` at `0x180025fb8`
- `RPCRT4!RpcStringFreeW` at `0x180025f85`
- `RPCRT4!RpcStringFreeW` at `0x180025f85`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025f79`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025f79`
- `RPCRT4!RpcStringBindingComposeW` at `0x180025f59`
- `RPCRT4!RpcStringBindingComposeW` at `0x180025f59`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  char *v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  __int64 v16; // rcx
  const wchar_t *v17; // r8
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rcx
  RPC_STATUS v21; // ebx
  RPC_STATUS v22; // ebx
  int v23; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = Src;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !Src )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&Src[2 * v7] );
  if ( !*(_WORD *)Src )
    goto LABEL_26;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_27;
    v5 = Src + 4;
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
      if ( v7 == nSize && !_wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( *(_WORD *)&v5[2 * v7 - 2] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(_wcsnicmp(v13, (const wchar_t *)v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v15 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_44;
  }
  v16 = 2147483646;
  v17 = L"\\PIPE\\";
  v18 = 14;
  do
  {
    if ( !v16 )
      break;
    if ( !*v17 )
      break;
    *v14++ = *v17++;
    --v16;
    --v18;
  }
  while ( v18 );
  v19 = v14 - 1;
  if ( v18 )
    v19 = v14;
  *v19 = 0;
  v20 = v15;
  if ( v18 )
  {
    if ( (int)RtlStringCbCatW(v15, 28, v17) >= 0 )
    {
      v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v15, 0, &String);
      LocalFree(v15);
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
        goto LABEL_44;
      }
      goto LABEL_21;
    }
    v20 = v15;
  }
  LocalFree(v20);
  v8 = -1073741811;
LABEL_44:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x180025d38  mov     [rsp-38h+arg_8], rbx
0x180025d3d  push    rbp
0x180025d3e  push    rsi
0x180025d3f  push    rdi
0x180025d40  push    r12
0x180025d42  push    r13
0x180025d44  push    r14
0x180025d46  push    r15
0x180025d48  mov     rbp, rsp
0x180025d4b  sub     rsp, 70h
0x180025d4f  mov     rax, cs:__security_cookie
0x180025d56  xor     rax, rsp
0x180025d59  mov     [rbp+var_10], rax
0x180025d5d  xor     r13d, r13d
0x180025d60  mov     r12, r9
0x180025d63  mov     [rbp+String], r13
0x180025d67  mov     rdi, rcx
0x180025d6a  mov     [rbp+nSize], r13d
0x180025d6e  mov     r14d, r13d
0x180025d71  mov     [r9], r13
0x180025d74  test    rcx, rcx
0x180025d77  jz      loc_180025EBA
0x180025d7d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025d81  inc     rbx
0x180025d84  cmp     [rcx+rbx*2], r13w
0x180025d89  jnz     short loc_180025D81
0x180025d8b  cmp     [rcx], r13w
0x180025d8f  jz      loc_180025EBA
0x180025d95  mov     esi, 5Ch ; '\'
0x180025d9a  cmp     [rcx], si
0x180025d9d  jnz     short loc_180025DCA
0x180025d9f  cmp     [rcx+2], si
0x180025da3  jnz     short loc_180025DAB
0x180025da5  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180025da9  jnz     short loc_180025DB5
0x180025dab  mov     ebx, 0C0000122h
0x180025db0  jmp     loc_180025FBE
0x180025db5  lea     rax, [rcx+4]
0x180025db9  mov     rsi, rdi
0x180025dbc  test    rax, rax
0x180025dbf  jz      loc_180025EBD
0x180025dc5  mov     rdi, rax
0x180025dc8  jmp     short loc_180025E09
0x180025dca  lea     rdx, ds:6[rbx*2]; uBytes
0x180025dd2  xor     ecx, ecx; uFlags
0x180025dd4  call    cs:__imp_LocalAlloc
0x180025dda  mov     r14, rax
0x180025ddd  test    rax, rax
0x180025de0  jnz     short loc_180025DEC
0x180025de2  mov     ebx, 0C0000017h
0x180025de7  jmp     loc_180025FBE
0x180025dec  lea     r8, ds:2[rbx*2]; Size
0x180025df4  mov     dword ptr [rax], 5C005Ch
0x180025dfa  lea     rcx, [rax+4]; void *
0x180025dfe  mov     rdx, rdi; Src
0x180025e01  call    memcpy_0
0x180025e06  mov     rsi, r14
0x180025e09  cmp     rbx, 0Fh
0x180025e0d  ja      short loc_180025E46
0x180025e0f  lea     r8, [rbp+nSize]; nSize
0x180025e13  mov     [rbp+nSize], 10h
0x180025e1a  lea     rdx, [rbp+Buffer]; lpBuffer
0x180025e1e  xor     ecx, ecx; NameType
0x180025e20  call    cs:__imp_GetComputerNameExW
0x180025e26  test    eax, eax
0x180025e28  jz      short loc_180025E46
0x180025e2a  mov     eax, [rbp+nSize]
0x180025e2d  cmp     rbx, rax
0x180025e30  jnz     short loc_180025E46
0x180025e32  mov     r8, rbx; MaxCount
0x180025e35  lea     rcx, [rbp+Buffer]; String1
0x180025e39  mov     rdx, rdi; String2
0x180025e3c  call    cs:__imp__wcsnicmp
0x180025e42  test    eax, eax
0x180025e44  jz      short loc_180025EBA
0x180025e46  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180025e4c  lea     r15, [rbx-1]
0x180025e50  mov     edx, 20Ah; uBytes
0x180025e55  cmovnz  r15, rbx
0x180025e59  xor     ecx, ecx; uFlags
0x180025e5b  call    cs:__imp_LocalAlloc
0x180025e61  mov     rbx, rax
0x180025e64  test    rax, rax
0x180025e67  jnz     short loc_180025E73
0x180025e69  mov     ebx, 0C0000017h
0x180025e6e  jmp     loc_180025FB0
0x180025e73  lea     r8, [rbp+nSize]; nSize
0x180025e77  mov     [rbp+nSize], 105h
0x180025e7e  mov     rdx, rbx; lpBuffer
0x180025e81  mov     ecx, 3; NameType
0x180025e86  call    cs:__imp_GetComputerNameExW
0x180025e8c  test    eax, eax
0x180025e8e  jz      short loc_180025EAF
0x180025e90  mov     eax, [rbp+nSize]
0x180025e93  cmp     r15, rax
0x180025e96  jnz     short loc_180025EAF
0x180025e98  mov     r8, r15; MaxCount
0x180025e9b  mov     rdx, rdi; String2
0x180025e9e  mov     rcx, rbx; String1
0x180025ea1  call    cs:__imp__wcsnicmp
0x180025ea7  neg     eax
0x180025ea9  sbb     rcx, rcx
0x180025eac  and     rsi, rcx
0x180025eaf  mov     rcx, rbx; hMem
0x180025eb2  call    cs:__imp_LocalFree
0x180025eb8  jmp     short loc_180025EBD
0x180025eba  mov     rsi, r13
0x180025ebd  mov     ebx, 1Ch
0x180025ec2  xor     ecx, ecx; uFlags
0x180025ec4  mov     edx, ebx; uBytes
0x180025ec6  call    cs:__imp_LocalAlloc
0x180025ecc  mov     rdi, rax
0x180025ecf  test    rax, rax
0x180025ed2  jz      short loc_180025E69
0x180025ed4  mov     ecx, 7FFFFFFEh
0x180025ed9  lea     r8, aPipe; "\\PIPE\\"
0x180025ee0  lea     edx, [rbx-0Eh]
0x180025ee3  test    rcx, rcx
0x180025ee6  jz      short loc_180025F07
0x180025ee8  movzx   r9d, word ptr [r8]
0x180025eec  test    r9w, r9w
0x180025ef0  jz      short loc_180025F07
0x180025ef2  mov     [rax], r9w
0x180025ef6  add     r8, 2
0x180025efa  add     rax, 2
0x180025efe  dec     rcx
0x180025f01  sub     rdx, 1
0x180025f05  jnz     short loc_180025EE3
0x180025f07  test    rdx, rdx
0x180025f0a  lea     rcx, [rax-2]
0x180025f0e  cmovnz  rcx, rax
0x180025f12  mov     [rcx], r13w
0x180025f16  mov     rcx, rdi; hMem
0x180025f19  jnz     short loc_180025F2B
0x180025f1b  call    cs:__imp_LocalFree
0x180025f21  mov     ebx, 0C000000Dh
0x180025f26  jmp     loc_180025FB0
0x180025f2b  mov     rdx, rbx
0x180025f2e  call    RtlStringCbCatW
0x180025f33  test    eax, eax
0x180025f35  jns     short loc_180025F3C
0x180025f37  mov     rcx, rdi
0x180025f3a  jmp     short loc_180025F1B
0x180025f3c  lea     rax, [rbp+String]
0x180025f40  mov     r9, rdi; Endpoint
0x180025f43  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180025f48  lea     rdx, ProtSeq; "ncacn_np"
0x180025f4f  mov     r8, rsi; NetworkAddr
0x180025f52  mov     [rsp+70h+Options], r13; Options
0x180025f57  xor     ecx, ecx; ObjUuid
0x180025f59  call    cs:__imp_RpcStringBindingComposeW
0x180025f5f  mov     rcx, rdi; hMem
0x180025f62  mov     ebx, eax
0x180025f64  call    cs:__imp_LocalFree
0x180025f6a  test    ebx, ebx
0x180025f6c  jnz     loc_180025E69
0x180025f72  mov     rcx, [rbp+String]; StringBinding
0x180025f76  mov     rdx, r12; Binding
0x180025f79  call    cs:__imp_RpcBindingFromStringBindingW
0x180025f7f  lea     rcx, [rbp+String]; String
0x180025f83  mov     ebx, eax
0x180025f85  call    cs:__imp_RpcStringFreeW
0x180025f8b  test    ebx, ebx
0x180025f8d  jz      short loc_180025FAD
0x180025f8f  lea     eax, [rbx-6AAh]
0x180025f95  mov     [r12], r13
0x180025f99  mov     ebx, 0C0000017h
0x180025f9e  cmp     eax, 1
0x180025fa1  mov     ecx, 0C0000122h
0x180025fa6  cmova   ecx, ebx
0x180025fa9  mov     ebx, ecx
0x180025fab  jmp     short loc_180025FB0
0x180025fad  mov     ebx, r13d
0x180025fb0  test    r14, r14
0x180025fb3  jz      short loc_180025FBE
0x180025fb5  mov     rcx, r14; hMem
0x180025fb8  call    cs:__imp_LocalFree
0x180025fbe  mov     eax, ebx
0x180025fc0  mov     rcx, [rbp+var_10]
0x180025fc4  xor     rcx, rsp; StackCookie
0x180025fc7  call    __security_check_cookie
0x180025fcc  mov     rbx, [rsp+70h+arg_8]
0x180025fd4  add     rsp, 70h
0x180025fd8  pop     r15
0x180025fda  pop     r14
0x180025fdc  pop     r13
0x180025fde  pop     r12
0x180025fe0  pop     rdi
0x180025fe1  pop     rsi
0x180025fe2  pop     rbp
0x180025fe3  retn
```
