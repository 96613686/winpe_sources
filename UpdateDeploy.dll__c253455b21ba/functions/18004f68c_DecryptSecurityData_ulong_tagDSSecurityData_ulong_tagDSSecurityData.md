# DecryptSecurityData(ulong,tagDSSecurityData *,ulong *,tagDSSecurityData * *)

- ea: `0x18004f68c`
- end: `0x18004f8b2`
- name: `?DecryptSecurityData@@YAJKPEAUtagDSSecurityData@@PEAKPEAPEAU1@@Z`
- size: `550`
- prototype: `__int64 __fastcall(unsigned int, struct tagDSSecurityData *, unsigned int *, struct tagDSSecurityData **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180051b80`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000de44`
- `0x18004f68c`
- `0x18004f8b8`
- `0x180061837`
- `0x180061873`
- `0x180061960`
- `0x180068f20`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f80d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f80d`
- `CRYPT32!CryptUnprotectData` at `0x18004f761`
- `CRYPT32!CryptUnprotectData` at `0x18004f761`

## pseudocode

```c
__int64 __fastcall DecryptSecurityData(
        unsigned int a1,
        struct tagDSSecurityData *a2,
        unsigned int *a3,
        struct tagDSSecurityData **a4)
{
  unsigned int v4; // r15d
  struct tagDSSecurityData *v5; // rbx
  unsigned int v6; // esi
  unsigned int LastError; // edi
  __int64 v9; // r12
  const char *v10; // r9
  void *v11; // rax
  unsigned __int64 cbData; // rdi
  unsigned __int64 v13; // r14
  int v14; // r14d
  int *v15; // rax
  int v16; // edi
  struct tagDSSecurityData *v17; // rax
  __int64 v19; // rdx
  int pPromptStruct; // [rsp+20h] [rbp-59h]
  int pPromptStructa; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+40h] [rbp-39h]
  struct tagDSSecurityData *v23; // [rsp+48h] [rbp-31h]
  BYTE *pbData; // [rsp+50h] [rbp-29h]
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-11h] BYREF
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = 0;
  v5 = 0;
  v23 = a2;
  v6 = -2147024882;
  if ( a1 )
  {
    v5 = (struct tagDSSecurityData *)SafeSusComAllocArray(a1, 0x10u);
    LastError = v5 == 0 ? 0x8007000E : 0;
    if ( !v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
        (const char *)LastError,
        pPromptStruct);
      goto LABEL_27;
    }
    a2 = v23;
  }
  v22 = 0;
  if ( !a1 )
  {
LABEL_21:
    *a3 = v4;
    v17 = v5;
    v5 = 0;
    *a4 = v17;
    v6 = 0;
    goto LABEL_22;
  }
  v9 = 0;
  while ( 1 )
  {
    pDataIn.cbData = *(_DWORD *)((char *)a2 + v9);
    pDataIn.pbData = *(BYTE **)((char *)a2 + v9 + 8);
    *(&pDataIn.cbData + 1) = 0;
    pDataOut = 0;
    if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      break;
    v11 = CoTaskMemAlloc(pDataOut.cbData);
    *(_QWORD *)((char *)v5 + v9 + 8) = v11;
    if ( !v11 )
    {
      v19 = 919;
      goto LABEL_24;
    }
    *(_DWORD *)((char *)v5 + v9) = pDataOut.cbData;
    cbData = pDataOut.cbData;
    v13 = pDataOut.cbData;
    pbData = pDataOut.pbData;
    if ( !pDataOut.cbData )
      goto LABEL_10;
    if ( pDataOut.pbData )
    {
      memmove(v11, pDataOut.pbData, pDataOut.cbData);
LABEL_10:
      v14 = 0;
      goto LABEL_19;
    }
    memset(v11, 0, pDataOut.cbData);
    if ( !pbData )
    {
      v15 = (int *)o__errno_0();
      v16 = 22;
LABEL_15:
      *v15 = v16;
      invalid_parameter_noinfo();
      v14 = v16;
      goto LABEL_19;
    }
    if ( v13 < cbData )
    {
      v15 = (int *)o__errno_0();
      v16 = 34;
      goto LABEL_15;
    }
    v14 = 22;
LABEL_19:
    memset(pDataOut.pbData, 0, pDataOut.cbData);
    LocalFree(pDataOut.pbData);
    if ( v14 )
    {
      v19 = 931;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
        (const char *)0x8007000ELL,
        pPromptStructa);
      goto LABEL_22;
    }
    ++v4;
    a2 = v23;
    v9 += 16;
    if ( ++v22 >= a1 )
      goto LABEL_21;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x393,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
                v10);
LABEL_27:
  v6 = LastError;
LABEL_22:
  FreeSecurityData(v4, v5);
  return v6;
}

```

## disassembly

```asm
0x18004f68c  push    rbp
0x18004f68e  push    rbx
0x18004f68f  push    rsi
0x18004f690  push    rdi
0x18004f691  push    r12
0x18004f693  push    r13
0x18004f695  push    r14
0x18004f697  push    r15
0x18004f699  lea     rbp, [rsp-1Fh]
0x18004f69e  sub     rsp, 98h
0x18004f6a5  mov     rax, cs:__security_cookie
0x18004f6ac  xor     rax, rsp
0x18004f6af  mov     [rbp+57h+var_48], rax
0x18004f6b3  xor     r15d, r15d
0x18004f6b6  mov     [rbp+57h+var_70], r9
0x18004f6ba  xor     ebx, ebx
0x18004f6bc  mov     [rbp+57h+var_78], r8
0x18004f6c0  mov     [rbp+57h+var_88], rdx
0x18004f6c4  mov     esi, 8007000Eh
0x18004f6c9  mov     r13d, ecx
0x18004f6cc  test    ecx, ecx
0x18004f6ce  jz      short loc_18004F70D
0x18004f6d0  mov     ecx, r13d; unsigned __int64
0x18004f6d3  lea     edx, [rbx+10h]; unsigned __int64
0x18004f6d6  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18004f6db  mov     rbx, rax
0x18004f6de  neg     rax
0x18004f6e1  sbb     edi, edi
0x18004f6e3  not     edi
0x18004f6e5  and     edi, esi
0x18004f6e7  test    rbx, rbx
0x18004f6ea  jnz     short loc_18004F709
0x18004f6ec  mov     rcx, [rbp+5Fh]; this
0x18004f6f0  lea     r8, aCW1SSrcClientE_9; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18004f6f7  mov     r9d, edi; char *
0x18004f6fa  mov     edx, 37Fh; void *
0x18004f6ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f704  jmp     loc_18004F8AE
0x18004f709  mov     rdx, [rbp+57h+var_88]
0x18004f70d  mov     [rbp+57h+var_90], r15d
0x18004f711  test    r13d, r13d
0x18004f714  jz      loc_18004F834
0x18004f71a  xor     r12d, r12d
0x18004f71d  mov     eax, [r12+rdx]
0x18004f721  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18004f725  mov     [rbp+57h+pDataIn.cbData], eax
0x18004f728  xorps   xmm0, xmm0
0x18004f72b  mov     rax, [r12+rdx+8]
0x18004f730  xor     r9d, r9d; pvReserved
0x18004f733  mov     [rbp+57h+pDataIn.pbData], rax
0x18004f737  xor     r8d, r8d; pOptionalEntropy
0x18004f73a  lea     rax, [rbp+57h+var_68]
0x18004f73e  mov     dword ptr [rbp+57h+pDataIn+4], 0
0x18004f745  mov     [rsp+0D0h+pDataOut], rax; pDataOut
0x18004f74a  xor     edx, edx; ppszDataDescr
0x18004f74c  mov     [rsp+0D0h+dwFlags], 1; dwFlags
0x18004f754  mov     [rsp+0D0h+pPromptStruct], 0; int
0x18004f75d  movups  xmmword ptr [rbp+57h+var_68.cbData], xmm0
0x18004f761  call    cs:__imp_CryptUnprotectData
0x18004f767  test    eax, eax
0x18004f769  jz      loc_18004F897
0x18004f76f  mov     ecx, [rbp+57h+var_68.cbData]; cb
0x18004f772  call    cs:__imp_CoTaskMemAlloc
0x18004f778  mov     [r12+rbx+8], rax
0x18004f77d  mov     rcx, rax; void *
0x18004f780  test    rax, rax
0x18004f783  jz      loc_18004F890
0x18004f789  mov     eax, [rbp+57h+var_68.cbData]
0x18004f78c  mov     [r12+rbx], eax
0x18004f790  mov     edi, [rbp+57h+var_68.cbData]
0x18004f793  mov     rax, [rbp+57h+var_68.pbData]
0x18004f797  mov     r14d, [rbp+57h+var_68.cbData]
0x18004f79b  mov     [rbp+57h+var_80], rax
0x18004f79f  test    rdi, rdi
0x18004f7a2  jnz     short loc_18004F7A9
0x18004f7a4  xor     r14d, r14d
0x18004f7a7  jmp     short loc_18004F7FE
0x18004f7a9  test    rax, rax
0x18004f7ac  jz      short loc_18004F7C0
0x18004f7ae  cmp     r14, rdi
0x18004f7b1  jb      short loc_18004F7C0
0x18004f7b3  mov     r8, rdi; Size
0x18004f7b6  mov     rdx, rax; Src
0x18004f7b9  call    memmove
0x18004f7be  jmp     short loc_18004F7A4
0x18004f7c0  mov     r8, r14; Size
0x18004f7c3  xor     edx, edx; Val
0x18004f7c5  call    memset
0x18004f7ca  cmp     [rbp+57h+var_80], 0
0x18004f7cf  jnz     short loc_18004F7E7
0x18004f7d1  call    _o__errno_0
0x18004f7d6  mov     edi, 16h
0x18004f7db  mov     [rax], edi
0x18004f7dd  call    _invalid_parameter_noinfo
0x18004f7e2  mov     r14d, edi
0x18004f7e5  jmp     short loc_18004F7FE
0x18004f7e7  cmp     r14, rdi
0x18004f7ea  jnb     short loc_18004F7F8
0x18004f7ec  call    _o__errno_0
0x18004f7f1  mov     edi, 22h ; '"'
0x18004f7f6  jmp     short loc_18004F7DB
0x18004f7f8  mov     r14d, 16h
0x18004f7fe  mov     ecx, [rbp+57h+var_68.cbData]
0x18004f801  xor     eax, eax
0x18004f803  mov     rdi, [rbp+57h+var_68.pbData]
0x18004f807  rep stosb
0x18004f809  mov     rcx, [rbp+57h+var_68.pbData]; hMem
0x18004f80d  call    cs:__imp_LocalFree
0x18004f813  test    r14d, r14d
0x18004f816  jnz     short loc_18004F876
0x18004f818  mov     edi, [rbp+57h+var_90]
0x18004f81b  inc     r15d
0x18004f81e  mov     rdx, [rbp+57h+var_88]
0x18004f822  inc     edi
0x18004f824  add     r12, 10h
0x18004f828  mov     [rbp+57h+var_90], edi
0x18004f82b  cmp     edi, r13d
0x18004f82e  jb      loc_18004F71D
0x18004f834  mov     rax, [rbp+57h+var_78]
0x18004f838  mov     rcx, [rbp+57h+var_70]
0x18004f83c  mov     [rax], r15d
0x18004f83f  mov     rax, rbx
0x18004f842  xor     ebx, ebx
0x18004f844  mov     [rcx], rax
0x18004f847  xor     esi, esi
0x18004f849  mov     rdx, rbx; struct tagDSSecurityData *
0x18004f84c  mov     ecx, r15d; unsigned int
0x18004f84f  call    ?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z; FreeSecurityData(ulong,tagDSSecurityData *)
0x18004f854  mov     eax, esi
0x18004f856  mov     rcx, [rbp+57h+var_48]
0x18004f85a  xor     rcx, rsp; StackCookie
0x18004f85d  call    __security_check_cookie
0x18004f862  add     rsp, 98h
0x18004f869  pop     r15
0x18004f86b  pop     r14
0x18004f86d  pop     r13
0x18004f86f  pop     r12
0x18004f871  pop     rdi
0x18004f872  pop     rsi
0x18004f873  pop     rbx
0x18004f874  pop     rbp
0x18004f875  retn
0x18004f876  mov     edx, 3A3h; void *
0x18004f87b  mov     rcx, [rbp+5Fh]; this
0x18004f87f  lea     r8, aCW1SSrcClientE_9; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18004f886  mov     r9d, esi; char *
0x18004f889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f88e  jmp     short loc_18004F849
0x18004f890  mov     edx, 397h
0x18004f895  jmp     short loc_18004F87B
0x18004f897  mov     rcx, [rbp+5Fh]; this
0x18004f89b  lea     r8, aCW1SSrcClientE_9; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18004f8a2  mov     edx, 393h; void *
0x18004f8a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f8ac  mov     edi, eax
0x18004f8ae  mov     esi, edi
0x18004f8b0  jmp     short loc_18004F849
```
