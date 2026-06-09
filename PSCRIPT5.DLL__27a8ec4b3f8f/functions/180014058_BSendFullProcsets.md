# BSendFullProcsets

- ea: `0x180014058`
- end: `0x18001414c`
- name: `BSendFullProcsets`
- size: `244`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014d7c`

## callees

- `0x180014058`
- `0x180014f48`
- `0x1800166c0`
- `0x1800167b0`
- `0x1800170a0`
- `0x18001b034`
- `0x18001b2cc`
- `0x18001b388`

## string_xrefs

- `0x180014080`: `/Pscript_WinNT_Full 300 dict 2 copy userdict 3 1 roll put dup begin\n`

## pseudocode

```c
_BOOL8 __fastcall BSendFullProcsets(__int64 a1)
{
  PSProcsetSend((_DWORD *)a1, 1);
  DSCSend(a1, "%%%%BeginResource: procset Pscript_WinNT_Full 5.0 0\r\n");
  OPRawPortWrite(a1, "/Pscript_WinNT_Full 300 dict 2 copy userdict 3 1 roll put dup begin\r\n", 0x45u);
  PSProcsetSend((_DWORD *)a1, 2);
  BSendProtocolError(a1);
  if ( *(int *)(*(_QWORD *)(a1 + 96) + 140LL) >= 2 )
    PSProcsetSend((_DWORD *)a1, 5);
  PSProcsetSend((_DWORD *)a1, 3);
  VMCheck(a1, 2u, 0);
  PSSendFullProcsets((int *)a1);
  PSProcsetSend((_DWORD *)a1, 23);
  OPRawPortWrite(a1, "end\r\n", 5u);
  OPRawPortWrite(a1, "/ProcSet defineresource pop\r\n", 0x1Du);
  DSCSend(a1, "%%%%EndResource\r\n\r\n");
  VMUse((_DWORD *)a1, 2u, 0, 0);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180014058  push    rbx
0x18001405a  sub     rsp, 20h
0x18001405e  mov     edx, 1
0x180014063  mov     rbx, rcx
0x180014066  call    PSProcsetSend
0x18001406b  lea     rdx, DSC_BeginProcsetRes; "%%%%BeginResource: procset Pscript_WinN"...
0x180014072  mov     rcx, rbx
0x180014075  call    DSCSend
0x18001407a  mov     r8d, 45h ; 'E'
0x180014080  lea     rdx, PSFRAG_definefulldict; "/Pscript_WinNT_Full 300 dict 2 copy use"...
0x180014087  mov     rcx, rbx
0x18001408a  call    OPRawPortWrite
0x18001408f  mov     edx, 2
0x180014094  mov     rcx, rbx
0x180014097  call    PSProcsetSend
0x18001409c  mov     rcx, rbx
0x18001409f  call    BSendProtocolError
0x1800140a4  mov     rax, [rbx+60h]
0x1800140a8  cmp     dword ptr [rax+8Ch], 2
0x1800140af  jl      short loc_1800140BE
0x1800140b1  mov     edx, 5
0x1800140b6  mov     rcx, rbx
0x1800140b9  call    PSProcsetSend
0x1800140be  mov     edx, 3
0x1800140c3  mov     rcx, rbx
0x1800140c6  call    PSProcsetSend
0x1800140cb  xor     r8d, r8d
0x1800140ce  mov     rcx, rbx
0x1800140d1  lea     edx, [r8+2]
0x1800140d5  call    VMCheck
0x1800140da  mov     rcx, rbx
0x1800140dd  call    PSSendFullProcsets
0x1800140e2  mov     edx, 17h
0x1800140e7  mov     rcx, rbx
0x1800140ea  call    PSProcsetSend
0x1800140ef  mov     r8d, 5
0x1800140f5  lea     rdx, PSFRAG_end; "end\r\n"
0x1800140fc  mov     rcx, rbx
0x1800140ff  call    OPRawPortWrite
0x180014104  mov     r8d, 1Dh
0x18001410a  lea     rdx, PSFRAG_defineprocsetres; "/ProcSet defineresource pop\r\n"
0x180014111  mov     rcx, rbx
0x180014114  call    OPRawPortWrite
0x180014119  lea     rdx, DSC_EndResource; "%%%%EndResource\r\n\r\n"
0x180014120  mov     rcx, rbx
0x180014123  call    DSCSend
0x180014128  xor     r9d, r9d
0x18001412b  xor     r8d, r8d
0x18001412e  mov     rcx, rbx
0x180014131  lea     edx, [r9+2]
0x180014135  call    VMUse
0x18001413a  xor     eax, eax
0x18001413c  cmp     [rbx+0D70h], eax
0x180014142  setz    al
0x180014145  add     rsp, 20h
0x180014149  pop     rbx
0x18001414a  retn
```
