# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x40b164`
- end: `0x40b27b`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QAEXABUFailureInfo@3@I@Z`
- size: `279`
- prototype: `void __thiscall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x40b2ec`

## callees

- `0x40a6b9`
- `0x40a9f0`
- `0x40b164`
- `0x40bbbd`
- `0x40bc30`
- `0x40eb27`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x40b211`
- `KERNEL32!GetProcessHeap` at `0x40b211`
- `KERNEL32!HeapFree` at `0x40b21b`
- `KERNEL32!HeapFree` at `0x40b21b`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        unsigned int a3)
{
  unsigned int v4; // esi
  char *v5; // eax
  const char *v6; // ecx
  unsigned int v7; // ebx
  const char *v8; // ecx
  SIZE_T v9; // eax
  SIZE_T *v10; // ebx
  void *v11; // esi
  HANDLE ProcessHeap; // eax
  char *v13; // ecx
  char *v14; // esi
  char *v15; // eax
  char *v16; // eax
  char *v17; // eax
  wil::details *v18; // [esp+0h] [ebp-1Ch]
  const unsigned __int16 *v19; // [esp+4h] [ebp-18h]
  _DWORD *v20; // [esp+Ch] [ebp-10h]
  _DWORD *v21; // [esp+10h] [ebp-Ch]
  SIZE_T v22; // [esp+14h] [ebp-8h]
  LPVOID v23; // [esp+18h] [ebp-4h]

  v4 = 1;
  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 3) = 0;
  *((_WORD *)this + 8) = *((_WORD *)a2 + 20);
  *((_BYTE *)this + 18) = *(_BYTE *)a2;
  *((_DWORD *)this + 5) = 0;
  v21 = (_DWORD *)((char *)this + 20);
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 20);
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 21);
  v5 = (char *)this + 32;
  *((_DWORD *)this + 8) = 0;
  v6 = (const char *)*((_DWORD *)a2 + 9);
  v20 = v5;
  if ( v6 )
    v7 = strlen(v6) + 1;
  else
    v7 = 1;
  v8 = (const char *)*((_DWORD *)a2 + 19);
  if ( v8 )
    v4 = strlen(v8) + 1;
  v9 = v7 + v4 + wil::details::ResultStringSize(v18, v19);
  v22 = v9;
  v10 = (SIZE_T *)((char *)this + 40);
  if ( !*((_DWORD *)this + 9) || *v10 < v9 )
  {
    v23 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v23 )
    {
      v11 = (void *)*((_DWORD *)this + 9);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      *((_DWORD *)this + 9) = v23;
      *v10 = v22;
    }
  }
  v13 = (char *)*((_DWORD *)this + 9);
  if ( v13 )
  {
    v14 = &v13[*v10];
    v15 = wil::details::WriteResultString<char const *>(v13, v14, *((_BYTE **)a2 + 9), (_DWORD *)this + 3);
    v16 = wil::details::WriteResultString<char const *>(v15, v14, *((_BYTE **)a2 + 19), v21);
    v17 = wil::details::WriteResultString<unsigned short const *>(v16, v14, *((_WORD **)a2 + 5), v20);
    memset(v17, 0, v14 - v17);
  }
}

```

## disassembly

```asm
0x40b164  mov     edi, edi
0x40b166  push    ebp
0x40b167  mov     ebp, esp
0x40b169  sub     esp, 10h
0x40b16c  mov     edx, [ebp+arg_0]
0x40b16f  mov     eax, [ebp+arg_4]
0x40b172  push    ebx; unsigned int
0x40b173  push    esi; unsigned int
0x40b174  push    edi; this
0x40b175  mov     edi, ecx
0x40b177  xor     esi, esi
0x40b179  xor     ecx, ecx
0x40b17b  inc     esi
0x40b17c  mov     [edi+4], eax
0x40b17f  mov     eax, [edx+8]
0x40b182  mov     [edi+8], eax
0x40b185  mov     [edi+0Ch], ecx
0x40b188  mov     ax, [edx+28h]
0x40b18c  mov     [edi+10h], ax
0x40b190  mov     al, [edx]
0x40b192  mov     [edi+12h], al
0x40b195  lea     eax, [edi+14h]
0x40b198  mov     [eax], ecx
0x40b19a  mov     [ebp+var_C], eax
0x40b19d  mov     eax, [edx+50h]
0x40b1a0  mov     [edi+18h], eax
0x40b1a3  mov     eax, [edx+54h]
0x40b1a6  mov     [edi+1Ch], eax
0x40b1a9  lea     eax, [edi+20h]
0x40b1ac  mov     [eax], ecx
0x40b1ae  mov     ecx, [edx+24h]
0x40b1b1  mov     [ebp+var_10], eax
0x40b1b4  test    ecx, ecx
0x40b1b6  jnz     short loc_40B1BC
0x40b1b8  mov     ebx, esi
0x40b1ba  jmp     short loc_40B1CB
0x40b1bc  lea     ebx, [ecx+1]
0x40b1bf  mov     al, [ecx]
0x40b1c1  inc     ecx
0x40b1c2  test    al, al
0x40b1c4  jnz     short loc_40B1BF
0x40b1c6  sub     ecx, ebx
0x40b1c8  lea     ebx, [ecx+1]
0x40b1cb  mov     ecx, [edx+4Ch]
0x40b1ce  test    ecx, ecx
0x40b1d0  jz      short loc_40B1E1
0x40b1d2  lea     esi, [ecx+1]
0x40b1d5  mov     al, [ecx]
0x40b1d7  inc     ecx
0x40b1d8  test    al, al
0x40b1da  jnz     short loc_40B1D5
0x40b1dc  sub     ecx, esi
0x40b1de  lea     esi, [ecx+1]
0x40b1e1  mov     ecx, [edx+14h]
0x40b1e4  call    ?ResultStringSize@details@wil@@YGIPBG@Z; wil::details::ResultStringSize(ushort const *)
0x40b1e9  add     eax, esi
0x40b1eb  add     eax, ebx
0x40b1ed  cmp     dword ptr [edi+24h], 0
0x40b1f1  mov     [ebp+var_8], eax
0x40b1f4  lea     ebx, [edi+28h]
0x40b1f7  jz      short loc_40B1FD
0x40b1f9  cmp     [ebx], eax
0x40b1fb  jnb     short loc_40B22C
0x40b1fd  push    8
0x40b1ff  mov     edx, eax
0x40b201  pop     ecx
0x40b202  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x40b207  mov     [ebp+var_4], eax
0x40b20a  test    eax, eax
0x40b20c  jz      short loc_40B22C
0x40b20e  mov     esi, [edi+24h]
0x40b211  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40b217  push    esi; lpMem
0x40b218  push    0; dwFlags
0x40b21a  push    eax; hHeap
0x40b21b  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40b221  mov     eax, [ebp+var_4]
0x40b224  mov     [edi+24h], eax
0x40b227  mov     eax, [ebp+var_8]
0x40b22a  mov     [ebx], eax
0x40b22c  mov     ecx, [edi+24h]; Destination
0x40b22f  test    ecx, ecx
0x40b231  jz      short loc_40B274
0x40b233  mov     esi, [ebx]
0x40b235  lea     eax, [edi+0Ch]
0x40b238  mov     edi, [ebp+arg_0]
0x40b23b  add     esi, ecx
0x40b23d  push    eax; int
0x40b23e  mov     edx, esi
0x40b240  push    dword ptr [edi+24h]; Source
0x40b243  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x40b248  push    [ebp+var_C]; int
0x40b24b  mov     edx, esi
0x40b24d  mov     ecx, eax; Destination
0x40b24f  push    dword ptr [edi+4Ch]; Source
0x40b252  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x40b257  push    [ebp+var_10]; int
0x40b25a  mov     edx, esi
0x40b25c  mov     ecx, eax; Destination
0x40b25e  push    dword ptr [edi+14h]; Source
0x40b261  call    ??$WriteResultString@PBG@details@wil@@YGPAEPAE0PBGPAPBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x40b266  sub     esi, eax
0x40b268  push    esi; Size
0x40b269  push    0; Val
0x40b26b  push    eax; void *
0x40b26c  call    _memset
0x40b271  add     esp, 0Ch
0x40b274  pop     edi
0x40b275  pop     esi
0x40b276  pop     ebx
0x40b277  leave
0x40b278  retn    8
```
