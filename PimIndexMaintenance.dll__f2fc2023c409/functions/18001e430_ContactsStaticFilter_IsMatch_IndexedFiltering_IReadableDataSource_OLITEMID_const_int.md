# ContactsStaticFilter::IsMatch(IndexedFiltering::IReadableDataSource *,OLITEMID const &,int *)

- ea: `0x18001e430`
- end: `0x18001e5d0`
- name: `?IsMatch@ContactsStaticFilter@@UEAAJPEAUIReadableDataSource@IndexedFiltering@@AEBUOLITEMID@@PEAH@Z`
- size: `416`
- prototype: `__int64 __fastcall(ContactsStaticFilter *__hidden this, struct IndexedFiltering::IReadableDataSource *, const struct OLITEMID *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003f0c`
- `0x1800086a0`
- `0x18000b5f4`
- `0x18001e20c`
- `0x18001e430`
- `0x180022010`

## string_xrefs

- `0x18001e515`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e545`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e563`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`

## pseudocode

```c
__int64 __fastcall ContactsStaticFilter::IsMatch(
        ContactsStaticFilter *this,
        struct IndexedFiltering::IReadableDataSource *a2,
        const struct OLITEMID *a3,
        int *a4)
{
  _DWORD **v6; // rcx
  _DWORD *v9; // rax
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct IndexedFiltering::IReadableDataSource *, const struct OLITEMID *, _DWORD *, __int64, _QWORD *, __int64 *); // rbx
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  _WORD *v17; // rbx
  _DWORD v18[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-20h] BYREF
  _WORD *v20; // [rsp+70h] [rbp+8h] BYREF

  v6 = (_DWORD **)*((_QWORD *)this + 8);
  if ( v6 )
  {
    v9 = *v6;
    if ( 0xAAAAAAAAAAAAAAABuLL * (v6[1] - *v6) )
    {
      while ( v9 != v6[1] )
      {
        if ( *v9 == *(_DWORD *)a3 && v9[1] == *((_DWORD *)a3 + 1) && v9[2] == *((_DWORD *)a3 + 2) )
        {
          *a4 = 0;
          return 0;
        }
        v9 += 3;
      }
    }
  }
  v11 = *(_QWORD *)a2;
  v18[0] = 29622291;
  v18[1] = 29687873;
  v20 = 0;
  v12 = *(__int64 (__fastcall **)(struct IndexedFiltering::IReadableDataSource *, const struct OLITEMID *, _DWORD *, __int64, _QWORD *, __int64 *))(v11 + 24);
  v19 = 0;
  v13 = tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v20);
  v14 = v12(a2, a3, v18, 2, v13, &v19);
  v16 = v14;
  if ( v14 >= 0 )
  {
    v17 = v20;
    if ( (v20[3] & 0x300) != 0 )
    {
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        321);
      v17 = v20;
    }
    if ( (v17[15] & 0x300) != 0 )
    {
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        323);
      v17 = v20;
    }
    *a4 = ((*((_DWORD *)v17 + 2) & *((_DWORD *)this + 10)) != 0
        || (unsigned int)StoreFilterBlob::HasCommonSetBit(
                           (ContactsStaticFilter *)((char *)this + 24),
                           (const struct _SQLCEBLOB *)(v17 + 16)))
       && (unsigned int)StoreFilterBlob::HasCommonSetBit(
                          (ContactsStaticFilter *)((char *)this + 48),
                          (const struct _SQLCEBLOB *)(v17 + 16));
    v16 = 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      318);
  }
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v20);
  return v16;
}

```

## disassembly

```asm
0x18001e430  mov     [rsp+arg_8], rbx
0x18001e435  mov     [rsp+arg_10], rsi
0x18001e43a  push    rdi
0x18001e43b  push    r14
0x18001e43d  push    r15
0x18001e43f  sub     rsp, 50h
0x18001e443  mov     rdi, rcx
0x18001e446  mov     rsi, r9
0x18001e449  mov     rcx, [rcx+40h]
0x18001e44d  mov     r14, r8
0x18001e450  mov     r15, rdx
0x18001e453  test    rcx, rcx
0x18001e456  jz      short loc_18001E4AE
0x18001e458  mov     r8, [rcx+8]
0x18001e45c  mov     rax, [rcx]
0x18001e45f  mov     r10, r8
0x18001e462  sub     r10, rax
0x18001e465  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18001e46f  sar     r10, 2
0x18001e473  imul    r10, rcx
0x18001e477  test    r10, r10
0x18001e47a  jz      short loc_18001E4AE
0x18001e47c  cmp     rax, r8
0x18001e47f  jz      short loc_18001E4AE
0x18001e481  mov     ecx, [r14]
0x18001e484  cmp     [rax], ecx
0x18001e486  jnz     short loc_18001E49A
0x18001e488  mov     ecx, [r14+4]
0x18001e48c  cmp     [rax+4], ecx
0x18001e48f  jnz     short loc_18001E49A
0x18001e491  mov     ecx, [r14+8]
0x18001e495  cmp     [rax+8], ecx
0x18001e498  jz      short loc_18001E4A0
0x18001e49a  add     rax, 0Ch
0x18001e49e  jmp     short loc_18001E47C
0x18001e4a0  mov     dword ptr [r9], 0
0x18001e4a7  xor     eax, eax
0x18001e4a9  jmp     loc_18001E5BA
0x18001e4ae  mov     rax, [rdx]
0x18001e4b1  lea     rcx, [rsp+68h+arg_0]
0x18001e4b6  mov     [rsp+68h+var_28], 1C40013h
0x18001e4be  mov     [rsp+68h+var_24], 1C50041h
0x18001e4c6  mov     [rsp+68h+arg_0], 0
0x18001e4cf  mov     rbx, [rax+18h]
0x18001e4d3  mov     [rsp+68h+var_20], 0
0x18001e4dc  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x18001e4e1  lea     rcx, [rsp+68h+var_20]
0x18001e4e6  mov     r9d, 2
0x18001e4ec  mov     [rsp+68h+var_40], rcx
0x18001e4f1  lea     r8, [rsp+68h+var_28]
0x18001e4f6  mov     [rsp+68h+var_48], rax
0x18001e4fb  mov     rdx, r14
0x18001e4fe  mov     rax, rbx
0x18001e501  mov     rcx, r15
0x18001e504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e509  mov     ebx, eax
0x18001e50b  test    eax, eax
0x18001e50d  jns     short loc_18001E52D
0x18001e50f  mov     r9d, 13Eh
0x18001e515  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e51c  mov     edx, 1
0x18001e521  mov     ecx, eax
0x18001e523  call    Log_HREvent
0x18001e528  jmp     loc_18001E5AE
0x18001e52d  mov     rbx, [rsp+68h+arg_0]
0x18001e532  mov     r14d, 300h
0x18001e538  test    [rbx+6], r14w
0x18001e53d  jz      short loc_18001E556
0x18001e53f  mov     r8d, 141h
0x18001e545  lea     rdx, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e54c  call    Log_AssertionEvent
0x18001e551  mov     rbx, [rsp+68h+arg_0]
0x18001e556  test    [rbx+1Eh], r14w
0x18001e55b  jz      short loc_18001E574
0x18001e55d  mov     r8d, 143h
0x18001e563  lea     rdx, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e56a  call    Log_AssertionEvent
0x18001e56f  mov     rbx, [rsp+68h+arg_0]
0x18001e574  mov     eax, [rbx+8]
0x18001e577  test    [rdi+28h], eax
0x18001e57a  jnz     short loc_18001E58D
0x18001e57c  lea     rdx, [rbx+20h]; struct _SQLCEBLOB *
0x18001e580  lea     rcx, [rdi+18h]; this
0x18001e584  call    ?HasCommonSetBit@StoreFilterBlob@@QEBAHPEBU_SQLCEBLOB@@@Z; StoreFilterBlob::HasCommonSetBit(_SQLCEBLOB const *)
0x18001e589  test    eax, eax
0x18001e58b  jz      short loc_18001E59E
0x18001e58d  lea     rdx, [rbx+20h]; struct _SQLCEBLOB *
0x18001e591  lea     rcx, [rdi+30h]; this
0x18001e595  call    ?HasCommonSetBit@StoreFilterBlob@@QEBAHPEBU_SQLCEBLOB@@@Z; StoreFilterBlob::HasCommonSetBit(_SQLCEBLOB const *)
0x18001e59a  test    eax, eax
0x18001e59c  jnz     short loc_18001E5A6
0x18001e59e  mov     dword ptr [rsi], 0
0x18001e5a4  jmp     short loc_18001E5AC
0x18001e5a6  mov     dword ptr [rsi], 1
0x18001e5ac  xor     ebx, ebx
0x18001e5ae  lea     rcx, [rsp+68h+arg_0]
0x18001e5b3  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18001e5b8  mov     eax, ebx
0x18001e5ba  lea     r11, [rsp+68h+var_18]
0x18001e5bf  mov     rbx, [r11+28h]
0x18001e5c3  mov     rsi, [r11+30h]
0x18001e5c7  mov     rsp, r11
0x18001e5ca  pop     r15
0x18001e5cc  pop     r14
0x18001e5ce  pop     rdi
0x18001e5cf  retn
```
