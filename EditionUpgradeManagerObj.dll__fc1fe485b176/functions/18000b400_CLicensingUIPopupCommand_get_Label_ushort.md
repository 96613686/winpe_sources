# CLicensingUIPopupCommand::get_Label(ushort * *)

- ea: `0x18000b400`
- end: `0x18000b441`
- name: `?get_Label@CLicensingUIPopupCommand@@UEAAJPEAPEAG@Z`
- size: `65`
- prototype: `__int64 __fastcall(HMODULE *this, unsigned __int16 **Src, __int64, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b400`
- `0x180017d2c`

## pseudocode

```c
__int64 __fastcall CLicensingUIPopupCommand::get_Label(HMODULE *this, unsigned __int16 **Src, __int64 a3, void *a4)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-18h]

  if ( !Src )
  {
    v4 = -2147024809;
    v5 = -2147024809;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_6;
  }
  v6 = TResourceStringAllocCopyEx<unsigned short *>(this[2], *((unsigned int *)this + 11), a3, a4, v8, (void **)Src);
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = v6;
    goto LABEL_5;
  }
LABEL_6:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18000b400  push    rbx
0x18000b402  sub     rsp, 30h
0x18000b406  test    rdx, rdx
0x18000b409  jnz     short loc_18000B414
0x18000b40b  mov     ebx, 80070057h
0x18000b410  mov     ecx, ebx
0x18000b412  jmp     short loc_18000B42D
0x18000b414  mov     [rsp+38h+Src], rdx; Src
0x18000b419  mov     edx, [rcx+2Ch]; int
0x18000b41c  mov     rcx, [rcx+10h]; int
0x18000b420  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000b425  mov     ebx, eax
0x18000b427  test    eax, eax
0x18000b429  jns     short loc_18000B432
0x18000b42b  mov     ecx, eax
0x18000b42d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b432  mov     ecx, ebx
0x18000b434  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b439  mov     eax, ebx
0x18000b43b  add     rsp, 30h
0x18000b43f  pop     rbx
0x18000b440  retn
```
