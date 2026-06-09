# Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18002a1c0`
- end: `0x18002a2a5`
- name: `?QueryInterface@SequentialPackageHandler@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(LPUNKNOWN punkOuter, const struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002a1c0`
- `0x180040cfc`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18002a211`
- `VCRUNTIME140!memcmp` at `0x18002a211`
- `KERNEL32!LeaveCriticalSection` at `0x18002a25c`
- `KERNEL32!LeaveCriticalSection` at `0x18002a267`
- `KERNEL32!LeaveCriticalSection` at `0x18002a25c`
- `KERNEL32!LeaveCriticalSection` at `0x18002a267`
- `KERNEL32!EnterCriticalSection` at `0x18002a238`
- `KERNEL32!EnterCriticalSection` at `0x18002a238`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18002a24a`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18002a24a`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::QueryInterface(
        InternalImplQueryInterface *punkOuter,
        const struct _GUID *a2,
        struct _GUID *a3)
{
  HRESULT FreeThreadedMarshaler; // edi
  LPUNKNOWN v7; // rsi
  void **v9; // [rsp+20h] [rbp-8h]

  FreeThreadedMarshaler = InternalImplQueryInterface::SingleInterfaceImp(
                            punkOuter,
                            (struct IUnknown *)&GUID_03779dc9_70da_4063_808f_43ee228b18c4,
                            a2,
                            a3,
                            v9);
  if ( FreeThreadedMarshaler == -2147467262 && !memcmp(a2, &GUID_00000003_0000_0000_c000_000000000046, 0x10u) )
  {
    if ( a3 )
    {
      v7 = (LPUNKNOWN)((char *)punkOuter + 48);
      if ( !*((_QWORD *)punkOuter + 6) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)punkOuter + 56));
        if ( !v7->lpVtbl )
        {
          FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)punkOuter, (LPUNKNOWN *)punkOuter + 6);
          if ( FreeThreadedMarshaler < 0 )
          {
            _mm_lfence();
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)punkOuter + 56));
            return (unsigned int)FreeThreadedMarshaler;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)punkOuter + 56));
      }
      return (*(unsigned int (__fastcall **)(struct IUnknownVtbl *, GUID *, struct _GUID *))v7->lpVtbl->QueryInterface)(
               v7->lpVtbl,
               &GUID_00000003_0000_0000_c000_000000000046,
               a3);
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x18002a1c0  mov     rax, rsp
0x18002a1c3  mov     [rax+8], rbx
0x18002a1c7  mov     [rax+10h], rbp
0x18002a1cb  mov     [rax+18h], rsi
0x18002a1cf  mov     [rax+20h], rdi
0x18002a1d3  push    r14; void **
0x18002a1d5  sub     rsp, 20h
0x18002a1d9  mov     r14, r8
0x18002a1dc  mov     r9, r8; struct _GUID *
0x18002a1df  mov     r8, rdx; struct _GUID *
0x18002a1e2  mov     rbx, rdx
0x18002a1e5  lea     rdx, _GUID_03779dc9_70da_4063_808f_43ee228b18c4; struct IUnknown *
0x18002a1ec  mov     rbp, rcx
0x18002a1ef  call    ?SingleInterfaceImp@InternalImplQueryInterface@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; InternalImplQueryInterface::SingleInterfaceImp(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18002a1f4  mov     edi, eax
0x18002a1f6  cmp     eax, 80004002h
0x18002a1fb  jnz     loc_18002A288
0x18002a201  mov     r8d, 10h; Size
0x18002a207  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; Buf2
0x18002a20e  mov     rcx, rbx; Buf1
0x18002a211  call    cs:__imp_memcmp
0x18002a217  test    eax, eax
0x18002a219  jnz     short loc_18002A288
0x18002a21b  test    r14, r14
0x18002a21e  jnz     short loc_18002A227
0x18002a220  mov     edi, 80004003h
0x18002a225  jmp     short loc_18002A288
0x18002a227  lea     rsi, [rbp+30h]
0x18002a22b  cmp     qword ptr [rsi], 0
0x18002a22f  jnz     short loc_18002A26D
0x18002a231  lea     rbx, [rbp+38h]
0x18002a235  mov     rcx, rbx; lpCriticalSection
0x18002a238  call    cs:__imp_EnterCriticalSection
0x18002a23e  cmp     qword ptr [rsi], 0
0x18002a242  jnz     short loc_18002A264
0x18002a244  mov     rdx, rsi; ppunkMarshal
0x18002a247  mov     rcx, rbp; punkOuter
0x18002a24a  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002a250  mov     edi, eax
0x18002a252  test    eax, eax
0x18002a254  jns     short loc_18002A264
0x18002a256  lfence
0x18002a259  mov     rcx, rbx; lpCriticalSection
0x18002a25c  call    cs:__imp_LeaveCriticalSection
0x18002a262  jmp     short loc_18002A288
0x18002a264  mov     rcx, rbx; lpCriticalSection
0x18002a267  call    cs:__imp_LeaveCriticalSection
0x18002a26d  mov     rcx, [rsi]
0x18002a270  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18002a277  mov     r8, r14
0x18002a27a  mov     rax, [rcx]
0x18002a27d  mov     rax, [rax]
0x18002a280  call    cs:__guard_dispatch_icall_fptr
0x18002a286  mov     edi, eax
0x18002a288  mov     rbx, [rsp+28h+arg_0]
0x18002a28d  mov     eax, edi
0x18002a28f  mov     rdi, [rsp+28h+arg_18]
0x18002a294  mov     rbp, [rsp+28h+arg_8]
0x18002a299  mov     rsi, [rsp+28h+arg_10]
0x18002a29e  add     rsp, 20h
0x18002a2a2  pop     r14
0x18002a2a4  retn
```
