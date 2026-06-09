# CASFUnknownContainer::RemoveObjects(_GUID const &)

- ea: `0x18001f110`
- end: `0x18001f1ba`
- name: `?RemoveObjects@CASFUnknownContainer@@UEAAJAEBU_GUID@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(CASFUnknownContainer *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001de98`

## callees

- `0x1800049b8`
- `0x18001df5c`
- `0x18001f110`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFUnknownContainer::RemoveObjects(CASFUnknownContainer *this, const struct _GUID *a2)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  unsigned int v6; // edi
  char *i; // rbx
  __int64 v8; // rax

  v4 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a2->Data1 )
    v4 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a2->Data4;
  if ( v4 )
  {
    while ( (*(int (__fastcall **)(CASFUnknownContainer *, const struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)this + 48LL))(
              this,
              a2,
              0,
              0) >= 0 )
      ;
  }
  else
  {
    v5 = *((_DWORD *)this + 58);
    v6 = 0;
    for ( i = (char *)this + 16; v6 < v5; ++v6 )
    {
      v8 = CTDynArray<IASFUnknown *,20>::operator[](i, v6);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)i);
    *((_DWORD *)i + 54) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f110  mov     [rsp+arg_0], rbx
0x18001f115  mov     [rsp+arg_8], rsi
0x18001f11a  push    rdi
0x18001f11b  sub     rsp, 30h
0x18001f11f  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18001f126  mov     rdi, rdx
0x18001f129  mov     rbx, rcx
0x18001f12c  sub     rax, [rdx]
0x18001f12f  jnz     short loc_18001F13C
0x18001f131  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18001f138  sub     rax, [rdx+8]
0x18001f13c  test    rax, rax
0x18001f13f  jnz     short loc_18001F18C
0x18001f141  mov     esi, [rcx+0E8h]
0x18001f147  xor     edi, edi
0x18001f149  add     rbx, 10h
0x18001f14d  test    esi, esi
0x18001f14f  jz      short loc_18001F178
0x18001f151  mov     edx, edi
0x18001f153  mov     rcx, rbx
0x18001f156  call    ??A?$CTDynArray@PEAUIASFUnknown@@$0BE@@@QEBAPEAUIASFUnknown@@K@Z; CTDynArray<IASFUnknown *,20>::operator[](ulong)
0x18001f15b  mov     rdx, rax
0x18001f15e  test    rax, rax
0x18001f161  jz      short loc_18001F172
0x18001f163  mov     rcx, [rax]
0x18001f166  mov     rax, [rcx+10h]
0x18001f16a  mov     rcx, rdx
0x18001f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f172  inc     edi
0x18001f174  cmp     edi, esi
0x18001f176  jb      short loc_18001F151
0x18001f178  mov     rcx, rbx
0x18001f17b  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x18001f180  mov     dword ptr [rbx+0D8h], 0
0x18001f18a  jmp     short loc_18001F1A8
0x18001f18c  mov     rax, [rbx]
0x18001f18f  xor     r9d, r9d
0x18001f192  xor     r8d, r8d
0x18001f195  mov     rdx, rdi
0x18001f198  mov     rcx, rbx
0x18001f19b  mov     rax, [rax+30h]
0x18001f19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1a4  test    eax, eax
0x18001f1a6  jns     short loc_18001F18C
0x18001f1a8  mov     rbx, [rsp+38h+arg_0]
0x18001f1ad  xor     eax, eax
0x18001f1af  mov     rsi, [rsp+38h+arg_8]
0x18001f1b4  add     rsp, 30h
0x18001f1b8  pop     rdi
0x18001f1b9  retn
```
