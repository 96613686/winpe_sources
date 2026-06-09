# RestoreGlobalContext(void)

- ea: `0x180003ce0`
- end: `0x180003e19`
- name: `?RestoreGlobalContext@@YAHXZ`
- size: `313`
- prototype: `__int64(void)`
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002450`
- `0x180002ad4`
- `0x180005ea0`
- `0x18000b8f0`
- `0x18000bdb0`
- `0x18000c0c0`
- `0x18000ef90`
- `0x18000f630`
- `0x18000f7b0`
- `0x180010710`

## callees

- `0x180003ce0`
- `0x180003f88`
- `0x180004700`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003df2`
- `KERNEL32!LocalFree` at `0x180003df2`
- `KERNEL32!EnterCriticalSection` at `0x180003ced`
- `KERNEL32!EnterCriticalSection` at `0x180003ced`
- `KERNEL32!LeaveCriticalSection` at `0x180003e0b`
- `KERNEL32!LeaveCriticalSection` at `0x180003e0b`
- `KERNEL32!LocalReAlloc` at `0x180003ddb`
- `KERNEL32!LocalReAlloc` at `0x180003ddb`

## pseudocode

```c
__int64 RestoreGlobalContext(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  HLOCAL v2; // r9
  unsigned __int64 v3; // rdx
  __int64 v4; // r8
  _OWORD *v5; // rax
  _OWORD *v6; // rcx
  __int128 v7; // xmm1
  void *v8; // r9
  HLOCAL v9; // rax
  SIZE_T uBytes; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(&CSPctxSave);
  v0 = cctxSaved;
  v1 = 0;
  if ( cctxSaved )
  {
    if ( hLibModule )
    {
      CommonInstallCleanup();
      v0 = cctxSaved;
    }
    v2 = pctxSave;
    v3 = v0 - 1;
    v4 = 8;
    cctxSaved = v0 - 1;
    v5 = &ctx;
    v6 = (char *)pctxSave + 1104 * v3;
    do
    {
      *v5 = *v6;
      v5[1] = v6[1];
      v5[2] = v6[2];
      v5[3] = v6[3];
      v5[4] = v6[4];
      v5[5] = v6[5];
      v5[6] = v6[6];
      v7 = v6[7];
      v6 += 8;
      v5[7] = v7;
      v5 += 8;
      --v4;
    }
    while ( v4 );
    *v5 = *v6;
    v5[1] = v6[1];
    v5[2] = v6[2];
    v5[3] = v6[3];
    v5[4] = v6[4];
    if ( !(_DWORD)v3 )
    {
      LocalFree(v2);
      pctxSave = 0;
LABEL_11:
      v1 = 1;
      goto LABEL_12;
    }
    uBytes = 0;
    if ( (int)ULongLongMult(v3, v3, &uBytes) >= 0 )
    {
      v9 = LocalReAlloc(v8, uBytes, 0x42u);
      if ( v9 )
        pctxSave = v9;
      goto LABEL_11;
    }
  }
LABEL_12:
  LeaveCriticalSection(&CSPctxSave);
  return v1;
}

```

## disassembly

```asm
0x180003ce0  push    rbx
0x180003ce2  sub     rsp, 20h
0x180003ce6  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003ced  call    cs:__imp_EnterCriticalSection
0x180003cf3  mov     eax, cs:?cctxSaved@@3KA; ulong cctxSaved
0x180003cf9  xor     ebx, ebx
0x180003cfb  test    eax, eax
0x180003cfd  jz      loc_180003E04
0x180003d03  cmp     cs:hLibModule, rbx
0x180003d0a  jz      short loc_180003D17
0x180003d0c  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x180003d11  mov     eax, cs:?cctxSaved@@3KA; ulong cctxSaved
0x180003d17  mov     r9, cs:?pctxSave@@3PEAUADVCONTEXTW@@EA; ADVCONTEXTW * pctxSave
0x180003d1e  dec     eax
0x180003d20  mov     edx, eax; unsigned __int64
0x180003d22  mov     r8d, 8
0x180003d28  imul    rcx, rdx, 450h
0x180003d2f  mov     cs:?cctxSaved@@3KA, eax; ulong cctxSaved
0x180003d35  lea     rax, ?ctx@@3UADVCONTEXTW@@A; ADVCONTEXTW ctx
0x180003d3c  add     rcx, r9
0x180003d3f  lea     r10d, [r8+78h]
0x180003d43  movups  xmm0, xmmword ptr [rcx]
0x180003d46  movups  xmmword ptr [rax], xmm0
0x180003d49  movups  xmm1, xmmword ptr [rcx+10h]
0x180003d4d  movups  xmmword ptr [rax+10h], xmm1
0x180003d51  movups  xmm0, xmmword ptr [rcx+20h]
0x180003d55  movups  xmmword ptr [rax+20h], xmm0
0x180003d59  movups  xmm1, xmmword ptr [rcx+30h]
0x180003d5d  movups  xmmword ptr [rax+30h], xmm1
0x180003d61  movups  xmm0, xmmword ptr [rcx+40h]
0x180003d65  movups  xmmword ptr [rax+40h], xmm0
0x180003d69  movups  xmm1, xmmword ptr [rcx+50h]
0x180003d6d  movups  xmmword ptr [rax+50h], xmm1
0x180003d71  movups  xmm0, xmmword ptr [rcx+60h]
0x180003d75  movups  xmmword ptr [rax+60h], xmm0
0x180003d79  movups  xmm1, xmmword ptr [rcx+70h]
0x180003d7d  add     rcx, r10
0x180003d80  movups  xmmword ptr [rax+70h], xmm1
0x180003d84  add     rax, r10
0x180003d87  sub     r8, 1
0x180003d8b  jnz     short loc_180003D43
0x180003d8d  movups  xmm0, xmmword ptr [rcx]
0x180003d90  movups  xmmword ptr [rax], xmm0
0x180003d93  movups  xmm1, xmmword ptr [rcx+10h]
0x180003d97  movups  xmmword ptr [rax+10h], xmm1
0x180003d9b  movups  xmm0, xmmword ptr [rcx+20h]
0x180003d9f  movups  xmmword ptr [rax+20h], xmm0
0x180003da3  movups  xmm1, xmmword ptr [rcx+30h]
0x180003da7  movups  xmmword ptr [rax+30h], xmm1
0x180003dab  movups  xmm0, xmmword ptr [rcx+40h]
0x180003daf  movups  xmmword ptr [rax+40h], xmm0
0x180003db3  test    edx, edx
0x180003db5  jz      short loc_180003DEF
0x180003db7  lea     r8, [rsp+28h+uBytes]; unsigned __int64 *
0x180003dbc  mov     [rsp+28h+uBytes], rbx
0x180003dc1  mov     rcx, rdx; unsigned __int64
0x180003dc4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003dc9  test    eax, eax
0x180003dcb  js      short loc_180003E04
0x180003dcd  mov     rdx, [rsp+28h+uBytes]; uBytes
0x180003dd2  mov     r8d, 42h ; 'B'; uFlags
0x180003dd8  mov     rcx, r9; hMem
0x180003ddb  call    cs:__imp_LocalReAlloc
0x180003de1  test    rax, rax
0x180003de4  jz      short loc_180003DFF
0x180003de6  mov     cs:?pctxSave@@3PEAUADVCONTEXTW@@EA, rax; ADVCONTEXTW * pctxSave
0x180003ded  jmp     short loc_180003DFF
0x180003def  mov     rcx, r9; hMem
0x180003df2  call    cs:__imp_LocalFree
0x180003df8  mov     cs:?pctxSave@@3PEAUADVCONTEXTW@@EA, rbx; ADVCONTEXTW * pctxSave
0x180003dff  mov     ebx, 1
0x180003e04  lea     rcx, ?CSPctxSave@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003e0b  call    cs:__imp_LeaveCriticalSection
0x180003e11  mov     eax, ebx
0x180003e13  add     rsp, 20h
0x180003e17  pop     rbx
0x180003e18  retn
```
