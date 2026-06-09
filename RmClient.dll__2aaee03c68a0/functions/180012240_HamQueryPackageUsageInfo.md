# HamQueryPackageUsageInfo

- ea: `0x180012240`
- end: `0x180012658`
- name: `HamQueryPackageUsageInfo`
- size: `1048`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000d260`
- `0x18000d4b0`
- `0x180012240`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800124cf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800124cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800122c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800122c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012340`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012591`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012340`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012591`

## pseudocode

```c
__int64 __fastcall HamQueryPackageUsageInfo(const unsigned __int16 *a1, void *a2, __int64 a3)
{
  _QWORD *v4; // r14
  int v5; // eax
  HKEY v6; // rdi
  int v7; // ebx
  LSTATUS v8; // eax
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rbx
  __int64 v15; // rax
  bool v16; // zf
  int *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  bool v20; // cc
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  bool v23; // cc
  int v24; // eax
  DWORD cchName[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+58h] [rbp-B0h]
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-A0h]
  __int64 v31; // [rsp+70h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v33; // [rsp+80h] [rbp-88h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-80h] BYREF
  __m128i v35; // [rsp+98h] [rbp-70h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-60h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B8h] [rbp-50h] BYREF
  char *v38; // [rsp+C8h] [rbp-40h]
  int v39; // [rsp+D0h] [rbp-38h]
  int v40; // [rsp+D4h] [rbp-34h]
  int *v41; // [rsp+D8h] [rbp-30h]
  int v42; // [rsp+E0h] [rbp-28h]
  int v43; // [rsp+E4h] [rbp-24h]
  WCHAR *v44; // [rsp+E8h] [rbp-20h]
  int v45; // [rsp+F0h] [rbp-18h]
  int v46; // [rsp+F4h] [rbp-14h]
  __int64 *v47; // [rsp+F8h] [rbp-10h]
  __int64 v48; // [rsp+100h] [rbp-8h]
  __int64 *v49; // [rsp+108h] [rbp+0h]
  __int64 v50; // [rsp+110h] [rbp+8h]
  WCHAR Name[72]; // [rsp+118h] [rbp+10h] BYREF

  v33 = (_QWORD *)a3;
  cchName[0] = 0;
  v35 = 0;
  hKey = 0;
  v4 = (_QWORD *)a3;
  v36 = 0;
  phkResult = 0;
  v5 = HampSystemOpenAppRegistryKey(a1, a2, a3, &hKey);
  v6 = hKey;
  v7 = v5;
  if ( v5 >= 0 )
  {
    v8 = RegOpenKeyExW(hKey, L"HAM\\AUI", 0, 8u, &phkResult);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0xC0070000;
    if ( v7 >= 0 )
    {
      v9 = -1;
      v10 = -1;
      v11 = 0;
      v12 = 0;
      LODWORD(v28) = 0;
      cchName[0] = 65;
      v7 = RegEnumKeyExW(phkResult, 0, Name, cchName, 0, 0, 0, 0);
      if ( v7 != 259 )
      {
        while ( 1 )
        {
          if ( v7 )
          {
            v6 = hKey;
            if ( v7 > 0 )
              v7 = (unsigned __int16)v7 | 0xC0070000;
            goto LABEL_47;
          }
          v7 = HampUsageInfoRegistryQuery(phkResult, Name, &v35);
          if ( v7 < 0 )
            goto LABEL_46;
          v13 = v35.m128i_u64[1];
          v14 = v35.m128i_i64[0];
          if ( (unsigned int)dword_18002E038 > 5
            && (qword_18002E048 & 1) != 0
            && (qword_18002E050 & 1) == qword_18002E050 )
          {
            v31 = v35.m128i_i64[1];
            v49 = &v31;
            v32 = v35.m128i_i64[0];
            v47 = &v32;
            v15 = -1;
            v50 = 8;
            v48 = 8;
            do
              v16 = Name[++v15] == 0;
            while ( !v16 );
            v46 = 0;
            v44 = Name;
            v45 = 2 * v15 + 2;
            if ( a1 )
            {
              v17 = (int *)a1;
              v18 = -1;
              do
                v16 = a1[++v18] == 0;
              while ( !v16 );
              v19 = 2 * v18 + 2;
            }
            else
            {
              v17 = &dword_1800232A4;
              v19 = 2;
            }
            v42 = v19;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_18002E040;
            v41 = v17;
            v43 = 0;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 1;
            UserData.Size = (unsigned __int16)*off_18002E040;
            v38 = byte_180026D85;
            UserData.Reserved = 2;
            v39 = 75;
            v40 = 1;
            LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
          }
          if ( v9 > v11 )
          {
            if ( v14 > v13 )
              goto LABEL_24;
            v20 = v9 <= v13;
          }
          else
          {
            if ( v14 > v13 )
            {
              if ( v14 > v11 )
                goto LABEL_33;
              goto LABEL_24;
            }
            if ( v9 > v13 )
              goto LABEL_33;
            v20 = v14 <= v11;
          }
          if ( !v20 )
          {
LABEL_33:
            if ( (__int64)v9 > (__int64)v14 )
              v14 = v9;
            goto LABEL_26;
          }
LABEL_24:
          if ( v9 < v14 )
            v14 = v9;
LABEL_26:
          v21 = *((_QWORD *)&v36 + 1);
          v9 = v14;
          v22 = v36;
          if ( v10 > v12 )
          {
            if ( (unsigned __int64)v36 > *((_QWORD *)&v36 + 1) )
              goto LABEL_37;
            v23 = v10 <= *((_QWORD *)&v36 + 1);
          }
          else
          {
            if ( (unsigned __int64)v36 > *((_QWORD *)&v36 + 1) )
            {
              if ( (unsigned __int64)v36 <= v12 )
                goto LABEL_37;
              goto LABEL_55;
            }
            if ( v10 > *((_QWORD *)&v36 + 1) )
              goto LABEL_55;
            v23 = (unsigned __int64)v36 <= v12;
          }
          if ( v23 )
          {
LABEL_37:
            if ( v10 < (unsigned __int64)v36 )
              v22 = v10;
            goto LABEL_39;
          }
LABEL_55:
          if ( (__int64)v10 > (__int64)v36 )
            v22 = v10;
LABEL_39:
          cchName[0] = 65;
          v10 = v22;
          v24 = v28;
          if ( v11 > v13 )
            v13 = v11;
          v11 = v13;
          if ( v12 > *((_QWORD *)&v36 + 1) )
            v21 = v12;
          v12 = v21;
          LODWORD(v28) = v28 + 1;
          v7 = RegEnumKeyExW(phkResult, v24 + 1, Name, cchName, 0, 0, 0, 0);
          if ( v7 == 259 )
          {
            v4 = v33;
            break;
          }
        }
      }
      *v4 = v9;
      v7 = 0;
      v4[1] = v11;
      v4[2] = v10;
      v4[3] = v12;
LABEL_46:
      v6 = hKey;
    }
  }
LABEL_47:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012240  mov     r11, rsp
0x180012243  push    rbp
0x180012244  push    rbx
0x180012245  push    rdi
0x180012246  lea     rbp, [r11-0E8h]
0x18001224d  sub     rsp, 1D0h
0x180012254  mov     rax, cs:__security_cookie
0x18001225b  xor     rax, rsp
0x18001225e  mov     [rbp+0E0h+var_40], rax
0x180012265  mov     [r11-30h], r14
0x180012269  lea     r9, [rsp+1E0h+hKey]; HKEY *
0x18001226e  xorps   xmm0, xmm0
0x180012271  mov     [r11-38h], r15
0x180012275  xor     ebx, ebx
0x180012277  mov     [rsp+1E0h+var_168], r8
0x18001227c  mov     r15, rcx
0x18001227f  mov     [rsp+1E0h+cchName], ebx
0x180012283  movups  [rbp+0E0h+var_150], xmm0
0x180012287  mov     [rsp+1E0h+hKey], rbx
0x18001228c  mov     r14, r8
0x18001228f  movups  [rbp+0E0h+var_140], xmm0
0x180012293  mov     [rsp+1E0h+var_188], rbx
0x180012298  call    ?HampSystemOpenAppRegistryKey@@YAJPEBGPEAXKPEAPEAUHKEY__@@@Z; HampSystemOpenAppRegistryKey(ushort const *,void *,ulong,HKEY__ * *)
0x18001229d  mov     rdi, [rsp+1E0h+hKey]
0x1800122a2  mov     ebx, eax
0x1800122a4  test    eax, eax
0x1800122a6  js      loc_1800125D7
0x1800122ac  lea     rax, [rsp+1E0h+var_188]
0x1800122b1  mov     r9d, 8; samDesired
0x1800122b7  xor     r8d, r8d; ulOptions
0x1800122ba  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800122bf  lea     rdx, aHamAui; "HAM\\AUI"
0x1800122c6  mov     rcx, rdi; hKey
0x1800122c9  call    cs:__imp_RegOpenKeyExW
0x1800122cf  mov     ebx, eax
0x1800122d1  test    eax, eax
0x1800122d3  jle     short loc_1800122DE
0x1800122d5  movzx   ebx, ax
0x1800122d8  or      ebx, 0C0070000h
0x1800122de  test    ebx, ebx
0x1800122e0  js      loc_1800125D7
0x1800122e6  mov     rcx, [rsp+1E0h+var_188]; hKey
0x1800122eb  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x1800122f0  xor     eax, eax
0x1800122f2  mov     [rsp+1E0h+arg_18], rsi
0x1800122fa  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800122ff  lea     r8, [rbp+0E0h+Name]; lpName
0x180012303  mov     [rsp+1E0h+lpcchClass], rax; lpcchClass
0x180012308  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001230f  mov     [rsp+1C8h], r12
0x180012317  xor     edx, edx; dwIndex
0x180012319  mov     [rsp+1E0h+lpClass], rax; lpClass
0x18001231e  mov     rsi, rdi
0x180012321  mov     [rsp+1E0h+var_20], r13
0x180012329  mov     r12d, eax
0x18001232c  mov     [rsp+1E0h+phkResult], rax; lpReserved
0x180012331  mov     r13d, eax
0x180012334  mov     dword ptr [rsp+1E0h+var_190], eax
0x180012338  mov     [rsp+1E0h+cchName], 41h ; 'A'
0x180012340  call    cs:__imp_RegEnumKeyExW
0x180012346  mov     ebx, eax
0x180012348  cmp     eax, 103h
0x18001234d  jz      loc_1800125A9
0x180012353  test    ebx, ebx
0x180012355  jnz     loc_18001263F
0x18001235b  mov     rcx, [rsp+1E0h+var_188]
0x180012360  lea     r8, [rbp+0E0h+var_150]
0x180012364  lea     rdx, [rbp+0E0h+Name]
0x180012368  call    HampUsageInfoRegistryQuery
0x18001236d  mov     ebx, eax
0x18001236f  test    eax, eax
0x180012371  js      loc_1800125BA
0x180012377  mov     eax, cs:dword_18002E038
0x18001237d  mov     r14, qword ptr [rbp+0E0h+var_150+8]
0x180012381  mov     rbx, qword ptr [rbp+0E0h+var_150]
0x180012385  cmp     eax, 5
0x180012388  jbe     loc_1800124D5
0x18001238e  mov     rcx, cs:qword_18002E050
0x180012395  mov     rax, cs:qword_18002E048
0x18001239c  test    al, 1
0x18001239e  jz      loc_1800124D5
0x1800123a4  mov     rax, rcx
0x1800123a7  and     eax, 1
0x1800123aa  cmp     rax, rcx
0x1800123ad  jnz     loc_1800124D5
0x1800123b3  lea     rax, [rsp+1E0h+var_178]
0x1800123b8  mov     [rsp+1E0h+var_178], r14
0x1800123bd  mov     [rbp+0E0h+var_E0], rax
0x1800123c1  lea     rcx, [rbp+0E0h+Name]
0x1800123c5  lea     rax, [rsp+1E0h+var_170]
0x1800123ca  mov     [rsp+1E0h+var_170], rbx
0x1800123cf  mov     [rbp+0E0h+var_F0], rax
0x1800123d3  xor     edx, edx
0x1800123d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800123dc  mov     [rbp+0E0h+var_D8], 8
0x1800123e4  mov     [rbp+0E0h+var_E8], 8
0x1800123ec  nop     dword ptr [rax+00h]
0x1800123f0  cmp     [rcx+rax*2+2], dx
0x1800123f5  lea     rax, [rax+1]
0x1800123f9  jnz     short loc_1800123F0
0x1800123fb  mov     [rbp+0E0h+var_F4], edx
0x1800123fe  lea     rcx, [rbp+0E0h+Name]
0x180012402  mov     [rbp+0E0h+var_100], rcx
0x180012406  lea     eax, ds:2[rax*2]
0x18001240d  mov     [rbp+0E0h+var_F8], eax
0x180012410  test    r15, r15
0x180012413  jz      short loc_180012435
0x180012415  mov     rcx, r15
0x180012418  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001241f  nop
0x180012420  cmp     [r15+rax*2+2], dx
0x180012426  lea     rax, [rax+1]
0x18001242a  jnz     short loc_180012420
0x18001242c  lea     eax, ds:2[rax*2]
0x180012433  jmp     short loc_180012441
0x180012435  lea     rcx, dword_1800232A4
0x18001243c  mov     eax, 2
0x180012441  mov     [rbp+0E0h+var_108], eax
0x180012444  xor     r9d, r9d; RelatedActivityId
0x180012447  movzx   eax, cs:word_180026D7B
0x18001244e  xor     r8d, r8d; ActivityId
0x180012451  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x180012454  mov     rax, cs:off_18002E040
0x18001245b  mov     [rbp+0E0h+UserData.Ptr], rax
0x18001245f  mov     [rbp+0E0h+var_110], rcx
0x180012463  lea     rcx, _TraceLoggingMetadata
0x18001246a  mov     [rbp+0E0h+var_104], edx
0x18001246d  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x180012471  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x180012478  mov     [rbp+0E0h+EventDescriptor.Keyword], 1
0x180012480  movzx   eax, word ptr [rax]
0x180012483  mov     [rbp+0E0h+UserData.Size], eax
0x180012486  lea     rax, byte_180026D85
0x18001248d  mov     [rbp+0E0h+var_120], rax
0x180012491  lea     rax, _TraceLoggingMetadataEnd
0x180012498  sub     eax, ecx
0x18001249a  mov     dword ptr [rbp+0E0h+UserData.0Ch], 2
0x1800124a1  mov     [rbp+0E0h+var_118], 4Bh ; 'K'
0x1800124a8  mov     [rbp+0E0h+var_114], 1
0x1800124af  mov     dword ptr [rsp+1E0h+var_180], eax
0x1800124b3  mov     eax, dword ptr [rsp+1E0h+var_180]
0x1800124b7  mov     rcx, cs:RegHandle; RegHandle
0x1800124be  lea     rax, [rbp+0E0h+UserData]
0x1800124c2  mov     [rsp+1E0h+lpClass], rax; UserData
0x1800124c7  mov     dword ptr [rsp+1E0h+phkResult], 6; UserDataCount
0x1800124cf  call    cs:__imp_EventWriteTransfer
0x1800124d5  cmp     rdi, r12
0x1800124d8  ja      short loc_18001251F
0x1800124da  cmp     rbx, r14
0x1800124dd  ja      short loc_1800124E9
0x1800124df  cmp     rdi, r14
0x1800124e2  ja      short loc_180012529
0x1800124e4  cmp     rbx, r12
0x1800124e7  jmp     short loc_180012527
0x1800124e9  cmp     rbx, r12
0x1800124ec  ja      short loc_180012529
0x1800124ee  cmp     rdi, rbx
0x1800124f1  cmovb   rbx, rdi
0x1800124f5  mov     rcx, qword ptr [rbp+0E0h+var_140+8]
0x1800124f9  mov     rdi, rbx
0x1800124fc  mov     rax, qword ptr [rbp+0E0h+var_140]
0x180012500  cmp     rsi, r13
0x180012503  ja      loc_180012621
0x180012509  cmp     rax, rcx
0x18001250c  ja      short loc_180012532
0x18001250e  cmp     rsi, rcx
0x180012511  ja      loc_180012633
0x180012517  cmp     rax, r13
0x18001251a  jmp     loc_18001262D
0x18001251f  cmp     rbx, r14
0x180012522  ja      short loc_1800124EE
0x180012524  cmp     rdi, r14
0x180012527  jbe     short loc_1800124EE
0x180012529  cmp     rdi, rbx
0x18001252c  cmovg   rbx, rdi
0x180012530  jmp     short loc_1800124F5
0x180012532  cmp     rax, r13
0x180012535  ja      loc_180012633
0x18001253b  cmp     rsi, rax
0x18001253e  cmovb   rax, rsi
0x180012542  cmp     r12, r14
0x180012545  mov     [rsp+1E0h+cchName], 41h ; 'A'
0x18001254d  mov     rsi, rax
0x180012550  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x180012555  mov     eax, dword ptr [rsp+1E0h+var_190]
0x180012559  lea     r8, [rbp+0E0h+Name]; lpName
0x18001255d  cmova   r14, r12
0x180012561  cmp     r13, rcx
0x180012564  mov     r12, r14
0x180012567  cmova   rcx, r13
0x18001256b  inc     eax
0x18001256d  mov     r13, rcx
0x180012570  mov     dword ptr [rsp+1E0h+var_190], eax
0x180012574  xor     ecx, ecx
0x180012576  mov     edx, eax; dwIndex
0x180012578  mov     [rsp+1E0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x18001257d  mov     [rsp+1E0h+lpcchClass], rcx; lpcchClass
0x180012582  mov     [rsp+1E0h+lpClass], rcx; lpClass
0x180012587  mov     [rsp+1E0h+phkResult], rcx; lpReserved
0x18001258c  mov     rcx, [rsp+1E0h+var_188]; hKey
0x180012591  call    cs:__imp_RegEnumKeyExW
0x180012597  mov     ebx, eax
0x180012599  cmp     eax, 103h
0x18001259e  jnz     loc_180012353
0x1800125a4  mov     r14, [rsp+1E0h+var_168]
0x1800125a9  mov     [r14], rdi
0x1800125ac  xor     ebx, ebx
0x1800125ae  mov     [r14+8], r12
0x1800125b2  mov     [r14+10h], rsi
0x1800125b6  mov     [r14+18h], r13
0x1800125ba  mov     rdi, [rsp+1E0h+hKey]
0x1800125bf  mov     r12, [rsp+1C8h]
0x1800125c7  mov     rsi, [rsp+1E0h+arg_18]
0x1800125cf  mov     r13, [rsp+1E0h+var_20]
0x1800125d7  mov     rcx, [rsp+1E0h+var_188]; hKey
0x1800125dc  mov     r15, [rsp+1E0h+var_30]
0x1800125e4  mov     r14, [rsp+1E0h+var_28]
0x1800125ec  test    rcx, rcx
0x1800125ef  jz      short loc_1800125F7
0x1800125f1  call    cs:__imp_RegCloseKey
0x1800125f7  test    rdi, rdi
0x1800125fa  jz      short loc_180012605
0x1800125fc  mov     rcx, rdi; hKey
0x1800125ff  call    cs:__imp_RegCloseKey
0x180012605  mov     eax, ebx
0x180012607  mov     rcx, [rbp+0E0h+var_40]
0x18001260e  xor     rcx, rsp; StackCookie
0x180012611  call    __security_check_cookie
0x180012616  add     rsp, 1D0h
0x18001261d  pop     rdi
0x18001261e  pop     rbx
0x18001261f  pop     rbp
0x180012620  retn
0x180012621  cmp     rax, rcx
0x180012624  ja      loc_18001253B
0x18001262a  cmp     rsi, rcx
0x18001262d  jbe     loc_18001253B
0x180012633  cmp     rsi, rax
0x180012636  cmovg   rax, rsi
0x18001263a  jmp     loc_180012542
0x18001263f  mov     rdi, [rsp+1E0h+hKey]
0x180012644  jle     loc_1800125BF
0x18001264a  movzx   ebx, bx
0x18001264d  or      ebx, 0C0070000h
0x180012653  jmp     loc_1800125BF
```
