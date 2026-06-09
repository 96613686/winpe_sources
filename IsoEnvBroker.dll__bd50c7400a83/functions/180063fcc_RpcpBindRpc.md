# RpcpBindRpc

- ea: `0x180063fcc`
- end: `0x1800642e1`
- name: `RpcpBindRpc`
- size: `789`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180063f20`

## callees

- `0x180002520`
- `0x180003064`
- `0x1800050c1`
- `0x180063fcc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800640b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180064119`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800640b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180064119`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064068`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800640ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064156`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064068`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800640ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064144`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800642a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800642b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064144`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800642a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800642b5`
- `RPCRT4!RpcStringFreeW` at `0x180064272`
- `RPCRT4!RpcStringFreeW` at `0x180064272`
- `RPCRT4!RpcStringBindingComposeW` at `0x180064246`
- `RPCRT4!RpcStringBindingComposeW` at `0x180064246`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180064266`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180064266`

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
  unsigned __int16 *v15; // rdi
  __int64 v16; // r11
  const wchar_t *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  __int64 v23; // r9
  const wchar_t *v24; // rcx
  unsigned __int16 *v25; // rax
  __int64 v26; // r8
  unsigned __int16 *v27; // rcx
  RPC_STATUS v28; // ebx
  RPC_STATUS v29; // ebx
  int v30; // ecx
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
      if ( v7 == nSize && !wcsnicmp(Buffer, v5, v7) )
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
    v9 &= -(__int64)(wcsnicmp(v13, v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v15 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_53;
  }
  v16 = 2147483646;
  v17 = L"\\PIPE\\";
  v18 = 2147483646;
  v19 = 14;
  do
  {
    if ( !v18 )
      break;
    if ( !*v17 )
      break;
    *v14++ = *v17++;
    --v18;
    --v19;
  }
  while ( v19 );
  v20 = v14 - 1;
  if ( v19 )
    v20 = v14;
  *v20 = 0;
  if ( v19 )
  {
    v21 = 14;
    v22 = v15;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v23 = (14 - v21) & -(__int64)(v21 != 0);
    if ( v21 )
    {
      v24 = L"lsarpc";
      v25 = &v15[v23];
      v26 = 14 - v23;
      if ( 14 != v23 )
      {
        do
        {
          if ( !v16 )
            break;
          if ( !*v24 )
            break;
          *v25++ = *v24++;
          --v16;
          --v26;
        }
        while ( v26 );
      }
      v27 = v25 - 1;
      if ( v26 )
        v27 = v25;
      *v27 = 0;
      if ( v26 )
      {
        v28 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v15, 0, &String);
        LocalFree(v15);
        if ( !v28 )
        {
          v29 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v29 )
          {
            *a4 = 0;
            v30 = -1073741534;
            if ( (unsigned int)(v29 - 1706) > 1 )
              v30 = -1073741801;
            v8 = v30;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_53;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v15);
  v8 = -1073741811;
LABEL_53:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x180063fcc  mov     [rsp-38h+arg_8], rbx
0x180063fd1  push    rbp
0x180063fd2  push    rsi
0x180063fd3  push    rdi
0x180063fd4  push    r12
0x180063fd6  push    r13
0x180063fd8  push    r14
0x180063fda  push    r15
0x180063fdc  mov     rbp, rsp
0x180063fdf  sub     rsp, 70h
0x180063fe3  mov     rax, cs:__security_cookie
0x180063fea  xor     rax, rsp
0x180063fed  mov     [rbp+var_10], rax
0x180063ff1  xor     r13d, r13d
0x180063ff4  mov     r12, r9
0x180063ff7  mov     [rbp+String], r13
0x180063ffb  mov     rdi, rcx
0x180063ffe  mov     [rbp+nSize], r13d
0x180064002  mov     r14d, r13d
0x180064005  mov     [r9], r13
0x180064008  test    rcx, rcx
0x18006400b  jz      loc_18006414C
0x180064011  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180064015  inc     rbx
0x180064018  cmp     [rcx+rbx*2], r13w
0x18006401d  jnz     short loc_180064015
0x18006401f  cmp     [rcx], r13w
0x180064023  jz      loc_18006414C
0x180064029  mov     esi, 5Ch ; '\'
0x18006402e  cmp     [rcx], si
0x180064031  jnz     short loc_18006405E
0x180064033  cmp     [rcx+2], si
0x180064037  jnz     short loc_18006403F
0x180064039  add     rbx, 0FFFFFFFFFFFFFFFEh
0x18006403d  jnz     short loc_180064049
0x18006403f  mov     ebx, 0C0000122h
0x180064044  jmp     loc_1800642BB
0x180064049  lea     rax, [rcx+4]
0x18006404d  mov     rsi, rdi
0x180064050  test    rax, rax
0x180064053  jz      loc_18006414F
0x180064059  mov     rdi, rax
0x18006405c  jmp     short loc_18006409D
0x18006405e  lea     rdx, ds:6[rbx*2]; uBytes
0x180064066  xor     ecx, ecx; uFlags
0x180064068  call    cs:__imp_LocalAlloc
0x18006406e  mov     r14, rax
0x180064071  test    rax, rax
0x180064074  jnz     short loc_180064080
0x180064076  mov     ebx, 0C0000017h
0x18006407b  jmp     loc_1800642BB
0x180064080  lea     r8, ds:2[rbx*2]; Size
0x180064088  mov     dword ptr [rax], 5C005Ch
0x18006408e  lea     rcx, [rax+4]; void *
0x180064092  mov     rdx, rdi; Src
0x180064095  call    memcpy_0
0x18006409a  mov     rsi, r14
0x18006409d  cmp     rbx, 0Fh
0x1800640a1  ja      short loc_1800640D9
0x1800640a3  lea     r8, [rbp+nSize]; nSize
0x1800640a7  mov     [rbp+nSize], 10h
0x1800640ae  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800640b2  xor     ecx, ecx; NameType
0x1800640b4  call    cs:__imp_GetComputerNameExW
0x1800640ba  test    eax, eax
0x1800640bc  jz      short loc_1800640D9
0x1800640be  mov     eax, [rbp+nSize]
0x1800640c1  cmp     rbx, rax
0x1800640c4  jnz     short loc_1800640D9
0x1800640c6  mov     r8, rbx; MaxCount
0x1800640c9  lea     rcx, [rbp+Buffer]; String1
0x1800640cd  mov     rdx, rdi; String2
0x1800640d0  call    _wcsnicmp
0x1800640d5  test    eax, eax
0x1800640d7  jz      short loc_18006414C
0x1800640d9  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800640df  lea     r15, [rbx-1]
0x1800640e3  mov     edx, 20Ah; uBytes
0x1800640e8  cmovnz  r15, rbx
0x1800640ec  xor     ecx, ecx; uFlags
0x1800640ee  call    cs:__imp_LocalAlloc
0x1800640f4  mov     rbx, rax
0x1800640f7  test    rax, rax
0x1800640fa  jnz     short loc_180064106
0x1800640fc  mov     ebx, 0C0000017h
0x180064101  jmp     loc_1800642AD
0x180064106  lea     r8, [rbp+nSize]; nSize
0x18006410a  mov     [rbp+nSize], 105h
0x180064111  mov     rdx, rbx; lpBuffer
0x180064114  mov     ecx, 3; NameType
0x180064119  call    cs:__imp_GetComputerNameExW
0x18006411f  test    eax, eax
0x180064121  jz      short loc_180064141
0x180064123  mov     eax, [rbp+nSize]
0x180064126  cmp     r15, rax
0x180064129  jnz     short loc_180064141
0x18006412b  mov     r8, r15; MaxCount
0x18006412e  mov     rdx, rdi; String2
0x180064131  mov     rcx, rbx; String1
0x180064134  call    _wcsnicmp
0x180064139  neg     eax
0x18006413b  sbb     rcx, rcx
0x18006413e  and     rsi, rcx
0x180064141  mov     rcx, rbx; hMem
0x180064144  call    cs:__imp_LocalFree
0x18006414a  jmp     short loc_18006414F
0x18006414c  mov     rsi, r13
0x18006414f  mov     edx, 1Ch; uBytes
0x180064154  xor     ecx, ecx; uFlags
0x180064156  call    cs:__imp_LocalAlloc
0x18006415c  mov     rdi, rax
0x18006415f  test    rax, rax
0x180064162  jz      short loc_1800640FC
0x180064164  mov     r11d, 7FFFFFFEh
0x18006416a  lea     r9, aPipe; "\\PIPE\\"
0x180064171  mov     r8d, 0Eh
0x180064177  mov     edx, r11d
0x18006417a  mov     ecx, r8d
0x18006417d  test    rdx, rdx
0x180064180  jz      short loc_1800641A1
0x180064182  movzx   r10d, word ptr [r9]
0x180064186  test    r10w, r10w
0x18006418a  jz      short loc_1800641A1
0x18006418c  mov     [rax], r10w
0x180064190  add     r9, 2
0x180064194  add     rax, 2
0x180064198  dec     rdx
0x18006419b  sub     rcx, 1
0x18006419f  jnz     short loc_18006417D
0x1800641a1  test    rcx, rcx
0x1800641a4  lea     rdx, [rax-2]
0x1800641a8  cmovnz  rdx, rax
0x1800641ac  mov     [rdx], r13w
0x1800641b0  jz      loc_18006429F
0x1800641b6  mov     rdx, r8
0x1800641b9  mov     rax, rdi
0x1800641bc  cmp     [rax], r13w
0x1800641c0  jz      short loc_1800641CC
0x1800641c2  add     rax, 2
0x1800641c6  sub     rdx, 1
0x1800641ca  jnz     short loc_1800641BC
0x1800641cc  mov     rcx, r8
0x1800641cf  mov     rax, rdx
0x1800641d2  sub     rcx, rdx
0x1800641d5  neg     rax
0x1800641d8  sbb     r9, r9
0x1800641db  and     r9, rcx
0x1800641de  test    rdx, rdx
0x1800641e1  jz      loc_18006429F
0x1800641e7  lea     rcx, aLsarpc; "lsarpc"
0x1800641ee  lea     rax, [rdi+r9*2]
0x1800641f2  sub     r8, r9
0x1800641f5  jz      short loc_180064218
0x1800641f7  test    r11, r11
0x1800641fa  jz      short loc_180064218
0x1800641fc  movzx   edx, word ptr [rcx]
0x1800641ff  test    dx, dx
0x180064202  jz      short loc_180064218
0x180064204  mov     [rax], dx
0x180064207  add     rcx, 2
0x18006420b  add     rax, 2
0x18006420f  dec     r11
0x180064212  sub     r8, 1
0x180064216  jnz     short loc_1800641F7
0x180064218  test    r8, r8
0x18006421b  lea     rcx, [rax-2]
0x18006421f  cmovnz  rcx, rax
0x180064223  mov     [rcx], r13w
0x180064227  jz      short loc_18006429F
0x180064229  lea     rax, [rbp+String]
0x18006422d  mov     r9, rdi; Endpoint
0x180064230  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180064235  lea     rdx, ProtSeq; "ncacn_np"
0x18006423c  mov     r8, rsi; NetworkAddr
0x18006423f  mov     [rsp+70h+Options], r13; Options
0x180064244  xor     ecx, ecx; ObjUuid
0x180064246  call    cs:__imp_RpcStringBindingComposeW
0x18006424c  mov     rcx, rdi; hMem
0x18006424f  mov     ebx, eax
0x180064251  call    cs:__imp_LocalFree
0x180064257  test    ebx, ebx
0x180064259  jnz     loc_1800640FC
0x18006425f  mov     rcx, [rbp+String]; StringBinding
0x180064263  mov     rdx, r12; Binding
0x180064266  call    cs:__imp_RpcBindingFromStringBindingW
0x18006426c  lea     rcx, [rbp+String]; String
0x180064270  mov     ebx, eax
0x180064272  call    cs:__imp_RpcStringFreeW
0x180064278  test    ebx, ebx
0x18006427a  jz      short loc_18006429A
0x18006427c  lea     eax, [rbx-6AAh]
0x180064282  mov     [r12], r13
0x180064286  mov     ebx, 0C0000017h
0x18006428b  cmp     eax, 1
0x18006428e  mov     ecx, 0C0000122h
0x180064293  cmova   ecx, ebx
0x180064296  mov     ebx, ecx
0x180064298  jmp     short loc_1800642AD
0x18006429a  mov     ebx, r13d
0x18006429d  jmp     short loc_1800642AD
0x18006429f  mov     rcx, rdi; hMem
0x1800642a2  call    cs:__imp_LocalFree
0x1800642a8  mov     ebx, 0C000000Dh
0x1800642ad  test    r14, r14
0x1800642b0  jz      short loc_1800642BB
0x1800642b2  mov     rcx, r14; hMem
0x1800642b5  call    cs:__imp_LocalFree
0x1800642bb  mov     eax, ebx
0x1800642bd  mov     rcx, [rbp+var_10]
0x1800642c1  xor     rcx, rsp; StackCookie
0x1800642c4  call    __security_check_cookie
0x1800642c9  mov     rbx, [rsp+70h+arg_8]
0x1800642d1  add     rsp, 70h
0x1800642d5  pop     r15
0x1800642d7  pop     r14
0x1800642d9  pop     r13
0x1800642db  pop     r12
0x1800642dd  pop     rdi
0x1800642de  pop     rsi
0x1800642df  pop     rbp
0x1800642e0  retn
```
