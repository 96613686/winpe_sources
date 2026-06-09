# CTemplate::GetCLSIDFromBrProgIDText(CByteRange &,_GUID *)

- ea: `0x18005bfbc`
- end: `0x18005c0db`
- name: `?GetCLSIDFromBrProgIDText@CTemplate@@AEAAXAEAVCByteRange@@PEAU_GUID@@@Z`
- size: `287`
- prototype: `void __fastcall(CTemplate *__hidden this, struct CByteRange *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005eec8`

## callees

- `0x18005bfbc`
- `0x18005ffac`
- `0x1800608c8`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x18005c072`
- `ole32!CLSIDFromProgID` at `0x18005c072`
- `KERNEL32!HeapFree` at `0x18005c048`
- `KERNEL32!HeapFree` at `0x18005c08d`
- `KERNEL32!HeapFree` at `0x18005c0cc`
- `KERNEL32!HeapFree` at `0x18005c048`
- `KERNEL32!HeapFree` at `0x18005c08d`
- `KERNEL32!HeapFree` at `0x18005c0cc`
- `KERNEL32!HeapAlloc` at `0x18005bff4`
- `KERNEL32!HeapAlloc` at `0x18005bff4`
- `KERNEL32!RaiseException` at `0x18005c00f`
- `KERNEL32!RaiseException` at `0x18005c05d`
- `KERNEL32!RaiseException` at `0x18005c00f`
- `KERNEL32!RaiseException` at `0x18005c05d`
- `KERNEL32!MultiByteToWideChar` at `0x18005c02d`
- `KERNEL32!MultiByteToWideChar` at `0x18005c02d`

## pseudocode

```c
void __fastcall CTemplate::GetCLSIDFromBrProgIDText(CTemplate *this, struct CByteRange *a2, struct _GUID *a3)
{
  SIZE_T v6; // rax
  void *lpWideCharStr; // rbx
  CTypelibCache *v8; // rcx

  v6 = 2LL * (unsigned int)(*((_DWORD *)a2 + 2) + 1);
  if ( !is_mul_ok((unsigned int)(*((_DWORD *)a2 + 2) + 1), 2u) )
    v6 = -1;
  lpWideCharStr = HeapAlloc(g_hDenaliHeap, 0, v6);
  if ( !lpWideCharStr )
    RaiseException(0x8007000E, 0, 0, 0);
  if ( !MultiByteToWideChar(0, 8u, *(LPCCH *)a2, *((_DWORD *)a2 + 2), (LPWSTR)lpWideCharStr, *((_DWORD *)a2 + 2)) )
  {
    if ( lpWideCharStr )
    {
      HeapFree(g_hDenaliHeap, 0, lpWideCharStr);
      lpWideCharStr = 0;
    }
    RaiseException(0x80004005, 0, 0, 0);
  }
  *((_WORD *)lpWideCharStr + *((unsigned int *)a2 + 2)) = 0;
  if ( CLSIDFromProgID((LPCOLESTR)lpWideCharStr, a3) < 0 )
  {
    if ( lpWideCharStr )
    {
      HeapFree(g_hDenaliHeap, 0, lpWideCharStr);
      lpWideCharStr = 0;
    }
    CTemplate::ThrowErrorSingleInsert(
      this,
      *(unsigned __int8 **)a2,
      0x7E4u,
      *(unsigned __int8 **)a2,
      *((_DWORD *)a2 + 2));
  }
  CTypelibCache::RememberProgidToCLSIDMapping(v8, (unsigned __int16 *)lpWideCharStr, a3);
  if ( lpWideCharStr )
    HeapFree(g_hDenaliHeap, 0, lpWideCharStr);
}

```

## disassembly

```asm
0x18005bfbc  push    rbx
0x18005bfbe  push    rbp
0x18005bfbf  push    rsi
0x18005bfc0  push    rdi
0x18005bfc1  sub     rsp, 38h
0x18005bfc5  mov     r9d, [rdx+8]
0x18005bfc9  mov     rdi, rdx
0x18005bfcc  mov     rbp, rcx
0x18005bfcf  inc     r9d
0x18005bfd2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bfd9  mov     rsi, r8
0x18005bfdc  mov     eax, 2
0x18005bfe1  mul     r9
0x18005bfe4  cmovb   rax, rcx
0x18005bfe8  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005bfef  mov     r8, rax; dwBytes
0x18005bff2  xor     edx, edx; dwFlags
0x18005bff4  call    cs:__imp_HeapAlloc
0x18005bffa  mov     rbx, rax
0x18005bffd  test    rax, rax
0x18005c000  jnz     short loc_18005C015
0x18005c002  xor     r9d, r9d; lpArguments
0x18005c005  xor     r8d, r8d; nNumberOfArguments
0x18005c008  xor     edx, edx; dwExceptionFlags
0x18005c00a  mov     ecx, 8007000Eh; dwExceptionCode
0x18005c00f  call    cs:__imp_RaiseException
0x18005c015  mov     r9d, [rdi+8]; cbMultiByte
0x18005c019  mov     edx, 8; dwFlags
0x18005c01e  mov     r8, [rdi]; lpMultiByteStr
0x18005c021  xor     ecx, ecx; CodePage
0x18005c023  mov     [rsp+58h+cchWideChar], r9d; cchWideChar
0x18005c028  mov     [rsp+58h+lpWideCharStr], rbx; lpWideCharStr
0x18005c02d  call    cs:__imp_MultiByteToWideChar
0x18005c033  test    eax, eax
0x18005c035  jnz     short loc_18005C063
0x18005c037  test    rbx, rbx
0x18005c03a  jz      short loc_18005C050
0x18005c03c  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005c043  mov     r8, rbx; lpMem
0x18005c046  xor     edx, edx; dwFlags
0x18005c048  call    cs:__imp_HeapFree
0x18005c04e  xor     ebx, ebx
0x18005c050  xor     r9d, r9d; lpArguments
0x18005c053  xor     r8d, r8d; nNumberOfArguments
0x18005c056  xor     edx, edx; dwExceptionFlags
0x18005c058  mov     ecx, 80004005h; dwExceptionCode
0x18005c05d  call    cs:__imp_RaiseException
0x18005c063  mov     ecx, [rdi+8]
0x18005c066  xor     eax, eax
0x18005c068  mov     rdx, rsi; lpclsid
0x18005c06b  mov     [rbx+rcx*2], ax
0x18005c06f  mov     rcx, rbx; lpszProgID
0x18005c072  call    cs:__imp_CLSIDFromProgID
0x18005c078  test    eax, eax
0x18005c07a  jns     short loc_18005C0B0
0x18005c07c  test    rbx, rbx
0x18005c07f  jz      short loc_18005C095
0x18005c081  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005c088  mov     r8, rbx; lpMem
0x18005c08b  xor     edx, edx; dwFlags
0x18005c08d  call    cs:__imp_HeapFree
0x18005c093  xor     ebx, ebx
0x18005c095  mov     r9, [rdi]; unsigned __int8 *
0x18005c098  mov     r8d, 7E4h; unsigned int
0x18005c09e  mov     eax, [rdi+8]
0x18005c0a1  mov     rdx, r9; unsigned __int8 *
0x18005c0a4  mov     rcx, rbp; this
0x18005c0a7  mov     dword ptr [rsp+58h+lpWideCharStr], eax; unsigned int
0x18005c0ab  call    ?ThrowErrorSingleInsert@CTemplate@@AEAAXPEAEI0I@Z; CTemplate::ThrowErrorSingleInsert(uchar *,uint,uchar *,uint)
0x18005c0b0  mov     r8, rsi; struct _GUID *
0x18005c0b3  mov     rdx, rbx; unsigned __int16 *
0x18005c0b6  call    ?RememberProgidToCLSIDMapping@CTypelibCache@@QEAAJPEAGAEBU_GUID@@@Z; CTypelibCache::RememberProgidToCLSIDMapping(ushort *,_GUID const &)
0x18005c0bb  test    rbx, rbx
0x18005c0be  jz      short loc_18005C0D2
0x18005c0c0  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005c0c7  mov     r8, rbx; lpMem
0x18005c0ca  xor     edx, edx; dwFlags
0x18005c0cc  call    cs:__imp_HeapFree
0x18005c0d2  add     rsp, 38h
0x18005c0d6  pop     rdi
0x18005c0d7  pop     rsi
0x18005c0d8  pop     rbp
0x18005c0d9  pop     rbx
0x18005c0da  retn
```
