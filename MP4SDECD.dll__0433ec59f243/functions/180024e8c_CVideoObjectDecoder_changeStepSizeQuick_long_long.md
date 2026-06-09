# CVideoObjectDecoder::changeStepSizeQuick(long,long)

- ea: `0x180024e8c`
- end: `0x180024ed9`
- name: `?changeStepSizeQuick@CVideoObjectDecoder@@AEAAXJJ@Z`
- size: `77`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003838`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180004430`
- `0x180024e8c`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::changeStepSizeQuick(CVideoObjectDecoder *this, int a2, int a3)
{
  int v3; // eax
  int v4; // edx
  __int64 v5; // r9
  int v6; // r8d

  if ( *((_DWORD *)this + 2) )
  {
    if ( a2 < 1 )
    {
      a2 = 1;
    }
    else
    {
      v3 = 1 << *((_DWORD *)this + 14);
      if ( a2 >= v3 )
        a2 = v3 - 1;
    }
  }
  if ( a3 )
    *((_DWORD *)this + 349) = a2;
  CVideoObjectDecoder::updateDCVLCMode(this);
  if ( !v6 )
    *(_DWORD *)(v5 + 1396) = v4;
}

```

## disassembly

```asm
0x180024e8c  sub     rsp, 28h
0x180024e90  cmp     dword ptr [rcx+8], 0
0x180024e94  mov     r9, rcx
0x180024e97  jz      short loc_180024EAB
0x180024e99  mov     eax, 1
0x180024e9e  cmp     edx, eax
0x180024ea0  jl      short loc_180024ED0
0x180024ea2  mov     ecx, [rcx+38h]
0x180024ea5  shl     eax, cl
0x180024ea7  cmp     edx, eax
0x180024ea9  jge     short loc_180024ED4
0x180024eab  test    r8d, r8d
0x180024eae  jz      short loc_180024EB7
0x180024eb0  mov     [r9+574h], edx
0x180024eb7  mov     rcx, r9; this
0x180024eba  call    ?updateDCVLCMode@CVideoObjectDecoder@@AEAAXXZ; CVideoObjectDecoder::updateDCVLCMode(void)
0x180024ebf  test    r8d, r8d
0x180024ec2  jnz     short loc_180024ECB
0x180024ec4  mov     [r9+574h], edx
0x180024ecb  add     rsp, 28h
0x180024ecf  retn
0x180024ed0  mov     edx, eax
0x180024ed2  jmp     short loc_180024EAB
0x180024ed4  lea     edx, [rax-1]
0x180024ed7  jmp     short loc_180024EAB
```
