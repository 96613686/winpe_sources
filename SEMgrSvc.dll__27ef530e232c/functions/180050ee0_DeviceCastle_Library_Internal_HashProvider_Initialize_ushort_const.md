# DeviceCastle::Library::Internal::HashProvider::Initialize(ushort const *)

- ea: `0x180050ee0`
- end: `0x180050fe4`
- name: `?Initialize@HashProvider@Internal@Library@DeviceCastle@@QEAAJPEBG@Z`
- size: `260`
- prototype: `int(DeviceCastle::Library::Internal::HashProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800485e4`
- `0x180058520`
- `0x180058810`
- `0x180061854`

## callees

- `0x18000584c`
- `0x180013014`
- `0x180050ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050fa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050fa1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180050f5c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180050f5c`
- `bcrypt!BCryptDestroyHash` at `0x180050f99`
- `bcrypt!BCryptDestroyHash` at `0x180050f99`
- `bcrypt!BCryptCreateHash` at `0x180050fc7`
- `bcrypt!BCryptCreateHash` at `0x180050fc7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180050f79`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180050f79`

## pseudocode

```c
__int64 __fastcall DeviceCastle::Library::Internal::HashProvider::Initialize(
        DeviceCastle::Library::Internal::HashProvider *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  char *v5; // rcx
  unsigned __int64 v6; // rdx
  char *v7; // rdi
  __int64 v8; // rbx
  BCRYPT_ALG_HANDLE *v9; // rdi
  void *v10; // rsi
  DWORD LastError; // ebx
  NTSTATUS Hash; // ecx
  void *v13; // rsi
  DWORD v14; // ebx

  v5 = (char *)this + 24;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > *((_QWORD *)v5 + 3) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v5,
      v6,
      a3,
      a2);
  }
  else
  {
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v7 = v5;
    else
      v7 = *(char **)v5;
    v8 = 2 * v6;
    *((_QWORD *)v5 + 2) = v6;
    memmove_0(v7, a2, 2 * v6);
    *(_WORD *)&v7[v8] = 0;
  }
  v9 = (BCRYPT_ALG_HANDLE *)((char *)this + 8);
  v10 = (void *)*((_QWORD *)this + 1);
  if ( v10 )
  {
    LastError = GetLastError();
    BCryptCloseAlgorithmProvider(v10, 0);
    SetLastError(LastError);
  }
  *v9 = 0;
  Hash = BCryptOpenAlgorithmProvider(v9, a2, 0, 0);
  if ( Hash >= 0 )
  {
    v13 = (void *)*((_QWORD *)this + 2);
    if ( v13 )
    {
      v14 = GetLastError();
      BCryptDestroyHash(v13);
      SetLastError(v14);
    }
    *((_QWORD *)this + 2) = 0;
    Hash = BCryptCreateHash(*v9, (BCRYPT_HASH_HANDLE *)this + 2, 0, 0, 0, 0, 0);
    if ( Hash >= 0 )
      return 0;
  }
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x180050ee0  push    rbx
0x180050ee2  push    rbp
0x180050ee3  push    rsi
0x180050ee4  push    rdi
0x180050ee5  push    r14
0x180050ee7  push    r15
0x180050ee9  sub     rsp, 48h
0x180050eed  mov     rbp, rdx
0x180050ef0  mov     r14, rcx
0x180050ef3  add     rcx, 18h
0x180050ef7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180050efb  xor     r15d, r15d
0x180050efe  inc     rdx
0x180050f01  cmp     [rbp+rdx*2+0], r15w
0x180050f07  jnz     short loc_180050EFE
0x180050f09  cmp     rdx, [rcx+18h]
0x180050f0d  ja      short loc_180050F3B
0x180050f0f  cmp     qword ptr [rcx+18h], 7
0x180050f14  jbe     short loc_180050F1B
0x180050f16  mov     rdi, [rcx]
0x180050f19  jmp     short loc_180050F1E
0x180050f1b  mov     rdi, rcx
0x180050f1e  lea     rbx, [rdx+rdx]
0x180050f22  mov     [rcx+10h], rdx
0x180050f26  mov     r8, rbx; Size
0x180050f29  mov     rdx, rbp; Src
0x180050f2c  mov     rcx, rdi; void *
0x180050f2f  call    memmove_0
0x180050f34  mov     [rbx+rdi], r15w
0x180050f39  jmp     short loc_180050F43
0x180050f3b  mov     r9, rbp
0x180050f3e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180050f43  lea     rdi, [r14+8]
0x180050f47  mov     rsi, [rdi]
0x180050f4a  test    rsi, rsi
0x180050f4d  jz      short loc_180050F6A
0x180050f4f  call    cs:__imp_GetLastError
0x180050f55  xor     edx, edx; dwFlags
0x180050f57  mov     rcx, rsi; hAlgorithm
0x180050f5a  mov     ebx, eax
0x180050f5c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180050f62  mov     ecx, ebx; dwErrCode
0x180050f64  call    cs:__imp_SetLastError
0x180050f6a  xor     r9d, r9d; dwFlags
0x180050f6d  mov     [rdi], r15
0x180050f70  xor     r8d, r8d; pszImplementation
0x180050f73  mov     rdx, rbp; pszAlgId
0x180050f76  mov     rcx, rdi; phAlgorithm
0x180050f79  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180050f7f  mov     ecx, eax
0x180050f81  test    eax, eax
0x180050f83  js      short loc_180050FD5
0x180050f85  mov     rsi, [r14+10h]
0x180050f89  test    rsi, rsi
0x180050f8c  jz      short loc_180050FA7
0x180050f8e  call    cs:__imp_GetLastError
0x180050f94  mov     rcx, rsi; hHash
0x180050f97  mov     ebx, eax
0x180050f99  call    cs:__imp_BCryptDestroyHash
0x180050f9f  mov     ecx, ebx; dwErrCode
0x180050fa1  call    cs:__imp_SetLastError
0x180050fa7  mov     [r14+10h], r15
0x180050fab  lea     rdx, [r14+10h]; phHash
0x180050faf  mov     rcx, [rdi]; hAlgorithm
0x180050fb2  xor     r9d, r9d; cbHashObject
0x180050fb5  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x180050fba  xor     r8d, r8d; pbHashObject
0x180050fbd  mov     [rsp+78h+cbSecret], r15d; cbSecret
0x180050fc2  mov     [rsp+78h+pbSecret], r15; pbSecret
0x180050fc7  call    cs:__imp_BCryptCreateHash
0x180050fcd  test    eax, eax
0x180050fcf  mov     ecx, eax
0x180050fd1  cmovns  ecx, r15d
0x180050fd5  mov     eax, ecx
0x180050fd7  add     rsp, 48h
0x180050fdb  pop     r15
0x180050fdd  pop     r14
0x180050fdf  pop     rdi
0x180050fe0  pop     rsi
0x180050fe1  pop     rbp
0x180050fe2  pop     rbx
0x180050fe3  retn
```
