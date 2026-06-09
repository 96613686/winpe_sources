# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x1800239f4`
- end: `0x180023bf8`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `516`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180006424`
- `0x180020760`
- `0x1800239f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023a59`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023abd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023aed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023a59`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023abd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023aed`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Find(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        unsigned int a3,
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
  char v15; // si
  bool *v16; // r13
  __int64 v17; // rsi
  __int64 *v18; // r14
  __int64 *i; // rdi
  __int64 *j; // rdi
  struct EMBEDDED_PDB_INFORMATION *v21; // rcx
  const unsigned __int16 *v22; // r8
  __int64 result; // rax
  unsigned int v24; // [rsp+80h] [rbp+18h] BYREF
  unsigned int *v25; // [rsp+88h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  try
  {
    v14 = 0;
    v15 = 0;
    v16 = a11;
    *a11 = 0;
    if ( a3 )
    {
      v17 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
              (__int64 *)this + 2,
              &v24);
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
        goto LABEL_21;
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
        goto LABEL_21;
    }
    v15 = 1;
    v14 = v18[5];
LABEL_21:
    if ( v15 )
    {
      if ( v14 )
      {
        *v25 = *(_DWORD *)(v14 + 64);
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
        v22 = (const unsigned __int16 *)(v14 + 32);
        if ( *(_QWORD *)(v14 + 56) > 7u )
          v22 = *(const unsigned __int16 **)v22;
        result = StringCchCopyW(a12, 0x30Cu, v22);
      }
      else
      {
        result = 2147500037LL;
      }
    }
    else
    {
      result = 2147943568LL;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800239f4  mov     rax, rsp
0x1800239f7  mov     [rax+8], rbx
0x1800239fb  mov     [rax+10h], rsi
0x1800239ff  mov     [rax+20h], r9
0x180023a03  mov     [rax+18h], r8d
0x180023a07  push    rdi
0x180023a08  push    r12
0x180023a0a  push    r13
0x180023a0c  push    r14
0x180023a0e  push    r15
0x180023a10  sub     rsp, 40h
0x180023a14  mov     r12, rdx
0x180023a17  mov     r15, rcx
0x180023a1a  xor     ebx, ebx
0x180023a1c  xor     sil, sil
0x180023a1f  mov     r13, [rsp+68h+arg_50]
0x180023a27  mov     [r13+0], bl
0x180023a2b  test    r8d, r8d
0x180023a2e  jz      short loc_180023AA3
0x180023a30  add     rcx, 10h
0x180023a34  lea     rdx, [rax+18h]
0x180023a38  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180023a3d  mov     rsi, rax
0x180023a40  mov     r14, [rax]
0x180023a43  mov     rdi, [r14+8]
0x180023a47  xor     eax, eax
0x180023a49  mov     [rsp+68h+var_3C], eax
0x180023a4d  cmp     [rdi+19h], al
0x180023a50  jnz     short loc_180023A7B
0x180023a52  mov     rdx, r12
0x180023a55  mov     rcx, [rdi+20h]
0x180023a59  call    cs:__imp__o__wcsicmp
0x180023a60  nop     dword ptr [rax+rax+00h]
0x180023a65  test    eax, eax
0x180023a67  jns     short loc_180023A6F
0x180023a69  add     rdi, 10h
0x180023a6d  jmp     short loc_180023A72
0x180023a6f  mov     r14, rdi
0x180023a72  mov     rdi, [rdi]
0x180023a75  cmp     byte ptr [rdi+19h], 0
0x180023a79  jz      short loc_180023A52
0x180023a7b  cmp     byte ptr [r14+19h], 0
0x180023a80  jnz     short loc_180023A9E
0x180023a82  mov     rdx, [r14+20h]
0x180023a86  mov     rcx, r12
0x180023a89  call    cs:__imp__o__wcsicmp
0x180023a90  nop     dword ptr [rax+rax+00h]
0x180023a95  test    eax, eax
0x180023a97  js      short loc_180023A9E
0x180023a99  cmp     r14, [rsi]
0x180023a9c  jnz     short loc_180023B03
0x180023a9e  xor     sil, sil
0x180023aa1  jmp     short loc_180023B0A
0x180023aa3  mov     r14, [rcx+20h]
0x180023aa7  mov     rdi, [r14+8]
0x180023aab  xor     eax, eax
0x180023aad  mov     [rsp+68h+var_3C], eax
0x180023ab1  cmp     [rdi+19h], al
0x180023ab4  jnz     short loc_180023ADF
0x180023ab6  mov     rdx, r12
0x180023ab9  mov     rcx, [rdi+20h]
0x180023abd  call    cs:__imp__o__wcsicmp
0x180023ac4  nop     dword ptr [rax+rax+00h]
0x180023ac9  test    eax, eax
0x180023acb  jns     short loc_180023AD3
0x180023acd  add     rdi, 10h
0x180023ad1  jmp     short loc_180023AD6
0x180023ad3  mov     r14, rdi
0x180023ad6  mov     rdi, [rdi]
0x180023ad9  cmp     byte ptr [rdi+19h], 0
0x180023add  jz      short loc_180023AB6
0x180023adf  cmp     byte ptr [r14+19h], 0
0x180023ae4  jnz     short loc_180023B0A
0x180023ae6  mov     rdx, [r14+20h]
0x180023aea  mov     rcx, r12
0x180023aed  call    cs:__imp__o__wcsicmp
0x180023af4  nop     dword ptr [rax+rax+00h]
0x180023af9  test    eax, eax
0x180023afb  js      short loc_180023B0A
0x180023afd  cmp     r14, [r15+20h]
0x180023b01  jz      short loc_180023B0A
0x180023b03  mov     sil, 1
0x180023b06  mov     rbx, [r14+28h]
0x180023b0a  test    sil, sil
0x180023b0d  jz      loc_180023BD3
0x180023b13  test    rbx, rbx
0x180023b16  jz      loc_180023BCC
0x180023b1c  mov     eax, [rbx+40h]
0x180023b1f  mov     rcx, [rsp+68h+arg_18]
0x180023b27  mov     [rcx], eax
0x180023b29  mov     rcx, [rbx+48h]
0x180023b2d  mov     rax, [rsp+68h+arg_20]
0x180023b35  mov     [rax], rcx
0x180023b38  mov     rcx, [rbx+50h]
0x180023b3c  mov     rax, [rsp+68h+arg_28]
0x180023b44  mov     [rax], rcx
0x180023b47  mov     rcx, [rsp+68h+arg_30]
0x180023b4f  test    rcx, rcx
0x180023b52  jz      short loc_180023B5B
0x180023b54  mov     rax, [rbx+58h]
0x180023b58  mov     [rcx], rax
0x180023b5b  mov     ecx, [rbx+84h]
0x180023b61  mov     rax, [rsp+68h+arg_38]
0x180023b69  mov     [rax], ecx
0x180023b6b  mov     ecx, [rbx+88h]
0x180023b71  mov     rax, [rsp+68h+arg_40]
0x180023b79  mov     [rax], ecx
0x180023b7b  mov     eax, [rbx+68h]
0x180023b7e  sub     eax, [rbx+60h]
0x180023b81  mov     rcx, [rsp+68h+arg_48]
0x180023b89  mov     [rcx], eax
0x180023b8b  mov     rax, [rbx+60h]
0x180023b8f  mov     [rcx+8], rax
0x180023b93  movzx   eax, word ptr [rbx+7Ah]
0x180023b97  mov     [rcx+10h], ax
0x180023b9b  movzx   eax, word ptr [rbx+78h]
0x180023b9f  mov     [rcx+12h], ax
0x180023ba3  mov     al, [rbx+7Ch]
0x180023ba6  mov     [r13+0], al
0x180023baa  lea     r8, [rbx+20h]
0x180023bae  cmp     qword ptr [r8+18h], 7
0x180023bb3  jbe     short loc_180023BB8
0x180023bb5  mov     r8, [r8]; unsigned __int16 *
0x180023bb8  mov     edx, 30Ch; unsigned __int64
0x180023bbd  mov     rcx, [rsp+68h+arg_58]; unsigned __int16 *
0x180023bc5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023bca  jmp     short loc_180023BDF
0x180023bcc  mov     eax, 80004005h
0x180023bd1  jmp     short loc_180023BDF
0x180023bd3  mov     eax, 80070490h
0x180023bd8  jmp     short loc_180023BDF
0x180023bda  mov     eax, 8007000Eh
0x180023bdf  mov     rbx, [rsp+68h+arg_0]
0x180023be4  mov     rsi, [rsp+68h+arg_8]
0x180023be9  add     rsp, 40h
0x180023bed  pop     r15
0x180023bef  pop     r14
0x180023bf1  pop     r13
0x180023bf3  pop     r12
0x180023bf5  pop     rdi
0x180023bf6  retn
```
