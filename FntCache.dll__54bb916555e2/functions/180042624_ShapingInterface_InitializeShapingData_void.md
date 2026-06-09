# ShapingInterface::InitializeShapingData(void)

- ea: `0x180042624`
- end: `0x180042709`
- name: `?InitializeShapingData@ShapingInterface@@AEAAAEBV?$map@IUSlotData@ShapingCacheElement@@U?$less@I@std@@U?$allocator@U?$pair@$$CBIUSlotData@ShapingCacheElement@@@std@@@StackAllocator@@@std@@XZ`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800423e0`

## callees

- `0x180042624`
- `0x1800b8744`
- `0x1800cd8c8`

## import_xrefs

- `TextShaping!ShapingLoadScriptEngine` at `0x180042676`
- `TextShaping!ShapingLoadScriptEngine` at `0x1800426dc`
- `TextShaping!ShapingLoadScriptEngine` at `0x180042676`
- `TextShaping!ShapingLoadScriptEngine` at `0x1800426dc`
- `TextShaping!ShapingCreateFontCacheData` at `0x18004265f`
- `TextShaping!ShapingCreateFontCacheData` at `0x18004265f`

## pseudocode

```c
__int64 __fastcall ShapingInterface::InitializeShapingData(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int FontCacheData; // eax
  int ScriptEngine; // eax
  ShapingException *v7; // rax
  ShapingException *v8; // rax
  char v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (a1 + 16) & -(__int64)(a1 != 0);
  v3 = (a1 + 8) & -(__int64)(a1 != 0);
  FontCacheData = ShapingCreateFontCacheData(a1, v3, v2, 0);
  if ( FontCacheData )
  {
    v7 = ShapingException::ShapingException((ShapingException *)&v9, FontCacheData);
    LogAndThrow<ShapingException>(v7, 0x656570616873LL, 372);
  }
  ScriptEngine = ShapingLoadScriptEngine(a1, v3, v2, *(unsigned int *)(a1 + 104));
  if ( ScriptEngine == -200 )
  {
    if ( !*(_DWORD *)(a1 + 104) )
    {
LABEL_8:
      v8 = ShapingException::ShapingException((ShapingException *)&v9, ScriptEngine);
      LogAndThrow<ShapingException>(v8, 0x656570616873LL, 390);
    }
    *(_DWORD *)(a1 + 104) = 0;
    ScriptEngine = ShapingLoadScriptEngine(a1, v3, v2, 0);
  }
  if ( ScriptEngine )
    goto LABEL_8;
  return a1 + 144;
}

```

## disassembly

```asm
0x180042624  mov     [rsp+arg_8], rbx
0x180042629  mov     [rsp+arg_10], rsi
0x18004262e  push    rdi
0x18004262f  sub     rsp, 20h
0x180042633  lea     rdx, [rcx+10h]
0x180042637  mov     rax, rcx
0x18004263a  neg     rax
0x18004263d  mov     rbx, rcx
0x180042640  mov     rax, rcx
0x180042643  sbb     rdi, rdi
0x180042646  and     rdi, rdx
0x180042649  lea     rdx, [rcx+8]
0x18004264d  neg     rax
0x180042650  mov     r8, rdi
0x180042653  sbb     rsi, rsi
0x180042656  xor     r9d, r9d
0x180042659  and     rsi, rdx
0x18004265c  mov     rdx, rsi
0x18004265f  call    cs:__imp_ShapingCreateFontCacheData
0x180042665  test    eax, eax
0x180042667  jnz     short loc_18004269E
0x180042669  mov     r9d, [rbx+68h]
0x18004266d  mov     r8, rdi
0x180042670  mov     rdx, rsi
0x180042673  mov     rcx, rbx
0x180042676  call    cs:__imp_ShapingLoadScriptEngine
0x18004267c  cmp     eax, 0FFFFFF38h
0x180042681  jz      short loc_1800426C3
0x180042683  test    eax, eax
0x180042685  jnz     short loc_1800426E4
0x180042687  mov     rsi, [rsp+28h+arg_10]
0x18004268c  lea     rax, [rbx+90h]
0x180042693  mov     rbx, [rsp+28h+arg_8]
0x180042698  add     rsp, 20h
0x18004269c  pop     rdi
0x18004269d  retn
0x18004269e  mov     edx, eax; int
0x1800426a0  lea     rcx, [rsp+28h+arg_0]; this
0x1800426a5  call    ??0ShapingException@@QEAA@H@Z; ShapingException::ShapingException(int)
0x1800426aa  mov     rdx, 656570616873h
0x1800426b4  mov     r8d, 174h
0x1800426ba  mov     rcx, rax
0x1800426bd  call    ??$LogAndThrow@VShapingException@@@@YAXAEBVShapingException@@VEventTag@@I@Z; LogAndThrow<ShapingException>(ShapingException const &,EventTag,uint)
0x1800426c3  cmp     dword ptr [rbx+68h], 0
0x1800426c7  jz      short loc_1800426E4
0x1800426c9  xor     r9d, r9d
0x1800426cc  mov     dword ptr [rbx+68h], 0
0x1800426d3  mov     r8, rdi
0x1800426d6  mov     rdx, rsi
0x1800426d9  mov     rcx, rbx
0x1800426dc  call    cs:__imp_ShapingLoadScriptEngine
0x1800426e2  jmp     short loc_180042683
0x1800426e4  mov     edx, eax; int
0x1800426e6  lea     rcx, [rsp+28h+arg_0]; this
0x1800426eb  call    ??0ShapingException@@QEAA@H@Z; ShapingException::ShapingException(int)
0x1800426f0  mov     rdx, 656570616873h
0x1800426fa  mov     r8d, 186h
0x180042700  mov     rcx, rax
0x180042703  call    ??$LogAndThrow@VShapingException@@@@YAXAEBVShapingException@@VEventTag@@I@Z; LogAndThrow<ShapingException>(ShapingException const &,EventTag,uint)
```
