# _anonymous_namespace_::HashData

- ea: `0x14007ecd8`
- end: `0x14007edda`
- name: `_anonymous_namespace_::HashData`
- size: `258`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007ede0`
- `0x14007efc0`

## callees

- `0x14002b430`
- `0x1400589a0`
- `0x14007ecd8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x14007ed1b`
- `bcrypt!BCryptCreateHash` at `0x14007ed1b`
- `bcrypt!BCryptHashData` at `0x14007ed45`
- `bcrypt!BCryptHashData` at `0x14007ed80`
- `bcrypt!BCryptHashData` at `0x14007ed45`
- `bcrypt!BCryptHashData` at `0x14007ed80`
- `bcrypt!BCryptFinishHash` at `0x14007edab`
- `bcrypt!BCryptFinishHash` at `0x14007edab`

## string_xrefs

- `0x14007ed5f`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::HashData(
        PUCHAR pbInput,
        __int64 cbInput,
        PUCHAR a3,
        ULONG a4,
        PUCHAR pbOutput)
{
  NTSTATUS Hash; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-58h]
  BCRYPT_HASH_HANDLE hHash[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  hHash[0] = 0;
  Hash = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, hHash, 0, 0, 0, 0, 0);
  if ( Hash >= 0 )
  {
    if ( cbInput && (Hash = BCryptHashData(hHash[0], pbInput, cbInput, 0), Hash < 0) )
    {
      v10 = 42;
    }
    else
    {
      Hash = BCryptHashData(hHash[0], a3, a4, 0);
      if ( Hash >= 0 )
      {
        Hash = BCryptFinishHash(hHash[0], pbOutput, 0x20u, 0);
        if ( Hash >= 0 )
        {
          v11 = 0;
          goto LABEL_12;
        }
        v10 = 54;
      }
      else
      {
        v10 = 48;
      }
    }
  }
  else
  {
    v10 = 34;
  }
  v11 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
          (const char *)(unsigned int)Hash,
          v13);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(hHash);
  return v11;
}

```

## disassembly

```asm
0x14007ecd8  mov     rax, rsp
0x14007ecdb  push    rbx
0x14007ecdc  push    rbp
0x14007ecdd  push    rsi
0x14007ecde  push    rdi
0x14007ecdf  sub     rsp, 58h
0x14007ece3  mov     dword ptr [rax-48h], 0
0x14007ecea  mov     rdi, r9
0x14007eced  xor     r9d, r9d; cbHashObject
0x14007ecf0  mov     dword ptr [rax-50h], 0
0x14007ecf7  mov     rsi, r8
0x14007ecfa  mov     qword ptr [rax-38h], 0
0x14007ed02  mov     rbx, rdx
0x14007ed05  mov     qword ptr [rax-58h], 0
0x14007ed0d  mov     rbp, rcx
0x14007ed10  lea     rdx, [rax-38h]; phHash
0x14007ed14  lea     ecx, [r9+41h]; hAlgorithm
0x14007ed18  xor     r8d, r8d; pbHashObject
0x14007ed1b  call    cs:__imp_BCryptCreateHash
0x14007ed22  nop     dword ptr [rax+rax+00h]
0x14007ed27  test    eax, eax
0x14007ed29  jns     short loc_14007ED32
0x14007ed2b  mov     edx, 22h ; '"'
0x14007ed30  jmp     short loc_14007ED5A
0x14007ed32  test    rbx, rbx
0x14007ed35  jz      short loc_14007ED72
0x14007ed37  mov     rcx, [rsp+78h+hHash]; hHash
0x14007ed3c  mov     r8d, ebx; cbInput
0x14007ed3f  xor     r9d, r9d; dwFlags
0x14007ed42  mov     rdx, rbp; pbInput
0x14007ed45  call    cs:__imp_BCryptHashData
0x14007ed4c  nop     dword ptr [rax+rax+00h]
0x14007ed51  test    eax, eax
0x14007ed53  jns     short loc_14007ED72
0x14007ed55  mov     edx, 2Ah ; '*'; void *
0x14007ed5a  mov     rcx, [rsp+78h]; this
0x14007ed5f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007ed66  mov     r9d, eax; char *
0x14007ed69  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14007ed6e  mov     ebx, eax
0x14007ed70  jmp     short loc_14007EDC4
0x14007ed72  mov     rcx, [rsp+78h+hHash]; hHash
0x14007ed77  mov     r8d, edi; cbInput
0x14007ed7a  xor     r9d, r9d; dwFlags
0x14007ed7d  mov     rdx, rsi; pbInput
0x14007ed80  call    cs:__imp_BCryptHashData
0x14007ed87  nop     dword ptr [rax+rax+00h]
0x14007ed8c  test    eax, eax
0x14007ed8e  jns     short loc_14007ED97
0x14007ed90  mov     edx, 30h ; '0'
0x14007ed95  jmp     short loc_14007ED5A
0x14007ed97  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x14007ed9f  xor     r9d, r9d; dwFlags
0x14007eda2  mov     rcx, [rsp+78h+hHash]; hHash
0x14007eda7  lea     r8d, [r9+20h]; cbOutput
0x14007edab  call    cs:__imp_BCryptFinishHash
0x14007edb2  nop     dword ptr [rax+rax+00h]
0x14007edb7  test    eax, eax
0x14007edb9  jns     short loc_14007EDC2
0x14007edbb  mov     edx, 36h ; '6'
0x14007edc0  jmp     short loc_14007ED5A
0x14007edc2  xor     ebx, ebx
0x14007edc4  lea     rcx, [rsp+78h+hHash]
0x14007edc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14007edce  mov     eax, ebx
0x14007edd0  add     rsp, 58h
0x14007edd4  pop     rdi
0x14007edd5  pop     rsi
0x14007edd6  pop     rbp
0x14007edd7  pop     rbx
0x14007edd8  retn
```
