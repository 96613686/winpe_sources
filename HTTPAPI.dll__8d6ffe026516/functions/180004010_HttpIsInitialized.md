# HttpIsInitialized

- ea: `0x180004010`
- end: `0x180004089`
- name: `HttpIsInitialized`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e20`
- `0x1800082d0`
- `0x180008550`
- `0x18000a280`
- `0x18000a3c0`

## callees

- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004023`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004076`

## pseudocode

```c
__int64 __fastcall HttpIsInitialized(int a1)
{
  unsigned int v2; // ecx
  unsigned int v3; // edi

  EnterCriticalSection(&g_InitCritSec);
  v2 = 0;
  if ( a1 )
  {
    v3 = 0;
    if ( (a1 & 0x17) != 0 )
    {
      LOBYTE(v3) = dword_180012770 != 0;
      if ( (a1 & 1) != 0 )
        v3 = (dword_180012768 != 0) & (unsigned __int8)v3;
      if ( (a1 & 2) != 0 )
      {
        LOBYTE(v2) = dword_18001276C != 0;
        v3 &= v2;
      }
    }
  }
  else
  {
    LOBYTE(v2) = dword_180012770 != 0;
    v3 = v2;
  }
  LeaveCriticalSection(&g_InitCritSec);
  return v3;
}

```

## disassembly

```asm
0x180004010  mov     [rsp+arg_0], rbx
0x180004015  push    rdi
0x180004016  sub     rsp, 20h
0x18000401a  mov     ebx, ecx
0x18000401c  lea     rcx, g_InitCritSec; lpCriticalSection
0x180004023  call    cs:__imp_EnterCriticalSection
0x180004029  xor     ecx, ecx
0x18000402b  test    ebx, ebx
0x18000402d  jnz     short loc_18000403C
0x18000402f  cmp     cs:dword_180012770, ecx
0x180004035  setnz   cl
0x180004038  mov     edi, ecx
0x18000403a  jmp     short loc_18000406F
0x18000403c  mov     edi, ecx
0x18000403e  test    bl, 17h
0x180004041  jz      short loc_18000406F
0x180004043  cmp     cs:dword_180012770, ecx
0x180004049  setnz   dil
0x18000404d  test    bl, 1
0x180004050  jz      short loc_18000405F
0x180004052  cmp     cs:dword_180012768, ecx
0x180004058  mov     eax, ecx
0x18000405a  setnz   al
0x18000405d  and     edi, eax
0x18000405f  test    bl, 2
0x180004062  jz      short loc_18000406F
0x180004064  cmp     cs:dword_18001276C, ecx
0x18000406a  setnz   cl
0x18000406d  and     edi, ecx
0x18000406f  lea     rcx, g_InitCritSec; lpCriticalSection
0x180004076  call    cs:__imp_LeaveCriticalSection
0x18000407c  mov     rbx, [rsp+28h+arg_0]
0x180004081  mov     eax, edi
0x180004083  add     rsp, 20h
0x180004087  pop     rdi
0x180004088  retn
```
