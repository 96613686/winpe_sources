# BSendFullProcsets

- ea: `0x1800139e8`
- end: `0x180013adb`
- name: `BSendFullProcsets`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800146dc`

## callees

- `0x1800139e8`
- `0x1800148a8`
- `0x180015f84`
- `0x180016074`
- `0x180016940`
- `0x18001a6fc`
- `0x18001a98c`
- `0x18001aa48`

## string_xrefs

- `0x180013a10`: `/Pscript_WinNT_Full 300 dict 2 copy userdict 3 1 roll put dup begin\n`

## pseudocode

```c
_BOOL8 __fastcall BSendFullProcsets(__int64 a1)
{
  PSProcsetSend(a1, 1);
  DSCSend(a1, "%%%%BeginResource: procset Pscript_WinNT_Full 5.0 0\r\n");
  OPRawPortWrite(a1, "/Pscript_WinNT_Full 300 dict 2 copy userdict 3 1 roll put dup begin\r\n", 0x45u);
  PSProcsetSend(a1, 2);
  BSendProtocolError(a1);
  if ( *(int *)(*(_QWORD *)(a1 + 96) + 140LL) >= 2 )
    PSProcsetSend(a1, 5);
  PSProcsetSend(a1, 3);
  VMCheck(a1, 2);
  PSSendFullProcsets(a1);
  PSProcsetSend(a1, 23);
  OPRawPortWrite(a1, "end\r\n", 5u);
  OPRawPortWrite(a1, "/ProcSet defineresource pop\r\n", 0x1Du);
  DSCSend(a1, "%%%%EndResource\r\n\r\n");
  VMUse(a1, 2, 0, 0);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x1800139e8  push    rbx
0x1800139ea  sub     rsp, 20h
0x1800139ee  mov     edx, 1
0x1800139f3  mov     rbx, rcx
0x1800139f6  call    PSProcsetSend
0x1800139fb  lea     rdx, DSC_BeginProcsetRes; "%%%%BeginResource: procset Pscript_WinN"...
0x180013a02  mov     rcx, rbx
0x180013a05  call    DSCSend
0x180013a0a  mov     r8d, 45h ; 'E'
0x180013a10  lea     rdx, PSFRAG_definefulldict; "/Pscript_WinNT_Full 300 dict 2 copy use"...
0x180013a17  mov     rcx, rbx
0x180013a1a  call    OPRawPortWrite
0x180013a1f  mov     edx, 2
0x180013a24  mov     rcx, rbx
0x180013a27  call    PSProcsetSend
0x180013a2c  mov     rcx, rbx
0x180013a2f  call    BSendProtocolError
0x180013a34  mov     rax, [rbx+60h]
0x180013a38  cmp     dword ptr [rax+8Ch], 2
0x180013a3f  jl      short loc_180013A4E
0x180013a41  mov     edx, 5
0x180013a46  mov     rcx, rbx
0x180013a49  call    PSProcsetSend
0x180013a4e  mov     edx, 3
0x180013a53  mov     rcx, rbx
0x180013a56  call    PSProcsetSend
0x180013a5b  xor     r8d, r8d
0x180013a5e  mov     rcx, rbx
0x180013a61  lea     edx, [r8+2]
0x180013a65  call    VMCheck
0x180013a6a  mov     rcx, rbx
0x180013a6d  call    PSSendFullProcsets
0x180013a72  mov     edx, 17h
0x180013a77  mov     rcx, rbx
0x180013a7a  call    PSProcsetSend
0x180013a7f  mov     r8d, 5
0x180013a85  lea     rdx, PSFRAG_end; "end\r\n"
0x180013a8c  mov     rcx, rbx
0x180013a8f  call    OPRawPortWrite
0x180013a94  mov     r8d, 1Dh
0x180013a9a  lea     rdx, PSFRAG_defineprocsetres; "/ProcSet defineresource pop\r\n"
0x180013aa1  mov     rcx, rbx
0x180013aa4  call    OPRawPortWrite
0x180013aa9  lea     rdx, DSC_EndResource; "%%%%EndResource\r\n\r\n"
0x180013ab0  mov     rcx, rbx
0x180013ab3  call    DSCSend
0x180013ab8  xor     r9d, r9d
0x180013abb  xor     r8d, r8d
0x180013abe  mov     rcx, rbx
0x180013ac1  lea     edx, [r9+2]
0x180013ac5  call    VMUse
0x180013aca  xor     eax, eax
0x180013acc  cmp     [rbx+0D70h], eax
0x180013ad2  setz    al
0x180013ad5  add     rsp, 20h
0x180013ad9  pop     rbx
0x180013ada  retn
```
