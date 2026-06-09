# _anonymous_namespace_::HashData

- ea: `0x140059688`
- end: `0x140059771`
- name: `_anonymous_namespace_::HashData`
- size: `233`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059778`
- `0x140059944`

## callees

- `0x14002bdcc`
- `0x140040338`
- `0x140059688`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1400596cb`
- `bcrypt!BCryptCreateHash` at `0x1400596cb`
- `bcrypt!BCryptHashData` at `0x1400596ef`
- `bcrypt!BCryptHashData` at `0x140059724`
- `bcrypt!BCryptHashData` at `0x1400596ef`
- `bcrypt!BCryptHashData` at `0x140059724`
- `bcrypt!BCryptFinishHash` at `0x140059749`
- `bcrypt!BCryptFinishHash` at `0x140059749`

## string_xrefs

- `0x140059703`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`

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
0x140059688  mov     rax, rsp
0x14005968b  push    rbx
0x14005968c  push    rbp
0x14005968d  push    rsi
0x14005968e  push    rdi
0x14005968f  sub     rsp, 58h
0x140059693  mov     dword ptr [rax-48h], 0
0x14005969a  mov     rdi, r9
0x14005969d  xor     r9d, r9d; cbHashObject
0x1400596a0  mov     dword ptr [rax-50h], 0
0x1400596a7  mov     rsi, r8
0x1400596aa  mov     qword ptr [rax-38h], 0
0x1400596b2  mov     rbx, rdx
0x1400596b5  mov     qword ptr [rax-58h], 0
0x1400596bd  mov     rbp, rcx
0x1400596c0  lea     rdx, [rax-38h]; phHash
0x1400596c4  lea     ecx, [r9+41h]; hAlgorithm
0x1400596c8  xor     r8d, r8d; pbHashObject
0x1400596cb  call    cs:__imp_BCryptCreateHash
0x1400596d1  test    eax, eax
0x1400596d3  jns     short loc_1400596DC
0x1400596d5  mov     edx, 22h ; '"'
0x1400596da  jmp     short loc_1400596FE
0x1400596dc  test    rbx, rbx
0x1400596df  jz      short loc_140059716
0x1400596e1  mov     rcx, [rsp+78h+hHash]; hHash
0x1400596e6  mov     r8d, ebx; cbInput
0x1400596e9  xor     r9d, r9d; dwFlags
0x1400596ec  mov     rdx, rbp; pbInput
0x1400596ef  call    cs:__imp_BCryptHashData
0x1400596f5  test    eax, eax
0x1400596f7  jns     short loc_140059716
0x1400596f9  mov     edx, 2Ah ; '*'; void *
0x1400596fe  mov     rcx, [rsp+78h]; this
0x140059703  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x14005970a  mov     r9d, eax; char *
0x14005970d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140059712  mov     ebx, eax
0x140059714  jmp     short loc_14005975C
0x140059716  mov     rcx, [rsp+78h+hHash]; hHash
0x14005971b  mov     r8d, edi; cbInput
0x14005971e  xor     r9d, r9d; dwFlags
0x140059721  mov     rdx, rsi; pbInput
0x140059724  call    cs:__imp_BCryptHashData
0x14005972a  test    eax, eax
0x14005972c  jns     short loc_140059735
0x14005972e  mov     edx, 30h ; '0'
0x140059733  jmp     short loc_1400596FE
0x140059735  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x14005973d  xor     r9d, r9d; dwFlags
0x140059740  mov     rcx, [rsp+78h+hHash]; hHash
0x140059745  lea     r8d, [r9+20h]; cbOutput
0x140059749  call    cs:__imp_BCryptFinishHash
0x14005974f  test    eax, eax
0x140059751  jns     short loc_14005975A
0x140059753  mov     edx, 36h ; '6'
0x140059758  jmp     short loc_1400596FE
0x14005975a  xor     ebx, ebx
0x14005975c  lea     rcx, [rsp+78h+hHash]
0x140059761  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140059766  mov     eax, ebx
0x140059768  add     rsp, 58h
0x14005976c  pop     rdi
0x14005976d  pop     rsi
0x14005976e  pop     rbp
0x14005976f  pop     rbx
0x140059770  retn
```
