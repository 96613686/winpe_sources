# CProviderRegistrationCache::ConstructNewSelectionCriteria(ulong,_CERT_SELECT_CRITERIA const *,ulong,_CERT_SELECT_CRITERIA const *,ulong *,_CERT_SELECT_CRITERIA const * *)

- ea: `0x1800143c0`
- end: `0x18001445e`
- name: `?ConstructNewSelectionCriteria@CProviderRegistrationCache@@QEAAKKPEBU_CERT_SELECT_CRITERIA@@K0PEAKPEAPEBU2@@Z`
- size: `158`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, unsigned int, const struct _CERT_SELECT_CRITERIA *, __int64, const struct _CERT_SELECT_CRITERIA *, unsigned int *, const struct _CERT_SELECT_CRITERIA **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000caa0`
- `0x1800148fc`

## callees

- `0x1800143c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014408`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014408`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ConstructNewSelectionCriteria(
        CProviderRegistrationCache *this,
        unsigned int a2,
        const struct _CERT_SELECT_CRITERIA *a3,
        __int64 a4,
        const struct _CERT_SELECT_CRITERIA *a5,
        unsigned int *a6,
        const struct _CERT_SELECT_CRITERIA **a7)
{
  unsigned int v7; // edi
  unsigned __int64 v10; // rax
  const struct _CERT_SELECT_CRITERIA *v11; // r8
  unsigned int v12; // edx
  __int64 i; // rcx
  __int64 v14; // rax

  v7 = a2 + 1;
  *a6 = 0;
  *a7 = 0;
  if ( a2 + 1 >= a2
    && (v10 = 16LL * v7, v10 <= 0xFFFFFFFF)
    && (v11 = (const struct _CERT_SELECT_CRITERIA *)LocalAlloc(0x40u, (unsigned int)v10)) != 0 )
  {
    v12 = 0;
    for ( i = 0; (unsigned int)i < a2; v11[v14] = a3[v14] )
    {
      v14 = (unsigned int)i;
      i = (unsigned int)(i + 1);
    }
    v11[i] = *a5;
    *a6 = v7;
    *a7 = v11;
  }
  else
  {
    return 14;
  }
  return v12;
}

```

## disassembly

```asm
0x1800143c0  push    rbx
0x1800143c2  push    rbp
0x1800143c3  push    rsi
0x1800143c4  push    rdi
0x1800143c5  push    r14
0x1800143c7  sub     rsp, 20h
0x1800143cb  mov     rsi, [rsp+48h+arg_28]
0x1800143d0  lea     edi, [rdx+1]
0x1800143d3  mov     r14, [rsp+48h+arg_30]
0x1800143db  mov     rbp, r8
0x1800143de  mov     ebx, edx
0x1800143e0  mov     dword ptr [rsi], 0
0x1800143e6  mov     qword ptr [r14], 0
0x1800143ed  cmp     edi, edx
0x1800143ef  jb      short loc_18001444C
0x1800143f1  mov     eax, edi
0x1800143f3  mov     ecx, 0FFFFFFFFh
0x1800143f8  shl     rax, 4
0x1800143fc  cmp     rax, rcx
0x1800143ff  ja      short loc_18001444C
0x180014401  mov     edx, eax; uBytes
0x180014403  mov     ecx, 40h ; '@'; uFlags
0x180014408  call    cs:__imp_LocalAlloc
0x18001440e  mov     r8, rax
0x180014411  test    rax, rax
0x180014414  jz      short loc_18001444C
0x180014416  xor     edx, edx
0x180014418  xor     ecx, ecx
0x18001441a  test    ebx, ebx
0x18001441c  jz      short loc_180014434
0x18001441e  mov     eax, ecx
0x180014420  inc     ecx
0x180014422  add     rax, rax
0x180014425  movups  xmm0, xmmword ptr [rbp+rax*8+0]
0x18001442a  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180014430  cmp     ecx, ebx
0x180014432  jb      short loc_18001441E
0x180014434  mov     rax, [rsp+48h+arg_20]
0x180014439  add     rcx, rcx
0x18001443c  movups  xmm0, xmmword ptr [rax]
0x18001443f  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x180014445  mov     [rsi], edi
0x180014447  mov     [r14], r8
0x18001444a  jmp     short loc_180014451
0x18001444c  mov     edx, 0Eh
0x180014451  mov     eax, edx
0x180014453  add     rsp, 20h
0x180014457  pop     r14
0x180014459  pop     rdi
0x18001445a  pop     rsi
0x18001445b  pop     rbp
0x18001445c  pop     rbx
0x18001445d  retn
```
