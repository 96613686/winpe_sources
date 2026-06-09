# WideStringToNarrowStringCoTaskMemAlloc(ushort const *,char * *)

- ea: `0x1800fb798`
- end: `0x1800fb8e1`
- name: `?WideStringToNarrowStringCoTaskMemAlloc@@YAJPEBGPEAPEAD@Z`
- size: `329`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fb718`

## callees

- `0x18007e0c8`
- `0x18007e75c`
- `0x180091b04`
- `0x1800c8458`
- `0x1800fb798`
- `0x1800fc644`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb7d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb8a3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb7d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb8a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb874`

## string_xrefs

- `0x1800fb7e8`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`
- `0x1800fb855`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`
- `0x1800fb8b1`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WideStringToNarrowStringCoTaskMemAlloc(LPCWCH lpWideCharStr, LPVOID *a2)
{
  int v4; // eax
  const char *v5; // r9
  int cbMultiByte; // esi
  void *v8; // rcx
  int LastError; // ebx
  unsigned int v10; // r10d
  void *v11; // rcx
  const char *v12; // r9
  int lpMultiByteStr; // [rsp+20h] [rbp-40h]
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  void *v15; // [rsp+48h] [rbp-18h] BYREF
  char v16; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF
  unsigned __int64 v19; // [rsp+A0h] [rbp+40h] BYREF

  *a2 = 0;
  v4 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
             v5);
  pv = 0;
  p_pv = &pv;
  v16 = 1;
  v15 = 0;
  v19 = 0;
  LastError = ULongLongMult(v4, 1u, &v19);
  if ( LastError >= 0 )
    LastError = CTCoAllocPolicy::Alloc(v8, v10, v19, &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( LastError >= 0 )
  {
    if ( WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, (LPSTR)pv, cbMultiByte, 0, 0) )
    {
      *a2 = pv;
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
                  v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
      (const char *)(unsigned int)LastError,
      lpMultiByteStr);
  }
  v11 = pv;
  pv = 0;
  if ( v11 )
    CoTaskMemFree(v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800fb798  mov     rax, rsp
0x1800fb79b  mov     [rax+8], rbx
0x1800fb79f  push    rbp
0x1800fb7a0  push    rsi
0x1800fb7a1  push    rdi
0x1800fb7a2  push    r14
0x1800fb7a4  push    r15
0x1800fb7a6  mov     rbp, rsp
0x1800fb7a9  sub     rsp, 60h
0x1800fb7ad  mov     rdi, rdx
0x1800fb7b0  mov     r14, rcx
0x1800fb7b3  xor     r15d, r15d
0x1800fb7b6  mov     [rdx], r15
0x1800fb7b9  mov     [rax-50h], r15
0x1800fb7bd  mov     [rax-58h], r15
0x1800fb7c1  mov     [rax-60h], r15d
0x1800fb7c5  mov     [rax-68h], r15
0x1800fb7c9  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800fb7cd  mov     r8, rcx; lpWideCharStr
0x1800fb7d0  mov     edx, 400h; dwFlags
0x1800fb7d5  xor     ecx, ecx; CodePage
0x1800fb7d7  call    cs:__imp_WideCharToMultiByte
0x1800fb7dd  movsxd  rsi, eax
0x1800fb7e0  test    eax, eax
0x1800fb7e2  jnz     short loc_1800FB7FC
0x1800fb7e4  mov     rcx, [rbp+28h]; this
0x1800fb7e8  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800fb7ef  lea     edx, [rax+0Ah]; void *
0x1800fb7f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fb7f7  jmp     loc_1800FB8CD
0x1800fb7fc  mov     [rbp+pv], r15
0x1800fb800  lea     rax, [rbp+pv]
0x1800fb804  mov     [rbp+var_20], rax
0x1800fb808  mov     r10d, 1
0x1800fb80e  mov     [rbp+var_10], r10b
0x1800fb812  mov     [rbp+var_18], r15
0x1800fb816  mov     [rbp+arg_10], r15
0x1800fb81a  mov     rcx, rsi; unsigned __int64
0x1800fb81d  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1800fb821  mov     edx, r10d; unsigned __int64
0x1800fb824  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800fb829  mov     ebx, eax
0x1800fb82b  test    eax, eax
0x1800fb82d  js      short loc_1800FB841
0x1800fb82f  lea     r9, [rbp+var_18]; void **
0x1800fb833  mov     r8, [rbp+arg_10]; unsigned __int64
0x1800fb837  mov     edx, r10d; unsigned int
0x1800fb83a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800fb83f  mov     ebx, eax
0x1800fb841  lea     rcx, [rbp+var_20]
0x1800fb845  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800fb84a  test    ebx, ebx
0x1800fb84c  jns     short loc_1800FB87E
0x1800fb84e  mov     rcx, [rbp+28h]; this
0x1800fb852  mov     r9d, ebx; char *
0x1800fb855  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800fb85c  mov     edx, 0Dh; void *
0x1800fb861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb866  nop
0x1800fb867  mov     rcx, [rbp+pv]; pv
0x1800fb86b  mov     [rbp+pv], r15
0x1800fb86f  test    rcx, rcx
0x1800fb872  jz      short loc_1800FB87A
0x1800fb874  call    cs:__imp_CoTaskMemFree
0x1800fb87a  mov     eax, ebx
0x1800fb87c  jmp     short loc_1800FB8CD
0x1800fb87e  mov     [rsp+60h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800fb883  mov     [rsp+60h+lpDefaultChar], r15; lpDefaultChar
0x1800fb888  mov     [rsp+60h+cbMultiByte], esi; cbMultiByte
0x1800fb88c  mov     rax, [rbp+pv]
0x1800fb890  mov     [rsp+60h+lpMultiByteStr], rax; lpMultiByteStr
0x1800fb895  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800fb899  mov     r8, r14; lpWideCharStr
0x1800fb89c  mov     edx, 400h; dwFlags
0x1800fb8a1  xor     ecx, ecx; CodePage
0x1800fb8a3  call    cs:__imp_WideCharToMultiByte
0x1800fb8a9  test    eax, eax
0x1800fb8ab  jnz     short loc_1800FB8C4
0x1800fb8ad  mov     rcx, [rbp+28h]; this
0x1800fb8b1  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800fb8b8  lea     edx, [rax+0Eh]; void *
0x1800fb8bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fb8c0  mov     ebx, eax
0x1800fb8c2  jmp     short loc_1800FB867
0x1800fb8c4  mov     rax, [rbp+pv]
0x1800fb8c8  mov     [rdi], rax
0x1800fb8cb  xor     eax, eax
0x1800fb8cd  mov     rbx, [rsp+60h+arg_0]
0x1800fb8d5  add     rsp, 60h
0x1800fb8d9  pop     r15
0x1800fb8db  pop     r14
0x1800fb8dd  pop     rdi
0x1800fb8de  pop     rsi
0x1800fb8df  pop     rbp
0x1800fb8e0  retn
```
