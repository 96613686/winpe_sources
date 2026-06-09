# Win32FileSystem::GetSystem32Path(void)

- ea: `0x1800922e0`
- end: `0x180092389`
- name: `?GetSystem32Path@Win32FileSystem@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c6e4`
- `0x1800922e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180092327`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009234b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180092327`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009234b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WCHAR *__fastcall Win32FileSystem::GetSystem32Path(__int64 a1, WCHAR *a2)
{
  WCHAR *v3; // rcx
  UINT SystemDirectoryW; // edi
  WCHAR *v5; // rcx
  WCHAR *v6; // rax
  __int64 v7; // rdx

  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 1;
  *((_QWORD *)a2 + 3) = 7;
  *(_DWORD *)a2 = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v3 = a2;
  else
    v3 = *(WCHAR **)a2;
  SystemDirectoryW = GetSystemDirectoryW(v3, 0);
  std::wstring::resize(a2, SystemDirectoryW + 1);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v5 = a2;
  else
    v5 = *(WCHAR **)a2;
  GetSystemDirectoryW(v5, SystemDirectoryW);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v6 = a2;
  else
    v6 = *(WCHAR **)a2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  std::wstring::resize(a2, v7);
  return a2;
}

```

## disassembly

```asm
0x1800922e0  mov     rax, rsp
0x1800922e3  mov     [rax+8], rbx
0x1800922e7  mov     [rax+18h], rbp
0x1800922eb  mov     [rax+10h], rdx
0x1800922ef  push    rdi
0x1800922f0  sub     rsp, 30h
0x1800922f4  mov     rbx, rdx
0x1800922f7  xor     ebp, ebp
0x1800922f9  mov     [rax-18h], ebp
0x1800922fc  xorps   xmm0, xmm0
0x1800922ff  movups  xmmword ptr [rdx], xmm0
0x180092302  lea     ecx, [rbp+1]
0x180092305  mov     [rdx+10h], rcx
0x180092309  mov     qword ptr [rdx+18h], 7
0x180092311  mov     [rdx], ebp
0x180092313  mov     [rax-18h], ecx
0x180092316  cmp     qword ptr [rdx+18h], 7
0x18009231b  jbe     short loc_180092322
0x18009231d  mov     rcx, [rdx]
0x180092320  jmp     short loc_180092325
0x180092322  mov     rcx, rbx; lpBuffer
0x180092325  xor     edx, edx; uSize
0x180092327  call    cs:__imp_GetSystemDirectoryW
0x18009232d  mov     edi, eax
0x18009232f  lea     edx, [rax+1]
0x180092332  mov     rcx, rbx
0x180092335  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18009233a  cmp     qword ptr [rbx+18h], 7
0x18009233f  jbe     short loc_180092346
0x180092341  mov     rcx, [rbx]
0x180092344  jmp     short loc_180092349
0x180092346  mov     rcx, rbx; lpBuffer
0x180092349  mov     edx, edi; uSize
0x18009234b  call    cs:__imp_GetSystemDirectoryW
0x180092351  cmp     qword ptr [rbx+18h], 7
0x180092356  jbe     short loc_18009235D
0x180092358  mov     rax, [rbx]
0x18009235b  jmp     short loc_180092360
0x18009235d  mov     rax, rbx
0x180092360  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180092364  inc     rdx
0x180092367  cmp     [rax+rdx*2], bp
0x18009236b  jnz     short loc_180092364
0x18009236d  mov     rcx, rbx
0x180092370  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180092375  mov     rax, rbx
0x180092378  mov     rbx, [rsp+38h+arg_0]
0x18009237d  mov     rbp, [rsp+38h+arg_10]
0x180092382  add     rsp, 30h
0x180092386  pop     rdi
0x180092387  retn
```
