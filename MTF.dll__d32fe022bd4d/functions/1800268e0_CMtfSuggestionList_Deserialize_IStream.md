# CMtfSuggestionList::Deserialize(IStream *)

- ea: `0x1800268e0`
- end: `0x180026ac9`
- name: `?Deserialize@CMtfSuggestionList@@UEAAJPEAUIStream@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180001fc4`
- `0x1800251b8`
- `0x1800268e0`
- `0x18002b6c4`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::Deserialize(CMtfSuggestionList *this, struct IStream *a2)
{
  int v4; // esi
  _QWORD *v5; // rbx
  _QWORD *v6; // rdi
  unsigned int i; // edi
  CMtfPredictionCandidate *v8; // rax
  CMtfPredictionCandidate *v9; // rbx
  __int64 result; // rax
  CMtfPredictionCandidate *v11; // rax
  char v12; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+18h] BYREF
  CMtfPredictionCandidate *v14; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    v13 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &v13, 4);
    if ( v4 < 0 )
      goto LABEL_17;
    v5 = (_QWORD *)*((_QWORD *)this + 1);
    v6 = (_QWORD *)*((_QWORD *)this + 2);
    while ( v5 != v6 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
      ++v5;
    }
    *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
    for ( i = 0; ; ++i )
    {
      if ( i >= v13 )
        goto LABEL_17;
      v12 = 0;
      v4 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64))(*(_QWORD *)a2 + 24LL))(a2, &v12, 1);
      if ( v4 < 0 )
        goto LABEL_17;
      if ( !v12 )
        break;
      v8 = (CMtfPredictionCandidate *)operator new(0x98u);
      if ( v8 )
        v9 = CMtfPredictionCandidate::CMtfPredictionCandidate(v8);
      else
        v9 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*((_QWORD *)v9 + 5) + 40LL))((__int64)v9 + 40, a2);
      if ( v4 < 0 )
      {
        if ( !v9 )
          goto LABEL_17;
        goto LABEL_16;
      }
      if ( v9 )
        v9 = (CMtfPredictionCandidate *)((char *)v9 + 8);
LABEL_21:
      v14 = v9;
      std::vector<IMtfSuggestionListElement *>::push_back((char *)this + 8, &v14);
    }
    v11 = (CMtfPredictionCandidate *)operator new(0x50u);
    v9 = v11;
    if ( v11 )
    {
      *(_QWORD *)v11 = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'};
      *((_QWORD *)v11 + 1) = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'};
      *((_QWORD *)v11 + 2) = &MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'};
      *((_QWORD *)v11 + 3) = &MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'};
      *((_QWORD *)v11 + 4) = 0;
      *((_QWORD *)v11 + 5) = 0;
      *((_QWORD *)v11 + 6) = 0;
      *((_QWORD *)v11 + 7) = 1;
      *((_QWORD *)v11 + 8) = 0;
      *((_DWORD *)v11 + 18) = -65536;
      *((_WORD *)v11 + 38) = -1;
      _InterlockedIncrement(&g_cRefDll);
    }
    v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*((_QWORD *)v11 + 3) + 40LL))((__int64)v11 + 24, a2);
    if ( v4 >= 0 )
      goto LABEL_21;
    if ( v9 )
LABEL_16:
      (*(void (__fastcall **)(CMtfPredictionCandidate *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_17:
    result = (unsigned int)v4;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800268e0  push    rbx
0x1800268e2  push    rsi
0x1800268e3  push    rdi
0x1800268e4  push    r14
0x1800268e6  push    r15
0x1800268e8  sub     rsp, 30h
0x1800268ec  mov     r15, rdx
0x1800268ef  mov     r14, rcx
0x1800268f2  mov     [rsp+58h+arg_10], 0
0x1800268fa  mov     rax, [rdx]
0x1800268fd  xor     r9d, r9d
0x180026900  lea     r8d, [r9+4]
0x180026904  lea     rdx, [rsp+58h+arg_10]
0x180026909  mov     rcx, r15
0x18002690c  mov     rax, [rax+18h]
0x180026910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026915  mov     esi, eax
0x180026917  test    eax, eax
0x180026919  js      loc_1800269CE
0x18002691f  mov     rbx, [r14+8]
0x180026923  mov     rdi, [r14+10h]
0x180026927  cmp     rbx, rdi
0x18002692a  jnz     loc_180026AAF
0x180026930  mov     rax, [r14+8]
0x180026934  mov     [r14+10h], rax
0x180026938  xor     edi, edi
0x18002693a  cmp     edi, [rsp+58h+arg_10]
0x18002693e  jnb     loc_1800269CE
0x180026944  mov     [rsp+58h+arg_8], 0
0x180026949  mov     rax, [r15]
0x18002694c  xor     r9d, r9d
0x18002694f  lea     r8d, [r9+1]
0x180026953  lea     rdx, [rsp+58h+arg_8]
0x180026958  mov     rcx, r15
0x18002695b  mov     rax, [rax+18h]
0x18002695f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026964  mov     esi, eax
0x180026966  test    eax, eax
0x180026968  js      short loc_1800269CE
0x18002696a  cmp     [rsp+58h+arg_8], 0
0x18002696f  jz      short loc_1800269E3
0x180026971  mov     ecx, 98h; Size
0x180026976  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002697b  test    rax, rax
0x18002697e  jz      short loc_18002698D
0x180026980  mov     rcx, rax; this
0x180026983  call    ??0CMtfPredictionCandidate@@QEAA@XZ; CMtfPredictionCandidate::CMtfPredictionCandidate(void)
0x180026988  mov     rbx, rax
0x18002698b  jmp     short loc_18002698F
0x18002698d  xor     ebx, ebx
0x18002698f  lea     rcx, [rbx+28h]
0x180026993  mov     rax, [rcx]
0x180026996  mov     rdx, r15
0x180026999  mov     rax, [rax+28h]
0x18002699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269a2  mov     esi, eax
0x1800269a4  test    eax, eax
0x1800269a6  js      short loc_1800269BA
0x1800269a8  test    rbx, rbx
0x1800269ab  jz      loc_180026A78
0x1800269b1  add     rbx, 8
0x1800269b5  jmp     loc_180026A78
0x1800269ba  test    rbx, rbx
0x1800269bd  jz      short loc_1800269CE
0x1800269bf  mov     rax, [rbx]
0x1800269c2  mov     rcx, rbx
0x1800269c5  mov     rax, [rax+10h]
0x1800269c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ce  mov     eax, esi
0x1800269d0  jmp     short loc_1800269D7
0x1800269d2  mov     eax, 80004005h
0x1800269d7  add     rsp, 30h
0x1800269db  pop     r15
0x1800269dd  pop     r14
0x1800269df  pop     rdi
0x1800269e0  pop     rsi
0x1800269e1  pop     rbx
0x1800269e2  retn
0x1800269e3  mov     ecx, 50h ; 'P'; Size
0x1800269e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800269ed  mov     rbx, rax
0x1800269f0  test    rbx, rbx
0x1800269f3  jz      short loc_180026A5F
0x1800269f5  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionListElement@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'}
0x1800269fc  mov     [rbx], rax
0x1800269ff  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionCandidatePrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'}
0x180026a06  mov     [rbx+8], rax
0x180026a0a  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfPrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'}
0x180026a11  mov     [rbx+10h], rax
0x180026a15  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSerializable@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'}
0x180026a1c  mov     [rbx+18h], rax
0x180026a20  mov     qword ptr [rbx+20h], 0
0x180026a28  mov     qword ptr [rbx+28h], 0
0x180026a30  mov     qword ptr [rbx+30h], 0
0x180026a38  mov     qword ptr [rbx+38h], 1
0x180026a40  mov     qword ptr [rbx+40h], 0
0x180026a48  mov     dword ptr [rbx+48h], 0FFFF0000h
0x180026a4f  mov     eax, 0FFFFh
0x180026a54  mov     [rbx+4Ch], ax
0x180026a58  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180026a5f  lea     rcx, [rbx+18h]
0x180026a63  mov     rax, [rcx]
0x180026a66  mov     rdx, r15
0x180026a69  mov     rax, [rax+28h]
0x180026a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a72  mov     esi, eax
0x180026a74  test    eax, eax
0x180026a76  js      short loc_180026A92
0x180026a78  mov     [rsp+58h+arg_18], rbx
0x180026a7d  lea     rdx, [rsp+58h+arg_18]
0x180026a82  lea     rcx, [r14+8]
0x180026a86  call    ?push_back@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@QEAAXAEBQEAUIMtfSuggestionListElement@@@Z; std::vector<IMtfSuggestionListElement *>::push_back(IMtfSuggestionListElement * const &)
0x180026a8b  inc     edi
0x180026a8d  jmp     loc_18002693A
0x180026a92  test    rbx, rbx
0x180026a95  jz      loc_1800269CE
0x180026a9b  mov     rax, [rbx]
0x180026a9e  mov     rcx, rbx
0x180026aa1  mov     rax, [rax+10h]
0x180026aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aaa  jmp     loc_1800269CE
0x180026aaf  mov     rcx, [rbx]
0x180026ab2  mov     rax, [rcx]
0x180026ab5  mov     rax, [rax+10h]
0x180026ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026abe  add     rbx, 8
0x180026ac2  jmp     loc_180026927
```
