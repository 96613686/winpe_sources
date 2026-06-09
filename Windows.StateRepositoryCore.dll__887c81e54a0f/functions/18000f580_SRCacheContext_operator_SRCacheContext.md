# SRCacheContext::operator=(SRCacheContext &&)

- ea: `0x18000f580`
- end: `0x18000f5bf`
- name: `??4SRCacheContext@@QEAAAEAU0@$$QEAU0@@Z`
- size: `63`
- prototype: `HKEY *__fastcall(HKEY *, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f6a4`
- `0x18000f880`

## callees

- `0x18000be00`
- `0x18000f580`

## pseudocode

```c
HKEY *__fastcall SRCacheContext::operator=(HKEY *a1, HKEY *a2)
{
  HKEY v4; // rax

  if ( a1 != a2 )
  {
    Common::AutoHandleCloseHKEY<HKEY__ *>(*a1);
    *a1 = 0;
    v4 = *a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f580  mov     [rsp+arg_0], rbx
0x18000f585  push    rdi
0x18000f586  sub     rsp, 20h
0x18000f58a  mov     rdi, rdx
0x18000f58d  mov     rbx, rcx
0x18000f590  cmp     rcx, rdx
0x18000f593  jz      short loc_18000F5B1
0x18000f595  mov     rcx, [rcx]
0x18000f598  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000f59d  mov     qword ptr [rbx], 0
0x18000f5a4  mov     rax, [rdi]
0x18000f5a7  mov     qword ptr [rdi], 0
0x18000f5ae  mov     [rbx], rax
0x18000f5b1  mov     rax, rbx
0x18000f5b4  mov     rbx, [rsp+28h+arg_0]
0x18000f5b9  add     rsp, 20h
0x18000f5bd  pop     rdi
0x18000f5be  retn
```
