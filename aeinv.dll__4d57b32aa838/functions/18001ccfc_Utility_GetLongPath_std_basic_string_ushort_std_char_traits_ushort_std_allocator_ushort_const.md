# Utility::GetLongPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001ccfc`
- end: `0x18001ce8c`
- name: `?GetLongPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `400`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180007824`
- `0x18000feac`
- `0x180011900`
- `0x18003c10c`

## callees

- `0x180018a60`
- `0x180018ff4`
- `0x18001ccfc`
- `0x18001e0d0`
- `0x18001ea80`
- `0x180029328`
- `0x18003ffec`
- `0x180052c34`
- `0x180059920`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x18001cd97`
- `KERNEL32!GetLongPathNameW` at `0x18001cdcf`
- `KERNEL32!GetLongPathNameW` at `0x18001cd97`
- `KERNEL32!GetLongPathNameW` at `0x18001cdcf`
- `KERNEL32!GetFileAttributesW` at `0x18001cd3e`
- `KERNEL32!GetFileAttributesW` at `0x18001cd3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Utility::GetLongPath(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  const WCHAR *v4; // rcx
  __int64 v5; // rdx
  WCHAR *v6; // rdx
  const WCHAR *v7; // rcx
  DWORD LongPathNameW; // eax
  WCHAR *v9; // rdx
  __int64 v10; // rcx
  LPWSTR *v11; // rcx
  size_t v12; // r8
  LPWSTR *v13; // r10
  __int16 v14; // dx
  __int64 v15; // r10
  __int64 v16; // r11
  LPWSTR lpszLongPath[2]; // [rsp+48h] [rbp-28h] BYREF
  DWORD cchBuffer[2]; // [rsp+58h] [rbp-18h]
  unsigned __int64 v20; // [rsp+60h] [rbp-10h]

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  if ( GetFileAttributesW(v4) == -1 )
  {
    std::wstring::wstring(a1, v2);
  }
  else
  {
    *(_OWORD *)lpszLongPath = 0;
    *(_QWORD *)cchBuffer = 0;
    v20 = 0;
    std::wstring::_Construct<0,unsigned short>(lpszLongPath, v5, 260);
    v6 = (WCHAR *)lpszLongPath;
    if ( v20 > 7 )
      v6 = lpszLongPath[0];
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v7 = v2;
    else
      v7 = *(const WCHAR **)v2;
    LongPathNameW = GetLongPathNameW(v7, v6, 0x104u);
    if ( LongPathNameW > 0x104 )
    {
      std::wstring::resize(lpszLongPath, LongPathNameW + 1);
      v9 = (WCHAR *)lpszLongPath;
      if ( v20 > 7 )
        v9 = lpszLongPath[0];
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(const WCHAR **)v2;
      LongPathNameW = GetLongPathNameW(v2, v9, cchBuffer[0]);
    }
    v10 = *(_QWORD *)cchBuffer;
    if ( (unsigned __int64)LongPathNameW > *(_QWORD *)cchBuffer )
    {
      v12 = LongPathNameW - *(_QWORD *)cchBuffer;
      if ( v12 > v20 - *(_QWORD *)cchBuffer )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
          (unsigned int)lpszLongPath,
          LongPathNameW - cchBuffer[0],
          v12,
          LongPathNameW - cchBuffer[0],
          0);
      }
      else
      {
        *(_QWORD *)cchBuffer = LongPathNameW;
        v13 = lpszLongPath;
        if ( v20 > 7 )
          v13 = (LPWSTR *)lpszLongPath[0];
        wmemset((wchar_t *)v13 + v10, 0, v12);
        *(_WORD *)(v15 + 2 * v16) = v14;
      }
    }
    else
    {
      *(_QWORD *)cchBuffer = LongPathNameW;
      v11 = lpszLongPath;
      if ( v20 > 7 )
        v11 = (LPWSTR *)lpszLongPath[0];
      *((_WORD *)v11 + LongPathNameW) = 0;
    }
    std::wstring::wstring(a1, lpszLongPath);
    std::wstring::~wstring(lpszLongPath);
  }
  return a1;
}

```

## disassembly

```asm
0x18001ccfc  mov     rax, rsp
0x18001ccff  push    rbp
0x18001cd00  mov     rbp, rsp
0x18001cd03  sub     rsp, 70h
0x18001cd07  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18001cd0f  mov     [rax+18h], rbx
0x18001cd13  mov     [rax+20h], rdi
0x18001cd17  mov     rax, cs:__security_cookie
0x18001cd1e  xor     rax, rsp
0x18001cd21  mov     [rbp+var_8], rax
0x18001cd25  mov     rbx, rdx
0x18001cd28  mov     rdi, rcx
0x18001cd2b  mov     [rbp+var_30], rcx
0x18001cd2f  cmp     qword ptr [rdx+18h], 7
0x18001cd34  jbe     short loc_18001CD3B
0x18001cd36  mov     rcx, [rdx]
0x18001cd39  jmp     short loc_18001CD3E
0x18001cd3b  mov     rcx, rbx; lpFileName
0x18001cd3e  call    cs:__imp_GetFileAttributesW
0x18001cd44  cmp     eax, 0FFFFFFFFh
0x18001cd47  jz      loc_18001CE60
0x18001cd4d  xorps   xmm0, xmm0
0x18001cd50  movups  xmmword ptr [rbp+lpszLongPath], xmm0
0x18001cd54  mov     qword ptr [rbp+cchBuffer], 0
0x18001cd5c  mov     [rbp+var_10], 0
0x18001cd64  mov     r8d, 104h
0x18001cd6a  lea     rcx, [rbp+lpszLongPath]
0x18001cd6e  call    ??$_Construct@$0A@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXG_K@Z; std::wstring::_Construct<0,ushort>(ushort,unsigned __int64)
0x18001cd73  nop
0x18001cd74  lea     rdx, [rbp+lpszLongPath]
0x18001cd78  cmp     [rbp+var_10], 7
0x18001cd7d  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x18001cd82  cmp     qword ptr [rbx+18h], 7
0x18001cd87  jbe     short loc_18001CD8E
0x18001cd89  mov     rcx, [rbx]
0x18001cd8c  jmp     short loc_18001CD91
0x18001cd8e  mov     rcx, rbx; lpszShortPath
0x18001cd91  mov     r8d, 104h; cchBuffer
0x18001cd97  call    cs:__imp_GetLongPathNameW
0x18001cd9d  cmp     eax, 104h
0x18001cda2  jbe     short loc_18001CDD5
0x18001cda4  lea     edx, [rax+1]
0x18001cda7  lea     rcx, [rbp+lpszLongPath]
0x18001cdab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001cdb0  lea     rdx, [rbp+lpszLongPath]
0x18001cdb4  cmp     [rbp+var_10], 7
0x18001cdb9  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x18001cdbe  cmp     qword ptr [rbx+18h], 7
0x18001cdc3  jbe     short loc_18001CDC8
0x18001cdc5  mov     rbx, [rbx]
0x18001cdc8  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x18001cdcc  mov     rcx, rbx; lpszShortPath
0x18001cdcf  call    cs:__imp_GetLongPathNameW
0x18001cdd5  mov     rcx, qword ptr [rbp+cchBuffer]
0x18001cdd9  mov     r11d, eax
0x18001cddc  cmp     r11, rcx
0x18001cddf  ja      short loc_18001CDFC
0x18001cde1  mov     qword ptr [rbp+cchBuffer], r11
0x18001cde5  lea     rcx, [rbp+lpszLongPath]
0x18001cde9  cmp     [rbp+var_10], 7
0x18001cdee  cmova   rcx, [rbp+lpszLongPath]
0x18001cdf3  xor     eax, eax
0x18001cdf5  mov     [rcx+r11*2], ax
0x18001cdfa  jmp     short loc_18001CE48
0x18001cdfc  mov     r8, r11
0x18001cdff  sub     r8, rcx; N
0x18001ce02  mov     rax, [rbp+var_10]
0x18001ce06  sub     rax, rcx
0x18001ce09  cmp     r8, rax
0x18001ce0c  ja      short loc_18001CE32
0x18001ce0e  mov     qword ptr [rbp+cchBuffer], r11
0x18001ce12  lea     r10, [rbp+lpszLongPath]
0x18001ce16  cmp     [rbp+var_10], 7
0x18001ce1b  cmova   r10, [rbp+lpszLongPath]
0x18001ce20  xor     edx, edx; C
0x18001ce22  lea     rcx, [r10+rcx*2]; S
0x18001ce26  call    wmemset
0x18001ce2b  mov     [r10+r11*2], dx
0x18001ce30  jmp     short loc_18001CE48
0x18001ce32  xor     ecx, ecx
0x18001ce34  mov     [rsp+70h+var_50], cx
0x18001ce39  mov     r9, r8
0x18001ce3c  mov     rdx, r8
0x18001ce3f  lea     rcx, [rbp+lpszLongPath]
0x18001ce43  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001ce48  lea     rdx, [rbp+lpszLongPath]
0x18001ce4c  mov     rcx, rdi
0x18001ce4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001ce54  nop
0x18001ce55  lea     rcx, [rbp+lpszLongPath]
0x18001ce59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ce5e  jmp     short loc_18001CE6B
0x18001ce60  mov     rdx, rbx
0x18001ce63  mov     rcx, rdi
0x18001ce66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ce6b  mov     rax, rdi
0x18001ce6e  mov     rcx, [rbp+var_8]
0x18001ce72  xor     rcx, rsp; StackCookie
0x18001ce75  call    __security_check_cookie
0x18001ce7a  lea     r11, [rsp+70h+var_s0]
0x18001ce7f  mov     rbx, [r11+20h]
0x18001ce83  mov     rdi, [r11+28h]
0x18001ce87  mov     rsp, r11
0x18001ce8a  pop     rbp
0x18001ce8b  retn
```
