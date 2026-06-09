# CW32System::CreateFontIndirect(tagLOGFONTW const *)

- ea: `0x18008d830`
- end: `0x18008d8bd`
- name: `?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z`
- size: `141`
- prototype: `HFONT __fastcall(const struct tagLOGFONTW *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0b0`
- `0x1800124f0`
- `0x18001b57c`
- `0x18002195c`
- `0x180021ef0`
- `0x180033b90`
- `0x18003b4e0`
- `0x18005f428`
- `0x18008e290`
- `0x18008f4dc`

## callees

- `0x18008d830`
- `0x18008faa4`
- `0x180091140`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x18008d8a2`
- `GDI32!CreateFontIndirectA` at `0x18008d8a2`
- `GDI32!CreateFontIndirectW` at `0x18008d84f`
- `GDI32!CreateFontIndirectW` at `0x18008d84f`

## pseudocode

```c
HFONT __fastcall CW32System::CreateFontIndirect(const struct tagLOGFONTW *a1)
{
  unsigned __int128 v2; // xmm1
  __int128 v3; // xmm0
  LOGFONTA lf; // [rsp+30h] [rbp-58h] BYREF

  if ( CW32System::_dwPlatformId != 1 )
    return CreateFontIndirectW(a1);
  v2 = *(_OWORD *)&a1->lfOrientation;
  memset(&lf.lfWeight, 0, 44);
  v3 = *(_OWORD *)&a1->lfHeight;
  lf.lfEscapement = *(_QWORD *)&a1->lfEscapement;
  *(_OWORD *)&lf.lfOrientation = v2;
  ((void (__fastcall *)(CHAR *, __int64, WCHAR *, __int64, _DWORD, int, _QWORD, _QWORD, _QWORD, _QWORD))CW32System::MbcsFromUnicode)(
    lf.lfFaceName,
    32,
    a1->lfFaceName,
    0xFFFFFFFFLL,
    0,
    1,
    v3,
    *(_QWORD *)&lf.lfEscapement,
    v2 >> 32,
    *(_QWORD *)&lf.lfOutPrecision);
  return CreateFontIndirectA(&lf);
}

```

## disassembly

```asm
0x18008d830  sub     rsp, 88h
0x18008d837  mov     rax, cs:__security_cookie
0x18008d83e  xor     rax, rsp
0x18008d841  mov     [rsp+88h+var_18], rax
0x18008d846  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18008d84d  jz      short loc_18008D857
0x18008d84f  call    cs:__imp_CreateFontIndirectW
0x18008d855  jmp     short loc_18008D8A8
0x18008d857  movups  xmm1, xmmword ptr [rcx+0Ch]
0x18008d85b  mov     [rsp+88h+var_60], 1
0x18008d863  xor     eax, eax
0x18008d865  xorps   xmm0, xmm0
0x18008d868  mov     [rsp+88h+var_68], eax
0x18008d86c  movups  xmmword ptr [rsp+88h+lf.lfFaceName+4], xmm0
0x18008d871  lea     r8, [rcx+1Ch]
0x18008d875  or      r9d, 0FFFFFFFFh
0x18008d879  movups  xmmword ptr [rsp+88h+lf.lfWeight], xmm0
0x18008d87e  lea     edx, [rax+20h]
0x18008d881  movups  xmmword ptr [rsp+88h+lf.lfFaceName+10h], xmm0
0x18008d886  movaps  xmm0, xmmword ptr [rcx]
0x18008d889  lea     rcx, [rsp+88h+lf.lfFaceName]
0x18008d88e  movups  xmmword ptr [rsp+88h+lf.lfHeight], xmm0
0x18008d893  movups  xmmword ptr [rsp+88h+lf.lfOrientation], xmm1
0x18008d898  call    ?MbcsFromUnicode@CW32System@@SAHPEADHPEBGHIW4UN_FLAGS@@@Z; CW32System::MbcsFromUnicode(char *,int,ushort const *,int,uint,UN_FLAGS)
0x18008d89d  lea     rcx, [rsp+88h+lf]; lplf
0x18008d8a2  call    cs:__imp_CreateFontIndirectA
0x18008d8a8  mov     rcx, [rsp+88h+var_18]
0x18008d8ad  xor     rcx, rsp; StackCookie
0x18008d8b0  call    __security_check_cookie
0x18008d8b5  add     rsp, 88h
0x18008d8bc  retn
```
