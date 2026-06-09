# CRuntimeBrokerLifetimeExtensionFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x140006b30`
- end: `0x140006be5`
- name: `?QueryInterface@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `181`
- prototype: `__int64 __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c170`

## callees

- `0x140006b30`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::QueryInterface(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  char *v8; // rax
  char *v9; // rcx

  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
  if ( !v4 )
    goto LABEL_4;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4;
  if ( v6 )
  {
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4;
    if ( v7 )
    {
      result = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1 )
        result = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4;
      if ( result )
      {
        return 2147500034LL;
      }
      else
      {
        v9 = (char *)this + 8;
        if ( !this )
          v9 = 0;
        *a3 = v9;
        _InterlockedIncrement((volatile signed __int32 *)this + 4);
      }
    }
    else
    {
      if ( this )
        v8 = (char *)this + 8;
      else
        v8 = 0;
      *a3 = v8;
      _InterlockedIncrement((volatile signed __int32 *)this + 4);
      return 0;
    }
  }
  else
  {
LABEL_4:
    *a3 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006b30  mov     qword ptr [r8], 0
0x140006b37  mov     r9, rcx
0x140006b3a  mov     rax, [rdx]
0x140006b3d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140006b44  jnz     short loc_140006B51
0x140006b46  mov     rax, [rdx+8]
0x140006b4a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140006b51  test    rax, rax
0x140006b54  jnz     short loc_140006B60
0x140006b56  mov     [r8], r9
0x140006b59  lock inc dword ptr [rcx+10h]
0x140006b5d  xor     eax, eax
0x140006b5f  retn
0x140006b60  mov     rax, [rdx]
0x140006b63  sub     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x140006b6a  jnz     short loc_140006B77
0x140006b6c  mov     rax, [rdx+8]
0x140006b70  sub     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x140006b77  test    rax, rax
0x140006b7a  jz      short loc_140006B56
0x140006b7c  mov     rax, [rdx]
0x140006b7f  sub     rax, qword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data1
0x140006b86  jnz     short loc_140006B93
0x140006b88  mov     rax, [rdx+8]
0x140006b8c  sub     rax, qword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x140006b93  test    rax, rax
0x140006b96  jnz     short loc_140006BAB
0x140006b98  test    r9, r9
0x140006b9b  jz      short loc_140006BE1
0x140006b9d  lea     rax, [rcx+8]
0x140006ba1  mov     [r8], rax
0x140006ba4  lock inc dword ptr [rcx+10h]
0x140006ba8  xor     eax, eax
0x140006baa  retn
0x140006bab  mov     rax, [rdx]
0x140006bae  sub     rax, qword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data1
0x140006bb5  jnz     short loc_140006BC2
0x140006bb7  mov     rax, [rdx+8]
0x140006bbb  sub     rax, qword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x140006bc2  test    rax, rax
0x140006bc5  jnz     short loc_140006BDB
0x140006bc7  add     rcx, 8
0x140006bcb  test    r9, r9
0x140006bce  cmovz   rcx, rax
0x140006bd2  mov     [r8], rcx
0x140006bd5  lock inc dword ptr [r9+10h]
0x140006bda  retn
0x140006bdb  mov     eax, 80004002h
0x140006be0  retn
0x140006be1  xor     eax, eax
0x140006be3  jmp     short loc_140006BA1
```
