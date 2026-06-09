# RPC_STATUSFromHRESULT(long)

- ea: `0x180005c9c`
- end: `0x180005cf5`
- name: `?RPC_STATUSFromHRESULT@@YAJJ@Z`
- size: `89`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010b0`
- `0x180002798`

## callees

- `0x180005c9c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180005cd2`
- `ntdll!RtlNtStatusToDosError` at `0x180005cd2`

## pseudocode

```c
__int64 __fastcall RPC_STATUSFromHRESULT(int a1)
{
  ULONG v1; // ebx
  bool v2; // zf
  ULONG v3; // eax

  v1 = a1;
  if ( a1 >= 0 )
    return 0;
  if ( (a1 & 0xFFFF0000) == 0x80010000 || (a1 & 0xFFFF0000) == 0x80070000 )
  {
    v1 = (unsigned __int16)a1;
    v2 = (unsigned __int16)a1 == 0;
  }
  else
  {
    if ( (a1 & 0x10000000) == 0 )
      return v1;
    v3 = RtlNtStatusToDosError(a1 & 0xEFFFFFFF);
    if ( v3 == 317 )
      return v1;
    v1 = v3;
    v2 = v3 == 0;
  }
  if ( v2 )
    return 87;
  return v1;
}

```

## disassembly

```asm
0x180005c9c  push    rbx
0x180005c9e  sub     rsp, 20h
0x180005ca2  mov     ebx, ecx
0x180005ca4  test    ecx, ecx
0x180005ca6  js      short loc_180005CAC
0x180005ca8  xor     ebx, ebx
0x180005caa  jmp     short loc_180005CED
0x180005cac  mov     eax, ecx
0x180005cae  and     eax, 0FFFF0000h
0x180005cb3  cmp     eax, 80010000h
0x180005cb8  jnz     short loc_180005CC1
0x180005cba  movzx   ebx, cx
0x180005cbd  test    ebx, ebx
0x180005cbf  jmp     short loc_180005CE5
0x180005cc1  cmp     eax, 80070000h
0x180005cc6  jz      short loc_180005CBA
0x180005cc8  bt      ecx, 1Ch
0x180005ccc  jnb     short loc_180005CED
0x180005cce  btr     ecx, 1Ch; Status
0x180005cd2  call    cs:__imp_RtlNtStatusToDosError
0x180005cd8  mov     ecx, eax
0x180005cda  cmp     eax, 13Dh
0x180005cdf  jz      short loc_180005CED
0x180005ce1  mov     ebx, eax
0x180005ce3  test    eax, eax
0x180005ce5  mov     eax, 57h ; 'W'
0x180005cea  cmovz   ebx, eax
0x180005ced  mov     eax, ebx
0x180005cef  add     rsp, 20h
0x180005cf3  pop     rbx
0x180005cf4  retn
```
