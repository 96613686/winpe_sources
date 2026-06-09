# CMapi2RowFilter::GetChunk(tagSTAT_CHUNK *)

- ea: `0x18001de80`
- end: `0x18001e083`
- name: `?GetChunk@CMapi2RowFilter@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(CMapi2RowFilter *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ec8c`
- `0x18000faac`
- `0x18000fd58`
- `0x1800119a0`
- `0x1800154e0`
- `0x18001870c`
- `0x18001de80`
- `0x18001e5d8`
- `0x18001e608`
- `0x180021fc4`
- `0x18002b124`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e042`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapi2RowFilter::GetChunk(CMapi2RowFilter *this, struct tagSTAT_CHUNK *a2)
{
  int Chunk; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  _QWORD *v7; // r14
  const struct CSingleLink *v8; // rbx
  __int64 v9; // rcx
  int v10; // r15d
  __int64 v11; // rax
  int v12; // ebx
  int v13; // r8d
  LCID v14; // r9d
  void *v15; // rcx
  LPVOID *p_pv; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h] BYREF
  char v18; // [rsp+30h] [rbp-10h]
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF
  __int64 *v20; // [rsp+80h] [rbp+40h] BYREF

  if ( !*((_DWORD *)this + 5946) )
  {
    Chunk = IFilterImpl<CMapi2RowFilter>::GetChunk();
    v5 = Chunk;
    if ( Chunk >= 0 )
    {
      a2->idChunk = ++*((_DWORD *)this + 5945);
      return v5;
    }
    if ( Chunk != -2147215616 )
    {
      CLogger::Error((unsigned int)Chunk, L"CMapi2RowFilter::GetChunk encountered an error");
      return v5;
    }
    *((_DWORD *)this + 5946) = 1;
  }
  v7 = (_QWORD *)((char *)this + 24008);
  while ( *v7 )
  {
LABEL_13:
    result = (*(__int64 (__fastcall **)(_QWORD, struct tagSTAT_CHUNK *))(*(_QWORD *)*v7 + 32LL))(*v7, a2);
    if ( (_DWORD)result == -2147418105 || (_DWORD)result == -2147023174 || (_DWORD)result == -2147417851 )
      return result;
    if ( (int)result < 0 )
    {
      v10 = 0;
      v20 = 0;
      if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 **))*v7)(
             *v7,
             &GUID_5bbb9cf4_e333_4a5f_89e8_29c917c9eff4,
             &v20) >= 0 )
      {
        pv = 0;
        v11 = *v20;
        p_pv = &pv;
        v17 = 0;
        v18 = 1;
        v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 24))(v20, &v17);
        wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
        if ( v12 >= 0 )
        {
          IFilterImpl<CMapi2RowFilter>::SetValueChunkAsStringAndTakeMemoryOwnership(this, &pv);
          CMapi2FullPropSpec::GetPropId((CMapi2FullPropSpec *)g_mfpsSearch_AutoSummary);
          a2->attribute.guidPropSet = *CMapi2FullPropSpec::GetPropGuid((CMapi2FullPropSpec *)g_mfpsSearch_AutoSummary);
          a2->attribute.psProperty.ulKind = 1;
          LODWORD(a2->attribute.psProperty.propid) = v13;
          a2->breakType = CHUNK_EOS;
          a2->flags = CHUNK_VALUE;
          a2->locale = v14;
          v10 = 1;
          *((_DWORD *)this + 5946) = 0;
        }
        (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
        v15 = pv;
        pv = 0;
        if ( v15 )
          CoTaskMemFree(v15);
      }
      TComPointer<IFilter>::operator=((_QWORD *)this + 3001, 0);
      if ( !v10 )
        continue;
    }
    a2->idChunk = ++*((_DWORD *)this + 5945);
    return 0;
  }
  if ( *((_DWORD *)this + 6000) )
  {
    v8 = CLnkList::RemoveFirst((CMapi2RowFilter *)((char *)this + 23976));
    CUnkSList::GetLinkValue(v8, (struct IUnknown **)this + 3001);
    if ( v8 )
      TNoUnkSList<CMapi2Accessor>::DestroyLink(v9, v8);
    goto LABEL_13;
  }
  return 2147751680LL;
}

```

## disassembly

```asm
0x18001de80  mov     [rsp-28h+arg_8], rbx
0x18001de85  push    rbp
0x18001de86  push    rsi
0x18001de87  push    rdi
0x18001de88  push    r14
0x18001de8a  push    r15
0x18001de8c  mov     rbp, rsp
0x18001de8f  sub     rsp, 40h
0x18001de93  mov     rsi, rdx
0x18001de96  mov     rdi, rcx
0x18001de99  cmp     dword ptr [rcx+5CE8h], 0
0x18001dea0  jnz     short loc_18001DEE4
0x18001dea2  call    ?GetChunk@?$IFilterImpl@VCMapi2RowFilter@@@@UEAAJPEAUtagSTAT_CHUNK@@@Z; IFilterImpl<CMapi2RowFilter>::GetChunk(tagSTAT_CHUNK *)
0x18001dea7  mov     ebx, eax
0x18001dea9  test    eax, eax
0x18001deab  js      short loc_18001DEC2
0x18001dead  inc     dword ptr [rdi+5CE4h]
0x18001deb3  mov     eax, [rdi+5CE4h]
0x18001deb9  mov     [rsi], eax
0x18001debb  mov     eax, ebx
0x18001debd  jmp     loc_18001E06B
0x18001dec2  cmp     ebx, 80041700h
0x18001dec8  jz      short loc_18001DEDA
0x18001deca  lea     rdx, aCmapi2rowfilte_3; "CMapi2RowFilter::GetChunk encountered a"...
0x18001ded1  mov     ecx, ebx; int
0x18001ded3  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001ded8  jmp     short loc_18001DEBB
0x18001deda  mov     dword ptr [rdi+5CE8h], 1
0x18001dee4  lea     r14, [rdi+5DC8h]
0x18001deeb  cmp     qword ptr [r14], 0
0x18001deef  jnz     short loc_18001DF25
0x18001def1  cmp     dword ptr [rdi+5DC0h], 0
0x18001def8  jz      loc_18001E07C
0x18001defe  lea     rcx, [rdi+5DA8h]; this
0x18001df05  call    ?RemoveFirst@CLnkList@@QEAAPEAVCSingleLink@@XZ; CLnkList::RemoveFirst(void)
0x18001df0a  mov     rbx, rax
0x18001df0d  mov     rdx, r14; struct IUnknown **
0x18001df10  mov     rcx, rax; struct CSingleLink *
0x18001df13  call    ?GetLinkValue@CUnkSList@@KAJPEBVCSingleLink@@PEAPEAUIUnknown@@@Z; CUnkSList::GetLinkValue(CSingleLink const *,IUnknown * *)
0x18001df18  test    rbx, rbx
0x18001df1b  jz      short loc_18001DF25
0x18001df1d  mov     rdx, rbx
0x18001df20  call    ?DestroyLink@?$TNoUnkSList@VCMapi2Accessor@@@@IEAAXPEAV?$TNoUnkSingleLink@VCMapi2Accessor@@@@@Z; TNoUnkSList<CMapi2Accessor>::DestroyLink(TNoUnkSingleLink<CMapi2Accessor> *)
0x18001df25  mov     rcx, [r14]
0x18001df28  mov     rax, [rcx]
0x18001df2b  mov     rdx, rsi
0x18001df2e  mov     rax, [rax+20h]
0x18001df32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df37  cmp     eax, 80010007h
0x18001df3c  jz      loc_18001E06B
0x18001df42  cmp     eax, 800706BAh
0x18001df47  jz      loc_18001E06B
0x18001df4d  cmp     eax, 80010105h
0x18001df52  jz      loc_18001E06B
0x18001df58  test    eax, eax
0x18001df5a  jns     loc_18001E05B
0x18001df60  xor     r15d, r15d
0x18001df63  mov     [rbp+arg_10], r15
0x18001df67  mov     rcx, [r14]
0x18001df6a  mov     rax, [rcx]
0x18001df6d  lea     r8, [rbp+arg_10]
0x18001df71  lea     rdx, _GUID_5bbb9cf4_e333_4a5f_89e8_29c917c9eff4
0x18001df78  mov     rax, [rax]
0x18001df7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df80  test    eax, eax
0x18001df82  js      loc_18001E048
0x18001df88  mov     [rbp+pv], r15
0x18001df8c  mov     rcx, [rbp+arg_10]
0x18001df90  mov     rax, [rcx]
0x18001df93  lea     rdx, [rbp+pv]
0x18001df97  mov     [rbp+var_20], rdx
0x18001df9b  mov     [rbp+var_18], r15
0x18001df9f  mov     [rbp+var_10], 1
0x18001dfa3  lea     rdx, [rbp+var_18]
0x18001dfa7  mov     rax, [rax+18h]
0x18001dfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb0  mov     ebx, eax
0x18001dfb2  lea     rcx, [rbp+var_20]
0x18001dfb6  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001dfbb  shr     ebx, 1Fh
0x18001dfbe  xor     bl, 1
0x18001dfc1  jz      short loc_18001E020
0x18001dfc3  lea     rdx, [rbp+pv]
0x18001dfc7  mov     rcx, rdi
0x18001dfca  call    ?SetValueChunkAsStringAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXAEAV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2RowFilter>::SetValueChunkAsStringAndTakeMemoryOwnership(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18001dfcf  mov     r9d, [rdi+54B0h]
0x18001dfd6  lea     rcx, ?g_mfpsSearch_AutoSummary@@3VCMapi2FullPropSpec@@B; this
0x18001dfdd  call    ?GetPropId@CMapi2FullPropSpec@@QEBAKXZ; CMapi2FullPropSpec::GetPropId(void)
0x18001dfe2  mov     r8d, eax
0x18001dfe5  lea     rcx, ?g_mfpsSearch_AutoSummary@@3VCMapi2FullPropSpec@@B; this
0x18001dfec  call    ?GetPropGuid@CMapi2FullPropSpec@@QEBAAEBU_GUID@@XZ; CMapi2FullPropSpec::GetPropGuid(void)
0x18001dff1  movups  xmm0, xmmword ptr [rax]
0x18001dff4  movdqu  xmmword ptr [rsi+10h], xmm0
0x18001dff9  mov     dword ptr [rsi+20h], 1
0x18001e000  mov     [rsi+28h], r8d
0x18001e004  lea     eax, [r15+2]
0x18001e008  mov     [rsi+4], eax
0x18001e00b  mov     [rsi+8], eax
0x18001e00e  mov     [rsi+0Ch], r9d
0x18001e012  lea     r15d, [rax-1]
0x18001e016  mov     dword ptr [rdi+5CE8h], 0
0x18001e020  mov     rcx, [rbp+arg_10]
0x18001e024  mov     rax, [rcx]
0x18001e027  mov     rax, [rax+10h]
0x18001e02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e030  nop
0x18001e031  mov     rcx, [rbp+pv]; pv
0x18001e035  mov     [rbp+pv], 0
0x18001e03d  test    rcx, rcx
0x18001e040  jz      short loc_18001E048
0x18001e042  call    cs:__imp_CoTaskMemFree
0x18001e048  xor     edx, edx
0x18001e04a  mov     rcx, r14
0x18001e04d  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001e052  test    r15d, r15d
0x18001e055  jz      loc_18001DEEB
0x18001e05b  inc     dword ptr [rdi+5CE4h]
0x18001e061  mov     eax, [rdi+5CE4h]
0x18001e067  mov     [rsi], eax
0x18001e069  xor     eax, eax
0x18001e06b  mov     rbx, [rsp+40h+arg_8]
0x18001e070  add     rsp, 40h
0x18001e074  pop     r15
0x18001e076  pop     r14
0x18001e078  pop     rdi
0x18001e079  pop     rsi
0x18001e07a  pop     rbp
0x18001e07b  retn
0x18001e07c  mov     eax, 80041700h
0x18001e081  jmp     short loc_18001E06B
```
