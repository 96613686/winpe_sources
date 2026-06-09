# IsFolderInSyncRoot(ushort const *,bool &,ushort * *)

- ea: `0x180019edc`
- end: `0x18001a2c1`
- name: `?IsFolderInSyncRoot@@YAJPEBGAEA_NPEAPEAG@Z`
- size: `997`
- prototype: `void __fastcall __noreturn(wchar_t *Str, bool *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017dec`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180013ae4`
- `0x1800152d4`
- `0x180019edc`
- `0x18001ebf4`
- `0x18001f66c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a244`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a244`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a1fc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a1fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019f45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019f45`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001a1d9`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001a1d9`

## pseudocode

```c
void __fastcall __noreturn IsFolderInSyncRoot(wchar_t *Str, bool *a2, unsigned __int16 **a3)
{
  HRESULT v6; // eax
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, GUID *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  unsigned int i; // r14d
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, __int64 *); // rbx
  LPVOID v19; // rdi
  int (__fastcall *v20)(LPVOID, __int64, _QWORD, wchar_t **); // rbx
  int SyncRootInfoByPath; // eax
  int v22; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v28; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *SubStr; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v36[3]; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+A8h] [rbp-58h]
  _BYTE v38[512]; // [rsp+ACh] [rbp-54h] BYREF
  _BYTE v39[512]; // [rsp+2ACh] [rbp+1ACh] BYREF
  int v40; // [rsp+4ACh] [rbp+3ACh]
  char v41; // [rsp+4B0h] [rbp+3B0h]
  int v42; // [rsp+4B1h] [rbp+3B1h]
  __int16 v43; // [rsp+4B5h] [rbp+3B5h]
  char v44; // [rsp+4B7h] [rbp+3B7h]
  _BYTE v45[528]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+618h]

  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v28);
  v6 = CoCreateInstance(
         &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
         0,
         1u,
         &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
         &v28);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9FD,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_24;
  }
  v25 = 0;
  v7 = v28;
  v8 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v28;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v9 = v8(v7, &GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad, &v25);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA00,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    goto LABEL_24;
  }
  v24 = 0;
  v10 = v25;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  v12 = v11(v10, &v24);
  if ( v12 < 0 )
  {
    v13 = 2563;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    goto LABEL_5;
  }
  v26 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v26);
  if ( v12 < 0 )
  {
    v13 = 2566;
    goto LABEL_8;
  }
  memset_0(v45, 0, 0x208u);
  *a3 = (unsigned __int16 *)v45;
  for ( i = 0; i < v26; ++i )
  {
    v27 = 0;
    v15 = v24;
    v16 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v24 + 32LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    if ( v16(v15, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v27) >= 0 )
    {
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v17 = v27;
      v18 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
      v33 = -1;
      v34 = -1;
      if ( v18(v17, &v32) >= 0 )
      {
        SubStr = 0;
        v30 = 0;
        v31 = 0;
        v19 = v28;
        v20 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, wchar_t **))(*(_QWORD *)v28 + 136LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&SubStr);
        v30 = -1;
        v31 = -1;
        if ( v20(v19, v32, 0, &SubStr) >= 0 )
        {
          memset(v36, 0, sizeof(v36));
          v37 = 0;
          memset_0(v38, 0, sizeof(v38));
          memset_0(v39, 0, sizeof(v39));
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
          v44 = 0;
          v35 = 0;
          SyncRootInfoByPath = CfGetSyncRootInfoByPath(SubStr, 1, v36, 1064, &v35);
          if ( (int)(SyncRootInfoByPath + 0x80000000) < 0 || SyncRootInfoByPath == -2147024662 )
          {
            if ( wcsstr(Str, SubStr) )
            {
              *a2 = 1;
              v22 = _o_wcscpy_s(v45, 260, v38);
              HrFromErrno(v22);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&SubStr);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
              break;
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&SubStr);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v28);
}

```

## disassembly

```asm
0x180019edc  mov     [rsp-8+arg_18], rbx
0x180019ee1  push    rbp
0x180019ee2  push    rsi
0x180019ee3  push    rdi
0x180019ee4  push    r12
0x180019ee6  push    r13
0x180019ee8  push    r14
0x180019eea  push    r15
0x180019eec  lea     rbp, [rsp-5E0h]
0x180019ef4  sub     rsp, 6E0h
0x180019efb  mov     rax, cs:__security_cookie
0x180019f02  xor     rax, rsp
0x180019f05  mov     [rbp+610h+var_40], rax
0x180019f0c  mov     r14, r8
0x180019f0f  mov     r12, rdx
0x180019f12  mov     r15, rcx
0x180019f15  xor     r13d, r13d
0x180019f18  mov     [rsp+710h+var_6C0], r13
0x180019f1d  lea     rcx, [rsp+710h+var_6C0]
0x180019f22  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180019f27  lea     rax, [rsp+710h+var_6C0]
0x180019f2c  mov     qword ptr [rsp+710h+ppv], rax; int
0x180019f31  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180019f38  xor     edx, edx; pUnkOuter
0x180019f3a  lea     r8d, [r13+1]; dwClsContext
0x180019f3e  lea     rcx, _GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe; rclsid
0x180019f45  call    cs:__imp_CoCreateInstance
0x180019f4b  mov     ebx, eax
0x180019f4d  test    eax, eax
0x180019f4f  jns     short loc_180019F71
0x180019f51  mov     rcx, [rbp+618h]; this
0x180019f58  mov     r9d, eax; char *
0x180019f5b  lea     r8, aOnecoreDrivers
0x180019f62  mov     edx, 9FDh; void *
0x180019f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180019f6c  jmp     loc_18001A28B
0x180019f71  mov     [rsp+710h+var_6D8], r13
0x180019f76  mov     rdi, [rsp+710h+var_6C0]
0x180019f7b  mov     rax, [rdi]
0x180019f7e  mov     rbx, [rax]
0x180019f81  lea     rcx, [rsp+710h+var_6D8]
0x180019f86  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180019f8b  lea     r8, [rsp+710h+var_6D8]
0x180019f90  lea     rdx, _GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad
0x180019f97  mov     rcx, rdi
0x180019f9a  mov     rax, rbx
0x180019f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa2  mov     ebx, eax
0x180019fa4  test    eax, eax
0x180019fa6  jns     short loc_180019FD3
0x180019fa8  mov     rcx, [rbp+618h]; this
0x180019faf  mov     r9d, eax; char *
0x180019fb2  lea     r8, aOnecoreDrivers
0x180019fb9  mov     edx, 0A00h; void *
0x180019fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180019fc3  nop
0x180019fc4  lea     rcx, [rsp+710h+var_6D8]
0x180019fc9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180019fce  jmp     loc_18001A28B
0x180019fd3  mov     [rsp+710h+var_6E0], r13
0x180019fd8  mov     rdi, [rsp+710h+var_6D8]
0x180019fdd  mov     rax, [rdi]
0x180019fe0  mov     rbx, [rax+18h]
0x180019fe4  lea     rcx, [rsp+710h+var_6E0]
0x180019fe9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180019fee  lea     rdx, [rsp+710h+var_6E0]
0x180019ff3  mov     rcx, rdi
0x180019ff6  mov     rax, rbx
0x180019ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ffe  mov     ebx, eax
0x18001a000  test    eax, eax
0x18001a002  jns     short loc_18001A02C
0x18001a004  mov     edx, 0A03h; void *
0x18001a009  lea     r8, aOnecoreDrivers
0x18001a010  mov     r9d, eax; char *
0x18001a013  mov     rcx, [rbp+618h]; this
0x18001a01a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001a01f  nop
0x18001a020  lea     rcx, [rsp+710h+var_6E0]
0x18001a025  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a02a  jmp     short loc_180019FC4
0x18001a02c  mov     [rsp+710h+var_6D0], r13d
0x18001a031  mov     rcx, [rsp+710h+var_6E0]
0x18001a036  mov     rax, [rcx]
0x18001a039  lea     rdx, [rsp+710h+var_6D0]
0x18001a03e  mov     rax, [rax+18h]
0x18001a042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a047  mov     ebx, eax
0x18001a049  test    eax, eax
0x18001a04b  jns     short loc_18001A054
0x18001a04d  mov     edx, 0A06h
0x18001a052  jmp     short loc_18001A009
0x18001a054  mov     esi, r13d
0x18001a057  xor     edx, edx; Val
0x18001a059  mov     r8d, 208h; Size
0x18001a05f  lea     rcx, [rbp+610h+var_250]; void *
0x18001a066  call    memset_0
0x18001a06b  lea     rax, [rbp+610h+var_250]
0x18001a072  mov     [r14], rax
0x18001a075  mov     r14d, r13d
0x18001a078  cmp     r14d, [rsp+710h+var_6D0]
0x18001a07d  jnb     loc_18001A274
0x18001a083  mov     esi, r13d
0x18001a086  mov     [rsp+710h+var_6C8], r13
0x18001a08b  mov     rdi, [rsp+710h+var_6E0]
0x18001a090  mov     rax, [rdi]
0x18001a093  mov     rbx, [rax+20h]
0x18001a097  lea     rcx, [rsp+710h+var_6C8]
0x18001a09c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a0a1  lea     r9, [rsp+710h+var_6C8]
0x18001a0a6  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x18001a0ad  mov     edx, r14d
0x18001a0b0  mov     rcx, rdi
0x18001a0b3  mov     rax, rbx
0x18001a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0bb  test    eax, eax
0x18001a0bd  js      loc_18001A21D
0x18001a0c3  mov     [rsp+710h+var_6A0], r13
0x18001a0c8  mov     [rsp+710h+var_698], r13
0x18001a0cd  mov     [rbp+610h+var_690], r13
0x18001a0d1  mov     rdi, [rsp+710h+var_6C8]
0x18001a0d6  mov     rax, [rdi]
0x18001a0d9  mov     rbx, [rax+18h]
0x18001a0dd  lea     rcx, [rsp+710h+var_6A0]
0x18001a0e2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a0e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a0eb  mov     [rsp+710h+var_698], rax
0x18001a0f0  mov     [rbp+610h+var_690], rax
0x18001a0f4  lea     rdx, [rsp+710h+var_6A0]
0x18001a0f9  mov     rcx, rdi
0x18001a0fc  mov     rax, rbx
0x18001a0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a104  test    eax, eax
0x18001a106  js      loc_18001A212
0x18001a10c  mov     [rsp+710h+SubStr], r13
0x18001a111  mov     [rsp+710h+var_6B0], r13
0x18001a116  mov     [rsp+710h+var_6A8], r13
0x18001a11b  mov     rdi, [rsp+710h+var_6C0]
0x18001a120  mov     rax, [rdi]
0x18001a123  mov     rbx, [rax+88h]
0x18001a12a  lea     rcx, [rsp+710h+SubStr]
0x18001a12f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a134  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a138  mov     [rsp+710h+var_6B0], rax
0x18001a13d  mov     [rsp+710h+var_6A8], rax
0x18001a142  lea     r9, [rsp+710h+SubStr]
0x18001a147  xor     r8d, r8d
0x18001a14a  mov     rdx, [rsp+710h+var_6A0]
0x18001a14f  mov     rcx, rdi
0x18001a152  mov     rax, rbx
0x18001a155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a15a  test    eax, eax
0x18001a15c  js      loc_18001A207
0x18001a162  mov     [rbp+610h+var_680], r13
0x18001a166  mov     [rbp+610h+var_678], r13
0x18001a16a  xor     eax, eax
0x18001a16c  mov     [rbp+610h+var_670], rax
0x18001a170  mov     [rbp+610h+var_668], eax
0x18001a173  mov     ebx, 200h
0x18001a178  mov     r8d, ebx; Size
0x18001a17b  xor     edx, edx; Val
0x18001a17d  lea     rcx, [rbp+610h+var_664]; void *
0x18001a181  call    memset_0
0x18001a186  mov     r8d, ebx; Size
0x18001a189  xor     edx, edx; Val
0x18001a18b  lea     rcx, [rbp+610h+var_464]; void *
0x18001a192  call    memset_0
0x18001a197  xor     eax, eax
0x18001a199  mov     [rbp+610h+var_264], eax
0x18001a19f  mov     [rbp+610h+var_260], al
0x18001a1a5  mov     [rbp+610h+var_25F], eax
0x18001a1ab  mov     [rbp+610h+var_25B], ax
0x18001a1b2  mov     [rbp+610h+var_259], al
0x18001a1b8  mov     [rbp+610h+var_688], r13d
0x18001a1bc  lea     rax, [rbp+610h+var_688]
0x18001a1c0  mov     qword ptr [rsp+710h+ppv], rax
0x18001a1c5  mov     r9d, 428h
0x18001a1cb  lea     r8, [rbp+610h+var_680]
0x18001a1cf  mov     edx, 1
0x18001a1d4  mov     rcx, [rsp+710h+SubStr]
0x18001a1d9  call    cs:__imp_CfGetSyncRootInfoByPath
0x18001a1df  mov     esi, eax
0x18001a1e1  mov     ebx, 80000000h
0x18001a1e6  lea     ecx, [rax+rbx]
0x18001a1e9  test    ebx, ecx
0x18001a1eb  jnz     short loc_18001A1F4
0x18001a1ed  cmp     eax, 800700EAh
0x18001a1f2  jnz     short loc_18001A207
0x18001a1f4  mov     rdx, [rsp+710h+SubStr]; SubStr
0x18001a1f9  mov     rcx, r15; Str
0x18001a1fc  call    cs:__imp_wcsstr
0x18001a202  test    rax, rax
0x18001a205  jnz     short loc_18001A22F
0x18001a207  lea     rcx, [rsp+710h+SubStr]
0x18001a20c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a211  nop
0x18001a212  lea     rcx, [rsp+710h+var_6A0]
0x18001a217  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a21c  nop
0x18001a21d  lea     rcx, [rsp+710h+var_6C8]
0x18001a222  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a227  inc     r14d
0x18001a22a  jmp     loc_18001A078
0x18001a22f  mov     byte ptr [r12], 1
0x18001a234  lea     r8, [rbp+610h+var_664]
0x18001a238  mov     edx, 104h
0x18001a23d  lea     rcx, [rbp+610h+var_250]
0x18001a244  call    cs:__imp__o_wcscpy_s
0x18001a24a  mov     ecx, eax; int
0x18001a24c  call    ?HrFromErrno@@YAJH@Z
0x18001a251  mov     esi, eax
0x18001a253  lea     rcx, [rsp+710h+SubStr]
0x18001a258  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a25d  nop
0x18001a25e  lea     rcx, [rsp+710h+var_6A0]
0x18001a263  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001a268  nop
0x18001a269  lea     rcx, [rsp+710h+var_6C8]
0x18001a26e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a273  nop
0x18001a274  lea     rcx, [rsp+710h+var_6E0]
0x18001a279  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a27e  nop
0x18001a27f  lea     rcx, [rsp+710h+var_6D8]
0x18001a284  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a289  mov     ebx, esi
0x18001a28b  lea     rcx, [rsp+710h+var_6C0]
0x18001a290  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001a295  mov     eax, ebx
0x18001a297  mov     rcx, [rbp+610h+var_40]
0x18001a29e  xor     rcx, rsp; StackCookie
0x18001a2a1  call    __security_check_cookie
0x18001a2a6  mov     rbx, [rsp+710h+arg_18]
0x18001a2ae  add     rsp, 6E0h
0x18001a2b5  pop     r15
0x18001a2b7  pop     r14
0x18001a2b9  pop     r13
0x18001a2bb  pop     r12
0x18001a2bd  pop     rdi
0x18001a2be  pop     rsi
0x18001a2bf  pop     rbp
0x18001a2c0  retn
```
