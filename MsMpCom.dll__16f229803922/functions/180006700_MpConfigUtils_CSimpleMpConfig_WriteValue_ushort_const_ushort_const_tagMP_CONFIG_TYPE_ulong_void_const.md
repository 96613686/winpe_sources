# MpConfigUtils::CSimpleMpConfig::WriteValue(ushort const *,ushort const *,tagMP_CONFIG_TYPE,ulong,void const *)

- ea: `0x180006700`
- end: `0x180006823`
- name: `?WriteValue@CSimpleMpConfig@MpConfigUtils@@UEAAJPEBG0W4tagMP_CONFIG_TYPE@@KPEBX@Z`
- size: `291`
- prototype: `__int64 __fastcall(MpConfigUtils::CSimpleMpConfig *, const unsigned __int16 *, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000627c`
- `0x180006700`
- `0x18000a010`

## import_xrefs

- `mpclient!MpConfigSetValue` at `0x180006795`
- `mpclient!MpConfigSetValue` at `0x180006795`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::CSimpleMpConfig::WriteValue(
        MpConfigUtils::CSimpleMpConfig *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  int CachedKey; // ebx
  struct MpConfigUtils::CRefCachedConfigKey *v9; // r8
  struct MpConfigUtils::CRefCachedConfigKey *v11; // rbx
  int v12; // edi
  struct MpConfigUtils::CRefCachedConfigKey *v13; // [rsp+30h] [rbp-18h] BYREF

  v13 = 0;
  CachedKey = MpConfigUtils::CSimpleMpConfig::GetCachedKey(a1, a2, &v13);
  if ( CachedKey < 0 )
  {
    v9 = v13;
    if ( v13 )
    {
      if ( *((_DWORD *)v13 + 2) == 1 )
      {
        *((_DWORD *)v13 + 2) = 0;
        goto LABEL_6;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) <= 1 )
      {
LABEL_6:
        if ( v9 )
          (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v9)(v9, 1);
      }
    }
    return (unsigned int)CachedKey;
  }
  v11 = v13;
  v12 = MpConfigSetValue(*((_QWORD *)v13 + 2), a3, a4, a5, a6);
  if ( v12 < 0 )
  {
    if ( *((_DWORD *)v11 + 2) == 1 )
    {
      *((_DWORD *)v11 + 2) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) > 1 )
    {
      return (unsigned int)v12;
    }
    if ( v11 )
      (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v11)(v11, 1);
    return (unsigned int)v12;
  }
  if ( *((_DWORD *)v11 + 2) == 1 )
  {
    *((_DWORD *)v11 + 2) = 0;
    goto LABEL_19;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) <= 1 )
  {
LABEL_19:
    if ( v11 )
      (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v11)(v11, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180006700  mov     rax, rsp
0x180006703  mov     [rax+8], rbx
0x180006707  mov     [rax+10h], rsi
0x18000670b  push    rdi
0x18000670c  sub     rsp, 40h
0x180006710  mov     rsi, r8
0x180006713  mov     qword ptr [rax-18h], 0
0x18000671b  lea     r8, [rax-18h]; struct MpConfigUtils::CRefCachedConfigKey **
0x18000671f  mov     edi, r9d
0x180006722  call    ?GetCachedKey@CSimpleMpConfig@MpConfigUtils@@AEBAJPEBGPEAPEAVCRefCachedConfigKey@2@@Z; MpConfigUtils::CSimpleMpConfig::GetCachedKey(ushort const *,MpConfigUtils::CRefCachedConfigKey * *)
0x180006727  mov     ebx, eax
0x180006729  test    eax, eax
0x18000672b  jns     short loc_180006777
0x18000672d  mov     r8, [rsp+48h+var_18]
0x180006732  test    r8, r8
0x180006735  jz      short loc_180006770
0x180006737  mov     ecx, [r8+8]
0x18000673b  cmp     ecx, 1
0x18000673e  jnz     short loc_18000674A
0x180006740  mov     dword ptr [r8+8], 0
0x180006748  jmp     short loc_180006758
0x18000674a  or      eax, 0FFFFFFFFh
0x18000674d  lock xadd [r8+8], eax
0x180006753  sub     eax, 1
0x180006756  jg      short loc_180006770
0x180006758  test    r8, r8
0x18000675b  jz      short loc_180006770
0x18000675d  mov     rax, [r8]
0x180006760  mov     edx, 1
0x180006765  mov     rcx, r8
0x180006768  mov     rax, [rax]
0x18000676b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006770  mov     eax, ebx
0x180006772  jmp     loc_180006813
0x180006777  mov     rax, [rsp+48h+arg_28]
0x18000677c  mov     r8d, edi
0x18000677f  mov     rbx, [rsp+48h+var_18]
0x180006784  mov     rdx, rsi
0x180006787  mov     r9d, [rsp+48h+arg_20]
0x18000678c  mov     [rsp+48h+var_28], rax
0x180006791  mov     rcx, [rbx+10h]
0x180006795  call    cs:__imp_MpConfigSetValue
0x18000679b  mov     edi, eax
0x18000679d  test    eax, eax
0x18000679f  jns     short loc_1800067DB
0x1800067a1  mov     ecx, [rbx+8]
0x1800067a4  cmp     ecx, 1
0x1800067a7  jnz     short loc_1800067B2
0x1800067a9  mov     dword ptr [rbx+8], 0
0x1800067b0  jmp     short loc_1800067BF
0x1800067b2  or      eax, 0FFFFFFFFh
0x1800067b5  lock xadd [rbx+8], eax
0x1800067ba  sub     eax, 1
0x1800067bd  jg      short loc_1800067D7
0x1800067bf  test    rbx, rbx
0x1800067c2  jz      short loc_1800067D7
0x1800067c4  mov     rax, [rbx]
0x1800067c7  mov     edx, 1
0x1800067cc  mov     rcx, rbx
0x1800067cf  mov     rax, [rax]
0x1800067d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d7  mov     eax, edi
0x1800067d9  jmp     short loc_180006813
0x1800067db  mov     eax, [rbx+8]
0x1800067de  cmp     eax, 1
0x1800067e1  jnz     short loc_1800067EC
0x1800067e3  mov     dword ptr [rbx+8], 0
0x1800067ea  jmp     short loc_1800067F9
0x1800067ec  or      eax, 0FFFFFFFFh
0x1800067ef  lock xadd [rbx+8], eax
0x1800067f4  sub     eax, 1
0x1800067f7  jg      short loc_180006811
0x1800067f9  test    rbx, rbx
0x1800067fc  jz      short loc_180006811
0x1800067fe  mov     rax, [rbx]
0x180006801  mov     edx, 1
0x180006806  mov     rcx, rbx
0x180006809  mov     rax, [rax]
0x18000680c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006811  xor     eax, eax
0x180006813  mov     rbx, [rsp+48h+arg_0]
0x180006818  mov     rsi, [rsp+48h+arg_8]
0x18000681d  add     rsp, 40h
0x180006821  pop     rdi
0x180006822  retn
```
