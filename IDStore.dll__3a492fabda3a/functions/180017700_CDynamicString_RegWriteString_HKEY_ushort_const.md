# CDynamicString::RegWriteString(HKEY__ *,ushort const *)

- ea: `0x180017700`
- end: `0x180017759`
- name: `?RegWriteString@CDynamicString@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `89`
- prototype: `LSTATUS __fastcall(const BYTE **this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017760`

## callees

- `0x180017700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017735`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017735`

## pseudocode

```c
LSTATUS __fastcall CDynamicString::RegWriteString(const BYTE **this, HKEY a2, const unsigned __int16 *a3)
{
  unsigned __int64 cbData; // rax
  LSTATUS result; // eax

  cbData = 2LL * *((unsigned int *)this + 2);
  if ( cbData > 0xFFFFFFFF )
    return -2147024362;
  result = RegSetValueExW(a2, a3, 0, 1u, *this, cbData);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180017700  sub     rsp, 38h
0x180017704  mov     eax, [rcx+8]
0x180017707  mov     r11, rdx
0x18001770a  add     rax, rax
0x18001770d  mov     edx, 0FFFFFFFFh
0x180017712  mov     r10, r8
0x180017715  cmp     rax, rdx
0x180017718  ja      short loc_18001774F
0x18001771a  mov     [rsp+38h+cbData], eax; cbData
0x18001771e  mov     r9d, 1; dwType
0x180017724  mov     rax, [rcx]
0x180017727  xor     r8d, r8d; Reserved
0x18001772a  mov     rcx, r11; hKey
0x18001772d  mov     [rsp+38h+lpData], rax; lpData
0x180017732  mov     rdx, r10; lpValueName
0x180017735  call    cs:__imp_RegSetValueExW
0x18001773b  test    eax, eax
0x18001773d  jz      short loc_18001774B
0x18001773f  jle     short loc_180017754
0x180017741  movzx   eax, ax
0x180017744  or      eax, 80070000h
0x180017749  jmp     short loc_180017754
0x18001774b  xor     eax, eax
0x18001774d  jmp     short loc_180017754
0x18001774f  mov     eax, 80070216h
0x180017754  add     rsp, 38h
0x180017758  retn
```
