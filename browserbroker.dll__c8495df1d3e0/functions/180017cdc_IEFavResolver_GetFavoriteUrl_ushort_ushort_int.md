# IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)

- ea: `0x180017cdc`
- end: `0x180017dde`
- name: `?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z`
- size: `258`
- prototype: `int(IEFavResolver *__hidden this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018528`
- `0x180018c10`
- `0x180019088`
- `0x1800192f8`
- `0x18001a80c`

## callees

- `0x180006cc4`
- `0x18000d17c`
- `0x180017cdc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dc3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017d1f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017d1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IEFavResolver::GetFavoriteUrl(IEFavResolver *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+28h] BYREF

  pv[0] = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_InternetShortcut, 0, 1u, &GUID_0000010b_0000_0000_c000_000000000046, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)ppv + 40LL))(ppv, a2, 0);
    if ( v5 >= 0 )
    {
      v6 = 0;
      v8 = 0;
      if ( ppv )
      {
        (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &GUID_cabb0da0_da57_11cf_9974_0020afd79762, &v8);
        v6 = v8;
      }
      if ( v6 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v6 + 32LL))(v6, pv);
        if ( v5 < 0 )
        {
LABEL_10:
          ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v8);
          goto LABEL_11;
        }
        if ( pv[0] )
        {
          v5 = StringCchCopyW(a3, 0x104u, (const unsigned __int16 *)pv[0]);
          goto LABEL_10;
        }
      }
      v5 = -2147467259;
      goto LABEL_10;
    }
  }
LABEL_11:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017cdc  mov     [rsp-20h+arg_0], rcx
0x180017ce1  push    rbp
0x180017ce2  push    rbx
0x180017ce3  push    rsi
0x180017ce4  push    rdi
0x180017ce5  mov     rbp, rsp
0x180017ce8  sub     rsp, 48h
0x180017cec  mov     rsi, r8
0x180017cef  mov     rdi, rdx
0x180017cf2  mov     [rbp+pv], 0
0x180017cfa  mov     [rbp+arg_0], 0
0x180017d02  lea     rax, [rbp+arg_0]
0x180017d06  mov     [rsp+48h+ppv], rax; ppv
0x180017d0b  lea     r9, _GUID_0000010b_0000_0000_c000_000000000046; riid
0x180017d12  xor     edx, edx; pUnkOuter
0x180017d14  lea     r8d, [rdx+1]; dwClsContext
0x180017d18  lea     rcx, CLSID_InternetShortcut; rclsid
0x180017d1f  call    cs:__imp_CoCreateInstance
0x180017d25  mov     ebx, eax
0x180017d27  test    eax, eax
0x180017d29  js      loc_180017DBA
0x180017d2f  mov     rcx, [rbp+arg_0]
0x180017d33  mov     rax, [rcx]
0x180017d36  xor     r8d, r8d
0x180017d39  mov     rdx, rdi
0x180017d3c  mov     rax, [rax+28h]
0x180017d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d45  mov     ebx, eax
0x180017d47  test    eax, eax
0x180017d49  js      short loc_180017DBA
0x180017d4b  mov     r9, [rbp+arg_0]
0x180017d4f  xor     ecx, ecx
0x180017d51  mov     [rbp+var_18], rcx
0x180017d55  test    r9, r9
0x180017d58  jz      short loc_180017D77
0x180017d5a  mov     rax, [r9]
0x180017d5d  lea     r8, [rbp+var_18]
0x180017d61  lea     rdx, _GUID_cabb0da0_da57_11cf_9974_0020afd79762
0x180017d68  mov     rcx, r9
0x180017d6b  mov     rax, [rax]
0x180017d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d73  mov     rcx, [rbp+var_18]
0x180017d77  test    rcx, rcx
0x180017d7a  jz      short loc_180017DAC
0x180017d7c  mov     rax, [rcx]
0x180017d7f  lea     rdx, [rbp+pv]
0x180017d83  mov     rax, [rax+20h]
0x180017d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d8c  mov     ebx, eax
0x180017d8e  test    eax, eax
0x180017d90  js      short loc_180017DB1
0x180017d92  mov     r8, [rbp+pv]; unsigned __int16 *
0x180017d96  test    r8, r8
0x180017d99  jz      short loc_180017DAC
0x180017d9b  mov     edx, 104h; unsigned __int64
0x180017da0  mov     rcx, rsi; unsigned __int16 *
0x180017da3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017da8  mov     ebx, eax
0x180017daa  jmp     short loc_180017DB1
0x180017dac  mov     ebx, 80004005h
0x180017db1  lea     rcx, [rbp+var_18]
0x180017db5  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180017dba  mov     rcx, [rbp+pv]; pv
0x180017dbe  test    rcx, rcx
0x180017dc1  jz      short loc_180017DCA
0x180017dc3  call    cs:__imp_CoTaskMemFree
0x180017dc9  nop
0x180017dca  lea     rcx, [rbp+arg_0]
0x180017dce  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180017dd3  mov     eax, ebx
0x180017dd5  add     rsp, 48h
0x180017dd9  pop     rdi
0x180017dda  pop     rsi
0x180017ddb  pop     rbx
0x180017ddc  pop     rbp
0x180017ddd  retn
```
