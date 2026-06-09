# Windows::Foundation::AsyncActionCompletedHandler::__abi_QueryInterface(Platform::Guid &,void * *)

- ea: `0x140020f10`
- end: `0x140021024`
- name: `?__abi_QueryInterface@AsyncActionCompletedHandler@Foundation@Windows@@UE$AAAJAEAVGuid@Platform@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008470`
- `0x140020f10`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::AsyncActionCompletedHandler::__abi_QueryInterface(
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
  if ( *(_DWORD *)a2 == -1527948159
    && *(_DWORD *)(a2 + 4) == 1086158537
    && *(_DWORD *)(a2 + 8) == -642652533
    && *(_DWORD *)(a2 + 12) == -418729457 )
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
  if ( *(_DWORD *)a2 == -1527948159
    && *(_DWORD *)(a2 + 4) == 1086158537
    && *(_DWORD *)(a2 + 8) == -642652533
    && *(_DWORD *)(a2 + 12) == -418729457 )
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
0x140020f10  sub     rsp, 28h
0x140020f14  cmp     dword ptr [rdx], 0
0x140020f17  mov     r9, rcx
0x140020f1a  mov     ecx, 0A4ED5C81h
0x140020f1f  jnz     short loc_140020F46
0x140020f21  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140020f27  cmp     [rdx+4], eax
0x140020f2a  jnz     short loc_140020F6B
0x140020f2c  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140020f32  cmp     [rdx+8], eax
0x140020f35  jnz     short loc_140020F6B
0x140020f37  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x140020f3d  cmp     [rdx+0Ch], eax
0x140020f40  jz      loc_140020FCC
0x140020f46  cmp     [rdx], ecx
0x140020f48  jnz     short loc_140020F6B
0x140020f4a  mov     eax, cs:dword_14003B73C
0x140020f50  cmp     [rdx+4], eax
0x140020f53  jnz     short loc_140020F6B
0x140020f55  mov     eax, cs:dword_14003B740
0x140020f5b  cmp     [rdx+8], eax
0x140020f5e  jnz     short loc_140020F6B
0x140020f60  mov     eax, cs:dword_14003B744
0x140020f66  cmp     [rdx+0Ch], eax
0x140020f69  jz      short loc_140020FCC
0x140020f6b  mov     rax, [r9+20h]
0x140020f6f  lea     r10, [r9+18h]
0x140020f73  neg     rax
0x140020f76  sbb     rax, rax
0x140020f79  test    r10, rax
0x140020f7c  jz      short loc_140020FA7
0x140020f7e  cmp     dword ptr [rdx], 94EA2B94h
0x140020f84  jnz     short loc_140020FA7
0x140020f86  mov     eax, cs:dword_140039C6C
0x140020f8c  cmp     [rdx+4], eax
0x140020f8f  jnz     short loc_140020FED
0x140020f91  mov     eax, cs:dword_140039C70
0x140020f97  cmp     [rdx+8], eax
0x140020f9a  jnz     short loc_140020FED
0x140020f9c  mov     eax, cs:dword_140039C74
0x140020fa2  cmp     [rdx+0Ch], eax
0x140020fa5  jz      short loc_140020FCC
0x140020fa7  cmp     [rdx], ecx
0x140020fa9  jnz     short loc_140020FED
0x140020fab  mov     eax, cs:dword_14003B74C
0x140020fb1  cmp     [rdx+4], eax
0x140020fb4  jnz     short loc_140020FED
0x140020fb6  mov     eax, cs:dword_14003B750
0x140020fbc  cmp     [rdx+8], eax
0x140020fbf  jnz     short loc_140020FED
0x140020fc1  mov     eax, cs:dword_14003B754
0x140020fc7  cmp     [rdx+0Ch], eax
0x140020fca  jnz     short loc_140020FED
0x140020fcc  mov     [r8], r9
0x140020fcf  mov     rax, [r9+18h]
0x140020fd3  test    rax, rax
0x140020fd6  jz      short loc_140021016
0x140020fd8  mov     rax, [r9+18h]
0x140020fdc  mov     ecx, [rax+0Ch]
0x140020fdf  test    ecx, ecx
0x140020fe1  js      short loc_140021016
0x140020fe3  mov     rax, [r9+18h]
0x140020fe7  lock inc dword ptr [rax+0Ch]
0x140020feb  jmp     short loc_140021016
0x140020fed  lea     rcx, [r9+18h]
0x140020ff1  mov     rax, [rcx+8]
0x140020ff5  neg     rax
0x140020ff8  sbb     rax, rax
0x140020ffb  test    rcx, rax
0x140020ffe  jz      short loc_14002101A
0x140021000  mov     rax, [r9+20h]
0x140021004  neg     rax
0x140021007  sbb     rcx, rcx
0x14002100a  and     rcx, r10; this
0x14002100d  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x140021012  test    eax, eax
0x140021014  jnz     short loc_14002101A
0x140021016  xor     eax, eax
0x140021018  jmp     short loc_14002101F
0x14002101a  mov     eax, 80004002h
0x14002101f  add     rsp, 28h
0x140021023  retn
```
