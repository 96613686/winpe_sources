# CAccountsSettingsPane::QueryCachedCommands(ushort * * *,ulong *)

- ea: `0x18002a680`
- end: `0x18002a856`
- name: `?QueryCachedCommands@CAccountsSettingsPane@@UEAAJPEAPEAPEAGPEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011ffc`
- `0x18001c434`
- `0x18001d3d0`
- `0x1800211c4`
- `0x18002a680`
- `0x18002b004`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a832`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccountsSettingsPane::QueryCachedCommands(
        CAccountsSettingsPane *this,
        HSTRING *a2,
        unsigned int *a3)
{
  CAccountsSettingsPane *v5; // rbx
  int v6; // r15d
  HSTRING v7; // rsi
  void *v8; // rcx
  unsigned int i; // r14d
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, unsigned __int64 *); // rbx
  unsigned __int64 v12; // rdi
  __int64 (__fastcall *v13)(unsigned __int64, HSTRING *); // rbx
  int v14; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // edx
  void *v20; // rcx
  int v21; // ebx
  void *v22; // r10
  unsigned __int64 v24; // [rsp+80h] [rbp+48h] BYREF
  unsigned __int64 v25; // [rsp+88h] [rbp+50h] BYREF
  HSTRING string; // [rsp+90h] [rbp+58h] BYREF
  unsigned __int64 v27; // [rsp+98h] [rbp+60h] BYREF

  v24 = (unsigned __int64)this;
  v5 = this;
  *a2 = 0;
  *a3 = 0;
  LODWORD(v25) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 8) + 56LL))(
         *((_QWORD *)this + 8),
         &v25);
  if ( v6 >= 0 && (_DWORD)v25 )
  {
    v7 = 0;
    string = 0;
    v27 = 0;
    v6 = ULongLongMult((unsigned int)v25, 8u, &v27);
    if ( v6 >= 0 )
    {
      v6 = CTCoAllocPolicy::Alloc(v8, 1u, v27, (void **)&string);
      v7 = string;
    }
    if ( v6 >= 0 )
    {
      for ( i = 0; i < (unsigned int)v25; ++i )
      {
        v27 = 0;
        v10 = *((_QWORD *)v5 + 8);
        v11 = *(int (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v10 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        if ( v11(v10, i, &v27) < 0 )
          goto LABEL_15;
        string = 0;
        v12 = v27;
        v13 = *(__int64 (__fastcall **)(unsigned __int64, HSTRING *))(*(_QWORD *)v27 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v14 = v13(v12, &string);
        if ( v14 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v18 = -1;
          do
            ++v18;
          while ( StringRawBuffer[v18] );
          v14 = _AllocStringWorker<CTCoAllocPolicy>(v17, v16, StringRawBuffer);
        }
        WindowsDeleteString(string);
        if ( v14 < 0 )
        {
LABEL_15:
          v7 = 0;
          string = 0;
          v24 = 0;
          v21 = ULongLongMult(i, 8u, &v24);
          if ( v21 >= 0 )
          {
            v21 = CTCoAllocPolicy::Realloc(v20, v19, v22, v24, (void **)&string);
            v7 = string;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
          if ( v21 < 0 )
          {
            v6 = v21;
            CoTaskMemFree(v7);
            return (unsigned int)v6;
          }
          break;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        v5 = (CAccountsSettingsPane *)v24;
      }
      *a3 = i;
      *a2 = v7;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002a680  mov     [rsp-40h+arg_0], rcx
0x18002a685  push    rbp
0x18002a686  push    rbx
0x18002a687  push    rsi
0x18002a688  push    rdi
0x18002a689  push    r12
0x18002a68b  push    r13
0x18002a68d  push    r14
0x18002a68f  push    r15
0x18002a691  mov     rbp, rsp
0x18002a694  sub     rsp, 38h
0x18002a698  mov     r12, r8
0x18002a69b  mov     r13, rdx
0x18002a69e  mov     rbx, rcx
0x18002a6a1  xor     edi, edi
0x18002a6a3  mov     [rdx], rdi
0x18002a6a6  mov     [r8], edi
0x18002a6a9  mov     dword ptr [rbp+arg_8], edi
0x18002a6ac  mov     rcx, [rcx+40h]
0x18002a6b0  mov     rax, [rcx]
0x18002a6b3  lea     rdx, [rbp+arg_8]
0x18002a6b7  mov     rax, [rax+38h]
0x18002a6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6c0  mov     r15d, eax
0x18002a6c3  test    eax, eax
0x18002a6c5  js      loc_18002A842
0x18002a6cb  mov     eax, dword ptr [rbp+arg_8]
0x18002a6ce  test    eax, eax
0x18002a6d0  jz      loc_18002A842
0x18002a6d6  mov     esi, edi
0x18002a6d8  mov     [rbp+string], rdi
0x18002a6dc  mov     [rbp+arg_18], rdi
0x18002a6e0  mov     ecx, eax; unsigned __int64
0x18002a6e2  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18002a6e6  lea     edx, [rdi+8]; unsigned __int64
0x18002a6e9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a6ee  mov     r15d, eax
0x18002a6f1  test    eax, eax
0x18002a6f3  js      short loc_18002A70C
0x18002a6f5  lea     r9, [rbp+string]; void **
0x18002a6f9  mov     r8, [rbp+arg_18]; unsigned __int64
0x18002a6fd  lea     edx, [rdi+1]; unsigned int
0x18002a700  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002a705  mov     r15d, eax
0x18002a708  mov     rsi, [rbp+string]
0x18002a70c  test    r15d, r15d
0x18002a70f  js      loc_18002A842
0x18002a715  mov     r14d, edi
0x18002a718  cmp     r14d, dword ptr [rbp+arg_8]
0x18002a71c  jnb     loc_18002A83A
0x18002a722  mov     [rbp+arg_18], rdi
0x18002a726  mov     rdi, [rbx+40h]
0x18002a72a  mov     rax, [rdi]
0x18002a72d  mov     rbx, [rax+30h]
0x18002a731  lea     rcx, [rbp+arg_18]
0x18002a735  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a73a  lea     r8, [rbp+arg_18]
0x18002a73e  mov     edx, r14d
0x18002a741  mov     rcx, rdi
0x18002a744  mov     rax, rbx
0x18002a747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a74c  xor     edi, edi
0x18002a74e  test    eax, eax
0x18002a750  js      loc_18002A7DF
0x18002a756  mov     [rbp+string], rdi
0x18002a75a  mov     rdi, [rbp+arg_18]
0x18002a75e  mov     rax, [rdi]
0x18002a761  mov     rbx, [rax+30h]
0x18002a765  xor     ecx, ecx; string
0x18002a767  call    cs:__imp_WindowsDeleteString
0x18002a76d  mov     [rbp+string], 0
0x18002a775  lea     rdx, [rbp+string]
0x18002a779  mov     rcx, rdi
0x18002a77c  mov     rax, rbx
0x18002a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a784  mov     ebx, eax
0x18002a786  xor     edi, edi
0x18002a788  test    eax, eax
0x18002a78a  js      short loc_18002A7BC
0x18002a78c  mov     eax, r14d
0x18002a78f  lea     rbx, [rsi+rax*8]
0x18002a793  xor     edx, edx; length
0x18002a795  mov     rcx, [rbp+string]; string
0x18002a799  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a79f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002a7a3  inc     r9
0x18002a7a6  cmp     [rax+r9*2], di
0x18002a7ab  jnz     short loc_18002A7A3
0x18002a7ad  mov     [rsp+38h+var_10], rbx
0x18002a7b2  mov     r8, rax
0x18002a7b5  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002a7ba  mov     ebx, eax
0x18002a7bc  mov     rcx, [rbp+string]; string
0x18002a7c0  call    cs:__imp_WindowsDeleteString
0x18002a7c6  test    ebx, ebx
0x18002a7c8  js      short loc_18002A7DF
0x18002a7ca  lea     rcx, [rbp+arg_18]
0x18002a7ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a7d3  inc     r14d
0x18002a7d6  mov     rbx, [rbp+arg_0]
0x18002a7da  jmp     loc_18002A718
0x18002a7df  mov     r10, rsi
0x18002a7e2  mov     rsi, rdi
0x18002a7e5  mov     [rbp+string], rdi
0x18002a7e9  mov     [rbp+arg_0], rdi
0x18002a7ed  mov     ecx, r14d; unsigned __int64
0x18002a7f0  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x18002a7f4  mov     edx, 8; unsigned __int64
0x18002a7f9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a7fe  mov     ebx, eax
0x18002a800  test    eax, eax
0x18002a802  js      short loc_18002A81F
0x18002a804  lea     rax, [rbp+string]
0x18002a808  mov     [rsp+38h+var_18], rax; void **
0x18002a80d  mov     r9, [rbp+arg_0]; unsigned __int64
0x18002a811  mov     r8, r10; void *
0x18002a814  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18002a819  mov     ebx, eax
0x18002a81b  mov     rsi, [rbp+string]
0x18002a81f  lea     rcx, [rbp+arg_18]
0x18002a823  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a828  test    ebx, ebx
0x18002a82a  jns     short loc_18002A83A
0x18002a82c  mov     r15d, ebx
0x18002a82f  mov     rcx, rsi; pv
0x18002a832  call    cs:__imp_CoTaskMemFree
0x18002a838  jmp     short loc_18002A842
0x18002a83a  mov     [r12], r14d
0x18002a83e  mov     [r13+0], rsi
0x18002a842  mov     eax, r15d
0x18002a845  add     rsp, 38h
0x18002a849  pop     r15
0x18002a84b  pop     r14
0x18002a84d  pop     r13
0x18002a84f  pop     r12
0x18002a851  pop     rdi
0x18002a852  pop     rsi
0x18002a853  pop     rbx
0x18002a854  pop     rbp
0x18002a855  retn
```
