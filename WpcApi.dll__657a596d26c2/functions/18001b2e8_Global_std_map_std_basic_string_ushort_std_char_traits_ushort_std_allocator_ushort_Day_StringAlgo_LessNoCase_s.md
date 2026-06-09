# Global<std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Day>>>>::~Global<std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Day>>>>(void)

- ea: `0x18001b2e8`
- end: `0x18001b385`
- name: `??1?$Global@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@ULessNoCase@StringAlgo@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@@std@@@2@@std@@@@QEAA@XZ`
- size: `157`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b110`

## callees

- `0x18001b2e8`
- `0x18001b4fc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b37e`

## pseudocode

```c
void __fastcall Global<std::map<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>>>::~Global<std::map<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx

  v3 = a1 + 152;
  *(_QWORD *)a1 = &Global<std::map<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>>>::`vftable';
  v4 = *(_QWORD *)(a1 + 208);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *(_QWORD *)(v3 + 56) = 0;
  }
  v5 = *(_QWORD *)(a1 + 144);
  if ( v5 )
  {
    LOBYTE(a2) = v5 != a1 + 88;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, a2);
    *(_QWORD *)(a1 + 144) = 0;
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>,0>>();
    *(_QWORD *)(a1 + 80) = 0;
  }
  *(_QWORD *)a1 = &Globals::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x18001b2e8  mov     [rsp+arg_0], rbx
0x18001b2ed  push    rdi
0x18001b2ee  sub     rsp, 20h
0x18001b2f2  lea     rax, ??_7?$Global@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@ULessNoCase@StringAlgo@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@@std@@@2@@std@@@@6B@; const Global<std::map<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>>>::`vftable'
0x18001b2f9  mov     rbx, rcx
0x18001b2fc  lea     rdi, [rcx+98h]
0x18001b303  mov     [rcx], rax
0x18001b306  mov     rcx, [rdi+38h]
0x18001b30a  test    rcx, rcx
0x18001b30d  jz      short loc_18001B329
0x18001b30f  mov     rax, [rcx]
0x18001b312  cmp     rcx, rdi
0x18001b315  setnz   dl
0x18001b318  mov     rax, [rax+20h]
0x18001b31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b321  mov     qword ptr [rdi+38h], 0
0x18001b329  lea     rdi, [rbx+58h]
0x18001b32d  mov     rcx, [rdi+38h]
0x18001b331  test    rcx, rcx
0x18001b334  jz      short loc_18001B350
0x18001b336  mov     rax, [rcx]
0x18001b339  cmp     rcx, rdi
0x18001b33c  setnz   dl
0x18001b33f  mov     rax, [rax+20h]
0x18001b343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b348  mov     qword ptr [rdi+38h], 0
0x18001b350  mov     rcx, [rbx+50h]
0x18001b354  test    rcx, rcx
0x18001b357  jz      short loc_18001B366
0x18001b359  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@ULessNoCase@StringAlgo@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VDay@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Day,StringAlgo::LessNoCase,std::allocator<std::pair<std::wstring const,Day>>,0>>(void)
0x18001b35e  mov     qword ptr [rbx+50h], 0
0x18001b366  lea     rax, ??_7Globals@@6B@; const Globals::`vftable'
0x18001b36d  lea     rcx, [rbx+8]
0x18001b371  mov     [rbx], rax
0x18001b374  mov     rbx, [rsp+28h+arg_0]
0x18001b379  add     rsp, 20h
0x18001b37d  pop     rdi
0x18001b37e  jmp     cs:__imp_DeleteCriticalSection
```
