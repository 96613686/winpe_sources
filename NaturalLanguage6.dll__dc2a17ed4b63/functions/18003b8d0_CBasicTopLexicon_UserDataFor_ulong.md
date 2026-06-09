# CBasicTopLexicon::UserDataFor(ulong)

- ea: `0x18003b8d0`
- end: `0x18003bce5`
- name: `?UserDataFor@CBasicTopLexicon@@UEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@K@Z`
- size: `1045`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180003edc`
- `0x180005160`
- `0x180009790`
- `0x18001a0d8`
- `0x180035640`
- `0x18003757c`
- `0x18003b8d0`
- `0x18003bcec`
- `0x18003ed6c`
- `0x18006b08c`
- `0x18006b554`
- `0x18006c154`
- `0x18006fa80`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall CBasicTopLexicon::UserDataFor(__int64 a1, __int64 *a2, unsigned int a3)
{
  __int64 *v4; // rsi
  __int64 v6; // rcx
  int v7; // r10d
  __int64 v8; // rcx
  int *v9; // rbx
  int i; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // edi
  unsigned int v13; // eax
  ByteSliceManager *v14; // r10
  unsigned __int8 *v15; // r11
  unsigned int FreeBlock; // eax
  __int64 v17; // r10
  __int64 v18; // r11
  unsigned __int8 *v19; // r9
  unsigned __int8 v20; // dl
  __int64 v21; // r14
  __int64 v22; // rdi
  __int64 v23; // rbx
  unsigned int v24; // ecx
  unsigned int v25; // r13d
  unsigned int *v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // edx
  __int64 v30; // rdx
  int v31; // r13d
  int v32; // esi
  __int64 *v33; // rax
  __int64 v34; // r12
  __int64 *v35; // rcx
  __int64 v36; // r12
  __int64 v37; // r12
  __int64 v39; // [rsp+28h] [rbp-79h] BYREF
  __int64 v40; // [rsp+30h] [rbp-71h] BYREF
  int v41; // [rsp+38h] [rbp-69h] BYREF
  __int64 v42; // [rsp+40h] [rbp-61h] BYREF
  __int64 v43; // [rsp+48h] [rbp-59h] BYREF
  void **v44; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v45; // [rsp+60h] [rbp-41h]
  ByteSliceManager *v46; // [rsp+68h] [rbp-39h]
  __int64 v47; // [rsp+70h] [rbp-31h] BYREF
  char v48; // [rsp+78h] [rbp-29h]
  __int64 v49; // [rsp+80h] [rbp-21h]
  _BYTE pExceptionObject[112]; // [rsp+88h] [rbp-19h] BYREF
  const void *retaddr; // [rsp+100h] [rbp+5Fh]
  unsigned __int8 v53; // [rsp+118h] [rbp+77h] BYREF
  volatile signed __int32 *v54; // [rsp+120h] [rbp+7Fh] BYREF

  v49 = -2;
  v4 = a2;
  LODWORD(v39) = 0;
  if ( a3
    && a3 <= NLG::CCompressedTrie::GetCWords((NLG::CCompressedTrie *)(*(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 120) + 48LL)
                                                                             + 4LL)
                                                                    + *(_QWORD *)(a1 + 120)
                                                                    + 48LL))
    && (v6 = *(_QWORD *)(a1 + 168), *(_DWORD *)(v6 + 8) > (unsigned int)*(unsigned __int8 *)(v6 + 36)) )
  {
    (*(void (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v6 + 56LL))(v6, &v41, a3);
    v7 = 0xFFFFFF;
    if ( (v41 & 0xFFFFFF) != 0 )
    {
      v8 = v41 & 0xFFFFFF;
      v9 = (int *)(v8 + *(_QWORD *)(*(_QWORD *)(a1 + 176) + 16LL));
      if ( v9 )
      {
        v47 = v8 + *(_QWORD *)(*(_QWORD *)(a1 + 176) + 16LL);
        v48 = 0;
        for ( i = *v9; ; i = *(_DWORD *)Indexes<EntryIndex>::Next(&v47, &v53) )
        {
          if ( !i )
            goto LABEL_57;
          if ( (i & 0xF000000) == 0x7000000 )
            break;
        }
        v11 = v7 & i;
        if ( !v11 )
          goto LABEL_57;
        HIDWORD(v39) = 0;
        v12 = *(_DWORD *)(a1 + 144) - 1;
        v13 = a3
            / (unsigned int)(NLG::CCompressedTrie::GetCWords((NLG::CCompressedTrie *)(*(_QWORD *)(a1 + 120)
                                                                                    + 48LL
                                                                                    + *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 120) + 48LL)
                                                                                             + 4LL)))
                           / *(__int64 *)(a1 + 144));
        if ( v13 >= v12 )
          LOWORD(v13) = v12;
        HIDWORD(v39) = (unsigned __int16)v13;
        v14 = *(ByteSliceManager **)(a1 + 184);
        v15 = (unsigned __int8 *)*((_QWORD *)v14 + 2);
        v44 = &ByteSliceStream::`vftable';
        v45 = v15;
        v46 = v14;
        FreeBlock = ByteSliceManager::LastFreeBlock(v14);
        if ( v18 )
          v19 = (unsigned __int8 *)(v18 + FreeBlock);
        else
          v19 = (unsigned __int8 *)(*(_QWORD *)(v17 + 16) + FreeBlock);
        v45 = v19;
        v45 = (unsigned __int8 *)(v11 + *(_QWORD *)(v17 + 16));
        v20 = *v45;
        v53 = *v45++;
        v21 = 0;
        v43 = 0;
        v22 = 0;
        v42 = 0;
        v23 = 0;
        v40 = 0;
        v24 = *v45++;
        if ( v24 - 1 <= 8 || v24 == 37 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        if ( v24 < 0x40 )
        {
          v25 = 0;
          v26 = (unsigned int *)(a1 + 264);
          if ( v24 == 39 )
          {
LABEL_38:
            v31 = 0;
            if ( v20 )
            {
              v32 = v20;
              do
              {
                v33 = (__int64 *)CBasicTopLexicon::ReadUserData(a1, &v54, &v44, (char *)&v39 + 4, v39);
                if ( v21 != *v33 )
                {
                  v34 = v21;
                  v21 = *v33;
                  v43 = *v33;
                  _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(&v43);
                  if ( v34 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
                _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v54);
                if ( !v22 && v21 )
                {
                  v22 = v21;
                  v42 = v21;
                  _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(&v42);
                }
                if ( v23 )
                {
                  v35 = (__int64 *)(_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(&v40)
                                  + 48);
                  v36 = *v35;
                  if ( *v35 != v21 )
                  {
                    *v35 = v21;
                    _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v35);
                    if ( v36 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                  }
                }
                if ( v23 != v21 )
                {
                  v37 = v23;
                  v23 = v21;
                  v40 = v21;
                  _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(&v40);
                  if ( v37 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                }
                ++v31;
              }
              while ( v31 < v32 );
              v4 = a2;
            }
            *v4 = v22;
            _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v4);
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v40);
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v42);
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v43);
            return v4;
          }
        }
        else
        {
          v25 = v24 - 63;
          v26 = (unsigned int *)(a1 + 264);
          if ( *(int *)(a1 + 264) < 0 )
          {
            CBasicTopLexicon::MemberNameFor(a1, &v54, v25);
            if ( v54 )
              v27 = *(_QWORD *)v54;
            else
              v27 = 0;
            if ( !v27 )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
              throw (CNLException *)pExceptionObject;
            }
            if ( v54 )
              v28 = *(_QWORD *)v54;
            else
              v28 = 0;
            if ( !(unsigned int)CMN_CompareStringNoCaseW(L"UserData", v28)
              || (!v54 ? (v30 = 0) : (v30 = *(_QWORD *)v54), !(unsigned int)CMN_CompareStringNoCaseW(
                                                                              L"LexUserData",
                                                                              v30)) )
            {
              *v26 = v25;
            }
            _bstr_t::_Free(&v54, v29);
            v20 = v53;
          }
        }
        if ( v25 != *v26 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        goto LABEL_38;
      }
    }
LABEL_57:
    *v4 = 0;
  }
  else
  {
    *v4 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18003b8d0  mov     rax, rsp
0x18003b8d3  mov     [rax+10h], rdx
0x18003b8d7  push    rbp
0x18003b8d8  push    rsi
0x18003b8d9  push    rdi
0x18003b8da  push    r12
0x18003b8dc  push    r13
0x18003b8de  push    r14
0x18003b8e0  push    r15
0x18003b8e2  lea     rbp, [rax-5Fh]
0x18003b8e6  sub     rsp, 0C0h
0x18003b8ed  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18003b8f5  mov     [rax+8], rbx
0x18003b8f9  mov     r14d, r8d
0x18003b8fc  mov     rsi, rdx
0x18003b8ff  mov     r15, rcx
0x18003b902  xor     r12d, r12d
0x18003b905  mov     [rbp+57h+var_D0], r12d
0x18003b909  test    r8d, r8d
0x18003b90c  jz      loc_18003BCBC
0x18003b912  mov     r10, [rcx+78h]
0x18003b916  mov     rax, [r10+30h]
0x18003b91a  movsxd  r9, dword ptr [rax+4]
0x18003b91e  lea     rcx, [r10+30h]
0x18003b922  add     rcx, r9; this
0x18003b925  call    ?GetCWords@CCompressedTrie@NLG@@UEBAIXZ; NLG::CCompressedTrie::GetCWords(void)
0x18003b92a  cmp     r14d, eax
0x18003b92d  ja      loc_18003BCBC
0x18003b933  mov     rcx, [r15+0A8h]
0x18003b93a  movzx   eax, byte ptr [rcx+24h]
0x18003b93e  cmp     [rcx+8], eax
0x18003b941  jbe     loc_18003BCBC
0x18003b947  mov     rax, [rcx]
0x18003b94a  mov     r8d, r14d
0x18003b94d  lea     rdx, [rbp+57h+var_C0]
0x18003b951  mov     rax, [rax+38h]
0x18003b955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b95a  mov     ecx, [rbp+57h+var_C0]
0x18003b95d  mov     r10d, 0FFFFFFh
0x18003b963  and     ecx, r10d
0x18003b966  jz      loc_18003BCB7
0x18003b96c  mov     rax, [r15+0B0h]
0x18003b973  mov     rbx, [rax+10h]
0x18003b977  add     rbx, rcx
0x18003b97a  jz      loc_18003BCB7
0x18003b980  mov     [rbp+57h+var_88], rbx
0x18003b984  mov     [rbp+57h+var_80], r12b
0x18003b988  mov     ebx, [rbx]
0x18003b98a  test    ebx, ebx
0x18003b98c  jz      loc_18003BCB7
0x18003b992  mov     eax, ebx
0x18003b994  and     eax, 0F000000h
0x18003b999  cmp     eax, 7000000h
0x18003b99e  jz      short loc_18003B9B1
0x18003b9a0  lea     rdx, [rbp+57h+arg_10]
0x18003b9a4  lea     rcx, [rbp+57h+var_88]
0x18003b9a8  call    ?Next@?$Indexes@UEntryIndex@@@@QEAA?AUEntryIndex@@XZ; Indexes<EntryIndex>::Next(void)
0x18003b9ad  mov     ebx, [rax]
0x18003b9af  jmp     short loc_18003B98A
0x18003b9b1  and     ebx, r10d
0x18003b9b4  jz      loc_18003BCB7
0x18003b9ba  mov     [rbp+57h+var_CC], r12d
0x18003b9be  mov     rdx, [r15+78h]
0x18003b9c2  mov     edi, [r15+90h]
0x18003b9c9  dec     edi
0x18003b9cb  mov     rax, [rdx+30h]
0x18003b9cf  movsxd  rcx, dword ptr [rax+4]
0x18003b9d3  add     rdx, 30h ; '0'
0x18003b9d7  add     rcx, rdx; this
0x18003b9da  call    ?GetCWords@CCompressedTrie@NLG@@UEBAIXZ; NLG::CCompressedTrie::GetCWords(void)
0x18003b9df  mov     eax, eax
0x18003b9e1  cqo
0x18003b9e3  idiv    qword ptr [r15+90h]
0x18003b9ea  mov     rcx, rax
0x18003b9ed  xor     edx, edx
0x18003b9ef  mov     eax, r14d
0x18003b9f2  div     ecx
0x18003b9f4  cmp     eax, edi
0x18003b9f6  cmovnb  ax, di
0x18003b9fa  movzx   eax, ax
0x18003b9fd  mov     [rbp+57h+var_CC], eax
0x18003ba00  mov     r10, [r15+0B8h]
0x18003ba07  mov     r11, [r10+10h]
0x18003ba0b  lea     rax, ??_7ByteSliceStream@@6B@; const ByteSliceStream::`vftable'
0x18003ba12  mov     [rbp+57h+var_A8], rax
0x18003ba16  mov     [rbp+57h+var_98], r11
0x18003ba1a  mov     [rbp+57h+var_90], r10
0x18003ba1e  mov     rcx, r10; this
0x18003ba21  call    ?LastFreeBlock@ByteSliceManager@@QEBAKXZ; ByteSliceManager::LastFreeBlock(void)
0x18003ba26  mov     r9d, eax
0x18003ba29  test    r11, r11
0x18003ba2c  jz      short loc_18003BA33
0x18003ba2e  add     r9, r11
0x18003ba31  jmp     short loc_18003BA37
0x18003ba33  add     r9, [r10+10h]
0x18003ba37  mov     [rbp+57h+var_98], r9
0x18003ba3b  mov     ecx, ebx
0x18003ba3d  mov     rax, [r10+10h]
0x18003ba41  add     rax, rcx
0x18003ba44  mov     [rbp+57h+var_98], rax
0x18003ba48  mov     dl, [rax]
0x18003ba4a  mov     [rbp+57h+arg_10], dl
0x18003ba4d  inc     rax
0x18003ba50  mov     [rbp+57h+var_98], rax
0x18003ba54  mov     r14, r12
0x18003ba57  mov     [rbp+57h+var_B0], r12
0x18003ba5b  mov     rdi, r12
0x18003ba5e  mov     [rbp+57h+var_B8], r12
0x18003ba62  mov     rbx, r12
0x18003ba65  mov     [rbp+57h+var_C8], rbx
0x18003ba69  mov     rax, [rbp+57h+var_98]
0x18003ba6d  movzx   ecx, byte ptr [rax]
0x18003ba70  inc     rax
0x18003ba73  mov     [rbp+57h+var_98], rax
0x18003ba77  lea     eax, [rcx-1]
0x18003ba7a  cmp     eax, 8
0x18003ba7d  jbe     loc_18003BC94
0x18003ba83  cmp     ecx, 25h ; '%'
0x18003ba86  jz      loc_18003BC94
0x18003ba8c  cmp     ecx, 40h ; '@'
0x18003ba8f  jb      loc_18003BB41
0x18003ba95  lea     r13d, [rcx-3Fh]
0x18003ba99  lea     r12, [r15+108h]
0x18003baa0  cmp     dword ptr [r12], 0
0x18003baa5  jge     loc_18003BB50
0x18003baab  mov     r8d, r13d
0x18003baae  lea     rdx, [rbp+57h+arg_18]
0x18003bab2  mov     rcx, r15
0x18003bab5  call    ?MemberNameFor@CBasicTopLexicon@@IEBA?AV_bstr_t@@H@Z; CBasicTopLexicon::MemberNameFor(int)
0x18003baba  nop
0x18003babb  mov     rax, [rbp+57h+arg_18]
0x18003babf  test    rax, rax
0x18003bac2  jz      short loc_18003BAC9
0x18003bac4  mov     rcx, [rax]
0x18003bac7  jmp     short loc_18003BACB
0x18003bac9  xor     ecx, ecx
0x18003bacb  test    rcx, rcx
0x18003bace  jnz     short loc_18003BAF3
0x18003bad0  mov     r8, [rbp+5Fh]; void *
0x18003bad4  mov     edx, 80004005h; int
0x18003bad9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003badd  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003bae2  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003bae9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003baed  call    _CxxThrowException_0
0x18003baf3  test    rax, rax
0x18003baf6  jz      short loc_18003BAFD
0x18003baf8  mov     rdx, [rax]
0x18003bafb  jmp     short loc_18003BAFF
0x18003bafd  xor     edx, edx
0x18003baff  lea     rcx, aUserdata; "UserData"
0x18003bb06  call    CMN_CompareStringNoCaseW
0x18003bb0b  test    eax, eax
0x18003bb0d  jz      short loc_18003BB2F
0x18003bb0f  mov     rax, [rbp+57h+arg_18]
0x18003bb13  test    rax, rax
0x18003bb16  jz      short loc_18003BB1D
0x18003bb18  mov     rdx, [rax]
0x18003bb1b  jmp     short loc_18003BB1F
0x18003bb1d  xor     edx, edx
0x18003bb1f  lea     rcx, aLexuserdata; "LexUserData"
0x18003bb26  call    CMN_CompareStringNoCaseW
0x18003bb2b  test    eax, eax
0x18003bb2d  jnz     short loc_18003BB33
0x18003bb2f  mov     [r12], r13d
0x18003bb33  lea     rcx, [rbp+57h+arg_18]; this
0x18003bb37  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003bb3c  mov     dl, [rbp+57h+arg_10]
0x18003bb3f  jmp     short loc_18003BB50
0x18003bb41  mov     r13d, r12d
0x18003bb44  lea     r12, [r15+108h]
0x18003bb4b  cmp     ecx, 27h ; '''
0x18003bb4e  jz      short loc_18003BB79
0x18003bb50  cmp     r13d, [r12]
0x18003bb54  jz      short loc_18003BB79
0x18003bb56  mov     r8, [rbp+5Fh]; void *
0x18003bb5a  mov     edx, 80004005h; int
0x18003bb5f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003bb63  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003bb68  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003bb6f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003bb73  call    _CxxThrowException_0
0x18003bb79  movzx   eax, dl
0x18003bb7c  xor     r13d, r13d
0x18003bb7f  test    dl, dl
0x18003bb81  jz      loc_18003BC63
0x18003bb87  mov     esi, eax
0x18003bb89  lea     r9, [rbp+57h+var_CC]
0x18003bb8d  lea     r8, [rbp+57h+var_A8]
0x18003bb91  lea     rdx, [rbp+57h+arg_18]
0x18003bb95  mov     rcx, r15
0x18003bb98  call    ?ReadUserData@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadUserData(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18003bb9d  nop
0x18003bb9e  cmp     r14, [rax]
0x18003bba1  jz      short loc_18003BBCC
0x18003bba3  mov     r12, r14
0x18003bba6  mov     r14, [rax]
0x18003bba9  mov     [rbp+57h+var_B0], r14
0x18003bbad  lea     rcx, [rbp+57h+var_B0]
0x18003bbb1  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18003bbb6  test    r12, r12
0x18003bbb9  jz      short loc_18003BBCC
0x18003bbbb  mov     rax, [r12]
0x18003bbbf  mov     rcx, r12
0x18003bbc2  mov     rax, [rax+10h]
0x18003bbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbcb  nop
0x18003bbcc  lea     rcx, [rbp+57h+arg_18]
0x18003bbd0  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003bbd5  test    rdi, rdi
0x18003bbd8  jnz     short loc_18003BBEF
0x18003bbda  test    r14, r14
0x18003bbdd  jz      short loc_18003BBEF
0x18003bbdf  mov     rdi, r14
0x18003bbe2  mov     [rbp+57h+var_B8], r14
0x18003bbe6  lea     rcx, [rbp+57h+var_B8]
0x18003bbea  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18003bbef  test    rbx, rbx
0x18003bbf2  jz      short loc_18003BC26
0x18003bbf4  lea     rcx, [rbp+57h+var_C8]
0x18003bbf8  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003bbfd  lea     rcx, [rax+30h]
0x18003bc01  mov     r12, [rcx]
0x18003bc04  cmp     r12, r14
0x18003bc07  jz      short loc_18003BC26
0x18003bc09  mov     [rcx], r14
0x18003bc0c  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18003bc11  test    r12, r12
0x18003bc14  jz      short loc_18003BC26
0x18003bc16  mov     rax, [r12]
0x18003bc1a  mov     rcx, r12
0x18003bc1d  mov     rax, [rax+10h]
0x18003bc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc26  cmp     rbx, r14
0x18003bc29  jz      short loc_18003BC53
0x18003bc2b  mov     r12, rbx
0x18003bc2e  mov     rbx, r14
0x18003bc31  mov     [rbp+57h+var_C8], rbx
0x18003bc35  lea     rcx, [rbp+57h+var_C8]
0x18003bc39  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18003bc3e  test    r12, r12
0x18003bc41  jz      short loc_18003BC53
0x18003bc43  mov     rax, [r12]
0x18003bc47  mov     rcx, r12
0x18003bc4a  mov     rax, [rax+10h]
0x18003bc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc53  inc     r13d
0x18003bc56  cmp     r13d, esi
0x18003bc59  jl      loc_18003BB89
0x18003bc5f  mov     rsi, [rbp+57h+arg_8]
0x18003bc63  mov     [rsi], rdi
0x18003bc66  mov     rcx, rsi
0x18003bc69  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18003bc6e  mov     [rbp+57h+var_D0], 1
0x18003bc75  lea     rcx, [rbp+57h+var_C8]
0x18003bc79  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003bc7e  nop
0x18003bc7f  lea     rcx, [rbp+57h+var_B8]
0x18003bc83  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003bc88  nop
0x18003bc89  lea     rcx, [rbp+57h+var_B0]
0x18003bc8d  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003bc92  jmp     short loc_18003BCC6
0x18003bc94  mov     r8, [rbp+5Fh]; void *
0x18003bc98  mov     edx, 80004005h; int
0x18003bc9d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003bca1  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003bca6  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003bcad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003bcb1  call    _CxxThrowException_0
0x18003bcb7  mov     [rsi], r12
0x18003bcba  jmp     short loc_18003BCBF
0x18003bcbc  mov     [rsi], r12
0x18003bcbf  mov     [rbp+57h+var_D0], 1
0x18003bcc6  mov     rax, rsi
0x18003bcc9  mov     rbx, [rsp+0F0h+arg_0]
0x18003bcd1  add     rsp, 0C0h
0x18003bcd8  pop     r15
0x18003bcda  pop     r14
0x18003bcdc  pop     r13
0x18003bcde  pop     r12
0x18003bce0  pop     rdi
0x18003bce1  pop     rsi
0x18003bce2  pop     rbp
0x18003bce3  retn
```
