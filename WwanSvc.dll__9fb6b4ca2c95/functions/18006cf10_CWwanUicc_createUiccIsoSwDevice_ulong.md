# CWwanUicc::createUiccIsoSwDevice(ulong)

- ea: `0x18006cf10`
- end: `0x18006d30a`
- name: `?createUiccIsoSwDevice@CWwanUicc@@AEAAXK@Z`
- size: `1018`
- prototype: `void __fastcall(CWwanUicc *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180068eac`
- `0x18006e224`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x18000f138`
- `0x180012300`
- `0x180013288`
- `0x180014f1c`
- `0x180018abc`
- `0x1800674d8`
- `0x18006cf10`
- `0x180076810`
- `0x1800769a4`
- `0x18007a0fc`
- `0x1800b6ac0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d111`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d111`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18006d289`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18006d289`

## string_xrefs

- `0x18006cffc`: `MBB device instance id is not available to create child UiccIso device`
- `0x18006d003`: `CWwanUicc::createUiccIsoSwDevice`
- `0x18006d038`: `CWwanUicc::createUiccIsoSwDevice`
- `0x18006d17b`: `StringCchCopy failed with %d`
- `0x18006d298`: `SwDeviceCreate failed with %d`
- `0x18006d2b6`: `Created a UICC ISO Software Device with Handle: 0x%p, Slot Id: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWwanUicc::createUiccIsoSwDevice(CWwanUicc *this, int a2)
{
  CWwanManager *Instance; // rax
  struct CWwanNetworkInterface *v5; // rax
  const unsigned __int16 *v6; // rax
  struct CWwanManager *v7; // rax
  __int64 v8; // rax
  int v9; // esi
  int v10; // eax
  const unsigned __int16 *v11; // r8
  __int64 v12; // rbx
  __int64 v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+20h] [rbp-E0h]
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v22; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v26; // [rsp+C4h] [rbp-3Ch] BYREF
  int v27; // [rsp+D4h] [rbp-2Ch]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+E4h] [rbp-1Ch]
  char *v31; // [rsp+E8h] [rbp-18h]
  __int128 v32; // [rsp+F0h] [rbp-10h]
  int v33; // [rsp+100h] [rbp+0h]
  int v34; // [rsp+104h] [rbp+4h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  int v36; // [rsp+110h] [rbp+10h]
  int v37; // [rsp+114h] [rbp+14h]
  char *v38; // [rsp+118h] [rbp+18h]
  __int128 v39; // [rsp+120h] [rbp+20h]
  int v40; // [rsp+130h] [rbp+30h]
  int v41; // [rsp+134h] [rbp+34h]
  __int64 v42; // [rsp+138h] [rbp+38h]
  int v43; // [rsp+140h] [rbp+40h]
  int v44; // [rsp+144h] [rbp+44h]
  __int64 *v45; // [rsp+148h] [rbp+48h]
  OLECHAR sz[40]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v47[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v48[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v49[264]; // [rsp+5C0h] [rbp+4C0h] BYREF

  v17 = 0;
  memset_0(&v21, 0, 0x48u);
  v25 = 0;
  memset_0(&v26, 0, 0x8Cu);
  memset_0(v47, 0, 0x208u);
  memset_0(v48, 0, 0x208u);
  memset_0(v49, 0, 0x208u);
  HIDWORD(v15) = a2;
  LOBYTE(v15) = 0;
  Instance = CWwanManager::GetInstance();
  v5 = CWwanManager::SelectInterface(
         Instance,
         (const struct _GUID *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8),
         0);
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v5 + 128);
  StringCchCopyW(v47, 0x104u, v6);
  if ( !v47[0] )
  {
    WwanLog::Error(
      "CWwanUicc::createUiccIsoSwDevice",
      0,
      L"MBB device instance id is not available to create child UiccIso device");
    return;
  }
  v7 = CWwanManager::GetInstance();
  CWwanManager::GetExecutorFromInterfaceGuid(v7, &v19, (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8);
  v8 = *((_QWORD *)this + 1);
  if ( v19 )
  {
    v18 = 0;
    v16 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, char *, __int64 *, int *, _QWORD))(*(_QWORD *)v19 + 288LL))(
            v19,
            (char *)this + *(int *)(v8 + 4) + 8,
            &v18,
            &v16,
            0)
      && v18 )
    {
      v9 = 0;
      LOBYTE(v15) = -(*(_DWORD *)(v18 + 2276) != 0);
      WwanMemFree(v18);
      goto LABEL_10;
    }
    WwanLog::Error(
      "CWwanUicc::createUiccIsoSwDevice",
      (const struct _GUID *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8),
      L"Wwan interface object not found for given interface");
  }
  else
  {
    WwanLog::Error(
      "CWwanUicc::createUiccIsoSwDevice",
      (const struct _GUID *)((char *)this + *(int *)(v8 + 4) + 8),
      L"Executor not found for given interface");
  }
  v9 = -2147023728;
LABEL_10:
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( v9 >= 0 )
  {
    memset_0(sz, 0, 0x4Eu);
    if ( !StringFromGUID2((const GUID *const)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8), sz, 39) )
    {
      WwanLog::Error("CWwanUicc::createUiccIsoSwDevice", 0, L"Failed to convert interface GUID to string");
      return;
    }
    LODWORD(v13) = HIDWORD(v15);
    v10 = StringCchPrintfW(v48, 0x104u, L"%s_%d", sz, v13);
    if ( v10 < 0 )
    {
      v11 = L"StringCchPrintf failed with %d";
LABEL_21:
      WwanLog::Error("CWwanUicc::createUiccIsoSwDevice", 0, v11, (unsigned int)v10);
      return;
    }
    v10 = StringCchCopyW(v49, 0x104u, L"Root\\UiccIso");
    if ( v10 < 0 )
    {
      v11 = L"StringCchCopy failed with %d";
      goto LABEL_21;
    }
    v25 = 1105224178;
    v26 = xmmword_1801109D4;
    v27 = 0;
    v28 = 0;
    v29 = 13;
    v30 = 16;
    v31 = (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8;
    v32 = DEVPKEY_MbbDevice_SlotId;
    v33 = 2;
    v34 = 0;
    v35 = 0;
    v36 = 7;
    v37 = 4;
    v38 = (char *)&v15 + 4;
    v39 = DEVPKEY_MbbDevice_IsEmbedded;
    v40 = 3;
    v41 = 0;
    v42 = 0;
    v43 = 17;
    v44 = 1;
    v45 = &v15;
    v21 = 72;
    v24 = 8;
    v22 = v48;
    v23 = v49;
    v10 = SwDeviceCreate(L"UICCISO", v47, &v21, 3, &v25, CWwanUicc::_SwDeviceCreateCallback, 0, &v17, v15);
    if ( v10 < 0 )
    {
      v11 = L"SwDeviceCreate failed with %d";
      goto LABEL_21;
    }
    LODWORD(v14) = HIDWORD(v15);
    WwanLog::Info(
      "CWwanUicc::createUiccIsoSwDevice",
      0,
      L"Created a UICC ISO Software Device with Handle: 0x%p, Slot Id: %d",
      v17,
      v14);
    v12 = v17;
    *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,void *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,void *>>,0>>::_Try_emplace<unsigned long const &,>(
                             (char *)this + 864,
                             &v19,
                             (char *)&v15 + 4)
              + 24LL) = v12;
  }
}

```

## disassembly

```asm
0x18006cf10  mov     [rsp-8+arg_10], rbx
0x18006cf15  push    rbp
0x18006cf16  push    rsi
0x18006cf17  push    rdi
0x18006cf18  push    r14
0x18006cf1a  push    r15
0x18006cf1c  lea     rbp, [rsp-6E0h]
0x18006cf24  sub     rsp, 7E0h
0x18006cf2b  mov     rax, cs:__security_cookie
0x18006cf32  xor     rax, rsp
0x18006cf35  mov     [rbp+700h+var_30], rax
0x18006cf3c  mov     ebx, edx
0x18006cf3e  mov     rdi, rcx
0x18006cf41  xor     r14d, r14d
0x18006cf44  mov     [rsp+800h+var_7B0], r14
0x18006cf49  xor     edx, edx; Val
0x18006cf4b  lea     r8d, [r14+48h]; Size
0x18006cf4f  lea     rcx, [rsp+800h+var_790]; void *
0x18006cf54  call    memset_0
0x18006cf59  mov     [rbp+700h+var_740], r14d
0x18006cf5d  xor     edx, edx; Val
0x18006cf5f  mov     r8d, 8Ch; Size
0x18006cf65  lea     rcx, [rbp+700h+var_73C]; void *
0x18006cf69  call    memset_0
0x18006cf6e  mov     esi, 208h
0x18006cf73  mov     r8d, esi; Size
0x18006cf76  xor     edx, edx; Val
0x18006cf78  lea     rcx, [rbp+700h+var_660]; void *
0x18006cf7f  call    memset_0
0x18006cf84  mov     r8d, esi; Size
0x18006cf87  xor     edx, edx; Val
0x18006cf89  lea     rcx, [rbp+700h+var_450]; void *
0x18006cf90  call    memset_0
0x18006cf95  mov     r8d, esi; Size
0x18006cf98  xor     edx, edx; Val
0x18006cf9a  lea     rcx, [rbp+700h+var_240]; void *
0x18006cfa1  call    memset_0
0x18006cfa6  mov     [rsp+800h+var_7BC], ebx
0x18006cfaa  mov     [rsp+800h+var_7C0], r14b
0x18006cfaf  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x18006cfb4  mov     rcx, [rdi+8]
0x18006cfb8  movsxd  rdx, dword ptr [rcx+4]
0x18006cfbc  add     rdx, 8
0x18006cfc0  add     rdx, rdi; struct _GUID *
0x18006cfc3  xor     r8d, r8d; int
0x18006cfc6  mov     rcx, rax; this
0x18006cfc9  call    ?SelectInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@H@Z; CWwanManager::SelectInterface(_GUID const *,int)
0x18006cfce  lea     rcx, [rax+80h]
0x18006cfd5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006cfda  mov     r8, rax; unsigned __int16 *
0x18006cfdd  mov     r15d, 104h
0x18006cfe3  mov     edx, r15d; unsigned __int64
0x18006cfe6  lea     rcx, [rbp+700h+var_660]; unsigned __int16 *
0x18006cfed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006cff2  cmp     r14w, [rbp+700h+var_660]
0x18006cffa  jnz     short loc_18006D016
0x18006cffc  lea     r8, aMbbDeviceInsta; "MBB device instance id is not available"...
0x18006d003  lea     rcx, aCwwanuiccCreat; "CWwanUicc::createUiccIsoSwDevice"
0x18006d00a  xor     edx, edx; struct _GUID *
0x18006d00c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18006d011  jmp     loc_18006D2E4
0x18006d016  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x18006d01b  mov     rcx, [rdi+8]
0x18006d01f  movsxd  r8, dword ptr [rcx+4]
0x18006d023  add     r8, 8
0x18006d027  add     r8, rdi
0x18006d02a  lea     rdx, [rsp+800h+var_7A0]
0x18006d02f  mov     rcx, rax
0x18006d032  call    ?GetExecutorFromInterfaceGuid@CWwanManager@@QEAA?AV?$shared_ptr@VCWwanExecutor@@@std@@PEBU_GUID@@@Z; CWwanManager::GetExecutorFromInterfaceGuid(_GUID const *)
0x18006d037  nop
0x18006d038  lea     rbx, aCwwanuiccCreat; "CWwanUicc::createUiccIsoSwDevice"
0x18006d03f  mov     rcx, [rsp+800h+var_7A0]
0x18006d044  mov     rax, [rdi+8]
0x18006d048  test    rcx, rcx
0x18006d04b  jnz     short loc_18006D056
0x18006d04d  lea     r8, aExecutorNotFou_0; "Executor not found for given interface"
0x18006d054  jmp     short loc_18006D0BA
0x18006d056  mov     [rsp+800h+var_7A8], r14
0x18006d05b  mov     [rsp+800h+var_7B8], r14d
0x18006d060  mov     r8, [rcx]
0x18006d063  movsxd  rdx, dword ptr [rax+4]
0x18006d067  add     rdx, 8
0x18006d06b  add     rdx, rdi
0x18006d06e  mov     rax, [r8+120h]
0x18006d075  mov     [rsp+800h+var_7E0], r14
0x18006d07a  lea     r9, [rsp+800h+var_7B8]
0x18006d07f  lea     r8, [rsp+800h+var_7A8]
0x18006d084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d089  test    eax, eax
0x18006d08b  jnz     short loc_18006D0AF
0x18006d08d  mov     rcx, [rsp+800h+var_7A8]
0x18006d092  test    rcx, rcx
0x18006d095  jz      short loc_18006D0AF
0x18006d097  mov     esi, r14d
0x18006d09a  mov     eax, [rcx+8E4h]
0x18006d0a0  neg     eax
0x18006d0a2  sbb     dl, dl
0x18006d0a4  mov     [rsp+800h+var_7C0], dl
0x18006d0a8  call    WwanMemFree
0x18006d0ad  jmp     short loc_18006D0D2
0x18006d0af  mov     rax, [rdi+8]
0x18006d0b3  lea     r8, aWwanInterfaceO; "Wwan interface object not found for giv"...
0x18006d0ba  movsxd  rdx, dword ptr [rax+4]
0x18006d0be  add     rdx, 8
0x18006d0c2  add     rdx, rdi; struct _GUID *
0x18006d0c5  mov     rcx, rbx; char *
0x18006d0c8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18006d0cd  mov     esi, 80070490h
0x18006d0d2  mov     rcx, [rsp+800h+var_798]; this
0x18006d0d7  test    rcx, rcx
0x18006d0da  jz      short loc_18006D0E1
0x18006d0dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006d0e1  test    esi, esi
0x18006d0e3  js      loc_18006D2E4
0x18006d0e9  xor     edx, edx; Val
0x18006d0eb  lea     r8d, [rdx+4Eh]; Size
0x18006d0ef  lea     rcx, [rbp+700h+sz]; void *
0x18006d0f3  call    memset_0
0x18006d0f8  mov     rax, [rdi+8]
0x18006d0fc  movsxd  rcx, dword ptr [rax+4]
0x18006d100  add     rcx, 8
0x18006d104  add     rcx, rdi; rguid
0x18006d107  mov     r8d, 27h ; '''; cchMax
0x18006d10d  lea     rdx, [rbp+700h+sz]; lpsz
0x18006d111  call    cs:__imp_StringFromGUID2
0x18006d117  test    eax, eax
0x18006d119  jnz     short loc_18006D12A
0x18006d11b  lea     r8, aFailedToConver_1; "Failed to convert interface GUID to str"...
0x18006d122  mov     rcx, rbx
0x18006d125  jmp     loc_18006D00A
0x18006d12a  mov     eax, [rsp+800h+var_7BC]
0x18006d12e  mov     dword ptr [rsp+800h+var_7E0], eax
0x18006d132  lea     r9, [rbp+700h+sz]
0x18006d136  lea     r8, aSD; "%s_%d"
0x18006d13d  mov     rdx, r15; unsigned __int64
0x18006d140  lea     rcx, [rbp+700h+var_450]; unsigned __int16 *
0x18006d147  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d14c  test    eax, eax
0x18006d14e  jns     short loc_18006D161
0x18006d150  lea     r8, aStringcchprint_1; "StringCchPrintf failed with %d"
0x18006d157  xor     edx, edx
0x18006d159  mov     rcx, rbx
0x18006d15c  jmp     loc_18006D29F
0x18006d161  lea     r8, aRootUicciso; "Root\\UiccIso"
0x18006d168  mov     rdx, r15; unsigned __int64
0x18006d16b  lea     rcx, [rbp+700h+var_240]; unsigned __int16 *
0x18006d172  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006d177  test    eax, eax
0x18006d179  jns     short loc_18006D184
0x18006d17b  lea     r8, aStringcchcopyF_1; "StringCchCopy failed with %d"
0x18006d182  jmp     short loc_18006D157
0x18006d184  mov     [rbp+700h+var_740], 41E061F2h
0x18006d18b  movups  xmm0, cs:xmmword_1801109D4
0x18006d192  movdqu  [rbp+700h+var_73C], xmm0
0x18006d197  mov     [rbp+700h+var_72C], r14d
0x18006d19b  mov     [rbp+700h+var_728], r14
0x18006d19f  mov     [rbp+700h+var_720], 0Dh
0x18006d1a6  mov     [rbp+700h+var_71C], 10h
0x18006d1ad  mov     rax, [rdi+8]
0x18006d1b1  movsxd  rax, dword ptr [rax+4]
0x18006d1b5  add     rax, 8
0x18006d1b9  add     rax, rdi
0x18006d1bc  mov     [rbp+700h+var_718], rax
0x18006d1c0  movups  xmm0, cs:DEVPKEY_MbbDevice_SlotId
0x18006d1c7  movaps  [rbp+700h+var_710], xmm0
0x18006d1cb  mov     eax, cs:dword_1801109C8
0x18006d1d1  mov     [rbp+700h+var_700], eax
0x18006d1d4  mov     [rbp+700h+var_6FC], r14d
0x18006d1d8  mov     [rbp+700h+var_6F8], r14
0x18006d1dc  mov     [rbp+700h+var_6F0], 7
0x18006d1e3  mov     [rbp+700h+var_6EC], 4
0x18006d1ea  lea     rax, [rsp+800h+var_7BC]
0x18006d1ef  mov     [rbp+700h+var_6E8], rax
0x18006d1f3  movups  xmm0, cs:DEVPKEY_MbbDevice_IsEmbedded
0x18006d1fa  movaps  [rbp+700h+var_6E0], xmm0
0x18006d1fe  mov     eax, cs:dword_1801109B0
0x18006d204  mov     [rbp+700h+var_6D0], eax
0x18006d207  mov     [rbp+700h+var_6CC], r14d
0x18006d20b  mov     [rbp+700h+var_6C8], r14
0x18006d20f  mov     [rbp+700h+var_6C0], 11h
0x18006d216  mov     [rbp+700h+var_6BC], 1
0x18006d21d  lea     rax, [rsp+800h+var_7C0]
0x18006d222  mov     [rbp+700h+var_6B8], rax
0x18006d226  mov     [rsp+800h+var_790], 48h ; 'H'
0x18006d22e  mov     [rbp+700h+var_768], 8
0x18006d235  lea     rax, [rbp+700h+var_450]
0x18006d23c  mov     [rsp+800h+var_788], rax
0x18006d241  lea     rax, [rbp+700h+var_240]
0x18006d248  mov     [rbp+700h+var_780], rax
0x18006d24c  lea     rax, [rsp+800h+var_7B0]
0x18006d251  mov     [rsp+800h+var_7C8], rax
0x18006d256  mov     [rsp+800h+var_7D0], r14
0x18006d25b  lea     rax, ?_SwDeviceCreateCallback@CWwanUicc@@CAXPEAXJ0PEBG@Z; CWwanUicc::_SwDeviceCreateCallback(void *,long,void *,ushort const *)
0x18006d262  mov     [rsp+800h+var_7D8], rax
0x18006d267  lea     rax, [rbp+700h+var_740]
0x18006d26b  mov     [rsp+800h+var_7E0], rax
0x18006d270  mov     r9d, 3
0x18006d276  lea     r8, [rsp+800h+var_790]
0x18006d27b  lea     rdx, [rbp+700h+var_660]
0x18006d282  lea     rcx, aUicciso; "UICCISO"
0x18006d289  call    cs:__imp_SwDeviceCreate
0x18006d28f  xor     edx, edx; struct _GUID *
0x18006d291  mov     rcx, rbx; char *
0x18006d294  test    eax, eax
0x18006d296  jns     short loc_18006D2A9
0x18006d298  lea     r8, aSwdevicecreate; "SwDeviceCreate failed with %d"
0x18006d29f  mov     r9d, eax
0x18006d2a2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18006d2a7  jmp     short loc_18006D2E4
0x18006d2a9  mov     eax, [rsp+800h+var_7BC]
0x18006d2ad  mov     dword ptr [rsp+800h+var_7E0], eax
0x18006d2b1  mov     r9, [rsp+800h+var_7B0]
0x18006d2b6  lea     r8, aCreatedAUiccIs; "Created a UICC ISO Software Device with"...
0x18006d2bd  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18006d2c2  mov     rbx, [rsp+800h+var_7B0]
0x18006d2c7  lea     rcx, [rdi+360h]
0x18006d2ce  lea     r8, [rsp+800h+var_7BC]
0x18006d2d3  lea     rdx, [rsp+800h+var_7A0]
0x18006d2d8  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KPEAXV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKPEAX@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,void *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,void *>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18006d2dd  mov     rcx, [rax]
0x18006d2e0  mov     [rcx+18h], rbx
0x18006d2e4  mov     rcx, [rbp+700h+var_30]
0x18006d2eb  xor     rcx, rsp; StackCookie
0x18006d2ee  call    __security_check_cookie
0x18006d2f3  mov     rbx, [rsp+800h+arg_10]
0x18006d2fb  add     rsp, 7E0h
0x18006d302  pop     r15
0x18006d304  pop     r14
0x18006d306  pop     rdi
0x18006d307  pop     rsi
0x18006d308  pop     rbp
0x18006d309  retn
```
