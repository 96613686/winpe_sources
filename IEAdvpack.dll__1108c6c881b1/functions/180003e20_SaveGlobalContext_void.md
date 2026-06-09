# SaveGlobalContext(void)

- ea: `0x180003e20`
- end: `0x180003f82`
- name: `?SaveGlobalContext@@YAHXZ`
- size: `354`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180002450`
- `0x180002ad4`
- `0x180005ea0`
- `0x18000b8f0`
- `0x18000bdb0`
- `0x18000c0c0`
- `0x18000ef90`
- `0x18000f7b0`
- `0x180010710`

## callees

- `0x180003e20`
- `0x180003f88`
- `0x18001b94e`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180003f65`
- `KERNEL32!LocalAlloc` at `0x180003f65`
- `KERNEL32!EnterCriticalSection` at `0x180003e2d`
- `KERNEL32!EnterCriticalSection` at `0x180003e2d`
- `KERNEL32!LeaveCriticalSection` at `0x180003f4d`
- `KERNEL32!LeaveCriticalSection` at `0x180003f4d`
- `KERNEL32!LocalReAlloc` at `0x180003e7b`
- `KERNEL32!LocalReAlloc` at `0x180003e7b`

## pseudocode

```c
__int64 SaveGlobalContext(void)
{
  unsigned __int64 v0; // rdx
  unsigned __int64 v1; // rcx
  void *v2; // r9
  char *v3; // rax
  char *v4; // rdx
  unsigned int v5; // r9d
  __int64 v6; // rcx
  char *v7; // rax
  _OWORD *v8; // rdx
  __int128 v9; // xmm1
  unsigned int v10; // ebx
  SIZE_T uBytes; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(&CSPctxSave);
  if ( pctxSave )
  {
    v1 = cctxSaved + 1LL;
    if ( v1 >= cctxSaved )
    {
      uBytes = cctxSaved + 1LL;
      if ( (int)ULongLongMult(v1, v0, &uBytes) >= 0 )
      {
        v3 = (char *)LocalReAlloc(v2, uBytes, 0x42u);
        v4 = v3;
        if ( v3 )
        {
          pctxSave = v3;
          goto LABEL_6;
        }
      }
    }
LABEL_11:
    v10 = 0;
    goto LABEL_9;
  }
  pctxSave = LocalAlloc(0x40u, 0x450u);
  v4 = (char *)pctxSave;
  if ( !pctxSave )
    goto LABEL_11;
LABEL_6:
  v5 = cctxSaved;
  v6 = 8;
  v7 = &v4[1104 * cctxSaved];
  v8 = &ctx;
  do
  {
    *(_OWORD *)v7 = *v8;
    *((_OWORD *)v7 + 1) = v8[1];
    *((_OWORD *)v7 + 2) = v8[2];
    *((_OWORD *)v7 + 3) = v8[3];
    *((_OWORD *)v7 + 4) = v8[4];
    *((_OWORD *)v7 + 5) = v8[5];
    *((_OWORD *)v7 + 6) = v8[6];
    v9 = v8[7];
    v8 += 8;
    *((_OWORD *)v7 + 7) = v9;
    v7 += 128;
    --v6;
  }
  while ( v6 );
  v10 = 1;
  *(_OWORD *)v7 = *v8;
  cctxSaved = v5 + 1;
  *((_OWORD *)v7 + 1) = v8[1];
  *((_OWORD *)v7 + 2) = v8[2];
  *((_OWORD *)v7 + 3) = v8[3];
  *((_OWORD *)v7 + 4) = v8[4];
  memset_0(&ctx, 0, 0x450u);
LABEL_9:
  LeaveCriticalSection(&CSPctxSave);
  return v10;
}

```

## disassembly

```asm
0x180003e20  push    rbx
0x180003e22  sub     rsp, 20h
0x180003e26  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003e2d  call    cs:__imp_EnterCriticalSection
0x180003e33  mov     r9, cs:?pctxSave@@3PEAUADVCONTEXTW@@EA; ADVCONTEXTW * pctxSave
0x180003e3a  test    r9, r9
0x180003e3d  jz      loc_180003F5B
0x180003e43  mov     eax, cs:?cctxSaved@@3KA; ulong cctxSaved
0x180003e49  lea     rcx, [rax+1]; unsigned __int64
0x180003e4d  cmp     rcx, rax
0x180003e50  jb      loc_180003F7E
0x180003e56  lea     r8, [rsp+28h+uBytes]; unsigned __int64 *
0x180003e5b  mov     [rsp+28h+uBytes], rcx
0x180003e60  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003e65  test    eax, eax
0x180003e67  js      loc_180003F7E
0x180003e6d  mov     rdx, [rsp+28h+uBytes]; uBytes
0x180003e72  mov     r8d, 42h ; 'B'; uFlags
0x180003e78  mov     rcx, r9; hMem
0x180003e7b  call    cs:__imp_LocalReAlloc
0x180003e81  mov     rdx, rax
0x180003e84  test    rax, rax
0x180003e87  jz      loc_180003F7E
0x180003e8d  mov     cs:?pctxSave@@3PEAUADVCONTEXTW@@EA, rax; ADVCONTEXTW * pctxSave
0x180003e94  mov     r9d, cs:?cctxSaved@@3KA; ulong cctxSaved
0x180003e9b  mov     ecx, 8
0x180003ea0  imul    rax, r9, 450h
0x180003ea7  lea     r8d, [rcx+78h]
0x180003eab  add     rax, rdx
0x180003eae  lea     rdx, ?ctx@@3UADVCONTEXTW@@A; ADVCONTEXTW ctx
0x180003eb5  movups  xmm0, xmmword ptr [rdx]
0x180003eb8  movups  xmmword ptr [rax], xmm0
0x180003ebb  movups  xmm1, xmmword ptr [rdx+10h]
0x180003ebf  movups  xmmword ptr [rax+10h], xmm1
0x180003ec3  movups  xmm0, xmmword ptr [rdx+20h]
0x180003ec7  movups  xmmword ptr [rax+20h], xmm0
0x180003ecb  movups  xmm1, xmmword ptr [rdx+30h]
0x180003ecf  movups  xmmword ptr [rax+30h], xmm1
0x180003ed3  movups  xmm0, xmmword ptr [rdx+40h]
0x180003ed7  movups  xmmword ptr [rax+40h], xmm0
0x180003edb  movups  xmm1, xmmword ptr [rdx+50h]
0x180003edf  movups  xmmword ptr [rax+50h], xmm1
0x180003ee3  movups  xmm0, xmmword ptr [rdx+60h]
0x180003ee7  movups  xmmword ptr [rax+60h], xmm0
0x180003eeb  movups  xmm1, xmmword ptr [rdx+70h]
0x180003eef  add     rdx, r8
0x180003ef2  movups  xmmword ptr [rax+70h], xmm1
0x180003ef6  add     rax, r8
0x180003ef9  sub     rcx, 1
0x180003efd  jnz     short loc_180003EB5
0x180003eff  movups  xmm0, xmmword ptr [rdx]
0x180003f02  lea     ebx, [rcx+1]
0x180003f05  mov     r8d, 450h; Size
0x180003f0b  add     r9d, ebx
0x180003f0e  lea     rcx, ?ctx@@3UADVCONTEXTW@@A; void *
0x180003f15  movups  xmmword ptr [rax], xmm0
0x180003f18  mov     cs:?cctxSaved@@3KA, r9d; ulong cctxSaved
0x180003f1f  movups  xmm1, xmmword ptr [rdx+10h]
0x180003f23  movups  xmmword ptr [rax+10h], xmm1
0x180003f27  movups  xmm0, xmmword ptr [rdx+20h]
0x180003f2b  movups  xmmword ptr [rax+20h], xmm0
0x180003f2f  movups  xmm1, xmmword ptr [rdx+30h]
0x180003f33  movups  xmmword ptr [rax+30h], xmm1
0x180003f37  movups  xmm0, xmmword ptr [rdx+40h]
0x180003f3b  xor     edx, edx; Val
0x180003f3d  movups  xmmword ptr [rax+40h], xmm0
0x180003f41  call    memset_0
0x180003f46  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003f4d  call    cs:__imp_LeaveCriticalSection
0x180003f53  mov     eax, ebx
0x180003f55  add     rsp, 20h
0x180003f59  pop     rbx
0x180003f5a  retn
0x180003f5b  mov     edx, 450h; uBytes
0x180003f60  mov     ecx, 40h ; '@'; uFlags
0x180003f65  call    cs:__imp_LocalAlloc
0x180003f6b  mov     cs:?pctxSave@@3PEAUADVCONTEXTW@@EA, rax; ADVCONTEXTW * pctxSave
0x180003f72  mov     rdx, rax
0x180003f75  test    rax, rax
0x180003f78  jnz     loc_180003E94
0x180003f7e  xor     ebx, ebx
0x180003f80  jmp     short loc_180003F46
```
