# ShowDialog(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,bool,ushort *,int)

- ea: `0x18000b640`
- end: `0x18000ba95`
- name: `?ShowDialog@@YAJPEAUHWND__@@PEBG1111111K_NPEAGH@Z`
- size: `1109`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, bool, unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c450`
- `0x18000c4b0`
- `0x18000c540`
- `0x18000c5a0`
- `0x18000c630`
- `0x18000c690`

## callees

- `0x18000208c`
- `0x180002db8`
- `0x1800054a4`
- `0x180007150`
- `0x18000b2f4`
- `0x18000b554`
- `0x18000b640`
- `0x18000ba9c`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000ba0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000ba0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b90f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b98c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b90f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b98c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b66f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b66f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba2c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ShowDialog(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned int a10,
        bool a11,
        unsigned __int16 *a12,
        int a13)
{
  HWND v16; // r12
  HRESULT v17; // eax
  char *v18; // rax
  char *v19; // rdi
  void **v20; // rcx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rdx
  char *v23; // r12
  __int64 v24; // rbx
  __int64 v25; // r8
  void **v26; // rcx
  unsigned __int64 v27; // rdx
  char *v28; // r14
  __int64 v29; // rbx
  void **v30; // rcx
  unsigned __int64 v31; // rdx
  char *v32; // r14
  __int64 v33; // rbx
  void **v34; // rcx
  void *v35; // r14
  HRESULT Instance; // eax
  bool v37; // bl
  struct IFileDialog *v38; // rcx
  HRESULT v39; // eax
  struct IFileDialog *v40; // rcx
  const char *v41; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  int ppvb; // [rsp+20h] [rbp-58h]
  struct IFileDialog *v46; // [rsp+30h] [rbp-48h] BYREF
  char *v47; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v16 = a1;
  v17 = CoInitializeEx(0, 2u);
  try
  {
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
        (const char *)(unsigned int)v17,
        ppv);
    v18 = (char *)operator new(0xF0u);
    v19 = v18;
    *(_OWORD *)(v18 + 8) = 0;
    *((_QWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 4) = 7;
    *((_WORD *)v18 + 4) = 0;
    *(_OWORD *)(v18 + 40) = 0;
    *((_QWORD *)v18 + 7) = 0;
    *((_QWORD *)v18 + 8) = 7;
    *((_WORD *)v18 + 20) = 0;
    *(_OWORD *)(v18 + 72) = 0;
    *((_QWORD *)v18 + 11) = 0;
    *((_QWORD *)v18 + 12) = 7;
    *((_WORD *)v18 + 36) = 0;
    *(_OWORD *)(v18 + 104) = 0;
    *((_QWORD *)v18 + 15) = 0;
    *((_QWORD *)v18 + 16) = 7;
    *((_WORD *)v18 + 52) = 0;
    *(_OWORD *)(v18 + 136) = 0;
    *((_QWORD *)v18 + 19) = 0;
    *((_QWORD *)v18 + 20) = 7;
    *((_WORD *)v18 + 68) = 0;
    *(_OWORD *)(v18 + 168) = 0;
    *((_QWORD *)v18 + 23) = 0;
    *((_QWORD *)v18 + 24) = 7;
    *((_WORD *)v18 + 84) = 0;
    *(_OWORD *)(v18 + 200) = 0;
    *((_QWORD *)v18 + 27) = 0;
    *((_QWORD *)v18 + 28) = 7;
    *((_WORD *)v18 + 100) = 0;
    v47 = v18;
    v20 = (void **)(v18 + 8);
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( a2[v22] );
    if ( v22 > *((_QWORD *)v18 + 4) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v20, v22, 7, a2);
    }
    else
    {
      if ( *((_QWORD *)v18 + 4) <= 7u )
        v23 = v18 + 8;
      else
        v23 = (char *)*v20;
      *((_QWORD *)v18 + 3) = v22;
      v24 = 2 * v22;
      memmove_0(v23, a2, 2 * v22);
      *(_WORD *)&v23[v24] = 0;
      v16 = a1;
    }
    v19[4] = !a2 || !*a2;
    if ( a3 && *a3 )
    {
      v26 = (void **)(v19 + 40);
      v27 = -1;
      do
        ++v27;
      while ( a3[v27] );
      if ( v27 > *((_QWORD *)v19 + 8) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v26,
          v27,
          v25,
          a3);
      }
      else
      {
        if ( *((_QWORD *)v19 + 8) <= 7u )
          v28 = v19 + 40;
        else
          v28 = (char *)*v26;
        *((_QWORD *)v19 + 7) = v27;
        v29 = 2 * v27;
        memmove_0(v28, a3, 2 * v27);
        *(_WORD *)&v28[v29] = 0;
      }
    }
    if ( a4 && *a4 )
      RemoteFileBrowseClient::SetFilter((RemoteFileBrowseClient *)v19, a4);
    if ( Src && *Src )
    {
      v30 = (void **)(v19 + 168);
      v31 = -1;
      do
        ++v31;
      while ( Src[v31] );
      if ( v31 > *((_QWORD *)v19 + 24) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v30,
          v31,
          v25,
          Src);
      }
      else
      {
        if ( *((_QWORD *)v19 + 24) <= 7u )
          v32 = v19 + 168;
        else
          v32 = (char *)*v30;
        *((_QWORD *)v19 + 23) = v31;
        v33 = 2 * v31;
        memmove_0(v32, Src, 2 * v31);
        *(_WORD *)&v32[v33] = 0;
      }
    }
    if ( a6 && *a6 )
    {
      v34 = (void **)(v19 + 200);
      do
        ++v21;
      while ( a6[v21] );
      if ( v21 > *((_QWORD *)v19 + 28) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v34,
          v21,
          v25,
          a6);
      }
      else
      {
        if ( *((_QWORD *)v19 + 28) <= 7u )
          v35 = v19 + 200;
        else
          v35 = *v34;
        *((_QWORD *)v19 + 27) = v21;
        memmove_0(v35, a6, 2 * v21);
        *((_WORD *)v35 + v21) = 0;
      }
    }
    *((_QWORD *)v19 + 29) = v16;
    *(_DWORD *)v19 = a10;
    v46 = 0;
    if ( a10 == 2 )
    {
      Instance = CoCreateInstance(
                   &GUID_c0b4e2f3_ba21_4773_8dba_335ec946eb8b,
                   0,
                   0x17u,
                   &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab,
                   (LPVOID *)&v46);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B4,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
      v37 = RemoteFileBrowseClient::ShowFileDialog((RemoteFileBrowseClient *)v19, v46, a7, a8, a9);
      v38 = v46;
      if ( v46 )
      {
        v46 = 0;
        ((void (__fastcall *)(struct IFileDialog *))v38->lpVtbl->Release)(v38);
      }
    }
    else
    {
      v39 = CoCreateInstance(
              &GUID_dc1c5a9c_e88a_4dde_a5a1_60f82a20aef7,
              0,
              0x17u,
              &GUID_d57c7288_d4ad_4768_be02_9d969532d960,
              (LPVOID *)&v46);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x28D,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
          (const char *)(unsigned int)v39,
          ppvb);
      v37 = RemoteFileBrowseClient::ShowFileDialog((RemoteFileBrowseClient *)v19, v46, a7, a8, a9);
      v40 = v46;
      if ( v46 )
      {
        v46 = 0;
        ((void (__fastcall *)(struct IFileDialog *))v40->lpVtbl->Release)(v40);
      }
    }
    if ( v37 )
      _o_wcscpy_s(a12, a13);
    else
      *a12 = 0;
    std::unique_ptr<RemoteFileBrowseClient>::~unique_ptr<RemoteFileBrowseClient>(&v47);
    CoUninitialize();
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9E,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\remotefilebrowseclient.cpp",
                           v41);
  }
  return result;
}

```

## disassembly

```asm
0x18000b640  mov     [rsp+arg_8], rbx
0x18000b645  mov     [rsp+arg_10], rsi
0x18000b64a  mov     [rsp+arg_0], rcx
0x18000b64f  push    rdi
0x18000b650  push    r12
0x18000b652  push    r13
0x18000b654  push    r14
0x18000b656  push    r15
0x18000b658  sub     rsp, 50h
0x18000b65c  mov     r13, r9
0x18000b65f  mov     r15, r8
0x18000b662  mov     r14, rdx
0x18000b665  mov     r12, rcx
0x18000b668  xor     ebx, ebx
0x18000b66a  lea     edx, [rbx+2]; dwCoInit
0x18000b66d  xor     ecx, ecx; pvReserved
0x18000b66f  call    cs:__imp_CoInitializeEx
0x18000b675  mov     rcx, [rsp+78h]; this
0x18000b67a  test    eax, eax
0x18000b67c  js      loc_18000BA57
0x18000b682  mov     ecx, 0F0h; Size
0x18000b687  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b68c  mov     rdi, rax
0x18000b68f  xorps   xmm0, xmm0
0x18000b692  movups  xmmword ptr [rax+8], xmm0
0x18000b696  mov     [rax+18h], rbx
0x18000b69a  mov     r8d, 7
0x18000b6a0  mov     [rax+20h], r8
0x18000b6a4  mov     [rax+8], bx
0x18000b6a8  movups  xmmword ptr [rax+28h], xmm0
0x18000b6ac  mov     [rax+38h], rbx
0x18000b6b0  mov     [rax+40h], r8
0x18000b6b4  mov     [rax+28h], bx
0x18000b6b8  movups  xmmword ptr [rax+48h], xmm0
0x18000b6bc  mov     [rax+58h], rbx
0x18000b6c0  mov     [rax+60h], r8
0x18000b6c4  mov     [rax+48h], bx
0x18000b6c8  movups  xmmword ptr [rax+68h], xmm0
0x18000b6cc  mov     [rax+78h], rbx
0x18000b6d0  mov     [rax+80h], r8
0x18000b6d7  mov     [rax+68h], bx
0x18000b6db  movups  xmmword ptr [rax+88h], xmm0
0x18000b6e2  mov     [rax+98h], rbx
0x18000b6e9  mov     [rax+0A0h], r8
0x18000b6f0  mov     [rax+88h], bx
0x18000b6f7  movups  xmmword ptr [rax+0A8h], xmm0
0x18000b6fe  mov     [rax+0B8h], rbx
0x18000b705  mov     [rax+0C0h], r8
0x18000b70c  mov     [rax+0A8h], bx
0x18000b713  movups  xmmword ptr [rax+0C8h], xmm0
0x18000b71a  mov     [rax+0D8h], rbx
0x18000b721  mov     [rax+0E0h], r8
0x18000b728  mov     [rax+0C8h], bx
0x18000b72f  mov     [rsp+78h+var_40], rax
0x18000b734  lea     rcx, [rax+8]
0x18000b738  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b73c  mov     rdx, rsi
0x18000b73f  inc     rdx
0x18000b742  cmp     [r14+rdx*2], bx
0x18000b747  jnz     short loc_18000B73F
0x18000b749  cmp     rdx, [rcx+18h]
0x18000b74d  ja      short loc_18000B786
0x18000b74f  cmp     [rcx+18h], r8
0x18000b753  jbe     short loc_18000B75A
0x18000b755  mov     r12, [rcx]
0x18000b758  jmp     short loc_18000B75D
0x18000b75a  mov     r12, rcx
0x18000b75d  mov     [rcx+10h], rdx
0x18000b761  lea     rbx, [rdx+rdx]
0x18000b765  mov     r8, rbx; Size
0x18000b768  mov     rdx, r14; Src
0x18000b76b  mov     rcx, r12; void *
0x18000b76e  call    memmove_0
0x18000b773  xor     eax, eax
0x18000b775  mov     [r12+rbx], ax
0x18000b77a  mov     r12, [rsp+78h+arg_0]
0x18000b782  xor     ebx, ebx
0x18000b784  jmp     short loc_18000B78E
0x18000b786  mov     r9, r14
0x18000b789  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000b78e  test    r14, r14
0x18000b791  jz      short loc_18000B79E
0x18000b793  cmp     [r14], bx
0x18000b797  jz      short loc_18000B79E
0x18000b799  mov     [rdi+4], bl
0x18000b79c  jmp     short loc_18000B7A2
0x18000b79e  mov     byte ptr [rdi+4], 1
0x18000b7a2  test    r15, r15
0x18000b7a5  jz      short loc_18000B7FC
0x18000b7a7  cmp     [r15], bx
0x18000b7ab  jz      short loc_18000B7FC
0x18000b7ad  lea     rcx, [rdi+28h]
0x18000b7b1  mov     rdx, rsi
0x18000b7b4  inc     rdx
0x18000b7b7  cmp     [r15+rdx*2], bx
0x18000b7bc  jnz     short loc_18000B7B4
0x18000b7be  cmp     rdx, [rcx+18h]
0x18000b7c2  ja      short loc_18000B7F4
0x18000b7c4  cmp     qword ptr [rcx+18h], 7
0x18000b7c9  jbe     short loc_18000B7D0
0x18000b7cb  mov     r14, [rcx]
0x18000b7ce  jmp     short loc_18000B7D3
0x18000b7d0  mov     r14, rcx
0x18000b7d3  mov     [rcx+10h], rdx
0x18000b7d7  lea     rbx, [rdx+rdx]
0x18000b7db  mov     r8, rbx; Size
0x18000b7de  mov     rdx, r15; Src
0x18000b7e1  mov     rcx, r14; void *
0x18000b7e4  call    memmove_0
0x18000b7e9  xor     eax, eax
0x18000b7eb  mov     [r14+rbx], ax
0x18000b7f0  xor     ebx, ebx
0x18000b7f2  jmp     short loc_18000B7FC
0x18000b7f4  mov     r9, r15
0x18000b7f7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000b7fc  test    r13, r13
0x18000b7ff  jz      short loc_18000B813
0x18000b801  cmp     [r13+0], bx
0x18000b806  jz      short loc_18000B813
0x18000b808  mov     rdx, r13; unsigned __int16 *
0x18000b80b  mov     rcx, rdi; this
0x18000b80e  call    ?SetFilter@RemoteFileBrowseClient@@QEAAXPEBG@Z; RemoteFileBrowseClient::SetFilter(ushort const *)
0x18000b813  mov     r9, [rsp+78h+Src]
0x18000b81b  test    r9, r9
0x18000b81e  jz      short loc_18000B875
0x18000b820  cmp     [r9], bx
0x18000b824  jz      short loc_18000B875
0x18000b826  lea     rcx, [rdi+0A8h]
0x18000b82d  mov     rdx, rsi
0x18000b830  inc     rdx
0x18000b833  cmp     [r9+rdx*2], bx
0x18000b838  jnz     short loc_18000B830
0x18000b83a  cmp     rdx, [rcx+18h]
0x18000b83e  ja      short loc_18000B870
0x18000b840  cmp     qword ptr [rcx+18h], 7
0x18000b845  jbe     short loc_18000B84C
0x18000b847  mov     r14, [rcx]
0x18000b84a  jmp     short loc_18000B84F
0x18000b84c  mov     r14, rcx
0x18000b84f  mov     [rcx+10h], rdx
0x18000b853  lea     rbx, [rdx+rdx]
0x18000b857  mov     r8, rbx; Size
0x18000b85a  mov     rdx, r9; Src
0x18000b85d  mov     rcx, r14; void *
0x18000b860  call    memmove_0
0x18000b865  xor     eax, eax
0x18000b867  mov     [r14+rbx], ax
0x18000b86c  xor     ebx, ebx
0x18000b86e  jmp     short loc_18000B875
0x18000b870  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000b875  mov     r9, [rsp+78h+arg_28]
0x18000b87d  test    r9, r9
0x18000b880  jz      short loc_18000B8D7
0x18000b882  cmp     [r9], bx
0x18000b886  jz      short loc_18000B8D7
0x18000b888  lea     rcx, [rdi+0C8h]
0x18000b88f  inc     rsi
0x18000b892  cmp     [r9+rsi*2], bx
0x18000b897  jnz     short loc_18000B88F
0x18000b899  cmp     rsi, [rcx+18h]
0x18000b89d  ja      short loc_18000B8CF
0x18000b89f  cmp     qword ptr [rcx+18h], 7
0x18000b8a4  jbe     short loc_18000B8AB
0x18000b8a6  mov     r14, [rcx]
0x18000b8a9  jmp     short loc_18000B8AE
0x18000b8ab  mov     r14, rcx
0x18000b8ae  mov     [rcx+10h], rsi
0x18000b8b2  lea     rbx, [rsi+rsi]
0x18000b8b6  mov     r8, rbx; Size
0x18000b8b9  mov     rdx, r9; Src
0x18000b8bc  mov     rcx, r14; void *
0x18000b8bf  call    memmove_0
0x18000b8c4  xor     eax, eax
0x18000b8c6  mov     [r14+rbx], ax
0x18000b8cb  xor     ebx, ebx
0x18000b8cd  jmp     short loc_18000B8D7
0x18000b8cf  mov     rdx, rsi
0x18000b8d2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000b8d7  mov     [rdi+0E8h], r12
0x18000b8de  mov     eax, [rsp+78h+arg_48]
0x18000b8e5  mov     [rdi], eax
0x18000b8e7  mov     [rsp+78h+var_48], rbx
0x18000b8ec  cmp     eax, 2
0x18000b8ef  jnz     short loc_18000B96E
0x18000b8f1  lea     rax, [rsp+78h+var_48]
0x18000b8f6  mov     qword ptr [rsp+78h+ppv], rax; int
0x18000b8fb  lea     r9, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab; riid
0x18000b902  xor     edx, edx; pUnkOuter
0x18000b904  lea     r8d, [rdx+17h]; dwClsContext
0x18000b908  lea     rcx, _GUID_c0b4e2f3_ba21_4773_8dba_335ec946eb8b; rclsid
0x18000b90f  call    cs:__imp_CoCreateInstance
0x18000b915  mov     rcx, [rsp+78h]; this
0x18000b91a  test    eax, eax
0x18000b91c  js      loc_18000BA6A
0x18000b922  mov     rax, [rsp+78h+arg_40]
0x18000b92a  mov     qword ptr [rsp+78h+ppv], rax; unsigned __int16 *
0x18000b92f  mov     r9, [rsp+78h+arg_38]; unsigned __int16 *
0x18000b937  mov     r8, [rsp+78h+arg_30]; unsigned __int16 *
0x18000b93f  mov     rdx, [rsp+78h+var_48]; struct IFileDialog *
0x18000b944  mov     rcx, rdi; this
0x18000b947  call    ?ShowFileDialog@RemoteFileBrowseClient@@AEAA_NPEAUIFileDialog@@PEBG11@Z; RemoteFileBrowseClient::ShowFileDialog(IFileDialog *,ushort const *,ushort const *,ushort const *)
0x18000b94c  mov     bl, al
0x18000b94e  mov     rcx, [rsp+78h+var_48]
0x18000b953  xor     esi, esi
0x18000b955  test    rcx, rcx
0x18000b958  jz      short loc_18000B96C
0x18000b95a  mov     [rsp+78h+var_48], rsi
0x18000b95f  mov     rdx, [rcx]
0x18000b962  mov     rax, [rdx+10h]
0x18000b966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b96b  nop
0x18000b96c  jmp     short loc_18000B9E9
0x18000b96e  lea     rax, [rsp+78h+var_48]
0x18000b973  mov     qword ptr [rsp+78h+ppv], rax; int
0x18000b978  lea     r9, _GUID_d57c7288_d4ad_4768_be02_9d969532d960; riid
0x18000b97f  xor     edx, edx; pUnkOuter
0x18000b981  lea     r8d, [rdx+17h]; dwClsContext
0x18000b985  lea     rcx, _GUID_dc1c5a9c_e88a_4dde_a5a1_60f82a20aef7; rclsid
0x18000b98c  call    cs:__imp_CoCreateInstance
0x18000b992  mov     rcx, [rsp+78h]; this
0x18000b997  test    eax, eax
0x18000b999  js      loc_18000BA7F
0x18000b99f  mov     rax, [rsp+78h+arg_40]
0x18000b9a7  mov     qword ptr [rsp+78h+ppv], rax; unsigned __int16 *
0x18000b9ac  mov     r9, [rsp+78h+arg_38]; unsigned __int16 *
0x18000b9b4  mov     r8, [rsp+78h+arg_30]; unsigned __int16 *
0x18000b9bc  mov     rdx, [rsp+78h+var_48]; struct IFileDialog *
0x18000b9c1  mov     rcx, rdi; this
0x18000b9c4  call    ?ShowFileDialog@RemoteFileBrowseClient@@AEAA_NPEAUIFileDialog@@PEBG11@Z; RemoteFileBrowseClient::ShowFileDialog(IFileDialog *,ushort const *,ushort const *,ushort const *)
0x18000b9c9  mov     bl, al
0x18000b9cb  mov     rcx, [rsp+78h+var_48]
0x18000b9d0  xor     esi, esi
0x18000b9d2  test    rcx, rcx
0x18000b9d5  jz      short loc_18000B9E9
0x18000b9d7  mov     [rsp+78h+var_48], rsi
0x18000b9dc  mov     rax, [rcx]
0x18000b9df  mov     rax, [rax+10h]
0x18000b9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e8  nop
0x18000b9e9  test    bl, bl
0x18000b9eb  jz      short loc_18000BA16
0x18000b9ed  lea     r8, [rdi+88h]
0x18000b9f4  cmp     qword ptr [r8+18h], 7
0x18000b9f9  jbe     short loc_18000B9FE
0x18000b9fb  mov     r8, [r8]
0x18000b9fe  movsxd  rdx, [rsp+78h+arg_60]
0x18000ba06  mov     rcx, [rsp+78h+arg_58]
0x18000ba0e  call    cs:__imp__o_wcscpy_s
0x18000ba14  jmp     short loc_18000BA21
0x18000ba16  mov     rax, [rsp+78h+arg_58]
0x18000ba1e  mov     [rax], si
0x18000ba21  lea     rcx, [rsp+78h+var_40]
0x18000ba26  call    ??1?$unique_ptr@VRemoteFileBrowseClient@@U?$default_delete@VRemoteFileBrowseClient@@@std@@@std@@QEAA@XZ; std::unique_ptr<RemoteFileBrowseClient>::~unique_ptr<RemoteFileBrowseClient>(void)
0x18000ba2b  nop
0x18000ba2c  call    cs:__imp_CoUninitialize
0x18000ba32  xor     eax, eax
0x18000ba34  jmp     short loc_18000BA3D
0x18000ba36  mov     eax, dword ptr [rsp+78h+arg_50]
0x18000ba3d  lea     r11, [rsp+78h+var_28]
0x18000ba42  mov     rbx, [r11+38h]
0x18000ba46  mov     rsi, [r11+40h]
0x18000ba4a  mov     rsp, r11
0x18000ba4d  pop     r15
0x18000ba4f  pop     r14
0x18000ba51  pop     r13
0x18000ba53  pop     r12
0x18000ba55  pop     rdi
0x18000ba56  retn
0x18000ba57  mov     r9d, eax; char *
0x18000ba5a  lea     r8, aVmUxUiRemotefi_5; "vm\\ux\\ui\\remotefilebrowse\\remotefil"...
0x18000ba61  lea     edx, [rbx+25h]; void *
0x18000ba64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ba6a  mov     r9d, eax; char *
0x18000ba6d  lea     r8, aVmUxUiRemotefi_5; "vm\\ux\\ui\\remotefilebrowse\\remotefil"...
0x18000ba74  mov     edx, 2B4h; void *
0x18000ba79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ba7f  mov     r9d, eax; char *
0x18000ba82  lea     r8, aVmUxUiRemotefi_5; "vm\\ux\\ui\\remotefilebrowse\\remotefil"...
0x18000ba89  mov     edx, 28Dh; void *
0x18000ba8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
