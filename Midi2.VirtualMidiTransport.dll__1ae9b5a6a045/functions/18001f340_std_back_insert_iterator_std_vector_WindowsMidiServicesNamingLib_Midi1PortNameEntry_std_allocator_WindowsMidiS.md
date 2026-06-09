# std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>::operator=(WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)

- ea: `0x18001f340`
- end: `0x18001f405`
- name: `??4?$back_insert_iterator@V?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@QEAAAEAV01@$$QEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001f40c`

## callees

- `0x18001ef14`
- `0x18001f340`

## pseudocode

```c
_QWORD **__fastcall std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(
        _QWORD **a1,
        __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  v4 = *a1;
  v5 = v4[1];
  if ( v5 == v4[2] )
  {
    std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Emplace_reallocate<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(
      v4,
      (_BYTE *)v5,
      a2);
  }
  else
  {
    *(_OWORD *)v5 = *(_OWORD *)a2;
    *(_OWORD *)(v5 + 16) = *(_OWORD *)(a2 + 16);
    *(_OWORD *)(v5 + 32) = *(_OWORD *)(a2 + 32);
    *(_OWORD *)(v5 + 48) = *(_OWORD *)(a2 + 48);
    *(_OWORD *)(v5 + 64) = *(_OWORD *)(a2 + 64);
    *(_OWORD *)(v5 + 80) = *(_OWORD *)(a2 + 80);
    *(_OWORD *)(v5 + 96) = *(_OWORD *)(a2 + 96);
    *(_OWORD *)(v5 + 112) = *(_OWORD *)(a2 + 112);
    *(_OWORD *)(v5 + 128) = *(_OWORD *)(a2 + 128);
    *(_OWORD *)(v5 + 144) = *(_OWORD *)(a2 + 144);
    *(_OWORD *)(v5 + 160) = *(_OWORD *)(a2 + 160);
    *(_OWORD *)(v5 + 176) = *(_OWORD *)(a2 + 176);
    *(_QWORD *)(v5 + 192) = *(_QWORD *)(a2 + 192);
    v4[1] += 200LL;
  }
  return a1;
}

```

## disassembly

```asm
0x18001f340  push    rbx
0x18001f342  sub     rsp, 20h
0x18001f346  mov     rbx, rcx
0x18001f349  mov     r8, rdx
0x18001f34c  mov     rcx, [rcx]
0x18001f34f  mov     rdx, [rcx+8]
0x18001f353  cmp     rdx, [rcx+10h]
0x18001f357  jz      loc_18001F3F7
0x18001f35d  movups  xmm0, xmmword ptr [r8]
0x18001f361  movups  xmmword ptr [rdx], xmm0
0x18001f364  movups  xmm1, xmmword ptr [r8+10h]
0x18001f369  movups  xmmword ptr [rdx+10h], xmm1
0x18001f36d  movups  xmm0, xmmword ptr [r8+20h]
0x18001f372  movups  xmmword ptr [rdx+20h], xmm0
0x18001f376  movups  xmm1, xmmword ptr [r8+30h]
0x18001f37b  movups  xmmword ptr [rdx+30h], xmm1
0x18001f37f  movups  xmm0, xmmword ptr [r8+40h]
0x18001f384  movups  xmmword ptr [rdx+40h], xmm0
0x18001f388  movups  xmm1, xmmword ptr [r8+50h]
0x18001f38d  movups  xmmword ptr [rdx+50h], xmm1
0x18001f391  movups  xmm0, xmmword ptr [r8+60h]
0x18001f396  movups  xmmword ptr [rdx+60h], xmm0
0x18001f39a  movups  xmm1, xmmword ptr [r8+70h]
0x18001f39f  movups  xmmword ptr [rdx+70h], xmm1
0x18001f3a3  movups  xmm0, xmmword ptr [r8+80h]
0x18001f3ab  movups  xmmword ptr [rdx+80h], xmm0
0x18001f3b2  movups  xmm1, xmmword ptr [r8+90h]
0x18001f3ba  movups  xmmword ptr [rdx+90h], xmm1
0x18001f3c1  movups  xmm0, xmmword ptr [r8+0A0h]
0x18001f3c9  movups  xmmword ptr [rdx+0A0h], xmm0
0x18001f3d0  movups  xmm1, xmmword ptr [r8+0B0h]
0x18001f3d8  movups  xmmword ptr [rdx+0B0h], xmm1
0x18001f3df  mov     rax, [r8+0C0h]
0x18001f3e6  mov     [rdx+0C0h], rax
0x18001f3ed  add     qword ptr [rcx+8], 0C8h
0x18001f3f5  jmp     short loc_18001F3FC
0x18001f3f7  call    ??$_Emplace_reallocate@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@AEAAPEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@QEAU23@$$QEAU23@@Z; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Emplace_reallocate<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(WindowsMidiServicesNamingLib::Midi1PortNameEntry * const,WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)
0x18001f3fc  mov     rax, rbx
0x18001f3ff  add     rsp, 20h
0x18001f403  pop     rbx
0x18001f404  retn
```
