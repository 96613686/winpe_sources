# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x1800091c0`
- end: `0x1800093bf`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `511`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a30c`

## callees

- `0x1800091c0`
- `0x18000d48c`
- `0x1800136c4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009226`
- `msvcrt!_wcsicmp` at `0x18000924f`
- `msvcrt!_wcsicmp` at `0x180009274`
- `msvcrt!_wcsicmp` at `0x18000929d`
- `msvcrt!_wcsicmp` at `0x180009226`
- `msvcrt!_wcsicmp` at `0x18000924f`
- `msvcrt!_wcsicmp` at `0x180009274`
- `msvcrt!_wcsicmp` at `0x18000929d`

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
        unsigned __int16 *a12,
        unsigned int a13)
{
  __int64 v15; // rdi
  __int64 v16; // rbx
  char v17; // r12
  __int64 v18; // r15
  __int64 *v19; // r14
  __int64 *v20; // rsi
  bool v21; // zf
  __int64 *v22; // rsi
  struct EMBEDDED_PDB_INFORMATION *v23; // rcx
  const unsigned __int16 *v24; // r8
  __int64; // rax
  int v26; // [rsp+70h] [rbp+18h] BYREF
  unsigned int *v27; // [rsp+78h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  LODWORD(v15) = 0;
  v16 = 0;
  v17 = 0;
  *a11 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( a3 )
    {
      v18 = (__int64)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
                       (__int64)this + 24,
                       (unsigned int *)&v26);
      v19 = *(__int64 **)(v18 + 8);
      v20 = (__int64 *)v19[1];
      while ( !*((_BYTE *)v20 + 41) )
      {
        if ( _wcsicmp((const wchar_t *)v20[3], a2) >= 0 )
        {
          v19 = v20;
          v20 = (__int64 *)*v20;
        }
        else
        {
          v20 = (__int64 *)v20[2];
        }
      }
      if ( v19 == *(__int64 **)(v18 + 8) || _wcsicmp(a2, (const wchar_t *)v19[3]) < 0 )
        v19 = *(__int64 **)(v18 + 8);
      v21 = v19 == *(__int64 **)(v18 + 8);
    }
    else
    {
      v19 = (__int64 *)*((_QWORD *)this + 7);
      v22 = (__int64 *)v19[1];
      while ( !*((_BYTE *)v22 + 41) )
      {
        if ( _wcsicmp((const wchar_t *)v22[3], a2) >= 0 )
        {
          v19 = v22;
          v22 = (__int64 *)*v22;
        }
        else
        {
          v22 = (__int64 *)v22[2];
        }
      }
      if ( v19 == *((__int64 **)this + 7) || _wcsicmp(a2, (const wchar_t *)v19[3]) < 0 )
        v19 = (__int64 *)*((_QWORD *)this + 7);
      v21 = v19 == *((__int64 **)this + 7);
    }
    if ( !v21 )
    {
      v17 = 1;
      v16 = v19[4];
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
    {
       = 2147942414LL;
      __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_1800093A2);
      return ;
    }
  }
  if ( !v17 )
    return 2147943568LL;
  if ( !v16 )
    return 2147500037LL;
  *v27 = *(_DWORD *)(v16 + 80);
  *a5 = *(const union _CVDD **)(v16 + 88);
  *a6 = *(const unsigned int **)(v16 + 96);
  if ( a7 )
    *a7 = *(const struct CODEVIEW_INFORMATION_1 **)(v16 + 104);
  *a8 = *(_DWORD *)(v16 + 156);
  *a9 = *(_DWORD *)(v16 + 160);
  if ( *(_QWORD *)(v16 + 120) )
    v15 = *(_QWORD *)(v16 + 128) - *(_QWORD *)(v16 + 120);
  v23 = a10;
  *(_DWORD *)a10 = v15;
  *((_QWORD *)v23 + 1) = *(_QWORD *)(v16 + 120);
  *((_WORD *)v23 + 8) = *(_WORD *)(v16 + 146);
  *((_WORD *)v23 + 9) = *(_WORD *)(v16 + 144);
  *a11 = *(_BYTE *)(v16 + 148);
  if ( *(_QWORD *)(v16 + 72) < 8u )
    v24 = (const unsigned __int16 *)(v16 + 48);
  else
    v24 = *(const unsigned __int16 **)(v16 + 48);
  return StringCchCopyW(a12, 0x30Cu, v24);
}

```

## disassembly

```asm
0x1800091c0  mov     r11, rsp
0x1800091c3  mov     [r11+20h], r9
0x1800091c7  mov     [r11+18h], r8d
0x1800091cb  push    rdi
0x1800091cc  push    r12
0x1800091ce  push    r13
0x1800091d0  push    r14
0x1800091d2  push    r15
0x1800091d4  sub     rsp, 30h
0x1800091d8  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1800091e0  mov     [r11+8], rbx
0x1800091e4  mov     [r11+10h], rsi
0x1800091e8  mov     r13, rdx
0x1800091eb  mov     r15, rcx
0x1800091ee  xor     edi, edi
0x1800091f0  mov     ebx, edi
0x1800091f2  mov     r12b, dil
0x1800091f5  mov     rax, [rsp+58h+arg_50]
0x1800091fd  mov     [rax], dil
0x180009200  test    r8d, r8d
0x180009203  jz      short loc_180009263
0x180009205  add     rcx, 18h
0x180009209  lea     rdx, [r11+18h]
0x18000920d  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180009212  mov     r15, rax
0x180009215  mov     r14, [rax+8]
0x180009219  mov     rsi, [r14+8]
0x18000921d  jmp     short loc_18000923C
0x18000921f  mov     rdx, r13; String2
0x180009222  mov     rcx, [rsi+18h]; String1
0x180009226  call    cs:__imp__wcsicmp
0x18000922c  test    eax, eax
0x18000922e  jns     short loc_180009236
0x180009230  mov     rsi, [rsi+10h]
0x180009234  jmp     short loc_18000923C
0x180009236  mov     r14, rsi
0x180009239  mov     rsi, [rsi]
0x18000923c  cmp     [rsi+29h], dil
0x180009240  jz      short loc_18000921F
0x180009242  cmp     r14, [r15+8]
0x180009246  jz      short loc_180009259
0x180009248  mov     rdx, [r14+18h]; String2
0x18000924c  mov     rcx, r13; String1
0x18000924f  call    cs:__imp__wcsicmp
0x180009255  test    eax, eax
0x180009257  jns     short loc_18000925D
0x180009259  mov     r14, [r15+8]
0x18000925d  cmp     r14, [r15+8]
0x180009261  jmp     short loc_1800092AF
0x180009263  mov     r14, [rcx+38h]
0x180009267  mov     rsi, [r14+8]
0x18000926b  jmp     short loc_18000928A
0x18000926d  mov     rdx, r13; String2
0x180009270  mov     rcx, [rsi+18h]; String1
0x180009274  call    cs:__imp__wcsicmp
0x18000927a  test    eax, eax
0x18000927c  jns     short loc_180009284
0x18000927e  mov     rsi, [rsi+10h]
0x180009282  jmp     short loc_18000928A
0x180009284  mov     r14, rsi
0x180009287  mov     rsi, [rsi]
0x18000928a  cmp     [rsi+29h], dil
0x18000928e  jz      short loc_18000926D
0x180009290  cmp     r14, [r15+38h]
0x180009294  jz      short loc_1800092A7
0x180009296  mov     rdx, [r14+18h]; String2
0x18000929a  mov     rcx, r13; String1
0x18000929d  call    cs:__imp__wcsicmp
0x1800092a3  test    eax, eax
0x1800092a5  jns     short loc_1800092AB
0x1800092a7  mov     r14, [r15+38h]
0x1800092ab  cmp     r14, [r15+38h]
0x1800092af  jz      short loc_1800092B8
0x1800092b1  mov     r12b, 1
0x1800092b4  mov     rbx, [r14+20h]
0x1800092b8  test    r12b, r12b
0x1800092bb  jz      loc_18000939B
0x1800092c1  test    rbx, rbx
0x1800092c4  jz      loc_180009394
0x1800092ca  mov     eax, [rbx+50h]
0x1800092cd  mov     rcx, [rsp+58h+arg_18]
0x1800092d2  mov     [rcx], eax
0x1800092d4  mov     rcx, [rbx+58h]
0x1800092d8  mov     rax, [rsp+58h+arg_20]
0x1800092e0  mov     [rax], rcx
0x1800092e3  mov     rcx, [rbx+60h]
0x1800092e7  mov     rax, [rsp+58h+arg_28]
0x1800092ef  mov     [rax], rcx
0x1800092f2  mov     rcx, [rsp+58h+arg_30]
0x1800092fa  test    rcx, rcx
0x1800092fd  jz      short loc_180009306
0x1800092ff  mov     rax, [rbx+68h]
0x180009303  mov     [rcx], rax
0x180009306  mov     ecx, [rbx+9Ch]
0x18000930c  mov     rax, [rsp+58h+arg_38]
0x180009314  mov     [rax], ecx
0x180009316  mov     ecx, [rbx+0A0h]
0x18000931c  mov     rax, [rsp+58h+arg_40]
0x180009324  mov     [rax], ecx
0x180009326  cmp     [rbx+78h], rdi
0x18000932a  jz      short loc_180009337
0x18000932c  mov     rdi, [rbx+80h]
0x180009333  sub     rdi, [rbx+78h]
0x180009337  mov     rcx, [rsp+58h+arg_48]
0x18000933f  mov     [rcx], edi
0x180009341  mov     rax, [rbx+78h]
0x180009345  mov     [rcx+8], rax
0x180009349  movzx   eax, word ptr [rbx+92h]
0x180009350  mov     [rcx+10h], ax
0x180009354  movzx   eax, word ptr [rbx+90h]
0x18000935b  mov     [rcx+12h], ax
0x18000935f  mov     al, [rbx+94h]
0x180009365  mov     rcx, [rsp+58h+arg_50]
0x18000936d  mov     [rcx], al
0x18000936f  cmp     qword ptr [rbx+48h], 8
0x180009374  jb      short loc_18000937C
0x180009376  mov     r8, [rbx+30h]
0x18000937a  jmp     short loc_180009380
0x18000937c  lea     r8, [rbx+30h]; unsigned __int16 *
0x180009380  mov     edx, 30Ch; unsigned __int64
0x180009385  mov     rcx, [rsp+58h+arg_58]; unsigned __int16 *
0x18000938d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009392  jmp     short loc_1800093A7
0x180009394  mov     eax, 80004005h
0x180009399  jmp     short loc_1800093A7
0x18000939b  mov     eax, 80070490h
0x1800093a0  jmp     short loc_1800093A7
0x1800093a2  mov     eax, 8007000Eh
0x1800093a7  mov     rbx, [rsp+58h+arg_0]
0x1800093ac  mov     rsi, [rsp+58h+arg_8]
0x1800093b1  add     rsp, 30h
0x1800093b5  pop     r15
0x1800093b7  pop     r14
0x1800093b9  pop     r13
0x1800093bb  pop     r12
0x1800093bd  pop     rdi
0x1800093be  retn
```
