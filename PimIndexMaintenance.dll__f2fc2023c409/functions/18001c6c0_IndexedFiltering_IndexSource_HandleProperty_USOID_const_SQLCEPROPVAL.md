# IndexedFiltering::IndexSource::HandleProperty(USOID const &,_SQLCEPROPVAL *)

- ea: `0x18001c6c0`
- end: `0x18001ca33`
- name: `?HandleProperty@IndexSource@IndexedFiltering@@MEAAJAEBUUSOID@@PEAU_SQLCEPROPVAL@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexSource *__hidden this, const struct USOID *, struct _SQLCEPROPVAL *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800012f0`
- `0x1800012fc`
- `0x180003f90`
- `0x18000428c`
- `0x1800086a0`
- `0x18000c51c`
- `0x18000e670`
- `0x1800124a8`
- `0x180013b80`
- `0x18001baac`
- `0x18001c460`
- `0x18001c6c0`
- `0x18001cb30`
- `0x18002120a`
- `0x180022010`

## import_xrefs

- `UserDataLanguageUtil!CHSPinYinHelper_CreateInstance` at `0x18001c7c4`
- `UserDataLanguageUtil!CHSPinYinHelper_CreateInstance` at `0x18001c7c4`
- `UserDataLanguageUtil!CHSPinYinHelper_HasPossibleCHSPinYin` at `0x18001c78d`
- `UserDataLanguageUtil!CHSPinYinHelper_HasPossibleCHSPinYin` at `0x18001c78d`
- `UserDataLanguageUtil!CHSPinYinHelper_Initialize` at `0x18001c797`
- `UserDataLanguageUtil!CHSPinYinHelper_Initialize` at `0x18001c797`
- `UserDataLanguageUtil!DecomposeHangulSyllables` at `0x18001c97a`
- `UserDataLanguageUtil!DecomposeHangulSyllables` at `0x18001c97a`

## string_xrefs

- `0x18001c717`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexSource::HandleProperty(
        IndexedFiltering::IndexSource *this,
        const struct USOID *a2,
        struct _SQLCEPROPVAL *a3)
{
  int v5; // r13d
  const struct USOID *v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // r15d
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // r14
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // ebx
  BOOL v14; // esi
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  void *v20; // rax
  void *v21; // rbx
  BOOL v22; // edi
  __int64 v23; // rax
  int v24; // eax
  int v25; // esi
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  __int64 v29; // r8
  int v30; // edi
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r9
  _QWORD *v36; // [rsp+30h] [rbp-50h] BYREF
  int v37; // [rsp+38h] [rbp-48h]
  _QWORD v38[3]; // [rsp+40h] [rbp-40h] BYREF
  void *v39[5]; // [rsp+58h] [rbp-28h] BYREF
  int v40; // [rsp+C0h] [rbp+40h] BYREF
  struct ICHSPinYinHelper *v41; // [rsp+D8h] [rbp+58h] BYREF

  v5 = (int)a2;
  utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v38);
  v36 = v38;
  LOBYTE(v37) = 1;
  v8 = 0;
  if ( (unsigned int)IsEmptyUsOid(v6) || !a3 )
    Log_AssertionEvent(
      v7,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
      903);
  v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(IndexedFiltering::IndexSource *, struct _SQLCEPROPVAL *))(*(_QWORD *)this + 168LL))(
                                   this,
                                   a3);
  v10 = v9;
  if ( !v9 || !*v9 )
    goto LABEL_47;
  v11 = IndexedFiltering::IndexSource::HandleProperty((_DWORD)this, v5, (_DWORD)v9, 0, (__int64)v38);
  v13 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent_7((unsigned int)v11, 1, v12, 914);
    goto LABEL_48;
  }
  v41 = 0;
  v14 = 0;
  if ( CHSPinYinHelper_HasPossibleCHSPinYin(v10) )
  {
    v15 = CHSPinYinHelper_Initialize();
    v13 = v15;
    if ( v15 < 0 )
    {
      v17 = 919;
LABEL_11:
      v18 = 1;
      v19 = (unsigned int)v15;
LABEL_12:
      Log_HREvent_7(v19, v18, v16, v17);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v41);
      goto LABEL_48;
    }
    v15 = CHSPinYinHelper_CreateInstance(&v41);
    v13 = v15;
    if ( v15 < 0 )
    {
      v17 = 920;
      goto LABEL_11;
    }
    v14 = 1;
  }
  v20 = operator new(0x4100u);
  v18 = 0;
  v21 = v20;
  if ( !v20 )
  {
    v13 = -2147024882;
    v17 = 925;
    v19 = 2147942414LL;
    goto LABEL_12;
  }
  memset_0(v20, 0, 0x4100u);
  v22 = 0;
  while ( v14 )
  {
    v23 = *(_QWORD *)v41;
    if ( v8 )
    {
      if ( (*(int (__fastcall **)(struct ICHSPinYinHelper *, void *))(v23 + 32))(v41, v21) < 0 )
        break;
      v14 = 1;
    }
    else
    {
      v24 = (*(__int64 (__fastcall **)(struct ICHSPinYinHelper *, const unsigned __int16 *, void *, _QWORD, _DWORD))(v23 + 24))(
              v41,
              v10,
              v21,
              0,
              0);
      v14 = v24 >= 0;
      if ( v24 < 0 )
        break;
    }
    v28 = IndexedFiltering::IndexSource::HandleProperty((_DWORD)this, v5, (_DWORD)v21, 128, (__int64)v38);
    v30 = v28;
    if ( v28 < 0 )
    {
      Log_HREvent_7((unsigned int)v28, 1, v29, 937);
LABEL_31:
      operator delete(v21);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v41);
      v13 = v30;
      goto LABEL_48;
    }
    v22 = 1;
    ++v8;
  }
  v8 = 0;
  v25 = 0;
  while ( v22 )
  {
    v26 = *(_QWORD *)v41;
    if ( v25 )
    {
      if ( (*(int (__fastcall **)(struct ICHSPinYinHelper *, void *))(v26 + 32))(v41, v21) < 0 )
      {
        v22 = 0;
        goto LABEL_37;
      }
      v22 = 1;
    }
    else
    {
      v27 = (*(__int64 (__fastcall **)(struct ICHSPinYinHelper *, const unsigned __int16 *, void *, _QWORD, int))(v26 + 24))(
              v41,
              v10,
              v21,
              0,
              1);
      v22 = v27 >= 0;
      if ( v27 < 0 )
        goto LABEL_37;
    }
    v31 = IndexedFiltering::IndexSource::HandleProperty((_DWORD)this, v5, (_DWORD)v21, 128, (__int64)v38);
    v8 = v31;
    if ( v31 < 0 )
    {
      Log_HREvent_7((unsigned int)v31, 1, v32, 956);
      goto LABEL_46;
    }
    v8 = 0;
LABEL_37:
    ++v25;
  }
  v40 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v39);
  v30 = DecomposeHangulSyllables(v10, 0, 1, v39, 0, &v40, v36, v37);
  if ( v30 < 0 )
  {
    v34 = 970;
LABEL_41:
    Log_HREvent_7((unsigned int)v30, 1, v33, v34);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v39);
    goto LABEL_31;
  }
  if ( v40 )
  {
    v30 = IndexedFiltering::IndexSource::HandleProperty((_DWORD)this, v5, v39[0], 128, (__int64)v38);
    if ( v30 < 0 )
    {
      v34 = 975;
      goto LABEL_41;
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v39);
LABEL_46:
  operator delete(v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v41);
LABEL_47:
  v13 = v8;
LABEL_48:
  tlx::_UndoSolo__lambda_9bf456a88572d8939f6954fdf97c9ca2___::__UndoSolo__lambda_9bf456a88572d8939f6954fdf97c9ca2___(&v36);
  utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v38);
  return v13;
}

```

## disassembly

```asm
0x18001c6c0  mov     [rsp-38h+arg_8], rbx
0x18001c6c5  push    rbp
0x18001c6c6  push    rsi
0x18001c6c7  push    rdi
0x18001c6c8  push    r12
0x18001c6ca  push    r13
0x18001c6cc  push    r14
0x18001c6ce  push    r15
0x18001c6d0  mov     rbp, rsp
0x18001c6d3  sub     rsp, 80h
0x18001c6da  mov     r12, rcx
0x18001c6dd  mov     rbx, r8
0x18001c6e0  lea     rcx, [rbp+var_40]
0x18001c6e4  mov     r13, rdx
0x18001c6e7  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18001c6ec  lea     rcx, [rbp+var_40]
0x18001c6f0  mov     edi, 1
0x18001c6f5  mov     [rbp+var_50], rcx
0x18001c6f9  mov     rcx, rdx; struct USOID *
0x18001c6fc  mov     byte ptr [rbp+var_48], dil
0x18001c700  call    ?IsEmptyUsOid@@YAHAEBUUSOID@@@Z; IsEmptyUsOid(USOID const &)
0x18001c705  xor     r15d, r15d
0x18001c708  test    eax, eax
0x18001c70a  jnz     short loc_18001C711
0x18001c70c  test    rbx, rbx
0x18001c70f  jnz     short loc_18001C723
0x18001c711  mov     r8d, 387h
0x18001c717  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001c71e  call    Log_AssertionEvent
0x18001c723  mov     rax, [r12]
0x18001c727  mov     rdx, rbx
0x18001c72a  mov     rcx, r12
0x18001c72d  mov     rax, [rax+0A8h]
0x18001c734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c739  mov     r14, rax
0x18001c73c  test    rax, rax
0x18001c73f  jz      loc_18001C9EF
0x18001c745  cmp     [rax], r15w
0x18001c749  jz      loc_18001C9EF
0x18001c74f  lea     rax, [rbp+var_40]
0x18001c753  xor     r9d, r9d
0x18001c756  mov     r8, r14
0x18001c759  mov     [rsp+80h+var_60], rax
0x18001c75e  mov     rdx, r13
0x18001c761  mov     rcx, r12
0x18001c764  call    ?HandleProperty@IndexSource@IndexedFiltering@@AEAAJAEBUUSOID@@PEBGKPEAV?$vector@PEAGV?$allocator@PEAG@utl@@@utl@@@Z; IndexedFiltering::IndexSource::HandleProperty(USOID const &,ushort const *,ulong,utl::vector<ushort *,utl::allocator<ushort *>> *)
0x18001c769  mov     ebx, eax
0x18001c76b  test    eax, eax
0x18001c76d  jns     short loc_18001C783
0x18001c76f  mov     r9d, 392h
0x18001c775  mov     edx, edi
0x18001c777  mov     ecx, eax
0x18001c779  call    Log_HREvent_7
0x18001c77e  jmp     loc_18001C9F2
0x18001c783  mov     rcx, r14
0x18001c786  mov     [rbp+arg_18], r15
0x18001c78a  mov     esi, r15d
0x18001c78d  call    cs:__imp_?CHSPinYinHelper_HasPossibleCHSPinYin@@YAHPEBG@Z; CHSPinYinHelper_HasPossibleCHSPinYin(ushort const *)
0x18001c793  test    eax, eax
0x18001c795  jz      short loc_18001C7DA
0x18001c797  call    cs:__imp_?CHSPinYinHelper_Initialize@@YAJXZ; CHSPinYinHelper_Initialize(void)
0x18001c79d  mov     ebx, eax
0x18001c79f  test    eax, eax
0x18001c7a1  jns     short loc_18001C7C0
0x18001c7a3  mov     r9d, 397h
0x18001c7a9  mov     edx, edi
0x18001c7ab  mov     ecx, eax
0x18001c7ad  call    Log_HREvent_7
0x18001c7b2  lea     rcx, [rbp+arg_18]
0x18001c7b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c7bb  jmp     loc_18001C9F2
0x18001c7c0  lea     rcx, [rbp+arg_18]
0x18001c7c4  call    cs:__imp_?CHSPinYinHelper_CreateInstance@@YAJPEAPEAUICHSPinYinHelper@@@Z; CHSPinYinHelper_CreateInstance(ICHSPinYinHelper * *)
0x18001c7ca  mov     ebx, eax
0x18001c7cc  test    eax, eax
0x18001c7ce  jns     short loc_18001C7D8
0x18001c7d0  mov     r9d, 398h
0x18001c7d6  jmp     short loc_18001C7A9
0x18001c7d8  mov     esi, edi
0x18001c7da  mov     edi, 4100h
0x18001c7df  mov     ecx, edi; Size
0x18001c7e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c7e6  xor     edx, edx; Val
0x18001c7e8  mov     rbx, rax
0x18001c7eb  test    rax, rax
0x18001c7ee  jz      loc_18001CA21
0x18001c7f4  mov     r8d, edi; Size
0x18001c7f7  mov     rcx, rax; void *
0x18001c7fa  call    memset_0
0x18001c7ff  mov     edi, r15d
0x18001c802  test    esi, esi
0x18001c804  jz      short loc_18001C834
0x18001c806  mov     rcx, [rbp+arg_18]
0x18001c80a  mov     rax, [rcx]
0x18001c80d  test    r15d, r15d
0x18001c810  jnz     short loc_18001C87F
0x18001c812  mov     rax, [rax+18h]
0x18001c816  xor     r9d, r9d
0x18001c819  mov     r8, rbx
0x18001c81c  mov     dword ptr [rsp+80h+var_60], r15d
0x18001c821  mov     rdx, r14
0x18001c824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c829  mov     esi, eax
0x18001c82b  not     esi
0x18001c82d  shr     esi, 1Fh
0x18001c830  test    esi, esi
0x18001c832  jnz     short loc_18001C894
0x18001c834  xor     r15d, r15d
0x18001c837  mov     esi, r15d
0x18001c83a  test    edi, edi
0x18001c83c  jz      loc_18001C94E
0x18001c842  mov     rcx, [rbp+arg_18]
0x18001c846  mov     rax, [rcx]
0x18001c849  test    esi, esi
0x18001c84b  jnz     loc_18001C8EE
0x18001c851  mov     rax, [rax+18h]
0x18001c855  xor     r9d, r9d
0x18001c858  mov     r8, rbx
0x18001c85b  mov     dword ptr [rsp+80h+var_60], 1
0x18001c863  mov     rdx, r14
0x18001c866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c86b  mov     edi, eax
0x18001c86d  not     edi
0x18001c86f  shr     edi, 1Fh
0x18001c872  test    edi, edi
0x18001c874  jz      loc_18001C92F
0x18001c87a  jmp     loc_18001C903
0x18001c87f  mov     rax, [rax+20h]
0x18001c883  mov     rdx, rbx
0x18001c886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c88b  test    eax, eax
0x18001c88d  js      short loc_18001C834
0x18001c88f  mov     esi, 1
0x18001c894  lea     rax, [rbp+var_40]
0x18001c898  mov     r9d, 80h
0x18001c89e  mov     r8, rbx
0x18001c8a1  mov     [rsp+80h+var_60], rax
0x18001c8a6  mov     rdx, r13
0x18001c8a9  mov     rcx, r12
0x18001c8ac  call    ?HandleProperty@IndexSource@IndexedFiltering@@AEAAJAEBUUSOID@@PEBGKPEAV?$vector@PEAGV?$allocator@PEAG@utl@@@utl@@@Z; IndexedFiltering::IndexSource::HandleProperty(USOID const &,ushort const *,ulong,utl::vector<ushort *,utl::allocator<ushort *>> *)
0x18001c8b1  mov     edi, eax
0x18001c8b3  test    eax, eax
0x18001c8b5  js      short loc_18001C8C4
0x18001c8b7  mov     edi, 1
0x18001c8bc  inc     r15d
0x18001c8bf  jmp     loc_18001C802
0x18001c8c4  mov     edx, 1
0x18001c8c9  mov     r9d, 3A9h
0x18001c8cf  mov     ecx, edi
0x18001c8d1  call    Log_HREvent_7
0x18001c8d6  mov     rcx, rbx; Block
0x18001c8d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c8de  lea     rcx, [rbp+arg_18]
0x18001c8e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c8e7  mov     ebx, edi
0x18001c8e9  jmp     loc_18001C9F2
0x18001c8ee  mov     rax, [rax+20h]
0x18001c8f2  mov     rdx, rbx
0x18001c8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8fa  test    eax, eax
0x18001c8fc  js      short loc_18001C92C
0x18001c8fe  mov     edi, 1
0x18001c903  lea     rax, [rbp+var_40]
0x18001c907  mov     r9d, 80h
0x18001c90d  mov     r8, rbx
0x18001c910  mov     [rsp+80h+var_60], rax
0x18001c915  mov     rdx, r13
0x18001c918  mov     rcx, r12
0x18001c91b  call    ?HandleProperty@IndexSource@IndexedFiltering@@AEAAJAEBUUSOID@@PEBGKPEAV?$vector@PEAGV?$allocator@PEAG@utl@@@utl@@@Z; IndexedFiltering::IndexSource::HandleProperty(USOID const &,ushort const *,ulong,utl::vector<ushort *,utl::allocator<ushort *>> *)
0x18001c920  mov     r15d, eax
0x18001c923  test    eax, eax
0x18001c925  js      short loc_18001C936
0x18001c927  xor     r15d, r15d
0x18001c92a  jmp     short loc_18001C92F
0x18001c92c  mov     edi, r15d
0x18001c92f  inc     esi
0x18001c931  jmp     loc_18001C83A
0x18001c936  mov     edx, 1
0x18001c93b  mov     r9d, 3BCh
0x18001c941  mov     ecx, r15d
0x18001c944  call    Log_HREvent_7
0x18001c949  jmp     loc_18001C9DE
0x18001c94e  lea     rcx, [rbp+var_28]
0x18001c952  mov     [rbp+arg_0], r15d
0x18001c956  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001c95b  lea     rcx, [rbp+arg_0]
0x18001c95f  mov     esi, 1
0x18001c964  mov     [rsp+80h+var_58], rcx
0x18001c969  lea     r9, [rbp+var_28]
0x18001c96d  mov     rcx, r14
0x18001c970  mov     [rsp+80h+var_60], r15
0x18001c975  mov     r8d, esi
0x18001c978  xor     edx, edx
0x18001c97a  call    cs:__imp_?DecomposeHangulSyllables@@YAJPEBGHHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAEPEAH@Z; DecomposeHangulSyllables(ushort const *,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,uchar *,int *)
0x18001c980  mov     edi, eax
0x18001c982  test    eax, eax
0x18001c984  jns     short loc_18001C9A3
0x18001c986  mov     r9d, 3CAh
0x18001c98c  mov     edx, esi
0x18001c98e  mov     ecx, edi
0x18001c990  call    Log_HREvent_7
0x18001c995  lea     rcx, [rbp+var_28]
0x18001c999  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001c99e  jmp     loc_18001C8D6
0x18001c9a3  cmp     [rbp+arg_0], r15d
0x18001c9a7  jz      short loc_18001C9D5
0x18001c9a9  mov     r8, [rbp+var_28]
0x18001c9ad  lea     rax, [rbp+var_40]
0x18001c9b1  mov     r9d, 80h
0x18001c9b7  mov     [rsp+80h+var_60], rax
0x18001c9bc  mov     rdx, r13
0x18001c9bf  mov     rcx, r12
0x18001c9c2  call    ?HandleProperty@IndexSource@IndexedFiltering@@AEAAJAEBUUSOID@@PEBGKPEAV?$vector@PEAGV?$allocator@PEAG@utl@@@utl@@@Z; IndexedFiltering::IndexSource::HandleProperty(USOID const &,ushort const *,ulong,utl::vector<ushort *,utl::allocator<ushort *>> *)
0x18001c9c7  mov     edi, eax
0x18001c9c9  test    eax, eax
0x18001c9cb  jns     short loc_18001C9D5
0x18001c9cd  mov     r9d, 3CFh
0x18001c9d3  jmp     short loc_18001C98C
0x18001c9d5  lea     rcx, [rbp+var_28]
0x18001c9d9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001c9de  mov     rcx, rbx; Block
0x18001c9e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c9e6  lea     rcx, [rbp+arg_18]
0x18001c9ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c9ef  mov     ebx, r15d
0x18001c9f2  lea     rcx, [rbp+var_50]
0x18001c9f6  call    tlx___UndoSolo__lambda_9bf456a88572d8939f6954fdf97c9ca2_______UndoSolo__lambda_9bf456a88572d8939f6954fdf97c9ca2___
0x18001c9fb  lea     rcx, [rbp+var_40]
0x18001c9ff  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x18001ca04  mov     eax, ebx
0x18001ca06  mov     rbx, [rsp+80h+arg_8]
0x18001ca0e  add     rsp, 80h
0x18001ca15  pop     r15
0x18001ca17  pop     r14
0x18001ca19  pop     r13
0x18001ca1b  pop     r12
0x18001ca1d  pop     rdi
0x18001ca1e  pop     rsi
0x18001ca1f  pop     rbp
0x18001ca20  retn
0x18001ca21  mov     ebx, 8007000Eh
0x18001ca26  mov     r9d, 39Dh
0x18001ca2c  mov     ecx, ebx
0x18001ca2e  jmp     loc_18001C7AD
```
