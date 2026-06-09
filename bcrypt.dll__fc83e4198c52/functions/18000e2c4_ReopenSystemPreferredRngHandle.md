# ReopenSystemPreferredRngHandle

- ea: `0x18000e2c4`
- end: `0x18000e362`
- name: `ReopenSystemPreferredRngHandle`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e270`

## callees

- `0x18000466c`
- `0x180005b00`
- `0x180007a7c`
- `0x18000e2c4`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000e349`
- `ntdll!RtlReleaseResource` at `0x18000e349`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e2d6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e2d6`

## string_xrefs

- `0x18000e31e`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall ReopenSystemPreferredRngHandle(BCRYPT_ALG_HANDLE *a1)
{
  int v2; // edx
  int v3; // ebx
  int v4; // r8d

  RtlAcquireResourceExclusive(g_pCachedRngRWLock, 1u);
  BCryptCloseAlgorithmProvider(*a1, 0);
  *a1 = 0;
  v3 = OpenSystemPreferredAlgorithmProvider(a1);
  if ( v3 >= 0 )
  {
    v3 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      v4,
      (unsigned int)"Status",
      v3,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
      127);
  }
  RtlReleaseResource(g_pCachedRngRWLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e2c4  push    rbx
0x18000e2c6  sub     rsp, 40h
0x18000e2ca  mov     rbx, rcx
0x18000e2cd  mov     dl, 1; Wait
0x18000e2cf  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000e2d6  call    cs:__imp_RtlAcquireResourceExclusive
0x18000e2dd  nop     dword ptr [rax+rax+00h]
0x18000e2e2  mov     rcx, [rbx]; hAlgorithm
0x18000e2e5  xor     edx, edx; dwFlags
0x18000e2e7  call    BCryptCloseAlgorithmProvider
0x18000e2ec  mov     rcx, rbx
0x18000e2ef  mov     qword ptr [rbx], 0
0x18000e2f6  call    OpenSystemPreferredAlgorithmProvider
0x18000e2fb  mov     ebx, eax
0x18000e2fd  test    eax, eax
0x18000e2ff  jns     short loc_18000E35E
0x18000e301  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e308  lea     rax, WPP_GLOBAL_Control
0x18000e30f  cmp     rcx, rax
0x18000e312  jz      short loc_18000E342
0x18000e314  test    byte ptr [rcx+1Ch], 1
0x18000e318  jz      short loc_18000E342
0x18000e31a  mov     rcx, [rcx+10h]
0x18000e31e  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e325  mov     [rsp+48h+var_18], 7Fh
0x18000e32d  lea     r9, aStatus; "Status"
0x18000e334  mov     [rsp+48h+var_20], rax
0x18000e339  mov     [rsp+48h+var_28], ebx
0x18000e33d  call    WPP_SF_sDsd
0x18000e342  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000e349  call    cs:__imp_RtlReleaseResource
0x18000e350  nop     dword ptr [rax+rax+00h]
0x18000e355  mov     eax, ebx
0x18000e357  add     rsp, 40h
0x18000e35b  pop     rbx
0x18000e35c  retn
0x18000e35e  xor     ebx, ebx
0x18000e360  jmp     short loc_18000E342
```
