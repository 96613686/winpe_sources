# CMPEG2ProgramController::CMpeg2MacroVision::CompleteCopyBuffer(unsigned __int64,uchar *,int,int,CTStickyVal<int> *,Mpeg2DemuxAttributes::CAttributeList *)

- ea: `0x18001e850`
- end: `0x18001e878`
- name: `?CompleteCopyBuffer@CMpeg2MacroVision@CMPEG2ProgramController@@UEAAJ_KPEAEHHPEAV?$CTStickyVal@H@@PEAVCAttributeList@Mpeg2DemuxAttributes@@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018698`
- `0x18001e850`

## pseudocode

```c
__int64 __fastcall CMPEG2ProgramController::CMpeg2MacroVision::CompleteCopyBuffer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  if ( a7 && *(int *)(a7 + 160) > 0 )
    return 2147549183LL;
  else
    return CMacroVision::DistributeMacroVision((CMacroVision *)(a1 + 32), *(_DWORD *)(a1 + 96));
}

```

## disassembly

```asm
0x18001e850  mov     rax, [rsp+arg_30]
0x18001e855  mov     rdx, rcx
0x18001e858  test    rax, rax
0x18001e85b  jz      short loc_18001E86C
0x18001e85d  cmp     dword ptr [rax+0A0h], 0
0x18001e864  jle     short loc_18001E86C
0x18001e866  mov     eax, 8000FFFFh
0x18001e86b  retn
0x18001e86c  mov     edx, [rdx+60h]; unsigned int
0x18001e86f  add     rcx, 20h ; ' '; this
0x18001e873  jmp     ?DistributeMacroVision@CMacroVision@@QEAAJK@Z; CMacroVision::DistributeMacroVision(ulong)
```
