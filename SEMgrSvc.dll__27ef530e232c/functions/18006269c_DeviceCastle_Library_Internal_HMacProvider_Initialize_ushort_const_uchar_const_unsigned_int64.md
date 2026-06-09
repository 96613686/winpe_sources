# DeviceCastle::Library::Internal::HMacProvider::Initialize(ushort const *,uchar const *,unsigned __int64)

- ea: `0x18006269c`
- end: `0x1800627c5`
- name: `?Initialize@HMacProvider@Internal@Library@DeviceCastle@@QEAAJPEBGPEBE_K@Z`
- size: `297`
- prototype: `int(DeviceCastle::Library::Internal::HMacProvider *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180058810`
- `0x18005a7fc`

## callees

- `0x18000584c`
- `0x180013014`
- `0x18006269c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062769`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006277c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006277c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006272f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006272f`
- `bcrypt!BCryptDestroyHash` at `0x180062774`
- `bcrypt!BCryptDestroyHash` at `0x180062774`
- `bcrypt!BCryptCreateHash` at `0x1800627a0`
- `bcrypt!BCryptCreateHash` at `0x1800627a0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180062753`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180062753`

## pseudocode

```c
NTSTATUS __fastcall DeviceCastle::Library::Internal::HMacProvider::Initialize(
        DeviceCastle::Library::Internal::HMacProvider *this,
        const unsigned __int16 *a2,
        UCHAR *a3,
        unsigned __int64 a4)
{
  ULONG cbSecret; // r15d
  char *v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  BCRYPT_ALG_HANDLE *v12; // rdi
  void *v13; // rsi
  DWORD LastError; // ebx
  NTSTATUS result; // eax
  BCRYPT_HASH_HANDLE *v16; // rsi
  void *v17; // rbp
  DWORD v18; // ebx

  cbSecret = a4;
  if ( a4 > 0xFFFFFFFF )
    return -2147024362;
  v8 = (char *)this + 24;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 > *((_QWORD *)v8 + 3) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v8,
      v9,
      a3,
      a2);
  }
  else
  {
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v10 = v8;
    else
      v10 = *(char **)v8;
    v11 = 2 * v9;
    *((_QWORD *)v8 + 2) = v9;
    memmove_0(v10, a2, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  v12 = (BCRYPT_ALG_HANDLE *)((char *)this + 8);
  v13 = (void *)*((_QWORD *)this + 1);
  if ( v13 )
  {
    LastError = GetLastError();
    BCryptCloseAlgorithmProvider(v13, 0);
    SetLastError(LastError);
  }
  *v12 = 0;
  result = BCryptOpenAlgorithmProvider(v12, a2, L"Microsoft Primitive Provider", 8u);
  if ( result >= 0 )
  {
    v16 = (BCRYPT_HASH_HANDLE *)((char *)this + 16);
    v17 = (void *)*((_QWORD *)this + 2);
    if ( v17 )
    {
      v18 = GetLastError();
      BCryptDestroyHash(v17);
      SetLastError(v18);
    }
    *v16 = 0;
    result = BCryptCreateHash(*v12, v16, 0, 0, a3, cbSecret, 0);
    if ( result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18006269c  push    rbx
0x18006269e  push    rbp
0x18006269f  push    rsi
0x1800626a0  push    rdi
0x1800626a1  push    r12
0x1800626a3  push    r13
0x1800626a5  push    r14
0x1800626a7  push    r15
0x1800626a9  sub     rsp, 48h
0x1800626ad  mov     eax, 0FFFFFFFFh
0x1800626b2  mov     r15, r9
0x1800626b5  mov     r12, r8
0x1800626b8  mov     r14, rdx
0x1800626bb  mov     rbp, rcx
0x1800626be  cmp     r9, rax
0x1800626c1  ja      loc_1800627AF
0x1800626c7  add     rcx, 18h
0x1800626cb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800626cf  xor     r13d, r13d
0x1800626d2  inc     rdx
0x1800626d5  cmp     [r14+rdx*2], r13w
0x1800626da  jnz     short loc_1800626D2
0x1800626dc  cmp     rdx, [rcx+18h]
0x1800626e0  ja      short loc_18006270E
0x1800626e2  cmp     qword ptr [rcx+18h], 7
0x1800626e7  jbe     short loc_1800626EE
0x1800626e9  mov     rdi, [rcx]
0x1800626ec  jmp     short loc_1800626F1
0x1800626ee  mov     rdi, rcx
0x1800626f1  lea     rbx, [rdx+rdx]
0x1800626f5  mov     [rcx+10h], rdx
0x1800626f9  mov     r8, rbx; Size
0x1800626fc  mov     rdx, r14; Src
0x1800626ff  mov     rcx, rdi; void *
0x180062702  call    memmove_0
0x180062707  mov     [rbx+rdi], r13w
0x18006270c  jmp     short loc_180062716
0x18006270e  mov     r9, r14
0x180062711  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180062716  lea     rdi, [rbp+8]
0x18006271a  mov     rsi, [rdi]
0x18006271d  test    rsi, rsi
0x180062720  jz      short loc_18006273D
0x180062722  call    cs:__imp_GetLastError
0x180062728  xor     edx, edx; dwFlags
0x18006272a  mov     rcx, rsi; hAlgorithm
0x18006272d  mov     ebx, eax
0x18006272f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180062735  mov     ecx, ebx; dwErrCode
0x180062737  call    cs:__imp_SetLastError
0x18006273d  mov     r9d, 8; dwFlags
0x180062743  mov     [rdi], r13
0x180062746  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18006274d  mov     rdx, r14; pszAlgId
0x180062750  mov     rcx, rdi; phAlgorithm
0x180062753  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180062759  test    eax, eax
0x18006275b  js      short loc_1800627B4
0x18006275d  lea     rsi, [rbp+10h]
0x180062761  mov     rbp, [rsi]
0x180062764  test    rbp, rbp
0x180062767  jz      short loc_180062782
0x180062769  call    cs:__imp_GetLastError
0x18006276f  mov     rcx, rbp; hHash
0x180062772  mov     ebx, eax
0x180062774  call    cs:__imp_BCryptDestroyHash
0x18006277a  mov     ecx, ebx; dwErrCode
0x18006277c  call    cs:__imp_SetLastError
0x180062782  mov     [rsi], r13
0x180062785  xor     r9d, r9d; cbHashObject
0x180062788  mov     rcx, [rdi]; hAlgorithm
0x18006278b  xor     r8d, r8d; pbHashObject
0x18006278e  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x180062793  mov     rdx, rsi; phHash
0x180062796  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18006279b  mov     [rsp+88h+pbSecret], r12; pbSecret
0x1800627a0  call    cs:__imp_BCryptCreateHash
0x1800627a6  test    eax, eax
0x1800627a8  js      short loc_1800627B4
0x1800627aa  mov     eax, r13d
0x1800627ad  jmp     short loc_1800627B4
0x1800627af  mov     eax, 80070216h
0x1800627b4  add     rsp, 48h
0x1800627b8  pop     r15
0x1800627ba  pop     r14
0x1800627bc  pop     r13
0x1800627be  pop     r12
0x1800627c0  pop     rdi
0x1800627c1  pop     rsi
0x1800627c2  pop     rbp
0x1800627c3  pop     rbx
0x1800627c4  retn
```
