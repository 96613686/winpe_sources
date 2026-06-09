# Vtl0TpmSubmitCommand(unsigned __int64 *,uchar *,uint,uint *,unsigned __int64 *)

- ea: `0x180076b50`
- end: `0x180076c39`
- name: `?Vtl0TpmSubmitCommand@@YAJPEA_KPEAEIPEAI0@Z`
- size: `233`
- prototype: `__int64 __fastcall(PTBS_HCONTEXT phContext, PCBYTE pabCommand, unsigned int, PUINT32 pcbResult, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180064870`

## callees

- `0x1800273c4`
- `0x180076aac`
- `0x180076b50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076c14`
- `tbs!Tbsi_Context_Create` at `0x180076b87`
- `tbs!Tbsi_Context_Create` at `0x180076b87`
- `tbs!Tbsip_Submit_Command` at `0x180076bdc`
- `tbs!Tbsip_Submit_Command` at `0x180076bdc`

## string_xrefs

- `0x180076b96`: `onecore\ds\security\trustlet\tpmplatform\vtl0\lib\tpmcallbacks.cpp`
- `0x180076beb`: `onecore\ds\security\trustlet\tpmplatform\vtl0\lib\tpmcallbacks.cpp`

## pseudocode

```c
int __fastcall Vtl0TpmSubmitCommand(
        PTBS_HCONTEXT phContext,
        PCBYTE pabCommand,
        UINT32 a3,
        PUINT32 pcbResult,
        unsigned __int64 *a5)
{
  signed int v9; // eax
  signed int v11; // eax
  int v12; // eax
  PBYTE v13; // rcx
  int v14; // ebx
  UINT32 cbCommand; // [rsp+20h] [rbp-58h]
  UINT32 cbCommanda; // [rsp+20h] [rbp-58h]
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
               cbCommand);
  }
  wil::make_unique_hlocal<unsigned char [0]>(pabResult);
  v11 = Tbsip_Submit_Command(*phContext, 0, 0xC8u, pabCommand, a3, pabResult[0], pcbResult);
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
            cbCommanda);
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
0x180076b50  mov     rax, rsp
0x180076b53  push    rbx
0x180076b54  push    rbp
0x180076b55  push    rsi
0x180076b56  push    rdi
0x180076b57  sub     rsp, 58h
0x180076b5b  cmp     qword ptr [rcx], 0
0x180076b5f  mov     rdi, r9
0x180076b62  mov     esi, r8d
0x180076b65  mov     rbp, rdx
0x180076b68  mov     rbx, rcx
0x180076b6b  jnz     short loc_180076BAF
0x180076b6d  mov     qword ptr [rax+8], 0
0x180076b75  mov     rdx, rcx; phContext
0x180076b78  or      dword ptr [rax+0Ch], 4
0x180076b7c  lea     rcx, [rax+8]; pContextParams
0x180076b80  mov     dword ptr [rax+8], 2
0x180076b87  call    cs:__imp_Tbsi_Context_Create
0x180076b8d  test    eax, eax
0x180076b8f  jns     short loc_180076BAF
0x180076b91  mov     rcx, [rsp+78h]; this
0x180076b96  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\trustlet\\tpmpla"...
0x180076b9d  mov     r9d, eax; char *
0x180076ba0  mov     edx, 1Bh; void *
0x180076ba5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180076baa  jmp     loc_180076C30
0x180076baf  mov     edx, [rdi]
0x180076bb1  lea     rcx, [rsp+78h+var_38]
0x180076bb6  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180076bbb  mov     rax, [rsp+78h+var_38]
0x180076bc0  mov     r9, rbp; pabCommand
0x180076bc3  mov     rcx, [rbx]; hContext
0x180076bc6  xor     edx, edx; Locality
0x180076bc8  mov     [rsp+78h+pcbResult], rdi; pcbResult
0x180076bcd  mov     r8d, 0C8h; Priority
0x180076bd3  mov     [rsp+78h+pabResult], rax; pabResult
0x180076bd8  mov     [rsp+78h+cbCommand], esi; int
0x180076bdc  call    cs:__imp_Tbsip_Submit_Command
0x180076be2  test    eax, eax
0x180076be4  jns     short loc_180076C1E
0x180076be6  mov     rcx, [rsp+78h]; this
0x180076beb  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\trustlet\\tpmpla"...
0x180076bf2  mov     r9d, eax; char *
0x180076bf5  mov     edx, 27h ; '''; void *
0x180076bfa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180076bff  mov     rcx, [rsp+78h+var_38]; hMem
0x180076c04  mov     ebx, eax
0x180076c06  mov     [rsp+78h+var_38], 0
0x180076c0f  test    rcx, rcx
0x180076c12  jz      short loc_180076C1A
0x180076c14  call    cs:__imp_LocalFree
0x180076c1a  mov     eax, ebx
0x180076c1c  jmp     short loc_180076C30
0x180076c1e  mov     rax, [rsp+78h+var_38]
0x180076c23  mov     rcx, [rsp+78h+arg_20]
0x180076c2b  mov     [rcx], rax
0x180076c2e  xor     eax, eax
0x180076c30  add     rsp, 58h
0x180076c34  pop     rdi
0x180076c35  pop     rsi
0x180076c36  pop     rbp
0x180076c37  pop     rbx
0x180076c38  retn
```
