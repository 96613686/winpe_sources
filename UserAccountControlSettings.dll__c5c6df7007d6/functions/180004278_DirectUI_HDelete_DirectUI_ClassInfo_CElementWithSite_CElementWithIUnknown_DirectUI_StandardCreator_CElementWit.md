# DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)

- ea: `0x180004278`
- end: `0x18000429f`
- name: `??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z`
- size: `39`
- prototype: `void __fastcall(DirectUI *this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f10`
- `0x180005160`
- `0x180009ec0`
- `0x180009f60`
- `0x18000a0d0`
- `0x18000a0f0`
- `0x18000ac30`
- `0x18000acd0`
- `0x18000ad80`
- `0x18000ada0`

## callees

- `0x1800051fc`
- `0x18000c010`

## pseudocode

```c
void __fastcall DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(
        DirectUI *this)
{
  void *v2; // rdx

  (*(void (__fastcall **)(DirectUI *, _QWORD))(*(_QWORD *)this + 144LL))(this, 0);
  DirectUI::HFree(this, v2);
}

```

## disassembly

```asm
0x180004278  push    rbx
0x18000427a  sub     rsp, 20h
0x18000427e  mov     rax, [rcx]
0x180004281  xor     edx, edx
0x180004283  mov     rbx, rcx
0x180004286  mov     rax, [rax+90h]
0x18000428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004292  mov     rcx, rbx; this
0x180004295  add     rsp, 20h
0x180004299  pop     rbx
0x18000429a  jmp     ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
```
