# CSyncEventFilterInfo::Load(IPropertyBag *,SYNC_FILTER_EVENT)

- ea: `0x18003a25c`
- end: `0x18003a336`
- name: `?Load@CSyncEventFilterInfo@@QEAAJPEAUIPropertyBag@@W4SYNC_FILTER_EVENT@@@Z`
- size: `218`
- prototype: `int __high(struct IPropertyBag *, enum SYNC_FILTER_EVENT)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003a340`

## callees

- `0x180005660`
- `0x18003a25c`
- `0x18004f870`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18003a2c0`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18003a301`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18003a2c0`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x18003a301`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a2e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a320`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a2e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a320`

## pseudocode

```c
__int64 __fastcall CSyncEventFilterInfo::Load(__int64 a1, IPropertyBag *a2)
{
  unsigned __int16 *v2; // r14
  unsigned __int16 *v4; // rsi
  BSTR value; // [rsp+40h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)a1 = 14;
  v2 = (unsigned __int16 *)(a1 + 4);
  *(_WORD *)(a1 + 4) = 0;
  v4 = (unsigned __int16 *)(a1 + 132);
  *(_WORD *)(a1 + 132) = 0;
  if ( a2 )
  {
    SHPropertyBag_ReadDWORDDef(a2, a2, a1);
    if ( !*(_DWORD *)a1 )
      *(_DWORD *)a1 = 14;
    value = 0;
    if ( PSPropertyBag_ReadBSTR(a2, L"SyncHandlerFilter", &value) >= 0 )
    {
      StringCchCopyW(v2, 0x40u, value);
      SysFreeString(value);
    }
    bstrString = 0;
    if ( PSPropertyBag_ReadBSTR(a2, L"ContentGroupFilter", &bstrString) >= 0 )
    {
      StringCchCopyW(v4, 0x40u, bstrString);
      SysFreeString(bstrString);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003a25c  mov     [rsp+arg_10], rbx
0x18003a261  push    rsi
0x18003a262  push    rdi
0x18003a263  push    r14
0x18003a265  sub     rsp, 20h
0x18003a269  xor     eax, eax
0x18003a26b  mov     dword ptr [rcx], 0Eh
0x18003a271  lea     r14, [rcx+4]
0x18003a275  mov     rdi, rdx
0x18003a278  mov     [r14], ax
0x18003a27c  lea     rsi, [rcx+84h]
0x18003a283  mov     [rsi], ax
0x18003a286  mov     rbx, rcx
0x18003a289  test    rdx, rdx
0x18003a28c  jz      loc_18003A326
0x18003a292  mov     r8, rcx
0x18003a295  mov     rcx, rdx
0x18003a298  call    SHPropertyBag_ReadDWORDDef
0x18003a29d  cmp     dword ptr [rbx], 0
0x18003a2a0  jnz     short loc_18003A2A8
0x18003a2a2  mov     dword ptr [rbx], 0Eh
0x18003a2a8  lea     r8, [rsp+38h+value]; value
0x18003a2ad  mov     [rsp+38h+value], 0
0x18003a2b6  lea     rdx, aSynchandlerfil_0; "SyncHandlerFilter"
0x18003a2bd  mov     rcx, rdi; propBag
0x18003a2c0  call    cs:__imp_PSPropertyBag_ReadBSTR
0x18003a2c6  mov     ebx, 40h ; '@'
0x18003a2cb  test    eax, eax
0x18003a2cd  js      short loc_18003A2E9
0x18003a2cf  mov     r8, [rsp+38h+value]; unsigned __int16 *
0x18003a2d4  mov     edx, ebx; unsigned __int64
0x18003a2d6  mov     rcx, r14; unsigned __int16 *
0x18003a2d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a2de  mov     rcx, [rsp+38h+value]; bstrString
0x18003a2e3  call    cs:__imp_SysFreeString
0x18003a2e9  lea     r8, [rsp+38h+bstrString]; value
0x18003a2ee  mov     [rsp+38h+bstrString], 0
0x18003a2f7  lea     rdx, aContentgroupfi_0; "ContentGroupFilter"
0x18003a2fe  mov     rcx, rdi; propBag
0x18003a301  call    cs:__imp_PSPropertyBag_ReadBSTR
0x18003a307  test    eax, eax
0x18003a309  js      short loc_18003A326
0x18003a30b  mov     r8, [rsp+38h+bstrString]; unsigned __int16 *
0x18003a310  mov     rdx, rbx; unsigned __int64
0x18003a313  mov     rcx, rsi; unsigned __int16 *
0x18003a316  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a31b  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18003a320  call    cs:__imp_SysFreeString
0x18003a326  mov     rbx, [rsp+38h+arg_10]
0x18003a32b  xor     eax, eax
0x18003a32d  add     rsp, 20h
0x18003a331  pop     r14
0x18003a333  pop     rdi
0x18003a334  pop     rsi
0x18003a335  retn
```
