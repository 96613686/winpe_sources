# InitializeSetupAPI(void)

- ea: `0x180007968`
- end: `0x1800079b7`
- name: `?InitializeSetupAPI@@YAHXZ`
- size: `79`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180006d24`
- `0x180006e54`
- `0x1800071c0`
- `0x180007454`
- `0x1800088c4`

## callees

- `0x180007968`
- `0x180008a6c`
- `0x180008f2c`

## string_xrefs

- `0x18000798b`: `SETUPAPI.DLL`

## pseudocode

```c
__int64 __fastcall InitializeSetupAPI(const unsigned __int16 *a1)
{
  if ( hLibModule )
    return 1;
  hLibModule = MyLoadLibrary(a1);
  if ( hLibModule )
    return 1;
  MsgBox2Param(0, 0x455u, L"SETUPAPI.DLL", 0, 0x10u, 0);
  return 0;
}

```

## disassembly

```asm
0x180007968  sub     rsp, 38h
0x18000796c  cmp     cs:hLibModule, 0
0x180007974  jnz     short loc_1800079AD
0x180007976  call    ?MyLoadLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; MyLoadLibrary(ushort const *)
0x18000797b  mov     cs:hLibModule, rax
0x180007982  test    rax, rax
0x180007985  jnz     short loc_1800079AD
0x180007987  mov     [rsp+38h+var_10], eax; unsigned int
0x18000798b  lea     r8, FileName; "SETUPAPI.DLL"
0x180007992  xor     r9d, r9d; unsigned __int16 *
0x180007995  mov     [rsp+38h+var_18], 10h; unsigned int
0x18000799d  mov     edx, 455h; uID
0x1800079a2  xor     ecx, ecx; hWnd
0x1800079a4  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800079a9  xor     eax, eax
0x1800079ab  jmp     short loc_1800079B2
0x1800079ad  mov     eax, 1
0x1800079b2  add     rsp, 38h
0x1800079b6  retn
```
