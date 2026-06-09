# Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>>::~Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>>(void)

- ea: `0x180021114`
- end: `0x1800211a7`
- name: `??1?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b150`

## callees

- `0x180021114`
- `0x1800215b0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800211a0`

## pseudocode

```c
void __fastcall Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::~Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx

  v3 = a1 + 216;
  *(_QWORD *)a1 = &Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::`vftable';
  v4 = *(_QWORD *)(a1 + 272);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *(_QWORD *)(v3 + 56) = 0;
  }
  v5 = *(_QWORD *)(a1 + 208);
  if ( v5 )
  {
    LOBYTE(a2) = v5 != a1 + 152;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, a2);
    *(_QWORD *)(a1 + 208) = 0;
  }
  Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::Reset(a1 + 56);
  *(_QWORD *)a1 = &Globals::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x180021114  mov     [rsp+arg_0], rbx
0x180021119  push    rdi
0x18002111a  sub     rsp, 20h
0x18002111e  lea     rax, ??_7?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@6B@; const Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::`vftable'
0x180021125  mov     rbx, rcx
0x180021128  lea     rdi, [rcx+0D8h]
0x18002112f  mov     [rcx], rax
0x180021132  mov     rcx, [rdi+38h]
0x180021136  test    rcx, rcx
0x180021139  jz      short loc_180021155
0x18002113b  mov     rax, [rcx]
0x18002113e  cmp     rcx, rdi
0x180021141  setnz   dl
0x180021144  mov     rax, [rax+20h]
0x180021148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002114d  mov     qword ptr [rdi+38h], 0
0x180021155  lea     rdi, [rbx+98h]
0x18002115c  mov     rcx, [rdi+38h]
0x180021160  test    rcx, rcx
0x180021163  jz      short loc_18002117F
0x180021165  mov     rax, [rcx]
0x180021168  cmp     rcx, rdi
0x18002116b  setnz   dl
0x18002116e  mov     rax, [rax+20h]
0x180021172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021177  mov     qword ptr [rdi+38h], 0
0x18002117f  lea     rcx, [rbx+38h]
0x180021183  call    ?Reset@?$Optional@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAXXZ; Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::Reset(void)
0x180021188  lea     rax, ??_7Globals@@6B@; const Globals::`vftable'
0x18002118f  lea     rcx, [rbx+8]
0x180021193  mov     [rbx], rax
0x180021196  mov     rbx, [rsp+28h+arg_0]
0x18002119b  add     rsp, 20h
0x18002119f  pop     rdi
0x1800211a0  jmp     cs:__imp_DeleteCriticalSection
```
