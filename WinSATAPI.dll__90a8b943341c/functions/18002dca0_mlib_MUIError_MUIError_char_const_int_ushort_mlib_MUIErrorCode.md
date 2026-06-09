# mlib::MUIError::MUIError(char const *,int,ushort,mlib::MUIErrorCode)

- ea: `0x18002dca0`
- end: `0x18002dd38`
- name: `??0MUIError@mlib@@QEAA@PEBDHGW4MUIErrorCode@1@@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002dd40`
- `0x18002df78`

## callees

- `0x18002dca0`

## string_xrefs

- `0x18002dca4`: `base\winsat\api-dll\winsatcominterface.cpp`
- `0x18002dce1`: `a MUIError was created incorrectly`

## pseudocode

```c
__int64 __fastcall mlib::MUIError::MUIError(__int64 a1, __int64 a2, int a3, __int16 a4, int a5)
{
  const wchar_t *v5; // rax

  *(_QWORD *)a1 = "base\\winsat\\api-dll\\winsatcominterface.cpp";
  *(_DWORD *)(a1 + 8) = a3;
  *(_WORD *)(a1 + 12) = a4;
  *(_DWORD *)(a1 + 16) = a5;
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1:
        v5 = L"resource ID does not exist";
        break;
      case 2:
        v5 = L"cannot get the size of the string";
        break;
      case 3:
        v5 = L"cannot load the resource";
        break;
      case 4:
        v5 = L"cannot lock the resource";
        break;
      case 5:
        v5 = L"the string is zero length";
        break;
      case 6:
        v5 = L"the string is not null terminated";
        break;
      case 7:
        v5 = L"string formatting error";
        break;
      default:
        v5 = L"a MUIError was created incorrectly";
        break;
    }
  }
  else
  {
    v5 = L"MUI string loader sub-system not initilized";
  }
  *(_QWORD *)(a1 + 24) = v5;
  return a1;
}

```

## disassembly

```asm
0x18002dca0  mov     edx, [rsp+arg_20]
0x18002dca4  lea     rax, aBaseWinsatApiD; "base\\winsat\\api-dll\\winsatcominterfa"...
0x18002dcab  mov     [rcx], rax
0x18002dcae  mov     [rcx+8], r8d
0x18002dcb2  mov     [rcx+0Ch], r9w
0x18002dcb7  mov     [rcx+10h], edx
0x18002dcba  test    edx, edx
0x18002dcbc  jz      short loc_18002DD29
0x18002dcbe  sub     edx, 1
0x18002dcc1  jz      short loc_18002DD20
0x18002dcc3  sub     edx, 1
0x18002dcc6  jz      short loc_18002DD17
0x18002dcc8  sub     edx, 1
0x18002dccb  jz      short loc_18002DD0E
0x18002dccd  sub     edx, 1
0x18002dcd0  jz      short loc_18002DD05
0x18002dcd2  sub     edx, 1
0x18002dcd5  jz      short loc_18002DCFC
0x18002dcd7  sub     edx, 1
0x18002dcda  jz      short loc_18002DCF3
0x18002dcdc  cmp     edx, 1
0x18002dcdf  jz      short loc_18002DCEA
0x18002dce1  lea     rax, aAMuierrorWasCr; "a MUIError was created incorrectly"
0x18002dce8  jmp     short loc_18002DD30
0x18002dcea  lea     rax, aStringFormatti; "string formatting error"
0x18002dcf1  jmp     short loc_18002DD30
0x18002dcf3  lea     rax, aTheStringIsNot; "the string is not null terminated"
0x18002dcfa  jmp     short loc_18002DD30
0x18002dcfc  lea     rax, aTheStringIsZer; "the string is zero length"
0x18002dd03  jmp     short loc_18002DD30
0x18002dd05  lea     rax, aCannotLockTheR; "cannot lock the resource"
0x18002dd0c  jmp     short loc_18002DD30
0x18002dd0e  lea     rax, aCannotLoadTheR; "cannot load the resource"
0x18002dd15  jmp     short loc_18002DD30
0x18002dd17  lea     rax, aCannotGetTheSi; "cannot get the size of the string"
0x18002dd1e  jmp     short loc_18002DD30
0x18002dd20  lea     rax, aResourceIdDoes; "resource ID does not exist"
0x18002dd27  jmp     short loc_18002DD30
0x18002dd29  lea     rax, aMuiStringLoade; "MUI string loader sub-system not initil"...
0x18002dd30  mov     [rcx+18h], rax
0x18002dd34  mov     rax, rcx
0x18002dd37  retn
```
