# CStartupImpactHelper::GetStartupImpact(void)

- ea: `0x1800d9b1c`
- end: `0x1800d9d97`
- name: `?GetStartupImpact@CStartupImpactHelper@@AEAAJXZ`
- size: `635`
- prototype: `__int64 __fastcall(CStartupImpactHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800d4ac8`

## callees

- `0x1800d9908`
- `0x1800d9b1c`
- `0x1800d9e84`
- `0x1800d9f98`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9c46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9c74`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9c46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9c74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9d31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d9d3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d9d3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9c96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d9c96`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800d9b89`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800d9b89`
- `XmlLite!CreateXmlReader` at `0x1800d9ba7`
- `XmlLite!CreateXmlReader` at `0x1800d9ba7`

## pseudocode

```c
__int64 __fastcall CStartupImpactHelper::GetStartupImpact(CStartupImpactHelper *this)
{
  int SIFileNames; // eax
  HRESULT ProcessAttributes; // ebx
  int v4; // r14d
  HANDLE ProcessHeap; // rax
  struct _STARTUPIMPACT *v6; // rax
  struct _STARTUPIMPACT *v7; // rdi
  CStartupImpactHelper *v8; // rcx
  CStartupImpactHelper *v9; // rcx
  __int64 v10; // rax
  HANDLE v11; // rax
  __int64 result; // rax
  IStream *ppstm; // [rsp+20h] [rbp-10h] BYREF
  int v14; // [rsp+68h] [rbp+38h] BYREF
  void *ppvObject; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  ppstm = 0;
  ppvObject = 0;
  v14 = 0;
  v16 = 0;
  SIFileNames = CStartupImpactHelper::GetSIFileNames(this);
  ProcessAttributes = SIFileNames;
  if ( SIFileNames >= 0 )
  {
    if ( SIFileNames == 1 )
    {
      ProcessAttributes = 0;
    }
    else if ( *((_DWORD *)this + 17) == -1 )
    {
      ProcessAttributes = -2147467259;
    }
    else
    {
      ProcessAttributes = SHCreateStreamOnFileW(*((LPCWSTR *)this + *((int *)this + 17) + 3), 0x20u, &ppstm);
      if ( ProcessAttributes >= 0 )
      {
        ProcessAttributes = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
        if ( ProcessAttributes >= 0 )
        {
          ProcessAttributes = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
          if ( ProcessAttributes >= 0 )
          {
            v4 = 0;
            ProcessAttributes = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(
                                  ppvObject,
                                  ppstm);
            if ( ProcessAttributes >= 0 )
            {
              while ( 1 )
              {
                ProcessAttributes = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(
                                      ppvObject,
                                      &v14);
                if ( ProcessAttributes )
                  break;
                if ( v14 == 1 )
                {
                  if ( (*(int (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                         ppvObject,
                         &v16,
                         0) >= 0 )
                  {
                    if ( (unsigned int)_o__wcsicmp(v16, L"Process") )
                    {
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 88LL))(ppvObject);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
                    }
                    else
                    {
                      ProcessHeap = GetProcessHeap();
                      v6 = (struct _STARTUPIMPACT *)HeapAlloc(ProcessHeap, 8u, 0x840u);
                      v7 = v6;
                      if ( !v6 )
                      {
                        ProcessAttributes = -2147024882;
                        goto LABEL_26;
                      }
                      *((_QWORD *)v6 + 1) = v6;
                      *(_QWORD *)v6 = v6;
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 88LL))(ppvObject);
                      ProcessAttributes = CStartupImpactHelper::ReadProcessAttributes(
                                            v8,
                                            (struct IXmlReader *)ppvObject,
                                            v7);
                      if ( ProcessAttributes < 0
                        || (ProcessAttributes = CStartupImpactHelper::ReadProcessInfo(
                                                  v9,
                                                  (struct IXmlReader *)ppvObject,
                                                  v7),
                            ProcessAttributes < 0) )
                      {
                        v11 = GetProcessHeap();
                        HeapFree(v11, 0, v7);
                        goto LABEL_26;
                      }
                      v10 = *(_QWORD *)this;
                      if ( *(CStartupImpactHelper **)(*(_QWORD *)this + 8LL) != this )
                        __fastfail(3u);
                      *(_QWORD *)v7 = v10;
                      ++v4;
                      *((_QWORD *)v7 + 1) = this;
                      *(_QWORD *)(v10 + 8) = v7;
                      *(_QWORD *)this = v7;
                    }
                  }
                }
                else if ( v14 == 15 )
                {
                  (*(void (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &v16, 0);
                  _o__wcsicmp(v16, L"StartupData");
                }
              }
              *((_DWORD *)this + 4) = v4;
            }
          }
        }
      }
    }
  }
LABEL_26:
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
  result = 0;
  if ( ProcessAttributes != 1 )
    return (unsigned int)ProcessAttributes;
  return result;
}

```

## disassembly

```asm
0x1800d9b1c  push    rbp
0x1800d9b1e  push    rbx
0x1800d9b1f  push    rsi
0x1800d9b20  push    rdi
0x1800d9b21  push    r14
0x1800d9b23  mov     rbp, rsp
0x1800d9b26  sub     rsp, 30h
0x1800d9b2a  mov     rsi, rcx
0x1800d9b2d  mov     [rbp+ppstm], 0
0x1800d9b35  mov     [rbp+ppvObject], 0
0x1800d9b3d  mov     [rbp+arg_8], 0
0x1800d9b44  mov     [rbp+arg_18], 0
0x1800d9b4c  call    ?GetSIFileNames@CStartupImpactHelper@@AEAAJXZ; CStartupImpactHelper::GetSIFileNames(void)
0x1800d9b51  mov     ebx, eax
0x1800d9b53  test    eax, eax
0x1800d9b55  js      loc_1800D9D52
0x1800d9b5b  cmp     eax, 1
0x1800d9b5e  jnz     short loc_1800D9B67
0x1800d9b60  xor     ebx, ebx
0x1800d9b62  jmp     loc_1800D9D52
0x1800d9b67  cmp     dword ptr [rsi+44h], 0FFFFFFFFh
0x1800d9b6b  jnz     short loc_1800D9B77
0x1800d9b6d  mov     ebx, 80004005h
0x1800d9b72  jmp     loc_1800D9D52
0x1800d9b77  movsxd  rcx, dword ptr [rsi+44h]
0x1800d9b7b  lea     r8, [rbp+ppstm]; ppstm
0x1800d9b7f  mov     edx, 20h ; ' '; grfMode
0x1800d9b84  mov     rcx, [rsi+rcx*8+18h]; pszFile
0x1800d9b89  call    cs:__imp_SHCreateStreamOnFileW
0x1800d9b8f  mov     ebx, eax
0x1800d9b91  test    eax, eax
0x1800d9b93  js      loc_1800D9D52
0x1800d9b99  xor     r8d, r8d; pMalloc
0x1800d9b9c  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800d9ba0  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800d9ba7  call    cs:__imp_CreateXmlReader
0x1800d9bad  mov     ebx, eax
0x1800d9baf  test    eax, eax
0x1800d9bb1  js      loc_1800D9D52
0x1800d9bb7  mov     rcx, [rbp+ppvObject]
0x1800d9bbb  xor     r8d, r8d
0x1800d9bbe  mov     rax, [rcx]
0x1800d9bc1  lea     edx, [r8+4]
0x1800d9bc5  mov     rax, [rax+28h]
0x1800d9bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bce  mov     ebx, eax
0x1800d9bd0  test    eax, eax
0x1800d9bd2  js      loc_1800D9D52
0x1800d9bd8  mov     rcx, [rbp+ppvObject]
0x1800d9bdc  xor     r14d, r14d
0x1800d9bdf  mov     rdx, [rbp+ppstm]
0x1800d9be3  mov     rax, [rcx]
0x1800d9be6  mov     rax, [rax+18h]
0x1800d9bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bef  mov     ebx, eax
0x1800d9bf1  test    eax, eax
0x1800d9bf3  js      loc_1800D9D52
0x1800d9bf9  mov     rcx, [rbp+ppvObject]
0x1800d9bfd  lea     rdx, [rbp+arg_8]
0x1800d9c01  mov     rax, [rcx]
0x1800d9c04  mov     rax, [rax+30h]
0x1800d9c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c0d  mov     ebx, eax
0x1800d9c0f  test    eax, eax
0x1800d9c11  jnz     loc_1800D9D4E
0x1800d9c17  mov     ecx, [rbp+arg_8]
0x1800d9c1a  sub     ecx, 1
0x1800d9c1d  jz      short loc_1800D9C4E
0x1800d9c1f  cmp     ecx, 0Eh
0x1800d9c22  jnz     short loc_1800D9BF9
0x1800d9c24  mov     rcx, [rbp+ppvObject]
0x1800d9c28  lea     rdx, [rbp+arg_18]
0x1800d9c2c  xor     r8d, r8d
0x1800d9c2f  mov     rax, [rcx]
0x1800d9c32  mov     rax, [rax+70h]
0x1800d9c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c3b  mov     rcx, [rbp+arg_18]
0x1800d9c3f  lea     rdx, aStartupdata; "StartupData"
0x1800d9c46  call    cs:__imp__o__wcsicmp
0x1800d9c4c  jmp     short loc_1800D9BF9
0x1800d9c4e  mov     rcx, [rbp+ppvObject]
0x1800d9c52  lea     rdx, [rbp+arg_18]
0x1800d9c56  xor     r8d, r8d
0x1800d9c59  mov     rax, [rcx]
0x1800d9c5c  mov     rax, [rax+70h]
0x1800d9c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c65  test    eax, eax
0x1800d9c67  js      short loc_1800D9BF9
0x1800d9c69  mov     rcx, [rbp+arg_18]
0x1800d9c6d  lea     rdx, aProcess; "Process"
0x1800d9c74  call    cs:__imp__o__wcsicmp
0x1800d9c7a  test    eax, eax
0x1800d9c7c  jnz     loc_1800D9D02
0x1800d9c82  call    cs:__imp_GetProcessHeap
0x1800d9c88  mov     edx, 8; dwFlags
0x1800d9c8d  mov     r8d, 840h; dwBytes
0x1800d9c93  mov     rcx, rax; hHeap
0x1800d9c96  call    cs:__imp_HeapAlloc
0x1800d9c9c  mov     rdi, rax
0x1800d9c9f  test    rax, rax
0x1800d9ca2  jz      loc_1800D9D47
0x1800d9ca8  mov     [rax+8], rax
0x1800d9cac  mov     [rax], rax
0x1800d9caf  mov     rcx, [rbp+ppvObject]
0x1800d9cb3  mov     rax, [rcx]
0x1800d9cb6  mov     rax, [rax+58h]
0x1800d9cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9cbf  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1800d9cc3  mov     r8, rdi; struct _STARTUPIMPACT *
0x1800d9cc6  call    ?ReadProcessAttributes@CStartupImpactHelper@@AEAAJPEAUIXmlReader@@PEAU_STARTUPIMPACT@@@Z; CStartupImpactHelper::ReadProcessAttributes(IXmlReader *,_STARTUPIMPACT *)
0x1800d9ccb  mov     ebx, eax
0x1800d9ccd  test    eax, eax
0x1800d9ccf  js      short loc_1800D9D31
0x1800d9cd1  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1800d9cd5  mov     r8, rdi; struct _STARTUPIMPACT *
0x1800d9cd8  call    ?ReadProcessInfo@CStartupImpactHelper@@AEAAJPEAUIXmlReader@@PEAU_STARTUPIMPACT@@@Z; CStartupImpactHelper::ReadProcessInfo(IXmlReader *,_STARTUPIMPACT *)
0x1800d9cdd  mov     ebx, eax
0x1800d9cdf  test    eax, eax
0x1800d9ce1  js      short loc_1800D9D31
0x1800d9ce3  mov     rax, [rsi]
0x1800d9ce6  cmp     [rax+8], rsi
0x1800d9cea  jnz     short loc_1800D9D2A
0x1800d9cec  mov     [rdi], rax
0x1800d9cef  inc     r14d
0x1800d9cf2  mov     [rdi+8], rsi
0x1800d9cf6  mov     [rax+8], rdi
0x1800d9cfa  mov     [rsi], rdi
0x1800d9cfd  jmp     loc_1800D9BF9
0x1800d9d02  mov     rcx, [rbp+ppvObject]
0x1800d9d06  mov     rax, [rcx]
0x1800d9d09  mov     rax, [rax+58h]
0x1800d9d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d12  mov     rcx, [rbp+ppvObject]
0x1800d9d16  mov     rax, [rcx]
0x1800d9d19  mov     rax, [rax+0A0h]
0x1800d9d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d25  jmp     loc_1800D9BF9
0x1800d9d2a  mov     ecx, 3
0x1800d9d2f  int     29h; Win8: RtlFailFast(ecx)
0x1800d9d31  call    cs:__imp_GetProcessHeap
0x1800d9d37  mov     r8, rdi; lpMem
0x1800d9d3a  xor     edx, edx; dwFlags
0x1800d9d3c  mov     rcx, rax; hHeap
0x1800d9d3f  call    cs:__imp_HeapFree
0x1800d9d45  jmp     short loc_1800D9D52
0x1800d9d47  mov     ebx, 8007000Eh
0x1800d9d4c  jmp     short loc_1800D9D52
0x1800d9d4e  mov     [rsi+10h], r14d
0x1800d9d52  mov     rcx, [rbp+ppvObject]
0x1800d9d56  test    rcx, rcx
0x1800d9d59  jz      short loc_1800D9D6F
0x1800d9d5b  mov     rax, [rcx]
0x1800d9d5e  mov     rax, [rax+10h]
0x1800d9d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d67  mov     [rbp+ppvObject], 0
0x1800d9d6f  mov     rcx, [rbp+ppstm]
0x1800d9d73  test    rcx, rcx
0x1800d9d76  jz      short loc_1800D9D84
0x1800d9d78  mov     rax, [rcx]
0x1800d9d7b  mov     rax, [rax+10h]
0x1800d9d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d84  xor     eax, eax
0x1800d9d86  cmp     ebx, 1
0x1800d9d89  cmovnz  eax, ebx
0x1800d9d8c  add     rsp, 30h
0x1800d9d90  pop     r14
0x1800d9d92  pop     rdi
0x1800d9d93  pop     rsi
0x1800d9d94  pop     rbx
0x1800d9d95  pop     rbp
0x1800d9d96  retn
```
