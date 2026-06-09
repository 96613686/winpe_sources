# GetSubCAOverrides

- ea: `0x180055c78`
- end: `0x180055ee3`
- name: `GetSubCAOverrides`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180057254`

## callees

- `0x18000dce4`
- `0x18000dd60`
- `0x180012264`
- `0x18004ac2c`
- `0x180055c78`
- `0x180058224`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055cf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055eb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055eb6`

## string_xrefs

- `0x180055ce3`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SubCAOverrides`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSubCAOverrides(_DWORD *a1, _QWORD *a2)
{
  LSTATUS v3; // edi
  __int64 v4; // rsi
  char IsEnabled; // al
  unsigned __int64 v6; // rcx
  _DWORD *v7; // rbx
  int *v8; // rdi
  __int64 v9; // rbp
  __int64 v10; // r15
  __int64 v11; // r14
  unsigned int *v12; // r13
  int *v13; // rdi
  __int64 v14; // r14
  char *v15; // r12
  __int64 v16; // r14
  char *v17; // r12
  _DWORD *v18; // rax
  HKEY hKey; // [rsp+48h] [rbp-50h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( !(unsigned int)__AreTestKeysAllowed(1) )
    return 2149847039LL;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SubCAOverrides",
         0,
         0x20019u,
         &hKey);
  if ( v3 >= 0 )
  {
    v4 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
    v6 = 28;
    if ( !IsEnabled )
      v6 = 10;
    v7 = SafeSusAllocArray(v6, 0x18u);
    if ( v7 )
    {
      v8 = dword_180092530;
      v9 = 2;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
      {
        v10 = 2;
        do
        {
          v11 = 5;
          do
          {
            v12 = &v7[6 * v4];
            if ( (int)RegQueryBinaryValue(hKey, *((LPCWSTR *)v8 + 1), (unsigned __int8 **)&v7[6 * v4 + 4], v12 + 2) >= 0
              && v12[2]
              && *(_QWORD *)&v7[6 * v4 + 4] )
            {
              v7[6 * v4] = *v8;
              v7[6 * v4 + 1] = v8[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v8 += 12;
            --v11;
          }
          while ( v11 );
          --v10;
        }
        while ( v10 );
        v13 = dword_1800921C0;
        do
        {
          v14 = 9;
          do
          {
            v15 = (char *)&v7[6 * v4];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v13 + 1),
                        (unsigned __int8 **)v15 + 2,
                        (unsigned int *)v15 + 2) >= 0
              && *((_DWORD *)v15 + 2)
              && *((_QWORD *)v15 + 2) )
            {
              v7[6 * v4] = *v13;
              v7[6 * v4 + 1] = v13[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v13 += 12;
            --v14;
          }
          while ( v14 );
          --v9;
        }
        while ( v9 );
      }
      else
      {
        do
        {
          v16 = 5;
          do
          {
            v17 = (char *)&v7[6 * v4];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v8 + 1),
                        (unsigned __int8 **)v17 + 2,
                        (unsigned int *)v17 + 2) >= 0
              && *((_DWORD *)v17 + 2)
              && *((_QWORD *)v17 + 2) )
            {
              v7[6 * v4] = *v8;
              v7[6 * v4 + 1] = v8[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v8 += 12;
            --v16;
          }
          while ( v16 );
          --v9;
        }
        while ( v9 );
      }
      if ( (_DWORD)v4 )
      {
        *a1 = v4;
        v18 = v7;
        v7 = 0;
        *a2 = v18;
        v3 = 0;
      }
      else
      {
        v3 = -2147024637;
      }
    }
    else
    {
      v3 = -2147024882;
    }
    if ( v7 )
      SusFree(v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180055c78  mov     [rsp+arg_10], rbx
0x180055c7d  push    rbp
0x180055c7e  push    rsi
0x180055c7f  push    rdi
0x180055c80  push    r12
0x180055c82  push    r13
0x180055c84  push    r14
0x180055c86  push    r15
0x180055c88  sub     rsp, 60h
0x180055c8c  mov     rax, cs:__security_cookie
0x180055c93  xor     rax, rsp
0x180055c96  mov     [rsp+98h+var_48], rax
0x180055c9b  mov     [rsp+98h+var_58], rdx
0x180055ca0  mov     [rsp+98h+var_60], rcx
0x180055ca5  mov     dword ptr [rcx], 0
0x180055cab  mov     qword ptr [rdx], 0
0x180055cb2  mov     cl, 1; bool
0x180055cb4  call    ?__AreTestKeysAllowed@@YAH_N@Z; __AreTestKeysAllowed(bool)
0x180055cb9  test    eax, eax
0x180055cbb  jnz     short loc_180055CC7
0x180055cbd  mov     eax, 80240FFFh
0x180055cc2  jmp     loc_180055EBE
0x180055cc7  mov     [rsp+98h+hKey], 0
0x180055cd0  lea     rax, [rsp+98h+hKey]
0x180055cd5  mov     [rsp+98h+phkResult], rax; phkResult
0x180055cda  mov     r9d, 20019h; samDesired
0x180055ce0  xor     r8d, r8d; ulOptions
0x180055ce3  lea     rdx, ?c_szSubCAOverridesTestKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180055cea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055cf1  call    cs:__imp_RegOpenKeyExW
0x180055cf7  mov     edi, eax
0x180055cf9  test    eax, eax
0x180055cfb  js      loc_180055EAC
0x180055d01  xor     esi, esi
0x180055d03  mov     [rsp+98h+var_68], rsi
0x180055d08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x180055d0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180055d14  lea     edx, [rsi+18h]; unsigned __int64
0x180055d17  test    al, al
0x180055d19  lea     ecx, [rsi+1Ch]
0x180055d1c  jnz     short loc_180055D21
0x180055d1e  lea     ecx, [rsi+0Ah]; unsigned __int64
0x180055d21  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180055d26  mov     [rsp+98h+var_68], rax
0x180055d2b  mov     rbx, rax
0x180055d2e  test    rax, rax
0x180055d31  jnz     short loc_180055D3D
0x180055d33  mov     edi, 8007000Eh
0x180055d38  jmp     loc_180055E9E
0x180055d3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x180055d44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180055d49  lea     rdi, dword_180092530
0x180055d50  mov     ebp, 2
0x180055d55  test    al, al
0x180055d57  jz      loc_180055E21
0x180055d5d  mov     r15d, ebp
0x180055d60  mov     r14d, 5
0x180055d66  lea     r12, [rsi+rsi*2]
0x180055d6a  lea     r13, [rbx+r12*8]
0x180055d6e  lea     r8, [r12+2]
0x180055d73  lea     r8, [rbx+r8*8]; unsigned __int8 **
0x180055d77  lea     r9, [r13+8]; unsigned int *
0x180055d7b  mov     rdx, [rdi+8]; lpValueName
0x180055d7f  mov     rcx, [rsp+98h+hKey]; hKey
0x180055d84  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x180055d89  test    eax, eax
0x180055d8b  js      short loc_180055DAC
0x180055d8d  cmp     dword ptr [r13+8], 0
0x180055d92  jbe     short loc_180055DAC
0x180055d94  cmp     qword ptr [rbx+r12*8+10h], 0
0x180055d9a  jz      short loc_180055DAC
0x180055d9c  mov     eax, [rdi]
0x180055d9e  mov     [rbx+r12*8], eax
0x180055da2  mov     eax, [rdi+4]
0x180055da5  mov     [rbx+r12*8+4], eax
0x180055daa  inc     esi
0x180055dac  add     rdi, 30h ; '0'
0x180055db0  sub     r14, 1
0x180055db4  jnz     short loc_180055D66
0x180055db6  sub     r15, 1
0x180055dba  jnz     short loc_180055D60
0x180055dbc  lea     rdi, dword_1800921C0
0x180055dc3  mov     r14d, 9
0x180055dc9  lea     r15, [rsi+rsi*2]
0x180055dcd  lea     r12, [rbx+r15*8]
0x180055dd1  lea     r13, [rbx+r15*8]
0x180055dd5  lea     r9, [r12+8]; unsigned int *
0x180055dda  lea     r8, [r13+10h]; unsigned __int8 **
0x180055dde  mov     rdx, [rdi+8]; lpValueName
0x180055de2  mov     rcx, [rsp+98h+hKey]; hKey
0x180055de7  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x180055dec  test    eax, eax
0x180055dee  js      short loc_180055E0F
0x180055df0  cmp     dword ptr [r12+8], 0
0x180055df6  jbe     short loc_180055E0F
0x180055df8  cmp     qword ptr [r13+10h], 0
0x180055dfd  jz      short loc_180055E0F
0x180055dff  mov     eax, [rdi]
0x180055e01  mov     [rbx+r15*8], eax
0x180055e05  mov     eax, [rdi+4]
0x180055e08  mov     [rbx+r15*8+4], eax
0x180055e0d  inc     esi
0x180055e0f  add     rdi, 30h ; '0'
0x180055e13  sub     r14, 1
0x180055e17  jnz     short loc_180055DC9
0x180055e19  sub     rbp, 1
0x180055e1d  jnz     short loc_180055DC3
0x180055e1f  jmp     short loc_180055E7D
0x180055e21  mov     r14d, 5
0x180055e27  lea     r15, [rsi+rsi*2]
0x180055e2b  lea     r12, [rbx+r15*8]
0x180055e2f  lea     r13, [rbx+r15*8]
0x180055e33  lea     r9, [r12+8]; unsigned int *
0x180055e38  lea     r8, [r13+10h]; unsigned __int8 **
0x180055e3c  mov     rdx, [rdi+8]; lpValueName
0x180055e40  mov     rcx, [rsp+98h+hKey]; hKey
0x180055e45  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x180055e4a  test    eax, eax
0x180055e4c  js      short loc_180055E6D
0x180055e4e  cmp     dword ptr [r12+8], 0
0x180055e54  jbe     short loc_180055E6D
0x180055e56  cmp     qword ptr [r13+10h], 0
0x180055e5b  jz      short loc_180055E6D
0x180055e5d  mov     eax, [rdi]
0x180055e5f  mov     [rbx+r15*8], eax
0x180055e63  mov     eax, [rdi+4]
0x180055e66  mov     [rbx+r15*8+4], eax
0x180055e6b  inc     esi
0x180055e6d  add     rdi, 30h ; '0'
0x180055e71  sub     r14, 1
0x180055e75  jnz     short loc_180055E27
0x180055e77  sub     rbp, 1
0x180055e7b  jnz     short loc_180055E21
0x180055e7d  test    esi, esi
0x180055e7f  jz      short loc_180055E99
0x180055e81  mov     rax, [rsp+98h+var_60]
0x180055e86  mov     [rax], esi
0x180055e88  mov     rax, rbx
0x180055e8b  xor     ebx, ebx
0x180055e8d  mov     rcx, [rsp+98h+var_58]
0x180055e92  mov     [rcx], rax
0x180055e95  xor     edi, edi
0x180055e97  jmp     short loc_180055E9E
0x180055e99  mov     edi, 80070103h
0x180055e9e  test    rbx, rbx
0x180055ea1  jz      short loc_180055EAC
0x180055ea3  mov     rcx, rbx; lpMem
0x180055ea6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180055eab  nop
0x180055eac  mov     rcx, [rsp+98h+hKey]; hKey
0x180055eb1  test    rcx, rcx
0x180055eb4  jz      short loc_180055EBC
0x180055eb6  call    cs:__imp_RegCloseKey
0x180055ebc  mov     eax, edi
0x180055ebe  mov     rcx, [rsp+98h+var_48]
0x180055ec3  xor     rcx, rsp; StackCookie
0x180055ec6  call    __security_check_cookie
0x180055ecb  mov     rbx, [rsp+98h+arg_10]
0x180055ed3  add     rsp, 60h
0x180055ed7  pop     r15
0x180055ed9  pop     r14
0x180055edb  pop     r13
0x180055edd  pop     r12
0x180055edf  pop     rdi
0x180055ee0  pop     rsi
0x180055ee1  pop     rbp
0x180055ee2  retn
```
