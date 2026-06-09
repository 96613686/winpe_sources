# ContactsStaticFilter::CreateInstance(_SQLCEBLOB *,__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001,utl::vector<OLITEMID,utl::allocator<OLITEMID>> *,IndexedFiltering::IStaticFilter * *)

- ea: `0x18001e008`
- end: `0x18001e102`
- name: `?CreateInstance@ContactsStaticFilter@@SAJPEAU_SQLCEBLOB@@W4__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001@@PEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@PEAPEAUIStaticFilter@IndexedFiltering@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015b60`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x18001e008`
- `0x18001e294`

## string_xrefs

- `0x18001e0bd`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e0df`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`

## pseudocode

```c
__int64 __fastcall ContactsStaticFilter::CreateInstance(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  int v13; // [rsp+34h] [rbp-34h]

  v8 = operator new(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *v8 = &IndexedFiltering::IStaticFilter::`vftable';
    v8[1] = &_CUnknownBase::`vftable';
    *((_DWORD *)v8 + 4) = 1;
    *v8 = &ContactsStaticFilter::`vftable'{for `IndexedFiltering::IStaticFilter'};
    v8[1] = &ContactsStaticFilter::`vftable'{for `CUnknownPrivate'};
    *((_DWORD *)v8 + 6) = 0;
    *((_DWORD *)v8 + 7) = v13;
    v8[4] = 0;
    *((_DWORD *)v8 + 10) = 0;
    *((_DWORD *)v8 + 12) = 0;
    *((_DWORD *)v8 + 13) = v13;
    v8[7] = 0;
    v8[8] = 0;
    v10 = ContactsStaticFilter::Initialize(v8, a1, a2, a3);
    v11 = v10;
    if ( v10 >= 0 )
    {
      *a4 = v9;
      return 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        38);
      return v11;
    }
  }
  else
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      33);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001e008  push    rbx
0x18001e00a  push    rbp
0x18001e00b  push    rsi
0x18001e00c  push    rdi
0x18001e00d  push    r14
0x18001e00f  sub     rsp, 40h
0x18001e013  mov     r14, rcx
0x18001e016  mov     rsi, r9
0x18001e019  mov     ecx, 48h ; 'H'; Size
0x18001e01e  mov     rdi, r8
0x18001e021  mov     ebp, edx
0x18001e023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e028  mov     rbx, rax
0x18001e02b  test    rax, rax
0x18001e02e  jz      loc_18001E0DA
0x18001e034  lea     rax, ??_7IStaticFilter@IndexedFiltering@@6B@; const IndexedFiltering::IStaticFilter::`vftable'
0x18001e03b  mov     r9, rdi
0x18001e03e  mov     [rbx], rax
0x18001e041  mov     r8d, ebp
0x18001e044  lea     rax, ??_7_CUnknownBase@@6B@; const _CUnknownBase::`vftable'
0x18001e04b  mov     rdx, r14
0x18001e04e  mov     [rbx+8], rax
0x18001e052  mov     rcx, rbx
0x18001e055  mov     dword ptr [rbx+10h], 1
0x18001e05c  lea     rax, ??_7ContactsStaticFilter@@6BIStaticFilter@IndexedFiltering@@@; const ContactsStaticFilter::`vftable'{for `IndexedFiltering::IStaticFilter'}
0x18001e063  mov     [rbx], rax
0x18001e066  lea     rax, ??_7ContactsStaticFilter@@6BCUnknownPrivate@@@; const ContactsStaticFilter::`vftable'{for `CUnknownPrivate'}
0x18001e06d  mov     [rbx+8], rax
0x18001e071  mov     eax, [rsp+68h+var_34]
0x18001e075  mov     dword ptr [rbx+18h], 0
0x18001e07c  mov     [rbx+1Ch], eax
0x18001e07f  mov     eax, [rsp+68h+var_34]
0x18001e083  mov     qword ptr [rbx+20h], 0
0x18001e08b  mov     dword ptr [rbx+28h], 0
0x18001e092  mov     dword ptr [rbx+30h], 0
0x18001e099  mov     [rbx+34h], eax
0x18001e09c  mov     qword ptr [rbx+38h], 0
0x18001e0a4  mov     qword ptr [rbx+40h], 0
0x18001e0ac  call    ?Initialize@ContactsStaticFilter@@IEAAJPEAU_SQLCEBLOB@@W4__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001@@PEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; ContactsStaticFilter::Initialize(_SQLCEBLOB *,__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001,utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x18001e0b1  mov     edi, eax
0x18001e0b3  test    eax, eax
0x18001e0b5  jns     short loc_18001E0D3
0x18001e0b7  mov     r9d, 26h ; '&'
0x18001e0bd  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e0c4  mov     ecx, eax
0x18001e0c6  lea     edx, [r9-25h]
0x18001e0ca  call    Log_HREvent
0x18001e0cf  mov     eax, edi
0x18001e0d1  jmp     short loc_18001E0F7
0x18001e0d3  mov     [rsi], rbx
0x18001e0d6  xor     eax, eax
0x18001e0d8  jmp     short loc_18001E0F7
0x18001e0da  mov     ebx, 8007000Eh
0x18001e0df  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e0e6  mov     ecx, ebx
0x18001e0e8  mov     r9d, 21h ; '!'
0x18001e0ee  xor     edx, edx
0x18001e0f0  call    Log_HREvent
0x18001e0f5  mov     eax, ebx
0x18001e0f7  add     rsp, 40h
0x18001e0fb  pop     r14
0x18001e0fd  pop     rdi
0x18001e0fe  pop     rsi
0x18001e0ff  pop     rbp
0x18001e100  pop     rbx
0x18001e101  retn
```
