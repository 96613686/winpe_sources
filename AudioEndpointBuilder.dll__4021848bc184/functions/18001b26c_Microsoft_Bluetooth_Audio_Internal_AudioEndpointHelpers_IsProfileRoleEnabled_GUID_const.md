# Microsoft::Bluetooth::Audio::Internal::AudioEndpointHelpers::IsProfileRoleEnabled(_GUID const &)

- ea: `0x18001b26c`
- end: `0x18001b4fe`
- name: `?IsProfileRoleEnabled@AudioEndpointHelpers@Internal@Audio@Bluetooth@Microsoft@@CA_NAEBU_GUID@@@Z`
- size: `658`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001af7c`

## callees

- `0x18001b26c`
- `0x18001b504`
- `0x18001b5bc`
- `0x18001b5f8`
- `0x18003e920`
- `0x18003f780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b35c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b35c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b37b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b45a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b477`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b37b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b45a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b309`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b309`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::Audio::Internal::AudioEndpointHelpers::IsProfileRoleEnabled(
        const struct _GUID *a1)
{
  int v1; // eax
  __int64 v2; // r8
  const wchar_t *v3; // rdx
  const char *v4; // r9
  const WCHAR *v5; // rdx
  bool v6; // bl
  bool result; // al
  int pvData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-44h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-40h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v12; // [rsp+68h] [rbp-20h]
  unsigned __int64 v13; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Buf1 = (__int128)*a1;
  v1 = memcmp_0(&Buf1, &HandsfreeServiceClass_UUID, 0x10u);
  try
  {
    v2 = 16;
    if ( v1 )
    {
      if ( !memcmp_0(&Buf1, &HandsfreeAudioGatewayServiceClass_UUID, 0x10u) )
      {
        v2 = 13;
        v3 = L"HFP\\HandsFree";
      }
      else
      {
        if ( memcmp_0(&Buf1, &AudioSinkServiceClass_UUID, 0x10u) )
        {
          if ( !memcmp_0(&Buf1, &AudioSourceServiceClass_UUID, 0x10u) )
          {
            std::wstring::wstring(lpSubKey, L"A2dp\\Sink");
          }
          else
          {
            *(_OWORD *)lpSubKey = 0;
            v12 = 0;
            v13 = 0;
            std::wstring::_Construct<1,unsigned short const *>(lpSubKey, &LocaleName, 0);
          }
LABEL_5:
          if ( v12 )
          {
            *(_QWORD *)&Buf1 = 0;
            if ( RegOpenKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Control\\Bluetooth\\Audio",
                   0,
                   0x20019u,
                   (PHKEY)&Buf1) )
            {
              if ( (_QWORD)Buf1 )
                RegCloseKey((HKEY)Buf1);
              if ( v13 > 7 )
                std::_Deallocate<16>((void *)lpSubKey[0], 2 * v13 + 2);
              return 0;
            }
            else
            {
              pvData = 0;
              pcbData = 4;
              v5 = (const WCHAR *)lpSubKey;
              if ( v13 > 7 )
                v5 = lpSubKey[0];
              if ( RegGetValueW((HKEY)Buf1, v5, L"Enabled", 0x10u, 0, &pvData, &pcbData) )
              {
                if ( (_QWORD)Buf1 )
                  RegCloseKey((HKEY)Buf1);
                if ( v13 > 7 )
                  std::_Deallocate<16>((void *)lpSubKey[0], 2 * v13 + 2);
                return 0;
              }
              else
              {
                v6 = pvData != 0;
                if ( (_QWORD)Buf1 )
                  RegCloseKey((HKEY)Buf1);
                if ( v13 > 7 )
                  std::_Deallocate<16>((void *)lpSubKey[0], 2 * v13 + 2);
                return v6;
              }
            }
          }
          else
          {
            if ( v13 > 7 )
              std::_Deallocate<16>((void *)lpSubKey[0], 2 * v13 + 2);
            return 0;
          }
        }
        v2 = 11;
        v3 = L"A2DP\\Source";
      }
    }
    else
    {
      v3 = L"HFP\\AudioGateway";
    }
    *(_OWORD *)lpSubKey = 0;
    v12 = 0;
    v13 = 0;
    std::wstring::_Construct<1,unsigned short const *>(lpSubKey, v3, v2);
    goto LABEL_5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x301,
      (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\audioendpointhelpers\\audioendpointhelpers.cpp",
      v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001b26c  mov     [rsp+arg_0], rbx
0x18001b271  push    rdi
0x18001b272  sub     rsp, 80h
0x18001b279  mov     rax, cs:__security_cookie
0x18001b280  xor     rax, rsp
0x18001b283  mov     [rsp+88h+var_10], rax
0x18001b288  xor     edi, edi
0x18001b28a  movups  xmm0, xmmword ptr [rcx]
0x18001b28d  movdqu  [rsp+88h+Buf1], xmm0
0x18001b293  lea     ebx, [rdi+10h]
0x18001b296  mov     r8d, ebx; Size
0x18001b299  lea     rdx, HandsfreeServiceClass_UUID; Buf2
0x18001b2a0  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18001b2a5  call    memcmp_0
0x18001b2aa  mov     r8d, ebx; Size
0x18001b2ad  test    eax, eax
0x18001b2af  jnz     loc_18001B3B0
0x18001b2b5  lea     rdx, aHfpAudiogatewa; "HFP\\AudioGateway"
0x18001b2bc  xorps   xmm0, xmm0
0x18001b2bf  movups  xmmword ptr [rsp+88h+lpSubKey], xmm0
0x18001b2c4  mov     [rsp+88h+var_20], rdi
0x18001b2c9  mov     [rsp+88h+var_18], rdi
0x18001b2ce  lea     rcx, [rsp+88h+lpSubKey]
0x18001b2d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b2d8  cmp     [rsp+88h+var_20], rdi
0x18001b2dd  jz      loc_18001B48F
0x18001b2e3  mov     qword ptr [rsp+88h+Buf1], rdi
0x18001b2e8  lea     rax, [rsp+88h+Buf1]
0x18001b2ed  mov     [rsp+88h+phkResult], rax; phkResult
0x18001b2f2  mov     r9d, 20019h; samDesired
0x18001b2f8  xor     r8d, r8d; ulOptions
0x18001b2fb  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Blu"...
0x18001b302  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b309  call    cs:__imp_RegOpenKeyExW
0x18001b30f  mov     rcx, qword ptr [rsp+88h+Buf1]; hKey
0x18001b314  test    eax, eax
0x18001b316  jnz     loc_18001B472
0x18001b31c  mov     [rsp+88h+var_48], edi
0x18001b320  mov     [rsp+88h+var_44], 4
0x18001b328  lea     rdx, [rsp+88h+lpSubKey]
0x18001b32d  cmp     [rsp+88h+var_18], 7
0x18001b333  cmova   rdx, [rsp+88h+lpSubKey]; lpSubKey
0x18001b339  lea     rax, [rsp+88h+var_44]
0x18001b33e  mov     [rsp+88h+pcbData], rax; pcbData
0x18001b343  lea     rax, [rsp+88h+var_48]
0x18001b348  mov     [rsp+88h+pvData], rax; pvData
0x18001b34d  mov     [rsp+88h+phkResult], rdi; pdwType
0x18001b352  mov     r9d, ebx; dwFlags
0x18001b355  lea     r8, aEnabled; "Enabled"
0x18001b35c  call    cs:__imp_RegGetValueW
0x18001b362  mov     rcx, qword ptr [rsp+88h+Buf1]; hKey
0x18001b367  test    eax, eax
0x18001b369  jnz     loc_18001B455
0x18001b36f  cmp     [rsp+88h+var_48], edi
0x18001b373  setnz   bl
0x18001b376  test    rcx, rcx
0x18001b379  jz      short loc_18001B381
0x18001b37b  call    cs:__imp_RegCloseKey
0x18001b381  mov     rdx, [rsp+88h+var_18]
0x18001b386  cmp     rdx, 7
0x18001b38a  ja      loc_18001B4C9
0x18001b390  mov     al, bl
0x18001b392  mov     rcx, [rsp+88h+var_10]
0x18001b397  xor     rcx, rsp; StackCookie
0x18001b39a  call    __security_check_cookie
0x18001b39f  mov     rbx, [rsp+88h+arg_0]
0x18001b3a7  add     rsp, 80h
0x18001b3ae  pop     rdi
0x18001b3af  retn
0x18001b3b0  lea     rdx, HandsfreeAudioGatewayServiceClass_UUID; Buf2
0x18001b3b7  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18001b3bc  call    memcmp_0
0x18001b3c1  test    eax, eax
0x18001b3c3  jz      short loc_18001B40B
0x18001b3c5  mov     r8, rbx; Size
0x18001b3c8  lea     rdx, AudioSinkServiceClass_UUID; Buf2
0x18001b3cf  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18001b3d4  call    memcmp_0
0x18001b3d9  test    eax, eax
0x18001b3db  jz      short loc_18001B41D
0x18001b3dd  mov     r8, rbx; Size
0x18001b3e0  lea     rdx, AudioSourceServiceClass_UUID; Buf2
0x18001b3e7  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18001b3ec  call    memcmp_0
0x18001b3f1  lea     rcx, [rsp+88h+lpSubKey]
0x18001b3f6  test    eax, eax
0x18001b3f8  jnz     short loc_18001B42F
0x18001b3fa  lea     rdx, aA2dpSink; "A2dp\\Sink"
0x18001b401  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b406  jmp     loc_18001B2D8
0x18001b40b  mov     r8d, 0Dh
0x18001b411  lea     rdx, aHfpHandsfree; "HFP\\HandsFree"
0x18001b418  jmp     loc_18001B2BC
0x18001b41d  mov     r8d, 0Bh
0x18001b423  lea     rdx, aA2dpSource; "A2DP\\Source"
0x18001b42a  jmp     loc_18001B2BC
0x18001b42f  xorps   xmm0, xmm0
0x18001b432  movups  xmmword ptr [rsp+88h+lpSubKey], xmm0
0x18001b437  mov     [rsp+88h+var_20], rdi
0x18001b43c  mov     [rsp+88h+var_18], rdi
0x18001b441  xor     r8d, r8d
0x18001b444  lea     rdx, LocaleName
0x18001b44b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b450  jmp     loc_18001B2D8
0x18001b455  test    rcx, rcx
0x18001b458  jz      short loc_18001B460
0x18001b45a  call    cs:__imp_RegCloseKey
0x18001b460  mov     rdx, [rsp+88h+var_18]
0x18001b465  cmp     rdx, 7
0x18001b469  ja      short loc_18001B4E0
0x18001b46b  xor     al, al
0x18001b46d  jmp     loc_18001B392
0x18001b472  test    rcx, rcx
0x18001b475  jz      short loc_18001B47D
0x18001b477  call    cs:__imp_RegCloseKey
0x18001b47d  mov     rdx, [rsp+88h+var_18]
0x18001b482  cmp     rdx, 7
0x18001b486  ja      short loc_18001B4B5
0x18001b488  xor     al, al
0x18001b48a  jmp     loc_18001B392
0x18001b48f  mov     rdx, [rsp+88h+var_18]
0x18001b494  cmp     rdx, 7
0x18001b498  ja      short loc_18001B4A1
0x18001b49a  xor     al, al
0x18001b49c  jmp     loc_18001B392
0x18001b4a1  lea     rdx, ds:2[rdx*2]
0x18001b4a9  mov     rcx, [rsp+88h+lpSubKey]
0x18001b4ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b4b3  jmp     short loc_18001B49A
0x18001b4b5  lea     rdx, ds:2[rdx*2]
0x18001b4bd  mov     rcx, [rsp+88h+lpSubKey]
0x18001b4c2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b4c7  jmp     short loc_18001B488
0x18001b4c9  lea     rdx, ds:2[rdx*2]
0x18001b4d1  mov     rcx, [rsp+88h+lpSubKey]
0x18001b4d6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b4db  jmp     loc_18001B390
0x18001b4e0  lea     rdx, ds:2[rdx*2]
0x18001b4e8  mov     rcx, [rsp+88h+lpSubKey]
0x18001b4ed  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b4f2  jmp     loc_18001B46B
0x18001b4f7  xor     al, al
0x18001b4f9  jmp     loc_18001B392
```
