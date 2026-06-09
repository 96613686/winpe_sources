# SemanticsUM::SchemaBinary::_SaveToMemoryMappedCache(wchar_t const *,IStream *)

- ea: `0x180026868`
- end: `0x180026ade`
- name: `?_SaveToMemoryMappedCache@SchemaBinary@SemanticsUM@@AEBAJPEB_WPEAUIStream@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(SemanticsUM::SchemaBinary *this, wchar_t *, struct IStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027f40`

## callees

- `0x18002683c`
- `0x180026868`
- `0x180028580`
- `0x18002aee0`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800268c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800268c1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180026971`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180026971`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180026a64`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180026a64`

## pseudocode

```c
__int64 __fastcall SemanticsUM::SchemaBinary::_SaveToMemoryMappedCache(
        SemanticsUM::SchemaBinary *this,
        wchar_t *a2,
        struct IStream *a3)
{
  const wchar_t *v5; // rdx
  HRESULT v6; // ebx
  unsigned int v7; // r8d
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, unsigned int *, __int64, __int64, _QWORD, int *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rcx
  LPVOID v16; // rcx
  __int64 v18; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-9h] BYREF
  ULARGE_INTEGER pui; // [rsp+68h] [rbp-1h] BYREF
  int v24; // [rsp+70h] [rbp+7h] BYREF
  __int64 v25; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v26; // [rsp+80h] [rbp+17h] BYREF
  __int64 v27; // [rsp+84h] [rbp+1Bh]
  int v28; // [rsp+8Ch] [rbp+23h]

  ppv = 0;
  Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&ppv);
  v6 = CoCreateInstance(&CLSID_MemoryMappedCacheMgr, 0, 1u, &GUID_ecf31d61_e474_453c_bee7_de68e441c6d0, &ppv);
  if ( v6 >= 0 )
  {
    v27 = *(_QWORD *)&GUID_StructuredQueryCache.Data2;
    v28 = *(_DWORD *)&GUID_StructuredQueryCache.Data4[4];
    v26 = 314159269 * HashFn::HashStringNoCase((HashFn *)a2, v5, v7) % 0x3B9ACA07;
    v24 = 0;
    v20 = 0;
    v8 = ppv;
    v9 = *(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64, __int64, _QWORD, int *, __int64 *))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v20);
    v6 = v9(v8, &v26, 3, 10, 0, &v24, &v20);
    if ( v6 >= 0 )
    {
      pui.QuadPart = 0;
      v6 = IStream_Size(a3, &pui);
      if ( v6 >= 0 )
      {
        v18 = 0;
        v10 = v20;
        v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v20 + 40LL);
        Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v18);
        v6 = v11(v10, 0x100000, &v18);
        if ( v6 >= 0 )
        {
          v25 = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, &v25);
          if ( v6 >= 0 )
          {
            v21 = 0;
            v6 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, 32, &v21);
            if ( v6 >= 0 )
            {
              v12 = v21;
              v13 = v25;
              *(_DWORD *)(v21 + v25) = pui.LowPart;
              v19 = 0;
              v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v18 + 24LL))(
                     v18,
                     pui.LowPart,
                     &v19);
              if ( v6 >= 0 )
              {
                *(_DWORD *)(v12 + v13 + 4) = v19;
                v6 = ISequentialStream_Read(a3, v25 + v19, pui.LowPart);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 48LL))(v20, v18);
                  IStream_Reset(a3);
                }
              }
            }
          }
        }
        v14 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v16 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026868  mov     [rsp-8+arg_0], rbx
0x18002686d  push    rbp
0x18002686e  push    rsi
0x18002686f  push    rdi
0x180026870  push    r14
0x180026872  push    r15
0x180026874  lea     rbp, [rsp-37h]
0x180026879  sub     rsp, 0A0h
0x180026880  mov     rax, cs:__security_cookie
0x180026887  xor     rax, rsp
0x18002688a  mov     [rbp+57h+var_30], rax
0x18002688e  mov     rsi, r8
0x180026891  mov     rdi, rdx
0x180026894  xor     r15d, r15d
0x180026897  mov     [rbp+57h+var_60], r15
0x18002689b  lea     rcx, [rbp+57h+var_60]
0x18002689f  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x1800268a4  lea     rax, [rbp+57h+var_60]
0x1800268a8  mov     [rsp+0C0h+ppv], rax; ppv
0x1800268ad  lea     r9, _GUID_ecf31d61_e474_453c_bee7_de68e441c6d0; riid
0x1800268b4  xor     edx, edx; pUnkOuter
0x1800268b6  lea     r8d, [r15+1]; dwClsContext
0x1800268ba  lea     rcx, CLSID_MemoryMappedCacheMgr; rclsid
0x1800268c1  call    cs:__imp_CoCreateInstance
0x1800268c7  mov     ebx, eax
0x1800268c9  test    eax, eax
0x1800268cb  js      loc_180026A9F
0x1800268d1  movsd   xmm0, qword ptr cs:GUID_StructuredQueryCache.Data2
0x1800268d9  movsd   [rbp+57h+var_3C], xmm0
0x1800268de  mov     eax, dword ptr cs:GUID_StructuredQueryCache.Data4+4
0x1800268e4  mov     [rbp+57h+var_34], eax
0x1800268e7  mov     rcx, rdi; this
0x1800268ea  call    ?HashStringNoCase@HashFn@@YAKPEB_WK@Z; HashFn::HashStringNoCase(wchar_t const *,ulong)
0x1800268ef  imul    ecx, eax, 12B9B0A5h
0x1800268f5  mov     eax, 12E0BE63h
0x1800268fa  mul     ecx
0x1800268fc  mov     eax, ecx
0x1800268fe  sub     eax, edx
0x180026900  shr     eax, 1
0x180026902  add     eax, edx
0x180026904  shr     eax, 1Dh
0x180026907  imul    eax, 3B9ACA07h
0x18002690d  sub     ecx, eax
0x18002690f  mov     [rbp+57h+var_40], ecx
0x180026912  mov     [rbp+57h+var_50], r15d
0x180026916  mov     [rbp+57h+var_70], r15
0x18002691a  mov     rdi, [rbp+57h+var_60]
0x18002691e  mov     rax, [rdi]
0x180026921  mov     rbx, [rax+18h]
0x180026925  lea     rcx, [rbp+57h+var_70]
0x180026929  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x18002692e  lea     rax, [rbp+57h+var_70]
0x180026932  mov     [rsp+0C0h+var_90], rax
0x180026937  lea     rax, [rbp+57h+var_50]
0x18002693b  mov     [rsp+0C0h+var_98], rax
0x180026940  mov     [rsp+0C0h+ppv], r15
0x180026945  lea     r9d, [r15+0Ah]
0x180026949  lea     r8d, [r15+3]
0x18002694d  lea     rdx, [rbp+57h+var_40]
0x180026951  mov     rcx, rdi
0x180026954  mov     rax, rbx
0x180026957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002695c  mov     ebx, eax
0x18002695e  test    eax, eax
0x180026960  js      loc_180026A85
0x180026966  mov     qword ptr [rbp+57h+pui], r15
0x18002696a  lea     rdx, [rbp+57h+pui]; pui
0x18002696e  mov     rcx, rsi; pstm
0x180026971  call    cs:__imp_IStream_Size
0x180026977  mov     ebx, eax
0x180026979  test    eax, eax
0x18002697b  js      loc_180026A85
0x180026981  mov     [rbp+57h+var_80], r15
0x180026985  mov     rdi, [rbp+57h+var_70]
0x180026989  mov     rax, [rdi]
0x18002698c  mov     rbx, [rax+28h]
0x180026990  lea     rcx, [rbp+57h+var_80]
0x180026994  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x180026999  lea     r8, [rbp+57h+var_80]
0x18002699d  mov     edx, 100000h
0x1800269a2  mov     rcx, rdi
0x1800269a5  mov     rax, rbx
0x1800269a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ad  mov     ebx, eax
0x1800269af  test    eax, eax
0x1800269b1  js      loc_180026A6B
0x1800269b7  mov     [rbp+57h+var_48], r15
0x1800269bb  mov     rcx, [rbp+57h+var_80]
0x1800269bf  mov     rax, [rcx]
0x1800269c2  lea     rdx, [rbp+57h+var_48]
0x1800269c6  mov     rax, [rax+28h]
0x1800269ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269cf  mov     ebx, eax
0x1800269d1  test    eax, eax
0x1800269d3  js      loc_180026A6B
0x1800269d9  mov     [rbp+57h+var_68], r15d
0x1800269dd  mov     rcx, [rbp+57h+var_80]
0x1800269e1  mov     rax, [rcx]
0x1800269e4  lea     r8, [rbp+57h+var_68]
0x1800269e8  lea     edx, [r15+20h]
0x1800269ec  mov     rax, [rax+18h]
0x1800269f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269f5  mov     ebx, eax
0x1800269f7  test    eax, eax
0x1800269f9  js      short loc_180026A6B
0x1800269fb  mov     edi, [rbp+57h+var_68]
0x1800269fe  mov     r14, [rbp+57h+var_48]
0x180026a02  mov     eax, dword ptr [rbp+57h+pui]
0x180026a05  mov     [rdi+r14], eax
0x180026a09  mov     [rbp+57h+var_78], r15d
0x180026a0d  mov     rcx, [rbp+57h+var_80]
0x180026a11  mov     rax, [rcx]
0x180026a14  lea     r8, [rbp+57h+var_78]
0x180026a18  mov     edx, dword ptr [rbp+57h+pui]
0x180026a1b  mov     rax, [rax+18h]
0x180026a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a24  mov     ebx, eax
0x180026a26  test    eax, eax
0x180026a28  js      short loc_180026A6B
0x180026a2a  mov     eax, [rbp+57h+var_78]
0x180026a2d  mov     [rdi+r14+4], eax
0x180026a32  mov     edx, [rbp+57h+var_78]
0x180026a35  add     rdx, [rbp+57h+var_48]
0x180026a39  mov     r8d, dword ptr [rbp+57h+pui]
0x180026a3d  mov     rcx, rsi
0x180026a40  call    ISequentialStream_Read
0x180026a45  mov     ebx, eax
0x180026a47  test    eax, eax
0x180026a49  js      short loc_180026A6B
0x180026a4b  mov     rcx, [rbp+57h+var_70]
0x180026a4f  mov     rax, [rcx]
0x180026a52  mov     rdx, [rbp+57h+var_80]
0x180026a56  mov     rax, [rax+30h]
0x180026a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a5f  mov     ebx, eax
0x180026a61  mov     rcx, rsi; pstm
0x180026a64  call    cs:__imp_IStream_Reset
0x180026a6a  nop
0x180026a6b  mov     rcx, [rbp+57h+var_80]
0x180026a6f  test    rcx, rcx
0x180026a72  jz      short loc_180026A85
0x180026a74  mov     [rbp+57h+var_80], r15
0x180026a78  mov     rax, [rcx]
0x180026a7b  mov     rax, [rax+10h]
0x180026a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a84  nop
0x180026a85  mov     rcx, [rbp+57h+var_70]
0x180026a89  test    rcx, rcx
0x180026a8c  jz      short loc_180026A9F
0x180026a8e  mov     [rbp+57h+var_70], r15
0x180026a92  mov     rax, [rcx]
0x180026a95  mov     rax, [rax+10h]
0x180026a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a9e  nop
0x180026a9f  mov     rcx, [rbp+57h+var_60]
0x180026aa3  test    rcx, rcx
0x180026aa6  jz      short loc_180026AB9
0x180026aa8  mov     [rbp+57h+var_60], r15
0x180026aac  mov     rax, [rcx]
0x180026aaf  mov     rax, [rax+10h]
0x180026ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ab8  nop
0x180026ab9  mov     eax, ebx
0x180026abb  mov     rcx, [rbp+57h+var_30]
0x180026abf  xor     rcx, rsp; StackCookie
0x180026ac2  call    __security_check_cookie
0x180026ac7  mov     rbx, [rsp+0C0h+arg_0]
0x180026acf  add     rsp, 0A0h
0x180026ad6  pop     r15
0x180026ad8  pop     r14
0x180026ada  pop     rdi
0x180026adb  pop     rsi
0x180026adc  pop     rbp
0x180026add  retn
```
