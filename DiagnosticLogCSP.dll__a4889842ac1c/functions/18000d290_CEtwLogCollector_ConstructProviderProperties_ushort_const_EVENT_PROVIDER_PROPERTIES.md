# CEtwLogCollector::ConstructProviderProperties(ushort const *,_EVENT_PROVIDER_PROPERTIES * &)

- ea: `0x18000d290`
- end: `0x18000d3ec`
- name: `?ConstructProviderProperties@CEtwLogCollector@@AEAAJPEBGAEAPEAU_EVENT_PROVIDER_PROPERTIES@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, LPCWSTR lpSubKey, struct _EVENT_PROVIDER_PROPERTIES **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ed34`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x180002b88`
- `0x180006518`
- `0x18000d290`
- `0x18000d9e0`
- `0x18000dc40`
- `0x18000df44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d396`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d396`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::ConstructProviderProperties(
        CEtwLogCollector *this,
        LPCWSTR lpSubKey,
        struct _EVENT_PROVIDER_PROPERTIES **a3)
{
  HRESULT IsProviderEnabled; // ebx
  struct _EVENT_PROVIDER_PROPERTIES *v7; // rax
  int v9; // [rsp+20h] [rbp-88h] BYREF
  int v10; // [rsp+24h] [rbp-84h] BYREF
  BYTE Data[8]; // [rsp+28h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-78h] BYREF

  v9 = 0;
  v10 = 0;
  *(_QWORD *)Data = 0;
  if ( !lpSubKey )
    goto LABEL_2;
  v7 = (struct _EVENT_PROVIDER_PROPERTIES *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    *a3 = 0;
    IsProviderEnabled = -2147024882;
    goto LABEL_11;
  }
  *(_OWORD *)v7 = 0;
  *((_OWORD *)v7 + 1) = 0;
  *a3 = v7;
  IsProviderEnabled = CEtwLogCollector::IsProviderEnabled(this, lpSubKey, &v9);
  if ( IsProviderEnabled < 0 )
    goto LABEL_11;
  IsProviderEnabled = CEtwLogCollector::GetTraceLevel(this, lpSubKey, &v10);
  if ( IsProviderEnabled < 0 )
    goto LABEL_11;
  IsProviderEnabled = CEtwLogCollector::GetKeywords(this, lpSubKey, Data);
  if ( IsProviderEnabled < 0 )
    goto LABEL_11;
  *((_DWORD *)*a3 + 7) = v9;
  *((_BYTE *)*a3 + 24) = v10;
  *((_QWORD *)*a3 + 2) = *(_QWORD *)Data;
  IsProviderEnabled = StringCchPrintfW(sz, 0x27u, L"{%s}", lpSubKey);
  if ( IsProviderEnabled < 0 )
    goto LABEL_11;
  IsProviderEnabled = CLSIDFromString(sz, (LPCLSID)*a3);
  if ( IsProviderEnabled < 0 )
  {
LABEL_2:
    IsProviderEnabled = -2147024809;
LABEL_11:
    operator delete(*a3);
    *a3 = 0;
  }
  return (unsigned int)IsProviderEnabled;
}

```

## disassembly

```asm
0x18000d290  mov     [rsp+arg_18], rbx
0x18000d295  push    rbp
0x18000d296  push    rsi
0x18000d297  push    rdi
0x18000d298  sub     rsp, 90h
0x18000d29f  mov     rax, cs:__security_cookie
0x18000d2a6  xor     rax, rsp
0x18000d2a9  mov     [rsp+0A8h+var_28], rax
0x18000d2b1  mov     [rsp+0A8h+var_88], 0
0x18000d2b9  mov     rdi, r8
0x18000d2bc  mov     [rsp+0A8h+var_84], 0
0x18000d2c4  mov     rsi, rdx
0x18000d2c7  mov     qword ptr [rsp+0A8h+Data], 0
0x18000d2d0  mov     rbp, rcx
0x18000d2d3  test    rdx, rdx
0x18000d2d6  jnz     short loc_18000D2E2
0x18000d2d8  mov     ebx, 80070057h
0x18000d2dd  jmp     loc_18000D3B3
0x18000d2e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d2e9  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d2ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d2f3  test    rax, rax
0x18000d2f6  jz      loc_18000D3A7
0x18000d2fc  xorps   xmm0, xmm0
0x18000d2ff  lea     r8, [rsp+0A8h+var_88]; int *
0x18000d304  movups  xmmword ptr [rax], xmm0
0x18000d307  mov     rdx, rsi; lpSubKey
0x18000d30a  mov     rcx, rbp; this
0x18000d30d  movups  xmmword ptr [rax+10h], xmm0
0x18000d311  mov     [rdi], rax
0x18000d314  call    ?IsProviderEnabled@CEtwLogCollector@@QEAAJPEBGAEAH@Z; CEtwLogCollector::IsProviderEnabled(ushort const *,int &)
0x18000d319  mov     ebx, eax
0x18000d31b  test    eax, eax
0x18000d31d  js      loc_18000D3B3
0x18000d323  lea     r8, [rsp+0A8h+var_84]; int *
0x18000d328  mov     rdx, rsi; lpSubKey
0x18000d32b  mov     rcx, rbp; this
0x18000d32e  call    ?GetTraceLevel@CEtwLogCollector@@QEAAJPEBGAEAJ@Z; CEtwLogCollector::GetTraceLevel(ushort const *,long &)
0x18000d333  mov     ebx, eax
0x18000d335  test    eax, eax
0x18000d337  js      short loc_18000D3B3
0x18000d339  lea     r8, [rsp+0A8h+Data]; lpData
0x18000d33e  mov     rdx, rsi; lpSubKey
0x18000d341  mov     rcx, rbp; this
0x18000d344  call    ?GetKeywords@CEtwLogCollector@@QEAAJPEBGAEA_K@Z; CEtwLogCollector::GetKeywords(ushort const *,unsigned __int64 &)
0x18000d349  mov     ebx, eax
0x18000d34b  test    eax, eax
0x18000d34d  js      short loc_18000D3B3
0x18000d34f  mov     rcx, [rdi]
0x18000d352  lea     r8, aS; "{%s}"
0x18000d359  mov     eax, [rsp+0A8h+var_88]
0x18000d35d  mov     r9, rsi
0x18000d360  mov     edx, 27h ; '''; unsigned __int64
0x18000d365  mov     [rcx+1Ch], eax
0x18000d368  mov     rcx, [rdi]
0x18000d36b  mov     al, byte ptr [rsp+0A8h+var_84]
0x18000d36f  mov     [rcx+18h], al
0x18000d372  mov     rcx, [rdi]
0x18000d375  mov     rax, qword ptr [rsp+0A8h+Data]
0x18000d37a  mov     [rcx+10h], rax
0x18000d37e  lea     rcx, [rsp+0A8h+sz]; unsigned __int16 *
0x18000d383  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d388  mov     ebx, eax
0x18000d38a  test    eax, eax
0x18000d38c  js      short loc_18000D3B3
0x18000d38e  mov     rdx, [rdi]; pclsid
0x18000d391  lea     rcx, [rsp+0A8h+sz]; lpsz
0x18000d396  call    cs:__imp_CLSIDFromString
0x18000d39c  mov     ebx, eax
0x18000d39e  test    eax, eax
0x18000d3a0  jns     short loc_18000D3C7
0x18000d3a2  jmp     loc_18000D2D8
0x18000d3a7  mov     qword ptr [rdi], 0
0x18000d3ae  mov     ebx, 8007000Eh
0x18000d3b3  mov     rcx, [rdi]; void *
0x18000d3b6  mov     edx, 20h ; ' '; unsigned __int64
0x18000d3bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d3c0  mov     qword ptr [rdi], 0
0x18000d3c7  mov     eax, ebx
0x18000d3c9  mov     rcx, [rsp+0A8h+var_28]
0x18000d3d1  xor     rcx, rsp; StackCookie
0x18000d3d4  call    __security_check_cookie
0x18000d3d9  mov     rbx, [rsp+0A8h+arg_18]
0x18000d3e1  add     rsp, 90h
0x18000d3e8  pop     rdi
0x18000d3e9  pop     rsi
0x18000d3ea  pop     rbp
0x18000d3eb  retn
```
