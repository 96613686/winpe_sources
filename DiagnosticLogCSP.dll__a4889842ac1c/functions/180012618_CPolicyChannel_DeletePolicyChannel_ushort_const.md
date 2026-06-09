# CPolicyChannel::DeletePolicyChannel(ushort const *)

- ea: `0x180012618`
- end: `0x1800127ce`
- name: `?DeletePolicyChannel@CPolicyChannel@@SAJPEBG@Z`
- size: `438`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c260`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x180010e98`
- `0x18001107c`
- `0x180012618`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180012693`
- `ntdll!RtlGetPersistedStateLocation` at `0x180012693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001279f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001279f`

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
  _QWORD v12[3]; // [rsp+48h] [rbp-B8h] BYREF
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
      v6 = CRegUtils::OpenKey(SubKey, (struct ATL::CRegKey *)v12);
      if ( v6 >= 0 )
      {
        v6 = CRegUtils::DeleteKey((struct ATL::CRegKey *)v12, v4);
        if ( v6 == 2 )
          v6 = 0;
      }
      v5 = (HKEY)v12[0];
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v11 = v6;
    if ( !v4 )
      v4 = &String2;
    v13 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&dword_180040064,
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
0x180012618  mov     [rsp-8+arg_8], rbx
0x18001261d  mov     [rsp-8+arg_10], rsi
0x180012622  push    rbp
0x180012623  push    rdi
0x180012624  push    r14
0x180012626  lea     rbp, [rsp-780h]
0x18001262e  sub     rsp, 880h
0x180012635  mov     rax, cs:__security_cookie
0x18001263c  xor     rax, rsp
0x18001263f  mov     [rbp+790h+var_20], rax
0x180012646  xor     r14d, r14d
0x180012649  mov     rsi, rcx
0x18001264c  mov     [rsp+890h+var_848], r14
0x180012651  mov     edi, r14d
0x180012654  mov     [rsp+890h+var_840], r14
0x180012659  mov     [rsp+890h+var_838], r14
0x18001265e  test    rcx, rcx
0x180012661  jnz     short loc_18001266D
0x180012663  mov     ebx, 80070057h
0x180012668  jmp     loc_180012755
0x18001266d  mov     [rsp+890h+var_860], r14
0x180012672  lea     rax, [rsp+890h+var_820]
0x180012677  mov     dword ptr [rsp+890h+var_868], 400h
0x18001267f  lea     rcx, aWinevt; "WINEVT"
0x180012686  xor     r9d, r9d
0x180012689  mov     [rsp+890h+var_870], rax
0x18001268e  xor     r8d, r8d
0x180012691  xor     edx, edx
0x180012693  call    cs:__imp_RtlGetPersistedStateLocation
0x180012699  mov     r10d, 200h
0x18001269f  test    eax, eax
0x1800126a1  jns     short loc_1800126FC
0x1800126a3  mov     eax, 7FFFFFFEh
0x1800126a8  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800126af  mov     edx, r10d
0x1800126b2  lea     r8, [rsp+890h+var_820]
0x1800126b7  test    rax, rax
0x1800126ba  jz      short loc_1800126DB
0x1800126bc  movzx   r9d, word ptr [rcx]
0x1800126c0  test    r9w, r9w
0x1800126c4  jz      short loc_1800126DB
0x1800126c6  mov     [r8], r9w
0x1800126ca  add     rcx, 2
0x1800126ce  add     r8, 2
0x1800126d2  dec     rax
0x1800126d5  sub     rdx, 1
0x1800126d9  jnz     short loc_1800126B7
0x1800126db  mov     rax, rdx
0x1800126de  lea     rcx, [r8-2]
0x1800126e2  neg     rax
0x1800126e5  sbb     ebx, ebx
0x1800126e7  not     ebx
0x1800126e9  and     ebx, 8007007Ah
0x1800126ef  test    rdx, rdx
0x1800126f2  cmovnz  rcx, r8
0x1800126f6  mov     [rcx], r14w
0x1800126fa  jz      short loc_180012755
0x1800126fc  lea     rax, aPolicies; "Policies"
0x180012703  mov     rdx, r10; unsigned __int64
0x180012706  lea     r9, [rsp+890h+var_820]
0x18001270b  mov     [rsp+890h+var_870], rax
0x180012710  lea     r8, aSS_0; "%s\\%s"
0x180012717  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18001271e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012723  lea     rdx, [rsp+890h+var_848]; struct ATL::CRegKey *
0x180012728  lea     rcx, [rbp+790h+SubKey]; lpSubKey
0x18001272f  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x180012734  mov     ebx, eax
0x180012736  test    eax, eax
0x180012738  js      short loc_180012750
0x18001273a  mov     rdx, rsi; unsigned __int16 *
0x18001273d  lea     rcx, [rsp+890h+var_848]; struct ATL::CRegKey *
0x180012742  call    ?DeleteKey@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG@Z; CRegUtils::DeleteKey(ATL::CRegKey &,ushort const *)
0x180012747  cmp     eax, 2
0x18001274a  mov     ebx, eax
0x18001274c  cmovz   ebx, r14d
0x180012750  mov     rdi, [rsp+890h+var_848]
0x180012755  mov     eax, cs:dword_180048E90
0x18001275b  cmp     eax, 5
0x18001275e  jbe     short loc_180012797
0x180012760  test    rsi, rsi
0x180012763  mov     [rsp+890h+var_850], ebx
0x180012767  lea     rax, String2
0x18001276e  cmovz   rsi, rax
0x180012772  lea     rdx, dword_180040064
0x180012779  lea     rax, [rsp+890h+var_850]
0x18001277e  mov     [rsp+890h+var_830], rsi
0x180012783  mov     [rsp+890h+var_868], rax
0x180012788  lea     rax, [rsp+890h+var_830]
0x18001278d  mov     [rsp+890h+var_870], rax
0x180012792  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180012797  test    rdi, rdi
0x18001279a  jz      short loc_1800127A5
0x18001279c  mov     rcx, rdi; hKey
0x18001279f  call    cs:__imp_RegCloseKey
0x1800127a5  mov     eax, ebx
0x1800127a7  mov     rcx, [rbp+790h+var_20]
0x1800127ae  xor     rcx, rsp; StackCookie
0x1800127b1  call    __security_check_cookie
0x1800127b6  lea     r11, [rsp+890h+var_10]
0x1800127be  mov     rbx, [r11+28h]
0x1800127c2  mov     rsi, [r11+30h]
0x1800127c6  mov     rsp, r11
0x1800127c9  pop     r14
0x1800127cb  pop     rdi
0x1800127cc  pop     rbp
0x1800127cd  retn
```
