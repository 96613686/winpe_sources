# GetSubCAOverrides

- ea: `0x14002b118`
- end: `0x14002b383`
- name: `GetSubCAOverrides`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002cbd8`
- `0x14002cef0`

## callees

- `0x14000ce30`
- `0x14000ce9c`
- `0x14000d4a4`
- `0x140017e9c`
- `0x14002b118`
- `0x14002e080`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b356`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b356`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b191`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b191`

## string_xrefs

- `0x14002b183`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SubCAOverrides`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSubCAOverrides(_DWORD *a1, _QWORD *a2, __int64 a3, unsigned int *a4)
{
  LSTATUS v5; // edi
  __int64 v6; // rsi
  char IsEnabled; // al
  unsigned __int64 v8; // rcx
  _DWORD *v9; // rbx
  int *v10; // rdi
  __int64 v11; // rbp
  __int64 v12; // r15
  __int64 v13; // r14
  unsigned int *v14; // r13
  int *v15; // rdi
  __int64 v16; // r14
  char *v17; // r12
  __int64 v18; // r14
  char *v19; // r12
  _DWORD *v20; // rax
  HKEY hKey; // [rsp+48h] [rbp-50h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( !(unsigned int)__AreTestKeysAllowed(1, (__int64)a2, a3, a4) )
    return 2149847039LL;
  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SubCAOverrides",
         0,
         0x20019u,
         &hKey);
  if ( v5 >= 0 )
  {
    v6 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
    v8 = 28;
    if ( !IsEnabled )
      v8 = 10;
    v9 = SafeSusAllocArray(v8, 0x18u);
    if ( v9 )
    {
      v10 = dword_14006A610;
      v11 = 2;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
      {
        v12 = 2;
        do
        {
          v13 = 5;
          do
          {
            v14 = &v9[6 * v6];
            if ( (int)RegQueryBinaryValue(hKey, *((LPCWSTR *)v10 + 1), (unsigned __int8 **)&v9[6 * v6 + 4], v14 + 2) >= 0
              && v14[2]
              && *(_QWORD *)&v9[6 * v6 + 4] )
            {
              v9[6 * v6] = *v10;
              v9[6 * v6 + 1] = v10[1];
              v6 = (unsigned int)(v6 + 1);
            }
            v10 += 12;
            --v13;
          }
          while ( v13 );
          --v12;
        }
        while ( v12 );
        v15 = dword_14006A2A0;
        do
        {
          v16 = 9;
          do
          {
            v17 = (char *)&v9[6 * v6];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v15 + 1),
                        (unsigned __int8 **)v17 + 2,
                        (unsigned int *)v17 + 2) >= 0
              && *((_DWORD *)v17 + 2)
              && *((_QWORD *)v17 + 2) )
            {
              v9[6 * v6] = *v15;
              v9[6 * v6 + 1] = v15[1];
              v6 = (unsigned int)(v6 + 1);
            }
            v15 += 12;
            --v16;
          }
          while ( v16 );
          --v11;
        }
        while ( v11 );
      }
      else
      {
        do
        {
          v18 = 5;
          do
          {
            v19 = (char *)&v9[6 * v6];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v10 + 1),
                        (unsigned __int8 **)v19 + 2,
                        (unsigned int *)v19 + 2) >= 0
              && *((_DWORD *)v19 + 2)
              && *((_QWORD *)v19 + 2) )
            {
              v9[6 * v6] = *v10;
              v9[6 * v6 + 1] = v10[1];
              v6 = (unsigned int)(v6 + 1);
            }
            v10 += 12;
            --v18;
          }
          while ( v18 );
          --v11;
        }
        while ( v11 );
      }
      if ( (_DWORD)v6 )
      {
        *a1 = v6;
        v20 = v9;
        v9 = 0;
        *a2 = v20;
        v5 = 0;
      }
      else
      {
        v5 = -2147024637;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    if ( v9 )
      SusFree(v9);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002b118  mov     [rsp+arg_10], rbx
0x14002b11d  push    rbp
0x14002b11e  push    rsi
0x14002b11f  push    rdi
0x14002b120  push    r12
0x14002b122  push    r13
0x14002b124  push    r14
0x14002b126  push    r15
0x14002b128  sub     rsp, 60h
0x14002b12c  mov     rax, cs:__security_cookie
0x14002b133  xor     rax, rsp
0x14002b136  mov     [rsp+98h+var_48], rax
0x14002b13b  mov     [rsp+98h+var_58], rdx
0x14002b140  mov     [rsp+98h+var_60], rcx
0x14002b145  mov     dword ptr [rcx], 0
0x14002b14b  mov     qword ptr [rdx], 0
0x14002b152  mov     cl, 1; bool
0x14002b154  call    ?__AreTestKeysAllowed@@YAH_N@Z; __AreTestKeysAllowed(bool)
0x14002b159  test    eax, eax
0x14002b15b  jnz     short loc_14002B167
0x14002b15d  mov     eax, 80240FFFh
0x14002b162  jmp     loc_14002B35E
0x14002b167  mov     [rsp+98h+hKey], 0
0x14002b170  lea     rax, [rsp+98h+hKey]
0x14002b175  mov     [rsp+98h+phkResult], rax; phkResult
0x14002b17a  mov     r9d, 20019h; samDesired
0x14002b180  xor     r8d, r8d; ulOptions
0x14002b183  lea     rdx, ?c_szSubCAOverridesTestKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002b18a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002b191  call    cs:__imp_RegOpenKeyExW
0x14002b197  mov     edi, eax
0x14002b199  test    eax, eax
0x14002b19b  js      loc_14002B34C
0x14002b1a1  xor     esi, esi
0x14002b1a3  mov     [rsp+98h+var_68], rsi
0x14002b1a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x14002b1af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x14002b1b4  lea     edx, [rsi+18h]; unsigned __int64
0x14002b1b7  test    al, al
0x14002b1b9  lea     ecx, [rsi+1Ch]
0x14002b1bc  jnz     short loc_14002B1C1
0x14002b1be  lea     ecx, [rsi+0Ah]; unsigned __int64
0x14002b1c1  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14002b1c6  mov     [rsp+98h+var_68], rax
0x14002b1cb  mov     rbx, rax
0x14002b1ce  test    rax, rax
0x14002b1d1  jnz     short loc_14002B1DD
0x14002b1d3  mov     edi, 8007000Eh
0x14002b1d8  jmp     loc_14002B33E
0x14002b1dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x14002b1e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x14002b1e9  lea     rdi, dword_14006A610
0x14002b1f0  mov     ebp, 2
0x14002b1f5  test    al, al
0x14002b1f7  jz      loc_14002B2C1
0x14002b1fd  mov     r15d, ebp
0x14002b200  mov     r14d, 5
0x14002b206  lea     r12, [rsi+rsi*2]
0x14002b20a  lea     r13, [rbx+r12*8]
0x14002b20e  lea     r8, [r12+2]
0x14002b213  lea     r8, [rbx+r8*8]; unsigned __int8 **
0x14002b217  lea     r9, [r13+8]; unsigned int *
0x14002b21b  mov     rdx, [rdi+8]; lpValueName
0x14002b21f  mov     rcx, [rsp+98h+hKey]; hKey
0x14002b224  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x14002b229  test    eax, eax
0x14002b22b  js      short loc_14002B24C
0x14002b22d  cmp     dword ptr [r13+8], 0
0x14002b232  jbe     short loc_14002B24C
0x14002b234  cmp     qword ptr [rbx+r12*8+10h], 0
0x14002b23a  jz      short loc_14002B24C
0x14002b23c  mov     eax, [rdi]
0x14002b23e  mov     [rbx+r12*8], eax
0x14002b242  mov     eax, [rdi+4]
0x14002b245  mov     [rbx+r12*8+4], eax
0x14002b24a  inc     esi
0x14002b24c  add     rdi, 30h ; '0'
0x14002b250  sub     r14, 1
0x14002b254  jnz     short loc_14002B206
0x14002b256  sub     r15, 1
0x14002b25a  jnz     short loc_14002B200
0x14002b25c  lea     rdi, dword_14006A2A0
0x14002b263  mov     r14d, 9
0x14002b269  lea     r15, [rsi+rsi*2]
0x14002b26d  lea     r12, [rbx+r15*8]
0x14002b271  lea     r13, [rbx+r15*8]
0x14002b275  lea     r9, [r12+8]; unsigned int *
0x14002b27a  lea     r8, [r13+10h]; unsigned __int8 **
0x14002b27e  mov     rdx, [rdi+8]; lpValueName
0x14002b282  mov     rcx, [rsp+98h+hKey]; hKey
0x14002b287  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x14002b28c  test    eax, eax
0x14002b28e  js      short loc_14002B2AF
0x14002b290  cmp     dword ptr [r12+8], 0
0x14002b296  jbe     short loc_14002B2AF
0x14002b298  cmp     qword ptr [r13+10h], 0
0x14002b29d  jz      short loc_14002B2AF
0x14002b29f  mov     eax, [rdi]
0x14002b2a1  mov     [rbx+r15*8], eax
0x14002b2a5  mov     eax, [rdi+4]
0x14002b2a8  mov     [rbx+r15*8+4], eax
0x14002b2ad  inc     esi
0x14002b2af  add     rdi, 30h ; '0'
0x14002b2b3  sub     r14, 1
0x14002b2b7  jnz     short loc_14002B269
0x14002b2b9  sub     rbp, 1
0x14002b2bd  jnz     short loc_14002B263
0x14002b2bf  jmp     short loc_14002B31D
0x14002b2c1  mov     r14d, 5
0x14002b2c7  lea     r15, [rsi+rsi*2]
0x14002b2cb  lea     r12, [rbx+r15*8]
0x14002b2cf  lea     r13, [rbx+r15*8]
0x14002b2d3  lea     r9, [r12+8]; unsigned int *
0x14002b2d8  lea     r8, [r13+10h]; unsigned __int8 **
0x14002b2dc  mov     rdx, [rdi+8]; lpValueName
0x14002b2e0  mov     rcx, [rsp+98h+hKey]; hKey
0x14002b2e5  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x14002b2ea  test    eax, eax
0x14002b2ec  js      short loc_14002B30D
0x14002b2ee  cmp     dword ptr [r12+8], 0
0x14002b2f4  jbe     short loc_14002B30D
0x14002b2f6  cmp     qword ptr [r13+10h], 0
0x14002b2fb  jz      short loc_14002B30D
0x14002b2fd  mov     eax, [rdi]
0x14002b2ff  mov     [rbx+r15*8], eax
0x14002b303  mov     eax, [rdi+4]
0x14002b306  mov     [rbx+r15*8+4], eax
0x14002b30b  inc     esi
0x14002b30d  add     rdi, 30h ; '0'
0x14002b311  sub     r14, 1
0x14002b315  jnz     short loc_14002B2C7
0x14002b317  sub     rbp, 1
0x14002b31b  jnz     short loc_14002B2C1
0x14002b31d  test    esi, esi
0x14002b31f  jz      short loc_14002B339
0x14002b321  mov     rax, [rsp+98h+var_60]
0x14002b326  mov     [rax], esi
0x14002b328  mov     rax, rbx
0x14002b32b  xor     ebx, ebx
0x14002b32d  mov     rcx, [rsp+98h+var_58]
0x14002b332  mov     [rcx], rax
0x14002b335  xor     edi, edi
0x14002b337  jmp     short loc_14002B33E
0x14002b339  mov     edi, 80070103h
0x14002b33e  test    rbx, rbx
0x14002b341  jz      short loc_14002B34C
0x14002b343  mov     rcx, rbx; lpMem
0x14002b346  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002b34b  nop
0x14002b34c  mov     rcx, [rsp+98h+hKey]; hKey
0x14002b351  test    rcx, rcx
0x14002b354  jz      short loc_14002B35C
0x14002b356  call    cs:__imp_RegCloseKey
0x14002b35c  mov     eax, edi
0x14002b35e  mov     rcx, [rsp+98h+var_48]
0x14002b363  xor     rcx, rsp; StackCookie
0x14002b366  call    __security_check_cookie
0x14002b36b  mov     rbx, [rsp+98h+arg_10]
0x14002b373  add     rsp, 60h
0x14002b377  pop     r15
0x14002b379  pop     r14
0x14002b37b  pop     r13
0x14002b37d  pop     r12
0x14002b37f  pop     rdi
0x14002b380  pop     rsi
0x14002b381  pop     rbp
0x14002b382  retn
```
