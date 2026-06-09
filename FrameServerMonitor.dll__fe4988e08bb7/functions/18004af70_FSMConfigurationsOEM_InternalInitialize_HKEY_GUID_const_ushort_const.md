# FSMConfigurationsOEM::InternalInitialize(HKEY__ *,_GUID const &,ushort const *)

- ea: `0x18004af70`
- end: `0x18004b406`
- name: `?InternalInitialize@FSMConfigurationsOEM@@MEAAJPEAUHKEY__@@AEBU_GUID@@PEBG@Z`
- size: `1174`
- prototype: `int(FSMConfigurationsOEM *__hidden this, HKEY, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180006a98`
- `0x18000e6bc`
- `0x180011438`
- `0x180017b98`
- `0x180018564`
- `0x18002fa3c`
- `0x18002fd04`
- `0x1800418b8`
- `0x18004af70`
- `0x18004bc28`
- `0x18004bd08`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18004b01e`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18004b01e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b08b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b08b`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsOEM::InternalInitialize(
        FSMConfigurationsOEM *this,
        const struct std::nothrow_t *a2,
        const struct _GUID *a3,
        const char *a4)
{
  char v4; // al
  int v6; // esi
  GuidTrace *v10; // rax
  const char *String; // rdx
  const char *v12; // rax
  int v13; // r10d
  unsigned int v14; // r10d
  const struct FSMCameraControlSchemaEntry *v15; // r13
  LSTATUS v16; // r8d
  __int64 j; // rcx
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r14
  unsigned __int64 v21; // rcx
  wchar_t **v22; // rdx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  char v25; // al
  _DWORD *v26; // rdi
  wchar_t *v27; // rax
  HKEY v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  HKEY v32; // rdx
  HKEY v33; // rdx
  unsigned int i; // edx
  __int64 v35; // rax
  unsigned int k; // edi
  const char *v37; // rax
  __int64 v38; // rdx
  _OWORD v40[3]; // [rsp+40h] [rbp-30h] BYREF
  bool v41; // [rsp+B0h] [rbp+40h]
  HKEY phkResult; // [rsp+C0h] [rbp+50h] BYREF

  v4 = 0;
  v6 = 0;
  phkResult = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v10 = GuidTrace::GuidTrace((GuidTrace *)v40, a3);
    String = GuidTrace::GetString(v10);
    v12 = a4;
    if ( !a4 )
      v12 = L"<nullptr>";
    WPP_SF_qqsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (char)a2, (__int64)String, (__int64)v12);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
    FSString::~FSString((FSString *)v40, a2);
  *(struct _GUID *)((char *)this + 12) = *a3;
  if ( a4 )
    v13 = _o__wtol(a4);
  else
    v13 = 0;
  *((_DWORD *)this + 7) = v13;
  *((_BYTE *)this + 312) = 0;
  if ( !v13 || (v15 = FSMFindMatchingSchemaEntry((const struct _GUID *)((char *)this + 12), v13)) == 0 )
  {
    for ( i = 0; i < 5; ++i )
    {
      v35 = (int)i;
      *((_DWORD *)this + 12 * v35 + 8) = -1610612736;
    }
    goto LABEL_49;
  }
  v41 = FSIsCameraControlPinScope((const struct _GUID *)((char *)this + 12), v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v16 = RegOpenKeyExW((HKEY)a2, (LPCWSTR)a4, 0, 0x20019u, &phkResult);
  if ( v16 )
  {
    for ( j = 0; j != 5; ++j )
    {
      v18 = 6 * j;
      *((_DWORD *)this + 12 * j + 8) = -1073741824;
      if ( v16 > 0 )
        v19 = (unsigned __int16)v16 | 0x80070000;
      else
        v19 = v16;
      *((_DWORD *)this + 2 * v18 + 9) = v19;
    }
    goto LABEL_49;
  }
  v20 = 0;
  *(_OWORD *)((char *)this + 312) = *(_OWORD *)v15;
  while ( 1 )
  {
    v21 = 48 * v20;
    v22 = (unsigned int)v20 >= 5uLL ? 0LL : &(&off_180050460)[v21 / 8];
    if ( v22 )
      break;
    *(_DWORD *)((char *)this + v21 + 32) |= 0xC0000000;
    *(_DWORD *)((char *)this + v21 + 36) = -1072875841;
LABEL_42:
    v20 = (unsigned int)(v20 + 1);
    if ( (int)v20 >= 5 )
      goto LABEL_49;
  }
  v23 = *((_OWORD *)v22 + 1);
  v40[0] = *(_OWORD *)v22;
  v24 = *((_OWORD *)v22 + 2);
  v40[1] = v23;
  v40[2] = v24;
  if ( v41 )
  {
    v25 = BYTE12(v40[0]);
    if ( DWORD2(v40[0]) == 1 )
      v25 = 1;
    BYTE12(v40[0]) = v25;
  }
  *(_DWORD *)((char *)this + v21 + 36) = 0;
  v26 = (_DWORD *)((char *)this + v21 + 32);
  *v26 = 0;
  *(_DWORD *)((char *)this + v21 + 40) = *((_DWORD *)v22 + 4);
  *(_QWORD *)((char *)this + v21 + 64) = v22[4];
  *(_QWORD *)((char *)this + v21 + 72) = v22[5];
  *(_DWORD *)((char *)this + v21 + 48) = *((_DWORD *)v15 + 3);
  if ( *((_DWORD *)v22 + 4) != 3 )
  {
    if ( *((_DWORD *)v22 + 4) == 4 )
    {
      v31 = *((_DWORD *)v22 + 6);
      v32 = phkResult;
      *(_DWORD *)((char *)this + v21 + 56) = v31;
      v29 = (*(__int64 (__fastcall **)(FSMConfigurationsOEM *, HKEY, _OWORD *, char *))(*(_QWORD *)this + 96LL))(
              this,
              v32,
              v40,
              (char *)this + v21 + 32);
      v6 = v29;
      if ( v29 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_49;
        v30 = 32;
        goto LABEL_46;
      }
    }
    else if ( *((_DWORD *)v22 + 4) == 11 )
    {
      v27 = v22[3];
      v28 = phkResult;
      *(_QWORD *)((char *)this + v21 + 56) = v27;
      v29 = (*(__int64 (__fastcall **)(FSMConfigurationsOEM *, HKEY, _OWORD *, char *))(*(_QWORD *)this + 104LL))(
              this,
              v28,
              v40,
              (char *)this + v21 + 32);
      v6 = v29;
      if ( v29 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_49;
        v30 = 33;
        goto LABEL_46;
      }
    }
    else
    {
      *(_DWORD *)((char *)this + v21 + 48) = 0;
    }
    goto LABEL_39;
  }
  v33 = phkResult;
  *(_QWORD *)((char *)this + v21 + 56) = 0;
  v29 = (*(__int64 (__fastcall **)(FSMConfigurationsOEM *, HKEY, _OWORD *, char *, _DWORD *, char *))(*(_QWORD *)this + 88LL))(
          this,
          v33,
          v40,
          (char *)this + 312,
          v26,
          (char *)this + 8 * (unsigned int)v20 + 272);
  v6 = v29;
  if ( v29 >= 0 )
  {
LABEL_39:
    if ( (*v26 & 0xFFFFFFFE) != 0 )
      *v26 |= 0x80000000;
    goto LABEL_42;
  }
  if ( !g_wppLevels )
    goto LABEL_49;
  v30 = 31;
LABEL_46:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids, this, v29);
LABEL_49:
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
  {
    for ( k = 0; k < 5; ++k )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        if ( k )
        {
          switch ( k )
          {
            case 1u:
              v37 = "pinid";
              break;
            case 2u:
              v37 = "flags";
              break;
            case 3u:
              v37 = "capability";
              break;
            default:
              v37 = "data";
              break;
          }
        }
        else
        {
          v37 = "version";
        }
        WPP_SF_qsd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          34,
          (unsigned int)&WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids,
          (_DWORD)this,
          (__int64)v37,
          *((_DWORD *)this + 12 * (int)k + 8));
      }
    }
  }
  if ( v6 >= 0 )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v38 = 36;
LABEL_68:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v38, &WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids, this, v6);
    }
  }
  else if ( byte_18005E5A5 )
  {
    v38 = 35;
    goto LABEL_68;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004af70  mov     [rsp-38h+arg_8], rbx
0x18004af75  push    rbp
0x18004af76  push    rsi
0x18004af77  push    rdi
0x18004af78  push    r12
0x18004af7a  push    r13
0x18004af7c  push    r14
0x18004af7e  push    r15
0x18004af80  mov     rbp, rsp
0x18004af83  sub     rsp, 70h
0x18004af87  xor     eax, eax
0x18004af89  mov     rdi, r9
0x18004af8c  mov     [rbp+arg_0], eax
0x18004af8f  xor     esi, esi
0x18004af91  mov     [rbp+arg_10], rax
0x18004af95  mov     r15, r8
0x18004af98  mov     r12, rdx
0x18004af9b  mov     rbx, rcx
0x18004af9e  cmp     cs:byte_18005E5A5, 8
0x18004afa5  lea     r13d, [rax+1]
0x18004afa9  jb      short loc_18004AFFB
0x18004afab  mov     rdx, r8; struct _GUID *
0x18004afae  lea     rcx, [rbp+var_30]; this
0x18004afb2  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18004afb7  mov     rcx, rax; this
0x18004afba  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18004afbf  mov     rdx, rax
0x18004afc2  lea     rcx, aNullptr; "<nullptr>"
0x18004afc9  test    rdi, rdi
0x18004afcc  mov     rax, rdi
0x18004afcf  mov     r9, rbx
0x18004afd2  cmovz   rax, rcx
0x18004afd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004afdd  mov     [rsp+70h+var_40], rax; __int64
0x18004afe2  mov     [rsp+70h+var_48], rdx; __int64
0x18004afe7  mov     [rsp+70h+phkResult], r12; char
0x18004afec  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18004aff3  call    WPP_SF_qqsS
0x18004aff8  mov     eax, r13d
0x18004affb  test    r13b, al
0x18004affe  jz      short loc_18004B009
0x18004b000  lea     rcx, [rbp+var_30]; this
0x18004b004  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18004b009  lea     r14, [rbx+0Ch]
0x18004b00d  movups  xmm0, xmmword ptr [r15]
0x18004b011  movdqu  xmmword ptr [r14], xmm0
0x18004b016  test    rdi, rdi
0x18004b019  jz      short loc_18004B029
0x18004b01b  mov     rcx, rdi
0x18004b01e  call    cs:__imp__o__wtol
0x18004b024  mov     r10d, eax
0x18004b027  jmp     short loc_18004B02C
0x18004b029  xor     r10d, r10d
0x18004b02c  mov     [rbx+1Ch], r10d
0x18004b030  lea     r15, [rbx+138h]
0x18004b037  mov     [r15], sil
0x18004b03a  test    r10d, r10d
0x18004b03d  jz      loc_18004B2D3
0x18004b043  mov     edx, r10d; int
0x18004b046  mov     rcx, r14; struct _GUID *
0x18004b049  call    ?FSMFindMatchingSchemaEntry@@YAPEBUFSMCameraControlSchemaEntry@@AEBU_GUID@@J@Z; FSMFindMatchingSchemaEntry(_GUID const &,long)
0x18004b04e  mov     r13, rax
0x18004b051  test    rax, rax
0x18004b054  jz      loc_18004B2CD
0x18004b05a  mov     edx, r10d; unsigned int
0x18004b05d  mov     rcx, r14; struct _GUID *
0x18004b060  call    ?FSIsCameraControlPinScope@@YA_NAEBU_GUID@@K@Z; FSIsCameraControlPinScope(_GUID const &,ulong)
0x18004b065  xor     edx, edx
0x18004b067  mov     byte ptr [rbp+arg_0], al
0x18004b06a  lea     rcx, [rbp+arg_10]
0x18004b06e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b073  lea     rax, [rbp+arg_10]
0x18004b077  mov     r9d, 20019h; samDesired
0x18004b07d  xor     r8d, r8d; ulOptions
0x18004b080  mov     [rsp+70h+phkResult], rax; phkResult
0x18004b085  mov     rdx, rdi; lpSubKey
0x18004b088  mov     rcx, r12; hKey
0x18004b08b  call    cs:__imp_RegOpenKeyExW
0x18004b091  mov     r8d, eax
0x18004b094  test    eax, eax
0x18004b096  jz      short loc_18004B0D2
0x18004b098  xor     ecx, ecx
0x18004b09a  lea     r13d, [rcx+1]
0x18004b09e  lea     rdx, [rcx+rcx*2]
0x18004b0a2  add     rdx, rdx
0x18004b0a5  mov     dword ptr [rbx+rdx*8+20h], 0C0000000h
0x18004b0ad  test    r8d, r8d
0x18004b0b0  jg      short loc_18004B0B7
0x18004b0b2  mov     eax, r8d
0x18004b0b5  jmp     short loc_18004B0C0
0x18004b0b7  movzx   eax, r8w
0x18004b0bb  or      eax, 80070000h
0x18004b0c0  add     rcx, r13
0x18004b0c3  mov     [rbx+rdx*8+24h], eax
0x18004b0c7  cmp     rcx, 5
0x18004b0cb  jnz     short loc_18004B09E
0x18004b0cd  jmp     loc_18004B2EF
0x18004b0d2  movups  xmm0, xmmword ptr [r13+0]
0x18004b0d7  mov     r12b, byte ptr [rbp+arg_0]
0x18004b0db  xor     r14d, r14d
0x18004b0de  movdqu  xmmword ptr [r15], xmm0
0x18004b0e3  lea     r8d, [r14+1]
0x18004b0e7  lea     rcx, [r14+r14*2]
0x18004b0eb  mov     r9d, r14d
0x18004b0ee  shl     rcx, 4
0x18004b0f2  cmp     r9, 5
0x18004b0f6  jnb     short loc_18004B104
0x18004b0f8  lea     rdx, off_180050460; "Version"
0x18004b0ff  add     rdx, rcx
0x18004b102  jmp     short loc_18004B106
0x18004b104  xor     edx, edx
0x18004b106  test    rdx, rdx
0x18004b109  jz      loc_18004B275
0x18004b10f  movups  xmm0, xmmword ptr [rdx]
0x18004b112  movups  xmm1, xmmword ptr [rdx+10h]
0x18004b116  movups  [rbp+var_30], xmm0
0x18004b11a  movups  xmm0, xmmword ptr [rdx+20h]
0x18004b11e  movups  [rbp+var_20], xmm1
0x18004b122  movups  [rbp+var_10], xmm0
0x18004b126  test    r12b, r12b
0x18004b129  jz      short loc_18004B13A
0x18004b12b  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x18004b12f  cmp     dword ptr [rbp+var_30+8], r8d
0x18004b133  cmovz   eax, r8d
0x18004b137  mov     byte ptr [rbp+var_30+0Ch], al
0x18004b13a  mov     dword ptr [rcx+rbx+24h], 0
0x18004b142  lea     rdi, [rbx+20h]
0x18004b146  add     rdi, rcx
0x18004b149  mov     dword ptr [rdi], 0
0x18004b14f  mov     eax, [rdx+10h]
0x18004b152  mov     [rcx+rbx+28h], eax
0x18004b156  mov     rax, [rdx+20h]
0x18004b15a  mov     [rcx+rbx+40h], rax
0x18004b15f  mov     rax, [rdx+28h]
0x18004b163  mov     [rcx+rbx+48h], rax
0x18004b168  mov     eax, [r13+0Ch]
0x18004b16c  mov     [rcx+rbx+30h], eax
0x18004b170  mov     r8d, [rdx+10h]
0x18004b174  sub     r8d, 3
0x18004b178  jz      loc_18004B223
0x18004b17e  sub     r8d, 1
0x18004b182  jz      short loc_18004B1E0
0x18004b184  cmp     r8d, 7
0x18004b188  jz      short loc_18004B197
0x18004b18a  mov     dword ptr [rcx+rbx+30h], 0
0x18004b192  jmp     loc_18004B25E
0x18004b197  mov     rax, [rdx+18h]
0x18004b19b  lea     r8, [rbp+var_30]
0x18004b19f  mov     rdx, [rbp+arg_10]
0x18004b1a3  mov     r9, rdi
0x18004b1a6  mov     [rcx+rbx+38h], rax
0x18004b1ab  mov     rcx, rbx
0x18004b1ae  mov     rax, [rbx]
0x18004b1b1  mov     rax, [rax+68h]
0x18004b1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1ba  mov     esi, eax
0x18004b1bc  test    eax, eax
0x18004b1be  jns     loc_18004B25E
0x18004b1c4  mov     r13d, 1
0x18004b1ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004b1d1  jb      loc_18004B2EF
0x18004b1d7  lea     edx, [r13+20h]
0x18004b1db  jmp     loc_18004B2AD
0x18004b1e0  mov     eax, [rdx+18h]
0x18004b1e3  lea     r8, [rbp+var_30]
0x18004b1e7  mov     rdx, [rbp+arg_10]
0x18004b1eb  mov     r9, rdi
0x18004b1ee  mov     [rcx+rbx+38h], eax
0x18004b1f2  mov     rcx, rbx
0x18004b1f5  mov     rax, [rbx]
0x18004b1f8  mov     rax, [rax+60h]
0x18004b1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b201  mov     esi, eax
0x18004b203  test    eax, eax
0x18004b205  jns     short loc_18004B25E
0x18004b207  mov     r13d, 1
0x18004b20d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004b214  jb      loc_18004B2EF
0x18004b21a  lea     edx, [r13+1Fh]
0x18004b21e  jmp     loc_18004B2AD
0x18004b223  mov     rdx, [rbp+arg_10]
0x18004b227  lea     r8, [rbp+var_30]
0x18004b22b  mov     qword ptr [rcx+rbx+38h], 0
0x18004b234  add     r9, 22h ; '"'
0x18004b238  mov     rax, [rbx]
0x18004b23b  lea     rcx, [rbx+r9*8]
0x18004b23f  mov     r9, r15
0x18004b242  mov     rax, [rax+58h]
0x18004b246  mov     [rsp+70h+var_48], rcx
0x18004b24b  mov     rcx, rbx
0x18004b24e  mov     [rsp+70h+phkResult], rdi
0x18004b253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b258  mov     esi, eax
0x18004b25a  test    eax, eax
0x18004b25c  js      short loc_18004B29A
0x18004b25e  mov     eax, [rdi]
0x18004b260  mov     r8d, 1
0x18004b266  test    eax, 0FFFFFFFEh
0x18004b26b  jz      short loc_18004B285
0x18004b26d  bts     eax, 1Fh
0x18004b271  mov     [rdi], eax
0x18004b273  jmp     short loc_18004B285
0x18004b275  or      dword ptr [rcx+rbx+20h], 0C0000000h
0x18004b27d  mov     dword ptr [rcx+rbx+24h], 0C00D36BFh
0x18004b285  add     r14d, r8d
0x18004b288  cmp     r14d, 5
0x18004b28c  jl      loc_18004B0E7
0x18004b292  mov     r13d, 1
0x18004b298  jmp     short loc_18004B2EF
0x18004b29a  mov     r13d, 1
0x18004b2a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004b2a7  jb      short loc_18004B2EF
0x18004b2a9  lea     edx, [r13+1Eh]
0x18004b2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b2b4  lea     r8, WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids
0x18004b2bb  mov     r9, rbx
0x18004b2be  mov     dword ptr [rsp+70h+phkResult], eax
0x18004b2c2  mov     rcx, [rcx+10h]
0x18004b2c6  call    WPP_SF_qD
0x18004b2cb  jmp     short loc_18004B2EF
0x18004b2cd  mov     r13d, 1
0x18004b2d3  xor     edx, edx
0x18004b2d5  movsxd  rax, edx
0x18004b2d8  add     edx, r13d
0x18004b2db  lea     rcx, [rax+rax*2]
0x18004b2df  add     rcx, rcx
0x18004b2e2  mov     dword ptr [rbx+rcx*8+20h], 0A0000000h
0x18004b2ea  cmp     edx, 5
0x18004b2ed  jb      short loc_18004B2D5
0x18004b2ef  cmp     cs:byte_18005E5A5, 10h
0x18004b2f6  jb      loc_18004B3A0
0x18004b2fc  xor     edi, edi
0x18004b2fe  cmp     cs:byte_18005E5A5, 8
0x18004b305  jb      loc_18004B394
0x18004b30b  movsxd  rax, edi
0x18004b30e  lea     rcx, [rax+rax*2]
0x18004b312  add     rcx, rcx
0x18004b315  mov     r8d, [rbx+rcx*8+20h]
0x18004b31a  mov     ecx, edi
0x18004b31c  test    edi, edi
0x18004b31e  jz      short loc_18004B361
0x18004b320  sub     ecx, 1
0x18004b323  jz      short loc_18004B358
0x18004b325  sub     ecx, 1
0x18004b328  jz      short loc_18004B34F
0x18004b32a  sub     ecx, 1
0x18004b32d  jz      short loc_18004B346
0x18004b32f  cmp     ecx, 1
0x18004b332  jz      short loc_18004B33D
0x18004b334  lea     rax, aUnknown; "unknown"
0x18004b33b  jmp     short loc_18004B368
0x18004b33d  lea     rax, aData_0; "data"
0x18004b344  jmp     short loc_18004B368
0x18004b346  lea     rax, aCapability; "capability"
0x18004b34d  jmp     short loc_18004B368
0x18004b34f  lea     rax, aFlags_0; "flags"
0x18004b356  jmp     short loc_18004B368
0x18004b358  lea     rax, aPinid; "pinid"
0x18004b35f  jmp     short loc_18004B368
0x18004b361  lea     rax, aVersion_0; "version"
0x18004b368  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b36f  mov     edx, 22h ; '"'
0x18004b374  mov     dword ptr [rsp+70h+var_48], r8d
0x18004b379  mov     r9, rbx
0x18004b37c  lea     r8, WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids
0x18004b383  mov     [rsp+70h+phkResult], rax
0x18004b388  mov     rcx, [rcx+0D8h]
0x18004b38f  call    WPP_SF_qsd
0x18004b394  add     edi, r13d
0x18004b397  cmp     edi, 5
0x18004b39a  jb      loc_18004B2FE
0x18004b3a0  test    esi, esi
0x18004b3a2  jns     short loc_18004B3B4
0x18004b3a4  cmp     cs:byte_18005E5A5, r13b
0x18004b3ab  jb      short loc_18004B3E3
0x18004b3ad  mov     edx, 23h ; '#'
0x18004b3b2  jmp     short loc_18004B3C2
0x18004b3b4  cmp     cs:byte_18005E5A5, 8
0x18004b3bb  jb      short loc_18004B3E3
0x18004b3bd  mov     edx, 24h ; '$'
0x18004b3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b3c9  lea     r8, WPP_98eb5cd08f9e39f70ad7ebfba028aff0_Traceguids
0x18004b3d0  mov     r9, rbx
0x18004b3d3  mov     dword ptr [rsp+70h+phkResult], esi
0x18004b3d7  mov     rcx, [rcx+0D8h]
0x18004b3de  call    WPP_SF_qD
0x18004b3e3  lea     rcx, [rbp+arg_10]
0x18004b3e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b3ec  mov     rbx, [rsp+70h+arg_8]
0x18004b3f4  mov     eax, esi
0x18004b3f6  add     rsp, 70h
0x18004b3fa  pop     r15
0x18004b3fc  pop     r14
0x18004b3fe  pop     r13
0x18004b400  pop     r12
0x18004b402  pop     rdi
0x18004b403  pop     rsi
0x18004b404  pop     rbp
0x18004b405  retn
```
