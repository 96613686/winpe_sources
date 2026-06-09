# ATL::CSid::operator=(_SID const &)

- ea: `0x14000958c`
- end: `0x140009646`
- name: `??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000cd94`
- `0x14000d3bc`

## callees

- `0x14000958c`
- `0x14000a220`
- `0x14000a2e8`
- `0x14000ba64`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400095ef`
- `ADVAPI32!GetLengthSid` at `0x1400095ef`
- `ADVAPI32!IsValidSid` at `0x1400095e2`
- `ADVAPI32!IsValidSid` at `0x1400095e2`
- `ADVAPI32!CopySid` at `0x140009606`
- `ADVAPI32!CopySid` at `0x140009606`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CSid::operator=(__int64 a1, void *a2)
{
  void *v2; // rsi
  DWORD LengthSid; // eax
  int Error; // eax

  v2 = (void *)(a1 + 8);
  if ( !*(_BYTE *)(a1 + 76) || v2 != a2 )
  {
    *(_DWORD *)(a1 + 80) = 7;
    ATL::CSimpleStringT<wchar_t,0>::Empty(a1 + 88);
    ATL::CSimpleStringT<wchar_t,0>::Empty(a1 + 96);
    ATL::CSimpleStringT<wchar_t,0>::Empty(a1 + 104);
    ATL::CSimpleStringT<wchar_t,0>::Empty(a1 + 112);
    *(_BYTE *)(a1 + 76) = 0;
    if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
      ATL::AtlThrowImpl(-2147024809);
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
0x14000958c  mov     [rsp+arg_0], rbx
0x140009591  mov     [rsp+arg_8], rsi
0x140009596  push    rdi
0x140009597  sub     rsp, 20h
0x14000959b  cmp     byte ptr [rcx+4Ch], 0
0x14000959f  lea     rsi, [rcx+8]
0x1400095a3  mov     rdi, rdx
0x1400095a6  mov     rbx, rcx
0x1400095a9  jz      short loc_1400095B0
0x1400095ab  cmp     rsi, rdx
0x1400095ae  jz      short loc_140009617
0x1400095b0  mov     dword ptr [rcx+50h], 7
0x1400095b7  add     rcx, 58h ; 'X'
0x1400095bb  call    ?Empty@?$CSimpleStringT@_W$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,0>::Empty(void)
0x1400095c0  lea     rcx, [rbx+60h]
0x1400095c4  call    ?Empty@?$CSimpleStringT@_W$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,0>::Empty(void)
0x1400095c9  lea     rcx, [rbx+68h]
0x1400095cd  call    ?Empty@?$CSimpleStringT@_W$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,0>::Empty(void)
0x1400095d2  lea     rcx, [rbx+70h]
0x1400095d6  call    ?Empty@?$CSimpleStringT@_W$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,0>::Empty(void)
0x1400095db  mov     rcx, rdi; pSid
0x1400095de  mov     byte ptr [rbx+4Ch], 0
0x1400095e2  call    cs:__imp_IsValidSid
0x1400095e8  test    eax, eax
0x1400095ea  jz      short loc_14000963B
0x1400095ec  mov     rcx, rdi; pSid
0x1400095ef  call    cs:__imp_GetLengthSid
0x1400095f5  cmp     eax, 44h ; 'D'
0x1400095f8  ja      short loc_14000963B
0x1400095fa  mov     r8, rdi; pSourceSid
0x1400095fd  mov     byte ptr [rbx+4Ch], 1
0x140009601  mov     rdx, rsi; pDestinationSid
0x140009604  mov     ecx, eax; nDestinationSidLength
0x140009606  call    cs:__imp_CopySid
0x14000960c  test    eax, eax
0x14000960e  jz      short loc_14000962A
0x140009610  mov     dword ptr [rbx+50h], 8
0x140009617  mov     rsi, [rsp+28h+arg_8]
0x14000961c  mov     rax, rbx
0x14000961f  mov     rbx, [rsp+28h+arg_0]
0x140009624  add     rsp, 20h
0x140009628  pop     rdi
0x140009629  retn
0x14000962a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000962f  mov     ecx, eax; int
0x140009631  mov     byte ptr [rbx+4Ch], 0
0x140009635  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000963b  mov     ecx, 80070057h; int
0x140009640  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
