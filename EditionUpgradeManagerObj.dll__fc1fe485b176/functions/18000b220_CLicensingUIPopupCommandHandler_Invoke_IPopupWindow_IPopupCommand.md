# CLicensingUIPopupCommandHandler::Invoke(IPopupWindow *,IPopupCommand *)

- ea: `0x18000b220`
- end: `0x18000b27c`
- name: `?Invoke@CLicensingUIPopupCommandHandler@@UEAAJPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(CLicensingUIPopupCommandHandler *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b220`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CLicensingUIPopupCommandHandler::Invoke(
        CLicensingUIPopupCommandHandler *this,
        struct IPopupWindow *a2,
        struct IPopupCommand *a3)
{
  int v3; // ecx
  unsigned int v4; // ebx
  __int64 (__fastcall *v5)(struct IPopupWindow *, struct IPopupCommand *, _QWORD); // rax
  int v6; // eax

  if ( !a2 || !a3 )
  {
    v3 = -2147024809;
    v4 = -2147024809;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    goto LABEL_9;
  }
  v5 = (__int64 (__fastcall *)(struct IPopupWindow *, struct IPopupCommand *, _QWORD))*((_QWORD *)this + 2);
  if ( !v5 )
  {
    v4 = -2147418113;
    v3 = -2147418113;
    goto LABEL_8;
  }
  v6 = v5(a2, a3, *((_QWORD *)this + 3));
  v4 = v6;
  if ( v6 < 0 )
  {
    v3 = v6;
    goto LABEL_8;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18000b220  push    rbx
0x18000b222  sub     rsp, 20h
0x18000b226  mov     r9, r8
0x18000b229  mov     r10, rdx
0x18000b22c  test    rdx, rdx
0x18000b22f  jnz     short loc_18000B23A
0x18000b231  mov     ecx, 80070057h
0x18000b236  mov     ebx, ecx
0x18000b238  jmp     short loc_18000B268
0x18000b23a  test    r9, r9
0x18000b23d  jz      short loc_18000B231
0x18000b23f  mov     rax, [rcx+10h]
0x18000b243  test    rax, rax
0x18000b246  jnz     short loc_18000B251
0x18000b248  mov     ebx, 8000FFFFh
0x18000b24d  mov     ecx, ebx
0x18000b24f  jmp     short loc_18000B268
0x18000b251  mov     r8, [rcx+18h]
0x18000b255  mov     rdx, r9
0x18000b258  mov     rcx, r10
0x18000b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b260  mov     ebx, eax
0x18000b262  test    eax, eax
0x18000b264  jns     short loc_18000B26D
0x18000b266  mov     ecx, eax
0x18000b268  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b26d  mov     ecx, ebx
0x18000b26f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b274  mov     eax, ebx
0x18000b276  add     rsp, 20h
0x18000b27a  pop     rbx
0x18000b27b  retn
```
