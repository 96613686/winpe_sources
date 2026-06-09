# CEtwLogCollector::ConstructProviderProperties(ushort const *,_EVENT_PROVIDER_PROPERTIES * &)

- ea: `0x18000d8f8`
- end: `0x18000da5f`
- name: `?ConstructProviderProperties@CEtwLogCollector@@AEAAJPEBGAEAPEAU_EVENT_PROVIDER_PROPERTIES@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, LPCWSTR lpSubKey, struct _EVENT_PROVIDER_PROPERTIES **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f478`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x180002bb8`
- `0x180006498`
- `0x18000d8f8`
- `0x18000e09c`
- `0x18000e314`
- `0x18000e628`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000da02`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000da02`

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
    operator delete(*a3, 0x20u);
    *a3 = 0;
  }
  return (unsigned int)IsProviderEnabled;
}

```

## disassembly

```asm
0x18000d8f8  mov     [rsp+arg_18], rbx
0x18000d8fd  push    rbp
0x18000d8fe  push    rsi
0x18000d8ff  push    rdi
0x18000d900  sub     rsp, 90h
0x18000d907  mov     rax, cs:__security_cookie
0x18000d90e  xor     rax, rsp
0x18000d911  mov     [rsp+0A8h+var_28], rax
0x18000d919  mov     [rsp+0A8h+var_88], 0
0x18000d921  mov     rdi, r8
0x18000d924  mov     [rsp+0A8h+var_84], 0
0x18000d92c  mov     rsi, rdx
0x18000d92f  mov     qword ptr [rsp+0A8h+Data], 0
0x18000d938  mov     rbp, rcx
0x18000d93b  test    rdx, rdx
0x18000d93e  jnz     short loc_18000D94A
0x18000d940  mov     ebx, 80070057h
0x18000d945  jmp     loc_18000DA25
0x18000d94a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d951  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d956  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d95b  test    rax, rax
0x18000d95e  jz      loc_18000DA19
0x18000d964  xorps   xmm0, xmm0
0x18000d967  lea     r8, [rsp+0A8h+var_88]; int *
0x18000d96c  movups  xmmword ptr [rax], xmm0
0x18000d96f  mov     rdx, rsi; lpSubKey
0x18000d972  mov     rcx, rbp; this
0x18000d975  movups  xmmword ptr [rax+10h], xmm0
0x18000d979  mov     [rdi], rax
0x18000d97c  call    ?IsProviderEnabled@CEtwLogCollector@@QEAAJPEBGAEAH@Z; CEtwLogCollector::IsProviderEnabled(ushort const *,int &)
0x18000d981  mov     ebx, eax
0x18000d983  test    eax, eax
0x18000d985  js      loc_18000DA25
0x18000d98b  lea     r8, [rsp+0A8h+var_84]; int *
0x18000d990  mov     rdx, rsi; lpSubKey
0x18000d993  mov     rcx, rbp; this
0x18000d996  call    ?GetTraceLevel@CEtwLogCollector@@QEAAJPEBGAEAJ@Z; CEtwLogCollector::GetTraceLevel(ushort const *,long &)
0x18000d99b  mov     ebx, eax
0x18000d99d  test    eax, eax
0x18000d99f  js      loc_18000DA25
0x18000d9a5  lea     r8, [rsp+0A8h+Data]; lpData
0x18000d9aa  mov     rdx, rsi; lpSubKey
0x18000d9ad  mov     rcx, rbp; this
0x18000d9b0  call    ?GetKeywords@CEtwLogCollector@@QEAAJPEBGAEA_K@Z; CEtwLogCollector::GetKeywords(ushort const *,unsigned __int64 &)
0x18000d9b5  mov     ebx, eax
0x18000d9b7  test    eax, eax
0x18000d9b9  js      short loc_18000DA25
0x18000d9bb  mov     rcx, [rdi]
0x18000d9be  lea     r8, aS; "{%s}"
0x18000d9c5  mov     eax, [rsp+0A8h+var_88]
0x18000d9c9  mov     r9, rsi
0x18000d9cc  mov     edx, 27h ; '''; unsigned __int64
0x18000d9d1  mov     [rcx+1Ch], eax
0x18000d9d4  mov     rcx, [rdi]
0x18000d9d7  mov     al, byte ptr [rsp+0A8h+var_84]
0x18000d9db  mov     [rcx+18h], al
0x18000d9de  mov     rcx, [rdi]
0x18000d9e1  mov     rax, qword ptr [rsp+0A8h+Data]
0x18000d9e6  mov     [rcx+10h], rax
0x18000d9ea  lea     rcx, [rsp+0A8h+sz]; unsigned __int16 *
0x18000d9ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d9f4  mov     ebx, eax
0x18000d9f6  test    eax, eax
0x18000d9f8  js      short loc_18000DA25
0x18000d9fa  mov     rdx, [rdi]; pclsid
0x18000d9fd  lea     rcx, [rsp+0A8h+sz]; lpsz
0x18000da02  call    cs:__imp_CLSIDFromString
0x18000da09  nop     dword ptr [rax+rax+00h]
0x18000da0e  mov     ebx, eax
0x18000da10  test    eax, eax
0x18000da12  jns     short loc_18000DA39
0x18000da14  jmp     loc_18000D940
0x18000da19  mov     qword ptr [rdi], 0
0x18000da20  mov     ebx, 8007000Eh
0x18000da25  mov     rcx, [rdi]; void *
0x18000da28  mov     edx, 20h ; ' '; unsigned __int64
0x18000da2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000da32  mov     qword ptr [rdi], 0
0x18000da39  mov     eax, ebx
0x18000da3b  mov     rcx, [rsp+0A8h+var_28]
0x18000da43  xor     rcx, rsp; StackCookie
0x18000da46  call    __security_check_cookie
0x18000da4b  mov     rbx, [rsp+0A8h+arg_18]
0x18000da53  add     rsp, 90h
0x18000da5a  pop     rdi
0x18000da5b  pop     rsi
0x18000da5c  pop     rbp
0x18000da5d  retn
```
