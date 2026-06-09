# Microsoft::Resources::Build::PriFileMerger::CreateUniqueTempDirectory(ulong,ushort *)

- ea: `0x18009b73c`
- end: `0x18009b898`
- name: `?CreateUniqueTempDirectory@PriFileMerger@Build@Resources@Microsoft@@SAJKPEAG@Z`
- size: `348`
- prototype: `static int(unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f184`
- `0x18009bc78`

## callees

- `0x18002c8d0`
- `0x18002eb8c`
- `0x180052344`
- `0x180083aa8`
- `0x1800862f0`
- `0x180086f7c`
- `0x18009b73c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b861`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009b84a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009b84a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18009b763`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18009b763`
- `RPCRT4!RpcStringFreeW` at `0x18009b801`
- `RPCRT4!RpcStringFreeW` at `0x18009b801`
- `RPCRT4!UuidToStringW` at `0x18009b7bc`
- `RPCRT4!UuidToStringW` at `0x18009b7bc`
- `RPCRT4!UuidCreate` at `0x18009b798`
- `RPCRT4!UuidCreate` at `0x18009b798`

## pseudocode

```c
int __fastcall Microsoft::Resources::Build::PriFileMerger::CreateUniqueTempDirectory(__int64 a1, unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  int result; // eax
  int v6; // ebx
  int v7; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-248h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-240h] BYREF
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !(unsigned int)GetTempPath2W(260) )
  {
    v4 = 267;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
             v3);
  }
  Uuid = 0;
  if ( UuidCreate(&Uuid) )
  {
    v4 = 270;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
             v3);
  }
  StringUuid = 0;
  if ( UuidToStringW(&Uuid, &StringUuid) )
  {
    v4 = 273;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
             v3);
  }
  memset_0(v10, 0, 0x208u);
  v6 = StringCchPrintfW(v10, 0x104u, L"%s", StringUuid);
  RpcStringFreeW(&StringUuid);
  if ( v6 < 0 )
    return v6;
  v7 = StringCchCatW(a2, 0x104u, v10);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)(unsigned int)v7,
      (int)StringUuid);
    return v6;
  }
  if ( CreateDirectoryW(a2, 0) || GetLastError() == 183 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18009b73c  mov     [rsp+arg_0], rbx
0x18009b741  push    rdi
0x18009b742  sub     rsp, 260h
0x18009b749  mov     rax, cs:__security_cookie
0x18009b750  xor     rax, rsp
0x18009b753  mov     [rsp+268h+var_18], rax
0x18009b75b  mov     ecx, 104h
0x18009b760  mov     rdi, rdx
0x18009b763  call    cs:__imp_GetTempPath2W
0x18009b769  test    eax, eax
0x18009b76b  jnz     short loc_18009B78B
0x18009b76d  mov     edx, 10Bh; void *
0x18009b772  mov     rcx, [rsp+268h]; this
0x18009b77a  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b781  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b786  jmp     loc_18009B877
0x18009b78b  xorps   xmm0, xmm0
0x18009b78e  lea     rcx, [rsp+268h+Uuid]; Uuid
0x18009b793  movups  xmmword ptr [rsp+268h+Uuid.Data1], xmm0
0x18009b798  call    cs:__imp_UuidCreate
0x18009b79e  test    eax, eax
0x18009b7a0  jz      short loc_18009B7A9
0x18009b7a2  mov     edx, 10Eh
0x18009b7a7  jmp     short loc_18009B772
0x18009b7a9  lea     rdx, [rsp+268h+StringUuid]; StringUuid
0x18009b7ae  mov     [rsp+268h+StringUuid], 0; int
0x18009b7b7  lea     rcx, [rsp+268h+Uuid]; Uuid
0x18009b7bc  call    cs:__imp_UuidToStringW
0x18009b7c2  test    eax, eax
0x18009b7c4  jz      short loc_18009B7CD
0x18009b7c6  mov     edx, 111h
0x18009b7cb  jmp     short loc_18009B772
0x18009b7cd  xor     edx, edx; Val
0x18009b7cf  lea     rcx, [rsp+268h+var_228]; void *
0x18009b7d4  mov     r8d, 208h; Size
0x18009b7da  call    memset_0
0x18009b7df  mov     r9, [rsp+268h+StringUuid]
0x18009b7e4  lea     r8, aS; "%s"
0x18009b7eb  mov     edx, 104h; unsigned __int64
0x18009b7f0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18009b7f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009b7fa  lea     rcx, [rsp+268h+StringUuid]; String
0x18009b7ff  mov     ebx, eax
0x18009b801  call    cs:__imp_RpcStringFreeW
0x18009b807  test    ebx, ebx
0x18009b809  jns     short loc_18009B80F
0x18009b80b  mov     eax, ebx
0x18009b80d  jmp     short loc_18009B877
0x18009b80f  lea     r8, [rsp+268h+var_228]; unsigned __int16 *
0x18009b814  mov     edx, 104h; unsigned __int64
0x18009b819  mov     rcx, rdi; unsigned __int16 *
0x18009b81c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009b821  mov     ebx, eax
0x18009b823  test    eax, eax
0x18009b825  jns     short loc_18009B845
0x18009b827  mov     rcx, [rsp+268h]; this
0x18009b82f  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x18009b836  mov     r9d, eax; char *
0x18009b839  mov     edx, 11Bh; void *
0x18009b83e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b843  jmp     short loc_18009B80B
0x18009b845  xor     edx, edx; lpSecurityAttributes
0x18009b847  mov     rcx, rdi; lpPathName
0x18009b84a  call    cs:__imp_CreateDirectoryW
0x18009b850  test    eax, eax
0x18009b852  jnz     short loc_18009B875
0x18009b854  call    cs:__imp_GetLastError
0x18009b85a  cmp     eax, 0B7h
0x18009b85f  jz      short loc_18009B875
0x18009b861  call    cs:__imp_GetLastError
0x18009b867  test    eax, eax
0x18009b869  jle     short loc_18009B877
0x18009b86b  movzx   eax, ax
0x18009b86e  or      eax, 80070000h
0x18009b873  jmp     short loc_18009B877
0x18009b875  xor     eax, eax
0x18009b877  mov     rcx, [rsp+268h+var_18]
0x18009b87f  xor     rcx, rsp; StackCookie
0x18009b882  call    __security_check_cookie
0x18009b887  mov     rbx, [rsp+268h+arg_0]
0x18009b88f  add     rsp, 260h
0x18009b896  pop     rdi
0x18009b897  retn
```
