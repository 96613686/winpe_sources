# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x180011e1c`
- end: `0x180012052`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `566`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x18000eb20`
- `0x180011e1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011e85`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011eb1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011edf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f0b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011e85`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011eb1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011edf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f0b`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Find(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        const union _CVDD **a5,
        const unsigned int **a6,
        const struct CODEVIEW_INFORMATION_1 **a7,
        unsigned int *a8,
        unsigned int *a9,
        struct EMBEDDED_PDB_INFORMATION *a10,
        bool *a11,
        unsigned __int16 *a12)
{
  __int64 v14; // rbx
  char v15; // r14
  bool *v16; // r13
  __int64 v17; // r14
  __int64 *v18; // rsi
  __int64 *i; // rdi
  __int64 *j; // rdi
  struct EMBEDDED_PDB_INFORMATION *v21; // rcx
  _QWORD *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int16 *v25; // r8
  unsigned __int16 v26; // dx
  __int64 result; // rax
  unsigned __int16 *v28; // rdx
  int v29; // [rsp+80h] [rbp+18h] BYREF
  unsigned int *v30; // [rsp+88h] [rbp+20h]

  v30 = a4;
  v29 = a3;
  try
  {
    v14 = 0;
    v15 = 0;
    v16 = a11;
    *a11 = 0;
    if ( a3 )
    {
      v17 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
              (char *)this + 16,
              &v29);
      v18 = *(__int64 **)v17;
      for ( i = *(__int64 **)(*(_QWORD *)v17 + 8LL); !*((_BYTE *)i + 25); i = (__int64 *)*i )
      {
        if ( (int)_o__wcsicmp(i[4], a2) >= 0 )
          v18 = i;
        else
          i += 2;
      }
      if ( *((_BYTE *)v18 + 25) || (int)_o__wcsicmp(a2, v18[4]) < 0 || v18 == *(__int64 **)v17 )
      {
        v15 = 0;
        goto LABEL_23;
      }
    }
    else
    {
      v18 = (__int64 *)*((_QWORD *)this + 4);
      for ( j = (__int64 *)v18[1]; !*((_BYTE *)j + 25); j = (__int64 *)*j )
      {
        if ( (int)_o__wcsicmp(j[4], a2) >= 0 )
          v18 = j;
        else
          j += 2;
      }
      if ( *((_BYTE *)v18 + 25) || (int)_o__wcsicmp(a2, v18[4]) < 0 || v18 == *((__int64 **)this + 4) )
      {
LABEL_23:
        if ( !v15 )
          return 2147943568LL;
        if ( !v14 )
          return 2147500037LL;
        *v30 = *(_DWORD *)(v14 + 64);
        *a5 = *(const union _CVDD **)(v14 + 72);
        *a6 = *(const unsigned int **)(v14 + 80);
        if ( a7 )
          *a7 = *(const struct CODEVIEW_INFORMATION_1 **)(v14 + 88);
        *a8 = *(_DWORD *)(v14 + 132);
        *a9 = *(_DWORD *)(v14 + 136);
        v21 = a10;
        *(_DWORD *)a10 = *(_DWORD *)(v14 + 104) - *(_DWORD *)(v14 + 96);
        *((_QWORD *)v21 + 1) = *(_QWORD *)(v14 + 96);
        *((_WORD *)v21 + 8) = *(_WORD *)(v14 + 122);
        *((_WORD *)v21 + 9) = *(_WORD *)(v14 + 120);
        *v16 = *(_BYTE *)(v14 + 124);
        v22 = (_QWORD *)(v14 + 32);
        if ( v22[3] > 7u )
          v22 = (_QWORD *)*v22;
        v23 = 2147483646;
        v24 = 780;
        v25 = a12;
        do
        {
          if ( !v23 )
            break;
          v26 = *(_WORD *)v22;
          if ( !*(_WORD *)v22 )
            break;
          v22 = (_QWORD *)((char *)v22 + 2);
          *v25++ = v26;
          --v23;
          --v24;
        }
        while ( v24 );
        result = v24 == 0 ? 0x8007007A : 0;
        v28 = v25 - 1;
        if ( v24 )
          v28 = v25;
        *v28 = 0;
        return result;
      }
    }
    v15 = 1;
    v14 = v18[5];
    goto LABEL_23;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  v14 = 0;
}

```

## disassembly

```asm
0x180011e1c  mov     rax, rsp
0x180011e1f  mov     [rax+8], rbx
0x180011e23  mov     [rax+10h], rsi
0x180011e27  mov     [rax+20h], r9
0x180011e2b  mov     [rax+18h], r8d
0x180011e2f  push    rdi
0x180011e30  push    r12
0x180011e32  push    r13
0x180011e34  push    r14
0x180011e36  push    r15
0x180011e38  sub     rsp, 40h
0x180011e3c  mov     r12, rdx
0x180011e3f  mov     r15, rcx
0x180011e42  xor     r9d, r9d
0x180011e45  mov     ebx, r9d
0x180011e48  mov     r14b, r9b
0x180011e4b  mov     r13, [rsp+68h+arg_50]
0x180011e53  mov     [r13+0], r9b
0x180011e57  test    r8d, r8d
0x180011e5a  jz      short loc_180011EC8
0x180011e5c  add     rcx, 10h
0x180011e60  lea     rdx, [rax+18h]
0x180011e64  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180011e69  mov     r14, rax
0x180011e6c  mov     rsi, [rax]
0x180011e6f  mov     rdi, [rsi+8]
0x180011e73  xor     eax, eax
0x180011e75  mov     [rsp+68h+var_3C], eax
0x180011e79  xor     r9d, r9d
0x180011e7c  jmp     short loc_180011E9E
0x180011e7e  mov     rdx, r12
0x180011e81  mov     rcx, [rdi+20h]
0x180011e85  call    cs:__imp__o__wcsicmp
0x180011e8b  xor     r9d, r9d
0x180011e8e  test    eax, eax
0x180011e90  jns     short loc_180011E98
0x180011e92  add     rdi, 10h
0x180011e96  jmp     short loc_180011E9B
0x180011e98  mov     rsi, rdi
0x180011e9b  mov     rdi, [rdi]
0x180011e9e  cmp     [rdi+19h], r9b
0x180011ea2  jz      short loc_180011E7E
0x180011ea4  cmp     [rsi+19h], r9b
0x180011ea8  jnz     short loc_180011EC3
0x180011eaa  mov     rdx, [rsi+20h]
0x180011eae  mov     rcx, r12
0x180011eb1  call    cs:__imp__o__wcsicmp
0x180011eb7  xor     r9d, r9d
0x180011eba  test    eax, eax
0x180011ebc  js      short loc_180011EC3
0x180011ebe  cmp     rsi, [r14]
0x180011ec1  jnz     short loc_180011F1E
0x180011ec3  mov     r14b, r9b
0x180011ec6  jmp     short loc_180011F25
0x180011ec8  mov     rsi, [rcx+20h]
0x180011ecc  mov     rdi, [rsi+8]
0x180011ed0  xor     eax, eax
0x180011ed2  mov     [rsp+68h+var_3C], eax
0x180011ed6  jmp     short loc_180011EF8
0x180011ed8  mov     rdx, r12
0x180011edb  mov     rcx, [rdi+20h]
0x180011edf  call    cs:__imp__o__wcsicmp
0x180011ee5  xor     r9d, r9d
0x180011ee8  test    eax, eax
0x180011eea  jns     short loc_180011EF2
0x180011eec  add     rdi, 10h
0x180011ef0  jmp     short loc_180011EF5
0x180011ef2  mov     rsi, rdi
0x180011ef5  mov     rdi, [rdi]
0x180011ef8  cmp     [rdi+19h], r9b
0x180011efc  jz      short loc_180011ED8
0x180011efe  cmp     [rsi+19h], r9b
0x180011f02  jnz     short loc_180011F25
0x180011f04  mov     rdx, [rsi+20h]
0x180011f08  mov     rcx, r12
0x180011f0b  call    cs:__imp__o__wcsicmp
0x180011f11  xor     r9d, r9d
0x180011f14  test    eax, eax
0x180011f16  js      short loc_180011F25
0x180011f18  cmp     rsi, [r15+20h]
0x180011f1c  jz      short loc_180011F25
0x180011f1e  mov     r14b, 1
0x180011f21  mov     rbx, [rsi+28h]
0x180011f25  test    r14b, r14b
0x180011f28  jz      loc_18001202E
0x180011f2e  test    rbx, rbx
0x180011f31  jz      loc_180012027
0x180011f37  mov     eax, [rbx+40h]
0x180011f3a  mov     rcx, [rsp+68h+arg_18]
0x180011f42  mov     [rcx], eax
0x180011f44  mov     rcx, [rbx+48h]
0x180011f48  mov     rax, [rsp+68h+arg_20]
0x180011f50  mov     [rax], rcx
0x180011f53  mov     rcx, [rbx+50h]
0x180011f57  mov     rax, [rsp+68h+arg_28]
0x180011f5f  mov     [rax], rcx
0x180011f62  mov     rcx, [rsp+68h+arg_30]
0x180011f6a  test    rcx, rcx
0x180011f6d  jz      short loc_180011F76
0x180011f6f  mov     rax, [rbx+58h]
0x180011f73  mov     [rcx], rax
0x180011f76  mov     ecx, [rbx+84h]
0x180011f7c  mov     rax, [rsp+68h+arg_38]
0x180011f84  mov     [rax], ecx
0x180011f86  mov     ecx, [rbx+88h]
0x180011f8c  mov     rax, [rsp+68h+arg_40]
0x180011f94  mov     [rax], ecx
0x180011f96  mov     eax, [rbx+68h]
0x180011f99  sub     eax, [rbx+60h]
0x180011f9c  mov     rcx, [rsp+68h+arg_48]
0x180011fa4  mov     [rcx], eax
0x180011fa6  mov     rax, [rbx+60h]
0x180011faa  mov     [rcx+8], rax
0x180011fae  movzx   eax, word ptr [rbx+7Ah]
0x180011fb2  mov     [rcx+10h], ax
0x180011fb6  movzx   eax, word ptr [rbx+78h]
0x180011fba  mov     [rcx+12h], ax
0x180011fbe  mov     al, [rbx+7Ch]
0x180011fc1  mov     [r13+0], al
0x180011fc5  add     rbx, 20h ; ' '
0x180011fc9  cmp     qword ptr [rbx+18h], 7
0x180011fce  jbe     short loc_180011FD3
0x180011fd0  mov     rbx, [rbx]
0x180011fd3  mov     eax, 7FFFFFFEh
0x180011fd8  mov     ecx, 30Ch
0x180011fdd  mov     r8, [rsp+68h+arg_58]
0x180011fe5  test    rax, rax
0x180011fe8  jz      short loc_180012007
0x180011fea  movzx   edx, word ptr [rbx]
0x180011fed  test    dx, dx
0x180011ff0  jz      short loc_180012007
0x180011ff2  add     rbx, 2
0x180011ff6  mov     [r8], dx
0x180011ffa  add     r8, 2
0x180011ffe  dec     rax
0x180012001  sub     rcx, 1
0x180012005  jnz     short loc_180011FE5
0x180012007  mov     rax, rcx
0x18001200a  neg     rax
0x18001200d  sbb     eax, eax
0x18001200f  not     eax
0x180012011  and     eax, 8007007Ah
0x180012016  lea     rdx, [r8-2]
0x18001201a  test    rcx, rcx
0x18001201d  cmovnz  rdx, r8
0x180012021  mov     [rdx], r9w
0x180012025  jmp     short loc_18001203A
0x180012027  mov     eax, 80004005h
0x18001202c  jmp     short loc_18001203A
0x18001202e  mov     eax, 80070490h
0x180012033  jmp     short loc_18001203A
0x180012035  mov     eax, 8007000Eh
0x18001203a  mov     rbx, [rsp+68h+arg_0]
0x18001203f  mov     rsi, [rsp+68h+arg_8]
0x180012044  add     rsp, 40h
0x180012048  pop     r15
0x18001204a  pop     r14
0x18001204c  pop     r13
0x18001204e  pop     r12
0x180012050  pop     rdi
0x180012051  retn
```
