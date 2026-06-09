# CProfileCache::GetProfileName(_GUID const &,ushort * *)

- ea: `0x1800064f4`
- end: `0x1800065a4`
- name: `?GetProfileName@CProfileCache@@QEAAJAEBU_GUID@@PEAPEAG@Z`
- size: `176`
- prototype: `int(CProfileCache *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003600`

## callees

- `0x1800064f4`
- `0x1800076c8`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180006599`
- `SHLWAPI!SHStrDupW` at `0x180006599`

## pseudocode

```c
__int64 __fastcall CProfileCache::GetProfileName(CProfileCache *this, const struct _GUID *a2, unsigned __int16 **a3)
{
  volatile signed __int32 *v5; // rcx
  signed __int32 v7; // r10d
  unsigned int v8; // ecx
  _QWORD *v9; // rdx
  unsigned int v10; // r8d
  signed __int32 v11; // edx

  v5 = (volatile signed __int32 *)((char *)this + 48);
  if ( (*v5 & 0xFFFF8000) != 0 || (v7 = *v5, v7 != _InterlockedCompareExchange(v5, v7 + 1, v7)) )
    CReaderWriterLock3::_LockSpin(v5, 2);
  v8 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    while ( 1 )
    {
      v9 = (_QWORD *)(*((_QWORD *)this + 5) + 16LL * v8);
      if ( *(_QWORD *)&a2->Data1 == *v9 && *(_QWORD *)a2->Data4 == v9[1] )
        break;
      if ( ++v8 >= *((_DWORD *)this + 4) )
        goto LABEL_8;
    }
    v10 = SHStrDupW(*(LPCWSTR *)(*((_QWORD *)this + 3) + 8LL * v8), a3);
  }
  else
  {
LABEL_8:
    v10 = -2147024809;
  }
  do
    v11 = *((_DWORD *)this + 12);
  while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)this + 12, v11 - 1, v11) );
  return v10;
}

```

## disassembly

```asm
0x1800064f4  mov     [rsp+arg_0], rbx
0x1800064f9  mov     [rsp+arg_8], rsi
0x1800064fe  push    rdi
0x1800064ff  sub     rsp, 20h
0x180006503  mov     rbx, rcx
0x180006506  mov     rsi, r8
0x180006509  add     rcx, 30h ; '0'
0x18000650d  mov     rdi, rdx
0x180006510  mov     r10d, [rcx]
0x180006513  test    r10d, 0FFFF8000h
0x18000651a  jnz     short loc_18000652D
0x18000651c  lea     r9d, [r10+1]
0x180006520  mov     eax, r10d
0x180006523  lock cmpxchg [rcx], r9d
0x180006528  cmp     r10d, eax
0x18000652b  jz      short loc_180006537
0x18000652d  mov     edx, 2
0x180006532  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x180006537  xor     ecx, ecx
0x180006539  cmp     [rbx+10h], ecx
0x18000653c  jbe     short loc_180006564
0x18000653e  mov     rax, [rdi]
0x180006541  mov     edx, ecx
0x180006543  shl     rdx, 4
0x180006547  add     rdx, [rbx+28h]
0x18000654b  mov     r8d, ecx
0x18000654e  cmp     rax, [rdx]
0x180006551  jnz     short loc_18000655D
0x180006553  mov     rax, [rdi+8]
0x180006557  cmp     rax, [rdx+8]
0x18000655b  jz      short loc_18000658E
0x18000655d  inc     ecx
0x18000655f  cmp     ecx, [rbx+10h]
0x180006562  jb      short loc_18000653E
0x180006564  mov     r8d, 80070057h
0x18000656a  mov     edx, [rbx+30h]
0x18000656d  mov     eax, edx
0x18000656f  lea     ecx, [rdx-1]
0x180006572  lock cmpxchg [rbx+30h], ecx
0x180006577  cmp     edx, eax
0x180006579  jnz     short loc_18000656A
0x18000657b  mov     rbx, [rsp+28h+arg_0]
0x180006580  mov     eax, r8d
0x180006583  mov     rsi, [rsp+28h+arg_8]
0x180006588  add     rsp, 20h
0x18000658c  pop     rdi
0x18000658d  retn
0x18000658e  mov     rcx, [rbx+18h]
0x180006592  mov     rdx, rsi; ppwsz
0x180006595  mov     rcx, [rcx+r8*8]; psz
0x180006599  call    cs:__imp_SHStrDupW
0x18000659f  mov     r8d, eax
0x1800065a2  jmp     short loc_18000656A
```
