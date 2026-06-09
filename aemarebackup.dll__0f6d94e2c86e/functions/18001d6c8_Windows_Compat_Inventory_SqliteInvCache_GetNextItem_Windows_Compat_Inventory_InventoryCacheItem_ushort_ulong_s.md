# Windows::Compat::Inventory::SqliteInvCache::GetNextItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001d6c8`
- end: `0x18001d810`
- name: `?GetNextItem@SqliteInvCache@Inventory@Compat@Windows@@QEAAJAEAPEAVInventoryCacheItem@234@PEAGKAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b490`
- `0x18001d820`

## callees

- `0x18000529c`
- `0x18000d5b8`
- `0x1800134b8`
- `0x18001d6c8`
- `0x18004c020`
- `0x1800ec010`

## string_xrefs

- `0x18001d7bf`: `OpenItem failed for item '%ls' [%#x]`
- `0x18001d7f3`: `OpenItem returned a null item for item '%ls' [%#x]`
- `0x18001d740`: `Windows::Compat::Inventory::SqliteInvCache::GetNextItem`
- `0x18001d7d1`: `Windows::Compat::Inventory::SqliteInvCache::GetNextItem`
- `0x18001d75e`: `StringCchCopyW failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetNextItem(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        _QWORD *a5)
{
  int v8; // ebx
  const unsigned __int16 *v9; // r8
  _QWORD *v10; // r11
  void *v11; // rbx
  _QWORD *v12; // rdx
  int v13; // eax

  *a2 = 0;
  if ( a5[1] )
  {
    v9 = (const unsigned __int16 *)(*(_QWORD *)(*a5 + 8LL) + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)(*a5 + 8LL) + 40LL) > 7u )
      v9 = *(const unsigned __int16 **)v9;
    v8 = StringCchCopyW(a3, a4, v9);
    if ( v8 == -2147024774 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::GetNextItem",
        954,
        "ItemName buffer is too small [%#x]",
        -2147024774);
    }
    else if ( v8 >= 0 )
    {
      v11 = *(void **)(*v10 + 8LL);
      v12 = *(_QWORD **)v11;
      --v10[1];
      **((_QWORD **)v11 + 1) = v12;
      v12[1] = *((_QWORD *)v11 + 1);
      std::wstring::~wstring((char **)v11 + 2);
      operator delete(v11, (const struct std::nothrow_t *)0x30);
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD *))(*(_QWORD *)a1 + 8LL))(a1, a3, a2);
      v8 = v13;
      if ( v13 >= 0 )
      {
        if ( *a2 )
        {
          return 0;
        }
        else
        {
          v8 = -2147467259;
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::GetNextItem",
            973,
            "OpenItem returned a null item for item '%ls' [%#x]",
            a3,
            -2147467259);
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::SqliteInvCache::GetNextItem",
          967,
          "OpenItem failed for item '%ls' [%#x]",
          a3,
          v13);
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::GetNextItem",
        959,
        "StringCchCopyW failed [%#x]",
        v8);
    }
  }
  else
  {
    return (unsigned int)-2147024637;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d6c8  push    rbx
0x18001d6ca  push    rsi
0x18001d6cb  push    rdi
0x18001d6cc  push    r14
0x18001d6ce  sub     rsp, 38h
0x18001d6d2  mov     rdi, r8
0x18001d6d5  mov     rsi, rdx
0x18001d6d8  mov     r14, rcx
0x18001d6db  mov     [rsp+58h+arg_8], 0
0x18001d6e4  mov     qword ptr [rdx], 0
0x18001d6eb  mov     r11, [rsp+58h+arg_20]
0x18001d6f3  cmp     qword ptr [r11+8], 0
0x18001d6f8  jnz     short loc_18001D704
0x18001d6fa  mov     ebx, 80070103h
0x18001d6ff  jmp     loc_18001D804
0x18001d704  mov     rax, [r11]
0x18001d707  mov     r8, [rax+8]
0x18001d70b  add     r8, 10h
0x18001d70f  cmp     qword ptr [r8+18h], 7
0x18001d714  jbe     short loc_18001D719
0x18001d716  mov     r8, [r8]; unsigned __int16 *
0x18001d719  mov     edx, r9d; unsigned __int64
0x18001d71c  mov     rcx, rdi; unsigned __int16 *
0x18001d71f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d724  mov     ebx, eax
0x18001d726  mov     eax, 8007007Ah
0x18001d72b  cmp     ebx, eax
0x18001d72d  jnz     short loc_18001D756
0x18001d72f  mov     dword ptr [rsp+58h+var_38], eax
0x18001d733  lea     r9, aItemnameBuffer; "ItemName buffer is too small [%#x]"
0x18001d73a  mov     r8d, 3BAh
0x18001d740  lea     rdx, aWindowsCompatI_37; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001d747  mov     ecx, 1
0x18001d74c  call    AslLogCallPrintf
0x18001d751  jmp     loc_18001D804
0x18001d756  test    ebx, ebx
0x18001d758  jns     short loc_18001D76D
0x18001d75a  mov     dword ptr [rsp+58h+var_38], ebx
0x18001d75e  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x18001d765  mov     r8d, 3BFh
0x18001d76b  jmp     short loc_18001D740
0x18001d76d  mov     rax, [r11]
0x18001d770  mov     rbx, [rax+8]
0x18001d774  mov     rdx, [rbx]
0x18001d777  dec     qword ptr [r11+8]
0x18001d77b  mov     rax, [rbx+8]
0x18001d77f  mov     [rax], rdx
0x18001d782  mov     rax, [rbx+8]
0x18001d786  mov     [rdx+8], rax
0x18001d78a  lea     rcx, [rbx+10h]
0x18001d78e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d793  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18001d798  mov     rcx, rbx; void *
0x18001d79b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d7a0  mov     rax, [r14]
0x18001d7a3  mov     r8, rsi
0x18001d7a6  mov     rdx, rdi
0x18001d7a9  mov     rcx, r14
0x18001d7ac  mov     rax, [rax+8]
0x18001d7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b5  mov     ebx, eax
0x18001d7b7  test    eax, eax
0x18001d7b9  jns     short loc_18001D7E4
0x18001d7bb  mov     [rsp+58h+var_30], eax
0x18001d7bf  lea     r9, aOpenitemFailed; "OpenItem failed for item '%ls' [%#x]"
0x18001d7c6  mov     r8d, 3C7h
0x18001d7cc  mov     [rsp+58h+var_38], rdi
0x18001d7d1  lea     rdx, aWindowsCompatI_37; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001d7d8  mov     ecx, 1
0x18001d7dd  call    AslLogCallPrintf
0x18001d7e2  jmp     short loc_18001D804
0x18001d7e4  cmp     qword ptr [rsi], 0
0x18001d7e8  jnz     short loc_18001D802
0x18001d7ea  mov     ebx, 80004005h
0x18001d7ef  mov     [rsp+58h+var_30], ebx
0x18001d7f3  lea     r9, aOpenitemReturn; "OpenItem returned a null item for item "...
0x18001d7fa  mov     r8d, 3CDh
0x18001d800  jmp     short loc_18001D7CC
0x18001d802  xor     ebx, ebx
0x18001d804  mov     eax, ebx
0x18001d806  add     rsp, 38h
0x18001d80a  pop     r14
0x18001d80c  pop     rdi
0x18001d80d  pop     rsi
0x18001d80e  pop     rbx
0x18001d80f  retn
```
