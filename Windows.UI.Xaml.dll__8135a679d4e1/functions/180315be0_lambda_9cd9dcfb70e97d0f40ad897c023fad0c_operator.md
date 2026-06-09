# _lambda_9cd9dcfb70e97d0f40ad897c023fad0c_::operator()

- ea: `0x180315be0`
- end: `0x180315d22`
- name: `_lambda_9cd9dcfb70e97d0f40ad897c023fad0c_::operator()`
- size: `322`
- prototype: `std::wstring *__fastcall(std::wstring *result)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18030b470`

## callees

- `0x180315be0`
- `0x180315d28`
- `0x1803cf970`
- `0x180645094`
- `0x180742244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180315c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180315c3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180315c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180315c48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180315c59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180315c59`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180315c97`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180315c97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180315c30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180315c8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180315c30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180315c8a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180315ca5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180315ca5`

## pseudocode

```c
std::wstring *__fastcall lambda_9cd9dcfb70e97d0f40ad897c023fad0c_::operator()(std::wstring *result, std::wstring *a2)
{
  const wchar_t *v3; // rbx
  PSID *m_ptr; // rsi
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  std::wstring *dwLength; // [rsp+50h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > tokenData; // [rsp+60h] [rbp+18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > hCurrentProcessToken; // [rsp+68h] [rbp+20h] BYREF

  dwLength = result;
  v3 = L"HI";
  std::wstring::wstring(a2, L"HI");
  LODWORD(dwLength) = 0;
  hCurrentProcessToken.m_ptr = (void *)-4LL;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, 0, 0, (PDWORD)&dwLength)
    || GetLastError() == 122 )
  {
    tokenData.m_ptr = LocalAlloc(0, (unsigned int)dwLength);
    m_ptr = (PSID *)tokenData.m_ptr;
    if ( tokenData.m_ptr
      && GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFCLL,
           TokenIntegrityLevel,
           tokenData.m_ptr,
           (DWORD)dwLength,
           (PDWORD)&dwLength) )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(*m_ptr);
      SidSubAuthority = GetSidSubAuthority(*m_ptr, (unsigned int)*SidSubAuthorityCount - 1);
      if ( *SidSubAuthority < 0x4000 )
      {
        if ( *SidSubAuthority < 0x3000 )
        {
          if ( *SidSubAuthority < 0x2100 )
          {
            v3 = L"ME";
            if ( *SidSubAuthority < 0x2000 )
              v3 = L"LW";
          }
          else
          {
            v3 = L"MP";
          }
        }
      }
      else
      {
        v3 = L"SI";
      }
      std::wstring::_Assign<unsigned short>(a2, v3, 2u);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&tokenData);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hCurrentProcessToken);
  }
  else
  {
    CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFCLL);
  }
  return a2;
}

```

## disassembly

```asm
0x180315be0  mov     [rsp+currentIL], rbx
0x180315be5  mov     [rsp+dwLength], rcx
0x180315bea  push    rbp
0x180315beb  push    rsi
0x180315bec  push    rdi
0x180315bed  sub     rsp, 30h
0x180315bf1  mov     rdi, rdx
0x180315bf4  lea     rbx, aHi; "HI"
0x180315bfb  mov     rdx, rbx; _Ptr
0x180315bfe  mov     rcx, rdi; this
0x180315c01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180315c06  mov     rbp, 0FFFFFFFFFFFFFFFCh
0x180315c0d  mov     dword ptr [rsp+48h+dwLength], 0
0x180315c15  lea     rax, [rsp+48h+dwLength]
0x180315c1a  mov     [rsp+48h+hCurrentProcessToken.m_ptr], rbp
0x180315c1f  xor     r9d, r9d; TokenInformationLength
0x180315c22  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180315c27  xor     r8d, r8d; TokenInformation
0x180315c2a  mov     rcx, rbp; TokenHandle
0x180315c2d  lea     edx, [rbp+1Dh]; TokenInformationClass
0x180315c30  call    cs:__imp_GetTokenInformation
0x180315c36  test    eax, eax
0x180315c38  jnz     short loc_180315C53
0x180315c3a  call    cs:__imp_GetLastError
0x180315c40  cmp     eax, 7Ah ; 'z'
0x180315c43  jz      short loc_180315C53
0x180315c45  mov     rcx, rbp; hObject
0x180315c48  call    cs:__imp_CloseHandle
0x180315c4e  jmp     loc_180315D12
0x180315c53  mov     edx, dword ptr [rsp+48h+dwLength]; uBytes
0x180315c57  xor     ecx, ecx; uFlags
0x180315c59  call    cs:__imp_LocalAlloc
0x180315c5f  mov     [rsp+48h+tokenData.m_ptr], rax
0x180315c64  mov     rsi, rax
0x180315c67  test    rax, rax
0x180315c6a  jz      loc_180315CFE
0x180315c70  mov     r9d, dword ptr [rsp+48h+dwLength]; TokenInformationLength
0x180315c75  lea     rax, [rsp+48h+dwLength]
0x180315c7a  mov     r8, rsi; TokenInformation
0x180315c7d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180315c82  mov     edx, 19h; TokenInformationClass
0x180315c87  mov     rcx, rbp; TokenHandle
0x180315c8a  call    cs:__imp_GetTokenInformation
0x180315c90  test    eax, eax
0x180315c92  jz      short loc_180315CFE
0x180315c94  mov     rcx, [rsi]; pSid
0x180315c97  call    cs:__imp_GetSidSubAuthorityCount
0x180315c9d  mov     rcx, [rsi]; pSid
0x180315ca0  movzx   edx, byte ptr [rax]
0x180315ca3  dec     edx; nSubAuthority
0x180315ca5  call    cs:__imp_GetSidSubAuthority
0x180315cab  cmp     dword ptr [rax], 4000h
0x180315cb1  jb      short loc_180315CBC
0x180315cb3  lea     rbx, aSi; "SI"
0x180315cba  jmp     short loc_180315CED
0x180315cbc  cmp     dword ptr [rax], 3000h
0x180315cc2  jnb     short loc_180315CED
0x180315cc4  cmp     dword ptr [rax], 2100h
0x180315cca  jb      short loc_180315CD5
0x180315ccc  lea     rbx, aMp; "MP"
0x180315cd3  jmp     short loc_180315CED
0x180315cd5  cmp     dword ptr [rax], 2000h
0x180315cdb  lea     rbx, aMe; "ME"
0x180315ce2  lea     rcx, aLw; "LW"
0x180315ce9  cmovb   rbx, rcx
0x180315ced  mov     r8d, 2; _Count
0x180315cf3  mov     rdx, rbx; _Ptr
0x180315cf6  mov     rcx, rdi; this
0x180315cf9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180315cfe  lea     rcx, [rsp+48h+tokenData]; this
0x180315d03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180315d08  lea     rcx, [rsp+48h+hCurrentProcessToken]; this
0x180315d0d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180315d12  mov     rbx, [rsp+48h+currentIL]
0x180315d17  mov     rax, rdi
0x180315d1a  add     rsp, 30h
0x180315d1e  pop     rdi
0x180315d1f  pop     rsi
0x180315d20  pop     rbp
0x180315d21  retn
```
