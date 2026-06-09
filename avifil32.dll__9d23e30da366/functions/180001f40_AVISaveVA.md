# AVISaveVA

- ea: `0x180001f40`
- end: `0x180001fd6`
- name: `AVISaveVA`
- size: `150`
- prototype: `HRESULT __stdcall(LPCSTR szFile, CLSID *pclsidHandler, AVISAVECALLBACK lpfnCallback, int nStreams, PAVISTREAM *ppavi, LPAVICOMPRESSOPTIONS *plpOptions)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001d80`

## callees

- `0x180001f40`
- `0x180001fe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180001f8b`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180001f8b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180001f59`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180001f59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fc1`

## pseudocode

```c
HRESULT __stdcall AVISaveVA(
        LPCSTR szFile,
        CLSID *pclsidHandler,
        AVISAVECALLBACK lpfnCallback,
        int nStreams,
        PAVISTREAM *ppavi,
        LPAVICOMPRESSOPTIONS *plpOptions)
{
  __int64 v10; // rsi
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  HRESULT v14; // ebx

  v10 = lstrlenA(szFile) + 1;
  v11 = (WCHAR *)LocalAlloc(0x40u, 2 * v10);
  v12 = v11;
  if ( !v11 )
    return -2147205017;
  _o_mbstowcs(v11, szFile, v10);
  v14 = AVISaveVW(v12, pclsidHandler, lpfnCallback, nStreams, ppavi, plpOptions);
  LocalFree(v12);
  return v14;
}

```

## disassembly

```asm
0x180001f40  push    rbx; AVISaveV
0x180001f42  push    rbp
0x180001f43  push    rsi
0x180001f44  push    rdi
0x180001f45  push    r14
0x180001f47  push    r15
0x180001f49  sub     rsp, 38h
0x180001f4d  mov     ebp, r9d
0x180001f50  mov     r14, r8
0x180001f53  mov     r15, rdx
0x180001f56  mov     rbx, rcx
0x180001f59  call    cs:__imp_lstrlenA
0x180001f5f  inc     eax
0x180001f61  mov     ecx, 40h ; '@'; uFlags
0x180001f66  movsxd  rsi, eax
0x180001f69  lea     rdx, [rsi+rsi]; uBytes
0x180001f6d  call    cs:__imp_LocalAlloc
0x180001f73  mov     rdi, rax
0x180001f76  test    rax, rax
0x180001f79  jnz     short loc_180001F82
0x180001f7b  mov     eax, 80044067h
0x180001f80  jmp     short loc_180001FC9
0x180001f82  mov     r8, rsi
0x180001f85  mov     rdx, rbx
0x180001f88  mov     rcx, rdi
0x180001f8b  call    cs:__imp__o_mbstowcs
0x180001f91  mov     rax, [rsp+68h+plpOptions]
0x180001f99  mov     r9d, ebp; nStreams
0x180001f9c  mov     [rsp+68h+var_40], rax; plpOptions
0x180001fa1  mov     r8, r14; lpfnCallback
0x180001fa4  mov     rax, [rsp+68h+ppavi]
0x180001fac  mov     rdx, r15; pclsidHandler
0x180001faf  mov     rcx, rdi; szFile
0x180001fb2  mov     [rsp+68h+var_48], rax; ppavi
0x180001fb7  call    AVISaveVW
0x180001fbc  mov     rcx, rdi; hMem
0x180001fbf  mov     ebx, eax
0x180001fc1  call    cs:__imp_LocalFree
0x180001fc7  mov     eax, ebx
0x180001fc9  add     rsp, 38h
0x180001fcd  pop     r15
0x180001fcf  pop     r14
0x180001fd1  pop     rdi
0x180001fd2  pop     rsi
0x180001fd3  pop     rbp
0x180001fd4  pop     rbx
0x180001fd5  retn
```
