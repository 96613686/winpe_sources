# CPolicyChannel::DeletePolicyChannel(ushort const *)

- ea: `0x180012fe0`
- end: `0x1800131a3`
- name: `?DeletePolicyChannel@CPolicyChannel@@SAJPEBG@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c7b0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x180011734`
- `0x180011930`
- `0x180012fe0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18001305b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001305b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001316d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001316d`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::DeletePolicyChannel(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // rsi
  HKEY v5; // rdi
  signed int v6; // ebx
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int v11; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v12[3]; // [rsp+48h] [rbp-B8h] BYREF
  const WCHAR *v13; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[1024]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[512]; // [rsp+470h] [rbp+370h] BYREF

  v4 = a1;
  memset(v12, 0, sizeof(v12));
  v5 = 0;
  if ( a1 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v14, 1024, 0) >= 0 )
      goto LABEL_11;
    v7 = 2147483646;
    v8 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v9 = 512;
    a3 = (unsigned __int16 *)v14;
    do
    {
      if ( !v7 )
        break;
      a4 = *v8;
      if ( !(_WORD)a4 )
        break;
      *a3 = a4;
      ++v8;
      ++a3;
      --v7;
      --v9;
    }
    while ( v9 );
    a1 = a3 - 1;
    v6 = v9 == 0 ? 0x8007007A : 0;
    if ( v9 )
      a1 = a3;
    *a1 = 0;
    if ( v9 )
    {
LABEL_11:
      StringCchPrintfW(SubKey, 0x200u, L"%s\\%s", v14, L"Policies");
      v6 = CRegUtils::OpenKey(SubKey, v12);
      if ( v6 >= 0 )
      {
        v6 = CRegUtils::DeleteKey((struct ATL::CRegKey *)v12, v4);
        if ( v6 == 2 )
          v6 = 0;
      }
      v5 = v12[0];
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v11 = v6;
    if ( !v4 )
      v4 = &String2;
    v13 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (unsigned __int8 *)&dword_180042064,
      (__int64)a3,
      a4,
      &v13,
      (__int64)&v11);
  }
  if ( v5 )
    RegCloseKey(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012fe0  mov     [rsp-8+arg_8], rbx
0x180012fe5  mov     [rsp-8+arg_10], rsi
0x180012fea  push    rbp
0x180012feb  push    rdi
0x180012fec  push    r14
0x180012fee  lea     rbp, [rsp-780h]
0x180012ff6  sub     rsp, 880h
0x180012ffd  mov     rax, cs:__security_cookie
0x180013004  xor     rax, rsp
0x180013007  mov     [rbp+790h+var_20], rax
0x18001300e  xor     r14d, r14d
0x180013011  mov     rsi, rcx
0x180013014  mov     [rsp+890h+var_848], r14
0x180013019  mov     edi, r14d
0x18001301c  mov     [rsp+890h+var_840], r14
0x180013021  mov     [rsp+890h+var_838], r14
0x180013026  test    rcx, rcx
0x180013029  jnz     short loc_180013035
0x18001302b  mov     ebx, 80070057h
0x180013030  jmp     loc_180013123
0x180013035  mov     [rsp+890h+var_860], r14
0x18001303a  lea     rax, [rsp+890h+var_820]
0x18001303f  mov     dword ptr [rsp+890h+var_868], 400h
0x180013047  lea     rcx, aWinevt; "WINEVT"
0x18001304e  xor     r9d, r9d
0x180013051  mov     [rsp+890h+var_870], rax
0x180013056  xor     r8d, r8d
0x180013059  xor     edx, edx
0x18001305b  call    cs:__imp_RtlGetPersistedStateLocation
0x180013062  nop     dword ptr [rax+rax+00h]
0x180013067  mov     r10d, 200h
0x18001306d  test    eax, eax
0x18001306f  jns     short loc_1800130CA
0x180013071  mov     eax, 7FFFFFFEh
0x180013076  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001307d  mov     edx, r10d
0x180013080  lea     r8, [rsp+890h+var_820]
0x180013085  test    rax, rax
0x180013088  jz      short loc_1800130A9
0x18001308a  movzx   r9d, word ptr [rcx]
0x18001308e  test    r9w, r9w
0x180013092  jz      short loc_1800130A9
0x180013094  mov     [r8], r9w
0x180013098  add     rcx, 2
0x18001309c  add     r8, 2
0x1800130a0  dec     rax
0x1800130a3  sub     rdx, 1
0x1800130a7  jnz     short loc_180013085
0x1800130a9  mov     rax, rdx
0x1800130ac  lea     rcx, [r8-2]
0x1800130b0  neg     rax
0x1800130b3  sbb     ebx, ebx
0x1800130b5  not     ebx
0x1800130b7  and     ebx, 8007007Ah
0x1800130bd  test    rdx, rdx
0x1800130c0  cmovnz  rcx, r8
0x1800130c4  mov     [rcx], r14w
0x1800130c8  jz      short loc_180013123
0x1800130ca  lea     rax, aPolicies; "Policies"
0x1800130d1  mov     rdx, r10; unsigned __int64
0x1800130d4  lea     r9, [rsp+890h+var_820]
0x1800130d9  mov     [rsp+890h+var_870], rax
0x1800130de  lea     r8, aSS_0; "%s\\%s"
0x1800130e5  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x1800130ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800130f1  lea     rdx, [rsp+890h+var_848]; struct ATL::CRegKey *
0x1800130f6  lea     rcx, [rbp+790h+SubKey]; lpSubKey
0x1800130fd  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x180013102  mov     ebx, eax
0x180013104  test    eax, eax
0x180013106  js      short loc_18001311E
0x180013108  mov     rdx, rsi; unsigned __int16 *
0x18001310b  lea     rcx, [rsp+890h+var_848]; struct ATL::CRegKey *
0x180013110  call    ?DeleteKey@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG@Z; CRegUtils::DeleteKey(ATL::CRegKey &,ushort const *)
0x180013115  cmp     eax, 2
0x180013118  mov     ebx, eax
0x18001311a  cmovz   ebx, r14d
0x18001311e  mov     rdi, [rsp+890h+var_848]
0x180013123  mov     eax, cs:dword_18004AE90
0x180013129  cmp     eax, 5
0x18001312c  jbe     short loc_180013165
0x18001312e  test    rsi, rsi
0x180013131  mov     [rsp+890h+var_850], ebx
0x180013135  lea     rax, String2
0x18001313c  cmovz   rsi, rax
0x180013140  lea     rdx, dword_180042064
0x180013147  lea     rax, [rsp+890h+var_850]
0x18001314c  mov     [rsp+890h+var_830], rsi
0x180013151  mov     [rsp+890h+var_868], rax
0x180013156  lea     rax, [rsp+890h+var_830]
0x18001315b  mov     [rsp+890h+var_870], rax
0x180013160  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013165  test    rdi, rdi
0x180013168  jz      short loc_180013179
0x18001316a  mov     rcx, rdi; hKey
0x18001316d  call    cs:__imp_RegCloseKey
0x180013174  nop     dword ptr [rax+rax+00h]
0x180013179  mov     eax, ebx
0x18001317b  mov     rcx, [rbp+790h+var_20]
0x180013182  xor     rcx, rsp; StackCookie
0x180013185  call    __security_check_cookie
0x18001318a  lea     r11, [rsp+890h+var_10]
0x180013192  mov     rbx, [r11+28h]
0x180013196  mov     rsi, [r11+30h]
0x18001319a  mov     rsp, r11
0x18001319d  pop     r14
0x18001319f  pop     rdi
0x1800131a0  pop     rbp
0x1800131a1  retn
```
