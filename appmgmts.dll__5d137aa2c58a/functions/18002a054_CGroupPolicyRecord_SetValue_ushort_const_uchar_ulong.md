# CGroupPolicyRecord::SetValue(ushort const *,uchar *,ulong)

- ea: `0x18002a054`
- end: `0x18002a109`
- name: `?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAEK@Z`
- size: `181`
- prototype: `__int64 __fastcall(CGroupPolicyRecord *this, const unsigned __int16 *, unsigned __int8 *, ULONG)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009584`

## callees

- `0x18002a054`
- `0x18002aa84`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002a07c`
- `OLEAUT32!__imp_VariantInit` at `0x18002a07c`
- `OLEAUT32!__imp_VariantClear` at `0x18002a0ee`
- `OLEAUT32!__imp_VariantClear` at `0x18002a0ee`

## string_xrefs

- `0x18002a0d4`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CGroupPolicyRecord::SetValue(
        CGroupPolicyRecord *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        ULONG a4)
{
  HRESULT v7; // esi
  __int64 v8; // rbx
  VARIANTARG pvarg; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h]
  unsigned __int8 v12; // [rsp+88h] [rbp+20h] BYREF

  v11 = 0;
  VariantInit(&pvarg);
  if ( a4 )
  {
    v8 = 0;
    while ( 1 )
    {
      v12 = a3[v8];
      v7 = CVariant::SetNextArrayElement((CVariant *)&pvarg, 0x11u, a4, &v12);
      if ( v7 < 0 )
        break;
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= a4 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(**((_QWORD **)this + 1)
                                                                                              + 40LL))(
               *((_QWORD *)this + 1),
               L"SecurityDescriptor",
               0,
               &pvarg,
               0);
        break;
      }
    }
  }
  else
  {
    v7 = 0;
  }
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a054  mov     rax, rsp
0x18002a057  mov     [rax+8], rbx
0x18002a05b  mov     [rax+10h], rbp
0x18002a05f  push    rsi
0x18002a060  push    rdi
0x18002a061  push    r14
0x18002a063  sub     rsp, 50h
0x18002a067  mov     r14, rcx
0x18002a06a  mov     qword ptr [rax-20h], 0
0x18002a072  lea     rcx, [rax-38h]; pvarg
0x18002a076  mov     edi, r9d
0x18002a079  mov     rbp, r8
0x18002a07c  call    cs:__imp_VariantInit
0x18002a082  test    edi, edi
0x18002a084  jnz     short loc_18002A08A
0x18002a086  xor     esi, esi
0x18002a088  jmp     short loc_18002A0E9
0x18002a08a  xor     ebx, ebx
0x18002a08c  test    edi, edi
0x18002a08e  jz      short loc_18002A0C0
0x18002a090  mov     cl, [rbx+rbp]
0x18002a093  lea     r9, [rsp+68h+arg_18]; void *
0x18002a09b  mov     [rsp+68h+arg_18], cl
0x18002a0a2  mov     edx, 11h; unsigned __int16
0x18002a0a7  lea     rcx, [rsp+68h+pvarg]; this
0x18002a0ac  mov     r8d, edi; unsigned int
0x18002a0af  call    ?SetNextArrayElement@CVariant@@AEAAJGKPEAX@Z; CVariant::SetNextArrayElement(ushort,ulong,void *)
0x18002a0b4  mov     esi, eax
0x18002a0b6  test    eax, eax
0x18002a0b8  js      short loc_18002A0E9
0x18002a0ba  inc     ebx
0x18002a0bc  cmp     ebx, edi
0x18002a0be  jb      short loc_18002A090
0x18002a0c0  mov     rcx, [r14+8]
0x18002a0c4  lea     r9, [rsp+68h+pvarg]
0x18002a0c9  xor     r8d, r8d
0x18002a0cc  mov     [rsp+68h+var_48], 0
0x18002a0d4  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18002a0db  mov     rax, [rcx]
0x18002a0de  mov     rax, [rax+28h]
0x18002a0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0e7  mov     esi, eax
0x18002a0e9  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002a0ee  call    cs:__imp_VariantClear
0x18002a0f4  mov     rbx, [rsp+68h+arg_0]
0x18002a0f9  mov     eax, esi
0x18002a0fb  mov     rbp, [rsp+68h+arg_8]
0x18002a100  add     rsp, 50h
0x18002a104  pop     r14
0x18002a106  pop     rdi
0x18002a107  pop     rsi
0x18002a108  retn
```
