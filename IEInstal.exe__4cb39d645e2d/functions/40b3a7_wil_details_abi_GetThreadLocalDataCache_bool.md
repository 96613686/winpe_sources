# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x40b3a7`
- end: `0x40b42b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z`
- size: `132`
- prototype: `struct wil::details_abi::ThreadLocalData *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40b5e0`

## callees

- `0x40b3a7`
- `0x40c3ba`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40b3ed`
- `KERNEL32!GetCurrentThreadId` at `0x40b3ed`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *wil::details_abi::GetThreadLocalDataCache()
{
  int v0; // esi
  _DWORD *v1; // edi
  int v2; // ecx
  int v3; // esi
  DWORD CurrentThreadId; // ecx
  _DWORD *i; // edi
  int v7; // [esp+Ch] [ebp-4h] BYREF

  v0 = wil::details_abi::g_pProcessLocalData;
  v1 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_DWORD *)(wil::details_abi::g_pProcessLocalData + 4) )
    {
      v2 = *(_DWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v2, &v7) >= 0
        && !*(_DWORD *)(v0 + 4) )
      {
        *(_DWORD *)(v0 + 4) = v7;
      }
    }
    v3 = *(_DWORD *)(v0 + 4) != 0 ? *(_DWORD *)(v0 + 4) + 16 : 0;
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_DWORD **)(v3 + 4 * ((CurrentThreadId >> 2) % 0xA) + 8); ; i = (_DWORD *)i[1] )
      {
        if ( !i )
          return 0;
        if ( *i == CurrentThreadId )
          break;
      }
      v1 = i + 2;
      if ( v1 && !v1[2] )
        v1[2] = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x40b3a7  mov     edi, edi
0x40b3a9  push    ebp
0x40b3aa  mov     ebp, esp
0x40b3ac  push    ecx
0x40b3ad  push    ebx
0x40b3ae  push    esi
0x40b3af  mov     esi, ?g_pProcessLocalData@details_abi@wil@@3PAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x40b3b5  xor     ebx, ebx
0x40b3b7  push    edi
0x40b3b8  mov     edi, ebx
0x40b3ba  test    esi, esi
0x40b3bc  jz      short loc_40B412
0x40b3be  cmp     [esi+4], ebx
0x40b3c1  jnz     short loc_40B3DF
0x40b3c3  mov     ecx, [esi]
0x40b3c5  lea     edx, [ebp+var_4]
0x40b3c8  mov     [ebp+var_4], ebx
0x40b3cb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x40b3d0  test    eax, eax
0x40b3d2  js      short loc_40B3DF
0x40b3d4  cmp     [esi+4], ebx
0x40b3d7  jnz     short loc_40B3DF
0x40b3d9  mov     eax, [ebp+var_4]
0x40b3dc  mov     [esi+4], eax
0x40b3df  mov     esi, [esi+4]
0x40b3e2  lea     eax, [esi+10h]
0x40b3e5  neg     esi
0x40b3e7  sbb     esi, esi
0x40b3e9  and     esi, eax
0x40b3eb  jz      short loc_40B412
0x40b3ed  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40b3f3  mov     ecx, eax
0x40b3f5  xor     edx, edx
0x40b3f7  push    0Ah
0x40b3f9  pop     edi
0x40b3fa  shr     eax, 2
0x40b3fd  div     edi
0x40b3ff  mov     edi, [esi+edx*4+8]
0x40b403  jmp     short loc_40B40C
0x40b405  cmp     [edi], ecx
0x40b407  jz      short loc_40B419
0x40b409  mov     edi, [edi+4]
0x40b40c  test    edi, edi
0x40b40e  jnz     short loc_40B405
0x40b410  mov     edi, ebx
0x40b412  mov     eax, edi
0x40b414  pop     edi
0x40b415  pop     esi
0x40b416  pop     ebx
0x40b417  leave
0x40b418  retn
0x40b419  add     edi, 8
0x40b41c  jz      short loc_40B412
0x40b41e  cmp     [edi+8], ebx
0x40b421  jnz     short loc_40B412
0x40b423  lea     eax, [esi+4]
0x40b426  mov     [edi+8], eax
0x40b429  jmp     short loc_40B412
```
