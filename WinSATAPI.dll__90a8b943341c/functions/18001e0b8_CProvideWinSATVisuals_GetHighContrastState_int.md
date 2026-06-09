# CProvideWinSATVisuals::GetHighContrastState(int &)

- ea: `0x18001e0b8`
- end: `0x18001e10a`
- name: `?GetHighContrastState@CProvideWinSATVisuals@@CAJAEAH@Z`
- size: `82`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e4a8`

## callees

- `0x18001e0b8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18001e0dd`
- `USER32!SystemParametersInfoW` at `0x18001e0dd`

## pseudocode

```c
__int64 __fastcall CProvideWinSATVisuals::GetHighContrastState(int *a1)
{
  BOOL v2; // eax
  int v3; // edx
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  v2 = SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0);
  v3 = 0;
  if ( v2 )
    v3 = BYTE4(pvParam) & 1;
  *a1 = v3;
  return !v2 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001e0b8  push    rbx
0x18001e0ba  sub     rsp, 30h
0x18001e0be  mov     edx, 10h; uiParam
0x18001e0c3  lea     r8, [rsp+38h+pvParam]; pvParam
0x18001e0c8  xorps   xmm0, xmm0
0x18001e0cb  mov     rbx, rcx
0x18001e0ce  movups  [rsp+38h+pvParam], xmm0
0x18001e0d3  xor     r9d, r9d; fWinIni
0x18001e0d6  mov     dword ptr [rsp+38h+pvParam], edx
0x18001e0da  lea     ecx, [rdx+32h]; uiAction
0x18001e0dd  call    cs:__imp_SystemParametersInfoW
0x18001e0e4  nop     dword ptr [rax+rax+00h]
0x18001e0e9  xor     edx, edx
0x18001e0eb  test    eax, eax
0x18001e0ed  jz      short loc_18001E0F6
0x18001e0ef  mov     edx, dword ptr [rsp+38h+pvParam+4]
0x18001e0f3  and     edx, 1
0x18001e0f6  neg     eax
0x18001e0f8  mov     [rbx], edx
0x18001e0fa  sbb     eax, eax
0x18001e0fc  not     eax
0x18001e0fe  and     eax, 80004005h
0x18001e103  add     rsp, 30h
0x18001e107  pop     rbx
0x18001e108  retn
```
