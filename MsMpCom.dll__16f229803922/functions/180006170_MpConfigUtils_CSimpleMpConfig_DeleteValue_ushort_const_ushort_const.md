# MpConfigUtils::CSimpleMpConfig::DeleteValue(ushort const *,ushort const *)

- ea: `0x180006170`
- end: `0x180006275`
- name: `?DeleteValue@CSimpleMpConfig@MpConfigUtils@@UEAAJPEBG0@Z`
- size: `261`
- prototype: `__int64 __fastcall(MpConfigUtils::CSimpleMpConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180006170`
- `0x18000627c`
- `0x18000a010`

## import_xrefs

- `mpclient!MpConfigDelValue` at `0x1800061ec`
- `mpclient!MpConfigDelValue` at `0x1800061ec`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::CSimpleMpConfig::DeleteValue(
        MpConfigUtils::CSimpleMpConfig *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3)
{
  int CachedKey; // ebx
  struct MpConfigUtils::CRefCachedConfigKey *v5; // r8
  struct MpConfigUtils::CRefCachedConfigKey *v7; // rbx
  int v8; // edi
  struct MpConfigUtils::CRefCachedConfigKey *v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  CachedKey = MpConfigUtils::CSimpleMpConfig::GetCachedKey(this, a2, &v9);
  if ( CachedKey < 0 )
  {
    v5 = v9;
    if ( v9 )
    {
      if ( *((_DWORD *)v9 + 2) == 1 )
      {
        *((_DWORD *)v9 + 2) = 0;
        goto LABEL_6;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) <= 1 )
      {
LABEL_6:
        if ( v5 )
          (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v5)(v5, 1);
      }
    }
    return (unsigned int)CachedKey;
  }
  v7 = v9;
  v8 = MpConfigDelValue(*((_QWORD *)v9 + 2), a3);
  if ( v8 < 0 )
  {
    if ( *((_DWORD *)v7 + 2) == 1 )
    {
      *((_DWORD *)v7 + 2) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) > 1 )
    {
      return (unsigned int)v8;
    }
    if ( v7 )
      (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v7)(v7, 1);
    return (unsigned int)v8;
  }
  if ( *((_DWORD *)v7 + 2) == 1 )
  {
    *((_DWORD *)v7 + 2) = 0;
    goto LABEL_19;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) <= 1 )
  {
LABEL_19:
    if ( v7 )
      (**(void (__fastcall ***)(struct MpConfigUtils::CRefCachedConfigKey *, __int64))v7)(v7, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180006170  mov     [rsp+arg_0], rbx
0x180006175  push    rdi
0x180006176  sub     rsp, 20h
0x18000617a  mov     rdi, r8
0x18000617d  mov     [rsp+28h+arg_18], 0
0x180006186  lea     r8, [rsp+28h+arg_18]; struct MpConfigUtils::CRefCachedConfigKey **
0x18000618b  call    ?GetCachedKey@CSimpleMpConfig@MpConfigUtils@@AEBAJPEBGPEAPEAVCRefCachedConfigKey@2@@Z; MpConfigUtils::CSimpleMpConfig::GetCachedKey(ushort const *,MpConfigUtils::CRefCachedConfigKey * *)
0x180006190  mov     ebx, eax
0x180006192  test    eax, eax
0x180006194  jns     short loc_1800061E0
0x180006196  mov     r8, [rsp+28h+arg_18]
0x18000619b  test    r8, r8
0x18000619e  jz      short loc_1800061D9
0x1800061a0  mov     ecx, [r8+8]
0x1800061a4  cmp     ecx, 1
0x1800061a7  jnz     short loc_1800061B3
0x1800061a9  mov     dword ptr [r8+8], 0
0x1800061b1  jmp     short loc_1800061C1
0x1800061b3  or      eax, 0FFFFFFFFh
0x1800061b6  lock xadd [r8+8], eax
0x1800061bc  sub     eax, 1
0x1800061bf  jg      short loc_1800061D9
0x1800061c1  test    r8, r8
0x1800061c4  jz      short loc_1800061D9
0x1800061c6  mov     rax, [r8]
0x1800061c9  mov     edx, 1
0x1800061ce  mov     rcx, r8
0x1800061d1  mov     rax, [rax]
0x1800061d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d9  mov     eax, ebx
0x1800061db  jmp     loc_18000626A
0x1800061e0  mov     rbx, [rsp+28h+arg_18]
0x1800061e5  mov     rdx, rdi
0x1800061e8  mov     rcx, [rbx+10h]
0x1800061ec  call    cs:__imp_MpConfigDelValue
0x1800061f2  mov     edi, eax
0x1800061f4  test    eax, eax
0x1800061f6  jns     short loc_180006232
0x1800061f8  mov     ecx, [rbx+8]
0x1800061fb  cmp     ecx, 1
0x1800061fe  jnz     short loc_180006209
0x180006200  mov     dword ptr [rbx+8], 0
0x180006207  jmp     short loc_180006216
0x180006209  or      eax, 0FFFFFFFFh
0x18000620c  lock xadd [rbx+8], eax
0x180006211  sub     eax, 1
0x180006214  jg      short loc_18000622E
0x180006216  test    rbx, rbx
0x180006219  jz      short loc_18000622E
0x18000621b  mov     rax, [rbx]
0x18000621e  mov     edx, 1
0x180006223  mov     rcx, rbx
0x180006226  mov     rax, [rax]
0x180006229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622e  mov     eax, edi
0x180006230  jmp     short loc_18000626A
0x180006232  mov     eax, [rbx+8]
0x180006235  cmp     eax, 1
0x180006238  jnz     short loc_180006243
0x18000623a  mov     dword ptr [rbx+8], 0
0x180006241  jmp     short loc_180006250
0x180006243  or      eax, 0FFFFFFFFh
0x180006246  lock xadd [rbx+8], eax
0x18000624b  sub     eax, 1
0x18000624e  jg      short loc_180006268
0x180006250  test    rbx, rbx
0x180006253  jz      short loc_180006268
0x180006255  mov     rax, [rbx]
0x180006258  mov     edx, 1
0x18000625d  mov     rcx, rbx
0x180006260  mov     rax, [rax]
0x180006263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006268  xor     eax, eax
0x18000626a  mov     rbx, [rsp+28h+arg_0]
0x18000626f  add     rsp, 20h
0x180006273  pop     rdi
0x180006274  retn
```
