# MpConfigUtils::CSimpleMpConfig::ReadValue(ushort const *,ushort const *,tagMP_CONFIG_TYPE *,ulong *,void *)

- ea: `0x1800065c0`
- end: `0x1800066ec`
- name: `?ReadValue@CSimpleMpConfig@MpConfigUtils@@UEAAJPEBG0PEAW4tagMP_CONFIG_TYPE@@PEAKPEAX@Z`
- size: `300`
- prototype: `__int64 __fastcall(MpConfigUtils::CSimpleMpConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, enum tagMP_CONFIG_TYPE *, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000627c`
- `0x1800065c0`
- `0x18000a010`

## import_xrefs

- `mpclient!MpConfigGetValue` at `0x18000665e`
- `mpclient!MpConfigGetValue` at `0x18000665e`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::CSimpleMpConfig::ReadValue(
        MpConfigUtils::CSimpleMpConfig *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        enum tagMP_CONFIG_TYPE *a4,
        unsigned int *a5,
        void *a6)
{
  int CachedKey; // ebx
  struct MpConfigUtils::CRefCachedConfigKey *v9; // r8
  struct MpConfigUtils::CRefCachedConfigKey *v11; // rbx
  int Value; // edi
  struct MpConfigUtils::CRefCachedConfigKey *v13; // [rsp+30h] [rbp-18h] BYREF

  v13 = 0;
  CachedKey = MpConfigUtils::CSimpleMpConfig::GetCachedKey(this, a2, &v13);
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
  Value = MpConfigGetValue(*((_QWORD *)v13 + 2), a3, a4, a5, a6, 0);
  if ( Value < 0 )
  {
    if ( *((_DWORD *)v11 + 2) == 1 )
    {
      *((_DWORD *)v11 + 2) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) > 1 )
    {
      return (unsigned int)Value;
    }
    if ( v11 )
      (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v11)(v11, 1);
    return (unsigned int)Value;
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
0x1800065c0  mov     rax, rsp
0x1800065c3  mov     [rax+8], rbx
0x1800065c7  mov     [rax+10h], rsi
0x1800065cb  push    rdi
0x1800065cc  sub     rsp, 40h
0x1800065d0  mov     rsi, r8
0x1800065d3  mov     qword ptr [rax-18h], 0
0x1800065db  lea     r8, [rax-18h]; struct MpConfigUtils::CRefCachedConfigKey **
0x1800065df  mov     rdi, r9
0x1800065e2  call    ?GetCachedKey@CSimpleMpConfig@MpConfigUtils@@AEBAJPEBGPEAPEAVCRefCachedConfigKey@2@@Z; MpConfigUtils::CSimpleMpConfig::GetCachedKey(ushort const *,MpConfigUtils::CRefCachedConfigKey * *)
0x1800065e7  mov     ebx, eax
0x1800065e9  test    eax, eax
0x1800065eb  jns     short loc_180006637
0x1800065ed  mov     r8, [rsp+48h+var_18]
0x1800065f2  test    r8, r8
0x1800065f5  jz      short loc_180006630
0x1800065f7  mov     ecx, [r8+8]
0x1800065fb  cmp     ecx, 1
0x1800065fe  jnz     short loc_18000660A
0x180006600  mov     dword ptr [r8+8], 0
0x180006608  jmp     short loc_180006618
0x18000660a  or      eax, 0FFFFFFFFh
0x18000660d  lock xadd [r8+8], eax
0x180006613  sub     eax, 1
0x180006616  jg      short loc_180006630
0x180006618  test    r8, r8
0x18000661b  jz      short loc_180006630
0x18000661d  mov     rax, [r8]
0x180006620  mov     edx, 1
0x180006625  mov     rcx, r8
0x180006628  mov     rax, [rax]
0x18000662b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006630  mov     eax, ebx
0x180006632  jmp     loc_1800066DC
0x180006637  mov     rax, [rsp+48h+arg_28]
0x18000663c  mov     r8, rdi
0x18000663f  mov     rbx, [rsp+48h+var_18]
0x180006644  mov     rdx, rsi
0x180006647  mov     r9, [rsp+48h+arg_20]
0x18000664c  mov     [rsp+48h+var_20], 0
0x180006655  mov     [rsp+48h+var_28], rax
0x18000665a  mov     rcx, [rbx+10h]
0x18000665e  call    cs:__imp_MpConfigGetValue
0x180006664  mov     edi, eax
0x180006666  test    eax, eax
0x180006668  jns     short loc_1800066A4
0x18000666a  mov     ecx, [rbx+8]
0x18000666d  cmp     ecx, 1
0x180006670  jnz     short loc_18000667B
0x180006672  mov     dword ptr [rbx+8], 0
0x180006679  jmp     short loc_180006688
0x18000667b  or      eax, 0FFFFFFFFh
0x18000667e  lock xadd [rbx+8], eax
0x180006683  sub     eax, 1
0x180006686  jg      short loc_1800066A0
0x180006688  test    rbx, rbx
0x18000668b  jz      short loc_1800066A0
0x18000668d  mov     rax, [rbx]
0x180006690  mov     edx, 1
0x180006695  mov     rcx, rbx
0x180006698  mov     rax, [rax]
0x18000669b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a0  mov     eax, edi
0x1800066a2  jmp     short loc_1800066DC
0x1800066a4  mov     eax, [rbx+8]
0x1800066a7  cmp     eax, 1
0x1800066aa  jnz     short loc_1800066B5
0x1800066ac  mov     dword ptr [rbx+8], 0
0x1800066b3  jmp     short loc_1800066C2
0x1800066b5  or      eax, 0FFFFFFFFh
0x1800066b8  lock xadd [rbx+8], eax
0x1800066bd  sub     eax, 1
0x1800066c0  jg      short loc_1800066DA
0x1800066c2  test    rbx, rbx
0x1800066c5  jz      short loc_1800066DA
0x1800066c7  mov     rax, [rbx]
0x1800066ca  mov     edx, 1
0x1800066cf  mov     rcx, rbx
0x1800066d2  mov     rax, [rax]
0x1800066d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066da  xor     eax, eax
0x1800066dc  mov     rbx, [rsp+48h+arg_0]
0x1800066e1  mov     rsi, [rsp+48h+arg_8]
0x1800066e6  add     rsp, 40h
0x1800066ea  pop     rdi
0x1800066eb  retn
```
