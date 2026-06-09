# RpcpBindRpc

- ea: `0x1800288b0`
- end: `0x180028bb9`
- name: `RpcpBindRpc`
- size: `777`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800287b0`
- `0x18007053c`

## callees

- `0x1800288b0`
- `0x18003df98`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800289c0`
- `msvcrt!_wcsnicmp` at `0x180028a3b`
- `msvcrt!_wcsnicmp` at `0x1800289c0`
- `msvcrt!_wcsnicmp` at `0x180028a3b`
- `KERNELBASE!LocalAlloc` at `0x18002894c`
- `KERNELBASE!LocalAlloc` at `0x1800289e9`
- `KERNELBASE!LocalAlloc` at `0x180028a6c`
- `KERNELBASE!LocalAlloc` at `0x18002894c`
- `KERNELBASE!LocalAlloc` at `0x1800289e9`
- `KERNELBASE!LocalAlloc` at `0x180028a6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002899e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180028a1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002899e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180028a1a`
- `KERNEL32!LocalFree` at `0x180028a52`
- `KERNEL32!LocalFree` at `0x180028acb`
- `KERNEL32!LocalFree` at `0x180028b20`
- `KERNEL32!LocalFree` at `0x180028b86`
- `KERNEL32!LocalFree` at `0x180028a52`
- `KERNEL32!LocalFree` at `0x180028acb`
- `KERNEL32!LocalFree` at `0x180028b20`
- `KERNEL32!LocalFree` at `0x180028b86`
- `RPCRT4!RpcStringFreeW` at `0x180028b4d`
- `RPCRT4!RpcStringFreeW` at `0x180028b4d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180028b3b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180028b3b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180028b0f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180028b0f`

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
0x1800288b0  mov     [rsp-38h+arg_8], rbx
0x1800288b5  push    rbp
0x1800288b6  push    rsi
0x1800288b7  push    rdi
0x1800288b8  push    r12
0x1800288ba  push    r13
0x1800288bc  push    r14
0x1800288be  push    r15
0x1800288c0  mov     rbp, rsp
0x1800288c3  sub     rsp, 70h
0x1800288c7  mov     rax, cs:__security_cookie
0x1800288ce  xor     rax, rsp
0x1800288d1  mov     [rbp+var_10], rax
0x1800288d5  xor     r13d, r13d
0x1800288d8  mov     r12, r9
0x1800288db  mov     [rbp+String], r13
0x1800288df  mov     rdi, rcx
0x1800288e2  mov     [rbp+nSize], r13d
0x1800288e6  mov     r14d, r13d
0x1800288e9  mov     [r9], r13
0x1800288ec  test    rcx, rcx
0x1800288ef  jz      loc_180028A60
0x1800288f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800288f9  inc     rbx
0x1800288fc  cmp     [rcx+rbx*2], r13w
0x180028901  jnz     short loc_1800288F9
0x180028903  cmp     [rcx], r13w
0x180028907  jz      loc_180028A60
0x18002890d  mov     esi, 5Ch ; '\'
0x180028912  cmp     [rcx], si
0x180028915  jnz     short loc_180028942
0x180028917  cmp     [rcx+2], si
0x18002891b  jnz     short loc_180028923
0x18002891d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180028921  jnz     short loc_18002892D
0x180028923  mov     ebx, 0C0000122h
0x180028928  jmp     loc_180028B92
0x18002892d  lea     rax, [rcx+4]
0x180028931  mov     rsi, rdi
0x180028934  test    rax, rax
0x180028937  jz      loc_180028A63
0x18002893d  mov     rdi, rax
0x180028940  jmp     short loc_180028987
0x180028942  lea     rdx, ds:6[rbx*2]; uBytes
0x18002894a  xor     ecx, ecx; uFlags
0x18002894c  call    cs:__imp_LocalAlloc
0x180028953  nop     dword ptr [rax+rax+00h]
0x180028958  mov     r14, rax
0x18002895b  test    rax, rax
0x18002895e  jnz     short loc_18002896A
0x180028960  mov     ebx, 0C0000017h
0x180028965  jmp     loc_180028B92
0x18002896a  lea     r8, ds:2[rbx*2]; Size
0x180028972  mov     dword ptr [rax], 5C005Ch
0x180028978  lea     rcx, [rax+4]; void *
0x18002897c  mov     rdx, rdi; Src
0x18002897f  call    memcpy_0
0x180028984  mov     rsi, r14
0x180028987  cmp     rbx, 0Fh
0x18002898b  ja      short loc_1800289D4
0x18002898d  lea     r8, [rbp+nSize]; nSize
0x180028991  mov     [rbp+nSize], 10h
0x180028998  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002899c  xor     ecx, ecx; NameType
0x18002899e  call    cs:__imp_GetComputerNameExW
0x1800289a5  nop     dword ptr [rax+rax+00h]
0x1800289aa  test    eax, eax
0x1800289ac  jz      short loc_1800289D4
0x1800289ae  mov     eax, [rbp+nSize]
0x1800289b1  cmp     rbx, rax
0x1800289b4  jnz     short loc_1800289D4
0x1800289b6  mov     r8, rbx; MaxCount
0x1800289b9  lea     rcx, [rbp+Buffer]; String1
0x1800289bd  mov     rdx, rdi; String2
0x1800289c0  call    cs:__imp__wcsnicmp
0x1800289c7  nop     dword ptr [rax+rax+00h]
0x1800289cc  test    eax, eax
0x1800289ce  jz      loc_180028A60
0x1800289d4  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800289da  lea     r15, [rbx-1]
0x1800289de  mov     edx, 20Ah; uBytes
0x1800289e3  cmovnz  r15, rbx
0x1800289e7  xor     ecx, ecx; uFlags
0x1800289e9  call    cs:__imp_LocalAlloc
0x1800289f0  nop     dword ptr [rax+rax+00h]
0x1800289f5  mov     rbx, rax
0x1800289f8  test    rax, rax
0x1800289fb  jnz     short loc_180028A07
0x1800289fd  mov     ebx, 0C0000017h
0x180028a02  jmp     loc_180028B7E
0x180028a07  lea     r8, [rbp+nSize]; nSize
0x180028a0b  mov     [rbp+nSize], 105h
0x180028a12  mov     rdx, rbx; lpBuffer
0x180028a15  mov     ecx, 3; NameType
0x180028a1a  call    cs:__imp_GetComputerNameExW
0x180028a21  nop     dword ptr [rax+rax+00h]
0x180028a26  test    eax, eax
0x180028a28  jz      short loc_180028A4F
0x180028a2a  mov     eax, [rbp+nSize]
0x180028a2d  cmp     r15, rax
0x180028a30  jnz     short loc_180028A4F
0x180028a32  mov     r8, r15; MaxCount
0x180028a35  mov     rdx, rdi; String2
0x180028a38  mov     rcx, rbx; String1
0x180028a3b  call    cs:__imp__wcsnicmp
0x180028a42  nop     dword ptr [rax+rax+00h]
0x180028a47  neg     eax
0x180028a49  sbb     rcx, rcx
0x180028a4c  and     rsi, rcx
0x180028a4f  mov     rcx, rbx; hMem
0x180028a52  call    cs:__imp_LocalFree
0x180028a59  nop     dword ptr [rax+rax+00h]
0x180028a5e  jmp     short loc_180028A63
0x180028a60  mov     rsi, r13
0x180028a63  mov     ebx, 1Ch
0x180028a68  xor     ecx, ecx; uFlags
0x180028a6a  mov     edx, ebx; uBytes
0x180028a6c  call    cs:__imp_LocalAlloc
0x180028a73  nop     dword ptr [rax+rax+00h]
0x180028a78  mov     rdi, rax
0x180028a7b  test    rax, rax
0x180028a7e  jz      loc_1800289FD
0x180028a84  mov     ecx, 7FFFFFFEh
0x180028a89  lea     r8, aPipe; "\\PIPE\\"
0x180028a90  lea     edx, [rbx-0Eh]
0x180028a93  test    rcx, rcx
0x180028a96  jz      short loc_180028AB7
0x180028a98  movzx   r9d, word ptr [r8]
0x180028a9c  test    r9w, r9w
0x180028aa0  jz      short loc_180028AB7
0x180028aa2  mov     [rax], r9w
0x180028aa6  add     r8, 2
0x180028aaa  add     rax, 2
0x180028aae  dec     rcx
0x180028ab1  sub     rdx, 1
0x180028ab5  jnz     short loc_180028A93
0x180028ab7  test    rdx, rdx
0x180028aba  lea     rcx, [rax-2]
0x180028abe  cmovnz  rcx, rax
0x180028ac2  mov     [rcx], r13w
0x180028ac6  mov     rcx, rdi; hMem
0x180028ac9  jnz     short loc_180028AE1
0x180028acb  call    cs:__imp_LocalFree
0x180028ad2  nop     dword ptr [rax+rax+00h]
0x180028ad7  mov     ebx, 0C000000Dh
0x180028adc  jmp     loc_180028B7E
0x180028ae1  mov     rdx, rbx
0x180028ae4  call    RtlStringCbCatW
0x180028ae9  test    eax, eax
0x180028aeb  jns     short loc_180028AF2
0x180028aed  mov     rcx, rdi
0x180028af0  jmp     short loc_180028ACB
0x180028af2  lea     rax, [rbp+String]
0x180028af6  mov     r9, rdi; Endpoint
0x180028af9  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180028afe  lea     rdx, ProtSeq; "ncacn_np"
0x180028b05  mov     r8, rsi; NetworkAddr
0x180028b08  mov     [rsp+70h+Options], r13; Options
0x180028b0d  xor     ecx, ecx; ObjUuid
0x180028b0f  call    cs:__imp_RpcStringBindingComposeW
0x180028b16  nop     dword ptr [rax+rax+00h]
0x180028b1b  mov     rcx, rdi; hMem
0x180028b1e  mov     ebx, eax
0x180028b20  call    cs:__imp_LocalFree
0x180028b27  nop     dword ptr [rax+rax+00h]
0x180028b2c  test    ebx, ebx
0x180028b2e  jnz     loc_1800289FD
0x180028b34  mov     rcx, [rbp+String]; StringBinding
0x180028b38  mov     rdx, r12; Binding
0x180028b3b  call    cs:__imp_RpcBindingFromStringBindingW
0x180028b42  nop     dword ptr [rax+rax+00h]
0x180028b47  lea     rcx, [rbp+String]; String
0x180028b4b  mov     ebx, eax
0x180028b4d  call    cs:__imp_RpcStringFreeW
0x180028b54  nop     dword ptr [rax+rax+00h]
0x180028b59  test    ebx, ebx
0x180028b5b  jz      short loc_180028B7B
0x180028b5d  lea     eax, [rbx-6AAh]
0x180028b63  mov     [r12], r13
0x180028b67  mov     ebx, 0C0000017h
0x180028b6c  cmp     eax, 1
0x180028b6f  mov     ecx, 0C0000122h
0x180028b74  cmova   ecx, ebx
0x180028b77  mov     ebx, ecx
0x180028b79  jmp     short loc_180028B7E
0x180028b7b  mov     ebx, r13d
0x180028b7e  test    r14, r14
0x180028b81  jz      short loc_180028B92
0x180028b83  mov     rcx, r14; hMem
0x180028b86  call    cs:__imp_LocalFree
0x180028b8d  nop     dword ptr [rax+rax+00h]
0x180028b92  mov     eax, ebx
0x180028b94  mov     rcx, [rbp+var_10]
0x180028b98  xor     rcx, rsp; StackCookie
0x180028b9b  call    __security_check_cookie
0x180028ba0  mov     rbx, [rsp+70h+arg_8]
0x180028ba8  add     rsp, 70h
0x180028bac  pop     r15
0x180028bae  pop     r14
0x180028bb0  pop     r13
0x180028bb2  pop     r12
0x180028bb4  pop     rdi
0x180028bb5  pop     rsi
0x180028bb6  pop     rbp
0x180028bb7  retn
```
