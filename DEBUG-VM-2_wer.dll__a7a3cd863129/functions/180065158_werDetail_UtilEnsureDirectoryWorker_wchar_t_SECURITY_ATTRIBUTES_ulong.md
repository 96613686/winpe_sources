# _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180065158`
- end: `0x180065284`
- name: `?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `300`
- prototype: `__int64 __fastcall(wchar_t *this, LPSECURITY_ATTRIBUTES lpSecurityAttributes, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006505c`
- `0x180065158`

## callees

- `0x18000716c`
- `0x180019808`
- `0x1800303dc`
- `0x180065158`
- `0x18006549c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065251`
- `ntdll!wcsrchr` at `0x180065203`
- `ntdll!wcsrchr` at `0x180065203`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800651c7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006523a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800651c7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006523a`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilEnsureDirectoryWorker(
        wchar_t *this,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        struct _SECURITY_ATTRIBUTES *a3)
{
  int v3; // ebx
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  wchar_t *v10; // rax
  unsigned int v11; // r9d
  wchar_t *v12; // r14
  int v13; // eax
  DWORD LastError; // eax
  wchar_t *v16; // [rsp+88h] [rbp+20h] BYREF

  v3 = (int)a3;
  if ( (unsigned int)a3 <= 0x1E )
  {
    if ( !CreateDirectoryW(this, lpSecurityAttributes) )
    {
      if ( GetLastError() == 183 )
        return !UtilPathIsDirectory(this) ? 0x80070050 : 0;
      v10 = wcsrchr(this, 0x5Cu);
      v12 = v10;
      if ( !v10 )
        return (unsigned int)-2147024893;
      *v10 = 0;
      v13 = _werDetail::UtilEnsureDirectoryWorker(
              this,
              lpSecurityAttributes,
              (struct _SECURITY_ATTRIBUTES *)(unsigned int)(v3 + 1),
              v11);
      *v12 = 92;
      v6 = v13;
      if ( v13 < 0 )
        return v6;
      if ( !CreateDirectoryW(this, lpSecurityAttributes) )
      {
        if ( GetLastError() != 183 )
        {
          LastError = GetLastError();
          return (unsigned int)ERROR_HR_FROM_WIN32(LastError);
        }
        v6 = -2147024816;
        if ( !UtilPathIsDirectory(this) )
          return v6;
      }
    }
    return 0;
  }
  v6 = -2147024735;
  if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    v16 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned int)&dword_1800C6F64,
      v8,
      v9,
      (__int64)&v16);
  }
  return v6;
}

```

## disassembly

```asm
0x180065158  push    rbx
0x18006515a  push    rbp
0x18006515b  push    rsi
0x18006515c  push    rdi
0x18006515d  push    r12
0x18006515f  push    r14
0x180065161  sub     rsp, 38h
0x180065165  mov     ebx, r8d
0x180065168  mov     rbp, rdx
0x18006516b  mov     rsi, rcx
0x18006516e  cmp     r8d, 1Eh
0x180065172  jbe     short loc_1800651C7
0x180065174  mov     eax, cs:dword_1800D8000
0x18006517a  mov     ebx, 800700A1h
0x18006517f  cmp     eax, 2
0x180065182  jbe     loc_180065275
0x180065188  mov     edx, 8
0x18006518d  lea     rcx, dword_1800D8000
0x180065194  call    _tlgKeywordOn
0x180065199  test    al, al
0x18006519b  jz      loc_180065275
0x1800651a1  lea     rax, [rsp+68h+arg_18]
0x1800651a9  mov     [rsp+68h+arg_18], rsi
0x1800651b1  lea     rdx, dword_1800C6F64
0x1800651b8  mov     [rsp+68h+var_48], rax
0x1800651bd  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800651c2  jmp     loc_180065275
0x1800651c7  call    cs:__imp_CreateDirectoryW
0x1800651cd  xor     edi, edi
0x1800651cf  test    eax, eax
0x1800651d1  jnz     loc_180065273
0x1800651d7  call    cs:__imp_GetLastError
0x1800651dd  mov     rcx, rsi; wchar_t *
0x1800651e0  cmp     eax, 0B7h
0x1800651e5  jnz     short loc_1800651FA
0x1800651e7  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x1800651ec  neg     al
0x1800651ee  sbb     ebx, ebx
0x1800651f0  not     ebx
0x1800651f2  and     ebx, 80070050h
0x1800651f8  jmp     short loc_180065275
0x1800651fa  mov     r12d, 5Ch ; '\'
0x180065200  mov     edx, r12d; Ch
0x180065203  call    cs:__imp_wcsrchr
0x180065209  mov     r14, rax
0x18006520c  test    rax, rax
0x18006520f  jnz     short loc_180065218
0x180065211  mov     ebx, 80070003h
0x180065216  jmp     short loc_180065275
0x180065218  lea     r8d, [rbx+1]; struct _SECURITY_ATTRIBUTES *
0x18006521c  mov     [rax], di
0x18006521f  mov     rdx, rbp; lpSecurityAttributes
0x180065222  mov     rcx, rsi; this
0x180065225  call    ?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z; _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)
0x18006522a  mov     [r14], r12w
0x18006522e  mov     ebx, eax
0x180065230  test    eax, eax
0x180065232  js      short loc_180065275
0x180065234  mov     rdx, rbp; lpSecurityAttributes
0x180065237  mov     rcx, rsi; lpPathName
0x18006523a  call    cs:__imp_CreateDirectoryW
0x180065240  test    eax, eax
0x180065242  jnz     short loc_180065273
0x180065244  call    cs:__imp_GetLastError
0x18006524a  cmp     eax, 0B7h
0x18006524f  jz      short loc_180065262
0x180065251  call    cs:__imp_GetLastError
0x180065257  mov     ecx, eax; unsigned int
0x180065259  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006525e  mov     ebx, eax
0x180065260  jmp     short loc_180065275
0x180065262  mov     rcx, rsi; wchar_t *
0x180065265  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18006526a  mov     ebx, 80070050h
0x18006526f  test    al, al
0x180065271  jz      short loc_180065275
0x180065273  mov     ebx, edi
0x180065275  mov     eax, ebx
0x180065277  add     rsp, 38h
0x18006527b  pop     r14
0x18006527d  pop     r12
0x18006527f  pop     rdi
0x180065280  pop     rsi
0x180065281  pop     rbp
0x180065282  pop     rbx
0x180065283  retn
```
