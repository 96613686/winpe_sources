# DdoShellItemToControlName(IShellItem *,ushort * *)

- ea: `0x1800037f4`
- end: `0x180003928`
- name: `?DdoShellItemToControlName@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003670`
- `0x18000adb4`

## callees

- `0x1800037f4`
- `0x180003f2c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800038d2`
- `KERNEL32!CompareStringOrdinal` at `0x1800038d2`
- `ole32!PropVariantClear` at `0x1800038f4`
- `ole32!PropVariantClear` at `0x1800038f4`
- `SHLWAPI!SHStrDupW` at `0x1800038e8`
- `SHLWAPI!SHStrDupW` at `0x1800038e8`

## pseudocode

```c
__int64 __fastcall DdoShellItemToControlName(struct IShellItem *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  unsigned __int64 v4; // rdx
  __int64 i; // rdi
  const unsigned __int16 *v6; // rsi
  PROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF
  __int64 v9; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int64 v10; // [rsp+78h] [rbp+28h] BYREF

  *a2 = 0;
  v9 = 0;
  v3 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
         &v9);
  memset(&pvar, 0, sizeof(pvar));
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v9 + 104LL))(
           v9,
           &PKEY_Devices_InterfacePaths,
           &pvar);
    if ( v3 >= 0 )
    {
      v3 = -2147467259;
      for ( i = 0; pvar.vt == 4127; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= pvar.lVal )
          break;
        if ( !pvar.bstrblobVal.pData )
          break;
        v6 = *(const unsigned __int16 **)&pvar.bstrblobVal.pData[8 * i];
        if ( !v6 )
          break;
        v10 = 0;
        v3 = StringCchLengthW(v6, v4, &v10);
        if ( v3 < 0 )
          break;
        if ( v10 > 0x27 && CompareStringOrdinal(v6, 39, L"{4F40006F-B933-4550-B532-2B58CEE614D3},", 39, 0) == 2 )
        {
          v3 = SHStrDupW(v6 + 39, a2);
          break;
        }
      }
    }
  }
  PropVariantClear(&pvar);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800037f4  mov     [rsp-18h+arg_10], rbx
0x1800037f9  mov     [rsp-18h+arg_18], rsi
0x1800037fe  push    rbp
0x1800037ff  push    rdi
0x180003800  push    r14
0x180003802  mov     rbp, rsp
0x180003805  sub     rsp, 50h
0x180003809  mov     r14, rdx
0x18000380c  mov     qword ptr [rdx], 0
0x180003813  mov     [rbp+arg_0], 0
0x18000381b  mov     rax, [rcx]
0x18000381e  lea     r8, [rbp+arg_0]
0x180003822  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180003829  mov     rax, [rax]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  mov     ebx, eax
0x180003833  xorps   xmm0, xmm0
0x180003836  xor     eax, eax
0x180003838  movups  xmmword ptr [rbp+pvar], xmm0
0x18000383c  mov     qword ptr [rbp+pvar+10h], rax
0x180003840  test    ebx, ebx
0x180003842  js      loc_1800038F0
0x180003848  mov     rcx, [rbp+arg_0]
0x18000384c  mov     rax, [rcx]
0x18000384f  lea     r8, [rbp+pvar]
0x180003853  lea     rdx, PKEY_Devices_InterfacePaths
0x18000385a  mov     rax, [rax+68h]
0x18000385e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003863  mov     ebx, eax
0x180003865  test    eax, eax
0x180003867  js      loc_1800038F0
0x18000386d  mov     ebx, 80004005h
0x180003872  xor     edi, edi
0x180003874  mov     eax, 101Fh
0x180003879  cmp     word ptr [rbp+pvar], ax
0x18000387d  jnz     short loc_1800038F0
0x18000387f  cmp     edi, dword ptr [rbp+pvar+8]
0x180003882  jnb     short loc_1800038F0
0x180003884  mov     rsi, qword ptr [rbp+pvar+10h]
0x180003888  test    rsi, rsi
0x18000388b  jz      short loc_1800038F0
0x18000388d  mov     rsi, [rsi+rdi*8]
0x180003891  test    rsi, rsi
0x180003894  jz      short loc_1800038F0
0x180003896  mov     [rbp+arg_8], 0
0x18000389e  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x1800038a2  mov     rcx, rsi; unsigned __int16 *
0x1800038a5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800038aa  mov     ebx, eax
0x1800038ac  test    eax, eax
0x1800038ae  js      short loc_1800038F0
0x1800038b0  cmp     [rbp+arg_8], 27h ; '''
0x1800038b5  jbe     short loc_1800038DD
0x1800038b7  mov     [rsp+50h+bIgnoreCase], 0; bIgnoreCase
0x1800038bf  mov     r9d, 27h ; '''; cchCount2
0x1800038c5  lea     r8, String2; "{4F40006F-B933-4550-B532-2B58CEE614D3},"
0x1800038cc  mov     edx, r9d; cchCount1
0x1800038cf  mov     rcx, rsi; lpString1
0x1800038d2  call    cs:__imp_CompareStringOrdinal
0x1800038d8  cmp     eax, 2
0x1800038db  jz      short loc_1800038E1
0x1800038dd  inc     edi
0x1800038df  jmp     short loc_180003874
0x1800038e1  lea     rcx, [rsi+4Eh]; psz
0x1800038e5  mov     rdx, r14; ppwsz
0x1800038e8  call    cs:__imp_SHStrDupW
0x1800038ee  mov     ebx, eax
0x1800038f0  lea     rcx, [rbp+pvar]; pvar
0x1800038f4  call    cs:__imp_PropVariantClear
0x1800038fa  nop
0x1800038fb  mov     rcx, [rbp+arg_0]
0x1800038ff  test    rcx, rcx
0x180003902  jz      short loc_180003911
0x180003904  mov     rax, [rcx]
0x180003907  mov     rax, [rax+10h]
0x18000390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003910  nop
0x180003911  mov     eax, ebx
0x180003913  lea     r11, [rsp+50h+var_s0]
0x180003918  mov     rbx, [r11+30h]
0x18000391c  mov     rsi, [r11+38h]
0x180003920  mov     rsp, r11
0x180003923  pop     r14
0x180003925  pop     rdi
0x180003926  pop     rbp
0x180003927  retn
```
