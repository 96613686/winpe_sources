# Vtl0TpmSubmitCommand(unsigned __int64 *,uchar *,uint,uint *,unsigned __int64 *)

- ea: `0x180028f3c`
- end: `0x180029038`
- name: `?Vtl0TpmSubmitCommand@@YAJPEA_KPEAEIPEAI0@Z`
- size: `252`
- prototype: `__int64 __fastcall(PTBS_HCONTEXT phContext, PCBYTE pabCommand, UINT32 cbCommand, PUINT32 pcbResult, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800412e4`

## callees

- `0x1800240e8`
- `0x180028f3c`
- `0x180029040`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002900c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002900c`
- `tbs!Tbsip_Submit_Command` at `0x180028fce`
- `tbs!Tbsip_Submit_Command` at `0x180028fce`
- `tbs!Tbsi_Context_Create` at `0x180028f73`
- `tbs!Tbsi_Context_Create` at `0x180028f73`

## string_xrefs

- `0x180028f88`: `onecore\ds\security\trustlet\tpmplatform\vtl0\lib\tpmcallbacks.cpp`
- `0x180028fe3`: `onecore\ds\security\trustlet\tpmplatform\vtl0\lib\tpmcallbacks.cpp`

## pseudocode

```c
int __fastcall Vtl0TpmSubmitCommand(
        PTBS_HCONTEXT phContext,
        PCBYTE pabCommand,
        UINT32 cbCommand,
        PUINT32 pcbResult,
        unsigned __int64 *a5)
{
  signed int v9; // eax
  signed int v11; // eax
  int v12; // eax
  PBYTE v13; // rcx
  int v14; // ebx
  UINT32 cbCommanda; // [rsp+20h] [rbp-58h]
  UINT32 cbCommandb; // [rsp+20h] [rbp-58h]
  PBYTE pabResult[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  if ( !*phContext )
  {
    v19 = 0x400000002LL;
    v9 = Tbsi_Context_Create((PCTBS_CONTEXT_PARAMS)&v19, phContext);
    if ( v9 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x1B,
               (unsigned int)"onecore\\ds\\security\\trustlet\\tpmplatform\\vtl0\\lib\\tpmcallbacks.cpp",
               (const char *)(unsigned int)v9,
               cbCommanda);
  }
  wil::make_unique_hlocal<unsigned char [0]>(pabResult);
  v11 = Tbsip_Submit_Command(*phContext, 0, 0xC8u, pabCommand, cbCommand, pabResult[0], pcbResult);
  if ( v11 >= 0 )
  {
    *a5 = (unsigned __int64)pabResult[0];
    return 0;
  }
  else
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x27,
            (unsigned int)"onecore\\ds\\security\\trustlet\\tpmplatform\\vtl0\\lib\\tpmcallbacks.cpp",
            (const char *)(unsigned int)v11,
            cbCommandb);
    v13 = pabResult[0];
    v14 = v12;
    pabResult[0] = 0;
    if ( v13 )
      LocalFree(v13);
    return v14;
  }
}

```

## disassembly

```asm
0x180028f3c  mov     rax, rsp
0x180028f3f  push    rbx
0x180028f40  push    rbp
0x180028f41  push    rsi
0x180028f42  push    rdi
0x180028f43  sub     rsp, 58h
0x180028f47  cmp     qword ptr [rcx], 0
0x180028f4b  mov     rdi, r9
0x180028f4e  mov     esi, r8d
0x180028f51  mov     rbp, rdx
0x180028f54  mov     rbx, rcx
0x180028f57  jnz     short loc_180028FA1
0x180028f59  mov     qword ptr [rax+8], 0
0x180028f61  mov     rdx, rcx; phContext
0x180028f64  or      dword ptr [rax+0Ch], 4
0x180028f68  lea     rcx, [rax+8]; pContextParams
0x180028f6c  mov     dword ptr [rax+8], 2
0x180028f73  call    cs:__imp_Tbsi_Context_Create
0x180028f7a  nop     dword ptr [rax+rax+00h]
0x180028f7f  test    eax, eax
0x180028f81  jns     short loc_180028FA1
0x180028f83  mov     rcx, [rsp+78h]; this
0x180028f88  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\trustlet\\tpmpla"...
0x180028f8f  mov     r9d, eax; char *
0x180028f92  mov     edx, 1Bh; void *
0x180028f97  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180028f9c  jmp     loc_18002902E
0x180028fa1  mov     edx, [rdi]
0x180028fa3  lea     rcx, [rsp+78h+var_38]
0x180028fa8  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180028fad  mov     rax, [rsp+78h+var_38]
0x180028fb2  mov     r9, rbp; pabCommand
0x180028fb5  mov     rcx, [rbx]; hContext
0x180028fb8  xor     edx, edx; Locality
0x180028fba  mov     [rsp+78h+pcbResult], rdi; pcbResult
0x180028fbf  mov     r8d, 0C8h; Priority
0x180028fc5  mov     [rsp+78h+pabResult], rax; pabResult
0x180028fca  mov     [rsp+78h+cbCommand], esi; int
0x180028fce  call    cs:__imp_Tbsip_Submit_Command
0x180028fd5  nop     dword ptr [rax+rax+00h]
0x180028fda  test    eax, eax
0x180028fdc  jns     short loc_18002901C
0x180028fde  mov     rcx, [rsp+78h]; this
0x180028fe3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\trustlet\\tpmpla"...
0x180028fea  mov     r9d, eax; char *
0x180028fed  mov     edx, 27h ; '''; void *
0x180028ff2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180028ff7  mov     rcx, [rsp+78h+var_38]; hMem
0x180028ffc  mov     ebx, eax
0x180028ffe  mov     [rsp+78h+var_38], 0
0x180029007  test    rcx, rcx
0x18002900a  jz      short loc_180029018
0x18002900c  call    cs:__imp_LocalFree
0x180029013  nop     dword ptr [rax+rax+00h]
0x180029018  mov     eax, ebx
0x18002901a  jmp     short loc_18002902E
0x18002901c  mov     rax, [rsp+78h+var_38]
0x180029021  mov     rcx, [rsp+78h+arg_20]
0x180029029  mov     [rcx], rax
0x18002902c  xor     eax, eax
0x18002902e  add     rsp, 58h
0x180029032  pop     rdi
0x180029033  pop     rsi
0x180029034  pop     rbp
0x180029035  pop     rbx
0x180029036  retn
```
