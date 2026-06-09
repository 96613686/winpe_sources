# CsxManager::Initialize(void)

- ea: `0x18000ae98`
- end: `0x18000b115`
- name: `?Initialize@CsxManager@@QEAAKXZ`
- size: `637`
- prototype: `__int64 __fastcall(CsxManager *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000aa40`

## callees

- `0x1800016c0`
- `0x180001b6c`
- `0x180002188`
- `0x180009508`
- `0x180009a08`
- `0x180009bf8`
- `0x18000ae98`
- `0x1800114a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000af3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000af3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aee9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000afdd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000afdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0e7`

## string_xrefs

- `0x18000aedb`: `System\CurrentControlSet\Services\XboxGipSvc\CoExAdapters`

## pseudocode

```c
__int64 __fastcall CsxManager::Initialize(CsxManager *this)
{
  unsigned int v1; // edi
  unsigned __int64 v2; // rax
  const struct std::nothrow_t *v3; // rdx
  WCHAR *v4; // r15
  DWORD v5; // r14d
  __m128i si128; // xmm6
  LSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rbx
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-49h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-45h] BYREF
  DWORD Type; // [rsp+70h] [rbp-41h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-3Dh] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-31h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-29h] BYREF
  _OWORD v21[2]; // [rsp+90h] [rbp-21h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-1h]

  hKey = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\XboxGipSvc\\CoExAdapters",
         0,
         0x20019u,
         &hKey);
  if ( !v1 )
  {
    cbMaxValueNameLen = 0;
    cValues = 0;
    v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v1 )
    {
      v2 = 2LL * (cbMaxValueNameLen + 1);
      if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
        v2 = -1;
      v4 = (WCHAR *)operator new[](v2, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        v1 = 0;
        v5 = 0;
        if ( cValues )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          do
          {
            cchValueName = cbMaxValueNameLen + 1;
            Type = 0;
            *(_DWORD *)Data = 0;
            cbData = 4;
            v7 = RegEnumValueW(hKey, v5, v4, &cchValueName, 0, &Type, Data, &cbData);
            if ( v7 || Type != 4 )
            {
              if ( !v1 )
              {
                v1 = -536870391;
                if ( v7 )
                  v1 = v7;
              }
            }
            else
            {
              v22 = 0;
              v21[0] = 0;
              v21[1] = si128;
              LOWORD(v21[0]) = 0;
              v8 = qword_18001A2C8;
              if ( qword_18001A2C8 == qword_18001A2D0 )
              {
                std::vector<CsxManager::KnownWiFiAdapter>::_Emplace_reallocate<CsxManager::KnownWiFiAdapter>(
                  &S1,
                  qword_18001A2C8,
                  v21);
              }
              else
              {
                *(_WORD *)qword_18001A2C8 = 0;
                *(_QWORD *)(v8 + 2) = *(_QWORD *)((char *)v21 + 2);
                *(_DWORD *)(v8 + 10) = *(_DWORD *)((char *)v21 + 10);
                *(_WORD *)(v8 + 14) = HIWORD(v21[0]);
                *(_QWORD *)(v8 + 16) = 0;
                *(_QWORD *)(v8 + 24) = 7;
                *(_DWORD *)(v8 + 32) = 0;
                qword_18001A2C8 += 40;
              }
              std::wstring::~wstring((char **)v21);
              v10 = (_QWORD *)(qword_18001A2C8 - 40);
              v11 = cchValueName;
              if ( (unsigned __int64)cchValueName > *(_QWORD *)(qword_18001A2C8 - 16) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  qword_18001A2C8 - 40,
                  cchValueName,
                  v9,
                  v4);
              }
              else
              {
                if ( *(_QWORD *)(qword_18001A2C8 - 16) > 7u )
                  v10 = (_QWORD *)*v10;
                *(_QWORD *)(qword_18001A2C8 - 24) = cchValueName;
                v12 = 2 * v11;
                memmove_0(v10, v4, 2 * v11);
                *(_WORD *)((char *)v10 + v12) = 0;
              }
              *(_DWORD *)(qword_18001A2C8 - 8) = *(_DWORD *)Data;
            }
            ++v5;
          }
          while ( v5 < cValues );
        }
        operator delete(v4, v3);
      }
      else
      {
        v1 = 14;
      }
    }
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18000ae98  mov     rax, rsp
0x18000ae9b  push    rbp
0x18000ae9c  push    rbx
0x18000ae9d  push    rsi
0x18000ae9e  push    rdi
0x18000ae9f  push    r12
0x18000aea1  push    r14
0x18000aea3  push    r15
0x18000aea5  lea     rbp, [rax-5Fh]
0x18000aea9  sub     rsp, 0D0h
0x18000aeb0  movaps  xmmword ptr [rax-48h], xmm6
0x18000aeb4  mov     rax, cs:__security_cookie
0x18000aebb  xor     rax, rsp
0x18000aebe  mov     [rbp+57h+var_50], rax
0x18000aec2  xor     r12d, r12d
0x18000aec5  mov     [rbp+57h+hKey], r12
0x18000aec9  lea     rax, [rbp+57h+hKey]
0x18000aecd  mov     [rsp+100h+phkResult], rax; phkResult
0x18000aed2  mov     r9d, 20019h; samDesired
0x18000aed8  xor     r8d, r8d; ulOptions
0x18000aedb  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Xb"...
0x18000aee2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aee9  call    cs:__imp_RegOpenKeyExW
0x18000aeef  mov     edi, eax
0x18000aef1  test    eax, eax
0x18000aef3  jnz     loc_18000B0ED
0x18000aef9  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x18000aefd  mov     [rbp+57h+cValues], r12d
0x18000af01  mov     [rsp+58h], r12; lpftLastWriteTime
0x18000af06  mov     [rsp+100h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000af0b  mov     [rsp+100h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000af10  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000af14  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000af19  lea     rax, [rbp+57h+cValues]
0x18000af1d  mov     [rsp+100h+lpcValues], rax; lpcValues
0x18000af22  mov     [rsp+100h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000af27  mov     [rsp+100h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000af2c  mov     [rsp+100h+phkResult], r12; lpcSubKeys
0x18000af31  xor     r9d, r9d; lpReserved
0x18000af34  xor     r8d, r8d; lpcchClass
0x18000af37  xor     edx, edx; lpClass
0x18000af39  mov     rcx, [rbp+57h+hKey]; hKey
0x18000af3d  call    cs:__imp_RegQueryInfoKeyW
0x18000af43  mov     edi, eax
0x18000af45  test    eax, eax
0x18000af47  jnz     loc_18000B0E3
0x18000af4d  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000af50  inc     ecx
0x18000af52  lea     eax, [rdi+2]
0x18000af55  mul     rcx
0x18000af58  lea     rcx, [r12-1]
0x18000af5d  cmovb   rax, rcx
0x18000af61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000af68  mov     rcx, rax; unsigned __int64
0x18000af6b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000af70  mov     r15, rax
0x18000af73  test    rax, rax
0x18000af76  jnz     short loc_18000AF80
0x18000af78  lea     edi, [rax+0Eh]
0x18000af7b  jmp     loc_18000B0E3
0x18000af80  mov     edi, r12d
0x18000af83  mov     r14d, r12d
0x18000af86  cmp     [rbp+57h+cValues], r12d
0x18000af8a  jbe     loc_18000B0DB
0x18000af90  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000af98  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18000af9b  inc     eax
0x18000af9d  mov     [rbp+57h+cchValueName], eax
0x18000afa0  mov     [rbp+57h+Type], r12d
0x18000afa4  mov     dword ptr [rbp+57h+Data], r12d
0x18000afa8  mov     [rbp+57h+cbData], 4
0x18000afaf  lea     rax, [rbp+57h+cbData]
0x18000afb3  mov     [rsp+100h+lpcValues], rax; lpcbData
0x18000afb8  lea     rax, [rbp+57h+Data]
0x18000afbc  mov     [rsp+100h+lpcbMaxClassLen], rax; lpData
0x18000afc1  lea     rax, [rbp+57h+Type]
0x18000afc5  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpType
0x18000afca  mov     [rsp+100h+phkResult], r12; lpReserved
0x18000afcf  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18000afd3  mov     r8, r15; lpValueName
0x18000afd6  mov     edx, r14d; dwIndex
0x18000afd9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000afdd  call    cs:__imp_RegEnumValueW
0x18000afe3  test    eax, eax
0x18000afe5  jnz     loc_18000B0C0
0x18000afeb  cmp     [rbp+57h+Type], 4
0x18000afef  jnz     loc_18000B0C0
0x18000aff5  mov     rcx, r12
0x18000aff8  mov     [rbp+57h+var_58], rcx
0x18000affc  xorps   xmm0, xmm0
0x18000afff  movups  [rbp+57h+var_78], xmm0
0x18000b003  movdqu  [rbp+57h+var_68], xmm6
0x18000b008  mov     word ptr [rbp+57h+var_78], r12w
0x18000b00d  mov     rdx, cs:qword_18001A2C8
0x18000b014  cmp     rdx, cs:qword_18001A2D0
0x18000b01b  jz      short loc_18000B052
0x18000b01d  mov     [rdx], r12w
0x18000b021  movsd   xmm0, qword ptr [rbp+57h+var_78+2]
0x18000b026  movsd   qword ptr [rdx+2], xmm0
0x18000b02b  mov     eax, dword ptr [rbp+57h+var_78+0Ah]
0x18000b02e  mov     [rdx+0Ah], eax
0x18000b031  movzx   eax, word ptr [rbp+57h+var_78+0Eh]
0x18000b035  mov     [rdx+0Eh], ax
0x18000b039  mov     [rdx+10h], r12
0x18000b03d  mov     qword ptr [rdx+18h], 7
0x18000b045  mov     [rdx+20h], ecx
0x18000b048  add     cs:qword_18001A2C8, 28h ; '('
0x18000b050  jmp     short loc_18000B062
0x18000b052  lea     r8, [rbp+57h+var_78]
0x18000b056  lea     rcx, S1
0x18000b05d  call    ??$_Emplace_reallocate@UKnownWiFiAdapter@CsxManager@@@?$vector@UKnownWiFiAdapter@CsxManager@@V?$allocator@UKnownWiFiAdapter@CsxManager@@@std@@@std@@AEAAPEAUKnownWiFiAdapter@CsxManager@@QEAU23@$$QEAU23@@Z; std::vector<CsxManager::KnownWiFiAdapter>::_Emplace_reallocate<CsxManager::KnownWiFiAdapter>(CsxManager::KnownWiFiAdapter * const,CsxManager::KnownWiFiAdapter &&)
0x18000b062  lea     rcx, [rbp+57h+var_78]
0x18000b066  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b06b  mov     rax, cs:qword_18001A2C8
0x18000b072  lea     rsi, [rax-28h]
0x18000b076  mov     edx, [rbp+57h+cchValueName]
0x18000b079  cmp     rdx, [rax-10h]
0x18000b07d  ja      short loc_18000B0A6
0x18000b07f  cmp     qword ptr [rax-10h], 7
0x18000b084  jbe     short loc_18000B089
0x18000b086  mov     rsi, [rsi]
0x18000b089  mov     [rax-18h], rdx
0x18000b08d  lea     rbx, [rdx+rdx]
0x18000b091  mov     r8, rbx; Size
0x18000b094  mov     rdx, r15; Src
0x18000b097  mov     rcx, rsi; void *
0x18000b09a  call    memmove_0
0x18000b09f  mov     [rbx+rsi], r12w
0x18000b0a4  jmp     short loc_18000B0B1
0x18000b0a6  mov     r9, r15
0x18000b0a9  mov     rcx, rsi
0x18000b0ac  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000b0b1  mov     ecx, dword ptr [rbp+57h+Data]
0x18000b0b4  mov     rax, cs:qword_18001A2C8
0x18000b0bb  mov     [rax-8], ecx
0x18000b0be  jmp     short loc_18000B0CE
0x18000b0c0  test    edi, edi
0x18000b0c2  jnz     short loc_18000B0CE
0x18000b0c4  mov     edi, 0E0000209h
0x18000b0c9  test    eax, eax
0x18000b0cb  cmovnz  edi, eax
0x18000b0ce  inc     r14d
0x18000b0d1  cmp     r14d, [rbp+57h+cValues]
0x18000b0d5  jb      loc_18000AF98
0x18000b0db  mov     rcx, r15; void *
0x18000b0de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b0e3  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b0e7  call    cs:__imp_RegCloseKey
0x18000b0ed  mov     eax, edi
0x18000b0ef  mov     rcx, [rbp+57h+var_50]
0x18000b0f3  xor     rcx, rsp; StackCookie
0x18000b0f6  call    __security_check_cookie
0x18000b0fb  movaps  xmm6, [rsp+100h+var_48+8]
0x18000b103  add     rsp, 0D0h
0x18000b10a  pop     r15
0x18000b10c  pop     r14
0x18000b10e  pop     r12
0x18000b110  pop     rdi
0x18000b111  pop     rsi
0x18000b112  pop     rbx
0x18000b113  pop     rbp
0x18000b114  retn
```
