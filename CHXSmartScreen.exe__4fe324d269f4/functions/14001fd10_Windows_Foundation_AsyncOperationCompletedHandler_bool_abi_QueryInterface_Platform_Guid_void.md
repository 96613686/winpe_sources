# Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_QueryInterface(Platform::Guid &,void * *)

- ea: `0x14001fd10`
- end: `0x14001fe27`
- name: `?__abi_QueryInterface@?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@UE$AAAJAEAVGuid@Platform@@PEAPEAX@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001fe30`
- `0x14001fe40`

## callees

- `0x140008470`
- `0x14001fd10`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_QueryInterface(
        _QWORD *a1,
        __int64 a2,
        void **a3)
{
  if ( !*(_DWORD *)a2 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_9;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == -1043082846
    && *(_DWORD *)(a2 + 4) == 1516219927
    && *(_DWORD *)(a2 + 8) == -859987275
    && *(_DWORD *)(a2 + 12) == -1702345592 )
  {
LABEL_18:
    *a3 = a1;
    if ( a1[3] )
    {
      if ( *(int *)(a1[3] + 12LL) >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(a1[3] + 12LL));
    }
    return 0;
  }
LABEL_9:
  if ( (-(__int64)(a1[4] != 0) & (unsigned __int64)(a1 + 3)) != 0 && *(_DWORD *)a2 == -1796592748 )
  {
    if ( *(_DWORD *)(a2 + 4) != 1239476684 || *(_DWORD *)(a2 + 8) != 1693384640 )
      goto LABEL_21;
    if ( *(_DWORD *)(a2 + 12) == -1873047606 )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == -52629460
    && *(_DWORD *)(a2 + 4) == 1148773848
    && *(_DWORD *)(a2 + 8) == -1873978735
    && *(_DWORD *)(a2 + 12) == -1518122057 )
  {
    goto LABEL_18;
  }
LABEL_21:
  if ( (-(__int64)(a1[4] != 0) & (unsigned __int64)(a1 + 3)) != 0
    && !(unsigned int)__abi_FTMWeakRefData::__abi_QueryInterface(
                        (__abi_FTMWeakRefData *)((unsigned __int64)(a1 + 3) & -(__int64)(a1[4] != 0)),
                        (struct Platform::Guid *)a2,
                        a3) )
  {
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x14001fd10  sub     rsp, 28h
0x14001fd14  cmp     dword ptr [rdx], 0
0x14001fd17  mov     r9, rcx
0x14001fd1a  jnz     short loc_14001FD41
0x14001fd1c  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14001fd22  cmp     [rdx+4], eax
0x14001fd25  jnz     short loc_14001FD6A
0x14001fd27  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14001fd2d  cmp     [rdx+8], eax
0x14001fd30  jnz     short loc_14001FD6A
0x14001fd32  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14001fd38  cmp     [rdx+0Ch], eax
0x14001fd3b  jz      loc_14001FDCF
0x14001fd41  cmp     dword ptr [rdx], 0C1D3D1A2h
0x14001fd47  jnz     short loc_14001FD6A
0x14001fd49  mov     eax, cs:dword_14003B6FC
0x14001fd4f  cmp     [rdx+4], eax
0x14001fd52  jnz     short loc_14001FD6A
0x14001fd54  mov     eax, cs:dword_14003B700
0x14001fd5a  cmp     [rdx+8], eax
0x14001fd5d  jnz     short loc_14001FD6A
0x14001fd5f  mov     eax, cs:dword_14003B704
0x14001fd65  cmp     [rdx+0Ch], eax
0x14001fd68  jz      short loc_14001FDCF
0x14001fd6a  mov     rax, [rcx+20h]
0x14001fd6e  lea     r10, [rcx+18h]
0x14001fd72  neg     rax
0x14001fd75  sbb     rax, rax
0x14001fd78  test    r10, rax
0x14001fd7b  jz      short loc_14001FDA6
0x14001fd7d  cmp     dword ptr [rdx], 94EA2B94h
0x14001fd83  jnz     short loc_14001FDA6
0x14001fd85  mov     eax, cs:dword_140039C6C
0x14001fd8b  cmp     [rdx+4], eax
0x14001fd8e  jnz     short loc_14001FDF0
0x14001fd90  mov     eax, cs:dword_140039C70
0x14001fd96  cmp     [rdx+8], eax
0x14001fd99  jnz     short loc_14001FDF0
0x14001fd9b  mov     eax, cs:dword_140039C74
0x14001fda1  cmp     [rdx+0Ch], eax
0x14001fda4  jz      short loc_14001FDCF
0x14001fda6  cmp     dword ptr [rdx], 0FCDCF02Ch
0x14001fdac  jnz     short loc_14001FDF0
0x14001fdae  mov     eax, cs:dword_14003B70C
0x14001fdb4  cmp     [rdx+4], eax
0x14001fdb7  jnz     short loc_14001FDF0
0x14001fdb9  mov     eax, cs:dword_14003B710
0x14001fdbf  cmp     [rdx+8], eax
0x14001fdc2  jnz     short loc_14001FDF0
0x14001fdc4  mov     eax, cs:dword_14003B714
0x14001fdca  cmp     [rdx+0Ch], eax
0x14001fdcd  jnz     short loc_14001FDF0
0x14001fdcf  mov     [r8], r9
0x14001fdd2  mov     rax, [rcx+18h]
0x14001fdd6  test    rax, rax
0x14001fdd9  jz      short loc_14001FE19
0x14001fddb  mov     rax, [rcx+18h]
0x14001fddf  mov     ecx, [rax+0Ch]
0x14001fde2  test    ecx, ecx
0x14001fde4  js      short loc_14001FE19
0x14001fde6  mov     rax, [r9+18h]
0x14001fdea  lock inc dword ptr [rax+0Ch]
0x14001fdee  jmp     short loc_14001FE19
0x14001fdf0  mov     rax, [rcx+20h]
0x14001fdf4  add     rcx, 18h
0x14001fdf8  neg     rax
0x14001fdfb  sbb     rax, rax
0x14001fdfe  test    rcx, rax
0x14001fe01  jz      short loc_14001FE1D
0x14001fe03  mov     rax, [r9+20h]
0x14001fe07  neg     rax
0x14001fe0a  sbb     rcx, rcx
0x14001fe0d  and     rcx, r10; this
0x14001fe10  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x14001fe15  test    eax, eax
0x14001fe17  jnz     short loc_14001FE1D
0x14001fe19  xor     eax, eax
0x14001fe1b  jmp     short loc_14001FE22
0x14001fe1d  mov     eax, 80004002h
0x14001fe22  add     rsp, 28h
0x14001fe26  retn
```
