# CLicensingUIPopupCommand::get_ID(uint *)

- ea: `0x18000b3c0`
- end: `0x18000b3ef`
- name: `?get_ID@CLicensingUIPopupCommand@@UEAAJPEAI@Z`
- size: `47`
- prototype: `__int64 __fastcall(CLicensingUIPopupCommand *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b3c0`

## pseudocode

```c
__int64 __fastcall CLicensingUIPopupCommand::get_ID(CLicensingUIPopupCommand *this, unsigned int *a2)
{
  unsigned int v2; // ebx

  if ( a2 )
  {
    v2 = 0;
    *a2 = *((_DWORD *)this + 10);
  }
  else
  {
    v2 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024809);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x18000b3c0  push    rbx
0x18000b3c2  sub     rsp, 20h
0x18000b3c6  test    rdx, rdx
0x18000b3c9  jnz     short loc_18000B3D9
0x18000b3cb  mov     ebx, 80070057h
0x18000b3d0  mov     ecx, ebx
0x18000b3d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b3d7  jmp     short loc_18000B3E0
0x18000b3d9  mov     ecx, [rcx+28h]
0x18000b3dc  xor     ebx, ebx
0x18000b3de  mov     [rdx], ecx
0x18000b3e0  mov     ecx, ebx
0x18000b3e2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b3e7  mov     eax, ebx
0x18000b3e9  add     rsp, 20h
0x18000b3ed  pop     rbx
0x18000b3ee  retn
```
