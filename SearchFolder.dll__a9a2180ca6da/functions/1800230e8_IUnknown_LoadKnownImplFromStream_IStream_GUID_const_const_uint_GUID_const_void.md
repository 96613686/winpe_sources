# IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)

- ea: `0x1800230e8`
- end: `0x18002320b`
- name: `?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct IStream *, const struct _GUID *const *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800233f0`

## callees

- `0x180006900`
- `0x1800230e8`
- `0x1800233a8`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180023121`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180023121`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002316c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002316c`

## pseudocode

```c
__int64 __fastcall IUnknown_LoadKnownImplFromStream(
        struct IStream *a1,
        const struct _GUID *const *a2,
        __int64 a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int v6; // edx
  const struct _GUID *const *v7; // rcx
  HRESULT v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-30h] BYREF
  struct _GUID pv; // [rsp+40h] [rbp-28h] BYREF

  pv = 0;
  *a5 = 0;
  v8 = IStream_Read(a1, &pv, 0x10u);
  if ( v8 >= 0 )
  {
    if ( (unsigned int)IsExpectedCLSID(v7, v6, &pv) )
    {
      ppv = 0;
      v8 = CoCreateInstance(&pv, 0, 0x415u, &GUID_0fc988d4_c935_4b97_a973_46282ea175c8, &ppv);
      if ( v8 >= 0 )
      {
        v10 = 0;
        v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_00000109_0000_0000_c000_000000000046,
               &v10);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v10 + 40LL))(v10, a1);
          if ( v8 >= 0 )
            v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v10)(
                   v10,
                   &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                   a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800230e8  push    rbp
0x1800230ea  push    rbx
0x1800230eb  push    rsi
0x1800230ec  push    rdi
0x1800230ed  mov     rbp, rsp
0x1800230f0  sub     rsp, 68h
0x1800230f4  mov     rax, cs:__security_cookie
0x1800230fb  xor     rax, rsp
0x1800230fe  mov     [rbp+var_18], rax
0x180023102  mov     rsi, [rbp+arg_20]
0x180023106  lea     rdx, [rbp+pv]; pv
0x18002310a  xorps   xmm0, xmm0
0x18002310d  mov     r8d, 10h; cb
0x180023113  mov     rdi, rcx
0x180023116  movups  [rbp+pv], xmm0
0x18002311a  mov     qword ptr [rsi], 0
0x180023121  call    cs:__imp_IStream_Read
0x180023127  mov     ebx, eax
0x180023129  test    eax, eax
0x18002312b  js      loc_1800231F4
0x180023131  lea     r8, [rbp+pv]; struct _GUID *
0x180023135  call    ?IsExpectedCLSID@@YAHPEBQEBU_GUID@@IAEBU1@@Z; IsExpectedCLSID(_GUID const * const *,uint,_GUID const &)
0x18002313a  test    eax, eax
0x18002313c  jnz     short loc_180023148
0x18002313e  mov     ebx, 80070057h
0x180023143  jmp     loc_1800231F4
0x180023148  lea     rax, [rbp+var_30]
0x18002314c  mov     [rbp+var_30], 0
0x180023154  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8; riid
0x18002315b  mov     [rsp+68h+ppv], rax; ppv
0x180023160  xor     edx, edx; pUnkOuter
0x180023162  lea     rcx, [rbp+pv]; rclsid
0x180023166  mov     r8d, 415h; dwClsContext
0x18002316c  call    cs:__imp_CoCreateInstance
0x180023172  mov     ebx, eax
0x180023174  test    eax, eax
0x180023176  js      short loc_1800231F4
0x180023178  mov     rcx, [rbp+var_30]
0x18002317c  lea     r8, [rbp+var_38]
0x180023180  mov     [rbp+var_38], 0
0x180023188  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18002318f  mov     rax, [rcx]
0x180023192  mov     rax, [rax]
0x180023195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002319a  mov     ebx, eax
0x18002319c  test    eax, eax
0x18002319e  js      short loc_1800231E4
0x1800231a0  mov     rcx, [rbp+var_38]
0x1800231a4  mov     rdx, rdi
0x1800231a7  mov     rax, [rcx]
0x1800231aa  mov     rax, [rax+28h]
0x1800231ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231b3  mov     ebx, eax
0x1800231b5  test    eax, eax
0x1800231b7  js      short loc_1800231D4
0x1800231b9  mov     rcx, [rbp+var_38]
0x1800231bd  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800231c4  mov     r8, rsi
0x1800231c7  mov     rax, [rcx]
0x1800231ca  mov     rax, [rax]
0x1800231cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d2  mov     ebx, eax
0x1800231d4  mov     rcx, [rbp+var_38]
0x1800231d8  mov     rax, [rcx]
0x1800231db  mov     rax, [rax+10h]
0x1800231df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231e4  mov     rcx, [rbp+var_30]
0x1800231e8  mov     rax, [rcx]
0x1800231eb  mov     rax, [rax+10h]
0x1800231ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231f4  mov     eax, ebx
0x1800231f6  mov     rcx, [rbp+var_18]
0x1800231fa  xor     rcx, rsp; StackCookie
0x1800231fd  call    __security_check_cookie
0x180023202  add     rsp, 68h
0x180023206  pop     rdi
0x180023207  pop     rsi
0x180023208  pop     rbx
0x180023209  pop     rbp
0x18002320a  retn
```
