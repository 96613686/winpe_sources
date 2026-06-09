# WX_WIN32_FROM_HR

- ea: `0x180009eac`
- end: `0x180009f0c`
- name: `WX_WIN32_FROM_HR`
- size: `96`
- prototype: `ULONG __fastcall(int)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800054bc`
- `0x180005924`
- `0x18000604c`
- `0x180007988`
- `0x180007b64`
- `0x180008cd0`
- `0x180008e40`
- `0x18000f670`
- `0x1800111cc`
- `0x180011548`
- `0x180011858`

## callees

- `0x180009eac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009ee4`
- `ntdll!RtlNtStatusToDosError` at `0x180009ee4`

## pseudocode

```c
ULONG __fastcall WX_WIN32_FROM_HR(int a1)
{
  ULONG result; // eax

  if ( (a1 & 0x1FFF0000) == 0xC0000 )
    return (unsigned __int16)a1;
  if ( a1 >= 0 )
    return 0;
  if ( (a1 & 0x1FFF0000) == 0x70000 )
  {
    result = (unsigned __int16)a1;
    if ( !(_WORD)a1 )
      return 317;
  }
  else
  {
    if ( (a1 & 0x10000000) == 0 )
      return a1;
    result = RtlNtStatusToDosError(a1 & 0xEFFFFFFF);
    if ( !result || result == 317 )
      return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180009eac  push    rbx
0x180009eae  sub     rsp, 20h
0x180009eb2  mov     eax, ecx
0x180009eb4  mov     ebx, ecx
0x180009eb6  and     eax, 1FFF0000h
0x180009ebb  cmp     eax, 0C0000h
0x180009ec0  jnz     short loc_180009EC7
0x180009ec2  movzx   eax, bx
0x180009ec5  jmp     short loc_180009F06
0x180009ec7  test    ebx, ebx
0x180009ec9  js      short loc_180009ECF
0x180009ecb  xor     eax, eax
0x180009ecd  jmp     short loc_180009F06
0x180009ecf  cmp     eax, 70000h
0x180009ed4  jz      short loc_180009EF9
0x180009ed6  bt      ebx, 1Ch
0x180009eda  jb      short loc_180009EE0
0x180009edc  mov     eax, ebx
0x180009ede  jmp     short loc_180009F06
0x180009ee0  btr     ecx, 1Ch; Status
0x180009ee4  call    cs:__imp_RtlNtStatusToDosError
0x180009eea  test    eax, eax
0x180009eec  jz      short loc_180009EDC
0x180009eee  mov     ecx, 13Dh
0x180009ef3  cmp     eax, ecx
0x180009ef5  jnz     short loc_180009F06
0x180009ef7  jmp     short loc_180009EDC
0x180009ef9  movzx   eax, bx
0x180009efc  mov     ecx, 13Dh
0x180009f01  test    eax, eax
0x180009f03  cmovz   eax, ecx
0x180009f06  add     rsp, 20h
0x180009f0a  pop     rbx
0x180009f0b  retn
```
