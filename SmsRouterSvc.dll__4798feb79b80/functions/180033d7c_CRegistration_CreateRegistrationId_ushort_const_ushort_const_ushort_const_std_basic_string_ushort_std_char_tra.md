# CRegistration::CreateRegistrationId(ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180033d7c`
- end: `0x180033fce`
- name: `?CreateRegistrationId@CRegistration@@SAJPEBG00AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010a28`

## callees

- `0x180003a60`
- `0x18000498c`
- `0x180004998`
- `0x18000659c`
- `0x1800069f0`
- `0x180033d7c`
- `0x1800351fc`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033e16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033e16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f4d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033e35`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033e35`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033e61`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033e61`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033ea5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033ea5`

## string_xrefs

- `0x180033e41`: `CoCreateGuid`
- `0x180033e7c`: `CRegistration::CreateRegistrationId`
- `0x180033f38`: `CRegistration::CreateRegistrationId`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRegistration::CreateRegistrationId(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  const WCHAR *v8; // r8
  unsigned __int64 v9; // rdi
  HRESULT v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int KeyW; // eax
  HKEY v14; // rbx
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  const wchar_t *v17; // rax
  void *v18; // rsi
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpValue[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp-90h]
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR sz[64]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(sz, 0, sizeof(sz));
  pcbData = 128;
  CRegistration::GetUniqueId(lpValue, a1, a2, a3);
  v8 = (const WCHAR *)lpValue;
  if ( v23 > 7 )
    v8 = lpValue[0];
  v9 = -1;
  if ( !RegGetValueW(g_SmsRouterKey, L"Registration\\Map", v8, 2u, 0, sz, &pcbData) )
    goto LABEL_21;
  pguid = 0;
  v10 = CoCreateGuid(&pguid);
  v11 = v10;
  if ( v10 < 0 )
  {
    LogSmsRouterError("CRegistration::CreateRegistrationId", 0x5ABu, v10, "CoCreateGuid");
    goto LABEL_29;
  }
  v12 = StringFromGUID2(&pguid, sz, 64);
  v11 = v12;
  if ( v12 < 0 )
  {
    LogSmsRouterError("CRegistration::CreateRegistrationId", 0x5B1u, v12, "StringFromGUID2");
    goto LABEL_29;
  }
  phkResult[0] = 0;
  KeyW = RegCreateKeyW(g_SmsRouterKey, L"Registration\\Map", phkResult);
  if ( !KeyW )
  {
    v14 = phkResult[0];
    phkResult[1] = phkResult[0];
    v15 = (const WCHAR *)lpValue;
    if ( v23 > 7 )
      v15 = lpValue[0];
    v16 = -1;
    do
      ++v16;
    while ( sz[v16] );
    RegSetValueExW(phkResult[0], v15, 0, 1u, (const BYTE *)sz, 2 * v16 + 2);
    v17 = (const wchar_t *)lpValue;
    if ( v23 > 7 )
      v17 = lpValue[0];
    LogSmsRouterInfo("CRegistration::CreateRegistrationId", 0x5C2u, "RegId: %S, UniqueId: %S", sz, v17);
    if ( v14 )
      RegCloseKey(v14);
    do
LABEL_21:
      ++v9;
    while ( sz[v9] );
    if ( v9 > (unsigned __int64)a4[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a4);
    }
    else
    {
      if ( (unsigned __int64)a4[3] <= 7 )
        v18 = a4;
      else
        v18 = *a4;
      a4[2] = (void *)v9;
      memmove_0(v18, sz, 2 * v9);
      *((_WORD *)v18 + v9) = 0;
    }
    v11 = 0;
    goto LABEL_29;
  }
  if ( KeyW > 0 )
    KeyW = (unsigned __int16)KeyW | 0x80070000;
  v11 = KeyW;
LABEL_29:
  std::wstring::~wstring(lpValue);
  return v11;
}

```

## disassembly

```asm
0x180033d7c  push    rbp
0x180033d7e  push    rbx
0x180033d7f  push    rsi
0x180033d80  push    rdi
0x180033d81  push    r14
0x180033d83  push    r15
0x180033d85  lea     rbp, [rsp-28h]
0x180033d8a  sub     rsp, 128h
0x180033d91  mov     rax, cs:__security_cookie
0x180033d98  xor     rax, rsp
0x180033d9b  mov     [rbp+50h+var_40], rax
0x180033d9f  mov     r14, r9
0x180033da2  mov     rsi, r8
0x180033da5  mov     rdi, rdx
0x180033da8  mov     rbx, rcx
0x180033dab  mov     r15d, 80h
0x180033db1  mov     r8d, r15d; Size
0x180033db4  xor     edx, edx; Val
0x180033db6  lea     rcx, [rbp+50h+sz]; void *
0x180033dba  call    memset_0
0x180033dbf  mov     [rsp+150h+var_110], r15d
0x180033dc4  mov     r9, rsi
0x180033dc7  mov     r8, rdi
0x180033dca  mov     rdx, rbx
0x180033dcd  lea     rcx, [rsp+150h+lpValue]
0x180033dd2  call    ?GetUniqueId@CRegistration@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00@Z; CRegistration::GetUniqueId(ushort const *,ushort const *,ushort const *)
0x180033dd7  nop
0x180033dd8  lea     r8, [rsp+150h+lpValue]
0x180033ddd  cmp     [rsp+150h+var_E0], 7
0x180033de3  cmova   r8, [rsp+150h+lpValue]; lpValue
0x180033de9  lea     rax, [rsp+150h+var_110]
0x180033dee  mov     [rsp+150h+pcbData], rax; pcbData
0x180033df3  lea     rax, [rbp+50h+sz]
0x180033df7  mov     [rsp+150h+pvData], rax; pvData
0x180033dfc  xor     r15d, r15d
0x180033dff  mov     [rsp+150h+pdwType], r15; pdwType
0x180033e04  lea     r9d, [r15+2]; dwFlags
0x180033e08  lea     rdx, aRegistrationMa; "Registration\\Map"
0x180033e0f  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x180033e16  call    cs:__imp_RegGetValueW
0x180033e1c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180033e20  test    eax, eax
0x180033e22  jz      loc_180033F53
0x180033e28  xorps   xmm0, xmm0
0x180033e2b  movups  xmmword ptr [rsp+150h+pguid.Data1], xmm0
0x180033e30  lea     rcx, [rsp+150h+pguid]; pguid
0x180033e35  call    cs:__imp_CoCreateGuid
0x180033e3b  mov     ebx, eax
0x180033e3d  test    eax, eax
0x180033e3f  jns     short loc_180033E52
0x180033e41  lea     r9, aCocreateguid; "CoCreateGuid"
0x180033e48  mov     r8d, eax
0x180033e4b  mov     edx, 5ABh
0x180033e50  jmp     short loc_180033E7C
0x180033e52  mov     r8d, 40h ; '@'; cchMax
0x180033e58  lea     rdx, [rbp+50h+sz]; lpsz
0x180033e5c  lea     rcx, [rsp+150h+pguid]; rguid
0x180033e61  call    cs:__imp_StringFromGUID2
0x180033e67  mov     ebx, eax
0x180033e69  test    eax, eax
0x180033e6b  jns     short loc_180033E8D
0x180033e6d  lea     r9, aStringfromguid_0; "StringFromGUID2"
0x180033e74  mov     r8d, eax; int
0x180033e77  mov     edx, 5B1h; unsigned int
0x180033e7c  lea     rcx, aCregistrationC; "CRegistration::CreateRegistrationId"
0x180033e83  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180033e88  jmp     loc_180033FA6
0x180033e8d  mov     [rsp+150h+phkResult], r15
0x180033e92  lea     r8, [rsp+150h+phkResult]; phkResult
0x180033e97  lea     rdx, aRegistrationMa; "Registration\\Map"
0x180033e9e  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180033ea5  call    cs:__imp_RegCreateKeyW
0x180033eab  test    eax, eax
0x180033ead  jz      short loc_180033EC0
0x180033eaf  jle     short loc_180033EB9
0x180033eb1  movzx   eax, ax
0x180033eb4  or      eax, 80070000h
0x180033eb9  mov     ebx, eax
0x180033ebb  jmp     loc_180033FA6
0x180033ec0  mov     rbx, [rsp+150h+phkResult]
0x180033ec5  mov     [rsp+150h+var_100], rbx
0x180033eca  lea     rdx, [rsp+150h+lpValue]
0x180033ecf  cmp     [rsp+150h+var_E0], 7
0x180033ed5  cmova   rdx, [rsp+150h+lpValue]; lpValueName
0x180033edb  lea     rcx, [rbp+50h+sz]
0x180033edf  mov     rax, rdi
0x180033ee2  inc     rax
0x180033ee5  cmp     [rcx+rax*2], r15w
0x180033eea  jnz     short loc_180033EE2
0x180033eec  lea     eax, ds:2[rax*2]
0x180033ef3  mov     dword ptr [rsp+150h+pvData], eax; cbData
0x180033ef7  lea     rax, [rbp+50h+sz]
0x180033efb  mov     [rsp+150h+pdwType], rax; lpData
0x180033f00  mov     r9d, 1; dwType
0x180033f06  xor     r8d, r8d; Reserved
0x180033f09  mov     rcx, rbx; hKey
0x180033f0c  call    cs:__imp_RegSetValueExW
0x180033f12  lea     rax, [rsp+150h+lpValue]
0x180033f17  cmp     [rsp+150h+var_E0], 7
0x180033f1d  cmova   rax, [rsp+150h+lpValue]
0x180033f23  mov     [rsp+150h+pdwType], rax
0x180033f28  lea     r9, [rbp+50h+sz]
0x180033f2c  lea     r8, aRegidSUniqueid; "RegId: %S, UniqueId: %S"
0x180033f33  mov     edx, 5C2h; unsigned int
0x180033f38  lea     rcx, aCregistrationC; "CRegistration::CreateRegistrationId"
0x180033f3f  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180033f44  nop
0x180033f45  test    rbx, rbx
0x180033f48  jz      short loc_180033F53
0x180033f4a  mov     rcx, rbx; hKey
0x180033f4d  call    cs:__imp_RegCloseKey
0x180033f53  lea     rax, [rbp+50h+sz]
0x180033f57  inc     rdi
0x180033f5a  cmp     [rax+rdi*2], r15w
0x180033f5f  jnz     short loc_180033F57
0x180033f61  cmp     rdi, [r14+18h]
0x180033f65  ja      short loc_180033F94
0x180033f67  cmp     qword ptr [r14+18h], 7
0x180033f6c  jbe     short loc_180033F73
0x180033f6e  mov     rsi, [r14]
0x180033f71  jmp     short loc_180033F76
0x180033f73  mov     rsi, r14
0x180033f76  mov     [r14+10h], rdi
0x180033f7a  lea     rbx, [rdi+rdi]
0x180033f7e  mov     r8, rbx; Size
0x180033f81  lea     rdx, [rbp+50h+sz]; Src
0x180033f85  mov     rcx, rsi; void *
0x180033f88  call    memmove_0
0x180033f8d  mov     [rbx+rsi], r15w
0x180033f92  jmp     short loc_180033FA3
0x180033f94  lea     r9, [rbp+50h+sz]
0x180033f98  mov     rdx, rdi
0x180033f9b  mov     rcx, r14
0x180033f9e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180033fa3  mov     ebx, r15d
0x180033fa6  lea     rcx, [rsp+150h+lpValue]; void *
0x180033fab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033fb0  mov     eax, ebx
0x180033fb2  mov     rcx, [rbp+50h+var_40]
0x180033fb6  xor     rcx, rsp; StackCookie
0x180033fb9  call    __security_check_cookie
0x180033fbe  add     rsp, 128h
0x180033fc5  pop     r15
0x180033fc7  pop     r14
0x180033fc9  pop     rdi
0x180033fca  pop     rsi
0x180033fcb  pop     rbx
0x180033fcc  pop     rbp
0x180033fcd  retn
```
