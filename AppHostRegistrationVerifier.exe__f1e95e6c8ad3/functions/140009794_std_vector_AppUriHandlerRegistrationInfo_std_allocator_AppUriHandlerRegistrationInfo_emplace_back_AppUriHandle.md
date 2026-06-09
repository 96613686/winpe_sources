# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::emplace_back<AppUriHandlerRegistrationInfo>(AppUriHandlerRegistrationInfo &&)

- ea: `0x140009794`
- end: `0x1400097e3`
- name: `??$emplace_back@UAppUriHandlerRegistrationInfo@@@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAAAEAUAppUriHandlerRegistrationInfo@@$$QEAU2@@Z`
- size: `79`
- prototype: `_QWORD *__fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x1400092ec`
- `0x140009794`

## pseudocode

```c
_QWORD *__fastcall std::vector<AppUriHandlerRegistrationInfo>::emplace_back<AppUriHandlerRegistrationInfo>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // r9
  __int64 v3; // rax
  __int64 v4; // rdx

  v2 = *(__int64 **)(a1 + 8);
  if ( v2 == *(__int64 **)(a1 + 16) )
    return std::vector<AppUriHandlerRegistrationInfo>::_Emplace_reallocate<AppUriHandlerRegistrationInfo>(
             (AppUriHandlerRegistrationInfo **)a1,
             *(AppUriHandlerRegistrationInfo **)(a1 + 8),
             a2);
  *v2 = *a2;
  v3 = a2[1];
  *a2 = 0;
  v2[1] = v3;
  a2[1] = 0;
  v4 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v4 + 16;
  return (_QWORD *)v4;
}

```

## disassembly

```asm
0x140009794  sub     rsp, 28h
0x140009798  mov     r9, [rcx+8]
0x14000979c  cmp     r9, [rcx+10h]
0x1400097a0  jz      short loc_1400097CD
0x1400097a2  mov     rax, [rdx]
0x1400097a5  mov     [r9], rax
0x1400097a8  mov     rax, [rdx+8]
0x1400097ac  mov     qword ptr [rdx], 0
0x1400097b3  mov     [r9+8], rax
0x1400097b7  mov     qword ptr [rdx+8], 0
0x1400097bf  mov     rdx, [rcx+8]
0x1400097c3  lea     rax, [rdx+10h]
0x1400097c7  mov     [rcx+8], rax
0x1400097cb  jmp     short loc_1400097DB
0x1400097cd  mov     r8, rdx
0x1400097d0  mov     rdx, r9
0x1400097d3  call    ??$_Emplace_reallocate@UAppUriHandlerRegistrationInfo@@@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@AEAAPEAUAppUriHandlerRegistrationInfo@@QEAU2@$$QEAU2@@Z; std::vector<AppUriHandlerRegistrationInfo>::_Emplace_reallocate<AppUriHandlerRegistrationInfo>(AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo &&)
0x1400097d8  mov     rdx, rax
0x1400097db  mov     rax, rdx
0x1400097de  add     rsp, 28h
0x1400097e2  retn
```
