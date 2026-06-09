# CloseConnectionsRepair::repair(AttributeList *)

- ea: `0x18000b0d0`
- end: `0x18000b280`
- name: `?repair@CloseConnectionsRepair@@UEAA?AW4RepairResult@@PEAVAttributeList@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b0d0`
- `0x18000dd04`
- `0x18000eb74`
- `0x18000fc30`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000b198`
- `msvcrt!_wcsnicmp` at `0x18000b198`
- `msvcrt!_wcsicmp` at `0x18000b1d9`
- `msvcrt!_wcsicmp` at `0x18000b1d9`
- `MPR!WNetEnumResourceW` at `0x18000b223`
- `MPR!WNetEnumResourceW` at `0x18000b223`
- `MPR!WNetGetUserW` at `0x18000b1c4`
- `MPR!WNetGetUserW` at `0x18000b1c4`
- `MPR!WNetCancelConnection2W` at `0x18000b1ed`
- `MPR!WNetCancelConnection2W` at `0x18000b1ed`
- `MPR!WNetCloseEnum` at `0x18000b236`
- `MPR!WNetCloseEnum` at `0x18000b24e`
- `MPR!WNetCloseEnum` at `0x18000b236`
- `MPR!WNetCloseEnum` at `0x18000b24e`
- `MPR!WNetOpenEnumW` at `0x18000b15e`
- `MPR!WNetOpenEnumW` at `0x18000b15e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b16f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b16f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b23f`

## string_xrefs

- `0x18000b11b`: `ServerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloseConnectionsRepair::repair(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // r12
  unsigned __int16 *ImpersonatedUsername; // rdi
  size_t v4; // r14
  unsigned int v5; // esi
  const WCHAR *v6; // rcx
  DWORD cCount; // [rsp+30h] [rbp-478h] BYREF
  DWORD BufferSize; // [rsp+34h] [rbp-474h] BYREF
  DWORD nLength; // [rsp+38h] [rbp-470h] BYREF
  HANDLE hEnum; // [rsp+40h] [rbp-468h] BYREF
  _BYTE v12[24]; // [rsp+48h] [rbp-460h] BYREF
  _BYTE Buffer[24]; // [rsp+60h] [rbp-448h] BYREF
  LPCWSTR String2[61]; // [rsp+78h] [rbp-430h]
  WCHAR UserName[256]; // [rsp+260h] [rbp-248h] BYREF

  hEnum = 0;
  nLength = 256;
  BufferSize = 512;
  cCount = -1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v2 = *(const wchar_t **)(AttributeList::getAttribute(a2, v12, L"ServerPath", 1) + 8);
    ImpersonatedUsername = GetImpersonatedUsername();
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &enum TestException `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_18000B259);
      return 1;
    }
  }
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  if ( !WNetOpenEnumW(1u, 0, 0, 0, &hEnum) )
  {
    while ( 1 )
    {
      if ( WNetEnumResourceW(hEnum, &cCount, Buffer, &BufferSize) )
      {
        WNetCloseEnum(hEnum);
        CoTaskMemFree(ImpersonatedUsername);
        return 0;
      }
      v5 = 0;
      if ( cCount )
        break;
LABEL_13:
      BufferSize = 512;
      cCount = -1;
    }
    while ( 1 )
    {
      if ( !_wcsnicmp(v2, String2[6 * v5], v4) )
      {
        v6 = String2[6 * v5];
        if ( v6[v4] == 92 )
        {
          nLength = 256;
          if ( !WNetGetUserW(v6, UserName, &nLength)
            && _wcsicmp(ImpersonatedUsername, UserName)
            && WNetCancelConnection2W(String2[6 * v5], 0, 0) )
          {
            break;
          }
        }
      }
      if ( ++v5 >= cCount )
        goto LABEL_13;
    }
    WNetCloseEnum(hEnum);
  }
  CoTaskMemFree(ImpersonatedUsername);
  return 1;
}

```

## disassembly

```asm
0x18000b0d0  push    rsi
0x18000b0d2  push    rdi
0x18000b0d3  push    r12
0x18000b0d5  push    r13
0x18000b0d7  push    r14
0x18000b0d9  push    r15
0x18000b0db  sub     rsp, 478h
0x18000b0e2  mov     rax, cs:__security_cookie
0x18000b0e9  xor     rax, rsp
0x18000b0ec  mov     [rsp+4A8h+var_48], rax
0x18000b0f4  mov     rax, rdx
0x18000b0f7  xor     r13d, r13d
0x18000b0fa  mov     [rsp+4A8h+hEnum], r13
0x18000b0ff  mov     [rsp+4A8h+nLength], 100h
0x18000b107  mov     [rsp+4A8h+BufferSize], 200h
0x18000b10f  mov     [rsp+4A8h+cCount], 0FFFFFFFFh
0x18000b117  lea     r9d, [r13+1]
0x18000b11b  lea     r8, aServerpath; "ServerPath"
0x18000b122  lea     rdx, [rsp+4A8h+var_460]
0x18000b127  mov     rcx, rax
0x18000b12a  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x18000b12f  mov     r12, [rax+8]
0x18000b133  call    ?GetImpersonatedUsername@@YAPEAGXZ; GetImpersonatedUsername(void)
0x18000b138  mov     rdi, rax
0x18000b13b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b13f  inc     r14
0x18000b142  cmp     [r12+r14*2], r13w
0x18000b147  jnz     short loc_18000B13F
0x18000b149  lea     rax, [rsp+4A8h+hEnum]
0x18000b14e  mov     [rsp+4A8h+lphEnum], rax; lphEnum
0x18000b153  xor     r9d, r9d; lpNetResource
0x18000b156  xor     r8d, r8d; dwUsage
0x18000b159  xor     edx, edx; dwType
0x18000b15b  lea     ecx, [rdx+1]; dwScope
0x18000b15e  call    cs:__imp_WNetOpenEnumW
0x18000b164  test    eax, eax
0x18000b166  jz      loc_18000B20F
0x18000b16c  mov     rcx, rdi; pv
0x18000b16f  call    cs:__imp_CoTaskMemFree
0x18000b175  jmp     loc_18000B259
0x18000b17a  mov     esi, r13d
0x18000b17d  cmp     [rsp+4A8h+cCount], r13d
0x18000b182  jbe     short loc_18000B1FF
0x18000b184  mov     eax, esi
0x18000b186  lea     r15, [rax+rax*2]
0x18000b18a  add     r15, r15
0x18000b18d  mov     r8, r14; MaxCount
0x18000b190  mov     rdx, [rsp+r15*8+4A8h+String2]; String2
0x18000b195  mov     rcx, r12; String1
0x18000b198  call    cs:__imp__wcsnicmp
0x18000b19e  test    eax, eax
0x18000b1a0  jnz     short loc_18000B1F7
0x18000b1a2  mov     rcx, [rsp+r15*8+4A8h+String2]; lpName
0x18000b1a7  cmp     word ptr [rcx+r14*2], 5Ch ; '\'
0x18000b1ad  jnz     short loc_18000B1F7
0x18000b1af  mov     [rsp+4A8h+nLength], 100h
0x18000b1b7  lea     r8, [rsp+4A8h+nLength]; lpnLength
0x18000b1bc  lea     rdx, [rsp+4A8h+UserName]; lpUserName
0x18000b1c4  call    cs:__imp_WNetGetUserW
0x18000b1ca  test    eax, eax
0x18000b1cc  jnz     short loc_18000B1F7
0x18000b1ce  lea     rdx, [rsp+4A8h+UserName]; String2
0x18000b1d6  mov     rcx, rdi; String1
0x18000b1d9  call    cs:__imp__wcsicmp
0x18000b1df  test    eax, eax
0x18000b1e1  jz      short loc_18000B1F7
0x18000b1e3  xor     r8d, r8d; fForce
0x18000b1e6  xor     edx, edx; dwFlags
0x18000b1e8  mov     rcx, [rsp+r15*8+4A8h+String2]; lpName
0x18000b1ed  call    cs:__imp_WNetCancelConnection2W
0x18000b1f3  test    eax, eax
0x18000b1f5  jnz     short loc_18000B249
0x18000b1f7  inc     esi
0x18000b1f9  cmp     esi, [rsp+4A8h+cCount]
0x18000b1fd  jb      short loc_18000B184
0x18000b1ff  mov     [rsp+4A8h+BufferSize], 200h
0x18000b207  mov     [rsp+4A8h+cCount], 0FFFFFFFFh
0x18000b20f  lea     r9, [rsp+4A8h+BufferSize]; lpBufferSize
0x18000b214  lea     r8, [rsp+4A8h+Buffer]; lpBuffer
0x18000b219  lea     rdx, [rsp+4A8h+cCount]; lpcCount
0x18000b21e  mov     rcx, [rsp+4A8h+hEnum]; hEnum
0x18000b223  call    cs:__imp_WNetEnumResourceW
0x18000b229  test    eax, eax
0x18000b22b  jz      loc_18000B17A
0x18000b231  mov     rcx, [rsp+4A8h+hEnum]; hEnum
0x18000b236  call    cs:__imp_WNetCloseEnum
0x18000b23c  mov     rcx, rdi; pv
0x18000b23f  call    cs:__imp_CoTaskMemFree
0x18000b245  xor     eax, eax
0x18000b247  jmp     short loc_18000B25E
0x18000b249  mov     rcx, [rsp+4A8h+hEnum]; hEnum
0x18000b24e  call    cs:__imp_WNetCloseEnum
0x18000b254  jmp     loc_18000B16C
0x18000b259  mov     eax, 1
0x18000b25e  mov     rcx, [rsp+4A8h+var_48]
0x18000b266  xor     rcx, rsp; StackCookie
0x18000b269  call    __security_check_cookie
0x18000b26e  add     rsp, 478h
0x18000b275  pop     r15
0x18000b277  pop     r14
0x18000b279  pop     r13
0x18000b27b  pop     r12
0x18000b27d  pop     rdi
0x18000b27e  pop     rsi
0x18000b27f  retn
```
