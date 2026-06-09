# WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier(ushort const *)

- ea: `0x180060b6c`
- end: `0x18006115d`
- name: `?ReadCpuInfoFromRegistryIdentifier@CPUHardwareIdParts@Device@WaaS2@@AEAAXPEBG@Z`
- size: `1521`
- prototype: `void __fastcall(WaaS2::Device::CPUHardwareIdParts *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x1800540a0`
- `0x1800608e0`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800086e0`
- `0x180008800`
- `0x1800098f0`
- `0x180009cd0`
- `0x180010db4`
- `0x18001d3ec`
- `0x180027dc8`
- `0x18002cbc4`
- `0x18002dba0`
- `0x18002e4b8`
- `0x18003e040`
- `0x1800497d4`
- `0x18005218c`
- `0x180055894`
- `0x180060b6c`
- `0x180061268`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060bc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060bc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061122`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier(
        wchar_t *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // r12
  unsigned __int64 v4; // rbx
  __m128i si128; // xmm6
  char *v6; // rsi
  wchar_t *v7; // rdi
  __int64 first_not_of_trivial_pos_2; // rax
  unsigned __int64 v9; // rdi
  wchar_t *v10; // rbx
  const wchar_t *v11; // rcx
  char IsNativeArchARM; // al
  const wchar_t *v13; // rdx
  wchar_t **v14; // rbx
  wchar_t *v15; // rdi
  __int64 v16; // rax
  int v17; // eax
  char *v18; // r14
  __int64 v19; // rsi
  wchar_t *v20; // rbx
  __int64 first_of_trivial_pos_2; // rax
  wchar_t *v22; // r15
  const wchar_t *v23; // rcx
  unsigned __int64 v24; // r8
  __int128 *v25; // rdx
  HKEY v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  int phkResult; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  HKEY hKey_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY v32; // [rsp+58h] [rbp-B0h]
  _QWORD v33[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v34[256]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v35; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int64 v36; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v37; // [rsp+1C0h] [rbp+B8h]
  __int128 v38; // [rsp+1C8h] [rbp+C0h] BYREF
  __m128i v39; // [rsp+1D8h] [rbp+D0h]
  _QWORD v40[4]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v41; // [rsp+208h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &hKey) )
  {
    WaaS2::Device::ReadRegString(hKey, L"VendorIdentifier", this + 16);
    *(_OWORD *)hKey_8 = 0;
    v32 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 7;
    LOWORD(v35) = 0;
    v3 = -1;
    if ( (unsigned __int8)WaaS2::Device::ReadRegString(hKey, L"Identifier", &v35) )
    {
      v4 = 0;
      if ( v36 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          v6 = (char *)&v35;
          if ( v37 > 7 )
            v6 = (char *)v35;
          if ( v4 >= v36 )
            break;
          v7 = (wchar_t *)&v6[2 * v4];
          if ( v36 - v4 + 4 < 0x10 )
          {
            v10 = (wchar_t *)&v6[2 * v36];
            memset_0(v34, 0, sizeof(v34));
            v11 = L" \t\r\n";
            while ( *v11 < 0x100u )
            {
              v34[*(unsigned __int8 *)v11++] = 1;
              if ( v11 == L"" )
              {
                while ( v7 < v10 )
                {
                  if ( *v7 >= 0x100u || !v34[*v7] )
                    goto LABEL_36;
                  ++v7;
                }
                goto LABEL_19;
              }
            }
            while ( v7 < v10 )
            {
              if ( !wmemchr(L" \t\r\n", *v7, 4u) )
              {
LABEL_36:
                v9 = ((char *)v7 - v6) >> 1;
                goto LABEL_37;
              }
              ++v7;
            }
            break;
          }
          first_not_of_trivial_pos_2 = _std_find_first_not_of_trivial_pos_2(&v6[2 * v4], v36 - v4, L" \t\r\n", 4);
          v9 = first_not_of_trivial_pos_2;
          if ( first_not_of_trivial_pos_2 != -1 )
            v9 = v4 + first_not_of_trivial_pos_2;
LABEL_37:
          if ( v9 == -1 )
            break;
          v18 = (char *)&v35;
          if ( v37 > 7 )
            v18 = (char *)v35;
          v19 = 2 * v9;
          if ( v9 < v36 )
          {
            v20 = (wchar_t *)&v18[v19];
            if ( v36 - v9 + 4 < 0x10 )
            {
              v22 = (wchar_t *)&v18[2 * v36];
              memset_0(v34, 0, sizeof(v34));
              v23 = L" \t\r\n";
              while ( *v23 < 0x100u )
              {
                v34[*(unsigned __int8 *)v23++] = 1;
                if ( v23 == L"" )
                {
                  while ( v20 < v22 )
                  {
                    if ( *v20 < 0x100u && v34[*v20] )
                      goto LABEL_57;
                    ++v20;
                  }
                  goto LABEL_59;
                }
              }
              while ( v20 < v22 )
              {
                if ( wmemchr(L" \t\r\n", *v20, 4u) )
                {
LABEL_57:
                  v4 = ((char *)v20 - v18) >> 1;
                  goto LABEL_58;
                }
                ++v20;
              }
            }
            else
            {
              first_of_trivial_pos_2 = _std_find_first_of_trivial_pos_2(&v18[v19], v36 - v9, L" \t\r\n", 4);
              v4 = first_of_trivial_pos_2;
              if ( first_of_trivial_pos_2 != -1 )
                v4 = v9 + first_of_trivial_pos_2;
LABEL_58:
              if ( v4 != -1 )
                goto LABEL_60;
            }
          }
LABEL_59:
          v4 = v36;
LABEL_60:
          v38 = 0;
          v39 = 0;
          if ( v36 < v9 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
          v24 = v36 - v9;
          if ( v36 - v9 >= v4 - v9 )
            v24 = v4 - v9;
          v25 = &v35;
          if ( v37 > 7 )
            v25 = (__int128 *)v35;
          std::wstring::_Construct<1,unsigned short const *>(&v38, (char *)v25 + v19, v24);
          v26 = hKey_8[1];
          if ( hKey_8[1] == v32 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(hKey_8, hKey_8[1], &v38);
          }
          else
          {
            *(_OWORD *)hKey_8[1] = v38;
            *((__m128i *)v26 + 1) = v39;
            v39 = si128;
            LOWORD(v38) = 0;
            hKey_8[1] += 8;
          }
          std::wstring::~wstring(&v38);
        }
        while ( v4 < v36 );
      }
    }
LABEL_19:
    IsNativeArchARM = WaaS2::Device::IsNativeArchARM();
    v13 = L"0x";
    if ( !IsNativeArchARM )
      v13 = word_180073298;
    v33[0] = L"Family";
    v33[1] = this + 112;
    v33[2] = L"Model";
    v33[3] = this + 160;
    v33[4] = L"Stepping";
    v33[5] = this + 32;
    v33[6] = L"Revision";
    v33[7] = this + 64;
    v38 = 0;
    v39 = 0;
    do
      ++v3;
    while ( v13[v3] );
    std::wstring::_Construct<1,unsigned short const *>(&v38, v13, v3);
    WaaS2::Device::ExtractLabeledNumericTokenValues_4_(hKey_8, &v38, v33);
    std::wstring::~wstring(&v38);
    v40[0] = this + 112;
    v40[1] = this + 160;
    v40[2] = this + 32;
    v40[3] = this + 64;
    v14 = (wchar_t **)v40;
    do
    {
      v15 = *v14;
      if ( *((_QWORD *)*v14 + 2) && (int)WaaS2::Device::ConvertToUInt32(v15) >= 0 )
      {
        v16 = WaaS2::Device::FormatUInt32AsHex(&v38, 0);
        std::wstring::operator=(v15, v16);
        std::wstring::~wstring(&v38);
      }
      ++v14;
    }
    while ( v14 != (wchar_t **)&v41 );
    if ( (unsigned __int8)WaaS2::Device::IsNativeArchARM() && *((_QWORD *)this + 18) )
    {
      v17 = WaaS2::Device::ConvertToUInt32(this + 64);
      if ( v17 >= 0 )
      {
        v27 = WaaS2::Device::FormatUInt32AsHex(&v38, 0);
        std::wstring::operator=(this + 32, v27);
        std::wstring::~wstring(&v38);
        v28 = WaaS2::Device::FormatUInt32AsHex(&v38, 0);
        std::wstring::operator=(this + 48, v28);
        std::wstring::~wstring(&v38);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x636,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v17,
          phkResult);
      }
    }
    std::wstring::~wstring(&v35);
    std::vector<std::wstring>::_Tidy(hKey_8);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180060b6c  mov     rax, rsp
0x180060b6f  mov     [rax+18h], rbx
0x180060b73  push    rbp
0x180060b74  push    rsi
0x180060b75  push    rdi
0x180060b76  push    r12
0x180060b78  push    r13
0x180060b7a  push    r14
0x180060b7c  push    r15
0x180060b7e  lea     rbp, [rax-158h]
0x180060b85  sub     rsp, 220h
0x180060b8c  movaps  xmmword ptr [rax-48h], xmm6
0x180060b90  mov     rax, cs:__security_cookie
0x180060b97  xor     rax, rsp
0x180060b9a  mov     [rbp+150h+var_50], rax
0x180060ba1  mov     r13, rcx
0x180060ba4  xor     r15d, r15d
0x180060ba7  mov     [rsp+250h+hKey], r15
0x180060bac  lea     rax, [rsp+250h+hKey]
0x180060bb1  mov     qword ptr [rsp+250h+phkResult], rax; phkResult
0x180060bb6  mov     r9d, 20119h; samDesired
0x180060bbc  xor     r8d, r8d; ulOptions
0x180060bbf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060bc6  call    cs:__imp_RegOpenKeyExW
0x180060bcc  test    eax, eax
0x180060bce  jnz     loc_180061118
0x180060bd4  lea     r8, [r13+20h]; void *
0x180060bd8  lea     rdx, aVendoridentifi; "VendorIdentifier"
0x180060bdf  mov     rcx, [rsp+250h+hKey]; hKey
0x180060be4  call    WaaS2__Device__ReadRegString
0x180060be9  xorps   xmm0, xmm0
0x180060bec  movdqu  xmmword ptr [rsp+250h+hKey+8], xmm0
0x180060bf2  mov     [rsp+250h+var_200], r15
0x180060bf7  movups  [rbp+150h+var_B0], xmm0
0x180060bfe  mov     [rbp+150h+var_A0], r15
0x180060c05  mov     [rbp+150h+var_98], 7
0x180060c10  mov     word ptr [rbp+150h+var_B0], r15w
0x180060c18  lea     r8, [rbp+150h+var_B0]; void *
0x180060c1f  lea     rdx, aIdentifier; "Identifier"
0x180060c26  mov     rcx, [rsp+250h+hKey]; hKey
0x180060c2b  call    WaaS2__Device__ReadRegString
0x180060c30  or      r12, 0FFFFFFFFFFFFFFFFh
0x180060c34  test    al, al
0x180060c36  jz      loc_180060D1C
0x180060c3c  mov     ebx, r15d
0x180060c3f  cmp     [rbp+150h+var_A0], r15
0x180060c46  jbe     loc_180060D1C
0x180060c4c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180060c54  mov     r14d, 100h
0x180060c5a  mov     rcx, [rbp+150h+var_A0]
0x180060c61  lea     rsi, [rbp+150h+var_B0]
0x180060c68  cmp     [rbp+150h+var_98], 7
0x180060c70  cmova   rsi, qword ptr [rbp+150h+var_B0]
0x180060c78  cmp     rbx, rcx
0x180060c7b  jnb     loc_180060D1C
0x180060c81  lea     rdi, [rsi+rbx*2]
0x180060c85  mov     rdx, rcx
0x180060c88  sub     rdx, rbx
0x180060c8b  lea     rax, [rdx+4]
0x180060c8f  cmp     rax, 10h
0x180060c93  jb      short loc_180060CBE
0x180060c95  mov     r9d, 4
0x180060c9b  lea     r8, asc_18008A058; " \t\r\n"
0x180060ca2  mov     rcx, rdi
0x180060ca5  call    __std_find_first_not_of_trivial_pos_2
0x180060caa  mov     rdi, rax
0x180060cad  cmp     rax, r12
0x180060cb0  jz      loc_180060EDB
0x180060cb6  add     rdi, rbx
0x180060cb9  jmp     loc_180060EDB
0x180060cbe  lea     rbx, [rsi+rcx*2]
0x180060cc2  mov     r8, r14; Size
0x180060cc5  xor     edx, edx; Val
0x180060cc7  lea     rcx, [rbp+150h+var_1B0]; void *
0x180060ccb  call    memset_0
0x180060cd0  lea     rcx, asc_18008A058; " \t\r\n"
0x180060cd7  cmp     [rcx], r14w
0x180060cdb  jnb     loc_180060ECB
0x180060ce1  movzx   eax, byte ptr [rcx]
0x180060ce4  mov     [rbp+rax+150h+var_1B0], 1
0x180060ce9  add     rcx, 2
0x180060ced  lea     rax, asc_18008A058+8; ""
0x180060cf4  cmp     rcx, rax
0x180060cf7  jnz     short loc_180060CD7
0x180060cf9  jmp     short loc_180060D17
0x180060cfb  cmp     [rdi], r14w
0x180060cff  jnb     loc_180060ED5
0x180060d05  movzx   eax, word ptr [rdi]
0x180060d08  cmp     [rbp+rax+150h+var_1B0], r15b
0x180060d0d  jz      loc_180060ED5
0x180060d13  add     rdi, 2
0x180060d17  cmp     rdi, rbx
0x180060d1a  jb      short loc_180060CFB
0x180060d1c  call    WaaS2__Device__IsNativeArchARM
0x180060d21  lea     rcx, word_180073298
0x180060d28  lea     rdx, a0x; "0x"
0x180060d2f  test    al, al
0x180060d31  cmovz   rdx, rcx
0x180060d35  lea     rbx, [r13+0E0h]
0x180060d3c  lea     rax, aFamily; "Family"
0x180060d43  mov     [rsp+250h+var_1F0], rax
0x180060d48  mov     [rsp+250h+var_1E8], rbx
0x180060d4d  lea     rdi, [r13+140h]
0x180060d54  lea     rax, aModel; "Model"
0x180060d5b  mov     [rsp+250h+var_1E0], rax
0x180060d60  mov     [rsp+250h+var_1D8], rdi
0x180060d65  lea     r14, [r13+40h]
0x180060d69  lea     rax, aStepping; "Stepping"
0x180060d70  mov     [rbp+150h+var_1D0], rax
0x180060d74  mov     [rbp+150h+var_1C8], r14
0x180060d78  lea     rsi, [r13+80h]
0x180060d7f  lea     rax, aRevision; "Revision"
0x180060d86  mov     [rbp+150h+var_1C0], rax
0x180060d8a  mov     [rbp+150h+var_1B8], rsi
0x180060d8e  xorps   xmm0, xmm0
0x180060d91  movups  [rbp+150h+var_90], xmm0
0x180060d98  xorps   xmm1, xmm1
0x180060d9b  movdqu  [rbp+150h+var_80], xmm1
0x180060da3  inc     r12
0x180060da6  cmp     [rdx+r12*2], r15w
0x180060dab  jnz     short loc_180060DA3
0x180060dad  mov     r8, r12
0x180060db0  lea     rcx, [rbp+150h+var_90]
0x180060db7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180060dbc  nop
0x180060dbd  lea     r8, [rsp+250h+var_1F0]
0x180060dc2  lea     rdx, [rbp+150h+var_90]
0x180060dc9  lea     rcx, [rsp+250h+hKey+8]
0x180060dce  call    WaaS2__Device__ExtractLabeledNumericTokenValues_4_
0x180060dd3  nop
0x180060dd4  lea     rcx, [rbp+150h+var_90]; void *
0x180060ddb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060de0  mov     [rbp+150h+var_70], rbx
0x180060de7  mov     [rbp+150h+var_68], rdi
0x180060dee  mov     [rbp+150h+var_60], r14
0x180060df5  mov     [rbp+150h+var_58], rsi
0x180060dfc  lea     rbx, [rbp+150h+var_70]
0x180060e03  mov     rdi, [rbx]
0x180060e06  mov     dword ptr [rsp+250h+var_220], r15d
0x180060e0b  cmp     [rdi+10h], r15
0x180060e0f  jz      short loc_180060E49
0x180060e11  lea     rdx, [rsp+250h+var_220]
0x180060e16  mov     rcx, rdi; String
0x180060e19  call    WaaS2__Device__ConvertToUInt32
0x180060e1e  test    eax, eax
0x180060e20  js      short loc_180060E49
0x180060e22  mov     edx, dword ptr [rsp+250h+var_220]
0x180060e26  lea     rcx, [rbp+150h+var_90]
0x180060e2d  call    WaaS2__Device__FormatUInt32AsHex
0x180060e32  mov     rdx, rax
0x180060e35  mov     rcx, rdi
0x180060e38  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060e3d  lea     rcx, [rbp+150h+var_90]; void *
0x180060e44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060e49  add     rbx, 8
0x180060e4d  lea     rax, [rbp+150h+var_50]
0x180060e54  cmp     rbx, rax
0x180060e57  jnz     short loc_180060E03
0x180060e59  call    WaaS2__Device__IsNativeArchARM
0x180060e5e  test    al, al
0x180060e60  jz      loc_180061100
0x180060e66  cmp     [r13+90h], r15
0x180060e6d  jz      loc_180061100
0x180060e73  mov     dword ptr [rsp+250h+var_220], r15d
0x180060e78  lea     rdx, [rsp+250h+var_220]
0x180060e7d  mov     rcx, rsi; String
0x180060e80  call    WaaS2__Device__ConvertToUInt32
0x180060e85  mov     rcx, [rbp+158h]; this
0x180060e8c  test    eax, eax
0x180060e8e  jns     loc_1800610A7
0x180060e94  mov     r9d, eax; char *
0x180060e97  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180060e9e  mov     edx, 636h; void *
0x180060ea3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060ea8  jmp     loc_180061100
0x180060ead  mov     r8d, 4; N
0x180060eb3  movzx   edx, word ptr [rdi]; C
0x180060eb6  lea     rcx, asc_18008A058; " \t\r\n"
0x180060ebd  call    wmemchr
0x180060ec2  test    rax, rax
0x180060ec5  jz      short loc_180060ED5
0x180060ec7  add     rdi, 2
0x180060ecb  cmp     rdi, rbx
0x180060ece  jb      short loc_180060EAD
0x180060ed0  jmp     loc_180060D1C
0x180060ed5  sub     rdi, rsi
0x180060ed8  sar     rdi, 1
0x180060edb  cmp     rdi, r12
0x180060ede  jz      loc_180060D1C
0x180060ee4  lea     r14, [rbp+150h+var_B0]
0x180060eeb  cmp     [rbp+150h+var_98], 7
0x180060ef3  cmova   r14, qword ptr [rbp+150h+var_B0]
0x180060efb  mov     rcx, [rbp+150h+var_A0]
0x180060f02  lea     rsi, [rdi+rdi]
0x180060f06  cmp     rdi, rcx
0x180060f09  jnb     loc_180060FD6
0x180060f0f  lea     rbx, [r14+rsi]
0x180060f13  mov     rdx, rcx
0x180060f16  sub     rdx, rdi
0x180060f19  lea     rax, [rdx+4]
0x180060f1d  cmp     rax, 10h
0x180060f21  jb      short loc_180060F4C
0x180060f23  mov     r9d, 4
0x180060f29  lea     r8, asc_18008A058; " \t\r\n"
0x180060f30  mov     rcx, rbx
0x180060f33  call    __std_find_first_of_trivial_pos_2
0x180060f38  mov     rbx, rax
0x180060f3b  cmp     rax, r12
0x180060f3e  jz      loc_180060FD1
0x180060f44  add     rbx, rdi
0x180060f47  jmp     loc_180060FD1
0x180060f4c  lea     r15, [r14+rcx*2]
0x180060f50  xor     edx, edx; Val
0x180060f52  mov     r8d, 100h; Size
0x180060f58  lea     rcx, [rbp+150h+var_1B0]; void *
0x180060f5c  call    memset_0
0x180060f61  lea     rcx, asc_18008A058; " \t\r\n"
0x180060f68  mov     edx, 100h
0x180060f6d  cmp     [rcx], dx
0x180060f70  jnb     short loc_180060FC4
0x180060f72  movzx   eax, byte ptr [rcx]
0x180060f75  mov     [rbp+rax+150h+var_1B0], 1
0x180060f7a  add     rcx, 2
0x180060f7e  lea     rax, asc_18008A058+8; ""
0x180060f85  cmp     rcx, rax
0x180060f88  jnz     short loc_180060F6D
0x180060f8a  jmp     short loc_180060F9F
0x180060f8c  cmp     [rbx], dx
0x180060f8f  jnb     short loc_180060F9B
0x180060f91  movzx   eax, word ptr [rbx]
0x180060f94  cmp     [rbp+rax+150h+var_1B0], 0
0x180060f99  jnz     short loc_180060FCB
0x180060f9b  add     rbx, 2
0x180060f9f  cmp     rbx, r15
0x180060fa2  jb      short loc_180060F8C
0x180060fa4  jmp     short loc_180060FD6
0x180060fa6  mov     r8d, 4; N
0x180060fac  movzx   edx, word ptr [rbx]; C
0x180060faf  lea     rcx, asc_18008A058; " \t\r\n"
0x180060fb6  call    wmemchr
0x180060fbb  test    rax, rax
0x180060fbe  jnz     short loc_180060FCB
0x180060fc0  add     rbx, 2
0x180060fc4  cmp     rbx, r15
0x180060fc7  jb      short loc_180060FA6
0x180060fc9  jmp     short loc_180060FD6
0x180060fcb  sub     rbx, r14
0x180060fce  sar     rbx, 1
0x180060fd1  cmp     rbx, r12
0x180060fd4  jnz     short loc_180060FDD
0x180060fd6  mov     rbx, [rbp+150h+var_A0]
0x180060fdd  xorps   xmm0, xmm0
0x180060fe0  movups  [rbp+150h+var_90], xmm0
0x180060fe7  xorps   xmm1, xmm1
0x180060fea  movdqu  [rbp+150h+var_80], xmm1
0x180060ff2  mov     r8, [rbp+150h+var_A0]
0x180060ff9  cmp     r8, rdi
0x180060ffc  jb      loc_180061157
0x180061002  mov     rax, rbx
0x180061005  sub     rax, rdi
0x180061008  sub     r8, rdi
0x18006100b  cmp     r8, rax
0x18006100e  cmovnb  r8, rax
0x180061012  lea     rdx, [rbp+150h+var_B0]
0x180061019  cmp     [rbp+150h+var_98], 7
0x180061021  cmova   rdx, qword ptr [rbp+150h+var_B0]
0x180061029  add     rdx, rsi
0x18006102c  lea     rcx, [rbp+150h+var_90]
0x180061033  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061038  nop
0x180061039  mov     rdx, [rsp+250h+var_208]
0x18006103e  cmp     rdx, [rsp+250h+var_200]
0x180061043  jz      short loc_180061075
0x180061045  movups  xmm0, [rbp+150h+var_90]
0x18006104c  movups  xmmword ptr [rdx], xmm0
0x18006104f  movups  xmm1, [rbp+150h+var_80]
0x180061056  movups  xmmword ptr [rdx+10h], xmm1
0x18006105a  movdqu  [rbp+150h+var_80], xmm6
0x180061062  xor     r15d, r15d
0x180061065  mov     word ptr [rbp+150h+var_90], r15w
0x18006106d  add     [rsp+250h+var_208], 20h ; ' '
0x180061073  jmp     short loc_180061089
0x180061075  lea     r8, [rbp+150h+var_90]
0x18006107c  lea     rcx, [rsp+250h+hKey+8]
0x180061081  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180061086  xor     r15d, r15d
0x180061089  lea     rcx, [rbp+150h+var_90]; void *
0x180061090  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061095  cmp     rbx, [rbp+150h+var_A0]
0x18006109c  jnb     loc_180060D1C
0x1800610a2  jmp     loc_180060C54
0x1800610a7  mov     ebx, dword ptr [rsp+250h+var_220]
0x1800610ab  mov     edx, ebx
0x1800610ad  shr     edx, 8
0x1800610b0  and     edx, 0Fh
0x1800610b3  lea     rcx, [rbp+150h+var_90]
0x1800610ba  call    WaaS2__Device__FormatUInt32AsHex
0x1800610bf  mov     rdx, rax
0x1800610c2  mov     rcx, r14
0x1800610c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
  ... truncated ...
```
