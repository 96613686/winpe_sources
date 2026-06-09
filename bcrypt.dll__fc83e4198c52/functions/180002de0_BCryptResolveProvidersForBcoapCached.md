# BCryptResolveProvidersForBcoapCached

- ea: `0x180002de0`
- end: `0x180003093`
- name: `BCryptResolveProvidersForBcoapCached`
- size: `691`
- prototype: `__int64 __fastcall(LPCWSTR pszFunction, LPCWSTR pszProvider, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x180002de0`
- `0x1800030a0`
- `0x180004200`
- `0x180007a7c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002fe2`
- `ntdll!RtlFreeHeap` at `0x180002fe2`

## string_xrefs

- `0x180002fa8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003018`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003066`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptResolveProvidersForBcoapCached(
        LPCWSTR pszFunction,
        LPCWSTR pszProvider,
        ULONG dwFlags,
        ULONG *pcbBuffer,
        PCRYPT_PROVIDER_REFS *ppBuffer,
        bool *a6)
{
  const WCHAR *v7; // rbp
  __int64 v8; // r10
  const WCHAR *v9; // rax
  int v10; // ecx
  int v11; // edx
  NTSTATUS v12; // esi
  bool v13; // di
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  char *v18; // rbx
  int v19; // r8d
  __int64 v20; // rax
  _WORD *v21; // rcx
  __int64 v22; // rdx
  _WORD *v23; // rax
  signed __int64 v24; // rax
  signed __int64 v25; // rcx

  v7 = pszFunction;
  if ( pszProvider || dwFlags != 2 )
  {
    v12 = BCryptResolveProviders(0, 0, pszFunction, pszProvider, 1u, dwFlags, pcbBuffer, ppBuffer);
    v13 = *ppBuffer != 0;
  }
  else
  {
    v8 = g_pResolveProviderCache;
    if ( g_pResolveProviderCache )
    {
      while ( 1 )
      {
        v9 = v7;
        do
        {
          v10 = *(const WCHAR *)((char *)v9 + v8 + 20 - (_QWORD)v7);
          v11 = *v9 - v10;
          if ( v11 )
            break;
          ++v9;
        }
        while ( v10 );
        if ( !v11 )
          break;
        v8 = *(_QWORD *)v8;
        if ( !v8 )
          goto LABEL_12;
      }
      *pcbBuffer = *(_DWORD *)(v8 + 16);
      v12 = 0;
      v13 = 0;
      *ppBuffer = *(PCRYPT_PROVIDER_REFS *)(v8 + 8);
    }
    else
    {
LABEL_12:
      v12 = BCryptResolveProviders(0, 0, v7, 0, 1u, 2u, pcbBuffer, ppBuffer);
      v13 = *ppBuffer != 0;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v16,
            (unsigned int)"Status",
            v12,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            252);
      }
      else
      {
        v18 = (char *)SafeAllocaAllocateFromHeap(64);
        if ( v18 )
        {
          v20 = 2147483646;
          v21 = v18 + 20;
          v22 = 20;
          do
          {
            if ( !v20 )
              break;
            v19 = *v7;
            if ( !(_WORD)v19 )
              break;
            *v21 = v19;
            ++v7;
            ++v21;
            --v20;
            --v22;
          }
          while ( v22 );
          v23 = v21 - 1;
          if ( v22 )
            v23 = v21;
          *v23 = 0;
          if ( v22 )
          {
            *((_DWORD *)v18 + 4) = *pcbBuffer;
            *((_QWORD *)v18 + 1) = *ppBuffer;
            v24 = g_pResolveProviderCache;
            do
            {
              *(_QWORD *)v18 = v24;
              v25 = v24;
              v24 = _InterlockedCompareExchange64(&g_pResolveProviderCache, (signed __int64)v18, v24);
            }
            while ( v25 != v24 );
            v13 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                0,
                v19,
                (unsigned int)"STATUS_BUFFER_TOO_SMALL",
                35,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                10);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v19,
            (unsigned int)"STATUS_NO_MEMORY",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            3);
        }
      }
    }
  }
  *a6 = v13;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180002de0  push    rbx
0x180002de2  push    rbp
0x180002de3  push    rsi
0x180002de4  push    rdi
0x180002de5  push    r14
0x180002de7  push    r15
0x180002de9  sub     rsp, 48h
0x180002ded  mov     r15, r9
0x180002df0  mov     rbp, rcx
0x180002df3  test    rdx, rdx
0x180002df6  jnz     short loc_180002E70
0x180002df8  cmp     r8d, 2
0x180002dfc  jnz     short loc_180002E70
0x180002dfe  mov     r10, cs:g_pResolveProviderCache
0x180002e05  test    r10, r10
0x180002e08  jz      loc_180002EBA
0x180002e0e  lea     r8, [r10+14h]
0x180002e12  mov     rax, rbp
0x180002e15  sub     r8, rbp
0x180002e18  nop     dword ptr [rax+rax+00000000h]
0x180002e20  movzx   edx, word ptr [rax]
0x180002e23  movzx   ecx, word ptr [rax+r8]
0x180002e28  sub     edx, ecx
0x180002e2a  jnz     short loc_180002E34
0x180002e2c  add     rax, 2
0x180002e30  test    ecx, ecx
0x180002e32  jnz     short loc_180002E20
0x180002e34  test    edx, edx
0x180002e36  jnz     short loc_180002EAE
0x180002e38  mov     eax, [r10+10h]
0x180002e3c  xor     ecx, ecx
0x180002e3e  mov     [r9], eax
0x180002e41  mov     esi, ecx
0x180002e43  mov     rax, [rsp+78h+arg_20]
0x180002e4b  xor     dil, dil
0x180002e4e  mov     rcx, [r10+8]
0x180002e52  mov     [rax], rcx
0x180002e55  mov     rax, [rsp+78h+arg_28]
0x180002e5d  mov     [rax], dil
0x180002e60  mov     eax, esi
0x180002e62  add     rsp, 48h
0x180002e66  pop     r15
0x180002e68  pop     r14
0x180002e6a  pop     rdi
0x180002e6b  pop     rsi
0x180002e6c  pop     rbp
0x180002e6d  pop     rbx
0x180002e6e  retn
0x180002e70  mov     rbx, [rsp+78h+arg_20]
0x180002e78  mov     r9, rdx; pszProvider
0x180002e7b  mov     [rsp+78h+ppBuffer], rbx; ppBuffer
0x180002e80  xor     edx, edx; dwInterface
0x180002e82  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x180002e87  xor     ecx, ecx; pszContext
0x180002e89  mov     [rsp+78h+dwFlags], r8d; dwFlags
0x180002e8e  xor     dil, dil
0x180002e91  mov     r8, rbp; pszFunction
0x180002e94  mov     [rsp+78h+dwMode], 1; dwMode
0x180002e9c  call    BCryptResolveProviders
0x180002ea1  cmp     qword ptr [rbx], 0
0x180002ea5  mov     esi, eax
0x180002ea7  jz      short loc_180002E55
0x180002ea9  mov     dil, 1
0x180002eac  jmp     short loc_180002E55
0x180002eae  mov     r10, [r10]
0x180002eb1  test    r10, r10
0x180002eb4  jnz     loc_180002E0E
0x180002eba  mov     r14, [rsp+78h+arg_20]
0x180002ec2  xor     r9d, r9d; pszProvider
0x180002ec5  mov     [rsp+78h+ppBuffer], r14; ppBuffer
0x180002eca  mov     r8, rbp; pszFunction
0x180002ecd  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x180002ed2  xor     edx, edx; dwInterface
0x180002ed4  mov     [rsp+78h+dwFlags], 2; dwFlags
0x180002edc  xor     ecx, ecx; pszContext
0x180002ede  mov     [rsp+78h+dwMode], 1; dwMode
0x180002ee6  call    BCryptResolveProviders
0x180002eeb  cmp     qword ptr [r14], 0
0x180002eef  mov     esi, eax
0x180002ef1  setnz   dil
0x180002ef5  test    eax, eax
0x180002ef7  js      loc_180002FF3
0x180002efd  mov     ecx, 40h ; '@'
0x180002f02  call    SafeAllocaAllocateFromHeap
0x180002f07  mov     rbx, rax
0x180002f0a  test    rax, rax
0x180002f0d  jz      loc_180003041
0x180002f13  mov     eax, 7FFFFFFEh
0x180002f18  lea     rcx, [rbx+14h]
0x180002f1c  mov     edx, 14h
0x180002f21  test    rax, rax
0x180002f24  jz      short loc_180002F46
0x180002f26  movzx   r8d, word ptr [rbp+0]
0x180002f2b  test    r8w, r8w
0x180002f2f  jz      short loc_180002F46
0x180002f31  mov     [rcx], r8w
0x180002f35  add     rbp, 2
0x180002f39  add     rcx, 2
0x180002f3d  dec     rax
0x180002f40  sub     rdx, 1
0x180002f44  jnz     short loc_180002F21
0x180002f46  test    rdx, rdx
0x180002f49  lea     rax, [rcx-2]
0x180002f4d  cmovnz  rax, rcx
0x180002f51  xor     ecx, ecx
0x180002f53  mov     [rax], cx
0x180002f56  test    rdx, rdx
0x180002f59  jz      short loc_180002F8B
0x180002f5b  mov     eax, [r15]
0x180002f5e  mov     [rbx+10h], eax
0x180002f61  mov     rax, [r14]
0x180002f64  mov     [rbx+8], rax
0x180002f68  mov     rax, cs:g_pResolveProviderCache
0x180002f6f  mov     [rbx], rax
0x180002f72  mov     rcx, rax
0x180002f75  lock cmpxchg cs:g_pResolveProviderCache, rbx
0x180002f7e  cmp     rcx, rax
0x180002f81  jnz     short loc_180002F6F
0x180002f83  xor     dil, dil
0x180002f86  jmp     loc_180002E55
0x180002f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f92  lea     rax, WPP_GLOBAL_Control
0x180002f99  cmp     rcx, rax
0x180002f9c  jz      short loc_180002FD0
0x180002f9e  test    byte ptr [rcx+1Ch], 1
0x180002fa2  jz      short loc_180002FD0
0x180002fa4  mov     rcx, [rcx+10h]
0x180002fa8  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002faf  mov     dword ptr [rsp+78h+pcbBuffer], 60Ah
0x180002fb7  lea     r9, aStatusBufferTo; "STATUS_BUFFER_TOO_SMALL"
0x180002fbe  mov     qword ptr [rsp+78h+dwFlags], rax
0x180002fc3  mov     [rsp+78h+dwMode], 0C0000023h
0x180002fcb  call    WPP_SF_sDsd
0x180002fd0  mov     rcx, gs:60h
0x180002fd9  mov     r8, rbx; P
0x180002fdc  xor     edx, edx; Flags
0x180002fde  mov     rcx, [rcx+30h]; HeapHandle
0x180002fe2  call    cs:__imp_RtlFreeHeap
0x180002fe9  nop     dword ptr [rax+rax+00h]
0x180002fee  jmp     loc_180002E55
0x180002ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ffa  lea     rax, WPP_GLOBAL_Control
0x180003001  cmp     rcx, rax
0x180003004  jz      loc_180002E55
0x18000300a  test    byte ptr [rcx+1Ch], 1
0x18000300e  jz      loc_180002E55
0x180003014  mov     rcx, [rcx+10h]
0x180003018  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000301f  mov     dword ptr [rsp+78h+pcbBuffer], 5FCh
0x180003027  lea     r9, aStatus; "Status"
0x18000302e  mov     qword ptr [rsp+78h+dwFlags], rax
0x180003033  mov     [rsp+78h+dwMode], esi
0x180003037  call    WPP_SF_sDsd
0x18000303c  jmp     loc_180002E55
0x180003041  mov     rcx, cs:WPP_GLOBAL_Control
0x180003048  lea     rax, WPP_GLOBAL_Control
0x18000304f  cmp     rcx, rax
0x180003052  jz      loc_180002E55
0x180003058  test    byte ptr [rcx+1Ch], 1
0x18000305c  jz      loc_180002E55
0x180003062  mov     rcx, [rcx+10h]
0x180003066  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000306d  mov     dword ptr [rsp+78h+pcbBuffer], 603h
0x180003075  lea     r9, aStatusNoMemory; "STATUS_NO_MEMORY"
0x18000307c  mov     qword ptr [rsp+78h+dwFlags], rax
0x180003081  mov     [rsp+78h+dwMode], 0C0000017h
0x180003089  call    WPP_SF_sDsd
0x18000308e  jmp     loc_180002E55
```
