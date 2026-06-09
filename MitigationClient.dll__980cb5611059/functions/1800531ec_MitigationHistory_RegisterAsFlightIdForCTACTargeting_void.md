# MitigationHistory::RegisterAsFlightIdForCTACTargeting(void)

- ea: `0x1800531ec`
- end: `0x18005358b`
- name: `?RegisterAsFlightIdForCTACTargeting@MitigationHistory@@QEAAJXZ`
- size: `927`
- prototype: `__int64 __fastcall(MitigationHistory *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005298c`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x18002407c`
- `0x180029cc8`
- `0x18002a488`
- `0x18002e974`
- `0x1800531ec`
- `0x180053804`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005323d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005323d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MitigationHistory::RegisterAsFlightIdForCTACTargeting(MitigationHistory *this)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  LPVOID v8; // rdi
  int (__fastcall *v9)(LPVOID, __int64, __int64 *); // rbx
  unsigned int v10; // eax
  __int128 *i; // rbx
  int v12; // eax
  int v13; // edi
  LPVOID v14; // rsi
  int (__fastcall *v15)(LPVOID, unsigned __int16 *, __int64 *); // rdi
  int v16; // eax
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, const wchar_t *, __int64, _QWORD); // rbx
  LPVOID *ppv; // [rsp+20h] [rbp-49h]
  LPVOID v21[2]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v22; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h]
  __int64 v25; // [rsp+60h] [rbp-9h]
  unsigned __int16 *v26[11]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v28; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v30; // [rsp+E8h] [rbp+7Fh] BYREF

  v30 = 0;
  v21[0] = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
  Instance = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, v21);
  v3 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
      (const char *)(unsigned int)Instance,
      (int)ppv);
    goto LABEL_28;
  }
  v4 = *((_QWORD *)this + 3);
  *(_OWORD *)v26 = *(_OWORD *)(v4 - 48);
  *(_OWORD *)((char *)&v26[1] + 4) = *(_OWORD *)(v4 - 36);
  v5 = *(_DWORD *)(v4 - 20);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  LODWORD(v29) = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)((char *)&v26[1] + 4), 4));
  WORD2(v29) = _mm_extract_epi16(*(__m128i *)((char *)&v26[1] + 4), 4);
  v22 = *(_OWORD *)v26;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
  v24 = -1;
  v25 = -1;
  v6 = StringUtils::ConvertMitigationToFlightIdHash(&v22, &v29, v5, &v23);
  v3 = v6;
  if ( v6 < 0 )
  {
    v7 = 228;
    goto LABEL_5;
  }
  v8 = v21[0];
  v9 = *(int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v21[0] + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  if ( v9(v8, v23, &v30) >= 0 )
    goto LABEL_27;
  v28 = 0;
  v29 = -2147483646;
  if ( (int)MitigationRegUtils::GetMitigationRegDWORD(
              &v29,
              *((unsigned int *)this + 20),
              L"RegisteredFlightIdCount",
              &v28) >= 0 )
  {
    v10 = v28;
  }
  else
  {
    v10 = 0;
    v28 = 0;
  }
  if ( v10 == 20 )
  {
    for ( i = (__int128 *)*((_QWORD *)this + 2); i != *((__int128 **)this + 3); i += 3 )
    {
      memset(v26, 0, 24);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v26);
      v26[1] = (unsigned __int16 *)-1LL;
      v26[2] = (unsigned __int16 *)-1LL;
      LODWORD(v29) = *((_DWORD *)i + 4);
      WORD2(v29) = *((_WORD *)i + 10);
      v22 = *i;
      v12 = StringUtils::ConvertMitigationToFlightIdHash(&v22, &v29, *((unsigned int *)i + 7), v26);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
          (const char *)(unsigned int)v12,
          0);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v26);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
        v3 = v13;
        goto LABEL_28;
      }
      v14 = v21[0];
      v15 = *(int (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v21[0] + 136LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
      if ( v15(v14, v26[0], &v30) >= 0 )
      {
        v16 = MitigationHistory::UnregisterFlightId(this, v26[0]);
        v3 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x105,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
            (const char *)(unsigned int)v16,
            0);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v26);
          goto LABEL_6;
        }
        --v28;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v26);
        break;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v26);
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  v17 = v21[0];
  v18 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v21[0] + 88LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  ppv = (LPVOID *)&v30;
  v6 = v18(v17, L"TroubleShooting", v23, 0);
  v3 = v6;
  if ( v6 < 0 )
  {
    v7 = 269;
    goto LABEL_5;
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 88LL))(v30);
  v3 = v6;
  if ( v6 < 0 )
  {
    v7 = 270;
    goto LABEL_5;
  }
  ++v28;
  v29 = -2147483646;
  LODWORD(ppv) = 0;
  v6 = MitigationRegUtils::SetMitigationRegDWORD(&v29, *((unsigned int *)this + 20), L"RegisteredFlightIdCount", v28);
  v3 = v6;
  if ( v6 >= 0 )
  {
LABEL_27:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
    v3 = 0;
    goto LABEL_28;
  }
  v7 = 274;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
    (const char *)(unsigned int)v6,
    (int)ppv);
LABEL_6:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  return v3;
}

```

## disassembly

```asm
0x1800531ec  mov     [rsp-8+arg_0], rbx
0x1800531f1  push    rbp
0x1800531f2  push    rsi
0x1800531f3  push    rdi
0x1800531f4  push    r13
0x1800531f6  push    r14
0x1800531f8  lea     rbp, [rsp-37h]
0x1800531fd  sub     rsp, 0A0h
0x180053204  mov     r14, rcx
0x180053207  mov     [rbp+57h+arg_18], 0
0x18005320f  mov     [rbp+57h+var_90], 0
0x180053217  lea     rcx, [rbp+57h+var_90]
0x18005321b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053220  lea     rax, [rbp+57h+var_90]
0x180053224  mov     [rsp+0C0h+ppv], rax; int
0x180053229  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180053230  xor     edx, edx; pUnkOuter
0x180053232  lea     r8d, [rdx+1]; dwClsContext
0x180053236  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18005323d  call    cs:__imp_CoCreateInstance
0x180053243  mov     ebx, eax
0x180053245  test    eax, eax
0x180053247  jns     short loc_180053266
0x180053249  mov     rcx, [rbp+5Fh]; this
0x18005324d  mov     r9d, eax; char *
0x180053250  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053257  mov     edx, 0DFh; void *
0x18005325c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053261  jmp     loc_18005355F
0x180053266  mov     rax, [r14+18h]
0x18005326a  movups  xmm0, xmmword ptr [rax-30h]
0x18005326e  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180053272  movups  xmm1, xmmword ptr [rax-24h]
0x180053276  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm1
0x18005327a  mov     ebx, [rax-14h]
0x18005327d  mov     [rbp+57h+var_70], 0
0x180053285  mov     [rbp+57h+var_68], 0
0x18005328d  mov     [rbp+57h+var_60], 0
0x180053295  movdqa  xmm0, xmm1
0x180053299  psrldq  xmm0, 4
0x18005329e  movd    dword ptr [rbp+57h+arg_10], xmm0
0x1800532a3  pextrw  eax, xmm1, 4
0x1800532a8  mov     word ptr [rbp+57h+arg_10+4], ax
0x1800532ac  movups  xmm0, xmmword ptr [rbp+57h+var_58]
0x1800532b0  movdqu  [rbp+57h+var_80], xmm0
0x1800532b5  lea     rcx, [rbp+57h+var_70]
0x1800532b9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800532be  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800532c2  mov     [rbp+57h+var_68], r13
0x1800532c6  mov     [rbp+57h+var_60], r13
0x1800532ca  lea     r9, [rbp+57h+var_70]
0x1800532ce  mov     r8d, ebx
0x1800532d1  lea     rdx, [rbp+57h+arg_10]
0x1800532d5  lea     rcx, [rbp+57h+var_80]
0x1800532d9  call    ?ConvertMitigationToFlightIdHash@StringUtils@@SAJU_GUID@@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0001@@KPEAPEAG@Z; StringUtils::ConvertMitigationToFlightIdHash(_GUID,__MIDL___MIDL_itf_mitigationclient_0000_0002_0001,ulong,ushort * *)
0x1800532de  mov     ebx, eax
0x1800532e0  test    eax, eax
0x1800532e2  jns     short loc_18005330B
0x1800532e4  mov     edx, 0E4h; void *
0x1800532e9  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800532f0  mov     r9d, eax; char *
0x1800532f3  mov     rcx, [rbp+5Fh]; this
0x1800532f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532fc  nop
0x1800532fd  lea     rcx, [rbp+57h+var_70]
0x180053301  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053306  jmp     loc_18005355F
0x18005330b  mov     rdi, [rbp+57h+var_90]
0x18005330f  mov     rax, [rdi]
0x180053312  mov     rbx, [rax+88h]
0x180053319  lea     rcx, [rbp+57h+arg_18]
0x18005331d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053322  lea     r8, [rbp+57h+arg_18]
0x180053326  mov     rdx, [rbp+57h+var_70]
0x18005332a  mov     rcx, rdi
0x18005332d  mov     rax, rbx
0x180053330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053335  test    eax, eax
0x180053337  jns     loc_180053554
0x18005333d  mov     [rbp+57h+arg_8], 0
0x180053344  mov     [rbp+57h+arg_10], 0FFFFFFFF80000002h
0x18005334c  mov     [rsp+0C0h+ppv], 0; int
0x180053355  lea     r9, [rbp+57h+arg_8]
0x180053359  lea     r8, aRegisteredflig; "RegisteredFlightIdCount"
0x180053360  mov     edx, [r14+50h]
0x180053364  lea     rcx, [rbp+57h+arg_10]
0x180053368  call    ?GetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAK2@Z; MitigationRegUtils::GetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong *,ushort const *)
0x18005336d  test    eax, eax
0x18005336f  jns     short loc_180053378
0x180053371  xor     eax, eax
0x180053373  mov     [rbp+57h+arg_8], eax
0x180053376  jmp     short loc_18005337B
0x180053378  mov     eax, [rbp+57h+arg_8]
0x18005337b  cmp     eax, 14h
0x18005337e  jnz     loc_180053475
0x180053384  mov     rbx, [r14+10h]
0x180053388  cmp     rbx, [r14+18h]
0x18005338c  jz      loc_180053475
0x180053392  mov     [rbp+57h+var_58], 0
0x18005339a  mov     [rbp+57h+var_58+8], 0
0x1800533a2  mov     [rbp+57h+var_48], 0
0x1800533aa  lea     rcx, [rbp+57h+var_58]
0x1800533ae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800533b3  mov     [rbp+57h+var_58+8], r13
0x1800533b7  mov     [rbp+57h+var_48], r13
0x1800533bb  mov     eax, [rbx+10h]
0x1800533be  mov     dword ptr [rbp+57h+arg_10], eax
0x1800533c1  movzx   eax, word ptr [rbx+14h]
0x1800533c5  mov     word ptr [rbp+57h+arg_10+4], ax
0x1800533c9  movups  xmm0, xmmword ptr [rbx]
0x1800533cc  movdqu  [rbp+57h+var_80], xmm0
0x1800533d1  lea     r9, [rbp+57h+var_58]
0x1800533d5  mov     r8d, [rbx+1Ch]
0x1800533d9  lea     rdx, [rbp+57h+arg_10]
0x1800533dd  lea     rcx, [rbp+57h+var_80]
0x1800533e1  call    ?ConvertMitigationToFlightIdHash@StringUtils@@SAJU_GUID@@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0001@@KPEAPEAG@Z; StringUtils::ConvertMitigationToFlightIdHash(_GUID,__MIDL___MIDL_itf_mitigationclient_0000_0002_0001,ulong,ushort * *)
0x1800533e6  mov     edi, eax
0x1800533e8  test    eax, eax
0x1800533ea  js      loc_1800534C4
0x1800533f0  mov     rsi, [rbp+57h+var_90]
0x1800533f4  mov     rax, [rsi]
0x1800533f7  mov     rdi, [rax+88h]
0x1800533fe  lea     rcx, [rbp+57h+arg_18]
0x180053402  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053407  lea     r8, [rbp+57h+arg_18]
0x18005340b  mov     rdx, [rbp+57h+var_58]
0x18005340f  mov     rcx, rsi
0x180053412  mov     rax, rdi
0x180053415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005341a  test    eax, eax
0x18005341c  jns     short loc_180053430
0x18005341e  lea     rcx, [rbp+57h+var_58]
0x180053422  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053427  add     rbx, 30h ; '0'
0x18005342b  jmp     loc_180053388
0x180053430  mov     rdx, [rbp+57h+var_58]; unsigned __int16 *
0x180053434  mov     rcx, r14; this
0x180053437  call    ?UnregisterFlightId@MitigationHistory@@AEAAJPEBG@Z; MitigationHistory::UnregisterFlightId(ushort const *)
0x18005343c  mov     ebx, eax
0x18005343e  test    eax, eax
0x180053440  jns     short loc_180053469
0x180053442  mov     rcx, [rbp+5Fh]; this
0x180053446  mov     r9d, eax; char *
0x180053449  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053450  mov     edx, 105h; void *
0x180053455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005345a  nop
0x18005345b  lea     rcx, [rbp+57h+var_58]
0x18005345f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053464  jmp     loc_1800532FD
0x180053469  dec     [rbp+57h+arg_8]
0x18005346c  lea     rcx, [rbp+57h+var_58]
0x180053470  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053475  lea     rcx, [rbp+57h+arg_18]
0x180053479  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005347e  mov     rdi, [rbp+57h+var_90]
0x180053482  mov     rax, [rdi]
0x180053485  mov     rbx, [rax+58h]
0x180053489  lea     rcx, [rbp+57h+arg_18]
0x18005348d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053492  lea     rax, [rbp+57h+arg_18]
0x180053496  mov     [rsp+0C0h+ppv], rax
0x18005349b  xor     r9d, r9d
0x18005349e  mov     r8, [rbp+57h+var_70]
0x1800534a2  lea     rdx, aTroubleshootin; "TroubleShooting"
0x1800534a9  mov     rcx, rdi
0x1800534ac  mov     rax, rbx
0x1800534af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534b4  mov     ebx, eax
0x1800534b6  test    eax, eax
0x1800534b8  jns     short loc_1800534F4
0x1800534ba  mov     edx, 10Dh
0x1800534bf  jmp     loc_1800532E9
0x1800534c4  mov     rcx, [rbp+5Fh]; this
0x1800534c8  mov     r9d, edi; char *
0x1800534cb  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800534d2  mov     edx, 0FFh; void *
0x1800534d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800534dc  nop
0x1800534dd  lea     rcx, [rbp+57h+var_58]
0x1800534e1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800534e6  nop
0x1800534e7  lea     rcx, [rbp+57h+var_70]
0x1800534eb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800534f0  mov     ebx, edi
0x1800534f2  jmp     short loc_18005355F
0x1800534f4  mov     rcx, [rbp+57h+arg_18]
0x1800534f8  mov     rax, [rcx]
0x1800534fb  mov     rax, [rax+58h]
0x1800534ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053504  mov     ebx, eax
0x180053506  test    eax, eax
0x180053508  jns     short loc_180053514
0x18005350a  mov     edx, 10Eh
0x18005350f  jmp     loc_1800532E9
0x180053514  mov     r9d, [rbp+57h+arg_8]
0x180053518  inc     r9d
0x18005351b  mov     [rbp+57h+arg_8], r9d
0x18005351f  mov     [rbp+57h+arg_10], 0FFFFFFFF80000002h
0x180053527  mov     [rsp+0C0h+ppv], 0
0x180053530  lea     r8, aRegisteredflig; "RegisteredFlightIdCount"
0x180053537  mov     edx, [r14+50h]
0x18005353b  lea     rcx, [rbp+57h+arg_10]
0x18005353f  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180053544  mov     ebx, eax
0x180053546  test    eax, eax
0x180053548  jns     short loc_180053554
0x18005354a  mov     edx, 112h
0x18005354f  jmp     loc_1800532E9
0x180053554  lea     rcx, [rbp+57h+var_70]
0x180053558  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005355d  xor     ebx, ebx
0x18005355f  lea     rcx, [rbp+57h+var_90]
0x180053563  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053568  nop
0x180053569  lea     rcx, [rbp+57h+arg_18]
0x18005356d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053572  mov     eax, ebx
0x180053574  mov     rbx, [rsp+0C0h+arg_0]
0x18005357c  add     rsp, 0A0h
0x180053583  pop     r14
0x180053585  pop     r13
0x180053587  pop     rdi
0x180053588  pop     rsi
0x180053589  pop     rbp
0x18005358a  retn
```
