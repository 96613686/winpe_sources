# ATL::CSid::operator=(_SID const &)

- ea: `0x180031094`
- end: `0x180031151`
- name: `??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002da4c`
- `0x180030260`

## callees

- `0x180002034`
- `0x180002604`
- `0x180031094`
- `0x18003151c`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1800310f7`
- `ADVAPI32!GetLengthSid` at `0x1800310f7`
- `ADVAPI32!CopySid` at `0x180031111`
- `ADVAPI32!CopySid` at `0x180031111`
- `ADVAPI32!IsValidSid` at `0x1800310ea`
- `ADVAPI32!IsValidSid` at `0x1800310ea`

## pseudocode

```c
__int64 __fastcall ATL::CSid::operator=(__int64 a1, void *a2)
{
  void *v2; // rsi
  DWORD LengthSid; // eax
  int Error; // eax

  v2 = (void *)(a1 + 8);
  if ( !*(_BYTE *)(a1 + 76) || v2 != a2 )
  {
    *(_DWORD *)(a1 + 80) = 7;
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 88);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 96);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 104);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 112);
    *(_BYTE *)(a1 + 76) = 0;
    if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
      ATL::AtlThrowImpl(-2147024809);
    _mm_lfence();
    *(_BYTE *)(a1 + 76) = 1;
    if ( !CopySid(LengthSid, v2, a2) )
    {
      Error = ATL::AtlHresultFromLastError();
      *(_BYTE *)(a1 + 76) = 0;
      ATL::AtlThrowImpl(Error);
    }
    *(_DWORD *)(a1 + 80) = 8;
  }
  return a1;
}

```

## disassembly

```asm
0x180031094  mov     [rsp+arg_0], rbx
0x180031099  mov     [rsp+arg_8], rsi
0x18003109e  push    rdi
0x18003109f  sub     rsp, 20h
0x1800310a3  cmp     byte ptr [rcx+4Ch], 0
0x1800310a7  lea     rsi, [rcx+8]
0x1800310ab  mov     rdi, rdx
0x1800310ae  mov     rbx, rcx
0x1800310b1  jz      short loc_1800310B8
0x1800310b3  cmp     rsi, rdx
0x1800310b6  jz      short loc_180031122
0x1800310b8  mov     dword ptr [rcx+50h], 7
0x1800310bf  add     rcx, 58h ; 'X'
0x1800310c3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800310c8  lea     rcx, [rbx+60h]
0x1800310cc  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800310d1  lea     rcx, [rbx+68h]
0x1800310d5  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800310da  lea     rcx, [rbx+70h]
0x1800310de  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800310e3  mov     rcx, rdi; pSid
0x1800310e6  mov     byte ptr [rbx+4Ch], 0
0x1800310ea  call    cs:__imp_IsValidSid
0x1800310f0  test    eax, eax
0x1800310f2  jz      short loc_180031146
0x1800310f4  mov     rcx, rdi; pSid
0x1800310f7  call    cs:__imp_GetLengthSid
0x1800310fd  cmp     eax, 44h ; 'D'
0x180031100  ja      short loc_180031146
0x180031102  lfence
0x180031105  mov     r8, rdi; pSourceSid
0x180031108  mov     byte ptr [rbx+4Ch], 1
0x18003110c  mov     rdx, rsi; pDestinationSid
0x18003110f  mov     ecx, eax; nDestinationSidLength
0x180031111  call    cs:__imp_CopySid
0x180031117  test    eax, eax
0x180031119  jz      short loc_180031135
0x18003111b  mov     dword ptr [rbx+50h], 8
0x180031122  mov     rsi, [rsp+28h+arg_8]
0x180031127  mov     rax, rbx
0x18003112a  mov     rbx, [rsp+28h+arg_0]
0x18003112f  add     rsp, 20h
0x180031133  pop     rdi
0x180031134  retn
0x180031135  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003113a  mov     ecx, eax; int
0x18003113c  mov     byte ptr [rbx+4Ch], 0
0x180031140  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180031146  mov     ecx, 80070057h; int
0x18003114b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
