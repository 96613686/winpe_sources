# CLocationCapabilityCheck::HasLocationDeviceCapability(void *)

- ea: `0x18002a1f8`
- end: `0x18002a413`
- name: `?HasLocationDeviceCapability@CLocationCapabilityCheck@@SA_NPEAX@Z`
- size: `539`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a034`

## callees

- `0x18001e858`
- `0x18001efe0`
- `0x18001f334`
- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020c64`
- `0x18002a1f8`
- `0x18002a488`
- `0x18008f888`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a2db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a3bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a2db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a3bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a2e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a2e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a3cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3aa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a308`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a308`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a245`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a3f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a245`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a3f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a39d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a39d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a376`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a376`

## string_xrefs

- `0x18002a29a`: `Failed to get SID from string`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CLocationCapabilityCheck::HasLocationDeviceCapability(HANDLE TokenHandle)
{
  char v2; // r14
  int LastErrorFailHr; // ebx
  HANDLE v5; // rax
  unsigned int i; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  wil::details *v11; // rcx
  const unsigned __int16 *v12; // r8
  DWORD v13; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v15; // rdi
  char *v16; // [rsp+28h] [rbp-91h]
  const char *v17; // [rsp+38h] [rbp-81h]
  _OWORD v18[2]; // [rsp+40h] [rbp-79h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE pSid2[120]; // [rsp+78h] [rbp-41h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = 0;
  TokenInformationLength = 0;
  if ( TokenHandle )
  {
    if ( !GetTokenInformation(TokenHandle, TokenCapabilities, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v13 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v15 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v13);
      if ( v15 )
      {
        if ( GetTokenInformation(TokenHandle, TokenCapabilities, v15, TokenInformationLength, &TokenInformationLength) )
        {
          memset_0(v21, 0, 0x78u);
          ATL::CSid::CSid((ATL::CSid *)v21);
          memset(v18, 0, sizeof(v18));
          v7 = std::_WChar_traits<unsigned short>::length(L"S-1-15-3-3215430884-1339816292-89257616-1145831019");
          std::wstring::_Construct<1,unsigned short const *>(v18, v8, v7);
          hMem = 0;
          v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18, v9);
          if ( ConvertStringSidToSidW(v10, &hMem)
            && ATL::CSid::LoadAccount((ATL::CSid *)v21, (const struct _SID *)hMem, v12) )
          {
            LocalFree(hMem);
            LastErrorFailHr = 0;
          }
          else
          {
            LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
            LocalFree(hMem);
          }
          std::wstring::_Tidy_deallocate(v18);
          LODWORD(v16) = LastErrorFailHr;
          wil::details::in1diag5::Log_IfFailedMsg(
            retaddr,
            (void *)0x3B,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\LocationCapabilityCheck.h",
            "CLocationCapabilityCheck::HasLocationDeviceCapability",
            "hr",
            v16,
            (__int64)"Failed to get SID from string",
            v17);
          if ( LastErrorFailHr >= 0 )
          {
            for ( i = 0; i < *v15; ++i )
            {
              if ( EqualSid(*(PSID *)&v15[4 * i + 2], pSid2) )
              {
                v2 = 1;
                break;
              }
            }
          }
          ATL::CSid::~CSid((ATL::CSid *)v21);
        }
        v5 = GetProcessHeap();
        HeapFree(v5, 0, v15);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002a1f8  mov     [rsp-8+arg_8], rbx
0x18002a1fd  mov     [rsp-8+arg_10], rsi
0x18002a202  push    rbp
0x18002a203  push    rdi
0x18002a204  push    r14
0x18002a206  lea     rbp, [rsp-47h]
0x18002a20b  sub     rsp, 100h
0x18002a212  mov     rax, cs:__security_cookie
0x18002a219  xor     rax, rsp
0x18002a21c  mov     [rbp+57h+var_20], rax
0x18002a220  mov     rsi, rcx
0x18002a223  xor     r14b, r14b
0x18002a226  mov     [rbp+57h+TokenInformationLength], 0
0x18002a22d  test    rcx, rcx
0x18002a230  jz      short loc_18002A253
0x18002a232  lea     rax, [rbp+57h+TokenInformationLength]
0x18002a236  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18002a23b  xor     r9d, r9d; TokenInformationLength
0x18002a23e  xor     r8d, r8d; TokenInformation
0x18002a241  lea     edx, [r9+1Eh]; TokenInformationClass
0x18002a245  call    cs:__imp_GetTokenInformation
0x18002a24b  test    eax, eax
0x18002a24d  jz      loc_18002A3AA
0x18002a253  mov     al, r14b
0x18002a256  mov     rcx, [rbp+57h+var_20]
0x18002a25a  xor     rcx, rsp; StackCookie
0x18002a25d  call    __security_check_cookie
0x18002a262  lea     r11, [rsp+110h+var_10]
0x18002a26a  mov     rbx, [r11+28h]
0x18002a26e  mov     rsi, [r11+30h]
0x18002a272  mov     rsp, r11
0x18002a275  pop     r14
0x18002a277  pop     rdi
0x18002a278  pop     rbp
0x18002a279  retn
0x18002a27a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a27f  nop
0x18002a280  mov     ebx, eax
0x18002a282  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a286  call    cs:__imp_LocalFree
0x18002a28c  nop
0x18002a28d  lea     rcx, [rbp+57h+var_D0]
0x18002a291  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a296  mov     rcx, [rbp+5Fh]; this
0x18002a29a  lea     rax, aFailedToGetSid; "Failed to get SID from string"
0x18002a2a1  mov     [rsp+110h+var_E0], rax; __int64
0x18002a2a6  mov     dword ptr [rsp+110h+var_E8], ebx; char *
0x18002a2aa  lea     rax, aHr; "hr"
0x18002a2b1  mov     [rsp+110h+ReturnLength], rax; char *
0x18002a2b6  lea     r9, aClocationcapab; "CLocationCapabilityCheck::HasLocationDe"...
0x18002a2bd  lea     r8, aOnecoreuapDriv_99; "onecoreuap\\drivers\\mobilepc\\location"...
0x18002a2c4  mov     edx, 3Bh ; ';'; void *
0x18002a2c9  call    ?Log_IfFailedMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_IfFailedMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18002a2ce  test    ebx, ebx
0x18002a2d0  jns     short loc_18002A2F4
0x18002a2d2  lea     rcx, [rbp+57h+var_A0]; this
0x18002a2d6  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002a2db  call    cs:__imp_GetProcessHeap
0x18002a2e1  mov     rcx, rax; hHeap
0x18002a2e4  mov     r8, rdi; lpMem
0x18002a2e7  xor     edx, edx; dwFlags
0x18002a2e9  call    cs:__imp_HeapFree
0x18002a2ef  jmp     loc_18002A253
0x18002a2f4  xor     ebx, ebx
0x18002a2f6  cmp     ebx, [rdi]
0x18002a2f8  jnb     short loc_18002A2D2
0x18002a2fa  mov     ecx, ebx
0x18002a2fc  add     rcx, rcx
0x18002a2ff  lea     rdx, [rbp+57h+pSid2]; pSid2
0x18002a303  mov     rcx, [rdi+rcx*8+8]; pSid1
0x18002a308  call    cs:__imp_EqualSid
0x18002a30e  test    eax, eax
0x18002a310  jnz     loc_18002A40A
0x18002a316  inc     ebx
0x18002a318  jmp     short loc_18002A2F6
0x18002a31a  xor     edx, edx; Val
0x18002a31c  lea     r8d, [rdx+78h]; Size
0x18002a320  lea     rcx, [rbp+57h+var_A0]; void *
0x18002a324  call    memset_0
0x18002a329  lea     rcx, [rbp+57h+var_A0]; this
0x18002a32d  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002a332  nop
0x18002a333  xorps   xmm0, xmm0
0x18002a336  movups  [rbp+57h+var_D0], xmm0
0x18002a33a  xorps   xmm1, xmm1
0x18002a33d  movdqu  [rbp+57h+var_C0], xmm1
0x18002a342  lea     rcx, aS1153321543088; "S-1-15-3-3215430884-1339816292-89257616"...
0x18002a349  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002a34e  mov     r8, rax
0x18002a351  mov     rdx, rcx
0x18002a354  lea     rcx, [rbp+57h+var_D0]
0x18002a358  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a35d  nop
0x18002a35e  mov     [rbp+57h+hMem], 0
0x18002a366  lea     rcx, [rbp+57h+var_D0]
0x18002a36a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a36f  mov     rcx, rax; StringSid
0x18002a372  lea     rdx, [rbp+57h+hMem]; Sid
0x18002a376  call    cs:__imp_ConvertStringSidToSidW
0x18002a37c  test    eax, eax
0x18002a37e  jz      loc_18002A27A
0x18002a384  mov     rdx, [rbp+57h+hMem]; struct _SID *
0x18002a388  lea     rcx, [rbp+57h+var_A0]; this
0x18002a38c  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18002a391  test    al, al
0x18002a393  jz      loc_18002A27A
0x18002a399  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a39d  call    cs:__imp_LocalFree
0x18002a3a3  xor     ebx, ebx
0x18002a3a5  jmp     loc_18002A28D
0x18002a3aa  call    cs:__imp_GetLastError
0x18002a3b0  cmp     eax, 7Ah ; 'z'
0x18002a3b3  jnz     loc_18002A253
0x18002a3b9  mov     ebx, [rbp+57h+TokenInformationLength]
0x18002a3bc  call    cs:__imp_GetProcessHeap
0x18002a3c2  mov     r8d, ebx; dwBytes
0x18002a3c5  mov     edx, 8; dwFlags
0x18002a3ca  mov     rcx, rax; hHeap
0x18002a3cd  call    cs:__imp_HeapAlloc
0x18002a3d3  mov     rdi, rax
0x18002a3d6  test    rax, rax
0x18002a3d9  jz      loc_18002A253
0x18002a3df  lea     rax, [rbp+57h+TokenInformationLength]
0x18002a3e3  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18002a3e8  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002a3ec  mov     r8, rdi; TokenInformation
0x18002a3ef  mov     edx, 1Eh; TokenInformationClass
0x18002a3f4  mov     rcx, rsi; TokenHandle
0x18002a3f7  call    cs:__imp_GetTokenInformation
0x18002a3fd  test    eax, eax
0x18002a3ff  jz      loc_18002A2DB
0x18002a405  jmp     loc_18002A31A
0x18002a40a  mov     r14b, 1
0x18002a40d  jmp     loc_18002A2D2
```
