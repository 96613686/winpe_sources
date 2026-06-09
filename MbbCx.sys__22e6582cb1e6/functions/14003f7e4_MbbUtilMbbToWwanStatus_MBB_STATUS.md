# MbbUtilMbbToWwanStatus(_MBB_STATUS)

- ea: `0x14003f7e4`
- end: `0x14003f89d`
- name: `?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `76`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000fa30`
- `0x140026698`
- `0x140026e44`
- `0x1400275f0`
- `0x140027a54`
- `0x140027eb8`
- `0x1400280f8`
- `0x140028340`
- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x1400296d0`
- `0x1400298a0`
- `0x140029b20`
- `0x140029d80`
- `0x140029fe0`
- `0x14002a240`
- `0x14002ae5c`
- `0x14002b930`
- `0x14002be90`
- `0x14002c394`
- `0x14002c9e0`
- `0x14002cfa0`
- `0x14002d18c`
- `0x14002d460`
- `0x14002daa0`
- `0x14002deb8`
- `0x14002e470`
- `0x14002e780`
- `0x14002f8e0`
- `0x14002fb40`
- `0x140030100`
- `0x140030590`
- `0x140030830`
- `0x140030bc0`
- `0x140030f80`
- `0x140031550`
- `0x140031a40`
- `0x140031e20`
- `0x140032280`
- `0x1400324f0`
- `0x1400327d0`
- `0x140032c30`
- `0x140032ee0`
- `0x140033580`
- `0x140033970`
- `0x140033f50`
- `0x140034530`
- `0x140034b50`
- `0x140035080`

## callees

- `0x140001db8`
- `0x14003f7e4`

## pseudocode

```c
__int64 __fastcall MbbUtilMbbToWwanStatus(unsigned int a1)
{
  __int64 v2; // rax
  __int64 v3; // rax

  if ( a1 < 0x2B )
    return (unsigned int)dword_140057AA0[a1];
  v2 = a1 - 100;
  if ( (unsigned int)v2 <= 5 )
    return (unsigned int)dword_140057A60[v2];
  if ( a1 + 2025652223 <= 2 )
    return (unsigned int)dword_140057A88[a1 + 2025652223];
  v3 = a1 - 200;
  if ( (unsigned int)v3 <= 4 )
    return (unsigned int)dword_140057A48[v3];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      3,
      10,
      (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
      a1);
  return 3221487619LL;
}

```

## disassembly

```asm
0x14003f7e4  sub     rsp, 38h
0x14003f7e8  cmp     ecx, 2Bh ; '+'
0x14003f7eb  jnb     short loc_14003F802
0x14003f7ed  mov     eax, ecx
0x14003f7ef  lea     rcx, cs:140000000h
0x14003f7f6  mov     eax, ds:rva dword_140057AA0[rcx+rax*4]
0x14003f7fd  jmp     loc_14003F897
0x14003f802  lea     eax, [rcx-64h]
0x14003f805  cmp     eax, 5
0x14003f808  ja      short loc_14003F81A
0x14003f80a  lea     rcx, cs:140000000h
0x14003f811  mov     eax, ds:rva dword_140057A60[rcx+rax*4]
0x14003f818  jmp     short loc_14003F897
0x14003f81a  lea     eax, [rcx+78BCFFFFh]
0x14003f820  cmp     eax, 2
0x14003f823  ja      short loc_14003F83B
0x14003f825  lea     eax, [rcx+78BCFFFFh]
0x14003f82b  lea     rcx, cs:140000000h
0x14003f832  mov     eax, ds:rva dword_140057A88[rcx+rax*4]
0x14003f839  jmp     short loc_14003F897
0x14003f83b  lea     eax, [rcx-0C8h]
0x14003f841  cmp     eax, 4
0x14003f844  ja      short loc_14003F856
0x14003f846  lea     rcx, cs:140000000h
0x14003f84d  mov     eax, ds:rva dword_140057A48[rcx+rax*4]
0x14003f854  jmp     short loc_14003F897
0x14003f856  lea     rax, WPP_RECORDER_INITIALIZED
0x14003f85d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f864  jz      short loc_14003F892
0x14003f866  mov     [rsp+38h+var_10], ecx
0x14003f86a  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003f871  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f878  mov     r9d, 0Ah
0x14003f87e  mov     dl, 2
0x14003f880  mov     [rsp+38h+var_18], rax
0x14003f885  mov     rcx, [rcx+40h]
0x14003f889  lea     r8d, [r9-7]
0x14003f88d  call    WPP_RECORDER_SF_d
0x14003f892  mov     eax, 0C0040003h
0x14003f897  add     rsp, 38h
0x14003f89b  retn
```
