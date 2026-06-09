# MvDsGetInfoFromMcc(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x180006eb0`
- end: `0x18000703b`
- name: `?MvDsGetInfoFromMcc@@YAJPEBG0PEAGK@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006e2c`
- `0x180006eb0`
- `0x180007818`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180006f47`
- `XmlLite!CreateXmlReader` at `0x180006f47`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180006f28`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180006f28`

## pseudocode

```c
__int64 __fastcall MvDsGetInfoFromMcc(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  HRESULT v8; // ebx
  void *ppvObject; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  IStream *ppstm; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszFile[264]; // [rsp+50h] [rbp-B0h] BYREF

  ppstm = 0;
  ppvObject = 0;
  *a3 = 0;
  v11 = 0;
  v8 = MVGetMccLookupTablePath(pszFile, (unsigned int)a2);
  if ( v8 >= 0 )
  {
    v8 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
    if ( v8 >= 0 )
    {
      v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
          if ( v8 >= 0 )
          {
            while ( 1 )
            {
              v8 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v11);
              if ( v8 )
                break;
              if ( v11 == 1 )
              {
                v8 = ProcessRowElement(ppvObject, a1, a2, a3, a4);
                if ( v8 < 0 )
                  goto LABEL_13;
                if ( *a3 )
                {
                  v8 = 0;
                  goto LABEL_13;
                }
              }
            }
            if ( v8 == 1 )
              v8 = -2147024894;
          }
        }
      }
    }
  }
LABEL_13:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( ppstm )
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006eb0  mov     [rsp-8+arg_0], rbx
0x180006eb5  push    rbp
0x180006eb6  push    rsi
0x180006eb7  push    rdi
0x180006eb8  push    r14
0x180006eba  push    r15
0x180006ebc  lea     rbp, [rsp-170h]
0x180006ec4  sub     rsp, 270h
0x180006ecb  mov     rax, cs:__security_cookie
0x180006ed2  xor     rax, rsp
0x180006ed5  mov     [rbp+190h+var_30], rax
0x180006edc  mov     r14, rcx
0x180006edf  mov     [rsp+290h+ppstm], 0
0x180006ee8  xor     eax, eax
0x180006eea  mov     [rsp+290h+ppvObject], 0
0x180006ef3  lea     rcx, [rsp+290h+pszFile]; unsigned __int16 *
0x180006ef8  mov     [r8], ax
0x180006efc  mov     esi, r9d
0x180006eff  mov     [rsp+290h+var_258], 0
0x180006f07  mov     rdi, r8
0x180006f0a  mov     r15, rdx
0x180006f0d  call    ?MVGetMccLookupTablePath@@YAJPEAGK@Z; MVGetMccLookupTablePath(ushort *,ulong)
0x180006f12  mov     ebx, eax
0x180006f14  test    eax, eax
0x180006f16  js      loc_180006FE7
0x180006f1c  lea     r8, [rsp+290h+ppstm]; ppstm
0x180006f21  xor     edx, edx; grfMode
0x180006f23  lea     rcx, [rsp+290h+pszFile]; pszFile
0x180006f28  call    cs:__imp_SHCreateStreamOnFileW
0x180006f2e  mov     ebx, eax
0x180006f30  test    eax, eax
0x180006f32  js      loc_180006FE7
0x180006f38  xor     r8d, r8d; pMalloc
0x180006f3b  lea     rdx, [rsp+290h+ppvObject]; ppvObject
0x180006f40  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180006f47  call    cs:__imp_CreateXmlReader
0x180006f4d  mov     ebx, eax
0x180006f4f  test    eax, eax
0x180006f51  js      loc_180006FE7
0x180006f57  mov     rcx, [rsp+290h+ppvObject]
0x180006f5c  xor     r8d, r8d
0x180006f5f  mov     rax, [rcx]
0x180006f62  lea     edx, [r8+4]
0x180006f66  mov     rax, [rax+28h]
0x180006f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6f  mov     ebx, eax
0x180006f71  test    eax, eax
0x180006f73  js      short loc_180006FE7
0x180006f75  mov     rcx, [rsp+290h+ppvObject]
0x180006f7a  mov     rdx, [rsp+290h+ppstm]
0x180006f7f  mov     rax, [rcx]
0x180006f82  mov     rax, [rax+18h]
0x180006f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f8b  mov     ebx, eax
0x180006f8d  test    eax, eax
0x180006f8f  js      short loc_180006FE7
0x180006f91  mov     rcx, [rsp+290h+ppvObject]
0x180006f96  lea     rdx, [rsp+290h+var_258]
0x180006f9b  mov     rax, [rcx]
0x180006f9e  mov     rax, [rax+30h]
0x180006fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa7  mov     ebx, eax
0x180006fa9  test    eax, eax
0x180006fab  jnz     short loc_180006FDC
0x180006fad  cmp     [rsp+290h+var_258], 1
0x180006fb2  jnz     short loc_180006F91
0x180006fb4  mov     rcx, [rsp+290h+ppvObject]
0x180006fb9  mov     r9, rdi
0x180006fbc  mov     r8, r15
0x180006fbf  mov     [rsp+290h+var_270], esi
0x180006fc3  mov     rdx, r14
0x180006fc6  call    ProcessRowElement
0x180006fcb  mov     ebx, eax
0x180006fcd  test    eax, eax
0x180006fcf  js      short loc_180006FE7
0x180006fd1  xor     eax, eax
0x180006fd3  cmp     ax, [rdi]
0x180006fd6  jz      short loc_180006F91
0x180006fd8  xor     ebx, ebx
0x180006fda  jmp     short loc_180006FE7
0x180006fdc  cmp     ebx, 1
0x180006fdf  mov     eax, 80070002h
0x180006fe4  cmovz   ebx, eax
0x180006fe7  mov     rcx, [rsp+290h+ppvObject]
0x180006fec  test    rcx, rcx
0x180006fef  jz      short loc_180006FFD
0x180006ff1  mov     rax, [rcx]
0x180006ff4  mov     rax, [rax+10h]
0x180006ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffd  mov     rcx, [rsp+290h+ppstm]
0x180007002  test    rcx, rcx
0x180007005  jz      short loc_180007013
0x180007007  mov     rax, [rcx]
0x18000700a  mov     rax, [rax+10h]
0x18000700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007013  mov     eax, ebx
0x180007015  mov     rcx, [rbp+190h+var_30]
0x18000701c  xor     rcx, rsp; StackCookie
0x18000701f  call    __security_check_cookie
0x180007024  mov     rbx, [rsp+290h+arg_0]
0x18000702c  add     rsp, 270h
0x180007033  pop     r15
0x180007035  pop     r14
0x180007037  pop     rdi
0x180007038  pop     rsi
0x180007039  pop     rbp
0x18000703a  retn
```
