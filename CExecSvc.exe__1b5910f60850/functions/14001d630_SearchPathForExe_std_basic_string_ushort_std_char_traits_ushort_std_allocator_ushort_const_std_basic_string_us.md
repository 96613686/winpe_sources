# SearchPathForExe(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001d630`
- end: `0x14001d755`
- name: `?SearchPathForExe@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@@Z`
- size: `293`
- prototype: `int __fastcall(_QWORD *lpFileName, _QWORD *lpPath, char *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14001ce88`

## callees

- `0x1400133d4`
- `0x14001d630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d743`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14001d697`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14001d697`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001d6dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001d6dc`

## pseudocode

```c
int __fastcall SearchPathForExe(_QWORD *lpFileName, _QWORD *lpPath, char *Src)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rsi
  WCHAR *lpBuffer; // rax
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  DWORD v10; // eax
  unsigned __int64 v11; // rdi
  _QWORD *v12; // r8
  DWORD FileAttributesW; // eax
  unsigned __int64 v15; // rcx
  bool v16; // cc
  _QWORD *v17; // r8
  _WORD *v18; // rdi

  v3 = Src;
  v4 = Src + 24;
  while ( 1 )
  {
    if ( v3[2] )
    {
      lpBuffer = (WCHAR *)v3;
      if ( *v4 > 7u )
        lpBuffer = (WCHAR *)*v3;
    }
    else
    {
      lpBuffer = 0;
    }
    v8 = lpFileName[3] <= 7u ? (const WCHAR *)lpFileName : (const WCHAR *)*lpFileName;
    v9 = lpPath[3] <= 7u ? (const WCHAR *)lpPath : (const WCHAR *)*lpPath;
    v10 = SearchPathW(v9, v8, L".exe", *((_DWORD *)v3 + 4), lpBuffer, 0);
    if ( !v10 )
      break;
    v11 = v3[2];
    if ( v10 > v11 )
    {
      v15 = v10 - v11;
      if ( v15 > *v4 - v11 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(v3);
      }
      else
      {
        v16 = *v4 <= 7u;
        v17 = v3;
        v3[2] = v10;
        if ( !v16 )
          v17 = (_QWORD *)*v3;
        v18 = (_WORD *)v17 + v11;
        if ( v15 )
        {
          while ( v15 )
          {
            *v18++ = 0;
            --v15;
          }
        }
        *((_WORD *)v17 + v10) = 0;
      }
    }
    else
    {
      v3[2] = v10;
      v12 = v3;
      if ( *v4 > 7u )
        v12 = (_QWORD *)*v3;
      *((_WORD *)v12 + v10) = 0;
      if ( v10 < v11 )
      {
        if ( *v4 > 7u )
          v3 = (_QWORD *)*v3;
        FileAttributesW = GetFileAttributesW((LPCWSTR)v3);
        if ( FileAttributesW != -1 )
          return (FileAttributesW & 0x10) != 0 ? 5 : 0;
        return GetLastError();
      }
    }
  }
  return GetLastError();
}

```

## disassembly

```asm
0x14001d630  push    rbx
0x14001d632  push    rsi
0x14001d633  push    rdi
0x14001d634  push    r14
0x14001d636  push    r15
0x14001d638  sub     rsp, 30h
0x14001d63c  mov     rbx, r8
0x14001d63f  lea     rsi, [r8+18h]
0x14001d643  mov     r15, rdx
0x14001d646  mov     r14, rcx
0x14001d649  cmp     qword ptr [rbx+10h], 0
0x14001d64e  jnz     short loc_14001D654
0x14001d650  xor     eax, eax
0x14001d652  jmp     short loc_14001D660
0x14001d654  cmp     qword ptr [rsi], 7
0x14001d658  mov     rax, rbx
0x14001d65b  jbe     short loc_14001D660
0x14001d65d  mov     rax, [rbx]
0x14001d660  cmp     qword ptr [r14+18h], 7
0x14001d665  jbe     short loc_14001D66C
0x14001d667  mov     rdx, [r14]
0x14001d66a  jmp     short loc_14001D66F
0x14001d66c  mov     rdx, r14; lpFileName
0x14001d66f  cmp     qword ptr [r15+18h], 7
0x14001d674  jbe     short loc_14001D67B
0x14001d676  mov     rcx, [r15]
0x14001d679  jmp     short loc_14001D67E
0x14001d67b  mov     rcx, r15; lpPath
0x14001d67e  mov     r9d, [rbx+10h]; nBufferLength
0x14001d682  lea     r8, Extension; ".exe"
0x14001d689  mov     [rsp+58h+lpFilePart], 0; lpFilePart
0x14001d692  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x14001d697  call    cs:__imp_SearchPathW
0x14001d69d  test    eax, eax
0x14001d69f  jz      loc_14001D743
0x14001d6a5  mov     rdi, [rbx+10h]
0x14001d6a9  mov     edx, eax
0x14001d6ab  cmp     rdx, rdi
0x14001d6ae  ja      short loc_14001D6F2
0x14001d6b0  mov     [rbx+10h], rdx
0x14001d6b4  mov     r8, rbx
0x14001d6b7  cmp     qword ptr [rsi], 7
0x14001d6bb  jbe     short loc_14001D6C0
0x14001d6bd  mov     r8, [rbx]
0x14001d6c0  xor     eax, eax
0x14001d6c2  mov     [r8+rdx*2], ax
0x14001d6c7  cmp     rdx, rdi
0x14001d6ca  jnb     loc_14001D649
0x14001d6d0  cmp     qword ptr [rsi], 7
0x14001d6d4  jbe     short loc_14001D6D9
0x14001d6d6  mov     rbx, [rbx]
0x14001d6d9  mov     rcx, rbx; lpFileName
0x14001d6dc  call    cs:__imp_GetFileAttributesW
0x14001d6e2  cmp     eax, 0FFFFFFFFh
0x14001d6e5  jz      short loc_14001D743
0x14001d6e7  and     al, 10h
0x14001d6e9  neg     al
0x14001d6eb  sbb     eax, eax
0x14001d6ed  and     eax, 5
0x14001d6f0  jmp     short loc_14001D749
0x14001d6f2  mov     rax, [rsi]
0x14001d6f5  mov     rcx, rdx
0x14001d6f8  sub     rcx, rdi
0x14001d6fb  sub     rax, rdi
0x14001d6fe  cmp     rcx, rax
0x14001d701  ja      short loc_14001D730
0x14001d703  cmp     qword ptr [rsi], 7
0x14001d707  mov     r8, rbx
0x14001d70a  mov     [rbx+10h], rdx
0x14001d70e  jbe     short loc_14001D713
0x14001d710  mov     r8, [rbx]
0x14001d713  lea     rdi, [r8+rdi*2]
0x14001d717  test    rcx, rcx
0x14001d71a  jz      short loc_14001D724
0x14001d71c  xor     eax, eax
0x14001d71e  movzx   eax, ax
0x14001d721  rep stosw
0x14001d724  xor     eax, eax
0x14001d726  mov     [r8+rdx*2], ax
0x14001d72b  jmp     loc_14001D649
0x14001d730  mov     r9, rcx
0x14001d733  mov     rdx, rcx
0x14001d736  mov     rcx, rbx; Src
0x14001d739  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14001d73e  jmp     loc_14001D649
0x14001d743  call    cs:__imp_GetLastError
0x14001d749  add     rsp, 30h
0x14001d74d  pop     r15
0x14001d74f  pop     r14
0x14001d751  pop     rdi
0x14001d752  pop     rsi
0x14001d753  pop     rbx
0x14001d754  retn
```
