# CWwanContextLifeCycle::UpdateL2Profile(bool)

- ea: `0x1800540f0`
- end: `0x180054472`
- name: `?UpdateL2Profile@CWwanContextLifeCycle@@AEAAK_N@Z`
- size: `898`
- prototype: `unsigned int __fastcall(CWwanContextLifeCycle *__hidden this, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800539fc`

## callees

- `0x1800085d0`
- `0x1800094dc`
- `0x1800094f4`
- `0x1800095f4`
- `0x180012300`
- `0x180014f1c`
- `0x18001db34`
- `0x180047340`
- `0x1800540f0`
- `0x1800769a4`
- `0x18009d0c8`
- `0x1800c8520`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005428c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054358`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005428c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180054358`

## string_xrefs

- `0x180054364`: `abnormal Sid (%s) Len %d`
- `0x180054207`: `CWwanContextLifeCycle::UpdateL2Profile`
- `0x180054312`: `CWwanContextLifeCycle::UpdateL2Profile`
- `0x18005436f`: `CWwanContextLifeCycle::UpdateL2Profile`
- `0x180054397`: `CWwanContextLifeCycle::UpdateL2Profile`
- `0x180054305`: `UpdateL2Profile abnormal MCC/MNC (%s) Len %d MCC %d MNC %d`
- `0x1800541fe`: `RegisterState %d, no need to UpdateL2Profile`

## pseudocode

```c
__int64 __fastcall CWwanContextLifeCycle::UpdateL2Profile(__m128i **this, unsigned __int8 a2)
{
  int v2; // r14d
  __m128i *v4; // rcx
  struct _GUID v5; // xmm0
  __m128i *v6; // rcx
  __int64 v7; // rax
  int v8; // esi
  __m128i v9; // xmm1
  __m128i v10; // xmm6
  __m128i v11; // xmm0
  __int128 v12; // xmm0
  unsigned int v13; // ebx
  int v15; // ebx
  int L2ProfileInformation; // edi
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+28h] [rbp-D8h]
  int v27[2]; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v31[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int128 v35; // [rsp+90h] [rbp-70h] BYREF
  __m128i v36; // [rsp+A0h] [rbp-60h]
  __m128i v37; // [rsp+B0h] [rbp-50h]
  __m128i v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  struct _GUID v40; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Source[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v42; // [rsp+100h] [rbp+0h]
  __int128 v43; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+120h] [rbp+20h]
  unsigned __int16 v45[256]; // [rsp+130h] [rbp+30h] BYREF

  v2 = a2;
  v4 = *this;
  memset(v31, 0, 28);
  v5 = *(struct _GUID *)(*(__int64 (__fastcall **)(__m128i *))(v4->m128i_i64[0] + 16))(v4);
  *(_OWORD *)Source = 0;
  v44 = 0;
  v40 = v5;
  v42 = 0;
  v43 = 0;
  memset_0(v45, 0, 0x18B0u);
  v6 = *this;
  v7 = (*this)->m128i_i64[1];
  v8 = (*this)[401].m128i_i32[3];
  v9 = (*this)[399];
  v10 = (*this)[397];
  v36 = (*this)[398];
  v11 = v6[400];
  v37 = v9;
  v9.m128i_i64[0] = v6[401].m128i_i64[0];
  v38 = v11;
  v12 = *(_OWORD *)(v7 + 14140);
  v39 = v9.m128i_i64[0];
  *(_OWORD *)Source = v12;
  v13 = _mm_cvtsi128_si32(v10);
  v42 = *(_OWORD *)(v7 + 14156);
  v43 = *(_OWORD *)(v7 + 14172);
  v44 = *(_QWORD *)(v7 + 14188);
  if ( v13 - 3 > 2 )
  {
    WwanLog::Info("CWwanContextLifeCycle::UpdateL2Profile", 0, L"RegisterState %d, no need to UpdateL2Profile", v13);
    return 0;
  }
  if ( (_BYTE)v2 )
    CWWANContextControllerBase::GetAnyProfileForCurrentSIM(
      (CWWANContextControllerBase *)v6,
      (unsigned __int16 (*)[256])v45);
  else
    memcpy_0(v45, &v6[1], 0x18B0u);
  v26 = v13;
  v15 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 4));
  L2ProfileInformation = WwanPmGetL2ProfileInformation(&v40, (int)v45, v8, v26, (__int64)v31);
  if ( v15 == 2 )
    goto LABEL_14;
  if ( v15 == 1 )
  {
    if ( (v8 & 0x260000) == 0 )
    {
      v17 = wcsnlen(Source, 7u);
      v18 = 0;
      v19 = 0;
      v20 = v17;
      v30 = 0;
      v29 = 0;
      if ( (unsigned int)(v17 - 5) <= 1 )
      {
        if ( swscanf_s(Source, L"%3d%d", &v30, &v29) == 2 )
        {
          v31[1] |= ((((unsigned __int16)v30 << 10) | v29 & 0x3FF) << 12) | 0x800;
          goto LABEL_17;
        }
        v18 = v30;
        v19 = v29;
      }
      LODWORD(v28) = v19;
      v27[0] = v18;
      LODWORD(v25) = v20;
      WwanLog::Error(
        "CWwanContextLifeCycle::UpdateL2Profile",
        0,
        L"UpdateL2Profile abnormal MCC/MNC (%s) Len %d MCC %d MNC %d",
        Source,
        v25,
        *(_QWORD *)v27,
        v28);
      goto LABEL_17;
    }
LABEL_14:
    v29 = 0;
    if ( swscanf_s(Source, L"%5d", &v29) == 1 )
    {
      v31[1] |= v29 << 12;
    }
    else
    {
      LODWORD(v25) = wcsnlen(Source, 7u);
      WwanLog::Error("CWwanContextLifeCycle::UpdateL2Profile", 0, L"abnormal Sid (%s) Len %d", Source, v25);
    }
  }
LABEL_17:
  if ( L2ProfileInformation )
  {
    v27[0] = v2;
    LODWORD(v25) = L2ProfileInformation;
    WwanLog::Error(
      "CWwanContextLifeCycle::UpdateL2Profile",
      &v40,
      L"get profile information failed, profile %ws, error %u, fExperimental_for_5GURSP %d",
      v45,
      v25,
      *(_QWORD *)v27);
  }
  v34 = 0;
  WwanLog::Info("CWwanContextLifeCycle::SetProfileIndex", &v40, L"set profile index, profile index %x", v31[0]);
  CWwanManager::GetInstance();
  v32 = 0u;
  v33 = 1u;
  v35 = 0u;
  v37.m128i_i64[0] = v34;
  v36 = (__m128i)1uLL;
  v23 = WwanTxmSendReqSyncNoQueue(&v40, v21, v22, &v35);
  v24 = v23;
  if ( v23 )
    WwanLog::Error("CWwanContextLifeCycle::SetProfileIndex", 0, L"WwanTxmSendReq failed, dwError (%u)", v23);
  else
    return 0;
  return v24;
}

```

## disassembly

```asm
0x1800540f0  mov     [rsp-8+arg_10], rbx
0x1800540f5  mov     [rsp-8+arg_18], rsi
0x1800540fa  push    rbp
0x1800540fb  push    rdi
0x1800540fc  push    r14
0x1800540fe  lea     rbp, [rsp-1900h]
0x180054106  mov     eax, 1A00h
0x18005410b  call    _alloca_probe
0x180054110  sub     rsp, rax
0x180054113  movaps  [rsp+1A10h+var_20], xmm6
0x18005411b  mov     rax, cs:__security_cookie
0x180054122  xor     rax, rsp
0x180054125  mov     [rbp+1910h+var_30], rax
0x18005412c  xorps   xmm0, xmm0
0x18005412f  movzx   r14d, dl
0x180054133  mov     rbx, rcx
0x180054136  mov     rcx, [rcx]
0x180054139  movups  xmmword ptr [rsp+1A10h+var_19C8], xmm0
0x18005413e  movups  xmmword ptr [rsp+1A10h+var_19C8+0Ch], xmm0
0x180054143  mov     rax, [rcx]
0x180054146  mov     rax, [rax+10h]
0x18005414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005414f  xorps   xmm1, xmm1
0x180054152  lea     rcx, [rbp+1910h+var_18E0]; void *
0x180054156  mov     edi, 18B0h
0x18005415b  xor     edx, edx; Val
0x18005415d  mov     r8d, edi; Size
0x180054160  movups  xmm0, xmmword ptr [rax]
0x180054163  xor     eax, eax
0x180054165  movups  xmmword ptr [rbp+1910h+Source], xmm1
0x180054169  mov     [rbp+1910h+var_18F0], rax
0x18005416d  movdqu  xmmword ptr [rbp+1910h+var_1930.Data1], xmm0
0x180054172  movups  [rbp+1910h+var_1910], xmm1
0x180054176  movups  [rbp+1910h+var_1900], xmm1
0x18005417a  call    memset_0
0x18005417f  mov     rcx, [rbx]; this
0x180054182  mov     rax, [rcx+8]
0x180054186  movups  xmm0, xmmword ptr [rcx+18E0h]
0x18005418d  mov     esi, [rcx+191Ch]
0x180054193  movups  xmm1, xmmword ptr [rcx+18F0h]
0x18005419a  movups  xmm6, xmmword ptr [rcx+18D0h]
0x1800541a1  movaps  [rbp+1910h+var_1970], xmm0
0x1800541a5  movups  xmm0, xmmword ptr [rcx+1900h]
0x1800541ac  movaps  [rbp+1910h+var_1960], xmm1
0x1800541b0  movsd   xmm1, qword ptr [rcx+1910h]
0x1800541b8  movaps  [rbp+1910h+var_1950], xmm0
0x1800541bc  movups  xmm0, xmmword ptr [rax+373Ch]
0x1800541c3  movsd   [rbp+1910h+var_1940], xmm1
0x1800541c8  movups  xmmword ptr [rbp+1910h+Source], xmm0
0x1800541cc  movups  xmm1, xmmword ptr [rax+374Ch]
0x1800541d3  movd    ebx, xmm6
0x1800541d7  movups  [rbp+1910h+var_1910], xmm1
0x1800541db  movups  xmm0, xmmword ptr [rax+375Ch]
0x1800541e2  movups  [rbp+1910h+var_1900], xmm0
0x1800541e6  movsd   xmm1, qword ptr [rax+376Ch]
0x1800541ee  lea     eax, [rbx-3]
0x1800541f1  movsd   [rbp+1910h+var_18F0], xmm1
0x1800541f6  cmp     eax, 2
0x1800541f9  jbe     short loc_18005421A
0x1800541fb  mov     r9d, ebx
0x1800541fe  lea     r8, aRegisterstateD; "RegisterState %d, no need to UpdateL2Pr"...
0x180054205  xor     edx, edx; struct _GUID *
0x180054207  lea     rcx, aCwwancontextli_22; "CWwanContextLifeCycle::UpdateL2Profile"
0x18005420e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180054213  xor     eax, eax
0x180054215  jmp     loc_180054446
0x18005421a  test    r14b, r14b
0x18005421d  jnz     short loc_180054231
0x18005421f  lea     rdx, [rcx+10h]; Src
0x180054223  mov     r8, rdi; Size
0x180054226  lea     rcx, [rbp+1910h+var_18E0]; void *
0x18005422a  call    memcpy_0
0x18005422f  jmp     short loc_18005423A
0x180054231  lea     rdx, [rbp+1910h+var_18E0]; unsigned __int16 (*)[256]
0x180054235  call    ?GetAnyProfileForCurrentSIM@CWWANContextControllerBase@@QEAAKAEAY0BAA@G@Z; CWWANContextControllerBase::GetAnyProfileForCurrentSIM(ushort (&)[256])
0x18005423a  lea     rax, [rsp+1A10h+var_19C8]
0x18005423f  psrldq  xmm6, 4
0x180054244  mov     [rsp+1A10h+var_19E0], rax; __int64
0x180054249  lea     rdx, [rbp+1910h+var_18E0]; int
0x18005424d  mov     [rsp+1A10h+var_19E8], ebx; int
0x180054251  lea     rcx, [rbp+1910h+var_1930]; struct _GUID *
0x180054255  movd    ebx, xmm6
0x180054259  mov     dword ptr [rsp+1A10h+var_19F0], esi; int
0x18005425d  mov     r9d, ebx
0x180054260  call    WwanPmGetL2ProfileInformation
0x180054265  mov     edi, eax
0x180054267  cmp     ebx, 2
0x18005426a  jz      loc_180054320
0x180054270  cmp     ebx, 1
0x180054273  jnz     loc_18005437B
0x180054279  test    esi, 260000h
0x18005427f  jnz     loc_180054320
0x180054285  lea     edx, [rbx+6]; MaxCount
0x180054288  lea     rcx, [rbp+1910h+Source]; Source
0x18005428c  call    cs:__imp_wcsnlen
0x180054292  xor     edx, edx
0x180054294  xor     r8d, r8d
0x180054297  mov     rbx, rax
0x18005429a  mov     [rsp+1A10h+var_19CC], edx
0x18005429e  mov     [rsp+1A10h+var_19D0], r8d
0x1800542a3  lea     ecx, [rax-5]
0x1800542a6  cmp     ecx, 1
0x1800542a9  ja      short loc_1800542F8
0x1800542ab  lea     r9, [rsp+1A10h+var_19D0]
0x1800542b0  lea     r8, [rsp+1A10h+var_19CC]
0x1800542b5  lea     rdx, a3dD; "%3d%d"
0x1800542bc  lea     rcx, [rbp+1910h+Source]; Buffer
0x1800542c0  call    swscanf_s
0x1800542c5  cmp     eax, 2
0x1800542c8  jnz     short loc_1800542EF
0x1800542ca  movzx   ecx, word ptr [rsp+1A10h+var_19D0]
0x1800542cf  movzx   eax, word ptr [rsp+1A10h+var_19CC]
0x1800542d4  and     ecx, 3FFh
0x1800542da  shl     eax, 0Ah
0x1800542dd  or      ecx, eax
0x1800542df  shl     ecx, 0Ch
0x1800542e2  bts     ecx, 0Bh
0x1800542e6  or      [rsp+1A10h+var_19C8+4], ecx
0x1800542ea  jmp     loc_18005437B
0x1800542ef  mov     edx, [rsp+1A10h+var_19CC]
0x1800542f3  mov     r8d, [rsp+1A10h+var_19D0]
0x1800542f8  mov     dword ptr [rsp+1A10h+var_19E0], r8d
0x1800542fd  lea     r9, [rbp+1910h+Source]
0x180054301  mov     [rsp+1A10h+var_19E8], edx
0x180054305  lea     r8, aUpdatel2profil; "UpdateL2Profile abnormal MCC/MNC (%s) L"...
0x18005430c  xor     edx, edx; struct _GUID *
0x18005430e  mov     dword ptr [rsp+1A10h+var_19F0], ebx
0x180054312  lea     rcx, aCwwancontextli_22; "CWwanContextLifeCycle::UpdateL2Profile"
0x180054319  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18005431e  jmp     short loc_18005437B
0x180054320  lea     r8, [rsp+1A10h+var_19D0]
0x180054325  mov     [rsp+1A10h+var_19D0], 0
0x18005432d  lea     rdx, a5d; "%5d"
0x180054334  lea     rcx, [rbp+1910h+Source]; Buffer
0x180054338  call    swscanf_s
0x18005433d  cmp     eax, 1
0x180054340  jnz     short loc_18005434F
0x180054342  mov     eax, [rsp+1A10h+var_19D0]
0x180054346  shl     eax, 0Ch
0x180054349  or      [rsp+1A10h+var_19C8+4], eax
0x18005434d  jmp     short loc_18005437B
0x18005434f  mov     edx, 7; MaxCount
0x180054354  lea     rcx, [rbp+1910h+Source]; Source
0x180054358  call    cs:__imp_wcsnlen
0x18005435e  lea     r9, [rbp+1910h+Source]
0x180054362  xor     edx, edx; struct _GUID *
0x180054364  lea     r8, aAbnormalSidSLe; "abnormal Sid (%s) Len %d"
0x18005436b  mov     dword ptr [rsp+1A10h+var_19F0], eax
0x18005436f  lea     rcx, aCwwancontextli_22; "CWwanContextLifeCycle::UpdateL2Profile"
0x180054376  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18005437b  test    edi, edi
0x18005437d  jz      short loc_1800543A3
0x18005437f  mov     [rsp+1A10h+var_19E8], r14d
0x180054384  lea     r9, [rbp+1910h+var_18E0]
0x180054388  lea     r8, aGetProfileInfo; "get profile information failed, profile"...
0x18005438f  mov     dword ptr [rsp+1A10h+var_19F0], edi
0x180054393  lea     rdx, [rbp+1910h+var_1930]; struct _GUID *
0x180054397  lea     rcx, aCwwancontextli_22; "CWwanContextLifeCycle::UpdateL2Profile"
0x18005439e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800543a3  mov     r9d, [rsp+1A10h+var_19C8]
0x1800543a8  lea     r8, aSetProfileInde; "set profile index, profile index %x"
0x1800543af  lea     rdx, [rbp+1910h+var_1930]; struct _GUID *
0x1800543b3  mov     [rbp+1910h+var_1988], 0
0x1800543bb  lea     rcx, aCwwancontextli_15; "CWwanContextLifeCycle::SetProfileIndex"
0x1800543c2  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800543c7  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x1800543cc  lea     rax, [rsp+1A10h+var_19C8]
0x1800543d1  mov     qword ptr [rsp+1A10h+var_19A8], 0
0x1800543da  mov     qword ptr [rsp+1A10h+var_19A8+8], 0
0x1800543e3  lea     r9, [rbp+1910h+var_1980]
0x1800543e7  movups  xmm0, [rsp+1A10h+var_19A8]
0x1800543ec  mov     qword ptr [rsp+1A10h+var_1998], 1
0x1800543f5  lea     rcx, [rbp+1910h+var_1930]
0x1800543f9  mov     qword ptr [rbp+1910h+var_1998+8], 0
0x180054401  movups  xmm1, [rsp+1A10h+var_1998]
0x180054406  mov     qword ptr [rsp+1A10h+var_19E8], rax
0x18005440b  movaps  [rbp+1910h+var_1980], xmm0
0x18005440f  movsd   xmm0, [rbp+1910h+var_1988]
0x180054414  movsd   qword ptr [rbp+1910h+var_1960], xmm0
0x180054419  movaps  [rbp+1910h+var_1970], xmm1
0x18005441d  call    ?WwanTxmSendReqSyncNoQueue@@YAKPEAU_GUID@@W4WWAN_EVENT_CODE@@W4WWAN_SETQUERY_TYPE@@UWWAN_API_INFO@@KPEBX@Z; WwanTxmSendReqSyncNoQueue(_GUID *,WWAN_EVENT_CODE,WWAN_SETQUERY_TYPE,WWAN_API_INFO,ulong,void const *)
0x180054422  mov     ebx, eax
0x180054424  test    eax, eax
0x180054426  jz      short loc_180054442
0x180054428  mov     r9d, eax
0x18005442b  lea     r8, aWwantxmsendreq_1; "WwanTxmSendReq failed, dwError (%u)"
0x180054432  xor     edx, edx; struct _GUID *
0x180054434  lea     rcx, aCwwancontextli_15; "CWwanContextLifeCycle::SetProfileIndex"
0x18005443b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180054440  jmp     short loc_180054444
0x180054442  xor     ebx, ebx
0x180054444  mov     eax, ebx
0x180054446  mov     rcx, [rbp+1910h+var_30]
0x18005444d  xor     rcx, rsp; StackCookie
0x180054450  call    __security_check_cookie
0x180054455  lea     r11, [rsp+1A10h+var_10]
0x18005445d  mov     rbx, [r11+30h]
0x180054461  mov     rsi, [r11+38h]
0x180054465  movaps  xmm6, xmmword ptr [r11-10h]
0x18005446a  mov     rsp, r11
0x18005446d  pop     r14
0x18005446f  pop     rdi
0x180054470  pop     rbp
0x180054471  retn
```
