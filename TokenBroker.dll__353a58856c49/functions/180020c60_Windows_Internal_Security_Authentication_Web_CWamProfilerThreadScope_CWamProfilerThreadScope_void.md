# Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)

- ea: `0x180020c60`
- end: `0x180020d85`
- name: `??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ`
- size: `293`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *__hidden this)`
- caller_count: `105`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e7c0`
- `0x18001fc10`
- `0x180020840`
- `0x180020d90`
- `0x18002eb80`
- `0x18002f450`
- `0x18002fc10`
- `0x180033800`
- `0x180040480`
- `0x180054240`
- `0x1800564d0`
- `0x180056540`
- `0x180057160`
- `0x180057310`
- `0x180057580`
- `0x180058520`
- `0x1800586a8`
- `0x18005a1f0`
- `0x18005d080`
- `0x18005d870`
- `0x180060250`
- `0x180069a40`
- `0x18006abe0`
- `0x18006b0c0`
- `0x1800803f0`
- `0x180081890`
- `0x180082e10`
- `0x180083f90`
- `0x1800845d0`
- `0x180084d40`
- `0x180085c40`
- `0x180086a40`
- `0x180087800`
- `0x180088620`
- `0x180089730`
- `0x1800899a0`
- `0x18008b9a0`
- `0x18008be40`
- `0x18008c150`
- `0x18008c410`
- `0x18008d0b0`
- `0x18008dc10`
- `0x18009ed20`
- `0x18009f0c0`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800a9060`
- `0x1800a90b0`
- `0x1800a9100`
- `0x1800a9150`

## callees

- `0x180020c60`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020d56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020cf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020cf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d7a`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *this)
{
  _QWORD *v2; // rbx
  char *v3; // rcx
  void *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  HSTRING v12; // rcx

  if ( *(_BYTE *)this )
  {
    TlsSetValue(dwTlsIndex, 0);
    *(_BYTE *)this = 0;
  }
  v2 = (_QWORD *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
  {
    v3 = (char *)v2[39];
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
    v4 = (void *)v2[38];
    if ( v4 )
      CloseHandle(v4);
    v5 = (char *)v2[37];
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    v6 = (char *)v2[36];
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    v7 = (HSTRING)v2[9];
    if ( v7 )
      WindowsDeleteString(v7);
    v8 = (HSTRING)v2[8];
    if ( v8 )
      WindowsDeleteString(v8);
    v9 = (HSTRING)v2[7];
    if ( v9 )
      WindowsDeleteString(v9);
    v10 = (HSTRING)v2[6];
    if ( v10 )
      WindowsDeleteString(v10);
    v11 = (HSTRING)v2[5];
    if ( v11 )
      WindowsDeleteString(v11);
    v12 = (HSTRING)v2[4];
    if ( v12 )
      WindowsDeleteString(v12);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180020c60  mov     [rsp+arg_0], rbx
0x180020c65  push    rdi
0x180020c66  sub     rsp, 20h
0x180020c6a  cmp     byte ptr [rcx], 0
0x180020c6d  mov     rdi, rcx
0x180020c70  jnz     loc_180020D4E
0x180020c76  mov     rbx, [rdi+8]
0x180020c7a  mov     qword ptr [rdi+8], 0
0x180020c82  test    rbx, rbx
0x180020c85  jz      loc_180020D43
0x180020c8b  mov     rcx, [rbx+138h]; hObject
0x180020c92  lea     rax, [rcx-1]
0x180020c96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020c9a  jbe     loc_180020D64
0x180020ca0  mov     rcx, [rbx+130h]; hObject
0x180020ca7  test    rcx, rcx
0x180020caa  jz      short loc_180020CB2
0x180020cac  call    cs:__imp_CloseHandle
0x180020cb2  mov     rcx, [rbx+128h]; hObject
0x180020cb9  lea     rax, [rcx-1]
0x180020cbd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020cc1  jbe     loc_180020D6F
0x180020cc7  mov     rcx, [rbx+120h]; hObject
0x180020cce  lea     rax, [rcx-1]
0x180020cd2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020cd6  jbe     loc_180020D7A
0x180020cdc  mov     rcx, [rbx+48h]; string
0x180020ce0  test    rcx, rcx
0x180020ce3  jz      short loc_180020CEB
0x180020ce5  call    cs:__imp_WindowsDeleteString
0x180020ceb  mov     rcx, [rbx+40h]; string
0x180020cef  test    rcx, rcx
0x180020cf2  jz      short loc_180020CFA
0x180020cf4  call    cs:__imp_WindowsDeleteString
0x180020cfa  mov     rcx, [rbx+38h]; string
0x180020cfe  test    rcx, rcx
0x180020d01  jz      short loc_180020D09
0x180020d03  call    cs:__imp_WindowsDeleteString
0x180020d09  mov     rcx, [rbx+30h]; string
0x180020d0d  test    rcx, rcx
0x180020d10  jz      short loc_180020D18
0x180020d12  call    cs:__imp_WindowsDeleteString
0x180020d18  mov     rcx, [rbx+28h]; string
0x180020d1c  test    rcx, rcx
0x180020d1f  jz      short loc_180020D27
0x180020d21  call    cs:__imp_WindowsDeleteString
0x180020d27  mov     rcx, [rbx+20h]; string
0x180020d2b  test    rcx, rcx
0x180020d2e  jz      short loc_180020D36
0x180020d30  call    cs:__imp_WindowsDeleteString
0x180020d36  mov     edx, 140h
0x180020d3b  mov     rcx, rbx; Block
0x180020d3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020d43  mov     rbx, [rsp+28h+arg_0]
0x180020d48  add     rsp, 20h
0x180020d4c  pop     rdi
0x180020d4d  retn
0x180020d4e  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180020d54  xor     edx, edx; lpTlsValue
0x180020d56  call    cs:__imp_TlsSetValue
0x180020d5c  mov     byte ptr [rdi], 0
0x180020d5f  jmp     loc_180020C76
0x180020d64  call    cs:__imp_CloseHandle
0x180020d6a  jmp     loc_180020CA0
0x180020d6f  call    cs:__imp_CloseHandle
0x180020d75  jmp     loc_180020CC7
0x180020d7a  call    cs:__imp_CloseHandle
0x180020d80  jmp     loc_180020CDC
```
